# Action::CreateUniqueId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000e454`
- end: `0x18000e4ce`
- name: `?CreateUniqueId@Action@@IEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001a7d8`
- `0x18001aba0`

## callees

- `0x18000ab70`
- `0x18000b4f0`
- `0x18000d1f0`
- `0x18000e454`
- `0x180020c30`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000e477`
- `RPCRT4!UuidCreate` at `0x18000e477`

## pseudocode

```c
__int64 __fastcall Action::CreateUniqueId(__int64 a1, void *a2)
{
  __int64 v2; // rdi
  void *v5; // rax
  __int64 v6; // rdx
  _BYTE v7[32]; // [rsp+20h] [rbp-38h] BYREF

  v2 = a1 + 88;
  if ( UuidCreate((UUID *)(a1 + 88)) )
    return 2147500037LL;
  if ( a2 )
  {
    v5 = (void *)TsipGuidToString(v7, v2);
    std::wstring::operator=(a2, v5);
    LOBYTE(v6) = 1;
    std::wstring::_Tidy(v7, v6, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e454  mov     [rsp+arg_10], rbx
0x18000e459  push    rdi
0x18000e45a  sub     rsp, 50h
0x18000e45e  mov     rax, cs:__security_cookie
0x18000e465  xor     rax, rsp
0x18000e468  mov     [rsp+58h+var_18], rax
0x18000e46d  lea     rdi, [rcx+58h]
0x18000e471  mov     rbx, rdx
0x18000e474  mov     rcx, rdi; Uuid
0x18000e477  call    cs:__imp_UuidCreate
0x18000e47d  test    eax, eax
0x18000e47f  jz      short loc_18000E488
0x18000e481  mov     eax, 80004005h
0x18000e486  jmp     short loc_18000E4B6
0x18000e488  test    rbx, rbx
0x18000e48b  jz      short loc_18000E4B4
0x18000e48d  mov     rdx, rdi
0x18000e490  lea     rcx, [rsp+58h+var_38]
0x18000e495  call    ?TsipGuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_GUID@@@Z; TsipGuidToString(_GUID const *)
0x18000e49a  mov     rdx, rax; Src
0x18000e49d  mov     rcx, rbx; void *
0x18000e4a0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e4a5  xor     r8d, r8d
0x18000e4a8  lea     rcx, [rsp+58h+var_38]
0x18000e4ad  mov     dl, 1
0x18000e4af  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e4b4  xor     eax, eax
0x18000e4b6  mov     rcx, [rsp+58h+var_18]
0x18000e4bb  xor     rcx, rsp; StackCookie
0x18000e4be  call    __security_check_cookie
0x18000e4c3  mov     rbx, [rsp+58h+arg_10]
0x18000e4c8  add     rsp, 50h
0x18000e4cc  pop     rdi
0x18000e4cd  retn
```
