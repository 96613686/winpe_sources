# sub_1806EFCC4

- ea: `0x1806efcc4`
- end: `0x1806effbc`
- name: `sub_1806EFCC4`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1806f282c`

## callees

- `0x1800164c0`
- `0x18007412c`
- `0x180075204`
- `0x1805e796c`
- `0x1805e8bc0`
- `0x1805ef794`
- `0x1805efbc8`
- `0x1806edf70`
- `0x1806efcc4`
- `0x1806f3fa4`
- `0x1806f4298`
- `0x1809be7b4`
- `0x1809c10de`
- `0x1809c1340`

## import_xrefs

- `GDI32!DeleteObject` at `0x1806eff4e`
- `GDI32!DeleteObject` at `0x1806eff4e`
- `GDI32!SaveDC` at `0x1806efea8`
- `GDI32!SaveDC` at `0x1806efece`
- `GDI32!SaveDC` at `0x1806eff14`
- `GDI32!SaveDC` at `0x1806efea8`
- `GDI32!SaveDC` at `0x1806efece`
- `GDI32!SaveDC` at `0x1806eff14`
- `GDI32!SelectClipRgn` at `0x1806efede`
- `GDI32!SelectClipRgn` at `0x1806eff23`
- `GDI32!SelectClipRgn` at `0x1806efede`
- `GDI32!SelectClipRgn` at `0x1806eff23`
- `gdiplus!GdipGetRegionHRgn` at `0x1806efdb0`
- `gdiplus!GdipGetRegionHRgn` at `0x1806efdb0`
- `gdiplus!GdipCreateRegion` at `0x1806efd5e`
- `gdiplus!GdipCreateRegion` at `0x1806efd5e`
- `gdiplus!GdipGetClip` at `0x1806efd78`
- `gdiplus!GdipGetClip` at `0x1806efd78`
- `gdiplus!GdipGetDC` at `0x1806efe93`
- `gdiplus!GdipGetDC` at `0x1806efef5`
- `gdiplus!GdipGetDC` at `0x1806efe93`
- `gdiplus!GdipGetDC` at `0x1806efef5`
- `gdiplus!GdipDeleteRegion` at `0x1806eff37`
- `gdiplus!GdipDeleteRegion` at `0x1806eff37`

## pseudocode

```c
__int64 __fastcall sub_1806EFCC4(__int64 a1, __int64 a2, _OWORD *a3, char a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int Clip; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned int RegionHRgn; // eax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  HDC *v19; // rdi
  HDC v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int DC; // eax
  HRGN v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  HDC *v27; // rbx
  unsigned int v28; // eax
  HRGN v29; // rdi
  __int64 v31; // [rsp+50h] [rbp+30h] BYREF
  HRGN hrgn; // [rsp+58h] [rbp+38h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp+48h] BYREF

  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &off_180A59410;
  *(_QWORD *)(a1 + 16) = a2;
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 16) + 624LL))(*(_QWORD *)(a2 + 16));
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  *(_QWORD *)(a1 + 24) = sub_1806EDF70(v9);
  *(_BYTE *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 41) = a4;
  *(_OWORD *)(a1 + 44) = *a3;
  *(_DWORD *)(a1 + 60) = 0;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 16) + 48LL) )
  {
    sub_180075204(2753992);
    sub_1805EF794(2753993);
    goto LABEL_27;
  }
  hrgn = 0;
  v31 = 0;
  v10 = GdipCreateRegion(&v31);
  sub_1805E796C(v10, 38871065);
  Clip = GdipGetClip(*(_QWORD *)(a1 + 24), v31);
  sub_1805E796C(Clip, 38871066);
  if ( hrgn )
  {
    if ( (unsigned __int8)sub_1800164C0(v13, v12, v14) )
    {
      pExceptionObject = 507311371;
      throw (int *)&pExceptionObject;
    }
LABEL_27:
    sub_18007412C(507311371, 0);
  }
  RegionHRgn = GdipGetRegionHRgn(v31, *(_QWORD *)(a1 + 24), &hrgn);
  sub_1805E796C(RegionHRgn, 38871067);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 16LL) + 464LL))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL)) == 3
    && (v16 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL),
        v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 928LL))(v16),
        *(_QWORD *)(a1 + 24) = sub_1806EDF70(v17),
        (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v16 + 776LL))(v16))
    && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v16 + 808LL))(v16) )
  {
    sub_1809BE7B4(*(_QWORD *)(v16 + 8));
    v18 = sub_1806F4298(v16);
    *(_QWORD *)(a1 + 24) = sub_1806EDF70(v18);
    v19 = (HDC *)(v16 + 560);
    if ( *(_QWORD *)(v16 + 560) )
    {
      sub_1805E8BC0(24142472);
      __debugbreak();
    }
    if ( (unsigned __int8)sub_1806F3FA4(v16) )
    {
      v21 = sub_1806F4298(v16);
      v22 = sub_1806EDF70(v21);
      DC = GdipGetDC(v22, v16 + 560);
      sub_1805E796C(DC, 38869190);
      *(_DWORD *)(v16 + 568) = SaveDC(*v19);
      v20 = *v19;
    }
    else
    {
      v20 = 0;
    }
    *(_QWORD *)(a1 + 32) = v20;
    if ( !v20 )
      sub_1805EFBC8(24142473);
    v24 = hrgn;
    if ( !*(_BYTE *)(a1 + 41) )
      *(_DWORD *)(a1 + 60) = SaveDC(v20);
    SelectClipRgn(*(HDC *)(a1 + 32), v24);
    *(_BYTE *)(a1 + 40) = 1;
  }
  else
  {
    v27 = (HDC *)(a1 + 32);
    v28 = GdipGetDC(*(_QWORD *)(a1 + 24), a1 + 32);
    sub_1805E796C(v28, 38871068);
    v29 = hrgn;
    if ( !*(_BYTE *)(a1 + 41) )
      *(_DWORD *)(a1 + 60) = SaveDC(*v27);
    SelectClipRgn(*v27, v29);
    *(_BYTE *)(a2 + 48) = 1;
  }
  if ( v31 )
  {
    GdipDeleteRegion(v31, v25, v26);
    v31 = 0;
  }
  if ( hrgn )
    DeleteObject(hrgn);
  return a1;
}

```

## disassembly

```asm
0x1806efcc4  push    rbp
0x1806efcc6  push    rbx
0x1806efcc7  push    rsi
0x1806efcc8  push    rdi
0x1806efcc9  push    r14
0x1806efccb  mov     rbp, rsp
0x1806efcce  sub     rsp, 20h
0x1806efcd2  mov     bl, r9b
0x1806efcd5  mov     rdi, r8
0x1806efcd8  mov     r14, rdx
0x1806efcdb  mov     rsi, rcx
0x1806efcde  mov     dword ptr [rcx+8], 1
0x1806efce5  lea     rax, off_180A59410
0x1806efcec  mov     [rcx], rax
0x1806efcef  mov     [rcx+10h], rdx
0x1806efcf3  mov     rcx, [rdx+10h]
0x1806efcf7  mov     rax, [rcx]
0x1806efcfa  mov     rax, [rax+270h]
0x1806efd01  call    cs:__guard_dispatch_icall_fptr
0x1806efd07  mov     rdx, rax
0x1806efd0a  mov     rcx, [rax]
0x1806efd0d  mov     rax, [rcx+68h]
0x1806efd11  mov     rcx, rdx
0x1806efd14  call    cs:__guard_dispatch_icall_fptr
0x1806efd1a  mov     rcx, rax
0x1806efd1d  call    sub_1806EDF70
0x1806efd22  mov     [rsi+18h], rax
0x1806efd26  mov     byte ptr [rsi+28h], 0
0x1806efd2a  mov     [rsi+29h], bl
0x1806efd2d  movups  xmm0, xmmword ptr [rdi]
0x1806efd30  movdqu  xmmword ptr [rsi+2Ch], xmm0
0x1806efd35  mov     dword ptr [rsi+3Ch], 0
0x1806efd3c  mov     rax, [rsi+10h]
0x1806efd40  cmp     byte ptr [rax+30h], 0
0x1806efd44  jnz     loc_1806EFF89
0x1806efd4a  mov     [rbp+hrgn], 0
0x1806efd52  mov     [rbp+arg_0], 0
0x1806efd5a  lea     rcx, [rbp+arg_0]
0x1806efd5e  call    cs:GdipCreateRegion
0x1806efd64  mov     ecx, eax
0x1806efd66  mov     edx, 2512019h
0x1806efd6b  call    sub_1805E796C
0x1806efd70  mov     rdx, [rbp+arg_0]
0x1806efd74  mov     rcx, [rsi+18h]
0x1806efd78  call    cs:GdipGetClip
0x1806efd7e  mov     ecx, eax
0x1806efd80  mov     edx, 251201Ah
0x1806efd85  call    sub_1805E796C
0x1806efd8a  nop
0x1806efd8b  cmp     [rbp+hrgn], 0
0x1806efd90  jz      short loc_1806EFDA4
0x1806efd92  call    sub_1800164C0
0x1806efd97  test    al, al
0x1806efd99  jnz     loc_1806EFF71
0x1806efd9f  jmp     loc_1806EFFA1
0x1806efda4  lea     r8, [rbp+hrgn]
0x1806efda8  mov     rdx, [rsi+18h]
0x1806efdac  mov     rcx, [rbp+arg_0]
0x1806efdb0  call    cs:GdipGetRegionHRgn
0x1806efdb6  mov     ecx, eax
0x1806efdb8  mov     edx, 251201Bh
0x1806efdbd  call    sub_1805E796C
0x1806efdc2  mov     rax, [rsi+10h]
0x1806efdc6  mov     rcx, [rax+10h]
0x1806efdca  mov     rax, [rcx]
0x1806efdcd  mov     rax, [rax+1D0h]
0x1806efdd4  call    cs:__guard_dispatch_icall_fptr
0x1806efdda  cmp     al, 3
0x1806efddc  jnz     loc_1806EFEEA
0x1806efde2  mov     rax, [rsi+10h]
0x1806efde6  mov     rbx, [rax+10h]
0x1806efdea  mov     rax, [rbx]
0x1806efded  mov     rcx, rbx
0x1806efdf0  mov     rax, [rax+3A0h]
0x1806efdf7  call    cs:__guard_dispatch_icall_fptr
0x1806efdfd  mov     rcx, rax
0x1806efe00  call    sub_1806EDF70
0x1806efe05  mov     [rsi+18h], rax
0x1806efe09  mov     rax, [rbx]
0x1806efe0c  mov     rcx, rbx
0x1806efe0f  mov     rax, [rax+308h]
0x1806efe16  call    cs:__guard_dispatch_icall_fptr
0x1806efe1c  test    al, al
0x1806efe1e  jz      loc_1806EFEEA
0x1806efe24  mov     rax, [rbx]
0x1806efe27  mov     rcx, rbx
0x1806efe2a  mov     rax, [rax+328h]
0x1806efe31  call    cs:__guard_dispatch_icall_fptr
0x1806efe37  test    al, al
0x1806efe39  jz      loc_1806EFEEA
0x1806efe3f  mov     rcx, [rbx+8]
0x1806efe43  call    sub_1809BE7B4
0x1806efe48  mov     rcx, rbx
0x1806efe4b  call    sub_1806F4298
0x1806efe50  mov     rcx, rax
0x1806efe53  call    sub_1806EDF70
0x1806efe58  mov     [rsi+18h], rax
0x1806efe5c  lea     rdi, [rbx+230h]
0x1806efe63  cmp     qword ptr [rdi], 0
0x1806efe67  jnz     loc_1806EFFB1
0x1806efe6d  mov     rcx, rbx
0x1806efe70  call    sub_1806F3FA4
0x1806efe75  test    al, al
0x1806efe77  jnz     short loc_1806EFE7D
0x1806efe79  xor     ecx, ecx
0x1806efe7b  jmp     short loc_1806EFEB7
0x1806efe7d  mov     rcx, rbx
0x1806efe80  call    sub_1806F4298
0x1806efe85  mov     rcx, rax
0x1806efe88  call    sub_1806EDF70
0x1806efe8d  mov     rdx, rdi
0x1806efe90  mov     rcx, rax
0x1806efe93  call    cs:GdipGetDC
0x1806efe99  mov     ecx, eax
0x1806efe9b  mov     edx, 25118C6h
0x1806efea0  call    sub_1805E796C
0x1806efea5  mov     rcx, [rdi]; hdc
0x1806efea8  call    cs:SaveDC
0x1806efeae  mov     [rbx+238h], eax
0x1806efeb4  mov     rcx, [rdi]; hdc
0x1806efeb7  mov     [rsi+20h], rcx
0x1806efebb  test    rcx, rcx
0x1806efebe  jz      loc_1806EFF62
0x1806efec4  mov     rbx, [rbp+hrgn]
0x1806efec8  cmp     byte ptr [rsi+29h], 0
0x1806efecc  jnz     short loc_1806EFED7
0x1806efece  call    cs:SaveDC
0x1806efed4  mov     [rsi+3Ch], eax
0x1806efed7  mov     rdx, rbx; hrgn
0x1806efeda  mov     rcx, [rsi+20h]; hdc
0x1806efede  call    cs:SelectClipRgn
0x1806efee4  mov     byte ptr [rsi+28h], 1
0x1806efee8  jmp     short loc_1806EFF2E
0x1806efeea  lea     rbx, [rsi+20h]
0x1806efeee  mov     rdx, rbx
0x1806efef1  mov     rcx, [rsi+18h]
0x1806efef5  call    cs:GdipGetDC
0x1806efefb  mov     ecx, eax
0x1806efefd  mov     edx, 251201Ch
0x1806eff02  call    sub_1805E796C
0x1806eff07  mov     rdi, [rbp+hrgn]
0x1806eff0b  cmp     byte ptr [rsi+29h], 0
0x1806eff0f  jnz     short loc_1806EFF1D
0x1806eff11  mov     rcx, [rbx]; hdc
0x1806eff14  call    cs:SaveDC
0x1806eff1a  mov     [rsi+3Ch], eax
0x1806eff1d  mov     rdx, rdi; hrgn
0x1806eff20  mov     rcx, [rbx]; hdc
0x1806eff23  call    cs:SelectClipRgn
0x1806eff29  mov     byte ptr [r14+30h], 1
0x1806eff2e  mov     rcx, [rbp+arg_0]
0x1806eff32  test    rcx, rcx
0x1806eff35  jz      short loc_1806EFF45
0x1806eff37  call    cs:GdipDeleteRegion
0x1806eff3d  mov     [rbp+arg_0], 0
0x1806eff45  mov     rcx, [rbp+hrgn]; ho
0x1806eff49  test    rcx, rcx
0x1806eff4c  jz      short loc_1806EFF54
0x1806eff4e  call    cs:DeleteObject
0x1806eff54  mov     rax, rsi
0x1806eff57  add     rsp, 20h
0x1806eff5b  pop     r14
0x1806eff5d  pop     rdi
0x1806eff5e  pop     rsi
0x1806eff5f  pop     rbx
0x1806eff60  pop     rbp
0x1806eff61  retn
0x1806eff62  mov     ecx, 1706289h
0x1806eff67  call    sub_1805EFBC8
0x1806eff71  mov     [rbp+pExceptionObject], 1E3CF50Bh
0x1806eff78  lea     rdx, __TI1H; pThrowInfo
0x1806eff7f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1806eff83  call    _CxxThrowException
0x1806eff89  mov     ecx, 2A05C8h
0x1806eff8e  call    sub_180075204
0x1806eff93  mov     ecx, 2A05C9h
0x1806eff98  call    sub_1805EF794
0x1806eff9d  nop
0x1806eff9e  jmp     short $+2
0x1806effa0  nop
0x1806effa1  xor     edx, edx
0x1806effa3  mov     ecx, 1E3CF50Bh
0x1806effa8  call    sub_18007412C
0x1806effae  jmp     short $+2
0x1806effb0  nop
0x1806effb1  mov     ecx, 1706288h
0x1806effb6  call    sub_1805E8BC0
0x1806effbb  int     3; Trap to Debugger
```
