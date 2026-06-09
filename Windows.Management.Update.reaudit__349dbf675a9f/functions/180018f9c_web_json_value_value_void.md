# web::json::value::~value(void)

- ea: `0x180018f9c`
- end: `0x180018fc2`
- name: `??1value@json@web@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(web::json::value *__hidden this)`
- caller_count: `71`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028d30`
- `0x180029b9d`
- `0x180029baf`
- `0x180029bd3`
- `0x180029bf7`
- `0x180029c1b`
- `0x180029c3f`
- `0x180029c75`
- `0x180029c99`
- `0x180029cbd`
- `0x180029ce1`
- `0x180029cf3`
- `0x180029d17`
- `0x180029d3b`
- `0x180029d5f`
- `0x180029d95`
- `0x180029da7`
- `0x180029dcb`
- `0x180029def`
- `0x180029e13`
- `0x180029e49`
- `0x180029e5b`
- `0x180029e7f`
- `0x180029ea3`
- `0x180029ec7`
- `0x180029efd`
- `0x180029f0f`
- `0x180029f33`
- `0x180029f57`
- `0x180029f7b`
- `0x180029fe1`
- `0x18002a011`
- `0x18002a053`
- `0x18002a083`
- `0x18002a0b3`
- `0x18002a0d7`
- `0x18002a0e9`
- `0x18002a11f`
- `0x18002a131`
- `0x18002a167`
- `0x18002a19d`
- `0x18002a1c1`
- `0x18002a1d3`
- `0x18002a209`
- `0x18002a23f`
- `0x18002a263`
- `0x18002a275`
- `0x18002a2ab`
- `0x18002a2e1`
- `0x18002a305`

## callees

- `0x180018f9c`
- `0x18002c010`

## pseudocode

```c
void __fastcall web::json::value::~value(web::json::value *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 192LL))(v1, 1);
}

```

## disassembly

```asm
0x180018f9c  sub     rsp, 28h
0x180018fa0  mov     rcx, [rcx]
0x180018fa3  test    rcx, rcx
0x180018fa6  jz      short loc_180018FBC
0x180018fa8  mov     rax, [rcx]
0x180018fab  mov     edx, 1
0x180018fb0  mov     rax, [rax+0C0h]
0x180018fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fbc  add     rsp, 28h
0x180018fc0  retn
```
