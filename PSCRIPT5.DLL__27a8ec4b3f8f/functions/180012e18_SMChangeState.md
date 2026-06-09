# SMChangeState

- ea: `0x180012e18`
- end: `0x180013099`
- name: `SMChangeState`
- size: `641`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `18`
- callee_count: `12`
- tags: ``

## callers

- `0x180004140`
- `0x180004170`
- `0x180004240`
- `0x180004c10`
- `0x180005d44`
- `0x180006a80`
- `0x1800074d0`
- `0x1800079e0`
- `0x180007ad0`
- `0x180007ba0`
- `0x180007ce0`
- `0x180007db0`
- `0x180009eb4`
- `0x18000aa00`
- `0x18000ac50`
- `0x18000af70`
- `0x18000d900`
- `0x180020ef0`

## callees

- `0x18000e910`
- `0x180012e18`
- `0x1800130a0`
- `0x18001502c`
- `0x180015180`
- `0x180015524`
- `0x180015750`
- `0x18001597c`
- `0x180015e8c`
- `0x18001600c`
- `0x1800160b0`
- `0x18001d42c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180012ef8`
- `KERNEL32!SetLastError` at `0x180012ef8`

## pseudocode

```c
_BOOL8 __fastcall SMChangeState(__int64 a1, int a2)
{
  int v4; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  bool v12; // zf
  void *v13; // rax
  _DWORD *v14; // rbx

  v4 = *(_DWORD *)(a1 + 2120);
  if ( v4 == a2 )
    return 1;
  if ( a2 == 6 )
    *(_DWORD *)(a1 + 2168) |= 2u;
  else
    *(_DWORD *)(a1 + 2168) = 0;
  if ( !v4 )
  {
    if ( a2 == 1 )
      goto LABEL_57;
    goto LABEL_19;
  }
  v6 = v4 - 1;
  if ( !v6 )
  {
    if ( a2 == 2 || a2 == 8 )
      goto LABEL_57;
    goto LABEL_19;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    if ( a2 == 1 )
      goto LABEL_57;
    goto LABEL_18;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( a2 != 5 )
    {
      if ( a2 == 6 )
      {
        *(_DWORD *)(a1 + 2152) |= 1u;
        if ( *(_WORD *)(a1 + 166) == 4 )
        {
          *(_WORD *)(a1 + 166) = 0;
          *(_QWORD *)(a1 + 3432) = OPRawPortWrite;
        }
        BInitUFL(a1);
        *(_DWORD *)(a1 + 2236) &= 0xFFFFFFFC;
        goto LABEL_57;
      }
      goto LABEL_36;
    }
    BInitUFL(a1);
    JCDocumentBegin(a1);
LABEL_40:
    JCPageBegin(a1);
    goto LABEL_57;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( a2 != 5 )
    {
      if ( a2 != 7 )
        goto LABEL_19;
      if ( (*(_BYTE *)(a1 + 2152) & 1) == 0 )
        JCDocumentEnd(a1);
LABEL_37:
      JCJobTerm(a1);
      goto LABEL_57;
    }
    if ( (*(_BYTE *)(a1 + 2152) & 1) != 0 )
      goto LABEL_19;
    goto LABEL_40;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( a2 == 4 )
    {
      if ( (*(_BYTE *)(a1 + 2152) & 1) != 0 )
        goto LABEL_57;
      goto LABEL_25;
    }
    if ( a2 == 6 )
    {
      if ( (*(_BYTE *)(a1 + 2152) & 1) != 0 )
      {
        VResetLineAttributes(a1);
        UnDefineAllFonts(a1, 1);
      }
      else
      {
        JCRawPrinterStart(a1);
      }
      goto LABEL_57;
    }
LABEL_36:
    if ( a2 != 7 )
      goto LABEL_19;
    goto LABEL_37;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( a2 == 4 )
    {
      if ( (*(_BYTE *)(a1 + 2152) & 1) != 0 )
        goto LABEL_57;
      JCRawPrinterEnd(a1);
LABEL_25:
      JCPageEnd(a1);
      VResetLineAttributes(a1);
      goto LABEL_57;
    }
    if ( a2 == 5 )
    {
      if ( (*(_BYTE *)(a1 + 2152) & 1) == 0 )
        JCRawPrinterEnd(a1);
      goto LABEL_57;
    }
LABEL_19:
    v14 = (_DWORD *)(a1 + 3440);
    if ( !*v14 )
    {
      *v14 = 1;
      SetLastError(0x32u);
    }
    return *v14 == 0;
  }
  if ( v11 != 1 )
    goto LABEL_19;
  if ( a2 == 1 )
  {
    *(_DWORD *)(a1 + 704) = 0;
    v12 = (*(_WORD *)(a1 + 166) & 0xFFEF) == 0;
    v13 = OPRawPortWrite;
    *(_DWORD *)(a1 + 3440) = 0;
    if ( !v12 )
      v13 = OPBinaryCookedPortWrite;
    *(_QWORD *)(a1 + 3432) = v13;
    goto LABEL_57;
  }
LABEL_18:
  if ( a2 != 3 )
    goto LABEL_19;
  JCJobInit(a1);
LABEL_57:
  *(_DWORD *)(a1 + 2120) = a2;
  v14 = (_DWORD *)(a1 + 3440);
  return *v14 == 0;
}

```

## disassembly

```asm
0x180012e18  mov     [rsp+arg_0], rbx
0x180012e1d  push    rdi
0x180012e1e  sub     rsp, 20h
0x180012e22  mov     rbx, rcx
0x180012e25  mov     edi, edx
0x180012e27  mov     ecx, [rcx+848h]
0x180012e2d  cmp     ecx, edx
0x180012e2f  jnz     short loc_180012E3B
0x180012e31  mov     eax, 1
0x180012e36  jmp     loc_180012F0B
0x180012e3b  cmp     edi, 6
0x180012e3e  jnz     short loc_180012E49
0x180012e40  or      dword ptr [rbx+878h], 2
0x180012e47  jmp     short loc_180012E53
0x180012e49  mov     dword ptr [rbx+878h], 0
0x180012e53  test    ecx, ecx
0x180012e55  jz      loc_18001307E
0x180012e5b  sub     ecx, 1
0x180012e5e  jz      loc_18001306F
0x180012e64  sub     ecx, 1
0x180012e67  jz      loc_18001305B
0x180012e6d  sub     ecx, 1
0x180012e70  jz      loc_180013004
0x180012e76  sub     ecx, 1
0x180012e79  jz      loc_180012FC9
0x180012e7f  sub     ecx, 1
0x180012e82  jz      loc_180012F69
0x180012e88  sub     ecx, 1
0x180012e8b  jz      loc_180012F17
0x180012e91  cmp     ecx, 1
0x180012e94  jnz     short loc_180012EE1
0x180012e96  cmp     edi, ecx
0x180012e98  jnz     short loc_180012ED8
0x180012e9a  mov     eax, 0FFEFh
0x180012e9f  mov     dword ptr [rbx+2C0h], 0
0x180012ea9  test    [rbx+0A6h], ax
0x180012eb0  lea     rcx, OPBinaryCookedPortWrite
0x180012eb7  lea     rax, OPRawPortWrite
0x180012ebe  mov     dword ptr [rbx+0D70h], 0
0x180012ec8  cmovnz  rax, rcx
0x180012ecc  mov     [rbx+0D68h], rax
0x180012ed3  jmp     loc_180013087
0x180012ed8  cmp     edi, 3
0x180012edb  jz      loc_180013065
0x180012ee1  add     rbx, 0D70h
0x180012ee8  cmp     dword ptr [rbx], 0
0x180012eeb  jnz     short loc_180012F04
0x180012eed  mov     ecx, 32h ; '2'; dwErrCode
0x180012ef2  mov     dword ptr [rbx], 1
0x180012ef8  call    cs:__imp_SetLastError
0x180012eff  nop     dword ptr [rax+rax+00h]
0x180012f04  xor     eax, eax
0x180012f06  cmp     [rbx], eax
0x180012f08  setz    al
0x180012f0b  mov     rbx, [rsp+28h+arg_0]
0x180012f10  add     rsp, 20h
0x180012f14  pop     rdi
0x180012f15  retn
0x180012f17  mov     eax, 4
0x180012f1c  cmp     edi, eax
0x180012f1e  jnz     short loc_180012F4A
0x180012f20  test    byte ptr [rbx+868h], 1
0x180012f27  jnz     loc_180013087
0x180012f2d  mov     rcx, rbx
0x180012f30  call    JCRawPrinterEnd
0x180012f35  mov     rcx, rbx
0x180012f38  call    JCPageEnd
0x180012f3d  mov     rcx, rbx
0x180012f40  call    VResetLineAttributes
0x180012f45  jmp     loc_180013087
0x180012f4a  cmp     edi, 5
0x180012f4d  jnz     short loc_180012EE1
0x180012f4f  test    byte ptr [rbx+868h], 1
0x180012f56  jnz     loc_180013087
0x180012f5c  mov     rcx, rbx
0x180012f5f  call    JCRawPrinterEnd
0x180012f64  jmp     loc_180013087
0x180012f69  mov     eax, 4
0x180012f6e  cmp     edi, eax
0x180012f70  jnz     short loc_180012F81
0x180012f72  test    byte ptr [rbx+868h], 1
0x180012f79  jnz     loc_180013087
0x180012f7f  jmp     short loc_180012F35
0x180012f81  cmp     edi, 6
0x180012f84  jnz     short loc_180012FB3
0x180012f86  test    byte ptr [rbx+868h], 1
0x180012f8d  mov     rcx, rbx
0x180012f90  jnz     short loc_180012F9C
0x180012f92  call    JCRawPrinterStart
0x180012f97  jmp     loc_180013087
0x180012f9c  call    VResetLineAttributes
0x180012fa1  mov     edx, 1
0x180012fa6  mov     rcx, rbx
0x180012fa9  call    UnDefineAllFonts
0x180012fae  jmp     loc_180013087
0x180012fb3  cmp     edi, 7
0x180012fb6  jnz     loc_180012EE1
0x180012fbc  mov     rcx, rbx
0x180012fbf  call    JCJobTerm
0x180012fc4  jmp     loc_180013087
0x180012fc9  cmp     edi, 5
0x180012fcc  jnz     short loc_180012FE8
0x180012fce  test    byte ptr [rbx+868h], 1
0x180012fd5  jnz     loc_180012EE1
0x180012fdb  mov     rcx, rbx
0x180012fde  call    JCPageBegin
0x180012fe3  jmp     loc_180013087
0x180012fe8  cmp     edi, 7
0x180012feb  jnz     loc_180012EE1
0x180012ff1  test    byte ptr [rbx+868h], 1
0x180012ff8  jnz     short loc_180012FBC
0x180012ffa  mov     rcx, rbx
0x180012ffd  call    JCDocumentEnd
0x180013002  jmp     short loc_180012FBC
0x180013004  cmp     edi, 5
0x180013007  jnz     short loc_18001301B
0x180013009  mov     rcx, rbx
0x18001300c  call    BInitUFL
0x180013011  mov     rcx, rbx
0x180013014  call    JCDocumentBegin
0x180013019  jmp     short loc_180012FDB
0x18001301b  cmp     edi, 6
0x18001301e  jnz     short loc_180012FB3
0x180013020  or      dword ptr [rbx+868h], 1
0x180013027  lea     eax, [rdi-2]
0x18001302a  cmp     [rbx+0A6h], ax
0x180013031  jnz     short loc_18001304A
0x180013033  xor     eax, eax
0x180013035  mov     [rbx+0A6h], ax
0x18001303c  lea     rax, OPRawPortWrite
0x180013043  mov     [rbx+0D68h], rax
0x18001304a  mov     rcx, rbx
0x18001304d  call    BInitUFL
0x180013052  and     dword ptr [rbx+8BCh], 0FFFFFFFCh
0x180013059  jmp     short loc_180013087
0x18001305b  cmp     edi, 1
0x18001305e  jz      short loc_180013087
0x180013060  jmp     loc_180012ED8
0x180013065  mov     rcx, rbx
0x180013068  call    JCJobInit
0x18001306d  jmp     short loc_180013087
0x18001306f  cmp     edi, 2
0x180013072  jz      short loc_180013087
0x180013074  cmp     edi, 8
0x180013077  jz      short loc_180013087
0x180013079  jmp     loc_180012EE1
0x18001307e  cmp     edi, 1
0x180013081  jnz     loc_180012EE1
0x180013087  mov     [rbx+848h], edi
0x18001308d  add     rbx, 0D70h
0x180013094  jmp     loc_180012F04
```
