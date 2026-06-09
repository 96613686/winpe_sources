# AslRegistryGetUInt32_UStr

- ea: `0x180016c10`
- end: `0x180016cf9`
- name: `AslRegistryGetUInt32_UStr`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180016b90`
- `0x18004b104`

## callees

- `0x18000f114`
- `0x180016c10`
- `0x180059270`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x180016c68`
- `ntdll!ZwQueryValueKey` at `0x180016c68`

## string_xrefs

- `0x180016cc1`: `AslRegistryGetUInt32_UStr`
- `0x180016ce1`: `AslRegistryGetUInt32_UStr`

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
0x180016c10  mov     r11, rsp
0x180016c13  mov     [r11+20h], rbx
0x180016c17  push    rdi
0x180016c18  sub     rsp, 60h
0x180016c1c  mov     rax, cs:__security_cookie
0x180016c23  xor     rax, rsp
0x180016c26  mov     [rsp+68h+var_18], rax
0x180016c2b  mov     rdi, rcx
0x180016c2e  lea     r9, [r11-30h]; KeyValueInformation
0x180016c32  xor     ecx, ecx
0x180016c34  mov     r10, r8
0x180016c37  mov     [rsp+68h+var_20], ecx
0x180016c3b  mov     rax, rdx
0x180016c3e  mov     [rsp+68h+var_38], ecx
0x180016c42  xorps   xmm0, xmm0
0x180016c45  mov     [rdi], ecx
0x180016c47  mov     r8d, 2; KeyValueInformationClass
0x180016c4d  lea     rcx, [r11-38h]
0x180016c51  mov     rdx, r10; ValueName
0x180016c54  mov     [r11-40h], rcx
0x180016c58  mov     rcx, rax; KeyHandle
0x180016c5b  movups  [rsp+68h+var_30], xmm0
0x180016c60  mov     [rsp+68h+Length], 14h; Length
0x180016c68  call    cs:__imp_ZwQueryValueKey
0x180016c6e  mov     ebx, eax
0x180016c70  test    eax, eax
0x180016c72  jns     short loc_180016C98
0x180016c74  cmp     eax, 0C0000034h
0x180016c79  jnz     short loc_180016CB0
0x180016c7b  mov     eax, ebx
0x180016c7d  mov     rcx, [rsp+68h+var_18]
0x180016c82  xor     rcx, rsp; StackCookie
0x180016c85  call    __security_check_cookie
0x180016c8a  mov     rbx, [rsp+68h+arg_18]
0x180016c92  add     rsp, 60h
0x180016c96  pop     rdi
0x180016c97  retn
0x180016c98  cmp     dword ptr [rsp+68h+var_30+4], 4
0x180016c9d  jnz     short loc_180016CD4
0x180016c9f  cmp     dword ptr [rsp+68h+var_30+8], 4
0x180016ca4  jnz     short loc_180016CD4
0x180016ca6  mov     eax, dword ptr [rsp+68h+var_30+0Ch]
0x180016caa  xor     ebx, ebx
0x180016cac  mov     [rdi], eax
0x180016cae  jmp     short loc_180016C7B
0x180016cb0  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x180016cb7  mov     [rsp+68h+Length], eax
0x180016cbb  mov     r8d, 443h
0x180016cc1  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x180016cc8  mov     ecx, 1
0x180016ccd  call    AslLogCallPrintf
0x180016cd2  jmp     short loc_180016C7B
0x180016cd4  lea     r9, aInvalidValueTy; "Invalid value type"
0x180016cdb  mov     r8d, 44Ah
0x180016ce1  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x180016ce8  mov     ecx, 1
0x180016ced  call    AslLogCallPrintf
0x180016cf2  mov     ebx, 0C0000024h
0x180016cf7  jmp     short loc_180016C7B
```
