# ipx::mtf::CMtfContextProp::Deserialize(IStream *)

- ea: `0x180010750`
- end: `0x180010c32`
- name: `?Deserialize@CMtfContextProp@mtf@ipx@@MEAAJPEAUIStream@@@Z`
- size: `1250`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfContextProp *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800046d4`
- `0x180006074`
- `0x180010688`
- `0x180010750`
- `0x1800113f0`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800109f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800109f9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800108d2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800109d1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800108d2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800109d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109f1`
- `OLEAUT32!__imp_SysStringLen` at `0x180010958`
- `OLEAUT32!__imp_SysStringLen` at `0x180010a57`
- `OLEAUT32!__imp_SysStringLen` at `0x180010958`
- `OLEAUT32!__imp_SysStringLen` at `0x180010a57`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ipx::mtf::CMtfContextProp::Deserialize(ipx::mtf::CMtfContextProp *this, struct IStream *a2)
{
  int v4; // eax
  const char *v5; // r9
  unsigned int v6; // ebx
  __int64 result; // rax
  char v8; // cl
  int v9; // edx
  _QWORD *v10; // rbx
  int v11; // eax
  unsigned int v12; // r14d
  int v13; // eax
  unsigned int v14; // ebx
  BSTR v15; // r15
  OLECHAR *v16; // r14
  DWORD LastError; // ebx
  int v18; // eax
  unsigned int v19; // ebx
  OLECHAR *v20; // rcx
  UINT v21; // eax
  int v22; // eax
  unsigned int v23; // ebx
  BSTR v24; // r15
  OLECHAR *v25; // r14
  DWORD v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  OLECHAR *v29; // rcx
  UINT v30; // eax
  int (*v31)(const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *, void **); // r14
  _QWORD *v32; // rbx
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // r14d
  int v36; // eax
  unsigned int v37; // r14d
  __int64 v38; // rcx
  int v39; // eax
  unsigned int v40; // esi
  __int64 v41; // rcx
  __int64 v42; // rcx
  int v43; // [rsp+20h] [rbp-68h]
  int v44; // [rsp+20h] [rbp-68h]
  UINT v45; // [rsp+30h] [rbp-58h] BYREF
  UINT ui; // [rsp+34h] [rbp-54h] BYREF
  __int64 v47; // [rsp+38h] [rbp-50h] BYREF
  __int128 v48; // [rsp+40h] [rbp-48h] BYREF
  __int128 v49; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  ipx::mtf::CMtfContextProp::Clear((ipx::mtf::CMtfContextProp *)((char *)this - 8));
  try
  {
    v48 = 0;
    v49 = 0;
    v4 = (*(__int64 (__fastcall **)(struct IStream *, __int128 *, __int64))(*(_QWORD *)a2 + 24LL))(a2, &v48, 32);
    v6 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
        (const char *)(unsigned int)v4,
        v43);
      return v6;
    }
    v8 = v49;
    *((_DWORD *)this + 4) = v49;
    *((_WORD *)this + 10) = WORD6(v49);
    v9 = DWORD1(v49);
    *((_DWORD *)this + 8) = DWORD1(v49);
    *(_OWORD *)((char *)this + 52) = v48;
    *((_DWORD *)this + 17) = DWORD2(v49);
    if ( (v8 & 2) != 0 )
    {
      v10 = (_QWORD *)((char *)this + 96);
      if ( v9 )
      {
        std::vector<unsigned long>::resize((char *)this + 96);
        v11 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
                a2,
                *v10,
                (unsigned int)(4 * *((_DWORD *)this + 8)),
                0);
        v12 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x128,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
            (const char *)(unsigned int)v11,
            v43);
          return v12;
        }
        *((_QWORD *)this + 3) = *v10;
      }
      else
      {
        *((_QWORD *)this + 13) = *((_QWORD *)this + 12);
        *((_QWORD *)this + 3) = 0;
        *((_DWORD *)this + 8) = 0;
      }
    }
    if ( (*((_BYTE *)this + 16) & 0x20) != 0 )
    {
      ui = 0;
      v13 = (*(__int64 (__fastcall **)(struct IStream *, UINT *, __int64))(*(_QWORD *)a2 + 24LL))(a2, &ui, 4);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x136,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          (const char *)(unsigned int)v13,
          v43);
        return v14;
      }
      v15 = SysAllocStringLen(0, ui);
      v16 = (OLECHAR *)*((_QWORD *)this + 16);
      if ( v16 )
      {
        LastError = GetLastError();
        SysFreeString(v16);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 16) = v15;
      v18 = (*(__int64 (__fastcall **)(struct IStream *, BSTR, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
              a2,
              v15,
              2 * ui,
              0);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          (const char *)(unsigned int)v18,
          v43);
        return v19;
      }
      v20 = (OLECHAR *)*((_QWORD *)this + 16);
      *((_QWORD *)this + 10) = v20;
      v21 = SysStringLen(v20);
      if ( ui != v21 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x13C,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          v5);
    }
    if ( (*((_BYTE *)this + 16) & 0x40) != 0 )
    {
      v45 = 0;
      v22 = (*(__int64 (__fastcall **)(struct IStream *, UINT *, __int64))(*(_QWORD *)a2 + 24LL))(a2, &v45, 4);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x141,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          (const char *)(unsigned int)v22,
          v43);
        return v23;
      }
      v24 = SysAllocStringLen(0, v45);
      v25 = (OLECHAR *)*((_QWORD *)this + 17);
      if ( v25 )
      {
        v26 = GetLastError();
        SysFreeString(v25);
        SetLastError(v26);
      }
      *((_QWORD *)this + 17) = v24;
      v27 = (*(__int64 (__fastcall **)(struct IStream *, BSTR, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
              a2,
              v24,
              2 * v45,
              0);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x144,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          (const char *)(unsigned int)v27,
          v43);
        return v28;
      }
      v29 = (OLECHAR *)*((_QWORD *)this + 17);
      *((_QWORD *)this + 11) = v29;
      v30 = SysStringLen(v29);
      if ( v45 != v30 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x147,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          v5);
    }
    if ( (*((_BYTE *)this + 16) & 0x10) != 0 )
    {
      v31 = Hooked_CoCreateInstance;
      v32 = (_QWORD *)((char *)this + 120);
      v33 = *((_QWORD *)this + 15);
      if ( v33 )
      {
        *v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v44 = (_DWORD)this + 120;
      v34 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *))v31)(
              &CLSID_MtfPropertyBag,
              0,
              1,
              &GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          (const char *)(unsigned int)v34,
          v44);
        return v35;
      }
      v47 = 0;
      v36 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v32)(
              *v32,
              &GUID_06445657_3a07_492d_94c3_052034ef2d12,
              &v47);
      v37 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x151,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          (const char *)(unsigned int)v36,
          v44);
        v38 = v47;
        v47 = 0;
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        return v37;
      }
      v39 = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*(_QWORD *)v47 + 40LL))(v47, a2);
      v40 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x153,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
          (const char *)(unsigned int)v39,
          v44);
        v41 = v47;
        v47 = 0;
        if ( v41 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        return v40;
      }
      *((_QWORD *)this + 9) = *v32;
      v42 = v47;
      v47 = 0;
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x159,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180010750  mov     [rsp+arg_10], rbx
0x180010755  mov     [rsp+arg_18], rsi
0x18001075a  push    rdi
0x18001075b  push    r14
0x18001075d  push    r15
0x18001075f  sub     rsp, 70h
0x180010763  mov     rax, cs:__security_cookie
0x18001076a  xor     rax, rsp
0x18001076d  mov     [rsp+88h+var_28], rax
0x180010772  mov     rsi, rdx
0x180010775  mov     rdi, rcx
0x180010778  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18001077c  call    ?Clear@CMtfContextProp@mtf@ipx@@IEAAXXZ; ipx::mtf::CMtfContextProp::Clear(void)
0x180010781  xorps   xmm0, xmm0
0x180010784  movups  [rsp+88h+var_48], xmm0
0x180010789  movups  [rsp+88h+var_38], xmm0
0x18001078e  mov     rax, [rsi]
0x180010791  xor     r9d, r9d
0x180010794  lea     r8d, [r9+20h]
0x180010798  lea     rdx, [rsp+88h+var_48]
0x18001079d  mov     rcx, rsi
0x1800107a0  mov     rax, [rax+18h]
0x1800107a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107a9  mov     ebx, eax
0x1800107ab  test    eax, eax
0x1800107ad  jns     short loc_1800107D2
0x1800107af  mov     rcx, [rsp+88h]; this
0x1800107b7  mov     r9d, eax; char *
0x1800107ba  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x1800107c1  mov     edx, 118h; void *
0x1800107c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107cb  mov     eax, ebx
0x1800107cd  jmp     loc_180010BEA
0x1800107d2  mov     ecx, dword ptr [rsp+88h+var_38]
0x1800107d6  mov     [rdi+10h], ecx
0x1800107d9  movzx   eax, word ptr [rsp+88h+var_38+0Ch]
0x1800107de  mov     [rdi+14h], ax
0x1800107e2  mov     edx, dword ptr [rsp+88h+var_38+4]
0x1800107e6  mov     [rdi+20h], edx
0x1800107e9  movups  xmm0, [rsp+88h+var_48]
0x1800107ee  movdqu  xmmword ptr [rdi+34h], xmm0
0x1800107f3  mov     eax, dword ptr [rsp+88h+var_38+8]
0x1800107f7  mov     [rdi+44h], eax
0x1800107fa  test    cl, 2
0x1800107fd  jz      short loc_180010876
0x1800107ff  lea     rbx, [rdi+60h]
0x180010803  test    edx, edx
0x180010805  jz      short loc_180010860
0x180010807  mov     rcx, rbx
0x18001080a  call    ?resize@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::resize(unsigned __int64)
0x18001080f  mov     rax, [rsi]
0x180010812  mov     r8d, [rdi+20h]
0x180010816  shl     r8d, 2
0x18001081a  xor     r9d, r9d
0x18001081d  mov     rdx, [rbx]
0x180010820  mov     rcx, rsi
0x180010823  mov     rax, [rax+18h]
0x180010827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001082c  mov     r14d, eax
0x18001082f  test    eax, eax
0x180010831  jns     short loc_180010857
0x180010833  mov     rcx, [rsp+88h]; this
0x18001083b  mov     r9d, eax; char *
0x18001083e  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x180010845  mov     edx, 128h; void *
0x18001084a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001084f  mov     eax, r14d
0x180010852  jmp     loc_180010BEA
0x180010857  mov     rax, [rbx]
0x18001085a  mov     [rdi+18h], rax
0x18001085e  jmp     short loc_180010876
0x180010860  mov     rax, [rbx]
0x180010863  mov     [rbx+8], rax
0x180010867  mov     qword ptr [rdi+18h], 0
0x18001086f  mov     dword ptr [rdi+20h], 0
0x180010876  test    byte ptr [rdi+10h], 20h
0x18001087a  jz      loc_180010975
0x180010880  mov     [rsp+88h+ui], 0
0x180010888  mov     rax, [rsi]
0x18001088b  xor     r9d, r9d
0x18001088e  lea     r8d, [r9+4]
0x180010892  lea     rdx, [rsp+88h+ui]
0x180010897  mov     rcx, rsi
0x18001089a  mov     rax, [rax+18h]
0x18001089e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a3  mov     ebx, eax
0x1800108a5  test    eax, eax
0x1800108a7  jns     short loc_1800108CC
0x1800108a9  mov     rcx, [rsp+88h]; this
0x1800108b1  mov     r9d, eax; char *
0x1800108b4  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x1800108bb  mov     edx, 136h; void *
0x1800108c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800108c5  mov     eax, ebx
0x1800108c7  jmp     loc_180010BEA
0x1800108cc  mov     edx, [rsp+88h+ui]; ui
0x1800108d0  xor     ecx, ecx; strIn
0x1800108d2  call    cs:__imp_SysAllocStringLen
0x1800108d8  mov     r15, rax
0x1800108db  mov     r14, [rdi+80h]
0x1800108e2  test    r14, r14
0x1800108e5  jz      short loc_180010900
0x1800108e7  call    cs:__imp_GetLastError
0x1800108ed  mov     ebx, eax
0x1800108ef  mov     rcx, r14; bstrString
0x1800108f2  call    cs:__imp_SysFreeString
0x1800108f8  mov     ecx, ebx; dwErrCode
0x1800108fa  call    cs:__imp_SetLastError
0x180010900  mov     [rdi+80h], r15
0x180010907  mov     rcx, [rsi]
0x18001090a  mov     r8d, [rsp+88h+ui]
0x18001090f  add     r8d, r8d
0x180010912  mov     rax, [rcx+18h]
0x180010916  xor     r9d, r9d
0x180010919  mov     rdx, r15
0x18001091c  mov     rcx, rsi
0x18001091f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010924  mov     ebx, eax
0x180010926  test    eax, eax
0x180010928  jns     short loc_18001094D
0x18001092a  mov     rcx, [rsp+88h]; this
0x180010932  mov     r9d, eax; char *
0x180010935  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x18001093c  mov     edx, 139h; void *
0x180010941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010946  mov     eax, ebx
0x180010948  jmp     loc_180010BEA
0x18001094d  mov     rcx, [rdi+80h]; pbstr
0x180010954  mov     [rdi+50h], rcx
0x180010958  call    cs:__imp_SysStringLen
0x18001095e  cmp     [rsp+88h+ui], eax
0x180010962  setz    al
0x180010965  mov     rcx, [rsp+88h]; this
0x18001096d  test    al, al
0x18001096f  jz      loc_180010C0D
0x180010975  test    byte ptr [rdi+10h], 40h
0x180010979  jz      loc_180010A74
0x18001097f  mov     [rsp+88h+var_58], 0
0x180010987  mov     rax, [rsi]
0x18001098a  xor     r9d, r9d
0x18001098d  lea     r8d, [r9+4]
0x180010991  lea     rdx, [rsp+88h+var_58]
0x180010996  mov     rcx, rsi
0x180010999  mov     rax, [rax+18h]
0x18001099d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a2  mov     ebx, eax
0x1800109a4  test    eax, eax
0x1800109a6  jns     short loc_1800109CB
0x1800109a8  mov     rcx, [rsp+88h]; this
0x1800109b0  mov     r9d, eax; char *
0x1800109b3  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x1800109ba  mov     edx, 141h; void *
0x1800109bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109c4  mov     eax, ebx
0x1800109c6  jmp     loc_180010BEA
0x1800109cb  mov     edx, [rsp+88h+var_58]; ui
0x1800109cf  xor     ecx, ecx; strIn
0x1800109d1  call    cs:__imp_SysAllocStringLen
0x1800109d7  mov     r15, rax
0x1800109da  mov     r14, [rdi+88h]
0x1800109e1  test    r14, r14
0x1800109e4  jz      short loc_1800109FF
0x1800109e6  call    cs:__imp_GetLastError
0x1800109ec  mov     ebx, eax
0x1800109ee  mov     rcx, r14; bstrString
0x1800109f1  call    cs:__imp_SysFreeString
0x1800109f7  mov     ecx, ebx; dwErrCode
0x1800109f9  call    cs:__imp_SetLastError
0x1800109ff  mov     [rdi+88h], r15
0x180010a06  mov     rcx, [rsi]
0x180010a09  mov     r8d, [rsp+88h+var_58]
0x180010a0e  add     r8d, r8d
0x180010a11  mov     rax, [rcx+18h]
0x180010a15  xor     r9d, r9d
0x180010a18  mov     rdx, r15
0x180010a1b  mov     rcx, rsi
0x180010a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a23  mov     ebx, eax
0x180010a25  test    eax, eax
0x180010a27  jns     short loc_180010A4C
0x180010a29  mov     rcx, [rsp+88h]; this
0x180010a31  mov     r9d, eax; char *
0x180010a34  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x180010a3b  mov     edx, 144h; void *
0x180010a40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a45  mov     eax, ebx
0x180010a47  jmp     loc_180010BEA
0x180010a4c  mov     rcx, [rdi+88h]; pbstr
0x180010a53  mov     [rdi+58h], rcx
0x180010a57  call    cs:__imp_SysStringLen
0x180010a5d  cmp     [rsp+88h+var_58], eax
0x180010a61  setz    al
0x180010a64  mov     rcx, [rsp+88h]; this
0x180010a6c  test    al, al
0x180010a6e  jz      loc_180010C1F
0x180010a74  test    byte ptr [rdi+10h], 10h
0x180010a78  jz      loc_180010BE2
0x180010a7e  mov     r14, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180010a85  lea     rbx, [rdi+78h]
0x180010a89  mov     rcx, [rbx]
0x180010a8c  test    rcx, rcx
0x180010a8f  jz      short loc_180010AA5
0x180010a91  mov     qword ptr [rbx], 0
0x180010a98  mov     rax, [rcx]
0x180010a9b  mov     rax, [rax+10h]
0x180010a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aa4  nop
0x180010aa5  mov     qword ptr [rsp+88h+var_68], rbx; int
0x180010aaa  lea     r9, _GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5
0x180010ab1  xor     edx, edx
0x180010ab3  lea     r8d, [rdx+1]
0x180010ab7  lea     rcx, CLSID_MtfPropertyBag
0x180010abe  mov     rax, r14
0x180010ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac6  mov     r14d, eax
0x180010ac9  test    eax, eax
0x180010acb  jns     short loc_180010AF1
0x180010acd  mov     rcx, [rsp+88h]; this
0x180010ad5  mov     r9d, eax; char *
0x180010ad8  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x180010adf  mov     edx, 14Eh; void *
0x180010ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ae9  mov     eax, r14d
0x180010aec  jmp     loc_180010BEA
0x180010af1  mov     [rsp+88h+var_50], 0
0x180010afa  mov     rcx, [rbx]
0x180010afd  mov     rax, [rcx]
0x180010b00  lea     r8, [rsp+88h+var_50]
0x180010b05  lea     rdx, _GUID_06445657_3a07_492d_94c3_052034ef2d12
0x180010b0c  mov     rax, [rax]
0x180010b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b14  mov     r14d, eax
0x180010b17  test    eax, eax
0x180010b19  jns     short loc_180010B60
0x180010b1b  mov     rcx, [rsp+88h]; this
0x180010b23  mov     r9d, eax; char *
0x180010b26  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x180010b2d  mov     edx, 151h; void *
0x180010b32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b37  nop
0x180010b38  mov     rcx, [rsp+88h+var_50]
0x180010b3d  mov     [rsp+88h+var_50], 0
0x180010b46  test    rcx, rcx
0x180010b49  jz      short loc_180010B58
0x180010b4b  mov     rax, [rcx]
0x180010b4e  mov     rax, [rax+10h]
0x180010b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b57  nop
0x180010b58  mov     eax, r14d
0x180010b5b  jmp     loc_180010BEA
0x180010b60  mov     rcx, [rsp+88h+var_50]
0x180010b65  mov     rax, [rcx]
0x180010b68  mov     rdx, rsi
0x180010b6b  mov     rax, [rax+28h]
0x180010b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b74  mov     esi, eax
0x180010b76  test    eax, eax
0x180010b78  jns     short loc_180010BBB
0x180010b7a  mov     rcx, [rsp+88h]; this
0x180010b82  mov     r9d, eax; char *
0x180010b85  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x180010b8c  mov     edx, 153h; void *
0x180010b91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b96  nop
0x180010b97  mov     rcx, [rsp+88h+var_50]
0x180010b9c  mov     [rsp+88h+var_50], 0
0x180010ba5  test    rcx, rcx
0x180010ba8  jz      short loc_180010BB7
0x180010baa  mov     rax, [rcx]
0x180010bad  mov     rax, [rax+10h]
0x180010bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bb6  nop
0x180010bb7  mov     eax, esi
0x180010bb9  jmp     short loc_180010BEA
0x180010bbb  mov     rax, [rbx]
0x180010bbe  mov     [rdi+48h], rax
0x180010bc2  mov     rcx, [rsp+88h+var_50]
0x180010bc7  mov     [rsp+88h+var_50], 0
0x180010bd0  test    rcx, rcx
0x180010bd3  jz      short loc_180010BE2
0x180010bd5  mov     rax, [rcx]
0x180010bd8  mov     rax, [rax+10h]
0x180010bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be1  nop
0x180010be2  xor     eax, eax
0x180010be4  jmp     short loc_180010BEA
0x180010be6  mov     eax, [rsp+88h+var_58]
0x180010bea  mov     rcx, [rsp+88h+var_28]
0x180010bef  xor     rcx, rsp; StackCookie
0x180010bf2  call    __security_check_cookie
0x180010bf7  lea     r11, [rsp+88h+var_18]
0x180010bfc  mov     rbx, [r11+30h]
0x180010c00  mov     rsi, [r11+38h]
0x180010c04  mov     rsp, r11
0x180010c07  pop     r15
0x180010c09  pop     r14
0x180010c0b  pop     rdi
0x180010c0c  retn
0x180010c0d  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x180010c14  mov     edx, 13Ch; void *
  ... truncated ...
```
