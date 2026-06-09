# CDPComDeviceQuery::CreateDeviceQueryInternalSafe(ICDPDeviceQuery * *)

- ea: `0x180003d64`
- end: `0x180003dde`
- name: `?CreateDeviceQueryInternalSafe@CDPComDeviceQuery@@AEAAJPEAPEAVICDPDeviceQuery@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(CDPComDeviceQuery *__hidden this, struct ICDPDeviceQuery **)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003bd0`
- `0x18001e1e0`
- `0x18001e4b0`
- `0x1800363b0`
- `0x180036690`
- `0x180037730`

## callees

- `0x180003d64`
- `0x180003e60`
- `0x18000cb8c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180003dae`
- `msvcp_win!_Mtx_unlock` at `0x180003dae`
- `cdp!CDPCreateDeviceQueryInternal` at `0x180003dbc`
- `cdp!CDPCreateDeviceQueryInternal` at `0x180003dbc`

## pseudocode

```c
__int64 __fastcall CDPComDeviceQuery::CreateDeviceQueryInternalSafe(
        CDPComDeviceQuery *this,
        struct ICDPDeviceQuery **a2)
{
  struct _Mtx_internal_imp_t *v4; // rbp
  __int64 v5; // rax
  std::_Ref_count_base *v6; // rsi
  __int64 v7; // rdi
  char v8; // bl
  __int64 v9; // rcx
  unsigned int Internal; // ebx

  v4 = (CDPComDeviceQuery *)((char *)this + 24);
  std::_Mutex_base::lock((CDPComDeviceQuery *)((char *)this + 24));
  v5 = *((_QWORD *)this + 16);
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 16);
  v7 = *((_QWORD *)this + 15);
  v8 = *((_BYTE *)this + 160);
  _Mtx_unlock(v4);
  LOBYTE(v9) = v8;
  Internal = CDPCreateDeviceQueryInternal(v9, v7, a2);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return Internal;
}

```

## disassembly

```asm
0x180003d64  push    rbx
0x180003d66  push    rbp
0x180003d67  push    rsi
0x180003d68  push    rdi
0x180003d69  push    r14
0x180003d6b  sub     rsp, 30h
0x180003d6f  mov     r14, rdx
0x180003d72  mov     rbx, rcx
0x180003d75  xorps   xmm0, xmm0
0x180003d78  movdqu  [rsp+58h+var_38], xmm0
0x180003d7e  lea     rbp, [rcx+18h]
0x180003d82  mov     rcx, rbp; this
0x180003d85  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180003d8a  mov     rax, [rbx+80h]
0x180003d91  test    rax, rax
0x180003d94  jz      short loc_180003D9A
0x180003d96  lock inc dword ptr [rax+8]
0x180003d9a  mov     rsi, [rbx+80h]
0x180003da1  mov     rdi, [rbx+78h]
0x180003da5  mov     bl, [rbx+0A0h]
0x180003dab  mov     rcx, rbp; _Mtx_t
0x180003dae  call    cs:__imp__Mtx_unlock
0x180003db4  mov     r8, r14
0x180003db7  mov     rdx, rdi
0x180003dba  mov     cl, bl
0x180003dbc  call    cs:__imp_CDPCreateDeviceQueryInternal
0x180003dc2  mov     ebx, eax
0x180003dc4  test    rsi, rsi
0x180003dc7  jz      short loc_180003DD1
0x180003dc9  mov     rcx, rsi; this
0x180003dcc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003dd1  mov     eax, ebx
0x180003dd3  add     rsp, 30h
0x180003dd7  pop     r14
0x180003dd9  pop     rdi
0x180003dda  pop     rsi
0x180003ddb  pop     rbp
0x180003ddc  pop     rbx
0x180003ddd  retn
```
