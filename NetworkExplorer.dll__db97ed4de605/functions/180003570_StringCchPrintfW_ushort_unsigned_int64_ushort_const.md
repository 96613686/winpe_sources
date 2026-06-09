# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003570`
- end: `0x1800035fb`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d2c`
- `0x180002dc0`
- `0x180008f7c`
- `0x18000cb58`

## callees

- `0x180003570`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800035a4`
- `msvcrt!_vsnwprintf` at `0x1800035a4`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rsi
  unsigned int v5; // ebx
  int v6; // eax
  __int64 result; // rax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = a2 - 1;
    v5 = 0;
    v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
    if ( v6 < 0 )
      goto LABEL_7;
    if ( v6 != v4 )
    {
      if ( v6 <= v4 )
        return v5;
LABEL_7:
      a1[v4] = 0;
      return (unsigned int)-2147024774;
    }
    a1[v4] = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003570  mov     [rsp+arg_10], r8
0x180003575  mov     qword ptr [rsp+Args], r9
0x18000357a  push    rbx
0x18000357b  push    rdi
0x18000357c  sub     rsp, 38h
0x180003580  mov     rdi, rcx
0x180003583  test    rdx, rdx
0x180003586  jz      short loc_1800035EA
0x180003588  cmp     rdx, 7FFFFFFFh
0x18000358f  ja      short loc_1800035E3
0x180003591  mov     [rsp+48h+var_18], rsi
0x180003596  lea     r9, [rsp+48h+Args]; Args
0x18000359b  lea     rsi, [rdx-1]
0x18000359f  xor     ebx, ebx
0x1800035a1  mov     rdx, rsi; BufferCount
0x1800035a4  call    cs:__imp__vsnwprintf
0x1800035aa  test    eax, eax
0x1800035ac  js      short loc_1800035C6
0x1800035ae  movsxd  rcx, eax
0x1800035b1  cmp     rcx, rsi
0x1800035b4  jz      short loc_1800035D1
0x1800035b6  ja      short loc_1800035C6
0x1800035b8  mov     rsi, [rsp+48h+var_18]
0x1800035bd  mov     eax, ebx
0x1800035bf  add     rsp, 38h
0x1800035c3  pop     rdi
0x1800035c4  pop     rbx
0x1800035c5  retn
0x1800035c6  mov     [rdi+rsi*2], bx
0x1800035ca  mov     ebx, 8007007Ah
0x1800035cf  jmp     short loc_1800035B8
0x1800035d1  mov     [rdi+rsi*2], bx
0x1800035d5  mov     eax, ebx
0x1800035d7  mov     rsi, [rsp+48h+var_18]
0x1800035dc  add     rsp, 38h
0x1800035e0  pop     rdi
0x1800035e1  pop     rbx
0x1800035e2  retn
0x1800035e3  mov     eax, 80070057h
0x1800035e8  jmp     short loc_1800035F4
0x1800035ea  mov     eax, 80070057h
0x1800035ef  test    rdx, rdx
0x1800035f2  jz      short loc_1800035BF
0x1800035f4  xor     ebx, ebx
0x1800035f6  mov     [rcx], bx
0x1800035f9  jmp     short loc_1800035BF
```
