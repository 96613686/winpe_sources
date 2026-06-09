# CLoginForm::CleanUri(ushort const *,ushort * *)

- ea: `0x14000d8d8`
- end: `0x14000daae`
- name: `?CleanUri@CLoginForm@@SAJPEBGPEAPEAG@Z`
- size: `470`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000d670`
- `0x140011aa4`

## callees

- `0x140002c98`
- `0x14000d214`
- `0x14000d8d8`
- `0x140014010`

## import_xrefs

- `urlmon!CreateIUriBuilder` at `0x14000d92e`
- `urlmon!CreateIUriBuilder` at `0x14000d92e`
- `urlmon!CreateUri` at `0x14000d911`
- `urlmon!CreateUri` at `0x14000d911`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLoginForm::CleanUri(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  IUriBuilder *ppIUriBuilder; // [rsp+58h] [rbp+28h] BYREF
  __int64 v8; // [rsp+60h] [rbp+30h] BYREF
  IUri *ppURI; // [rsp+68h] [rbp+38h] BYREF

  ppURI = 0;
  ppIUriBuilder = 0;
  v8 = 0;
  *a2 = 0;
  v3 = CreateUri(a1, 0x3002B80u, 0, &ppURI);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v5 = 39;
      goto LABEL_26;
    }
  }
  else
  {
    v3 = CreateIUriBuilder(ppURI, 0, 0, &ppIUriBuilder);
    if ( v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v5 = 38;
        goto LABEL_26;
      }
    }
    else
    {
      v3 = ((__int64 (__fastcall *)(IUriBuilder *, __int64))ppIUriBuilder->lpVtbl->RemoveProperties)(
             ppIUriBuilder,
             83376);
      if ( v3 < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v5 = 37;
          goto LABEL_26;
        }
      }
      else
      {
        v3 = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD, _QWORD, __int64 *))ppIUriBuilder->lpVtbl->CreateUriSimple)(
               ppIUriBuilder,
               0,
               0,
               &v8);
        if ( v3 < 0 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            v5 = 36;
            goto LABEL_26;
          }
        }
        else
        {
          v3 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v8 + 56LL))(v8, a2);
          if ( v3 < 0 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
            {
              v5 = 35;
LABEL_26:
              WPP_SF_d(v4[7], v5, WPP_3a4fffaa845934d8edf59f75967dfe07_Traceguids, (unsigned int)v3);
            }
          }
        }
      }
    }
  }
  ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(&v8);
  ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(&ppIUriBuilder);
  ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(&ppURI);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000d8d8  push    rbp
0x14000d8da  push    rbx
0x14000d8db  push    rdi
0x14000d8dc  mov     rbp, rsp
0x14000d8df  sub     rsp, 30h
0x14000d8e3  mov     rdi, rdx
0x14000d8e6  mov     [rbp+ppURI], 0
0x14000d8ee  mov     [rbp+ppIUriBuilder], 0
0x14000d8f6  mov     [rbp+arg_10], 0
0x14000d8fe  mov     qword ptr [rdx], 0
0x14000d905  lea     r9, [rbp+ppURI]; ppURI
0x14000d909  xor     r8d, r8d; dwReserved
0x14000d90c  mov     edx, 3002B80h; dwFlags
0x14000d911  call    cs:__imp_CreateUri
0x14000d917  mov     ebx, eax
0x14000d919  test    eax, eax
0x14000d91b  js      loc_14000DA4F
0x14000d921  lea     r9, [rbp+ppIUriBuilder]; ppIUriBuilder
0x14000d925  xor     r8d, r8d; dwReserved
0x14000d928  xor     edx, edx; dwFlags
0x14000d92a  mov     rcx, [rbp+ppURI]; pIUri
0x14000d92e  call    cs:__imp_CreateIUriBuilder
0x14000d934  mov     ebx, eax
0x14000d936  test    eax, eax
0x14000d938  js      loc_14000DA29
0x14000d93e  mov     rcx, [rbp+ppIUriBuilder]
0x14000d942  mov     rax, [rcx]
0x14000d945  mov     edx, 145B0h
0x14000d94a  mov     rax, [rax+0C0h]
0x14000d951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d956  mov     ebx, eax
0x14000d958  test    eax, eax
0x14000d95a  js      loc_14000DA03
0x14000d960  mov     rcx, [rbp+ppIUriBuilder]
0x14000d964  mov     rax, [rcx]
0x14000d967  lea     r9, [rbp+arg_10]
0x14000d96b  xor     r8d, r8d
0x14000d96e  xor     edx, edx
0x14000d970  mov     rax, [rax+18h]
0x14000d974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d979  mov     ebx, eax
0x14000d97b  test    eax, eax
0x14000d97d  js      short loc_14000D9D1
0x14000d97f  mov     rcx, [rbp+arg_10]
0x14000d983  mov     rax, [rcx]
0x14000d986  mov     rdx, rdi
0x14000d989  mov     rax, [rax+38h]
0x14000d98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d992  mov     ebx, eax
0x14000d994  test    eax, eax
0x14000d996  jns     loc_14000DA87
0x14000d99c  lea     rax, WPP_GLOBAL_Control
0x14000d9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9aa  cmp     rcx, rax
0x14000d9ad  jz      loc_14000DA87
0x14000d9b3  test    byte ptr [rcx+44h], 2
0x14000d9b7  jz      loc_14000DA87
0x14000d9bd  cmp     byte ptr [rcx+41h], 2
0x14000d9c1  jb      loc_14000DA87
0x14000d9c7  mov     edx, 23h ; '#'
0x14000d9cc  jmp     loc_14000DA73
0x14000d9d1  lea     rax, WPP_GLOBAL_Control
0x14000d9d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9df  cmp     rcx, rax
0x14000d9e2  jz      loc_14000DA87
0x14000d9e8  test    byte ptr [rcx+44h], 2
0x14000d9ec  jz      loc_14000DA87
0x14000d9f2  cmp     byte ptr [rcx+41h], 2
0x14000d9f6  jb      loc_14000DA87
0x14000d9fc  mov     edx, 24h ; '$'
0x14000da01  jmp     short loc_14000DA73
0x14000da03  lea     rax, WPP_GLOBAL_Control
0x14000da0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da11  cmp     rcx, rax
0x14000da14  jz      short loc_14000DA87
0x14000da16  test    byte ptr [rcx+44h], 2
0x14000da1a  jz      short loc_14000DA87
0x14000da1c  cmp     byte ptr [rcx+41h], 2
0x14000da20  jb      short loc_14000DA87
0x14000da22  mov     edx, 25h ; '%'
0x14000da27  jmp     short loc_14000DA73
0x14000da29  lea     rax, WPP_GLOBAL_Control
0x14000da30  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da37  cmp     rcx, rax
0x14000da3a  jz      short loc_14000DA87
0x14000da3c  test    byte ptr [rcx+44h], 2
0x14000da40  jz      short loc_14000DA87
0x14000da42  cmp     byte ptr [rcx+41h], 2
0x14000da46  jb      short loc_14000DA87
0x14000da48  mov     edx, 26h ; '&'
0x14000da4d  jmp     short loc_14000DA73
0x14000da4f  lea     rax, WPP_GLOBAL_Control
0x14000da56  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da5d  cmp     rcx, rax
0x14000da60  jz      short loc_14000DA87
0x14000da62  test    byte ptr [rcx+44h], 2
0x14000da66  jz      short loc_14000DA87
0x14000da68  cmp     byte ptr [rcx+41h], 2
0x14000da6c  jb      short loc_14000DA87
0x14000da6e  mov     edx, 27h ; '''
0x14000da73  mov     r9d, ebx
0x14000da76  lea     r8, WPP_3a4fffaa845934d8edf59f75967dfe07_Traceguids
0x14000da7d  mov     rcx, [rcx+38h]
0x14000da81  call    WPP_SF_d
0x14000da86  nop
0x14000da87  lea     rcx, [rbp+arg_10]
0x14000da8b  call    ??1?$CComPtr@UIHTMLFormElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(void)
0x14000da90  nop
0x14000da91  lea     rcx, [rbp+ppIUriBuilder]
0x14000da95  call    ??1?$CComPtr@UIHTMLFormElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(void)
0x14000da9a  nop
0x14000da9b  lea     rcx, [rbp+ppURI]
0x14000da9f  call    ??1?$CComPtr@UIHTMLFormElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(void)
0x14000daa4  mov     eax, ebx
0x14000daa6  add     rsp, 30h
0x14000daaa  pop     rdi
0x14000daab  pop     rbx
0x14000daac  pop     rbp
0x14000daad  retn
```
