# __crt_stdio_output::common_data<wchar_t>::common_data<wchar_t>(void)

- ea: `0x40c9d4`
- end: `0x40ca1e`
- name: `??0?$common_data@_W@__crt_stdio_output@@IAE@XZ`
- size: `74`
- prototype: `_DWORD *__thiscall(_DWORD *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x40ca1e`

## pseudocode

```c
_DWORD *__thiscall __crt_stdio_output::common_data<wchar_t>::common_data<wchar_t>(_DWORD *this)
{
  _DWORD *result; // eax

  *this = 0;
  this[1] = 0;
  this[2] = 0;
  this[3] = 0;
  *((_WORD *)this + 25) = 0;
  result = this;
  this[4] = 0;
  this[5] = 0;
  this[6] = 0;
  this[7] = 0;
  this[8] = 0;
  this[9] = 0;
  this[10] = 0;
  *((_BYTE *)this + 48) = 0;
  this[14] = 0;
  *((_BYTE *)this + 60) = 0;
  this[272] = 0;
  this[273] = 0;
  return result;
}

```

## disassembly

```asm
0x40c9d4  mov     edi, edi
0x40c9d6  push    ebp
0x40c9d7  mov     ebp, esp
0x40c9d9  push    ecx
0x40c9da  xor     edx, edx
0x40c9dc  mov     [ebp+var_4], ecx
0x40c9df  mov     [ecx], edx
0x40c9e1  xor     eax, eax
0x40c9e3  mov     [ecx+4], edx
0x40c9e6  mov     [ecx+8], edx
0x40c9e9  mov     [ecx+0Ch], edx
0x40c9ec  mov     [ecx+32h], ax
0x40c9f0  mov     eax, ecx
0x40c9f2  mov     [ecx+10h], edx
0x40c9f5  mov     [ecx+14h], edx
0x40c9f8  mov     [ecx+18h], edx
0x40c9fb  mov     [ecx+1Ch], edx
0x40c9fe  mov     [ecx+20h], edx
0x40ca01  mov     [ecx+24h], edx
0x40ca04  mov     [ecx+28h], edx
0x40ca07  mov     [ecx+30h], dl
0x40ca0a  mov     [ecx+38h], edx
0x40ca0d  mov     [ecx+3Ch], dl
0x40ca10  mov     [ecx+440h], edx
0x40ca16  mov     [ecx+444h], edx
0x40ca1c  leave
0x40ca1d  retn
```
