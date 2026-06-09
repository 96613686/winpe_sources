# MpCompareOsVersionAndBuildNumber

- ea: `0x140004aa0`
- end: `0x140004adb`
- name: `MpCompareOsVersionAndBuildNumber`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004af8`
- `0x140004b1c`

## callees

- `0x1400025dc`
- `0x140004aa0`

## pseudocode

```c
__int64 __fastcall MpCompareOsVersionAndBuildNumber(unsigned int a1, unsigned int a2)
{
  __int64 WindowsVersionInfo; // rax

  WindowsVersionInfo = MpGetWindowsVersionInfo();
  if ( *(_DWORD *)(WindowsVersionInfo + 292) <= a1 )
  {
    if ( *(_DWORD *)(WindowsVersionInfo + 292) < a1 )
      return 0xFFFFFFFFLL;
    if ( *(_DWORD *)(WindowsVersionInfo + 20) <= a2 )
      return (unsigned int)-(*(_DWORD *)(WindowsVersionInfo + 20) < a2);
  }
  return 1;
}

```

## disassembly

```asm
0x140004aa0  mov     [rsp+arg_0], rbx
0x140004aa5  push    rdi
0x140004aa6  sub     rsp, 20h
0x140004aaa  mov     ebx, edx
0x140004aac  mov     edi, ecx
0x140004aae  call    MpGetWindowsVersionInfo
0x140004ab3  cmp     [rax+124h], edi
0x140004ab9  ja      short loc_140004ACB
0x140004abb  jb      short loc_140004AC6
0x140004abd  cmp     [rax+14h], ebx
0x140004ac0  ja      short loc_140004ACB
0x140004ac2  sbb     eax, eax
0x140004ac4  jmp     short loc_140004AD0
0x140004ac6  or      eax, 0FFFFFFFFh
0x140004ac9  jmp     short loc_140004AD0
0x140004acb  mov     eax, 1
0x140004ad0  mov     rbx, [rsp+28h+arg_0]
0x140004ad5  add     rsp, 20h
0x140004ad9  pop     rdi
0x140004ada  retn
```
