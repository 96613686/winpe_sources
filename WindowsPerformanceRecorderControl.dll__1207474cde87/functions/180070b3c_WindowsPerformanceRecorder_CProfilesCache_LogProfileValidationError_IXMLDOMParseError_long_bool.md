# WindowsPerformanceRecorder::CProfilesCache::LogProfileValidationError(IXMLDOMParseError *,long &,bool)

- ea: `0x180070b3c`
- end: `0x180070d7f`
- name: `?LogProfileValidationError@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEAUIXMLDOMParseError@@AEAJ_N@Z`
- size: `579`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CProfilesCache *__hidden this, struct IXMLDOMParseError *, int *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021b7c`

## callees

- `0x18001e6e0`
- `0x1800481b8`
- `0x18004b024`
- `0x180070b3c`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180070d37`
- `OLEAUT32!__imp_SysFreeString` at `0x180070d41`
- `OLEAUT32!__imp_SysFreeString` at `0x180070d37`
- `OLEAUT32!__imp_SysFreeString` at `0x180070d41`

## string_xrefs

- `0x180070d15`: `Xml validation Hr=0x%x at line=%d column=%d reason=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::CProfilesCache::LogProfileValidationError(
        WindowsPerformanceRecorder::CProfilesCache *this,
        struct IXMLDOMParseError *a2,
        struct ATL::CComBSTR *a3,
        char a4)
{
  WindowsPerformanceRecorder::CProfilesCache *v7; // r15
  char v8; // si
  OLECHAR *v9; // rbx
  const unsigned __int16 *v10; // r9
  int Format; // [rsp+20h] [rbp-88h]
  char *v13; // [rsp+28h] [rbp-80h]
  unsigned int v14; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v15; // [rsp+54h] [rbp-54h] BYREF
  int v16; // [rsp+58h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-48h] BYREF
  struct _GUID v18; // [rsp+68h] [rbp-40h] BYREF
  char v20; // [rsp+C0h] [rbp+18h]

  *(_QWORD *)v18.Data4 = -2;
  v7 = this;
  if ( !*((_QWORD *)this + 6) || (v8 = 1, v20 = 1, *((_BYTE *)this + 56)) )
  {
    v8 = 0;
    v20 = 0;
  }
  try
  {
    *(_DWORD *)a3 = 1;
    if ( v8 )
      (*(void (__fastcall **)(_QWORD, GUID *))(**((_QWORD **)this + 6) + 24LL))(
        *((_QWORD *)this + 6),
        &GUID_b96aa961_1fc7_4fd2_9f6b_513ff7bbe38d);
    v14 = 0;
    if ( a2
      && !((unsigned int (__fastcall *)(struct IXMLDOMParseError *, unsigned int *))a2->lpVtbl->get_linepos)(a2, &v14)
      && v8 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v7 + 6) + 72LL))(*((_QWORD *)v7 + 6), v14);
    }
    v15 = 0;
    if ( a2
      && !((unsigned int (__fastcall *)(struct IXMLDOMParseError *, unsigned int *))a2->lpVtbl->get_line)(a2, &v15)
      && v8 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v7 + 6) + 80LL))(*((_QWORD *)v7 + 6), v15);
    }
    *(_QWORD *)&v18.Data1 = 0;
    if ( (unsigned int)WindowsPerformanceRecorder::Impl::GetStringFromGuid(this, &v18, a3) || !v8 )
    {
      v9 = *(OLECHAR **)&v18.Data1;
    }
    else
    {
      v9 = *(OLECHAR **)&v18.Data1;
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v7 + 6) + 32LL))(
        *((_QWORD *)v7 + 6),
        *(_QWORD *)&v18.Data1);
    }
    bstrString = 0;
    if ( a2
      && !((unsigned int (__fastcall *)(struct IXMLDOMParseError *, BSTR *))a2->lpVtbl->get_reason)(a2, &bstrString)
      && v8 )
    {
      (*(void (__fastcall **)(_QWORD, BSTR))(**((_QWORD **)v7 + 6) + 40LL))(*((_QWORD *)v7 + 6), bstrString);
    }
    v16 = 0;
    if ( a2 && !((unsigned int (__fastcall *)(struct IXMLDOMParseError *, int *))a2->lpVtbl->get_errorCode)(a2, &v16) )
      *(_DWORD *)a3 = v16;
    v10 = (const unsigned __int16 *)*(unsigned int *)a3;
    if ( a4 )
    {
      WindowsPerformanceRecorder::TelemetryError(
        (WindowsPerformanceRecorder *)0x1000,
        (unsigned __int64)"LogProfileValidationError",
        (const char *)bstrString,
        v10,
        Format);
    }
    else
    {
      LODWORD(v13) = *(_DWORD *)a3;
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        "LogProfileValidationError",
        (const char *)0x260,
        (unsigned int)v10,
        "Xml validation Hr=0x%x at line=%d column=%d reason=%ws",
        v13,
        v15,
        v14,
        bstrString);
    }
    SysFreeString(bstrString);
    SysFreeString(v9);
  }
  catch ( ATL::CAtlException )
  {
    v7 = this;
    v8 = v20;
  }
  if ( v8 )
    *((_BYTE *)v7 + 56) = 1;
  return 0;
}

```

## disassembly

```asm
0x180070b3c  mov     rax, rsp
0x180070b3f  mov     [rax+8], rcx
0x180070b43  push    rsi
0x180070b44  push    r12
0x180070b46  push    r13
0x180070b48  push    r14
0x180070b4a  push    r15
0x180070b4c  sub     rsp, 80h
0x180070b53  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180070b5b  mov     [rax+10h], rbx
0x180070b5f  mov     r13b, r9b
0x180070b62  mov     r12, r8
0x180070b65  mov     r14, rdx
0x180070b68  mov     r15, rcx
0x180070b6b  cmp     qword ptr [rcx+30h], 0
0x180070b70  jz      short loc_180070B83
0x180070b72  mov     sil, 1
0x180070b75  mov     [rsp+0A8h+arg_10], sil
0x180070b7d  cmp     byte ptr [rcx+38h], 0
0x180070b81  jz      short loc_180070B8E
0x180070b83  xor     sil, sil
0x180070b86  mov     [rsp+0A8h+arg_10], sil
0x180070b8e  mov     dword ptr [r8], 1
0x180070b95  test    sil, sil
0x180070b98  jz      short loc_180070BB1
0x180070b9a  mov     rcx, [rcx+30h]
0x180070b9e  mov     rax, [rcx]
0x180070ba1  lea     rdx, _GUID_b96aa961_1fc7_4fd2_9f6b_513ff7bbe38d
0x180070ba8  mov     rax, [rax+18h]
0x180070bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070bb1  mov     [rsp+0A8h+var_58], 0
0x180070bb9  test    r14, r14
0x180070bbc  jz      short loc_180070BEF
0x180070bbe  mov     rax, [r14]
0x180070bc1  lea     rdx, [rsp+0A8h+var_58]
0x180070bc6  mov     rcx, r14
0x180070bc9  mov     rax, [rax+60h]
0x180070bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070bd2  test    eax, eax
0x180070bd4  jnz     short loc_180070BEF
0x180070bd6  test    sil, sil
0x180070bd9  jz      short loc_180070BEF
0x180070bdb  mov     rcx, [r15+30h]
0x180070bdf  mov     rax, [rcx]
0x180070be2  mov     edx, [rsp+0A8h+var_58]
0x180070be6  mov     rax, [rax+48h]
0x180070bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070bef  mov     [rsp+0A8h+var_54], 0
0x180070bf7  test    r14, r14
0x180070bfa  jz      short loc_180070C2D
0x180070bfc  mov     rax, [r14]
0x180070bff  lea     rdx, [rsp+0A8h+var_54]
0x180070c04  mov     rcx, r14
0x180070c07  mov     rax, [rax+58h]
0x180070c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c10  test    eax, eax
0x180070c12  jnz     short loc_180070C2D
0x180070c14  test    sil, sil
0x180070c17  jz      short loc_180070C2D
0x180070c19  mov     rcx, [r15+30h]
0x180070c1d  mov     rax, [rcx]
0x180070c20  mov     edx, [rsp+0A8h+var_54]
0x180070c24  mov     rax, [rax+50h]
0x180070c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c2d  mov     qword ptr [rsp+0A8h+var_40.Data1], 0
0x180070c36  lea     rdx, [rsp+0A8h+var_40]; struct _GUID *
0x180070c3b  call    ?GetStringFromGuid@Impl@WindowsPerformanceRecorder@@YAJAEBU_GUID@@AEAVCComBSTR@ATL@@@Z; WindowsPerformanceRecorder::Impl::GetStringFromGuid(_GUID const &,ATL::CComBSTR &)
0x180070c40  test    eax, eax
0x180070c42  jnz     short loc_180070C63
0x180070c44  test    sil, sil
0x180070c47  jz      short loc_180070C63
0x180070c49  mov     rcx, [r15+30h]
0x180070c4d  mov     rax, [rcx]
0x180070c50  mov     rbx, qword ptr [rsp+0A8h+var_40.Data1]
0x180070c55  mov     rdx, rbx
0x180070c58  mov     rax, [rax+20h]
0x180070c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c61  jmp     short loc_180070C68
0x180070c63  mov     rbx, qword ptr [rsp+0A8h+var_40.Data1]
0x180070c68  mov     [rsp+0A8h+bstrString], 0
0x180070c71  test    r14, r14
0x180070c74  jz      short loc_180070CA8
0x180070c76  mov     rax, [r14]
0x180070c79  lea     rdx, [rsp+0A8h+bstrString]
0x180070c7e  mov     rcx, r14
0x180070c81  mov     rax, [rax+48h]
0x180070c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c8a  test    eax, eax
0x180070c8c  jnz     short loc_180070CA8
0x180070c8e  test    sil, sil
0x180070c91  jz      short loc_180070CA8
0x180070c93  mov     rcx, [r15+30h]
0x180070c97  mov     rax, [rcx]
0x180070c9a  mov     rdx, [rsp+0A8h+bstrString]
0x180070c9f  mov     rax, [rax+28h]
0x180070ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070ca8  mov     [rsp+0A8h+var_50], 0
0x180070cb0  test    r14, r14
0x180070cb3  jz      short loc_180070CD5
0x180070cb5  mov     rax, [r14]
0x180070cb8  lea     rdx, [rsp+0A8h+var_50]
0x180070cbd  mov     rcx, r14
0x180070cc0  mov     rax, [rax+38h]
0x180070cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070cc9  test    eax, eax
0x180070ccb  jnz     short loc_180070CD5
0x180070ccd  mov     eax, [rsp+0A8h+var_50]
0x180070cd1  mov     [r12], eax
0x180070cd5  mov     r9d, [r12]; unsigned int
0x180070cd9  lea     rdx, aLogprofilevali; "LogProfileValidationError"
0x180070ce0  test    r13b, r13b
0x180070ce3  jz      short loc_180070CF6
0x180070ce5  mov     r8, [rsp+0A8h+bstrString]; char *
0x180070cea  mov     ecx, 1000h; this
0x180070cef  call    ?TelemetryError@WindowsPerformanceRecorder@@YAX_KPEBDPEBGJ@Z; WindowsPerformanceRecorder::TelemetryError(unsigned __int64,char const *,ushort const *,long)
0x180070cf4  jmp     short loc_180070D32
0x180070cf6  mov     rax, [rsp+0A8h+bstrString]
0x180070cfb  mov     [rsp+0A8h+var_68], rax
0x180070d00  mov     eax, [rsp+0A8h+var_58]
0x180070d04  mov     [rsp+0A8h+var_70], eax
0x180070d08  mov     eax, [rsp+0A8h+var_54]
0x180070d0c  mov     [rsp+0A8h+var_78], eax
0x180070d10  mov     dword ptr [rsp+0A8h+var_80], r9d; char *
0x180070d15  lea     rax, aXmlValidationH; "Xml validation Hr=0x%x at line=%d colum"...
0x180070d1c  mov     [rsp+0A8h+Format], rax; Format
0x180070d21  mov     r8d, 260h; char *
0x180070d27  mov     ecx, 2; this
0x180070d2c  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180070d31  nop
0x180070d32  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x180070d37  call    cs:__imp_SysFreeString
0x180070d3d  nop
0x180070d3e  mov     rcx, rbx; bstrString
0x180070d41  call    cs:__imp_SysFreeString
0x180070d47  nop
0x180070d48  jmp     short loc_180070D5A
0x180070d4a  mov     r15, [rsp+0A8h+arg_0]
0x180070d52  mov     sil, [rsp+0A8h+arg_10]
0x180070d5a  test    sil, sil
0x180070d5d  jz      short loc_180070D64
0x180070d5f  mov     byte ptr [r15+38h], 1
0x180070d64  xor     eax, eax
0x180070d66  mov     rbx, [rsp+0A8h+arg_8]
0x180070d6e  add     rsp, 80h
0x180070d75  pop     r15
0x180070d77  pop     r14
0x180070d79  pop     r13
0x180070d7b  pop     r12
0x180070d7d  pop     rsi
0x180070d7e  retn
```
