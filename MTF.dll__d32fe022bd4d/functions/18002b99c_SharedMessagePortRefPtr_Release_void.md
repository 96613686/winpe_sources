# SharedMessagePortRefPtr::Release(void)

- ea: `0x18002b99c`
- end: `0x18002ba08`
- name: `?Release@SharedMessagePortRefPtr@@QEAAXXZ`
- size: `108`
- prototype: `void __fastcall(SharedMessagePortRefPtr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002341c`

## callees

- `0x18002b99c`
- `0x18002f010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18002b9bc`
- `ntdll!RtlDllShutdownInProgress` at `0x18002b9bc`

## pseudocode

```c
void __fastcall SharedMessagePortRefPtr::Release(SharedMessagePortRefPtr *this)
{
  __int64 v1; // rdi
  __int64 v2; // rbx

  v1 = *(_QWORD *)this;
  v2 = *((_QWORD *)this + 1);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  if ( !RtlDllShutdownInProgress() )
  {
    if ( v1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 32LL))(v1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
    }
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
}

```

## disassembly

```asm
0x18002b99c  mov     [rsp+arg_0], rbx
0x18002b9a1  push    rdi
0x18002b9a2  sub     rsp, 20h
0x18002b9a6  mov     rdi, [rcx]
0x18002b9a9  mov     rbx, [rcx+8]
0x18002b9ad  mov     qword ptr [rcx], 0
0x18002b9b4  mov     qword ptr [rcx+8], 0
0x18002b9bc  call    cs:__imp_RtlDllShutdownInProgress
0x18002b9c2  test    al, al
0x18002b9c4  jnz     short loc_18002B9FD
0x18002b9c6  test    rdi, rdi
0x18002b9c9  jz      short loc_18002B9E9
0x18002b9cb  mov     rax, [rdi]
0x18002b9ce  mov     rcx, rdi
0x18002b9d1  mov     rax, [rax+20h]
0x18002b9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9da  mov     rax, [rdi]
0x18002b9dd  mov     rcx, rdi
0x18002b9e0  mov     rax, [rax+10h]
0x18002b9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9e9  test    rbx, rbx
0x18002b9ec  jz      short loc_18002B9FD
0x18002b9ee  mov     rax, [rbx]
0x18002b9f1  mov     rcx, rbx
0x18002b9f4  mov     rax, [rax+10h]
0x18002b9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9fd  mov     rbx, [rsp+28h+arg_0]
0x18002ba02  add     rsp, 20h
0x18002ba06  pop     rdi
0x18002ba07  retn
```
