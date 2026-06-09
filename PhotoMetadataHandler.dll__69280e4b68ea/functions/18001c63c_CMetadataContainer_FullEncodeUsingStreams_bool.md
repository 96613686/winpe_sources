# CMetadataContainer::_FullEncodeUsingStreams(bool)

- ea: `0x18001c63c`
- end: `0x18001c8ec`
- name: `?_FullEncodeUsingStreams@CMetadataContainer@@AEAAJ_N@Z`
- size: `688`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001c518`

## callees

- `0x1800053bc`
- `0x180005440`
- `0x180008b54`
- `0x180016a40`
- `0x180017408`
- `0x18001bacc`
- `0x18001c63c`
- `0x180020ae0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c824`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c824`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001c6a2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001c6a2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001c8b7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001c8b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMetadataContainer::_FullEncodeUsingStreams(CMetadataContainer *this, bool a2)
{
  HRESULT TemporaryFilePath; // ebx
  int v5; // eax
  __int64 v6; // rbx
  __int64 v7; // rdx
  IStream *ppstm; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+70h] [rbp-90h]
  WCHAR pszFile[264]; // [rsp+B0h] [rbp-50h] BYREF

  ppstm = 0;
  memset_0(pszFile, 0, 0x208u);
  TemporaryFilePath = GetTemporaryFilePath(pszFile);
  if ( TemporaryFilePath >= 0 )
  {
    TemporaryFilePath = SHCreateStreamOnFileW(pszFile, 2u, &ppstm);
    if ( TemporaryFilePath >= 0 )
    {
      TemporaryFilePath = CMetadataContainer::_DoFullEncodeUsingTempStream(this, ppstm, a2);
      if ( TemporaryFilePath < 0 )
      {
LABEL_17:
        v10 = 0;
        ((void (__fastcall *)(IStream *, _QWORD))ppstm->lpVtbl->SetSize)(ppstm, 0);
        ATL::CComPtrBase<IStream>::Release(&ppstm);
        DeleteFileW(pszFile);
        goto LABEL_18;
      }
      ATL::CComPtrBase<IWICComponentFactory>::Release((char *)this + 8);
      memset_0(v14, 0, 0x50u);
      v11 = 0;
      v12 = 0;
      v5 = ((__int64 (__fastcall *)(IStream *, _BYTE *, __int64))ppstm->lpVtbl->Stat)(ppstm, v14, 1);
      v6 = v12;
      if ( v5 >= 0 )
      {
        v7 = v15;
        v11 = v15;
      }
      else
      {
        if ( ((int (__fastcall *)(IStream *, __int64, __int64, __int64 *))ppstm->lpVtbl->Seek)(ppstm, v12, 2, &v11) < 0 )
        {
LABEL_13:
          ppv[0] = 0;
          TemporaryFilePath = CoCreateInstance(
                                &CLSID_WICImagingFactory2,
                                0,
                                1u,
                                &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                                ppv);
          if ( TemporaryFilePath >= 0 )
          {
            v10 = 0;
            TemporaryFilePath = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)this + 40LL))(
                                  *(_QWORD *)this,
                                  0,
                                  0,
                                  0);
            if ( TemporaryFilePath >= 0 )
              TemporaryFilePath = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)ppv[0] + 32LL))(
                                    ppv[0],
                                    *(_QWORD *)this,
                                    0,
                                    0,
                                    (char *)this + 8);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppv);
          goto LABEL_17;
        }
        v7 = v11;
      }
      if ( (*(int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)this + 48LL))(*(_QWORD *)this, v7) >= 0
        && ((int (__fastcall *)(IStream *, __int64, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, v6, 0, 0) >= 0
        && (*(int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)this + 40LL))(
             *(_QWORD *)this,
             v6,
             0,
             0) >= 0 )
      {
        v10 = 0;
        v12 = 0;
        if ( ((int (__fastcall *)(IStream *, _QWORD, __int64, __int64 *, __int64 *))ppstm->lpVtbl->CopyTo)(
               ppstm,
               *(_QWORD *)this,
               v11,
               &v10,
               &v12) >= 0 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 64LL))(*(_QWORD *)this, 0);
      }
      goto LABEL_13;
    }
  }
LABEL_18:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  return (unsigned int)TemporaryFilePath;
}

```

## disassembly

```asm
0x18001c63c  push    rbp
0x18001c63e  push    rbx
0x18001c63f  push    rsi
0x18001c640  push    rdi
0x18001c641  lea     rbp, [rsp-1D8h]
0x18001c649  sub     rsp, 2D8h
0x18001c650  mov     rax, cs:__security_cookie
0x18001c657  xor     rax, rsp
0x18001c65a  mov     [rbp+1F0h+var_30], rax
0x18001c661  mov     sil, dl
0x18001c664  mov     rdi, rcx
0x18001c667  mov     [rsp+2F0h+ppstm], 0
0x18001c670  xor     edx, edx; Val
0x18001c672  mov     r8d, 208h; Size
0x18001c678  lea     rcx, [rbp+1F0h+pszFile]; void *
0x18001c67c  call    memset_0
0x18001c681  lea     rcx, [rbp+1F0h+pszFile]; lpTempFileName
0x18001c685  call    ?GetTemporaryFilePath@@YAJPEAG@Z; GetTemporaryFilePath(ushort *)
0x18001c68a  mov     ebx, eax
0x18001c68c  test    eax, eax
0x18001c68e  js      loc_18001C8C4
0x18001c694  lea     r8, [rsp+2F0h+ppstm]; ppstm
0x18001c699  mov     edx, 2; grfMode
0x18001c69e  lea     rcx, [rbp+1F0h+pszFile]; pszFile
0x18001c6a2  call    cs:__imp_SHCreateStreamOnFileW
0x18001c6a9  nop     dword ptr [rax+rax+00h]
0x18001c6ae  mov     ebx, eax
0x18001c6b0  test    eax, eax
0x18001c6b2  js      loc_18001C8C4
0x18001c6b8  mov     r8b, sil; bool
0x18001c6bb  mov     rdx, [rsp+2F0h+ppstm]; struct IStream *
0x18001c6c0  mov     rcx, rdi; this
0x18001c6c3  call    ?_DoFullEncodeUsingTempStream@CMetadataContainer@@AEAAJPEAUIStream@@_N@Z; CMetadataContainer::_DoFullEncodeUsingTempStream(IStream *,bool)
0x18001c6c8  mov     ebx, eax
0x18001c6ca  test    eax, eax
0x18001c6cc  js      loc_18001C88A
0x18001c6d2  lea     rsi, [rdi+8]
0x18001c6d6  mov     rcx, rsi
0x18001c6d9  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x18001c6de  xor     edx, edx; Val
0x18001c6e0  lea     r8d, [rdx+50h]; Size
0x18001c6e4  lea     rcx, [rsp+2F0h+var_290]; void *
0x18001c6e9  call    memset_0
0x18001c6ee  mov     [rsp+2F0h+var_2B0], 0
0x18001c6f7  mov     [rsp+2F0h+var_2A8], 0
0x18001c700  mov     rcx, [rsp+2F0h+ppstm]
0x18001c705  mov     rax, [rcx]
0x18001c708  mov     r8d, 1
0x18001c70e  lea     rdx, [rsp+2F0h+var_290]
0x18001c713  mov     rax, [rax+60h]
0x18001c717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c71c  mov     rbx, [rsp+2F0h+var_2A8]
0x18001c721  test    eax, eax
0x18001c723  jns     short loc_18001C753
0x18001c725  mov     rcx, [rsp+2F0h+ppstm]
0x18001c72a  mov     rax, [rcx]
0x18001c72d  lea     r9, [rsp+2F0h+var_2B0]
0x18001c732  mov     r8d, 2
0x18001c738  mov     rdx, rbx
0x18001c73b  mov     rax, [rax+28h]
0x18001c73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c744  test    eax, eax
0x18001c746  js      loc_18001C7FD
0x18001c74c  mov     rdx, [rsp+2F0h+var_2B0]
0x18001c751  jmp     short loc_18001C75D
0x18001c753  mov     rdx, [rsp+2F0h+var_280]
0x18001c758  mov     [rsp+2F0h+var_2B0], rdx
0x18001c75d  mov     rcx, [rdi]
0x18001c760  mov     rax, [rcx]
0x18001c763  mov     rax, [rax+30h]
0x18001c767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c76c  test    eax, eax
0x18001c76e  js      loc_18001C7FD
0x18001c774  mov     rcx, [rsp+2F0h+ppstm]
0x18001c779  mov     rax, [rcx]
0x18001c77c  xor     r9d, r9d
0x18001c77f  xor     r8d, r8d
0x18001c782  mov     rdx, rbx
0x18001c785  mov     rax, [rax+28h]
0x18001c789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c78e  test    eax, eax
0x18001c790  js      short loc_18001C7FD
0x18001c792  mov     rcx, [rdi]
0x18001c795  mov     rax, [rcx]
0x18001c798  xor     r9d, r9d
0x18001c79b  xor     r8d, r8d
0x18001c79e  mov     rdx, rbx
0x18001c7a1  mov     rax, [rax+28h]
0x18001c7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7aa  test    eax, eax
0x18001c7ac  js      short loc_18001C7FD
0x18001c7ae  mov     [rsp+2F0h+var_2B8], 0
0x18001c7b7  mov     [rsp+2F0h+var_2A8], 0
0x18001c7c0  mov     rcx, [rsp+2F0h+ppstm]
0x18001c7c5  mov     rax, [rcx]
0x18001c7c8  lea     rdx, [rsp+2F0h+var_2A8]
0x18001c7cd  mov     [rsp+2F0h+ppv], rdx
0x18001c7d2  lea     r9, [rsp+2F0h+var_2B8]
0x18001c7d7  mov     r8, [rsp+2F0h+var_2B0]
0x18001c7dc  mov     rdx, [rdi]
0x18001c7df  mov     rax, [rax+38h]
0x18001c7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7e8  test    eax, eax
0x18001c7ea  js      short loc_18001C7FD
0x18001c7ec  mov     rcx, [rdi]
0x18001c7ef  mov     rax, [rcx]
0x18001c7f2  xor     edx, edx
0x18001c7f4  mov     rax, [rax+40h]
0x18001c7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7fd  mov     [rsp+2F0h+var_2A0], 0
0x18001c806  lea     rax, [rsp+2F0h+var_2A0]
0x18001c80b  mov     [rsp+2F0h+ppv], rax; ppv
0x18001c810  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18001c817  xor     edx, edx; pUnkOuter
0x18001c819  lea     r8d, [rdx+1]; dwClsContext
0x18001c81d  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18001c824  call    cs:__imp_CoCreateInstance
0x18001c82b  nop     dword ptr [rax+rax+00h]
0x18001c830  mov     ebx, eax
0x18001c832  test    eax, eax
0x18001c834  js      short loc_18001C880
0x18001c836  mov     [rsp+2F0h+var_2B8], 0
0x18001c83f  mov     rcx, [rdi]
0x18001c842  mov     rax, [rcx]
0x18001c845  xor     r9d, r9d
0x18001c848  xor     r8d, r8d
0x18001c84b  mov     rdx, [rsp+2F0h+var_2B8]
0x18001c850  mov     rax, [rax+28h]
0x18001c854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c859  mov     ebx, eax
0x18001c85b  test    eax, eax
0x18001c85d  js      short loc_18001C880
0x18001c85f  mov     rcx, [rsp+2F0h+var_2A0]
0x18001c864  mov     rax, [rcx]
0x18001c867  mov     [rsp+2F0h+ppv], rsi
0x18001c86c  xor     r9d, r9d
0x18001c86f  xor     r8d, r8d
0x18001c872  mov     rdx, [rdi]
0x18001c875  mov     rax, [rax+20h]
0x18001c879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c87e  mov     ebx, eax
0x18001c880  lea     rcx, [rsp+2F0h+var_2A0]
0x18001c885  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c88a  mov     [rsp+2F0h+var_2B8], 0
0x18001c893  mov     rcx, [rsp+2F0h+ppstm]
0x18001c898  mov     rax, [rcx]
0x18001c89b  mov     rdx, [rsp+2F0h+var_2B8]
0x18001c8a0  mov     rax, [rax+30h]
0x18001c8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8a9  lea     rcx, [rsp+2F0h+ppstm]
0x18001c8ae  call    ?Release@?$CComPtrBase@UIStream@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IStream>::Release(void)
0x18001c8b3  lea     rcx, [rbp+1F0h+pszFile]; lpFileName
0x18001c8b7  call    cs:__imp_DeleteFileW
0x18001c8be  nop     dword ptr [rax+rax+00h]
0x18001c8c3  nop
0x18001c8c4  lea     rcx, [rsp+2F0h+ppstm]
0x18001c8c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c8ce  mov     eax, ebx
0x18001c8d0  mov     rcx, [rbp+1F0h+var_30]
0x18001c8d7  xor     rcx, rsp; StackCookie
0x18001c8da  call    __security_check_cookie
0x18001c8df  add     rsp, 2D8h
0x18001c8e6  pop     rdi
0x18001c8e7  pop     rsi
0x18001c8e8  pop     rbx
0x18001c8e9  pop     rbp
0x18001c8ea  retn
```
