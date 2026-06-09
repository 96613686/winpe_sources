# PSUI::CalculatePrintableArea(PSUI::ProviderDevcapsOperationToken *,int *,int *,int *,int *,int *,int *)

- ea: `0x180138e5c`
- end: `0x180139248`
- name: `?CalculatePrintableArea@PSUI@@YAJPEAUProviderDevcapsOperationToken@1@PEAH11111@Z`
- size: `1004`
- prototype: `__int64 __fastcall(PSUI *__hidden this, struct PSUI::ProviderDevcapsOperationToken *, int *, int *, int *, int *, int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18012603c`
- `0x18013bf80`

## callees

- `0x18012c19c`
- `0x18012d1cc`
- `0x18012d36c`
- `0x180138e5c`
- `0x1801480c8`
- `0x180148100`
- `0x180148d9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180139044`
- `KERNEL32!GetLastError` at `0x180139044`
- `KERNEL32!LocalFree` at `0x180138f42`
- `KERNEL32!LocalFree` at `0x180138f42`
- `GDI32!DeleteDC` at `0x180139039`
- `GDI32!DeleteDC` at `0x180139039`
- `GDI32!CreateDCW` at `0x180138f36`
- `GDI32!CreateDCW` at `0x180138f36`
- `GDI32!GetDeviceCaps` at `0x180138f59`
- `GDI32!GetDeviceCaps` at `0x180138f6a`
- `GDI32!GetDeviceCaps` at `0x180138f7b`
- `GDI32!GetDeviceCaps` at `0x180138f8c`
- `GDI32!GetDeviceCaps` at `0x180138f9d`
- `GDI32!GetDeviceCaps` at `0x180138fae`
- `GDI32!GetDeviceCaps` at `0x180138fbf`
- `GDI32!GetDeviceCaps` at `0x180138fcf`
- `GDI32!GetDeviceCaps` at `0x180138f59`
- `GDI32!GetDeviceCaps` at `0x180138f6a`
- `GDI32!GetDeviceCaps` at `0x180138f7b`
- `GDI32!GetDeviceCaps` at `0x180138f8c`
- `GDI32!GetDeviceCaps` at `0x180138f9d`
- `GDI32!GetDeviceCaps` at `0x180138fae`
- `GDI32!GetDeviceCaps` at `0x180138fbf`
- `GDI32!GetDeviceCaps` at `0x180138fcf`

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
  LPCWSTR *Printer; // rax
  LPCWSTR *v13; // rdi
  HDC DCW; // rsi
  int v15; // edi
  int v16; // eax
  signed int v17; // ebx
  signed int LastError; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  struct _PSDRVEXTRA *inited; // rdi
  __int64 v23; // r8
  PSUI *v24; // rcx
  void *v25; // rdx
  int v26; // esi
  LONG right; // r14d
  __int64 v28; // rsi
  int v29; // eax
  unsigned int v30; // ecx
  int v31; // r8d
  LONG left; // eax
  int v33; // ecx
  int v34; // eax
  struct tagSIZE *v35; // [rsp+30h] [rbp-69h]
  struct _RECTL v36; // [rsp+58h] [rbp-41h] BYREF
  int v37; // [rsp+68h] [rbp-31h]
  int top; // [rsp+6Ch] [rbp-2Dh]
  int v39; // [rsp+70h] [rbp-29h]
  __int128 v40; // [rsp+78h] [rbp-21h] BYREF
  int DeviceCaps; // [rsp+88h] [rbp-11h]
  int v42; // [rsp+8Ch] [rbp-Dh]
  struct _devicemodeW *v43; // [rsp+90h] [rbp-9h]
  int v44; // [rsp+E8h] [rbp+4Fh]

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
  v44 = 0;
  v36.bottom = 0;
  v37 = 0;
  v11 = *((_QWORD *)v10 + 6);
  top = 0;
  if ( (*(_DWORD *)(v11 + 24) & 0x100000) == 0 )
  {
    Printer = (LPCWSTR *)MyGetPrinter(*((HANDLE *)this + 11), 4u);
    v13 = Printer;
    if ( !Printer || (DCW = CreateDCW(0, *Printer, 0, *((const DEVMODEW **)this + 4)), LocalFree(v13), !DCW) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        return (unsigned int)-2147467259;
      return (unsigned int)LastError;
    }
    v36.right = GetDeviceCaps(DCW, 112);
    DeviceCaps = GetDeviceCaps(DCW, 8);
    v42 = GetDeviceCaps(DCW, 113);
    LODWORD(v43) = GetDeviceCaps(DCW, 10);
    v36.left = GetDeviceCaps(DCW, 110);
    v39 = GetDeviceCaps(DCW, 111);
    v15 = GetDeviceCaps(DCW, 88);
    v16 = GetDeviceCaps(DCW, 90);
    if ( v15 && v16 )
    {
      v17 = 0;
      v44 = 25400 * v36.right / v15;
      v8 = 25400 * DeviceCaps / v15;
      v36.bottom = 25400 * v42 / v16;
      v9 = 25400 * (int)v43 / v16;
      v37 = 25400 * v36.left / v15;
      top = 25400 * v39 / v16;
    }
    else
    {
      v17 = -2147467259;
    }
    DeleteDC(DCW);
LABEL_36:
    if ( v17 >= 0 )
    {
      *(_DWORD *)a2 = v44;
      *a3 = v36.bottom;
      v33 = top;
      *a4 = v8;
      v34 = v37;
      *a5 = v9;
      *a6 = v34;
      *a7 = v33;
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
        v20 = *((_QWORD *)this + 1);
        if ( v20 )
        {
          if ( *((_QWORD *)this + 4) )
          {
            inited = (struct _PSDRVEXTRA *)InitBinaryData(v19, a2, v20);
            if ( !inited )
              return 2147500037LL;
            v23 = *((_QWORD *)this + 4);
            v24 = (PSUI *)*((_QWORD *)this + 11);
            v43 = (struct _devicemodeW *)(v23 + *(unsigned __int16 *)(v23 + 68));
            v25 = (void *)*((_QWORD *)this + 1);
            v40 = 0;
            v36.right = 0;
            v39 = PSUI::BPSGetXpsDrvPaperFormat(
                    v24,
                    v25,
                    (struct _OPTSELECT *)v23,
                    v43,
                    inited,
                    (struct _INFOHEADER *)&v40,
                    &v36,
                    (struct tagSIZE *)&v36.right,
                    (unsigned int *)v10 + 30,
                    (struct _FORM_INFO_2W **)v10 + 16,
                    0);
            v26 = v39;
            if ( v39 )
            {
              right = v36.right;
              v28 = *((_QWORD *)this + 4);
              v35 = *(struct tagSIZE **)&v36.left;
              v29 = PSUI::PSRotateXpsDrvImageableArea(*((_QWORD *)this + 1), v28, v43, inited, &v40);
              if ( *(_WORD *)(v28 + 76) == 2 )
              {
                if ( v29 == 1 )
                {
                  v30 = v40;
                  v31 = DWORD2(v40);
                  LODWORD(v40) = v36.top - HIDWORD(v40);
                  *(_QWORD *)((char *)&v40 + 4) = __PAIR64__(v36.top - DWORD1(v40), v30);
                  HIDWORD(v40) = v31;
                }
                if ( right != 1 )
                {
                  left = v36.left;
                  v36.left = v36.top;
                  v36.top = left;
                }
              }
              PSUI::PSSimulateV3ImageableArea(
                *((PSUI **)this + 1),
                (struct _OPTSELECT *)v28,
                (struct _devicemodeW *)inited,
                (struct _INFOHEADER *)&v40,
                &v36,
                v35);
              v8 = DWORD2(v40) - v40;
              v26 = v39;
              v44 = v40;
              v9 = HIDWORD(v40) - DWORD1(v40);
              v36.bottom = DWORD1(v40);
              v37 = v36.left;
              top = v36.top;
            }
            FreeBinaryData(inited);
            v17 = v26 == 0 ? 0x80004005 : 0;
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
0x180138e5c  mov     rax, rsp
0x180138e5f  mov     [rax+20h], r9
0x180138e63  mov     [rax+18h], r8
0x180138e67  mov     [rax+10h], rdx
0x180138e6b  push    rbp
0x180138e6c  push    rbx
0x180138e6d  push    rsi
0x180138e6e  push    rdi
0x180138e6f  push    r12
0x180138e71  push    r13
0x180138e73  push    r14
0x180138e75  push    r15
0x180138e77  lea     rbp, [rax-47h]
0x180138e7b  sub     rsp, 98h
0x180138e82  xor     r10d, r10d
0x180138e85  mov     rbx, rcx
0x180138e88  test    rcx, rcx
0x180138e8b  jz      loc_18013922F
0x180138e91  test    rdx, rdx
0x180138e94  jz      loc_18013922F
0x180138e9a  test    r8, r8
0x180138e9d  jz      loc_18013922F
0x180138ea3  test    r9, r9
0x180138ea6  jz      loc_18013922F
0x180138eac  mov     r12, [rbp+3Fh+arg_20]
0x180138eb0  test    r12, r12
0x180138eb3  jz      loc_18013922F
0x180138eb9  mov     r13, [rbp+3Fh+arg_28]
0x180138ebd  test    r13, r13
0x180138ec0  jz      loc_18013922F
0x180138ec6  mov     rax, [rbp+3Fh+arg_30]
0x180138eca  test    rax, rax
0x180138ecd  jz      loc_18013922F
0x180138ed3  mov     [rdx], r10d
0x180138ed6  mov     r14d, r10d
0x180138ed9  mov     [r8], r10d
0x180138edc  mov     r15d, r10d
0x180138edf  mov     [r9], r10d
0x180138ee2  mov     [r12], r10d
0x180138ee6  mov     [r13+0], r10d
0x180138eea  mov     [rax], r10d
0x180138eed  mov     rsi, [rcx]
0x180138ef0  mov     [rbp+3Fh+arg_0], r10d
0x180138ef4  mov     [rbp+3Fh+var_80.bottom], r10d
0x180138ef8  mov     [rbp+3Fh+var_70], r10d
0x180138efc  mov     rax, [rsi+30h]
0x180138f00  mov     [rbp+3Fh+var_6C], r10d
0x180138f04  test    dword ptr [rax+18h], 100000h
0x180138f0b  jnz     loc_180139067
0x180138f11  mov     rcx, [rcx+58h]; hPrinter
0x180138f15  lea     edx, [r10+4]; Level
0x180138f19  call    MyGetPrinter
0x180138f1e  mov     rdi, rax
0x180138f21  test    rax, rax
0x180138f24  jz      loc_180139044
0x180138f2a  mov     r9, [rbx+20h]; pdm
0x180138f2e  xor     r8d, r8d; pszPort
0x180138f31  mov     rdx, [rax]; pwszDevice
0x180138f34  xor     ecx, ecx; pwszDriver
0x180138f36  call    cs:__imp_CreateDCW
0x180138f3c  mov     rcx, rdi; hMem
0x180138f3f  mov     rsi, rax
0x180138f42  call    cs:__imp_LocalFree
0x180138f48  test    rsi, rsi
0x180138f4b  jz      loc_180139044
0x180138f51  mov     edx, 70h ; 'p'; index
0x180138f56  mov     rcx, rsi; hdc
0x180138f59  call    cs:__imp_GetDeviceCaps
0x180138f5f  mov     edx, 8; index
0x180138f64  mov     rcx, rsi; hdc
0x180138f67  mov     [rbp+3Fh+var_80.right], eax
0x180138f6a  call    cs:__imp_GetDeviceCaps
0x180138f70  mov     edx, 71h ; 'q'; index
0x180138f75  mov     rcx, rsi; hdc
0x180138f78  mov     [rbp+3Fh+var_50], eax
0x180138f7b  call    cs:__imp_GetDeviceCaps
0x180138f81  mov     edx, 0Ah; index
0x180138f86  mov     rcx, rsi; hdc
0x180138f89  mov     [rbp+3Fh+var_4C], eax
0x180138f8c  call    cs:__imp_GetDeviceCaps
0x180138f92  mov     edx, 6Eh ; 'n'; index
0x180138f97  mov     rcx, rsi; hdc
0x180138f9a  mov     dword ptr [rbp+3Fh+var_48], eax
0x180138f9d  call    cs:__imp_GetDeviceCaps
0x180138fa3  mov     edx, 6Fh ; 'o'; index
0x180138fa8  mov     rcx, rsi; hdc
0x180138fab  mov     [rbp+3Fh+var_80.left], eax
0x180138fae  call    cs:__imp_GetDeviceCaps
0x180138fb4  mov     edx, 58h ; 'X'; index
0x180138fb9  mov     rcx, rsi; hdc
0x180138fbc  mov     [rbp+3Fh+var_68], eax
0x180138fbf  call    cs:__imp_GetDeviceCaps
0x180138fc5  mov     edx, 5Ah ; 'Z'; index
0x180138fca  mov     rcx, rsi; hdc
0x180138fcd  mov     edi, eax
0x180138fcf  call    cs:__imp_GetDeviceCaps
0x180138fd5  mov     ecx, eax
0x180138fd7  test    edi, edi
0x180138fd9  jz      short loc_180139031
0x180138fdb  test    eax, eax
0x180138fdd  jz      short loc_180139031
0x180138fdf  imul    eax, [rbp+3Fh+var_80.right], 6338h
0x180138fe6  xor     ebx, ebx
0x180138fe8  cdq
0x180138fe9  idiv    edi
0x180138feb  mov     [rbp+3Fh+arg_0], eax
0x180138fee  imul    eax, [rbp+3Fh+var_50], 6338h
0x180138ff5  cdq
0x180138ff6  idiv    edi
0x180138ff8  mov     r14d, eax
0x180138ffb  imul    eax, [rbp+3Fh+var_4C], 6338h
0x180139002  cdq
0x180139003  idiv    ecx
0x180139005  mov     [rbp+3Fh+var_80.bottom], eax
0x180139008  imul    eax, dword ptr [rbp+3Fh+var_48], 6338h
0x18013900f  cdq
0x180139010  idiv    ecx
0x180139012  mov     r15d, eax
0x180139015  imul    eax, [rbp+3Fh+var_80.left], 6338h
0x18013901c  cdq
0x18013901d  idiv    edi
0x18013901f  mov     [rbp+3Fh+var_70], eax
0x180139022  imul    eax, [rbp+3Fh+var_68], 6338h
0x180139029  cdq
0x18013902a  idiv    ecx
0x18013902c  mov     [rbp+3Fh+var_6C], eax
0x18013902f  jmp     short loc_180139036
0x180139031  mov     ebx, 80004005h
0x180139036  mov     rcx, rsi; hdc
0x180139039  call    cs:__imp_DeleteDC
0x18013903f  jmp     loc_1801391F3
0x180139044  call    cs:__imp_GetLastError
0x18013904a  test    eax, eax
0x18013904c  jle     short loc_180139056
0x18013904e  movzx   eax, ax
0x180139051  or      eax, 80070000h
0x180139056  mov     ebx, 80004005h
0x18013905b  test    eax, eax
0x18013905d  cmovns  eax, ebx
0x180139060  mov     ebx, eax
0x180139062  jmp     loc_180139224
0x180139067  test    rsi, rsi
0x18013906a  jz      loc_180139228
0x180139070  test    rax, rax
0x180139073  jz      loc_180139228
0x180139079  mov     rcx, [rax+28h]
0x18013907d  test    rcx, rcx
0x180139080  jz      loc_180139228
0x180139086  mov     r8, [rbx+8]
0x18013908a  test    r8, r8
0x18013908d  jz      loc_180139228
0x180139093  cmp     [rbx+20h], r10
0x180139097  jz      loc_180139228
0x18013909d  call    InitBinaryData
0x1801390a2  mov     rdi, rax
0x1801390a5  test    rax, rax
0x1801390a8  jnz     short loc_1801390B4
0x1801390aa  mov     eax, 80004005h
0x1801390af  jmp     loc_180139234
0x1801390b4  mov     r8, [rbx+20h]; struct _OPTSELECT *
0x1801390b8  lea     rax, [rsi+80h]
0x1801390bf  mov     [rsp+48h], rax; struct _FORM_INFO_2W **
0x1801390c4  lea     rcx, [rsi+78h]
0x1801390c8  mov     [rsp+0D0h+var_90], rcx; unsigned int *
0x1801390cd  lea     rax, [rbp+3Fh+var_80.right]
0x1801390d1  mov     rcx, [rbx+58h]; this
0x1801390d5  xorps   xmm0, xmm0
0x1801390d8  movzx   edx, word ptr [r8+44h]
0x1801390dd  mov     [rsp+0D0h+var_98], rax; struct tagSIZE *
0x1801390e2  add     rdx, r8
0x1801390e5  lea     rax, [rbp+3Fh+var_80]
0x1801390e9  mov     [rbp+3Fh+var_48], rdx
0x1801390ed  mov     [rsp+0D0h+var_A0], rax; struct _RECTL *
0x1801390f2  mov     r9, rdx; struct _devicemodeW *
0x1801390f5  mov     rdx, [rbx+8]; void *
0x1801390f9  lea     rax, [rbp+3Fh+var_60]
0x1801390fd  mov     [rsp+0D0h+var_A8], rax; struct _INFOHEADER *
0x180139102  mov     [rsp+0D0h+var_B0], rdi; struct _PSDRVEXTRA *
0x180139107  movups  [rbp+3Fh+var_60], xmm0
0x18013910b  mov     qword ptr [rbp+3Fh+var_80.left], r14
0x18013910f  mov     [rbp+3Fh+var_80.right], r14d
0x180139113  call    ?BPSGetXpsDrvPaperFormat@PSUI@@YAHPEAXPEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_PSDRVEXTRA@@PEAU_INFOHEADER@@PEAU_RECTL@@PEAUtagSIZE@@PEAKPEAPEAU_FORM_INFO_2W@@7@Z; PSUI::BPSGetXpsDrvPaperFormat(void *,_OPTSELECT *,_devicemodeW *,_PSDRVEXTRA *,_INFOHEADER *,_RECTL *,tagSIZE *,ulong *,_FORM_INFO_2W * *,ulong *)
0x180139118  mov     [rbp+3Fh+var_68], eax
0x18013911b  mov     esi, eax
0x18013911d  test    eax, eax
0x18013911f  jz      loc_1801391DE
0x180139125  mov     rcx, qword ptr [rbp+3Fh+var_80.left]
0x180139129  lea     rax, [rbp+3Fh+var_60]
0x18013912d  mov     r14d, [rbp+3Fh+var_80.right]
0x180139131  mov     r9, rdi
0x180139134  mov     rsi, [rbx+20h]
0x180139138  mov     r8, [rbp+3Fh+var_48]
0x18013913c  mov     rdx, rsi
0x18013913f  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x180139144  mov     [rsp+0D0h+var_A8], rcx; struct tagSIZE *
0x180139149  mov     rcx, [rbx+8]
0x18013914d  mov     [rsp+0D0h+var_B0], rax
0x180139152  call    ?PSRotateXpsDrvImageableArea@PSUI@@YA?AW4Enum@ImageableAreaRotationMode@1@PEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_PSDRVEXTRA@@PEAU_INFOHEADER@@PEAU_RECTL@@UtagSIZE@@K@Z; PSUI::PSRotateXpsDrvImageableArea(_OPTSELECT *,_devicemodeW *,_PSDRVEXTRA *,_INFOHEADER *,_RECTL *,tagSIZE,ulong)
0x180139157  cmp     word ptr [rsi+4Ch], 2
0x18013915c  jnz     short loc_180139199
0x18013915e  mov     r9d, [rbp+3Fh+var_80.top]
0x180139162  cmp     eax, 1
0x180139165  jnz     short loc_180139189
0x180139167  mov     ecx, dword ptr [rbp+3Fh+var_60]
0x18013916a  mov     eax, r9d
0x18013916d  sub     eax, dword ptr [rbp+3Fh+var_60+0Ch]
0x180139170  mov     edx, dword ptr [rbp+3Fh+var_60+4]
0x180139173  mov     r8d, dword ptr [rbp+3Fh+var_60+8]
0x180139177  mov     dword ptr [rbp+3Fh+var_60], eax
0x18013917a  mov     eax, r9d
0x18013917d  sub     eax, edx
0x18013917f  mov     dword ptr [rbp+3Fh+var_60+4], ecx
0x180139182  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x180139185  mov     dword ptr [rbp+3Fh+var_60+0Ch], r8d
0x180139189  cmp     r14d, 1
0x18013918d  jz      short loc_180139199
0x18013918f  mov     eax, [rbp+3Fh+var_80.left]
0x180139192  mov     [rbp+3Fh+var_80.left], r9d
0x180139196  mov     [rbp+3Fh+var_80.top], eax
0x180139199  mov     rcx, [rbx+8]; this
0x18013919d  lea     rax, [rbp+3Fh+var_80]
0x1801391a1  lea     r9, [rbp+3Fh+var_60]; struct _INFOHEADER *
0x1801391a5  mov     [rsp+0D0h+var_B0], rax; struct _RECTL *
0x1801391aa  mov     r8, rdi; struct _devicemodeW *
0x1801391ad  mov     rdx, rsi; struct _OPTSELECT *
0x1801391b0  call    ?PSSimulateV3ImageableArea@PSUI@@YAXPEAU_OPTSELECT@@PEAU_devicemodeW@@PEAU_INFOHEADER@@PEAU_RECTL@@PEAUtagSIZE@@@Z; PSUI::PSSimulateV3ImageableArea(_OPTSELECT *,_devicemodeW *,_INFOHEADER *,_RECTL *,tagSIZE *)
0x1801391b5  mov     eax, dword ptr [rbp+3Fh+var_60]
0x1801391b8  mov     r14d, dword ptr [rbp+3Fh+var_60+8]
0x1801391bc  mov     r15d, dword ptr [rbp+3Fh+var_60+0Ch]
0x1801391c0  sub     r14d, eax
0x1801391c3  mov     esi, [rbp+3Fh+var_68]
0x1801391c6  mov     [rbp+3Fh+arg_0], eax
0x1801391c9  mov     eax, dword ptr [rbp+3Fh+var_60+4]
0x1801391cc  sub     r15d, eax
0x1801391cf  mov     [rbp+3Fh+var_80.bottom], eax
0x1801391d2  mov     eax, [rbp+3Fh+var_80.left]
0x1801391d5  mov     [rbp+3Fh+var_70], eax
0x1801391d8  mov     eax, [rbp+3Fh+var_80.top]
0x1801391db  mov     [rbp+3Fh+var_6C], eax
0x1801391de  mov     rcx, rdi
0x1801391e1  call    FreeBinaryData
0x1801391e6  neg     esi
0x1801391e8  mov     ebx, 80004005h
0x1801391ed  sbb     ecx, ecx
0x1801391ef  not     ecx
0x1801391f1  and     ebx, ecx
0x1801391f3  test    ebx, ebx
0x1801391f5  js      short loc_180139224
0x1801391f7  mov     rax, [rbp+3Fh+arg_8]
0x1801391fb  mov     ecx, [rbp+3Fh+arg_0]
0x1801391fe  mov     [rax], ecx
0x180139200  mov     rax, [rbp+3Fh+arg_10]
0x180139204  mov     ecx, [rbp+3Fh+var_80.bottom]
0x180139207  mov     [rax], ecx
0x180139209  mov     rax, [rbp+3Fh+arg_18]
0x18013920d  mov     ecx, [rbp+3Fh+var_6C]
0x180139210  mov     [rax], r14d
0x180139213  mov     eax, [rbp+3Fh+var_70]
0x180139216  mov     [r12], r15d
0x18013921a  mov     [r13+0], eax
0x18013921e  mov     rax, [rbp+3Fh+arg_30]
0x180139222  mov     [rax], ecx
0x180139224  mov     eax, ebx
0x180139226  jmp     short loc_180139234
0x180139228  mov     eax, 8000FFFFh
0x18013922d  jmp     short loc_180139234
0x18013922f  mov     eax, 80004003h
0x180139234  add     rsp, 98h
0x18013923b  pop     r15
0x18013923d  pop     r14
0x18013923f  pop     r13
0x180139241  pop     r12
0x180139243  pop     rdi
0x180139244  pop     rsi
0x180139245  pop     rbx
0x180139246  pop     rbp
0x180139247  retn
```
