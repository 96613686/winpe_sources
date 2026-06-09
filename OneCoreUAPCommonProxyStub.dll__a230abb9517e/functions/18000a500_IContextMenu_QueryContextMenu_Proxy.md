# IContextMenu_QueryContextMenu_Proxy

- ea: `0x18000a500`
- end: `0x18000a7a3`
- name: `IContextMenu_QueryContextMenu_Proxy`
- size: `675`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002670`
- `0x1800033f8`
- `0x180003518`
- `0x180003760`
- `0x1800045ba`
- `0x180005880`
- `0x1800069ec`
- `0x180006a58`
- `0x1800073e8`
- `0x18000a500`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000a5e1`
- `RPCRT4!NdrClientCall3` at `0x18000a5e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a75c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a75c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a776`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a72d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a72d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IContextMenu_QueryContextMenu_Proxy(__int64 a1, int a2, __int64 a3, int a4, int a5)
{
  int Pointer; // ebx
  unsigned int v8; // r8d
  int v9; // eax
  void *v10; // rcx
  unsigned __int64 v11; // r8
  __int64 v12; // rdi
  unsigned int v13; // r8d
  const char *v14; // r9
  void *v15; // rcx
  void *v16; // rcx
  __int64 result; // rax
  int v18; // [rsp+60h] [rbp-C8h] BYREF
  LPVOID v19; // [rsp+68h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-B8h] BYREF
  void *v21[2]; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+88h] [rbp-A0h]
  void *p_pv; // [rsp+90h] [rbp-98h] BYREF
  LPVOID *v24; // [rsp+98h] [rbp-90h]
  char v25; // [rsp+A0h] [rbp-88h]
  _BYTE v26[120]; // [rsp+B0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v18 = 0;
  v19 = 0;
  pv = 0;
  ContextMenuRemoteProxyProvider::WatchCurrentThread(v26, "QueryContextMenu_Proxy");
  p_pv = &pv;
  v24 = 0;
  v25 = 1;
  v21[0] = &v19;
  v21[1] = 0;
  LOBYTE(v22) = 1;
  try
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1801FD350, 3u, 0).Pointer;
    wil::details::out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v21);
    wil::details::out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    p_pv = &v18;
    v24 = &v19;
    v25 = 1;
    if ( Pointer < 0 )
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x32E, v8, (const char *)(unsigned int)Pointer, a2);
    v9 = v18;
    if ( v18 && v19 && pv )
    {
      if ( (unsigned __int8)IsDeleteObjectPresent(retaddr) )
      {
        *(_OWORD *)v21 = 0;
        v22 = 0;
        ReplaceOOPBitmaps(a2, a4, a5, v18, (__int64)v19, (unsigned int *)pv, (__int64)v21);
        v10 = v21[0];
        v11 = (unsigned __int64)((char *)v21[1] - (char *)v21[0] + 7) >> 3;
        if ( v21[0] > v21[1] )
          v11 = 0;
        if ( v11 )
        {
          memset_0(v21[0], 0, 8 * v11);
          v10 = v21[0];
        }
        if ( v10 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>();
          std::_Deallocate<16>(v21[0], (v22 - (unsigned __int64)v21[0]) & 0xFFFFFFFFFFFFFFF8uLL);
        }
      }
      v9 = v18;
    }
    if ( v9 && v19 )
    {
      v12 = 0;
      do
      {
        CloseHandle(*((HANDLE *)v19 + v12));
        v12 = (unsigned int)(v12 + 1);
      }
      while ( (unsigned int)v12 < v18 );
    }
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v26);
    v15 = pv;
    pv = 0;
    if ( v15 )
      CoTaskMemFree(v15);
    v16 = v19;
    v19 = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    result = (unsigned int)Pointer;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x340, v13, v14);
  }
  return result;
}

```

## disassembly

```asm
0x18000a500  mov     rax, rsp
0x18000a503  push    rbx
0x18000a504  push    rsi
0x18000a505  push    rdi
0x18000a506  push    r14
0x18000a508  push    r15
0x18000a50a  sub     rsp, 100h
0x18000a511  mov     edi, r9d
0x18000a514  mov     ebx, r8d
0x18000a517  mov     rsi, rdx
0x18000a51a  mov     r14, rcx
0x18000a51d  mov     [rsp+128h+var_C8], 0
0x18000a525  mov     [rsp+128h+var_C0], 0
0x18000a52e  mov     [rsp+128h+pv], 0
0x18000a537  lea     rdx, aQuerycontextme_0; "QueryContextMenu_Proxy"
0x18000a53e  lea     rcx, [rax-78h]
0x18000a542  call    ?WatchCurrentThread@ContextMenuRemoteProxyProvider@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; ContextMenuRemoteProxyProvider::WatchCurrentThread(char const *)
0x18000a547  nop
0x18000a548  lea     rax, [rsp+128h+pv]
0x18000a54d  mov     [rsp+128h+var_98], rax
0x18000a555  mov     [rsp+128h+var_90], 0
0x18000a561  mov     [rsp+128h+var_88], 1
0x18000a569  lea     rax, [rsp+128h+var_C0]
0x18000a56e  mov     [rsp+128h+var_B0], rax
0x18000a573  mov     [rsp+128h+var_B0+8], 0
0x18000a57f  mov     byte ptr [rsp+128h+var_A0], 1
0x18000a587  lea     rax, [rsp+128h+var_90]
0x18000a58f  mov     [rsp+128h+var_D0], rax
0x18000a594  lea     rax, [rsp+128h+var_B0+8]
0x18000a59c  mov     [rsp+128h+var_D8], rax
0x18000a5a1  lea     rax, [rsp+128h+var_C8]
0x18000a5a6  mov     [rsp+128h+var_E0], rax
0x18000a5ab  mov     eax, [rsp+128h+arg_28]
0x18000a5b2  mov     [rsp+128h+var_E8], eax
0x18000a5b6  mov     r15d, [rsp+128h+arg_20]
0x18000a5be  mov     [rsp+128h+var_F0], r15d
0x18000a5c3  mov     dword ptr [rsp+128h+var_F8], edi
0x18000a5c7  mov     dword ptr [rsp+128h+var_100], ebx
0x18000a5cb  mov     [rsp+128h+var_108], rsi; int
0x18000a5d0  mov     r9, r14
0x18000a5d3  xor     r8d, r8d; pReturnValue
0x18000a5d6  lea     edx, [r8+3]; nProcNum
0x18000a5da  lea     rcx, stru_1801FD350; pProxyInfo
0x18000a5e1  call    cs:__imp_NdrClientCall3
0x18000a5e7  mov     rbx, rax
0x18000a5ea  lea     rcx, [rsp+128h+var_B0]
0x18000a5ef  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@PEAXU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18000a5f4  nop
0x18000a5f5  lea     rcx, [rsp+128h+var_98]
0x18000a5fd  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@PEAXU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18000a602  lea     rax, [rsp+128h+var_C8]
0x18000a607  mov     [rsp+128h+var_98], rax
0x18000a60f  lea     rax, [rsp+128h+var_C0]
0x18000a614  mov     [rsp+128h+var_90], rax
0x18000a61c  mov     [rsp+128h+var_88], 1
0x18000a624  mov     rcx, [rsp+128h]; this
0x18000a62c  test    ebx, ebx
0x18000a62e  js      loc_18000A794
0x18000a634  mov     eax, [rsp+128h+var_C8]
0x18000a638  test    eax, eax
0x18000a63a  jz      loc_18000A712
0x18000a640  cmp     [rsp+128h+var_C0], 0
0x18000a646  jz      loc_18000A712
0x18000a64c  cmp     [rsp+128h+pv], 0
0x18000a652  jz      loc_18000A712
0x18000a658  call    IsDeleteObjectPresent
0x18000a65d  test    al, al
0x18000a65f  jz      loc_18000A70E
0x18000a665  xorps   xmm0, xmm0
0x18000a668  movdqu  xmmword ptr [rsp+128h+var_B0], xmm0
0x18000a66e  mov     [rsp+128h+var_A0], 0
0x18000a67a  lea     rax, [rsp+128h+var_B0]
0x18000a67f  mov     [rsp+128h+var_F8], rax; __int64
0x18000a684  mov     rax, [rsp+128h+pv]
0x18000a689  mov     [rsp+128h+var_100], rax; unsigned int *
0x18000a68e  mov     rax, [rsp+128h+var_C0]
0x18000a693  mov     [rsp+128h+var_108], rax; __int64
0x18000a698  mov     r9d, [rsp+128h+var_C8]; int
0x18000a69d  mov     r8d, r15d; int
0x18000a6a0  mov     edx, edi; int
0x18000a6a2  mov     rcx, rsi; int
0x18000a6a5  call    ?ReplaceOOPBitmaps@@YAXPEAUHMENU__@@IIIPEBQEAXPEBKPEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@Z; ReplaceOOPBitmaps(HMENU__ *,uint,uint,uint,void * const *,ulong const *,std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>> *)
0x18000a6aa  mov     rcx, [rsp+128h+var_B0]; void *
0x18000a6af  mov     rdx, [rsp+128h+var_B0+8]
0x18000a6b7  mov     r8, rdx
0x18000a6ba  sub     r8, rcx
0x18000a6bd  add     r8, 7
0x18000a6c1  shr     r8, 3
0x18000a6c5  xor     eax, eax
0x18000a6c7  cmp     rcx, rdx
0x18000a6ca  cmova   r8, rax
0x18000a6ce  test    r8, r8
0x18000a6d1  jz      short loc_18000A6EB
0x18000a6d3  shl     r8, 3; Size
0x18000a6d7  xor     edx, edx; Val
0x18000a6d9  call    memset_0
0x18000a6de  mov     rdx, [rsp+128h+var_B0+8]
0x18000a6e6  mov     rcx, [rsp+128h+var_B0]
0x18000a6eb  test    rcx, rcx
0x18000a6ee  jz      short loc_18000A70E
0x18000a6f0  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>> &)
0x18000a6f5  mov     rcx, [rsp+128h+var_B0]
0x18000a6fa  mov     rdx, [rsp+128h+var_A0]
0x18000a702  sub     rdx, rcx
0x18000a705  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000a709  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a70e  mov     eax, [rsp+128h+var_C8]
0x18000a712  test    eax, eax
0x18000a714  jz      short loc_18000A73B
0x18000a716  cmp     [rsp+128h+var_C0], 0
0x18000a71c  jz      short loc_18000A73B
0x18000a71e  xor     edi, edi
0x18000a720  test    eax, eax
0x18000a722  jz      short loc_18000A73B
0x18000a724  mov     rcx, [rsp+128h+var_C0]
0x18000a729  mov     rcx, [rcx+rdi*8]; hObject
0x18000a72d  call    cs:__imp_CloseHandle
0x18000a733  inc     edi
0x18000a735  cmp     edi, [rsp+128h+var_C8]
0x18000a739  jb      short loc_18000A724
0x18000a73b  lea     rcx, [rsp+128h+var_78]; this
0x18000a743  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18000a748  nop
0x18000a749  mov     rcx, [rsp+128h+pv]; pv
0x18000a74e  mov     [rsp+128h+pv], 0
0x18000a757  test    rcx, rcx
0x18000a75a  jz      short loc_18000A763
0x18000a75c  call    cs:__imp_CoTaskMemFree
0x18000a762  nop
0x18000a763  mov     rcx, [rsp+128h+var_C0]; pv
0x18000a768  mov     [rsp+128h+var_C0], 0
0x18000a771  test    rcx, rcx
0x18000a774  jz      short loc_18000A77D
0x18000a776  call    cs:__imp_CoTaskMemFree
0x18000a77c  nop
0x18000a77d  mov     eax, ebx
0x18000a77f  jmp     short loc_18000A785
0x18000a781  mov     eax, [rsp+128h+var_C8]
0x18000a785  add     rsp, 100h
0x18000a78c  pop     r15
0x18000a78e  pop     r14
0x18000a790  pop     rdi
0x18000a791  pop     rsi
0x18000a792  pop     rbx
0x18000a793  retn
0x18000a794  mov     r9d, ebx; char *
0x18000a797  mov     edx, 32Eh; void *
0x18000a79c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
