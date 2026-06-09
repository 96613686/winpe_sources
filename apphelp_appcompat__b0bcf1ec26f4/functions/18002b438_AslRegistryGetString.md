# AslRegistryGetString

- ea: `0x18002b438`
- end: `0x18002b60b`
- name: `AslRegistryGetString`
- size: `467`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180003c7c`
- `0x180030054`
- `0x180030810`
- `0x18003d3ac`

## callees

- `0x18000f114`
- `0x18001577c`
- `0x18002b438`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002b467`
- `ntdll!RtlInitUnicodeString` at `0x18002b467`
- `ntdll!ZwQueryValueKey` at `0x18002b48e`
- `ntdll!ZwQueryValueKey` at `0x18002b501`
- `ntdll!ZwQueryValueKey` at `0x18002b48e`
- `ntdll!ZwQueryValueKey` at `0x18002b501`
- `ntdll!RtlFreeHeap` at `0x18002b541`
- `ntdll!RtlFreeHeap` at `0x18002b541`
- `ntdll!RtlAllocateHeap` at `0x18002b4cc`
- `ntdll!RtlAllocateHeap` at `0x18002b4cc`

## string_xrefs

- `0x18002b51a`: `AslRegistryGetString`
- `0x18002b55a`: `AslRegistryGetString`
- `0x18002b5cb`: `AslRegistryGetString`
- `0x18002b5f0`: `AslRegistryGetString`

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
  if ( v5 != -1073741772 )
  {
    if ( v5 != -2147483643 && v5 != -1073741789 )
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]", v5);
      return v6;
    }
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
    if ( v9 >= 0 )
    {
      if ( (unsigned int)(v8[1] - 1) > 1 )
      {
        AslLogCallPrintf(1, "AslRegistryGetString", 1368, "Invalid value type");
        v6 = -1073741788;
        goto LABEL_7;
      }
      *((_WORD *)v8 + ((unsigned __int64)(unsigned int)v8[2] >> 1) + 6) = 0;
      v9 = AslStringDuplicate(a1, v8 + 3);
      v6 = v9;
      if ( v9 >= 0 )
      {
LABEL_7:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        return v6;
      }
      v10 = "Out of memory [%x]";
      v11 = 1378;
    }
    else
    {
      v10 = "Failed to query key value [%x]";
      v11 = 1360;
    }
    LODWORD(Length) = v9;
    AslLogCallPrintf(1, "AslRegistryGetString", v11, v10, Length);
    goto LABEL_7;
  }
  return v6;
}

```

## disassembly

```asm
0x18002b438  push    rbx
0x18002b43a  push    rsi
0x18002b43b  push    rdi
0x18002b43c  push    r14
0x18002b43e  sub     rsp, 48h
0x18002b442  mov     rsi, rdx
0x18002b445  mov     qword ptr [rcx], 0
0x18002b44c  mov     r14, rcx
0x18002b44f  mov     [rsp+68h+arg_0], 0
0x18002b457  xorps   xmm0, xmm0
0x18002b45a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18002b45f  mov     rdx, r8; SourceString
0x18002b462  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18002b467  call    cs:__imp_RtlInitUnicodeString
0x18002b46d  xor     r9d, r9d; KeyValueInformation
0x18002b470  lea     rax, [rsp+68h+arg_0]
0x18002b475  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18002b47a  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x18002b47f  mov     rcx, rsi; KeyHandle
0x18002b482  mov     dword ptr [rsp+68h+Length], 0; Length
0x18002b48a  lea     r8d, [r9+2]; KeyValueInformationClass
0x18002b48e  call    cs:__imp_ZwQueryValueKey
0x18002b494  mov     ebx, eax
0x18002b496  cmp     eax, 0C0000034h
0x18002b49b  jz      loc_18002B56B
0x18002b4a1  cmp     eax, 80000005h
0x18002b4a6  jnz     loc_18002B5B1
0x18002b4ac  mov     eax, [rsp+68h+arg_0]
0x18002b4b0  mov     edx, 8; Flags
0x18002b4b5  add     eax, 2
0x18002b4b8  mov     [rsp+68h+arg_0], eax
0x18002b4bc  mov     rcx, gs:60h
0x18002b4c5  mov     r8d, eax; Size
0x18002b4c8  mov     rcx, [rcx+30h]; HeapHandle
0x18002b4cc  call    cs:__imp_RtlAllocateHeap
0x18002b4d2  mov     rdi, rax
0x18002b4d5  test    rax, rax
0x18002b4d8  jz      loc_18002B5BE
0x18002b4de  lea     rax, [rsp+68h+arg_0]
0x18002b4e3  mov     r9, rdi; KeyValueInformation
0x18002b4e6  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18002b4eb  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x18002b4f0  mov     eax, [rsp+68h+arg_0]
0x18002b4f4  mov     r8d, 2; KeyValueInformationClass
0x18002b4fa  mov     rcx, rsi; KeyHandle
0x18002b4fd  mov     dword ptr [rsp+68h+Length], eax; Length
0x18002b501  call    cs:__imp_ZwQueryValueKey
0x18002b507  mov     ebx, eax
0x18002b509  test    eax, eax
0x18002b50b  jns     short loc_18002B577
0x18002b50d  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x18002b514  mov     r8d, 550h
0x18002b51a  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18002b521  mov     dword ptr [rsp+68h+Length], eax
0x18002b525  mov     ecx, 1
0x18002b52a  call    AslLogCallPrintf
0x18002b52f  mov     rcx, gs:60h
0x18002b538  mov     r8, rdi; P
0x18002b53b  xor     edx, edx; Flags
0x18002b53d  mov     rcx, [rcx+30h]; HeapHandle
0x18002b541  call    cs:__imp_RtlFreeHeap
0x18002b547  jmp     short loc_18002B56B
0x18002b549  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x18002b550  mov     dword ptr [rsp+68h+Length], eax
0x18002b554  mov     r8d, 536h
0x18002b55a  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18002b561  mov     ecx, 1
0x18002b566  call    AslLogCallPrintf
0x18002b56b  mov     eax, ebx
0x18002b56d  add     rsp, 48h
0x18002b571  pop     r14
0x18002b573  pop     rdi
0x18002b574  pop     rsi
0x18002b575  pop     rbx
0x18002b576  retn
0x18002b577  mov     eax, [rdi+4]
0x18002b57a  dec     eax
0x18002b57c  cmp     eax, 1
0x18002b57f  ja      short loc_18002B5E3
0x18002b581  mov     ecx, [rdi+8]
0x18002b584  lea     rdx, [rdi+0Ch]
0x18002b588  shr     rcx, 1
0x18002b58b  xor     eax, eax
0x18002b58d  mov     [rdx+rcx*2], ax
0x18002b591  mov     rcx, r14
0x18002b594  call    AslStringDuplicate
0x18002b599  mov     ebx, eax
0x18002b59b  test    eax, eax
0x18002b59d  jns     short loc_18002B52F
0x18002b59f  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x18002b5a6  mov     r8d, 562h
0x18002b5ac  jmp     loc_18002B51A
0x18002b5b1  cmp     eax, 0C0000023h
0x18002b5b6  jz      loc_18002B4AC
0x18002b5bc  jmp     short loc_18002B549
0x18002b5be  lea     r9, aOutOfMemory; "Out of memory"
0x18002b5c5  mov     r8d, 544h
0x18002b5cb  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18002b5d2  mov     ecx, 1
0x18002b5d7  mov     ebx, 0C0000017h
0x18002b5dc  call    AslLogCallPrintf
0x18002b5e1  jmp     short loc_18002B56B
0x18002b5e3  lea     r9, aInvalidValueTy; "Invalid value type"
0x18002b5ea  mov     r8d, 558h
0x18002b5f0  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18002b5f7  mov     ecx, 1
0x18002b5fc  call    AslLogCallPrintf
0x18002b601  mov     ebx, 0C0000024h
0x18002b606  jmp     loc_18002B52F
```
