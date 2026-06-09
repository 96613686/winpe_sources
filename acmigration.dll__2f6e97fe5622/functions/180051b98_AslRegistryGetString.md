# AslRegistryGetString

- ea: `0x180051b98`
- end: `0x180051d5b`
- name: `AslRegistryGetString`
- size: `451`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180051d64`
- `0x18005a904`
- `0x18005b258`
- `0x18005f728`

## callees

- `0x180051b98`
- `0x1800543c0`
- `0x180054934`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180051bc7`
- `ntdll!RtlInitUnicodeString` at `0x180051bc7`
- `ntdll!RtlAllocateHeap` at `0x180051c56`
- `ntdll!RtlAllocateHeap` at `0x180051c56`
- `ntdll!RtlFreeHeap` at `0x180051d49`
- `ntdll!RtlFreeHeap` at `0x180051d49`
- `ntdll!ZwQueryValueKey` at `0x180051bee`
- `ntdll!ZwQueryValueKey` at `0x180051cad`
- `ntdll!ZwQueryValueKey` at `0x180051bee`
- `ntdll!ZwQueryValueKey` at `0x180051cad`

## string_xrefs

- `0x180051c20`: `AslRegistryGetString`
- `0x180051c71`: `AslRegistryGetString`
- `0x180051cdf`: `AslRegistryGetString`
- `0x180051d22`: `AslRegistryGetString`

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
0x180051b98  push    rbx
0x180051b9a  push    rsi
0x180051b9b  push    rdi
0x180051b9c  push    r14
0x180051b9e  sub     rsp, 48h
0x180051ba2  mov     rsi, rdx
0x180051ba5  mov     qword ptr [rcx], 0
0x180051bac  mov     r14, rcx
0x180051baf  mov     [rsp+68h+arg_0], 0
0x180051bb7  xorps   xmm0, xmm0
0x180051bba  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180051bbf  mov     rdx, r8; SourceString
0x180051bc2  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180051bc7  call    cs:__imp_RtlInitUnicodeString
0x180051bcd  xor     r9d, r9d; KeyValueInformation
0x180051bd0  lea     rax, [rsp+68h+arg_0]
0x180051bd5  mov     [rsp+68h+ResultLength], rax; ResultLength
0x180051bda  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180051bdf  mov     rcx, rsi; KeyHandle
0x180051be2  mov     dword ptr [rsp+68h+Length], 0; Length
0x180051bea  lea     r8d, [r9+2]; KeyValueInformationClass
0x180051bee  call    cs:__imp_ZwQueryValueKey
0x180051bf4  mov     ebx, eax
0x180051bf6  cmp     eax, 80000005h
0x180051bfb  jz      short loc_180051C36
0x180051bfd  cmp     eax, 0C0000023h
0x180051c02  jz      short loc_180051C36
0x180051c04  cmp     eax, 0C0000034h
0x180051c09  jz      loc_180051D4F
0x180051c0f  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180051c16  mov     dword ptr [rsp+68h+Length], eax
0x180051c1a  mov     r8d, 536h
0x180051c20  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180051c27  mov     ecx, 1
0x180051c2c  call    AslLogCallPrintf
0x180051c31  jmp     loc_180051D4F
0x180051c36  mov     eax, [rsp+68h+arg_0]
0x180051c3a  mov     edx, 8; Flags
0x180051c3f  add     eax, 2
0x180051c42  mov     [rsp+68h+arg_0], eax
0x180051c46  mov     rcx, gs:60h
0x180051c4f  mov     r8d, eax; Size
0x180051c52  mov     rcx, [rcx+30h]; HeapHandle
0x180051c56  call    cs:__imp_RtlAllocateHeap
0x180051c5c  mov     rdi, rax
0x180051c5f  test    rax, rax
0x180051c62  jnz     short loc_180051C8A
0x180051c64  lea     r9, aOutOfMemory; "Out of memory"
0x180051c6b  mov     r8d, 544h
0x180051c71  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180051c78  mov     ebx, 0C0000017h
0x180051c7d  lea     ecx, [rax+1]
0x180051c80  call    AslLogCallPrintf
0x180051c85  jmp     loc_180051D4F
0x180051c8a  lea     rax, [rsp+68h+arg_0]
0x180051c8f  mov     r9, rdi; KeyValueInformation
0x180051c92  mov     [rsp+68h+ResultLength], rax; ResultLength
0x180051c97  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180051c9c  mov     eax, [rsp+68h+arg_0]
0x180051ca0  mov     r8d, 2; KeyValueInformationClass
0x180051ca6  mov     rcx, rsi; KeyHandle
0x180051ca9  mov     dword ptr [rsp+68h+Length], eax; Length
0x180051cad  call    cs:__imp_ZwQueryValueKey
0x180051cb3  mov     ebx, eax
0x180051cb5  test    eax, eax
0x180051cb7  jns     short loc_180051CC8
0x180051cb9  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180051cc0  mov     r8d, 550h
0x180051cc6  jmp     short loc_180051D22
0x180051cc8  mov     eax, [rdi+4]
0x180051ccb  dec     eax
0x180051ccd  cmp     eax, 1
0x180051cd0  jbe     short loc_180051CF7
0x180051cd2  lea     r9, aInvalidValueTy; "Invalid value type"
0x180051cd9  mov     r8d, 558h
0x180051cdf  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180051ce6  mov     ecx, 1
0x180051ceb  call    AslLogCallPrintf
0x180051cf0  mov     ebx, 0C0000024h
0x180051cf5  jmp     short loc_180051D37
0x180051cf7  mov     ecx, [rdi+8]
0x180051cfa  lea     rdx, [rdi+0Ch]
0x180051cfe  shr     rcx, 1
0x180051d01  xor     eax, eax
0x180051d03  mov     [rdx+rcx*2], ax
0x180051d07  mov     rcx, r14
0x180051d0a  call    AslStringDuplicate
0x180051d0f  mov     ebx, eax
0x180051d11  test    eax, eax
0x180051d13  jns     short loc_180051D37
0x180051d15  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x180051d1c  mov     r8d, 562h
0x180051d22  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180051d29  mov     dword ptr [rsp+68h+Length], eax
0x180051d2d  mov     ecx, 1
0x180051d32  call    AslLogCallPrintf
0x180051d37  mov     rcx, gs:60h
0x180051d40  mov     r8, rdi; P
0x180051d43  xor     edx, edx; Flags
0x180051d45  mov     rcx, [rcx+30h]; HeapHandle
0x180051d49  call    cs:__imp_RtlFreeHeap
0x180051d4f  mov     eax, ebx
0x180051d51  add     rsp, 48h
0x180051d55  pop     r14
0x180051d57  pop     rdi
0x180051d58  pop     rsi
0x180051d59  pop     rbx
0x180051d5a  retn
```
