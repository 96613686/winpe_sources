# RegistryKey::GetDwordValues(void)

- ea: `0x180020650`
- end: `0x18002078f`
- name: `?GetDwordValues@RegistryKey@@UEBA?AV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@XZ`
- size: `319`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180004080`
- `0x180004a50`
- `0x18000f684`
- `0x18000f744`
- `0x180020650`
- `0x18002121c`
- `0x1800227c0`
- `0x180025010`

## pseudocode

```c
_QWORD *__fastcall RegistryKey::GetDwordValues(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // r14
  unsigned int i; // esi
  void **v6; // rax
  void **v7; // rdx
  _DWORD v9[2]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v10; // [rsp+40h] [rbp-31h]
  _QWORD *v11; // [rsp+48h] [rbp-29h]
  void *v12[5]; // [rsp+50h] [rbp-21h] BYREF
  int v13; // [rsp+78h] [rbp+7h]
  _BYTE v14[40]; // [rsp+80h] [rbp+Fh] BYREF

  v10 = -2;
  v11 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v9[1] = 1;
  if ( a1[8] )
  {
    v4 = (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 64LL))(a1);
    std::vector<std::pair<std::wstring,unsigned long>>::reserve(a2, v4);
    for ( i = 0; i < (unsigned int)v4; ++i )
    {
      v9[0] = 0;
      std::pair<std::wstring,unsigned long>::pair<std::wstring,unsigned long>(v12);
      v6 = (void **)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *, _QWORD, _DWORD *))(*a1 + 72LL))(a1, v14, i, v9);
      std::wstring::assign(v12, v6);
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v14);
      if ( v9[0] == 4 )
      {
        v7 = v12;
        if ( v12[3] >= (void *)8 )
          v7 = (void **)v12[0];
        v13 = (*(__int64 (__fastcall **)(_QWORD *, void **))(*a1 + 8LL))(a1, v7);
        std::vector<std::pair<std::wstring,unsigned long>>::push_back(a2, v12);
      }
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v12);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180020650  mov     rax, rsp
0x180020653  push    rbp
0x180020654  push    rdi
0x180020655  push    r14
0x180020657  lea     rbp, [rax-5Fh]
0x18002065b  sub     rsp, 0B0h
0x180020662  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18002066a  mov     [rax+18h], rbx
0x18002066e  mov     [rax+20h], rsi
0x180020672  mov     rax, cs:__security_cookie
0x180020679  xor     rax, rsp
0x18002067c  mov     [rbp+57h+var_20], rax
0x180020680  mov     rbx, rdx
0x180020683  mov     rdi, rcx
0x180020686  mov     [rbp+57h+var_80], rdx
0x18002068a  mov     [rbp+57h+var_8C], 0
0x180020691  mov     qword ptr [rdx], 0
0x180020698  mov     qword ptr [rdx+8], 0
0x1800206a0  mov     qword ptr [rdx+10h], 0
0x1800206a8  mov     [rbp+57h+var_8C], 1
0x1800206af  cmp     qword ptr [rcx+40h], 0
0x1800206b4  jz      loc_180020767
0x1800206ba  mov     rax, [rcx]
0x1800206bd  mov     rax, [rax+40h]
0x1800206c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206c6  mov     r14d, eax
0x1800206c9  mov     edx, eax
0x1800206cb  mov     rcx, rbx
0x1800206ce  call    ?reserve@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAX_K@Z; std::vector<std::pair<std::wstring,ulong>>::reserve(unsigned __int64)
0x1800206d3  xor     esi, esi
0x1800206d5  test    r14d, r14d
0x1800206d8  jz      loc_180020767
0x1800206de  mov     [rbp+57h+var_90], 0
0x1800206e5  lea     rcx, [rbp+57h+var_78]
0x1800206e9  call    ??0?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::pair<std::wstring,ulong>(void)
0x1800206ee  nop
0x1800206ef  mov     rax, [rdi]
0x1800206f2  lea     r9, [rbp+57h+var_90]
0x1800206f6  mov     r8d, esi
0x1800206f9  lea     rdx, [rbp+57h+var_48]
0x1800206fd  mov     rcx, rdi
0x180020700  mov     rax, [rax+48h]
0x180020704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020709  nop
0x18002070a  mov     rdx, rax; Src
0x18002070d  lea     rcx, [rbp+57h+var_78]; void *
0x180020711  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x180020716  nop
0x180020717  lea     rcx, [rbp+57h+var_48]
0x18002071b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180020720  cmp     [rbp+57h+var_90], 4
0x180020724  jnz     short loc_180020753
0x180020726  mov     rax, [rdi]
0x180020729  lea     rdx, [rbp+57h+var_78]
0x18002072d  cmp     [rbp+57h+var_60], 8
0x180020732  cmovnb  rdx, [rbp+57h+var_78]
0x180020737  mov     rcx, rdi
0x18002073a  mov     rax, [rax+8]
0x18002073e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020743  mov     [rbp+57h+var_50], eax
0x180020746  lea     rdx, [rbp+57h+var_78]
0x18002074a  mov     rcx, rbx
0x18002074d  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAXAEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@2@@Z; std::vector<std::pair<std::wstring,ulong>>::push_back(std::pair<std::wstring,ulong> const &)
0x180020752  nop
0x180020753  lea     rcx, [rbp+57h+var_78]
0x180020757  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18002075c  inc     esi
0x18002075e  cmp     esi, r14d
0x180020761  jb      loc_1800206DE
0x180020767  mov     rax, rbx
0x18002076a  mov     rcx, [rbp+57h+var_20]
0x18002076e  xor     rcx, rsp; StackCookie
0x180020771  call    __security_check_cookie
0x180020776  lea     r11, [rsp+0C0h+var_10]
0x18002077e  mov     rbx, [r11+30h]
0x180020782  mov     rsi, [r11+38h]
0x180020786  mov     rsp, r11
0x180020789  pop     r14
0x18002078b  pop     rdi
0x18002078c  pop     rbp
0x18002078d  retn
```
