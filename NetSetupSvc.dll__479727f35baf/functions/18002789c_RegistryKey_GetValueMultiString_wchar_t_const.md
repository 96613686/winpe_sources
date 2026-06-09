# RegistryKey::GetValueMultiString(wchar_t const *)

- ea: `0x18002789c`
- end: `0x18002795d`
- name: `?GetValueMultiString@RegistryKey@@QEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEB_W@Z`
- size: `193`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18001d9c0`

## callees

- `0x1800027c0`
- `0x180007048`
- `0x18000d974`
- `0x18002687c`
- `0x18002789c`
- `0x180027964`
- `0x180029ef8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall RegistryKey::GetValueMultiString(__int64 a1, _QWORD *a2)
{
  __int64 v3; // r9
  const wchar_t *v4; // rbx
  __int64 v5; // rax
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  const wchar_t *v8; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v9[3]; // [rsp+40h] [rbp-20h] BYREF

  v7[1] = a2;
  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(a2);
  RegistryKey::GetValueMultiSz(v3, v9);
  v4 = (const wchar_t *)v9[0];
  if ( v9[0] == v9[1] || !*(_WORD *)v9[0] )
    v4 = &MultiSz::emptyMultiSz;
  MultiSz::end(v9, v7);
  while ( v4 != (const wchar_t *)v7[0] )
  {
    v8 = v4;
    std::vector<std::wstring>::emplace_back<wchar_t const * &>(a2, &v8);
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    v4 += v5 + 1;
  }
  std::vector<unsigned char>::_Tidy((__int64)v9);
  return a2;
}

```

## disassembly

```asm
0x18002789c  mov     [rsp-18h+arg_18], rbx
0x1800278a1  push    rbp
0x1800278a2  push    rsi
0x1800278a3  push    rdi
0x1800278a4  mov     rbp, rsp
0x1800278a7  sub     rsp, 60h
0x1800278ab  mov     rax, cs:__security_cookie
0x1800278b2  xor     rax, rsp
0x1800278b5  mov     [rbp+var_8], rax
0x1800278b9  mov     rdi, rdx
0x1800278bc  mov     r9, rcx
0x1800278bf  mov     [rbp+var_30], rdx
0x1800278c3  xor     esi, esi
0x1800278c5  mov     [rbp+var_40], esi
0x1800278c8  mov     rcx, rdx
0x1800278cb  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x1800278d0  mov     [rbp+var_40], 1
0x1800278d7  lea     rdx, [rbp+var_20]
0x1800278db  mov     rcx, r9
0x1800278de  call    ?GetValueMultiSz@RegistryKey@@QEBA?AVMultiSz@@PEB_W@Z; RegistryKey::GetValueMultiSz(wchar_t const *)
0x1800278e3  nop
0x1800278e4  mov     rbx, [rbp+var_20]
0x1800278e8  cmp     rbx, [rbp+var_18]
0x1800278ec  jz      short loc_1800278F3
0x1800278ee  cmp     [rbx], si
0x1800278f1  jnz     short loc_1800278FA
0x1800278f3  lea     rbx, ?emptyMultiSz@MultiSz@@0_WB; wchar_t const MultiSz::emptyMultiSz
0x1800278fa  lea     rdx, [rbp+var_38]
0x1800278fe  lea     rcx, [rbp+var_20]
0x180027902  call    ?end@MultiSz@@QEBA?AVMultiSzIterator@@XZ; MultiSz::end(void)
0x180027907  cmp     rbx, [rbp+var_38]
0x18002790b  jz      short loc_180027934
0x18002790d  mov     [rbp+var_28], rbx
0x180027911  lea     rdx, [rbp+var_28]
0x180027915  mov     rcx, rdi
0x180027918  call    ??$emplace_back@AEAPEB_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEB_W@Z; std::vector<std::wstring>::emplace_back<wchar_t const * &>(wchar_t const * &)
0x18002791d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027921  inc     rax
0x180027924  cmp     [rbx+rax*2], si
0x180027928  jnz     short loc_180027921
0x18002792a  lea     rbx, [rbx+rax*2]
0x18002792e  add     rbx, 2
0x180027932  jmp     short loc_180027907
0x180027934  lea     rcx, [rbp+var_20]
0x180027938  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002793d  mov     rax, rdi
0x180027940  mov     rcx, [rbp+var_8]
0x180027944  xor     rcx, rsp; StackCookie
0x180027947  call    __security_check_cookie
0x18002794c  mov     rbx, [rsp+60h+arg_18]
0x180027954  add     rsp, 60h
0x180027958  pop     rdi
0x180027959  pop     rsi
0x18002795a  pop     rbp
0x18002795b  retn
```
