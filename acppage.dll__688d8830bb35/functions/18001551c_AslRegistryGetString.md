# AslRegistryGetString

- ea: `0x18001551c`
- end: `0x1800156df`
- name: `AslRegistryGetString`
- size: `451`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180012d8c`
- `0x1800137e0`
- `0x1800156e8`

## callees

- `0x180015220`
- `0x18001551c`
- `0x180015a4c`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x180015572`
- `ntdll!ZwQueryValueKey` at `0x180015631`
- `ntdll!ZwQueryValueKey` at `0x180015572`
- `ntdll!ZwQueryValueKey` at `0x180015631`
- `ntdll!RtlFreeHeap` at `0x1800156cd`
- `ntdll!RtlFreeHeap` at `0x1800156cd`
- `ntdll!RtlAllocateHeap` at `0x1800155da`
- `ntdll!RtlAllocateHeap` at `0x1800155da`
- `ntdll!RtlInitUnicodeString` at `0x18001554b`
- `ntdll!RtlInitUnicodeString` at `0x18001554b`

## string_xrefs

- `0x1800155a4`: `AslRegistryGetString`
- `0x1800155f5`: `AslRegistryGetString`
- `0x180015663`: `AslRegistryGetString`
- `0x1800156a6`: `AslRegistryGetString`

## pseudocode

```c
__int64 __fastcall AslRegistryGetString(_QWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS v5; // eax
  NTSTATUS v6; // ebx
  _DWORD *Heap; // rax
  _DWORD *v8; // rdi
  const char *v9; // r9
  __int64 v10; // r8
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
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
      return (unsigned int)v6;
    }
    v6 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, Heap, ResultLength, &ResultLength);
    if ( v6 < 0 )
    {
      v9 = "Failed to query key value [%x]";
      v10 = 1360;
LABEL_13:
      AslLogCallPrintf(1, "AslRegistryGetString", v10, v9);
      goto LABEL_14;
    }
    if ( (unsigned int)(v8[1] - 1) <= 1 )
    {
      *((_WORD *)v8 + ((unsigned __int64)(unsigned int)v8[2] >> 1) + 6) = 0;
      v6 = AslStringDuplicate(a1);
      if ( v6 < 0 )
      {
        v9 = "Out of memory [%x]";
        v10 = 1378;
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
    return (unsigned int)v6;
  }
  if ( v5 != -1073741772 )
    AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001551c  push    rbx
0x18001551e  push    rsi
0x18001551f  push    rdi
0x180015520  push    r14
0x180015522  sub     rsp, 48h
0x180015526  mov     rsi, rdx
0x180015529  mov     qword ptr [rcx], 0
0x180015530  mov     r14, rcx
0x180015533  mov     [rsp+68h+arg_0], 0
0x18001553b  xorps   xmm0, xmm0
0x18001553e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180015543  mov     rdx, r8; SourceString
0x180015546  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18001554b  call    cs:__imp_RtlInitUnicodeString
0x180015551  xor     r9d, r9d; KeyValueInformation
0x180015554  lea     rax, [rsp+68h+arg_0]
0x180015559  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18001555e  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180015563  mov     rcx, rsi; KeyHandle
0x180015566  mov     [rsp+68h+Length], 0; Length
0x18001556e  lea     r8d, [r9+2]; KeyValueInformationClass
0x180015572  call    cs:__imp_ZwQueryValueKey
0x180015578  mov     ebx, eax
0x18001557a  cmp     eax, 80000005h
0x18001557f  jz      short loc_1800155BA
0x180015581  cmp     eax, 0C0000023h
0x180015586  jz      short loc_1800155BA
0x180015588  cmp     eax, 0C0000034h
0x18001558d  jz      loc_1800156D3
0x180015593  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18001559a  mov     [rsp+68h+Length], eax
0x18001559e  mov     r8d, 536h
0x1800155a4  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x1800155ab  mov     ecx, 1
0x1800155b0  call    AslLogCallPrintf
0x1800155b5  jmp     loc_1800156D3
0x1800155ba  mov     eax, [rsp+68h+arg_0]
0x1800155be  mov     edx, 8; Flags
0x1800155c3  add     eax, 2
0x1800155c6  mov     [rsp+68h+arg_0], eax
0x1800155ca  mov     rcx, gs:60h
0x1800155d3  mov     r8d, eax; Size
0x1800155d6  mov     rcx, [rcx+30h]; HeapHandle
0x1800155da  call    cs:__imp_RtlAllocateHeap
0x1800155e0  mov     rdi, rax
0x1800155e3  test    rax, rax
0x1800155e6  jnz     short loc_18001560E
0x1800155e8  lea     r9, aOutOfMemory; "Out of memory"
0x1800155ef  mov     r8d, 544h
0x1800155f5  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x1800155fc  mov     ebx, 0C0000017h
0x180015601  lea     ecx, [rax+1]
0x180015604  call    AslLogCallPrintf
0x180015609  jmp     loc_1800156D3
0x18001560e  lea     rax, [rsp+68h+arg_0]
0x180015613  mov     r9, rdi; KeyValueInformation
0x180015616  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18001561b  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180015620  mov     eax, [rsp+68h+arg_0]
0x180015624  mov     r8d, 2; KeyValueInformationClass
0x18001562a  mov     rcx, rsi; KeyHandle
0x18001562d  mov     [rsp+68h+Length], eax; Length
0x180015631  call    cs:__imp_ZwQueryValueKey
0x180015637  mov     ebx, eax
0x180015639  test    eax, eax
0x18001563b  jns     short loc_18001564C
0x18001563d  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180015644  mov     r8d, 550h
0x18001564a  jmp     short loc_1800156A6
0x18001564c  mov     eax, [rdi+4]
0x18001564f  dec     eax
0x180015651  cmp     eax, 1
0x180015654  jbe     short loc_18001567B
0x180015656  lea     r9, aInvalidValueTy; "Invalid value type"
0x18001565d  mov     r8d, 558h
0x180015663  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x18001566a  mov     ecx, 1
0x18001566f  call    AslLogCallPrintf
0x180015674  mov     ebx, 0C0000024h
0x180015679  jmp     short loc_1800156BB
0x18001567b  mov     ecx, [rdi+8]
0x18001567e  lea     rdx, [rdi+0Ch]
0x180015682  shr     rcx, 1
0x180015685  xor     eax, eax
0x180015687  mov     [rdx+rcx*2], ax
0x18001568b  mov     rcx, r14
0x18001568e  call    AslStringDuplicate
0x180015693  mov     ebx, eax
0x180015695  test    eax, eax
0x180015697  jns     short loc_1800156BB
0x180015699  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x1800156a0  mov     r8d, 562h
0x1800156a6  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x1800156ad  mov     [rsp+68h+Length], eax
0x1800156b1  mov     ecx, 1
0x1800156b6  call    AslLogCallPrintf
0x1800156bb  mov     rcx, gs:60h
0x1800156c4  mov     r8, rdi; P
0x1800156c7  xor     edx, edx; Flags
0x1800156c9  mov     rcx, [rcx+30h]; HeapHandle
0x1800156cd  call    cs:__imp_RtlFreeHeap
0x1800156d3  mov     eax, ebx
0x1800156d5  add     rsp, 48h
0x1800156d9  pop     r14
0x1800156db  pop     rdi
0x1800156dc  pop     rsi
0x1800156dd  pop     rbx
0x1800156de  retn
```
