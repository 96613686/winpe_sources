# AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)

- ea: `0x180006d40`
- end: `0x180007272`
- name: `?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z`
- size: `1330`
- prototype: `__int64 __fastcall(AppxAllUserStore *this, const unsigned __int16 *, unsigned int *, struct Common::StringBuffer *)`
- caller_count: `75`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c94`
- `0x180003abc`
- `0x180003bf0`
- `0x180003e28`
- `0x1800040dc`
- `0x180004f1c`
- `0x1800051e0`
- `0x18000566c`
- `0x1800065d4`
- `0x1800069e0`
- `0x180007638`
- `0x180008780`
- `0x18000fed4`
- `0x180012dcc`
- `0x1800137e0`
- `0x180014240`
- `0x1800143e4`
- `0x18001487c`
- `0x1800156d0`
- `0x180016188`
- `0x180016d5c`
- `0x1800175c4`
- `0x1800178e8`
- `0x180017f80`
- `0x180018130`
- `0x180018698`
- `0x1800187d8`
- `0x180019604`
- `0x18001f2cc`
- `0x180020544`
- `0x180020794`
- `0x180021884`
- `0x1800219d4`
- `0x180021ad4`
- `0x180029bc4`
- `0x180029f10`
- `0x18002a9f0`
- `0x18002ac4c`
- `0x18002ad3c`
- `0x18002ae38`
- `0x18002b79c`
- `0x18002bbf0`
- `0x18002cba0`
- `0x18002d110`
- `0x18002e280`
- `0x18002e8c0`
- `0x18002ed50`
- `0x18002eee0`
- `0x18002f100`
- `0x18002f2d0`

## callees

- `0x1800068f0`
- `0x180006d40`
- `0x180007278`
- `0x180017f50`
- `0x180018248`
- `0x18004c972`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006d6b`
- `ntdll!RtlFreeHeap` at `0x180006d6b`

## string_xrefs

- `0x180006e88`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180006eaa`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180006f48`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180007080`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800070a0`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800070c2`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800070e3`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18000711a`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800071a1`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800071c2`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180007205`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180007222`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18000723c`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180007259`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180006ec2`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`
- `0x180006f66`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`
- `0x180006fed`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`
- `0x180007132`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`
- `0x1800071e6`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetAllUserChildStorePath(
        AppxAllUserStore *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct Common::StringBuffer *a4)
{
  unsigned int *v4; // rsi
  char v5; // bl
  void *v6; // r8
  const int *v7; // r8
  int v8; // r13d
  LPCWSTR v9; // r15
  __int64 v10; // rcx
  LPCWSTR v11; // rax
  unsigned int v12; // r14d
  unsigned int v13; // edi
  int v14; // ebx
  __int64 v15; // rsi
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rcx
  AppxAllUserStore *v19; // rax
  int IsStateSeparationEnabled; // eax
  unsigned int v22; // ebx
  const wchar_t *v23; // rsi
  __int64 v24; // rcx
  const wchar_t *v25; // rax
  unsigned int v26; // r14d
  unsigned int v27; // ebx
  __int64 v28; // rdi
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rdi
  int v32; // eax
  __int64 v33; // rcx
  const unsigned __int16 *v34; // rax
  unsigned int v35; // r12d
  __int64 v36; // rbx
  int v37; // eax
  const int *v38; // [rsp+20h] [rbp-30h] BYREF
  unsigned int *v39; // [rsp+28h] [rbp-28h]
  unsigned int *v40; // [rsp+30h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  bool v43; // [rsp+88h] [rbp+38h] BYREF

  v4 = a3;
  v5 = (char)a2;
  v6 = (void *)*((_QWORD *)a3 + 1);
  if ( v6 )
    RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v6);
  v7 = &Common::StringBufferBuilder::`vftable';
  *((_QWORD *)v4 + 1) = 0;
  *v4 = 0;
  v8 = -2147023613;
  v4[4] = 0;
  v39 = v4;
  v38 = &Common::StringBufferBuilder::`vftable';
  v40 = v4;
  if ( !v5 )
    goto LABEL_4;
  v43 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v43);
  v22 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      (int)v38);
    return v22;
  }
  v23 = L"OSDATA\\Software\\";
  v24 = 0x3FFFFFFF;
  if ( !v43 )
    v23 = L"Software\\";
  v25 = v23;
  while ( *v25 )
  {
    ++v25;
    if ( !--v24 )
    {
      v26 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)0x80070057LL,
        (int)v38);
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
        (const char *)v26,
        (int)v38);
      return v26;
    }
  }
  v30 = 0x3FFFFFFF - v24;
  v31 = *v39;
  if ( (unsigned int)v31 > ~(0x3FFFFFFF - (int)v24) )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)0x80070216LL,
      (int)v38);
    v26 = -2147024362;
LABEL_61:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v26,
      (int)v38);
    goto LABEL_44;
  }
  if ( (unsigned int)v31 + v30 > 0x3FFFFFFF )
  {
    v26 = -2147023613;
    goto LABEL_61;
  }
  v32 = (*(__int64 (__fastcall **)(const int **))v38)(&v38);
  v26 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v32,
      (int)v38);
    goto LABEL_61;
  }
  memcpy_0((void *)(*((_QWORD *)v39 + 1) + 2 * v31), v23, 2LL * v30);
  v26 = 0;
LABEL_44:
  if ( (v26 & 0x80000000) != 0 )
    goto LABEL_32;
  v4 = v39;
  v7 = v38;
LABEL_4:
  v9 = AppxAllUserStore::appxAllUserStorePathString;
  if ( AppxAllUserStore::appxAllUserStorePathString )
  {
    v10 = 0x3FFFFFFF;
    v11 = AppxAllUserStore::appxAllUserStorePathString;
    while ( *v11 )
    {
      ++v11;
      if ( !--v10 )
      {
        v12 = -2147024809;
        v13 = 0;
        v14 = -2147024809;
        goto LABEL_10;
      }
    }
    v14 = 0;
    v13 = 0x3FFFFFFF - v10;
    v12 = -2147024809;
LABEL_10:
    if ( v14 >= 0 )
    {
      v15 = *v4;
      if ( (unsigned int)v15 > ~v13 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)0x80070216LL,
          (int)v38);
        v14 = -2147024362;
      }
      else
      {
        v16 = v13 + (unsigned int)v15;
        if ( (unsigned int)v16 > 0x3FFFFFFF )
        {
          v14 = -2147023613;
        }
        else
        {
          v17 = (*(__int64 (__fastcall **)(const int **, __int64, const int *, struct Common::StringBuffer *))v7)(
                  &v38,
                  v16,
                  v7,
                  a4);
          v14 = v17;
          if ( v17 >= 0 )
          {
            memcpy_0((void *)(*((_QWORD *)v39 + 1) + 2 * v15), v9, 2LL * v13);
            v14 = 0;
            goto LABEL_15;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x10D,
            (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
            (const char *)(unsigned int)v17,
            (int)v38);
        }
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v14,
        (int)v38);
LABEL_15:
      if ( v14 >= 0 )
      {
        if ( !this )
          return 0;
        v18 = 0x3FFFFFFF;
        v19 = this;
        while ( *(_WORD *)v19 )
        {
          v19 = (AppxAllUserStore *)((char *)v19 + 2);
          if ( !--v18 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x35,
              (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
              (const char *)0x80070057LL,
              (int)v38);
LABEL_39:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x60,
              (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
              (const char *)v12,
              (int)v38);
            return v12;
          }
        }
        v27 = 0x3FFFFFFF - v18;
        v28 = *v39;
        if ( (unsigned int)v28 > ~(0x3FFFFFFF - (int)v18) )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x107,
            (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
            (const char *)0x80070216LL,
            (int)v38);
          v8 = -2147024362;
        }
        else if ( v27 + (unsigned int)v28 <= 0x3FFFFFFF )
        {
          v29 = (*(__int64 (__fastcall **)(const int **))v38)(&v38);
          v8 = v29;
          if ( v29 >= 0 )
          {
            memcpy_0((void *)(*((_QWORD *)v39 + 1) + 2 * v28), this, 2LL * v27);
            v8 = 0;
LABEL_37:
            if ( v8 < 0 )
            {
              v12 = v8;
              goto LABEL_39;
            }
            v33 = 0x3FFFFFFF;
            v34 = L"\\";
            while ( *v34 )
            {
              ++v34;
              if ( !--v33 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x35,
                  (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
                  (const char *)0x80070057LL,
                  (int)v38);
LABEL_55:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x61,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
                  (const char *)v12,
                  (int)v38);
                return v12;
              }
            }
            v35 = 0x3FFFFFFF - v33;
            v36 = *v39;
            v37 = Common::StringBuilder::Insert((Common::StringBuilder *)&v38, *v39, 0x3FFFFFFF - (int)v33);
            v12 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x79,
                (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
                (const char *)(unsigned int)v37,
                (int)v38);
            }
            else
            {
              memcpy_0((void *)(*((_QWORD *)v39 + 1) + 2 * v36), L"\\", 2LL * v35);
              v12 = 0;
            }
            if ( (v12 & 0x80000000) != 0 )
              goto LABEL_55;
            return 0;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x10D,
            (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
            (const char *)(unsigned int)v29,
            (int)v38);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)(unsigned int)v8,
          (int)v38);
        goto LABEL_37;
      }
      goto LABEL_23;
    }
  }
  else
  {
    v14 = -2147024809;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x35,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)(unsigned int)v14,
    (int)v38);
LABEL_23:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5D,
    (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
    (const char *)(unsigned int)v14,
    (int)v38);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180006d40  mov     [rsp-28h+Src], rcx
0x180006d45  push    rbp
0x180006d46  push    rbx
0x180006d47  push    rsi
0x180006d48  push    r12
0x180006d4a  push    r13
0x180006d4c  mov     rbp, rsp
0x180006d4f  sub     rsp, 50h
0x180006d53  mov     rsi, r8
0x180006d56  movzx   ebx, dl
0x180006d59  mov     r8, [r8+8]; P
0x180006d5d  test    r8, r8
0x180006d60  jz      short loc_180006D71
0x180006d62  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x180006d69  xor     edx, edx; Flags
0x180006d6b  call    cs:__imp_RtlFreeHeap
0x180006d71  xor     edx, edx
0x180006d73  mov     [rsp+50h+arg_10], rdi
0x180006d7b  mov     [rsp+50h+var_8], r14
0x180006d80  lea     r8, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180006d87  mov     [rsi+8], rdx
0x180006d8b  mov     r12d, 3FFFFFFFh
0x180006d91  mov     [rsi], edx
0x180006d93  mov     r13d, 80070503h
0x180006d99  mov     [rsi+10h], edx
0x180006d9c  mov     [rbp+var_28], rsi
0x180006da0  mov     [rbp+var_30], r8
0x180006da4  mov     [rbp+var_20], rsi
0x180006da8  test    bl, bl
0x180006daa  jnz     loc_180006EF6
0x180006db0  mov     [rsp+50h+var_10], r15
0x180006db5  mov     r15, cs:?appxAllUserStorePathString@AppxAllUserStore@@3PEBGEB; ushort const * const AppxAllUserStore::appxAllUserStorePathString
0x180006dbc  test    r15, r15
0x180006dbf  jz      loc_180006EA1
0x180006dc5  mov     rcx, r12
0x180006dc8  mov     rax, r15
0x180006dcb  nop     dword ptr [rax+rax+00h]
0x180006dd0  cmp     word ptr [rax], 0
0x180006dd4  jz      short loc_180006DEE
0x180006dd6  add     rax, 2
0x180006dda  sub     rcx, 1
0x180006dde  jnz     short loc_180006DD0
0x180006de0  mov     r14d, 80070057h
0x180006de6  mov     rdi, rdx
0x180006de9  mov     ebx, r14d
0x180006dec  jmp     short loc_180006DFC
0x180006dee  mov     rdi, r12
0x180006df1  mov     ebx, edx
0x180006df3  sub     rdi, rcx
0x180006df6  mov     r14d, 80070057h
0x180006dfc  test    ebx, ebx
0x180006dfe  js      loc_180006EA6
0x180006e04  mov     esi, [rsi]
0x180006e06  mov     eax, edi
0x180006e08  not     eax
0x180006e0a  cmp     esi, eax
0x180006e0c  ja      loc_18000707C
0x180006e12  lea     edx, [rdi+rsi]
0x180006e15  cmp     edx, r12d
0x180006e18  ja      loc_1800070B9
0x180006e1e  mov     rax, [r8]
0x180006e21  lea     rcx, [rbp+var_30]
0x180006e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e2a  mov     ebx, eax
0x180006e2c  test    eax, eax
0x180006e2e  js      loc_180007238
0x180006e34  mov     rax, [rbp+var_28]
0x180006e38  mov     rdx, r15; Src
0x180006e3b  mov     r8d, edi
0x180006e3e  add     r8, r8; Size
0x180006e41  mov     rcx, [rax+8]
0x180006e45  lea     rcx, [rcx+rsi*2]; void *
0x180006e49  call    memcpy_0
0x180006e4e  xor     ebx, ebx
0x180006e50  test    ebx, ebx
0x180006e52  js      short loc_180006EBE
0x180006e54  mov     rsi, [rbp+Src]
0x180006e58  test    rsi, rsi
0x180006e5b  jz      loc_180007196
0x180006e61  mov     rcx, r12
0x180006e64  mov     rax, rsi
0x180006e67  nop     word ptr [rax+rax+00000000h]
0x180006e70  cmp     word ptr [rax], 0
0x180006e74  jz      loc_180006F82
0x180006e7a  add     rax, 2
0x180006e7e  sub     rcx, 1
0x180006e82  jnz     short loc_180006E70
0x180006e84  mov     rcx, [rbp+28h]; this
0x180006e88  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180006e8f  mov     r9d, r14d; char *
0x180006e92  mov     edx, 35h ; '5'; void *
0x180006e97  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006e9c  jmp     loc_180006FE9
0x180006ea1  mov     ebx, 80070057h
0x180006ea6  mov     rcx, [rbp+28h]; this
0x180006eaa  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180006eb1  mov     r9d, ebx; char *
0x180006eb4  mov     edx, 35h ; '5'; void *
0x180006eb9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006ebe  mov     rcx, [rbp+28h]; this
0x180006ec2  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x180006ec9  mov     r9d, ebx; char *
0x180006ecc  mov     edx, 5Dh ; ']'; void *
0x180006ed1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ed6  mov     eax, ebx
0x180006ed8  mov     r15, [rsp+50h+var_10]
0x180006edd  mov     r14, [rsp+50h+var_8]
0x180006ee2  mov     rdi, [rsp+50h+arg_10]
0x180006eea  add     rsp, 50h
0x180006eee  pop     r13
0x180006ef0  pop     r12
0x180006ef2  pop     rsi
0x180006ef3  pop     rbx
0x180006ef4  pop     rbp
0x180006ef5  retn
0x180006ef6  lea     rcx, [rbp+arg_8]; bool *
0x180006efa  mov     [rbp+arg_8], dl
0x180006efd  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x180006f02  mov     ebx, eax
0x180006f04  test    eax, eax
0x180006f06  js      loc_1800071E2
0x180006f0c  cmp     [rbp+arg_8], 0
0x180006f10  lea     rax, aSoftware_1; "Software\\"
0x180006f17  lea     rsi, aOsdataSoftware; "OSDATA\\Software\\"
0x180006f1e  mov     rcx, r12
0x180006f21  cmovz   rsi, rax
0x180006f25  mov     rax, rsi
0x180006f28  nop     dword ptr [rax+rax+00000000h]
0x180006f30  cmp     word ptr [rax], 0
0x180006f34  jz      loc_180007009
0x180006f3a  add     rax, 2
0x180006f3e  sub     rcx, 1
0x180006f42  jnz     short loc_180006F30
0x180006f44  mov     rcx, [rbp+28h]; this
0x180006f48  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180006f4f  mov     r14d, 80070057h
0x180006f55  mov     edx, 35h ; '5'; void *
0x180006f5a  mov     r9d, r14d; char *
0x180006f5d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006f62  mov     rcx, [rbp+28h]; this
0x180006f66  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x180006f6d  mov     r9d, r14d; char *
0x180006f70  mov     edx, 5Bh ; '['; void *
0x180006f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f7a  mov     eax, r14d
0x180006f7d  jmp     loc_180006EDD
0x180006f82  mov     rax, [rbp+var_28]
0x180006f86  mov     ebx, r12d
0x180006f89  sub     ebx, ecx
0x180006f8b  mov     edi, [rax]
0x180006f8d  mov     eax, ebx
0x180006f8f  not     eax
0x180006f91  cmp     edi, eax
0x180006f93  ja      loc_1800070BE
0x180006f99  lea     edx, [rbx+rdi]
0x180006f9c  cmp     edx, r12d
0x180006f9f  ja      loc_1800070DF
0x180006fa5  mov     rax, [rbp+var_30]
0x180006fa9  lea     rcx, [rbp+var_30]
0x180006fad  mov     rax, [rax]
0x180006fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fb5  mov     r13d, eax
0x180006fb8  test    eax, eax
0x180006fba  js      loc_180007255
0x180006fc0  mov     rax, [rbp+var_28]
0x180006fc4  mov     rdx, rsi; Src
0x180006fc7  mov     r8d, ebx
0x180006fca  add     r8, r8; Size
0x180006fcd  mov     rcx, [rax+8]
0x180006fd1  lea     rcx, [rcx+rdi*2]; void *
0x180006fd5  call    memcpy_0
0x180006fda  xor     r13d, r13d
0x180006fdd  test    r13d, r13d
0x180006fe0  jns     loc_1800070FC
0x180006fe6  mov     r14d, r13d
0x180006fe9  mov     rcx, [rbp+28h]; this
0x180006fed  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x180006ff4  mov     r9d, r14d; char *
0x180006ff7  mov     edx, 60h ; '`'; void *
0x180006ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007001  mov     eax, r14d
0x180007004  jmp     loc_180006ED8
0x180007009  mov     rax, [rbp+var_28]
0x18000700d  mov     ebx, r12d
0x180007010  sub     ebx, ecx
0x180007012  mov     edi, [rax]
0x180007014  mov     eax, ebx
0x180007016  not     eax
0x180007018  cmp     edi, eax
0x18000701a  ja      loc_18000719D
0x180007020  lea     edx, [rdi+rbx]
0x180007023  cmp     edx, r12d
0x180007026  ja      loc_1800071DD
0x18000702c  mov     rax, [rbp+var_30]
0x180007030  lea     rcx, [rbp+var_30]
0x180007034  mov     rax, [rax]
0x180007037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000703c  mov     r14d, eax
0x18000703f  test    eax, eax
0x180007041  js      loc_18000721E
0x180007047  mov     rax, [rbp+var_28]
0x18000704b  mov     rdx, rsi; Src
0x18000704e  mov     r8d, ebx
0x180007051  add     r8, r8; Size
0x180007054  mov     rcx, [rax+8]
0x180007058  lea     rcx, [rcx+rdi*2]; void *
0x18000705c  call    memcpy_0
0x180007061  xor     edx, edx
0x180007063  mov     r14d, edx
0x180007066  test    r14d, r14d
0x180007069  js      loc_180006F62
0x18000706f  mov     rsi, [rbp+var_28]
0x180007073  mov     r8, [rbp+var_30]
0x180007077  jmp     loc_180006DB0
0x18000707c  mov     rcx, [rbp+28h]; this
0x180007080  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180007087  mov     r9d, 80070216h; char *
0x18000708d  mov     edx, 107h; void *
0x180007092  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007097  mov     ebx, 80070216h
0x18000709c  mov     rcx, [rbp+28h]; this
0x1800070a0  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800070a7  mov     r9d, ebx; char *
0x1800070aa  mov     edx, 79h ; 'y'; void *
0x1800070af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800070b4  jmp     loc_180006E50
0x1800070b9  mov     ebx, r13d
0x1800070bc  jmp     short loc_18000709C
0x1800070be  mov     rcx, [rbp+28h]; this
0x1800070c2  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800070c9  mov     r9d, 80070216h; char *
0x1800070cf  mov     edx, 107h; void *
0x1800070d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800070d9  mov     r13d, 80070216h
0x1800070df  mov     rcx, [rbp+28h]; this
0x1800070e3  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800070ea  mov     r9d, r13d; char *
0x1800070ed  mov     edx, 79h ; 'y'; void *
0x1800070f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800070f7  jmp     loc_180006FDD
0x1800070fc  mov     rcx, r12
0x1800070ff  lea     rax, asc_18004F868; "\\"
0x180007106  cmp     word ptr [rax], 0
0x18000710a  jz      short loc_18000714E
0x18000710c  add     rax, 2
0x180007110  sub     rcx, 1
0x180007114  jnz     short loc_180007106
0x180007116  mov     rcx, [rbp+28h]; this
0x18000711a  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180007121  mov     r9d, r14d; char *
0x180007124  mov     edx, 35h ; '5'; void *
0x180007129  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000712e  mov     rcx, [rbp+28h]; this
0x180007132  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x180007139  mov     r9d, r14d; char *
0x18000713c  mov     edx, 61h ; 'a'; void *
0x180007141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007146  mov     eax, r14d
0x180007149  jmp     loc_180006ED8
0x18000714e  mov     rax, [rbp+var_28]
0x180007152  sub     r12d, ecx
0x180007155  mov     r8d, r12d; unsigned int
0x180007158  lea     rcx, [rbp+var_30]; this
0x18000715c  mov     ebx, [rax]
0x18000715e  mov     edx, ebx; unsigned int
0x180007160  call    ?Insert@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Insert(ulong,ulong)
0x180007165  mov     r14d, eax
0x180007168  test    eax, eax
0x18000716a  js      loc_180007201
0x180007170  mov     rax, [rbp+var_28]
0x180007174  lea     rdx, asc_18004F868; "\\"
0x18000717b  mov     r8d, r12d
0x18000717e  add     r8, r8; Size
0x180007181  mov     rcx, [rax+8]
0x180007185  lea     rcx, [rcx+rbx*2]; void *
0x180007189  call    memcpy_0
0x18000718e  xor     r14d, r14d
0x180007191  test    r14d, r14d
0x180007194  js      short loc_18000712E
0x180007196  xor     eax, eax
0x180007198  jmp     loc_180006ED8
0x18000719d  mov     rcx, [rbp+28h]; this
0x1800071a1  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800071a8  mov     r9d, 80070216h; char *
0x1800071ae  mov     edx, 107h; void *
0x1800071b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800071b8  mov     r14d, 80070216h
0x1800071be  mov     rcx, [rbp+28h]; this
0x1800071c2  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800071c9  mov     r9d, r14d; char *
0x1800071cc  mov     edx, 79h ; 'y'; void *
0x1800071d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800071d6  xor     edx, edx
0x1800071d8  jmp     loc_180007066
0x1800071dd  mov     r14d, r13d
0x1800071e0  jmp     short loc_1800071BE
0x1800071e2  mov     rcx, [rbp+28h]; this
0x1800071e6  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x1800071ed  mov     r9d, ebx; char *
0x1800071f0  mov     edx, 5Ah ; 'Z'; void *
  ... truncated ...
```
