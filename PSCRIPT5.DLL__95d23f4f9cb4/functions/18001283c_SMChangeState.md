# SMChangeState

- ea: `0x18001283c`
- end: `0x180012ab2`
- name: `SMChangeState`
- size: `630`
- prototype: ``
- caller_count: `18`
- callee_count: `12`
- tags: ``

## callers

- `0x1800040b0`
- `0x1800040e0`
- `0x1800041a0`
- `0x180004bc0`
- `0x180005c48`
- `0x180006950`
- `0x180007378`
- `0x1800077d0`
- `0x1800078c0`
- `0x180007980`
- `0x180007ab0`
- `0x180007b70`
- `0x180009b84`
- `0x18000a660`
- `0x18000a8a0`
- `0x18000abb0`
- `0x18000d4f0`
- `0x1800202b0`

## callees

- `0x18000e4ac`
- `0x18001283c`
- `0x180012ab8`
- `0x180014988`
- `0x180014ad8`
- `0x180014e7c`
- `0x180015074`
- `0x180015264`
- `0x180015774`
- `0x1800158f4`
- `0x180015994`
- `0x18001ca00`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180012918`
- `KERNEL32!SetLastError` at `0x180012918`

## pseudocode

```c
__int64 __fastcall SMChangeState(__int64 a1, int a2)
{
  int v4; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  bool v12; // zf
  __int64 (__fastcall *v13)(__int64, char *, unsigned int); // rax
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
      v13 = (__int64 (__fastcall *)(__int64, char *, unsigned int))OPBinaryCookedPortWrite;
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
0x18001283c  mov     [rsp+arg_0], rbx
0x180012841  push    rdi
0x180012842  sub     rsp, 20h
0x180012846  mov     rbx, rcx
0x180012849  mov     edi, edx
0x18001284b  mov     ecx, [rcx+848h]
0x180012851  cmp     ecx, edx
0x180012853  jnz     short loc_18001285F
0x180012855  mov     eax, 1
0x18001285a  jmp     loc_180012925
0x18001285f  cmp     edi, 6
0x180012862  jnz     short loc_18001286D
0x180012864  or      dword ptr [rbx+878h], 2
0x18001286b  jmp     short loc_180012877
0x18001286d  mov     dword ptr [rbx+878h], 0
0x180012877  test    ecx, ecx
0x180012879  jz      loc_180012A97
0x18001287f  sub     ecx, 1
0x180012882  jz      loc_180012A88
0x180012888  sub     ecx, 1
0x18001288b  jz      loc_180012A74
0x180012891  sub     ecx, 1
0x180012894  jz      loc_180012A1D
0x18001289a  sub     ecx, 1
0x18001289d  jz      loc_1800129E2
0x1800128a3  sub     ecx, 1
0x1800128a6  jz      loc_180012982
0x1800128ac  sub     ecx, 1
0x1800128af  jz      short loc_180012930
0x1800128b1  cmp     ecx, 1
0x1800128b4  jnz     short loc_180012901
0x1800128b6  cmp     edi, ecx
0x1800128b8  jnz     short loc_1800128F8
0x1800128ba  mov     eax, 0FFEFh
0x1800128bf  mov     dword ptr [rbx+2C0h], 0
0x1800128c9  test    [rbx+0A6h], ax
0x1800128d0  lea     rcx, OPBinaryCookedPortWrite
0x1800128d7  lea     rax, OPRawPortWrite
0x1800128de  mov     dword ptr [rbx+0D70h], 0
0x1800128e8  cmovnz  rax, rcx
0x1800128ec  mov     [rbx+0D68h], rax
0x1800128f3  jmp     loc_180012AA0
0x1800128f8  cmp     edi, 3
0x1800128fb  jz      loc_180012A7E
0x180012901  add     rbx, 0D70h
0x180012908  cmp     dword ptr [rbx], 0
0x18001290b  jnz     short loc_18001291E
0x18001290d  mov     ecx, 32h ; '2'; dwErrCode
0x180012912  mov     dword ptr [rbx], 1
0x180012918  call    cs:__imp_SetLastError
0x18001291e  xor     eax, eax
0x180012920  cmp     [rbx], eax
0x180012922  setz    al
0x180012925  mov     rbx, [rsp+28h+arg_0]
0x18001292a  add     rsp, 20h
0x18001292e  pop     rdi
0x18001292f  retn
0x180012930  mov     eax, 4
0x180012935  cmp     edi, eax
0x180012937  jnz     short loc_180012963
0x180012939  test    byte ptr [rbx+868h], 1
0x180012940  jnz     loc_180012AA0
0x180012946  mov     rcx, rbx
0x180012949  call    JCRawPrinterEnd
0x18001294e  mov     rcx, rbx
0x180012951  call    JCPageEnd
0x180012956  mov     rcx, rbx
0x180012959  call    VResetLineAttributes
0x18001295e  jmp     loc_180012AA0
0x180012963  cmp     edi, 5
0x180012966  jnz     short loc_180012901
0x180012968  test    byte ptr [rbx+868h], 1
0x18001296f  jnz     loc_180012AA0
0x180012975  mov     rcx, rbx
0x180012978  call    JCRawPrinterEnd
0x18001297d  jmp     loc_180012AA0
0x180012982  mov     eax, 4
0x180012987  cmp     edi, eax
0x180012989  jnz     short loc_18001299A
0x18001298b  test    byte ptr [rbx+868h], 1
0x180012992  jnz     loc_180012AA0
0x180012998  jmp     short loc_18001294E
0x18001299a  cmp     edi, 6
0x18001299d  jnz     short loc_1800129CC
0x18001299f  test    byte ptr [rbx+868h], 1
0x1800129a6  mov     rcx, rbx
0x1800129a9  jnz     short loc_1800129B5
0x1800129ab  call    JCRawPrinterStart
0x1800129b0  jmp     loc_180012AA0
0x1800129b5  call    VResetLineAttributes
0x1800129ba  mov     edx, 1
0x1800129bf  mov     rcx, rbx
0x1800129c2  call    UnDefineAllFonts
0x1800129c7  jmp     loc_180012AA0
0x1800129cc  cmp     edi, 7
0x1800129cf  jnz     loc_180012901
0x1800129d5  mov     rcx, rbx
0x1800129d8  call    JCJobTerm
0x1800129dd  jmp     loc_180012AA0
0x1800129e2  cmp     edi, 5
0x1800129e5  jnz     short loc_180012A01
0x1800129e7  test    byte ptr [rbx+868h], 1
0x1800129ee  jnz     loc_180012901
0x1800129f4  mov     rcx, rbx
0x1800129f7  call    JCPageBegin
0x1800129fc  jmp     loc_180012AA0
0x180012a01  cmp     edi, 7
0x180012a04  jnz     loc_180012901
0x180012a0a  test    byte ptr [rbx+868h], 1
0x180012a11  jnz     short loc_1800129D5
0x180012a13  mov     rcx, rbx
0x180012a16  call    JCDocumentEnd
0x180012a1b  jmp     short loc_1800129D5
0x180012a1d  cmp     edi, 5
0x180012a20  jnz     short loc_180012A34
0x180012a22  mov     rcx, rbx
0x180012a25  call    BInitUFL
0x180012a2a  mov     rcx, rbx
0x180012a2d  call    JCDocumentBegin
0x180012a32  jmp     short loc_1800129F4
0x180012a34  cmp     edi, 6
0x180012a37  jnz     short loc_1800129CC
0x180012a39  or      dword ptr [rbx+868h], 1
0x180012a40  lea     eax, [rdi-2]
0x180012a43  cmp     [rbx+0A6h], ax
0x180012a4a  jnz     short loc_180012A63
0x180012a4c  xor     eax, eax
0x180012a4e  mov     [rbx+0A6h], ax
0x180012a55  lea     rax, OPRawPortWrite
0x180012a5c  mov     [rbx+0D68h], rax
0x180012a63  mov     rcx, rbx
0x180012a66  call    BInitUFL
0x180012a6b  and     dword ptr [rbx+8BCh], 0FFFFFFFCh
0x180012a72  jmp     short loc_180012AA0
0x180012a74  cmp     edi, 1
0x180012a77  jz      short loc_180012AA0
0x180012a79  jmp     loc_1800128F8
0x180012a7e  mov     rcx, rbx
0x180012a81  call    JCJobInit
0x180012a86  jmp     short loc_180012AA0
0x180012a88  cmp     edi, 2
0x180012a8b  jz      short loc_180012AA0
0x180012a8d  cmp     edi, 8
0x180012a90  jz      short loc_180012AA0
0x180012a92  jmp     loc_180012901
0x180012a97  cmp     edi, 1
0x180012a9a  jnz     loc_180012901
0x180012aa0  mov     [rbx+848h], edi
0x180012aa6  add     rbx, 0D70h
0x180012aad  jmp     loc_18001291E
```
