# Wallet::Utils::GetApplicationInfoFromAppProductId(ushort const *,ATL::CComPtr<IPMApplicationInfo> &)

- ea: `0x1800381e4`
- end: `0x18003831e`
- name: `?GetApplicationInfoFromAppProductId@Utils@Wallet@@YAJPEBGAEAV?$CComPtr@UIPMApplicationInfo@@@ATL@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(const OLECHAR *, __int64 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d944`
- `0x180037fe4`
- `0x180038120`

## callees

- `0x180008cc0`
- `0x18002d048`
- `0x1800381e4`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038269`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038269`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18003821b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18003821b`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::GetApplicationInfoFromAppProductId(const OLECHAR *a1, __int64 *a2)
{
  HRESULT Instance; // ebx
  LPVOID v5; // rbx
  __int64 (__fastcall *v6)(LPVOID, GUID *, __int64 *); // rbp
  __int64 v7; // rcx
  LPVOID ppv[2]; // [rsp+30h] [rbp-58h] BYREF
  GUID v10; // [rsp+40h] [rbp-48h] BYREF
  GUID iid; // [rsp+50h] [rbp-38h] BYREF

  iid = 0;
  ppv[0] = 0;
  Instance = IIDFromString(a1, &iid);
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_PMSvc, 0, 0x17u, &IID_IPMEnumerationManager, ppv);
    if ( Instance >= 0 )
    {
      v5 = ppv[0];
      if ( ppv[0] )
      {
        v6 = *(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)ppv[0] + 72LL);
        v7 = *a2;
        if ( *a2 )
        {
          *a2 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        v10 = iid;
        Instance = v6(v5, &v10, a2);
        if ( Instance >= 0 )
        {
          Instance = 0;
          goto LABEL_10;
        }
      }
      else
      {
        Instance = -2147024882;
      }
    }
  }
  wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(
    0,
    "Wallet::Utils::GetApplicationInfoFromAppProductId",
    2154,
    "Product id %S, hr 0x%x",
    (const char *)a1,
    Instance);
LABEL_10:
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800381e4  mov     [rsp+arg_10], rbx
0x1800381e9  push    rbp
0x1800381ea  push    rsi
0x1800381eb  push    rdi
0x1800381ec  sub     rsp, 70h
0x1800381f0  mov     rax, cs:__security_cookie
0x1800381f7  xor     rax, rsp
0x1800381fa  mov     [rsp+88h+var_28], rax
0x1800381ff  mov     rdi, rdx
0x180038202  mov     rsi, rcx
0x180038205  xorps   xmm0, xmm0
0x180038208  movups  xmmword ptr [rsp+88h+iid.Data1], xmm0
0x18003820d  mov     [rsp+88h+var_58], 0
0x180038216  lea     rdx, [rsp+88h+iid]; lpiid
0x18003821b  call    cs:__imp_IIDFromString
0x180038221  mov     ebx, eax
0x180038223  test    eax, eax
0x180038225  js      loc_1800382CD
0x18003822b  mov     rcx, [rsp+88h+var_58]
0x180038230  test    rcx, rcx
0x180038233  jz      short loc_18003824B
0x180038235  mov     [rsp+88h+var_58], 0
0x18003823e  mov     rax, [rcx]
0x180038241  mov     rax, [rax+10h]
0x180038245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003824a  nop
0x18003824b  lea     rax, [rsp+88h+var_58]
0x180038250  mov     [rsp+88h+ppv], rax; ppv
0x180038255  lea     r9, IID_IPMEnumerationManager; riid
0x18003825c  xor     edx, edx; pUnkOuter
0x18003825e  lea     r8d, [rdx+17h]; dwClsContext
0x180038262  lea     rcx, CLSID_PMSvc; rclsid
0x180038269  call    cs:__imp_CoCreateInstance
0x18003826f  mov     ebx, eax
0x180038271  test    eax, eax
0x180038273  js      short loc_1800382CD
0x180038275  mov     rbx, [rsp+88h+var_58]
0x18003827a  test    rbx, rbx
0x18003827d  jnz     short loc_180038286
0x18003827f  mov     ebx, 8007000Eh
0x180038284  jmp     short loc_1800382CD
0x180038286  mov     rax, [rbx]
0x180038289  mov     rbp, [rax+48h]
0x18003828d  mov     rcx, [rdi]
0x180038290  test    rcx, rcx
0x180038293  jz      short loc_1800382A9
0x180038295  mov     qword ptr [rdi], 0
0x18003829c  mov     rax, [rcx]
0x18003829f  mov     rax, [rax+10h]
0x1800382a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382a8  nop
0x1800382a9  movaps  xmm0, xmmword ptr [rsp+88h+iid.Data1]
0x1800382ae  movdqa  [rsp+88h+var_48], xmm0
0x1800382b4  mov     r8, rdi
0x1800382b7  lea     rdx, [rsp+88h+var_48]
0x1800382bc  mov     rcx, rbx
0x1800382bf  mov     rax, rbp
0x1800382c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382c7  mov     ebx, eax
0x1800382c9  test    eax, eax
0x1800382cb  jns     short loc_1800382F3
0x1800382cd  mov     [rsp+88h+var_60], ebx
0x1800382d1  mov     [rsp+88h+ppv], rsi
0x1800382d6  lea     r9, aProductIdSHr0x; "Product id %S, hr 0x%x"
0x1800382dd  mov     r8d, 86Ah
0x1800382e3  lea     rdx, aWalletUtilsGet; "Wallet::Utils::GetApplicationInfoFromAp"...
0x1800382ea  xor     ecx, ecx
0x1800382ec  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800382f1  jmp     short loc_1800382F5
0x1800382f3  xor     ebx, ebx
0x1800382f5  lea     rcx, [rsp+88h+var_58]
0x1800382fa  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x1800382ff  mov     eax, ebx
0x180038301  mov     rcx, [rsp+88h+var_28]
0x180038306  xor     rcx, rsp; StackCookie
0x180038309  call    __security_check_cookie
0x18003830e  mov     rbx, [rsp+88h+arg_10]
0x180038316  add     rsp, 70h
0x18003831a  pop     rdi
0x18003831b  pop     rsi
0x18003831c  pop     rbp
0x18003831d  retn
```
