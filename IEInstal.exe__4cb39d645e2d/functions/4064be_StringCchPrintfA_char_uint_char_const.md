# StringCchPrintfA(char *,uint,char const *,...)

- ea: `0x4064be`
- end: `0x40651b`
- name: `?StringCchPrintfA@@YAJPADIPBDZZ`
- size: `93`
- prototype: `int(char *Buffer, signed int, char *Format, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x4072e3`
- `0x407a3f`
- `0x407b9f`

## callees

- `0x4064be`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x4064e5`
- `msvcrt!_vsnprintf` at `0x4064e5`

## pseudocode

```c
int StringCchPrintfA(char *Buffer, signed int a2, char *Format, ...)
{
  int v3; // esi
  unsigned int v4; // edi
  int v5; // eax
  va_list ArgList; // [esp+18h] [ebp+14h] BYREF

  va_start(ArgList, Format);
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
    v5 = __vsnprintf(Buffer, a2 - 1, Format, ArgList);
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
0x4064be  mov     edi, edi
0x4064c0  push    ebp
0x4064c1  mov     ebp, esp
0x4064c3  mov     eax, [ebp+arg_4]
0x4064c6  push    esi
0x4064c7  test    eax, eax
0x4064c9  jz      short loc_406507
0x4064cb  cmp     eax, 7FFFFFFFh
0x4064d0  ja      short loc_406507
0x4064d2  push    ebx
0x4064d3  mov     ebx, [ebp+Buffer]
0x4064d6  xor     esi, esi
0x4064d8  push    edi
0x4064d9  lea     edi, [eax-1]
0x4064dc  lea     eax, [ebp+ArgList]
0x4064df  push    eax; ArgList
0x4064e0  push    [ebp+Format]; Format
0x4064e3  push    edi; BufferCount
0x4064e4  push    ebx; Buffer
0x4064e5  call    ds:__imp___vsnprintf
0x4064eb  add     esp, 10h
0x4064ee  test    eax, eax
0x4064f0  js      short loc_4064FA
0x4064f2  cmp     eax, edi
0x4064f4  ja      short loc_4064FA
0x4064f6  jnz     short loc_406503
0x4064f8  jmp     short loc_4064FF
0x4064fa  mov     esi, 8007007Ah
0x4064ff  mov     byte ptr [edi+ebx], 0
0x406503  pop     edi
0x406504  pop     ebx
0x406505  jmp     short loc_406516
0x406507  mov     esi, 80070057h
0x40650c  test    eax, eax
0x40650e  jz      short loc_406516
0x406510  mov     ecx, [ebp+Buffer]
0x406513  mov     byte ptr [ecx], 0
0x406516  mov     eax, esi
0x406518  pop     esi
0x406519  pop     ebp
0x40651a  retn
```
