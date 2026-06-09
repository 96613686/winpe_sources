# SdbpGetManifestedMergeStubAlloc

- ea: `0x140038174`
- end: `0x1400385d4`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1120`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400375fc`
- `0x1400385dc`

## callees

- `0x140001b64`
- `0x140038174`
- `0x140038d3c`
- `0x140038e44`
- `0x14003bf18`
- `0x14003c368`
- `0x14003c618`
- `0x14003e090`
- `0x140041140`
- `0x140047010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14003848b`
- `msvcrt!_wcsnicmp` at `0x14003848b`
- `ntdll!ZwClose` at `0x140038566`
- `ntdll!ZwClose` at `0x140038566`
- `ntdll!RtlAllocateHeap` at `0x1400382c0`
- `ntdll!RtlAllocateHeap` at `0x140038399`
- `ntdll!RtlAllocateHeap` at `0x1400382c0`
- `ntdll!RtlAllocateHeap` at `0x140038399`
- `ntdll!ZwEnumerateValueKey` at `0x14003831d`
- `ntdll!ZwEnumerateValueKey` at `0x1400383d8`
- `ntdll!ZwEnumerateValueKey` at `0x14003831d`
- `ntdll!ZwEnumerateValueKey` at `0x1400383d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140038454`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140038454`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003846a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003846a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003843c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003843c`

## string_xrefs

- `0x14003842a`: `ntdll.dll`
- `0x1400381ee`: `SdbpGetManifestedMergeStubAlloc`
- `0x140038250`: `SdbpGetManifestedMergeStubAlloc`
- `0x1400382e1`: `SdbpGetManifestedMergeStubAlloc`
- `0x1400384c9`: `SdbpGetManifestedMergeStubAlloc`
- `0x14003853b`: `SdbpGetManifestedMergeStubAlloc`
- `0x14003823f`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x14003820f`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x1400384bc`: `Failed to allocate or convert stub path.`
- `0x140038510`: `Failed to allocate stub path.`
- `0x1400384f3`: `Failed to duplicate stub path.`

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
              1);
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
      while ( wcsicmp_0(a2, (const wchar_t *)qword_1400486F8[4 * v10]) )
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
        if ( v16 == -2147483643 || v16 == -1073741789 )
          goto LABEL_26;
        if ( v16 == -2147483622 )
        {
          Heap = (PVOID)KeyValueInformation;
          goto LABEL_57;
        }
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
        v20 = (__int64)qword_140064238;
        if ( !qword_140064238 )
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
          qword_140064238 = (wchar_t *)v20;
        }
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)(v20 + 2 * v24) );
        if ( _wcsnicmp((const wchar_t *)v20, v8 + 6, v24) )
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
0x140038174  mov     [rsp-38h+arg_8], rbx
0x140038179  mov     [rsp-38h+arg_0], rcx
0x14003817e  push    rbp
0x14003817f  push    rsi
0x140038180  push    rdi
0x140038181  push    r12
0x140038183  push    r13
0x140038185  push    r14
0x140038187  push    r15
0x140038189  mov     rbp, rsp
0x14003818c  sub     rsp, 50h
0x140038190  xor     r14d, r14d
0x140038193  mov     r15, rdx
0x140038196  mov     [rbp+arg_18], r14d
0x14003819a  mov     esi, r14d
0x14003819d  mov     [rbp+arg_10], r14d
0x1400381a1  mov     [rbp+var_18], r14
0x1400381a5  mov     [rbp+KeyHandle], r14
0x1400381a9  test    rcx, rcx
0x1400381ac  jnz     short loc_1400381B8
0x1400381ae  mov     eax, 0C00000EFh
0x1400381b3  jmp     loc_1400385BC
0x1400381b8  mov     [rcx], r14
0x1400381bb  call    SdbpGetMergeSdbsSupported
0x1400381c0  test    eax, eax
0x1400381c2  jnz     short loc_1400381CE
0x1400381c4  mov     ebx, 0C0000034h
0x1400381c9  jmp     loc_1400385BA
0x1400381ce  lea     rcx, [rbp+arg_18]
0x1400381d2  call    SdbpGetMergeSdbsDisabled
0x1400381d7  mov     ebx, eax
0x1400381d9  test    eax, eax
0x1400381db  jns     short loc_140038204
0x1400381dd  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x1400381e4  mov     [rsp+50h+Length], eax
0x1400381e8  mov     r8d, 4A2h
0x1400381ee  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1400381f5  mov     ecx, 1
0x1400381fa  call    AslLogCallPrintf
0x1400381ff  jmp     loc_1400385BA
0x140038204  cmp     [rbp+arg_18], r14d
0x140038208  jnz     short loc_1400381C4
0x14003820a  mov     edi, 1
0x14003820f  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x140038216  mov     r9d, edi
0x140038219  lea     rcx, [rbp+KeyHandle]
0x14003821d  mov     r8d, 80000100h
0x140038223  mov     r12, r14
0x140038226  mov     r13, r14
0x140038229  call    AslRegistryGetKey
0x14003822e  mov     ebx, eax
0x140038230  test    eax, eax
0x140038232  jns     short loc_140038263
0x140038234  cmp     eax, 0C0000034h
0x140038239  jz      loc_140038558
0x14003823f  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x140038246  mov     [rsp+50h+Length], eax
0x14003824a  mov     r8d, 4B2h
0x140038250  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x140038257  mov     ecx, edi
0x140038259  call    AslLogCallPrintf
0x14003825e  jmp     loc_140038558
0x140038263  mov     ebx, edi
0x140038265  lea     rax, qword_1400486F8
0x14003826c  mov     edx, ebx
0x14003826e  shl     rdx, 5
0x140038272  mov     rcx, r15; String1
0x140038275  mov     rdx, [rdx+rax]; String2
0x140038279  call    _wcsicmp_0
0x14003827e  test    eax, eax
0x140038280  jz      short loc_14003828E
0x140038282  add     ebx, edi
0x140038284  cmp     ebx, 0Ah
0x140038287  jl      short loc_140038265
0x140038289  jmp     loc_140038553
0x14003828e  or      r14, 0FFFFFFFFFFFFFFFFh
0x140038292  mov     rax, r14
0x140038295  xor     ecx, ecx
0x140038297  inc     rax
0x14003829a  cmp     [r15+rax*2], cx
0x14003829f  jnz     short loc_140038297
0x1400382a1  mov     rcx, gs:60h
0x1400382aa  lea     ebx, ds:12h[rax*2]
0x1400382b1  mov     r8d, ebx; Size
0x1400382b4  mov     edx, 8; Flags
0x1400382b9  mov     [rbp+arg_18], ebx
0x1400382bc  mov     rcx, [rcx+30h]; HeapHandle
0x1400382c0  call    cs:__imp_RtlAllocateHeap
0x1400382c6  mov     r12, rax
0x1400382c9  mov     [rbp+KeyValueInformation], rax
0x1400382cd  xor     eax, eax
0x1400382cf  test    r12, r12
0x1400382d2  jnz     short loc_1400382F9
0x1400382d4  lea     r9, aFailedToAlloca_1; "Failed to allocate partial info."
0x1400382db  mov     r8d, 4C6h
0x1400382e1  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1400382e8  mov     ecx, edi
0x1400382ea  mov     ebx, 0C0000017h
0x1400382ef  call    AslLogCallPrintf
0x1400382f4  jmp     loc_140038558
0x1400382f9  mov     r12d, eax
0x1400382fc  mov     rax, [rbp+KeyValueInformation]
0x140038300  lea     rcx, [rbp+arg_10]
0x140038304  mov     r9, rax; KeyValueInformation
0x140038307  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x14003830c  mov     r8d, 2; KeyValueInformationClass
0x140038312  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140038316  mov     edx, r12d; Index
0x140038319  mov     [rsp+50h+Length], ebx; Length
0x14003831d  call    cs:__imp_ZwEnumerateValueKey
0x140038323  mov     ebx, eax
0x140038325  cmp     eax, 80000005h
0x14003832a  jz      short loc_140038361
0x14003832c  cmp     eax, 0C0000023h
0x140038331  jz      short loc_140038361
0x140038333  cmp     eax, 8000001Ah
0x140038338  jz      loc_14003854F
0x14003833e  test    eax, eax
0x140038340  js      loc_14003852E
0x140038346  mov     rax, [rbp+KeyValueInformation]
0x14003834a  cmp     [rax+4], edi
0x14003834d  jnz     short loc_140038365
0x14003834f  lea     rdx, [rax+0Ch]; String2
0x140038353  mov     rcx, r15; String1
0x140038356  call    _wcsicmp_0
0x14003835b  xor     ecx, ecx
0x14003835d  test    eax, eax
0x14003835f  jz      short loc_14003836D
0x140038361  mov     rax, [rbp+KeyValueInformation]
0x140038365  mov     ebx, [rbp+arg_18]
0x140038368  add     r12d, edi
0x14003836b  jmp     short loc_140038300
0x14003836d  mov     rax, r14
0x140038370  inc     rax
0x140038373  cmp     [r15+rax*2], cx
0x140038378  jnz     short loc_140038370
0x14003837a  mov     rcx, gs:60h
0x140038383  lea     ebx, ds:21Ah[rax*2]
0x14003838a  mov     r8d, ebx; Size
0x14003838d  mov     edx, 8; Flags
0x140038392  mov     r15d, ebx
0x140038395  mov     rcx, [rcx+30h]; HeapHandle
0x140038399  call    cs:__imp_RtlAllocateHeap
0x14003839f  mov     r13, rax
0x1400383a2  test    rax, rax
0x1400383a5  jnz     short loc_1400383BE
0x1400383a7  mov     ebx, 0C0000017h
0x1400383ac  lea     r9, aFailedToAlloca_7; "Failed to allocate basic info."
0x1400383b3  mov     r8d, 4EAh
0x1400383b9  jmp     loc_14003853B
0x1400383be  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400383c2  lea     rax, [rbp+arg_10]
0x1400383c6  mov     [rsp+50h+ResultLength], rax; ResultLength
0x1400383cb  mov     r9, r13; KeyValueInformation
0x1400383ce  xor     r8d, r8d; KeyValueInformationClass
0x1400383d1  mov     [rsp+50h+Length], ebx; Length
0x1400383d5  mov     edx, r12d; Index
0x1400383d8  call    cs:__imp_ZwEnumerateValueKey
0x1400383de  xor     r12d, r12d
0x1400383e1  mov     ebx, eax
0x1400383e3  test    eax, eax
0x1400383e5  jns     short loc_1400383F9
0x1400383e7  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x1400383ee  mov     r8d, 4F5h
0x1400383f4  jmp     loc_14003853B
0x1400383f9  mov     eax, [rbp+arg_10]
0x1400383fc  add     rax, 2
0x140038400  cmp     rax, r15
0x140038403  jbe     short loc_14003841C
0x140038405  mov     ebx, 0C0000023h
0x14003840a  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x140038411  mov     r8d, 4FAh
0x140038417  jmp     loc_14003853B
0x14003841c  mov     rbx, cs:qword_140064238
0x140038423  test    rbx, rbx
0x140038426  jnz     short loc_140038477
0x140038428  xor     edx, edx; hFile
0x14003842a  lea     rcx, LibFileName; "ntdll.dll"
0x140038431  mov     r8d, 800h; dwFlags
0x140038437  mov     ebx, 7FFE0030h
0x14003843c  call    cs:__imp_LoadLibraryExW
0x140038442  mov     rsi, rax
0x140038445  test    rax, rax
0x140038448  jz      short loc_140038470
0x14003844a  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x140038451  mov     rcx, rax; hModule
0x140038454  call    cs:__imp_GetProcAddress
0x14003845a  test    rax, rax
0x14003845d  jz      short loc_140038467
0x14003845f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038464  mov     rbx, rax
0x140038467  mov     rcx, rsi; hLibModule
0x14003846a  call    cs:__imp_FreeLibrary
0x140038470  mov     cs:qword_140064238, rbx
0x140038477  mov     r8, r14
0x14003847a  inc     r8; MaxCount
0x14003847d  cmp     [rbx+r8*2], r12w
0x140038482  jnz     short loc_14003847A
0x140038484  lea     rdx, [r13+0Ch]; String2
0x140038488  mov     rcx, rbx; String1
0x14003848b  call    cs:__imp__wcsnicmp
0x140038491  test    eax, eax
0x140038493  jnz     short loc_1400384DD
0x140038495  inc     r14
0x140038498  cmp     [rbx+r14*2], r12w
0x14003849d  jnz     short loc_140038495
0x14003849f  lea     rdx, ds:0Ch[r14*2]
0x1400384a7  add     rdx, r13
0x1400384aa  lea     rcx, [rbp+var_18]
0x1400384ae  call    AslPathToSystemPath
0x1400384b3  xor     r14d, r14d
0x1400384b6  mov     ebx, eax
0x1400384b8  test    eax, eax
0x1400384ba  jns     short loc_140038502
0x1400384bc  lea     r9, aFailedToAlloca_3; "Failed to allocate or convert stub path"...
0x1400384c3  mov     r8d, 50Eh
0x1400384c9  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1400384d0  mov     ecx, edi
0x1400384d2  call    AslLogCallPrintf
0x1400384d7  mov     rsi, [rbp+var_18]
0x1400384db  jmp     short loc_140038549
0x1400384dd  lea     rdx, [r13+0Ch]
0x1400384e1  lea     rcx, [rbp+var_18]
0x1400384e5  call    AslStringDuplicate
0x1400384ea  xor     r14d, r14d
0x1400384ed  mov     ebx, eax
0x1400384ef  test    eax, eax
0x1400384f1  jns     short loc_140038502
0x1400384f3  lea     r9, aFailedToDuplic; "Failed to duplicate stub path."
0x1400384fa  mov     r8d, 515h
0x140038500  jmp     short loc_1400384C9
0x140038502  mov     rsi, [rbp+var_18]
0x140038506  test    rsi, rsi
0x140038509  jnz     short loc_14003851F
0x14003850b  mov     ebx, 0C0000017h
0x140038510  lea     r9, aFailedToAlloca_11; "Failed to allocate stub path."
0x140038517  mov     r8d, 51Ch
0x14003851d  jmp     short loc_14003853B
0x14003851f  mov     rax, [rbp+arg_0]
0x140038523  mov     ebx, r14d
0x140038526  mov     [rax], rsi
0x140038529  mov     rsi, r14
0x14003852c  jmp     short loc_140038549
0x14003852e  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x140038535  mov     r8d, 4D9h
0x14003853b  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x140038542  mov     ecx, edi
0x140038544  call    AslLogCallPrintf
0x140038549  mov     r12, [rbp+KeyValueInformation]
0x14003854d  jmp     short loc_140038558
0x14003854f  mov     r12, [rbp+KeyValueInformation]
0x140038553  mov     ebx, 0C0000034h
0x140038558  mov     rcx, [rbp+KeyHandle]; Handle
0x14003855c  lea     rax, [rcx-1]
0x140038560  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140038564  ja      short loc_14003856C
0x140038566  call    cs:__imp_ZwClose
0x14003856c  test    rsi, rsi
0x14003856f  jz      short loc_140038586
0x140038571  mov     rcx, gs:60h
0x14003857a  mov     rdx, rsi
0x14003857d  mov     rcx, [rcx+30h]
0x140038581  call    AslFree
0x140038586  test    r12, r12
0x140038589  jz      short loc_1400385A0
0x14003858b  mov     rcx, gs:60h
0x140038594  mov     rdx, r12
0x140038597  mov     rcx, [rcx+30h]
0x14003859b  call    AslFree
0x1400385a0  test    r13, r13
0x1400385a3  jz      short loc_1400385BA
0x1400385a5  mov     rcx, gs:60h
0x1400385ae  mov     rdx, r13
0x1400385b1  mov     rcx, [rcx+30h]
0x1400385b5  call    AslFree
0x1400385ba  mov     eax, ebx
0x1400385bc  mov     rbx, [rsp+50h+arg_8]
0x1400385c4  add     rsp, 50h
0x1400385c8  pop     r15
0x1400385ca  pop     r14
0x1400385cc  pop     r13
0x1400385ce  pop     r12
0x1400385d0  pop     rdi
0x1400385d1  pop     rsi
0x1400385d2  pop     rbp
0x1400385d3  retn
```
