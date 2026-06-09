# CDlpManager::SetThreadPriority(WINDLP_PRIORITY)

- ea: `0x14004eda0`
- end: `0x14004f23d`
- name: `?SetThreadPriority@CDlpManager@@UEAAJW4WINDLP_PRIORITY@@@Z`
- size: `1181`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140029f5c`

## callees

- `0x140002116`
- `0x140003ad0`
- `0x1400076c8`
- `0x14000c20c`
- `0x1400135b8`
- `0x14002cae4`
- `0x140034ab4`
- `0x14004eda0`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x14004efeb`
- `KERNEL32!SetThreadPriority` at `0x14004efeb`
- `KERNEL32!GetCurrentThread` at `0x14004efda`
- `KERNEL32!GetCurrentThread` at `0x14004efda`
- `KERNEL32!GetLastError` at `0x14004effb`
- `KERNEL32!GetLastError` at `0x14004effb`
- `ntdll!RtlGetVersion` at `0x14004ef0b`
- `ntdll!RtlGetVersion` at `0x14004ef0b`
- `ntdll!NtSetInformationThread` at `0x14004f0fd`
- `ntdll!NtSetInformationThread` at `0x14004f180`
- `ntdll!NtSetInformationThread` at `0x14004f0fd`
- `ntdll!NtSetInformationThread` at `0x14004f180`

## string_xrefs

- `0x14004ee68`: `CDlpManager::SetThreadPriority`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::SetThreadPriority(__int64 a1, int a2)
{
  int v4; // ebx
  __int64 v5; // rax
  unsigned int v6; // edi
  int v7; // eax
  NTSTATUS Version; // eax
  int v9; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  int v15; // [rsp+28h] [rbp-E0h]
  int v16; // [rsp+30h] [rbp-D8h]
  int v17; // [rsp+38h] [rbp-D0h] BYREF
  int ThreadInformation; // [rsp+3Ch] [rbp-CCh] BYREF
  int v19; // [rsp+40h] [rbp-C8h] BYREF
  int v20; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v21; // [rsp+48h] [rbp-C0h] BYREF
  void *v22[3]; // [rsp+50h] [rbp-B8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+68h] [rbp-A0h] BYREF

  v22[1] = (void *)-2LL;
  memset_0(&VersionInformation, 0, 0x11Cu);
  v20 = 0;
  v19 = 0;
  ThreadInformation = 0;
  v22[0] = 0;
  LODWORD(v21) = 14;
  if ( (unsigned int)(a2 - 1) <= 4 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 192LL))(a1, &v20);
    v17 = v4;
    if ( v4 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
        goto LABEL_54;
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
      v6 = 0;
      if ( !v5 )
        goto LABEL_7;
      v16 = v4;
      v15 = 1954;
      goto LABEL_5;
    }
    VersionInformation.dwOSVersionInfoSize = 284;
    Version = RtlGetVersion(&VersionInformation);
    if ( !SErrorConverter::C_NtStatus2HR(Version, &v17) )
    {
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
      {
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
        v6 = 0;
        v4 = v17;
        if ( v17 >= 0 || !v5 )
          goto LABEL_7;
        v16 = v17;
        v15 = 1960;
        goto LABEL_5;
      }
LABEL_53:
      v4 = v17;
      goto LABEL_54;
    }
    v9 = 0;
    ThreadInformation = 2;
    v19 = 5;
    switch ( a2 )
    {
      case 2:
        v9 = -2;
        ThreadInformation = 0;
        v19 = 1;
        break;
      case 3:
        v9 = 2;
LABEL_22:
        ThreadInformation = 3;
        break;
      case 4:
        v9 = -1;
        ThreadInformation = 1;
        v19 = 3;
        break;
      case 5:
        v9 = 1;
        goto LABEL_22;
      default:
        break;
    }
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, v9) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v4 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
        goto LABEL_54;
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
      v6 = 0;
      if ( v4 >= 0 || !v5 )
        goto LABEL_7;
      v16 = v4;
      v15 = 2006;
LABEL_5:
      v7 = CDlpLogT<CEmptyType>::DlpLogFormat(
             v5,
             4,
             L"%s(%d): Result = 0x%X",
             L"CDlpManager::SetThreadPriority",
             v15,
             v16);
      v6 = v7;
      if ( v7 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
      goto LABEL_7;
    }
    if ( VersionInformation.dwMajorVersion >= 6 )
    {
      if ( ((a2 - 3) & 0xFFFFFFFD) == 0 )
      {
        v4 = CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(v22, &v21, 1);
        v17 = v4;
        if ( v4 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
            goto LABEL_54;
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
          v6 = 0;
          if ( !v5 )
            goto LABEL_7;
          v16 = v4;
          v15 = 2017;
          goto LABEL_5;
        }
      }
      v12 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, &ThreadInformation, 4u);
      if ( !SErrorConverter::C_NtStatus2HR(v12, &v17) )
      {
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
        {
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
          v6 = 0;
          v4 = v17;
          if ( v17 >= 0 || !v5 )
            goto LABEL_7;
          v16 = v17;
          v15 = 2025;
          goto LABEL_5;
        }
        goto LABEL_53;
      }
      v13 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &v19, 4u);
      if ( !SErrorConverter::C_NtStatus2HR(v13, &v17) )
      {
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
        {
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
          v6 = 0;
          v4 = v17;
          if ( v17 >= 0 || !v5 )
            goto LABEL_7;
          v16 = v17;
          v15 = 2032;
          goto LABEL_5;
        }
        goto LABEL_53;
      }
    }
    if ( !*(_DWORD *)(a1 + 852) )
      *(_DWORD *)(a1 + 852) = v20;
    goto LABEL_53;
  }
  v4 = -2147024809;
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
    v6 = 0;
    if ( v5 )
    {
      v16 = -2147024809;
      v15 = 1950;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  }
LABEL_54:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  CAutoRevertApplyPrivilegesT<CEmptyType>::~CAutoRevertApplyPrivilegesT<CEmptyType>(v22);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14004eda0  mov     rax, rsp
0x14004eda3  push    rbp
0x14004eda4  push    rdi
0x14004eda5  push    r12
0x14004eda7  lea     rbp, [rax-0A8h]
0x14004edae  sub     rsp, 190h
0x14004edb5  mov     [rsp+1A0h+var_150], 0FFFFFFFFFFFFFFFEh
0x14004edbe  mov     [rax+10h], rbx
0x14004edc2  mov     [rax+18h], rsi
0x14004edc6  mov     rax, cs:__security_cookie
0x14004edcd  xor     rax, rsp
0x14004edd0  mov     [rbp+0A0h+var_20], rax
0x14004edd7  mov     esi, edx
0x14004edd9  mov     rdi, rcx
0x14004eddc  xor     edx, edx; Val
0x14004edde  mov     r8d, 11Ch; Size
0x14004ede4  lea     rcx, [rsp+1A0h+VersionInformation]; void *
0x14004ede9  call    memset_0
0x14004edee  mov     [rsp+1A0h+var_164], 0
0x14004edf6  mov     [rsp+1A0h+var_168], 0
0x14004edfe  mov     [rsp+1A0h+ThreadInformation], 0
0x14004ee06  mov     [rsp+1A0h+var_158], 0
0x14004ee0f  mov     dword ptr [rsp+1A0h+var_160], 0Eh
0x14004ee17  lea     eax, [rsi-1]
0x14004ee1a  mov     r12d, 4
0x14004ee20  cmp     eax, r12d
0x14004ee23  jbe     short loc_14004EE9A
0x14004ee25  mov     ebx, 80070057h
0x14004ee2a  mov     rax, [rdi+50h]
0x14004ee2e  lea     rcx, [rdi+50h]
0x14004ee32  mov     rax, [rax+10h]
0x14004ee36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ee3b  test    rax, rax
0x14004ee3e  jz      loc_14004F202
0x14004ee44  mov     rax, [rdi+50h]
0x14004ee48  lea     rcx, [rdi+50h]
0x14004ee4c  mov     rax, [rax+10h]
0x14004ee50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ee55  xor     edi, edi
0x14004ee57  test    rax, rax
0x14004ee5a  jz      short loc_14004EE8E
0x14004ee5c  mov     [rsp+1A0h+var_178], ebx
0x14004ee60  mov     [rsp+1A0h+var_180], 79Eh
0x14004ee68  lea     r9, aCdlpmanagerSet_3; "CDlpManager::SetThreadPriority"
0x14004ee6f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004ee76  mov     edx, r12d
0x14004ee79  mov     rcx, rax
0x14004ee7c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004ee81  test    eax, eax
0x14004ee83  mov     edi, eax
0x14004ee85  jns     short loc_14004EE8E
0x14004ee87  mov     ecx, eax
0x14004ee89  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004ee8e  mov     ecx, edi
0x14004ee90  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004ee95  jmp     loc_14004F202
0x14004ee9a  mov     rax, [rdi]
0x14004ee9d  lea     rdx, [rsp+1A0h+var_164]
0x14004eea2  mov     rcx, rdi
0x14004eea5  mov     rax, [rax+0C0h]
0x14004eeac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eeb1  mov     ebx, eax
0x14004eeb3  mov     [rsp+1A0h+var_170], eax
0x14004eeb7  test    eax, eax
0x14004eeb9  jns     short loc_14004EEFE
0x14004eebb  mov     rax, [rdi+50h]
0x14004eebf  lea     rcx, [rdi+50h]
0x14004eec3  mov     rax, [rax+10h]
0x14004eec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eecc  test    rax, rax
0x14004eecf  jz      loc_14004F202
0x14004eed5  mov     rax, [rdi+50h]
0x14004eed9  lea     rcx, [rdi+50h]
0x14004eedd  mov     rax, [rax+10h]
0x14004eee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eee6  xor     edi, edi
0x14004eee8  test    rax, rax
0x14004eeeb  jz      short loc_14004EE8E
0x14004eeed  mov     [rsp+1A0h+var_178], ebx
0x14004eef1  mov     [rsp+1A0h+var_180], 7A2h
0x14004eef9  jmp     loc_14004EE68
0x14004eefe  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14004ef06  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x14004ef0b  call    cs:__imp_RtlGetVersion
0x14004ef12  nop     dword ptr [rax+rax+00h]
0x14004ef17  mov     ecx, eax; int
0x14004ef19  lea     rdx, [rsp+1A0h+var_170]; int *
0x14004ef1e  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x14004ef23  test    eax, eax
0x14004ef25  jnz     short loc_14004EF7A
0x14004ef27  mov     rax, [rdi+50h]
0x14004ef2b  lea     rcx, [rdi+50h]
0x14004ef2f  mov     rax, [rax+10h]
0x14004ef33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ef38  test    rax, rax
0x14004ef3b  jz      loc_14004F1FE
0x14004ef41  mov     rax, [rdi+50h]
0x14004ef45  lea     rcx, [rdi+50h]
0x14004ef49  mov     rax, [rax+10h]
0x14004ef4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ef52  xor     edi, edi
0x14004ef54  mov     ebx, [rsp+1A0h+var_170]
0x14004ef58  test    ebx, ebx
0x14004ef5a  jns     loc_14004EE8E
0x14004ef60  test    rax, rax
0x14004ef63  jz      loc_14004EE8E
0x14004ef69  mov     [rsp+1A0h+var_178], ebx
0x14004ef6d  mov     [rsp+1A0h+var_180], 7A8h
0x14004ef75  jmp     loc_14004EE68
0x14004ef7a  xor     ebx, ebx
0x14004ef7c  lea     edx, [rbx+2]
0x14004ef7f  mov     [rsp+1A0h+ThreadInformation], edx
0x14004ef83  mov     [rsp+1A0h+var_168], 5
0x14004ef8b  mov     ecx, esi
0x14004ef8d  sub     ecx, edx
0x14004ef8f  jz      short loc_14004EFC5
0x14004ef91  sub     ecx, 1
0x14004ef94  jz      short loc_14004EFC1
0x14004ef96  sub     ecx, 1
0x14004ef99  jz      short loc_14004EFAC
0x14004ef9b  cmp     ecx, 1
0x14004ef9e  jnz     short loc_14004EFDA
0x14004efa0  mov     ebx, ecx
0x14004efa2  mov     [rsp+1A0h+ThreadInformation], 3
0x14004efaa  jmp     short loc_14004EFDA
0x14004efac  or      ebx, 0FFFFFFFFh
0x14004efaf  mov     [rsp+1A0h+ThreadInformation], 1
0x14004efb7  mov     [rsp+1A0h+var_168], 3
0x14004efbf  jmp     short loc_14004EFDA
0x14004efc1  mov     ebx, edx
0x14004efc3  jmp     short loc_14004EFA2
0x14004efc5  mov     ebx, 0FFFFFFFEh
0x14004efca  mov     [rsp+1A0h+ThreadInformation], 0
0x14004efd2  mov     [rsp+1A0h+var_168], 1
0x14004efda  call    cs:__imp_GetCurrentThread
0x14004efe1  nop     dword ptr [rax+rax+00h]
0x14004efe6  mov     rcx, rax; hThread
0x14004efe9  mov     edx, ebx; nPriority
0x14004efeb  call    cs:__imp_SetThreadPriority
0x14004eff2  nop     dword ptr [rax+rax+00h]
0x14004eff7  test    eax, eax
0x14004eff9  jnz     short loc_14004F06E
0x14004effb  call    cs:__imp_GetLastError
0x14004f002  nop     dword ptr [rax+rax+00h]
0x14004f007  mov     ebx, eax
0x14004f009  test    eax, eax
0x14004f00b  jnz     short loc_14004F014
0x14004f00d  mov     ebx, 80004005h
0x14004f012  jmp     short loc_14004F01F
0x14004f014  jle     short loc_14004F01F
0x14004f016  movzx   ebx, ax
0x14004f019  or      ebx, 80070000h
0x14004f01f  mov     rax, [rdi+50h]
0x14004f023  lea     rcx, [rdi+50h]
0x14004f027  mov     rax, [rax+10h]
0x14004f02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f030  test    rax, rax
0x14004f033  jz      loc_14004F202
0x14004f039  mov     rax, [rdi+50h]
0x14004f03d  lea     rcx, [rdi+50h]
0x14004f041  mov     rax, [rax+10h]
0x14004f045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f04a  xor     edi, edi
0x14004f04c  test    ebx, ebx
0x14004f04e  jns     loc_14004EE8E
0x14004f054  test    rax, rax
0x14004f057  jz      loc_14004EE8E
0x14004f05d  mov     [rsp+1A0h+var_178], ebx
0x14004f061  mov     [rsp+1A0h+var_180], 7D6h
0x14004f069  jmp     loc_14004EE68
0x14004f06e  cmp     [rsp+1A0h+VersionInformation.dwMajorVersion], 6
0x14004f073  jb      loc_14004F1EB
0x14004f079  lea     eax, [rsi-3]
0x14004f07c  test    eax, 0FFFFFFFDh
0x14004f081  jnz     short loc_14004F0E9
0x14004f083  mov     r8d, 1
0x14004f089  lea     rdx, [rsp+1A0h+var_160]
0x14004f08e  lea     rcx, [rsp+1A0h+var_158]
0x14004f093  call    ?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z; CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)
0x14004f098  mov     ebx, eax
0x14004f09a  mov     [rsp+1A0h+var_170], eax
0x14004f09e  test    eax, eax
0x14004f0a0  jns     short loc_14004F0E9
0x14004f0a2  mov     rax, [rdi+50h]
0x14004f0a6  lea     rcx, [rdi+50h]
0x14004f0aa  mov     rax, [rax+10h]
0x14004f0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f0b3  test    rax, rax
0x14004f0b6  jz      loc_14004F202
0x14004f0bc  mov     rax, [rdi+50h]
0x14004f0c0  lea     rcx, [rdi+50h]
0x14004f0c4  mov     rax, [rax+10h]
0x14004f0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f0cd  xor     edi, edi
0x14004f0cf  test    rax, rax
0x14004f0d2  jz      loc_14004EE8E
0x14004f0d8  mov     [rsp+1A0h+var_178], ebx
0x14004f0dc  mov     [rsp+1A0h+var_180], 7E1h
0x14004f0e4  jmp     loc_14004EE68
0x14004f0e9  mov     r9d, r12d; ThreadInformationLength
0x14004f0ec  lea     r8, [rsp+1A0h+ThreadInformation]; ThreadInformation
0x14004f0f1  mov     edx, 16h; ThreadInformationClass
0x14004f0f6  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14004f0fd  call    cs:__imp_NtSetInformationThread
0x14004f104  nop     dword ptr [rax+rax+00h]
0x14004f109  mov     ecx, eax; int
0x14004f10b  lea     rdx, [rsp+1A0h+var_170]; int *
0x14004f110  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x14004f115  test    eax, eax
0x14004f117  jnz     short loc_14004F16C
0x14004f119  mov     rax, [rdi+50h]
0x14004f11d  lea     rcx, [rdi+50h]
0x14004f121  mov     rax, [rax+10h]
0x14004f125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f12a  test    rax, rax
0x14004f12d  jz      loc_14004F1FE
0x14004f133  mov     rax, [rdi+50h]
0x14004f137  lea     rcx, [rdi+50h]
0x14004f13b  mov     rax, [rax+10h]
0x14004f13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f144  xor     edi, edi
0x14004f146  mov     ebx, [rsp+1A0h+var_170]
0x14004f14a  test    ebx, ebx
0x14004f14c  jns     loc_14004EE8E
0x14004f152  test    rax, rax
0x14004f155  jz      loc_14004EE8E
0x14004f15b  mov     [rsp+1A0h+var_178], ebx
0x14004f15f  mov     [rsp+1A0h+var_180], 7E9h
0x14004f167  jmp     loc_14004EE68
0x14004f16c  mov     r9d, r12d; ThreadInformationLength
0x14004f16f  lea     r8, [rsp+1A0h+var_168]; ThreadInformation
0x14004f174  mov     edx, 18h; ThreadInformationClass
0x14004f179  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14004f180  call    cs:__imp_NtSetInformationThread
0x14004f187  nop     dword ptr [rax+rax+00h]
0x14004f18c  mov     ecx, eax; int
0x14004f18e  lea     rdx, [rsp+1A0h+var_170]; int *
0x14004f193  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x14004f198  test    eax, eax
0x14004f19a  jnz     short loc_14004F1EB
0x14004f19c  mov     rax, [rdi+50h]
0x14004f1a0  lea     rcx, [rdi+50h]
0x14004f1a4  mov     rax, [rax+10h]
0x14004f1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1ad  test    rax, rax
0x14004f1b0  jz      short loc_14004F1FE
0x14004f1b2  mov     rax, [rdi+50h]
0x14004f1b6  lea     rcx, [rdi+50h]
0x14004f1ba  mov     rax, [rax+10h]
0x14004f1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1c3  xor     edi, edi
0x14004f1c5  mov     ebx, [rsp+1A0h+var_170]
0x14004f1c9  test    ebx, ebx
0x14004f1cb  jns     loc_14004EE8E
0x14004f1d1  test    rax, rax
0x14004f1d4  jz      loc_14004EE8E
0x14004f1da  mov     [rsp+1A0h+var_178], ebx
0x14004f1de  mov     [rsp+1A0h+var_180], 7F0h
0x14004f1e6  jmp     loc_14004EE68
0x14004f1eb  cmp     dword ptr [rdi+354h], 0
0x14004f1f2  jnz     short loc_14004F1FE
0x14004f1f4  mov     eax, [rsp+1A0h+var_164]
0x14004f1f8  mov     [rdi+354h], eax
0x14004f1fe  mov     ebx, [rsp+1A0h+var_170]
0x14004f202  mov     ecx, ebx
0x14004f204  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f209  lea     rcx, [rsp+1A0h+var_158]
0x14004f20e  call    ??1?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::~CAutoRevertApplyPrivilegesT<CEmptyType>(void)
0x14004f213  mov     eax, ebx
0x14004f215  mov     rcx, [rbp+0A0h+var_20]
0x14004f21c  xor     rcx, rsp; StackCookie
0x14004f21f  call    __security_check_cookie
0x14004f224  lea     r11, [rsp+1A0h+var_10]
0x14004f22c  mov     rbx, [r11+28h]
0x14004f230  mov     rsi, [r11+30h]
0x14004f234  mov     rsp, r11
0x14004f237  pop     r12
0x14004f239  pop     rdi
0x14004f23a  pop     rbp
0x14004f23b  retn
```
