# mlib::XmlDOM::LoadDocumentFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMDocument2 * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)

- ea: `0x1400555ac`
- end: `0x1400557eb`
- name: `?LoadDocumentFromFile@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMDocument2@@PEAV32@_N@Z`
- size: `575`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140011458`
- `0x14001e7a8`
- `0x14004cec0`

## callees

- `0x140002f80`
- `0x140002ff0`
- `0x14000712c`
- `0x14003ad18`
- `0x140055054`
- `0x1400555ac`
- `0x1400557f4`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140055689`
- `OLEAUT32!__imp_SysAllocString` at `0x140055689`
- `OLEAUT32!__imp_VariantInit` at `0x140055665`
- `OLEAUT32!__imp_VariantInit` at `0x140055665`
- `OLEAUT32!__imp_VariantClear` at `0x140055677`
- `OLEAUT32!__imp_VariantClear` at `0x140055721`
- `OLEAUT32!__imp_VariantClear` at `0x1400557b0`
- `OLEAUT32!__imp_VariantClear` at `0x140055677`
- `OLEAUT32!__imp_VariantClear` at `0x140055721`
- `OLEAUT32!__imp_VariantClear` at `0x1400557b0`
- `ole32!CoCreateInstance` at `0x140055653`
- `ole32!CoCreateInstance` at `0x140055653`

## string_xrefs

- `0x14005570f`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055764`: `base\winsat\mlib\mxmldom.cpp`
- `0x1400556ee`: `cannot create an IXMLDOMDocument2 document`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall mlib::XmlDOM::LoadDocumentFromFile(__int64 a1, char *a2)
{
  const OLECHAR *v4; // rdi
  int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  LPVOID v9; // rax
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG v12; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp+40h] BYREF
  __int16 v14; // [rsp+C8h] [rbp+48h] BYREF

  ppv = 0;
  v14 = 0;
  if ( dword_1401CBCC0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1401CBCC0);
    if ( dword_1401CBCC0 == -1 )
    {
      byte_1401CBCBC = *a2;
      Init_thread_footer(&dword_1401CBCC0);
    }
  }
  *(_QWORD *)a2 = 0;
  if ( mlib::XmlDOM::Init()
    && CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv) >= 0 )
  {
    VariantInit(&pvarg);
    v4 = *(const OLECHAR **)(*(_QWORD *)a1 + 24LL);
    VariantClear(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(v4);
    if ( !pvarg.llVal )
    {
      if ( v4 )
      {
        pvarg.vt = 10;
        pvarg.lVal = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
      }
    }
    v12 = pvarg;
    v5 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)ppv + 464LL))(ppv, &v12, &v14);
    if ( v5 >= 0 )
    {
      if ( v14 )
      {
        v8 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
        if ( v8 >= 0 )
        {
          v9 = ppv;
          ppv = 0;
          *(_QWORD *)a2 = v9;
          VariantClear(&pvarg);
          ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&ppv);
          return 0;
        }
        v6 = mlib::XmlDOM::ReportCOMError_w(
               (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
               246,
               v8,
               (_DWORD)ppv,
               (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               0,
               (__int64)L"cannot set the 'preserve white space' flag");
      }
      else
      {
        v6 = mlib::XmlDOM::ReportCOMError_w(
               (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
               235,
               -2147467259,
               (_DWORD)ppv,
               (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               0,
               (__int64)L"cannot load document from file '%s'",
               *(_QWORD *)(*(_QWORD *)a1 + 24LL));
      }
    }
    else
    {
      v6 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             230,
             v5,
             0,
             (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
             0,
             (__int64)L"cannot create an IXMLDOMDocument2 document");
    }
    v7 = v6;
    VariantClear(&pvarg);
  }
  else
  {
    v7 = -2147467259;
  }
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&ppv);
  return v7;
}

```

## disassembly

```asm
0x1400555ac  mov     [rsp-28h+arg_0], rbx
0x1400555b1  mov     byte ptr [rsp-28h+arg_18], r9b
0x1400555b6  mov     [rsp-28h+arg_10], r8
0x1400555bb  push    rbp
0x1400555bc  push    rsi
0x1400555bd  push    rdi
0x1400555be  push    r14
0x1400555c0  push    r15
0x1400555c2  mov     rbp, rsp
0x1400555c5  sub     rsp, 80h
0x1400555cc  mov     rbx, rdx
0x1400555cf  mov     rsi, rcx
0x1400555d2  xor     r14d, r14d
0x1400555d5  mov     [rbp+arg_10], r14
0x1400555d9  mov     [rbp+arg_18], r14w
0x1400555de  mov     ecx, 4
0x1400555e3  mov     rax, gs:58h
0x1400555ec  mov     rax, [rax]
0x1400555ef  mov     eax, [rcx+rax]
0x1400555f2  cmp     cs:dword_1401CBCC0, eax
0x1400555f8  jle     short loc_140055623
0x1400555fa  lea     rcx, dword_1401CBCC0
0x140055601  call    _Init_thread_header
0x140055606  cmp     cs:dword_1401CBCC0, 0FFFFFFFFh
0x14005560d  jnz     short loc_140055623
0x14005560f  mov     al, [rbx]
0x140055611  mov     cs:byte_1401CBCBC, al
0x140055617  lea     rcx, dword_1401CBCC0
0x14005561e  call    _Init_thread_footer
0x140055623  mov     [rbx], r14
0x140055626  call    ?Init@XmlDOM@mlib@@CA_NXZ; mlib::XmlDOM::Init(void)
0x14005562b  test    al, al
0x14005562d  jz      loc_1400557C4
0x140055633  lea     rax, [rbp+arg_10]
0x140055637  mov     [rsp+80h+ppv], rax; ppv
0x14005563c  lea     r15, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140055643  mov     r9, r15; riid
0x140055646  xor     edx, edx; pUnkOuter
0x140055648  lea     r8d, [rdx+1]; dwClsContext
0x14005564c  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x140055653  call    cs:__imp_CoCreateInstance
0x140055659  test    eax, eax
0x14005565b  js      loc_1400557C4
0x140055661  lea     rcx, [rbp+pvarg]; pvarg
0x140055665  call    cs:__imp_VariantInit
0x14005566b  nop
0x14005566c  mov     rax, [rsi]
0x14005566f  mov     rdi, [rax+18h]
0x140055673  lea     rcx, [rbp+pvarg]; pvarg
0x140055677  call    cs:__imp_VariantClear
0x14005567d  mov     eax, 8
0x140055682  mov     word ptr [rbp+pvarg], ax
0x140055686  mov     rcx, rdi; psz
0x140055689  call    cs:__imp_SysAllocString
0x14005568f  mov     dword ptr [rbp+pvarg+8], eax
0x140055692  mov     rcx, rax
0x140055695  sar     rcx, 20h
0x140055699  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x14005569c  test    rax, rax
0x14005569f  jnz     short loc_1400556BD
0x1400556a1  test    rdi, rdi
0x1400556a4  jz      short loc_1400556BD
0x1400556a6  mov     eax, 0Ah
0x1400556ab  mov     word ptr [rbp+pvarg], ax
0x1400556af  mov     ecx, 8007000Eh; int
0x1400556b4  mov     dword ptr [rbp+pvarg+8], ecx
0x1400556b7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400556bd  mov     rcx, [rbp+arg_10]
0x1400556c1  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400556c5  movaps  [rbp+var_20], xmm0
0x1400556c9  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400556ce  movsd   [rbp+var_10], xmm1
0x1400556d3  mov     rax, [rcx]
0x1400556d6  lea     r8, [rbp+arg_18]
0x1400556da  lea     rdx, [rbp+var_20]
0x1400556de  mov     rax, [rax+1D0h]
0x1400556e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400556ea  test    eax, eax
0x1400556ec  jns     short loc_14005572C
0x1400556ee  lea     rcx, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x1400556f5  xor     r9d, r9d
0x1400556f8  mov     edx, 0E6h
0x1400556fd  mov     [rsp+80h+var_50], rcx
0x140055702  mov     [rsp+80h+var_58], r14
0x140055707  mov     r8d, eax
0x14005570a  mov     [rsp+80h+ppv], r15
0x14005570f  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055716  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x14005571b  mov     ebx, eax
0x14005571d  lea     rcx, [rbp+pvarg]; pvarg
0x140055721  call    cs:__imp_VariantClear
0x140055727  jmp     loc_1400557C9
0x14005572c  cmp     [rbp+arg_18], r14w
0x140055731  jnz     short loc_140055772
0x140055733  mov     rax, [rsi]
0x140055736  mov     rcx, [rax+18h]
0x14005573a  mov     [rsp+80h+var_48], rcx
0x14005573f  lea     rax, aCannotLoadDocu; "cannot load document from file '%s'"
0x140055746  mov     [rsp+80h+var_50], rax
0x14005574b  mov     [rsp+80h+var_58], r14
0x140055750  mov     [rsp+80h+ppv], r15
0x140055755  mov     r9, [rbp+arg_10]
0x140055759  mov     edx, 0EBh
0x14005575e  mov     r8d, 80004005h
0x140055764  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x14005576b  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055770  jmp     short loc_14005571B
0x140055772  mov     rcx, [rbp+arg_10]
0x140055776  mov     rax, [rcx]
0x140055779  or      edx, 0FFFFFFFFh
0x14005577c  mov     rax, [rax+240h]
0x140055783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055788  test    eax, eax
0x14005578a  jns     short loc_1400557A1
0x14005578c  lea     rcx, aCannotSetThePr; "cannot set the 'preserve white space' f"...
0x140055793  mov     r9, [rbp+arg_10]
0x140055797  mov     edx, 0F6h
0x14005579c  jmp     loc_1400556FD
0x1400557a1  mov     rax, [rbp+arg_10]
0x1400557a5  mov     [rbp+arg_10], r14
0x1400557a9  mov     [rbx], rax
0x1400557ac  lea     rcx, [rbp+pvarg]; pvarg
0x1400557b0  call    cs:__imp_VariantClear
0x1400557b6  nop
0x1400557b7  lea     rcx, [rbp+arg_10]
0x1400557bb  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400557c0  xor     eax, eax
0x1400557c2  jmp     short loc_1400557D4
0x1400557c4  mov     ebx, 80004005h
0x1400557c9  lea     rcx, [rbp+arg_10]
0x1400557cd  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400557d2  mov     eax, ebx
0x1400557d4  mov     rbx, [rsp+80h+arg_0]
0x1400557dc  add     rsp, 80h
0x1400557e3  pop     r15
0x1400557e5  pop     r14
0x1400557e7  pop     rdi
0x1400557e8  pop     rsi
0x1400557e9  pop     rbp
0x1400557ea  retn
```
