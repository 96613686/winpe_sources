# GetWMI_Win32_Processor(IEnumWbemClassObject * *)

- ea: `0x18001a604`
- end: `0x18001a7c3`
- name: `?GetWMI_Win32_Processor@@YAJPEAPEAUIEnumWbemClassObject@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(struct IEnumWbemClassObject **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019874`
- `0x18001a074`

## callees

- `0x18001a604`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001a65f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a6f3`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a703`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a65f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a6f3`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a703`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a77a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a783`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a79c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a77a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a783`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a79c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001a6da`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001a6da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a641`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a641`

## pseudocode

```c
__int64 __fastcall GetWMI_Win32_Processor(struct IEnumWbemClassObject **a1)
{
  HRESULT v2; // ebx
  OLECHAR *v3; // rsi
  OLECHAR *v4; // r14
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  IUnknown *pProxy; // [rsp+90h] [rbp+40h] BYREF
  __int64 v9; // [rsp+98h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp+50h] BYREF

  *a1 = 0;
  ppv = 0;
  v2 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &ppv);
  if ( v2 >= 0 )
  {
    v2 = -2147024882;
    v3 = SysAllocString(L"root\\cimv2");
    if ( v3 )
    {
      pProxy = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
             ppv,
             v3,
             0,
             0,
             0,
             0,
             0,
             0,
             &pProxy);
      if ( v2 >= 0 )
      {
        v2 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
        if ( v2 >= 0 )
        {
          v2 = -2147024882;
          v4 = SysAllocString(L"WQL");
          v5 = SysAllocString(L"select MaxClockSpeed from Win32_Processor");
          v6 = v5;
          if ( v4 )
          {
            if ( v5 )
            {
              v9 = 0;
              v2 = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, BSTR, __int64, _QWORD, __int64 *))pProxy->lpVtbl[6].Release)(
                     pProxy,
                     v4,
                     v5,
                     48,
                     0,
                     &v9);
              if ( v2 >= 0 )
              {
                v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEnumWbemClassObject **))v9)(
                       v9,
                       &GUID_027947e1_d731_11ce_a357_000000000001,
                       a1);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
              }
            }
          }
          SysFreeString(v6);
          SysFreeString(v4);
        }
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      }
      SysFreeString(v3);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001a604  push    rbp
0x18001a606  push    rbx
0x18001a607  push    rsi
0x18001a608  push    rdi
0x18001a609  push    r12
0x18001a60b  push    r14
0x18001a60d  push    r15
0x18001a60f  mov     rbp, rsp
0x18001a612  sub     rsp, 50h
0x18001a616  xor     r12d, r12d
0x18001a619  lea     rax, [rbp+arg_10]
0x18001a61d  mov     r15, rcx
0x18001a620  mov     [rcx], r12
0x18001a623  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x18001a62a  mov     [rbp+arg_10], r12
0x18001a62e  xor     edx, edx; pUnkOuter
0x18001a630  mov     [rsp+50h+ppv], rax; ppv
0x18001a635  lea     r8d, [r12+1]; dwClsContext
0x18001a63a  lea     rcx, CLSID_WbemLocator; rclsid
0x18001a641  call    cs:__imp_CoCreateInstance
0x18001a647  mov     ebx, eax
0x18001a649  test    eax, eax
0x18001a64b  js      loc_18001A7B2
0x18001a651  mov     edi, 8007000Eh
0x18001a656  lea     rcx, aRootCimv2; "root\\cimv2"
0x18001a65d  mov     ebx, edi
0x18001a65f  call    cs:__imp_SysAllocString
0x18001a665  mov     rsi, rax
0x18001a668  test    rax, rax
0x18001a66b  jz      loc_18001A7A2
0x18001a671  mov     rcx, [rbp+arg_10]
0x18001a675  xor     r9d, r9d
0x18001a678  mov     [rbp+pProxy], r12
0x18001a67c  xor     r8d, r8d
0x18001a67f  mov     rdx, [rcx]
0x18001a682  mov     rax, [rdx+18h]
0x18001a686  lea     rdx, [rbp+pProxy]
0x18001a68a  mov     [rsp+50h+var_10], rdx
0x18001a68f  mov     rdx, rsi
0x18001a692  mov     qword ptr [rsp+50h+dwCapabilities], r12
0x18001a697  mov     [rsp+50h+pAuthInfo], r12
0x18001a69c  mov     [rsp+50h+dwImpLevel], r12d
0x18001a6a1  mov     [rsp+50h+ppv], r12
0x18001a6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6ab  mov     ebx, eax
0x18001a6ad  test    eax, eax
0x18001a6af  js      loc_18001A799
0x18001a6b5  mov     rcx, [rbp+pProxy]; pProxy
0x18001a6b9  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001a6bc  mov     [rsp+50h+dwCapabilities], r12d; dwCapabilities
0x18001a6c1  mov     r8d, edx; dwAuthzSvc
0x18001a6c4  mov     [rsp+50h+pAuthInfo], r12; pAuthInfo
0x18001a6c9  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001a6cd  mov     [rsp+50h+dwImpLevel], 3; dwImpLevel
0x18001a6d5  mov     dword ptr [rsp+50h+ppv], r12d; dwAuthnLevel
0x18001a6da  call    cs:__imp_CoSetProxyBlanket
0x18001a6e0  mov     ebx, eax
0x18001a6e2  test    eax, eax
0x18001a6e4  js      loc_18001A789
0x18001a6ea  lea     rcx, aWql; "WQL"
0x18001a6f1  mov     ebx, edi
0x18001a6f3  call    cs:__imp_SysAllocString
0x18001a6f9  lea     rcx, aSelectMaxclock; "select MaxClockSpeed from Win32_Process"...
0x18001a700  mov     r14, rax
0x18001a703  call    cs:__imp_SysAllocString
0x18001a709  mov     rdi, rax
0x18001a70c  test    r14, r14
0x18001a70f  jz      short loc_18001A777
0x18001a711  test    rax, rax
0x18001a714  jz      short loc_18001A777
0x18001a716  mov     rcx, [rbp+pProxy]
0x18001a71a  lea     r9d, [r12+30h]
0x18001a71f  mov     [rbp+arg_8], r12
0x18001a723  mov     r8, rdi
0x18001a726  mov     rdx, [rcx]
0x18001a729  mov     rax, [rdx+0A0h]
0x18001a730  lea     rdx, [rbp+arg_8]
0x18001a734  mov     qword ptr [rsp+50h+dwImpLevel], rdx
0x18001a739  mov     rdx, r14
0x18001a73c  mov     [rsp+50h+ppv], r12
0x18001a741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a746  mov     ebx, eax
0x18001a748  test    eax, eax
0x18001a74a  js      short loc_18001A777
0x18001a74c  mov     rcx, [rbp+arg_8]
0x18001a750  lea     rdx, _GUID_027947e1_d731_11ce_a357_000000000001
0x18001a757  mov     r8, r15
0x18001a75a  mov     rax, [rcx]
0x18001a75d  mov     rax, [rax]
0x18001a760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a765  mov     rcx, [rbp+arg_8]
0x18001a769  mov     ebx, eax
0x18001a76b  mov     rax, [rcx]
0x18001a76e  mov     rax, [rax+10h]
0x18001a772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a777  mov     rcx, rdi; bstrString
0x18001a77a  call    cs:__imp_SysFreeString
0x18001a780  mov     rcx, r14; bstrString
0x18001a783  call    cs:__imp_SysFreeString
0x18001a789  mov     rcx, [rbp+pProxy]
0x18001a78d  mov     rax, [rcx]
0x18001a790  mov     rax, [rax+10h]
0x18001a794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a799  mov     rcx, rsi; bstrString
0x18001a79c  call    cs:__imp_SysFreeString
0x18001a7a2  mov     rcx, [rbp+arg_10]
0x18001a7a6  mov     rax, [rcx]
0x18001a7a9  mov     rax, [rax+10h]
0x18001a7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7b2  mov     eax, ebx
0x18001a7b4  add     rsp, 50h
0x18001a7b8  pop     r15
0x18001a7ba  pop     r14
0x18001a7bc  pop     r12
0x18001a7be  pop     rdi
0x18001a7bf  pop     rsi
0x18001a7c0  pop     rbx
0x18001a7c1  pop     rbp
0x18001a7c2  retn
```
