# SetNullCredentials(IBackgroundCopyJob *)

- ea: `0x18001eac4`
- end: `0x18001eb9f`
- name: `?SetNullCredentials@@YAJPEAUIBackgroundCopyJob@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b05c`

## callees

- `0x18001afb4`
- `0x18001eac4`
- `0x180021010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x18001eb3c`
- `ole32!CoSetProxyBlanket` at `0x18001eb3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetNullCredentials(struct IBackgroundCopyJob *a1)
{
  HRESULT v1; // ebx
  IUnknown *pProxy; // [rsp+48h] [rbp-28h] BYREF
  _OWORD v4[2]; // [rsp+50h] [rbp-20h] BYREF

  memset(v4, 0, 24);
  pProxy = 0;
  v1 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, IUnknown **))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af,
         &pProxy);
  if ( v1 >= 0 )
  {
    v1 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
    if ( v1 >= 0 )
    {
      v4[0] = 0x400000001uLL;
      v1 = ((__int64 (__fastcall *)(IUnknown *, _OWORD *))pProxy->lpVtbl[13].Release)(pProxy, v4);
    }
  }
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)&pProxy);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001eac4  mov     [rsp-8+arg_0], rbx
0x18001eac9  mov     [rsp-8+arg_8], rsi
0x18001eace  push    rbp
0x18001eacf  mov     rbp, rsp
0x18001ead2  sub     rsp, 70h
0x18001ead6  xorps   xmm0, xmm0
0x18001ead9  xor     eax, eax
0x18001eadb  movups  [rbp+var_20], xmm0
0x18001eadf  mov     [rbp+var_10], rax
0x18001eae3  mov     [rbp+pProxy], rax
0x18001eae7  lea     rsi, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001eaee  mov     [rbp+var_30], rsi
0x18001eaf2  mov     rax, [rcx]
0x18001eaf5  lea     r8, [rbp+pProxy]
0x18001eaf9  lea     rdx, _GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af
0x18001eb00  mov     rax, [rax]
0x18001eb03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb08  mov     ebx, eax
0x18001eb0a  test    eax, eax
0x18001eb0c  js      short loc_18001EB7D
0x18001eb0e  mov     [rsp+70h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18001eb16  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x18001eb1f  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x18001eb27  mov     [rsp+70h+dwAuthnLevel], 0; dwAuthnLevel
0x18001eb2f  xor     r9d, r9d; pServerPrincName
0x18001eb32  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001eb35  mov     r8d, edx; dwAuthzSvc
0x18001eb38  mov     rcx, [rbp+pProxy]; pProxy
0x18001eb3c  call    cs:__imp_CoSetProxyBlanket
0x18001eb43  nop     dword ptr [rax+rax+00h]
0x18001eb48  mov     ebx, eax
0x18001eb4a  test    eax, eax
0x18001eb4c  js      short loc_18001EB7D
0x18001eb4e  mov     dword ptr [rbp+var_20], 1
0x18001eb55  mov     dword ptr [rbp+var_20+4], 4
0x18001eb5c  xorps   xmm0, xmm0
0x18001eb5f  movdqu  [rbp+var_20+8], xmm0
0x18001eb64  mov     rcx, [rbp+pProxy]
0x18001eb68  mov     rax, [rcx]
0x18001eb6b  lea     rdx, [rbp+var_20]
0x18001eb6f  mov     rax, [rax+148h]
0x18001eb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb7b  mov     ebx, eax
0x18001eb7d  mov     [rbp+var_30], rsi
0x18001eb81  lea     rcx, [rbp+pProxy]
0x18001eb85  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001eb8a  mov     eax, ebx
0x18001eb8c  lea     r11, [rsp+70h+var_s0]
0x18001eb91  mov     rbx, [r11+10h]
0x18001eb95  mov     rsi, [r11+18h]
0x18001eb99  mov     rsp, r11
0x18001eb9c  pop     rbp
0x18001eb9d  retn
```
