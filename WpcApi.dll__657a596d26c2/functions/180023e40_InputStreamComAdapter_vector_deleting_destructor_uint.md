# InputStreamComAdapter::`vector deleting destructor'(uint)

- ea: `0x180023e40`
- end: `0x180023ec1`
- name: `??_EInputStreamComAdapter@@UEAAPEAXI@Z`
- size: `129`
- prototype: `InputStreamComAdapter *__fastcall(InputStreamComAdapter *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800036e4`
- `0x180023e40`
- `0x18002c010`

## pseudocode

```c
InputStreamComAdapter *__fastcall InputStreamComAdapter::`vector deleting destructor'(
        InputStreamComAdapter *this,
        char a2)
{
  volatile signed __int32 *v2; // rbx

  v2 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180023e40  mov     [rsp+arg_0], rbx
0x180023e45  mov     [rsp+arg_8], rsi
0x180023e4a  push    rdi
0x180023e4b  sub     rsp, 20h
0x180023e4f  mov     rbx, [rcx+18h]
0x180023e53  mov     esi, edx
0x180023e55  mov     rdi, rcx
0x180023e58  test    rbx, rbx
0x180023e5b  jz      short loc_180023E94
0x180023e5d  or      eax, 0FFFFFFFFh
0x180023e60  lock xadd [rbx+8], eax
0x180023e65  cmp     eax, 1
0x180023e68  jnz     short loc_180023E94
0x180023e6a  mov     rax, [rbx]
0x180023e6d  mov     rcx, rbx
0x180023e70  mov     rax, [rax]
0x180023e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e78  or      eax, 0FFFFFFFFh
0x180023e7b  lock xadd [rbx+0Ch], eax
0x180023e80  cmp     eax, 1
0x180023e83  jnz     short loc_180023E94
0x180023e85  mov     rax, [rbx]
0x180023e88  mov     rcx, rbx
0x180023e8b  mov     rax, [rax+8]
0x180023e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e94  mov     dword ptr [rdi+0Ch], 0C0000001h
0x180023e9b  test    sil, 1
0x180023e9f  jz      short loc_180023EAE
0x180023ea1  mov     edx, 28h ; '('
0x180023ea6  mov     rcx, rdi; Block
0x180023ea9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023eae  mov     rbx, [rsp+28h+arg_0]
0x180023eb3  mov     rax, rdi
0x180023eb6  mov     rsi, [rsp+28h+arg_8]
0x180023ebb  add     rsp, 20h
0x180023ebf  pop     rdi
0x180023ec0  retn
```
