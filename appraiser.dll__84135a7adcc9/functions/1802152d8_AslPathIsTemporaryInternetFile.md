# AslPathIsTemporaryInternetFile

- ea: `0x1802152d8`
- end: `0x18021571f`
- name: `AslPathIsTemporaryInternetFile`
- size: `1095`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180214de0`

## callees

- `0x1800091d4`
- `0x180017fc4`
- `0x18001a2f4`
- `0x1802152d8`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18021536e`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18021536e`
- `ntdll!RtlAppendUnicodeToString` at `0x1802153cf`
- `ntdll!RtlAppendUnicodeToString` at `0x1802153cf`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1802153a9`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1802153a9`
- `ntdll!RtlFreeUnicodeString` at `0x180215667`
- `ntdll!RtlFreeUnicodeString` at `0x180215667`
- `ntdll!RtlFreeHeap` at `0x1802154a6`
- `ntdll!RtlFreeHeap` at `0x180215685`
- `ntdll!RtlFreeHeap` at `0x1802156a2`
- `ntdll!RtlFreeHeap` at `0x1802156ce`
- `ntdll!RtlFreeHeap` at `0x1802154a6`
- `ntdll!RtlFreeHeap` at `0x180215685`
- `ntdll!RtlFreeHeap` at `0x1802156a2`
- `ntdll!RtlFreeHeap` at `0x1802156ce`
- `ntdll!RtlAllocateHeap` at `0x180215335`
- `ntdll!RtlAllocateHeap` at `0x180215442`
- `ntdll!RtlAllocateHeap` at `0x1802154c2`
- `ntdll!RtlAllocateHeap` at `0x1802155e8`
- `ntdll!RtlAllocateHeap` at `0x180215335`
- `ntdll!RtlAllocateHeap` at `0x180215442`
- `ntdll!RtlAllocateHeap` at `0x1802154c2`
- `ntdll!RtlAllocateHeap` at `0x1802155e8`
- `ntdll!NtClose` at `0x1802156b1`
- `ntdll!NtClose` at `0x1802156b1`
- `ntdll!NtQueryValueKey` at `0x180215485`
- `ntdll!NtQueryValueKey` at `0x1802154fc`
- `ntdll!NtQueryValueKey` at `0x180215485`
- `ntdll!NtQueryValueKey` at `0x1802154fc`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18021557d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180215621`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18021557d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180215621`
- `KERNEL32!GetLastError` at `0x180215589`
- `KERNEL32!GetLastError` at `0x180215593`
- `KERNEL32!GetLastError` at `0x18021559d`
- `KERNEL32!GetLastError` at `0x1802156f1`
- `KERNEL32!GetLastError` at `0x1802156fb`
- `KERNEL32!GetLastError` at `0x180215705`
- `KERNEL32!GetLastError` at `0x180215589`
- `KERNEL32!GetLastError` at `0x180215593`
- `KERNEL32!GetLastError` at `0x18021559d`
- `KERNEL32!GetLastError` at `0x1802156f1`
- `KERNEL32!GetLastError` at `0x1802156fb`
- `KERNEL32!GetLastError` at `0x180215705`

## string_xrefs

- `0x180215414`: `AslRegistryOpenKey failed [%x]`
- `0x18021537a`: `RtlFormatCurrentUserKeyPath failed [%x]`
- `0x180215359`: `AslPathIsTemporaryInternetFile`
- `0x180215390`: `AslPathIsTemporaryInternetFile`
- `0x1802155bd`: `AslPathIsTemporaryInternetFile`
- `0x180215603`: `AslPathIsTemporaryInternetFile`
- `0x1802155b2`: `Failed to expand environment variables in temporary internet file path [%x]`
- `0x18021551d`: `NtQueryValueKey failed to get registry value of temporary internet file [%x]`
- `0x18021553d`: `Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ`
- `0x1802153b5`: `RtlAppendUnicodeStringToString failed for root HKCU path [%x]`
- `0x1802153db`: `RtlAppendUnicodeToString failed for shell folders path [%x]`

## pseudocode

```c
__int64 __fastcall AslPathIsTemporaryInternetFile(_DWORD *a1, const wchar_t *a2)
{
  _DWORD *v2; // r14
  WCHAR *v4; // r15
  _DWORD *Heap; // rsi
  int v6; // r13d
  int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  NTSTATUS appended; // eax
  const char *v11; // r9
  __int64 v12; // r8
  int v13; // eax
  const WCHAR *v14; // r14
  __int64 v15; // rax
  DWORD v16; // eax
  DWORD v17; // ebx
  __int64 v18; // r8
  WCHAR *v19; // rax
  DWORD v20; // eax
  __int64 result; // rax
  __int64 Length; // [rsp+20h] [rbp-30h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+50h] BYREF
  HANDLE KeyHandle; // [rsp+A8h] [rbp+58h] BYREF

  v2 = a1;
  ResultLength = 0;
  KeyHandle = 0;
  Destination = 0;
  Destination.MaximumLength = 520;
  KeyPath = 0;
  v4 = 0;
  Heap = 0;
  v6 = 0;
  Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
  if ( !Destination.Buffer )
  {
    LastError = -1073741801;
    v8 = "Out of memory";
    v9 = 396;
LABEL_3:
    AslLogCallPrintf(1, "AslPathIsTemporaryInternetFile", v9, v8);
    goto LABEL_44;
  }
  appended = RtlFormatCurrentUserKeyPath(&KeyPath);
  LastError = appended;
  if ( appended < 0 )
  {
    v11 = "RtlFormatCurrentUserKeyPath failed [%x]";
    v12 = 402;
LABEL_6:
    LODWORD(Length) = appended;
LABEL_7:
    AslLogCallPrintf(1, "AslPathIsTemporaryInternetFile", v12, v11, Length);
    goto LABEL_44;
  }
  appended = RtlAppendUnicodeStringToString(&Destination, &KeyPath);
  LastError = appended;
  if ( appended < 0 )
  {
    v11 = "RtlAppendUnicodeStringToString failed for root HKCU path [%x]";
    v12 = 408;
    goto LABEL_6;
  }
  appended = RtlAppendUnicodeToString(
               &Destination,
               L"\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders");
  LastError = appended;
  if ( appended < 0 )
  {
    v11 = "RtlAppendUnicodeToString failed for shell folders path [%x]";
    v12 = 414;
    goto LABEL_6;
  }
  v13 = AslRegistryOpenKey_UStr(&KeyHandle, &Destination, 1);
  LastError = v13;
  if ( v13 < 0 )
  {
    if ( v13 != -1073741772 )
    {
      LODWORD(Length) = v13;
      v11 = "AslRegistryOpenKey failed [%x]";
      v12 = 429;
      goto LABEL_7;
    }
    goto LABEL_23;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
  if ( !Heap )
  {
    v9 = 439;
LABEL_17:
    v8 = "Out of memory";
    LastError = -1073741801;
    goto LABEL_3;
  }
  LastError = NtQueryValueKey(
                KeyHandle,
                (PUNICODE_STRING)&stru_180225928,
                KeyValueFullInformation,
                Heap,
                0x208u,
                &ResultLength);
  if ( LastError == -1073741789 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
    if ( !Heap )
    {
      v9 = 455;
      goto LABEL_17;
    }
    LastError = NtQueryValueKey(
                  KeyHandle,
                  (PUNICODE_STRING)&stru_180225928,
                  KeyValueFullInformation,
                  Heap,
                  ResultLength,
                  &ResultLength);
  }
  if ( LastError == -1073741772 )
  {
LABEL_23:
    LastError = 0;
    goto LABEL_44;
  }
  if ( LastError < 0 )
  {
    LODWORD(Length) = LastError;
    v11 = "NtQueryValueKey failed to get registry value of temporary internet file [%x]";
    v12 = 475;
    goto LABEL_7;
  }
  if ( (unsigned int)(Heap[1] - 1) > 1 )
  {
    LastError = -1073741492;
    v8 = "Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ";
    v9 = 481;
    goto LABEL_3;
  }
  v14 = (const WCHAR *)((char *)Heap + (unsigned int)Heap[2]);
  v15 = -1;
  *(const WCHAR *)((char *)v14 + (unsigned int)Heap[3] - 2) = 0;
  do
    ++v15;
  while ( v14[v15] );
  if ( Heap[1] != 2 )
    goto LABEL_42;
  v16 = ExpandEnvironmentStringsW(v14, 0, 0);
  v17 = v16;
  if ( v16 )
  {
    v19 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v16);
    v4 = v19;
    if ( !v19 )
    {
      LastError = -1073741801;
      AslLogCallPrintf(1, "AslPathIsTemporaryInternetFile", 502, "Out of memory");
      goto LABEL_43;
    }
    v20 = ExpandEnvironmentStringsW(v14, v19, v17);
    if ( !v20 || v20 > v17 )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      v18 = 509;
      goto LABEL_36;
    }
    v14 = v4;
    LODWORD(v15) = v20 - 1;
LABEL_42:
    LastError = 0;
    LOBYTE(v6) = wcsnicmp(v14, a2, (unsigned int)v15) == 0;
    goto LABEL_43;
  }
  if ( (int)GetLastError() > 0 )
    LastError = (unsigned __int16)GetLastError() | 0xC0070000;
  else
    LastError = GetLastError();
  v18 = 495;
LABEL_36:
  AslLogCallPrintf(
    1,
    "AslPathIsTemporaryInternetFile",
    v18,
    "Failed to expand environment variables in temporary internet file path [%x]",
    LastError);
LABEL_43:
  v2 = a1;
LABEL_44:
  if ( KeyPath.Buffer )
    RtlFreeUnicodeString(&KeyPath);
  if ( Destination.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  result = (unsigned int)LastError;
  *v2 = v6;
  return result;
}

```

## disassembly

```asm
0x1802152d8  mov     [rsp-38h+arg_8], rbx
0x1802152dd  mov     [rsp-38h+arg_0], rcx
0x1802152e2  push    rbp
0x1802152e3  push    rsi
0x1802152e4  push    rdi
0x1802152e5  push    r12
0x1802152e7  push    r13
0x1802152e9  push    r14
0x1802152eb  push    r15
0x1802152ed  mov     rbp, rsp
0x1802152f0  sub     rsp, 50h
0x1802152f4  xor     edi, edi
0x1802152f6  mov     eax, 208h
0x1802152fb  mov     r14, rcx
0x1802152fe  mov     [rbp+arg_10], edi
0x180215301  mov     [rbp+KeyHandle], rdi
0x180215305  xorps   xmm0, xmm0
0x180215308  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18021530c  mov     [rbp+Destination.MaximumLength], ax
0x180215310  mov     r12, rdx
0x180215313  xorps   xmm1, xmm1
0x180215316  lea     edx, [rdi+8]; Flags
0x180215319  movups  xmmword ptr [rbp+KeyPath.Length], xmm1
0x18021531d  mov     rcx, gs:60h
0x180215326  mov     r8d, eax; Size
0x180215329  mov     r15d, edi
0x18021532c  mov     esi, edi
0x18021532e  mov     r13d, edi
0x180215331  mov     rcx, [rcx+30h]; HeapHandle
0x180215335  call    cs:__imp_RtlAllocateHeap
0x18021533b  mov     [rbp+Destination.Buffer], rax
0x18021533f  test    rax, rax
0x180215342  jnz     short loc_18021536A
0x180215344  mov     ebx, 0C0000017h
0x180215349  lea     r9, aOutOfMemory_0; "Out of memory"
0x180215350  mov     r8d, 18Ch
0x180215356  lea     ecx, [rdi+1]
0x180215359  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x180215360  call    AslLogCallPrintf
0x180215365  jmp     loc_18021565B
0x18021536a  lea     rcx, [rbp+KeyPath]; KeyPath
0x18021536e  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180215374  mov     ebx, eax
0x180215376  test    eax, eax
0x180215378  jns     short loc_1802153A1
0x18021537a  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x180215381  mov     r8d, 192h
0x180215387  mov     dword ptr [rsp+50h+Length], eax
0x18021538b  mov     ecx, 1
0x180215390  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x180215397  call    AslLogCallPrintf
0x18021539c  jmp     loc_18021565B
0x1802153a1  lea     rdx, [rbp+KeyPath]; Source
0x1802153a5  lea     rcx, [rbp+Destination]; Destination
0x1802153a9  call    cs:__imp_RtlAppendUnicodeStringToString
0x1802153af  mov     ebx, eax
0x1802153b1  test    eax, eax
0x1802153b3  jns     short loc_1802153C4
0x1802153b5  lea     r9, aRtlappendunico; "RtlAppendUnicodeStringToString failed f"...
0x1802153bc  mov     r8d, 198h
0x1802153c2  jmp     short loc_180215387
0x1802153c4  lea     rdx, aSoftwareMicros_45; "\\Software\\Microsoft\\Windows\\Current"...
0x1802153cb  lea     rcx, [rbp+Destination]; Destination
0x1802153cf  call    cs:__imp_RtlAppendUnicodeToString
0x1802153d5  mov     ebx, eax
0x1802153d7  test    eax, eax
0x1802153d9  jns     short loc_1802153EA
0x1802153db  lea     r9, aRtlappendunico_1; "RtlAppendUnicodeToString failed for she"...
0x1802153e2  mov     r8d, 19Eh
0x1802153e8  jmp     short loc_180215387
0x1802153ea  mov     edi, 1
0x1802153ef  lea     rdx, [rbp+Destination]
0x1802153f3  mov     r8d, edi
0x1802153f6  lea     rcx, [rbp+KeyHandle]
0x1802153fa  call    AslRegistryOpenKey_UStr
0x1802153ff  mov     ebx, eax
0x180215401  test    eax, eax
0x180215403  jns     short loc_180215428
0x180215405  cmp     eax, 0C0000034h
0x18021540a  jz      loc_18021550C
0x180215410  mov     dword ptr [rsp+50h+Length], eax
0x180215414  lea     r9, aAslregistryope_3; "AslRegistryOpenKey failed [%x]"
0x18021541b  mov     r8d, 1ADh
0x180215421  mov     ecx, edi
0x180215423  jmp     loc_180215390
0x180215428  mov     rcx, gs:60h
0x180215431  mov     ebx, 208h
0x180215436  mov     r8d, ebx; Size
0x180215439  mov     edx, 8; Flags
0x18021543e  mov     rcx, [rcx+30h]; HeapHandle
0x180215442  call    cs:__imp_RtlAllocateHeap
0x180215448  mov     rsi, rax
0x18021544b  test    rax, rax
0x18021544e  jnz     short loc_180215467
0x180215450  lea     r8d, [rbx-51h]
0x180215454  lea     r9, aOutOfMemory_0; "Out of memory"
0x18021545b  mov     ebx, 0C0000017h
0x180215460  mov     ecx, edi
0x180215462  jmp     loc_180215359
0x180215467  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18021546b  lea     rax, [rbp+arg_10]
0x18021546f  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180215474  lea     rdx, stru_180225928; ValueName
0x18021547b  mov     r9, rsi; KeyValueInformation
0x18021547e  mov     dword ptr [rsp+50h+Length], ebx; Length
0x180215482  mov     r8d, edi; KeyValueInformationClass
0x180215485  call    cs:__imp_NtQueryValueKey
0x18021548b  mov     ebx, eax
0x18021548d  cmp     eax, 0C0000023h
0x180215492  jnz     short loc_180215504
0x180215494  mov     rcx, gs:60h
0x18021549d  mov     r8, rsi; P
0x1802154a0  xor     edx, edx; Flags
0x1802154a2  mov     rcx, [rcx+30h]; HeapHandle
0x1802154a6  call    cs:__imp_RtlFreeHeap
0x1802154ac  mov     rcx, gs:60h
0x1802154b5  mov     edx, 8; Flags
0x1802154ba  mov     r8d, [rbp+arg_10]; Size
0x1802154be  mov     rcx, [rcx+30h]; HeapHandle
0x1802154c2  call    cs:__imp_RtlAllocateHeap
0x1802154c8  mov     rsi, rax
0x1802154cb  test    rax, rax
0x1802154ce  jnz     short loc_1802154DB
0x1802154d0  mov     r8d, 1C7h
0x1802154d6  jmp     loc_180215454
0x1802154db  mov     eax, [rbp+arg_10]
0x1802154de  lea     rcx, [rbp+arg_10]
0x1802154e2  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x1802154e7  lea     rdx, stru_180225928; ValueName
0x1802154ee  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1802154f2  mov     r9, rsi; KeyValueInformation
0x1802154f5  mov     r8d, edi; KeyValueInformationClass
0x1802154f8  mov     dword ptr [rsp+50h+Length], eax; Length
0x1802154fc  call    cs:__imp_NtQueryValueKey
0x180215502  mov     ebx, eax
0x180215504  cmp     ebx, 0C0000034h
0x18021550a  jnz     short loc_180215513
0x18021550c  xor     ebx, ebx
0x18021550e  jmp     loc_18021565B
0x180215513  xor     edx, edx; lpDst
0x180215515  test    ebx, ebx
0x180215517  jns     short loc_18021552F
0x180215519  mov     dword ptr [rsp+50h+Length], ebx
0x18021551d  lea     r9, aNtqueryvalueke; "NtQueryValueKey failed to get registry "...
0x180215524  mov     r8d, 1DBh
0x18021552a  jmp     loc_180215421
0x18021552f  mov     eax, [rsi+4]
0x180215532  sub     eax, edi
0x180215534  cmp     eax, edi
0x180215536  jbe     short loc_18021554F
0x180215538  mov     ebx, 0C000014Ch
0x18021553d  lea     r9, aErrorInRegistr; "Error in registry value retrieved with "...
0x180215544  mov     r8d, 1E1h
0x18021554a  jmp     loc_180215460
0x18021554f  mov     r14d, [rsi+8]
0x180215553  mov     ecx, [rsi+0Ch]
0x180215556  add     r14, rsi
0x180215559  or      rax, 0FFFFFFFFFFFFFFFFh
0x18021555d  mov     [rcx+r14-2], dx
0x180215563  inc     rax
0x180215566  cmp     [r14+rax*2], dx
0x18021556b  jnz     short loc_180215563
0x18021556d  cmp     dword ptr [rsi+4], 2
0x180215571  jnz     loc_18021563E
0x180215577  xor     r8d, r8d; nSize
0x18021557a  mov     rcx, r14; lpSrc
0x18021557d  call    cs:__imp_ExpandEnvironmentStringsW
0x180215583  mov     ebx, eax
0x180215585  test    eax, eax
0x180215587  jnz     short loc_1802155D0
0x180215589  call    cs:__imp_GetLastError
0x18021558f  test    eax, eax
0x180215591  jg      short loc_18021559D
0x180215593  call    cs:__imp_GetLastError
0x180215599  mov     ebx, eax
0x18021559b  jmp     short loc_1802155AC
0x18021559d  call    cs:__imp_GetLastError
0x1802155a3  movzx   ebx, ax
0x1802155a6  or      ebx, 0C0070000h
0x1802155ac  mov     r8d, 1EFh
0x1802155b2  lea     r9, aFailedToExpand; "Failed to expand environment variables "...
0x1802155b9  mov     dword ptr [rsp+50h+Length], ebx
0x1802155bd  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x1802155c4  mov     ecx, edi
0x1802155c6  call    AslLogCallPrintf
0x1802155cb  jmp     loc_180215657
0x1802155d0  mov     rcx, gs:60h
0x1802155d9  mov     r8, rbx
0x1802155dc  add     r8, r8; Size
0x1802155df  mov     edx, 8; Flags
0x1802155e4  mov     rcx, [rcx+30h]; HeapHandle
0x1802155e8  call    cs:__imp_RtlAllocateHeap
0x1802155ee  mov     r15, rax
0x1802155f1  test    rax, rax
0x1802155f4  jnz     short loc_180215618
0x1802155f6  lea     r9, aOutOfMemory_0; "Out of memory"
0x1802155fd  mov     r8d, 1F6h
0x180215603  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x18021560a  mov     ecx, edi
0x18021560c  mov     ebx, 0C0000017h
0x180215611  call    AslLogCallPrintf
0x180215616  jmp     short loc_180215657
0x180215618  mov     r8d, ebx; nSize
0x18021561b  mov     rdx, r15; lpDst
0x18021561e  mov     rcx, r14; lpSrc
0x180215621  call    cs:__imp_ExpandEnvironmentStringsW
0x180215627  xor     edx, edx
0x180215629  test    eax, eax
0x18021562b  jz      loc_1802156F1
0x180215631  cmp     eax, ebx
0x180215633  ja      loc_1802156F1
0x180215639  mov     r14, r15
0x18021563c  dec     eax
0x18021563e  mov     ebx, edx
0x180215640  mov     r8d, eax; MaxCount
0x180215643  mov     rdx, r12; String2
0x180215646  mov     rcx, r14; String1
0x180215649  call    _wcsnicmp
0x18021564e  xor     r14d, r14d
0x180215651  test    eax, eax
0x180215653  setz    r13b
0x180215657  mov     r14, [rbp+arg_0]
0x18021565b  xor     edi, edi
0x18021565d  cmp     [rbp+KeyPath.Buffer], rdi
0x180215661  jz      short loc_18021566D
0x180215663  lea     rcx, [rbp+KeyPath]; UnicodeString
0x180215667  call    cs:__imp_RtlFreeUnicodeString
0x18021566d  mov     r8, [rbp+Destination.Buffer]; P
0x180215671  test    r8, r8
0x180215674  jz      short loc_18021568B
0x180215676  mov     rcx, gs:60h
0x18021567f  xor     edx, edx; Flags
0x180215681  mov     rcx, [rcx+30h]; HeapHandle
0x180215685  call    cs:__imp_RtlFreeHeap
0x18021568b  test    rsi, rsi
0x18021568e  jz      short loc_1802156A8
0x180215690  mov     rcx, gs:60h
0x180215699  mov     r8, rsi; P
0x18021569c  xor     edx, edx; Flags
0x18021569e  mov     rcx, [rcx+30h]; HeapHandle
0x1802156a2  call    cs:__imp_RtlFreeHeap
0x1802156a8  mov     rcx, [rbp+KeyHandle]; Handle
0x1802156ac  test    rcx, rcx
0x1802156af  jz      short loc_1802156B7
0x1802156b1  call    cs:__imp_NtClose
0x1802156b7  test    r15, r15
0x1802156ba  jz      short loc_1802156D4
0x1802156bc  mov     rcx, gs:60h
0x1802156c5  mov     r8, r15; P
0x1802156c8  xor     edx, edx; Flags
0x1802156ca  mov     rcx, [rcx+30h]; HeapHandle
0x1802156ce  call    cs:__imp_RtlFreeHeap
0x1802156d4  mov     eax, ebx
0x1802156d6  mov     [r14], r13d
0x1802156d9  mov     rbx, [rsp+50h+arg_8]
0x1802156e1  add     rsp, 50h
0x1802156e5  pop     r15
0x1802156e7  pop     r14
0x1802156e9  pop     r13
0x1802156eb  pop     r12
0x1802156ed  pop     rdi
0x1802156ee  pop     rsi
0x1802156ef  pop     rbp
0x1802156f0  retn
0x1802156f1  call    cs:__imp_GetLastError
0x1802156f7  test    eax, eax
0x1802156f9  jg      short loc_180215705
0x1802156fb  call    cs:__imp_GetLastError
0x180215701  mov     ebx, eax
0x180215703  jmp     short loc_180215714
0x180215705  call    cs:__imp_GetLastError
0x18021570b  movzx   ebx, ax
0x18021570e  or      ebx, 0C0070000h
0x180215714  mov     r8d, 1FDh
0x18021571a  jmp     loc_1802155B2
```
