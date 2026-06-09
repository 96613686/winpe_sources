# AslRegistryGetString

- ea: `0x18004c4fc`
- end: `0x18004c6bf`
- name: `AslRegistryGetString`
- size: `451`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800463f0`
- `0x180049234`
- `0x18004c6c8`

## callees

- `0x18004c020`
- `0x18004c4fc`
- `0x18004ccd4`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x18004c552`
- `ntdll!ZwQueryValueKey` at `0x18004c611`
- `ntdll!ZwQueryValueKey` at `0x18004c552`
- `ntdll!ZwQueryValueKey` at `0x18004c611`
- `ntdll!RtlAllocateHeap` at `0x18004c5ba`
- `ntdll!RtlAllocateHeap` at `0x18004c5ba`
- `ntdll!RtlFreeHeap` at `0x18004c6ad`
- `ntdll!RtlFreeHeap` at `0x18004c6ad`
- `ntdll!RtlInitUnicodeString` at `0x18004c52b`
- `ntdll!RtlInitUnicodeString` at `0x18004c52b`

## string_xrefs

- `0x18004c584`: `AslRegistryGetString`
- `0x18004c5d5`: `AslRegistryGetString`
- `0x18004c643`: `AslRegistryGetString`
- `0x18004c686`: `AslRegistryGetString`

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
      v9 = AslStringDuplicate(a1, v8 + 3);
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
0x18004c4fc  push    rbx
0x18004c4fe  push    rsi
0x18004c4ff  push    rdi
0x18004c500  push    r14
0x18004c502  sub     rsp, 48h
0x18004c506  mov     rsi, rdx
0x18004c509  mov     qword ptr [rcx], 0
0x18004c510  mov     r14, rcx
0x18004c513  mov     [rsp+68h+arg_0], 0
0x18004c51b  xorps   xmm0, xmm0
0x18004c51e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18004c523  mov     rdx, r8; SourceString
0x18004c526  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18004c52b  call    cs:__imp_RtlInitUnicodeString
0x18004c531  xor     r9d, r9d; KeyValueInformation
0x18004c534  lea     rax, [rsp+68h+arg_0]
0x18004c539  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18004c53e  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x18004c543  mov     rcx, rsi; KeyHandle
0x18004c546  mov     dword ptr [rsp+68h+Length], 0; Length
0x18004c54e  lea     r8d, [r9+2]; KeyValueInformationClass
0x18004c552  call    cs:__imp_ZwQueryValueKey
0x18004c558  mov     ebx, eax
0x18004c55a  cmp     eax, 80000005h
0x18004c55f  jz      short loc_18004C59A
0x18004c561  cmp     eax, 0C0000023h
0x18004c566  jz      short loc_18004C59A
0x18004c568  cmp     eax, 0C0000034h
0x18004c56d  jz      loc_18004C6B3
0x18004c573  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18004c57a  mov     dword ptr [rsp+68h+Length], eax
0x18004c57e  mov     r8d, 536h
0x18004c584  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18004c58b  mov     ecx, 1
0x18004c590  call    AslLogCallPrintf
0x18004c595  jmp     loc_18004C6B3
0x18004c59a  mov     eax, [rsp+68h+arg_0]
0x18004c59e  mov     edx, 8; Flags
0x18004c5a3  add     eax, 2
0x18004c5a6  mov     [rsp+68h+arg_0], eax
0x18004c5aa  mov     rcx, gs:60h
0x18004c5b3  mov     r8d, eax; Size
0x18004c5b6  mov     rcx, [rcx+30h]; HeapHandle
0x18004c5ba  call    cs:__imp_RtlAllocateHeap
0x18004c5c0  mov     rdi, rax
0x18004c5c3  test    rax, rax
0x18004c5c6  jnz     short loc_18004C5EE
0x18004c5c8  lea     r9, aOutOfMemory_0; "Out of memory"
0x18004c5cf  mov     r8d, 544h
0x18004c5d5  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18004c5dc  mov     ebx, 0C0000017h
0x18004c5e1  lea     ecx, [rax+1]
0x18004c5e4  call    AslLogCallPrintf
0x18004c5e9  jmp     loc_18004C6B3
0x18004c5ee  lea     rax, [rsp+68h+arg_0]
0x18004c5f3  mov     r9, rdi; KeyValueInformation
0x18004c5f6  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18004c5fb  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x18004c600  mov     eax, [rsp+68h+arg_0]
0x18004c604  mov     r8d, 2; KeyValueInformationClass
0x18004c60a  mov     rcx, rsi; KeyHandle
0x18004c60d  mov     dword ptr [rsp+68h+Length], eax; Length
0x18004c611  call    cs:__imp_ZwQueryValueKey
0x18004c617  mov     ebx, eax
0x18004c619  test    eax, eax
0x18004c61b  jns     short loc_18004C62C
0x18004c61d  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18004c624  mov     r8d, 550h
0x18004c62a  jmp     short loc_18004C686
0x18004c62c  mov     eax, [rdi+4]
0x18004c62f  dec     eax
0x18004c631  cmp     eax, 1
0x18004c634  jbe     short loc_18004C65B
0x18004c636  lea     r9, aInvalidValueTy; "Invalid value type"
0x18004c63d  mov     r8d, 558h
0x18004c643  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18004c64a  mov     ecx, 1
0x18004c64f  call    AslLogCallPrintf
0x18004c654  mov     ebx, 0C0000024h
0x18004c659  jmp     short loc_18004C69B
0x18004c65b  mov     ecx, [rdi+8]
0x18004c65e  lea     rdx, [rdi+0Ch]
0x18004c662  shr     rcx, 1
0x18004c665  xor     eax, eax
0x18004c667  mov     [rdx+rcx*2], ax
0x18004c66b  mov     rcx, r14
0x18004c66e  call    AslStringDuplicate
0x18004c673  mov     ebx, eax
0x18004c675  test    eax, eax
0x18004c677  jns     short loc_18004C69B
0x18004c679  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x18004c680  mov     r8d, 562h
0x18004c686  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18004c68d  mov     dword ptr [rsp+68h+Length], eax
0x18004c691  mov     ecx, 1
0x18004c696  call    AslLogCallPrintf
0x18004c69b  mov     rcx, gs:60h
0x18004c6a4  mov     r8, rdi; P
0x18004c6a7  xor     edx, edx; Flags
0x18004c6a9  mov     rcx, [rcx+30h]; HeapHandle
0x18004c6ad  call    cs:__imp_RtlFreeHeap
0x18004c6b3  mov     eax, ebx
0x18004c6b5  add     rsp, 48h
0x18004c6b9  pop     r14
0x18004c6bb  pop     rdi
0x18004c6bc  pop     rsi
0x18004c6bd  pop     rbx
0x18004c6be  retn
```
