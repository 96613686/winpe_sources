# InputStreamComAdapter::~InputStreamComAdapter(void)

- ea: `0x180022784`
- end: `0x1800227e3`
- name: `??1InputStreamComAdapter@@UEAA@XZ`
- size: `95`
- prototype: `void __fastcall(InputStreamComAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a7f1`

## callees

- `0x180022784`
- `0x18002c010`

## pseudocode

```c
void __fastcall InputStreamComAdapter::~InputStreamComAdapter(InputStreamComAdapter *this)
{
  volatile signed __int32 *v1; // rbx

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v1 )
  {
    if ( _InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      if ( _InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180022784  mov     [rsp+arg_0], rbx
0x180022789  push    rdi
0x18002278a  sub     rsp, 20h
0x18002278e  mov     rbx, [rcx+18h]
0x180022792  mov     rdi, rcx
0x180022795  test    rbx, rbx
0x180022798  jz      short loc_1800227D1
0x18002279a  or      eax, 0FFFFFFFFh
0x18002279d  lock xadd [rbx+8], eax
0x1800227a2  cmp     eax, 1
0x1800227a5  jnz     short loc_1800227D1
0x1800227a7  mov     rax, [rbx]
0x1800227aa  mov     rcx, rbx
0x1800227ad  mov     rax, [rax]
0x1800227b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227b5  or      eax, 0FFFFFFFFh
0x1800227b8  lock xadd [rbx+0Ch], eax
0x1800227bd  cmp     eax, 1
0x1800227c0  jnz     short loc_1800227D1
0x1800227c2  mov     rax, [rbx]
0x1800227c5  mov     rcx, rbx
0x1800227c8  mov     rax, [rax+8]
0x1800227cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227d1  mov     rbx, [rsp+28h+arg_0]
0x1800227d6  mov     dword ptr [rdi+0Ch], 0C0000001h
0x1800227dd  add     rsp, 20h
0x1800227e1  pop     rdi
0x1800227e2  retn
```
