# AppxAllUserStore::GetProvisionedSharedPackageContainersPath(Common::StringBuffer *)

- ea: `0x180007b4c`
- end: `0x180007eb3`
- name: `?GetProvisionedSharedPackageContainersPath@AppxAllUserStore@@YAJPEAVStringBuffer@Common@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, struct Common::StringBuffer *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007884`
- `0x18001b5bc`
- `0x180034d10`

## callees

- `0x1800068f0`
- `0x180007b4c`
- `0x180009040`
- `0x180017f50`
- `0x180018248`
- `0x18004c972`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180007b76`
- `ntdll!RtlFreeHeap` at `0x180007b76`

## string_xrefs

- `0x180007bf7`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180007e2b`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180007d92`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetProvisionedSharedPackageContainersPath(
        AppxAllUserStore *this,
        struct Common::StringBuffer *a2)
{
  void *v2; // r8
  LPCWSTR v4; // r15
  _WORD *v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // r14
  __int64 v9; // r13
  int v10; // eax
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rax
  __int64 v13; // r14
  __int64 v14; // r15
  int v15; // eax
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rax
  __int64 v18; // r14
  __int64 v19; // rsi
  int v20; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r9
  const int *v27; // [rsp+20h] [rbp-20h] BYREF
  AppxAllUserStore *v28; // [rsp+28h] [rbp-18h]
  AppxAllUserStore *v29; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v2);
  v4 = AppxAllUserStore::appxAllUserStorePathString;
  *((_QWORD *)this + 1) = 0;
  *(_DWORD *)this = 0;
  *((_DWORD *)this + 4) = 0;
  v28 = this;
  v27 = &Common::StringBufferBuilder::`vftable';
  v29 = this;
  if ( !v4 )
  {
    v7 = -2147024809;
LABEL_41:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v7);
    goto LABEL_42;
  }
  v5 = v4;
  v6 = 0x3FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = v6 == 0 ? 0x80070057 : 0;
  v8 = (0x3FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
    goto LABEL_41;
  v9 = *(unsigned int *)this;
  v7 = -2147024362;
  if ( (unsigned int)v9 > ~(_DWORD)v8 )
  {
    v23 = 2147942934LL;
    v24 = 263;
  }
  else
  {
    if ( (unsigned int)(v8 + v9) > 0x3FFFFFFF )
    {
      v7 = -2147023613;
      goto LABEL_34;
    }
    v10 = Common::StringBufferBuilder::SetLength((Common::StringBufferBuilder *)&v27, (int)v8 + (int)v9);
    v7 = v10;
    if ( v10 >= 0 )
    {
      memcpy_0((void *)(*((_QWORD *)v28 + 1) + 2 * v9), v4, 2LL * (unsigned int)v8);
      v7 = 0;
      goto LABEL_12;
    }
    v23 = (unsigned int)v10;
    v24 = 269;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v24,
    (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v23);
LABEL_34:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x79,
    (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v7);
LABEL_12:
  if ( (v7 & 0x80000000) != 0 )
  {
LABEL_42:
    v22 = 309;
    goto LABEL_31;
  }
  v11 = 0x3FFFFFFF;
  v12 = L"ProvisionedSharedPackageContainers";
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v7 = v11 == 0 ? 0x80070057 : 0;
  v13 = (0x3FFFFFFF - v11) & -(__int64)(v11 != 0);
  if ( !v11 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v7);
    goto LABEL_30;
  }
  v14 = *(unsigned int *)v28;
  if ( (unsigned int)v14 > ~(_DWORD)v13 )
  {
    v7 = -2147024362;
    v25 = 263;
    v26 = 2147942934LL;
  }
  else
  {
    if ( (unsigned int)(v13 + v14) > 0x3FFFFFFF )
    {
      v7 = -2147023613;
      goto LABEL_37;
    }
    v15 = (*(__int64 (__fastcall **)(const int **))v27)(&v27);
    v7 = v15;
    if ( v15 >= 0 )
    {
      memcpy_0((void *)(*((_QWORD *)v28 + 1) + 2 * v14), L"ProvisionedSharedPackageContainers", 2LL * (unsigned int)v13);
      v7 = 0;
      goto LABEL_21;
    }
    v26 = (unsigned int)v15;
    v25 = 269;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v25,
    (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v26);
LABEL_37:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x79,
    (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v7);
LABEL_21:
  if ( (v7 & 0x80000000) != 0 )
  {
LABEL_30:
    v22 = 310;
    goto LABEL_31;
  }
  v16 = 0x3FFFFFFF;
  v17 = L"\\";
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v7 = v16 == 0 ? 0x80070057 : 0;
  v18 = (0x3FFFFFFF - v16) & -(__int64)(v16 != 0);
  if ( v16 )
  {
    v19 = *(unsigned int *)v28;
    v20 = Common::StringBuilder::Insert((Common::StringBuilder *)&v27, *(_DWORD *)v28, v18);
    v7 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v20);
    }
    else
    {
      memcpy_0((void *)(*((_QWORD *)v28 + 1) + 2 * v19), L"\\", 2LL * (unsigned int)v18);
      v7 = 0;
    }
    if ( (v7 & 0x80000000) == 0 )
      return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v7);
  }
  v22 = 311;
LABEL_31:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v22,
    (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
    (const char *)v7,
    (int)v27);
  return v7;
}

```

## disassembly

```asm
0x180007b4c  push    rbp
0x180007b4e  push    rbx
0x180007b4f  push    rsi
0x180007b50  push    rdi
0x180007b51  push    r13
0x180007b53  push    r14
0x180007b55  push    r15
0x180007b57  mov     rbp, rsp
0x180007b5a  sub     rsp, 40h
0x180007b5e  mov     r8, [rcx+8]; P
0x180007b62  xor     r13d, r13d
0x180007b65  mov     rdi, rcx
0x180007b68  test    r8, r8
0x180007b6b  jz      short loc_180007B7C
0x180007b6d  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x180007b74  xor     edx, edx; Flags
0x180007b76  call    cs:__imp_RtlFreeHeap
0x180007b7c  mov     r15, cs:?appxAllUserStorePathString@AppxAllUserStore@@3PEBGEB; ushort const * const AppxAllUserStore::appxAllUserStorePathString
0x180007b83  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180007b8a  mov     [rdi+8], r13
0x180007b8e  mov     [rdi], r13d
0x180007b91  mov     [rdi+10h], r13d
0x180007b95  mov     [rbp+var_18], rdi
0x180007b99  mov     [rbp+var_20], rax
0x180007b9d  mov     [rbp+var_10], rdi
0x180007ba1  test    r15, r15
0x180007ba4  jz      loc_180007E22
0x180007baa  mov     esi, 3FFFFFFFh
0x180007baf  mov     rax, r15
0x180007bb2  mov     edx, esi
0x180007bb4  cmp     [rax], r13w
0x180007bb8  jz      short loc_180007BC4
0x180007bba  add     rax, 2
0x180007bbe  sub     rdx, 1
0x180007bc2  jnz     short loc_180007BB4
0x180007bc4  mov     rax, rdx
0x180007bc7  mov     rcx, rsi
0x180007bca  neg     rax
0x180007bcd  mov     rax, rdx
0x180007bd0  sbb     ebx, ebx
0x180007bd2  sub     rcx, rdx
0x180007bd5  not     ebx
0x180007bd7  and     ebx, 80070057h
0x180007bdd  neg     rax
0x180007be0  sbb     r14, r14
0x180007be3  and     r14, rcx
0x180007be6  test    rdx, rdx
0x180007be9  jz      loc_180007E27
0x180007bef  mov     r13d, [rdi]
0x180007bf2  mov     eax, r14d
0x180007bf5  not     eax
0x180007bf7  lea     rdi, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180007bfe  mov     ebx, 80070216h
0x180007c03  cmp     r13d, eax
0x180007c06  ja      loc_180007DB2
0x180007c0c  lea     edx, [r14+r13]; unsigned int
0x180007c10  cmp     edx, esi
0x180007c12  ja      loc_180007E14
0x180007c18  lea     rcx, [rbp+var_20]; this
0x180007c1c  call    ?SetLength@StringBufferBuilder@Common@@UEAAJK@Z; Common::StringBufferBuilder::SetLength(ulong)
0x180007c21  mov     ebx, eax
0x180007c23  test    eax, eax
0x180007c25  js      loc_180007E62
0x180007c2b  mov     rax, [rbp+var_18]
0x180007c2f  mov     rdx, r15; Src
0x180007c32  mov     r8d, r14d
0x180007c35  add     r8, r8; Size
0x180007c38  mov     rcx, [rax+8]
0x180007c3c  lea     rcx, [rcx+r13*2]; void *
0x180007c40  call    memcpy_0
0x180007c45  xor     r13d, r13d
0x180007c48  mov     ebx, r13d
0x180007c4b  test    ebx, ebx
0x180007c4d  js      loc_180007E3F
0x180007c53  mov     rdx, rsi
0x180007c56  lea     rax, ?provisionedSharedPackageContainersString@AppxAllUserStore@@3QBGB; "ProvisionedSharedPackageContainers"
0x180007c5d  cmp     [rax], r13w
0x180007c61  jz      short loc_180007C6D
0x180007c63  add     rax, 2
0x180007c67  sub     rdx, 1
0x180007c6b  jnz     short loc_180007C5D
0x180007c6d  mov     rax, rdx
0x180007c70  mov     rcx, rsi
0x180007c73  neg     rax
0x180007c76  mov     rax, rdx
0x180007c79  sbb     ebx, ebx
0x180007c7b  sub     rcx, rdx
0x180007c7e  not     ebx
0x180007c80  and     ebx, 80070057h
0x180007c86  neg     rax
0x180007c89  sbb     r14, r14
0x180007c8c  and     r14, rcx
0x180007c8f  test    rdx, rdx
0x180007c92  jz      loc_180007E6F
0x180007c98  mov     rax, [rbp+var_18]
0x180007c9c  mov     r15d, [rax]
0x180007c9f  mov     eax, r14d
0x180007ca2  not     eax
0x180007ca4  cmp     r15d, eax
0x180007ca7  ja      loc_180007DE2
0x180007cad  lea     edx, [r14+r15]
0x180007cb1  cmp     edx, esi
0x180007cb3  ja      loc_180007E1B
0x180007cb9  mov     rax, [rbp+var_20]
0x180007cbd  lea     rcx, [rbp+var_20]
0x180007cc1  mov     rax, [rax]
0x180007cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc9  mov     ebx, eax
0x180007ccb  test    eax, eax
0x180007ccd  js      loc_180007E88
0x180007cd3  mov     rax, [rbp+var_18]
0x180007cd7  lea     rdx, ?provisionedSharedPackageContainersString@AppxAllUserStore@@3QBGB; "ProvisionedSharedPackageContainers"
0x180007cde  mov     r8d, r14d
0x180007ce1  add     r8, r8; Size
0x180007ce4  mov     rcx, [rax+8]
0x180007ce8  lea     rcx, [rcx+r15*2]; void *
0x180007cec  call    memcpy_0
0x180007cf1  mov     ebx, r13d
0x180007cf4  test    ebx, ebx
0x180007cf6  js      loc_180007D89
0x180007cfc  mov     rcx, rsi
0x180007cff  lea     rax, asc_18004F868; "\\"
0x180007d06  cmp     [rax], r13w
0x180007d0a  jz      short loc_180007D16
0x180007d0c  add     rax, 2
0x180007d10  sub     rcx, 1
0x180007d14  jnz     short loc_180007D06
0x180007d16  mov     rax, rcx
0x180007d19  neg     rax
0x180007d1c  mov     rax, rcx
0x180007d1f  sbb     ebx, ebx
0x180007d21  sub     rsi, rcx
0x180007d24  not     ebx
0x180007d26  and     ebx, 80070057h
0x180007d2c  neg     rax
0x180007d2f  sbb     r14, r14
0x180007d32  and     r14, rsi
0x180007d35  test    rcx, rcx
0x180007d38  jz      loc_180007E95
0x180007d3e  mov     rax, [rbp+var_18]
0x180007d42  lea     rcx, [rbp+var_20]; this
0x180007d46  mov     r8d, r14d; unsigned int
0x180007d49  mov     esi, [rax]
0x180007d4b  mov     edx, esi; unsigned int
0x180007d4d  call    ?Insert@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Insert(ulong,ulong)
0x180007d52  mov     ebx, eax
0x180007d54  test    eax, eax
0x180007d56  js      loc_180007E49
0x180007d5c  mov     rax, [rbp+var_18]
0x180007d60  lea     rdx, asc_18004F868; "\\"
0x180007d67  mov     r8d, r14d
0x180007d6a  add     r8, r8; Size
0x180007d6d  mov     rcx, [rax+8]
0x180007d71  lea     rcx, [rcx+rsi*2]; void *
0x180007d75  call    memcpy_0
0x180007d7a  mov     ebx, r13d
0x180007d7d  test    ebx, ebx
0x180007d7f  js      loc_180007EA9
0x180007d85  xor     eax, eax
0x180007d87  jmp     short loc_180007DA3
0x180007d89  mov     edx, 136h; void *
0x180007d8e  mov     rcx, [rbp+38h]; this
0x180007d92  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x180007d99  mov     r9d, ebx; char *
0x180007d9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007da1  mov     eax, ebx
0x180007da3  add     rsp, 40h
0x180007da7  pop     r15
0x180007da9  pop     r14
0x180007dab  pop     r13
0x180007dad  pop     rdi
0x180007dae  pop     rsi
0x180007daf  pop     rbx
0x180007db0  pop     rbp
0x180007db1  retn
0x180007db2  mov     r9d, ebx; char *
0x180007db5  mov     edx, 107h; void *
0x180007dba  mov     rcx, [rbp+38h]; this
0x180007dbe  mov     r8, rdi; unsigned int
0x180007dc1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007dc6  mov     rcx, [rbp+38h]; this
0x180007dca  mov     r9d, ebx; char *
0x180007dcd  mov     r8, rdi; unsigned int
0x180007dd0  mov     edx, 79h ; 'y'; void *
0x180007dd5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007dda  xor     r13d, r13d
0x180007ddd  jmp     loc_180007C4B
0x180007de2  mov     ebx, 80070216h
0x180007de7  mov     edx, 107h; void *
0x180007dec  mov     r9d, ebx; char *
0x180007def  mov     rcx, [rbp+38h]; this
0x180007df3  mov     r8, rdi; unsigned int
0x180007df6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007dfb  mov     rcx, [rbp+38h]; this
0x180007dff  mov     r9d, ebx; char *
0x180007e02  mov     r8, rdi; unsigned int
0x180007e05  mov     edx, 79h ; 'y'; void *
0x180007e0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007e0f  jmp     loc_180007CF4
0x180007e14  mov     ebx, 80070503h
0x180007e19  jmp     short loc_180007DC6
0x180007e1b  mov     ebx, 80070503h
0x180007e20  jmp     short loc_180007DFB
0x180007e22  mov     ebx, 80070057h
0x180007e27  mov     rcx, [rbp+38h]; this
0x180007e2b  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180007e32  mov     r9d, ebx; char *
0x180007e35  mov     edx, 35h ; '5'; void *
0x180007e3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007e3f  mov     edx, 135h
0x180007e44  jmp     loc_180007D8E
0x180007e49  mov     rcx, [rbp+38h]; this
0x180007e4d  mov     r9d, eax; char *
0x180007e50  mov     r8, rdi; unsigned int
0x180007e53  mov     edx, 79h ; 'y'; void *
0x180007e58  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007e5d  jmp     loc_180007D7D
0x180007e62  mov     r9d, eax
0x180007e65  mov     edx, 10Dh
0x180007e6a  jmp     loc_180007DBA
0x180007e6f  mov     rcx, [rbp+38h]; this
0x180007e73  mov     r9d, ebx; char *
0x180007e76  mov     r8, rdi; unsigned int
0x180007e79  mov     edx, 35h ; '5'; void *
0x180007e7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007e83  jmp     loc_180007D89
0x180007e88  mov     r9d, eax
0x180007e8b  mov     edx, 10Dh
0x180007e90  jmp     loc_180007DEF
0x180007e95  mov     rcx, [rbp+38h]; this
0x180007e99  mov     r9d, ebx; char *
0x180007e9c  mov     r8, rdi; unsigned int
0x180007e9f  mov     edx, 35h ; '5'; void *
0x180007ea4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007ea9  mov     edx, 137h
0x180007eae  jmp     loc_180007D8E
```
