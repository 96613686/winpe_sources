# std::_Locinfo::~_Locinfo(void)

- ea: `0x180031a54`
- end: `0x180031af9`
- name: `??1_Locinfo@std@@QEAA@XZ`
- size: `165`
- prototype: `void __fastcall(std::_Locinfo *__hidden this)`
- caller_count: `41`
- callee_count: `3`
- tags: ``

## callers

- `0x18000392c`
- `0x1800039e0`
- `0x180003ab8`
- `0x180003b6c`
- `0x180003c20`
- `0x180005fe8`
- `0x18000c640`
- `0x18000c720`
- `0x18000c83c`
- `0x18000c958`
- `0x18000ca50`
- `0x18000cb04`
- `0x18000cbb8`
- `0x18000cc6c`
- `0x18000cd20`
- `0x18000cdd4`
- `0x18000ce88`
- `0x18000cf74`
- `0x18000d060`
- `0x18000d14c`
- `0x18000d238`
- `0x18000d2ec`
- `0x18000d3a0`
- `0x18000d454`
- `0x18000d508`
- `0x18000d5e4`
- `0x18000d6c0`
- `0x18000d798`
- `0x18000d870`
- `0x18001d820`
- `0x18001d93c`
- `0x18001d9f0`
- `0x18001daa4`
- `0x18001db58`
- `0x18001dc44`
- `0x18001dd30`
- `0x18001de08`
- `0x18003158c`
- `0x180033e38`
- `0x1800352bd`
- `0x1800353c9`

## callees

- `0x18000241c`
- `0x18000274c`
- `0x180031a54`

## import_xrefs

- `msvcrt!free` at `0x180031a6b`
- `msvcrt!free` at `0x180031a82`
- `msvcrt!free` at `0x180031a99`
- `msvcrt!free` at `0x180031ab0`
- `msvcrt!free` at `0x180031ac7`
- `msvcrt!free` at `0x180031ade`
- `msvcrt!free` at `0x180031a6b`
- `msvcrt!free` at `0x180031a82`
- `msvcrt!free` at `0x180031a99`
- `msvcrt!free` at `0x180031ab0`
- `msvcrt!free` at `0x180031ac7`
- `msvcrt!free` at `0x180031ade`

## pseudocode

```c
void __fastcall std::_Locinfo::~_Locinfo(std::_Locinfo *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  std::_Locinfo::_Locinfo_dtor(this);
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
    free(v2);
  *((_QWORD *)this + 11) = 0;
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    free(v3);
  *((_QWORD *)this + 9) = 0;
  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
    free(v4);
  *((_QWORD *)this + 7) = 0;
  v5 = (void *)*((_QWORD *)this + 5);
  if ( v5 )
    free(v5);
  *((_QWORD *)this + 5) = 0;
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
    free(v6);
  *((_QWORD *)this + 3) = 0;
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
    free(v7);
  *((_QWORD *)this + 1) = 0;
  std::_Lockit::~_Lockit(this);
}

```

## disassembly

```asm
0x180031a54  push    rbx
0x180031a56  sub     rsp, 20h
0x180031a5a  mov     rbx, rcx
0x180031a5d  call    ?_Locinfo_dtor@_Locinfo@std@@SAXPEAV12@@Z; std::_Locinfo::_Locinfo_dtor(std::_Locinfo *)
0x180031a62  mov     rcx, [rbx+58h]; Block
0x180031a66  test    rcx, rcx
0x180031a69  jz      short loc_180031A71
0x180031a6b  call    cs:__imp_free
0x180031a71  mov     qword ptr [rbx+58h], 0
0x180031a79  mov     rcx, [rbx+48h]; Block
0x180031a7d  test    rcx, rcx
0x180031a80  jz      short loc_180031A88
0x180031a82  call    cs:__imp_free
0x180031a88  mov     qword ptr [rbx+48h], 0
0x180031a90  mov     rcx, [rbx+38h]; Block
0x180031a94  test    rcx, rcx
0x180031a97  jz      short loc_180031A9F
0x180031a99  call    cs:__imp_free
0x180031a9f  mov     qword ptr [rbx+38h], 0
0x180031aa7  mov     rcx, [rbx+28h]; Block
0x180031aab  test    rcx, rcx
0x180031aae  jz      short loc_180031AB6
0x180031ab0  call    cs:__imp_free
0x180031ab6  mov     qword ptr [rbx+28h], 0
0x180031abe  mov     rcx, [rbx+18h]; Block
0x180031ac2  test    rcx, rcx
0x180031ac5  jz      short loc_180031ACD
0x180031ac7  call    cs:__imp_free
0x180031acd  mov     qword ptr [rbx+18h], 0
0x180031ad5  mov     rcx, [rbx+8]; Block
0x180031ad9  test    rcx, rcx
0x180031adc  jz      short loc_180031AE4
0x180031ade  call    cs:__imp_free
0x180031ae4  mov     qword ptr [rbx+8], 0
0x180031aec  mov     rcx, rbx; this
0x180031aef  add     rsp, 20h
0x180031af3  pop     rbx
0x180031af4  jmp     ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
```
