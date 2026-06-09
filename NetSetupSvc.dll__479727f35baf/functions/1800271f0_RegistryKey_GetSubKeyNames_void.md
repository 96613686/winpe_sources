# RegistryKey::GetSubKeyNames(void)

- ea: `0x1800271f0`
- end: `0x180027294`
- name: `?GetSubKeyNames@RegistryKey@@QEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `164`
- prototype: `_QWORD *__fastcall(HKEY *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18001e3a8`

## callees

- `0x1800027c0`
- `0x180007048`
- `0x18000d9b4`
- `0x180018490`
- `0x1800268c8`
- `0x1800270e4`
- `0x1800271f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall RegistryKey::GetSubKeyNames(HKEY *a1, _QWORD *a2)
{
  int v4; // edi
  DWORD i; // edx
  _BYTE v7[32]; // [rsp+30h] [rbp-38h] BYREF

  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(a2);
  std::wstring::wstring((__int64)v7);
  v4 = 1;
  for ( i = 0; RegistryKey::GetSubKeyByIndex(a1, i, (__int64)v7); i = v4++ )
    std::vector<std::wstring>::emplace_back<std::wstring>(a2, v7);
  std::wstring::_Tidy_deallocate((__int64)v7);
  return a2;
}

```

## disassembly

```asm
0x1800271f0  mov     [rsp+arg_10], rbx
0x1800271f5  mov     [rsp+arg_18], rsi
0x1800271fa  push    rdi
0x1800271fb  sub     rsp, 60h
0x1800271ff  mov     rax, cs:__security_cookie
0x180027206  xor     rax, rsp
0x180027209  mov     [rsp+68h+var_18], rax
0x18002720e  mov     rbx, rdx
0x180027211  mov     rsi, rcx
0x180027214  mov     [rsp+68h+var_40], rdx
0x180027219  mov     [rsp+68h+var_48], 0
0x180027221  mov     rcx, rdx
0x180027224  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x180027229  mov     [rsp+68h+var_48], 1
0x180027231  lea     rcx, [rsp+68h+var_38]
0x180027236  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002723b  nop
0x18002723c  mov     edi, 1
0x180027241  xor     edx, edx
0x180027243  jmp     short loc_180027256
0x180027245  lea     rdx, [rsp+68h+var_38]
0x18002724a  mov     rcx, rbx
0x18002724d  call    ??$emplace_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring>(std::wstring &&)
0x180027252  mov     edx, edi
0x180027254  inc     edi
0x180027256  lea     r8, [rsp+68h+var_38]
0x18002725b  mov     rcx, rsi
0x18002725e  call    ?GetSubKeyByIndex@RegistryKey@@QEBA_NKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RegistryKey::GetSubKeyByIndex(ulong,std::wstring &)
0x180027263  test    al, al
0x180027265  jnz     short loc_180027245
0x180027267  lea     rcx, [rsp+68h+var_38]
0x18002726c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027271  mov     rax, rbx
0x180027274  mov     rcx, [rsp+68h+var_18]
0x180027279  xor     rcx, rsp; StackCookie
0x18002727c  call    __security_check_cookie
0x180027281  lea     r11, [rsp+68h+var_8]
0x180027286  mov     rbx, [r11+20h]
0x18002728a  mov     rsi, [r11+28h]
0x18002728e  mov     rsp, r11
0x180027291  pop     rdi
0x180027292  retn
```
