# Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::IsPackageFamilyInAppPolicyList(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort *)

- ea: `0x18007e0a8`
- end: `0x18007e174`
- name: `?IsPackageFamilyInAppPolicyList@CapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@AEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007e19c`

## callees

- `0x180029408`
- `0x18007e0a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e0e9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e0e9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e115`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e13b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e115`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e13b`

## pseudocode

```c
char __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::IsPackageFamilyInAppPolicyList(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3)
{
  const wchar_t *v3; // rbx
  char v5; // di
  wchar_t *v6; // rax
  wchar_t *v7; // rsi
  const WCHAR *v8; // rax

  v3 = a3;
  v5 = 0;
  if ( a3 )
  {
    do
    {
      if ( !*v3 || v5 )
        break;
      v6 = wcschr(v3, 0x3Bu);
      v7 = v6;
      if ( v6 )
        *v6 = 0;
      v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      if ( CompareStringOrdinal(v3, -1, v8, -1, 1) == 2 )
      {
        v5 = 1;
      }
      else if ( CompareStringOrdinal(v3, -1, L"*", -1, 1) == 2 )
      {
        v5 = 1;
      }
      if ( !v7 )
        break;
      v3 = v7 + 1;
      *v7 = 59;
    }
    while ( v7 != (wchar_t *)-2LL );
  }
  return v5;
}

```

## disassembly

```asm
0x18007e0a8  push    rbx
0x18007e0aa  push    rbp
0x18007e0ab  push    rsi
0x18007e0ac  push    rdi
0x18007e0ad  push    r12
0x18007e0af  push    r14
0x18007e0b1  push    r15
0x18007e0b3  sub     rsp, 30h
0x18007e0b7  xor     r14d, r14d
0x18007e0ba  mov     rbx, r8
0x18007e0bd  mov     rbp, rdx
0x18007e0c0  mov     dil, r14b
0x18007e0c3  test    r8, r8
0x18007e0c6  jz      loc_18007E162
0x18007e0cc  lea     r12d, [r14+3Bh]
0x18007e0d0  lea     r15d, [r14+1]
0x18007e0d4  cmp     [rbx], r14w
0x18007e0d8  jz      loc_18007E162
0x18007e0de  test    dil, dil
0x18007e0e1  jnz     short loc_18007E162
0x18007e0e3  mov     edx, r12d; Ch
0x18007e0e6  mov     rcx, rbx; Str
0x18007e0e9  call    cs:__imp_wcschr
0x18007e0ef  mov     rsi, rax
0x18007e0f2  test    rax, rax
0x18007e0f5  jz      short loc_18007E0FB
0x18007e0f7  mov     [rax], r14w
0x18007e0fb  mov     rcx, rbp
0x18007e0fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e103  or      r9d, 0FFFFFFFFh; cchCount2
0x18007e107  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x18007e10c  or      edx, r9d; cchCount1
0x18007e10f  mov     r8, rax; lpString2
0x18007e112  mov     rcx, rbx; lpString1
0x18007e115  call    cs:__imp_CompareStringOrdinal
0x18007e11b  cmp     eax, 2
0x18007e11e  jnz     short loc_18007E125
0x18007e120  mov     dil, r15b
0x18007e123  jmp     short loc_18007E14C
0x18007e125  or      r9d, 0FFFFFFFFh; cchCount2
0x18007e129  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x18007e12e  or      edx, r9d; cchCount1
0x18007e131  lea     r8, String2; "*"
0x18007e138  mov     rcx, rbx; lpString1
0x18007e13b  call    cs:__imp_CompareStringOrdinal
0x18007e141  cmp     eax, 2
0x18007e144  movzx   edi, dil
0x18007e148  cmovz   edi, r15d
0x18007e14c  test    rsi, rsi
0x18007e14f  jz      short loc_18007E162
0x18007e151  lea     rbx, [rsi+2]
0x18007e155  mov     [rsi], r12w
0x18007e159  test    rbx, rbx
0x18007e15c  jnz     loc_18007E0D4
0x18007e162  mov     al, dil
0x18007e165  add     rsp, 30h
0x18007e169  pop     r15
0x18007e16b  pop     r14
0x18007e16d  pop     r12
0x18007e16f  pop     rdi
0x18007e170  pop     rsi
0x18007e171  pop     rbp
0x18007e172  pop     rbx
0x18007e173  retn
```
