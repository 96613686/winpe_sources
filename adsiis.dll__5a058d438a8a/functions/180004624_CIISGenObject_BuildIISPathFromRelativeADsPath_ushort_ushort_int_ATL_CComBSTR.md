# CIISGenObject::BuildIISPathFromRelativeADsPath(ushort *,ushort * *,int &,ATL::CComBSTR &)

- ea: `0x180004624`
- end: `0x180004744`
- name: `?BuildIISPathFromRelativeADsPath@CIISGenObject@@IEAAJPEAGPEAPEAGAEAHAEAVCComBSTR@ATL@@@Z`
- size: `288`
- prototype: `int(CIISGenObject *__hidden this, unsigned __int16 *, unsigned __int16 **, int *, struct ATL::CComBSTR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800049c0`

## callees

- `0x180004284`
- `0x180004574`
- `0x180004624`
- `0x1800151fc`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000466c`
- `msvcrt!_wcsnicmp` at `0x18000468f`
- `msvcrt!_wcsnicmp` at `0x18000466c`
- `msvcrt!_wcsnicmp` at `0x18000468f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800046bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800046f0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800046bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800046f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180004713`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180004713`
- `OLEAUT32!__imp_SysStringLen` at `0x1800046cb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800046fc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800046cb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800046fc`

## pseudocode

```c
__int64 __fastcall CIISGenObject::BuildIISPathFromRelativeADsPath(
        CIISGenObject *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        int *a4,
        unsigned __int16 **a5)
{
  const wchar_t *v9; // rdx
  size_t v10; // r8
  OLECHAR *v12; // rbx
  UINT v13; // eax
  OLECHAR *v14; // rbx
  UINT v15; // eax

  *a3 = 0;
  *a4 = 0;
  ATL::CComBSTR::operator=(a5, a2);
  if ( *a5 )
  {
    if ( !_wcsnicmp(a2, L"IIS://", 6u) )
    {
      v9 = (const wchar_t *)*((_QWORD *)this + 17);
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
      if ( _wcsnicmp(a2 + 6, v9, v10) )
        return 2147504128LL;
      return BuildIISPathFromADsPath(*a5, a3);
    }
    ATL::CComBSTR::operator=(a5, *((_QWORD *)this + 3));
    if ( *a5 )
    {
      v12 = SysAllocString(L"/");
      v13 = SysStringLen(v12);
      ATL::CComBSTR::Append((ATL::CComBSTR *)a5, v12, v13);
      SysFreeString(v12);
      if ( *a5 )
      {
        v14 = SysAllocString(a2);
        v15 = SysStringLen(v14);
        ATL::CComBSTR::Append((ATL::CComBSTR *)a5, v14, v15);
        SysFreeString(v14);
        if ( *a5 )
        {
          *a4 = 1;
          return BuildIISPathFromADsPath(*a5, a3);
        }
      }
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004624  push    rbx
0x180004626  push    rbp
0x180004627  push    rsi
0x180004628  push    rdi
0x180004629  push    r14
0x18000462b  push    r15
0x18000462d  sub     rsp, 28h
0x180004631  mov     rdi, [rsp+58h+arg_20]
0x180004639  mov     rbx, rcx
0x18000463c  xor     ebp, ebp
0x18000463e  mov     rcx, rdi
0x180004641  mov     r14, r9
0x180004644  mov     [r8], rbp
0x180004647  mov     r15, r8
0x18000464a  mov     [r9], ebp
0x18000464d  mov     rsi, rdx
0x180004650  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180004655  cmp     [rdi], rbp
0x180004658  jz      loc_180004732
0x18000465e  lea     r8d, [rbp+6]; MaxCount
0x180004662  mov     rcx, rsi; String1
0x180004665  lea     rdx, aIis_1; "IIS://"
0x18000466c  call    cs:__imp__wcsnicmp
0x180004672  test    eax, eax
0x180004674  jnz     short loc_1800046A7
0x180004676  mov     rdx, [rbx+88h]; String2
0x18000467d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004681  inc     r8; MaxCount
0x180004684  cmp     [rdx+r8*2], bp
0x180004689  jnz     short loc_180004681
0x18000468b  lea     rcx, [rsi+0Ch]; String1
0x18000468f  call    cs:__imp__wcsnicmp
0x180004695  test    eax, eax
0x180004697  jz      loc_180004725
0x18000469d  mov     eax, 80005000h
0x1800046a2  jmp     loc_180004737
0x1800046a7  mov     rdx, [rbx+18h]
0x1800046ab  mov     rcx, rdi
0x1800046ae  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800046b3  cmp     [rdi], rbp
0x1800046b6  jz      short loc_180004732
0x1800046b8  lea     rcx, Source; "/"
0x1800046bf  call    cs:__imp_SysAllocString
0x1800046c5  mov     rcx, rax; pbstr
0x1800046c8  mov     rbx, rax
0x1800046cb  call    cs:__imp_SysStringLen
0x1800046d1  mov     rdx, rbx; unsigned __int16 *
0x1800046d4  mov     rcx, rdi; this
0x1800046d7  mov     r8d, eax; int
0x1800046da  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800046df  mov     rcx, rbx; bstrString
0x1800046e2  call    cs:__imp_SysFreeString
0x1800046e8  cmp     [rdi], rbp
0x1800046eb  jz      short loc_180004732
0x1800046ed  mov     rcx, rsi; psz
0x1800046f0  call    cs:__imp_SysAllocString
0x1800046f6  mov     rcx, rax; pbstr
0x1800046f9  mov     rbx, rax
0x1800046fc  call    cs:__imp_SysStringLen
0x180004702  mov     rdx, rbx; unsigned __int16 *
0x180004705  mov     rcx, rdi; this
0x180004708  mov     r8d, eax; int
0x18000470b  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180004710  mov     rcx, rbx; bstrString
0x180004713  call    cs:__imp_SysFreeString
0x180004719  cmp     [rdi], rbp
0x18000471c  jz      short loc_180004732
0x18000471e  mov     dword ptr [r14], 1
0x180004725  mov     rcx, [rdi]; unsigned __int16 *
0x180004728  mov     rdx, r15; unsigned __int16 **
0x18000472b  call    ?BuildIISPathFromADsPath@@YAJPEAGPEAPEAG@Z; BuildIISPathFromADsPath(ushort *,ushort * *)
0x180004730  jmp     short loc_180004737
0x180004732  mov     eax, 8007000Eh
0x180004737  add     rsp, 28h
0x18000473b  pop     r15
0x18000473d  pop     r14
0x18000473f  pop     rdi
0x180004740  pop     rsi
0x180004741  pop     rbp
0x180004742  pop     rbx
0x180004743  retn
```
