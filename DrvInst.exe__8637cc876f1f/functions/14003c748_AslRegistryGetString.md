# AslRegistryGetString

- ea: `0x14003c748`
- end: `0x14003c908`
- name: `AslRegistryGetString`
- size: `448`
- prototype: `__int64 __fastcall(_QWORD *, void *, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1400385dc`

## callees

- `0x14003bf18`
- `0x14003c368`
- `0x14003c748`
- `0x140041140`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14003c777`
- `ntdll!RtlInitUnicodeString` at `0x14003c777`
- `ntdll!ZwQueryValueKey` at `0x14003c79e`
- `ntdll!ZwQueryValueKey` at `0x14003c85d`
- `ntdll!ZwQueryValueKey` at `0x14003c79e`
- `ntdll!ZwQueryValueKey` at `0x14003c85d`
- `ntdll!RtlAllocateHeap` at `0x14003c806`
- `ntdll!RtlAllocateHeap` at `0x14003c806`

## string_xrefs

- `0x14003c7d0`: `AslRegistryGetString`
- `0x14003c821`: `AslRegistryGetString`
- `0x14003c88f`: `AslRegistryGetString`
- `0x14003c8d2`: `AslRegistryGetString`

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
0x14003c748  push    rbx
0x14003c74a  push    rsi
0x14003c74b  push    rdi
0x14003c74c  push    r14
0x14003c74e  sub     rsp, 48h
0x14003c752  mov     rsi, rdx
0x14003c755  mov     qword ptr [rcx], 0
0x14003c75c  mov     r14, rcx
0x14003c75f  mov     [rsp+68h+arg_0], 0
0x14003c767  xorps   xmm0, xmm0
0x14003c76a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14003c76f  mov     rdx, r8; SourceString
0x14003c772  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14003c777  call    cs:__imp_RtlInitUnicodeString
0x14003c77d  xor     r9d, r9d; KeyValueInformation
0x14003c780  lea     rax, [rsp+68h+arg_0]
0x14003c785  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14003c78a  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14003c78f  mov     rcx, rsi; KeyHandle
0x14003c792  mov     dword ptr [rsp+68h+Length], 0; Length
0x14003c79a  lea     r8d, [r9+2]; KeyValueInformationClass
0x14003c79e  call    cs:__imp_ZwQueryValueKey
0x14003c7a4  mov     ebx, eax
0x14003c7a6  cmp     eax, 80000005h
0x14003c7ab  jz      short loc_14003C7E6
0x14003c7ad  cmp     eax, 0C0000023h
0x14003c7b2  jz      short loc_14003C7E6
0x14003c7b4  cmp     eax, 0C0000034h
0x14003c7b9  jz      loc_14003C8FC
0x14003c7bf  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x14003c7c6  mov     dword ptr [rsp+68h+Length], eax
0x14003c7ca  mov     r8d, 536h
0x14003c7d0  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x14003c7d7  mov     ecx, 1
0x14003c7dc  call    AslLogCallPrintf
0x14003c7e1  jmp     loc_14003C8FC
0x14003c7e6  mov     eax, [rsp+68h+arg_0]
0x14003c7ea  mov     edx, 8; Flags
0x14003c7ef  add     eax, 2
0x14003c7f2  mov     [rsp+68h+arg_0], eax
0x14003c7f6  mov     rcx, gs:60h
0x14003c7ff  mov     r8d, eax; Size
0x14003c802  mov     rcx, [rcx+30h]; HeapHandle
0x14003c806  call    cs:__imp_RtlAllocateHeap
0x14003c80c  mov     rdi, rax
0x14003c80f  test    rax, rax
0x14003c812  jnz     short loc_14003C83A
0x14003c814  lea     r9, aOutOfMemory; "Out of memory"
0x14003c81b  mov     r8d, 544h
0x14003c821  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x14003c828  mov     ebx, 0C0000017h
0x14003c82d  lea     ecx, [rax+1]
0x14003c830  call    AslLogCallPrintf
0x14003c835  jmp     loc_14003C8FC
0x14003c83a  lea     rax, [rsp+68h+arg_0]
0x14003c83f  mov     r9, rdi; KeyValueInformation
0x14003c842  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14003c847  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14003c84c  mov     eax, [rsp+68h+arg_0]
0x14003c850  mov     r8d, 2; KeyValueInformationClass
0x14003c856  mov     rcx, rsi; KeyHandle
0x14003c859  mov     dword ptr [rsp+68h+Length], eax; Length
0x14003c85d  call    cs:__imp_ZwQueryValueKey
0x14003c863  mov     ebx, eax
0x14003c865  test    eax, eax
0x14003c867  jns     short loc_14003C878
0x14003c869  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x14003c870  mov     r8d, 550h
0x14003c876  jmp     short loc_14003C8D2
0x14003c878  mov     eax, [rdi+4]
0x14003c87b  dec     eax
0x14003c87d  cmp     eax, 1
0x14003c880  jbe     short loc_14003C8A7
0x14003c882  lea     r9, aInvalidValueTy; "Invalid value type"
0x14003c889  mov     r8d, 558h
0x14003c88f  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x14003c896  mov     ecx, 1
0x14003c89b  call    AslLogCallPrintf
0x14003c8a0  mov     ebx, 0C0000024h
0x14003c8a5  jmp     short loc_14003C8E7
0x14003c8a7  mov     ecx, [rdi+8]
0x14003c8aa  lea     rdx, [rdi+0Ch]
0x14003c8ae  shr     rcx, 1
0x14003c8b1  xor     eax, eax
0x14003c8b3  mov     [rdx+rcx*2], ax
0x14003c8b7  mov     rcx, r14
0x14003c8ba  call    AslStringDuplicate
0x14003c8bf  mov     ebx, eax
0x14003c8c1  test    eax, eax
0x14003c8c3  jns     short loc_14003C8E7
0x14003c8c5  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x14003c8cc  mov     r8d, 562h
0x14003c8d2  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x14003c8d9  mov     dword ptr [rsp+68h+Length], eax
0x14003c8dd  mov     ecx, 1
0x14003c8e2  call    AslLogCallPrintf
0x14003c8e7  mov     rcx, gs:60h
0x14003c8f0  mov     rdx, rdi
0x14003c8f3  mov     rcx, [rcx+30h]
0x14003c8f7  call    AslFree
0x14003c8fc  mov     eax, ebx
0x14003c8fe  add     rsp, 48h
0x14003c902  pop     r14
0x14003c904  pop     rdi
0x14003c905  pop     rsi
0x14003c906  pop     rbx
0x14003c907  retn
```
