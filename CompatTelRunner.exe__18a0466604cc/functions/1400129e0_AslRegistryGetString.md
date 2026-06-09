# AslRegistryGetString

- ea: `0x1400129e0`
- end: `0x140012ba3`
- name: `AslRegistryGetString`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD *, void *, const WCHAR *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140012bac`
- `0x14001582c`
- `0x140016744`

## callees

- `0x1400129e0`
- `0x1400151b0`
- `0x140016288`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x140012a36`
- `ntdll!ZwQueryValueKey` at `0x140012af5`
- `ntdll!ZwQueryValueKey` at `0x140012a36`
- `ntdll!ZwQueryValueKey` at `0x140012af5`
- `ntdll!RtlFreeHeap` at `0x140012b91`
- `ntdll!RtlFreeHeap` at `0x140012b91`
- `ntdll!RtlAllocateHeap` at `0x140012a9e`
- `ntdll!RtlAllocateHeap` at `0x140012a9e`
- `ntdll!RtlInitUnicodeString` at `0x140012a0f`
- `ntdll!RtlInitUnicodeString` at `0x140012a0f`

## string_xrefs

- `0x140012a68`: `AslRegistryGetString`
- `0x140012ab9`: `AslRegistryGetString`
- `0x140012b27`: `AslRegistryGetString`
- `0x140012b6a`: `AslRegistryGetString`

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
0x1400129e0  push    rbx
0x1400129e2  push    rsi
0x1400129e3  push    rdi
0x1400129e4  push    r14
0x1400129e6  sub     rsp, 48h
0x1400129ea  mov     rsi, rdx
0x1400129ed  mov     qword ptr [rcx], 0
0x1400129f4  mov     r14, rcx
0x1400129f7  mov     [rsp+68h+arg_0], 0
0x1400129ff  xorps   xmm0, xmm0
0x140012a02  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140012a07  mov     rdx, r8; SourceString
0x140012a0a  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140012a0f  call    cs:__imp_RtlInitUnicodeString
0x140012a15  xor     r9d, r9d; KeyValueInformation
0x140012a18  lea     rax, [rsp+68h+arg_0]
0x140012a1d  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140012a22  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x140012a27  mov     rcx, rsi; KeyHandle
0x140012a2a  mov     dword ptr [rsp+68h+Length], 0; Length
0x140012a32  lea     r8d, [r9+2]; KeyValueInformationClass
0x140012a36  call    cs:__imp_ZwQueryValueKey
0x140012a3c  mov     ebx, eax
0x140012a3e  cmp     eax, 80000005h
0x140012a43  jz      short loc_140012A7E
0x140012a45  cmp     eax, 0C0000023h
0x140012a4a  jz      short loc_140012A7E
0x140012a4c  cmp     eax, 0C0000034h
0x140012a51  jz      loc_140012B97
0x140012a57  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x140012a5e  mov     dword ptr [rsp+68h+Length], eax
0x140012a62  mov     r8d, 536h
0x140012a68  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140012a6f  mov     ecx, 1
0x140012a74  call    AslLogCallPrintf
0x140012a79  jmp     loc_140012B97
0x140012a7e  mov     eax, [rsp+68h+arg_0]
0x140012a82  mov     edx, 8; Flags
0x140012a87  add     eax, 2
0x140012a8a  mov     [rsp+68h+arg_0], eax
0x140012a8e  mov     rcx, gs:60h
0x140012a97  mov     r8d, eax; Size
0x140012a9a  mov     rcx, [rcx+30h]; HeapHandle
0x140012a9e  call    cs:__imp_RtlAllocateHeap
0x140012aa4  mov     rdi, rax
0x140012aa7  test    rax, rax
0x140012aaa  jnz     short loc_140012AD2
0x140012aac  lea     r9, aOutOfMemory_0; "Out of memory"
0x140012ab3  mov     r8d, 544h
0x140012ab9  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140012ac0  mov     ebx, 0C0000017h
0x140012ac5  lea     ecx, [rax+1]
0x140012ac8  call    AslLogCallPrintf
0x140012acd  jmp     loc_140012B97
0x140012ad2  lea     rax, [rsp+68h+arg_0]
0x140012ad7  mov     r9, rdi; KeyValueInformation
0x140012ada  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140012adf  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x140012ae4  mov     eax, [rsp+68h+arg_0]
0x140012ae8  mov     r8d, 2; KeyValueInformationClass
0x140012aee  mov     rcx, rsi; KeyHandle
0x140012af1  mov     dword ptr [rsp+68h+Length], eax; Length
0x140012af5  call    cs:__imp_ZwQueryValueKey
0x140012afb  mov     ebx, eax
0x140012afd  test    eax, eax
0x140012aff  jns     short loc_140012B10
0x140012b01  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x140012b08  mov     r8d, 550h
0x140012b0e  jmp     short loc_140012B6A
0x140012b10  mov     eax, [rdi+4]
0x140012b13  dec     eax
0x140012b15  cmp     eax, 1
0x140012b18  jbe     short loc_140012B3F
0x140012b1a  lea     r9, aInvalidValueTy; "Invalid value type"
0x140012b21  mov     r8d, 558h
0x140012b27  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140012b2e  mov     ecx, 1
0x140012b33  call    AslLogCallPrintf
0x140012b38  mov     ebx, 0C0000024h
0x140012b3d  jmp     short loc_140012B7F
0x140012b3f  mov     ecx, [rdi+8]
0x140012b42  lea     rdx, [rdi+0Ch]
0x140012b46  shr     rcx, 1
0x140012b49  xor     eax, eax
0x140012b4b  mov     [rdx+rcx*2], ax
0x140012b4f  mov     rcx, r14
0x140012b52  call    AslStringDuplicate
0x140012b57  mov     ebx, eax
0x140012b59  test    eax, eax
0x140012b5b  jns     short loc_140012B7F
0x140012b5d  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x140012b64  mov     r8d, 562h
0x140012b6a  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140012b71  mov     dword ptr [rsp+68h+Length], eax
0x140012b75  mov     ecx, 1
0x140012b7a  call    AslLogCallPrintf
0x140012b7f  mov     rcx, gs:60h
0x140012b88  mov     r8, rdi; P
0x140012b8b  xor     edx, edx; Flags
0x140012b8d  mov     rcx, [rcx+30h]; HeapHandle
0x140012b91  call    cs:__imp_RtlFreeHeap
0x140012b97  mov     eax, ebx
0x140012b99  add     rsp, 48h
0x140012b9d  pop     r14
0x140012b9f  pop     rdi
0x140012ba0  pop     rsi
0x140012ba1  pop     rbx
0x140012ba2  retn
```
