# SdbpGetManifestedMergeStubAlloc

- ea: `0x18005f30c`
- end: `0x18005f721`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1045`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005f728`

## callees

- `0x180002790`
- `0x1800027a8`
- `0x180051a88`
- `0x1800543c0`
- `0x180054934`
- `0x18005a404`
- `0x18005a480`
- `0x18005f30c`
- `0x18005ff28`
- `0x18006002c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18005f458`
- `ntdll!RtlAllocateHeap` at `0x18005f531`
- `ntdll!RtlAllocateHeap` at `0x18005f458`
- `ntdll!RtlAllocateHeap` at `0x18005f531`
- `ntdll!RtlFreeHeap` at `0x18005f6c7`
- `ntdll!RtlFreeHeap` at `0x18005f6e4`
- `ntdll!RtlFreeHeap` at `0x18005f701`
- `ntdll!RtlFreeHeap` at `0x18005f6c7`
- `ntdll!RtlFreeHeap` at `0x18005f6e4`
- `ntdll!RtlFreeHeap` at `0x18005f701`
- `ntdll!ZwClose` at `0x18005f6aa`
- `ntdll!ZwClose` at `0x18005f6aa`
- `ntdll!ZwEnumerateValueKey` at `0x18005f4b5`
- `ntdll!ZwEnumerateValueKey` at `0x18005f570`
- `ntdll!ZwEnumerateValueKey` at `0x18005f4b5`
- `ntdll!ZwEnumerateValueKey` at `0x18005f570`

## string_xrefs

- `0x18005f386`: `SdbpGetManifestedMergeStubAlloc`
- `0x18005f3e0`: `SdbpGetManifestedMergeStubAlloc`
- `0x18005f479`: `SdbpGetManifestedMergeStubAlloc`
- `0x18005f60d`: `SdbpGetManifestedMergeStubAlloc`
- `0x18005f67f`: `SdbpGetManifestedMergeStubAlloc`
- `0x18005f3cf`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x18005f3a8`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x18005f600`: `Failed to allocate or convert stub path.`
- `0x18005f654`: `Failed to allocate stub path.`
- `0x18005f637`: `Failed to duplicate stub path.`

## pseudocode

```c
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  void *v3; // rsi
  NTSTATUS v5; // ebx
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
  const wchar_t *NtSystemRoot; // rax
  const wchar_t *v21; // rbx
  size_t v22; // r8
  const wchar_t *KeyValueInformation; // [rsp+30h] [rbp-20h]
  void *v24; // [rsp+38h] [rbp-18h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+50h] BYREF
  ULONG v28; // [rsp+A8h] [rbp+58h] BYREF

  v28 = 0;
  v3 = 0;
  ResultLength = 0;
  v24 = 0;
  KeyHandle[0] = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&v28);
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
    if ( !v28 )
    {
      Heap = 0;
      v8 = 0;
      Key = AslRegistryGetKey(
              KeyHandle,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
              2147483904LL);
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
LABEL_52:
        if ( (unsigned __int64)KeyHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          ZwClose(KeyHandle[0]);
        if ( v3 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
        if ( Heap )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        if ( v8 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        return (unsigned int)v5;
      }
      v10 = 1;
      while ( wcsicmp(a2, *((const wchar_t **)&unk_18006B5F8 + 4 * v10)) )
      {
        if ( (int)++v10 >= 10 )
        {
LABEL_51:
          v5 = -1073741772;
          goto LABEL_52;
        }
      }
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      Length = 2 * v12 + 18;
      v28 = Length;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
      KeyValueInformation = (const wchar_t *)Heap;
      if ( !Heap )
      {
        v5 = -1073741801;
        AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1222, "Failed to allocate partial info.");
        goto LABEL_52;
      }
      v14 = 0;
      v15 = (wchar_t *)KeyValueInformation;
      while ( 1 )
      {
        v16 = ZwEnumerateValueKey(KeyHandle[0], v14, KeyValuePartialInformation, v15, Length, &ResultLength);
        v5 = v16;
        if ( v16 == -2147483643 || v16 == -1073741789 )
          goto LABEL_26;
        if ( v16 == -2147483622 )
        {
          Heap = (PVOID)KeyValueInformation;
          goto LABEL_51;
        }
        if ( v16 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1241, "Failed to query partial info.");
          goto LABEL_49;
        }
        v15 = (wchar_t *)KeyValueInformation;
        if ( *((_DWORD *)KeyValueInformation + 1) == 1 )
          break;
LABEL_27:
        Length = v28;
        ++v14;
      }
      if ( !wcsicmp(a2, KeyValueInformation + 6) )
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
LABEL_49:
          Heap = (PVOID)KeyValueInformation;
          goto LABEL_52;
        }
        v5 = ZwEnumerateValueKey(KeyHandle[0], v14, KeyValueBasicInformation, v8, v18, &ResultLength);
        if ( v5 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1269, "Failed to query basic info.");
          goto LABEL_49;
        }
        if ( (unsigned __int64)ResultLength + 2 > v19 )
        {
          v5 = -1073741789;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1274, "Buffer too small to query basic info.");
          goto LABEL_49;
        }
        NtSystemRoot = (const wchar_t *)AslPathGetNtSystemRoot();
        v21 = NtSystemRoot;
        v22 = -1;
        do
          ++v22;
        while ( NtSystemRoot[v22] );
        if ( wcsnicmp(NtSystemRoot, v8 + 6, v22) )
        {
          v5 = AslStringDuplicate(&v24, v8 + 6);
          if ( v5 < 0 )
          {
            AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1301, "Failed to duplicate stub path.");
            goto LABEL_42;
          }
        }
        else
        {
          do
            ++v11;
          while ( v21[v11] );
          v5 = AslPathToSystemPath(&v24, &v8[v11 + 6]);
          if ( v5 < 0 )
          {
            AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1294, "Failed to allocate or convert stub path.");
LABEL_42:
            v3 = v24;
            goto LABEL_49;
          }
        }
        v3 = v24;
        if ( v24 )
        {
          v5 = 0;
          *a1 = v24;
          v3 = 0;
        }
        else
        {
          v5 = -1073741801;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1308, "Failed to allocate stub path.");
        }
        goto LABEL_49;
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
0x18005f30c  mov     [rsp-38h+arg_8], rbx
0x18005f311  mov     [rsp-38h+arg_0], rcx
0x18005f316  push    rbp
0x18005f317  push    rsi
0x18005f318  push    rdi
0x18005f319  push    r12
0x18005f31b  push    r13
0x18005f31d  push    r14
0x18005f31f  push    r15
0x18005f321  mov     rbp, rsp
0x18005f324  sub     rsp, 50h
0x18005f328  xor     r14d, r14d
0x18005f32b  mov     r15, rdx
0x18005f32e  mov     [rbp+arg_18], r14d
0x18005f332  mov     esi, r14d
0x18005f335  mov     [rbp+arg_10], r14d
0x18005f339  mov     [rbp+var_18], r14
0x18005f33d  mov     [rbp+KeyHandle], r14
0x18005f341  test    rcx, rcx
0x18005f344  jnz     short loc_18005F350
0x18005f346  mov     eax, 0C00000EFh
0x18005f34b  jmp     loc_18005F709
0x18005f350  mov     [rcx], r14
0x18005f353  call    SdbpGetMergeSdbsSupported
0x18005f358  test    eax, eax
0x18005f35a  jnz     short loc_18005F366
0x18005f35c  mov     ebx, 0C0000034h
0x18005f361  jmp     loc_18005F707
0x18005f366  lea     rcx, [rbp+arg_18]
0x18005f36a  call    SdbpGetMergeSdbsDisabled
0x18005f36f  mov     ebx, eax
0x18005f371  test    eax, eax
0x18005f373  jns     short loc_18005F39C
0x18005f375  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x18005f37c  mov     [rsp+50h+Length], eax
0x18005f380  mov     r8d, 4A2h
0x18005f386  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18005f38d  mov     ecx, 1
0x18005f392  call    AslLogCallPrintf
0x18005f397  jmp     loc_18005F707
0x18005f39c  cmp     [rbp+arg_18], r14d
0x18005f3a0  jnz     short loc_18005F35C
0x18005f3a2  mov     r8d, 80000100h
0x18005f3a8  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005f3af  lea     rcx, [rbp+KeyHandle]
0x18005f3b3  mov     r12, r14
0x18005f3b6  mov     r13, r14
0x18005f3b9  call    AslRegistryGetKey
0x18005f3be  mov     ebx, eax
0x18005f3c0  test    eax, eax
0x18005f3c2  jns     short loc_18005F3F6
0x18005f3c4  cmp     eax, 0C0000034h
0x18005f3c9  jz      loc_18005F69C
0x18005f3cf  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x18005f3d6  mov     [rsp+50h+Length], eax
0x18005f3da  mov     r8d, 4B2h
0x18005f3e0  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18005f3e7  mov     ecx, 1
0x18005f3ec  call    AslLogCallPrintf
0x18005f3f1  jmp     loc_18005F69C
0x18005f3f6  mov     edi, 1
0x18005f3fb  mov     ebx, edi
0x18005f3fd  lea     rax, unk_18006B5F8
0x18005f404  mov     edx, ebx
0x18005f406  shl     rdx, 5
0x18005f40a  mov     rcx, r15; String1
0x18005f40d  mov     rdx, [rdx+rax]; String2
0x18005f411  call    _wcsicmp
0x18005f416  test    eax, eax
0x18005f418  jz      short loc_18005F426
0x18005f41a  add     ebx, edi
0x18005f41c  cmp     ebx, 0Ah
0x18005f41f  jl      short loc_18005F3FD
0x18005f421  jmp     loc_18005F697
0x18005f426  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005f42a  mov     rax, r14
0x18005f42d  xor     ecx, ecx
0x18005f42f  inc     rax
0x18005f432  cmp     [r15+rax*2], cx
0x18005f437  jnz     short loc_18005F42F
0x18005f439  mov     rcx, gs:60h
0x18005f442  lea     ebx, ds:12h[rax*2]
0x18005f449  mov     r8d, ebx; Size
0x18005f44c  mov     edx, 8; Flags
0x18005f451  mov     [rbp+arg_18], ebx
0x18005f454  mov     rcx, [rcx+30h]; HeapHandle
0x18005f458  call    cs:__imp_RtlAllocateHeap
0x18005f45e  mov     r12, rax
0x18005f461  mov     [rbp+KeyValueInformation], rax
0x18005f465  xor     eax, eax
0x18005f467  test    r12, r12
0x18005f46a  jnz     short loc_18005F491
0x18005f46c  lea     r9, aFailedToAlloca_2; "Failed to allocate partial info."
0x18005f473  mov     r8d, 4C6h
0x18005f479  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18005f480  mov     ecx, edi
0x18005f482  mov     ebx, 0C0000017h
0x18005f487  call    AslLogCallPrintf
0x18005f48c  jmp     loc_18005F69C
0x18005f491  mov     r12d, eax
0x18005f494  mov     rax, [rbp+KeyValueInformation]
0x18005f498  lea     rcx, [rbp+arg_10]
0x18005f49c  mov     r9, rax; KeyValueInformation
0x18005f49f  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x18005f4a4  mov     r8d, 2; KeyValueInformationClass
0x18005f4aa  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005f4ae  mov     edx, r12d; Index
0x18005f4b1  mov     [rsp+50h+Length], ebx; Length
0x18005f4b5  call    cs:__imp_ZwEnumerateValueKey
0x18005f4bb  mov     ebx, eax
0x18005f4bd  cmp     eax, 80000005h
0x18005f4c2  jz      short loc_18005F4F9
0x18005f4c4  cmp     eax, 0C0000023h
0x18005f4c9  jz      short loc_18005F4F9
0x18005f4cb  cmp     eax, 8000001Ah
0x18005f4d0  jz      loc_18005F693
0x18005f4d6  test    eax, eax
0x18005f4d8  js      loc_18005F672
0x18005f4de  mov     rax, [rbp+KeyValueInformation]
0x18005f4e2  cmp     [rax+4], edi
0x18005f4e5  jnz     short loc_18005F4FD
0x18005f4e7  lea     rdx, [rax+0Ch]; String2
0x18005f4eb  mov     rcx, r15; String1
0x18005f4ee  call    _wcsicmp
0x18005f4f3  xor     ecx, ecx
0x18005f4f5  test    eax, eax
0x18005f4f7  jz      short loc_18005F505
0x18005f4f9  mov     rax, [rbp+KeyValueInformation]
0x18005f4fd  mov     ebx, [rbp+arg_18]
0x18005f500  add     r12d, edi
0x18005f503  jmp     short loc_18005F498
0x18005f505  mov     rax, r14
0x18005f508  inc     rax
0x18005f50b  cmp     [r15+rax*2], cx
0x18005f510  jnz     short loc_18005F508
0x18005f512  mov     rcx, gs:60h
0x18005f51b  lea     ebx, ds:21Ah[rax*2]
0x18005f522  mov     r8d, ebx; Size
0x18005f525  mov     edx, 8; Flags
0x18005f52a  mov     r15d, ebx
0x18005f52d  mov     rcx, [rcx+30h]; HeapHandle
0x18005f531  call    cs:__imp_RtlAllocateHeap
0x18005f537  mov     r13, rax
0x18005f53a  test    rax, rax
0x18005f53d  jnz     short loc_18005F556
0x18005f53f  mov     ebx, 0C0000017h
0x18005f544  lea     r9, aFailedToAlloca_7; "Failed to allocate basic info."
0x18005f54b  mov     r8d, 4EAh
0x18005f551  jmp     loc_18005F67F
0x18005f556  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005f55a  lea     rax, [rbp+arg_10]
0x18005f55e  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18005f563  mov     r9, r13; KeyValueInformation
0x18005f566  xor     r8d, r8d; KeyValueInformationClass
0x18005f569  mov     [rsp+50h+Length], ebx; Length
0x18005f56d  mov     edx, r12d; Index
0x18005f570  call    cs:__imp_ZwEnumerateValueKey
0x18005f576  xor     r12d, r12d
0x18005f579  mov     ebx, eax
0x18005f57b  test    eax, eax
0x18005f57d  jns     short loc_18005F591
0x18005f57f  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x18005f586  mov     r8d, 4F5h
0x18005f58c  jmp     loc_18005F67F
0x18005f591  mov     eax, [rbp+arg_10]
0x18005f594  add     rax, 2
0x18005f598  cmp     rax, r15
0x18005f59b  jbe     short loc_18005F5B4
0x18005f59d  mov     ebx, 0C0000023h
0x18005f5a2  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x18005f5a9  mov     r8d, 4FAh
0x18005f5af  jmp     loc_18005F67F
0x18005f5b4  call    AslPathGetNtSystemRoot
0x18005f5b9  mov     rbx, rax
0x18005f5bc  mov     r8, r14
0x18005f5bf  inc     r8; MaxCount
0x18005f5c2  cmp     [rax+r8*2], r12w
0x18005f5c7  jnz     short loc_18005F5BF
0x18005f5c9  lea     rdx, [r13+0Ch]; String2
0x18005f5cd  mov     rcx, rbx; String1
0x18005f5d0  call    _wcsnicmp
0x18005f5d5  test    eax, eax
0x18005f5d7  jnz     short loc_18005F621
0x18005f5d9  inc     r14
0x18005f5dc  cmp     [rbx+r14*2], r12w
0x18005f5e1  jnz     short loc_18005F5D9
0x18005f5e3  lea     rdx, ds:0Ch[r14*2]
0x18005f5eb  add     rdx, r13
0x18005f5ee  lea     rcx, [rbp+var_18]
0x18005f5f2  call    AslPathToSystemPath
0x18005f5f7  xor     r14d, r14d
0x18005f5fa  mov     ebx, eax
0x18005f5fc  test    eax, eax
0x18005f5fe  jns     short loc_18005F646
0x18005f600  lea     r9, aFailedToAlloca_3; "Failed to allocate or convert stub path"...
0x18005f607  mov     r8d, 50Eh
0x18005f60d  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18005f614  mov     ecx, edi
0x18005f616  call    AslLogCallPrintf
0x18005f61b  mov     rsi, [rbp+var_18]
0x18005f61f  jmp     short loc_18005F68D
0x18005f621  lea     rdx, [r13+0Ch]
0x18005f625  lea     rcx, [rbp+var_18]
0x18005f629  call    AslStringDuplicate
0x18005f62e  xor     r14d, r14d
0x18005f631  mov     ebx, eax
0x18005f633  test    eax, eax
0x18005f635  jns     short loc_18005F646
0x18005f637  lea     r9, aFailedToDuplic; "Failed to duplicate stub path."
0x18005f63e  mov     r8d, 515h
0x18005f644  jmp     short loc_18005F60D
0x18005f646  mov     rsi, [rbp+var_18]
0x18005f64a  test    rsi, rsi
0x18005f64d  jnz     short loc_18005F663
0x18005f64f  mov     ebx, 0C0000017h
0x18005f654  lea     r9, aFailedToAlloca_13; "Failed to allocate stub path."
0x18005f65b  mov     r8d, 51Ch
0x18005f661  jmp     short loc_18005F67F
0x18005f663  mov     rax, [rbp+arg_0]
0x18005f667  mov     ebx, r14d
0x18005f66a  mov     [rax], rsi
0x18005f66d  mov     rsi, r14
0x18005f670  jmp     short loc_18005F68D
0x18005f672  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x18005f679  mov     r8d, 4D9h
0x18005f67f  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18005f686  mov     ecx, edi
0x18005f688  call    AslLogCallPrintf
0x18005f68d  mov     r12, [rbp+KeyValueInformation]
0x18005f691  jmp     short loc_18005F69C
0x18005f693  mov     r12, [rbp+KeyValueInformation]
0x18005f697  mov     ebx, 0C0000034h
0x18005f69c  mov     rcx, [rbp+KeyHandle]; Handle
0x18005f6a0  lea     rax, [rcx-1]
0x18005f6a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005f6a8  ja      short loc_18005F6B0
0x18005f6aa  call    cs:__imp_ZwClose
0x18005f6b0  test    rsi, rsi
0x18005f6b3  jz      short loc_18005F6CD
0x18005f6b5  mov     rcx, gs:60h
0x18005f6be  mov     r8, rsi; P
0x18005f6c1  xor     edx, edx; Flags
0x18005f6c3  mov     rcx, [rcx+30h]; HeapHandle
0x18005f6c7  call    cs:__imp_RtlFreeHeap
0x18005f6cd  test    r12, r12
0x18005f6d0  jz      short loc_18005F6EA
0x18005f6d2  mov     rcx, gs:60h
0x18005f6db  mov     r8, r12; P
0x18005f6de  xor     edx, edx; Flags
0x18005f6e0  mov     rcx, [rcx+30h]; HeapHandle
0x18005f6e4  call    cs:__imp_RtlFreeHeap
0x18005f6ea  test    r13, r13
0x18005f6ed  jz      short loc_18005F707
0x18005f6ef  mov     rcx, gs:60h
0x18005f6f8  mov     r8, r13; P
0x18005f6fb  xor     edx, edx; Flags
0x18005f6fd  mov     rcx, [rcx+30h]; HeapHandle
0x18005f701  call    cs:__imp_RtlFreeHeap
0x18005f707  mov     eax, ebx
0x18005f709  mov     rbx, [rsp+50h+arg_8]
0x18005f711  add     rsp, 50h
0x18005f715  pop     r15
0x18005f717  pop     r14
0x18005f719  pop     r13
0x18005f71b  pop     r12
0x18005f71d  pop     rdi
0x18005f71e  pop     rsi
0x18005f71f  pop     rbp
0x18005f720  retn
```
