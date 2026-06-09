# UniDrvUI::CalculatePrintableArea(UniDrvUI::ProviderDevcapsOperationToken *,int *,int *,int *,int *,int *,int *)

- ea: `0x180112bb8`
- end: `0x180112f6e`
- name: `?CalculatePrintableArea@UniDrvUI@@YAJPEAUProviderDevcapsOperationToken@1@PEAH11111@Z`
- size: `950`
- prototype: `__int64 __fastcall(UniDrvUI *__hidden this, struct UniDrvUI::ProviderDevcapsOperationToken *, int *, int *, int *, int *, int *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800eb350`
- `0x180116310`

## callees

- `0x180104930`
- `0x180105818`
- `0x180112bb8`
- `0x1801480c8`
- `0x180148100`
- `0x180148d9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180112da6`
- `KERNEL32!GetLastError` at `0x180112da6`
- `KERNEL32!LocalFree` at `0x180112c9c`
- `KERNEL32!LocalFree` at `0x180112c9c`
- `GDI32!DeleteDC` at `0x180112d9b`
- `GDI32!DeleteDC` at `0x180112d9b`
- `GDI32!CreateDCW` at `0x180112c90`
- `GDI32!CreateDCW` at `0x180112c90`
- `GDI32!GetDeviceCaps` at `0x180112cb3`
- `GDI32!GetDeviceCaps` at `0x180112cc4`
- `GDI32!GetDeviceCaps` at `0x180112cd5`
- `GDI32!GetDeviceCaps` at `0x180112ce6`
- `GDI32!GetDeviceCaps` at `0x180112cf7`
- `GDI32!GetDeviceCaps` at `0x180112d08`
- `GDI32!GetDeviceCaps` at `0x180112d19`
- `GDI32!GetDeviceCaps` at `0x180112d2a`
- `GDI32!GetDeviceCaps` at `0x180112cb3`
- `GDI32!GetDeviceCaps` at `0x180112cc4`
- `GDI32!GetDeviceCaps` at `0x180112cd5`
- `GDI32!GetDeviceCaps` at `0x180112ce6`
- `GDI32!GetDeviceCaps` at `0x180112cf7`
- `GDI32!GetDeviceCaps` at `0x180112d08`
- `GDI32!GetDeviceCaps` at `0x180112d19`
- `GDI32!GetDeviceCaps` at `0x180112d2a`

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
  char *v13; // rbx
  __int64 v14; // rax
  LPCWSTR *Printer; // rax
  LPCWSTR *v16; // rbx
  HDC DCW; // rdi
  int v18; // eax
  signed int v19; // ebx
  signed int LastError; // eax
  __int64 v21; // rcx
  HANDLE v22; // r8
  struct _devicemodeW *inited; // rax
  struct _OPTSELECT *v25; // r8
  HANDLE v26; // rcx
  HANDLE v27; // rdx
  LONG right; // ebx
  _WORD *v29; // rbx
  int v30; // eax
  int v31; // esi
  int v32; // r12d
  unsigned int *v33; // [rsp+50h] [rbp-49h]
  tagSIZE v34; // [rsp+58h] [rbp-41h] BYREF
  struct _RECTL v35; // [rsp+60h] [rbp-39h] BYREF
  __int128 v36; // [rsp+70h] [rbp-29h] BYREF
  struct _devicemodeW *v37; // [rsp+80h] [rbp-19h]
  int DeviceCaps; // [rsp+88h] [rbp-11h]
  int v39; // [rsp+8Ch] [rbp-Dh]
  int v40; // [rsp+90h] [rbp-9h]
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
  v13 = (char *)*this;
  left = 0;
  v14 = *((_QWORD *)*this + 6);
  if ( (*(_DWORD *)(v14 + 24) & 0x100000) == 0 )
  {
    Printer = (LPCWSTR *)MyGetPrinter(this[11], 4u);
    v16 = Printer;
    if ( !Printer || (DCW = CreateDCW(0, *Printer, 0, (const DEVMODEW *)this[4]), LocalFree(v16), !DCW) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        return (unsigned int)-2147467259;
      return (unsigned int)LastError;
    }
    DeviceCaps = GetDeviceCaps(DCW, 112);
    v39 = GetDeviceCaps(DCW, 8);
    v40 = GetDeviceCaps(DCW, 113);
    LODWORD(v37) = GetDeviceCaps(DCW, 10);
    v35.left = GetDeviceCaps(DCW, 110);
    v35.right = GetDeviceCaps(DCW, 111);
    v34.cx = GetDeviceCaps(DCW, 88);
    v18 = GetDeviceCaps(DCW, 90);
    if ( v34.cx && v18 )
    {
      v19 = 0;
      v8 = 25400 * DeviceCaps / v34.cx;
      v9 = 25400 * v39 / v34.cx;
      v10 = 25400 * v40 / v18;
      v11 = 25400 * (int)v37 / v18;
      left = 25400 * v35.left / v34.cx;
      top = 25400 * v35.right / v18;
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
            inited = (struct _devicemodeW *)InitBinaryData(v21, a7, v22);
            v37 = inited;
            if ( !inited )
              return 2147500037LL;
            v25 = (struct _OPTSELECT *)this[4];
            v26 = this[11];
            v27 = this[1];
            v36 = 0;
            *(_QWORD *)&v35.left = 0;
            v34.cx = 0;
            v35.right = UniDrvUI::BUniGetXpsDrvPaperFormat(
                          v26,
                          v27,
                          v25,
                          inited,
                          (struct _INFOHEADER *)&v36,
                          &v35,
                          &v34,
                          (enum _XPSDRVLANDSCAPE *)(v13 + 120),
                          (struct _FORM_INFO_2W **)v13 + 16,
                          v33);
            right = v35.right;
            if ( !v35.right )
              goto LABEL_38;
            v29 = this[4];
            v30 = UniDrvUI::UniRotateXpsDrvImageableArea(this[1], v29, v37, &v36, *(_QWORD *)&v35.left, v34.cx);
            top = v35.top;
            if ( v29[38] == 2 )
            {
              if ( v30 == 1 )
              {
                v10 = v36;
                v8 = v35.top - HIDWORD(v36);
                v31 = v35.top - DWORD1(v36);
                v32 = DWORD2(v36);
              }
              else
              {
                v32 = HIDWORD(v36);
                v31 = DWORD2(v36);
                v10 = DWORD1(v36);
                v8 = v36;
              }
              if ( v34.cx != 1 )
              {
                left = v35.top;
                top = v35.left;
LABEL_37:
                right = v35.right;
                v9 = v31 - v8;
                v11 = v32 - v10;
LABEL_38:
                FreeBinaryData(v37);
                v19 = right != 0 ? 0 : 0x80004005;
                goto LABEL_39;
              }
            }
            else
            {
              v32 = HIDWORD(v36);
              v31 = DWORD2(v36);
              v10 = DWORD1(v36);
              v8 = v36;
            }
            left = v35.left;
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
0x180112bb8  mov     rax, rsp
0x180112bbb  mov     [rax+20h], r9
0x180112bbf  mov     [rax+18h], r8
0x180112bc3  mov     [rax+10h], rdx
0x180112bc7  push    rbp
0x180112bc8  push    rbx
0x180112bc9  push    rsi
0x180112bca  push    rdi
0x180112bcb  push    r12
0x180112bcd  push    r13
0x180112bcf  push    r14
0x180112bd1  push    r15
0x180112bd3  lea     rbp, [rax-47h]
0x180112bd7  sub     rsp, 98h
0x180112bde  xor     r11d, r11d
0x180112be1  mov     r10, rdx
0x180112be4  mov     rdi, rcx
0x180112be7  test    rcx, rcx
0x180112bea  jz      loc_180112F55
0x180112bf0  test    rdx, rdx
0x180112bf3  jz      loc_180112F55
0x180112bf9  test    r8, r8
0x180112bfc  jz      loc_180112F55
0x180112c02  test    r9, r9
0x180112c05  jz      loc_180112F55
0x180112c0b  mov     rax, [rbp+3Fh+arg_20]
0x180112c0f  test    rax, rax
0x180112c12  jz      loc_180112F55
0x180112c18  mov     rcx, [rbp+3Fh+arg_28]
0x180112c1c  test    rcx, rcx
0x180112c1f  jz      loc_180112F55
0x180112c25  mov     rdx, [rbp+3Fh+arg_30]
0x180112c29  test    rdx, rdx
0x180112c2c  jz      loc_180112F55
0x180112c32  mov     [r10], r11d
0x180112c35  mov     r14d, r11d
0x180112c38  mov     [r8], r11d
0x180112c3b  mov     esi, r11d
0x180112c3e  mov     [r9], r11d
0x180112c41  mov     r13d, r11d
0x180112c44  mov     [rax], r11d
0x180112c47  mov     r12d, r11d
0x180112c4a  mov     [rcx], r11d
0x180112c4d  mov     r15d, r11d
0x180112c50  mov     [rdx], r11d
0x180112c53  mov     rbx, [rdi]
0x180112c56  mov     [rbp+3Fh+arg_0], r11d
0x180112c5a  mov     rax, [rbx+30h]
0x180112c5e  test    dword ptr [rax+18h], 100000h
0x180112c65  jnz     loc_180112DC9
0x180112c6b  mov     rcx, [rdi+58h]; hPrinter
0x180112c6f  lea     edx, [r11+4]; Level
0x180112c73  call    MyGetPrinter
0x180112c78  mov     rbx, rax
0x180112c7b  test    rax, rax
0x180112c7e  jz      loc_180112DA6
0x180112c84  mov     r9, [rdi+20h]; pdm
0x180112c88  xor     r8d, r8d; pszPort
0x180112c8b  mov     rdx, [rax]; pwszDevice
0x180112c8e  xor     ecx, ecx; pwszDriver
0x180112c90  call    cs:__imp_CreateDCW
0x180112c96  mov     rcx, rbx; hMem
0x180112c99  mov     rdi, rax
0x180112c9c  call    cs:__imp_LocalFree
0x180112ca2  test    rdi, rdi
0x180112ca5  jz      loc_180112DA6
0x180112cab  mov     edx, 70h ; 'p'; index
0x180112cb0  mov     rcx, rdi; hdc
0x180112cb3  call    cs:__imp_GetDeviceCaps
0x180112cb9  mov     edx, 8; index
0x180112cbe  mov     rcx, rdi; hdc
0x180112cc1  mov     [rbp+3Fh+var_50], eax
0x180112cc4  call    cs:__imp_GetDeviceCaps
0x180112cca  mov     edx, 71h ; 'q'; index
0x180112ccf  mov     rcx, rdi; hdc
0x180112cd2  mov     [rbp+3Fh+var_4C], eax
0x180112cd5  call    cs:__imp_GetDeviceCaps
0x180112cdb  mov     edx, 0Ah; index
0x180112ce0  mov     rcx, rdi; hdc
0x180112ce3  mov     [rbp+3Fh+var_48], eax
0x180112ce6  call    cs:__imp_GetDeviceCaps
0x180112cec  mov     edx, 6Eh ; 'n'; index
0x180112cf1  mov     rcx, rdi; hdc
0x180112cf4  mov     dword ptr [rbp+3Fh+var_58], eax
0x180112cf7  call    cs:__imp_GetDeviceCaps
0x180112cfd  mov     edx, 6Fh ; 'o'; index
0x180112d02  mov     rcx, rdi; hdc
0x180112d05  mov     [rbp+3Fh+var_78.left], eax
0x180112d08  call    cs:__imp_GetDeviceCaps
0x180112d0e  mov     edx, 58h ; 'X'; index
0x180112d13  mov     rcx, rdi; hdc
0x180112d16  mov     [rbp+3Fh+var_78.right], eax
0x180112d19  call    cs:__imp_GetDeviceCaps
0x180112d1f  mov     edx, 5Ah ; 'Z'; index
0x180112d24  mov     rcx, rdi; hdc
0x180112d27  mov     [rbp+3Fh+var_80.cx], eax
0x180112d2a  call    cs:__imp_GetDeviceCaps
0x180112d30  mov     r8d, [rbp+3Fh+var_80.cx]
0x180112d34  mov     ecx, eax
0x180112d36  test    r8d, r8d
0x180112d39  jz      short loc_180112D93
0x180112d3b  test    eax, eax
0x180112d3d  jz      short loc_180112D93
0x180112d3f  imul    eax, [rbp+3Fh+var_50], 6338h
0x180112d46  xor     ebx, ebx
0x180112d48  cdq
0x180112d49  idiv    r8d
0x180112d4c  mov     r14d, eax
0x180112d4f  imul    eax, [rbp+3Fh+var_4C], 6338h
0x180112d56  cdq
0x180112d57  idiv    r8d
0x180112d5a  mov     esi, eax
0x180112d5c  imul    eax, [rbp+3Fh+var_48], 6338h
0x180112d63  cdq
0x180112d64  idiv    ecx
0x180112d66  mov     r13d, eax
0x180112d69  imul    eax, dword ptr [rbp+3Fh+var_58], 6338h
0x180112d70  cdq
0x180112d71  idiv    ecx
0x180112d73  mov     r12d, eax
0x180112d76  imul    eax, [rbp+3Fh+var_78.left], 6338h
0x180112d7d  cdq
0x180112d7e  idiv    r8d
0x180112d81  mov     [rbp+3Fh+arg_0], eax
0x180112d84  imul    eax, [rbp+3Fh+var_78.right], 6338h
0x180112d8b  cdq
0x180112d8c  idiv    ecx
0x180112d8e  mov     r15d, eax
0x180112d91  jmp     short loc_180112D98
0x180112d93  mov     ebx, 80004005h
0x180112d98  mov     rcx, rdi; hdc
0x180112d9b  call    cs:__imp_DeleteDC
0x180112da1  jmp     loc_180112F1B
0x180112da6  call    cs:__imp_GetLastError
0x180112dac  test    eax, eax
0x180112dae  jle     short loc_180112DB8
0x180112db0  movzx   eax, ax
0x180112db3  or      eax, 80070000h
0x180112db8  mov     ebx, 80004005h
0x180112dbd  test    eax, eax
0x180112dbf  cmovns  eax, ebx
0x180112dc2  mov     ebx, eax
0x180112dc4  jmp     loc_180112F4A
0x180112dc9  test    rbx, rbx
0x180112dcc  jz      loc_180112F4E
0x180112dd2  test    rax, rax
0x180112dd5  jz      loc_180112F4E
0x180112ddb  mov     rcx, [rax+28h]
0x180112ddf  test    rcx, rcx
0x180112de2  jz      loc_180112F4E
0x180112de8  mov     r8, [rdi+8]
0x180112dec  test    r8, r8
0x180112def  jz      loc_180112F4E
0x180112df5  cmp     [rdi+20h], r11
0x180112df9  jz      loc_180112F4E
0x180112dff  call    InitBinaryData
0x180112e04  mov     [rbp+3Fh+var_58], rax
0x180112e08  mov     rdx, rax
0x180112e0b  test    rax, rax
0x180112e0e  jnz     short loc_180112E1A
0x180112e10  mov     eax, 80004005h
0x180112e15  jmp     loc_180112F5A
0x180112e1a  mov     r8, [rdi+20h]; struct _OPTSELECT *
0x180112e1e  lea     rax, [rbx+80h]
0x180112e25  mov     [rsp+40h], rax; struct _FORM_INFO_2W **
0x180112e2a  lea     rcx, [rbx+78h]
0x180112e2e  mov     [rsp+0D0h+var_98], rcx; enum _XPSDRVLANDSCAPE *
0x180112e33  lea     rax, [rbp+3Fh+var_80]
0x180112e37  mov     rcx, [rdi+58h]; hPrinter
0x180112e3b  xorps   xmm0, xmm0
0x180112e3e  mov     [rsp+0D0h+var_A0], rax; struct tagSIZE *
0x180112e43  mov     r9, rdx; struct _devicemodeW *
0x180112e46  mov     rdx, [rdi+8]; void *
0x180112e4a  lea     rax, [rbp+3Fh+var_78]
0x180112e4e  mov     [rsp+0D0h+var_A8], rax; struct _RECTL *
0x180112e53  lea     rax, [rbp+3Fh+var_68]
0x180112e57  mov     [rsp+0D0h+var_B0], rax; struct _INFOHEADER *
0x180112e5c  movups  [rbp+3Fh+var_68], xmm0
0x180112e60  mov     qword ptr [rbp+3Fh+var_78.left], rsi
0x180112e64  mov     [rbp+3Fh+var_80.cx], esi
0x180112e67  call    ?BUniGetXpsDrvPaperFormat@UniDrvUI@@YAHPEAXPEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_INFOHEADER@@PEAU_RECTL@@PEAUtagSIZE@@PEAW4_XPSDRVLANDSCAPE@@PEAPEAU_FORM_INFO_2W@@PEAK@Z; UniDrvUI::BUniGetXpsDrvPaperFormat(void *,_OPTSELECT *,_devicemodeW *,_INFOHEADER *,_RECTL *,tagSIZE *,_XPSDRVLANDSCAPE *,_FORM_INFO_2W * *,ulong *)
0x180112e6c  mov     [rbp+3Fh+var_78.right], eax
0x180112e6f  mov     ebx, eax
0x180112e71  test    eax, eax
0x180112e73  jz      loc_180112F05
0x180112e79  mov     ecx, [rbp+3Fh+var_80.cx]
0x180112e7c  lea     r9, [rbp+3Fh+var_68]
0x180112e80  mov     rbx, [rdi+20h]
0x180112e84  mov     r8, [rbp+3Fh+var_58]
0x180112e88  mov     rdx, rbx
0x180112e8b  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x180112e8f  mov     rcx, qword ptr [rbp+3Fh+var_78.left]
0x180112e93  mov     [rsp+0D0h+var_B0], rcx
0x180112e98  mov     rcx, [rdi+8]
0x180112e9c  call    ?UniRotateXpsDrvImageableArea@UniDrvUI@@YA?AW4Enum@ImageableAreaRotationMode@1@PEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_INFOHEADER@@PEAU_RECTL@@UtagSIZE@@W4_XPSDRVLANDSCAPE@@@Z; UniDrvUI::UniRotateXpsDrvImageableArea(_OPTSELECT *,_devicemodeW *,_INFOHEADER *,_RECTL *,tagSIZE,_XPSDRVLANDSCAPE)
0x180112ea1  cmp     word ptr [rbx+4Ch], 2
0x180112ea6  mov     r15d, [rbp+3Fh+var_78.top]
0x180112eaa  jnz     short loc_180112EE7
0x180112eac  cmp     eax, 1
0x180112eaf  jnz     short loc_180112EC8
0x180112eb1  mov     r13d, dword ptr [rbp+3Fh+var_68]
0x180112eb5  mov     r14d, r15d
0x180112eb8  sub     r14d, dword ptr [rbp+3Fh+var_68+0Ch]
0x180112ebc  mov     esi, r15d
0x180112ebf  sub     esi, dword ptr [rbp+3Fh+var_68+4]
0x180112ec2  mov     r12d, dword ptr [rbp+3Fh+var_68+8]
0x180112ec6  jmp     short loc_180112ED7
0x180112ec8  mov     r12d, dword ptr [rbp+3Fh+var_68+0Ch]
0x180112ecc  mov     esi, dword ptr [rbp+3Fh+var_68+8]
0x180112ecf  mov     r13d, dword ptr [rbp+3Fh+var_68+4]
0x180112ed3  mov     r14d, dword ptr [rbp+3Fh+var_68]
0x180112ed7  cmp     [rbp+3Fh+var_80.cx], 1
0x180112edb  jz      short loc_180112EF6
0x180112edd  mov     [rbp+3Fh+arg_0], r15d
0x180112ee1  mov     r15d, [rbp+3Fh+var_78.left]
0x180112ee5  jmp     short loc_180112EFC
0x180112ee7  mov     r12d, dword ptr [rbp+3Fh+var_68+0Ch]
0x180112eeb  mov     esi, dword ptr [rbp+3Fh+var_68+8]
0x180112eee  mov     r13d, dword ptr [rbp+3Fh+var_68+4]
0x180112ef2  mov     r14d, dword ptr [rbp+3Fh+var_68]
0x180112ef6  mov     eax, [rbp+3Fh+var_78.left]
0x180112ef9  mov     [rbp+3Fh+arg_0], eax
0x180112efc  mov     ebx, [rbp+3Fh+var_78.right]
0x180112eff  sub     esi, r14d
0x180112f02  sub     r12d, r13d
0x180112f05  mov     rcx, [rbp+3Fh+var_58]
0x180112f09  call    FreeBinaryData
0x180112f0e  neg     ebx
0x180112f10  mov     ebx, 80004005h
0x180112f15  sbb     ecx, ecx
0x180112f17  not     ecx
0x180112f19  and     ebx, ecx
0x180112f1b  test    ebx, ebx
0x180112f1d  js      short loc_180112F4A
0x180112f1f  mov     rax, [rbp+3Fh+arg_8]
0x180112f23  mov     rcx, [rbp+3Fh+arg_28]
0x180112f27  mov     [rax], r14d
0x180112f2a  mov     rax, [rbp+3Fh+arg_10]
0x180112f2e  mov     [rax], r13d
0x180112f31  mov     rax, [rbp+3Fh+arg_18]
0x180112f35  mov     [rax], esi
0x180112f37  mov     rax, [rbp+3Fh+arg_20]
0x180112f3b  mov     [rax], r12d
0x180112f3e  mov     eax, [rbp+3Fh+arg_0]
0x180112f41  mov     [rcx], eax
0x180112f43  mov     rax, [rbp+3Fh+arg_30]
0x180112f47  mov     [rax], r15d
0x180112f4a  mov     eax, ebx
0x180112f4c  jmp     short loc_180112F5A
0x180112f4e  mov     eax, 8000FFFFh
0x180112f53  jmp     short loc_180112F5A
0x180112f55  mov     eax, 80004003h
0x180112f5a  add     rsp, 98h
0x180112f61  pop     r15
0x180112f63  pop     r14
0x180112f65  pop     r13
0x180112f67  pop     r12
0x180112f69  pop     rdi
0x180112f6a  pop     rsi
0x180112f6b  pop     rbx
0x180112f6c  pop     rbp
0x180112f6d  retn
```
