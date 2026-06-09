# Read(std::shared_ptr<std::basic_istream<char,std::char_traits<char>>>,unsigned __int64)

- ea: `0x180349b30`
- end: `0x180349d12`
- name: `?Read@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@_K@Z`
- size: `482`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1803490e0`

## callees

- `0x180014a60`
- `0x180016430`
- `0x180040860`
- `0x180349b30`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f910`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180349bf7`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180349bf7`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180349c27`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180349c27`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180349c19`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180349c19`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180349c8e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180349c8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Read(_QWORD *a1, _QWORD *a2, size_t a3)
{
  void *v6; // rax
  void *v7; // rcx
  char *v8; // rax
  char *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rcx
  char *v12; // rcx
  char *v13; // rax
  volatile signed __int32 *v14; // rbx
  char *Block; // [rsp+28h] [rbp-50h]
  char *v17; // [rsp+38h] [rbp-40h]

  Block = 0;
  v17 = 0;
  if ( a3 )
  {
    if ( a3 > 0x7FFFFFFFFFFFFFFFLL )
      std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(a1, a2);
    if ( a3 < 0x1000 )
    {
      v8 = (char *)operator new(a3);
    }
    else
    {
      if ( a3 + 39 <= a3 )
        __scrt_throw_std_bad_array_new_length();
      v6 = operator new(a3 + 39);
      v7 = v6;
      if ( !v6 )
LABEL_17:
        _invalid_parameter_noinfo_noreturn();
      v8 = (char *)(((unsigned __int64)v6 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *((_QWORD *)v8 - 1) = v7;
    }
    Block = v8;
    v9 = &v8[a3];
    v17 = &v8[a3];
    memset_0(v8, 0, a3);
  }
  else
  {
    v9 = 0;
  }
  std::istream::read(*a2, Block, v9 - Block);
  v10 = *(_QWORD *)(*a2 + 8LL);
  v11 = *a2 + *(int *)(*(_QWORD *)*a2 + 4LL);
  if ( (*(_BYTE *)(v11 + 16) & 1) != 0 )
  {
    std::ios::clear(v11, 0, 0);
    std::istream::seekg(*a2, 0, 0);
  }
  v12 = Block;
  *a1 = 0;
  a1[2] = 0;
  a1[3] = 15;
  *(_BYTE *)a1 = 0;
  if ( Block != &Block[v10] )
  {
    std::string::assign(a1);
    v12 = Block;
  }
  if ( v12 )
  {
    v13 = v12;
    if ( (unsigned __int64)(v17 - v12) >= 0x1000 )
    {
      v12 = (char *)*((_QWORD *)v12 - 1);
      if ( (unsigned __int64)(v13 - v12 - 8) > 0x1F )
        goto LABEL_17;
    }
    operator delete(v12);
  }
  v14 = (volatile signed __int32 *)a2[1];
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180349b30  push    rbx
0x180349b32  push    rbp
0x180349b33  push    rsi
0x180349b34  push    rdi
0x180349b35  push    r14
0x180349b37  sub     rsp, 50h
0x180349b3b  mov     rax, cs:__security_cookie
0x180349b42  xor     rax, rsp
0x180349b45  mov     [rsp+78h+var_38], rax
0x180349b4a  mov     rbx, r8
0x180349b4d  mov     r14, rdx
0x180349b50  mov     rdi, rcx
0x180349b53  mov     [rsp+78h+var_58], rcx
0x180349b58  mov     [rsp+78h+var_58], rdx
0x180349b5d  xorps   xmm1, xmm1
0x180349b60  movdqu  xmmword ptr [rsp+78h+Block], xmm1
0x180349b66  xor     ebp, ebp
0x180349b68  mov     [rsp+78h+var_40], rbp
0x180349b6d  test    r8, r8
0x180349b70  jz      short loc_180349BE4
0x180349b72  mov     rax, 7FFFFFFFFFFFFFFFh
0x180349b7c  cmp     rbx, rax
0x180349b7f  ja      loc_180349D0C
0x180349b85  cmp     rbx, 1000h
0x180349b8c  jb      short loc_180349BBA
0x180349b8e  lea     rcx, [r8+27h]; Size
0x180349b92  cmp     rcx, rbx
0x180349b95  jbe     loc_180349D06
0x180349b9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180349ba0  mov     rcx, rax
0x180349ba3  test    rax, rax
0x180349ba6  jz      loc_180349C8E
0x180349bac  add     rax, 27h ; '''
0x180349bb0  and     rax, 0FFFFFFFFFFFFFFE0h
0x180349bb4  mov     [rax-8], rcx
0x180349bb8  jmp     short loc_180349BC2
0x180349bba  mov     rcx, rbx; Size
0x180349bbd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180349bc2  mov     [rsp+78h+Block], rax
0x180349bc7  lea     rsi, [rbx+rax]
0x180349bcb  mov     [rsp+78h+var_40], rsi
0x180349bd0  mov     r8, rbx; Size
0x180349bd3  xor     edx, edx; Val
0x180349bd5  mov     rcx, rax; void *
0x180349bd8  call    memset_0
0x180349bdd  mov     [rsp+78h+Block+8], rsi
0x180349be2  jmp     short loc_180349BE9
0x180349be4  mov     rsi, [rsp+78h+Block+8]
0x180349be9  mov     rdx, [rsp+78h+Block]
0x180349bee  sub     rsi, rdx
0x180349bf1  mov     r8, rsi
0x180349bf4  mov     rcx, [r14]
0x180349bf7  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x180349bfd  mov     rdx, [r14]
0x180349c00  mov     rbx, [rdx+8]
0x180349c04  mov     rax, [rdx]
0x180349c07  movsxd  rcx, dword ptr [rax+4]
0x180349c0b  add     rcx, rdx
0x180349c0e  test    byte ptr [rcx+10h], 1
0x180349c12  jz      short loc_180349C2D
0x180349c14  xor     r8d, r8d
0x180349c17  xor     edx, edx
0x180349c19  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x180349c1f  xor     r8d, r8d
0x180349c22  xor     edx, edx
0x180349c24  mov     rcx, [r14]
0x180349c27  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x180349c2d  mov     rcx, [rsp+78h+Block]
0x180349c32  lea     r8, [rcx+rbx]
0x180349c36  mov     [rdi], rbp
0x180349c39  mov     [rdi+10h], rbp
0x180349c3d  mov     qword ptr [rdi+18h], 0Fh
0x180349c45  mov     byte ptr [rdi], 0
0x180349c48  cmp     rcx, r8
0x180349c4b  jz      short loc_180349C60
0x180349c4d  sub     r8, rcx
0x180349c50  mov     rdx, rcx
0x180349c53  mov     rcx, rdi; void *
0x180349c56  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180349c5b  mov     rcx, [rsp+78h+Block]; Block
0x180349c60  test    rcx, rcx
0x180349c63  jz      short loc_180349CA8
0x180349c65  mov     rdx, [rsp+78h+var_40]
0x180349c6a  sub     rdx, rcx
0x180349c6d  mov     rax, rcx
0x180349c70  cmp     rdx, 1000h
0x180349c77  jb      short loc_180349C95
0x180349c79  add     rdx, 27h ; '''
0x180349c7d  mov     rcx, [rcx-8]
0x180349c81  sub     rax, rcx
0x180349c84  add     rax, 0FFFFFFFFFFFFFFF8h
0x180349c88  cmp     rax, 1Fh
0x180349c8c  jbe     short loc_180349C95
0x180349c8e  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180349c95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180349c9a  xorps   xmm0, xmm0
0x180349c9d  movdqu  xmmword ptr [rsp+78h+Block], xmm0
0x180349ca3  mov     [rsp+78h+var_40], rbp
0x180349ca8  mov     rbx, [r14+8]
0x180349cac  test    rbx, rbx
0x180349caf  jz      short loc_180349CEB
0x180349cb1  mov     esi, 0FFFFFFFFh
0x180349cb6  mov     eax, esi
0x180349cb8  lock xadd [rbx+8], eax
0x180349cbd  cmp     eax, 1
0x180349cc0  jnz     short loc_180349CEB
0x180349cc2  mov     rax, [rbx]
0x180349cc5  mov     rcx, rbx
0x180349cc8  mov     rax, [rax]
0x180349ccb  call    cs:__guard_dispatch_icall_fptr
0x180349cd1  lock xadd [rbx+0Ch], esi
0x180349cd6  cmp     esi, 1
0x180349cd9  jnz     short loc_180349CEB
0x180349cdb  mov     rdx, [rbx]
0x180349cde  mov     rcx, rbx
0x180349ce1  mov     rax, [rdx+8]
0x180349ce5  call    cs:__guard_dispatch_icall_fptr
0x180349ceb  mov     rax, rdi
0x180349cee  mov     rcx, [rsp+78h+var_38]
0x180349cf3  xor     rcx, rsp; StackCookie
0x180349cf6  call    __security_check_cookie
0x180349cfb  add     rsp, 50h
0x180349cff  pop     r14
0x180349d01  pop     rdi
0x180349d02  pop     rsi
0x180349d03  pop     rbp
0x180349d04  pop     rbx
0x180349d05  retn
0x180349d06  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180349d0c  call    ?_Xlength@?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@std@@CAXXZ; std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(void)
```
