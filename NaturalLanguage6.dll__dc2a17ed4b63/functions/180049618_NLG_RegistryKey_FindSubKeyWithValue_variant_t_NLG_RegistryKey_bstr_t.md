# NLG::RegistryKey::FindSubKeyWithValue(_variant_t &,NLG::RegistryKey *,_bstr_t *)

- ea: `0x180049618`
- end: `0x18004975c`
- name: `?FindSubKeyWithValue@RegistryKey@NLG@@QEBA?AV12@AEAV_variant_t@@PEAV12@PEAV_bstr_t@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016ea0`
- `0x18002e1b0`
- `0x180049618`

## callees

- `0x1800420dc`
- `0x180049618`
- `0x1800498d4`
- `0x1800499bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800496c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800496dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049709`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800496c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800496dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049709`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HKEY *__fastcall NLG::RegistryKey::FindSubKeyWithValue(
        NLG::RegistryKey *a1,
        HKEY *a2,
        unsigned __int16 **a3,
        __int64 a4,
        struct _bstr_t *a5)
{
  unsigned int Count; // r14d
  unsigned int i; // edi
  HKEY v11[2]; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF

  if ( *(_QWORD *)a1 )
  {
    Count = NLG::RegistryKey::GetCount(a1);
    if ( Count )
    {
      for ( i = 0; i < Count; ++i )
      {
        NLG::RegistryKey::GetItem(a1, v11, i);
        if ( NLG::RegistryKey::ContainsValue((NLG::RegistryKey *)v11, a3, a5) )
        {
          *a2 = v11[0];
          v11[0] = 0;
          return a2;
        }
        NLG::RegistryKey::FindSubKeyWithValue(v11, hKey, a3);
        if ( hKey[0] )
        {
          *a2 = hKey[0];
          hKey[0] = 0;
          if ( v11[0] )
          {
            RegCloseKey(v11[0]);
            v11[0] = 0;
          }
          return a2;
        }
        if ( v11[0] )
        {
          RegCloseKey(v11[0]);
          v11[0] = 0;
        }
      }
    }
  }
  *a2 = 0;
  return a2;
}

```

## disassembly

```asm
0x180049618  mov     rax, rsp
0x18004961b  mov     [rax+10h], rdx
0x18004961f  push    rbp
0x180049620  push    rdi
0x180049621  push    r12
0x180049623  push    r14
0x180049625  push    r15
0x180049627  mov     rbp, rsp
0x18004962a  sub     rsp, 60h
0x18004962e  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x180049636  mov     [rax+8], rbx
0x18004963a  mov     [rax+18h], rsi
0x18004963e  mov     r12, r8
0x180049641  mov     rbx, rdx
0x180049644  mov     rsi, rcx
0x180049647  mov     [rbp+var_30], 0
0x18004964e  cmp     qword ptr [rcx], 0
0x180049652  jz      loc_180049731
0x180049658  call    ?GetCount@RegistryKey@NLG@@QEBAKXZ; NLG::RegistryKey::GetCount(void)
0x18004965d  mov     r14d, eax
0x180049660  test    eax, eax
0x180049662  jz      loc_180049731
0x180049668  xor     edi, edi
0x18004966a  mov     r15, [rbp+arg_20]
0x18004966e  cmp     edi, r14d
0x180049671  jnb     loc_180049731
0x180049677  mov     r8d, edi
0x18004967a  lea     rdx, [rbp+var_20]
0x18004967e  mov     rcx, rsi
0x180049681  call    ?GetItem@RegistryKey@NLG@@QEBA?AV12@K@Z; NLG::RegistryKey::GetItem(ulong)
0x180049686  nop
0x180049687  mov     r8, r15; struct _bstr_t *
0x18004968a  mov     rdx, r12; struct _variant_t *
0x18004968d  lea     rcx, [rbp+var_20]; this
0x180049691  call    ?ContainsValue@RegistryKey@NLG@@QEBA_NAEAV_variant_t@@PEAV_bstr_t@@@Z; NLG::RegistryKey::ContainsValue(_variant_t &,_bstr_t *)
0x180049696  test    al, al
0x180049698  jnz     short loc_180049719
0x18004969a  mov     [rsp+60h+var_40], r15
0x18004969f  xor     r9d, r9d
0x1800496a2  mov     r8, r12
0x1800496a5  lea     rdx, [rbp+hKey]
0x1800496a9  lea     rcx, [rbp+var_20]
0x1800496ad  call    ?FindSubKeyWithValue@RegistryKey@NLG@@QEBA?AV12@AEAV_variant_t@@PEAV12@PEAV_bstr_t@@@Z; NLG::RegistryKey::FindSubKeyWithValue(_variant_t &,NLG::RegistryKey *,_bstr_t *)
0x1800496b2  nop
0x1800496b3  mov     rax, [rbp+hKey]
0x1800496b7  test    rax, rax
0x1800496ba  jnz     short loc_1800496EE
0x1800496bc  mov     rcx, [rbp+hKey]; hKey
0x1800496c0  test    rcx, rcx
0x1800496c3  jz      short loc_1800496D3
0x1800496c5  call    cs:__imp_RegCloseKey
0x1800496cb  mov     [rbp+hKey], 0
0x1800496d3  mov     rcx, [rbp+var_20]; hKey
0x1800496d7  test    rcx, rcx
0x1800496da  jz      short loc_1800496EA
0x1800496dc  call    cs:__imp_RegCloseKey
0x1800496e2  mov     [rbp+var_20], 0
0x1800496ea  inc     edi
0x1800496ec  jmp     short loc_18004966E
0x1800496ee  mov     [rbx], rax
0x1800496f1  mov     [rbp+hKey], 0
0x1800496f9  mov     [rbp+var_30], 1
0x180049700  mov     rcx, [rbp+var_20]; hKey
0x180049704  test    rcx, rcx
0x180049707  jz      short loc_18004973F
0x180049709  call    cs:__imp_RegCloseKey
0x18004970f  mov     [rbp+var_20], 0
0x180049717  jmp     short loc_18004973F
0x180049719  mov     rax, [rbp+var_20]
0x18004971d  mov     [rbx], rax
0x180049720  mov     [rbp+var_20], 0
0x180049728  mov     [rbp+var_30], 1
0x18004972f  jmp     short loc_18004973F
0x180049731  mov     qword ptr [rbx], 0
0x180049738  mov     [rbp+var_30], 1
0x18004973f  mov     rax, rbx
0x180049742  lea     r11, [rsp+60h+var_s0]
0x180049747  mov     rbx, [r11+30h]
0x18004974b  mov     rsi, [r11+40h]
0x18004974f  mov     rsp, r11
0x180049752  pop     r15
0x180049754  pop     r14
0x180049756  pop     r12
0x180049758  pop     rdi
0x180049759  pop     rbp
0x18004975a  retn
```
