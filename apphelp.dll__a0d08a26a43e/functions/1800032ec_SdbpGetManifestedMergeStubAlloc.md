# SdbpGetManifestedMergeStubAlloc

- ea: `0x1800032ec`
- end: `0x180003750`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1124`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002118`
- `0x180003c7c`

## callees

- `0x1800032ec`
- `0x180003a64`
- `0x180003b74`
- `0x180004c1c`
- `0x18000f114`
- `0x18001577c`
- `0x180016910`
- `0x180018f20`
- `0x180039a5a`
- `0x180039a66`
- `0x18005a010`

## import_xrefs

- `ntdll!ZwEnumerateValueKey` at `0x18000349a`
- `ntdll!ZwEnumerateValueKey` at `0x180003555`
- `ntdll!ZwEnumerateValueKey` at `0x18000349a`
- `ntdll!ZwEnumerateValueKey` at `0x180003555`
- `ntdll!ZwClose` at `0x1800036e2`
- `ntdll!ZwClose` at `0x1800036e2`
- `ntdll!RtlAllocateHeap` at `0x18000343d`
- `ntdll!RtlAllocateHeap` at `0x180003516`
- `ntdll!RtlAllocateHeap` at `0x18000343d`
- `ntdll!RtlAllocateHeap` at `0x180003516`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800035b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800035b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800035e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800035e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800035d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800035d1`

## string_xrefs

- `0x18000338f`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x180003366`: `SdbpGetManifestedMergeStubAlloc`
- `0x1800033cd`: `SdbpGetManifestedMergeStubAlloc`
- `0x18000345e`: `SdbpGetManifestedMergeStubAlloc`
- `0x180003645`: `SdbpGetManifestedMergeStubAlloc`
- `0x1800036b7`: `SdbpGetManifestedMergeStubAlloc`
- `0x180003638`: `Failed to allocate or convert stub path.`
- `0x1800035a7`: `ntdll.dll`
- `0x1800033bc`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x18000366f`: `Failed to duplicate stub path.`
- `0x18000368c`: `Failed to allocate stub path.`

## pseudocode

```c
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  void *v3; // rsi
  int v5; // ebx
  int MergeSdbsDisabled; // eax
  PVOID Heap; // r12
  wchar_t *v8; // r13
  int Key; // eax
  unsigned int v10; // ebx
  __int64 v11; // r14
  __int64 v12; // rax
  ULONG Length; // ebx
  ULONG v14; // r12d
  wchar_t *v15; // rax
  NTSTATUS v16; // eax
  __int64 v17; // rax
  ULONG v18; // ebx
  unsigned __int64 v19; // r15
  __int64 v20; // rbx
  HMODULE Library; // rax
  HMODULE v22; // rsi
  __int64 (*ProcAddress)(void); // rax
  size_t v24; // r8
  const wchar_t *KeyValueInformation; // [rsp+30h] [rbp-20h]
  void *v26; // [rsp+38h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+50h] BYREF
  ULONG v30; // [rsp+A8h] [rbp+58h] BYREF

  v30 = 0;
  v3 = 0;
  ResultLength = 0;
  v26 = 0;
  KeyHandle = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&v30);
    v5 = MergeSdbsDisabled;
    if ( MergeSdbsDisabled < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbpGetManifestedMergeStubAlloc",
        1186,
        "SdbpGetMergeSdbsDisabled failed [%x]",
        MergeSdbsDisabled);
      return (unsigned int)v5;
    }
    if ( !v30 )
    {
      Heap = 0;
      v8 = 0;
      Key = AslRegistryGetKey(
              &KeyHandle,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
              0x80000100,
              1,
              0);
      v5 = Key;
      if ( Key < 0 )
      {
        if ( Key != -1073741772 )
          AslLogCallPrintf(
            1,
            "SdbpGetManifestedMergeStubAlloc",
            1202,
            "AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]",
            Key);
LABEL_58:
        if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          ZwClose(KeyHandle);
        if ( v3 )
          AslFree(NtCurrentPeb()->ProcessHeap, v3);
        if ( Heap )
          AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        if ( v8 )
          AslFree(NtCurrentPeb()->ProcessHeap, v8);
        return (unsigned int)v5;
      }
      v10 = 1;
      while ( wcsicmp_0(a2, (const wchar_t *)qword_18005B368[4 * v10]) )
      {
        if ( (int)++v10 >= 10 )
        {
LABEL_57:
          v5 = -1073741772;
          goto LABEL_58;
        }
      }
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      Length = 2 * v12 + 18;
      v30 = Length;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
      KeyValueInformation = (const wchar_t *)Heap;
      if ( !Heap )
      {
        v5 = -1073741801;
        AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1222, "Failed to allocate partial info.");
        goto LABEL_58;
      }
      v14 = 0;
      v15 = (wchar_t *)KeyValueInformation;
      while ( 1 )
      {
        v16 = ZwEnumerateValueKey(KeyHandle, v14, KeyValuePartialInformation, v15, Length, &ResultLength);
        v5 = v16;
        if ( v16 == -2147483622 )
        {
          Heap = (PVOID)KeyValueInformation;
          goto LABEL_57;
        }
        if ( v16 == -2147483643 || v16 == -1073741789 )
          goto LABEL_26;
        if ( v16 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1241, "Failed to query partial info.");
          goto LABEL_55;
        }
        v15 = (wchar_t *)KeyValueInformation;
        if ( *((_DWORD *)KeyValueInformation + 1) == 1 )
          break;
LABEL_27:
        Length = v30;
        ++v14;
      }
      if ( !wcsicmp_0(a2, KeyValueInformation + 6) )
      {
        v17 = -1;
        do
          ++v17;
        while ( a2[v17] );
        v18 = 2 * v17 + 538;
        v19 = v18;
        v8 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v18);
        if ( !v8 )
        {
          v5 = -1073741801;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1258, "Failed to allocate basic info.");
LABEL_55:
          Heap = (PVOID)KeyValueInformation;
          goto LABEL_58;
        }
        v5 = ZwEnumerateValueKey(KeyHandle, v14, KeyValueBasicInformation, v8, v18, &ResultLength);
        if ( v5 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1269, "Failed to query basic info.");
          goto LABEL_55;
        }
        if ( (unsigned __int64)ResultLength + 2 > v19 )
        {
          v5 = -1073741789;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1274, "Buffer too small to query basic info.");
          goto LABEL_55;
        }
        v20 = (__int64)String1;
        if ( !String1 )
        {
          v20 = 2147352624;
          Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
          v22 = Library;
          if ( Library )
          {
            ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
            if ( ProcAddress )
              v20 = ProcAddress();
            FreeLibrary(v22);
          }
          String1 = (wchar_t *)v20;
        }
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)(v20 + 2 * v24) );
        if ( wcsnicmp_0((const wchar_t *)v20, v8 + 6, v24) )
        {
          v5 = AslStringDuplicate(&v26, v8 + 6);
          if ( v5 < 0 )
          {
            AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1301, "Failed to duplicate stub path.");
            goto LABEL_48;
          }
        }
        else
        {
          do
            ++v11;
          while ( *(_WORD *)(v20 + 2 * v11) );
          v5 = AslPathToSystemPath(&v26, (__int64)&v8[v11 + 6]);
          if ( v5 < 0 )
          {
            AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1294, "Failed to allocate or convert stub path.");
LABEL_48:
            v3 = v26;
            goto LABEL_55;
          }
        }
        v3 = v26;
        if ( v26 )
        {
          v5 = 0;
          *a1 = v26;
          v3 = 0;
        }
        else
        {
          v5 = -1073741801;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1308, "Failed to allocate stub path.");
        }
        goto LABEL_55;
      }
LABEL_26:
      v15 = (wchar_t *)KeyValueInformation;
      goto LABEL_27;
    }
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x1800032ec  mov     [rsp-38h+arg_8], rbx
0x1800032f1  mov     [rsp-38h+arg_0], rcx
0x1800032f6  push    rbp
0x1800032f7  push    rsi
0x1800032f8  push    rdi
0x1800032f9  push    r12
0x1800032fb  push    r13
0x1800032fd  push    r14
0x1800032ff  push    r15
0x180003301  mov     rbp, rsp
0x180003304  sub     rsp, 50h
0x180003308  xor     r14d, r14d
0x18000330b  mov     r15, rdx
0x18000330e  mov     [rbp+arg_18], r14d
0x180003312  mov     esi, r14d
0x180003315  mov     [rbp+arg_10], r14d
0x180003319  mov     [rbp+var_18], r14
0x18000331d  mov     [rbp+KeyHandle], r14
0x180003321  test    rcx, rcx
0x180003324  jnz     short loc_180003330
0x180003326  mov     eax, 0C00000EFh
0x18000332b  jmp     loc_180003738
0x180003330  mov     [rcx], r14
0x180003333  call    SdbpGetMergeSdbsSupported
0x180003338  test    eax, eax
0x18000333a  jnz     short loc_180003346
0x18000333c  mov     ebx, 0C0000034h
0x180003341  jmp     loc_180003736
0x180003346  lea     rcx, [rbp+arg_18]
0x18000334a  call    SdbpGetMergeSdbsDisabled
0x18000334f  mov     ebx, eax
0x180003351  test    eax, eax
0x180003353  jns     short loc_18000337C
0x180003355  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x18000335c  mov     [rsp+50h+Length], eax
0x180003360  mov     r8d, 4A2h
0x180003366  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18000336d  mov     ecx, 1
0x180003372  call    AslLogCallPrintf
0x180003377  jmp     loc_180003736
0x18000337c  cmp     [rbp+arg_18], r14d
0x180003380  jnz     short loc_18000333C
0x180003382  mov     edi, 1
0x180003387  mov     [rsp+50h+Length], r14d
0x18000338c  mov     r9d, edi
0x18000338f  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003396  mov     r8d, 80000100h
0x18000339c  lea     rcx, [rbp+KeyHandle]
0x1800033a0  mov     r12, r14
0x1800033a3  mov     r13, r14
0x1800033a6  call    AslRegistryGetKey
0x1800033ab  mov     ebx, eax
0x1800033ad  test    eax, eax
0x1800033af  jns     short loc_1800033E0
0x1800033b1  cmp     eax, 0C0000034h
0x1800033b6  jz      loc_1800036D4
0x1800033bc  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x1800033c3  mov     [rsp+50h+Length], eax
0x1800033c7  mov     r8d, 4B2h
0x1800033cd  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1800033d4  mov     ecx, edi
0x1800033d6  call    AslLogCallPrintf
0x1800033db  jmp     loc_1800036D4
0x1800033e0  mov     ebx, edi
0x1800033e2  lea     rax, qword_18005B368
0x1800033e9  mov     edx, ebx
0x1800033eb  shl     rdx, 5
0x1800033ef  mov     rcx, r15; String1
0x1800033f2  mov     rdx, [rdx+rax]; String2
0x1800033f6  call    _wcsicmp_0
0x1800033fb  test    eax, eax
0x1800033fd  jz      short loc_18000340B
0x1800033ff  add     ebx, edi
0x180003401  cmp     ebx, 0Ah
0x180003404  jl      short loc_1800033E2
0x180003406  jmp     loc_1800036CF
0x18000340b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000340f  mov     rax, r14
0x180003412  xor     ecx, ecx
0x180003414  inc     rax
0x180003417  cmp     [r15+rax*2], cx
0x18000341c  jnz     short loc_180003414
0x18000341e  mov     rcx, gs:60h
0x180003427  lea     ebx, ds:12h[rax*2]
0x18000342e  mov     r8d, ebx; Size
0x180003431  mov     edx, 8; Flags
0x180003436  mov     [rbp+arg_18], ebx
0x180003439  mov     rcx, [rcx+30h]; HeapHandle
0x18000343d  call    cs:__imp_RtlAllocateHeap
0x180003443  mov     r12, rax
0x180003446  mov     [rbp+KeyValueInformation], rax
0x18000344a  xor     eax, eax
0x18000344c  test    r12, r12
0x18000344f  jnz     short loc_180003476
0x180003451  lea     r9, aFailedToAlloca_4; "Failed to allocate partial info."
0x180003458  mov     r8d, 4C6h
0x18000345e  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x180003465  mov     ecx, edi
0x180003467  mov     ebx, 0C0000017h
0x18000346c  call    AslLogCallPrintf
0x180003471  jmp     loc_1800036D4
0x180003476  mov     r12d, eax
0x180003479  mov     rax, [rbp+KeyValueInformation]
0x18000347d  lea     rcx, [rbp+arg_10]
0x180003481  mov     r9, rax; KeyValueInformation
0x180003484  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x180003489  mov     r8d, 2; KeyValueInformationClass
0x18000348f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180003493  mov     edx, r12d; Index
0x180003496  mov     [rsp+50h+Length], ebx; Length
0x18000349a  call    cs:__imp_ZwEnumerateValueKey
0x1800034a0  mov     ebx, eax
0x1800034a2  cmp     eax, 8000001Ah
0x1800034a7  jz      loc_1800036CB
0x1800034ad  cmp     eax, 80000005h
0x1800034b2  jz      short loc_1800034DE
0x1800034b4  cmp     eax, 0C0000023h
0x1800034b9  jz      short loc_1800034DE
0x1800034bb  test    eax, eax
0x1800034bd  js      loc_1800036AA
0x1800034c3  mov     rax, [rbp+KeyValueInformation]
0x1800034c7  cmp     [rax+4], edi
0x1800034ca  jnz     short loc_1800034E2
0x1800034cc  lea     rdx, [rax+0Ch]; String2
0x1800034d0  mov     rcx, r15; String1
0x1800034d3  call    _wcsicmp_0
0x1800034d8  xor     ecx, ecx
0x1800034da  test    eax, eax
0x1800034dc  jz      short loc_1800034EA
0x1800034de  mov     rax, [rbp+KeyValueInformation]
0x1800034e2  mov     ebx, [rbp+arg_18]
0x1800034e5  add     r12d, edi
0x1800034e8  jmp     short loc_18000347D
0x1800034ea  mov     rax, r14
0x1800034ed  inc     rax
0x1800034f0  cmp     [r15+rax*2], cx
0x1800034f5  jnz     short loc_1800034ED
0x1800034f7  mov     rcx, gs:60h
0x180003500  lea     ebx, ds:21Ah[rax*2]
0x180003507  mov     r8d, ebx; Size
0x18000350a  mov     edx, 8; Flags
0x18000350f  mov     r15d, ebx
0x180003512  mov     rcx, [rcx+30h]; HeapHandle
0x180003516  call    cs:__imp_RtlAllocateHeap
0x18000351c  mov     r13, rax
0x18000351f  test    rax, rax
0x180003522  jnz     short loc_18000353B
0x180003524  mov     ebx, 0C0000017h
0x180003529  lea     r9, aFailedToAlloca_24; "Failed to allocate basic info."
0x180003530  mov     r8d, 4EAh
0x180003536  jmp     loc_1800036B7
0x18000353b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000353f  lea     rax, [rbp+arg_10]
0x180003543  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180003548  mov     r9, r13; KeyValueInformation
0x18000354b  xor     r8d, r8d; KeyValueInformationClass
0x18000354e  mov     [rsp+50h+Length], ebx; Length
0x180003552  mov     edx, r12d; Index
0x180003555  call    cs:__imp_ZwEnumerateValueKey
0x18000355b  xor     r12d, r12d
0x18000355e  mov     ebx, eax
0x180003560  test    eax, eax
0x180003562  jns     short loc_180003576
0x180003564  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x18000356b  mov     r8d, 4F5h
0x180003571  jmp     loc_1800036B7
0x180003576  mov     eax, [rbp+arg_10]
0x180003579  add     rax, 2
0x18000357d  cmp     rax, r15
0x180003580  jbe     short loc_180003599
0x180003582  mov     ebx, 0C0000023h
0x180003587  lea     r9, aBufferTooSmall_2; "Buffer too small to query basic info."
0x18000358e  mov     r8d, 4FAh
0x180003594  jmp     loc_1800036B7
0x180003599  mov     rbx, cs:String1
0x1800035a0  test    rbx, rbx
0x1800035a3  jnz     short loc_1800035F4
0x1800035a5  xor     edx, edx; hFile
0x1800035a7  lea     rcx, LibFileName; "ntdll.dll"
0x1800035ae  mov     r8d, 800h; dwFlags
0x1800035b4  mov     ebx, 7FFE0030h
0x1800035b9  call    cs:__imp_LoadLibraryExW
0x1800035bf  mov     rsi, rax
0x1800035c2  test    rax, rax
0x1800035c5  jz      short loc_1800035ED
0x1800035c7  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x1800035ce  mov     rcx, rax; hModule
0x1800035d1  call    cs:__imp_GetProcAddress
0x1800035d7  test    rax, rax
0x1800035da  jz      short loc_1800035E4
0x1800035dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e1  mov     rbx, rax
0x1800035e4  mov     rcx, rsi; hLibModule
0x1800035e7  call    cs:__imp_FreeLibrary
0x1800035ed  mov     cs:String1, rbx
0x1800035f4  mov     r8, r14
0x1800035f7  inc     r8; MaxCount
0x1800035fa  cmp     [rbx+r8*2], r12w
0x1800035ff  jnz     short loc_1800035F7
0x180003601  lea     rdx, [r13+0Ch]; String2
0x180003605  mov     rcx, rbx; String1
0x180003608  call    _wcsnicmp_0
0x18000360d  test    eax, eax
0x18000360f  jnz     short loc_180003659
0x180003611  inc     r14
0x180003614  cmp     [rbx+r14*2], r12w
0x180003619  jnz     short loc_180003611
0x18000361b  lea     rdx, ds:0Ch[r14*2]
0x180003623  add     rdx, r13
0x180003626  lea     rcx, [rbp+var_18]
0x18000362a  call    AslPathToSystemPath
0x18000362f  xor     r14d, r14d
0x180003632  mov     ebx, eax
0x180003634  test    eax, eax
0x180003636  jns     short loc_18000367E
0x180003638  lea     r9, aFailedToAlloca_14; "Failed to allocate or convert stub path"...
0x18000363f  mov     r8d, 50Eh
0x180003645  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18000364c  mov     ecx, edi
0x18000364e  call    AslLogCallPrintf
0x180003653  mov     rsi, [rbp+var_18]
0x180003657  jmp     short loc_1800036C5
0x180003659  lea     rdx, [r13+0Ch]
0x18000365d  lea     rcx, [rbp+var_18]
0x180003661  call    AslStringDuplicate
0x180003666  xor     r14d, r14d
0x180003669  mov     ebx, eax
0x18000366b  test    eax, eax
0x18000366d  jns     short loc_18000367E
0x18000366f  lea     r9, aFailedToDuplic; "Failed to duplicate stub path."
0x180003676  mov     r8d, 515h
0x18000367c  jmp     short loc_180003645
0x18000367e  mov     rsi, [rbp+var_18]
0x180003682  test    rsi, rsi
0x180003685  jnz     short loc_18000369B
0x180003687  mov     ebx, 0C0000017h
0x18000368c  lea     r9, aFailedToAlloca_32; "Failed to allocate stub path."
0x180003693  mov     r8d, 51Ch
0x180003699  jmp     short loc_1800036B7
0x18000369b  mov     rax, [rbp+arg_0]
0x18000369f  mov     ebx, r14d
0x1800036a2  mov     [rax], rsi
0x1800036a5  mov     rsi, r14
0x1800036a8  jmp     short loc_1800036C5
0x1800036aa  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x1800036b1  mov     r8d, 4D9h
0x1800036b7  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1800036be  mov     ecx, edi
0x1800036c0  call    AslLogCallPrintf
0x1800036c5  mov     r12, [rbp+KeyValueInformation]
0x1800036c9  jmp     short loc_1800036D4
0x1800036cb  mov     r12, [rbp+KeyValueInformation]
0x1800036cf  mov     ebx, 0C0000034h
0x1800036d4  mov     rcx, [rbp+KeyHandle]; Handle
0x1800036d8  lea     rax, [rcx-1]
0x1800036dc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800036e0  ja      short loc_1800036E8
0x1800036e2  call    cs:__imp_ZwClose
0x1800036e8  test    rsi, rsi
0x1800036eb  jz      short loc_180003702
0x1800036ed  mov     rcx, gs:60h
0x1800036f6  mov     rdx, rsi
0x1800036f9  mov     rcx, [rcx+30h]
0x1800036fd  call    AslFree
0x180003702  test    r12, r12
0x180003705  jz      short loc_18000371C
0x180003707  mov     rcx, gs:60h
0x180003710  mov     rdx, r12
0x180003713  mov     rcx, [rcx+30h]
0x180003717  call    AslFree
0x18000371c  test    r13, r13
0x18000371f  jz      short loc_180003736
0x180003721  mov     rcx, gs:60h
0x18000372a  mov     rdx, r13
0x18000372d  mov     rcx, [rcx+30h]
0x180003731  call    AslFree
0x180003736  mov     eax, ebx
0x180003738  mov     rbx, [rsp+50h+arg_8]
0x180003740  add     rsp, 50h
0x180003744  pop     r15
0x180003746  pop     r14
0x180003748  pop     r13
0x18000374a  pop     r12
0x18000374c  pop     rdi
0x18000374d  pop     rsi
0x18000374e  pop     rbp
0x18000374f  retn
```
