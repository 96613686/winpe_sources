# KeyMachine::DoUpdateRooting(void)

- ea: `0x18002b084`
- end: `0x18002b291`
- name: `?DoUpdateRooting@KeyMachine@@IEAAXXZ`
- size: `525`
- prototype: `void __fastcall(KeyMachine *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002a484`

## callees

- `0x1800171b0`
- `0x18002b084`
- `0x18002b298`
- `0x180039dd0`
- `0x180054a54`
- `0x1800593bc`
- `0x180075e60`
- `0x18008251f`
- `0x1800b8010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002b0e4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002b0e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b256`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall KeyMachine::DoUpdateRooting(KeyMachine *this)
{
  char *v2; // rdi
  unsigned __int64 v3; // r14
  __int128 *v4; // r15
  __int64 v5; // rbx
  _WORD *v6; // rcx
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rbx
  void (__fastcall *v14)(__int64, char **, __int128 *, char *); // r14
  char *v15; // rcx
  int v16; // [rsp+20h] [rbp-58h]
  LPVOID pv; // [rsp+30h] [rbp-48h] BYREF
  char *v18; // [rsp+38h] [rbp-40h] BYREF
  __int128 v19; // [rsp+40h] [rbp-38h] BYREF
  __int128 v20; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v2 = (char *)this + 200;
  v19 = 0;
  v20 = 0;
  v3 = *((_QWORD *)this + 27);
  if ( *((_QWORD *)this + 28) <= 7u )
    v4 = (__int128 *)((char *)this + 200);
  else
    v4 = *(__int128 **)v2;
  if ( v3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v3 > 7 )
  {
    v5 = std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Calculate_growth(
           *((_QWORD *)this + 27),
           7,
           0x7FFFFFFFFFFFFFFELL);
    *(_QWORD *)&v19 = std::allocator<unsigned short>::allocate(&v19, v5 + 1);
    *(_QWORD *)&v20 = v3;
    *((_QWORD *)&v20 + 1) = v5;
    memcpy_0((void *)v19, v4, 2 * v3 + 2);
  }
  else
  {
    *(_QWORD *)&v20 = *((_QWORD *)this + 27);
    *((_QWORD *)&v20 + 1) = 7;
    v19 = *v4;
  }
  *((_QWORD *)v2 + 2) = 0;
  if ( *((_QWORD *)v2 + 3) <= 7u )
    v6 = v2;
  else
    v6 = *(_WORD **)v2;
  *v6 = 0;
  pv = 0;
  v7 = (__int64 *)*((_QWORD *)this + 37);
  if ( v7 )
  {
    v8 = *v7;
    pv = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v8 + 56))(v7, &pv);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v9,
        v16);
  }
  else
  {
    v10 = (__int64 *)*((_QWORD *)this + 34);
    if ( !v10 )
      goto LABEL_20;
    v11 = *v10;
    pv = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v11 + 56))(v10, &pv);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v12,
        v16);
  }
  if ( pv )
    std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::assign(v2);
LABEL_20:
  v13 = *((_QWORD *)this + 20);
  v14 = *(void (__fastcall **)(__int64, char **, __int128 *, char *))(*(_QWORD *)v13 + 64LL);
  v18 = (char *)this + 16;
  if ( this != (KeyMachine *)-16LL )
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16);
  v14(v13, &v18, &v19, v2);
  v15 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( *((_QWORD *)&v20 + 1) > 7u )
    std::_Deallocate<16>(v19, 2LL * *((_QWORD *)&v20 + 1) + 2);
}

```

## disassembly

```asm
0x18002b084  push    rbp
0x18002b086  push    rbx
0x18002b087  push    rsi
0x18002b088  push    rdi
0x18002b089  push    r14
0x18002b08b  push    r15
0x18002b08d  mov     rbp, rsp
0x18002b090  sub     rsp, 78h
0x18002b094  mov     rax, cs:__security_cookie
0x18002b09b  xor     rax, rsp
0x18002b09e  mov     [rbp+var_18], rax
0x18002b0a2  mov     rsi, rcx
0x18002b0a5  lea     rdi, [rcx+0C8h]
0x18002b0ac  xorps   xmm0, xmm0
0x18002b0af  movups  [rbp+var_38], xmm0
0x18002b0b3  xorps   xmm1, xmm1
0x18002b0b6  movdqu  [rbp+var_28], xmm1
0x18002b0bb  mov     r14, [rdi+10h]
0x18002b0bf  cmp     qword ptr [rdi+18h], 7
0x18002b0c4  jbe     short loc_18002B0CB
0x18002b0c6  mov     r15, [rdi]
0x18002b0c9  jmp     short loc_18002B0CE
0x18002b0cb  mov     r15, rdi
0x18002b0ce  mov     r8, 7FFFFFFFFFFFFFFEh
0x18002b0d8  cmp     r14, r8
0x18002b0db  jbe     short loc_18002B0EB
0x18002b0dd  lea     rcx, aStringTooLong; "string too long"
0x18002b0e4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002b0eb  cmp     r14, 7
0x18002b0ef  ja      short loc_18002B10E
0x18002b0f1  mov     qword ptr [rbp+var_28], r14
0x18002b0f5  mov     qword ptr [rbp+var_28+8], 7
0x18002b0fd  mov     rax, [r15]
0x18002b100  mov     qword ptr [rbp+var_38], rax
0x18002b104  mov     rax, [r15+8]
0x18002b108  mov     qword ptr [rbp+var_38+8], rax
0x18002b10c  jmp     short loc_18002B14B
0x18002b10e  mov     edx, 7
0x18002b113  mov     rcx, r14
0x18002b116  call    ?_Calculate_growth@?$basic_string@GUcontent_id_char_traits@@V?$allocator@G@std@@@std@@CA_K_K00@Z; std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>>::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18002b11b  mov     rbx, rax
0x18002b11e  lea     rdx, [rax+1]
0x18002b122  lea     rcx, [rbp+var_38]
0x18002b126  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18002b12b  mov     qword ptr [rbp+var_38], rax
0x18002b12f  mov     qword ptr [rbp+var_28], r14
0x18002b133  mov     qword ptr [rbp+var_28+8], rbx
0x18002b137  lea     r8, ds:2[r14*2]; Size
0x18002b13f  mov     rdx, r15; Src
0x18002b142  mov     rcx, rax; void *
0x18002b145  call    memcpy_0
0x18002b14a  nop
0x18002b14b  xor     r15d, r15d
0x18002b14e  mov     [rdi+10h], r15
0x18002b152  cmp     qword ptr [rdi+18h], 7
0x18002b157  jbe     short loc_18002B15E
0x18002b159  mov     rcx, [rdi]
0x18002b15c  jmp     short loc_18002B161
0x18002b15e  mov     rcx, rdi
0x18002b161  mov     [rcx], r15w
0x18002b165  mov     [rbp+pv], r15
0x18002b169  mov     rcx, [rsi+128h]
0x18002b170  test    rcx, rcx
0x18002b173  jz      short loc_18002B1A6
0x18002b175  mov     rax, [rcx]
0x18002b178  mov     [rbp+pv], r15
0x18002b17c  lea     rdx, [rbp+pv]
0x18002b180  mov     rax, [rax+38h]
0x18002b184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b189  mov     rcx, [rbp+30h]; this
0x18002b18d  test    eax, eax
0x18002b18f  jns     short loc_18002B1E3
0x18002b191  mov     r9d, eax; char *
0x18002b194  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002b19b  mov     edx, 4E3h; void *
0x18002b1a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b1a6  mov     rcx, [rsi+110h]
0x18002b1ad  test    rcx, rcx
0x18002b1b0  jz      short loc_18002B1F4
0x18002b1b2  mov     rax, [rcx]
0x18002b1b5  mov     [rbp+pv], r15
0x18002b1b9  lea     rdx, [rbp+pv]
0x18002b1bd  mov     rax, [rax+38h]
0x18002b1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1c6  mov     rcx, [rbp+30h]; this
0x18002b1ca  test    eax, eax
0x18002b1cc  jns     short loc_18002B1E3
0x18002b1ce  mov     r9d, eax; char *
0x18002b1d1  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002b1d8  mov     edx, 4E7h; void *
0x18002b1dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b1e3  mov     rdx, [rbp+pv]
0x18002b1e7  test    rdx, rdx
0x18002b1ea  jz      short loc_18002B1F4
0x18002b1ec  mov     rcx, rdi
0x18002b1ef  call    ?assign@?$basic_string@GUcontent_id_char_traits@@V?$allocator@G@std@@@std@@QEAAAEAV12@QEBG@Z; std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>>::assign(ushort const * const)
0x18002b1f4  mov     rbx, [rsi+0A0h]
0x18002b1fb  mov     rax, [rbx]
0x18002b1fe  mov     r14, [rax+40h]
0x18002b202  lea     rcx, [rsi+10h]
0x18002b206  mov     [rbp+var_40], rcx
0x18002b20a  test    rcx, rcx
0x18002b20d  jz      short loc_18002B21C
0x18002b20f  mov     rax, [rcx]
0x18002b212  mov     rax, [rax+8]
0x18002b216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b21b  nop
0x18002b21c  mov     r9, rdi
0x18002b21f  lea     r8, [rbp+var_38]
0x18002b223  lea     rdx, [rbp+var_40]
0x18002b227  mov     rcx, rbx
0x18002b22a  mov     rax, r14
0x18002b22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b232  nop
0x18002b233  mov     rcx, [rbp+var_40]
0x18002b237  test    rcx, rcx
0x18002b23a  jz      short loc_18002B24D
0x18002b23c  mov     [rbp+var_40], r15
0x18002b240  mov     rax, [rcx]
0x18002b243  mov     rax, [rax+10h]
0x18002b247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b24c  nop
0x18002b24d  mov     rcx, [rbp+pv]; pv
0x18002b251  test    rcx, rcx
0x18002b254  jz      short loc_18002B25D
0x18002b256  call    cs:__imp_CoTaskMemFree
0x18002b25c  nop
0x18002b25d  mov     rdx, qword ptr [rbp+var_28+8]
0x18002b261  cmp     rdx, 7
0x18002b265  jbe     short loc_18002B278
0x18002b267  lea     rdx, ds:2[rdx*2]
0x18002b26f  mov     rcx, qword ptr [rbp+var_38]
0x18002b273  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b278  mov     rcx, [rbp+var_18]
0x18002b27c  xor     rcx, rsp; StackCookie
0x18002b27f  call    __security_check_cookie
0x18002b284  add     rsp, 78h
0x18002b288  pop     r15
0x18002b28a  pop     r14
0x18002b28c  pop     rdi
0x18002b28d  pop     rsi
0x18002b28e  pop     rbx
0x18002b28f  pop     rbp
0x18002b290  retn
```
