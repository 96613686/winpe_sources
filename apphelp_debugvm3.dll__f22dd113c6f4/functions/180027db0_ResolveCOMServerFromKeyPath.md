# ResolveCOMServerFromKeyPath

- ea: `0x180027db0`
- end: `0x1800280e9`
- name: `ResolveCOMServerFromKeyPath`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027a50`

## callees

- `0x18000f114`
- `0x180027db0`
- `0x180059169`

## import_xrefs

- `ntdll!NtClose` at `0x180027ecf`
- `ntdll!NtClose` at `0x180027ecf`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180027f67`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180027f67`
- `ntdll!NtQueryValueKey` at `0x180027ea9`
- `ntdll!NtQueryValueKey` at `0x1800280c9`
- `ntdll!NtQueryValueKey` at `0x180027ea9`
- `ntdll!NtQueryValueKey` at `0x1800280c9`
- `ntdll!NtOpenKey` at `0x180027e4b`
- `ntdll!NtOpenKey` at `0x180027e4b`
- `ntdll!RtlFreeHeap` at `0x180027eec`
- `ntdll!RtlFreeHeap` at `0x18002806f`
- `ntdll!RtlFreeHeap` at `0x180027eec`
- `ntdll!RtlFreeHeap` at `0x18002806f`
- `ntdll!RtlAllocateHeap` at `0x180027e77`
- `ntdll!RtlAllocateHeap` at `0x18002808b`
- `ntdll!RtlAllocateHeap` at `0x180027e77`
- `ntdll!RtlAllocateHeap` at `0x18002808b`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027e12`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027e12`

## string_xrefs

- `0x180027f1f`: `ResolveCOMServerFromKeyPath`
- `0x180028006`: `ResolveCOMServerFromKeyPath`
- `0x180027fde`: `Failed to open key [%x]`

## pseudocode

```c
__int64 __fastcall ResolveCOMServerFromKeyPath(struct _UNICODE_STRING *a1, __int64 a2, void *a3, unsigned int a4)
{
  SIZE_T v4; // rsi
  unsigned int *Heap; // rdi
  NTSTATUS inited; // eax
  const char *v10; // r9
  __int64 v11; // r8
  unsigned int v12; // eax
  const char *v13; // r9
  __int64 v14; // r8
  ULONG Length[2]; // [rsp+28h] [rbp-39h]
  ULONG v16; // [rsp+38h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-21h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-19h] BYREF
  struct _UNICODE_STRING Source; // [rsp+58h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+17h] BYREF
  ULONG ResultLength; // [rsp+D0h] [rbp+6Fh] BYREF
  int v23; // [rsp+D4h] [rbp+73h]

  v23 = HIDWORD(a2);
  v4 = a4;
  v16 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  Heap = 0;
  DestinationString = 0;
  Source = 0;
  Destination = 0;
  memset(&ObjectAttributes, 0, 44);
  inited = RtlInitUnicodeStringEx(&DestinationString, &word_1800626B4);
  if ( inited < 0 )
  {
    v10 = "Failed to initialize value name [%x]";
    v11 = 238;
    goto LABEL_14;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  inited = NtOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
  if ( inited < 0 )
  {
    if ( inited == -1073741772 )
      goto LABEL_8;
    v10 = "Failed to open key [%x]";
    v11 = 254;
LABEL_14:
    Length[0] = inited;
    AslLogCallPrintf(1, "ResolveCOMServerFromKeyPath", v11, v10, *(_QWORD *)Length);
    goto LABEL_8;
  }
  if ( !a3 && (_DWORD)v4 )
  {
    v13 = "Bad parameters";
    v14 = 260;
    goto LABEL_24;
  }
  Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v4);
  if ( !Heap )
  {
    v13 = "Memory allocation failure";
    v14 = 269;
    goto LABEL_24;
  }
  inited = NtQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Heap, v4, &ResultLength);
  if ( inited < 0 )
  {
    if ( inited != -1073741789 )
    {
      v10 = "Failed to retrieve default key value [%x]";
      v11 = 312;
      goto LABEL_14;
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
    if ( !Heap )
    {
      v13 = "Memory allocation failure";
      v14 = 293;
      goto LABEL_24;
    }
    inited = NtQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Heap, ResultLength, &ResultLength);
    if ( inited < 0 )
    {
      v10 = "Failed to retrieve default key value [%x]";
      v11 = 307;
      goto LABEL_14;
    }
  }
  if ( Heap[1] == 1 )
  {
    v12 = Heap[3];
    if ( v12 + 2 < v12 )
    {
      v16 = -1;
      v13 = "DWORD overflow occured.";
      v14 = 319;
LABEL_24:
      AslLogCallPrintf(1, "ResolveCOMServerFromKeyPath", v14, v13);
      goto LABEL_8;
    }
    v16 = v12 + 2;
    if ( (unsigned int)v4 >= v12 + 2 )
    {
      memmove_0(a3, (char *)Heap + Heap[2], Heap[3]);
      *((_WORD *)a3 + ((unsigned __int64)Heap[3] >> 1)) = 0;
    }
  }
  else if ( Heap[1] == 2 )
  {
    Source.Buffer = (PWSTR)((char *)Heap + Heap[2]);
    Source.Length = *((_WORD *)Heap + 6);
    Source.MaximumLength = *((_WORD *)Heap + 6);
    Destination.Length = 0;
    Destination.Buffer = (PWSTR)a3;
    Destination.MaximumLength = v4;
    inited = RtlExpandEnvironmentStrings_U(0, &Source, &Destination, &v16);
    if ( (int)(inited + 0x80000000) >= 0 && inited != -1073741789 )
    {
      v10 = "Failed to expand key value [%x]";
      v11 = 343;
      goto LABEL_14;
    }
  }
LABEL_8:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return v16;
}

```

## disassembly

```asm
0x180027db0  mov     rax, rsp
0x180027db3  mov     [rax+8], rbx
0x180027db7  mov     [rax+18h], rsi
0x180027dbb  mov     [rax+10h], rdx
0x180027dbf  push    rbp
0x180027dc0  push    rdi
0x180027dc1  push    r14
0x180027dc3  lea     rbp, [rax-5Fh]
0x180027dc7  sub     rsp, 0A0h
0x180027dce  xorps   xmm0, xmm0
0x180027dd1  mov     esi, r9d
0x180027dd4  xor     eax, eax
0x180027dd6  mov     [rbp+57h+var_80], 0
0x180027ddd  mov     rbx, rcx
0x180027de0  mov     [rbp+57h+KeyHandle], rax
0x180027de4  xorps   xmm1, xmm1
0x180027de7  mov     [rbp+57h+arg_8], eax
0x180027dea  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180027dee  lea     rdx, word_1800626B4; SourceString
0x180027df5  mov     r14, r8
0x180027df8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180027dfc  xor     edi, edi
0x180027dfe  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180027e02  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180027e06  movups  xmmword ptr [rbp+57h+Source.Length], xmm1
0x180027e0a  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180027e0e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180027e12  call    cs:__imp_RtlInitUnicodeStringEx
0x180027e18  test    eax, eax
0x180027e1a  js      loc_180027F0D
0x180027e20  xorps   xmm0, xmm0
0x180027e23  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180027e2a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180027e2e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180027e32  mov     edx, 80000000h; DesiredAccess
0x180027e37  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180027e3e  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180027e42  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x180027e46  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180027e4b  call    cs:__imp_NtOpenKey
0x180027e51  test    eax, eax
0x180027e53  js      loc_180027FD3
0x180027e59  test    r14, r14
0x180027e5c  jz      loc_180028032
0x180027e62  mov     rcx, gs:60h
0x180027e6b  mov     r8, rsi; Size
0x180027e6e  mov     edx, 8; Flags
0x180027e73  mov     rcx, [rcx+30h]; HeapHandle
0x180027e77  call    cs:__imp_RtlAllocateHeap
0x180027e7d  mov     rdi, rax
0x180027e80  test    rax, rax
0x180027e83  jz      loc_180028049
0x180027e89  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180027e8d  lea     rax, [rbp+57h+arg_8]
0x180027e91  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x180027e96  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180027e9a  mov     ebx, 1
0x180027e9f  mov     [rsp+0B0h+Length], esi; Length
0x180027ea3  mov     r8d, ebx; KeyValueInformationClass
0x180027ea6  mov     r9, rdi; KeyValueInformation
0x180027ea9  call    cs:__imp_NtQueryValueKey
0x180027eaf  test    eax, eax
0x180027eb1  js      loc_180028017
0x180027eb7  cmp     [rdi+4], ebx
0x180027eba  jz      loc_180027F9A
0x180027ec0  cmp     dword ptr [rdi+4], 2
0x180027ec4  jz      short loc_180027F31
0x180027ec6  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180027eca  test    rcx, rcx
0x180027ecd  jz      short loc_180027ED5
0x180027ecf  call    cs:__imp_NtClose
0x180027ed5  test    rdi, rdi
0x180027ed8  jz      short loc_180027EF2
0x180027eda  mov     rcx, gs:60h
0x180027ee3  mov     r8, rdi; P
0x180027ee6  xor     edx, edx; Flags
0x180027ee8  mov     rcx, [rcx+30h]; HeapHandle
0x180027eec  call    cs:__imp_RtlFreeHeap
0x180027ef2  mov     eax, [rbp+57h+var_80]
0x180027ef5  lea     r11, [rsp+0B0h+var_10]
0x180027efd  mov     rbx, [r11+20h]
0x180027f01  mov     rsi, [r11+30h]
0x180027f05  mov     rsp, r11
0x180027f08  pop     r14
0x180027f0a  pop     rdi
0x180027f0b  pop     rbp
0x180027f0c  retn
0x180027f0d  lea     r9, aFailedToInitia_4; "Failed to initialize value name [%x]"
0x180027f14  mov     r8d, 0EEh
0x180027f1a  mov     ecx, 1
0x180027f1f  lea     rdx, aResolvecomserv; "ResolveCOMServerFromKeyPath"
0x180027f26  mov     [rsp+0B0h+Length], eax
0x180027f2a  call    AslLogCallPrintf
0x180027f2f  jmp     short loc_180027EC6
0x180027f31  mov     eax, [rdi+8]
0x180027f34  lea     r9, [rbp+57h+var_80]; Length
0x180027f38  add     rax, rdi
0x180027f3b  lea     r8, [rbp+57h+Destination]; Destination
0x180027f3f  mov     [rbp+57h+Source.Buffer], rax
0x180027f43  lea     rdx, [rbp+57h+Source]; Source
0x180027f47  movzx   eax, word ptr [rdi+0Ch]
0x180027f4b  xor     ecx, ecx; Environment
0x180027f4d  mov     [rbp+57h+Source.Length], ax
0x180027f51  movzx   eax, word ptr [rdi+0Ch]
0x180027f55  mov     [rbp+57h+Source.MaximumLength], ax
0x180027f59  xor     eax, eax
0x180027f5b  mov     [rbp+57h+Destination.Length], ax
0x180027f5f  mov     [rbp+57h+Destination.Buffer], r14
0x180027f63  mov     [rbp+57h+Destination.MaximumLength], si
0x180027f67  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x180027f6d  mov     edx, 80000000h
0x180027f72  lea     ecx, [rax+rdx]
0x180027f75  test    edx, ecx
0x180027f77  jnz     loc_180027EC6
0x180027f7d  cmp     eax, 0C0000023h
0x180027f82  jz      loc_180027EC6
0x180027f88  lea     r9, aFailedToExpand_3; "Failed to expand key value [%x]"
0x180027f8f  mov     r8d, 157h
0x180027f95  jmp     loc_18002802B
0x180027f9a  mov     eax, [rdi+0Ch]
0x180027f9d  lea     ecx, [rax+2]
0x180027fa0  cmp     ecx, eax
0x180027fa2  jb      short loc_180027FF0
0x180027fa4  mov     [rbp+57h+var_80], ecx
0x180027fa7  cmp     esi, ecx
0x180027fa9  jb      loc_180027EC6
0x180027faf  mov     edx, [rdi+8]
0x180027fb2  mov     rcx, r14; void *
0x180027fb5  mov     r8d, [rdi+0Ch]; Size
0x180027fb9  add     rdx, rdi; Src
0x180027fbc  call    memmove_0
0x180027fc1  mov     ecx, [rdi+0Ch]
0x180027fc4  shr     rcx, 1
0x180027fc7  xor     eax, eax
0x180027fc9  mov     [r14+rcx*2], ax
0x180027fce  jmp     loc_180027EC6
0x180027fd3  cmp     eax, 0C0000034h
0x180027fd8  jz      loc_180027EC6
0x180027fde  lea     r9, aFailedToOpenKe; "Failed to open key [%x]"
0x180027fe5  mov     r8d, 0FEh
0x180027feb  jmp     loc_180027F1A
0x180027ff0  mov     [rbp+57h+var_80], 0FFFFFFFFh
0x180027ff7  lea     r9, aDwordOverflowO; "DWORD overflow occured."
0x180027ffe  mov     r8d, 13Fh
0x180028004  mov     ecx, ebx
0x180028006  lea     rdx, aResolvecomserv; "ResolveCOMServerFromKeyPath"
0x18002800d  call    AslLogCallPrintf
0x180028012  jmp     loc_180027EC6
0x180028017  cmp     eax, 0C0000023h
0x18002801c  jz      short loc_18002805D
0x18002801e  lea     r9, aFailedToRetrie_2; "Failed to retrieve default key value [%"...
0x180028025  mov     r8d, 138h
0x18002802b  mov     ecx, ebx
0x18002802d  jmp     loc_180027F1F
0x180028032  test    esi, esi
0x180028034  jz      loc_180027E62
0x18002803a  lea     r9, aBadParameters; "Bad parameters"
0x180028041  mov     r8d, 104h
0x180028047  jmp     short loc_180028056
0x180028049  lea     r9, aMemoryAllocati_0; "Memory allocation failure"
0x180028050  mov     r8d, 10Dh
0x180028056  mov     ecx, 1
0x18002805b  jmp     short loc_180028006
0x18002805d  mov     rcx, gs:60h
0x180028066  mov     r8, rdi; P
0x180028069  xor     edx, edx; Flags
0x18002806b  mov     rcx, [rcx+30h]; HeapHandle
0x18002806f  call    cs:__imp_RtlFreeHeap
0x180028075  mov     rcx, gs:60h
0x18002807e  mov     edx, 8; Flags
0x180028083  mov     r8d, [rbp+57h+arg_8]; Size
0x180028087  mov     rcx, [rcx+30h]; HeapHandle
0x18002808b  call    cs:__imp_RtlAllocateHeap
0x180028091  mov     rdi, rax
0x180028094  test    rax, rax
0x180028097  jnz     short loc_1800280AB
0x180028099  lea     r9, aMemoryAllocati_0; "Memory allocation failure"
0x1800280a0  mov     r8d, 125h
0x1800280a6  jmp     loc_180028004
0x1800280ab  mov     eax, [rbp+57h+arg_8]
0x1800280ae  lea     rcx, [rbp+57h+arg_8]
0x1800280b2  mov     [rsp+0B0h+ResultLength], rcx; ResultLength
0x1800280b7  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800280bb  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800280bf  mov     r9, rdi; KeyValueInformation
0x1800280c2  mov     r8d, ebx; KeyValueInformationClass
0x1800280c5  mov     [rsp+0B0h+Length], eax; Length
0x1800280c9  call    cs:__imp_NtQueryValueKey
0x1800280cf  test    eax, eax
0x1800280d1  jns     loc_180027EB7
0x1800280d7  lea     r9, aFailedToRetrie_2; "Failed to retrieve default key value [%"...
0x1800280de  mov     r8d, 133h
0x1800280e4  jmp     loc_18002802B
```
