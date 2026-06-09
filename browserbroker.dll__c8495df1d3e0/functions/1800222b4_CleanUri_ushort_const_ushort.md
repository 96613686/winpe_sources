# CleanUri(ushort const *,ushort * *)

- ea: `0x1800222b4`
- end: `0x18002238b`
- name: `?CleanUri@@YAJPEBGPEAPEAG@Z`
- size: `215`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022120`
- `0x180022bdc`
- `0x180023260`
- `0x180024070`

## callees

- `0x180006cc4`
- `0x1800214c8`
- `0x1800222b4`
- `0x18002d010`

## import_xrefs

- `iertutil!CreateUri` at `0x1800222ed`
- `iertutil!CreateUri` at `0x1800222ed`
- `urlmon!CreateIUriBuilder` at `0x180022306`
- `urlmon!CreateIUriBuilder` at `0x180022306`

## pseudocode

```c
__int64 __fastcall CleanUri(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  IUriBuilder *ppIUriBuilder; // [rsp+58h] [rbp+28h] BYREF
  __int64 v6; // [rsp+60h] [rbp+30h] BYREF
  IUri *ppURI; // [rsp+68h] [rbp+38h] BYREF

  ppURI = 0;
  ppIUriBuilder = 0;
  v6 = 0;
  *a2 = 0;
  v3 = CreateUri(a1, 0x3002B80u, 0, &ppURI);
  if ( v3 >= 0 )
  {
    v3 = CreateIUriBuilder(ppURI, 0, 0, &ppIUriBuilder);
    if ( v3 >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(IUriBuilder *, __int64))ppIUriBuilder->lpVtbl->RemoveProperties)(
             ppIUriBuilder,
             83376);
      if ( v3 >= 0 )
      {
        v3 = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD, _QWORD, __int64 *))ppIUriBuilder->lpVtbl->CreateUriSimple)(
               ppIUriBuilder,
               0,
               0,
               &v6);
        if ( v3 >= 0 )
          v3 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v6 + 56LL))(v6, a2);
      }
    }
  }
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(&v6);
  ATL::CComPtr<IUriBuilder>::~CComPtr<IUriBuilder>((__int64 *)&ppIUriBuilder);
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppURI);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800222b4  push    rbp
0x1800222b6  push    rbx
0x1800222b7  push    rdi
0x1800222b8  mov     rbp, rsp
0x1800222bb  sub     rsp, 30h
0x1800222bf  mov     rdi, rdx
0x1800222c2  mov     [rbp+ppURI], 0
0x1800222ca  mov     [rbp+ppIUriBuilder], 0
0x1800222d2  mov     [rbp+arg_10], 0
0x1800222da  mov     qword ptr [rdx], 0
0x1800222e1  lea     r9, [rbp+ppURI]; ppURI
0x1800222e5  xor     r8d, r8d; dwReserved
0x1800222e8  mov     edx, 3002B80h; dwFlags
0x1800222ed  call    cs:__imp_CreateUri
0x1800222f3  mov     ebx, eax
0x1800222f5  test    eax, eax
0x1800222f7  js      short loc_180022364
0x1800222f9  lea     r9, [rbp+ppIUriBuilder]; ppIUriBuilder
0x1800222fd  xor     r8d, r8d; dwReserved
0x180022300  xor     edx, edx; dwFlags
0x180022302  mov     rcx, [rbp+ppURI]; pIUri
0x180022306  call    cs:__imp_CreateIUriBuilder
0x18002230c  mov     ebx, eax
0x18002230e  test    eax, eax
0x180022310  js      short loc_180022364
0x180022312  mov     rcx, [rbp+ppIUriBuilder]
0x180022316  mov     rax, [rcx]
0x180022319  mov     edx, 145B0h
0x18002231e  mov     rax, [rax+0C0h]
0x180022325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002232a  mov     ebx, eax
0x18002232c  test    eax, eax
0x18002232e  js      short loc_180022364
0x180022330  mov     rcx, [rbp+ppIUriBuilder]
0x180022334  mov     rax, [rcx]
0x180022337  lea     r9, [rbp+arg_10]
0x18002233b  xor     r8d, r8d
0x18002233e  xor     edx, edx
0x180022340  mov     rax, [rax+18h]
0x180022344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022349  mov     ebx, eax
0x18002234b  test    eax, eax
0x18002234d  js      short loc_180022364
0x18002234f  mov     rcx, [rbp+arg_10]
0x180022353  mov     rax, [rcx]
0x180022356  mov     rdx, rdi
0x180022359  mov     rax, [rax+38h]
0x18002235d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022362  mov     ebx, eax
0x180022364  lea     rcx, [rbp+arg_10]
0x180022368  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18002236d  nop
0x18002236e  lea     rcx, [rbp+ppIUriBuilder]
0x180022372  call    ??1?$CComPtr@UIUriBuilder@@@ATL@@QEAA@XZ; ATL::CComPtr<IUriBuilder>::~CComPtr<IUriBuilder>(void)
0x180022377  nop
0x180022378  lea     rcx, [rbp+ppURI]
0x18002237c  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180022381  mov     eax, ebx
0x180022383  add     rsp, 30h
0x180022387  pop     rdi
0x180022388  pop     rbx
0x180022389  pop     rbp
0x18002238a  retn
```
