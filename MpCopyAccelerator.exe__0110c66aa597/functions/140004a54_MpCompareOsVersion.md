# MpCompareOsVersion

- ea: `0x140004a54`
- end: `0x140004a9e`
- name: `MpCompareOsVersion`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004adc`

## callees

- `0x1400025dc`
- `0x140004a54`

## pseudocode

```c
__int64 __fastcall MpCompareOsVersion(unsigned int a1, unsigned int a2)
{
  __int64 WindowsVersionInfo; // rax
  unsigned int v5; // eax

  WindowsVersionInfo = MpGetWindowsVersionInfo();
  if ( *(_DWORD *)(WindowsVersionInfo + 292) <= a1 )
  {
    if ( *(_DWORD *)(WindowsVersionInfo + 292) < a1 )
      return 0xFFFFFFFFLL;
    if ( a2 == -1 )
      return 0;
    v5 = *(unsigned __int16 *)(WindowsVersionInfo + 284);
    if ( v5 <= a2 )
      return (unsigned int)-(v5 < a2);
  }
  return 1;
}

```

## disassembly

```asm
0x140004a54  mov     [rsp+arg_0], rbx
0x140004a59  push    rdi
0x140004a5a  sub     rsp, 20h
0x140004a5e  mov     ebx, edx
0x140004a60  mov     edi, ecx
0x140004a62  call    MpGetWindowsVersionInfo
0x140004a67  cmp     [rax+124h], edi
0x140004a6d  ja      short loc_140004A8E
0x140004a6f  jb      short loc_140004A89
0x140004a71  cmp     ebx, 0FFFFFFFFh
0x140004a74  jz      short loc_140004A85
0x140004a76  movzx   eax, word ptr [rax+11Ch]
0x140004a7d  cmp     eax, ebx
0x140004a7f  ja      short loc_140004A8E
0x140004a81  sbb     eax, eax
0x140004a83  jmp     short loc_140004A93
0x140004a85  xor     eax, eax
0x140004a87  jmp     short loc_140004A93
0x140004a89  or      eax, 0FFFFFFFFh
0x140004a8c  jmp     short loc_140004A93
0x140004a8e  mov     eax, 1
0x140004a93  mov     rbx, [rsp+28h+arg_0]
0x140004a98  add     rsp, 20h
0x140004a9c  pop     rdi
0x140004a9d  retn
```
