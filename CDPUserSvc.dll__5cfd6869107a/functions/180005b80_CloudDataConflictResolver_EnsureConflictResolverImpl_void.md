# CloudDataConflictResolver::EnsureConflictResolverImpl(void)

- ea: `0x180005b80`
- end: `0x180005c5c`
- name: `?EnsureConflictResolverImpl@CloudDataConflictResolver@@AEAAJXZ`
- size: `220`
- prototype: `__int64 __fastcall(CloudDataConflictResolver *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005810`
- `0x1800158c0`

## callees

- `0x180003678`
- `0x180005b80`
- `0x180005c64`
- `0x180006494`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180005baf`
- `msvcp_win!_Mtx_unlock` at `0x180005c1a`
- `msvcp_win!_Mtx_unlock` at `0x180005baf`
- `msvcp_win!_Mtx_unlock` at `0x180005c1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005be5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005be5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CloudDataConflictResolver::EnsureConflictResolverImpl(CloudDataConflictResolver *this)
{
  struct _Mtx_internal_imp_t *v2; // rdi
  LPVOID *ppv; // rsi
  HRESULT Instance; // eax
  int v6; // edx
  int v7; // ecx
  unsigned int v8; // [rsp+50h] [rbp+8h] BYREF
  int v9; // [rsp+58h] [rbp+10h]
  int v10; // [rsp+60h] [rbp+18h] BYREF
  char *v11; // [rsp+68h] [rbp+20h]

  v9 = 0;
  v2 = (CloudDataConflictResolver *)((char *)this + 16);
  v11 = (char *)this + 16;
  std::_Mutex_base::lock((CloudDataConflictResolver *)((char *)this + 16));
  ppv = (LPVOID *)((char *)this + 96);
  if ( *ppv
    || (Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv),
        Instance = CoCreateInstance(&rclsid, 0, 1u, &GUID_f31c3589_6bda_42b8_a920_bb0053f2c8a0, ppv),
        Instance >= 0) )
  {
    _Mtx_unlock(v2);
    return 0;
  }
  else
  {
    v8 = Instance;
    v10 = 133;
    Log<long &,char const (&)[36],int>(
      v7,
      v6,
      (unsigned int)&v8,
      (unsigned int)"..\\cdpclouddataconflictresolver.cpp",
      (__int64)&v10);
    _Mtx_unlock(v2);
    return v8;
  }
}

```

## disassembly

```asm
0x180005b80  push    rbx
0x180005b82  push    rsi
0x180005b83  push    rdi
0x180005b84  sub     rsp, 30h
0x180005b88  mov     rsi, rcx
0x180005b8b  xor     ebx, ebx
0x180005b8d  mov     [rsp+48h+arg_8], ebx
0x180005b91  lea     rdi, [rcx+10h]
0x180005b95  mov     [rsp+48h+arg_18], rdi
0x180005b9a  mov     rcx, rdi; this
0x180005b9d  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180005ba2  nop
0x180005ba3  add     rsi, 60h ; '`'
0x180005ba7  cmp     [rsi], rbx
0x180005baa  jz      short loc_180005BC4
0x180005bac  mov     rcx, rdi; _Mtx_t
0x180005baf  call    cs:__imp__Mtx_unlock
0x180005bb5  nop
0x180005bb6  test    ebx, ebx
0x180005bb8  js      short loc_180005C2C
0x180005bba  xor     eax, eax
0x180005bbc  add     rsp, 30h
0x180005bc0  pop     rdi
0x180005bc1  pop     rsi
0x180005bc2  pop     rbx
0x180005bc3  retn
0x180005bc4  mov     rcx, rsi
0x180005bc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005bcc  mov     [rsp+48h+ppv], rsi; ppv
0x180005bd1  lea     r9, _GUID_f31c3589_6bda_42b8_a920_bb0053f2c8a0; riid
0x180005bd8  xor     edx, edx; pUnkOuter
0x180005bda  lea     r8d, [rdx+1]; dwClsContext
0x180005bde  lea     rcx, rclsid; rclsid
0x180005be5  call    cs:__imp_CoCreateInstance
0x180005beb  test    eax, eax
0x180005bed  jns     short loc_180005BAC
0x180005bef  mov     [rsp+48h+arg_0], eax
0x180005bf3  mov     [rsp+48h+arg_10], 85h
0x180005bfb  lea     rax, [rsp+48h+arg_10]
0x180005c00  mov     [rsp+48h+ppv], rax
0x180005c05  lea     r9, aCdpclouddataco; "..\\cdpclouddataconflictresolver.cpp"
0x180005c0c  lea     r8, [rsp+48h+arg_0]
0x180005c11  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180005c16  nop
0x180005c17  mov     rcx, rdi; _Mtx_t
0x180005c1a  call    cs:__imp__Mtx_unlock
0x180005c20  mov     eax, [rsp+48h+arg_0]
0x180005c24  jmp     short loc_180005BBC
0x180005c26  mov     ebx, [rsp+48h+arg_8]
0x180005c2a  jmp     short loc_180005BB6
0x180005c2c  mov     [rsp+48h+arg_0], ebx
0x180005c30  mov     [rsp+48h+arg_8], 89h
0x180005c38  lea     rax, [rsp+48h+arg_8]
0x180005c3d  mov     [rsp+48h+ppv], rax
0x180005c42  lea     r9, aCdpclouddataco; "..\\cdpclouddataconflictresolver.cpp"
0x180005c49  lea     r8, [rsp+48h+arg_0]
0x180005c4e  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180005c53  mov     eax, [rsp+48h+arg_0]
0x180005c57  jmp     loc_180005BBC
```
