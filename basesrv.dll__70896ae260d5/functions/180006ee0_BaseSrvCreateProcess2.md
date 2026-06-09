# BaseSrvCreateProcess2

- ea: `0x180006ee0`
- end: `0x180007210`
- name: `BaseSrvCreateProcess2`
- size: `816`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007cf0`

## callees

- `0x180006ee0`
- `0x180007280`
- `0x18000a014`
- `0x18000c2a4`

## import_xrefs

- `ntdll!NtClose` at `0x1800071d8`
- `ntdll!NtClose` at `0x1800071ed`
- `ntdll!NtClose` at `0x1800071d8`
- `ntdll!NtClose` at `0x1800071ed`
- `ntdll!NtQueryInformationProcess` at `0x180006fc6`
- `ntdll!NtQueryInformationProcess` at `0x18000701d`
- `ntdll!NtQueryInformationProcess` at `0x18000704e`
- `ntdll!NtQueryInformationProcess` at `0x180006fc6`
- `ntdll!NtQueryInformationProcess` at `0x18000701d`
- `ntdll!NtQueryInformationProcess` at `0x18000704e`
- `ntdll!RtlEnterCriticalSection` at `0x180007164`
- `ntdll!RtlEnterCriticalSection` at `0x180007164`
- `ntdll!RtlLeaveCriticalSection` at `0x1800071c3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800071c3`
- `ntdll!NtOpenProcess` at `0x180006f8c`
- `ntdll!NtOpenProcess` at `0x180006f8c`
- `ntdll!NtOpenThread` at `0x180007093`
- `ntdll!NtOpenThread` at `0x180007093`

## pseudocode

```c
__int64 __fastcall BaseSrvCreateProcess2(__int64 a1, _DWORD *a2)
{
  BOOL v3; // r14d
  int v4; // esi
  _QWORD *v5; // r15
  __int64 v6; // rax
  int v7; // r12d
  ACCESS_MASK v8; // edx
  __int64 v9; // r13
  NTSTATUS Process; // ebx
  ACCESS_MASK v11; // edx
  int v12; // r9d
  int v13; // ecx
  int v14; // esi
  __int64 v15; // rdi
  _QWORD *v16; // rcx
  int v18; // [rsp+40h] [rbp-59h]
  __int64 ProcessInformation; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int64 v21; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  __int64 v23; // [rsp+100h] [rbp+67h] BYREF
  _DWORD *v24; // [rsp+108h] [rbp+6Fh]
  void *ProcessHandle; // [rsp+110h] [rbp+77h] BYREF
  void *ThreadHandle; // [rsp+118h] [rbp+7Fh] BYREF

  v24 = a2;
  ProcessHandle = 0;
  v3 = 0;
  ThreadHandle = 0;
  v4 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v5 = (_QWORD *)(a1 + 80);
  v6 = *(_QWORD *)(a1 + 72);
  v7 = *(_DWORD *)(a1 + 64) & 3;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ProcessInformation = 0;
  v21 = 0;
  v20 = 0;
  *(_QWORD *)(a1 + 64) = 0;
  if ( (v6 & 3) != 0 )
  {
    v4 = v6 & 1;
    v3 = (v6 & 2) != 0;
  }
  *(_QWORD *)(a1 + 72) = 0;
  v8 = 1062912;
  v9 = *((_QWORD *)NtCurrentTeb()->CsrClientThread + 7);
  ObjectAttributes.RootDirectory = 0;
  if ( !v3 )
    v8 = 0x1FFFFF;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = 0;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Process = NtOpenProcess(&ProcessHandle, v8, &ObjectAttributes, (PCLIENT_ID)(a1 + 80));
  if ( Process < 0 )
  {
    ProcessHandle = 0;
    goto LABEL_42;
  }
  Process = NtQueryInformationProcess(ProcessHandle, ProcessIoPriority|ProcessUserModeIOPL, &ProcessInformation, 8u, 0);
  if ( Process >= 0 )
  {
    if ( (ProcessInformation & 1) != 0 )
    {
      Process = -1073741790;
      goto LABEL_40;
    }
    if ( (ProcessInformation & 0xFFFFFFFFFFFFFFFCuLL) != *(_QWORD *)v9 )
    {
      Process = -1073741790;
      goto LABEL_40;
    }
    Process = NtQueryInformationProcess(*(HANDLE *)(v9 + 80), ProcessLUIDDeviceMapsEnabled|0x40, &v21, 8u, 0);
    if ( Process >= 0 )
    {
      Process = NtQueryInformationProcess(ProcessHandle, ProcessLUIDDeviceMapsEnabled|0x40, &v20, 8u, 0);
      if ( Process >= 0 )
      {
        if ( v21 >= v20 )
        {
          Process = -1073741790;
          goto LABEL_40;
        }
        v11 = 1055744;
        if ( !v3 )
          v11 = 0x1FFFFF;
        Process = NtOpenThread(&ThreadHandle, v11, &ObjectAttributes, (PCLIENT_ID)(a1 + 80));
        if ( Process < 0 )
        {
          ThreadHandle = 0;
          goto LABEL_40;
        }
        v12 = *(_DWORD *)(a1 + 100);
        v18 = *(_DWORD *)(a1 + 96);
        LODWORD(v23) = 1;
        Process = InternalBaseSrvCreateProcess(
                    v3,
                    v4,
                    v7,
                    v12,
                    v9,
                    ProcessHandle,
                    (__int64)ThreadHandle,
                    a1 + 80,
                    v18,
                    a1,
                    (__int64)&v23);
        if ( !(_DWORD)v23 )
        {
          ProcessHandle = 0;
          ThreadHandle = 0;
        }
        if ( Process == -1073741749 )
        {
          *v24 = 2;
          goto LABEL_40;
        }
        if ( Process >= 0 )
        {
          v13 = *(_DWORD *)(a1 + 100);
          if ( v13 )
          {
            Process = BaseSrvUpdateVDMSequenceNumber(
                        v13,
                        *(_QWORD *)(a1 + 112),
                        *(_DWORD *)(a1 + 104),
                        *v5,
                        *(_QWORD *)(a1 + 8));
            if ( Process < 0 )
            {
              v14 = *(_DWORD *)(a1 + 104);
              v15 = *(_QWORD *)(a1 + 112);
              RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
              if ( v15 )
              {
                v16 = DOSHead;
                if ( !DOSHead )
                {
LABEL_39:
                  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
                  goto LABEL_40;
                }
                while ( v16[1] != v15 )
                {
                  v16 = (_QWORD *)*v16;
                  if ( !v16 )
                    goto LABEL_39;
                }
              }
              else
              {
                if ( !v14 )
                  goto LABEL_39;
                v16 = DOSHead;
                if ( !DOSHead )
                  goto LABEL_39;
                while ( v16[1] || *((_DWORD *)v16 + 13) != v14 )
                {
                  v16 = (_QWORD *)*v16;
                  if ( !v16 )
                    goto LABEL_39;
                }
              }
              BaseSrvExitVDMWorker(v16);
              goto LABEL_39;
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
  return (unsigned int)Process;
}

```

## disassembly

```asm
0x180006ee0  mov     [rsp-8+arg_8], rdx
0x180006ee5  push    rbp
0x180006ee6  push    rbx
0x180006ee7  push    rsi
0x180006ee8  push    rdi
0x180006ee9  push    r12
0x180006eeb  push    r13
0x180006eed  push    r14
0x180006eef  push    r15
0x180006ef1  lea     rbp, [rsp-1Fh]
0x180006ef6  sub     rsp, 0B8h
0x180006efd  mov     rdi, rcx
0x180006f00  xor     ecx, ecx
0x180006f02  mov     [rbp+57h+ProcessHandle], rcx
0x180006f06  mov     r14d, ecx
0x180006f09  mov     [rbp+57h+ThreadHandle], rcx
0x180006f0d  mov     esi, ecx
0x180006f0f  mov     dword ptr [rbp+57h+ObjectAttributes+4], ecx
0x180006f12  mov     r12d, [rdi+40h]
0x180006f16  lea     r15, [rdi+50h]
0x180006f1a  mov     rax, [rdi+48h]
0x180006f1e  and     r12d, 3
0x180006f22  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], ecx
0x180006f25  mov     [rbp+57h+ProcessInformation], rcx
0x180006f29  mov     [rbp+57h+var_80], rcx
0x180006f2d  mov     [rbp+57h+var_88], rcx
0x180006f31  mov     [rdi+40h], rcx
0x180006f35  test    al, 3
0x180006f37  jz      short loc_180006F46
0x180006f39  mov     esi, eax
0x180006f3b  and     esi, 1
0x180006f3e  test    al, 2
0x180006f40  jz      short loc_180006F46
0x180006f42  lea     r14d, [rcx+1]
0x180006f46  mov     [rdi+48h], rcx
0x180006f4a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006f4e  mov     rax, gs:70h
0x180006f57  mov     edx, 103800h
0x180006f5c  xorps   xmm0, xmm0
0x180006f5f  test    r14d, r14d
0x180006f62  mov     r9, r15; ClientId
0x180006f65  mov     r13, [rax+38h]
0x180006f69  mov     eax, 1FFFFFh
0x180006f6e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x180006f72  cmovz   edx, eax; DesiredAccess
0x180006f75  mov     [rbp+57h+ObjectAttributes.Attributes], ecx
0x180006f78  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x180006f7c  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180006f80  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180006f87  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006f8c  call    cs:__imp_NtOpenProcess
0x180006f93  nop     dword ptr [rax+rax+00h]
0x180006f98  mov     ebx, eax
0x180006f9a  test    eax, eax
0x180006f9c  jns     short loc_180006FAB
0x180006f9e  mov     [rbp+57h+ProcessHandle], 0
0x180006fa6  jmp     loc_1800071E4
0x180006fab  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180006faf  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x180006fb3  mov     r9d, 8; ProcessInformationLength
0x180006fb9  mov     [rsp+0F0h+ReturnLength], 0; ReturnLength
0x180006fc2  lea     edx, [r9+29h]; ProcessInformationClass
0x180006fc6  call    cs:__imp_NtQueryInformationProcess
0x180006fcd  nop     dword ptr [rax+rax+00h]
0x180006fd2  mov     ebx, eax
0x180006fd4  test    eax, eax
0x180006fd6  js      loc_1800071CF
0x180006fdc  mov     rax, [rbp+57h+ProcessInformation]
0x180006fe0  test    al, 1
0x180006fe2  jz      short loc_180006FEE
0x180006fe4  mov     ebx, 0C0000022h
0x180006fe9  jmp     loc_1800071CF
0x180006fee  and     rax, 0FFFFFFFFFFFFFFFCh
0x180006ff2  cmp     rax, [r13+0]
0x180006ff6  jz      short loc_180007002
0x180006ff8  mov     ebx, 0C0000022h
0x180006ffd  jmp     loc_1800071CF
0x180007002  mov     rcx, [r13+50h]; ProcessHandle
0x180007006  lea     r8, [rbp+57h+var_80]; ProcessInformation
0x18000700a  mov     r9d, 8; ProcessInformationLength
0x180007010  mov     [rsp+0F0h+ReturnLength], 0; ReturnLength
0x180007019  lea     edx, [r9+54h]; ProcessInformationClass
0x18000701d  call    cs:__imp_NtQueryInformationProcess
0x180007024  nop     dword ptr [rax+rax+00h]
0x180007029  mov     ebx, eax
0x18000702b  test    eax, eax
0x18000702d  js      loc_1800071CF
0x180007033  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180007037  lea     r8, [rbp+57h+var_88]; ProcessInformation
0x18000703b  mov     r9d, 8; ProcessInformationLength
0x180007041  mov     [rsp+0F0h+ReturnLength], 0; ReturnLength
0x18000704a  lea     edx, [r9+54h]; ProcessInformationClass
0x18000704e  call    cs:__imp_NtQueryInformationProcess
0x180007055  nop     dword ptr [rax+rax+00h]
0x18000705a  mov     ebx, eax
0x18000705c  test    eax, eax
0x18000705e  js      loc_1800071CF
0x180007064  mov     rax, [rbp+57h+var_88]
0x180007068  cmp     [rbp+57h+var_80], rax
0x18000706c  jb      short loc_180007078
0x18000706e  mov     ebx, 0C0000022h
0x180007073  jmp     loc_1800071CF
0x180007078  mov     edx, 101C00h
0x18000707d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180007081  mov     eax, 1FFFFFh
0x180007086  lea     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x18000708a  test    r14d, r14d
0x18000708d  mov     r9, r15; ClientId
0x180007090  cmovz   edx, eax; DesiredAccess
0x180007093  call    cs:__imp_NtOpenThread
0x18000709a  nop     dword ptr [rax+rax+00h]
0x18000709f  mov     ebx, eax
0x1800070a1  test    eax, eax
0x1800070a3  jns     short loc_1800070B2
0x1800070a5  mov     [rbp+57h+ThreadHandle], 0
0x1800070ad  jmp     loc_1800071CF
0x1800070b2  mov     r9d, [rdi+64h]; int
0x1800070b6  lea     rax, [rbp+57h+arg_0]
0x1800070ba  mov     [rsp+0F0h+var_A0], rax; __int64
0x1800070bf  mov     r8d, r12d; int
0x1800070c2  mov     eax, [rdi+60h]
0x1800070c5  mov     edx, esi; int
0x1800070c7  mov     [rsp+0F0h+var_A8], rdi; __int64
0x1800070cc  mov     ecx, r14d; int
0x1800070cf  mov     [rsp+0F0h+var_B0], eax; int
0x1800070d3  mov     rax, [rbp+57h+ThreadHandle]
0x1800070d7  mov     [rsp+0F0h+var_B8], r15; __int64
0x1800070dc  mov     [rsp+0F0h+var_C0], rax; __int64
0x1800070e1  mov     rax, [rbp+57h+ProcessHandle]
0x1800070e5  mov     [rsp+0F0h+var_C8], rax; ProcessHandle
0x1800070ea  mov     [rsp+0F0h+ReturnLength], r13; __int64
0x1800070ef  mov     dword ptr [rbp+57h+arg_0], 1
0x1800070f6  call    InternalBaseSrvCreateProcess
0x1800070fb  cmp     dword ptr [rbp+57h+arg_0], 0
0x1800070ff  mov     ebx, eax
0x180007101  jnz     short loc_18000710D
0x180007103  xor     eax, eax
0x180007105  mov     [rbp+57h+ProcessHandle], rax
0x180007109  mov     [rbp+57h+ThreadHandle], rax
0x18000710d  cmp     ebx, 0C000004Bh
0x180007113  jnz     short loc_180007124
0x180007115  mov     rax, [rbp+57h+arg_8]
0x180007119  mov     dword ptr [rax], 2
0x18000711f  jmp     loc_1800071CF
0x180007124  test    ebx, ebx
0x180007126  js      loc_1800071CF
0x18000712c  mov     ecx, [rdi+64h]
0x18000712f  test    ecx, ecx
0x180007131  jz      loc_1800071CF
0x180007137  mov     rax, [rdi+8]
0x18000713b  mov     r9, [r15]
0x18000713e  mov     r8d, [rdi+68h]
0x180007142  mov     rdx, [rdi+70h]
0x180007146  mov     [rsp+0F0h+ReturnLength], rax
0x18000714b  call    BaseSrvUpdateVDMSequenceNumber
0x180007150  mov     ebx, eax
0x180007152  test    eax, eax
0x180007154  jns     short loc_1800071CF
0x180007156  mov     esi, [rdi+68h]
0x180007159  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180007160  mov     rdi, [rdi+70h]
0x180007164  call    cs:__imp_RtlEnterCriticalSection
0x18000716b  nop     dword ptr [rax+rax+00h]
0x180007170  test    rdi, rdi
0x180007173  jnz     short loc_18000719B
0x180007175  test    esi, esi
0x180007177  jz      short loc_1800071BC
0x180007179  mov     rcx, cs:DOSHead; P
0x180007180  test    rcx, rcx
0x180007183  jz      short loc_1800071BC
0x180007185  cmp     qword ptr [rcx+8], 0
0x18000718a  jnz     short loc_180007191
0x18000718c  cmp     [rcx+34h], esi
0x18000718f  jz      short loc_1800071B7
0x180007191  mov     rcx, [rcx]
0x180007194  test    rcx, rcx
0x180007197  jnz     short loc_180007185
0x180007199  jmp     short loc_1800071BC
0x18000719b  mov     rcx, cs:DOSHead
0x1800071a2  test    rcx, rcx
0x1800071a5  jz      short loc_1800071BC
0x1800071a7  cmp     [rcx+8], rdi
0x1800071ab  jz      short loc_1800071B7
0x1800071ad  mov     rcx, [rcx]
0x1800071b0  test    rcx, rcx
0x1800071b3  jnz     short loc_1800071A7
0x1800071b5  jmp     short loc_1800071BC
0x1800071b7  call    BaseSrvExitVDMWorker
0x1800071bc  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x1800071c3  call    cs:__imp_RtlLeaveCriticalSection
0x1800071ca  nop     dword ptr [rax+rax+00h]
0x1800071cf  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x1800071d3  test    rcx, rcx
0x1800071d6  jz      short loc_1800071E4
0x1800071d8  call    cs:__imp_NtClose
0x1800071df  nop     dword ptr [rax+rax+00h]
0x1800071e4  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x1800071e8  test    rcx, rcx
0x1800071eb  jz      short loc_1800071F9
0x1800071ed  call    cs:__imp_NtClose
0x1800071f4  nop     dword ptr [rax+rax+00h]
0x1800071f9  mov     eax, ebx
0x1800071fb  add     rsp, 0B8h
0x180007202  pop     r15
0x180007204  pop     r14
0x180007206  pop     r13
0x180007208  pop     r12
0x18000720a  pop     rdi
0x18000720b  pop     rsi
0x18000720c  pop     rbx
0x18000720d  pop     rbp
0x18000720e  retn
```
