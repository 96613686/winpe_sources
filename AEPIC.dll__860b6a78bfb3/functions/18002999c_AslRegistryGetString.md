# AslRegistryGetString

- ea: `0x18002999c`
- end: `0x180029b5c`
- name: `AslRegistryGetString`
- size: `448`
- prototype: `__int64 __fastcall(_QWORD *, void *, const WCHAR *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180029b64`
- `0x18002e270`
- `0x180035868`

## callees

- `0x1800295dc`
- `0x18002979c`
- `0x18002999c`
- `0x18002ae1c`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x1800299f2`
- `ntdll!ZwQueryValueKey` at `0x180029ab1`
- `ntdll!ZwQueryValueKey` at `0x1800299f2`
- `ntdll!ZwQueryValueKey` at `0x180029ab1`
- `ntdll!RtlAllocateHeap` at `0x180029a5a`
- `ntdll!RtlAllocateHeap` at `0x180029a5a`
- `ntdll!RtlInitUnicodeString` at `0x1800299cb`
- `ntdll!RtlInitUnicodeString` at `0x1800299cb`

## string_xrefs

- `0x180029a24`: `AslRegistryGetString`
- `0x180029a75`: `AslRegistryGetString`
- `0x180029ae3`: `AslRegistryGetString`
- `0x180029b26`: `AslRegistryGetString`

## pseudocode

```c
__int64 __fastcall AslRegistryGetString(_QWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  _WORD *Heap; // rax
  _WORD *v8; // rdi
  int v9; // eax
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
    if ( (unsigned int)(*((_DWORD *)v8 + 1) - 1) <= 1 )
    {
      v8[((unsigned __int64)*((unsigned int *)v8 + 2) >> 1) + 6] = 0;
      v9 = AslStringDuplicate(a1, (__int64)(v8 + 6));
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
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
    return v6;
  }
  if ( v5 != -1073741772 )
    AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]", v5);
  return v6;
}

```

## disassembly

```asm
0x18002999c  push    rbx
0x18002999e  push    rsi
0x18002999f  push    rdi
0x1800299a0  push    r14
0x1800299a2  sub     rsp, 48h
0x1800299a6  mov     rsi, rdx
0x1800299a9  mov     qword ptr [rcx], 0
0x1800299b0  mov     r14, rcx
0x1800299b3  mov     [rsp+68h+arg_0], 0
0x1800299bb  xorps   xmm0, xmm0
0x1800299be  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800299c3  mov     rdx, r8; SourceString
0x1800299c6  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800299cb  call    cs:__imp_RtlInitUnicodeString
0x1800299d1  xor     r9d, r9d; KeyValueInformation
0x1800299d4  lea     rax, [rsp+68h+arg_0]
0x1800299d9  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1800299de  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1800299e3  mov     rcx, rsi; KeyHandle
0x1800299e6  mov     dword ptr [rsp+68h+Length], 0; Length
0x1800299ee  lea     r8d, [r9+2]; KeyValueInformationClass
0x1800299f2  call    cs:__imp_ZwQueryValueKey
0x1800299f8  mov     ebx, eax
0x1800299fa  cmp     eax, 80000005h
0x1800299ff  jz      short loc_180029A3A
0x180029a01  cmp     eax, 0C0000023h
0x180029a06  jz      short loc_180029A3A
0x180029a08  cmp     eax, 0C0000034h
0x180029a0d  jz      loc_180029B50
0x180029a13  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180029a1a  mov     dword ptr [rsp+68h+Length], eax
0x180029a1e  mov     r8d, 536h
0x180029a24  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180029a2b  mov     ecx, 1
0x180029a30  call    AslLogCallPrintf
0x180029a35  jmp     loc_180029B50
0x180029a3a  mov     eax, [rsp+68h+arg_0]
0x180029a3e  mov     edx, 8; Flags
0x180029a43  add     eax, 2
0x180029a46  mov     [rsp+68h+arg_0], eax
0x180029a4a  mov     rcx, gs:60h
0x180029a53  mov     r8d, eax; Size
0x180029a56  mov     rcx, [rcx+30h]; HeapHandle
0x180029a5a  call    cs:__imp_RtlAllocateHeap
0x180029a60  mov     rdi, rax
0x180029a63  test    rax, rax
0x180029a66  jnz     short loc_180029A8E
0x180029a68  lea     r9, aOutOfMemory_0; "Out of memory"
0x180029a6f  mov     r8d, 544h
0x180029a75  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180029a7c  mov     ebx, 0C0000017h
0x180029a81  lea     ecx, [rax+1]
0x180029a84  call    AslLogCallPrintf
0x180029a89  jmp     loc_180029B50
0x180029a8e  lea     rax, [rsp+68h+arg_0]
0x180029a93  mov     r9, rdi; KeyValueInformation
0x180029a96  mov     [rsp+68h+ResultLength], rax; ResultLength
0x180029a9b  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180029aa0  mov     eax, [rsp+68h+arg_0]
0x180029aa4  mov     r8d, 2; KeyValueInformationClass
0x180029aaa  mov     rcx, rsi; KeyHandle
0x180029aad  mov     dword ptr [rsp+68h+Length], eax; Length
0x180029ab1  call    cs:__imp_ZwQueryValueKey
0x180029ab7  mov     ebx, eax
0x180029ab9  test    eax, eax
0x180029abb  jns     short loc_180029ACC
0x180029abd  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180029ac4  mov     r8d, 550h
0x180029aca  jmp     short loc_180029B26
0x180029acc  mov     eax, [rdi+4]
0x180029acf  dec     eax
0x180029ad1  cmp     eax, 1
0x180029ad4  jbe     short loc_180029AFB
0x180029ad6  lea     r9, aInvalidValueTy; "Invalid value type"
0x180029add  mov     r8d, 558h
0x180029ae3  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180029aea  mov     ecx, 1
0x180029aef  call    AslLogCallPrintf
0x180029af4  mov     ebx, 0C0000024h
0x180029af9  jmp     short loc_180029B3B
0x180029afb  mov     ecx, [rdi+8]
0x180029afe  lea     rdx, [rdi+0Ch]
0x180029b02  shr     rcx, 1
0x180029b05  xor     eax, eax
0x180029b07  mov     [rdx+rcx*2], ax
0x180029b0b  mov     rcx, r14
0x180029b0e  call    AslStringDuplicate
0x180029b13  mov     ebx, eax
0x180029b15  test    eax, eax
0x180029b17  jns     short loc_180029B3B
0x180029b19  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x180029b20  mov     r8d, 562h
0x180029b26  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180029b2d  mov     dword ptr [rsp+68h+Length], eax
0x180029b31  mov     ecx, 1
0x180029b36  call    AslLogCallPrintf
0x180029b3b  mov     rcx, gs:60h
0x180029b44  mov     rdx, rdi
0x180029b47  mov     rcx, [rcx+30h]
0x180029b4b  call    AslFree
0x180029b50  mov     eax, ebx
0x180029b52  add     rsp, 48h
0x180029b56  pop     r14
0x180029b58  pop     rdi
0x180029b59  pop     rsi
0x180029b5a  pop     rbx
0x180029b5b  retn
```
