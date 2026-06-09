# StringCchPrintfW(ushort *,uint,ushort const *,...)

- ea: `0x402df9`
- end: `0x402e5a`
- name: `?StringCchPrintfW@@YAJPAGIPBGZZ`
- size: `97`
- prototype: `int(wchar_t *Buffer, signed int, wchar_t *Format, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x4044ae`
- `0x4076da`
- `0x407d14`
- `0x407eab`
- `0x408235`
- `0x40c3ba`

## callees

- `0x402df9`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x402e20`
- `msvcrt!_vsnwprintf` at `0x402e20`

## pseudocode

```c
int StringCchPrintfW(wchar_t *Buffer, signed int a2, wchar_t *Format, ...)
{
  int v3; // esi
  unsigned int v4; // edi
  int v5; // eax
  va_list Args; // [esp+18h] [ebp+14h] BYREF

  va_start(Args, Format);
  if ( a2 <= 0 )
  {
    v3 = -2147024809;
    if ( a2 )
      *Buffer = 0;
  }
  else
  {
    v3 = 0;
    v4 = a2 - 1;
    v5 = __vsnwprintf(Buffer, a2 - 1, Format, Args);
    if ( v5 < 0 || v5 > v4 )
    {
      v3 = -2147024774;
LABEL_7:
      Buffer[v4] = 0;
      return v3;
    }
    if ( v5 == v4 )
      goto LABEL_7;
  }
  return v3;
}

```

## disassembly

```asm
0x402df9  mov     edi, edi
0x402dfb  push    ebp
0x402dfc  mov     ebp, esp
0x402dfe  mov     eax, [ebp+arg_4]
0x402e01  push    esi
0x402e02  test    eax, eax
0x402e04  jz      short loc_402E44
0x402e06  cmp     eax, 7FFFFFFFh
0x402e0b  ja      short loc_402E44
0x402e0d  push    ebx
0x402e0e  mov     ebx, [ebp+Buffer]
0x402e11  xor     esi, esi
0x402e13  push    edi
0x402e14  lea     edi, [eax-1]
0x402e17  lea     eax, [ebp+Args]
0x402e1a  push    eax; Args
0x402e1b  push    [ebp+Format]; Format
0x402e1e  push    edi; BufferCount
0x402e1f  push    ebx; Buffer
0x402e20  call    ds:__imp___vsnwprintf
0x402e26  add     esp, 10h
0x402e29  test    eax, eax
0x402e2b  js      short loc_402E35
0x402e2d  cmp     eax, edi
0x402e2f  ja      short loc_402E35
0x402e31  jnz     short loc_402E40
0x402e33  jmp     short loc_402E3A
0x402e35  mov     esi, 8007007Ah
0x402e3a  xor     eax, eax
0x402e3c  mov     [ebx+edi*2], ax
0x402e40  pop     edi
0x402e41  pop     ebx
0x402e42  jmp     short loc_402E55
0x402e44  mov     esi, 80070057h
0x402e49  test    eax, eax
0x402e4b  jz      short loc_402E55
0x402e4d  mov     ecx, [ebp+Buffer]
0x402e50  xor     eax, eax
0x402e52  mov     [ecx], ax
0x402e55  mov     eax, esi
0x402e57  pop     esi
0x402e58  pop     ebp
0x402e59  retn
```
