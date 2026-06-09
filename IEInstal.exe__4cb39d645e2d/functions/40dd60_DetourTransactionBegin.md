# DetourTransactionBegin()

- ea: `0x40dd60`
- end: `0x40dddd`
- name: `_DetourTransactionBegin@0`
- size: `125`
- prototype: `DWORD __thiscall(void *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x409e9d`
- `0x409f13`

## callees

- `0x40dd60`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40dd6a`
- `KERNEL32!GetCurrentThreadId` at `0x40dd6a`
- `KERNEL32!VirtualProtect` at `0x40ddad`
- `KERNEL32!VirtualProtect` at `0x40ddad`
- `KERNEL32!GetLastError` at `0x40ddc8`
- `KERNEL32!GetLastError` at `0x40ddc8`

## pseudocode

```c
DWORD __thiscall DetourTransactionBegin(void *this)
{
  _DWORD *v1; // esi
  DWORD result; // eax
  DWORD flOldProtect; // [esp+0h] [ebp-4h] BYREF

  flOldProtect = (DWORD)this;
  if ( dword_40F47C || _InterlockedCompareExchange(&dword_40F47C, GetCurrentThreadId(), 0) )
    return 4317;
  v1 = lpBaseAddress;
  lpMem = 0;
  dword_40F488 = 0;
  dword_40F484 = 0;
  if ( lpBaseAddress )
  {
    while ( VirtualProtect(v1, 0x10000u, 0x40u, &flOldProtect) )
    {
      v1 = (_DWORD *)v1[1];
      if ( !v1 )
        goto LABEL_6;
    }
    result = GetLastError();
    dword_40F480 = result;
  }
  else
  {
LABEL_6:
    result = 0;
    dword_40F480 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x40dd60  push    ecx
0x40dd61  cmp     dword_40F47C, 0
0x40dd68  jnz     short loc_40DDD6
0x40dd6a  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40dd70  mov     ecx, eax
0x40dd72  mov     edx, offset dword_40F47C
0x40dd77  xor     eax, eax
0x40dd79  lock cmpxchg [edx], ecx
0x40dd7d  test    eax, eax
0x40dd7f  jnz     short loc_40DDD6
0x40dd81  push    esi
0x40dd82  mov     esi, lpBaseAddress
0x40dd88  mov     lpMem, eax
0x40dd8d  mov     dword_40F488, eax
0x40dd92  mov     dword_40F484, eax
0x40dd97  test    esi, esi
0x40dd99  jz      short loc_40DDBE
0x40dd9b  nop     dword ptr [eax+eax+00h]
0x40dda0  lea     eax, [esp+8+flOldProtect]
0x40dda4  push    eax; lpflOldProtect
0x40dda5  push    40h ; '@'; flNewProtect
0x40dda7  push    10000h; dwSize
0x40ddac  push    esi; lpAddress
0x40ddad  call    ds:__imp__VirtualProtect@16; VirtualProtect(x,x,x,x)
0x40ddb3  test    eax, eax
0x40ddb5  jz      short loc_40DDC8
0x40ddb7  mov     esi, [esi+4]
0x40ddba  test    esi, esi
0x40ddbc  jnz     short loc_40DDA0
0x40ddbe  xor     eax, eax
0x40ddc0  mov     dword_40F480, eax
0x40ddc5  pop     esi
0x40ddc6  pop     ecx
0x40ddc7  retn
0x40ddc8  call    ds:__imp__GetLastError@0; GetLastError()
0x40ddce  mov     dword_40F480, eax
0x40ddd3  pop     esi
0x40ddd4  pop     ecx
0x40ddd5  retn
0x40ddd6  mov     eax, 10DDh
0x40dddb  pop     ecx
0x40dddc  retn
```
