# EmfEnumState::SelectObject(void)

- ea: `0x18006b970`
- end: `0x18006baf0`
- name: `?SelectObject@EmfEnumState@@QEAAXXZ`
- size: `384`
- prototype: `void __fastcall(EmfEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18006b1b0`

## callees

- `0x18006a34c`
- `0x18006b80c`
- `0x18006b970`
- `0x18006c064`
- `0x1800fe680`
- `0x180169010`

## import_xrefs

- `GDI32!CreatePenIndirect` at `0x18006ba5e`
- `GDI32!CreatePenIndirect` at `0x18006ba5e`
- `GDI32!CreateBrushIndirect` at `0x18006ba32`
- `GDI32!CreateBrushIndirect` at `0x18006ba32`
- `GDI32!GetStockObject` at `0x18006baa9`
- `GDI32!GetStockObject` at `0x18006baa9`
- `GDI32!SelectObject` at `0x18006ba8b`
- `GDI32!SelectObject` at `0x18006ba8b`

## pseudocode

```c
void __fastcall EmfEnumState::SelectObject(HDC *this)
{
  int v2; // edi
  unsigned int v3; // edi
  const struct RecolorStockObject near *const *v4; // rsi
  __int64 v5; // rbp
  HDC *v6; // r14
  HFONT PenIndirect; // rax
  __int64 v8; // rdx
  COLORREF v9; // eax
  COLORREF v10; // eax
  __int64 v11; // rax
  __int64 v12; // rsi
  HFONT StockObject; // rax
  LOGBRUSH plbrush; // [rsp+20h] [rbp-38h] BYREF

  if ( (*((unsigned int (__fastcall **)(HDC *))*this + 6))(this) >= 0xC )
  {
    v2 = EmfEnumState::GetPartialRecord((EmfEnumState *)this)->dParm[0];
    if ( v2 < 0 )
    {
      v3 = v2 & 0x7FFFFFFF;
      if ( v3 <= 7 && this[18] )
      {
        v4 = &RecolorStockObjectList;
        plbrush = 0;
        v5 = 0;
        while ( 1 )
        {
          if ( *(_DWORD *)v4 == v3 )
          {
            v6 = &this[v5];
            PenIndirect = (HFONT)v6[289];
            if ( PenIndirect )
              goto LABEL_14;
            v8 = *((unsigned int *)v4 + 1);
            if ( *((_DWORD *)v4 + 2) )
            {
              v9 = MfEnumState::ModifyColor(this, v8, 2);
              plbrush.lbStyle = 0;
              plbrush.lbColor = v9;
              plbrush.lbHatch = 0;
              PenIndirect = (HFONT)CreateBrushIndirect(&plbrush);
            }
            else
            {
              v10 = MfEnumState::ModifyColor(this, v8, 3);
              plbrush.lbStyle = 0;
              LODWORD(plbrush.lbHatch) = 0;
              plbrush.lbColor = v10;
              PenIndirect = (HFONT)CreatePenIndirect((const LOGPEN *)&plbrush);
            }
            v6[289] = (HDC)PenIndirect;
            if ( PenIndirect )
              goto LABEL_14;
          }
          v5 = (unsigned int)(v5 + 1);
          v4 = (const struct RecolorStockObject near *const *)((char *)v4 + 12);
          if ( (int)v5 >= 7 )
            goto LABEL_18;
        }
      }
      v11 = v3 - 10;
      if ( (unsigned int)v11 <= 7 )
      {
        v12 = (unsigned int)v11;
        PenIndirect = (HFONT)this[v11 + 9];
        if ( PenIndirect
          || (StockObject = (HFONT)GetStockObject(v3),
              PenIndirect = CreateTrueTypeFont(StockObject),
              (this[v12 + 9] = (HDC)PenIndirect) != 0) )
        {
LABEL_14:
          SelectObject(this[2], PenIndirect);
          return;
        }
      }
    }
LABEL_18:
    (*((void (__fastcall **)(HDC *))*this + 3))(this);
  }
}

```

## disassembly

```asm
0x18006b970  mov     [rsp+arg_8], rbx
0x18006b975  mov     [rsp+arg_10], rbp
0x18006b97a  push    rsi
0x18006b97b  push    rdi
0x18006b97c  push    r14
0x18006b97e  sub     rsp, 40h
0x18006b982  mov     rax, cs:__security_cookie
0x18006b989  xor     rax, rsp
0x18006b98c  mov     [rsp+58h+var_28], rax
0x18006b991  mov     rax, [rcx]
0x18006b994  mov     rbx, rcx
0x18006b997  mov     rax, [rax+30h]
0x18006b99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9a0  cmp     eax, 0Ch
0x18006b9a3  jb      loc_18006BAD0
0x18006b9a9  mov     rcx, rbx; this
0x18006b9ac  call    ?GetPartialRecord@EmfEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; EmfEnumState::GetPartialRecord(void)
0x18006b9b1  mov     edi, [rax+8]
0x18006b9b4  test    edi, edi
0x18006b9b6  jns     loc_18006BAC1
0x18006b9bc  btr     edi, 1Fh
0x18006b9c0  cmp     edi, 7
0x18006b9c3  ja      loc_18006BA93
0x18006b9c9  cmp     qword ptr [rbx+90h], 0
0x18006b9d1  jz      loc_18006BA93
0x18006b9d7  xorps   xmm0, xmm0
0x18006b9da  lea     rsi, ?RecolorStockObjectList@@3QBURecolorStockObject@@B; RecolorStockObject const near * const RecolorStockObjectList
0x18006b9e1  movups  xmmword ptr [rsp+58h+plbrush.lbStyle], xmm0
0x18006b9e6  xor     ebp, ebp
0x18006b9e8  cmp     [rsi], edi
0x18006b9ea  jnz     loc_18006BA73
0x18006b9f0  lea     r14, [rbx+rbp*8]
0x18006b9f4  mov     rax, [r14+908h]
0x18006b9fb  test    rax, rax
0x18006b9fe  jnz     loc_18006BA84
0x18006ba04  mov     rcx, rbx
0x18006ba07  mov     edx, [rsi+4]
0x18006ba0a  cmp     [rsi+8], eax
0x18006ba0d  jz      short loc_18006BA3A
0x18006ba0f  lea     r8d, [rax+2]
0x18006ba13  call    ?ModifyColor@MfEnumState@@IEAAKKW4ColorAdjustType@@@Z; MfEnumState::ModifyColor(ulong,ColorAdjustType)
0x18006ba18  lea     rcx, [rsp+58h+plbrush]; plbrush
0x18006ba1d  mov     [rsp+58h+plbrush.lbStyle], 0
0x18006ba25  mov     [rsp+58h+plbrush.lbColor], eax
0x18006ba29  mov     [rsp+58h+plbrush.lbHatch], 0
0x18006ba32  call    cs:__imp_CreateBrushIndirect
0x18006ba38  jmp     short loc_18006BA64
0x18006ba3a  mov     r8d, 3
0x18006ba40  call    ?ModifyColor@MfEnumState@@IEAAKKW4ColorAdjustType@@@Z; MfEnumState::ModifyColor(ulong,ColorAdjustType)
0x18006ba45  lea     rcx, [rsp+58h+plbrush]; plpen
0x18006ba4a  mov     [rsp+58h+plbrush.lbStyle], 0
0x18006ba52  mov     dword ptr [rsp+58h+plbrush.lbHatch], 0
0x18006ba5a  mov     [rsp+58h+plbrush.lbColor], eax
0x18006ba5e  call    cs:__imp_CreatePenIndirect
0x18006ba64  mov     [r14+908h], rax
0x18006ba6b  mov     rcx, rax
0x18006ba6e  test    rax, rax
0x18006ba71  jnz     short loc_18006BA84
0x18006ba73  inc     ebp
0x18006ba75  add     rsi, 0Ch
0x18006ba79  cmp     ebp, 7
0x18006ba7c  jl      loc_18006B9E8
0x18006ba82  jmp     short loc_18006BAC1
0x18006ba84  mov     rcx, [rbx+10h]; hdc
0x18006ba88  mov     rdx, rax; h
0x18006ba8b  call    cs:__imp_SelectObject
0x18006ba91  jmp     short loc_18006BAD0
0x18006ba93  lea     eax, [rdi-0Ah]
0x18006ba96  cmp     eax, 7
0x18006ba99  ja      short loc_18006BAC1
0x18006ba9b  mov     esi, eax
0x18006ba9d  mov     rax, [rbx+rax*8+48h]
0x18006baa2  test    rax, rax
0x18006baa5  jnz     short loc_18006BA84
0x18006baa7  mov     ecx, edi; i
0x18006baa9  call    cs:__imp_GetStockObject
0x18006baaf  mov     rcx, rax; h
0x18006bab2  call    ?CreateTrueTypeFont@@YAPEAUHFONT__@@PEAU1@@Z; CreateTrueTypeFont(HFONT__ *)
0x18006bab7  mov     [rbx+rsi*8+48h], rax
0x18006babc  test    rax, rax
0x18006babf  jnz     short loc_18006BA84
0x18006bac1  mov     rax, [rbx]
0x18006bac4  mov     rcx, rbx
0x18006bac7  mov     rax, [rax+18h]
0x18006bacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bad0  mov     rcx, [rsp+58h+var_28]
0x18006bad5  xor     rcx, rsp; StackCookie
0x18006bad8  call    __security_check_cookie
0x18006badd  mov     rbx, [rsp+58h+arg_8]
0x18006bae2  mov     rbp, [rsp+58h+arg_10]
0x18006bae7  add     rsp, 40h
0x18006baeb  pop     r14
0x18006baed  pop     rdi
0x18006baee  pop     rsi
0x18006baef  retn
```
