# GetLangType(uint)

- ea: `0x180009030`
- end: `0x180009139`
- name: `?GetLangType@@YAII@Z`
- size: `265`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007280`
- `0x180008af8`

## callees

- `0x180009030`

## import_xrefs

- `msvcrt!iswspace` at `0x180009038`
- `msvcrt!iswspace` at `0x180009038`

## pseudocode

```c
__int64 __fastcall GetLangType(int a1)
{
  __int64 result; // rax

  if ( iswspace(a1) )
    return 1;
  if ( (unsigned int)(a1 - 13312) <= 0x6BFF
    || (unsigned int)(a1 - 63744) <= 0x1FF
    || (unsigned int)(a1 - 0x20000) <= 0xA6D6
    || (unsigned int)(a1 - 173824) <= 0x1034
    || (unsigned int)(a1 - 177984) <= 0xDD )
  {
    return 14;
  }
  if ( (unsigned int)(a1 - 12352) <= 0xBF )
    return 8;
  if ( (unsigned int)(a1 - 12544) <= 0x2F || (unsigned int)(a1 - 12704) <= 0x1F )
    return 4;
  if ( (unsigned int)(a1 - 12592) <= 0x5F
    || (unsigned int)(a1 - 44032) <= 0x2BA3
    || (unsigned int)(a1 - 4352) <= 0xFF
    || (unsigned int)(a1 - 43360) <= 0x1F
    || (unsigned int)(a1 - 55216) <= 0x4F )
  {
    return 16;
  }
  result = 1;
  if ( (unsigned int)(a1 - 3584) <= 0x7F )
    return 32;
  return result;
}

```

## disassembly

```asm
0x180009030  push    rbx
0x180009032  sub     rsp, 20h
0x180009036  mov     ebx, ecx
0x180009038  call    cs:__imp_iswspace
0x18000903e  test    eax, eax
0x180009040  jnz     loc_18000912E
0x180009046  lea     eax, [rbx-3400h]
0x18000904c  cmp     eax, 6BFFh
0x180009051  jbe     loc_180009127
0x180009057  lea     eax, [rbx-0F900h]
0x18000905d  cmp     eax, 1FFh
0x180009062  jbe     loc_180009127
0x180009068  lea     eax, [rbx-20000h]
0x18000906e  cmp     eax, 0A6D6h
0x180009073  jbe     loc_180009127
0x180009079  lea     eax, [rbx-2A700h]
0x18000907f  cmp     eax, 1034h
0x180009084  jbe     loc_180009127
0x18000908a  lea     eax, [rbx-2B740h]
0x180009090  cmp     eax, 0DDh
0x180009095  jbe     loc_180009127
0x18000909b  lea     eax, [rbx-3040h]
0x1800090a1  cmp     eax, 0BFh
0x1800090a6  ja      short loc_1800090B2
0x1800090a8  mov     eax, 8
0x1800090ad  jmp     loc_180009133
0x1800090b2  lea     eax, [rbx-3100h]
0x1800090b8  cmp     eax, 2Fh ; '/'
0x1800090bb  jbe     short loc_180009120
0x1800090bd  lea     eax, [rbx-31A0h]
0x1800090c3  cmp     eax, 1Fh
0x1800090c6  jbe     short loc_180009120
0x1800090c8  lea     eax, [rbx-3130h]
0x1800090ce  cmp     eax, 5Fh ; '_'
0x1800090d1  jbe     short loc_180009119
0x1800090d3  lea     eax, [rbx-0AC00h]
0x1800090d9  cmp     eax, 2BA3h
0x1800090de  jbe     short loc_180009119
0x1800090e0  lea     eax, [rbx-1100h]
0x1800090e6  cmp     eax, 0FFh
0x1800090eb  jbe     short loc_180009119
0x1800090ed  lea     eax, [rbx-0A960h]
0x1800090f3  cmp     eax, 1Fh
0x1800090f6  jbe     short loc_180009119
0x1800090f8  lea     eax, [rbx-0D7B0h]
0x1800090fe  cmp     eax, 4Fh ; 'O'
0x180009101  jbe     short loc_180009119
0x180009103  mov     eax, 1
0x180009108  lea     ecx, [rbx-0E00h]
0x18000910e  cmp     ecx, 7Fh
0x180009111  lea     edx, [rax+1Fh]
0x180009114  cmovbe  eax, edx
0x180009117  jmp     short loc_180009133
0x180009119  mov     eax, 10h
0x18000911e  jmp     short loc_180009133
0x180009120  mov     eax, 4
0x180009125  jmp     short loc_180009133
0x180009127  mov     eax, 0Eh
0x18000912c  jmp     short loc_180009133
0x18000912e  mov     eax, 1
0x180009133  add     rsp, 20h
0x180009137  pop     rbx
0x180009138  retn
```
