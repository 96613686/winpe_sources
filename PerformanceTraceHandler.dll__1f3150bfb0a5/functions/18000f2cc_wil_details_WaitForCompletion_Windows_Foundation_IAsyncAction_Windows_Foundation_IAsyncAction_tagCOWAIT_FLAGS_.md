# wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18000f2cc`
- end: `0x18000f406`
- name: `??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012334`

## callees

- `0x180006324`
- `0x180007f3c`
- `0x18000f038`
- `0x18000f2cc`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000f371`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000f371`

## string_xrefs

- `0x18000f333`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        int a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  v14 = a3;
  dwindex = a2;
  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___details_wil__YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___details_wil__YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1608;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v4,
      lpdwindex);
    goto LABEL_14;
  }
  v4 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1609;
    goto LABEL_5;
  }
  pHandles = *(HANDLE *)(v15 + 56);
  dwindex = 0;
  v4 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1621;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(v15 + 48) == 1 )
  {
    v5 = 0;
  }
  else
  {
    v10 = 0;
    v7 = **a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v5 = v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10);
    if ( v5 >= 0 )
    {
      v14 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 64LL))(v10, &v14);
      if ( v5 >= 0 )
        v5 = v14;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f2cc  mov     [rsp-18h+arg_18], r9
0x18000f2d1  mov     [rsp-18h+arg_10], r8d
0x18000f2d6  mov     [rsp-18h+dwindex], edx
0x18000f2da  push    rbp
0x18000f2db  push    rbx
0x18000f2dc  push    rdi
0x18000f2dd  mov     rbp, rsp
0x18000f2e0  sub     rsp, 40h
0x18000f2e4  mov     rdi, rcx
0x18000f2e7  mov     [rbp+arg_18], 0
0x18000f2ef  lea     rcx, [rbp+arg_18]
0x18000f2f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f2f8  lea     rcx, [rbp+arg_18]
0x18000f2fc  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x18000f301  mov     ebx, eax
0x18000f303  test    eax, eax
0x18000f305  jns     short loc_18000F30E
0x18000f307  mov     edx, 648h
0x18000f30c  jmp     short loc_18000F32C
0x18000f30e  mov     rax, [rdi]
0x18000f311  mov     rdx, [rbp+arg_18]
0x18000f315  mov     rcx, rdi
0x18000f318  mov     rax, [rax+30h]
0x18000f31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f321  mov     ebx, eax
0x18000f323  test    eax, eax
0x18000f325  jns     short loc_18000F344
0x18000f327  mov     edx, 649h; void *
0x18000f32c  mov     rcx, [rbp+18h]; this
0x18000f330  mov     r9d, eax; char *
0x18000f333  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f33a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f33f  jmp     loc_18000F3F3
0x18000f344  mov     rax, [rbp+arg_18]
0x18000f348  mov     rcx, [rax+38h]
0x18000f34c  mov     [rbp+pHandles], rcx
0x18000f350  mov     [rbp+dwindex], 0
0x18000f357  lea     rax, [rbp+dwindex]
0x18000f35b  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18000f360  lea     r9, [rbp+pHandles]; pHandles
0x18000f364  mov     r8d, 1; cHandles
0x18000f36a  or      edx, 0FFFFFFFFh; dwTimeout
0x18000f36d  lea     ecx, [r8+7]; dwFlags
0x18000f371  call    cs:__imp_CoWaitForMultipleHandles
0x18000f377  mov     ebx, eax
0x18000f379  test    eax, eax
0x18000f37b  jns     short loc_18000F384
0x18000f37d  mov     edx, 655h
0x18000f382  jmp     short loc_18000F32C
0x18000f384  mov     rax, [rbp+arg_18]
0x18000f388  mov     ecx, [rax+30h]
0x18000f38b  cmp     ecx, 1
0x18000f38e  jz      short loc_18000F3F1
0x18000f390  mov     [rbp+var_10], 0
0x18000f398  mov     rax, [rdi]
0x18000f39b  mov     rbx, [rax]
0x18000f39e  lea     rcx, [rbp+var_10]
0x18000f3a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f3a7  lea     r8, [rbp+var_10]
0x18000f3ab  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000f3b2  mov     rcx, rdi
0x18000f3b5  mov     rax, rbx
0x18000f3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3bd  mov     ebx, eax
0x18000f3bf  test    eax, eax
0x18000f3c1  js      short loc_18000F3E6
0x18000f3c3  mov     [rbp+arg_10], 8000FFFFh
0x18000f3ca  mov     rcx, [rbp+var_10]
0x18000f3ce  mov     rax, [rcx]
0x18000f3d1  lea     rdx, [rbp+arg_10]
0x18000f3d5  mov     rax, [rax+40h]
0x18000f3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3de  mov     ebx, eax
0x18000f3e0  test    eax, eax
0x18000f3e2  cmovns  ebx, [rbp+arg_10]
0x18000f3e6  lea     rcx, [rbp+var_10]
0x18000f3ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f3ef  jmp     short loc_18000F3F3
0x18000f3f1  xor     ebx, ebx
0x18000f3f3  lea     rcx, [rbp+arg_18]
0x18000f3f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f3fc  mov     eax, ebx
0x18000f3fe  add     rsp, 40h
0x18000f402  pop     rdi
0x18000f403  pop     rbx
0x18000f404  pop     rbp
0x18000f405  retn
```
