# AslRegistryGetUInt32_UStr

- ea: `0x140051560`
- end: `0x140051649`
- name: `AslRegistryGetUInt32_UStr`
- size: `233`
- prototype: `__int64 __fastcall(_DWORD *, void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002d038`

## callees

- `0x14000449f`
- `0x1400079f0`
- `0x14003e364`
- `0x140051560`

## string_xrefs

- `0x140051611`: `AslRegistryGetUInt32_UStr`
- `0x140051631`: `AslRegistryGetUInt32_UStr`

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
  v4 = ZwQueryValueKey_0(a2, a3, KeyValuePartialInformation, &v8, 0x14u, &v7);
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
0x140051560  mov     r11, rsp
0x140051563  mov     [r11+20h], rbx
0x140051567  push    rdi
0x140051568  sub     rsp, 60h
0x14005156c  mov     rax, cs:__security_cookie
0x140051573  xor     rax, rsp
0x140051576  mov     [rsp+68h+var_18], rax
0x14005157b  mov     rdi, rcx
0x14005157e  lea     r9, [r11-30h]; KeyValueInformation
0x140051582  xor     ecx, ecx
0x140051584  mov     r10, r8
0x140051587  mov     [rsp+68h+var_20], ecx
0x14005158b  mov     rax, rdx
0x14005158e  mov     [rsp+68h+var_38], ecx
0x140051592  xorps   xmm0, xmm0
0x140051595  mov     [rdi], ecx
0x140051597  mov     r8d, 2; KeyValueInformationClass
0x14005159d  lea     rcx, [r11-38h]
0x1400515a1  mov     rdx, r10; ValueName
0x1400515a4  mov     [r11-40h], rcx
0x1400515a8  mov     rcx, rax; KeyHandle
0x1400515ab  movups  [rsp+68h+var_30], xmm0
0x1400515b0  mov     [rsp+68h+Length], 14h; Length
0x1400515b8  call    ZwQueryValueKey_0
0x1400515bd  mov     ebx, eax
0x1400515bf  test    eax, eax
0x1400515c1  jns     short loc_1400515E8
0x1400515c3  cmp     eax, 0C0000034h
0x1400515c8  jnz     short loc_140051600
0x1400515ca  mov     eax, ebx
0x1400515cc  mov     rcx, [rsp+68h+var_18]
0x1400515d1  xor     rcx, rsp; StackCookie
0x1400515d4  call    __security_check_cookie
0x1400515d9  mov     rbx, [rsp+68h+arg_18]
0x1400515e1  add     rsp, 60h
0x1400515e5  pop     rdi
0x1400515e6  retn
0x1400515e8  cmp     dword ptr [rsp+68h+var_30+4], 4
0x1400515ed  jnz     short loc_140051624
0x1400515ef  cmp     dword ptr [rsp+68h+var_30+8], 4
0x1400515f4  jnz     short loc_140051624
0x1400515f6  mov     eax, dword ptr [rsp+68h+var_30+0Ch]
0x1400515fa  xor     ebx, ebx
0x1400515fc  mov     [rdi], eax
0x1400515fe  jmp     short loc_1400515CA
0x140051600  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x140051607  mov     [rsp+68h+Length], eax
0x14005160b  mov     r8d, 443h
0x140051611  lea     rdx, aAslregistryget_1; "AslRegistryGetUInt32_UStr"
0x140051618  mov     ecx, 1
0x14005161d  call    AslLogCallPrintf
0x140051622  jmp     short loc_1400515CA
0x140051624  lea     r9, aInvalidValueTy; "Invalid value type"
0x14005162b  mov     r8d, 44Ah
0x140051631  lea     rdx, aAslregistryget_1; "AslRegistryGetUInt32_UStr"
0x140051638  mov     ecx, 1
0x14005163d  call    AslLogCallPrintf
0x140051642  mov     ebx, 0C0000024h
0x140051647  jmp     short loc_1400515CA
```
