# mlib::XmlDOM::GetExtendedErrorInfo(IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18002e778`
- end: `0x18002e85b`
- name: `?GetExtendedErrorInfo@XmlDOM@mlib@@CAXPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006494`

## callees

- `0x1800035cc`
- `0x18000be30`
- `0x18000e490`
- `0x18002e778`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002e837`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e837`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002e7f4`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002e7f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall mlib::XmlDOM::GetExtendedErrorInfo(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3)
{
  int v6; // eax
  IErrorInfo *pperrinfo[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  pperrinfo[1] = (IErrorInfo *)-2LL;
  pperrinfo[0] = 0;
  bstrString = 0;
  v9 = 0;
  if ( a3 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a3);
    v6 = (**a1)(a1, &GUID_df0b3d60_548f_101b_8e65_08002b2bd119, &v9);
    if ( v9 )
    {
      if ( v6 >= 0
        && (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 24LL))(v9, a2) >= 0
        && GetErrorInfo(0, pperrinfo) >= 0
        && ((int (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo[0]->lpVtbl->GetDescription)(pperrinfo[0], &bstrString) >= 0 )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
          a3,
          bstrString);
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  SysFreeString(bstrString);
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)pperrinfo);
}

```

## disassembly

```asm
0x18002e778  push    rbp
0x18002e77a  push    rsi
0x18002e77b  push    rdi
0x18002e77c  mov     rbp, rsp
0x18002e77f  sub     rsp, 30h
0x18002e783  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18002e78b  mov     [rsp+30h+arg_0], rbx
0x18002e790  mov     rbx, r8
0x18002e793  mov     rsi, rdx
0x18002e796  mov     rdi, rcx
0x18002e799  and     [rbp+pperrinfo], 0
0x18002e79e  and     [rbp+bstrString], 0
0x18002e7a3  and     [rbp+arg_10], 0
0x18002e7a8  test    r8, r8
0x18002e7ab  jz      short loc_18002E829
0x18002e7ad  mov     rcx, rbx
0x18002e7b0  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18002e7b5  mov     rax, [rdi]
0x18002e7b8  lea     r8, [rbp+arg_10]
0x18002e7bc  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x18002e7c3  mov     rcx, rdi
0x18002e7c6  mov     rax, [rax]
0x18002e7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7ce  mov     rcx, [rbp+arg_10]
0x18002e7d2  test    rcx, rcx
0x18002e7d5  jz      short loc_18002E829
0x18002e7d7  test    eax, eax
0x18002e7d9  js      short loc_18002E829
0x18002e7db  mov     rax, [rcx]
0x18002e7de  mov     rdx, rsi
0x18002e7e1  mov     rax, [rax+18h]
0x18002e7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7ea  test    eax, eax
0x18002e7ec  js      short loc_18002E829
0x18002e7ee  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18002e7f2  xor     ecx, ecx; dwReserved
0x18002e7f4  call    cs:__imp_GetErrorInfo
0x18002e7fb  nop     dword ptr [rax+rax+00h]
0x18002e800  test    eax, eax
0x18002e802  js      short loc_18002E829
0x18002e804  mov     rcx, [rbp+pperrinfo]
0x18002e808  mov     rax, [rcx]
0x18002e80b  lea     rdx, [rbp+bstrString]
0x18002e80f  mov     rax, [rax+28h]
0x18002e813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e818  test    eax, eax
0x18002e81a  js      short loc_18002E829
0x18002e81c  mov     rdx, [rbp+bstrString]
0x18002e820  mov     rcx, rbx
0x18002e823  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x18002e828  nop
0x18002e829  lea     rcx, [rbp+arg_10]
0x18002e82d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e832  nop
0x18002e833  mov     rcx, [rbp+bstrString]; bstrString
0x18002e837  call    cs:__imp_SysFreeString
0x18002e83e  nop     dword ptr [rax+rax+00h]
0x18002e843  nop
0x18002e844  lea     rcx, [rbp+pperrinfo]
0x18002e848  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e84d  mov     rbx, [rsp+30h+arg_0]
0x18002e852  add     rsp, 30h
0x18002e856  pop     rdi
0x18002e857  pop     rsi
0x18002e858  pop     rbp
0x18002e859  retn
```
