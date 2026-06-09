# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18004249c`
- end: `0x180042631`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004518c`

## callees

- `0x18001fa00`
- `0x180041c08`
- `0x18004249c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180042546`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180042546`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  int v4; // ebx
  char v5; // bl
  int (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v10; // [rsp+70h] [rbp+20h] BYREF
  HRESULT v11; // [rsp+78h] [rbp+28h] BYREF
  __int64 dwindex; // [rsp+80h] [rbp+30h] BYREF
  __int64 v13; // [rsp+88h] [rbp+38h] BYREF

  dwindex = a3;
  v11 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v13);
  v11 = v4;
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v13);
    v11 = v4;
    if ( v4 >= 0 )
    {
      pHandles[0] = *(HANDLE *)(v13 + 56);
      pHandles[1] = 0;
      v5 = 0;
      LODWORD(dwindex) = 0;
      v11 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
      if ( v11 >= 0 && (_DWORD)dwindex )
      {
        v11 = -2147023673;
        v5 = 1;
      }
      v10 = 0;
      if ( v5 )
      {
        v6 = **a1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        if ( v6(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 72LL))(v10);
      }
      if ( v11 >= 0 && *(_DWORD *)(v13 + 48) != 1 )
      {
        if ( v10
          || (v7 = **a1,
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10),
              v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10) >= 0) )
        {
          (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v10 + 64LL))(v10, &v11);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      v4 = v11;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004249c  mov     [rsp-18h+dwindex], r8
0x1800424a1  mov     [rsp-18h+arg_8], edx
0x1800424a5  push    rbp
0x1800424a6  push    rbx
0x1800424a7  push    rdi
0x1800424a8  mov     rbp, rsp
0x1800424ab  sub     rsp, 50h
0x1800424af  mov     rdi, rcx
0x1800424b2  mov     [rbp+var_20], rcx
0x1800424b6  test    rcx, rcx
0x1800424b9  jz      short loc_1800424C8
0x1800424bb  mov     rax, [rcx]
0x1800424be  mov     rax, [rax+8]
0x1800424c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424c7  nop
0x1800424c8  mov     [rbp+arg_18], 0
0x1800424d0  lea     rcx, [rbp+arg_18]
0x1800424d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800424d9  lea     rcx, [rbp+arg_18]
0x1800424dd  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x1800424e2  mov     ebx, eax
0x1800424e4  mov     [rbp+arg_8], eax
0x1800424e7  test    eax, eax
0x1800424e9  js      loc_180042608
0x1800424ef  mov     rax, [rdi]
0x1800424f2  mov     rdx, [rbp+arg_18]
0x1800424f6  mov     rcx, rdi
0x1800424f9  mov     rax, [rax+30h]
0x1800424fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042502  mov     ebx, eax
0x180042504  mov     [rbp+arg_8], eax
0x180042507  test    eax, eax
0x180042509  js      loc_180042608
0x18004250f  mov     rax, [rbp+arg_18]
0x180042513  mov     rcx, [rax+38h]
0x180042517  mov     [rbp+pHandles], rcx
0x18004251b  mov     [rbp+var_10], 0
0x180042523  xor     bl, bl
0x180042525  mov     dword ptr [rbp+dwindex], 0
0x18004252c  lea     rax, [rbp+dwindex]
0x180042530  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180042535  lea     r9, [rbp+pHandles]; pHandles
0x180042539  mov     r8d, 1; cHandles
0x18004253f  or      edx, 0FFFFFFFFh; dwTimeout
0x180042542  lea     ecx, [r8+7]; dwFlags
0x180042546  call    cs:__imp_CoWaitForMultipleHandles
0x18004254c  mov     [rbp+arg_8], eax
0x18004254f  test    eax, eax
0x180042551  js      short loc_180042562
0x180042553  cmp     dword ptr [rbp+dwindex], 0
0x180042557  jz      short loc_180042562
0x180042559  mov     [rbp+arg_8], 800704C7h
0x180042560  mov     bl, 1
0x180042562  mov     [rbp+arg_0], 0
0x18004256a  test    bl, bl
0x18004256c  jz      short loc_1800425A7
0x18004256e  mov     rax, [rdi]
0x180042571  mov     rbx, [rax]
0x180042574  lea     rcx, [rbp+arg_0]
0x180042578  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004257d  lea     r8, [rbp+arg_0]
0x180042581  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180042588  mov     rcx, rdi
0x18004258b  mov     rax, rbx
0x18004258e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042593  test    eax, eax
0x180042595  js      short loc_1800425A7
0x180042597  mov     rcx, [rbp+arg_0]
0x18004259b  mov     rax, [rcx]
0x18004259e  mov     rax, [rax+48h]
0x1800425a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425a7  cmp     [rbp+arg_8], 0
0x1800425ab  jl      short loc_1800425FC
0x1800425ad  mov     rax, [rbp+arg_18]
0x1800425b1  cmp     dword ptr [rax+30h], 1
0x1800425b5  jz      short loc_1800425FC
0x1800425b7  cmp     [rbp+arg_0], 0
0x1800425bc  jnz     short loc_1800425E7
0x1800425be  mov     rax, [rdi]
0x1800425c1  mov     rbx, [rax]
0x1800425c4  lea     rcx, [rbp+arg_0]
0x1800425c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800425cd  lea     r8, [rbp+arg_0]
0x1800425d1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800425d8  mov     rcx, rdi
0x1800425db  mov     rax, rbx
0x1800425de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425e3  test    eax, eax
0x1800425e5  js      short loc_1800425FC
0x1800425e7  mov     rcx, [rbp+arg_0]
0x1800425eb  mov     rax, [rcx]
0x1800425ee  lea     rdx, [rbp+arg_8]
0x1800425f2  mov     rax, [rax+40h]
0x1800425f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425fb  nop
0x1800425fc  lea     rcx, [rbp+arg_0]
0x180042600  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042605  mov     ebx, [rbp+arg_8]
0x180042608  lea     rcx, [rbp+arg_18]
0x18004260c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042611  nop
0x180042612  test    rdi, rdi
0x180042615  jz      short loc_180042627
0x180042617  mov     rcx, [rdi]
0x18004261a  mov     rax, [rcx+10h]
0x18004261e  mov     rcx, rdi
0x180042621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042626  nop
0x180042627  mov     eax, ebx
0x180042629  add     rsp, 50h
0x18004262d  pop     rdi
0x18004262e  pop     rbx
0x18004262f  pop     rbp
0x180042630  retn
```
