# sub_1806EFFF8

- ea: `0x1806efff8`
- end: `0x1806f0241`
- name: `sub_1806EFFF8`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1806effc0`

## callees

- `0x1805e796c`
- `0x1805e8bc0`
- `0x1806a7d94`
- `0x1806a7eb0`
- `0x1806ed5e0`
- `0x1806edf70`
- `0x1806efff8`
- `0x1806f3fa4`
- `0x1809c1340`

## import_xrefs

- `GDI32!DeleteObject` at `0x1806f0217`
- `GDI32!DeleteObject` at `0x1806f0217`
- `GDI32!CreateRectRgn` at `0x1806f0026`
- `GDI32!CreateRectRgn` at `0x1806f0026`
- `GDI32!RestoreDC` at `0x1806f0059`
- `GDI32!RestoreDC` at `0x1806f00fd`
- `GDI32!RestoreDC` at `0x1806f0059`
- `GDI32!RestoreDC` at `0x1806f00fd`
- `GDI32!GetClipRgn` at `0x1806f003e`
- `GDI32!GetClipRgn` at `0x1806f003e`
- `gdiplus!GdipResetClip` at `0x1806f01db`
- `gdiplus!GdipResetClip` at `0x1806f01db`
- `gdiplus!GdipSetClipRegion` at `0x1806f01b3`
- `gdiplus!GdipSetClipRegion` at `0x1806f01b3`
- `gdiplus!GdipReleaseDC` at `0x1806f006d`
- `gdiplus!GdipReleaseDC` at `0x1806f0126`
- `gdiplus!GdipReleaseDC` at `0x1806f006d`
- `gdiplus!GdipReleaseDC` at `0x1806f0126`
- `gdiplus!GdipDeleteRegion` at `0x1806f01d0`
- `gdiplus!GdipDeleteRegion` at `0x1806f01d0`

## pseudocode

```c
int __fastcall sub_1806EFFF8(__int64 a1)
{
  HRGN RectRgn; // rbx
  int v3; // edx
  __int64 v4; // rax
  __int64 v5; // r12
  __int64 v6; // r15
  int v7; // edx
  HDC *v8; // r14
  __int64 v9; // rcx
  HDC v10; // r15
  __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // r14
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // eax
  __int64 v20; // rax
  _BYTE v22[72]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v23; // [rsp+78h] [rbp+10h] BYREF
  HRGN v24; // [rsp+80h] [rbp+18h]

  *(_QWORD *)a1 = &off_180A59410;
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v24 = RectRgn;
  LODWORD(v23) = GetClipRgn(*(HDC *)(a1 + 32), RectRgn);
  v3 = *(_DWORD *)(a1 + 60);
  if ( v3 && !*(_BYTE *)(a1 + 41) )
    RestoreDC(*(HDC *)(a1 + 32), v3);
  if ( *(_BYTE *)(a1 + 40) )
  {
    v5 = a1 + 16;
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL);
    if ( !(unsigned __int8)sub_1806F3FA4(v6) )
    {
      sub_1805E8BC0(8753629);
      __debugbreak();
    }
    v7 = *(_DWORD *)(v6 + 568);
    v8 = (HDC *)(v6 + 560);
    if ( v7 )
      RestoreDC(*v8, v7);
    v9 = *(_QWORD *)(v6 + 576);
    if ( v9 )
    {
      v10 = *v8;
      v11 = sub_1806EDF70(v9);
      v12 = GdipReleaseDC(v11, v10);
      sub_1805E796C(v12, 38869191);
      v5 = a1 + 16;
    }
    *v8 = 0;
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v5 + 16LL) + 624LL))(*(_QWORD *)(*(_QWORD *)v5 + 16LL));
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 104LL))(v13);
    v15 = sub_1806EDF70(v14);
    sub_1806A7D94(v22, v15);
    if ( (_DWORD)v23 == 1 && RectRgn )
    {
      v23 = 0;
      sub_1806ED5E0(RectRgn, &v23);
      v16 = GdipSetClipRegion(v15, v23, 0);
      sub_1805E796C(v16, 38871069);
      if ( v23 )
        GdipDeleteRegion(v23, v17, v18);
    }
    else
    {
      v19 = GdipResetClip(v15);
      sub_1805E796C(v19, 38871070);
    }
    sub_1806A7EB0(v22);
  }
  else
  {
    GdipReleaseDC(*(_QWORD *)(a1 + 24), *(_QWORD *)(a1 + 32));
    if ( *(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 16LL) + 624LL))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL))
                  + 216) )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 16LL) + 624LL))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL));
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 88LL))(v4, a1 + 44);
    }
  }
  v20 = *(_QWORD *)(a1 + 16);
  *(_BYTE *)(v20 + 48) = 0;
  if ( RectRgn )
    LODWORD(v20) = DeleteObject(RectRgn);
  return v20;
}

```

## disassembly

```asm
0x1806efff8  mov     [rsp+arg_18], rbx
0x1806efffd  mov     [rsp+arg_0], rcx
0x1806f0002  push    rsi
0x1806f0003  push    r12
0x1806f0005  push    r13
0x1806f0007  push    r14
0x1806f0009  push    r15
0x1806f000b  sub     rsp, 40h
0x1806f000f  mov     rsi, rcx
0x1806f0012  lea     rax, off_180A59410
0x1806f0019  mov     [rcx], rax
0x1806f001c  xor     r9d, r9d; y2
0x1806f001f  xor     r8d, r8d; x2
0x1806f0022  xor     edx, edx; y1
0x1806f0024  xor     ecx, ecx; x1
0x1806f0026  call    cs:CreateRectRgn
0x1806f002c  mov     rbx, rax
0x1806f002f  mov     [rsp+68h+arg_10], rax
0x1806f0037  mov     rdx, rax; hrgn
0x1806f003a  mov     rcx, [rsi+20h]; hdc
0x1806f003e  call    cs:GetClipRgn
0x1806f0044  mov     dword ptr [rsp+68h+arg_8], eax
0x1806f0048  mov     edx, [rsi+3Ch]; nSavedDC
0x1806f004b  test    edx, edx
0x1806f004d  jz      short loc_1806F005F
0x1806f004f  cmp     byte ptr [rsi+29h], 0
0x1806f0053  jnz     short loc_1806F005F
0x1806f0055  mov     rcx, [rsi+20h]; hdc
0x1806f0059  call    cs:RestoreDC
0x1806f005f  cmp     byte ptr [rsi+28h], 0
0x1806f0063  jnz     short loc_1806F00CC
0x1806f0065  mov     rdx, [rsi+20h]
0x1806f0069  mov     rcx, [rsi+18h]
0x1806f006d  call    cs:GdipReleaseDC
0x1806f0073  mov     rax, [rsi+10h]
0x1806f0077  mov     rcx, [rax+10h]
0x1806f007b  mov     rax, [rcx]
0x1806f007e  mov     rax, [rax+270h]
0x1806f0085  call    cs:__guard_dispatch_icall_fptr
0x1806f008b  cmp     byte ptr [rax+0D8h], 0
0x1806f0092  jz      loc_1806F0207
0x1806f0098  mov     rax, [rsi+10h]
0x1806f009c  mov     rcx, [rax+10h]
0x1806f00a0  mov     rax, [rcx]
0x1806f00a3  mov     rax, [rax+270h]
0x1806f00aa  call    cs:__guard_dispatch_icall_fptr
0x1806f00b0  mov     r8, rax
0x1806f00b3  mov     rcx, [rax]
0x1806f00b6  mov     rax, [rcx+58h]
0x1806f00ba  lea     rdx, [rsi+2Ch]
0x1806f00be  mov     rcx, r8
0x1806f00c1  call    cs:__guard_dispatch_icall_fptr
0x1806f00c7  jmp     loc_1806F0207
0x1806f00cc  lea     r12, [rsi+10h]
0x1806f00d0  mov     rax, [r12]
0x1806f00d4  mov     r15, [rax+10h]
0x1806f00d8  mov     rcx, r15
0x1806f00db  call    sub_1806F3FA4
0x1806f00e0  test    al, al
0x1806f00e2  jz      loc_1806F0234
0x1806f00e8  mov     edx, [r15+238h]; nSavedDC
0x1806f00ef  lea     r14, [r15+230h]
0x1806f00f6  test    edx, edx
0x1806f00f8  jz      short loc_1806F0109
0x1806f00fa  mov     rcx, [r14]; hdc
0x1806f00fd  call    cs:RestoreDC
0x1806f0103  lea     r13, [rsi+10h]
0x1806f0107  jmp     short loc_1806F010C
0x1806f0109  mov     r13, r12
0x1806f010c  mov     rcx, [r15+240h]
0x1806f0113  test    rcx, rcx
0x1806f0116  jz      short loc_1806F013B
0x1806f0118  mov     r15, [r14]
0x1806f011b  call    sub_1806EDF70
0x1806f0120  mov     rdx, r15
0x1806f0123  mov     rcx, rax
0x1806f0126  call    cs:GdipReleaseDC
0x1806f012c  mov     ecx, eax
0x1806f012e  mov     edx, 25118C7h
0x1806f0133  call    sub_1805E796C
0x1806f0138  mov     r12, r13
0x1806f013b  mov     qword ptr [r14], 0
0x1806f0142  mov     rax, [r12]
0x1806f0146  mov     rcx, [rax+10h]
0x1806f014a  mov     rax, [rcx]
0x1806f014d  mov     rax, [rax+270h]
0x1806f0154  call    cs:__guard_dispatch_icall_fptr
0x1806f015a  mov     rdx, rax
0x1806f015d  mov     rcx, [rax]
0x1806f0160  mov     rax, [rcx+68h]
0x1806f0164  mov     rcx, rdx
0x1806f0167  call    cs:__guard_dispatch_icall_fptr
0x1806f016d  mov     rcx, rax
0x1806f0170  call    sub_1806EDF70
0x1806f0175  mov     r14, rax
0x1806f0178  mov     rdx, rax
0x1806f017b  lea     rcx, [rsp+68h+var_48]
0x1806f0180  call    sub_1806A7D94
0x1806f0185  nop
0x1806f0186  cmp     dword ptr [rsp+68h+arg_8], 1
0x1806f018b  jnz     short loc_1806F01D8
0x1806f018d  test    rbx, rbx
0x1806f0190  jz      short loc_1806F01D8
0x1806f0192  mov     [rsp+68h+arg_8], 0
0x1806f019b  lea     rdx, [rsp+68h+arg_8]
0x1806f01a0  mov     rcx, rbx
0x1806f01a3  call    sub_1806ED5E0
0x1806f01a8  xor     r8d, r8d
0x1806f01ab  mov     rdx, [rsp+68h+arg_8]
0x1806f01b0  mov     rcx, r14
0x1806f01b3  call    cs:GdipSetClipRegion
0x1806f01b9  mov     ecx, eax
0x1806f01bb  mov     edx, 251201Dh
0x1806f01c0  call    sub_1805E796C
0x1806f01c5  nop
0x1806f01c6  mov     rcx, [rsp+68h+arg_8]
0x1806f01cb  test    rcx, rcx
0x1806f01ce  jz      short loc_1806F01EE
0x1806f01d0  call    cs:GdipDeleteRegion
0x1806f01d6  jmp     short loc_1806F01EE
0x1806f01d8  mov     rcx, r14
0x1806f01db  call    cs:GdipResetClip
0x1806f01e1  mov     ecx, eax
0x1806f01e3  mov     edx, 251201Eh
0x1806f01e8  call    sub_1805E796C
0x1806f01ed  nop
0x1806f01ee  lea     rcx, [rsp+68h+var_48]
0x1806f01f3  call    sub_1806A7EB0
0x1806f01f8  jmp     short loc_1806F0207
0x1806f01fa  mov     rsi, [rsp+68h+arg_0]
0x1806f01ff  mov     rbx, [rsp+68h+arg_10]
0x1806f0207  mov     rax, [rsi+10h]
0x1806f020b  mov     byte ptr [rax+30h], 0
0x1806f020f  test    rbx, rbx
0x1806f0212  jz      short loc_1806F021E
0x1806f0214  mov     rcx, rbx; ho
0x1806f0217  call    cs:DeleteObject
0x1806f021d  nop
0x1806f021e  mov     rbx, [rsp+68h+arg_18]
0x1806f0226  add     rsp, 40h
0x1806f022a  pop     r15
0x1806f022c  pop     r14
0x1806f022e  pop     r13
0x1806f0230  pop     r12
0x1806f0232  pop     rsi
0x1806f0233  retn
0x1806f0234  mov     ecx, 8591DDh
0x1806f0239  call    sub_1805E8BC0
0x1806f023e  int     3; Trap to Debugger
```
