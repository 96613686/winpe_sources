# TiffUncompressMmrPage

- ea: `0x18000d3d0`
- end: `0x18000d4a3`
- name: `TiffUncompressMmrPage`
- size: `211`
- prototype: `__int64 __fastcall(__int64, int, int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e16c`

## callees

- `0x180009a7c`
- `0x18000d3d0`
- `0x18000d4b0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000d42c`
- `KERNEL32!SetLastError` at `0x18000d42c`

## pseudocode

```c
__int64 __fastcall TiffUncompressMmrPage(__int64 a1, int a2, int a3, unsigned int *a4)
{
  unsigned int v8; // eax
  int v10; // r8d
  int v11; // edx
  __int64 v12; // rcx
  size_t Size; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
  }
  v8 = *(_DWORD *)(a1 + 1568);
  if ( v8 <= *a4 )
  {
    v10 = *(_DWORD *)(a1 + 1564);
    v11 = *(_DWORD *)(a1 + 1552);
    v12 = *(_QWORD *)(a1 + 1536);
    *(_QWORD *)(a1 + 1572) = 0;
    *(_QWORD *)(a1 + 1668) = 0;
    LODWORD(Size) = a3;
    return TiffUncompressMmrPageRaw(v12, v11, v10, a2, Size);
  }
  else
  {
    *a4 = v8;
    SetLastError(0x6Fu);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000d3d0  push    rbx
0x18000d3d2  push    rbp
0x18000d3d3  push    rsi
0x18000d3d4  push    rdi
0x18000d3d5  push    r15
0x18000d3d7  sub     rsp, 30h
0x18000d3db  mov     rdi, r9
0x18000d3de  mov     esi, r8d
0x18000d3e1  mov     rbp, rdx
0x18000d3e4  mov     rbx, rcx
0x18000d3e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3ee  lea     r15, WPP_GLOBAL_Control
0x18000d3f5  cmp     rcx, r15
0x18000d3f8  jz      short loc_18000D41B
0x18000d3fa  test    byte ptr [rcx+1Ch], 2
0x18000d3fe  jz      short loc_18000D41B
0x18000d400  cmp     byte ptr [rcx+19h], 5
0x18000d404  jb      short loc_18000D41B
0x18000d406  mov     rcx, [rcx+10h]
0x18000d40a  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000d411  mov     edx, 30h ; '0'
0x18000d416  call    WPP_SF_
0x18000d41b  mov     eax, [rbx+620h]
0x18000d421  cmp     eax, [rdi]
0x18000d423  jbe     short loc_18000D463
0x18000d425  mov     ecx, 6Fh ; 'o'; dwErrCode
0x18000d42a  mov     [rdi], eax
0x18000d42c  call    cs:__imp_SetLastError
0x18000d432  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d439  cmp     rcx, r15
0x18000d43c  jz      short loc_18000D45F
0x18000d43e  test    byte ptr [rcx+1Ch], 2
0x18000d442  jz      short loc_18000D45F
0x18000d444  cmp     byte ptr [rcx+19h], 2
0x18000d448  jb      short loc_18000D45F
0x18000d44a  mov     rcx, [rcx+10h]
0x18000d44e  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000d455  mov     edx, 31h ; '1'
0x18000d45a  call    WPP_SF_
0x18000d45f  xor     eax, eax
0x18000d461  jmp     short loc_18000D498
0x18000d463  mov     r8d, [rbx+61Ch]; int
0x18000d46a  xor     eax, eax
0x18000d46c  mov     edx, [rbx+610h]; int
0x18000d472  mov     r9, rbp; int
0x18000d475  mov     rcx, [rbx+600h]; int
0x18000d47c  mov     [rsp+58h+var_30], rdi
0x18000d481  mov     [rbx+624h], rax
0x18000d488  mov     [rbx+684h], rax
0x18000d48f  mov     dword ptr [rsp+58h+Size], esi; Size
0x18000d493  call    TiffUncompressMmrPageRaw
0x18000d498  add     rsp, 30h
0x18000d49c  pop     r15
0x18000d49e  pop     rdi
0x18000d49f  pop     rsi
0x18000d4a0  pop     rbp
0x18000d4a1  pop     rbx
0x18000d4a2  retn
```
