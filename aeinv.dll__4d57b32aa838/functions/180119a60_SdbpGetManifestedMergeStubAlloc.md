# SdbpGetManifestedMergeStubAlloc

- ea: `0x180119a60`
- end: `0x180119ebf`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1119`
- prototype: `__int64 __fastcall(_QWORD *, const wchar_t *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180118eec`
- `0x180119ec8`

## callees

- `0x1800197d4`
- `0x18001b0b8`
- `0x18001cce4`
- `0x180027118`
- `0x18005a7c0`
- `0x18005a7d8`
- `0x18006be1c`
- `0x180119a60`
- `0x18011a61c`
- `0x18011a724`
- `0x180130010`

## import_xrefs

- `ntdll!ZwClose` at `0x180119e51`
- `ntdll!ZwClose` at `0x180119e51`
- `ntdll!RtlAllocateHeap` at `0x180119bac`
- `ntdll!RtlAllocateHeap` at `0x180119c85`
- `ntdll!RtlAllocateHeap` at `0x180119bac`
- `ntdll!RtlAllocateHeap` at `0x180119c85`
- `ntdll!ZwEnumerateValueKey` at `0x180119c09`
- `ntdll!ZwEnumerateValueKey` at `0x180119cc4`
- `ntdll!ZwEnumerateValueKey` at `0x180119c09`
- `ntdll!ZwEnumerateValueKey` at `0x180119cc4`
- `KERNEL32!LoadLibraryExW` at `0x180119d28`
- `KERNEL32!LoadLibraryExW` at `0x180119d28`
- `KERNEL32!FreeLibrary` at `0x180119d56`
- `KERNEL32!FreeLibrary` at `0x180119d56`
- `KERNEL32!GetProcAddress` at `0x180119d40`
- `KERNEL32!GetProcAddress` at `0x180119d40`

## string_xrefs

- `0x180119d16`: `ntdll.dll`
- `0x180119ada`: `SdbpGetManifestedMergeStubAlloc`
- `0x180119b3c`: `SdbpGetManifestedMergeStubAlloc`
- `0x180119bcd`: `SdbpGetManifestedMergeStubAlloc`
- `0x180119db4`: `SdbpGetManifestedMergeStubAlloc`
- `0x180119e26`: `SdbpGetManifestedMergeStubAlloc`
- `0x180119afb`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x180119b2b`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x180119da7`: `Failed to allocate or convert stub path.`
- `0x180119dde`: `Failed to duplicate stub path.`
- `0x180119dfb`: `Failed to allocate stub path.`

## pseudocode

```c
// Hidden C++ exception states: #wind=67
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  __int64 v3; // rsi
  NTSTATUS MergeSdbsDisabled; // ebx
  const wchar_t *Heap; // r12
  wchar_t *v7; // r13
  int Key; // eax
  unsigned int v9; // ebx
  __int64 v10; // r14
  __int64 v11; // rax
  ULONG Length; // ebx
  ULONG v13; // r12d
  wchar_t *v14; // rax
  NTSTATUS v15; // eax
  __int64 v16; // rax
  ULONG v17; // ebx
  unsigned __int64 v18; // r15
  const char *v19; // r9
  int v20; // r8d
  __int64 v21; // rbx
  HMODULE Library; // rax
  HMODULE v23; // rsi
  __int64 (*ProcAddress)(void); // rax
  size_t v25; // r8
  const char *v26; // r9
  int v27; // r8d
  const wchar_t *KeyValueInformation; // [rsp+30h] [rbp-20h]
  __int64 v29; // [rsp+38h] [rbp-18h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+50h] BYREF
  ULONG v33; // [rsp+A8h] [rbp+58h] BYREF

  v33 = 0;
  v3 = 0;
  ResultLength = 0;
  v29 = 0;
  KeyHandle[0] = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&v33);
    if ( MergeSdbsDisabled < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetManifestedMergeStubAlloc",
        1186,
        (unsigned int)"SdbpGetMergeSdbsDisabled failed [%x]");
      return (unsigned int)MergeSdbsDisabled;
    }
    if ( !v33 )
    {
      Heap = 0;
      v7 = 0;
      Key = AslRegistryGetKey(
              KeyHandle,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
              2147483904LL,
              1);
      MergeSdbsDisabled = Key;
      if ( Key < 0 )
      {
        if ( Key != -1073741772 )
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetManifestedMergeStubAlloc",
            1202,
            (unsigned int)"AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]");
LABEL_59:
        if ( (unsigned __int64)KeyHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          ZwClose(KeyHandle[0]);
        if ( v3 )
          AslFree(NtCurrentPeb()->ProcessHeap, v3);
        if ( Heap )
          AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        if ( v7 )
          AslFree(NtCurrentPeb()->ProcessHeap, v7);
        return (unsigned int)MergeSdbsDisabled;
      }
      v9 = 1;
      while ( wcsicmp(a2, (const wchar_t *)qword_180133278[4 * v9]) )
      {
        if ( (int)++v9 >= 10 )
        {
LABEL_58:
          MergeSdbsDisabled = -1073741772;
          goto LABEL_59;
        }
      }
      v10 = -1;
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      Length = 2 * v11 + 18;
      v33 = Length;
      Heap = (const wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
      KeyValueInformation = Heap;
      if ( !Heap )
      {
        MergeSdbsDisabled = -1073741801;
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetManifestedMergeStubAlloc",
          1222,
          (unsigned int)"Failed to allocate partial info.");
        goto LABEL_59;
      }
      v13 = 0;
      v14 = (wchar_t *)KeyValueInformation;
      while ( 1 )
      {
        v15 = ZwEnumerateValueKey(KeyHandle[0], v13, KeyValuePartialInformation, v14, Length, &ResultLength);
        MergeSdbsDisabled = v15;
        if ( v15 == -2147483643 || v15 == -1073741789 )
          goto LABEL_26;
        if ( v15 == -2147483622 )
        {
          Heap = KeyValueInformation;
          goto LABEL_58;
        }
        if ( v15 < 0 )
        {
          v19 = "Failed to query partial info.";
          v20 = 1241;
LABEL_55:
          AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v20, (_DWORD)v19);
          goto LABEL_56;
        }
        v14 = (wchar_t *)KeyValueInformation;
        if ( *((_DWORD *)KeyValueInformation + 1) == 1 )
          break;
LABEL_27:
        Length = v33;
        ++v13;
      }
      if ( !wcsicmp(a2, KeyValueInformation + 6) )
      {
        v16 = -1;
        do
          ++v16;
        while ( a2[v16] );
        v17 = 2 * v16 + 538;
        v18 = v17;
        v7 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v17);
        if ( !v7 )
        {
          MergeSdbsDisabled = -1073741801;
          v19 = "Failed to allocate basic info.";
          v20 = 1258;
          goto LABEL_55;
        }
        MergeSdbsDisabled = ZwEnumerateValueKey(KeyHandle[0], v13, KeyValueBasicInformation, v7, v17, &ResultLength);
        if ( MergeSdbsDisabled < 0 )
        {
          v19 = "Failed to query basic info.";
          v20 = 1269;
          goto LABEL_55;
        }
        if ( (unsigned __int64)ResultLength + 2 > v18 )
        {
          MergeSdbsDisabled = -1073741789;
          v19 = "Buffer too small to query basic info.";
          v20 = 1274;
          goto LABEL_55;
        }
        v21 = (__int64)qword_180183C08;
        if ( !qword_180183C08 )
        {
          v21 = 2147352624;
          Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
          v23 = Library;
          if ( Library )
          {
            ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
            if ( ProcAddress )
              v21 = ProcAddress();
            FreeLibrary(v23);
          }
          qword_180183C08 = (wchar_t *)v21;
        }
        v25 = -1;
        do
          ++v25;
        while ( *(_WORD *)(v21 + 2 * v25) );
        if ( wcsnicmp((const wchar_t *)v21, v7 + 6, v25) )
        {
          MergeSdbsDisabled = AslStringDuplicate(&v29, v7 + 6);
          if ( MergeSdbsDisabled >= 0 )
            goto LABEL_51;
          v26 = "Failed to duplicate stub path.";
          v27 = 1301;
LABEL_48:
          AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v27, (_DWORD)v26);
          v3 = v29;
        }
        else
        {
          do
            ++v10;
          while ( *(_WORD *)(v21 + 2 * v10) );
          MergeSdbsDisabled = AslPathToSystemPath(&v29, &v7[v10 + 6]);
          if ( MergeSdbsDisabled < 0 )
          {
            v26 = "Failed to allocate or convert stub path.";
            v27 = 1294;
            goto LABEL_48;
          }
LABEL_51:
          v3 = v29;
          if ( !v29 )
          {
            MergeSdbsDisabled = -1073741801;
            v19 = "Failed to allocate stub path.";
            v20 = 1308;
            goto LABEL_55;
          }
          MergeSdbsDisabled = 0;
          *a1 = v29;
          v3 = 0;
        }
LABEL_56:
        Heap = KeyValueInformation;
        goto LABEL_59;
      }
LABEL_26:
      v14 = (wchar_t *)KeyValueInformation;
      goto LABEL_27;
    }
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x180119a60  mov     [rsp-38h+arg_8], rbx
0x180119a65  mov     [rsp-38h+arg_0], rcx
0x180119a6a  push    rbp
0x180119a6b  push    rsi
0x180119a6c  push    rdi
0x180119a6d  push    r12
0x180119a6f  push    r13
0x180119a71  push    r14
0x180119a73  push    r15
0x180119a75  mov     rbp, rsp
0x180119a78  sub     rsp, 50h
0x180119a7c  xor     r14d, r14d
0x180119a7f  mov     r15, rdx
0x180119a82  mov     [rbp+arg_18], r14d
0x180119a86  mov     esi, r14d
0x180119a89  mov     [rbp+arg_10], r14d
0x180119a8d  mov     [rbp+var_18], r14
0x180119a91  mov     [rbp+KeyHandle], r14
0x180119a95  test    rcx, rcx
0x180119a98  jnz     short loc_180119AA4
0x180119a9a  mov     eax, 0C00000EFh
0x180119a9f  jmp     loc_180119EA7
0x180119aa4  mov     [rcx], r14
0x180119aa7  call    SdbpGetMergeSdbsSupported
0x180119aac  test    eax, eax
0x180119aae  jnz     short loc_180119ABA
0x180119ab0  mov     ebx, 0C0000034h
0x180119ab5  jmp     loc_180119EA5
0x180119aba  lea     rcx, [rbp+arg_18]
0x180119abe  call    SdbpGetMergeSdbsDisabled
0x180119ac3  mov     ebx, eax
0x180119ac5  test    eax, eax
0x180119ac7  jns     short loc_180119AF0
0x180119ac9  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x180119ad0  mov     [rsp+50h+Length], eax
0x180119ad4  mov     r8d, 4A2h
0x180119ada  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x180119ae1  mov     ecx, 1
0x180119ae6  call    AslLogCallPrintf
0x180119aeb  jmp     loc_180119EA5
0x180119af0  cmp     [rbp+arg_18], r14d
0x180119af4  jnz     short loc_180119AB0
0x180119af6  mov     edi, 1
0x180119afb  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x180119b02  mov     r9d, edi
0x180119b05  lea     rcx, [rbp+KeyHandle]
0x180119b09  mov     r8d, 80000100h
0x180119b0f  mov     r12, r14
0x180119b12  mov     r13, r14
0x180119b15  call    AslRegistryGetKey
0x180119b1a  mov     ebx, eax
0x180119b1c  test    eax, eax
0x180119b1e  jns     short loc_180119B4F
0x180119b20  cmp     eax, 0C0000034h
0x180119b25  jz      loc_180119E43
0x180119b2b  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x180119b32  mov     [rsp+50h+Length], eax
0x180119b36  mov     r8d, 4B2h
0x180119b3c  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x180119b43  mov     ecx, edi
0x180119b45  call    AslLogCallPrintf
0x180119b4a  jmp     loc_180119E43
0x180119b4f  mov     ebx, edi
0x180119b51  lea     rax, qword_180133278
0x180119b58  mov     edx, ebx
0x180119b5a  shl     rdx, 5
0x180119b5e  mov     rcx, r15; String1
0x180119b61  mov     rdx, [rdx+rax]; String2
0x180119b65  call    _wcsicmp
0x180119b6a  test    eax, eax
0x180119b6c  jz      short loc_180119B7A
0x180119b6e  add     ebx, edi
0x180119b70  cmp     ebx, 0Ah
0x180119b73  jl      short loc_180119B51
0x180119b75  jmp     loc_180119E3E
0x180119b7a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180119b7e  mov     rax, r14
0x180119b81  xor     ecx, ecx
0x180119b83  inc     rax
0x180119b86  cmp     [r15+rax*2], cx
0x180119b8b  jnz     short loc_180119B83
0x180119b8d  mov     rcx, gs:60h
0x180119b96  lea     ebx, ds:12h[rax*2]
0x180119b9d  mov     r8d, ebx; Size
0x180119ba0  mov     edx, 8; Flags
0x180119ba5  mov     [rbp+arg_18], ebx
0x180119ba8  mov     rcx, [rcx+30h]; HeapHandle
0x180119bac  call    cs:__imp_RtlAllocateHeap
0x180119bb2  mov     r12, rax
0x180119bb5  mov     [rbp+KeyValueInformation], rax
0x180119bb9  xor     eax, eax
0x180119bbb  test    r12, r12
0x180119bbe  jnz     short loc_180119BE5
0x180119bc0  lea     r9, aFailedToAlloca_1; "Failed to allocate partial info."
0x180119bc7  mov     r8d, 4C6h
0x180119bcd  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x180119bd4  mov     ecx, edi
0x180119bd6  mov     ebx, 0C0000017h
0x180119bdb  call    AslLogCallPrintf
0x180119be0  jmp     loc_180119E43
0x180119be5  mov     r12d, eax
0x180119be8  mov     rax, [rbp+KeyValueInformation]
0x180119bec  lea     rcx, [rbp+arg_10]
0x180119bf0  mov     r9, rax; KeyValueInformation
0x180119bf3  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x180119bf8  mov     r8d, 2; KeyValueInformationClass
0x180119bfe  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180119c02  mov     edx, r12d; Index
0x180119c05  mov     [rsp+50h+Length], ebx; Length
0x180119c09  call    cs:__imp_ZwEnumerateValueKey
0x180119c0f  mov     ebx, eax
0x180119c11  cmp     eax, 80000005h
0x180119c16  jz      short loc_180119C4D
0x180119c18  cmp     eax, 0C0000023h
0x180119c1d  jz      short loc_180119C4D
0x180119c1f  cmp     eax, 8000001Ah
0x180119c24  jz      loc_180119E3A
0x180119c2a  test    eax, eax
0x180119c2c  js      loc_180119E19
0x180119c32  mov     rax, [rbp+KeyValueInformation]
0x180119c36  cmp     [rax+4], edi
0x180119c39  jnz     short loc_180119C51
0x180119c3b  lea     rdx, [rax+0Ch]; String2
0x180119c3f  mov     rcx, r15; String1
0x180119c42  call    _wcsicmp
0x180119c47  xor     ecx, ecx
0x180119c49  test    eax, eax
0x180119c4b  jz      short loc_180119C59
0x180119c4d  mov     rax, [rbp+KeyValueInformation]
0x180119c51  mov     ebx, [rbp+arg_18]
0x180119c54  add     r12d, edi
0x180119c57  jmp     short loc_180119BEC
0x180119c59  mov     rax, r14
0x180119c5c  inc     rax
0x180119c5f  cmp     [r15+rax*2], cx
0x180119c64  jnz     short loc_180119C5C
0x180119c66  mov     rcx, gs:60h
0x180119c6f  lea     ebx, ds:21Ah[rax*2]
0x180119c76  mov     r8d, ebx; Size
0x180119c79  mov     edx, 8; Flags
0x180119c7e  mov     r15d, ebx
0x180119c81  mov     rcx, [rcx+30h]; HeapHandle
0x180119c85  call    cs:__imp_RtlAllocateHeap
0x180119c8b  mov     r13, rax
0x180119c8e  test    rax, rax
0x180119c91  jnz     short loc_180119CAA
0x180119c93  mov     ebx, 0C0000017h
0x180119c98  lea     r9, aFailedToAlloca_7; "Failed to allocate basic info."
0x180119c9f  mov     r8d, 4EAh
0x180119ca5  jmp     loc_180119E26
0x180119caa  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180119cae  lea     rax, [rbp+arg_10]
0x180119cb2  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180119cb7  mov     r9, r13; KeyValueInformation
0x180119cba  xor     r8d, r8d; KeyValueInformationClass
0x180119cbd  mov     [rsp+50h+Length], ebx; Length
0x180119cc1  mov     edx, r12d; Index
0x180119cc4  call    cs:__imp_ZwEnumerateValueKey
0x180119cca  xor     r12d, r12d
0x180119ccd  mov     ebx, eax
0x180119ccf  test    eax, eax
0x180119cd1  jns     short loc_180119CE5
0x180119cd3  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x180119cda  mov     r8d, 4F5h
0x180119ce0  jmp     loc_180119E26
0x180119ce5  mov     eax, [rbp+arg_10]
0x180119ce8  add     rax, 2
0x180119cec  cmp     rax, r15
0x180119cef  jbe     short loc_180119D08
0x180119cf1  mov     ebx, 0C0000023h
0x180119cf6  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x180119cfd  mov     r8d, 4FAh
0x180119d03  jmp     loc_180119E26
0x180119d08  mov     rbx, cs:qword_180183C08
0x180119d0f  test    rbx, rbx
0x180119d12  jnz     short loc_180119D63
0x180119d14  xor     edx, edx; hFile
0x180119d16  lea     rcx, LibFileName; "ntdll.dll"
0x180119d1d  mov     r8d, 800h; dwFlags
0x180119d23  mov     ebx, 7FFE0030h
0x180119d28  call    cs:__imp_LoadLibraryExW
0x180119d2e  mov     rsi, rax
0x180119d31  test    rax, rax
0x180119d34  jz      short loc_180119D5C
0x180119d36  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180119d3d  mov     rcx, rax; hModule
0x180119d40  call    cs:__imp_GetProcAddress
0x180119d46  test    rax, rax
0x180119d49  jz      short loc_180119D53
0x180119d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119d50  mov     rbx, rax
0x180119d53  mov     rcx, rsi; hLibModule
0x180119d56  call    cs:__imp_FreeLibrary
0x180119d5c  mov     cs:qword_180183C08, rbx
0x180119d63  mov     r8, r14
0x180119d66  inc     r8; MaxCount
0x180119d69  cmp     [rbx+r8*2], r12w
0x180119d6e  jnz     short loc_180119D66
0x180119d70  lea     rdx, [r13+0Ch]; String2
0x180119d74  mov     rcx, rbx; String1
0x180119d77  call    _wcsnicmp
0x180119d7c  test    eax, eax
0x180119d7e  jnz     short loc_180119DC8
0x180119d80  inc     r14
0x180119d83  cmp     [rbx+r14*2], r12w
0x180119d88  jnz     short loc_180119D80
0x180119d8a  lea     rdx, ds:0Ch[r14*2]
0x180119d92  add     rdx, r13
0x180119d95  lea     rcx, [rbp+var_18]
0x180119d99  call    AslPathToSystemPath
0x180119d9e  xor     r14d, r14d
0x180119da1  mov     ebx, eax
0x180119da3  test    eax, eax
0x180119da5  jns     short loc_180119DED
0x180119da7  lea     r9, aFailedToAlloca_3; "Failed to allocate or convert stub path"...
0x180119dae  mov     r8d, 50Eh
0x180119db4  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x180119dbb  mov     ecx, edi
0x180119dbd  call    AslLogCallPrintf
0x180119dc2  mov     rsi, [rbp+var_18]
0x180119dc6  jmp     short loc_180119E34
0x180119dc8  lea     rdx, [r13+0Ch]
0x180119dcc  lea     rcx, [rbp+var_18]
0x180119dd0  call    AslStringDuplicate
0x180119dd5  xor     r14d, r14d
0x180119dd8  mov     ebx, eax
0x180119dda  test    eax, eax
0x180119ddc  jns     short loc_180119DED
0x180119dde  lea     r9, aFailedToDuplic; "Failed to duplicate stub path."
0x180119de5  mov     r8d, 515h
0x180119deb  jmp     short loc_180119DB4
0x180119ded  mov     rsi, [rbp+var_18]
0x180119df1  test    rsi, rsi
0x180119df4  jnz     short loc_180119E0A
0x180119df6  mov     ebx, 0C0000017h
0x180119dfb  lea     r9, aFailedToAlloca_11; "Failed to allocate stub path."
0x180119e02  mov     r8d, 51Ch
0x180119e08  jmp     short loc_180119E26
0x180119e0a  mov     rax, [rbp+arg_0]
0x180119e0e  mov     ebx, r14d
0x180119e11  mov     [rax], rsi
0x180119e14  mov     rsi, r14
0x180119e17  jmp     short loc_180119E34
0x180119e19  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x180119e20  mov     r8d, 4D9h
0x180119e26  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x180119e2d  mov     ecx, edi
0x180119e2f  call    AslLogCallPrintf
0x180119e34  mov     r12, [rbp+KeyValueInformation]
0x180119e38  jmp     short loc_180119E43
0x180119e3a  mov     r12, [rbp+KeyValueInformation]
0x180119e3e  mov     ebx, 0C0000034h
0x180119e43  mov     rcx, [rbp+KeyHandle]; Handle
0x180119e47  lea     rax, [rcx-1]
0x180119e4b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180119e4f  ja      short loc_180119E57
0x180119e51  call    cs:__imp_ZwClose
0x180119e57  test    rsi, rsi
0x180119e5a  jz      short loc_180119E71
0x180119e5c  mov     rcx, gs:60h
0x180119e65  mov     rdx, rsi
0x180119e68  mov     rcx, [rcx+30h]
0x180119e6c  call    AslFree
0x180119e71  test    r12, r12
0x180119e74  jz      short loc_180119E8B
0x180119e76  mov     rcx, gs:60h
0x180119e7f  mov     rdx, r12
0x180119e82  mov     rcx, [rcx+30h]
0x180119e86  call    AslFree
0x180119e8b  test    r13, r13
0x180119e8e  jz      short loc_180119EA5
0x180119e90  mov     rcx, gs:60h
0x180119e99  mov     rdx, r13
0x180119e9c  mov     rcx, [rcx+30h]
0x180119ea0  call    AslFree
0x180119ea5  mov     eax, ebx
0x180119ea7  mov     rbx, [rsp+50h+arg_8]
0x180119eaf  add     rsp, 50h
0x180119eb3  pop     r15
0x180119eb5  pop     r14
0x180119eb7  pop     r13
0x180119eb9  pop     r12
0x180119ebb  pop     rdi
0x180119ebc  pop     rsi
0x180119ebd  pop     rbp
0x180119ebe  retn
```
