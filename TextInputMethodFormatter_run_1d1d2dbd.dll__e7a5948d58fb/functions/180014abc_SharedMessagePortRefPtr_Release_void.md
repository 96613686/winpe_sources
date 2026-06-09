# SharedMessagePortRefPtr::Release(void)

- ea: `0x180014abc`
- end: `0x180014b28`
- name: `?Release@SharedMessagePortRefPtr@@QEAAXXZ`
- size: `108`
- prototype: `void __fastcall(SharedMessagePortRefPtr *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a3b0`
- `0x18001a8a8`
- `0x180034ea8`
- `0x1800527a4`

## callees

- `0x180014abc`
- `0x180058010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180014adc`
- `ntdll!RtlDllShutdownInProgress` at `0x180014adc`

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
0x180014abc  mov     [rsp+arg_0], rbx
0x180014ac1  push    rdi
0x180014ac2  sub     rsp, 20h
0x180014ac6  mov     rdi, [rcx]
0x180014ac9  mov     rbx, [rcx+8]
0x180014acd  mov     qword ptr [rcx], 0
0x180014ad4  mov     qword ptr [rcx+8], 0
0x180014adc  call    cs:__imp_RtlDllShutdownInProgress
0x180014ae2  test    al, al
0x180014ae4  jnz     short loc_180014B1D
0x180014ae6  test    rdi, rdi
0x180014ae9  jz      short loc_180014B09
0x180014aeb  mov     rax, [rdi]
0x180014aee  mov     rcx, rdi
0x180014af1  mov     rax, [rax+20h]
0x180014af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014afa  mov     rax, [rdi]
0x180014afd  mov     rcx, rdi
0x180014b00  mov     rax, [rax+10h]
0x180014b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b09  test    rbx, rbx
0x180014b0c  jz      short loc_180014B1D
0x180014b0e  mov     rax, [rbx]
0x180014b11  mov     rcx, rbx
0x180014b14  mov     rax, [rax+10h]
0x180014b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b1d  mov     rbx, [rsp+28h+arg_0]
0x180014b22  add     rsp, 20h
0x180014b26  pop     rdi
0x180014b27  retn
```
