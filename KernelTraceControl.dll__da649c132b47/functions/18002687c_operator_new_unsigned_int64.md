# operator new(unsigned __int64)

- ea: `0x18002687c`
- end: `0x1800268f4`
- name: `??2@YAPEAX_K@Z`
- size: `120`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `49`
- callee_count: `7`
- tags: ``

## callers

- `0x1800025f8`
- `0x180005384`
- `0x1800058d0`
- `0x1800059bc`
- `0x180005aa8`
- `0x180008a18`
- `0x18000d62c`
- `0x18000dc84`
- `0x18000e4d0`
- `0x18000e50c`
- `0x18000eb8c`
- `0x18000f3b4`
- `0x18000fcec`
- `0x18000fd3c`
- `0x18000fdb0`
- `0x18000fe00`
- `0x18000fe94`
- `0x180011ab8`
- `0x180012264`
- `0x1800137f8`
- `0x180015b98`
- `0x180016418`
- `0x18001675c`
- `0x1800167c8`
- `0x180016834`
- `0x180017074`
- `0x180019690`
- `0x180019ffc`
- `0x18001a1d8`
- `0x18001a2c0`
- `0x18001a314`
- `0x18001a364`
- `0x18001b4e8`
- `0x18001b808`
- `0x18001b924`
- `0x18001beec`
- `0x18001dab4`
- `0x18001db94`
- `0x18001ea44`
- `0x18001ede4`
- `0x180022710`
- `0x1800227bc`
- `0x1800231a8`
- `0x180023b1c`
- `0x1800249b8`
- `0x180024b10`
- `0x1800268fc`
- `0x180027a80`
- `0x18002888d`

## callees

- `0x1800025d4`
- `0x18002684c`
- `0x18002687c`
- `0x180026ee0`
- `0x180026f30`
- `0x180026f3c`
- `0x180026f66`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
    {
      if ( (dword_180038A58 & 1) == 0 )
      {
        dword_180038A58 |= 1u;
        std::bad_alloc::bad_alloc((std::bad_alloc *)&qword_180038A40);
        atexit(sub_180029F10);
      }
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, (const struct std::bad_alloc *)&qword_180038A40);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002687c  push    rbx
0x18002687e  sub     rsp, 40h
0x180026882  mov     rbx, rcx
0x180026885  jmp     short loc_180026896
0x180026887  mov     rcx, rbx; Size
0x18002688a  call    _callnewh_0
0x18002688f  test    eax, eax
0x180026891  jz      short loc_1800268A6
0x180026893  mov     rcx, rbx; Size
0x180026896  call    malloc_0
0x18002689b  test    rax, rax
0x18002689e  jz      short loc_180026887
0x1800268a0  add     rsp, 40h
0x1800268a4  pop     rbx
0x1800268a5  retn
0x1800268a6  mov     eax, cs:dword_180038A58
0x1800268ac  test    al, 1
0x1800268ae  jnz     short loc_1800268D1
0x1800268b0  or      eax, 1
0x1800268b3  lea     rcx, qword_180038A40; this
0x1800268ba  mov     cs:dword_180038A58, eax
0x1800268c0  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800268c5  lea     rcx, sub_180029F10; void (__cdecl *)()
0x1800268cc  call    atexit
0x1800268d1  lea     rdx, qword_180038A40; struct std::bad_alloc *
0x1800268d8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800268dd  call    ??0bad_alloc@std@@QEAA@AEBV01@@Z; std::bad_alloc::bad_alloc(std::bad_alloc const &)
0x1800268e2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800268e9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800268ee  call    _CxxThrowException_0
```
