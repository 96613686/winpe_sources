# MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)

- ea: `0x140002e6c`
- end: `0x140002f0a`
- name: `?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z`
- size: `158`
- prototype: `void(unsigned int, const int *const, unsigned int, int, unsigned int, void *)`
- caller_count: `17`
- callee_count: `5`
- tags: ``

## callers

- `0x140001fb0`
- `0x14000215c`
- `0x1400023dc`
- `0x140002518`
- `0x140002630`
- `0x140002c1c`
- `0x140002c64`
- `0x140002cf0`
- `0x140002fbc`
- `0x1400031e0`
- `0x140003350`
- `0x140003480`
- `0x1400035ac`
- `0x140004470`
- `0x14000d744`
- `0x14000dadc`
- `0x14000f9e0`

## callees

- `0x140002e6c`
- `0x140003644`
- `0x14000f724`
- `0x14000f898`
- `0x14000f8b8`

## pseudocode

```c
void __fastcall MilInstrumentationCheckHR_MaybeFailFast(
        unsigned int a1,
        const int *const a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        void *a6)
{
  void *v6; // rdi
  bool v9; // al
  int v10; // ecx
  const int *v11; // r10
  unsigned int v12; // r11d
  bool v13; // bp
  void *retaddr; // [rsp+48h] [rbp+0h]

  v6 = a6;
  if ( !a6 )
    v6 = retaddr;
  v9 = IsOOM(a4);
  v13 = v9;
  if ( (a1 & 0x10) != 0 && v9 )
  {
    if ( !v11 || !v12 )
      goto LABEL_12;
  }
  else if ( !v11 || !v12 )
  {
    v11 = (const int *)qword_1400132E0;
    v12 = 10;
  }
  if ( !IsHRInList(v10, v11, v12) )
  {
LABEL_12:
    MilInstrumentationHandleFailure_MaybeFailFast(a4, a1, a5, v6);
    return;
  }
  if ( (a1 & 4) != 0 && v13 )
    DoStackCapture(a4, a5, v6);
}

```

## disassembly

```asm
0x140002e6c  push    rbx
0x140002e6e  push    rbp
0x140002e6f  push    rsi
0x140002e70  push    rdi
0x140002e71  sub     rsp, 28h
0x140002e75  mov     rdi, [rsp+48h+arg_28]
0x140002e7a  mov     ebx, r9d
0x140002e7d  mov     r11d, r8d
0x140002e80  mov     r10, rdx
0x140002e83  mov     esi, ecx
0x140002e85  test    rdi, rdi
0x140002e88  jnz     short loc_140002E8F
0x140002e8a  mov     rdi, [rsp+48h]
0x140002e8f  mov     ecx, ebx; int
0x140002e91  call    ?IsOOM@@YA_NJ@Z; IsOOM(long)
0x140002e96  mov     bpl, al
0x140002e99  test    sil, 10h
0x140002e9d  jz      short loc_140002EAF
0x140002e9f  test    al, al
0x140002ea1  jz      short loc_140002EAF
0x140002ea3  test    r10, r10
0x140002ea6  jz      short loc_140002ED5
0x140002ea8  test    r11d, r11d
0x140002eab  jnz     short loc_140002EC6
0x140002ead  jmp     short loc_140002ED5
0x140002eaf  test    r10, r10
0x140002eb2  jz      short loc_140002EB9
0x140002eb4  test    r11d, r11d
0x140002eb7  jnz     short loc_140002EC6
0x140002eb9  lea     r10, qword_1400132E0
0x140002ec0  mov     r11d, 0Ah
0x140002ec6  mov     r8d, r11d; unsigned int
0x140002ec9  mov     rdx, r10; int *
0x140002ecc  call    ?IsHRInList@@YA_NJQEBJI@Z; IsHRInList(long,long const * const,uint)
0x140002ed1  test    al, al
0x140002ed3  jnz     short loc_140002EE8
0x140002ed5  mov     r8d, [rsp+48h+arg_20]; unsigned int
0x140002eda  mov     r9, rdi; void *
0x140002edd  mov     edx, esi; unsigned int
0x140002edf  mov     ecx, ebx; int
0x140002ee1  call    ?MilInstrumentationHandleFailure_MaybeFailFast@@YAXJKIPEAX@Z; MilInstrumentationHandleFailure_MaybeFailFast(long,ulong,uint,void *)
0x140002ee6  jmp     short loc_140002F01
0x140002ee8  test    sil, 4
0x140002eec  jz      short loc_140002F01
0x140002eee  test    bpl, bpl
0x140002ef1  jz      short loc_140002F01
0x140002ef3  mov     edx, [rsp+48h+arg_20]; unsigned int
0x140002ef7  mov     r8, rdi; void *
0x140002efa  mov     ecx, ebx; int
0x140002efc  call    ?DoStackCapture@@YAXJIPEAX@Z; DoStackCapture(long,uint,void *)
0x140002f01  add     rsp, 28h
0x140002f05  pop     rdi
0x140002f06  pop     rsi
0x140002f07  pop     rbp
0x140002f08  pop     rbx
0x140002f09  retn
```
