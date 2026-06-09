# CMetadataContainer::_FullEncodeUsingStreams(bool)

- ea: `0x18001b95c`
- end: `0x18001bbf9`
- name: `?_FullEncodeUsingStreams@CMetadataContainer@@AEAAJ_N@Z`
- size: `669`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001b83c`

## callees

- `0x1800052a8`
- `0x180005328`
- `0x180007804`
- `0x180016020`
- `0x1800169b8`
- `0x18001ae18`
- `0x18001b95c`
- `0x18001fb3c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bb3e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bb3e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001b9c2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001b9c2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001bbcb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001bbcb`

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
0x18001b95c  push    rbp
0x18001b95e  push    rbx
0x18001b95f  push    rsi
0x18001b960  push    rdi
0x18001b961  lea     rbp, [rsp-1D8h]
0x18001b969  sub     rsp, 2D8h
0x18001b970  mov     rax, cs:__security_cookie
0x18001b977  xor     rax, rsp
0x18001b97a  mov     [rbp+1F0h+var_30], rax
0x18001b981  mov     sil, dl
0x18001b984  mov     rdi, rcx
0x18001b987  mov     [rsp+2F0h+ppstm], 0
0x18001b990  xor     edx, edx; Val
0x18001b992  mov     r8d, 208h; Size
0x18001b998  lea     rcx, [rbp+1F0h+pszFile]; void *
0x18001b99c  call    memset_0
0x18001b9a1  lea     rcx, [rbp+1F0h+pszFile]; lpTempFileName
0x18001b9a5  call    ?GetTemporaryFilePath@@YAJPEAG@Z; GetTemporaryFilePath(ushort *)
0x18001b9aa  mov     ebx, eax
0x18001b9ac  test    eax, eax
0x18001b9ae  js      loc_18001BBD2
0x18001b9b4  lea     r8, [rsp+2F0h+ppstm]; ppstm
0x18001b9b9  mov     edx, 2; grfMode
0x18001b9be  lea     rcx, [rbp+1F0h+pszFile]; pszFile
0x18001b9c2  call    cs:__imp_SHCreateStreamOnFileW
0x18001b9c8  mov     ebx, eax
0x18001b9ca  test    eax, eax
0x18001b9cc  js      loc_18001BBD2
0x18001b9d2  mov     r8b, sil; bool
0x18001b9d5  mov     rdx, [rsp+2F0h+ppstm]; struct IStream *
0x18001b9da  mov     rcx, rdi; this
0x18001b9dd  call    ?_DoFullEncodeUsingTempStream@CMetadataContainer@@AEAAJPEAUIStream@@_N@Z; CMetadataContainer::_DoFullEncodeUsingTempStream(IStream *,bool)
0x18001b9e2  mov     ebx, eax
0x18001b9e4  test    eax, eax
0x18001b9e6  js      loc_18001BB9E
0x18001b9ec  lea     rsi, [rdi+8]
0x18001b9f0  mov     rcx, rsi
0x18001b9f3  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x18001b9f8  xor     edx, edx; Val
0x18001b9fa  lea     r8d, [rdx+50h]; Size
0x18001b9fe  lea     rcx, [rsp+2F0h+var_290]; void *
0x18001ba03  call    memset_0
0x18001ba08  mov     [rsp+2F0h+var_2B0], 0
0x18001ba11  mov     [rsp+2F0h+var_2A8], 0
0x18001ba1a  mov     rcx, [rsp+2F0h+ppstm]
0x18001ba1f  mov     rax, [rcx]
0x18001ba22  mov     r8d, 1
0x18001ba28  lea     rdx, [rsp+2F0h+var_290]
0x18001ba2d  mov     rax, [rax+60h]
0x18001ba31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba36  mov     rbx, [rsp+2F0h+var_2A8]
0x18001ba3b  test    eax, eax
0x18001ba3d  jns     short loc_18001BA6D
0x18001ba3f  mov     rcx, [rsp+2F0h+ppstm]
0x18001ba44  mov     rax, [rcx]
0x18001ba47  lea     r9, [rsp+2F0h+var_2B0]
0x18001ba4c  mov     r8d, 2
0x18001ba52  mov     rdx, rbx
0x18001ba55  mov     rax, [rax+28h]
0x18001ba59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba5e  test    eax, eax
0x18001ba60  js      loc_18001BB17
0x18001ba66  mov     rdx, [rsp+2F0h+var_2B0]
0x18001ba6b  jmp     short loc_18001BA77
0x18001ba6d  mov     rdx, [rsp+2F0h+var_280]
0x18001ba72  mov     [rsp+2F0h+var_2B0], rdx
0x18001ba77  mov     rcx, [rdi]
0x18001ba7a  mov     rax, [rcx]
0x18001ba7d  mov     rax, [rax+30h]
0x18001ba81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba86  test    eax, eax
0x18001ba88  js      loc_18001BB17
0x18001ba8e  mov     rcx, [rsp+2F0h+ppstm]
0x18001ba93  mov     rax, [rcx]
0x18001ba96  xor     r9d, r9d
0x18001ba99  xor     r8d, r8d
0x18001ba9c  mov     rdx, rbx
0x18001ba9f  mov     rax, [rax+28h]
0x18001baa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baa8  test    eax, eax
0x18001baaa  js      short loc_18001BB17
0x18001baac  mov     rcx, [rdi]
0x18001baaf  mov     rax, [rcx]
0x18001bab2  xor     r9d, r9d
0x18001bab5  xor     r8d, r8d
0x18001bab8  mov     rdx, rbx
0x18001babb  mov     rax, [rax+28h]
0x18001babf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bac4  test    eax, eax
0x18001bac6  js      short loc_18001BB17
0x18001bac8  mov     [rsp+2F0h+var_2B8], 0
0x18001bad1  mov     [rsp+2F0h+var_2A8], 0
0x18001bada  mov     rcx, [rsp+2F0h+ppstm]
0x18001badf  mov     rax, [rcx]
0x18001bae2  lea     rdx, [rsp+2F0h+var_2A8]
0x18001bae7  mov     [rsp+2F0h+ppv], rdx
0x18001baec  lea     r9, [rsp+2F0h+var_2B8]
0x18001baf1  mov     r8, [rsp+2F0h+var_2B0]
0x18001baf6  mov     rdx, [rdi]
0x18001baf9  mov     rax, [rax+38h]
0x18001bafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb02  test    eax, eax
0x18001bb04  js      short loc_18001BB17
0x18001bb06  mov     rcx, [rdi]
0x18001bb09  mov     rax, [rcx]
0x18001bb0c  xor     edx, edx
0x18001bb0e  mov     rax, [rax+40h]
0x18001bb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb17  mov     [rsp+2F0h+var_2A0], 0
0x18001bb20  lea     rax, [rsp+2F0h+var_2A0]
0x18001bb25  mov     [rsp+2F0h+ppv], rax; ppv
0x18001bb2a  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18001bb31  xor     edx, edx; pUnkOuter
0x18001bb33  lea     r8d, [rdx+1]; dwClsContext
0x18001bb37  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18001bb3e  call    cs:__imp_CoCreateInstance
0x18001bb44  mov     ebx, eax
0x18001bb46  test    eax, eax
0x18001bb48  js      short loc_18001BB94
0x18001bb4a  mov     [rsp+2F0h+var_2B8], 0
0x18001bb53  mov     rcx, [rdi]
0x18001bb56  mov     rax, [rcx]
0x18001bb59  xor     r9d, r9d
0x18001bb5c  xor     r8d, r8d
0x18001bb5f  mov     rdx, [rsp+2F0h+var_2B8]
0x18001bb64  mov     rax, [rax+28h]
0x18001bb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb6d  mov     ebx, eax
0x18001bb6f  test    eax, eax
0x18001bb71  js      short loc_18001BB94
0x18001bb73  mov     rcx, [rsp+2F0h+var_2A0]
0x18001bb78  mov     rax, [rcx]
0x18001bb7b  mov     [rsp+2F0h+ppv], rsi
0x18001bb80  xor     r9d, r9d
0x18001bb83  xor     r8d, r8d
0x18001bb86  mov     rdx, [rdi]
0x18001bb89  mov     rax, [rax+20h]
0x18001bb8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb92  mov     ebx, eax
0x18001bb94  lea     rcx, [rsp+2F0h+var_2A0]
0x18001bb99  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bb9e  mov     [rsp+2F0h+var_2B8], 0
0x18001bba7  mov     rcx, [rsp+2F0h+ppstm]
0x18001bbac  mov     rax, [rcx]
0x18001bbaf  mov     rdx, [rsp+2F0h+var_2B8]
0x18001bbb4  mov     rax, [rax+30h]
0x18001bbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbbd  lea     rcx, [rsp+2F0h+ppstm]
0x18001bbc2  call    ?Release@?$CComPtrBase@UIStream@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IStream>::Release(void)
0x18001bbc7  lea     rcx, [rbp+1F0h+pszFile]; lpFileName
0x18001bbcb  call    cs:__imp_DeleteFileW
0x18001bbd1  nop
0x18001bbd2  lea     rcx, [rsp+2F0h+ppstm]
0x18001bbd7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bbdc  mov     eax, ebx
0x18001bbde  mov     rcx, [rbp+1F0h+var_30]
0x18001bbe5  xor     rcx, rsp; StackCookie
0x18001bbe8  call    __security_check_cookie
0x18001bbed  add     rsp, 2D8h
0x18001bbf4  pop     rdi
0x18001bbf5  pop     rsi
0x18001bbf6  pop     rbx
0x18001bbf7  pop     rbp
0x18001bbf8  retn
```
