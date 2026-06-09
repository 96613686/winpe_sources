# wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)

- ea: `0x180002a70`
- end: `0x180002ae7`
- name: `?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ`
- size: `119`
- prototype: `unsigned __int16 *(wil::details *this, char *, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024c4`

## callees

- `0x180002a70`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002aa9`
- `msvcrt!_vsnwprintf` at `0x180002aa9`

## pseudocode

```c
unsigned __int16 *wil::details::LogStringPrintf(
        wil::details *this,
        char *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        ...)
{
  unsigned __int64 v4; // rdi
  unsigned __int16 *v6; // rbx
  size_t v7; // rdi
  int v8; // eax
  __int64 v9; // rax
  const unsigned __int16 *Args; // [rsp+78h] [rbp+20h] BYREF

  Args = a4;
  v4 = (a2 - (char *)this) >> 1;
  v6 = (unsigned __int16 *)this;
  if ( v4 )
  {
    if ( v4 > 0x7FFFFFFF )
    {
      *(_WORD *)this = 0;
    }
    else
    {
      v7 = v4 - 1;
      v8 = _vsnwprintf((wchar_t *)this, v7, a3, (va_list)&Args);
      if ( v8 < 0 || v8 >= v7 )
        v6[v7] = 0;
    }
  }
  if ( a2 != (char *)v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v6[v9] );
    v6 += v9;
  }
  return v6;
}

```

## disassembly

```asm
0x180002a70  mov     [rsp+arg_10], r8
0x180002a75  mov     [rsp+Args], r9
0x180002a7a  push    rbx
0x180002a7b  push    rbp
0x180002a7c  push    rsi
0x180002a7d  push    rdi
0x180002a7e  sub     rsp, 38h
0x180002a82  mov     rdi, rdx
0x180002a85  lea     r9, [rsp+58h+Args]; Args
0x180002a8a  sub     rdi, rcx
0x180002a8d  xor     ebp, ebp
0x180002a8f  sar     rdi, 1
0x180002a92  mov     rsi, rdx
0x180002a95  mov     rbx, rcx
0x180002a98  jz      short loc_180002AC5
0x180002a9a  cmp     rdi, 7FFFFFFFh
0x180002aa1  ja      short loc_180002AC2
0x180002aa3  dec     rdi
0x180002aa6  mov     rdx, rdi; BufferCount
0x180002aa9  call    cs:__imp__vsnwprintf
0x180002aaf  test    eax, eax
0x180002ab1  js      short loc_180002ABC
0x180002ab3  cdqe
0x180002ab5  cmp     rax, rdi
0x180002ab8  ja      short loc_180002ABC
0x180002aba  jnz     short loc_180002AC5
0x180002abc  mov     [rbx+rdi*2], bp
0x180002ac0  jmp     short loc_180002AC5
0x180002ac2  mov     [rcx], bp
0x180002ac5  cmp     rsi, rbx
0x180002ac8  jz      short loc_180002ADB
0x180002aca  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002ace  inc     rax
0x180002ad1  cmp     [rbx+rax*2], bp
0x180002ad5  jnz     short loc_180002ACE
0x180002ad7  lea     rbx, [rbx+rax*2]
0x180002adb  mov     rax, rbx
0x180002ade  add     rsp, 38h
0x180002ae2  pop     rdi
0x180002ae3  pop     rsi
0x180002ae4  pop     rbp
0x180002ae5  pop     rbx
0x180002ae6  retn
```
