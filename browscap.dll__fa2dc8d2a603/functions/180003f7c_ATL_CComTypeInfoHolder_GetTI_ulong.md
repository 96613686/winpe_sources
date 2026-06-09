# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180003f7c`
- end: `0x180004320`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `932`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004330`
- `0x18000833c`
- `0x18000851c`

## callees

- `0x1800021e0`
- `0x180003750`
- `0x1800037f4`
- `0x180003f7c`
- `0x1800045b4`
- `0x180007034`
- `0x18000b640`
- `0x18000b700`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x180004178`
- `msvcrt!free` at `0x18000418d`
- `msvcrt!free` at `0x180004178`
- `msvcrt!free` at `0x18000418d`
- `msvcrt!malloc` at `0x180004117`
- `msvcrt!malloc` at `0x180004117`
- `KERNEL32!MultiByteToWideChar` at `0x180004157`
- `KERNEL32!MultiByteToWideChar` at `0x180004157`
- `KERNEL32!LeaveCriticalSection` at `0x18000419b`
- `KERNEL32!LeaveCriticalSection` at `0x1800042e4`
- `KERNEL32!LeaveCriticalSection` at `0x18000419b`
- `KERNEL32!LeaveCriticalSection` at `0x1800042e4`
- `KERNEL32!EnterCriticalSection` at `0x180003fdb`
- `KERNEL32!EnterCriticalSection` at `0x180003fdb`
- `KERNEL32!GetModuleFileNameA` at `0x18000407b`
- `KERNEL32!GetModuleFileNameA` at `0x18000407b`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180004168`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180004168`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800041b7`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800041b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  ATL::CComTypeInfoHolder *v5; // rcx
  HRESULT NameCache; // edi
  DWORD ModuleFileNameA; // eax
  _QWORD *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rdi
  __int64 v12; // rax
  void *v13; // rsp
  WCHAR *lpWideCharStr; // rsi
  _QWORD *v15; // rax
  void *v16; // rcx
  void *v17; // rcx
  int (__fastcall ***v18)(_QWORD, GUID *, _QWORD *); // rcx
  unsigned __int64 v19; // r8
  struct ITypeInfo *v20; // rax
  WCHAR WideCharStr[4]; // [rsp+30h] [rbp+0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp+8h] BYREF
  int (__fastcall ***v23)(_QWORD, GUID *, _QWORD *); // [rsp+40h] [rbp+10h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp+18h] BYREF
  char v25; // [rsp+58h] [rbp+28h]
  CHAR Filename[272]; // [rsp+60h] [rbp+30h] BYREF

  if ( qword_1800120A8 && qword_1800120B8 )
    return 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  v24[1] = (char *)ATL::_pAtlModule + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v25 = 1;
  if ( qword_1800120A8 )
  {
    NameCache = 0;
  }
  else
  {
    pptlib = 0;
    if ( ATL::CAtlModule::m_libid.Data1 != rguid->Data1
      || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)&rguid->Data2
      || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)rguid->Data4
      || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)&rguid->Data4[4]
      || *(_DWORD *)&wVerMajor != -1 )
    {
      NameCache = LoadRegTypeLib(rguid, wVerMajor, *(&wVerMajor + 1), a2, &pptlib);
LABEL_35:
      if ( NameCache >= 0 )
      {
        v23 = 0;
        NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                      pptlib,
                      ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::_tih[0],
                      &v23);
        if ( NameCache >= 0 )
        {
          v18 = v23;
          *(_QWORD *)WideCharStr = v23;
          if ( v23 )
          {
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v23)[1])(v23);
            v18 = v23;
          }
          v24[0] = 0;
          if ( (**v18)(v18, &GUID_00020412_0000_0000_c000_000000000046, v24) >= 0 )
            ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(WideCharStr, v24);
          v20 = *(struct ITypeInfo **)WideCharStr;
          *(_QWORD *)WideCharStr = 0;
          qword_1800120A8 = v20;
          ATL::AtlModuleAddTermFunc(
            (struct ATL::_ATL_MODULE70 *)(((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0)),
            (void (*)(unsigned __int64))((char *)ATL::_pAtlModule + 8),
            v19);
          if ( v24[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v24[0] + 16LL))(v24[0]);
          if ( *(_QWORD *)WideCharStr )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)WideCharStr + 16LL))(*(_QWORD *)WideCharStr);
        }
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        v5 = (ATL::CComTypeInfoHolder *)v23;
        if ( v23 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v23)[2])(v23);
      }
      goto LABEL_49;
    }
    NameCache = -2147467259;
    ModuleFileNameA = GetModuleFileNameA(hModule, Filename, 0x104u);
    if ( ModuleFileNameA && ModuleFileNameA != 260 )
    {
      v8 = 0;
      v24[0] = 0;
      v9 = -1;
      do
        ++v9;
      while ( Filename[v9] );
      v10 = 2LL * ((int)v9 + 1);
      if ( (unsigned __int64)(v10 + 0x80000000LL) > 0xFFFFFFFF )
        goto LABEL_32;
      v11 = (int)v10;
      if ( (int)v10 <= 1024
        && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)v10, 0xFFFFFFFF) )
      {
        v12 = v11 + 15;
        if ( v11 + 15 < v11 )
          v12 = 0xFFFFFFFFFFFFFF0LL;
        v13 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
        lpWideCharStr = WideCharStr;
      }
      else
      {
        if ( ~v11 < 0x10 )
          ATL::AtlThrowImpl(-2147024809);
        v15 = malloc(v11 + 16);
        if ( v15 )
        {
          *v15 = 0;
          v8 = v15;
          lpWideCharStr = (WCHAR *)(v15 + 2);
        }
        else
        {
          lpWideCharStr = 0;
        }
      }
      if ( !lpWideCharStr || (*lpWideCharStr = 0, !MultiByteToWideChar(3u, 0, Filename, -1, lpWideCharStr, v11 >> 1)) )
      {
LABEL_32:
        while ( v8 )
        {
          v17 = v8;
          v8 = (_QWORD *)*v8;
          free(v17);
        }
        LeaveCriticalSection(v4);
        return 2147942414LL;
      }
      NameCache = LoadTypeLib(lpWideCharStr, &pptlib);
      while ( v8 )
      {
        v16 = v8;
        v8 = (_QWORD *)*v8;
        free(v16);
      }
      goto LABEL_35;
    }
  }
LABEL_49:
  if ( qword_1800120A8 )
  {
    if ( !qword_1800120B8 )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v5, qword_1800120A8);
  }
  LeaveCriticalSection(v4);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180003f7c  push    rbp
0x180003f7e  push    rdi
0x180003f7f  push    r14
0x180003f81  sub     rsp, 180h
0x180003f88  lea     rbp, [rsp+30h]
0x180003f8d  mov     [rbp+160h+arg_0], rbx
0x180003f94  mov     [rbp+160h+arg_10], rsi
0x180003f9b  mov     rax, cs:__security_cookie
0x180003fa2  xor     rax, rbp
0x180003fa5  mov     [rbp+160h+var_20], rax
0x180003fac  mov     ebx, edx
0x180003fae  cmp     cs:qword_1800120A8, 0
0x180003fb6  jz      short loc_180003FC9
0x180003fb8  cmp     cs:qword_1800120B8, 0
0x180003fc0  jz      short loc_180003FC9
0x180003fc2  xor     eax, eax
0x180003fc4  jmp     loc_1800042EC
0x180003fc9  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003fd0  add     r14, 18h
0x180003fd4  mov     [rbp+160h+var_140], r14
0x180003fd8  mov     rcx, r14; lpCriticalSection
0x180003fdb  call    cs:__imp_EnterCriticalSection
0x180003fe1  mov     [rbp+160h+var_138], 1
0x180003fe5  cmp     cs:qword_1800120A8, 0
0x180003fed  jnz     loc_1800042C2
0x180003ff3  mov     [rbp+160h+pptlib], 0
0x180003ffb  mov     r8, cs:wVerMajor+2; wVerMinor
0x180004002  mov     rdx, cs:wVerMajor; wVerMajor
0x180004009  mov     rcx, cs:rguid; rguid
0x180004010  mov     eax, [rcx]
0x180004012  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x180004018  jnz     loc_1800041AB
0x18000401e  mov     eax, [rcx+4]
0x180004021  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x180004027  jnz     loc_1800041AB
0x18000402d  mov     eax, [rcx+8]
0x180004030  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180004036  jnz     loc_1800041AB
0x18000403c  mov     eax, [rcx+0Ch]
0x18000403f  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180004045  jnz     loc_1800041AB
0x18000404b  mov     eax, 0FFFFh
0x180004050  cmp     dx, ax
0x180004053  jnz     loc_1800041AB
0x180004059  cmp     r8w, ax
0x18000405d  jnz     loc_1800041AB
0x180004063  mov     edi, 80004005h
0x180004068  mov     ebx, 104h
0x18000406d  mov     r8d, ebx; nSize
0x180004070  lea     rdx, [rbp+160h+Filename]; lpFilename
0x180004074  mov     rcx, cs:hModule; hModule
0x18000407b  call    cs:__imp_GetModuleFileNameA
0x180004081  test    eax, eax
0x180004083  jz      loc_1800042C4
0x180004089  cmp     eax, ebx
0x18000408b  jz      loc_1800042C4
0x180004091  xor     ebx, ebx
0x180004093  mov     [rbp+160h+var_148], rbx
0x180004097  lea     rcx, [rbp+160h+Filename]
0x18000409b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000409f  inc     rax
0x1800040a2  cmp     byte ptr [rcx+rax], 0
0x1800040a6  jnz     short loc_18000409F
0x1800040a8  inc     eax
0x1800040aa  movsxd  rcx, eax
0x1800040ad  add     rcx, rcx
0x1800040b0  mov     eax, 80000000h
0x1800040b5  add     rax, rcx
0x1800040b8  mov     edx, 0FFFFFFFFh; unsigned __int64
0x1800040bd  cmp     rax, rdx
0x1800040c0  ja      loc_180004185
0x1800040c6  movsxd  rdi, ecx
0x1800040c9  cmp     ecx, 400h
0x1800040cf  jg      short loc_180004103
0x1800040d1  mov     rcx, rdi; this
0x1800040d4  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800040d9  test    al, al
0x1800040db  jz      short loc_180004103
0x1800040dd  lea     rax, [rdi+0Fh]
0x1800040e1  cmp     rax, rdi
0x1800040e4  ja      short loc_1800040F0
0x1800040e6  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800040f0  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800040f4  call    _alloca_probe
0x1800040f9  sub     rsp, rax
0x1800040fc  lea     rsi, [rsp+190h+WideCharStr]
0x180004101  jmp     short loc_180004134
0x180004103  mov     rax, rdi
0x180004106  not     rax
0x180004109  cmp     rax, 10h
0x18000410d  jb      loc_180004315
0x180004113  lea     rcx, [rdi+10h]; Size
0x180004117  call    cs:__imp_malloc
0x18000411d  test    rax, rax
0x180004120  jnz     short loc_180004126
0x180004122  xor     esi, esi
0x180004124  jmp     short loc_180004134
0x180004126  mov     qword ptr [rax], 0
0x18000412d  mov     rbx, rax
0x180004130  lea     rsi, [rax+10h]
0x180004134  test    rsi, rsi
0x180004137  jz      short loc_180004185
0x180004139  xor     eax, eax
0x18000413b  mov     [rsi], ax
0x18000413e  shr     rdi, 1
0x180004141  mov     [rsp+190h+cchWideChar], edi; cchWideChar
0x180004145  mov     [rsp+190h+lpWideCharStr], rsi; lpWideCharStr
0x18000414a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000414e  lea     r8, [rbp+160h+Filename]; lpMultiByteStr
0x180004152  xor     edx, edx; dwFlags
0x180004154  lea     ecx, [rax+3]; CodePage
0x180004157  call    cs:__imp_MultiByteToWideChar
0x18000415d  test    eax, eax
0x18000415f  jz      short loc_180004185
0x180004161  lea     rdx, [rbp+160h+pptlib]; pptlib
0x180004165  mov     rcx, rsi; szFile
0x180004168  call    cs:__imp_LoadTypeLib
0x18000416e  mov     edi, eax
0x180004170  jmp     short loc_18000417E
0x180004172  mov     rcx, rbx; Block
0x180004175  mov     rbx, [rbx]
0x180004178  call    cs:__imp_free
0x18000417e  test    rbx, rbx
0x180004181  jnz     short loc_180004172
0x180004183  jmp     short loc_1800041BF
0x180004185  jmp     short loc_180004193
0x180004187  mov     rcx, rbx; Block
0x18000418a  mov     rbx, [rbx]
0x18000418d  call    cs:__imp_free
0x180004193  test    rbx, rbx
0x180004196  jnz     short loc_180004187
0x180004198  mov     rcx, r14; lpCriticalSection
0x18000419b  call    cs:__imp_LeaveCriticalSection
0x1800041a1  mov     eax, 8007000Eh
0x1800041a6  jmp     loc_1800042EC
0x1800041ab  lea     rax, [rbp+160h+pptlib]
0x1800041af  mov     [rsp+190h+lpWideCharStr], rax; pptlib
0x1800041b4  mov     r9d, ebx; lcid
0x1800041b7  call    cs:__imp_LoadRegTypeLib
0x1800041bd  mov     edi, eax
0x1800041bf  test    edi, edi
0x1800041c1  js      loc_1800042C4
0x1800041c7  mov     [rbp+160h+var_150], 0
0x1800041cf  mov     rcx, [rbp+160h+pptlib]
0x1800041d3  mov     rax, [rcx]
0x1800041d6  lea     r8, [rbp+160h+var_150]
0x1800041da  mov     rdx, cs:?_tih@?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::_tih
0x1800041e1  mov     rax, [rax+30h]
0x1800041e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ea  mov     edi, eax
0x1800041ec  test    eax, eax
0x1800041ee  js      loc_180004299
0x1800041f4  mov     rcx, [rbp+160h+var_150]
0x1800041f8  mov     qword ptr [rbp+160h+WideCharStr], rcx
0x1800041fc  test    rcx, rcx
0x1800041ff  jz      short loc_180004211
0x180004201  mov     rax, [rcx]
0x180004204  mov     rax, [rax+8]
0x180004208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420d  mov     rcx, [rbp+160h+var_150]
0x180004211  mov     [rbp+160h+var_148], 0
0x180004219  mov     rax, [rcx]
0x18000421c  lea     r8, [rbp+160h+var_148]
0x180004220  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180004227  mov     rax, [rax]
0x18000422a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000422f  test    eax, eax
0x180004231  js      short loc_180004240
0x180004233  lea     rdx, [rbp+160h+var_148]
0x180004237  lea     rcx, [rbp+160h+WideCharStr]
0x18000423b  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x180004240  mov     rax, qword ptr [rbp+160h+WideCharStr]
0x180004244  mov     qword ptr [rbp+160h+WideCharStr], 0
0x18000424c  mov     cs:qword_1800120A8, rax
0x180004253  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000425a  lea     rdx, [rax+8]; void (*)(unsigned __int64)
0x18000425e  neg     rax
0x180004261  sbb     rcx, rcx
0x180004264  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180004267  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x18000426c  nop
0x18000426d  mov     rcx, [rbp+160h+var_148]
0x180004271  test    rcx, rcx
0x180004274  jz      short loc_180004283
0x180004276  mov     rax, [rcx]
0x180004279  mov     rax, [rax+10h]
0x18000427d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004282  nop
0x180004283  mov     rcx, qword ptr [rbp+160h+WideCharStr]
0x180004287  test    rcx, rcx
0x18000428a  jz      short loc_180004299
0x18000428c  mov     rax, [rcx]
0x18000428f  mov     rax, [rax+10h]
0x180004293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004298  nop
0x180004299  mov     rcx, [rbp+160h+pptlib]
0x18000429d  mov     rax, [rcx]
0x1800042a0  mov     rax, [rax+10h]
0x1800042a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a9  nop
0x1800042aa  mov     rcx, [rbp+160h+var_150]
0x1800042ae  test    rcx, rcx
0x1800042b1  jz      short loc_1800042C0
0x1800042b3  mov     rax, [rcx]
0x1800042b6  mov     rax, [rax+10h]
0x1800042ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042bf  nop
0x1800042c0  jmp     short loc_1800042C4
0x1800042c2  xor     edi, edi
0x1800042c4  mov     rdx, cs:qword_1800120A8; struct ITypeInfo *
0x1800042cb  test    rdx, rdx
0x1800042ce  jz      short loc_1800042E1
0x1800042d0  cmp     cs:qword_1800120B8, 0
0x1800042d8  jnz     short loc_1800042E1
0x1800042da  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x1800042df  mov     edi, eax
0x1800042e1  mov     rcx, r14; lpCriticalSection
0x1800042e4  call    cs:__imp_LeaveCriticalSection
0x1800042ea  mov     eax, edi
0x1800042ec  mov     rcx, [rbp+160h+var_20]
0x1800042f3  xor     rcx, rbp; StackCookie
0x1800042f6  call    __security_check_cookie
0x1800042fb  mov     rbx, [rbp+160h+arg_0]
0x180004302  mov     rsi, [rbp+160h+arg_10]
0x180004309  lea     rsp, [rbp+150h]
0x180004310  pop     r14
0x180004312  pop     rdi
0x180004313  pop     rbp
0x180004314  retn
0x180004315  mov     ecx, 80070057h; int
0x18000431a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
