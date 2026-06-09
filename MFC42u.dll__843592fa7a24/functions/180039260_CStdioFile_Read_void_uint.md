# CStdioFile::Read(void *,uint)

- ea: `0x180039260`
- end: `0x18003930a`
- name: `?Read@CStdioFile@@UEAAIPEAXI@Z`
- size: `170`
- prototype: `unsigned int(CStdioFile *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002cba0`
- `0x18002da20`
- `0x180039260`

## import_xrefs

- `msvcrt!clearerr` at `0x1800392dd`
- `msvcrt!clearerr` at `0x1800392dd`
- `msvcrt!ferror` at `0x1800392cf`
- `msvcrt!ferror` at `0x1800392cf`
- `msvcrt!feof` at `0x1800392a7`
- `msvcrt!feof` at `0x1800392a7`
- `msvcrt!fread` at `0x180039296`
- `msvcrt!fread` at `0x180039296`
- `msvcrt!__doserrno` at `0x1800392b5`
- `msvcrt!__doserrno` at `0x1800392e7`
- `msvcrt!__doserrno` at `0x1800392b5`
- `msvcrt!__doserrno` at `0x1800392e7`

## pseudocode

```c
__int64 __fastcall CStdioFile::Read(FILE **this, void *a2, unsigned int a3)
{
  unsigned int v5; // edi
  const unsigned __int16 *v6; // rbx
  int *v7; // rax
  const unsigned __int16 *v8; // rbx
  int *v9; // rax

  if ( !a3 )
    return 0;
  if ( !a2 )
    AfxThrowInvalidArgException();
  v5 = fread(a2, 1u, a3, this[4]);
  if ( !v5 && !feof(this[4]) )
  {
    v6 = (const unsigned __int16 *)this[3];
    v7 = (int *)__doserrno();
    AfxThrowFileException(1, *v7, v6);
  }
  if ( ferror(this[4]) )
  {
    clearerr(this[4]);
    v8 = (const unsigned __int16 *)this[3];
    v9 = (int *)__doserrno();
    AfxThrowFileException(1, *v9, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x180039260  mov     [rsp+arg_0], rbx
0x180039265  push    rdi
0x180039266  sub     rsp, 20h
0x18003926a  mov     rax, rdx
0x18003926d  mov     rbx, rcx
0x180039270  test    r8d, r8d
0x180039273  jnz     short loc_18003927C
0x180039275  xor     eax, eax
0x180039277  jmp     loc_1800392FF
0x18003927c  test    rax, rax
0x18003927f  jnz     short loc_180039287
0x180039281  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180039287  mov     r9, [rcx+20h]; Stream
0x18003928b  mov     edx, 1; ElementSize
0x180039290  mov     rcx, rax; Buffer
0x180039293  mov     r8d, r8d; ElementCount
0x180039296  call    cs:__imp_fread
0x18003929c  mov     rdi, rax
0x18003929f  test    eax, eax
0x1800392a1  jnz     short loc_1800392CB
0x1800392a3  mov     rcx, [rbx+20h]; Stream
0x1800392a7  call    cs:__imp_feof
0x1800392ad  test    eax, eax
0x1800392af  jnz     short loc_1800392CB
0x1800392b1  mov     rbx, [rbx+18h]
0x1800392b5  call    cs:__imp___doserrno
0x1800392bb  mov     r8, rbx; unsigned __int16 *
0x1800392be  mov     ecx, 1; int
0x1800392c3  mov     edx, [rax]; int
0x1800392c5  call    ?AfxThrowFileException@@YAXHJPEBG@Z; AfxThrowFileException(int,long,ushort const *)
0x1800392cb  mov     rcx, [rbx+20h]; Stream
0x1800392cf  call    cs:__imp_ferror
0x1800392d5  test    eax, eax
0x1800392d7  jz      short loc_1800392FD
0x1800392d9  mov     rcx, [rbx+20h]; Stream
0x1800392dd  call    cs:__imp_clearerr
0x1800392e3  mov     rbx, [rbx+18h]
0x1800392e7  call    cs:__imp___doserrno
0x1800392ed  mov     r8, rbx; unsigned __int16 *
0x1800392f0  mov     ecx, 1; int
0x1800392f5  mov     edx, [rax]; int
0x1800392f7  call    ?AfxThrowFileException@@YAXHJPEBG@Z; AfxThrowFileException(int,long,ushort const *)
0x1800392fd  mov     eax, edi
0x1800392ff  mov     rbx, [rsp+28h+arg_0]
0x180039304  add     rsp, 20h
0x180039308  pop     rdi
0x180039309  retn
```
