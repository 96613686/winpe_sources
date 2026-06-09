# UniDrvUI::CalculatePrintableArea(UniDrvUI::ProviderDevcapsOperationToken *,int *,int *,int *,int *,int *,int *)

- ea: `0x180117bf8`
- end: `0x180117ff7`
- name: `?CalculatePrintableArea@UniDrvUI@@YAJPEAUProviderDevcapsOperationToken@1@PEAH11111@Z`
- size: `1023`
- prototype: `__int64 __fastcall(HANDLE *this, struct UniDrvUI::ProviderDevcapsOperationToken *, int *, int *, int *, int *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800efb44`
- `0x18011b3f0`

## callees

- `0x18010955c`
- `0x18010a4bc`
- `0x180117bf8`
- `0x18014ed04`
- `0x18014ed44`
- `0x18014fa24`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180117e28`
- `KERNEL32!GetLastError` at `0x180117e28`
- `KERNEL32!LocalFree` at `0x180117ce2`
- `KERNEL32!LocalFree` at `0x180117ce2`
- `GDI32!DeleteDC` at `0x180117e17`
- `GDI32!DeleteDC` at `0x180117e17`
- `GDI32!CreateDCW` at `0x180117cd0`
- `GDI32!CreateDCW` at `0x180117cd0`
- `GDI32!GetDeviceCaps` at `0x180117cff`
- `GDI32!GetDeviceCaps` at `0x180117d16`
- `GDI32!GetDeviceCaps` at `0x180117d2d`
- `GDI32!GetDeviceCaps` at `0x180117d44`
- `GDI32!GetDeviceCaps` at `0x180117d5b`
- `GDI32!GetDeviceCaps` at `0x180117d72`
- `GDI32!GetDeviceCaps` at `0x180117d89`
- `GDI32!GetDeviceCaps` at `0x180117da0`
- `GDI32!GetDeviceCaps` at `0x180117cff`
- `GDI32!GetDeviceCaps` at `0x180117d16`
- `GDI32!GetDeviceCaps` at `0x180117d2d`
- `GDI32!GetDeviceCaps` at `0x180117d44`
- `GDI32!GetDeviceCaps` at `0x180117d5b`
- `GDI32!GetDeviceCaps` at `0x180117d72`
- `GDI32!GetDeviceCaps` at `0x180117d89`
- `GDI32!GetDeviceCaps` at `0x180117da0`

## pseudocode

```c
__int64 __fastcall UniDrvUI::CalculatePrintableArea(
        HANDLE *this,
        struct UniDrvUI::ProviderDevcapsOperationToken *a2,
        int *a3,
        int *a4,
        int *a5,
        int *a6,
        int *a7)
{
  int v8; // r14d
  int v9; // esi
  int v10; // r13d
  int v11; // r12d
  int top; // r15d
  _QWORD *v13; // rbx
  __int64 v14; // rax
  BYTE *Printer; // rax
  BYTE *v16; // rbx
  HDC DCW; // rdi
  int v18; // eax
  signed int v19; // ebx
  signed int LastError; // eax
  __int64 v21; // rcx
  HANDLE v22; // r8
  struct _devicemodeW *inited; // rax
  struct _OPTSELECT *v25; // r8
  HANDLE v26; // rcx
  unsigned __int8 *v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // r8
  LONG right; // ebx
  _WORD *v31; // rbx
  int v32; // eax
  int v33; // esi
  int v34; // r12d
  tagSIZE v35; // [rsp+58h] [rbp-41h] BYREF
  struct _RECTL v36; // [rsp+60h] [rbp-39h] BYREF
  __int128 v37; // [rsp+70h] [rbp-29h] BYREF
  struct _devicemodeW *v38; // [rsp+80h] [rbp-19h]
  int DeviceCaps; // [rsp+88h] [rbp-11h]
  int v40; // [rsp+8Ch] [rbp-Dh]
  int v41; // [rsp+90h] [rbp-9h]
  int left; // [rsp+E8h] [rbp+4Fh]

  if ( !this || !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
    return 2147500035LL;
  *(_DWORD *)a2 = 0;
  v8 = 0;
  *a3 = 0;
  v9 = 0;
  *a4 = 0;
  v10 = 0;
  *a5 = 0;
  v11 = 0;
  *a6 = 0;
  top = 0;
  *a7 = 0;
  v13 = *this;
  left = 0;
  v14 = *((_QWORD *)*this + 6);
  if ( (*(_DWORD *)(v14 + 24) & 0x100000) == 0 )
  {
    Printer = MyGetPrinter(this[11], 4u);
    v16 = Printer;
    if ( !Printer || (DCW = CreateDCW(0, *(LPCWSTR *)Printer, 0, (const DEVMODEW *)this[4]), LocalFree(v16), !DCW) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        return (unsigned int)-2147467259;
      return (unsigned int)LastError;
    }
    DeviceCaps = GetDeviceCaps(DCW, 112);
    v40 = GetDeviceCaps(DCW, 8);
    v41 = GetDeviceCaps(DCW, 113);
    LODWORD(v38) = GetDeviceCaps(DCW, 10);
    v36.left = GetDeviceCaps(DCW, 110);
    v36.right = GetDeviceCaps(DCW, 111);
    v35.cx = GetDeviceCaps(DCW, 88);
    v18 = GetDeviceCaps(DCW, 90);
    if ( v35.cx && v18 )
    {
      v19 = 0;
      v8 = 25400 * DeviceCaps / v35.cx;
      v9 = 25400 * v40 / v35.cx;
      v10 = 25400 * v41 / v18;
      v11 = 25400 * (int)v38 / v18;
      left = 25400 * v36.left / v35.cx;
      top = 25400 * v36.right / v18;
    }
    else
    {
      v19 = -2147467259;
    }
    DeleteDC(DCW);
LABEL_39:
    if ( v19 >= 0 )
    {
      *(_DWORD *)a2 = v8;
      *a3 = v10;
      *a4 = v9;
      *a5 = v11;
      *a6 = left;
      *a7 = top;
    }
    return (unsigned int)v19;
  }
  if ( v13 )
  {
    if ( v14 )
    {
      v21 = *(_QWORD *)(v14 + 40);
      if ( v21 )
      {
        v22 = this[1];
        if ( v22 )
        {
          if ( this[4] )
          {
            inited = (struct _devicemodeW *)InitBinaryData(v21, (__int64)a7, v22);
            v38 = inited;
            if ( !inited )
              return 2147500037LL;
            v25 = (struct _OPTSELECT *)this[4];
            v26 = this[11];
            v27 = (unsigned __int8 *)this[1];
            v37 = 0;
            *(_QWORD *)&v36.left = 0;
            v35.cx = 0;
            v36.right = UniDrvUI::BUniGetXpsDrvPaperFormat(
                          v26,
                          v27,
                          v25,
                          inited,
                          (struct _INFOHEADER *)&v37,
                          &v36,
                          &v35,
                          (enum _XPSDRVLANDSCAPE *)(v13 + 15),
                          (struct _FORM_INFO_2W **)v13 + 16);
            right = v36.right;
            if ( !v36.right )
              goto LABEL_38;
            v31 = this[4];
            v32 = UniDrvUI::UniRotateXpsDrvImageableArea(
                    (__int64)this[1],
                    (__int64)v31,
                    (__int64)v38,
                    (int *)&v37,
                    *(__int64 *)&v36.left,
                    v35.cx);
            top = v36.top;
            if ( v31[38] == 2 )
            {
              if ( v32 == 1 )
              {
                v10 = v37;
                v8 = v36.top - HIDWORD(v37);
                v33 = v36.top - DWORD1(v37);
                v34 = DWORD2(v37);
              }
              else
              {
                v34 = HIDWORD(v37);
                v33 = DWORD2(v37);
                v10 = DWORD1(v37);
                v8 = v37;
              }
              if ( v35.cx != 1 )
              {
                left = v36.top;
                top = v36.left;
LABEL_37:
                right = v36.right;
                v9 = v33 - v8;
                v11 = v34 - v10;
LABEL_38:
                FreeBinaryData((__int64)v38, v28, v29);
                v19 = right != 0 ? 0 : 0x80004005;
                goto LABEL_39;
              }
            }
            else
            {
              v34 = HIDWORD(v37);
              v33 = DWORD2(v37);
              v10 = DWORD1(v37);
              v8 = v37;
            }
            left = v36.left;
            goto LABEL_37;
          }
        }
      }
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180117bf8  mov     rax, rsp
0x180117bfb  mov     [rax+20h], r9
0x180117bff  mov     [rax+18h], r8
0x180117c03  mov     [rax+10h], rdx
0x180117c07  push    rbp
0x180117c08  push    rbx
0x180117c09  push    rsi
0x180117c0a  push    rdi
0x180117c0b  push    r12
0x180117c0d  push    r13
0x180117c0f  push    r14
0x180117c11  push    r15
0x180117c13  lea     rbp, [rax-47h]
0x180117c17  sub     rsp, 98h
0x180117c1e  xor     r11d, r11d
0x180117c21  mov     r10, rdx
0x180117c24  mov     rdi, rcx
0x180117c27  test    rcx, rcx
0x180117c2a  jz      loc_180117FDD
0x180117c30  test    rdx, rdx
0x180117c33  jz      loc_180117FDD
0x180117c39  test    r8, r8
0x180117c3c  jz      loc_180117FDD
0x180117c42  test    r9, r9
0x180117c45  jz      loc_180117FDD
0x180117c4b  mov     rax, [rbp+3Fh+arg_20]
0x180117c4f  test    rax, rax
0x180117c52  jz      loc_180117FDD
0x180117c58  mov     rcx, [rbp+3Fh+arg_28]
0x180117c5c  test    rcx, rcx
0x180117c5f  jz      loc_180117FDD
0x180117c65  mov     rdx, [rbp+3Fh+arg_30]
0x180117c69  test    rdx, rdx
0x180117c6c  jz      loc_180117FDD
0x180117c72  mov     [r10], r11d
0x180117c75  mov     r14d, r11d
0x180117c78  mov     [r8], r11d
0x180117c7b  mov     esi, r11d
0x180117c7e  mov     [r9], r11d
0x180117c81  mov     r13d, r11d
0x180117c84  mov     [rax], r11d
0x180117c87  mov     r12d, r11d
0x180117c8a  mov     [rcx], r11d
0x180117c8d  mov     r15d, r11d
0x180117c90  mov     [rdx], r11d
0x180117c93  mov     rbx, [rdi]
0x180117c96  mov     [rbp+3Fh+arg_0], r11d
0x180117c9a  mov     rax, [rbx+30h]
0x180117c9e  test    dword ptr [rax+18h], 100000h
0x180117ca5  jnz     loc_180117E51
0x180117cab  mov     rcx, [rdi+58h]; hPrinter
0x180117caf  lea     edx, [r11+4]; Level
0x180117cb3  call    MyGetPrinter
0x180117cb8  mov     rbx, rax
0x180117cbb  test    rax, rax
0x180117cbe  jz      loc_180117E28
0x180117cc4  mov     r9, [rdi+20h]; pdm
0x180117cc8  xor     r8d, r8d; pszPort
0x180117ccb  mov     rdx, [rax]; pwszDevice
0x180117cce  xor     ecx, ecx; pwszDriver
0x180117cd0  call    cs:__imp_CreateDCW
0x180117cd7  nop     dword ptr [rax+rax+00h]
0x180117cdc  mov     rcx, rbx; hMem
0x180117cdf  mov     rdi, rax
0x180117ce2  call    cs:__imp_LocalFree
0x180117ce9  nop     dword ptr [rax+rax+00h]
0x180117cee  test    rdi, rdi
0x180117cf1  jz      loc_180117E28
0x180117cf7  mov     edx, 70h ; 'p'; index
0x180117cfc  mov     rcx, rdi; hdc
0x180117cff  call    cs:__imp_GetDeviceCaps
0x180117d06  nop     dword ptr [rax+rax+00h]
0x180117d0b  mov     edx, 8; index
0x180117d10  mov     rcx, rdi; hdc
0x180117d13  mov     [rbp+3Fh+var_50], eax
0x180117d16  call    cs:__imp_GetDeviceCaps
0x180117d1d  nop     dword ptr [rax+rax+00h]
0x180117d22  mov     edx, 71h ; 'q'; index
0x180117d27  mov     rcx, rdi; hdc
0x180117d2a  mov     [rbp+3Fh+var_4C], eax
0x180117d2d  call    cs:__imp_GetDeviceCaps
0x180117d34  nop     dword ptr [rax+rax+00h]
0x180117d39  mov     edx, 0Ah; index
0x180117d3e  mov     rcx, rdi; hdc
0x180117d41  mov     [rbp+3Fh+var_48], eax
0x180117d44  call    cs:__imp_GetDeviceCaps
0x180117d4b  nop     dword ptr [rax+rax+00h]
0x180117d50  mov     edx, 6Eh ; 'n'; index
0x180117d55  mov     rcx, rdi; hdc
0x180117d58  mov     dword ptr [rbp+3Fh+var_58], eax
0x180117d5b  call    cs:__imp_GetDeviceCaps
0x180117d62  nop     dword ptr [rax+rax+00h]
0x180117d67  mov     edx, 6Fh ; 'o'; index
0x180117d6c  mov     rcx, rdi; hdc
0x180117d6f  mov     [rbp+3Fh+var_78.left], eax
0x180117d72  call    cs:__imp_GetDeviceCaps
0x180117d79  nop     dword ptr [rax+rax+00h]
0x180117d7e  mov     edx, 58h ; 'X'; index
0x180117d83  mov     rcx, rdi; hdc
0x180117d86  mov     [rbp+3Fh+var_78.right], eax
0x180117d89  call    cs:__imp_GetDeviceCaps
0x180117d90  nop     dword ptr [rax+rax+00h]
0x180117d95  mov     edx, 5Ah ; 'Z'; index
0x180117d9a  mov     rcx, rdi; hdc
0x180117d9d  mov     [rbp+3Fh+var_80.cx], eax
0x180117da0  call    cs:__imp_GetDeviceCaps
0x180117da7  nop     dword ptr [rax+rax+00h]
0x180117dac  mov     r8d, [rbp+3Fh+var_80.cx]
0x180117db0  mov     ecx, eax
0x180117db2  test    r8d, r8d
0x180117db5  jz      short loc_180117E0F
0x180117db7  test    eax, eax
0x180117db9  jz      short loc_180117E0F
0x180117dbb  imul    eax, [rbp+3Fh+var_50], 6338h
0x180117dc2  xor     ebx, ebx
0x180117dc4  cdq
0x180117dc5  idiv    r8d
0x180117dc8  mov     r14d, eax
0x180117dcb  imul    eax, [rbp+3Fh+var_4C], 6338h
0x180117dd2  cdq
0x180117dd3  idiv    r8d
0x180117dd6  mov     esi, eax
0x180117dd8  imul    eax, [rbp+3Fh+var_48], 6338h
0x180117ddf  cdq
0x180117de0  idiv    ecx
0x180117de2  mov     r13d, eax
0x180117de5  imul    eax, dword ptr [rbp+3Fh+var_58], 6338h
0x180117dec  cdq
0x180117ded  idiv    ecx
0x180117def  mov     r12d, eax
0x180117df2  imul    eax, [rbp+3Fh+var_78.left], 6338h
0x180117df9  cdq
0x180117dfa  idiv    r8d
0x180117dfd  mov     [rbp+3Fh+arg_0], eax
0x180117e00  imul    eax, [rbp+3Fh+var_78.right], 6338h
0x180117e07  cdq
0x180117e08  idiv    ecx
0x180117e0a  mov     r15d, eax
0x180117e0d  jmp     short loc_180117E14
0x180117e0f  mov     ebx, 80004005h
0x180117e14  mov     rcx, rdi; hdc
0x180117e17  call    cs:__imp_DeleteDC
0x180117e1e  nop     dword ptr [rax+rax+00h]
0x180117e23  jmp     loc_180117FA3
0x180117e28  call    cs:__imp_GetLastError
0x180117e2f  nop     dword ptr [rax+rax+00h]
0x180117e34  test    eax, eax
0x180117e36  jle     short loc_180117E40
0x180117e38  movzx   eax, ax
0x180117e3b  or      eax, 80070000h
0x180117e40  mov     ebx, 80004005h
0x180117e45  test    eax, eax
0x180117e47  cmovns  eax, ebx
0x180117e4a  mov     ebx, eax
0x180117e4c  jmp     loc_180117FD2
0x180117e51  test    rbx, rbx
0x180117e54  jz      loc_180117FD6
0x180117e5a  test    rax, rax
0x180117e5d  jz      loc_180117FD6
0x180117e63  mov     rcx, [rax+28h]
0x180117e67  test    rcx, rcx
0x180117e6a  jz      loc_180117FD6
0x180117e70  mov     r8, [rdi+8]
0x180117e74  test    r8, r8
0x180117e77  jz      loc_180117FD6
0x180117e7d  cmp     [rdi+20h], r11
0x180117e81  jz      loc_180117FD6
0x180117e87  call    InitBinaryData
0x180117e8c  mov     [rbp+3Fh+var_58], rax
0x180117e90  mov     rdx, rax
0x180117e93  test    rax, rax
0x180117e96  jnz     short loc_180117EA2
0x180117e98  mov     eax, 80004005h
0x180117e9d  jmp     loc_180117FE2
0x180117ea2  mov     r8, [rdi+20h]; struct _OPTSELECT *
0x180117ea6  lea     rax, [rbx+80h]
0x180117ead  mov     [rsp+40h], rax; struct _FORM_INFO_2W **
0x180117eb2  lea     rcx, [rbx+78h]
0x180117eb6  mov     [rsp+0D0h+var_98], rcx; enum _XPSDRVLANDSCAPE *
0x180117ebb  lea     rax, [rbp+3Fh+var_80]
0x180117ebf  mov     rcx, [rdi+58h]; hPrinter
0x180117ec3  xorps   xmm0, xmm0
0x180117ec6  mov     [rsp+0D0h+var_A0], rax; struct tagSIZE *
0x180117ecb  mov     r9, rdx; struct _devicemodeW *
0x180117ece  mov     rdx, [rdi+8]; void *
0x180117ed2  lea     rax, [rbp+3Fh+var_78]
0x180117ed6  mov     [rsp+0D0h+var_A8], rax; struct _RECTL *
0x180117edb  lea     rax, [rbp+3Fh+var_68]
0x180117edf  mov     [rsp+0D0h+var_B0], rax; struct _INFOHEADER *
0x180117ee4  movups  [rbp+3Fh+var_68], xmm0
0x180117ee8  mov     qword ptr [rbp+3Fh+var_78.left], rsi
0x180117eec  mov     [rbp+3Fh+var_80.cx], esi
0x180117eef  call    ?BUniGetXpsDrvPaperFormat@UniDrvUI@@YAHPEAXPEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_INFOHEADER@@PEAU_RECTL@@PEAUtagSIZE@@PEAW4_XPSDRVLANDSCAPE@@PEAPEAU_FORM_INFO_2W@@PEAK@Z; UniDrvUI::BUniGetXpsDrvPaperFormat(void *,_OPTSELECT *,_devicemodeW *,_INFOHEADER *,_RECTL *,tagSIZE *,_XPSDRVLANDSCAPE *,_FORM_INFO_2W * *,ulong *)
0x180117ef4  mov     [rbp+3Fh+var_78.right], eax
0x180117ef7  mov     ebx, eax
0x180117ef9  test    eax, eax
0x180117efb  jz      loc_180117F8D
0x180117f01  mov     ecx, [rbp+3Fh+var_80.cx]
0x180117f04  lea     r9, [rbp+3Fh+var_68]
0x180117f08  mov     rbx, [rdi+20h]
0x180117f0c  mov     r8, [rbp+3Fh+var_58]
0x180117f10  mov     rdx, rbx
0x180117f13  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x180117f17  mov     rcx, qword ptr [rbp+3Fh+var_78.left]
0x180117f1b  mov     [rsp+0D0h+var_B0], rcx
0x180117f20  mov     rcx, [rdi+8]
0x180117f24  call    ?UniRotateXpsDrvImageableArea@UniDrvUI@@YA?AW4Enum@ImageableAreaRotationMode@1@PEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_INFOHEADER@@PEAU_RECTL@@UtagSIZE@@W4_XPSDRVLANDSCAPE@@@Z; UniDrvUI::UniRotateXpsDrvImageableArea(_OPTSELECT *,_devicemodeW *,_INFOHEADER *,_RECTL *,tagSIZE,_XPSDRVLANDSCAPE)
0x180117f29  cmp     word ptr [rbx+4Ch], 2
0x180117f2e  mov     r15d, [rbp+3Fh+var_78.top]
0x180117f32  jnz     short loc_180117F6F
0x180117f34  cmp     eax, 1
0x180117f37  jnz     short loc_180117F50
0x180117f39  mov     r13d, dword ptr [rbp+3Fh+var_68]
0x180117f3d  mov     r14d, r15d
0x180117f40  sub     r14d, dword ptr [rbp+3Fh+var_68+0Ch]
0x180117f44  mov     esi, r15d
0x180117f47  sub     esi, dword ptr [rbp+3Fh+var_68+4]
0x180117f4a  mov     r12d, dword ptr [rbp+3Fh+var_68+8]
0x180117f4e  jmp     short loc_180117F5F
0x180117f50  mov     r12d, dword ptr [rbp+3Fh+var_68+0Ch]
0x180117f54  mov     esi, dword ptr [rbp+3Fh+var_68+8]
0x180117f57  mov     r13d, dword ptr [rbp+3Fh+var_68+4]
0x180117f5b  mov     r14d, dword ptr [rbp+3Fh+var_68]
0x180117f5f  cmp     [rbp+3Fh+var_80.cx], 1
0x180117f63  jz      short loc_180117F7E
0x180117f65  mov     [rbp+3Fh+arg_0], r15d
0x180117f69  mov     r15d, [rbp+3Fh+var_78.left]
0x180117f6d  jmp     short loc_180117F84
0x180117f6f  mov     r12d, dword ptr [rbp+3Fh+var_68+0Ch]
0x180117f73  mov     esi, dword ptr [rbp+3Fh+var_68+8]
0x180117f76  mov     r13d, dword ptr [rbp+3Fh+var_68+4]
0x180117f7a  mov     r14d, dword ptr [rbp+3Fh+var_68]
0x180117f7e  mov     eax, [rbp+3Fh+var_78.left]
0x180117f81  mov     [rbp+3Fh+arg_0], eax
0x180117f84  mov     ebx, [rbp+3Fh+var_78.right]
0x180117f87  sub     esi, r14d
0x180117f8a  sub     r12d, r13d
0x180117f8d  mov     rcx, [rbp+3Fh+var_58]
0x180117f91  call    FreeBinaryData
0x180117f96  neg     ebx
0x180117f98  mov     ebx, 80004005h
0x180117f9d  sbb     ecx, ecx
0x180117f9f  not     ecx
0x180117fa1  and     ebx, ecx
0x180117fa3  test    ebx, ebx
0x180117fa5  js      short loc_180117FD2
0x180117fa7  mov     rax, [rbp+3Fh+arg_8]
0x180117fab  mov     rcx, [rbp+3Fh+arg_28]
0x180117faf  mov     [rax], r14d
0x180117fb2  mov     rax, [rbp+3Fh+arg_10]
0x180117fb6  mov     [rax], r13d
0x180117fb9  mov     rax, [rbp+3Fh+arg_18]
0x180117fbd  mov     [rax], esi
0x180117fbf  mov     rax, [rbp+3Fh+arg_20]
0x180117fc3  mov     [rax], r12d
0x180117fc6  mov     eax, [rbp+3Fh+arg_0]
0x180117fc9  mov     [rcx], eax
0x180117fcb  mov     rax, [rbp+3Fh+arg_30]
0x180117fcf  mov     [rax], r15d
0x180117fd2  mov     eax, ebx
0x180117fd4  jmp     short loc_180117FE2
0x180117fd6  mov     eax, 8000FFFFh
0x180117fdb  jmp     short loc_180117FE2
0x180117fdd  mov     eax, 80004003h
0x180117fe2  add     rsp, 98h
0x180117fe9  pop     r15
0x180117feb  pop     r14
0x180117fed  pop     r13
0x180117fef  pop     r12
0x180117ff1  pop     rdi
0x180117ff2  pop     rsi
0x180117ff3  pop     rbx
0x180117ff4  pop     rbp
0x180117ff5  retn
```
