# CGetCmdProps::CopyDbProp(CDbProp &,CDbProp &,ulong,int)

- ea: `0x1800f4a60`
- end: `0x1800f4d18`
- name: `?CopyDbProp@CGetCmdProps@@AEAAXAEAVCDbProp@@0KH@Z`
- size: `696`
- prototype: `void __fastcall(CGetCmdProps *__hidden this, struct CDbProp *, struct CDbProp *, unsigned int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18006df7c`

## callees

- `0x180038f08`
- `0x180063848`
- `0x1800740f4`
- `0x180075d8c`
- `0x1800f4a60`
- `0x18015aa68`
- `0x180188d90`
- `0x180189280`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f4b2f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f4bb5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f4be7`
- `OLEAUT32!__imp_SysAllocString` at `0x1802bec09`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f4b2f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f4bb5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f4be7`
- `OLEAUT32!__imp_SysAllocString` at `0x1802bec09`

## string_xrefs

- `0x1800f4c44`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1800f4c83`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1800f4c23`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1800f4c5d`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1800f4c9c`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1800f4cbb`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1800f4cda`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1800f4d06`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1802bea5a`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1802bea8e`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1802beac2`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1802beb88`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1802bebbe`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1802bebf4`: `onecoreuap\base\appmodel\search\tquery\icommand\cmdprutl.cxx`
- `0x1800f4c38`: `[Query] CopyDbProp: index value out of range: %x\n`
- `0x1800f4c77`: `[Query] CopyDbProp: Invalid VARIANT type: %x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CGetCmdProps::CopyDbProp(
        CGetCmdProps *this,
        struct CDbProp *a2,
        struct CDbProp *a3,
        __int64 a4,
        int a5)
{
  int v7; // ecx
  const wchar_t **v8; // rsi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  const wchar_t *v14; // rsi
  const wchar_t **v15; // rsi
  BSTR v16; // rax
  _WORD *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  BSTR v21; // rax
  unsigned __int64 v22; // rbx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int *v26; // rax
  _WORD *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned __int64 v30; // rbx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR *psz; // [rsp+28h] [rbp-D8h]
  _BYTE v36[528]; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+240h] [rbp+140h] BYREF
  OLECHAR *v38; // [rsp+248h] [rbp+148h]
  _BYTE v39[528]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+398h]

  *(_OWORD *)a2 = *(_OWORD *)a3;
  *((_OWORD *)a2 + 1) = *((_OWORD *)a3 + 1);
  *((_OWORD *)a2 + 2) = *((_OWORD *)a3 + 2);
  *((_OWORD *)a2 + 3) = 0;
  *((_QWORD *)a2 + 8) = 0;
  v7 = *((unsigned __int16 *)a3 + 24);
  v8 = (const wchar_t **)((char *)a3 + 56);
  if ( (v7 & 0x2000) != 0 && !*((_DWORD *)*v8 + 6) )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
      (const wchar_t *)0x1A2,
      (unsigned int)L"[Query] CopyDbProp: index value out of range: %x\n",
      0);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
      (const char *)0xC000000DLL,
      v34);
  }
  v9 = v7 - 3;
  if ( !v9 )
    goto LABEL_16;
  v10 = v9 - 5;
  if ( v10 )
  {
    v11 = v10 - 11;
    if ( v11 )
    {
      v12 = v11 - 8176;
      if ( v12 )
      {
        v13 = v12 - 5;
        if ( !v13 )
        {
          v14 = *v8;
          if ( *v14 != 1 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1B1,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
              (const char *)0xC000000DLL,
              v34);
          v15 = (const wchar_t **)*((_QWORD *)v14 + 2);
          *((_WORD *)a2 + 24) = 8;
          if ( a5 && (v17 = (_WORD *)*((_QWORD *)this + 14)) != 0 && *v17 )
          {
            v34 = 260;
            psz = (OLECHAR *)v36;
            XGrowable<wchar_t,260>::SetSize(&v34, 260);
            v18 = -1;
            v19 = -1;
            do
              ++v19;
            while ( *(_WORD *)(*((_QWORD *)this + 14) + 2 * v19) );
            do
              ++v18;
            while ( (*v15)[v18] );
            v22 = (unsigned int)(v19 + v18 + 2);
            XGrowable<wchar_t,260>::SetSize(&v34, v22);
            v23 = StringCchCopyW(psz, (unsigned int)v22, *((const wchar_t **)this + 14));
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1BD,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
                (const char *)(unsigned int)v23,
                v34);
            v24 = StringCchCatW(psz, v22, L"\\");
            if ( v24 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1C1,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
                (const char *)(unsigned int)v24,
                v34);
            v25 = StringCchCatW(psz, v22, *v15);
            if ( v25 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1C5,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
                (const char *)(unsigned int)v25,
                v34);
            v16 = SysAllocString(psz);
            *((_QWORD *)a2 + 7) = v16;
            if ( psz != (OLECHAR *)v36 )
            {
              operator delete(psz);
              v16 = (BSTR)*((_QWORD *)a2 + 7);
            }
          }
          else
          {
            v16 = SysAllocString(*v15);
            *((_QWORD *)a2 + 7) = v16;
          }
          if ( !v16 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1CD,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
              (const char *)0x8007000ELL,
              v34);
          return;
        }
        if ( v13 != 11 )
        {
          SearchIndexerDebug::Error(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
            (const wchar_t *)0x20B,
            (unsigned int)L"[Query] CopyDbProp: Invalid VARIANT type: %x\n",
            0);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
            (const char *)0xC000000DLL,
            v34);
        }
      }
      if ( **v8 != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1FA,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
          (const char *)0xC000000DLL,
          v34);
      v26 = (int *)*((_QWORD *)*v8 + 2);
      *((_WORD *)a2 + 24) = 3;
      v20 = *v26;
LABEL_17:
      *((_DWORD *)a2 + 14) = v20;
      return;
    }
LABEL_16:
    *((_WORD *)a2 + 24) = 3;
    v20 = *(_DWORD *)v8;
    goto LABEL_17;
  }
  *((_WORD *)a2 + 24) = 8;
  if ( a5 && (v27 = (_WORD *)*((_QWORD *)this + 14)) != 0 && *v27 )
  {
    v37 = 260;
    v38 = (OLECHAR *)v39;
    XGrowable<wchar_t,260>::SetSize(&v37, 260);
    v28 = -1;
    v29 = -1;
    do
      ++v29;
    while ( (*v8)[v29] );
    do
      ++v28;
    while ( *(_WORD *)(*((_QWORD *)this + 14) + 2 * v28) );
    v30 = (unsigned int)(v29 + v28 + 2);
    XGrowable<wchar_t,260>::SetSize(&v37, v30);
    v31 = StringCchCopyW(v38, (unsigned int)v30, *((const wchar_t **)this + 14));
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
        (const char *)(unsigned int)v31,
        v34);
    v32 = StringCchCatW(v38, v30, L"\\");
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
        (const char *)(unsigned int)v32,
        v34);
    v33 = StringCchCatW(v38, v30, *v8);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E6,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
        (const char *)(unsigned int)v33,
        v34);
    v21 = SysAllocString(v38);
    *((_QWORD *)a2 + 7) = v21;
    if ( v38 != (OLECHAR *)v39 )
    {
      operator delete(v38);
      v21 = (BSTR)*((_QWORD *)a2 + 7);
    }
  }
  else
  {
    v21 = SysAllocString(*v8);
    *((_QWORD *)a2 + 7) = v21;
  }
  if ( !v21 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\cmdprutl.cxx",
      (const char *)0x8007000ELL,
      v34);
}

```

## disassembly

```asm
0x1800f4a60  mov     [rsp-8+arg_18], rbx
0x1800f4a65  push    rbp
0x1800f4a66  push    rsi
0x1800f4a67  push    rdi
0x1800f4a68  push    r14
0x1800f4a6a  push    r15
0x1800f4a6c  lea     rbp, [rsp-370h]
0x1800f4a74  sub     rsp, 470h
0x1800f4a7b  mov     rax, cs:__security_cookie
0x1800f4a82  xor     rax, rsp
0x1800f4a85  mov     [rbp+390h+var_30], rax
0x1800f4a8c  mov     rdi, rdx
0x1800f4a8f  mov     r14, rcx
0x1800f4a92  movups  xmm0, xmmword ptr [r8]
0x1800f4a96  movups  xmmword ptr [rdx], xmm0
0x1800f4a99  movups  xmm1, xmmword ptr [r8+10h]
0x1800f4a9e  movups  xmmword ptr [rdx+10h], xmm1
0x1800f4aa2  movups  xmm0, xmmword ptr [r8+20h]
0x1800f4aa7  movups  xmmword ptr [rdx+20h], xmm0
0x1800f4aab  xorps   xmm0, xmm0
0x1800f4aae  xor     eax, eax
0x1800f4ab0  movups  xmmword ptr [rdx+30h], xmm0
0x1800f4ab4  mov     [rdx+40h], rax
0x1800f4ab8  movzx   ecx, word ptr [r8+30h]
0x1800f4abd  lea     rsi, [r8+38h]
0x1800f4ac1  xor     r15d, r15d
0x1800f4ac4  bt      cx, 0Dh
0x1800f4ac9  jnb     short loc_1800F4AD8
0x1800f4acb  mov     rax, [rsi]
0x1800f4ace  cmp     [rax+18h], r15d
0x1800f4ad2  jbe     loc_1800F4C35
0x1800f4ad8  mov     edx, 3
0x1800f4add  sub     ecx, edx
0x1800f4adf  jz      loc_1800F4BA5
0x1800f4ae5  sub     ecx, 5
0x1800f4ae8  jz      loc_1802BEAE3
0x1800f4aee  sub     ecx, 0Bh
0x1800f4af1  jz      loc_1800F4BA5
0x1800f4af7  sub     ecx, 1FF0h
0x1800f4afd  jz      loc_1800F4CEC
0x1800f4b03  sub     ecx, 5
0x1800f4b06  jnz     loc_1800F4C6F
0x1800f4b0c  mov     rsi, [rsi]
0x1800f4b0f  cmp     word ptr [rsi], 1
0x1800f4b13  jnz     loc_1800F4CAE
0x1800f4b19  mov     rsi, [rsi+10h]
0x1800f4b1d  mov     word ptr [rdi+30h], 8
0x1800f4b23  cmp     [rbp+390h+arg_20], r15d
0x1800f4b2a  jnz     short loc_1800F4B68
0x1800f4b2c  mov     rcx, [rsi]; psz
0x1800f4b2f  call    cs:__imp_SysAllocString
0x1800f4b35  mov     [rdi+38h], rax
0x1800f4b39  test    rax, rax
0x1800f4b3c  jz      loc_1800F4CCD
0x1800f4b42  mov     rcx, [rbp+390h+var_30]
0x1800f4b49  xor     rcx, rsp; StackCookie
0x1800f4b4c  call    __security_check_cookie
0x1800f4b51  mov     rbx, [rsp+490h+arg_18]
0x1800f4b59  add     rsp, 470h
0x1800f4b60  pop     r15
0x1800f4b62  pop     r14
0x1800f4b64  pop     rdi
0x1800f4b65  pop     rsi
0x1800f4b66  pop     rbp
0x1800f4b67  retn
0x1800f4b68  mov     rcx, [r14+70h]
0x1800f4b6c  test    rcx, rcx
0x1800f4b6f  jz      short loc_1800F4B2C
0x1800f4b71  cmp     r15w, [rcx]
0x1800f4b75  jz      short loc_1800F4B2C
0x1800f4b77  mov     edx, 104h
0x1800f4b7c  mov     [rsp+490h+var_470], edx; int
0x1800f4b80  lea     rax, [rsp+490h+var_460]
0x1800f4b85  mov     [rsp+490h+psz], rax
0x1800f4b8a  lea     rcx, [rsp+490h+var_470]
0x1800f4b8f  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x1800f4b94  nop
0x1800f4b95  mov     rdx, [r14+70h]
0x1800f4b99  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f4b9d  mov     rcx, rax
0x1800f4ba0  jmp     loc_1802BEA14
0x1800f4ba5  mov     [rdi+30h], dx
0x1800f4ba9  mov     eax, [rsi]
0x1800f4bab  mov     [rdi+38h], eax
0x1800f4bae  jmp     short loc_1800F4B42
0x1800f4bb0  mov     rcx, [rsp+490h+psz]; psz
0x1800f4bb5  call    cs:__imp_SysAllocString
0x1800f4bbb  mov     [rdi+38h], rax
0x1800f4bbf  lea     rdx, [rsp+490h+var_460]
0x1800f4bc4  mov     rcx, [rsp+490h+psz]; Block
0x1800f4bc9  cmp     rcx, rdx
0x1800f4bcc  jz      loc_1800F4B39
0x1800f4bd2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f4bd7  mov     rax, [rdi+38h]
0x1800f4bdb  jmp     loc_1800F4B39
0x1800f4be0  mov     rcx, [rbp+390h+var_248]; psz
0x1800f4be7  call    cs:__imp_SysAllocString
0x1800f4bed  mov     [rdi+38h], rax
0x1800f4bf1  lea     rdx, [rbp+390h+var_240]
0x1800f4bf8  mov     rcx, [rbp+390h+var_248]; Block
0x1800f4bff  cmp     rcx, rdx
0x1800f4c02  jz      short loc_1800F4C0D
0x1800f4c04  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f4c09  mov     rax, [rdi+38h]
0x1800f4c0d  test    rax, rax
0x1800f4c10  jnz     loc_1800F4B42
0x1800f4c16  mov     rcx, [rbp+398h]; this
0x1800f4c1d  mov     r9d, 8007000Eh; char *
0x1800f4c23  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f4c2a  mov     edx, 1EEh; void *
0x1800f4c2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4c35  xor     r9d, r9d; wchar_t *
0x1800f4c38  lea     r8, aQueryCopydbpro; "[Query] CopyDbProp: index value out of "...
0x1800f4c3f  mov     edx, 1A2h; wchar_t *
0x1800f4c44  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f4c4b  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800f4c50  mov     rcx, [rbp+398h]; this
0x1800f4c57  mov     r9d, 0C000000Dh; char *
0x1800f4c5d  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f4c64  mov     edx, 1A3h; void *
0x1800f4c69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4c6f  cmp     ecx, 0Bh
0x1800f4c72  jz      short loc_1800F4CEC
0x1800f4c74  xor     r9d, r9d; wchar_t *
0x1800f4c77  lea     r8, aQueryCopydbpro_0; "[Query] CopyDbProp: Invalid VARIANT typ"...
0x1800f4c7e  mov     edx, 20Bh; wchar_t *
0x1800f4c83  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f4c8a  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800f4c8f  mov     rcx, [rbp+398h]; this
0x1800f4c96  mov     r9d, 0C000000Dh; char *
0x1800f4c9c  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f4ca3  mov     edx, 20Ch; void *
0x1800f4ca8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4cae  mov     rcx, [rbp+398h]; this
0x1800f4cb5  mov     r9d, 0C000000Dh; char *
0x1800f4cbb  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f4cc2  mov     edx, 1B1h; void *
0x1800f4cc7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4ccd  mov     rcx, [rbp+398h]; this
0x1800f4cd4  mov     r9d, 8007000Eh; char *
0x1800f4cda  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f4ce1  mov     edx, 1CDh; void *
0x1800f4ce6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4cec  mov     rax, [rsi]
0x1800f4cef  cmp     word ptr [rax], 1
0x1800f4cf3  jz      loc_1802BEAD4
0x1800f4cf9  mov     rcx, [rbp+398h]; this
0x1800f4d00  mov     r9d, 0C000000Dh; char *
0x1800f4d06  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f4d0d  mov     edx, 1FAh; void *
0x1800f4d12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802bea14  inc     rcx
0x1802bea17  cmp     [rdx+rcx*2], r15w
0x1802bea1c  jnz     short loc_1802BEA14
0x1802bea1e  mov     rdx, [rsi]
0x1802bea21  inc     rax
0x1802bea24  cmp     [rdx+rax*2], r15w
0x1802bea29  jnz     short loc_1802BEA21
0x1802bea2b  lea     ebx, [rax+2]
0x1802bea2e  add     ebx, ecx
0x1802bea30  mov     edx, ebx
0x1802bea32  lea     rcx, [rsp+490h+var_470]
0x1802bea37  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x1802bea3c  mov     r8, [r14+70h]; wchar_t *
0x1802bea40  mov     edx, ebx; unsigned __int64
0x1802bea42  mov     rcx, [rsp+490h+psz]; wchar_t *
0x1802bea47  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1802bea4c  test    eax, eax
0x1802bea4e  jns     short loc_1802BEA6C
0x1802bea50  mov     rcx, [rbp+398h]; this
0x1802bea57  mov     r9d, eax; char *
0x1802bea5a  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802bea61  mov     edx, 1BDh; void *
0x1802bea66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802bea6c  lea     r8, S; "\\"
0x1802bea73  mov     rdx, rbx; unsigned __int64
0x1802bea76  mov     rcx, [rsp+490h+psz]; wchar_t *
0x1802bea7b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1802bea80  test    eax, eax
0x1802bea82  jns     short loc_1802BEAA0
0x1802bea84  mov     rcx, [rbp+398h]; this
0x1802bea8b  mov     r9d, eax; char *
0x1802bea8e  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802bea95  mov     edx, 1C1h; void *
0x1802bea9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802beaa0  mov     r8, [rsi]; wchar_t *
0x1802beaa3  mov     rdx, rbx; unsigned __int64
0x1802beaa6  mov     rcx, [rsp+490h+psz]; wchar_t *
0x1802beaab  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1802beab0  test    eax, eax
0x1802beab2  jns     loc_1800F4BB0
0x1802beab8  mov     rcx, [rbp+398h]; this
0x1802beabf  mov     r9d, eax; char *
0x1802beac2  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802beac9  mov     edx, 1C5h; void *
0x1802beace  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802bead4  mov     rax, [rax+10h]
0x1802bead8  mov     [rdi+30h], dx
0x1802beadc  mov     eax, [rax]
0x1802beade  jmp     loc_1800F4BAB
0x1802beae3  mov     word ptr [rdi+30h], 8
0x1802beae9  cmp     [rbp+390h+arg_20], r15d
0x1802beaf0  jz      loc_1802BEC06
0x1802beaf6  mov     rcx, [r14+70h]
0x1802beafa  test    rcx, rcx
0x1802beafd  jz      loc_1802BEC06
0x1802beb03  cmp     r15w, [rcx]
0x1802beb07  jz      loc_1802BEC06
0x1802beb0d  mov     edx, 104h
0x1802beb12  mov     [rbp+390h+var_250], edx
0x1802beb18  lea     rax, [rbp+390h+var_240]
0x1802beb1f  mov     [rbp+390h+var_248], rax
0x1802beb26  lea     rcx, [rbp+390h+var_250]
0x1802beb2d  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x1802beb32  nop
0x1802beb33  mov     rdx, [rsi]
0x1802beb36  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802beb3a  mov     rcx, rax
0x1802beb3d  inc     rcx
0x1802beb40  cmp     [rdx+rcx*2], r15w
0x1802beb45  jnz     short loc_1802BEB3D
0x1802beb47  mov     rdx, [r14+70h]
0x1802beb4b  inc     rax
0x1802beb4e  cmp     [rdx+rax*2], r15w
0x1802beb53  jnz     short loc_1802BEB4B
0x1802beb55  lea     ebx, [rax+2]
0x1802beb58  add     ebx, ecx
0x1802beb5a  mov     edx, ebx
0x1802beb5c  lea     rcx, [rbp+390h+var_250]
0x1802beb63  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x1802beb68  mov     r8, [r14+70h]; wchar_t *
0x1802beb6c  mov     edx, ebx; unsigned __int64
0x1802beb6e  mov     rcx, [rbp+390h+var_248]; wchar_t *
0x1802beb75  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1802beb7a  test    eax, eax
0x1802beb7c  jns     short loc_1802BEB9A
0x1802beb7e  mov     rcx, [rbp+398h]; this
0x1802beb85  mov     r9d, eax; char *
0x1802beb88  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802beb8f  mov     edx, 1DEh; void *
0x1802beb94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802beb9a  lea     r8, S; "\\"
0x1802beba1  mov     rdx, rbx; unsigned __int64
0x1802beba4  mov     rcx, [rbp+390h+var_248]; wchar_t *
0x1802bebab  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1802bebb0  test    eax, eax
0x1802bebb2  jns     short loc_1802BEBD0
0x1802bebb4  mov     rcx, [rbp+398h]; this
0x1802bebbb  mov     r9d, eax; char *
0x1802bebbe  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802bebc5  mov     edx, 1E2h; void *
0x1802bebca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802bebd0  mov     r8, [rsi]; wchar_t *
0x1802bebd3  mov     rdx, rbx; unsigned __int64
0x1802bebd6  mov     rcx, [rbp+390h+var_248]; wchar_t *
0x1802bebdd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1802bebe2  test    eax, eax
0x1802bebe4  jns     loc_1800F4BE0
0x1802bebea  mov     rcx, [rbp+398h]; this
0x1802bebf1  mov     r9d, eax; char *
0x1802bebf4  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802bebfb  mov     edx, 1E6h; void *
0x1802bec00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802bec06  mov     rcx, [rsi]; psz
0x1802bec09  call    cs:__imp_SysAllocString
0x1802bec0f  mov     [rdi+38h], rax
0x1802bec13  jmp     loc_1800F4C0D
```
