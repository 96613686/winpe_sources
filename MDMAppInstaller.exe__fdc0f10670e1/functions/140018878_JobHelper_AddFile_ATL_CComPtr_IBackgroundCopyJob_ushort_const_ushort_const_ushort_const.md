# JobHelper::AddFile(ATL::CComPtr<IBackgroundCopyJob> &,ushort const *,ushort const *,ushort const *)

- ea: `0x140018878`
- end: `0x140018968`
- name: `?AddFile@JobHelper@@SAJAEAV?$CComPtr@UIBackgroundCopyJob@@@ATL@@PEBG11@Z`
- size: `240`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010a2c`

## callees

- `0x1400056a4`
- `0x14000904c`
- `0x140018878`
- `0x14001c010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x1400188e9`
- `ole32!CoSetProxyBlanket` at `0x1400188e9`

## pseudocode

```c
__int64 __fastcall JobHelper::AddFile(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  IUnknown *pProxy; // [rsp+70h] [rbp+8h] BYREF

  pProxy = 0;
  v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, IUnknown **))*a1)(
         *a1,
         &GUID_ee2584cf_a69c_4848_b633_2649962b3ef7,
         &pProxy);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
    v8 = v7;
    if ( v7 >= 0 )
    {
      dwAuthnLevel = 0;
      v7 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64))pProxy->lpVtbl[1].QueryInterface)(
             pProxy,
             a4,
             a3,
             a2);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v8 = 0;
        goto LABEL_9;
      }
      v9 = 38;
    }
    else
    {
      v9 = 36;
    }
  }
  else
  {
    v9 = 33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"admin\\enterprisemgmt\\desktopappcsps\\sharedlib\\jobhelper.cpp",
    (const char *)(unsigned int)v7,
    dwAuthnLevel);
LABEL_9:
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&pProxy);
  return v8;
}

```

## disassembly

```asm
0x140018878  push    rbx
0x14001887a  push    rbp
0x14001887b  push    rsi
0x14001887c  push    rdi
0x14001887d  sub     rsp, 48h
0x140018881  mov     rdi, r9
0x140018884  mov     rsi, r8
0x140018887  mov     rbp, rdx
0x14001888a  mov     [rsp+68h+pProxy], 0
0x140018893  mov     rcx, [rcx]
0x140018896  mov     rax, [rcx]
0x140018899  lea     r8, [rsp+68h+pProxy]
0x14001889e  lea     rdx, _GUID_ee2584cf_a69c_4848_b633_2649962b3ef7
0x1400188a5  mov     rax, [rax]
0x1400188a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400188ad  mov     ebx, eax
0x1400188af  test    eax, eax
0x1400188b1  jns     short loc_1400188BA
0x1400188b3  mov     edx, 21h ; '!'
0x1400188b8  jmp     short loc_1400188FA
0x1400188ba  mov     [rsp+68h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1400188c2  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x1400188cb  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x1400188d3  mov     [rsp+68h+dwAuthnLevel], 0; int
0x1400188db  xor     r9d, r9d; pServerPrincName
0x1400188de  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1400188e1  mov     r8d, edx; dwAuthzSvc
0x1400188e4  mov     rcx, [rsp+68h+pProxy]; pProxy
0x1400188e9  call    cs:__imp_CoSetProxyBlanket
0x1400188ef  mov     ebx, eax
0x1400188f1  test    eax, eax
0x1400188f3  jns     short loc_140018910
0x1400188f5  mov     edx, 24h ; '$'; void *
0x1400188fa  mov     rcx, [rsp+68h]; this
0x1400188ff  mov     r9d, eax; char *
0x140018902  lea     r8, aAdminEnterpris_0; "admin\\enterprisemgmt\\desktopappcsps\\"...
0x140018909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001890e  jmp     short loc_140018953
0x140018910  mov     rcx, [rsp+68h+pProxy]
0x140018915  mov     rax, [rcx]
0x140018918  mov     [rsp+68h+pAuthInfo], 0
0x140018921  mov     qword ptr [rsp+68h+dwImpLevel], 0
0x14001892a  mov     [rsp+68h+dwAuthnLevel], 0
0x140018932  mov     r9, rbp
0x140018935  mov     r8, rsi
0x140018938  mov     rdx, rdi
0x14001893b  mov     rax, [rax+18h]
0x14001893f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018944  mov     ebx, eax
0x140018946  test    eax, eax
0x140018948  jns     short loc_140018951
0x14001894a  mov     edx, 26h ; '&'
0x14001894f  jmp     short loc_1400188FA
0x140018951  xor     ebx, ebx
0x140018953  lea     rcx, [rsp+68h+pProxy]
0x140018958  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x14001895d  mov     eax, ebx
0x14001895f  add     rsp, 48h
0x140018963  pop     rdi
0x140018964  pop     rsi
0x140018965  pop     rbp
0x140018966  pop     rbx
0x140018967  retn
```
