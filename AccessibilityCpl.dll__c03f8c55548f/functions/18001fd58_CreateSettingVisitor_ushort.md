# CreateSettingVisitor(ushort)

- ea: `0x18001fd58`
- end: `0x18001fe08`
- name: `?CreateSettingVisitor@@YAPEAVSettingVisitor@@G@Z`
- size: `176`
- prototype: `struct SettingVisitor *__fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x18000314c`
- `0x18001fd58`

## import_xrefs

- `DUI70!StrToID` at `0x18001fd6b`
- `DUI70!StrToID` at `0x18001fdb3`
- `DUI70!StrToID` at `0x18001fd6b`
- `DUI70!StrToID` at `0x18001fdb3`

## string_xrefs

- `0x18001fd64`: `pageRecommendations`

## pseudocode

```c
struct SettingVisitor *__fastcall CreateSettingVisitor(__int16 a1)
{
  unsigned __int64 v2; // rdx
  _DWORD *v3; // rbx
  void **v4; // rax
  unsigned int i; // edi
  int v6; // edi

  if ( a1 == (unsigned __int16)StrToID(L"pageRecommendations") )
  {
    v3 = DirectUI::HAllocAndZero((DirectUI *)0x10, v2);
    if ( v3 )
    {
      v4 = &CountingVisitor::`vftable';
      v3[2] = 0;
LABEL_12:
      *(_QWORD *)v3 = v4;
      return (struct SettingVisitor *)v3;
    }
    return 0;
  }
  v3 = 0;
  for ( i = 1; i < 0xA; ++i )
  {
    if ( a1 == (unsigned __int16)StrToID(qword_180030350[2 * i]) )
      goto LABEL_9;
  }
  i = 0;
LABEL_9:
  v6 = qword_180030350[2 * (int)i + 1];
  if ( v6 )
  {
    v3 = DirectUI::HAllocAndZero((DirectUI *)0x10, v2);
    if ( v3 )
    {
      v4 = &BitGatherVisitor::`vftable';
      v3[2] = v6;
      v3[3] = 0;
      goto LABEL_12;
    }
    return 0;
  }
  return (struct SettingVisitor *)v3;
}

```

## disassembly

```asm
0x18001fd58  push    rbx
0x18001fd5a  push    rbp
0x18001fd5b  push    rsi
0x18001fd5c  push    rdi
0x18001fd5d  sub     rsp, 28h
0x18001fd61  movzx   esi, cx
0x18001fd64  lea     rcx, aPagerecommenda; "pageRecommendations"
0x18001fd6b  call    cs:__imp_StrToID
0x18001fd71  cmp     si, ax
0x18001fd74  jnz     short loc_18001FD98
0x18001fd76  mov     ecx, 10h; this
0x18001fd7b  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18001fd80  mov     rbx, rax
0x18001fd83  test    rax, rax
0x18001fd86  jz      short loc_18001FDFA
0x18001fd88  lea     rax, ??_7CountingVisitor@@6B@; const CountingVisitor::`vftable'
0x18001fd8f  mov     dword ptr [rbx+8], 0
0x18001fd96  jmp     short loc_18001FDF5
0x18001fd98  xor     ebx, ebx
0x18001fd9a  lea     rbp, qword_180030350
0x18001fda1  lea     edi, [rbx+1]
0x18001fda4  cmp     edi, 0Ah
0x18001fda7  jnb     short loc_18001FDC2
0x18001fda9  mov     ecx, edi
0x18001fdab  add     rcx, rcx
0x18001fdae  mov     rcx, [rbp+rcx*8+0]
0x18001fdb3  call    cs:__imp_StrToID
0x18001fdb9  cmp     si, ax
0x18001fdbc  jz      short loc_18001FDC4
0x18001fdbe  inc     edi
0x18001fdc0  jmp     short loc_18001FDA4
0x18001fdc2  xor     edi, edi
0x18001fdc4  movsxd  rax, edi
0x18001fdc7  add     rax, rax
0x18001fdca  mov     edi, [rbp+rax*8+8]
0x18001fdce  test    edi, edi
0x18001fdd0  jz      short loc_18001FDFC
0x18001fdd2  mov     ecx, 10h; this
0x18001fdd7  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18001fddc  mov     rbx, rax
0x18001fddf  test    rax, rax
0x18001fde2  jz      short loc_18001FDFA
0x18001fde4  lea     rax, ??_7BitGatherVisitor@@6B@; const BitGatherVisitor::`vftable'
0x18001fdeb  mov     [rbx+8], edi
0x18001fdee  mov     dword ptr [rbx+0Ch], 0
0x18001fdf5  mov     [rbx], rax
0x18001fdf8  jmp     short loc_18001FDFC
0x18001fdfa  xor     ebx, ebx
0x18001fdfc  mov     rax, rbx
0x18001fdff  add     rsp, 28h
0x18001fe03  pop     rdi
0x18001fe04  pop     rsi
0x18001fe05  pop     rbp
0x18001fe06  pop     rbx
0x18001fe07  retn
```
