# DllInitCodec

- ea: `0x1800059d0`
- end: `0x180005a1c`
- name: `DllInitCodec`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005950`

## callees

- `0x1800059d0`
- `0x180005a30`

## pseudocode

```c
__int64 __fastcall DllInitCodec(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v5; // rcx

  if ( a1 == 3 )
  {
    v5 = 2;
  }
  else
  {
    result = a1;
    if ( a1 )
    {
      if ( a1 != 1 )
        return result;
      v5 = 0;
    }
    else
    {
      v5 = 3;
    }
  }
  result = auippIntelIPP(v5, a2, a3);
  if ( (int)result < 0 && a1 == 1 )
  {
    _InterlockedIncrement(&dword_1800B4D28);
    _InterlockedIncrement(&dword_1800B4D28);
  }
  return result;
}

```

## disassembly

```asm
0x1800059d0  push    rbx
0x1800059d2  sub     rsp, 20h
0x1800059d6  mov     ebx, ecx
0x1800059d8  cmp     ecx, 3
0x1800059db  jz      short loc_1800059EE
0x1800059dd  mov     eax, ecx
0x1800059df  test    ecx, ecx
0x1800059e1  jz      short loc_180005A15
0x1800059e3  cmp     eax, 1
0x1800059e6  jz      short loc_180005A11
0x1800059e8  add     rsp, 20h
0x1800059ec  pop     rbx
0x1800059ed  retn
0x1800059ee  mov     ecx, 2
0x1800059f3  call    auippIntelIPP
0x1800059f8  test    eax, eax
0x1800059fa  jns     short loc_1800059E8
0x1800059fc  cmp     ebx, 1
0x1800059ff  jnz     short loc_1800059E8
0x180005a01  lock inc cs:dword_1800B4D28
0x180005a08  lock inc cs:dword_1800B4D28
0x180005a0f  jmp     short loc_1800059E8
0x180005a11  xor     ecx, ecx
0x180005a13  jmp     short loc_1800059F3
0x180005a15  mov     ecx, 3
0x180005a1a  jmp     short loc_1800059F3
```
