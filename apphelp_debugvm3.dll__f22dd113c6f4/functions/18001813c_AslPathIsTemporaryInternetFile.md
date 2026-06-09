# AslPathIsTemporaryInternetFile

- ea: `0x18001813c`
- end: `0x1800185c9`
- name: `AslPathIsTemporaryInternetFile`
- size: `1165`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016dc0`

## callees

- `0x18000f114`
- `0x18001813c`
- `0x180018f20`
- `0x180039a66`
- `0x180039aba`

## import_xrefs

- `ntdll!NtClose` at `0x180018354`
- `ntdll!NtClose` at `0x180018354`
- `ntdll!ZwOpenKey` at `0x18001822b`
- `ntdll!ZwOpenKey` at `0x18001822b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800181cb`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800181cb`
- `ntdll!NtQueryValueKey` at `0x180018283`
- `ntdll!NtQueryValueKey` at `0x1800184c9`
- `ntdll!NtQueryValueKey` at `0x180018283`
- `ntdll!NtQueryValueKey` at `0x1800184c9`
- `ntdll!RtlFreeHeap` at `0x180018328`
- `ntdll!RtlFreeHeap` at `0x180018345`
- `ntdll!RtlFreeHeap` at `0x180018371`
- `ntdll!RtlFreeHeap` at `0x180018328`
- `ntdll!RtlFreeHeap` at `0x180018345`
- `ntdll!RtlFreeHeap` at `0x180018371`
- `ntdll!RtlFreeUnicodeString` at `0x18001830a`
- `ntdll!RtlFreeUnicodeString` at `0x18001830a`
- `ntdll!RtlAppendUnicodeToString` at `0x1800181e6`
- `ntdll!RtlAppendUnicodeToString` at `0x1800181e6`
- `ntdll!RtlAllocateHeap` at `0x18001819c`
- `ntdll!RtlAllocateHeap` at `0x180018253`
- `ntdll!RtlAllocateHeap` at `0x18001849a`
- `ntdll!RtlAllocateHeap` at `0x18001855a`
- `ntdll!RtlAllocateHeap` at `0x18001819c`
- `ntdll!RtlAllocateHeap` at `0x180018253`
- `ntdll!RtlAllocateHeap` at `0x18001849a`
- `ntdll!RtlAllocateHeap` at `0x18001855a`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800181b3`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800181b3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800184dc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018596`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800184dc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018596`

## string_xrefs

- `0x1800183bc`: `AslPathIsTemporaryInternetFile`
- `0x1800183e3`: `AslPathIsTemporaryInternetFile`
- `0x18001852f`: `AslPathIsTemporaryInternetFile`
- `0x180018575`: `AslPathIsTemporaryInternetFile`
- `0x1800183cd`: `RtlFormatCurrentUserKeyPath failed [%x]`
- `0x180018416`: `AslRegistryOpenKey failed [%x]`
- `0x1800183f4`: `RtlAppendUnicodeStringToString failed for root HKCU path [%x]`
- `0x180018403`: `RtlAppendUnicodeToString failed for shell folders path [%x]`
- `0x180018429`: `NtQueryValueKey failed to get registry value of temporary internet file [%x]`
- `0x18001845b`: `Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ`
- `0x180018524`: `Failed to expand environment variables in temporary internet file path [%x]`

## pseudocode

```c
__int64 __fastcall AslPathIsTemporaryInternetFile(_DWORD *a1, const wchar_t *a2)
{
  _DWORD *v2; // r14
  WCHAR *v4; // r15
  _DWORD *Heap; // rsi
  int v6; // r13d
  NTSTATUS appended; // eax
  int LastError_0; // ebx
  NTSTATUS v9; // eax
  const WCHAR *v10; // r14
  __int64 v11; // rax
  __int64 result; // rax
  const char *v13; // r9
  __int64 v14; // r8
  const char *v15; // r9
  __int64 v16; // r8
  DWORD v17; // eax
  DWORD v18; // ebx
  __int64 v19; // r8
  WCHAR *v20; // rax
  DWORD v21; // eax
  __int64 Length; // [rsp+20h] [rbp-60h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+D0h] [rbp+50h] BYREF
  void *KeyHandle; // [rsp+D8h] [rbp+58h] BYREF

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
    LastError_0 = -1073741801;
    v13 = "Out of memory";
    v14 = 396;
LABEL_30:
    AslLogCallPrintf(1, "AslPathIsTemporaryInternetFile", v14, v13);
    goto LABEL_16;
  }
  appended = RtlFormatCurrentUserKeyPath(&KeyPath);
  LastError_0 = appended;
  if ( appended < 0 )
  {
    v15 = "RtlFormatCurrentUserKeyPath failed [%x]";
    v16 = 402;
LABEL_32:
    LODWORD(Length) = appended;
    goto LABEL_33;
  }
  appended = RtlAppendUnicodeStringToString(&Destination, &KeyPath);
  LastError_0 = appended;
  if ( appended < 0 )
  {
    v15 = "RtlAppendUnicodeStringToString failed for root HKCU path [%x]";
    v16 = 408;
    goto LABEL_32;
  }
  appended = RtlAppendUnicodeToString(
               &Destination,
               L"\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders");
  LastError_0 = appended;
  if ( appended < 0 )
  {
    v15 = "RtlAppendUnicodeToString failed for shell folders path [%x]";
    v16 = 414;
    goto LABEL_32;
  }
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &Destination;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  LastError_0 = v9;
  if ( v9 < 0 )
  {
    if ( v9 != -1073741772 )
    {
      LODWORD(Length) = v9;
      v15 = "AslRegistryOpenKey failed [%x]";
      v16 = 429;
      goto LABEL_33;
    }
LABEL_28:
    LastError_0 = 0;
    goto LABEL_16;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
  if ( !Heap )
  {
    v14 = 439;
LABEL_40:
    v13 = "Out of memory";
    LastError_0 = -1073741801;
    goto LABEL_30;
  }
  LastError_0 = NtQueryValueKey(
                  KeyHandle,
                  (PUNICODE_STRING)&ValueName,
                  KeyValueFullInformation,
                  Heap,
                  0x208u,
                  &ResultLength);
  if ( LastError_0 != -1073741789 )
    goto LABEL_8;
  AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
  if ( !Heap )
  {
    v14 = 455;
    goto LABEL_40;
  }
  LastError_0 = NtQueryValueKey(
                  KeyHandle,
                  (PUNICODE_STRING)&ValueName,
                  KeyValueFullInformation,
                  Heap,
                  ResultLength,
                  &ResultLength);
LABEL_8:
  if ( LastError_0 == -1073741772 )
    goto LABEL_28;
  if ( LastError_0 >= 0 )
  {
    if ( (unsigned int)(Heap[1] - 1) <= 1 )
    {
      v10 = (const WCHAR *)((char *)Heap + (unsigned int)Heap[2]);
      v11 = -1;
      *(const WCHAR *)((char *)v10 + (unsigned int)Heap[3] - 2) = 0;
      do
        ++v11;
      while ( v10[v11] );
      if ( Heap[1] != 2 )
        goto LABEL_14;
      v17 = ExpandEnvironmentStringsW(v10, 0, 0);
      v18 = v17;
      if ( v17 )
      {
        v20 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v17);
        v4 = v20;
        if ( !v20 )
        {
          LastError_0 = -1073741801;
          AslLogCallPrintf(1, "AslPathIsTemporaryInternetFile", 502, "Out of memory");
          goto LABEL_15;
        }
        v21 = ExpandEnvironmentStringsW(v10, v20, v18);
        if ( v21 && v21 <= v18 )
        {
          v10 = v4;
          LODWORD(v11) = v21 - 1;
LABEL_14:
          LastError_0 = 0;
          LOBYTE(v6) = wcsnicmp_0(v10, a2, (unsigned int)v11) == 0;
LABEL_15:
          v2 = a1;
          goto LABEL_16;
        }
        if ( (int)GetLastError_0() > 0 )
          LastError_0 = (unsigned __int16)GetLastError_0() | 0xC0070000;
        else
          LastError_0 = GetLastError_0();
        v19 = 509;
      }
      else
      {
        if ( (int)GetLastError_0() > 0 )
          LastError_0 = (unsigned __int16)GetLastError_0() | 0xC0070000;
        else
          LastError_0 = GetLastError_0();
        v19 = 495;
      }
      AslLogCallPrintf(
        1,
        "AslPathIsTemporaryInternetFile",
        v19,
        "Failed to expand environment variables in temporary internet file path [%x]",
        LastError_0);
      goto LABEL_15;
    }
    LastError_0 = -1073741492;
    v13 = "Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ";
    v14 = 481;
    goto LABEL_30;
  }
  LODWORD(Length) = LastError_0;
  v15 = "NtQueryValueKey failed to get registry value of temporary internet file [%x]";
  v16 = 475;
LABEL_33:
  AslLogCallPrintf(1, "AslPathIsTemporaryInternetFile", v16, v15, Length);
LABEL_16:
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
  result = (unsigned int)LastError_0;
  *v2 = v6;
  return result;
}

```

## disassembly

```asm
0x18001813c  mov     [rsp-38h+arg_8], rbx
0x180018141  mov     [rsp-38h+arg_0], rcx
0x180018146  push    rbp
0x180018147  push    rsi
0x180018148  push    rdi
0x180018149  push    r12
0x18001814b  push    r13
0x18001814d  push    r14
0x18001814f  push    r15
0x180018151  mov     rbp, rsp
0x180018154  sub     rsp, 80h
0x18001815b  xor     edi, edi
0x18001815d  mov     eax, 208h
0x180018162  mov     r14, rcx
0x180018165  mov     [rbp+arg_10], edi
0x180018168  mov     [rbp+KeyHandle], rdi
0x18001816c  xorps   xmm0, xmm0
0x18001816f  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x180018173  mov     [rbp+Destination.MaximumLength], ax
0x180018177  mov     r12, rdx
0x18001817a  xorps   xmm1, xmm1
0x18001817d  lea     edx, [rdi+8]; Flags
0x180018180  movups  xmmword ptr [rbp+KeyPath.Length], xmm1
0x180018184  mov     rcx, gs:60h
0x18001818d  mov     r8d, eax; Size
0x180018190  mov     r15d, edi
0x180018193  mov     esi, edi
0x180018195  mov     r13d, edi
0x180018198  mov     rcx, [rcx+30h]; HeapHandle
0x18001819c  call    cs:__imp_RtlAllocateHeap
0x1800181a2  mov     [rbp+Destination.Buffer], rax
0x1800181a6  test    rax, rax
0x1800181a9  jz      loc_1800183A5
0x1800181af  lea     rcx, [rbp+KeyPath]; KeyPath
0x1800181b3  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800181b9  mov     ebx, eax
0x1800181bb  test    eax, eax
0x1800181bd  js      loc_1800183CD
0x1800181c3  lea     rdx, [rbp+KeyPath]; Source
0x1800181c7  lea     rcx, [rbp+Destination]; Destination
0x1800181cb  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800181d1  mov     ebx, eax
0x1800181d3  test    eax, eax
0x1800181d5  js      loc_1800183F4
0x1800181db  lea     rdx, Source; "\\Software\\Microsoft\\Windows\\Current"...
0x1800181e2  lea     rcx, [rbp+Destination]; Destination
0x1800181e6  call    cs:__imp_RtlAppendUnicodeToString
0x1800181ec  mov     ebx, eax
0x1800181ee  test    eax, eax
0x1800181f0  js      loc_180018403
0x1800181f6  mov     [rbp+KeyHandle], rdi
0x1800181fa  lea     rax, [rbp+Destination]
0x1800181fe  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x180018202  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180018206  xorps   xmm0, xmm0
0x180018209  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180018211  lea     edi, [rsi+1]
0x180018214  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001821c  mov     edx, edi; DesiredAccess
0x18001821e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180018222  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180018226  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001822b  call    cs:__imp_ZwOpenKey
0x180018231  mov     ebx, eax
0x180018233  test    eax, eax
0x180018235  js      loc_180018397
0x18001823b  mov     rcx, gs:60h
0x180018244  lea     edx, [rsi+8]; Flags
0x180018247  mov     ebx, 208h
0x18001824c  mov     r8d, ebx; Size
0x18001824f  mov     rcx, [rcx+30h]; HeapHandle
0x180018253  call    cs:__imp_RtlAllocateHeap
0x180018259  mov     rsi, rax
0x18001825c  test    rax, rax
0x18001825f  jz      loc_18001843A
0x180018265  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180018269  lea     rax, [rbp+arg_10]
0x18001826d  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180018272  lea     rdx, ValueName; ValueName
0x180018279  mov     r9, rsi; KeyValueInformation
0x18001827c  mov     dword ptr [rsp+80h+Length], ebx; Length
0x180018280  mov     r8d, edi; KeyValueInformationClass
0x180018283  call    cs:__imp_NtQueryValueKey
0x180018289  mov     ebx, eax
0x18001828b  cmp     eax, 0C0000023h
0x180018290  jz      loc_18001846F
0x180018296  cmp     ebx, 0C0000034h
0x18001829c  jz      loc_18001839E
0x1800182a2  xor     edx, edx; lpDst
0x1800182a4  test    ebx, ebx
0x1800182a6  js      loc_180018425
0x1800182ac  mov     eax, [rsi+4]
0x1800182af  sub     eax, edi
0x1800182b1  cmp     eax, edi
0x1800182b3  ja      loc_180018456
0x1800182b9  mov     r14d, [rsi+8]
0x1800182bd  mov     ecx, [rsi+0Ch]
0x1800182c0  add     r14, rsi
0x1800182c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800182c7  mov     [rcx+r14-2], dx
0x1800182cd  inc     rax
0x1800182d0  cmp     [r14+rax*2], dx
0x1800182d5  jnz     short loc_1800182CD
0x1800182d7  cmp     dword ptr [rsi+4], 2
0x1800182db  jz      loc_1800184D6
0x1800182e1  mov     ebx, edx
0x1800182e3  mov     r8d, eax; MaxCount
0x1800182e6  mov     rdx, r12; String2
0x1800182e9  mov     rcx, r14; String1
0x1800182ec  call    _wcsnicmp_0
0x1800182f1  xor     r14d, r14d
0x1800182f4  test    eax, eax
0x1800182f6  setz    r13b
0x1800182fa  mov     r14, [rbp+arg_0]
0x1800182fe  xor     edi, edi
0x180018300  cmp     [rbp+KeyPath.Buffer], rdi
0x180018304  jz      short loc_180018310
0x180018306  lea     rcx, [rbp+KeyPath]; UnicodeString
0x18001830a  call    cs:__imp_RtlFreeUnicodeString
0x180018310  mov     r8, [rbp+Destination.Buffer]; P
0x180018314  test    r8, r8
0x180018317  jz      short loc_18001832E
0x180018319  mov     rcx, gs:60h
0x180018322  xor     edx, edx; Flags
0x180018324  mov     rcx, [rcx+30h]; HeapHandle
0x180018328  call    cs:__imp_RtlFreeHeap
0x18001832e  test    rsi, rsi
0x180018331  jz      short loc_18001834B
0x180018333  mov     rcx, gs:60h
0x18001833c  mov     r8, rsi; P
0x18001833f  xor     edx, edx; Flags
0x180018341  mov     rcx, [rcx+30h]; HeapHandle
0x180018345  call    cs:__imp_RtlFreeHeap
0x18001834b  mov     rcx, [rbp+KeyHandle]; Handle
0x18001834f  test    rcx, rcx
0x180018352  jz      short loc_18001835A
0x180018354  call    cs:__imp_NtClose
0x18001835a  test    r15, r15
0x18001835d  jz      short loc_180018377
0x18001835f  mov     rcx, gs:60h
0x180018368  mov     r8, r15; P
0x18001836b  xor     edx, edx; Flags
0x18001836d  mov     rcx, [rcx+30h]; HeapHandle
0x180018371  call    cs:__imp_RtlFreeHeap
0x180018377  mov     eax, ebx
0x180018379  mov     [r14], r13d
0x18001837c  mov     rbx, [rsp+80h+arg_8]
0x180018384  add     rsp, 80h
0x18001838b  pop     r15
0x18001838d  pop     r14
0x18001838f  pop     r13
0x180018391  pop     r12
0x180018393  pop     rdi
0x180018394  pop     rsi
0x180018395  pop     rbp
0x180018396  retn
0x180018397  cmp     eax, 0C0000034h
0x18001839c  jnz     short loc_180018412
0x18001839e  xor     ebx, ebx
0x1800183a0  jmp     loc_1800182FE
0x1800183a5  mov     ebx, 0C0000017h
0x1800183aa  lea     r9, aOutOfMemory; "Out of memory"
0x1800183b1  mov     r8d, 18Ch
0x1800183b7  mov     ecx, 1
0x1800183bc  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x1800183c3  call    AslLogCallPrintf
0x1800183c8  jmp     loc_1800182FE
0x1800183cd  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x1800183d4  mov     r8d, 192h
0x1800183da  mov     dword ptr [rsp+80h+Length], eax
0x1800183de  mov     ecx, 1
0x1800183e3  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x1800183ea  call    AslLogCallPrintf
0x1800183ef  jmp     loc_1800182FE
0x1800183f4  lea     r9, aRtlappendunico; "RtlAppendUnicodeStringToString failed f"...
0x1800183fb  mov     r8d, 198h
0x180018401  jmp     short loc_1800183DA
0x180018403  lea     r9, aRtlappendunico_1; "RtlAppendUnicodeToString failed for she"...
0x18001840a  mov     r8d, 19Eh
0x180018410  jmp     short loc_1800183DA
0x180018412  mov     dword ptr [rsp+80h+Length], eax
0x180018416  lea     r9, aAslregistryope_3; "AslRegistryOpenKey failed [%x]"
0x18001841d  mov     r8d, 1ADh
0x180018423  jmp     short loc_180018436
0x180018425  mov     dword ptr [rsp+80h+Length], ebx
0x180018429  lea     r9, aNtqueryvalueke; "NtQueryValueKey failed to get registry "...
0x180018430  mov     r8d, 1DBh
0x180018436  mov     ecx, edi
0x180018438  jmp     short loc_1800183E3
0x18001843a  mov     r8d, 1B7h
0x180018440  jmp     short loc_180018448
0x180018442  mov     r8d, 1C7h
0x180018448  lea     r9, aOutOfMemory; "Out of memory"
0x18001844f  mov     ebx, 0C0000017h
0x180018454  jmp     short loc_180018468
0x180018456  mov     ebx, 0C000014Ch
0x18001845b  lea     r9, aErrorInRegistr; "Error in registry value retrieved with "...
0x180018462  mov     r8d, 1E1h
0x180018468  mov     ecx, edi
0x18001846a  jmp     loc_1800183BC
0x18001846f  mov     rcx, gs:60h
0x180018478  mov     rdx, rsi
0x18001847b  mov     rcx, [rcx+30h]
0x18001847f  call    AslFree
0x180018484  mov     rcx, gs:60h
0x18001848d  mov     edx, 8; Flags
0x180018492  mov     r8d, [rbp+arg_10]; Size
0x180018496  mov     rcx, [rcx+30h]; HeapHandle
0x18001849a  call    cs:__imp_RtlAllocateHeap
0x1800184a0  mov     rsi, rax
0x1800184a3  test    rax, rax
0x1800184a6  jz      short loc_180018442
0x1800184a8  mov     eax, [rbp+arg_10]
0x1800184ab  lea     rcx, [rbp+arg_10]
0x1800184af  mov     [rsp+80h+ResultLength], rcx; ResultLength
0x1800184b4  lea     rdx, ValueName; ValueName
0x1800184bb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800184bf  mov     r9, rsi; KeyValueInformation
0x1800184c2  mov     r8d, edi; KeyValueInformationClass
0x1800184c5  mov     dword ptr [rsp+80h+Length], eax; Length
0x1800184c9  call    cs:__imp_NtQueryValueKey
0x1800184cf  mov     ebx, eax
0x1800184d1  jmp     loc_180018296
0x1800184d6  xor     r8d, r8d; nSize
0x1800184d9  mov     rcx, r14; lpSrc
0x1800184dc  call    cs:__imp_ExpandEnvironmentStringsW
0x1800184e2  mov     ebx, eax
0x1800184e4  test    eax, eax
0x1800184e6  jnz     short loc_180018542
0x1800184e8  call    GetLastError_0
0x1800184ed  test    eax, eax
0x1800184ef  jg      short loc_1800184FA
0x1800184f1  call    GetLastError_0
0x1800184f6  mov     ebx, eax
0x1800184f8  jmp     short loc_180018508
0x1800184fa  call    GetLastError_0
0x1800184ff  movzx   ebx, ax
0x180018502  or      ebx, 0C0070000h
0x180018508  mov     r8d, 1EFh
0x18001850e  jmp     short loc_180018524
0x180018510  call    GetLastError_0
0x180018515  movzx   ebx, ax
0x180018518  or      ebx, 0C0070000h
0x18001851e  mov     r8d, 1FDh
0x180018524  lea     r9, aFailedToExpand; "Failed to expand environment variables "...
0x18001852b  mov     dword ptr [rsp+80h+Length], ebx
0x18001852f  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x180018536  mov     ecx, edi
0x180018538  call    AslLogCallPrintf
0x18001853d  jmp     loc_1800182FA
0x180018542  mov     rcx, gs:60h
0x18001854b  mov     r8, rbx
0x18001854e  add     r8, r8; Size
0x180018551  mov     edx, 8; Flags
0x180018556  mov     rcx, [rcx+30h]; HeapHandle
0x18001855a  call    cs:__imp_RtlAllocateHeap
0x180018560  mov     r15, rax
0x180018563  test    rax, rax
0x180018566  jnz     short loc_18001858D
0x180018568  lea     r9, aOutOfMemory; "Out of memory"
0x18001856f  mov     r8d, 1F6h
0x180018575  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x18001857c  mov     ecx, edi
0x18001857e  mov     ebx, 0C0000017h
0x180018583  call    AslLogCallPrintf
0x180018588  jmp     loc_1800182FA
0x18001858d  mov     r8d, ebx; nSize
0x180018590  mov     rdx, r15; lpDst
0x180018593  mov     rcx, r14; lpSrc
0x180018596  call    cs:__imp_ExpandEnvironmentStringsW
0x18001859c  xor     edx, edx
0x18001859e  test    eax, eax
0x1800185a0  jz      short loc_1800185B0
0x1800185a2  cmp     eax, ebx
0x1800185a4  ja      short loc_1800185B0
0x1800185a6  mov     r14, r15
0x1800185a9  dec     eax
0x1800185ab  jmp     loc_1800182E1
0x1800185b0  call    GetLastError_0
0x1800185b5  test    eax, eax
0x1800185b7  jg      loc_180018510
0x1800185bd  call    GetLastError_0
0x1800185c2  mov     ebx, eax
0x1800185c4  jmp     loc_18001851E
```
