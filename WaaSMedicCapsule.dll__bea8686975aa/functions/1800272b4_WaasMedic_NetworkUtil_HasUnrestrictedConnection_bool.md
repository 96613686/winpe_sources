# WaasMedic::NetworkUtil::HasUnrestrictedConnection(bool &)

- ea: `0x1800272b4`
- end: `0x1800275d4`
- name: `?HasUnrestrictedConnection@NetworkUtil@WaasMedic@@SAJAEA_N@Z`
- size: `800`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000d5e0`
- `0x1800387e0`
- `0x180051c80`

## callees

- `0x180009a54`
- `0x18002543c`
- `0x1800272b4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800272fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002748d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800272fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002748d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaasMedic::NetworkUtil::HasUnrestrictedConnection(bool *a1)
{
  __int64 (__fastcall ***v2)(LPVOID, GUID *, __int64 *); // r9
  void (*v3)(void); // rax
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // edi
  int v8; // esi
  bool v9; // r14
  HRESULT v10; // eax
  int v11; // edi
  int v12; // eax
  LPVOID v13; // rcx
  int ppv; // [rsp+20h] [rbp-20h]
  LPVOID v15; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v17; // [rsp+70h] [rbp+30h] BYREF
  int v18; // [rsp+78h] [rbp+38h] BYREF
  __int64 v19; // [rsp+80h] [rbp+40h] BYREF
  LPVOID v20; // [rsp+88h] [rbp+48h] BYREF

  v18 = 0;
  *a1 = 0;
  v19 = 0;
  v20 = 0;
  CoCreateInstance(&GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &v20);
  v2 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v20;
  if ( !v20 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\networkutil.cpp",
      (const char *)0x80004003LL,
      ppv);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    if ( !v19 )
      return 2147500035LL;
    v3 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
LABEL_19:
    v3();
    return 2147500035LL;
  }
  v4 = v19;
  v19 = 0;
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    v2 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v20;
  }
  v5 = (**v2)(v2, &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b, &v19);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\networkutil.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return v6;
  }
  if ( !v19 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\networkutil.cpp",
      (const char *)0x80004003LL,
      ppv);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    if ( !v19 )
      return 2147500035LL;
    v3 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
    goto LABEL_19;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v19 + 24LL))(v19, &v18, 0);
  if ( v8 == -2147024846 )
  {
    v9 = 0;
    v17 = 0;
    v15 = 0;
    v10 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &v15);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v15 + 104LL))(v15, &v17);
      v11 = v12;
      if ( v12 >= 0 )
        v9 = (v17 & 0x440) != 0;
      else
        LogLevelW(2u, L"Failed to GetConnectivity status. hr = 0x%08x.", (unsigned int)v12);
    }
    else
    {
      LogLevelW(2u, L"Failed CCI on INetworkListManager. hr = 0x%08x.", (unsigned int)v10);
    }
    v13 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
    }
    if ( v11 >= 0 && v9 )
    {
      *a1 = 1;
      LogLevelW(5u, L"Unrestricted network present. GetCost = 0x%08x, IsInternetConnected = %d", 2147942450LL, v9);
LABEL_44:
      if ( v20 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      return 0;
    }
    goto LABEL_42;
  }
  if ( v8 < 0 )
  {
LABEL_42:
    *a1 = 0;
    if ( v8 == -2147023674 )
    {
      LogLevelW(4u, L"INetworkCostManager::GetCost returned ERROR_NO_NETWORK.");
      goto LABEL_44;
    }
    goto LABEL_36;
  }
  if ( v18 )
  {
    *a1 = 1;
    LogLevelW(5u, L"Unrestricted network present. Cost: %d");
    goto LABEL_44;
  }
  *a1 = 0;
LABEL_36:
  if ( v20 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800272b4  push    rbp
0x1800272b6  push    rbx
0x1800272b7  push    rsi
0x1800272b8  push    rdi
0x1800272b9  push    r14
0x1800272bb  mov     rbp, rsp
0x1800272be  sub     rsp, 40h
0x1800272c2  mov     rbx, rcx
0x1800272c5  mov     [rbp+arg_8], 0
0x1800272cc  mov     byte ptr [rcx], 0
0x1800272cf  mov     [rbp+arg_10], 0
0x1800272d7  mov     [rbp+arg_18], 0
0x1800272df  lea     rax, [rbp+arg_18]
0x1800272e3  mov     qword ptr [rsp+40h+ppv], rax; int
0x1800272e8  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x1800272ef  xor     edx, edx; pUnkOuter
0x1800272f1  lea     r8d, [rdx+1]; dwClsContext
0x1800272f5  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x1800272fc  call    cs:__imp_CoCreateInstance
0x180027302  nop
0x180027303  mov     r9, [rbp+arg_18]
0x180027307  test    r9, r9
0x18002730a  jnz     short loc_180027357
0x18002730c  mov     rcx, [rbp+28h]; this
0x180027310  mov     r9d, 80004003h; char *
0x180027316  lea     r8, aOnecoreEnduser_32; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002731d  mov     edx, 43h ; 'C'; void *
0x180027322  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027327  nop
0x180027328  mov     rcx, [rbp+arg_18]
0x18002732c  test    rcx, rcx
0x18002732f  jz      short loc_18002733E
0x180027331  mov     rax, [rcx]
0x180027334  mov     rax, [rax+10h]
0x180027338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002733d  nop
0x18002733e  mov     rcx, [rbp+arg_10]
0x180027342  test    rcx, rcx
0x180027345  jz      loc_180027434
0x18002734b  mov     rax, [rcx]
0x18002734e  mov     rax, [rax+10h]
0x180027352  jmp     loc_18002742E
0x180027357  mov     rcx, [rbp+arg_10]
0x18002735b  mov     [rbp+arg_10], 0
0x180027363  test    rcx, rcx
0x180027366  jz      short loc_180027378
0x180027368  mov     rax, [rcx]
0x18002736b  mov     rax, [rax+10h]
0x18002736f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027374  mov     r9, [rbp+arg_18]
0x180027378  mov     rax, [r9]
0x18002737b  lea     r8, [rbp+arg_10]
0x18002737f  lea     rdx, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b
0x180027386  mov     rcx, r9
0x180027389  mov     rax, [rax]
0x18002738c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027391  mov     edi, eax
0x180027393  test    eax, eax
0x180027395  jns     short loc_1800273E3
0x180027397  mov     rcx, [rbp+28h]; this
0x18002739b  mov     r9d, eax; char *
0x18002739e  lea     r8, aOnecoreEnduser_32; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800273a5  mov     edx, 44h ; 'D'; void *
0x1800273aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800273af  nop
0x1800273b0  mov     rcx, [rbp+arg_18]
0x1800273b4  test    rcx, rcx
0x1800273b7  jz      short loc_1800273C6
0x1800273b9  mov     rax, [rcx]
0x1800273bc  mov     rax, [rax+10h]
0x1800273c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273c5  nop
0x1800273c6  mov     rcx, [rbp+arg_10]
0x1800273ca  test    rcx, rcx
0x1800273cd  jz      short loc_1800273DC
0x1800273cf  mov     rax, [rcx]
0x1800273d2  mov     rax, [rax+10h]
0x1800273d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273db  nop
0x1800273dc  mov     eax, edi
0x1800273de  jmp     loc_180027566
0x1800273e3  mov     rcx, [rbp+arg_10]
0x1800273e7  test    rcx, rcx
0x1800273ea  jnz     short loc_18002743E
0x1800273ec  mov     rcx, [rbp+28h]; this
0x1800273f0  mov     r9d, 80004003h; char *
0x1800273f6  lea     r8, aOnecoreEnduser_32; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800273fd  mov     edx, 45h ; 'E'; void *
0x180027402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027407  nop
0x180027408  mov     rcx, [rbp+arg_18]
0x18002740c  test    rcx, rcx
0x18002740f  jz      short loc_18002741E
0x180027411  mov     rax, [rcx]
0x180027414  mov     rax, [rax+10h]
0x180027418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002741d  nop
0x18002741e  mov     rcx, [rbp+arg_10]
0x180027422  test    rcx, rcx
0x180027425  jz      short loc_180027434
0x180027427  mov     rdx, [rcx]
0x18002742a  mov     rax, [rdx+10h]
0x18002742e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027433  nop
0x180027434  mov     eax, 80004003h
0x180027439  jmp     loc_180027566
0x18002743e  mov     rax, [rcx]
0x180027441  xor     r8d, r8d
0x180027444  lea     rdx, [rbp+arg_8]
0x180027448  mov     rax, [rax+18h]
0x18002744c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027451  mov     esi, eax
0x180027453  cmp     eax, 80070032h
0x180027458  jnz     loc_180027528
0x18002745e  xor     r14b, r14b
0x180027461  mov     [rbp+arg_0], 0
0x180027468  mov     [rbp+var_10], 0
0x180027470  lea     rax, [rbp+var_10]
0x180027474  mov     qword ptr [rsp+40h+ppv], rax; ppv
0x180027479  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x180027480  xor     edx, edx; pUnkOuter
0x180027482  lea     r8d, [rdx+1]; dwClsContext
0x180027486  lea     rcx, CLSID_NetworkListManager; rclsid
0x18002748d  call    cs:__imp_CoCreateInstance
0x180027493  mov     edi, eax
0x180027495  test    eax, eax
0x180027497  jns     short loc_1800274AF
0x180027499  lea     rdx, aFailedCciOnIne; "Failed CCI on INetworkListManager. hr ="...
0x1800274a0  mov     r8d, eax
0x1800274a3  mov     ecx, 2; unsigned __int8
0x1800274a8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800274ad  jmp     short loc_1800274DD
0x1800274af  mov     rcx, [rbp+var_10]
0x1800274b3  mov     rax, [rcx]
0x1800274b6  lea     rdx, [rbp+arg_0]
0x1800274ba  mov     rax, [rax+68h]
0x1800274be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274c3  mov     edi, eax
0x1800274c5  test    eax, eax
0x1800274c7  jns     short loc_1800274D2
0x1800274c9  lea     rdx, aFailedToGetcon; "Failed to GetConnectivity status. hr = "...
0x1800274d0  jmp     short loc_1800274A0
0x1800274d2  test    [rbp+arg_0], 440h
0x1800274d9  setnz   r14b
0x1800274dd  mov     rcx, [rbp+var_10]
0x1800274e1  test    rcx, rcx
0x1800274e4  jz      short loc_1800274FB
0x1800274e6  mov     [rbp+var_10], 0
0x1800274ee  mov     rax, [rcx]
0x1800274f1  mov     rax, [rax+10h]
0x1800274f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274fa  nop
0x1800274fb  test    edi, edi
0x1800274fd  js      loc_180027587
0x180027503  test    r14b, r14b
0x180027506  jz      short loc_180027587
0x180027508  mov     byte ptr [rbx], 1
0x18002750b  movzx   r9d, r14b
0x18002750f  mov     r8d, 80070032h
0x180027515  lea     rdx, aUnrestrictedNe; "Unrestricted network present. GetCost ="...
0x18002751c  mov     ecx, 5; unsigned __int8
0x180027521  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027526  jmp     short loc_1800275A4
0x180027528  test    esi, esi
0x18002752a  js      short loc_180027587
0x18002752c  mov     r8d, [rbp+arg_8]
0x180027530  test    r8d, r8d
0x180027533  jnz     short loc_180027571
0x180027535  mov     [rbx], r8b
0x180027538  mov     rcx, [rbp+arg_18]
0x18002753c  test    rcx, rcx
0x18002753f  jz      short loc_18002754E
0x180027541  mov     rax, [rcx]
0x180027544  mov     rax, [rax+10h]
0x180027548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002754d  nop
0x18002754e  mov     rcx, [rbp+arg_10]
0x180027552  test    rcx, rcx
0x180027555  jz      short loc_180027564
0x180027557  mov     rax, [rcx]
0x18002755a  mov     rax, [rax+10h]
0x18002755e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027563  nop
0x180027564  mov     eax, esi
0x180027566  add     rsp, 40h
0x18002756a  pop     r14
0x18002756c  pop     rdi
0x18002756d  pop     rsi
0x18002756e  pop     rbx
0x18002756f  pop     rbp
0x180027570  retn
0x180027571  mov     byte ptr [rbx], 1
0x180027574  lea     rdx, aUnrestrictedNe_0; "Unrestricted network present. Cost: %d"
0x18002757b  mov     ecx, 5; unsigned __int8
0x180027580  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027585  jmp     short loc_1800275A4
0x180027587  mov     byte ptr [rbx], 0
0x18002758a  cmp     esi, 800704C6h
0x180027590  jnz     short loc_180027538
0x180027592  lea     rdx, aInetworkcostma; "INetworkCostManager::GetCost returned E"...
0x180027599  mov     ecx, 4; unsigned __int8
0x18002759e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800275a3  nop
0x1800275a4  mov     rcx, [rbp+arg_18]
0x1800275a8  test    rcx, rcx
0x1800275ab  jz      short loc_1800275BA
0x1800275ad  mov     rax, [rcx]
0x1800275b0  mov     rax, [rax+10h]
0x1800275b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275b9  nop
0x1800275ba  mov     rcx, [rbp+arg_10]
0x1800275be  test    rcx, rcx
0x1800275c1  jz      short loc_1800275D0
0x1800275c3  mov     rax, [rcx]
0x1800275c6  mov     rax, [rax+10h]
0x1800275ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275cf  nop
0x1800275d0  xor     eax, eax
0x1800275d2  jmp     short loc_180027566
```
