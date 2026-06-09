# GetAppSessionGuidsFromJob(void *,ulong *,_GUID * *)

- ea: `0x1800070d4`
- end: `0x1800073e1`
- name: `?GetAppSessionGuidsFromJob@@YAJPEAXPEAKPEAPEAU_GUID@@@Z`
- size: `781`
- prototype: `__int64 __fastcall(HANDLE JobHandle, unsigned int *, struct _GUID **)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f7d0`
- `0x18000fdd0`
- `0x1800109a0`

## callees

- `0x180001960`
- `0x180007018`
- `0x1800070d4`
- `0x18000bde0`
- `0x18000e9c4`
- `0x180011470`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007192`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000723d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007192`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000723d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000735a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000735a`
- `ntdll!NtOpenProcess` at `0x18000729c`
- `ntdll!NtOpenProcess` at `0x18000729c`
- `ntdll!NtIsProcessInJob` at `0x1800072af`
- `ntdll!NtIsProcessInJob` at `0x1800072af`
- `ntdll!NtClose` at `0x1800072de`
- `ntdll!NtClose` at `0x1800072de`
- `ntdll!NtQueryInformationJobObject` at `0x180007168`
- `ntdll!NtQueryInformationJobObject` at `0x1800071ff`
- `ntdll!NtQueryInformationJobObject` at `0x180007168`
- `ntdll!NtQueryInformationJobObject` at `0x1800071ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAppSessionGuidsFromJob(char *JobHandle, unsigned int *a2, struct _GUID **a3)
{
  unsigned int v5; // r15d
  int IsProcessInJob; // ebx
  unsigned int *p_JobInformation; // rsi
  signed int v8; // ebx
  struct _GUID *v9; // rdi
  unsigned int v10; // r14d
  signed int LastError; // eax
  int v13; // edx
  unsigned int v14; // r8d
  signed int v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  ULONG JobInformationLength; // [rsp+40h] [rbp-59h] BYREF
  void *ProcessHandle; // [rsp+48h] [rbp-51h] BYREF
  void **v20; // [rsp+50h] [rbp-49h] BYREF
  unsigned int *v21; // [rsp+58h] [rbp-41h]
  struct _GUID **v22; // [rsp+60h] [rbp-39h]
  _CLIENT_ID ClientId; // [rsp+68h] [rbp-31h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  __int128 JobInformation; // [rsp+A8h] [rbp+Fh] BYREF

  v22 = a3;
  JobInformationLength = 16;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v20 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
  v5 = 0;
  v21 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( (unsigned __int64)(JobHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    JobInformation = 0;
    DWORD1(JobInformation) = 1;
    IsProcessInJob = NtQueryInformationJobObject(
                       JobHandle,
                       JobObjectBasicProcessIdList,
                       &JobInformation,
                       0x10u,
                       &JobInformationLength);
    if ( IsProcessInJob == -2147483643 )
    {
      ProcessHandle = 0;
      if ( is_mul_ok(JobInformationLength, 1u) )
      {
        p_JobInformation = (unsigned int *)LocalAlloc(0x40u, JobInformationLength);
        v8 = p_JobInformation == 0 ? 0x8007000E : 0;
      }
      else
      {
        p_JobInformation = 0;
        v8 = -2147024362;
      }
      if ( p_JobInformation != v21 )
      {
        if ( v21 && !((unsigned __int8 (__fastcall *)(void ***))*v20)(&v20) )
          goto LABEL_37;
        v21 = p_JobInformation;
      }
      IsProcessInJob = (v8 >> 31) & 0xC000009A;
      if ( IsProcessInJob < 0 )
      {
        v9 = 0;
        goto LABEL_29;
      }
      IsProcessInJob = NtQueryInformationJobObject(
                         JobHandle,
                         JobObjectBasicProcessIdList,
                         p_JobInformation,
                         JobInformationLength,
                         &JobInformationLength);
    }
    else
    {
      p_JobInformation = (unsigned int *)&JobInformation;
    }
    v9 = 0;
    if ( IsProcessInJob < 0 )
      goto LABEL_29;
    ProcessHandle = 0;
    if ( is_mul_ok(*p_JobInformation, 0x10u) )
    {
      v9 = (struct _GUID *)LocalAlloc(0x40u, 16LL * *p_JobInformation);
      if ( v9 )
      {
        v10 = 0;
        ObjectAttributes.Length = 48;
        memset(&ObjectAttributes.RootDirectory, 0, 20);
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( !*p_JobInformation )
          goto LABEL_26;
        do
        {
          ClientId.UniqueThread = 0;
          ProcessHandle = 0;
          ClientId.UniqueProcess = (HANDLE)p_JobInformation[2 * v5 + 2];
          IsProcessInJob = NtOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
          if ( IsProcessInJob >= 0 )
          {
            IsProcessInJob = NtIsProcessInJob(ProcessHandle, JobHandle);
            if ( IsProcessInJob == 292 )
            {
              IsProcessInJob = GetAppSessionFromProcess(ProcessHandle, &v9[v10]);
              if ( IsProcessInJob >= 0 )
                ++v10;
            }
          }
          if ( NtClose(ProcessHandle) < 0 )
            LogMessage(
              1u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
              0x211u,
              "GetAppSessionGuidsFromJob",
              L"Assert (%s): %s",
              L"(((NTSTATUS)(NtClose(process))) >= 0)",
              L"Failed");
          ++v5;
        }
        while ( v5 < *p_JobInformation );
        if ( IsProcessInJob >= 0 )
        {
LABEL_26:
          *v22 = v9;
          *a2 = v10;
          goto LABEL_30;
        }
LABEL_29:
        LocalFree(v9);
LABEL_30:
        v20 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
        if ( !v21 || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v20) )
          return (unsigned int)IsProcessInJob;
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v13, v14);
LABEL_37:
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
        JUMPOUT(0x1800073E0LL);
      }
    }
    else
    {
      v9 = 0;
    }
    IsProcessInJob = -1073741670;
    goto LABEL_29;
  }
  return 0;
}

```

## disassembly

```asm
0x1800070d4  mov     [rsp-8+arg_18], rbx
0x1800070d9  push    rbp
0x1800070da  push    rsi
0x1800070db  push    rdi
0x1800070dc  push    r12
0x1800070de  push    r13
0x1800070e0  push    r14
0x1800070e2  push    r15
0x1800070e4  lea     rbp, [rsp-27h]
0x1800070e9  sub     rsp, 0C0h
0x1800070f0  mov     rax, cs:__security_cookie
0x1800070f7  xor     rax, rsp
0x1800070fa  mov     [rbp+57h+var_38], rax
0x1800070fe  mov     [rbp+57h+var_90], r8
0x180007102  mov     r12, rdx
0x180007105  mov     r13, rcx
0x180007108  mov     r14d, 10h
0x18000710e  mov     [rbp+57h+JobInformationLength], r14d
0x180007112  xorps   xmm0, xmm0
0x180007115  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180007119  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000711d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180007121  lea     rcx, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180007128  mov     [rbp+57h+var_A0], rcx
0x18000712c  xor     r15d, r15d
0x18000712f  mov     [rbp+57h+var_98], r15
0x180007133  mov     [rdx], r15d
0x180007136  mov     [r8], r15
0x180007139  lea     rax, [r13-1]
0x18000713d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007141  ja      loc_180007383
0x180007147  movups  [rbp+57h+JobInformation], xmm0
0x18000714b  lea     edi, [r14-0Fh]
0x18000714f  mov     dword ptr [rbp+57h+JobInformation+4], edi
0x180007152  lea     rax, [rbp+57h+JobInformationLength]
0x180007156  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x18000715b  mov     r9d, r14d; JobInformationLength
0x18000715e  lea     r8, [rbp+57h+JobInformation]; JobInformation
0x180007162  lea     edx, [rdi+2]; JobInformationClass
0x180007165  mov     rcx, r13; JobHandle
0x180007168  call    cs:__imp_NtQueryInformationJobObject
0x18000716e  mov     ebx, eax
0x180007170  cmp     eax, 80000005h
0x180007175  jnz     loc_180007211
0x18000717b  mov     [rbp+57h+ProcessHandle], r15
0x18000717f  mov     ecx, [rbp+57h+JobInformationLength]
0x180007182  mov     eax, edi
0x180007184  mul     rcx
0x180007187  test    rdx, rdx
0x18000718a  jnz     short loc_1800071AA
0x18000718c  mov     rdx, rax; uBytes
0x18000718f  lea     ecx, [rdi+3Fh]; uFlags
0x180007192  call    cs:__imp_LocalAlloc
0x180007198  mov     rsi, rax
0x18000719b  neg     rax
0x18000719e  sbb     ebx, ebx
0x1800071a0  not     ebx
0x1800071a2  and     ebx, 8007000Eh
0x1800071a8  jmp     short loc_1800071B2
0x1800071aa  mov     rsi, r15
0x1800071ad  mov     ebx, 80070216h
0x1800071b2  mov     rax, [rbp+57h+var_98]
0x1800071b6  cmp     rsi, rax
0x1800071b9  jz      short loc_1800071DC
0x1800071bb  test    rax, rax
0x1800071be  jz      short loc_1800071D8
0x1800071c0  mov     rax, [rbp+57h+var_A0]
0x1800071c4  lea     rcx, [rbp+57h+var_A0]
0x1800071c8  mov     rax, [rax]
0x1800071cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d0  test    al, al
0x1800071d2  jz      loc_1800073C6
0x1800071d8  mov     [rbp+57h+var_98], rsi
0x1800071dc  sar     ebx, 1Fh
0x1800071df  and     ebx, 0C000009Ah
0x1800071e5  jl      short loc_180007209
0x1800071e7  lea     rax, [rbp+57h+JobInformationLength]
0x1800071eb  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x1800071f0  mov     r9d, [rbp+57h+JobInformationLength]; JobInformationLength
0x1800071f4  mov     r8, rsi; JobInformation
0x1800071f7  mov     edx, 3; JobInformationClass
0x1800071fc  mov     rcx, r13; JobHandle
0x1800071ff  call    cs:__imp_NtQueryInformationJobObject
0x180007205  mov     ebx, eax
0x180007207  jmp     short loc_180007215
0x180007209  mov     rdi, r15
0x18000720c  jmp     loc_180007357
0x180007211  lea     rsi, [rbp+57h+JobInformation]
0x180007215  mov     rdi, r15
0x180007218  test    ebx, ebx
0x18000721a  js      loc_180007357
0x180007220  mov     [rbp+57h+ProcessHandle], r15
0x180007224  mov     edx, [rsi]
0x180007226  mov     rax, r14
0x180007229  mul     rdx
0x18000722c  test    rdx, rdx
0x18000722f  jnz     loc_18000734F
0x180007235  mov     rdx, rax; uBytes
0x180007238  mov     ecx, 40h ; '@'; uFlags
0x18000723d  call    cs:__imp_LocalAlloc
0x180007243  mov     rdi, rax
0x180007246  test    rax, rax
0x180007249  jz      loc_180007352
0x18000724f  mov     r14d, r15d
0x180007252  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180007259  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18000725d  mov     [rbp+57h+ObjectAttributes.Attributes], r15d
0x180007261  mov     [rbp+57h+ObjectAttributes.ObjectName], r15
0x180007265  xorps   xmm0, xmm0
0x180007268  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000726d  cmp     [rsi], r15d
0x180007270  jbe     loc_18000733F
0x180007276  xor     eax, eax
0x180007278  mov     [rbp+57h+ClientId.UniqueThread], rax
0x18000727c  mov     [rbp+57h+ProcessHandle], rax
0x180007280  mov     eax, r15d
0x180007283  mov     ecx, [rsi+rax*8+8]
0x180007287  mov     [rbp+57h+ClientId.UniqueProcess], rcx
0x18000728b  lea     r9, [rbp+57h+ClientId]; ClientId
0x18000728f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180007293  mov     edx, 400h; DesiredAccess
0x180007298  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18000729c  call    cs:__imp_NtOpenProcess
0x1800072a2  mov     ebx, eax
0x1800072a4  test    eax, eax
0x1800072a6  js      short loc_1800072DA
0x1800072a8  mov     rdx, r13; JobHandle
0x1800072ab  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1800072af  call    cs:__imp_NtIsProcessInJob
0x1800072b5  mov     ebx, eax
0x1800072b7  cmp     eax, 124h
0x1800072bc  jnz     short loc_1800072DA
0x1800072be  mov     edx, r14d
0x1800072c1  shl     rdx, 4
0x1800072c5  add     rdx, rdi; struct _GUID *
0x1800072c8  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1800072cc  call    ?GetAppSessionFromProcess@@YAJPEAXPEAU_GUID@@@Z; GetAppSessionFromProcess(void *,_GUID *)
0x1800072d1  mov     ebx, eax
0x1800072d3  test    eax, eax
0x1800072d5  js      short loc_1800072DA
0x1800072d7  inc     r14d
0x1800072da  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x1800072de  call    cs:__imp_NtClose
0x1800072e4  test    eax, eax
0x1800072e6  jns     short loc_18000732A
0x1800072e8  lea     rax, aFailed; "Failed"
0x1800072ef  mov     [rsp+0F0h+var_C0], rax
0x1800072f4  lea     rax, aNtstatusNtclos; "(((NTSTATUS)(NtClose(process))) >= 0)"
0x1800072fb  mov     [rsp+0F0h+var_C8], rax
0x180007300  lea     rax, aAssertSS; "Assert (%s): %s"
0x180007307  mov     [rsp+0F0h+ReturnLength], rax; unsigned __int16 *
0x18000730c  lea     r9, aGetappsessiong; "GetAppSessionGuidsFromJob"
0x180007313  mov     r8d, 211h; unsigned int
0x180007319  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\licensem"...
0x180007320  mov     ecx, 1; unsigned int
0x180007325  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000732a  inc     r15d
0x18000732d  cmp     r15d, [rsi]
0x180007330  jb      loc_180007276
0x180007336  xor     r15d, r15d
0x180007339  test    ebx, ebx
0x18000733b  js      short loc_180007357
0x18000733d  jmp     short loc_180007342
0x18000733f  xor     r15d, r15d
0x180007342  mov     rax, [rbp+57h+var_90]
0x180007346  mov     [rax], rdi
0x180007349  mov     [r12], r14d
0x18000734d  jmp     short loc_180007361
0x18000734f  mov     rdi, r15
0x180007352  mov     ebx, 0C000009Ah
0x180007357  mov     rcx, rdi; hMem
0x18000735a  call    cs:__imp_LocalFree
0x180007360  nop
0x180007361  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180007368  mov     [rbp+57h+var_A0], rax
0x18000736c  cmp     [rbp+57h+var_98], r15
0x180007370  jz      short loc_18000737F
0x180007372  lea     rcx, [rbp+57h+var_A0]
0x180007376  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x18000737b  test    al, al
0x18000737d  jz      short loc_1800073AC
0x18000737f  mov     eax, ebx
0x180007381  jmp     short loc_180007385
0x180007383  xor     eax, eax
0x180007385  mov     rcx, [rbp+57h+var_38]
0x180007389  xor     rcx, rsp; StackCookie
0x18000738c  call    __security_check_cookie
0x180007391  mov     rbx, [rsp+0F0h+arg_18]
0x180007399  add     rsp, 0C0h
0x1800073a0  pop     r15
0x1800073a2  pop     r14
0x1800073a4  pop     r13
0x1800073a6  pop     r12
0x1800073a8  pop     rdi
0x1800073a9  pop     rsi
0x1800073aa  pop     rbp
0x1800073ab  retn
0x1800073ac  call    cs:__imp_GetLastError
0x1800073b2  test    eax, eax
0x1800073b4  jle     short loc_1800073BE
0x1800073b6  movzx   eax, ax
0x1800073b9  or      eax, 80070000h
0x1800073be  mov     ecx, eax; this
0x1800073c0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800073c5  nop
0x1800073c6  call    cs:__imp_GetLastError
0x1800073cc  nop
0x1800073cd  test    eax, eax
0x1800073cf  jle     short loc_1800073D9
0x1800073d1  movzx   eax, ax
0x1800073d4  or      eax, 80070000h
0x1800073d9  mov     ecx, eax; this
0x1800073db  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
