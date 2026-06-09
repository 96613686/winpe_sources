# FrameWindow::OpenURLInBrowser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180026810`
- end: `0x18002699e`
- name: `?OpenURLInBrowser@FrameWindow@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(IUri *, const WCHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b910`

## callees

- `0x180002dd4`
- `0x180026810`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026887`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002689c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026887`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002689c`
- `OLEAUT32!__imp_SysFreeString` at `0x180026948`
- `OLEAUT32!__imp_SysFreeString` at `0x180026978`
- `OLEAUT32!__imp_SysFreeString` at `0x180026948`
- `OLEAUT32!__imp_SysFreeString` at `0x180026978`
- `SHELL32!ShellExecuteW` at `0x1800268f5`
- `SHELL32!ShellExecuteW` at `0x1800268f5`
- `urlmon!CreateUri` at `0x180026835`
- `urlmon!CreateUri` at `0x180026835`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FrameWindow::OpenURLInBrowser(IUri *a1, const WCHAR **a2)
{
  const WCHAR *v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // eax
  LPCWSTR v5; // rdx
  _QWORD *v6; // rdx
  LPCWSTR lpFile[3]; // [rsp+30h] [rbp-18h] BYREF
  IUri *ppURI; // [rsp+60h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+20h] BYREF
  __int64 v11; // [rsp+70h] [rbp+28h] BYREF
  BSTR v12; // [rsp+78h] [rbp+30h] BYREF

  ppURI = a1;
  v2 = *a2;
  ppURI = 0;
  v3 = CreateUri(v2, 0x12900u, 0, &ppURI);
  if ( !v3 )
  {
    v12 = 0;
    v3 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &v12);
    if ( !v3 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v11,
        v12);
      if ( !(unsigned int)_o__wcsicmp(v11, L"http") || !(unsigned int)_o__wcsicmp(v11, L"https") )
      {
        bstrString = 0;
        v3 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetAbsoluteUri)(ppURI, &bstrString);
        if ( !v3 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            lpFile,
            bstrString);
          v4 = (unsigned int)ShellExecuteW(0, 0, lpFile[0], 0, 0, 10);
          if ( v4 )
            v3 = v4 <= 0x20 ? (unsigned __int16)v4 | 0x80070000 : 0;
          else
            v3 = -2147024882;
          v5 = lpFile[0] - 12;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpFile[0] - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
        }
        SysFreeString(bstrString);
      }
      v6 = (_QWORD *)(v11 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    }
    SysFreeString(v12);
  }
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  return v3;
}

```

## disassembly

```asm
0x180026810  mov     [rsp-10h+ppURI], rcx
0x180026815  push    rbp
0x180026816  push    rbx
0x180026817  mov     rbp, rsp
0x18002681a  sub     rsp, 48h
0x18002681e  mov     rcx, [rdx]; pwzURI
0x180026821  mov     [rbp+ppURI], 0
0x180026829  lea     r9, [rbp+ppURI]; ppURI
0x18002682d  xor     r8d, r8d; dwReserved
0x180026830  mov     edx, 12900h; dwFlags
0x180026835  call    cs:__imp_CreateUri
0x18002683b  mov     ebx, eax
0x18002683d  test    eax, eax
0x18002683f  jnz     loc_18002697F
0x180026845  mov     [rbp+arg_18], 0
0x18002684d  mov     rcx, [rbp+ppURI]
0x180026851  mov     rax, [rcx]
0x180026854  lea     rdx, [rbp+arg_18]
0x180026858  mov     rax, [rax+98h]
0x18002685f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026864  mov     ebx, eax
0x180026866  test    eax, eax
0x180026868  jnz     loc_180026974
0x18002686e  mov     rdx, [rbp+arg_18]
0x180026872  lea     rcx, [rbp+arg_10]
0x180026876  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002687b  nop
0x18002687c  lea     rdx, aHttp; "http"
0x180026883  mov     rcx, [rbp+arg_10]
0x180026887  call    cs:__imp__o__wcsicmp
0x18002688d  test    eax, eax
0x18002688f  jz      short loc_1800268AA
0x180026891  lea     rdx, aHttps; "https"
0x180026898  mov     rcx, [rbp+arg_10]
0x18002689c  call    cs:__imp__o__wcsicmp
0x1800268a2  test    eax, eax
0x1800268a4  jnz     loc_18002694F
0x1800268aa  mov     [rbp+bstrString], 0
0x1800268b2  mov     rcx, [rbp+ppURI]
0x1800268b6  mov     rax, [rcx]
0x1800268b9  lea     rdx, [rbp+bstrString]
0x1800268bd  mov     rax, [rax+38h]
0x1800268c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268c6  mov     ebx, eax
0x1800268c8  test    eax, eax
0x1800268ca  jnz     short loc_180026944
0x1800268cc  mov     rdx, [rbp+bstrString]
0x1800268d0  lea     rcx, [rbp+lpFile]
0x1800268d4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800268d9  mov     [rsp+48h+nShowCmd], 0Ah; nShowCmd
0x1800268e1  mov     [rsp+48h+lpDirectory], 0; lpDirectory
0x1800268ea  xor     r9d, r9d; lpParameters
0x1800268ed  mov     r8, [rbp+lpFile]; lpFile
0x1800268f1  xor     edx, edx; lpOperation
0x1800268f3  xor     ecx, ecx; hwnd
0x1800268f5  call    cs:__imp_ShellExecuteW
0x1800268fb  mov     rbx, rax
0x1800268fe  test    eax, eax
0x180026900  jnz     short loc_180026909
0x180026902  mov     ebx, 8007000Eh
0x180026907  jmp     short loc_18002691F
0x180026909  cmp     eax, 20h ; ' '
0x18002690c  jbe     short loc_180026912
0x18002690e  xor     ebx, ebx
0x180026910  jmp     short loc_18002691F
0x180026912  test    eax, eax
0x180026914  jle     short loc_18002691F
0x180026916  movzx   ebx, ax
0x180026919  or      ebx, 80070000h
0x18002691f  mov     rdx, [rbp+lpFile]
0x180026923  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180026927  or      eax, 0FFFFFFFFh
0x18002692a  lock xadd [rdx+10h], eax
0x18002692f  sub     eax, 1
0x180026932  jg      short loc_180026944
0x180026934  mov     rcx, [rdx]
0x180026937  mov     rax, [rcx]
0x18002693a  mov     rax, [rax+8]
0x18002693e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026943  nop
0x180026944  mov     rcx, [rbp+bstrString]; bstrString
0x180026948  call    cs:__imp_SysFreeString
0x18002694e  nop
0x18002694f  mov     rdx, [rbp+arg_10]
0x180026953  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180026957  or      eax, 0FFFFFFFFh
0x18002695a  lock xadd [rdx+10h], eax
0x18002695f  sub     eax, 1
0x180026962  jg      short loc_180026974
0x180026964  mov     rcx, [rdx]
0x180026967  mov     rax, [rcx]
0x18002696a  mov     rax, [rax+8]
0x18002696e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026973  nop
0x180026974  mov     rcx, [rbp+arg_18]; bstrString
0x180026978  call    cs:__imp_SysFreeString
0x18002697e  nop
0x18002697f  mov     rcx, [rbp+ppURI]
0x180026983  test    rcx, rcx
0x180026986  jz      short loc_180026995
0x180026988  mov     rax, [rcx]
0x18002698b  mov     rax, [rax+10h]
0x18002698f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026994  nop
0x180026995  mov     eax, ebx
0x180026997  add     rsp, 48h
0x18002699b  pop     rbx
0x18002699c  pop     rbp
0x18002699d  retn
```
