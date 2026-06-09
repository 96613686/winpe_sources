# _IsUpdateCurrentVersionOnly

- ea: `0x180049794`
- end: `0x180049954`
- name: `_IsUpdateCurrentVersionOnly`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180047e48`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180049794`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800497d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800497d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800498f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004991c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800498f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004991c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180049806`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180049806`

## string_xrefs

- `0x180049819`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004987a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004985b`: `Language Overlay Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IsUpdateCurrentVersionOnly(_BYTE *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  IUnknown *v4; // rcx
  int v6; // eax
  IUnknown *v7; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  bool v9; // bl
  void *v10; // rcx
  void *v11; // rcx
  IUnknown *v12; // rcx
  int ppv; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+48h] [rbp-30h] BYREF
  char v15; // [rsp+50h] [rbp-28h]
  IUnknown *pProxy; // [rsp+58h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  *a1 = 1;
  pProxy = 0;
  if ( CoCreateInstance(
         &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
         0,
         0x15u,
         &GUID_f112757a_565b_4260_bd05_9fa34417349a,
         (LPVOID *)&pProxy) >= 0 )
  {
    v2 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 3u, 3u, 0, 0);
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v2,
        ppv);
      v4 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v4->lpVtbl->Release)(v4);
      }
      return v3;
    }
    v6 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, const OLECHAR *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
           pProxy,
           0,
           L"Language Overlay Service",
           0);
    v3 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v6,
        0);
      v7 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
      }
      return v3;
    }
    pv = 0;
    lpVtbl = pProxy->lpVtbl;
    v14 = 0;
    v15 = 1;
    v9 = ((int (__fastcall *)(IUnknown *, __int64, void **))lpVtbl[4].QueryInterface)(pProxy, 27, &v14) >= 0;
    if ( v15 )
    {
      v10 = pv;
      pv = v14;
      if ( v10 )
        CoTaskMemFree(v10);
    }
    v11 = pv;
    if ( v9 && *(_WORD *)pv == 49 && !*((_WORD *)pv + 1) )
      *a1 = 0;
    pv = 0;
    if ( v11 )
      CoTaskMemFree(v11);
  }
  v12 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v12->lpVtbl->Release)(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180049794  push    rbp
0x180049796  push    rbx
0x180049797  push    rsi
0x180049798  push    rdi
0x180049799  mov     rbp, rsp
0x18004979c  sub     rsp, 78h
0x1800497a0  mov     rax, cs:__security_cookie
0x1800497a7  xor     rax, rsp
0x1800497aa  mov     [rbp+var_10], rax
0x1800497ae  mov     rdi, rcx
0x1800497b1  mov     byte ptr [rcx], 1
0x1800497b4  xor     esi, esi
0x1800497b6  mov     [rbp+pProxy], rsi
0x1800497ba  lea     rax, [rbp+pProxy]
0x1800497be  mov     [rsp+78h+ppv], rax; ppv
0x1800497c3  lea     r9, _GUID_f112757a_565b_4260_bd05_9fa34417349a; riid
0x1800497ca  xor     edx, edx; pUnkOuter
0x1800497cc  lea     r8d, [rsi+15h]; dwClsContext
0x1800497d0  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x1800497d7  call    cs:__imp_CoCreateInstance
0x1800497dd  test    eax, eax
0x1800497df  js      loc_180049923
0x1800497e5  mov     [rsp+78h+dwCapabilities], esi; dwCapabilities
0x1800497e9  mov     [rsp+78h+pAuthInfo], rsi; pAuthInfo
0x1800497ee  lea     eax, [rsi+3]
0x1800497f1  mov     [rsp+78h+dwImpLevel], eax; dwImpLevel
0x1800497f5  mov     dword ptr [rsp+78h+ppv], eax; int
0x1800497f9  xor     r9d, r9d; pServerPrincName
0x1800497fc  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800497ff  mov     r8d, edx; dwAuthzSvc
0x180049802  mov     rcx, [rbp+pProxy]; pProxy
0x180049806  call    cs:__imp_CoSetProxyBlanket
0x18004980c  mov     ebx, eax
0x18004980e  test    eax, eax
0x180049810  jns     short loc_18004984C
0x180049812  mov     rcx, [rbp+20h]; this
0x180049816  mov     r9d, eax; char *
0x180049819  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180049820  mov     edx, 1BFh; void *
0x180049825  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004982a  nop
0x18004982b  mov     rcx, [rbp+pProxy]
0x18004982f  test    rcx, rcx
0x180049832  jz      short loc_180049845
0x180049834  mov     [rbp+pProxy], rsi
0x180049838  mov     rax, [rcx]
0x18004983b  mov     rax, [rax+10h]
0x18004983f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049844  nop
0x180049845  mov     eax, ebx
0x180049847  jmp     loc_18004993F
0x18004984c  mov     rcx, [rbp+pProxy]
0x180049850  mov     rax, [rcx]
0x180049853  mov     [rsp+78h+ppv], rsi; int
0x180049858  xor     r9d, r9d
0x18004985b  lea     r8, sourceString; "Language Overlay Service"
0x180049862  xor     edx, edx
0x180049864  mov     rax, [rax+18h]
0x180049868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004986d  mov     ebx, eax
0x18004986f  test    eax, eax
0x180049871  jns     short loc_1800498A8
0x180049873  mov     rcx, [rbp+20h]; this
0x180049877  mov     r9d, eax; char *
0x18004987a  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180049881  mov     edx, 1C1h; void *
0x180049886  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004988b  nop
0x18004988c  mov     rcx, [rbp+pProxy]
0x180049890  test    rcx, rcx
0x180049893  jz      short loc_1800498A6
0x180049895  mov     [rbp+pProxy], rsi
0x180049899  mov     rax, [rcx]
0x18004989c  mov     rax, [rax+10h]
0x1800498a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498a5  nop
0x1800498a6  jmp     short loc_180049845
0x1800498a8  mov     [rbp+pv], rsi
0x1800498ac  mov     rcx, [rbp+pProxy]
0x1800498b0  mov     rax, [rcx]
0x1800498b3  lea     rdx, [rbp+pv]
0x1800498b7  mov     [rbp+var_38], rdx
0x1800498bb  mov     [rbp+var_30], rsi
0x1800498bf  mov     [rbp+var_28], 1
0x1800498c3  lea     r8, [rbp+var_30]
0x1800498c7  mov     edx, 1Bh
0x1800498cc  mov     rax, [rax+60h]
0x1800498d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498d5  mov     ebx, eax
0x1800498d7  shr     ebx, 1Fh
0x1800498da  xor     bl, 1
0x1800498dd  cmp     [rbp+var_28], sil
0x1800498e1  jz      short loc_1800498FC
0x1800498e3  mov     r8, [rbp+var_38]
0x1800498e7  mov     rcx, [r8]; pv
0x1800498ea  mov     rdx, [rbp+var_30]
0x1800498ee  mov     [r8], rdx
0x1800498f1  test    rcx, rcx
0x1800498f4  jz      short loc_1800498FC
0x1800498f6  call    cs:__imp_CoTaskMemFree
0x1800498fc  mov     rcx, [rbp+pv]; pv
0x180049900  test    bl, bl
0x180049902  jz      short loc_180049913
0x180049904  cmp     word ptr [rcx], 31h ; '1'
0x180049908  jnz     short loc_180049913
0x18004990a  cmp     [rcx+2], si
0x18004990e  jnz     short loc_180049913
0x180049910  mov     [rdi], sil
0x180049913  mov     [rbp+pv], rsi
0x180049917  test    rcx, rcx
0x18004991a  jz      short loc_180049923
0x18004991c  call    cs:__imp_CoTaskMemFree
0x180049922  nop
0x180049923  mov     rcx, [rbp+pProxy]
0x180049927  test    rcx, rcx
0x18004992a  jz      short loc_18004993D
0x18004992c  mov     [rbp+pProxy], rsi
0x180049930  mov     rax, [rcx]
0x180049933  mov     rax, [rax+10h]
0x180049937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004993c  nop
0x18004993d  xor     eax, eax
0x18004993f  mov     rcx, [rbp+var_10]
0x180049943  xor     rcx, rsp; StackCookie
0x180049946  call    __security_check_cookie
0x18004994b  add     rsp, 78h
0x18004994f  pop     rdi
0x180049950  pop     rsi
0x180049951  pop     rbx
0x180049952  pop     rbp
0x180049953  retn
```
