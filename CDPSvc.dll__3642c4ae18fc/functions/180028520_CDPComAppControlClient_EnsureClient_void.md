# CDPComAppControlClient::EnsureClient(void)

- ea: `0x180028520`
- end: `0x180028582`
- name: `?EnsureClient@CDPComAppControlClient@@AEAAJXZ`
- size: `98`
- prototype: `__int64 __fastcall(CDPComAppControlClient *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ad90`
- `0x180028130`
- `0x180028a20`
- `0x180029020`
- `0x180029100`
- `0x180029580`
- `0x18002a3d0`
- `0x18002a850`

## callees

- `0x18000cb8c`
- `0x1800177f4`
- `0x180028520`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18002856f`
- `msvcp_win!_Mtx_unlock` at `0x18002856f`
- `cdp!CDPCreateAppControlClientInternal` at `0x18002855a`
- `cdp!CDPCreateAppControlClientInternal` at `0x18002855a`

## pseudocode

```c
__int64 __fastcall CDPComAppControlClient::EnsureClient(CDPComAppControlClient *this)
{
  struct _Mtx_internal_imp_t *v1; // rdi
  _QWORD *v3; // rbx
  unsigned int v4; // ebx
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = (CDPComAppControlClient *)((char *)this + 56);
  std::_Mutex_base::lock((CDPComAppControlClient *)((char *)this + 56));
  v3 = (_QWORD *)((char *)this + 24);
  if ( *v3 )
  {
    v4 = 0;
  }
  else
  {
    v6[0] = 0;
    v6[1] = v3;
    v4 = CDPCreateAppControlClientInternal(v6);
    cdp::detail::address_of<ICDPAppControlClient>::~address_of<ICDPAppControlClient>(v6);
  }
  _Mtx_unlock(v1);
  return v4;
}

```

## disassembly

```asm
0x180028520  mov     [rsp+arg_0], rbx
0x180028525  push    rdi
0x180028526  sub     rsp, 30h
0x18002852a  lea     rdi, [rcx+38h]
0x18002852e  mov     rbx, rcx
0x180028531  mov     rcx, rdi; this
0x180028534  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180028539  add     rbx, 18h
0x18002853d  cmp     qword ptr [rbx], 0
0x180028541  jz      short loc_180028547
0x180028543  xor     ebx, ebx
0x180028545  jmp     short loc_18002856C
0x180028547  lea     rcx, [rsp+38h+var_18]
0x18002854c  mov     [rsp+38h+var_18], 0
0x180028555  mov     [rsp+38h+var_10], rbx
0x18002855a  call    cs:__imp_CDPCreateAppControlClientInternal
0x180028560  lea     rcx, [rsp+38h+var_18]
0x180028565  mov     ebx, eax
0x180028567  call    ??1?$address_of@VICDPAppControlClient@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPAppControlClient>::~address_of<ICDPAppControlClient>(void)
0x18002856c  mov     rcx, rdi; _Mtx_t
0x18002856f  call    cs:__imp__Mtx_unlock
0x180028575  mov     eax, ebx
0x180028577  mov     rbx, [rsp+38h+arg_0]
0x18002857c  add     rsp, 30h
0x180028580  pop     rdi
0x180028581  retn
```
