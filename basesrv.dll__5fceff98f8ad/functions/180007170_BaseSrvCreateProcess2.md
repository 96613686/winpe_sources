# BaseSrvCreateProcess2

- ea: `0x180007170`
- end: `0x18000750f`
- name: `BaseSrvCreateProcess2`
- size: `927`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008000`

## callees

- `0x180007170`
- `0x180007580`
- `0x18000a2f8`
- `0x18000c678`

## import_xrefs

- `ntdll!NtClose` at `0x180007484`
- `ntdll!NtClose` at `0x1800074c9`
- `ntdll!NtClose` at `0x180007484`
- `ntdll!NtClose` at `0x1800074c9`
- `ntdll!NtQueryInformationProcess` at `0x180007279`
- `ntdll!NtQueryInformationProcess` at `0x1800072d1`
- `ntdll!NtQueryInformationProcess` at `0x180007303`
- `ntdll!NtQueryInformationProcess` at `0x180007279`
- `ntdll!NtQueryInformationProcess` at `0x1800072d1`
- `ntdll!NtQueryInformationProcess` at `0x180007303`
- `ntdll!RtlEnterCriticalSection` at `0x180007418`
- `ntdll!RtlEnterCriticalSection` at `0x180007418`
- `ntdll!RtlLeaveCriticalSection` at `0x18000746f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000746f`
- `ntdll!NtOpenProcess` at `0x18000723e`
- `ntdll!NtOpenProcess` at `0x18000723e`
- `ntdll!NtOpenThread` at `0x18000733b`
- `ntdll!NtOpenThread` at `0x18000733b`

## pseudocode

```c
__int64 __fastcall BaseSrvCreateProcess2(__int64 a1, _DWORD *a2)
{
  int v3; // r12d
  __int64 v4; // rax
  struct _CLIENT_ID *v5; // r15
  int v6; // esi
  int v7; // r14d
  __int64 v8; // r13
  ACCESS_MASK v9; // eax
  ACCESS_MASK v10; // edx
  NTSTATUS updated; // ebx
  int v12; // r9d
  int Process; // eax
  int v14; // ecx
  int v15; // esi
  __int64 v16; // rdi
  void *v17; // r14
  _QWORD *v18; // rax
  int v19; // eax
  int v21; // [rsp+48h] [rbp-59h]
  __int64 ProcessInformation; // [rsp+68h] [rbp-39h] BYREF
  unsigned __int64 v23; // [rsp+70h] [rbp-31h] BYREF
  unsigned __int64 v24; // [rsp+78h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-21h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+108h] [rbp+67h] BYREF
  _DWORD *v27; // [rsp+110h] [rbp+6Fh]
  void *ProcessHandle; // [rsp+118h] [rbp+77h] BYREF
  void *ThreadHandle; // [rsp+120h] [rbp+7Fh] BYREF

  v27 = a2;
  v3 = *(_DWORD *)(a1 + 64);
  v4 = *(_QWORD *)(a1 + 72);
  v5 = (struct _CLIENT_ID *)(a1 + 80);
  ProcessHandle = 0;
  ThreadHandle = 0;
  ProcessInformation = 0;
  v24 = 0;
  v23 = 0;
  *(_QWORD *)(a1 + 64) = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (v4 & 3) != 0 )
  {
    v6 = v4 & 1;
    if ( (v4 & 2) != 0 )
    {
      v7 = 1;
      goto LABEL_6;
    }
  }
  else
  {
    v6 = 0;
  }
  v7 = 0;
LABEL_6:
  *(_QWORD *)(a1 + 72) = 0;
  v8 = *((_QWORD *)NtCurrentTeb()->CsrClientThread + 7);
  v9 = 1055744;
  ObjectAttributes.RootDirectory = 0;
  if ( !v7 )
    v9 = 0x1FFFFF;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = 0;
  v10 = 1062912;
  if ( !v7 )
    v10 = 0x1FFFFF;
  DesiredAccess = v9;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  updated = NtOpenProcess(&ProcessHandle, v10, &ObjectAttributes, v5);
  if ( updated < 0 )
  {
    ProcessHandle = 0;
    goto LABEL_42;
  }
  updated = NtQueryInformationProcess(ProcessHandle, ProcessIoPriority|ProcessUserModeIOPL, &ProcessInformation, 8u, 0);
  if ( updated >= 0 )
  {
    if ( (ProcessInformation & 1) != 0 )
    {
      updated = -1073741790;
      goto LABEL_40;
    }
    if ( (ProcessInformation & 0xFFFFFFFFFFFFFFFCuLL) != *(_QWORD *)v8 )
    {
      updated = -1073741790;
      goto LABEL_40;
    }
    updated = NtQueryInformationProcess(*(HANDLE *)(v8 + 80), ProcessLUIDDeviceMapsEnabled|0x40, &v24, 8u, 0);
    if ( updated >= 0 )
    {
      updated = NtQueryInformationProcess(ProcessHandle, ProcessLUIDDeviceMapsEnabled|0x40, &v23, 8u, 0);
      if ( updated >= 0 )
      {
        if ( v24 >= v23 )
        {
          updated = -1073741790;
          goto LABEL_40;
        }
        updated = NtOpenThread(&ThreadHandle, DesiredAccess, &ObjectAttributes, v5);
        if ( updated < 0 )
        {
          ThreadHandle = 0;
          goto LABEL_40;
        }
        v12 = *(_DWORD *)(a1 + 100);
        v21 = *(_DWORD *)(a1 + 96);
        DesiredAccess = 1;
        Process = InternalBaseSrvCreateProcess(
                    v7,
                    v6,
                    v3 & 3,
                    v12,
                    v8,
                    ProcessHandle,
                    (__int64)ThreadHandle,
                    (__int64)v5,
                    v21,
                    a1,
                    (__int64)&DesiredAccess);
        updated = Process;
        if ( !DesiredAccess )
        {
          ProcessHandle = 0;
          ThreadHandle = 0;
        }
        if ( Process == -1073741749 )
        {
          *v27 = 2;
          goto LABEL_40;
        }
        if ( Process >= 0 )
        {
          v14 = *(_DWORD *)(a1 + 100);
          if ( v14 )
          {
            updated = BaseSrvUpdateVDMSequenceNumber(
                        v14,
                        *(_QWORD *)(a1 + 112),
                        *(_DWORD *)(a1 + 104),
                        v5->UniqueProcess,
                        *(_QWORD *)(a1 + 8));
            if ( updated < 0 )
            {
              v15 = *(_DWORD *)(a1 + 104);
              v16 = *(_QWORD *)(a1 + 112);
              v17 = 0;
              RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
              if ( v16 )
              {
                v18 = DOSHead;
                if ( DOSHead )
                {
                  while ( v18[1] != v16 )
                  {
                    v18 = (_QWORD *)*v18;
                    if ( !v18 )
                      goto LABEL_36;
                  }
                  goto LABEL_49;
                }
              }
              else if ( v15 )
              {
                v18 = DOSHead;
                if ( DOSHead )
                {
                  while ( v18[1] || *((_DWORD *)v18 + 13) != v15 )
                  {
                    v18 = (_QWORD *)*v18;
                    if ( !v18 )
                      goto LABEL_36;
                  }
LABEL_49:
                  v17 = v18;
                  v19 = 0;
                  goto LABEL_37;
                }
              }
LABEL_36:
              v19 = -1073741811;
LABEL_37:
              if ( v19 >= 0 )
                BaseSrvExitVDMWorker(v17);
              RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
            }
          }
        }
      }
    }
  }
LABEL_40:
  if ( ProcessHandle )
    NtClose(ProcessHandle);
LABEL_42:
  if ( ThreadHandle )
    NtClose(ThreadHandle);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180007170  mov     rax, rsp
0x180007173  mov     [rax+10h], rdx
0x180007177  push    rbp
0x180007178  push    rbx
0x180007179  lea     rbp, [rax-5Fh]
0x18000717d  sub     rsp, 0E8h
0x180007184  mov     [rax-18h], rsi
0x180007188  xor     edx, edx
0x18000718a  mov     [rax-20h], rdi
0x18000718e  xorps   xmm0, xmm0
0x180007191  mov     [rax-28h], r12
0x180007195  mov     rdi, rcx
0x180007198  mov     r12d, [rcx+40h]
0x18000719c  mov     [rax-30h], r13
0x1800071a0  mov     [rax-38h], r14
0x1800071a4  mov     [rax-40h], r15
0x1800071a8  xor     eax, eax
0x1800071aa  mov     rax, [rcx+48h]
0x1800071ae  lea     r15, [rcx+50h]
0x1800071b2  mov     [rbp+57h+ProcessHandle], rdx
0x1800071b6  mov     [rbp+57h+ThreadHandle], rdx
0x1800071ba  mov     [rbp+57h+ProcessInformation], rdx
0x1800071be  mov     [rbp+57h+var_80], rdx
0x1800071c2  mov     [rbp+57h+var_88], rdx
0x1800071c6  mov     [rcx+40h], rdx
0x1800071ca  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800071ce  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800071d2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800071d6  test    al, 3
0x1800071d8  jz      short loc_1800071EB
0x1800071da  mov     esi, eax
0x1800071dc  and     esi, 1
0x1800071df  test    al, 2
0x1800071e1  jz      short loc_1800071ED
0x1800071e3  mov     r14d, 1
0x1800071e9  jmp     short loc_1800071F0
0x1800071eb  mov     esi, edx
0x1800071ed  mov     r14d, edx
0x1800071f0  mov     [rcx+48h], rdx
0x1800071f4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800071f8  mov     rax, gs:70h
0x180007201  mov     ecx, 1FFFFFh
0x180007206  test    r14d, r14d
0x180007209  mov     r9, r15; ClientId
0x18000720c  mov     r13, [rax+38h]
0x180007210  mov     eax, 101C00h
0x180007215  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdx
0x180007219  cmovz   eax, ecx
0x18000721c  mov     [rbp+57h+ObjectAttributes.Attributes], edx
0x18000721f  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x180007223  mov     edx, 103800h
0x180007228  cmovz   edx, ecx; DesiredAccess
0x18000722b  mov     [rbp+57h+DesiredAccess], eax
0x18000722e  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180007232  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180007239  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000723e  call    cs:__imp_NtOpenProcess
0x180007245  nop     dword ptr [rax+rax+00h]
0x18000724a  mov     ebx, eax
0x18000724c  test    eax, eax
0x18000724e  jns     short loc_18000725D
0x180007250  mov     [rbp+57h+ProcessHandle], 0
0x180007258  jmp     loc_180007490
0x18000725d  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180007261  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x180007265  mov     r9d, 8; ProcessInformationLength
0x18000726b  mov     [rsp+0F0h+ReturnLength], 0; ReturnLength
0x180007274  mov     edx, 31h ; '1'; ProcessInformationClass
0x180007279  call    cs:__imp_NtQueryInformationProcess
0x180007280  nop     dword ptr [rax+rax+00h]
0x180007285  mov     ebx, eax
0x180007287  test    eax, eax
0x180007289  js      loc_18000747B
0x18000728f  mov     rax, [rbp+57h+ProcessInformation]
0x180007293  test    al, 1
0x180007295  jz      short loc_1800072A1
0x180007297  mov     ebx, 0C0000022h
0x18000729c  jmp     loc_18000747B
0x1800072a1  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800072a5  cmp     rax, [r13+0]
0x1800072a9  jz      short loc_1800072B5
0x1800072ab  mov     ebx, 0C0000022h
0x1800072b0  jmp     loc_18000747B
0x1800072b5  mov     rcx, [r13+50h]; ProcessHandle
0x1800072b9  lea     r8, [rbp+57h+var_80]; ProcessInformation
0x1800072bd  mov     r9d, 8; ProcessInformationLength
0x1800072c3  mov     [rsp+0F0h+ReturnLength], 0; ReturnLength
0x1800072cc  mov     edx, 5Ch ; '\'; ProcessInformationClass
0x1800072d1  call    cs:__imp_NtQueryInformationProcess
0x1800072d8  nop     dword ptr [rax+rax+00h]
0x1800072dd  mov     ebx, eax
0x1800072df  test    eax, eax
0x1800072e1  js      loc_18000747B
0x1800072e7  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1800072eb  lea     r8, [rbp+57h+var_88]; ProcessInformation
0x1800072ef  mov     r9d, 8; ProcessInformationLength
0x1800072f5  mov     [rsp+0F0h+ReturnLength], 0; ReturnLength
0x1800072fe  mov     edx, 5Ch ; '\'; ProcessInformationClass
0x180007303  call    cs:__imp_NtQueryInformationProcess
0x18000730a  nop     dword ptr [rax+rax+00h]
0x18000730f  mov     ebx, eax
0x180007311  test    eax, eax
0x180007313  js      loc_18000747B
0x180007319  mov     rax, [rbp+57h+var_88]
0x18000731d  cmp     [rbp+57h+var_80], rax
0x180007321  jb      short loc_18000732D
0x180007323  mov     ebx, 0C0000022h
0x180007328  jmp     loc_18000747B
0x18000732d  mov     edx, [rbp+57h+DesiredAccess]; DesiredAccess
0x180007330  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180007334  mov     r9, r15; ClientId
0x180007337  lea     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x18000733b  call    cs:__imp_NtOpenThread
0x180007342  nop     dword ptr [rax+rax+00h]
0x180007347  mov     ebx, eax
0x180007349  test    eax, eax
0x18000734b  jns     short loc_18000735A
0x18000734d  mov     [rbp+57h+ThreadHandle], 0
0x180007355  jmp     loc_18000747B
0x18000735a  mov     r9d, [rdi+64h]; int
0x18000735e  lea     rax, [rbp+57h+DesiredAccess]
0x180007362  mov     [rsp+50h], rax; __int64
0x180007367  and     r12d, 3
0x18000736b  mov     eax, [rdi+60h]
0x18000736e  mov     r8d, r12d; int
0x180007371  mov     [rsp+0F0h+var_A8], rdi; __int64
0x180007376  mov     edx, esi; int
0x180007378  mov     [rsp+0F0h+var_B0], eax; int
0x18000737c  mov     ecx, r14d; int
0x18000737f  mov     rax, [rbp+57h+ThreadHandle]
0x180007383  mov     [rsp+0F0h+var_B8], r15; __int64
0x180007388  mov     [rsp+0F0h+var_C0], rax; __int64
0x18000738d  mov     rax, [rbp+57h+ProcessHandle]
0x180007391  mov     [rsp+0F0h+var_C8], rax; ProcessHandle
0x180007396  mov     [rsp+0F0h+ReturnLength], r13; __int64
0x18000739b  mov     [rbp+57h+DesiredAccess], 1
0x1800073a2  call    InternalBaseSrvCreateProcess
0x1800073a7  cmp     [rbp+57h+DesiredAccess], 0
0x1800073ab  mov     ebx, eax
0x1800073ad  jnz     short loc_1800073BF
0x1800073af  mov     [rbp+57h+ProcessHandle], 0
0x1800073b7  mov     [rbp+57h+ThreadHandle], 0
0x1800073bf  cmp     eax, 0C000004Bh
0x1800073c4  jnz     short loc_1800073D5
0x1800073c6  mov     rax, [rbp+57h+arg_8]
0x1800073ca  mov     dword ptr [rax], 2
0x1800073d0  jmp     loc_18000747B
0x1800073d5  test    eax, eax
0x1800073d7  js      loc_18000747B
0x1800073dd  mov     ecx, [rdi+64h]
0x1800073e0  test    ecx, ecx
0x1800073e2  jz      loc_18000747B
0x1800073e8  mov     rax, [rdi+8]
0x1800073ec  mov     r9, [r15]
0x1800073ef  mov     r8d, [rdi+68h]
0x1800073f3  mov     rdx, [rdi+70h]
0x1800073f7  mov     [rsp+0F0h+ReturnLength], rax
0x1800073fc  call    BaseSrvUpdateVDMSequenceNumber
0x180007401  mov     ebx, eax
0x180007403  test    eax, eax
0x180007405  jns     short loc_18000747B
0x180007407  mov     esi, [rdi+68h]
0x18000740a  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180007411  mov     rdi, [rdi+70h]
0x180007415  xor     r14d, r14d
0x180007418  call    cs:__imp_RtlEnterCriticalSection
0x18000741f  nop     dword ptr [rax+rax+00h]
0x180007424  test    rdi, rdi
0x180007427  jnz     loc_1800074E2
0x18000742d  test    esi, esi
0x18000742f  jz      short loc_180007457
0x180007431  mov     rax, cs:DOSHead
0x180007438  test    rax, rax
0x18000743b  jz      short loc_180007457
0x18000743d  nop     dword ptr [rax]
0x180007440  cmp     [rax+8], r14
0x180007444  jnz     short loc_18000744F
0x180007446  cmp     [rax+34h], esi
0x180007449  jz      loc_180007505
0x18000744f  mov     rax, [rax]
0x180007452  test    rax, rax
0x180007455  jnz     short loc_180007440
0x180007457  mov     eax, 0C000000Dh
0x18000745c  test    eax, eax
0x18000745e  js      short loc_180007468
0x180007460  mov     rcx, r14; P
0x180007463  call    BaseSrvExitVDMWorker
0x180007468  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000746f  call    cs:__imp_RtlLeaveCriticalSection
0x180007476  nop     dword ptr [rax+rax+00h]
0x18000747b  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x18000747f  test    rcx, rcx
0x180007482  jz      short loc_180007490
0x180007484  call    cs:__imp_NtClose
0x18000748b  nop     dword ptr [rax+rax+00h]
0x180007490  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x180007494  mov     r15, [rsp+0F0h+var_38]
0x18000749c  mov     r14, [rsp+0F0h+var_30]
0x1800074a4  mov     r13, [rsp+0F0h+var_28]
0x1800074ac  mov     r12, [rsp+0F0h+var_20]
0x1800074b4  mov     rdi, [rsp+0F0h+var_18]
0x1800074bc  mov     rsi, [rsp+0E0h]
0x1800074c4  test    rcx, rcx
0x1800074c7  jz      short loc_1800074D5
0x1800074c9  call    cs:__imp_NtClose
0x1800074d0  nop     dword ptr [rax+rax+00h]
0x1800074d5  mov     eax, ebx
0x1800074d7  add     rsp, 0E8h
0x1800074de  pop     rbx
0x1800074df  pop     rbp
0x1800074e0  retn
0x1800074e2  mov     rax, cs:DOSHead
0x1800074e9  test    rax, rax
0x1800074ec  jz      loc_180007457
0x1800074f2  cmp     [rax+8], rdi
0x1800074f6  jz      short loc_180007505
0x1800074f8  mov     rax, [rax]
0x1800074fb  test    rax, rax
0x1800074fe  jnz     short loc_1800074F2
0x180007500  jmp     loc_180007457
0x180007505  mov     r14, rax
0x180007508  xor     eax, eax
0x18000750a  jmp     loc_18000745C
```
