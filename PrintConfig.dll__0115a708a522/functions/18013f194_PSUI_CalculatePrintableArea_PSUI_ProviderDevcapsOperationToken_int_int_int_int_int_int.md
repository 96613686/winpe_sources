# PSUI::CalculatePrintableArea(PSUI::ProviderDevcapsOperationToken *,int *,int *,int *,int *,int *,int *)

- ea: `0x18013f194`
- end: `0x18013f5c9`
- name: `?CalculatePrintableArea@PSUI@@YAJPEAUProviderDevcapsOperationToken@1@PEAH11111@Z`
- size: `1077`
- prototype: `__int64 __fastcall(PSUI *this, struct PSUI::ProviderDevcapsOperationToken *, int *, int *, int *, int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18012bcf0`
- `0x180142360`

## callees

- `0x18013203c`
- `0x18013307c`
- `0x18013321c`
- `0x18013f194`
- `0x18014ed04`
- `0x18014ed44`
- `0x18014fa24`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013f3be`
- `KERNEL32!GetLastError` at `0x18013f3be`
- `KERNEL32!LocalFree` at `0x18013f280`
- `KERNEL32!LocalFree` at `0x18013f280`
- `GDI32!DeleteDC` at `0x18013f3ad`
- `GDI32!DeleteDC` at `0x18013f3ad`
- `GDI32!CreateDCW` at `0x18013f26e`
- `GDI32!CreateDCW` at `0x18013f26e`
- `GDI32!GetDeviceCaps` at `0x18013f29d`
- `GDI32!GetDeviceCaps` at `0x18013f2b4`
- `GDI32!GetDeviceCaps` at `0x18013f2cb`
- `GDI32!GetDeviceCaps` at `0x18013f2e2`
- `GDI32!GetDeviceCaps` at `0x18013f2f9`
- `GDI32!GetDeviceCaps` at `0x18013f310`
- `GDI32!GetDeviceCaps` at `0x18013f327`
- `GDI32!GetDeviceCaps` at `0x18013f33d`
- `GDI32!GetDeviceCaps` at `0x18013f29d`
- `GDI32!GetDeviceCaps` at `0x18013f2b4`
- `GDI32!GetDeviceCaps` at `0x18013f2cb`
- `GDI32!GetDeviceCaps` at `0x18013f2e2`
- `GDI32!GetDeviceCaps` at `0x18013f2f9`
- `GDI32!GetDeviceCaps` at `0x18013f310`
- `GDI32!GetDeviceCaps` at `0x18013f327`
- `GDI32!GetDeviceCaps` at `0x18013f33d`

## pseudocode

```c
__int64 __fastcall PSUI::CalculatePrintableArea(
        PSUI *this,
        struct PSUI::ProviderDevcapsOperationToken *a2,
        int *a3,
        int *a4,
        int *a5,
        int *a6,
        int *a7)
{
  int v8; // r14d
  int v9; // r15d
  HANDLE v10; // rsi
  __int64 v11; // rax
  BYTE *Printer; // rax
  BYTE *v13; // rdi
  HDC DCW; // rsi
  int v15; // edi
  int v16; // eax
  signed int v17; // ebx
  signed int LastError; // eax
  __int64 v19; // rcx
  void *v20; // r8
  struct _PSDRVEXTRA *inited; // rdi
  __int64 v23; // r8
  PSUI *v24; // rcx
  unsigned __int8 *v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // esi
  LONG right; // r14d
  __int64 v30; // rsi
  int v31; // eax
  unsigned int v32; // ecx
  int v33; // r8d
  LONG left; // eax
  int v35; // ecx
  int v36; // eax
  struct _RECTL v37; // [rsp+58h] [rbp-41h] BYREF
  int v38; // [rsp+68h] [rbp-31h]
  int top; // [rsp+6Ch] [rbp-2Dh]
  int v40; // [rsp+70h] [rbp-29h]
  __int128 v41; // [rsp+78h] [rbp-21h] BYREF
  int DeviceCaps; // [rsp+88h] [rbp-11h]
  int v43; // [rsp+8Ch] [rbp-Dh]
  struct _devicemodeW *v44; // [rsp+90h] [rbp-9h]
  int v45; // [rsp+E8h] [rbp+4Fh]

  if ( !this || !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
    return 2147500035LL;
  *(_DWORD *)a2 = 0;
  v8 = 0;
  *a3 = 0;
  v9 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v10 = *(HANDLE *)this;
  v45 = 0;
  v37.bottom = 0;
  v38 = 0;
  v11 = *((_QWORD *)v10 + 6);
  top = 0;
  if ( (*(_DWORD *)(v11 + 24) & 0x100000) == 0 )
  {
    Printer = MyGetPrinter(*((HANDLE *)this + 11), 4u);
    v13 = Printer;
    if ( !Printer || (DCW = CreateDCW(0, *(LPCWSTR *)Printer, 0, *((const DEVMODEW **)this + 4)), LocalFree(v13), !DCW) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        return (unsigned int)-2147467259;
      return (unsigned int)LastError;
    }
    v37.right = GetDeviceCaps(DCW, 112);
    DeviceCaps = GetDeviceCaps(DCW, 8);
    v43 = GetDeviceCaps(DCW, 113);
    LODWORD(v44) = GetDeviceCaps(DCW, 10);
    v37.left = GetDeviceCaps(DCW, 110);
    v40 = GetDeviceCaps(DCW, 111);
    v15 = GetDeviceCaps(DCW, 88);
    v16 = GetDeviceCaps(DCW, 90);
    if ( v15 && v16 )
    {
      v17 = 0;
      v45 = 25400 * v37.right / v15;
      v8 = 25400 * DeviceCaps / v15;
      v37.bottom = 25400 * v43 / v16;
      v9 = 25400 * (int)v44 / v16;
      v38 = 25400 * v37.left / v15;
      top = 25400 * v40 / v16;
    }
    else
    {
      v17 = -2147467259;
    }
    DeleteDC(DCW);
LABEL_36:
    if ( v17 >= 0 )
    {
      *(_DWORD *)a2 = v45;
      *a3 = v37.bottom;
      v35 = top;
      *a4 = v8;
      v36 = v38;
      *a5 = v9;
      *a6 = v36;
      *a7 = v35;
    }
    return (unsigned int)v17;
  }
  if ( v10 )
  {
    if ( v11 )
    {
      v19 = *(_QWORD *)(v11 + 40);
      if ( v19 )
      {
        v20 = (void *)*((_QWORD *)this + 1);
        if ( v20 )
        {
          if ( *((_QWORD *)this + 4) )
          {
            inited = (struct _PSDRVEXTRA *)InitBinaryData(v19, (__int64)a2, v20);
            if ( !inited )
              return 2147500037LL;
            v23 = *((_QWORD *)this + 4);
            v24 = (PSUI *)*((_QWORD *)this + 11);
            v44 = (struct _devicemodeW *)(v23 + *(unsigned __int16 *)(v23 + 68));
            v25 = (unsigned __int8 *)*((_QWORD *)this + 1);
            v41 = 0;
            *(_QWORD *)&v37.left = 0;
            v37.right = 0;
            v40 = PSUI::BPSGetXpsDrvPaperFormat(
                    v24,
                    v25,
                    (struct _OPTSELECT *)v23,
                    v44,
                    inited,
                    (struct _INFOHEADER *)&v41,
                    &v37,
                    (struct tagSIZE *)&v37.right,
                    (unsigned int *)v10 + 30,
                    (struct _FORM_INFO_2W **)v10 + 16);
            v28 = v40;
            if ( v40 )
            {
              right = v37.right;
              v30 = *((_QWORD *)this + 4);
              LOBYTE(v31) = PSUI::PSRotateXpsDrvImageableArea(
                              *((_QWORD *)this + 1),
                              v30,
                              (__int64)v44,
                              (__int64)inited,
                              (int *)&v41,
                              *(__int64 *)&v37.left,
                              v37.right);
              if ( *(_WORD *)(v30 + 76) == 2 )
              {
                if ( v31 == 1 )
                {
                  v32 = v41;
                  v33 = DWORD2(v41);
                  LODWORD(v41) = v37.top - HIDWORD(v41);
                  *(_QWORD *)((char *)&v41 + 4) = __PAIR64__(v37.top - DWORD1(v41), v32);
                  HIDWORD(v41) = v33;
                }
                if ( right != 1 )
                {
                  left = v37.left;
                  v37.left = v37.top;
                  v37.top = left;
                }
              }
              PSUI::PSSimulateV3ImageableArea(
                *((PSUI **)this + 1),
                (struct _OPTSELECT *)v30,
                (struct _devicemodeW *)inited,
                (struct _INFOHEADER *)&v41,
                &v37);
              v8 = DWORD2(v41) - v41;
              v28 = v40;
              v45 = v41;
              v9 = HIDWORD(v41) - DWORD1(v41);
              v37.bottom = DWORD1(v41);
              v38 = v37.left;
              top = v37.top;
            }
            FreeBinaryData((__int64)inited, v26, v27);
            v17 = v28 == 0 ? 0x80004005 : 0;
            goto LABEL_36;
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
0x18013f194  mov     rax, rsp
0x18013f197  mov     [rax+20h], r9
0x18013f19b  mov     [rax+18h], r8
0x18013f19f  mov     [rax+10h], rdx
0x18013f1a3  push    rbp
0x18013f1a4  push    rbx
0x18013f1a5  push    rsi
0x18013f1a6  push    rdi
0x18013f1a7  push    r12
0x18013f1a9  push    r13
0x18013f1ab  push    r14
0x18013f1ad  push    r15
0x18013f1af  lea     rbp, [rax-47h]
0x18013f1b3  sub     rsp, 98h
0x18013f1ba  xor     r10d, r10d
0x18013f1bd  mov     rbx, rcx
0x18013f1c0  test    rcx, rcx
0x18013f1c3  jz      loc_18013F5AF
0x18013f1c9  test    rdx, rdx
0x18013f1cc  jz      loc_18013F5AF
0x18013f1d2  test    r8, r8
0x18013f1d5  jz      loc_18013F5AF
0x18013f1db  test    r9, r9
0x18013f1de  jz      loc_18013F5AF
0x18013f1e4  mov     r12, [rbp+3Fh+arg_20]
0x18013f1e8  test    r12, r12
0x18013f1eb  jz      loc_18013F5AF
0x18013f1f1  mov     r13, [rbp+3Fh+arg_28]
0x18013f1f5  test    r13, r13
0x18013f1f8  jz      loc_18013F5AF
0x18013f1fe  mov     rax, [rbp+3Fh+arg_30]
0x18013f202  test    rax, rax
0x18013f205  jz      loc_18013F5AF
0x18013f20b  mov     [rdx], r10d
0x18013f20e  mov     r14d, r10d
0x18013f211  mov     [r8], r10d
0x18013f214  mov     r15d, r10d
0x18013f217  mov     [r9], r10d
0x18013f21a  mov     [r12], r10d
0x18013f21e  mov     [r13+0], r10d
0x18013f222  mov     [rax], r10d
0x18013f225  mov     rsi, [rcx]
0x18013f228  mov     [rbp+3Fh+arg_0], r10d
0x18013f22c  mov     [rbp+3Fh+var_80.bottom], r10d
0x18013f230  mov     [rbp+3Fh+var_70], r10d
0x18013f234  mov     rax, [rsi+30h]
0x18013f238  mov     [rbp+3Fh+var_6C], r10d
0x18013f23c  test    dword ptr [rax+18h], 100000h
0x18013f243  jnz     loc_18013F3E7
0x18013f249  mov     rcx, [rcx+58h]; hPrinter
0x18013f24d  lea     edx, [r10+4]; Level
0x18013f251  call    MyGetPrinter
0x18013f256  mov     rdi, rax
0x18013f259  test    rax, rax
0x18013f25c  jz      loc_18013F3BE
0x18013f262  mov     r9, [rbx+20h]; pdm
0x18013f266  xor     r8d, r8d; pszPort
0x18013f269  mov     rdx, [rax]; pwszDevice
0x18013f26c  xor     ecx, ecx; pwszDriver
0x18013f26e  call    cs:__imp_CreateDCW
0x18013f275  nop     dword ptr [rax+rax+00h]
0x18013f27a  mov     rcx, rdi; hMem
0x18013f27d  mov     rsi, rax
0x18013f280  call    cs:__imp_LocalFree
0x18013f287  nop     dword ptr [rax+rax+00h]
0x18013f28c  test    rsi, rsi
0x18013f28f  jz      loc_18013F3BE
0x18013f295  mov     edx, 70h ; 'p'; index
0x18013f29a  mov     rcx, rsi; hdc
0x18013f29d  call    cs:__imp_GetDeviceCaps
0x18013f2a4  nop     dword ptr [rax+rax+00h]
0x18013f2a9  mov     edx, 8; index
0x18013f2ae  mov     rcx, rsi; hdc
0x18013f2b1  mov     [rbp+3Fh+var_80.right], eax
0x18013f2b4  call    cs:__imp_GetDeviceCaps
0x18013f2bb  nop     dword ptr [rax+rax+00h]
0x18013f2c0  mov     edx, 71h ; 'q'; index
0x18013f2c5  mov     rcx, rsi; hdc
0x18013f2c8  mov     [rbp+3Fh+var_50], eax
0x18013f2cb  call    cs:__imp_GetDeviceCaps
0x18013f2d2  nop     dword ptr [rax+rax+00h]
0x18013f2d7  mov     edx, 0Ah; index
0x18013f2dc  mov     rcx, rsi; hdc
0x18013f2df  mov     [rbp+3Fh+var_4C], eax
0x18013f2e2  call    cs:__imp_GetDeviceCaps
0x18013f2e9  nop     dword ptr [rax+rax+00h]
0x18013f2ee  mov     edx, 6Eh ; 'n'; index
0x18013f2f3  mov     rcx, rsi; hdc
0x18013f2f6  mov     dword ptr [rbp+3Fh+var_48], eax
0x18013f2f9  call    cs:__imp_GetDeviceCaps
0x18013f300  nop     dword ptr [rax+rax+00h]
0x18013f305  mov     edx, 6Fh ; 'o'; index
0x18013f30a  mov     rcx, rsi; hdc
0x18013f30d  mov     [rbp+3Fh+var_80.left], eax
0x18013f310  call    cs:__imp_GetDeviceCaps
0x18013f317  nop     dword ptr [rax+rax+00h]
0x18013f31c  mov     edx, 58h ; 'X'; index
0x18013f321  mov     rcx, rsi; hdc
0x18013f324  mov     [rbp+3Fh+var_68], eax
0x18013f327  call    cs:__imp_GetDeviceCaps
0x18013f32e  nop     dword ptr [rax+rax+00h]
0x18013f333  mov     edx, 5Ah ; 'Z'; index
0x18013f338  mov     rcx, rsi; hdc
0x18013f33b  mov     edi, eax
0x18013f33d  call    cs:__imp_GetDeviceCaps
0x18013f344  nop     dword ptr [rax+rax+00h]
0x18013f349  mov     ecx, eax
0x18013f34b  test    edi, edi
0x18013f34d  jz      short loc_18013F3A5
0x18013f34f  test    eax, eax
0x18013f351  jz      short loc_18013F3A5
0x18013f353  imul    eax, [rbp+3Fh+var_80.right], 6338h
0x18013f35a  xor     ebx, ebx
0x18013f35c  cdq
0x18013f35d  idiv    edi
0x18013f35f  mov     [rbp+3Fh+arg_0], eax
0x18013f362  imul    eax, [rbp+3Fh+var_50], 6338h
0x18013f369  cdq
0x18013f36a  idiv    edi
0x18013f36c  mov     r14d, eax
0x18013f36f  imul    eax, [rbp+3Fh+var_4C], 6338h
0x18013f376  cdq
0x18013f377  idiv    ecx
0x18013f379  mov     [rbp+3Fh+var_80.bottom], eax
0x18013f37c  imul    eax, dword ptr [rbp+3Fh+var_48], 6338h
0x18013f383  cdq
0x18013f384  idiv    ecx
0x18013f386  mov     r15d, eax
0x18013f389  imul    eax, [rbp+3Fh+var_80.left], 6338h
0x18013f390  cdq
0x18013f391  idiv    edi
0x18013f393  mov     [rbp+3Fh+var_70], eax
0x18013f396  imul    eax, [rbp+3Fh+var_68], 6338h
0x18013f39d  cdq
0x18013f39e  idiv    ecx
0x18013f3a0  mov     [rbp+3Fh+var_6C], eax
0x18013f3a3  jmp     short loc_18013F3AA
0x18013f3a5  mov     ebx, 80004005h
0x18013f3aa  mov     rcx, rsi; hdc
0x18013f3ad  call    cs:__imp_DeleteDC
0x18013f3b4  nop     dword ptr [rax+rax+00h]
0x18013f3b9  jmp     loc_18013F573
0x18013f3be  call    cs:__imp_GetLastError
0x18013f3c5  nop     dword ptr [rax+rax+00h]
0x18013f3ca  test    eax, eax
0x18013f3cc  jle     short loc_18013F3D6
0x18013f3ce  movzx   eax, ax
0x18013f3d1  or      eax, 80070000h
0x18013f3d6  mov     ebx, 80004005h
0x18013f3db  test    eax, eax
0x18013f3dd  cmovns  eax, ebx
0x18013f3e0  mov     ebx, eax
0x18013f3e2  jmp     loc_18013F5A4
0x18013f3e7  test    rsi, rsi
0x18013f3ea  jz      loc_18013F5A8
0x18013f3f0  test    rax, rax
0x18013f3f3  jz      loc_18013F5A8
0x18013f3f9  mov     rcx, [rax+28h]
0x18013f3fd  test    rcx, rcx
0x18013f400  jz      loc_18013F5A8
0x18013f406  mov     r8, [rbx+8]
0x18013f40a  test    r8, r8
0x18013f40d  jz      loc_18013F5A8
0x18013f413  cmp     [rbx+20h], r10
0x18013f417  jz      loc_18013F5A8
0x18013f41d  call    InitBinaryData
0x18013f422  mov     rdi, rax
0x18013f425  test    rax, rax
0x18013f428  jnz     short loc_18013F434
0x18013f42a  mov     eax, 80004005h
0x18013f42f  jmp     loc_18013F5B4
0x18013f434  mov     r8, [rbx+20h]; struct _OPTSELECT *
0x18013f438  lea     rax, [rsi+80h]
0x18013f43f  mov     [rsp+48h], rax; struct _FORM_INFO_2W **
0x18013f444  lea     rcx, [rsi+78h]
0x18013f448  mov     [rsp+0D0h+var_90], rcx; unsigned int *
0x18013f44d  lea     rax, [rbp+3Fh+var_80.right]
0x18013f451  mov     rcx, [rbx+58h]; this
0x18013f455  xorps   xmm0, xmm0
0x18013f458  movzx   edx, word ptr [r8+44h]
0x18013f45d  mov     [rsp+0D0h+var_98], rax; struct tagSIZE *
0x18013f462  add     rdx, r8
0x18013f465  lea     rax, [rbp+3Fh+var_80]
0x18013f469  mov     [rbp+3Fh+var_48], rdx
0x18013f46d  mov     [rsp+0D0h+var_A0], rax; struct _RECTL *
0x18013f472  mov     r9, rdx; struct _devicemodeW *
0x18013f475  mov     rdx, [rbx+8]; void *
0x18013f479  lea     rax, [rbp+3Fh+var_60]
0x18013f47d  mov     [rsp+0D0h+var_A8], rax; struct _INFOHEADER *
0x18013f482  mov     [rsp+0D0h+var_B0], rdi; struct _PSDRVEXTRA *
0x18013f487  movups  [rbp+3Fh+var_60], xmm0
0x18013f48b  mov     qword ptr [rbp+3Fh+var_80.left], r14
0x18013f48f  mov     [rbp+3Fh+var_80.right], r14d
0x18013f493  call    ?BPSGetXpsDrvPaperFormat@PSUI@@YAHPEAXPEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_PSDRVEXTRA@@PEAU_INFOHEADER@@PEAU_RECTL@@PEAUtagSIZE@@PEAKPEAPEAU_FORM_INFO_2W@@7@Z; PSUI::BPSGetXpsDrvPaperFormat(void *,_OPTSELECT *,_devicemodeW *,_PSDRVEXTRA *,_INFOHEADER *,_RECTL *,tagSIZE *,ulong *,_FORM_INFO_2W * *,ulong *)
0x18013f498  mov     [rbp+3Fh+var_68], eax
0x18013f49b  mov     esi, eax
0x18013f49d  test    eax, eax
0x18013f49f  jz      loc_18013F55E
0x18013f4a5  mov     rcx, qword ptr [rbp+3Fh+var_80.left]
0x18013f4a9  lea     rax, [rbp+3Fh+var_60]
0x18013f4ad  mov     r14d, [rbp+3Fh+var_80.right]
0x18013f4b1  mov     r9, rdi
0x18013f4b4  mov     rsi, [rbx+20h]
0x18013f4b8  mov     r8, [rbp+3Fh+var_48]
0x18013f4bc  mov     rdx, rsi
0x18013f4bf  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x18013f4c4  mov     [rsp+0D0h+var_A8], rcx; struct tagSIZE *
0x18013f4c9  mov     rcx, [rbx+8]
0x18013f4cd  mov     [rsp+0D0h+var_B0], rax
0x18013f4d2  call    ?PSRotateXpsDrvImageableArea@PSUI@@YA?AW4Enum@ImageableAreaRotationMode@1@PEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_PSDRVEXTRA@@PEAU_INFOHEADER@@PEAU_RECTL@@UtagSIZE@@K@Z; PSUI::PSRotateXpsDrvImageableArea(_OPTSELECT *,_devicemodeW *,_PSDRVEXTRA *,_INFOHEADER *,_RECTL *,tagSIZE,ulong)
0x18013f4d7  cmp     word ptr [rsi+4Ch], 2
0x18013f4dc  jnz     short loc_18013F519
0x18013f4de  mov     r9d, [rbp+3Fh+var_80.top]
0x18013f4e2  cmp     eax, 1
0x18013f4e5  jnz     short loc_18013F509
0x18013f4e7  mov     ecx, dword ptr [rbp+3Fh+var_60]
0x18013f4ea  mov     eax, r9d
0x18013f4ed  sub     eax, dword ptr [rbp+3Fh+var_60+0Ch]
0x18013f4f0  mov     edx, dword ptr [rbp+3Fh+var_60+4]
0x18013f4f3  mov     r8d, dword ptr [rbp+3Fh+var_60+8]
0x18013f4f7  mov     dword ptr [rbp+3Fh+var_60], eax
0x18013f4fa  mov     eax, r9d
0x18013f4fd  sub     eax, edx
0x18013f4ff  mov     dword ptr [rbp+3Fh+var_60+4], ecx
0x18013f502  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x18013f505  mov     dword ptr [rbp+3Fh+var_60+0Ch], r8d
0x18013f509  cmp     r14d, 1
0x18013f50d  jz      short loc_18013F519
0x18013f50f  mov     eax, [rbp+3Fh+var_80.left]
0x18013f512  mov     [rbp+3Fh+var_80.left], r9d
0x18013f516  mov     [rbp+3Fh+var_80.top], eax
0x18013f519  mov     rcx, [rbx+8]; this
0x18013f51d  lea     rax, [rbp+3Fh+var_80]
0x18013f521  lea     r9, [rbp+3Fh+var_60]; struct _INFOHEADER *
0x18013f525  mov     [rsp+0D0h+var_B0], rax; struct _RECTL *
0x18013f52a  mov     r8, rdi; struct _devicemodeW *
0x18013f52d  mov     rdx, rsi; struct _OPTSELECT *
0x18013f530  call    ?PSSimulateV3ImageableArea@PSUI@@YAXPEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_INFOHEADER@@PEAU_RECTL@@PEAUtagSIZE@@@Z; PSUI::PSSimulateV3ImageableArea(_OPTSELECT *,_devicemodeW *,_INFOHEADER *,_RECTL *,tagSIZE *)
0x18013f535  mov     eax, dword ptr [rbp+3Fh+var_60]
0x18013f538  mov     r14d, dword ptr [rbp+3Fh+var_60+8]
0x18013f53c  mov     r15d, dword ptr [rbp+3Fh+var_60+0Ch]
0x18013f540  sub     r14d, eax
0x18013f543  mov     esi, [rbp+3Fh+var_68]
0x18013f546  mov     [rbp+3Fh+arg_0], eax
0x18013f549  mov     eax, dword ptr [rbp+3Fh+var_60+4]
0x18013f54c  sub     r15d, eax
0x18013f54f  mov     [rbp+3Fh+var_80.bottom], eax
0x18013f552  mov     eax, [rbp+3Fh+var_80.left]
0x18013f555  mov     [rbp+3Fh+var_70], eax
0x18013f558  mov     eax, [rbp+3Fh+var_80.top]
0x18013f55b  mov     [rbp+3Fh+var_6C], eax
0x18013f55e  mov     rcx, rdi
0x18013f561  call    FreeBinaryData
0x18013f566  neg     esi
0x18013f568  mov     ebx, 80004005h
0x18013f56d  sbb     ecx, ecx
0x18013f56f  not     ecx
0x18013f571  and     ebx, ecx
0x18013f573  test    ebx, ebx
0x18013f575  js      short loc_18013F5A4
0x18013f577  mov     rax, [rbp+3Fh+arg_8]
0x18013f57b  mov     ecx, [rbp+3Fh+arg_0]
0x18013f57e  mov     [rax], ecx
0x18013f580  mov     rax, [rbp+3Fh+arg_10]
0x18013f584  mov     ecx, [rbp+3Fh+var_80.bottom]
0x18013f587  mov     [rax], ecx
0x18013f589  mov     rax, [rbp+3Fh+arg_18]
0x18013f58d  mov     ecx, [rbp+3Fh+var_6C]
0x18013f590  mov     [rax], r14d
0x18013f593  mov     eax, [rbp+3Fh+var_70]
0x18013f596  mov     [r12], r15d
0x18013f59a  mov     [r13+0], eax
0x18013f59e  mov     rax, [rbp+3Fh+arg_30]
0x18013f5a2  mov     [rax], ecx
0x18013f5a4  mov     eax, ebx
0x18013f5a6  jmp     short loc_18013F5B4
0x18013f5a8  mov     eax, 8000FFFFh
0x18013f5ad  jmp     short loc_18013F5B4
0x18013f5af  mov     eax, 80004003h
0x18013f5b4  add     rsp, 98h
0x18013f5bb  pop     r15
0x18013f5bd  pop     r14
0x18013f5bf  pop     r13
0x18013f5c1  pop     r12
0x18013f5c3  pop     rdi
0x18013f5c4  pop     rsi
0x18013f5c5  pop     rbx
0x18013f5c6  pop     rbp
0x18013f5c7  retn
```
