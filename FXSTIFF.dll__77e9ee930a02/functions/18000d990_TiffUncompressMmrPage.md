# TiffUncompressMmrPage

- ea: `0x18000d990`
- end: `0x18000da6a`
- name: `TiffUncompressMmrPage`
- size: `218`
- prototype: `__int64 __fastcall(__int64, int, int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e784`

## callees

- `0x180009f04`
- `0x18000d990`
- `0x18000da70`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000d9ec`
- `KERNEL32!SetLastError` at `0x18000d9ec`

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
0x18000d990  push    rbx
0x18000d992  push    rbp
0x18000d993  push    rsi
0x18000d994  push    rdi
0x18000d995  push    r15
0x18000d997  sub     rsp, 30h
0x18000d99b  mov     rdi, r9
0x18000d99e  mov     esi, r8d
0x18000d9a1  mov     rbp, rdx
0x18000d9a4  mov     rbx, rcx
0x18000d9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9ae  lea     r15, WPP_GLOBAL_Control
0x18000d9b5  cmp     rcx, r15
0x18000d9b8  jz      short loc_18000D9DB
0x18000d9ba  test    byte ptr [rcx+1Ch], 2
0x18000d9be  jz      short loc_18000D9DB
0x18000d9c0  cmp     byte ptr [rcx+19h], 5
0x18000d9c4  jb      short loc_18000D9DB
0x18000d9c6  mov     rcx, [rcx+10h]
0x18000d9ca  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000d9d1  mov     edx, 30h ; '0'
0x18000d9d6  call    WPP_SF_
0x18000d9db  mov     eax, [rbx+620h]
0x18000d9e1  cmp     eax, [rdi]
0x18000d9e3  jbe     short loc_18000DA29
0x18000d9e5  mov     ecx, 6Fh ; 'o'; dwErrCode
0x18000d9ea  mov     [rdi], eax
0x18000d9ec  call    cs:__imp_SetLastError
0x18000d9f3  nop     dword ptr [rax+rax+00h]
0x18000d9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9ff  cmp     rcx, r15
0x18000da02  jz      short loc_18000DA25
0x18000da04  test    byte ptr [rcx+1Ch], 2
0x18000da08  jz      short loc_18000DA25
0x18000da0a  cmp     byte ptr [rcx+19h], 2
0x18000da0e  jb      short loc_18000DA25
0x18000da10  mov     rcx, [rcx+10h]
0x18000da14  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000da1b  mov     edx, 31h ; '1'
0x18000da20  call    WPP_SF_
0x18000da25  xor     eax, eax
0x18000da27  jmp     short loc_18000DA5E
0x18000da29  mov     r8d, [rbx+61Ch]; int
0x18000da30  xor     eax, eax
0x18000da32  mov     edx, [rbx+610h]; int
0x18000da38  mov     r9, rbp; int
0x18000da3b  mov     rcx, [rbx+600h]; int
0x18000da42  mov     [rsp+58h+var_30], rdi
0x18000da47  mov     [rbx+624h], rax
0x18000da4e  mov     [rbx+684h], rax
0x18000da55  mov     dword ptr [rsp+58h+Size], esi; Size
0x18000da59  call    TiffUncompressMmrPageRaw
0x18000da5e  add     rsp, 30h
0x18000da62  pop     r15
0x18000da64  pop     rdi
0x18000da65  pop     rsi
0x18000da66  pop     rbp
0x18000da67  pop     rbx
0x18000da68  retn
```
