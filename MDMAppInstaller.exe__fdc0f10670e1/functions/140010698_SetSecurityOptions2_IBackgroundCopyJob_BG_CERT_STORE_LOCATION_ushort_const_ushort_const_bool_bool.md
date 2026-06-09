# SetSecurityOptions2(IBackgroundCopyJob *,BG_CERT_STORE_LOCATION,ushort const *,ushort const *,bool,bool)

- ea: `0x140010698`
- end: `0x140010963`
- name: `?SetSecurityOptions2@@YAJPEAUIBackgroundCopyJob@@W4BG_CERT_STORE_LOCATION@@PEBG2_N3@Z`
- size: `715`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, bool, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140010a2c`

## callees

- `0x1400056a4`
- `0x14000904c`
- `0x140010698`
- `0x140018140`
- `0x14001878c`
- `0x14001c010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400107b8`
- `KERNEL32!GetProcessHeap` at `0x1400107b8`
- `KERNEL32!HeapAlloc` at `0x1400107c9`
- `KERNEL32!HeapAlloc` at `0x1400107c9`
- `ole32!CoSetProxyBlanket` at `0x140010724`
- `ole32!CoSetProxyBlanket` at `0x140010724`

## pseudocode

```c
__int64 __fastcall SetSecurityOptions2(
        struct IBackgroundCopyJob *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        bool a6)
{
  int v8; // ebx
  HRESULT v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  int v14; // [rsp+58h] [rbp-9h] BYREF
  unsigned int v15; // [rsp+5Ch] [rbp-5h] BYREF
  unsigned int v16; // [rsp+60h] [rbp-1h] BYREF
  IUnknown *pProxy; // [rsp+68h] [rbp+7h] BYREF
  __int64 v18; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+78h] [rbp+17h] BYREF
  __int64 v20; // [rsp+80h] [rbp+1Fh] BYREF
  SIZE_T dwBytes[2]; // [rsp+88h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+4Fh]
  unsigned int v23; // [rsp+B8h] [rbp+57h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+67h] BYREF

  v24 = a3;
  pProxy = 0;
  *(_OWORD *)dwBytes = 0;
  if ( !a1 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_24;
  }
  v8 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, IUnknown **))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_f1bd1079_9f01_4bdc_8036_f09b70095066,
         &pProxy);
  if ( v8 < 0 )
    goto LABEL_24;
  v9 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
  v8 = v9;
  if ( v9 >= 0 )
  {
    LODWORD(v24) = 0;
    v8 = ((__int64 (__fastcall *)(IUnknown *, const unsigned __int16 **))pProxy->lpVtbl[3].AddRef)(pProxy, &v24);
    if ( v8 < 0 )
      goto LABEL_24;
    v10 = a5 ? (unsigned int)v24 | 1 : (unsigned int)v24 & 0xFFFFFFFE;
    LODWORD(v24) = v10;
    v8 = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[3].QueryInterface)(pProxy);
    if ( v8 < 0 )
      goto LABEL_24;
    v8 = HexStringToBinary(a4, 0, dwBytes);
    if ( v8 < 0 )
      goto LABEL_24;
    v11 = dwBytes[0];
    ProcessHeap = GetProcessHeap();
    dwBytes[1] = (SIZE_T)HeapAlloc(ProcessHeap, 8u, v11);
    if ( dwBytes[1] )
    {
      v8 = HexStringToBinary(a4, dwBytes[1], dwBytes);
      if ( v8 < 0 )
        goto LABEL_24;
      v8 = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].Release)(pProxy);
      if ( v8 < 0 )
        goto LABEL_24;
      if ( a6 )
      {
        v18 = 0;
        v19 = 0;
        v20 = 0;
        v16 = 0;
        v15 = 0;
        v14 = 0;
        v23 = 0;
        v8 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))pProxy->lpVtbl->QueryInterface)(
               pProxy,
               &GUID_0000013d_0000_0000_c000_000000000046,
               &v18);
        if ( v8 < 0
          || (v8 = (*(__int64 (__fastcall **)(__int64, IUnknown *, unsigned int *, unsigned int *, __int64 *, int *, _QWORD, __int64 *, unsigned int *))(*(_QWORD *)v18 + 24LL))(
                     v18,
                     pProxy,
                     &v16,
                     &v15,
                     &v20,
                     &v14,
                     0,
                     &v19,
                     &v23),
              v8 < 0)
          || (v23 = v23 & 0xFFFFFF9F | 0x40,
              v8 = (*(__int64 (__fastcall **)(__int64, IUnknown *, _QWORD, _QWORD, __int64, int, int, __int64, unsigned int))(*(_QWORD *)v18 + 32LL))(
                     v18,
                     pProxy,
                     v16,
                     v15,
                     v20,
                     v14,
                     3,
                     v19,
                     v23),
              v8 < 0) )
        {
          ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v18);
          goto LABEL_24;
        }
        ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v18);
      }
      v8 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, const wchar_t *, SIZE_T))pProxy->lpVtbl[1].QueryInterface)(
             pProxy,
             a2,
             L"MY",
             dwBytes[1]);
      goto LABEL_24;
    }
    v8 = -2147024882;
LABEL_24:
    SafeHeapFree((void *)dwBytes[1]);
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4C1,
    (int)"admin\\enterprisemgmt\\desktopappcsps\\sharedlib\\jobexecution.cpp",
    (const char *)(unsigned int)v9);
LABEL_25:
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>((__int64 *)&pProxy);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140010698  mov     rax, rsp
0x14001069b  mov     [rax+10h], rbx
0x14001069f  mov     [rax+20h], rsi
0x1400106a3  mov     [rax+18h], r8
0x1400106a7  push    rbp
0x1400106a8  push    rdi
0x1400106a9  push    r14
0x1400106ab  lea     rbp, [rax-4Fh]
0x1400106af  sub     rsp, 90h
0x1400106b6  mov     rdi, r9
0x1400106b9  mov     esi, edx
0x1400106bb  xor     r14d, r14d
0x1400106be  mov     [rbp+47h+pProxy], r14
0x1400106c2  xorps   xmm0, xmm0
0x1400106c5  movups  xmmword ptr [rbp+47h+dwBytes], xmm0
0x1400106c9  test    rcx, rcx
0x1400106cc  jnz     short loc_1400106D8
0x1400106ce  mov     ebx, 80070057h
0x1400106d3  jmp     loc_140010936
0x1400106d8  test    rdi, rdi
0x1400106db  jz      short loc_1400106CE
0x1400106dd  mov     rax, [rcx]
0x1400106e0  lea     r8, [rbp+47h+pProxy]
0x1400106e4  lea     rdx, _GUID_f1bd1079_9f01_4bdc_8036_f09b70095066
0x1400106eb  mov     rax, [rax]
0x1400106ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106f3  mov     ebx, eax
0x1400106f5  test    eax, eax
0x1400106f7  js      loc_140010936
0x1400106fd  mov     [rsp+0A0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x140010705  mov     [rsp+0A0h+pAuthInfo], r14; pAuthInfo
0x14001070a  mov     [rsp+0A0h+dwImpLevel], 3; dwImpLevel
0x140010712  mov     [rsp+0A0h+dwAuthnLevel], r14d; int
0x140010717  xor     r9d, r9d; pServerPrincName
0x14001071a  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x14001071d  mov     r8d, edx; dwAuthzSvc
0x140010720  mov     rcx, [rbp+47h+pProxy]; pProxy
0x140010724  call    cs:__imp_CoSetProxyBlanket
0x14001072a  mov     ebx, eax
0x14001072c  test    eax, eax
0x14001072e  jns     short loc_14001074D
0x140010730  mov     rcx, [rbp+4Fh]; this
0x140010734  mov     r9d, eax; char *
0x140010737  lea     r8, aAdminEnterpris; "admin\\enterprisemgmt\\desktopappcsps\\"...
0x14001073e  mov     edx, 4C1h; void *
0x140010743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010748  jmp     loc_140010940
0x14001074d  mov     dword ptr [rbp+47h+arg_10], r14d
0x140010751  mov     rcx, [rbp+47h+pProxy]
0x140010755  mov     rax, [rcx]
0x140010758  lea     rdx, [rbp+47h+arg_10]
0x14001075c  mov     rax, [rax+50h]
0x140010760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010765  mov     ebx, eax
0x140010767  test    eax, eax
0x140010769  js      loc_140010936
0x14001076f  mov     edx, dword ptr [rbp+47h+arg_10]
0x140010772  cmp     [rbp+47h+arg_20], 1
0x140010776  jnz     short loc_14001077D
0x140010778  or      edx, 1
0x14001077b  jmp     short loc_140010780
0x14001077d  and     edx, 0FFFFFFFEh
0x140010780  mov     dword ptr [rbp+47h+arg_10], edx
0x140010783  mov     rcx, [rbp+47h+pProxy]
0x140010787  mov     rax, [rcx]
0x14001078a  mov     rax, [rax+48h]
0x14001078e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010793  mov     ebx, eax
0x140010795  test    eax, eax
0x140010797  js      loc_140010936
0x14001079d  lea     r8, [rbp+47h+dwBytes]
0x1400107a1  xor     edx, edx
0x1400107a3  mov     rcx, rdi
0x1400107a6  call    HexStringToBinary
0x1400107ab  mov     ebx, eax
0x1400107ad  test    eax, eax
0x1400107af  js      loc_140010936
0x1400107b5  mov     ebx, dword ptr [rbp+47h+dwBytes]
0x1400107b8  call    cs:__imp_GetProcessHeap
0x1400107be  mov     rcx, rax; hHeap
0x1400107c1  mov     r8d, ebx; dwBytes
0x1400107c4  mov     edx, 8; dwFlags
0x1400107c9  call    cs:__imp_HeapAlloc
0x1400107cf  mov     [rbp+47h+dwBytes+8], rax
0x1400107d3  test    rax, rax
0x1400107d6  jnz     short loc_1400107E2
0x1400107d8  mov     ebx, 8007000Eh
0x1400107dd  jmp     loc_140010936
0x1400107e2  lea     r8, [rbp+47h+dwBytes]
0x1400107e6  mov     rdx, [rbp+47h+dwBytes+8]
0x1400107ea  mov     rcx, rdi
0x1400107ed  call    HexStringToBinary
0x1400107f2  mov     ebx, eax
0x1400107f4  test    eax, eax
0x1400107f6  js      loc_140010936
0x1400107fc  mov     rcx, [rbp+47h+pProxy]
0x140010800  mov     rax, [rcx]
0x140010803  mov     rax, [rax+28h]
0x140010807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001080c  mov     ebx, eax
0x14001080e  test    eax, eax
0x140010810  js      loc_140010936
0x140010816  cmp     [rbp+47h+arg_28], r14b
0x14001081a  jz      loc_140010917
0x140010820  mov     [rbp+47h+var_38], r14
0x140010824  mov     [rbp+47h+var_30], r14
0x140010828  mov     [rbp+47h+var_28], r14
0x14001082c  mov     [rbp+47h+var_48], r14d
0x140010830  mov     [rbp+47h+var_4C], r14d
0x140010834  mov     [rbp+47h+var_50], r14d
0x140010838  mov     [rbp+47h+arg_0], r14d
0x14001083c  mov     rcx, [rbp+47h+pProxy]
0x140010840  mov     rax, [rcx]
0x140010843  lea     r8, [rbp+47h+var_38]
0x140010847  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x14001084e  mov     rax, [rax]
0x140010851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010856  mov     ebx, eax
0x140010858  test    eax, eax
0x14001085a  jns     short loc_14001086A
0x14001085c  lea     rcx, [rbp+47h+var_38]
0x140010860  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x140010865  jmp     loc_140010936
0x14001086a  mov     rcx, [rbp+47h+var_38]
0x14001086e  mov     rax, [rcx]
0x140010871  lea     rdx, [rbp+47h+arg_0]
0x140010875  mov     [rsp+0A0h+var_60], rdx
0x14001087a  lea     rdx, [rbp+47h+var_30]
0x14001087e  mov     qword ptr [rsp+0A0h+dwCapabilities], rdx
0x140010883  mov     [rsp+0A0h+pAuthInfo], r14
0x140010888  lea     rdx, [rbp+47h+var_50]
0x14001088c  mov     qword ptr [rsp+0A0h+dwImpLevel], rdx
0x140010891  lea     rdx, [rbp+47h+var_28]
0x140010895  mov     qword ptr [rsp+0A0h+dwAuthnLevel], rdx
0x14001089a  lea     r9, [rbp+47h+var_4C]
0x14001089e  lea     r8, [rbp+47h+var_48]
0x1400108a2  mov     rdx, [rbp+47h+pProxy]
0x1400108a6  mov     rax, [rax+18h]
0x1400108aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108af  mov     ebx, eax
0x1400108b1  test    eax, eax
0x1400108b3  js      short loc_14001085C
0x1400108b5  mov     edx, [rbp+47h+arg_0]
0x1400108b8  and     edx, 0FFFFFFDFh
0x1400108bb  or      edx, 40h
0x1400108be  mov     [rbp+47h+arg_0], edx
0x1400108c1  mov     rcx, [rbp+47h+var_38]
0x1400108c5  mov     r10, [rbp+47h+var_30]
0x1400108c9  mov     r11d, [rbp+47h+var_50]
0x1400108cd  mov     rbx, [rbp+47h+var_28]
0x1400108d1  mov     rax, [rcx]
0x1400108d4  mov     dword ptr [rsp+0A0h+var_60], edx
0x1400108d8  mov     qword ptr [rsp+0A0h+dwCapabilities], r10
0x1400108dd  mov     dword ptr [rsp+0A0h+pAuthInfo], 3
0x1400108e5  mov     [rsp+0A0h+dwImpLevel], r11d
0x1400108ea  mov     qword ptr [rsp+0A0h+dwAuthnLevel], rbx
0x1400108ef  mov     r9d, [rbp+47h+var_4C]
0x1400108f3  mov     r8d, [rbp+47h+var_48]
0x1400108f7  mov     rdx, [rbp+47h+pProxy]
0x1400108fb  mov     rax, [rax+20h]
0x1400108ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010904  mov     ebx, eax
0x140010906  lea     rcx, [rbp+47h+var_38]
0x14001090a  test    eax, eax
0x14001090c  js      loc_140010860
0x140010912  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x140010917  mov     rcx, [rbp+47h+pProxy]
0x14001091b  mov     rax, [rcx]
0x14001091e  mov     r9, [rbp+47h+dwBytes+8]
0x140010922  lea     r8, aMy; "MY"
0x140010929  mov     edx, esi
0x14001092b  mov     rax, [rax+18h]
0x14001092f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010934  mov     ebx, eax
0x140010936  mov     rcx, [rbp+47h+dwBytes+8]; void *
0x14001093a  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x14001093f  nop
0x140010940  lea     rcx, [rbp+47h+pProxy]
0x140010944  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x140010949  mov     eax, ebx
0x14001094b  lea     r11, [rsp+0A0h+var_10]
0x140010953  mov     rbx, [r11+28h]
0x140010957  mov     rsi, [r11+38h]
0x14001095b  mov     rsp, r11
0x14001095e  pop     r14
0x140010960  pop     rdi
0x140010961  pop     rbp
0x140010962  retn
```
