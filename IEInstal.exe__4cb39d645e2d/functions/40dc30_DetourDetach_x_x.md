# DetourDetach(x,x)

- ea: `0x40dc30`
- end: `0x40dd59`
- name: `_DetourDetach@8`
- size: `297`
- prototype: `DWORD __thiscall(void *this, LPCVOID *, LPCVOID lpAddress)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x409f13`

## callees

- `0x4026e7`
- `0x40dba0`
- `0x40dc30`
- `0x40eb05`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40dc31`
- `KERNEL32!GetCurrentThreadId` at `0x40dc31`
- `KERNEL32!VirtualProtect` at `0x40dce4`
- `KERNEL32!VirtualProtect` at `0x40dce4`
- `KERNEL32!GetLastError` at `0x40dcee`
- `KERNEL32!GetLastError` at `0x40dcee`

## pseudocode

```c
DWORD __thiscall DetourDetach(void *this, LPCVOID *a2, LPCVOID lpAddress)
{
  DWORD result; // eax
  _DWORD *v4; // esi
  DWORD LastError; // ebx
  int v6; // ebp
  int v7; // eax
  SIZE_T v8; // ecx
  void *v9; // ebx
  DWORD flOldProtect; // [esp+0h] [ebp-4h] BYREF

  flOldProtect = (DWORD)this;
  if ( dword_40F47C != GetCurrentThreadId() )
    return 4317;
  result = dword_40F480;
  if ( !dword_40F480 )
  {
    if ( !lpAddress )
      return 87;
    if ( !a2 )
      return 6;
    if ( !*a2 )
    {
      dword_40F480 = 6;
      dword_40F484 = (int)a2;
      return 6;
    }
    v4 = operator new(0x18u);
    if ( v4 )
    {
      v6 = DetourCodeFromPointer(*a2, 0);
      v7 = DetourCodeFromPointer(lpAddress, 0);
      v8 = *(unsigned __int8 *)(v6 + 54);
      v9 = (void *)(*(_DWORD *)(v6 + 64) - v8);
      if ( *(_BYTE *)(v6 + 54) && v8 <= 0x1E && *(_DWORD *)(v6 + 68) == v7 )
      {
        flOldProtect = 0;
        if ( VirtualProtect(v9, v8, 0x40u, &flOldProtect) )
        {
          v4[2] = a2;
          v4[4] = v6;
          v4[3] = v9;
          v4[1] = 1;
          v4[5] = flOldProtect;
          *v4 = lpMem;
          result = 0;
          lpMem = v4;
          return result;
        }
        LastError = GetLastError();
      }
      else
      {
        LastError = 9;
        if ( dword_40F474 )
          goto LABEL_20;
      }
    }
    else
    {
      LastError = 8;
    }
    dword_40F480 = LastError;
    if ( !v4 )
    {
LABEL_21:
      dword_40F484 = (int)a2;
      return LastError;
    }
LABEL_20:
    operator delete(v4);
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x40dc30  push    ecx
0x40dc31  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40dc37  cmp     dword_40F47C, eax
0x40dc3d  jz      short loc_40DC48
0x40dc3f  mov     eax, 10DDh
0x40dc44  pop     ecx
0x40dc45  retn    8
0x40dc48  mov     eax, dword_40F480
0x40dc4d  test    eax, eax
0x40dc4f  jnz     loc_40DD55
0x40dc55  push    ebx
0x40dc56  mov     ebx, [esp+8+lpAddress]
0x40dc5a  test    ebx, ebx
0x40dc5c  jnz     short loc_40DC66
0x40dc5e  lea     eax, [ebx+57h]
0x40dc61  pop     ebx
0x40dc62  pop     ecx
0x40dc63  retn    8
0x40dc66  push    edi
0x40dc67  mov     edi, [esp+0Ch+arg_0]
0x40dc6b  test    edi, edi
0x40dc6d  jz      short loc_40DC84
0x40dc6f  cmp     dword ptr [edi], 0
0x40dc72  jnz     short loc_40DC8F
0x40dc74  mov     dword_40F480, 6
0x40dc7e  mov     dword_40F484, edi
0x40dc84  pop     edi
0x40dc85  mov     eax, 6
0x40dc8a  pop     ebx
0x40dc8b  pop     ecx
0x40dc8c  retn    8
0x40dc8f  push    ebp
0x40dc90  push    esi
0x40dc91  push    18h; dwBytes
0x40dc93  call    ??2@YAPAXI@Z; operator new(uint)
0x40dc98  mov     esi, eax
0x40dc9a  add     esp, 4
0x40dc9d  test    esi, esi
0x40dc9f  jnz     short loc_40DCA9
0x40dca1  lea     ebx, [eax+8]
0x40dca4  jmp     loc_40DD34
0x40dca9  push    0; int
0x40dcab  push    dword ptr [edi]; lpAddress
0x40dcad  call    _DetourCodeFromPointer@8; DetourCodeFromPointer(x,x)
0x40dcb2  push    0; int
0x40dcb4  push    ebx; lpAddress
0x40dcb5  mov     ebp, eax
0x40dcb7  call    _DetourCodeFromPointer@8; DetourCodeFromPointer(x,x)
0x40dcbc  movzx   ecx, byte ptr [ebp+36h]
0x40dcc0  mov     ebx, [ebp+40h]
0x40dcc3  sub     ebx, ecx
0x40dcc5  test    ecx, ecx
0x40dcc7  jz      short loc_40DD26
0x40dcc9  cmp     ecx, 1Eh
0x40dccc  ja      short loc_40DD26
0x40dcce  cmp     [ebp+44h], eax
0x40dcd1  jnz     short loc_40DD26
0x40dcd3  lea     eax, [esp+14h+flOldProtect]
0x40dcd7  mov     [esp+14h+flOldProtect], 0
0x40dcdf  push    eax; lpflOldProtect
0x40dce0  push    40h ; '@'; flNewProtect
0x40dce2  push    ecx; dwSize
0x40dce3  push    ebx; lpAddress
0x40dce4  call    ds:__imp__VirtualProtect@16; VirtualProtect(x,x,x,x)
0x40dcea  test    eax, eax
0x40dcec  jnz     short loc_40DCF8
0x40dcee  call    ds:__imp__GetLastError@0; GetLastError()
0x40dcf4  mov     ebx, eax
0x40dcf6  jmp     short loc_40DD34
0x40dcf8  mov     [esi+8], edi
0x40dcfb  mov     [esi+10h], ebp
0x40dcfe  mov     [esi+0Ch], ebx
0x40dd01  mov     dword ptr [esi+4], 1
0x40dd08  mov     eax, [esp+14h+flOldProtect]
0x40dd0c  mov     [esi+14h], eax
0x40dd0f  mov     eax, lpMem
0x40dd14  mov     [esi], eax
0x40dd16  xor     eax, eax
0x40dd18  mov     lpMem, esi
0x40dd1e  pop     esi
0x40dd1f  pop     ebp
0x40dd20  pop     edi
0x40dd21  pop     ebx
0x40dd22  pop     ecx
0x40dd23  retn    8
0x40dd26  cmp     dword_40F474, 0
0x40dd2d  mov     ebx, 9
0x40dd32  jnz     short loc_40DD3E
0x40dd34  mov     dword_40F480, ebx
0x40dd3a  test    esi, esi
0x40dd3c  jz      short loc_40DD49
0x40dd3e  push    18h; unsigned int
0x40dd40  push    esi; lpMem
0x40dd41  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x40dd46  add     esp, 8
0x40dd49  pop     esi
0x40dd4a  pop     ebp
0x40dd4b  mov     dword_40F484, edi
0x40dd51  mov     eax, ebx
0x40dd53  pop     edi
0x40dd54  pop     ebx
0x40dd55  pop     ecx
0x40dd56  retn    8
```
