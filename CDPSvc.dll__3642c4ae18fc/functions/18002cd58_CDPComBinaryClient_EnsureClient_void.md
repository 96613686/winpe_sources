# CDPComBinaryClient::EnsureClient(void)

- ea: `0x18002cd58`
- end: `0x18002cdbd`
- name: `?EnsureClient@CDPComBinaryClient@@AEAAJXZ`
- size: `101`
- prototype: `__int64 __fastcall(CDPComBinaryClient *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020ac0`
- `0x180020ce0`
- `0x18002d2f0`
- `0x18002d3f0`

## callees

- `0x18000cb8c`
- `0x180017b40`
- `0x18002cd58`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18002cdaa`
- `msvcp_win!_Mtx_unlock` at `0x18002cdaa`
- `cdp!CDPCreateBinaryClientInternal` at `0x18002cd95`
- `cdp!CDPCreateBinaryClientInternal` at `0x18002cd95`

## pseudocode

```c
__int64 __fastcall CDPComBinaryClient::EnsureClient(CDPComBinaryClient *this)
{
  struct _Mtx_internal_imp_t *v1; // rdi
  _QWORD *v3; // rbx
  unsigned int v4; // ebx
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = (CDPComBinaryClient *)((char *)this + 152);
  std::_Mutex_base::lock((CDPComBinaryClient *)((char *)this + 152));
  v3 = (_QWORD *)((char *)this + 24);
  if ( *v3 )
  {
    v4 = 0;
  }
  else
  {
    v6[0] = 0;
    v6[1] = v3;
    v4 = CDPCreateBinaryClientInternal(v6);
    cdp::detail::address_of<ICDPBinaryClient>::~address_of<ICDPBinaryClient>(v6);
  }
  _Mtx_unlock(v1);
  return v4;
}

```

## disassembly

```asm
0x18002cd58  mov     [rsp+arg_0], rbx
0x18002cd5d  push    rdi
0x18002cd5e  sub     rsp, 30h
0x18002cd62  lea     rdi, [rcx+98h]
0x18002cd69  mov     rbx, rcx
0x18002cd6c  mov     rcx, rdi; this
0x18002cd6f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002cd74  add     rbx, 18h
0x18002cd78  cmp     qword ptr [rbx], 0
0x18002cd7c  jz      short loc_18002CD82
0x18002cd7e  xor     ebx, ebx
0x18002cd80  jmp     short loc_18002CDA7
0x18002cd82  lea     rcx, [rsp+38h+var_18]
0x18002cd87  mov     [rsp+38h+var_18], 0
0x18002cd90  mov     [rsp+38h+var_10], rbx
0x18002cd95  call    cs:__imp_CDPCreateBinaryClientInternal
0x18002cd9b  lea     rcx, [rsp+38h+var_18]
0x18002cda0  mov     ebx, eax
0x18002cda2  call    ??1?$address_of@VICDPBinaryClient@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPBinaryClient>::~address_of<ICDPBinaryClient>(void)
0x18002cda7  mov     rcx, rdi; _Mtx_t
0x18002cdaa  call    cs:__imp__Mtx_unlock
0x18002cdb0  mov     eax, ebx
0x18002cdb2  mov     rbx, [rsp+38h+arg_0]
0x18002cdb7  add     rsp, 30h
0x18002cdbb  pop     rdi
0x18002cdbc  retn
```
