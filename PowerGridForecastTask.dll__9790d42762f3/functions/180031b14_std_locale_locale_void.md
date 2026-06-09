# std::locale::~locale(void)

- ea: `0x180031b14`
- end: `0x180031b4d`
- name: `??1locale@std@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(std::locale *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180035263`
- `0x180035301`
- `0x180035313`
- `0x180035337`
- `0x180035515`
- `0x180035527`
- `0x180035932`
- `0x180035944`
- `0x180035956`
- `0x180035968`
- `0x180035ff5`

## callees

- `0x180031b14`
- `0x180037010`

## pseudocode

```c
void __fastcall std::locale::~locale(std::locale *this)
{
  __int64 v1; // rcx
  void (__fastcall ***v2)(_QWORD, __int64); // rax

  v1 = *(_QWORD *)this;
  if ( v1 )
  {
    v2 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
    if ( v2 )
      (**v2)(v2, 1);
  }
}

```

## disassembly

```asm
0x180031b14  sub     rsp, 28h
0x180031b18  mov     rcx, [rcx]
0x180031b1b  test    rcx, rcx
0x180031b1e  jz      short loc_180031B48
0x180031b20  mov     rax, [rcx]
0x180031b23  mov     rax, [rax+10h]
0x180031b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b2c  mov     r8, rax
0x180031b2f  test    rax, rax
0x180031b32  jz      short loc_180031B48
0x180031b34  mov     rcx, [rax]
0x180031b37  mov     rax, [rcx]
0x180031b3a  mov     edx, 1
0x180031b3f  mov     rcx, r8
0x180031b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b47  nop
0x180031b48  add     rsp, 28h
0x180031b4c  retn
```
