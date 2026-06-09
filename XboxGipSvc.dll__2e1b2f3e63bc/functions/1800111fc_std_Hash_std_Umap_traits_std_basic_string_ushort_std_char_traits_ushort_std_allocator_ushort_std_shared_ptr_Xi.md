# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::erase(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800111fc`
- end: `0x18001132a`
- name: `?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f5d4`
- `0x180010410`
- `0x180010768`
- `0x180010a74`

## callees

- `0x180001b6c`
- `0x180009bf8`
- `0x18000e224`
- `0x1800111fc`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v3; // rax
  _QWORD *v4; // rcx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // r9
  __int64 v7; // rdi
  __int64 i; // rbp
  __int64 v9; // rax
  char **v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  char *v13; // rax
  char *v14; // rcx
  volatile signed __int32 *v15; // rdi
  _QWORD v17[7]; // [rsp+20h] [rbp-38h] BYREF

  v3 = a2[2];
  if ( a2[3] <= 7u )
    v4 = a2;
  else
    v4 = (_QWORD *)*a2;
  v5 = 0;
  v6 = 2 * v3;
  v7 = 0xCBF29CE484222325uLL;
  for ( i = 1; v5 < v6; v7 = 0x100000001B3LL * (v9 ^ v7) )
    v9 = *((unsigned __int8 *)v4 + v5++);
  v10 = (char **)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Find_last<std::wstring>(
                   a1,
                   v17,
                   (__int64)a2,
                   v7)[1];
  if ( !v10 )
    return 0;
  v11 = a1[3];
  v12 = 2 * (v7 & a1[6]);
  if ( *(char ***)(v11 + 16 * (v7 & a1[6]) + 8) == v10 )
  {
    if ( *(char ***)(v11 + 16 * (v7 & a1[6])) == v10 )
    {
      v13 = (char *)a1[1];
      *(_QWORD *)(v11 + 16 * (v7 & a1[6])) = v13;
    }
    else
    {
      v13 = v10[1];
    }
    *(_QWORD *)(v11 + 8 * v12 + 8) = v13;
  }
  else if ( *(char ***)(v11 + 16 * (v7 & a1[6])) == v10 )
  {
    *(_QWORD *)(v11 + 16 * (v7 & a1[6])) = *v10;
  }
  v14 = *v10;
  --a1[2];
  *(_QWORD *)v10[1] = v14;
  *((_QWORD *)v14 + 1) = v10[1];
  v15 = (volatile signed __int32 *)v10[7];
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  std::wstring::~wstring(v10 + 2);
  operator delete(v10, (const struct std::nothrow_t *)0x40);
  return i;
}

```

## disassembly

```asm
0x1800111fc  push    rbx
0x1800111fe  push    rbp
0x1800111ff  push    rsi
0x180011200  push    rdi
0x180011201  sub     rsp, 38h
0x180011205  cmp     qword ptr [rdx+18h], 7
0x18001120a  mov     rsi, rcx
0x18001120d  mov     rax, [rdx+10h]
0x180011211  jbe     short loc_180011218
0x180011213  mov     rcx, [rdx]
0x180011216  jmp     short loc_18001121B
0x180011218  mov     rcx, rdx
0x18001121b  xor     r8d, r8d
0x18001121e  lea     r9, [rax+rax]
0x180011222  mov     rdi, 0CBF29CE484222325h
0x18001122c  lea     ebp, [r8+1]
0x180011230  test    r9, r9
0x180011233  jz      short loc_180011253
0x180011235  movzx   eax, byte ptr [rcx+r8]
0x18001123a  mov     r10, 100000001B3h
0x180011244  xor     rdi, rax
0x180011247  add     r8, rbp
0x18001124a  imul    rdi, r10
0x18001124e  cmp     r8, r9
0x180011251  jb      short loc_180011235
0x180011253  mov     r8, rdx
0x180011256  mov     r9, rdi
0x180011259  lea     rdx, [rsp+58h+var_38]
0x18001125e  mov     rcx, rsi
0x180011261  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180011266  mov     rbx, [rax+8]
0x18001126a  test    rbx, rbx
0x18001126d  jz      loc_18001131C
0x180011273  mov     rcx, [rsi+30h]
0x180011277  mov     rdx, [rsi+18h]
0x18001127b  and     rcx, rdi
0x18001127e  add     rcx, rcx
0x180011281  cmp     [rdx+rcx*8+8], rbx
0x180011286  jnz     short loc_1800112A3
0x180011288  cmp     [rdx+rcx*8], rbx
0x18001128c  jnz     short loc_180011298
0x18001128e  mov     rax, [rsi+8]
0x180011292  mov     [rdx+rcx*8], rax
0x180011296  jmp     short loc_18001129C
0x180011298  mov     rax, [rbx+8]
0x18001129c  mov     [rdx+rcx*8+8], rax
0x1800112a1  jmp     short loc_1800112B0
0x1800112a3  cmp     [rdx+rcx*8], rbx
0x1800112a7  jnz     short loc_1800112B0
0x1800112a9  mov     rax, [rbx]
0x1800112ac  mov     [rdx+rcx*8], rax
0x1800112b0  mov     rcx, [rbx]
0x1800112b3  dec     qword ptr [rsi+10h]
0x1800112b7  mov     rax, [rbx+8]
0x1800112bb  mov     [rax], rcx
0x1800112be  mov     rax, [rbx+8]
0x1800112c2  mov     [rcx+8], rax
0x1800112c6  mov     rdi, [rbx+38h]
0x1800112ca  test    rdi, rdi
0x1800112cd  jz      short loc_180011304
0x1800112cf  or      eax, 0FFFFFFFFh
0x1800112d2  lock xadd [rdi+8], eax
0x1800112d7  cmp     eax, ebp
0x1800112d9  jnz     short loc_180011304
0x1800112db  mov     rax, [rdi]
0x1800112de  mov     rcx, rdi
0x1800112e1  mov     rax, [rax]
0x1800112e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112e9  or      eax, 0FFFFFFFFh
0x1800112ec  lock xadd [rdi+0Ch], eax
0x1800112f1  cmp     eax, ebp
0x1800112f3  jnz     short loc_180011304
0x1800112f5  mov     rax, [rdi]
0x1800112f8  mov     rcx, rdi
0x1800112fb  mov     rax, [rax+8]
0x1800112ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011304  lea     rcx, [rbx+10h]
0x180011308  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001130d  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x180011312  mov     rcx, rbx; void *
0x180011315  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001131a  jmp     short loc_18001131E
0x18001131c  xor     ebp, ebp
0x18001131e  mov     rax, rbp
0x180011321  add     rsp, 38h
0x180011325  pop     rdi
0x180011326  pop     rsi
0x180011327  pop     rbp
0x180011328  pop     rbx
0x180011329  retn
```
