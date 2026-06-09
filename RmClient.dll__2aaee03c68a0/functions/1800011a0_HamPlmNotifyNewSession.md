# HamPlmNotifyNewSession

- ea: `0x1800011a0`
- end: `0x180001410`
- name: `HamPlmNotifyNewSession`
- size: `624`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnk)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800011a0`
- `0x180001f10`
- `0x180002f50`
- `0x180004550`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001211`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001211`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000138c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000138c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800013fb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800013fb`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180001265`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180001265`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800013bc`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800013bc`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000123c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000123c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800011da`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800011da`
- `RPCRT4!NdrClientCall3` at `0x18000134b`
- `RPCRT4!NdrClientCall3` at `0x18000134b`
- `RPCRT4!RpcBindingFree` at `0x1800013f0`
- `RPCRT4!RpcBindingFree` at `0x1800013f0`
- `RPCRT4!RpcExceptionFilter` at `0x18001afde`
- `RPCRT4!RpcExceptionFilter` at `0x18001afde`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001361`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001361`

## pseudocode

```c
__int64 __fastcall HamPlmNotifyNewSession(LPUNKNOWN pUnk)
{
  void *v2; // r14
  HRESULT v3; // eax
  void *v4; // r15
  int v5; // r12d
  CLIENT_CALL_RETURN v6; // rbx
  unsigned int v7; // eax
  HGLOBAL v8; // rax
  __int64 mshlflags; // [rsp+28h] [rbp-70h]
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-60h] BYREF
  size_t size; // [rsp+40h] [rbp-58h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+48h] [rbp-50h]
  HGLOBAL v14; // [rsp+50h] [rbp-48h]
  __int64 v15; // [rsp+58h] [rbp-40h]
  void *v16; // [rsp+60h] [rbp-38h]
  int v17; // [rsp+A8h] [rbp+10h] BYREF
  int v18; // [rsp+B0h] [rbp+18h]
  LPSTREAM ppstm; // [rsp+B8h] [rbp+20h] BYREF

  size = 0;
  v17 = 0;
  ppstm = 0;
  v2 = 0;
  v15 = 0;
  Binding = 0;
  v3 = CoInitializeEx(0, 0);
  if ( v3 < 0 )
  {
    v4 = 0;
    v5 = 0;
    goto LABEL_3;
  }
  v5 = 1;
  v18 = 1;
  v8 = GlobalAlloc(2u, 0);
  v4 = v8;
  v14 = v8;
  if ( !v8 )
  {
LABEL_7:
    LODWORD(v6.Pointer) = -1073741801;
    goto LABEL_16;
  }
  v3 = CreateStreamOnHGlobal(v8, 1, &ppstm);
  if ( v3 < 0 )
    goto LABEL_3;
  v3 = CoMarshalInterface(ppstm, &GUID_cf354276_51cb_46d8_9470_b192975390a1, pUnk, 0, 0, 1u);
  if ( v3 < 0 )
    goto LABEL_3;
  v3 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, __int64, size_t *))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 2, &size);
  if ( v3 < 0 )
    goto LABEL_3;
  v2 = MIDL_user_allocate((unsigned int)size);
  v16 = v2;
  if ( !v2 )
    goto LABEL_7;
  v3 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
  if ( v3 < 0
    || (v3 = (*(__int64 (__fastcall **)(LPSTREAM, void *, _QWORD, int *))(*(_QWORD *)ppstm + 24LL))(
               ppstm,
               v2,
               (unsigned int)size,
               &v17),
        v3 < 0) )
  {
LABEL_3:
    LODWORD(v6.Pointer) = (unsigned __int16)v3;
    v7 = (unsigned __int16)v3 | 0xC0070000;
    if ( LODWORD(v6.Pointer) )
      LODWORD(v6.Pointer) = v7;
    goto LABEL_16;
  }
  LODWORD(v6.Pointer) = CempRpcBindToServer(qword_18001DC80, &Binding);
  if ( SLODWORD(v6.Simple) >= 0 )
  {
    v13.Simple = 0;
    LODWORD(mshlflags) = v17;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x17u, 0, Binding, v2, mshlflags).Pointer;
    v13.Pointer = v6.Pointer;
  }
LABEL_16:
  if ( v4 )
    GlobalFree(v4);
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
    CoReleaseMarshalData(ppstm);
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  }
  if ( v2 )
    HamFreeBuffer(v2);
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( v5 )
    CoUninitialize();
  return LODWORD(v6.Pointer);
}

```

## disassembly

```asm
0x1800011a0  mov     rax, rsp
0x1800011a3  push    rbx
0x1800011a4  push    rdi
0x1800011a5  push    r12
0x1800011a7  push    r14
0x1800011a9  push    r15
0x1800011ab  sub     rsp, 70h
0x1800011af  mov     rbx, rcx
0x1800011b2  mov     qword ptr [rax-58h], 0
0x1800011ba  mov     dword ptr [rax+10h], 0
0x1800011c1  mov     qword ptr [rax+20h], 0
0x1800011c9  xor     r14d, r14d
0x1800011cc  xor     edi, edi
0x1800011ce  mov     [rax-40h], rdi
0x1800011d2  mov     [rax-60h], rdi
0x1800011d6  xor     edx, edx; dwCoInit
0x1800011d8  xor     ecx, ecx; pvReserved
0x1800011da  call    cs:__imp_CoInitializeEx
0x1800011e0  test    eax, eax
0x1800011e2  jns     short loc_1800011FE
0x1800011e4  xor     r15d, r15d
0x1800011e7  xor     r12d, r12d
0x1800011ea  movzx   ebx, ax
0x1800011ed  mov     eax, ebx
0x1800011ef  or      eax, 0C0070000h
0x1800011f4  test    ebx, ebx
0x1800011f6  cmovnz  ebx, eax
0x1800011f9  jmp     loc_180001384
0x1800011fe  mov     r12d, 1
0x180001204  mov     [rsp+98h+arg_10], r12d
0x18000120c  xor     edx, edx; dwBytes
0x18000120e  lea     ecx, [rdx+2]; uFlags
0x180001211  call    cs:__imp_GlobalAlloc
0x180001217  mov     r15, rax
0x18000121a  mov     [rsp+98h+var_48], rax
0x18000121f  test    rax, rax
0x180001222  jnz     short loc_18000122E
0x180001224  mov     ebx, 0C0000017h
0x180001229  jmp     loc_180001384
0x18000122e  lea     r8, [rsp+98h+ppstm]; ppstm
0x180001236  mov     edx, r12d; fDeleteOnRelease
0x180001239  mov     rcx, rax; hGlobal
0x18000123c  call    cs:__imp_CreateStreamOnHGlobal
0x180001242  test    eax, eax
0x180001244  js      short loc_1800011EA
0x180001246  mov     dword ptr [rsp+98h+mshlflags], r12d; mshlflags
0x18000124b  mov     [rsp+98h+pvDestContext], rdi; pvDestContext
0x180001250  xor     r9d, r9d; dwDestContext
0x180001253  mov     r8, rbx; pUnk
0x180001256  lea     rdx, _GUID_cf354276_51cb_46d8_9470_b192975390a1; riid
0x18000125d  mov     rcx, [rsp+98h+ppstm]; pStm
0x180001265  call    cs:__imp_CoMarshalInterface
0x18000126b  test    eax, eax
0x18000126d  js      loc_1800011EA
0x180001273  mov     rcx, [rsp+98h+ppstm]
0x18000127b  mov     rax, [rcx]
0x18000127e  lea     r9, [rsp+98h+size]
0x180001283  mov     r8d, 2
0x180001289  mov     rdx, rdi
0x18000128c  mov     rax, [rax+28h]
0x180001290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001295  test    eax, eax
0x180001297  js      loc_1800011EA
0x18000129d  mov     ecx, dword ptr [rsp+98h+size]; size
0x1800012a1  call    MIDL_user_allocate
0x1800012a6  mov     r14, rax
0x1800012a9  mov     [rsp+98h+var_38], rax
0x1800012ae  test    rax, rax
0x1800012b1  jz      loc_180001224
0x1800012b7  mov     rcx, [rsp+98h+ppstm]
0x1800012bf  mov     rax, [rcx]
0x1800012c2  xor     r9d, r9d
0x1800012c5  xor     r8d, r8d
0x1800012c8  mov     rdx, rdi
0x1800012cb  mov     rax, [rax+28h]
0x1800012cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012d4  test    eax, eax
0x1800012d6  js      loc_1800011EA
0x1800012dc  mov     rcx, [rsp+98h+ppstm]
0x1800012e4  mov     rax, [rcx]
0x1800012e7  lea     r9, [rsp+98h+arg_8]
0x1800012ef  mov     r8d, dword ptr [rsp+98h+size]
0x1800012f4  mov     rdx, r14
0x1800012f7  mov     rax, [rax+18h]
0x1800012fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001300  test    eax, eax
0x180001302  js      loc_1800011EA
0x180001308  lea     rdx, [rsp+98h+Binding]
0x18000130d  lea     rcx, qword_18001DC80; IfSpec
0x180001314  call    CempRpcBindToServer
0x180001319  mov     ebx, eax
0x18000131b  test    eax, eax
0x18000131d  js      short loc_180001384
0x18000131f  mov     eax, [rsp+98h+arg_8]
0x180001326  mov     [rsp+98h+var_50], 0
0x18000132f  mov     dword ptr [rsp+98h+mshlflags], eax
0x180001333  mov     [rsp+98h+pvDestContext], r14
0x180001338  mov     r9, [rsp+98h+Binding]
0x18000133d  xor     r8d, r8d; pReturnValue
0x180001340  lea     edx, [r8+17h]; nProcNum
0x180001344  lea     rcx, pProxyInfo; pProxyInfo
0x18000134b  call    cs:__imp_NdrClientCall3
0x180001351  mov     rbx, rax
0x180001354  mov     [rsp+98h+var_50], rax
0x180001359  mov     [rsp+98h+var_68], eax
0x18000135d  jmp     short loc_180001384
0x18000135f  mov     ecx, eax; Status
0x180001361  call    cs:__imp_I_RpcMapWin32Status
0x180001367  mov     ebx, eax
0x180001369  mov     [rsp+98h+var_68], eax
0x18000136d  mov     r15, [rsp+98h+var_48]
0x180001372  mov     rdi, [rsp+98h+var_40]
0x180001377  mov     r14, [rsp+98h+var_38]
0x18000137c  mov     r12d, [rsp+98h+arg_10]
0x180001384  test    r15, r15
0x180001387  jz      short loc_180001392
0x180001389  mov     rcx, r15; hMem
0x18000138c  call    cs:__imp_GlobalFree
0x180001392  mov     rcx, [rsp+98h+ppstm]
0x18000139a  test    rcx, rcx
0x18000139d  jz      short loc_1800013D6
0x18000139f  mov     rax, [rcx]
0x1800013a2  xor     r9d, r9d
0x1800013a5  xor     r8d, r8d
0x1800013a8  mov     rdx, rdi
0x1800013ab  mov     rax, [rax+28h]
0x1800013af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013b4  mov     rcx, [rsp+98h+ppstm]; pStm
0x1800013bc  call    cs:__imp_CoReleaseMarshalData
0x1800013c2  mov     rcx, [rsp+98h+ppstm]
0x1800013ca  mov     rax, [rcx]
0x1800013cd  mov     rax, [rax+10h]
0x1800013d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013d6  test    r14, r14
0x1800013d9  jz      short loc_1800013E3
0x1800013db  mov     rcx, r14
0x1800013de  call    HamFreeBuffer
0x1800013e3  cmp     [rsp+98h+Binding], 0
0x1800013e9  jz      short loc_1800013F6
0x1800013eb  lea     rcx, [rsp+98h+Binding]; Binding
0x1800013f0  call    cs:__imp_RpcBindingFree
0x1800013f6  test    r12d, r12d
0x1800013f9  jz      short loc_180001401
0x1800013fb  call    cs:__imp_CoUninitialize
0x180001401  mov     eax, ebx
0x180001403  add     rsp, 70h
0x180001407  pop     r15
0x180001409  pop     r14
0x18000140b  pop     r12
0x18000140d  pop     rdi
0x18000140e  pop     rbx
0x18000140f  retn
0x18001afd0  push    rbp
0x18001afd2  sub     rsp, 30h
0x18001afd6  mov     rbp, rdx
0x18001afd9  mov     rcx, [rcx]
0x18001afdc  mov     ecx, [rcx]; ExceptionCode
0x18001afde  call    cs:__imp_RpcExceptionFilter
0x18001afe4  nop
0x18001afe5  add     rsp, 30h
0x18001afe9  pop     rbp
0x18001afea  retn
```
