# AslRegistryGetString

- ea: `0x180030fb4`
- end: `0x180031177`
- name: `AslRegistryGetString`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e694`
- `0x18002f0f4`
- `0x180031180`

## callees

- `0x180030fb4`
- `0x1800314e4`
- `0x180031a3c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180031072`
- `ntdll!RtlAllocateHeap` at `0x180031072`
- `ntdll!RtlFreeHeap` at `0x180031165`
- `ntdll!RtlFreeHeap` at `0x180031165`
- `ntdll!RtlInitUnicodeString` at `0x180030fe3`
- `ntdll!RtlInitUnicodeString` at `0x180030fe3`
- `ntdll!ZwQueryValueKey` at `0x18003100a`
- `ntdll!ZwQueryValueKey` at `0x1800310c9`
- `ntdll!ZwQueryValueKey` at `0x18003100a`
- `ntdll!ZwQueryValueKey` at `0x1800310c9`

## string_xrefs

- `0x18003103c`: `AslRegistryGetString`
- `0x18003108d`: `AslRegistryGetString`
- `0x1800310fb`: `AslRegistryGetString`
- `0x18003113e`: `AslRegistryGetString`

## pseudocode

```c
__int64 __fastcall AslRegistryGetString(_QWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  _DWORD *Heap; // rax
  _DWORD *v8; // rdi
  NTSTATUS v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  __int64 Length; // [rsp+20h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  *a1 = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  v5 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v6 = v5;
  if ( v5 == -2147483643 || v5 == -1073741789 )
  {
    ResultLength += 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
    v8 = Heap;
    if ( !Heap )
    {
      v6 = -1073741801;
      AslLogCallPrintf(1, "AslRegistryGetString", 1348, "Out of memory");
      return v6;
    }
    v9 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, Heap, ResultLength, &ResultLength);
    v6 = v9;
    if ( v9 < 0 )
    {
      v10 = "Failed to query key value [%x]";
      v11 = 1360;
LABEL_13:
      LODWORD(Length) = v9;
      AslLogCallPrintf(1, "AslRegistryGetString", v11, v10, Length);
      goto LABEL_14;
    }
    if ( (unsigned int)(v8[1] - 1) <= 1 )
    {
      *((_WORD *)v8 + ((unsigned __int64)(unsigned int)v8[2] >> 1) + 6) = 0;
      v9 = AslStringDuplicate(a1);
      v6 = v9;
      if ( v9 < 0 )
      {
        v10 = "Out of memory [%x]";
        v11 = 1378;
        goto LABEL_13;
      }
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1368, "Invalid value type");
      v6 = -1073741788;
    }
LABEL_14:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    return v6;
  }
  if ( v5 != -1073741772 )
    AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]", v5);
  return v6;
}

```

## disassembly

```asm
0x180030fb4  push    rbx
0x180030fb6  push    rsi
0x180030fb7  push    rdi
0x180030fb8  push    r14
0x180030fba  sub     rsp, 48h
0x180030fbe  mov     rsi, rdx
0x180030fc1  mov     qword ptr [rcx], 0
0x180030fc8  mov     r14, rcx
0x180030fcb  mov     [rsp+68h+arg_0], 0
0x180030fd3  xorps   xmm0, xmm0
0x180030fd6  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180030fdb  mov     rdx, r8; SourceString
0x180030fde  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180030fe3  call    cs:__imp_RtlInitUnicodeString
0x180030fe9  xor     r9d, r9d; KeyValueInformation
0x180030fec  lea     rax, [rsp+68h+arg_0]
0x180030ff1  mov     [rsp+68h+ResultLength], rax; ResultLength
0x180030ff6  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180030ffb  mov     rcx, rsi; KeyHandle
0x180030ffe  mov     dword ptr [rsp+68h+Length], 0; Length
0x180031006  lea     r8d, [r9+2]; KeyValueInformationClass
0x18003100a  call    cs:__imp_ZwQueryValueKey
0x180031010  mov     ebx, eax
0x180031012  cmp     eax, 80000005h
0x180031017  jz      short loc_180031052
0x180031019  cmp     eax, 0C0000023h
0x18003101e  jz      short loc_180031052
0x180031020  cmp     eax, 0C0000034h
0x180031025  jz      loc_18003116B
0x18003102b  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180031032  mov     dword ptr [rsp+68h+Length], eax
0x180031036  mov     r8d, 536h
0x18003103c  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x180031043  mov     ecx, 1
0x180031048  call    AslLogCallPrintf
0x18003104d  jmp     loc_18003116B
0x180031052  mov     eax, [rsp+68h+arg_0]
0x180031056  mov     edx, 8; Flags
0x18003105b  add     eax, 2
0x18003105e  mov     [rsp+68h+arg_0], eax
0x180031062  mov     rcx, gs:60h
0x18003106b  mov     r8d, eax; Size
0x18003106e  mov     rcx, [rcx+30h]; HeapHandle
0x180031072  call    cs:__imp_RtlAllocateHeap
0x180031078  mov     rdi, rax
0x18003107b  test    rax, rax
0x18003107e  jnz     short loc_1800310A6
0x180031080  lea     r9, aOutOfMemory; "Out of memory"
0x180031087  mov     r8d, 544h
0x18003108d  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x180031094  mov     ebx, 0C0000017h
0x180031099  lea     ecx, [rax+1]
0x18003109c  call    AslLogCallPrintf
0x1800310a1  jmp     loc_18003116B
0x1800310a6  lea     rax, [rsp+68h+arg_0]
0x1800310ab  mov     r9, rdi; KeyValueInformation
0x1800310ae  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1800310b3  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1800310b8  mov     eax, [rsp+68h+arg_0]
0x1800310bc  mov     r8d, 2; KeyValueInformationClass
0x1800310c2  mov     rcx, rsi; KeyHandle
0x1800310c5  mov     dword ptr [rsp+68h+Length], eax; Length
0x1800310c9  call    cs:__imp_ZwQueryValueKey
0x1800310cf  mov     ebx, eax
0x1800310d1  test    eax, eax
0x1800310d3  jns     short loc_1800310E4
0x1800310d5  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x1800310dc  mov     r8d, 550h
0x1800310e2  jmp     short loc_18003113E
0x1800310e4  mov     eax, [rdi+4]
0x1800310e7  dec     eax
0x1800310e9  cmp     eax, 1
0x1800310ec  jbe     short loc_180031113
0x1800310ee  lea     r9, aInvalidValueTy; "Invalid value type"
0x1800310f5  mov     r8d, 558h
0x1800310fb  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x180031102  mov     ecx, 1
0x180031107  call    AslLogCallPrintf
0x18003110c  mov     ebx, 0C0000024h
0x180031111  jmp     short loc_180031153
0x180031113  mov     ecx, [rdi+8]
0x180031116  lea     rdx, [rdi+0Ch]
0x18003111a  shr     rcx, 1
0x18003111d  xor     eax, eax
0x18003111f  mov     [rdx+rcx*2], ax
0x180031123  mov     rcx, r14
0x180031126  call    AslStringDuplicate
0x18003112b  mov     ebx, eax
0x18003112d  test    eax, eax
0x18003112f  jns     short loc_180031153
0x180031131  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x180031138  mov     r8d, 562h
0x18003113e  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x180031145  mov     dword ptr [rsp+68h+Length], eax
0x180031149  mov     ecx, 1
0x18003114e  call    AslLogCallPrintf
0x180031153  mov     rcx, gs:60h
0x18003115c  mov     r8, rdi; P
0x18003115f  xor     edx, edx; Flags
0x180031161  mov     rcx, [rcx+30h]; HeapHandle
0x180031165  call    cs:__imp_RtlFreeHeap
0x18003116b  mov     eax, ebx
0x18003116d  add     rsp, 48h
0x180031171  pop     r14
0x180031173  pop     rdi
0x180031174  pop     rsi
0x180031175  pop     rbx
0x180031176  retn
```
