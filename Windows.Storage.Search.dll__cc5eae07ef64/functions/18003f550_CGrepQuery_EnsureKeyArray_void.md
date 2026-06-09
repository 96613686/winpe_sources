# CGrepQuery::_EnsureKeyArray(void)

- ea: `0x18003f550`
- end: `0x18003f9f1`
- name: `?_EnsureKeyArray@CGrepQuery@@AEAAJXZ`
- size: `1185`
- prototype: `__int64 __fastcall(CGrepQuery *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014e20`

## callees

- `0x18003f550`
- `0x18003f9f8`
- `0x18003fba8`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f6b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f7ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f962`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f6b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f7ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f962`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f74b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f906`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f74b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f906`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x18003f60a`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x18003f7db`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x18003f60a`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x18003f7db`

## pseudocode

```c
__int64 __fastcall CGrepQuery::_EnsureKeyArray(CGrepQuery *this, const struct _GUID *a2)
{
  __int64 result; // rax
  __int64 *v4; // rbx
  struct _tagpropertykey *v5; // r14
  unsigned int v6; // r13d
  void *v7; // rdi
  int KeyArrayFromTwoPropertyKeyStores; // r12d
  __int64 v9; // rax
  void *v10; // rcx
  __int64 v11; // rdi
  struct _tagpropertykey *v12; // r14
  int v13; // ebx
  int v14; // eax
  __int64 v15; // rdi
  int v16; // eax
  struct _tagpropertykey *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rdx
  BOOL v20; // eax
  __int64 v21; // r14
  HLOCAL v22; // rdi
  int v23; // ebx
  int v24; // eax
  __int64 v25; // rax
  int v26; // [rsp+20h] [rbp-29h] BYREF
  struct _tagpropertykey *v27; // [rsp+28h] [rbp-21h]
  unsigned int v28; // [rsp+30h] [rbp-19h] BYREF
  __int64 v29; // [rsp+38h] [rbp-11h] BYREF
  void *v30; // [rsp+40h] [rbp-9h] BYREF
  struct _tagpropertykey *v31; // [rsp+48h] [rbp-1h] BYREF
  struct IPropertyKeyStore *v32; // [rsp+50h] [rbp+7h] BYREF
  __int128 v33; // [rsp+58h] [rbp+Fh] BYREF
  int v34; // [rsp+68h] [rbp+1Fh]

  result = 0;
  if ( *((_QWORD *)this + 13) )
    return result;
  v30 = 0;
  CGrepQuery::_GetFastProperties(this, a2, &v30);
  v4 = (__int64 *)*((_QWORD *)this + 12);
  v5 = 0;
  v6 = 0;
  v27 = 0;
  v31 = 0;
  v28 = 0;
  if ( v4 )
  {
    v7 = v30;
    if ( v30 )
    {
      v32 = 0;
      v29 = 0;
      KeyArrayFromTwoPropertyKeyStores = PSCreatePropertyKeyStore(
                                           0,
                                           0,
                                           &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                                           &v29);
      if ( KeyArrayFromTwoPropertyKeyStores < 0 )
        goto LABEL_10;
      v9 = *v4;
      v26 = 0;
      KeyArrayFromTwoPropertyKeyStores = (*(__int64 (__fastcall **)(__int64 *, int *))(v9 + 24))(v4, &v26);
      if ( KeyArrayFromTwoPropertyKeyStores < 0 )
      {
LABEL_8:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        if ( KeyArrayFromTwoPropertyKeyStores >= 0 )
        {
          KeyArrayFromTwoPropertyKeyStores = GetKeyArrayFromTwoPropertyKeyStores(
                                               *((struct IPropertyKeyStore **)this + 11),
                                               v32,
                                               &v31,
                                               &v28);
          (*(void (__fastcall **)(struct IPropertyKeyStore *))(*(_QWORD *)v32 + 16LL))(v32);
          v5 = v31;
          v6 = v28;
          v27 = v31;
          goto LABEL_10;
        }
      }
      else
      {
        do
        {
          if ( (int)v5 >= v26 )
          {
            KeyArrayFromTwoPropertyKeyStores = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IPropertyKeyStore **))v29)(
                                                 v29,
                                                 &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                                                 &v32);
            goto LABEL_8;
          }
          v34 = 0;
          v25 = *v4;
          v33 = 0;
          KeyArrayFromTwoPropertyKeyStores = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int128 *))(v25 + 32))(
                                               v4,
                                               (unsigned int)v5,
                                               &v33);
          if ( KeyArrayFromTwoPropertyKeyStores >= 0
            && !(*(unsigned int (__fastcall **)(void *, __int128 *))(*(_QWORD *)v7 + 56LL))(v7, &v33) )
          {
            KeyArrayFromTwoPropertyKeyStores = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v29 + 40LL))(
                                                 v29,
                                                 &v33);
          }
          LODWORD(v5) = (_DWORD)v5 + 1;
        }
        while ( KeyArrayFromTwoPropertyKeyStores >= 0 );
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      goto LABEL_24;
    }
  }
  v11 = *((_QWORD *)this + 11);
  v26 = 0;
  KeyArrayFromTwoPropertyKeyStores = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 24LL))(v11, &v26);
  if ( KeyArrayFromTwoPropertyKeyStores < 0 )
    goto LABEL_10;
  if ( is_mul_ok(v26, 0x14u) )
  {
    KeyArrayFromTwoPropertyKeyStores = 0;
    v12 = (struct _tagpropertykey *)LocalAlloc(0x40u, 20LL * v26);
    if ( v12 )
    {
      v13 = 0;
      while ( v13 < v26 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _tagpropertykey *))(*(_QWORD *)v11 + 32LL))(
                v11,
                (unsigned int)v13,
                &v12[v13]);
        ++v13;
        KeyArrayFromTwoPropertyKeyStores = v14;
        if ( v14 < 0 )
          goto LABEL_23;
      }
      v27 = v12;
      v6 = v26;
      v12 = 0;
LABEL_23:
      LocalFree(v12);
    }
    else
    {
      KeyArrayFromTwoPropertyKeyStores = -2147024882;
    }
LABEL_24:
    v5 = v27;
    goto LABEL_10;
  }
  KeyArrayFromTwoPropertyKeyStores = -2147024362;
LABEL_10:
  if ( KeyArrayFromTwoPropertyKeyStores >= 0 )
  {
    *((_DWORD *)this + 28) = 1;
    v15 = 0;
    KeyArrayFromTwoPropertyKeyStores = PSCreatePropertyKeyStore(
                                         0,
                                         0,
                                         &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                                         (char *)this + 104);
    if ( KeyArrayFromTwoPropertyKeyStores >= 0 )
    {
      while ( (unsigned int)v15 < v6 )
      {
        v16 = 0;
        v17 = &v5[v15];
        LODWORD(v18) = 1;
        while ( (_DWORD)v18 )
        {
          v19 = *((_QWORD *)&off_1800F2CC0 + v16);
          if ( v17->pid != *(_DWORD *)(v19 + 16) )
            goto LABEL_31;
          v18 = *(_QWORD *)&v17->fmtid.Data1 - *(_QWORD *)v19;
          if ( *(_QWORD *)&v17->fmtid.Data1 == *(_QWORD *)v19 )
            v18 = *(_QWORD *)v17->fmtid.Data4 - *(_QWORD *)(v19 + 8);
          if ( v18 )
LABEL_31:
            LODWORD(v18) = 1;
          if ( (unsigned int)++v16 >= 7 )
          {
            if ( (_DWORD)v18 )
            {
              KeyArrayFromTwoPropertyKeyStores = (*(__int64 (__fastcall **)(_QWORD, struct _tagpropertykey *))(**((_QWORD **)this + 13) + 40LL))(
                                                   *((_QWORD *)this + 13),
                                                   &v5[v15]);
              v20 = *((_DWORD *)this + 28)
                 && v30
                 && !(*(unsigned int (__fastcall **)(void *, struct _tagpropertykey *))(*(_QWORD *)v30 + 56LL))(
                       v30,
                       &v5[v15]);
              *((_DWORD *)this + 28) = v20;
            }
            break;
          }
        }
        v15 = (unsigned int)(v15 + 1);
        if ( KeyArrayFromTwoPropertyKeyStores < 0 )
          goto LABEL_11;
      }
      v21 = *((_QWORD *)this + 13);
      *((_QWORD *)this + 15) = 0;
      *((_DWORD *)this + 32) = 0;
      v26 = 0;
      KeyArrayFromTwoPropertyKeyStores = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 24LL))(v21, &v26);
      if ( KeyArrayFromTwoPropertyKeyStores >= 0 )
      {
        v31 = 0;
        if ( is_mul_ok(v26, 0x14u) )
        {
          KeyArrayFromTwoPropertyKeyStores = 0;
          v22 = LocalAlloc(0x40u, 20LL * v26);
          if ( v22 )
          {
            v23 = 0;
            while ( v23 < v26 )
            {
              v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 32LL))(
                      v21,
                      (unsigned int)v23,
                      (__int64)v22 + 20 * v23);
              ++v23;
              KeyArrayFromTwoPropertyKeyStores = v24;
              if ( v24 < 0 )
                goto LABEL_55;
            }
            *((_DWORD *)this + 32) = v26;
            *((_QWORD *)this + 15) = v22;
            v22 = 0;
LABEL_55:
            LocalFree(v22);
          }
          else
          {
            KeyArrayFromTwoPropertyKeyStores = -2147024882;
          }
        }
        else
        {
          KeyArrayFromTwoPropertyKeyStores = -2147024362;
        }
      }
      v5 = v27;
    }
  }
LABEL_11:
  LocalFree(v5);
  v10 = v30;
  v30 = 0;
  if ( v10 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)KeyArrayFromTwoPropertyKeyStores;
}

```

## disassembly

```asm
0x18003f550  push    rbp
0x18003f552  push    rsi
0x18003f553  push    r15
0x18003f555  lea     rbp, [rsp-47h]
0x18003f55a  sub     rsp, 90h
0x18003f561  mov     rax, cs:__security_cookie
0x18003f568  xor     rax, rsp
0x18003f56b  mov     [rbp+57h+var_30], rax
0x18003f56f  xor     eax, eax
0x18003f571  mov     rsi, rcx
0x18003f574  cmp     [rcx+68h], rax
0x18003f578  jz      short loc_18003F592
0x18003f57a  mov     rcx, [rbp+57h+var_30]
0x18003f57e  xor     rcx, rsp; StackCookie
0x18003f581  call    __security_check_cookie
0x18003f586  add     rsp, 90h
0x18003f58d  pop     r15
0x18003f58f  pop     rsi
0x18003f590  pop     rbp
0x18003f591  retn
0x18003f592  mov     [rsp+0A0h+arg_8], rbx
0x18003f59a  lea     r8, [rbp+57h+var_60]; void **
0x18003f59e  mov     [rsp+0A0h+arg_18], r12
0x18003f5a6  mov     [rsp+0A0h+var_18], r13
0x18003f5ae  mov     [rsp+0A0h+var_20], r14
0x18003f5b6  mov     [rsp+0A0h+arg_10], rdi
0x18003f5be  mov     [rbp+57h+var_60], rax
0x18003f5c2  call    ?_GetFastProperties@CGrepQuery@@AEAAJAEBU_GUID@@PEAPEAX@Z; CGrepQuery::_GetFastProperties(_GUID const &,void * *)
0x18003f5c7  mov     rbx, [rsi+60h]
0x18003f5cb  xor     r14d, r14d
0x18003f5ce  xor     r13d, r13d
0x18003f5d1  mov     [rbp+57h+var_78], r14
0x18003f5d5  mov     [rbp+57h+var_58], r14
0x18003f5d9  mov     [rbp+57h+var_70], r13d
0x18003f5dd  test    rbx, rbx
0x18003f5e0  jz      loc_18003F70C
0x18003f5e6  mov     rdi, [rbp+57h+var_60]
0x18003f5ea  test    rdi, rdi
0x18003f5ed  jz      loc_18003F70C
0x18003f5f3  lea     r9, [rbp+57h+var_68]
0x18003f5f7  mov     [rbp+57h+var_50], r13
0x18003f5fb  lea     r8, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x18003f602  mov     [rbp+57h+var_68], r13
0x18003f606  xor     edx, edx
0x18003f608  xor     ecx, ecx
0x18003f60a  call    cs:__imp_PSCreatePropertyKeyStore
0x18003f610  mov     r12d, eax
0x18003f613  test    eax, eax
0x18003f615  js      loc_18003F6AD
0x18003f61b  mov     rax, [rbx]
0x18003f61e  lea     rdx, [rbp+57h+var_80]
0x18003f622  mov     rcx, rbx
0x18003f625  mov     [rbp+57h+var_80], r13d
0x18003f629  mov     rax, [rax+18h]
0x18003f62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f632  mov     r12d, eax
0x18003f635  test    eax, eax
0x18003f637  js      short loc_18003F660
0x18003f639  cmp     r14d, [rbp+57h+var_80]
0x18003f63d  jl      loc_18003F979
0x18003f643  mov     rcx, [rbp+57h+var_68]
0x18003f647  lea     r8, [rbp+57h+var_50]
0x18003f64b  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x18003f652  mov     rax, [rcx]
0x18003f655  mov     rax, [rax]
0x18003f658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f65d  mov     r12d, eax
0x18003f660  mov     rcx, [rbp+57h+var_68]
0x18003f664  mov     rax, [rcx]
0x18003f667  mov     rax, [rax+10h]
0x18003f66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f670  test    r12d, r12d
0x18003f673  js      loc_18003F7B1
0x18003f679  mov     rdx, [rbp+57h+var_50]; struct IPropertyKeyStore *
0x18003f67d  lea     r9, [rbp+57h+var_70]; unsigned int *
0x18003f681  mov     rcx, [rsi+58h]; struct IPropertyKeyStore *
0x18003f685  lea     r8, [rbp+57h+var_58]; struct _tagpropertykey **
0x18003f689  call    ?GetKeyArrayFromTwoPropertyKeyStores@@YAJPEAUIPropertyKeyStore@@0PEAPEAU_tagpropertykey@@PEAI@Z; GetKeyArrayFromTwoPropertyKeyStores(IPropertyKeyStore *,IPropertyKeyStore *,_tagpropertykey * *,uint *)
0x18003f68e  mov     rcx, [rbp+57h+var_50]
0x18003f692  mov     r12d, eax
0x18003f695  mov     rax, [rcx]
0x18003f698  mov     rax, [rax+10h]
0x18003f69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6a1  mov     r14, [rbp+57h+var_58]
0x18003f6a5  mov     r13d, [rbp+57h+var_70]
0x18003f6a9  mov     [rbp+57h+var_78], r14
0x18003f6ad  test    r12d, r12d
0x18003f6b0  jns     loc_18003F7C5
0x18003f6b6  mov     rcx, r14; hMem
0x18003f6b9  call    cs:__imp_LocalFree
0x18003f6bf  mov     rcx, [rbp+57h+var_60]
0x18003f6c3  mov     r14, [rsp+0A0h+var_20]
0x18003f6cb  mov     r13, [rsp+0A0h+var_18]
0x18003f6d3  mov     rdi, [rsp+0A0h+arg_10]
0x18003f6db  mov     rbx, [rsp+0A0h+arg_8]
0x18003f6e3  mov     [rbp+57h+var_60], 0
0x18003f6eb  test    rcx, rcx
0x18003f6ee  jz      short loc_18003F6FC
0x18003f6f0  mov     rax, [rcx]
0x18003f6f3  mov     rax, [rax+10h]
0x18003f6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6fc  mov     eax, r12d
0x18003f6ff  mov     r12, [rsp+0A0h+arg_18]
0x18003f707  jmp     loc_18003F57A
0x18003f70c  mov     rdi, [rsi+58h]
0x18003f710  lea     rdx, [rbp+57h+var_80]
0x18003f714  mov     rcx, rdi
0x18003f717  mov     [rbp+57h+var_80], r13d
0x18003f71b  mov     rax, [rdi]
0x18003f71e  mov     rax, [rax+18h]
0x18003f722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f727  mov     r12d, eax
0x18003f72a  test    eax, eax
0x18003f72c  js      loc_18003F6AD
0x18003f732  movsxd  rcx, [rbp+57h+var_80]
0x18003f736  mov     eax, 14h
0x18003f73b  mul     rcx
0x18003f73e  test    rdx, rdx
0x18003f741  jnz     short loc_18003F7BA
0x18003f743  mov     rdx, rax; uBytes
0x18003f746  mov     ecx, 40h ; '@'; uFlags
0x18003f74b  call    cs:__imp_LocalAlloc
0x18003f751  xor     r12d, r12d
0x18003f754  mov     r14, rax
0x18003f757  test    rax, rax
0x18003f75a  mov     eax, 8007000Eh
0x18003f75f  cmovz   r12d, eax
0x18003f763  test    r14, r14
0x18003f766  jz      short loc_18003F7B1
0x18003f768  xor     ebx, ebx
0x18003f76a  nop     word ptr [rax+rax+00h]
0x18003f770  mov     eax, [rbp+57h+var_80]
0x18003f773  cmp     ebx, eax
0x18003f775  jge     short loc_18003F79E
0x18003f777  mov     rdx, [rdi]
0x18003f77a  movsxd  rax, ebx
0x18003f77d  lea     rcx, [rax+rax*4]
0x18003f781  mov     rax, [rdx+20h]
0x18003f785  lea     r8, [r14+rcx*4]
0x18003f789  mov     edx, ebx
0x18003f78b  mov     rcx, rdi
0x18003f78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f793  inc     ebx
0x18003f795  mov     r12d, eax
0x18003f798  test    eax, eax
0x18003f79a  jns     short loc_18003F770
0x18003f79c  jmp     short loc_18003F7A8
0x18003f79e  mov     [rbp+57h+var_78], r14
0x18003f7a2  mov     r13d, eax
0x18003f7a5  xor     r14d, r14d
0x18003f7a8  mov     rcx, r14; hMem
0x18003f7ab  call    cs:__imp_LocalFree
0x18003f7b1  mov     r14, [rbp+57h+var_78]
0x18003f7b5  jmp     loc_18003F6AD
0x18003f7ba  mov     r12d, 80070216h
0x18003f7c0  jmp     loc_18003F6AD
0x18003f7c5  lea     r9, [rsi+68h]
0x18003f7c9  mov     dword ptr [rsi+70h], 1
0x18003f7d0  lea     r8, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x18003f7d7  xor     edx, edx
0x18003f7d9  xor     ecx, ecx
0x18003f7db  call    cs:__imp_PSCreatePropertyKeyStore
0x18003f7e1  xor     edi, edi
0x18003f7e3  mov     r12d, eax
0x18003f7e6  test    eax, eax
0x18003f7e8  js      loc_18003F6B6
0x18003f7ee  lea     rdx, off_1800F2CC0
0x18003f7f5  cmp     edi, r13d
0x18003f7f8  jnb     loc_18003F8AA
0x18003f7fe  lea     rcx, [rdi+rdi*4]
0x18003f802  xor     eax, eax
0x18003f804  lea     rbx, [r14+rcx*4]
0x18003f808  mov     ecx, 1
0x18003f80d  nop     dword ptr [rax]
0x18003f810  test    ecx, ecx
0x18003f812  jz      short loc_18003F841
0x18003f814  movsxd  rcx, eax
0x18003f817  mov     rdx, [rdx+rcx*8]
0x18003f81b  mov     ecx, [rdx+10h]
0x18003f81e  cmp     [rbx+10h], ecx
0x18003f821  jz      short loc_18003F84D
0x18003f823  mov     ecx, 1
0x18003f828  inc     eax
0x18003f82a  lea     rdx, off_1800F2CC0
0x18003f831  cmp     eax, 7
0x18003f834  jb      short loc_18003F810
0x18003f836  test    ecx, ecx
0x18003f838  jnz     short loc_18003F864
0x18003f83a  lea     rdx, off_1800F2CC0
0x18003f841  inc     edi
0x18003f843  test    r12d, r12d
0x18003f846  jns     short loc_18003F7F5
0x18003f848  jmp     loc_18003F6B6
0x18003f84d  mov     rcx, [rbx]
0x18003f850  sub     rcx, [rdx]
0x18003f853  jnz     short loc_18003F85D
0x18003f855  mov     rcx, [rbx+8]
0x18003f859  sub     rcx, [rdx+8]
0x18003f85d  test    rcx, rcx
0x18003f860  jnz     short loc_18003F823
0x18003f862  jmp     short loc_18003F828
0x18003f864  mov     rcx, [rsi+68h]
0x18003f868  mov     rdx, rbx
0x18003f86b  mov     rax, [rcx]
0x18003f86e  mov     rax, [rax+28h]
0x18003f872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f877  cmp     dword ptr [rsi+70h], 0
0x18003f87b  mov     r12d, eax
0x18003f87e  jz      short loc_18003F8A6
0x18003f880  mov     rcx, [rbp+57h+var_60]
0x18003f884  test    rcx, rcx
0x18003f887  jz      short loc_18003F8A6
0x18003f889  mov     rax, [rcx]
0x18003f88c  mov     rdx, rbx
0x18003f88f  mov     rax, [rax+38h]
0x18003f893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f898  test    eax, eax
0x18003f89a  jnz     short loc_18003F8A6
0x18003f89c  mov     eax, 1
0x18003f8a1  mov     [rsi+70h], eax
0x18003f8a4  jmp     short loc_18003F83A
0x18003f8a6  xor     eax, eax
0x18003f8a8  jmp     short loc_18003F8A1
0x18003f8aa  mov     r14, [rsi+68h]
0x18003f8ae  lea     rdx, [rbp+57h+var_80]
0x18003f8b2  mov     qword ptr [rsi+78h], 0
0x18003f8ba  mov     rcx, r14
0x18003f8bd  mov     dword ptr [rsi+80h], 0
0x18003f8c7  mov     [rbp+57h+var_80], 0
0x18003f8ce  mov     rax, [r14]
0x18003f8d1  mov     rax, [rax+18h]
0x18003f8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8da  mov     r12d, eax
0x18003f8dd  test    eax, eax
0x18003f8df  js      loc_18003F968
0x18003f8e5  movsxd  rdx, [rbp+57h+var_80]
0x18003f8e9  mov     eax, 14h
0x18003f8ee  mul     rdx
0x18003f8f1  mov     [rbp+57h+var_58], 0
0x18003f8f9  test    rdx, rdx
0x18003f8fc  jnz     short loc_18003F971
0x18003f8fe  mov     rdx, rax; uBytes
0x18003f901  mov     ecx, 40h ; '@'; uFlags
0x18003f906  call    cs:__imp_LocalAlloc
0x18003f90c  xor     r12d, r12d
0x18003f90f  mov     rdi, rax
0x18003f912  test    rax, rax
0x18003f915  mov     eax, 8007000Eh
0x18003f91a  cmovz   r12d, eax
0x18003f91e  test    rdi, rdi
0x18003f921  jz      short loc_18003F968
0x18003f923  xor     ebx, ebx
0x18003f925  mov     eax, [rbp+57h+var_80]
0x18003f928  cmp     ebx, eax
0x18003f92a  jge     short loc_18003F953
0x18003f92c  mov     rdx, [r14]
0x18003f92f  movsxd  rax, ebx
0x18003f932  lea     rcx, [rax+rax*4]
0x18003f936  mov     rax, [rdx+20h]
0x18003f93a  lea     r8, [rdi+rcx*4]
0x18003f93e  mov     edx, ebx
0x18003f940  mov     rcx, r14
0x18003f943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f948  inc     ebx
0x18003f94a  mov     r12d, eax
0x18003f94d  test    eax, eax
0x18003f94f  jns     short loc_18003F925
0x18003f951  jmp     short loc_18003F95F
0x18003f953  mov     [rsi+80h], eax
0x18003f959  mov     [rsi+78h], rdi
0x18003f95d  xor     edi, edi
0x18003f95f  mov     rcx, rdi; hMem
0x18003f962  call    cs:__imp_LocalFree
0x18003f968  mov     r14, [rbp+57h+var_78]
0x18003f96c  jmp     loc_18003F6B6
0x18003f971  mov     r12d, 80070216h
0x18003f977  jmp     short loc_18003F968
0x18003f979  xor     eax, eax
0x18003f97b  lea     r8, [rbp+57h+var_48]
0x18003f97f  mov     [rbp+57h+var_38], eax
0x18003f982  xorps   xmm0, xmm0
0x18003f985  mov     rax, [rbx]
0x18003f988  mov     edx, r14d
0x18003f98b  mov     rcx, rbx
0x18003f98e  movups  [rbp+57h+var_48], xmm0
0x18003f992  mov     rax, [rax+20h]
0x18003f996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f99b  mov     r12d, eax
0x18003f99e  test    eax, eax
0x18003f9a0  js      short loc_18003F9D0
0x18003f9a2  mov     rax, [rdi]
0x18003f9a5  lea     rdx, [rbp+57h+var_48]
0x18003f9a9  mov     rcx, rdi
0x18003f9ac  mov     rax, [rax+38h]
0x18003f9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9b5  test    eax, eax
0x18003f9b7  jnz     short loc_18003F9D0
0x18003f9b9  mov     rcx, [rbp+57h+var_68]
0x18003f9bd  lea     rdx, [rbp+57h+var_48]
0x18003f9c1  mov     rax, [rcx]
  ... truncated ...
```
