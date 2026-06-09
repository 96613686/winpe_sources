# MapsBrokerAsyncOperation::InvokeCallback(void)

- ea: `0x180007bc0`
- end: `0x180007c07`
- name: `?InvokeCallback@MapsBrokerAsyncOperation@@AEAAXXZ`
- size: `71`
- prototype: `void __fastcall(MapsBrokerAsyncOperation *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007c10`
- `0x180007e40`

## callees

- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bf0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bf0`

## pseudocode

```c
void __fastcall MapsBrokerAsyncOperation::InvokeCallback(MapsBrokerAsyncOperation *this)
{
  void (__fastcall *v1)(__int64); // rax
  char *v2; // rdx
  __int64 v3; // r8
  __int64 v5; // rcx

  v1 = (void (__fastcall *)(__int64))*((_QWORD *)this + 8);
  v2 = (char *)this + 104;
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 8) = 0;
  v5 = *((unsigned int *)this + 24);
  *((_QWORD *)v2 + 3) = v3;
  v1(v5);
  free(*((void **)this + 17));
  *((_QWORD *)this + 17) = 0;
}

```

## disassembly

```asm
0x180007bc0  push    rbx
0x180007bc2  sub     rsp, 20h
0x180007bc6  mov     rax, [rcx+40h]
0x180007bca  lea     rdx, [rcx+68h]
0x180007bce  mov     r8, [rcx+50h]
0x180007bd2  mov     rbx, rcx
0x180007bd5  mov     qword ptr [rcx+40h], 0
0x180007bdd  mov     ecx, [rcx+60h]
0x180007be0  mov     [rdx+18h], r8
0x180007be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be9  mov     rcx, [rbx+88h]; Block
0x180007bf0  call    cs:__imp_free
0x180007bf6  mov     qword ptr [rbx+88h], 0
0x180007c01  add     rsp, 20h
0x180007c05  pop     rbx
0x180007c06  retn
```
