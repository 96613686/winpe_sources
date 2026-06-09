# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const * const)

- ea: `0x180006308`
- end: `0x18000633d`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180001130`
- `0x18000681c`
- `0x180008c1c`
- `0x18000bafc`
- `0x18000c808`
- `0x18000ca20`
- `0x18000e0e4`
- `0x18000eb20`
- `0x18000eb50`
- `0x18000eb80`
- `0x18000ebb0`
- `0x18000ebe0`
- `0x18000ecb0`

## callees

- `0x1800061d0`
- `0x180006308`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  __int64 v3; // r8

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(a2 + 2 * v3) );
  std::wstring::_Construct<1,unsigned short const *>();
  return a1;
}

```

## disassembly

```asm
0x180006308  push    rbx
0x18000630a  sub     rsp, 20h
0x18000630e  xor     eax, eax
0x180006310  xorps   xmm0, xmm0
0x180006313  movups  xmmword ptr [rcx], xmm0
0x180006316  mov     [rcx+10h], rax
0x18000631a  mov     rbx, rcx
0x18000631d  mov     [rcx+18h], rax
0x180006321  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006325  inc     r8
0x180006328  cmp     [rdx+r8*2], ax
0x18000632d  jnz     short loc_180006325
0x18000632f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180006334  mov     rax, rbx
0x180006337  add     rsp, 20h
0x18000633b  pop     rbx
0x18000633c  retn
```
