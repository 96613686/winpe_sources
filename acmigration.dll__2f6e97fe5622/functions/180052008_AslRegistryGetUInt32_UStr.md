# AslRegistryGetUInt32_UStr

- ea: `0x180052008`
- end: `0x1800520ef`
- name: `AslRegistryGetUInt32_UStr`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180051f88`

## callees

- `0x180001cf0`
- `0x180052008`
- `0x1800543c0`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x180052060`
- `ntdll!ZwQueryValueKey` at `0x180052060`

## string_xrefs

- `0x180052084`: `AslRegistryGetUInt32_UStr`
- `0x1800520bc`: `AslRegistryGetUInt32_UStr`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32_UStr(_DWORD *a1, void *a2, struct _UNICODE_STRING *a3)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  ULONG v7; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+38h] [rbp-30h] BYREF
  int v9; // [rsp+48h] [rbp-20h]

  v9 = 0;
  v7 = 0;
  *a1 = 0;
  v8 = 0;
  v4 = ZwQueryValueKey(a2, a3, KeyValuePartialInformation, &v8, 0x14u, &v7);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( *(_QWORD *)((char *)&v8 + 4) == 0x400000004LL )
    {
      v5 = 0;
      *a1 = HIDWORD(v8);
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1098, "Invalid value type");
      return (unsigned int)-1073741788;
    }
  }
  else if ( v4 != -1073741772 )
  {
    AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1091, "Failed to query key value [%x]", v4);
  }
  return v5;
}

```

## disassembly

```asm
0x180052008  mov     r11, rsp
0x18005200b  mov     [r11+20h], rbx
0x18005200f  push    rdi
0x180052010  sub     rsp, 60h
0x180052014  mov     rax, cs:__security_cookie
0x18005201b  xor     rax, rsp
0x18005201e  mov     [rsp+68h+var_18], rax
0x180052023  mov     rdi, rcx
0x180052026  lea     r9, [r11-30h]; KeyValueInformation
0x18005202a  xor     ecx, ecx
0x18005202c  mov     r10, r8
0x18005202f  mov     [rsp+68h+var_20], ecx
0x180052033  mov     rax, rdx
0x180052036  mov     [rsp+68h+var_38], ecx
0x18005203a  xorps   xmm0, xmm0
0x18005203d  mov     [rdi], ecx
0x18005203f  mov     r8d, 2; KeyValueInformationClass
0x180052045  lea     rcx, [r11-38h]
0x180052049  mov     rdx, r10; ValueName
0x18005204c  mov     [r11-40h], rcx
0x180052050  mov     rcx, rax; KeyHandle
0x180052053  movups  [rsp+68h+var_30], xmm0
0x180052058  mov     [rsp+68h+Length], 14h; Length
0x180052060  call    cs:__imp_ZwQueryValueKey
0x180052066  mov     ebx, eax
0x180052068  test    eax, eax
0x18005206a  jns     short loc_180052097
0x18005206c  cmp     eax, 0C0000034h
0x180052071  jz      short loc_1800520D2
0x180052073  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18005207a  mov     [rsp+68h+Length], eax
0x18005207e  mov     r8d, 443h
0x180052084  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x18005208b  mov     ecx, 1
0x180052090  call    AslLogCallPrintf
0x180052095  jmp     short loc_1800520D2
0x180052097  cmp     dword ptr [rsp+68h+var_30+4], 4
0x18005209c  jnz     short loc_1800520AF
0x18005209e  cmp     dword ptr [rsp+68h+var_30+8], 4
0x1800520a3  jnz     short loc_1800520AF
0x1800520a5  mov     eax, dword ptr [rsp+68h+var_30+0Ch]
0x1800520a9  xor     ebx, ebx
0x1800520ab  mov     [rdi], eax
0x1800520ad  jmp     short loc_1800520D2
0x1800520af  lea     r9, aInvalidValueTy; "Invalid value type"
0x1800520b6  mov     r8d, 44Ah
0x1800520bc  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x1800520c3  mov     ecx, 1
0x1800520c8  call    AslLogCallPrintf
0x1800520cd  mov     ebx, 0C0000024h
0x1800520d2  mov     eax, ebx
0x1800520d4  mov     rcx, [rsp+68h+var_18]
0x1800520d9  xor     rcx, rsp; StackCookie
0x1800520dc  call    __security_check_cookie
0x1800520e1  mov     rbx, [rsp+68h+arg_18]
0x1800520e9  add     rsp, 60h
0x1800520ed  pop     rdi
0x1800520ee  retn
```
