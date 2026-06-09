# __crt_stdio_output::common_data<wchar_t>::common_data<wchar_t>(void)

- ea: `0x411e67`
- end: `0x411eb1`
- name: `??0?$common_data@_W@__crt_stdio_output@@IAE@XZ`
- size: `74`
- prototype: `_DWORD *__thiscall(_DWORD *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x411eb1`

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
0x411e67  mov     edi, edi
0x411e69  push    ebp
0x411e6a  mov     ebp, esp
0x411e6c  push    ecx
0x411e6d  xor     edx, edx
0x411e6f  mov     [ebp+var_4], ecx
0x411e72  mov     [ecx], edx
0x411e74  xor     eax, eax
0x411e76  mov     [ecx+4], edx
0x411e79  mov     [ecx+8], edx
0x411e7c  mov     [ecx+0Ch], edx
0x411e7f  mov     [ecx+32h], ax
0x411e83  mov     eax, ecx
0x411e85  mov     [ecx+10h], edx
0x411e88  mov     [ecx+14h], edx
0x411e8b  mov     [ecx+18h], edx
0x411e8e  mov     [ecx+1Ch], edx
0x411e91  mov     [ecx+20h], edx
0x411e94  mov     [ecx+24h], edx
0x411e97  mov     [ecx+28h], edx
0x411e9a  mov     [ecx+30h], dl
0x411e9d  mov     [ecx+38h], edx
0x411ea0  mov     [ecx+3Ch], dl
0x411ea3  mov     [ecx+440h], edx
0x411ea9  mov     [ecx+444h], edx
0x411eaf  leave
0x411eb0  retn
```
