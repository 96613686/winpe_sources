# com::http::register_marshalling(void)

- ea: `0x140158284`
- end: `0x14015846d`
- name: `?register_marshalling@http@com@@YAJXZ`
- size: `489`
- prototype: `__int64 __fastcall(com::http *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400eaa58`
- `0x1400ed28c`

## callees

- `0x14003a3c0`
- `0x14003a430`
- `0x14003a5c0`
- `0x140158284`
- `0x140166250`

## import_xrefs

- `ole32!CoRegisterClassObject` at `0x140158392`
- `ole32!CoRegisterClassObject` at `0x140158392`
- `ole32!CoRegisterPSClsid` at `0x1401583c8`
- `ole32!CoRegisterPSClsid` at `0x1401583c8`
- `RPCRT4!NdrDllGetClassObject` at `0x140158324`
- `RPCRT4!NdrDllGetClassObject` at `0x140158324`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall com::http::register_marshalling(com::http *this)
{
  const CLSID *pclsid; // rax
  HRESULT ClassObject; // ebx
  LPUNKNOWN v3; // rcx
  unsigned int v5; // ebx
  HRESULT v6; // edi
  void *ppv; // [rsp+38h] [rbp-28h] BYREF
  LPUNKNOWN pUnk; // [rsp+40h] [rbp-20h]
  DWORD dwRegister; // [rsp+48h] [rbp-18h] BYREF

  if ( dword_1401E7BD0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1401E7BD0);
    if ( dword_1401E7BD0 == -1 )
    {
      stru_1401E75D0 = IID_IHttpRequestQueue;
      Init_thread_footer(&dword_1401E7BD0);
    }
  }
  pUnk = 0;
  ppv = 0;
  if ( com_http_server_if_StubVtblList )
    pclsid = *com_http_server_if_StubVtblList;
  else
    pclsid = 0;
  ClassObject = NdrDllGetClassObject(
                  &stru_1401E75D0,
                  &IID_IPSFactoryBuffer,
                  &ppv,
                  (const ProxyFileInfo **)&aProxyFileList,
                  pclsid,
                  &gPFactory);
  v3 = pUnk;
  pUnk = (LPUNKNOWN)ppv;
  if ( v3 )
    ((void (__fastcall *)(LPUNKNOWN))v3->lpVtbl->Release)(v3);
  if ( ClassObject < 0 )
  {
    _mm_lfence();
    if ( pUnk )
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    return (unsigned int)ClassObject;
  }
  dwRegister = 0;
  ClassObject = CoRegisterClassObject(&stru_1401E75D0, pUnk, 1u, 1u, &dwRegister);
  if ( ClassObject < 0 )
  {
    _mm_lfence();
    if ( pUnk )
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    return (unsigned int)ClassObject;
  }
  v5 = 0;
  while ( 1 )
  {
    v6 = CoRegisterPSClsid(&stru_1401E75D0 + v5, &stru_1401E75D0);
    if ( v6 < 0 )
      break;
    if ( ++v5 )
    {
      if ( pUnk )
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      return 0;
    }
  }
  _mm_lfence();
  if ( pUnk )
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140158284  mov     [rsp-8+arg_0], rbx
0x140158289  mov     [rsp-8+arg_8], rdi
0x14015828e  mov     [rsp-8+arg_10], r15
0x140158293  push    rbp
0x140158294  mov     rbp, rsp
0x140158297  sub     rsp, 60h
0x14015829b  mov     rax, cs:__security_cookie
0x1401582a2  xor     rax, rsp
0x1401582a5  mov     [rbp+var_10], rax
0x1401582a9  mov     ecx, 4
0x1401582ae  mov     rax, gs:58h
0x1401582b7  mov     rax, [rax]
0x1401582ba  mov     eax, [rcx+rax]
0x1401582bd  cmp     cs:dword_1401E7BD0, eax
0x1401582c3  jg      loc_140158434
0x1401582c9  mov     [rbp+pUnk], 0
0x1401582d1  lea     rax, [rbp+pUnk]
0x1401582d5  mov     [rbp+var_30], rax
0x1401582d9  mov     [rbp+ppv], 0
0x1401582e1  mov     rax, cs:off_1401943A8
0x1401582e8  mov     rcx, [rax]
0x1401582eb  test    rcx, rcx
0x1401582ee  jz      short loc_1401582F5
0x1401582f0  mov     rax, [rcx]
0x1401582f3  jmp     short loc_1401582F7
0x1401582f5  xor     eax, eax
0x1401582f7  lea     rcx, gPFactory
0x1401582fe  mov     [rsp+60h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x140158303  mov     [rsp+60h+pclsid], rax; pclsid
0x140158308  lea     r9, aProxyFileList; pProxyFileList
0x14015830f  lea     r8, [rbp+ppv]; ppv
0x140158313  lea     rdx, IID_IPSFactoryBuffer; riid
0x14015831a  lea     r15, stru_1401E75D0
0x140158321  mov     rcx, r15; rclsid
0x140158324  call    cs:__imp_NdrDllGetClassObject
0x14015832a  mov     ebx, eax
0x14015832c  mov     r8, [rbp+var_30]
0x140158330  mov     rcx, [r8]
0x140158333  mov     rdx, [rbp+ppv]
0x140158337  mov     [r8], rdx
0x14015833a  test    rcx, rcx
0x14015833d  jz      short loc_14015834D
0x14015833f  mov     rdx, [rcx]
0x140158342  mov     rax, [rdx+10h]
0x140158346  call    cs:__guard_dispatch_icall_fptr
0x14015834c  nop
0x14015834d  test    ebx, ebx
0x14015834f  jns     short loc_140158372
0x140158351  lfence
0x140158354  mov     rcx, [rbp+pUnk]
0x140158358  test    rcx, rcx
0x14015835b  jz      short loc_14015836B
0x14015835d  mov     rax, [rcx]
0x140158360  mov     rax, [rax+10h]
0x140158364  call    cs:__guard_dispatch_icall_fptr
0x14015836a  nop
0x14015836b  mov     eax, ebx
0x14015836d  jmp     loc_140158412
0x140158372  mov     [rbp+dwRegister], 0
0x140158379  lea     rax, [rbp+dwRegister]
0x14015837d  mov     [rsp+60h+pclsid], rax; lpdwRegister
0x140158382  mov     r9d, 1; flags
0x140158388  mov     r8d, r9d; dwClsContext
0x14015838b  mov     rdx, [rbp+pUnk]; pUnk
0x14015838f  mov     rcx, r15; rclsid
0x140158392  call    cs:__imp_CoRegisterClassObject
0x140158398  mov     ebx, eax
0x14015839a  test    eax, eax
0x14015839c  jns     short loc_1401583BA
0x14015839e  lfence
0x1401583a1  mov     rcx, [rbp+pUnk]
0x1401583a5  test    rcx, rcx
0x1401583a8  jz      short loc_1401583B8
0x1401583aa  mov     rdx, [rcx]
0x1401583ad  mov     rax, [rdx+10h]
0x1401583b1  call    cs:__guard_dispatch_icall_fptr
0x1401583b7  nop
0x1401583b8  jmp     short loc_14015836B
0x1401583ba  xor     ebx, ebx
0x1401583bc  mov     ecx, ebx
0x1401583be  shl     rcx, 4
0x1401583c2  add     rcx, r15; riid
0x1401583c5  mov     rdx, r15; rclsid
0x1401583c8  call    cs:__imp_CoRegisterPSClsid
0x1401583ce  mov     edi, eax
0x1401583d0  test    eax, eax
0x1401583d2  js      short loc_1401583F6
0x1401583d4  inc     ebx
0x1401583d6  cmp     ebx, 1
0x1401583d9  jb      short loc_1401583BC
0x1401583db  mov     rcx, [rbp+pUnk]
0x1401583df  test    rcx, rcx
0x1401583e2  jz      short loc_1401583F2
0x1401583e4  mov     rax, [rcx]
0x1401583e7  mov     rax, [rax+10h]
0x1401583eb  call    cs:__guard_dispatch_icall_fptr
0x1401583f1  nop
0x1401583f2  xor     eax, eax
0x1401583f4  jmp     short loc_140158412
0x1401583f6  lfence
0x1401583f9  mov     rcx, [rbp+pUnk]
0x1401583fd  test    rcx, rcx
0x140158400  jz      short loc_140158410
0x140158402  mov     rax, [rcx]
0x140158405  mov     rax, [rax+10h]
0x140158409  call    cs:__guard_dispatch_icall_fptr
0x14015840f  nop
0x140158410  mov     eax, edi
0x140158412  mov     rcx, [rbp+var_10]
0x140158416  xor     rcx, rsp; StackCookie
0x140158419  call    __security_check_cookie
0x14015841e  lea     r11, [rsp+60h+var_s0]
0x140158423  mov     rbx, [r11+10h]
0x140158427  mov     rdi, [r11+18h]
0x14015842b  mov     r15, [r11+20h]
0x14015842f  mov     rsp, r11
0x140158432  pop     rbp
0x140158433  retn
0x140158434  lea     rcx, dword_1401E7BD0
0x14015843b  call    _Init_thread_header
0x140158440  cmp     cs:dword_1401E7BD0, 0FFFFFFFFh
0x140158447  jnz     loc_1401582C9
0x14015844d  movups  xmm0, xmmword ptr cs:IID_IHttpRequestQueue.Data1
0x140158454  movdqu  xmmword ptr cs:stru_1401E75D0.Data1, xmm0
0x14015845c  lea     rcx, dword_1401E7BD0
0x140158463  call    _Init_thread_footer
0x140158468  jmp     loc_1401582C9
```
