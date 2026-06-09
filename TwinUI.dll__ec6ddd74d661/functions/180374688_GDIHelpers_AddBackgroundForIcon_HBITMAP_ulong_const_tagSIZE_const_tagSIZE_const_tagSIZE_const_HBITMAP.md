# GDIHelpers::AddBackgroundForIcon(HBITMAP__ *,ulong const &,tagSIZE const &,tagSIZE const &,tagSIZE const &,HBITMAP__ * *)

- ea: `0x180374688`
- end: `0x180374973`
- name: `?AddBackgroundForIcon@GDIHelpers@@YAJPEAUHBITMAP__@@AEBKAEBUtagSIZE@@22PEAPEAU2@@Z`
- size: `747`
- prototype: `__int64 __usercall@<rax>(HANDLE h@<rcx>, HBITMAP@<rdx>, const unsigned int *@<r8>, const struct tagSIZE *@<r9>, const struct tagSIZE *, const struct tagSIZE *, HBITMAP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180374b9c`

## callees

- `0x1800378dc`
- `0x1800bf908`
- `0x1800f1a00`
- `0x1800f82ec`
- `0x18010c930`
- `0x18010e6e8`
- `0x180142e10`
- `0x180374688`

## import_xrefs

- `GDI32!GdiAlphaBlend` at `0x1803748f9`
- `GDI32!GdiAlphaBlend` at `0x1803748f9`
- `GDI32!GetObjectW` at `0x180374760`
- `GDI32!GetObjectW` at `0x180374760`
- `GDI32!CreateCompatibleDC` at `0x1803746ca`
- `GDI32!CreateCompatibleDC` at `0x180374703`
- `GDI32!CreateCompatibleDC` at `0x1803746ca`
- `GDI32!CreateCompatibleDC` at `0x180374703`
- `GDI32!DeleteDC` at `0x180374796`
- `GDI32!DeleteDC` at `0x180374932`
- `GDI32!DeleteDC` at `0x180374944`
- `GDI32!DeleteDC` at `0x180374796`
- `GDI32!DeleteDC` at `0x180374932`
- `GDI32!DeleteDC` at `0x180374944`
- `GDI32!CreateDIBSection` at `0x1803747f1`
- `GDI32!CreateDIBSection` at `0x1803747f1`

## pseudocode

```c
__int64 __fastcall GDIHelpers::AddBackgroundForIcon(
        HANDLE h,
        int *a2,
        LONG *a3,
        const struct tagSIZE *a4,
        const struct tagSIZE *a5,
        struct tagSIZE *a6)
{
  HDC CompatibleDC; // rax
  HDC v11; // rdi
  unsigned int LastError; // esi
  HDC v13; // rax
  HDC v14; // rbx
  const char *v15; // r9
  LONG v16; // eax
  LONG v17; // eax
  HBITMAP v18; // rax
  HBITMAP v19; // rsi
  int v20; // ecx
  int v21; // r9d
  int v22; // eax
  const struct tagRECT *v23; // r8
  LONG cy; // r10d
  LONG cx; // r9d
  unsigned int v26; // eax
  bool v27; // cc
  int hSection; // [rsp+20h] [rbp-E0h]
  unsigned int hSectiona; // [rsp+20h] [rbp-E0h]
  bool offset; // [rsp+28h] [rbp-D8h]
  BLENDFUNCTION ftn[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *ppvBits; // [rsp+68h] [rbp-98h] BYREF
  struct tagSIZE *v34; // [rsp+70h] [rbp-90h]
  _BYTE v35[16]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD pv[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v37[16]; // [rsp+A8h] [rbp-58h] BYREF
  struct HDC__ v38; // [rsp+B8h] [rbp-48h] BYREF
  int v39; // [rsp+BCh] [rbp-44h]
  int v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C4h] [rbp-3Ch]
  BITMAPINFO pbmi; // [rsp+C8h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v34 = a6;
  CompatibleDC = CreateCompatibleDC(0);
  v11 = CompatibleDC;
  if ( CompatibleDC )
  {
    v13 = CreateCompatibleDC(CompatibleDC);
    v14 = v13;
    if ( v13 )
    {
      Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::AutoSelectObject<HBITMAP__ *>(v35, v13, h);
      memset(pv, 0, sizeof(pv));
      if ( GetObjectW(h, 32, pv) )
      {
        v16 = *a3;
        memset(&pbmi.bmiHeader.biWidth, 0, 40);
        pbmi.bmiHeader.biWidth = v16;
        v17 = a3[1];
        ppvBits = 0;
        pbmi.bmiHeader.biHeight = v17;
        pbmi.bmiHeader.biSize = 44;
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
        v18 = CreateDIBSection(v11, &pbmi, 0, &ppvBits, 0, 0);
        *(_QWORD *)&ftn[0].BlendOp = v18;
        v19 = v18;
        if ( v18 )
        {
          Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::AutoSelectObject<HBITMAP__ *>(v37, v11, v18);
          v38.unused = (*a3 - a4->cx) / 2;
          v20 = a4->cx + v38.unused;
          v21 = *a2;
          v39 = (a3[1] - a4->cy) / 2;
          v22 = a4->cy + v39;
          v40 = v20;
          v41 = v22;
          GDIHelpers::FillRectARGB(v11, &v38, v23, v21, hSectiona, offset);
          cy = DWORD2(pv[0]);
          cx = DWORD1(pv[0]);
          v26 = a3[1];
          if ( a5->cx < SDWORD1(pv[0]) )
            cx = a5->cx;
          v27 = a5->cy < SDWORD2(pv[0]);
          ftn[0] = (BLENDFUNCTION)33488896;
          if ( v27 )
            cy = a5->cy;
          GdiAlphaBlend(
            v11,
            (*a3 - cx) / 2,
            (int)(v26 - cy) / 2,
            cx,
            cy,
            v14,
            0,
            0,
            SDWORD1(pv[0]),
            SDWORD2(pv[0]),
            ftn[0]);
          *(_QWORD *)&ftn[0].BlendOp = 0;
          *v34 = (struct tagSIZE)v19;
          Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(v37);
          CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(ftn);
          Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(v35);
          DeleteDC(v14);
          LastError = 0;
          goto LABEL_15;
        }
        LastError = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18D,
          (unsigned int)"shell\\inc\\GDIHelpers.h",
          (const char *)0x8007000ELL,
          hSectiona);
        CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(ftn);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x181,
                      (unsigned int)"shell\\inc\\GDIHelpers.h",
                      v15);
      }
      Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(v35);
      DeleteDC(v14);
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"shell\\inc\\GDIHelpers.h",
        (const char *)0x8007000ELL,
        hSection);
    }
LABEL_15:
    DeleteDC(v11);
    return LastError;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x178,
    (unsigned int)"shell\\inc\\GDIHelpers.h",
    (const char *)0x8007000ELL,
    hSection);
  return LastError;
}

```

## disassembly

```asm
0x180374688  push    rbp
0x18037468a  push    rbx
0x18037468b  push    rsi
0x18037468c  push    rdi
0x18037468d  push    r12
0x18037468f  push    r13
0x180374691  push    r14
0x180374693  push    r15
0x180374695  lea     rbp, [rsp-8]
0x18037469a  sub     rsp, 108h
0x1803746a1  mov     rax, cs:__security_cookie
0x1803746a8  xor     rax, rsp
0x1803746ab  mov     [rbp+40h+var_48], rax
0x1803746af  mov     rax, [rbp+40h+arg_28]
0x1803746b3  mov     rsi, rcx
0x1803746b6  mov     r12, [rbp+40h+arg_20]
0x1803746ba  xor     ecx, ecx; hdc
0x1803746bc  mov     [rsp+140h+var_D0], rax
0x1803746c1  mov     r15, r9
0x1803746c4  mov     r14, r8
0x1803746c7  mov     r13, rdx
0x1803746ca  call    cs:__imp_CreateCompatibleDC
0x1803746d1  nop     dword ptr [rax+rax+00h]
0x1803746d6  mov     rdi, rax
0x1803746d9  test    rax, rax
0x1803746dc  jnz     short loc_180374700
0x1803746de  mov     rcx, [rbp+48h]; this
0x1803746e2  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x1803746e9  mov     esi, 8007000Eh
0x1803746ee  mov     edx, 178h; void *
0x1803746f3  mov     r9d, esi; char *
0x1803746f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803746fb  jmp     loc_180374950
0x180374700  mov     rcx, rdi; hdc
0x180374703  call    cs:__imp_CreateCompatibleDC
0x18037470a  nop     dword ptr [rax+rax+00h]
0x18037470f  mov     rbx, rax
0x180374712  test    rax, rax
0x180374715  jnz     short loc_180374739
0x180374717  mov     rcx, [rbp+48h]; this
0x18037471b  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x180374722  mov     esi, 8007000Eh
0x180374727  mov     edx, 17Bh; void *
0x18037472c  mov     r9d, esi; char *
0x18037472f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180374734  jmp     loc_180374941
0x180374739  mov     r8, rsi
0x18037473c  lea     rcx, [rsp+140h+var_C8]
0x180374741  mov     rdx, rbx
0x180374744  call    ??0?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@PEAUHDC__@@PEAUHBITMAP__@@@Z; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::AutoSelectObject<HBITMAP__ *>(HDC__ *,HBITMAP__ *)
0x180374749  xorps   xmm0, xmm0
0x18037474c  lea     r8, [rbp+40h+pv]; pv
0x180374750  mov     edx, 20h ; ' '; c
0x180374755  mov     rcx, rsi; h
0x180374758  movups  [rbp+40h+pv], xmm0
0x18037475c  movups  [rbp+40h+var_A8], xmm0
0x180374760  call    cs:__imp_GetObjectW
0x180374767  nop     dword ptr [rax+rax+00h]
0x18037476c  xor     ecx, ecx
0x18037476e  test    eax, eax
0x180374770  jnz     short loc_1803747A7
0x180374772  mov     rcx, [rbp+48h]; this
0x180374776  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18037477d  mov     edx, 181h; void *
0x180374782  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180374787  mov     esi, eax
0x180374789  lea     rcx, [rsp+140h+var_C8]
0x18037478e  call    ??1?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(void)
0x180374793  mov     rcx, rbx; hdc
0x180374796  call    cs:__imp_DeleteDC
0x18037479d  nop     dword ptr [rax+rax+00h]
0x1803747a2  jmp     loc_180374941
0x1803747a7  xor     eax, eax
0x1803747a9  mov     [rsp+140h+offset], ecx; bool
0x1803747ad  xorps   xmm0, xmm0
0x1803747b0  mov     qword ptr [rbp+40h+pbmi.bmiHeader.biClrImportant], rax
0x1803747b4  mov     eax, [r14]
0x1803747b7  lea     r9, [rsp+140h+ppvBits]; ppvBits
0x1803747bc  movups  xmmword ptr [rbp+40h+pbmi.bmiHeader.biWidth], xmm0
0x1803747c0  mov     [rbp+40h+pbmi.bmiHeader.biWidth], eax
0x1803747c3  lea     rdx, [rbp+40h+pbmi]; pbmi
0x1803747c7  mov     eax, [r14+4]
0x1803747cb  xor     r8d, r8d; usage
0x1803747ce  mov     [rsp+140h+ppvBits], rcx
0x1803747d3  mov     [rsp+140h+hSection], rcx; unsigned int
0x1803747d8  mov     rcx, rdi; hdc
0x1803747db  mov     [rbp+40h+pbmi.bmiHeader.biHeight], eax
0x1803747de  mov     [rbp+40h+pbmi.bmiHeader.biSize], 2Ch ; ','
0x1803747e5  movups  xmmword ptr [rbp+40h+pbmi.bmiHeader.biSizeImage], xmm0
0x1803747e9  mov     qword ptr [rbp+40h+pbmi.bmiHeader.biPlanes], 200001h
0x1803747f1  call    cs:__imp_CreateDIBSection
0x1803747f8  nop     dword ptr [rax+rax+00h]
0x1803747fd  mov     qword ptr [rsp+140h+var_E0.BlendOp], rax
0x180374802  mov     rsi, rax
0x180374805  test    rax, rax
0x180374808  jnz     short loc_180374836
0x18037480a  mov     rcx, [rbp+48h]; this
0x18037480e  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x180374815  mov     esi, 8007000Eh
0x18037481a  mov     edx, 18Dh; void *
0x18037481f  mov     r9d, esi; char *
0x180374822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180374827  lea     rcx, [rsp+140h+var_E0]
0x18037482c  call    ?Release@?$CTSmartObj@PEAUHFONT__@@V?$CAutoHandle_Policy@PEAUHFONT__@@@@@@QEAAXXZ; CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(void)
0x180374831  jmp     loc_180374789
0x180374836  mov     r8, rsi
0x180374839  lea     rcx, [rbp+40h+var_98]
0x18037483d  mov     rdx, rdi
0x180374840  call    ??0?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@PEAUHDC__@@PEAUHBITMAP__@@@Z; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::AutoSelectObject<HBITMAP__ *>(HDC__ *,HBITMAP__ *)
0x180374845  mov     eax, [r14]
0x180374848  mov     r9d, 2
0x18037484e  sub     eax, [r15]
0x180374851  cdq
0x180374852  idiv    r9d
0x180374855  mov     ecx, eax
0x180374857  mov     [rbp+40h+var_88.unused], eax
0x18037485a  mov     eax, [r14+4]
0x18037485e  sub     eax, [r15+4]
0x180374862  add     ecx, [r15]
0x180374865  cdq
0x180374866  idiv    r9d
0x180374869  mov     r9d, [r13+0]; unsigned __int8
0x18037486d  lea     rdx, [rbp+40h+var_88]; HDC
0x180374871  mov     [rbp+40h+var_84], eax
0x180374874  add     eax, [r15+4]
0x180374878  mov     [rbp+40h+var_80], ecx
0x18037487b  mov     rcx, rdi; hdc
0x18037487e  mov     [rbp+40h+var_7C], eax
0x180374881  call    ?FillRectARGB@GDIHelpers@@YAXPEAUHDC__@@PEBUtagRECT@@EK_N@Z; GDIHelpers::FillRectARGB(HDC__ *,tagRECT const *,uchar,ulong,bool)
0x180374886  mov     ecx, dword ptr [rbp+40h+pv+8]
0x180374889  mov     r10d, ecx
0x18037488c  mov     r11d, dword ptr [rbp+40h+pv+4]
0x180374890  mov     r9d, r11d
0x180374893  cmp     [r12], r11d
0x180374897  mov     eax, [r14+4]
0x18037489b  cmovl   r9d, [r12]; wDest
0x1803748a0  cmp     [r12+4], ecx
0x1803748a5  mov     dword ptr [rsp+140h+var_E0.BlendOp], 1FF0000h
0x1803748ad  cmovl   r10d, [r12+4]
0x1803748b3  xor     r12d, r12d
0x1803748b6  sub     eax, r10d
0x1803748b9  cdq
0x1803748ba  lea     r15d, [r12+2]
0x1803748bf  idiv    r15d
0x1803748c2  mov     r8d, eax; yoriginDest
0x1803748c5  mov     eax, [r14]
0x1803748c8  sub     eax, r9d
0x1803748cb  cdq
0x1803748cc  idiv    r15d
0x1803748cf  mov     edx, eax; xoriginDest
0x1803748d1  mov     eax, dword ptr [rsp+140h+var_E0.BlendOp]
0x1803748d5  mov     dword ptr [rsp+140h+ftn.BlendOp], eax; ftn
0x1803748d9  mov     [rsp+140h+hSrc], ecx; hSrc
0x1803748dd  mov     rcx, rdi; hdcDest
0x1803748e0  mov     [rsp+140h+wSrc], r11d; wSrc
0x1803748e5  mov     [rsp+140h+yoriginSrc], r12d; yoriginSrc
0x1803748ea  mov     [rsp+140h+xoriginSrc], r12d; xoriginSrc
0x1803748ef  mov     qword ptr [rsp+140h+offset], rbx; hdcSrc
0x1803748f4  mov     dword ptr [rsp+140h+hSection], r10d; hDest
0x1803748f9  call    cs:__imp_GdiAlphaBlend
0x180374900  nop     dword ptr [rax+rax+00h]
0x180374905  mov     rax, [rsp+140h+var_D0]
0x18037490a  lea     rcx, [rbp+40h+var_98]
0x18037490e  mov     qword ptr [rsp+140h+var_E0.BlendOp], r12
0x180374913  mov     [rax], rsi
0x180374916  call    ??1?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(void)
0x18037491b  lea     rcx, [rsp+140h+var_E0]
0x180374920  call    ?Release@?$CTSmartObj@PEAUHFONT__@@V?$CAutoHandle_Policy@PEAUHFONT__@@@@@@QEAAXXZ; CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(void)
0x180374925  lea     rcx, [rsp+140h+var_C8]
0x18037492a  call    ??1?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(void)
0x18037492f  mov     rcx, rbx; hdc
0x180374932  call    cs:__imp_DeleteDC
0x180374939  nop     dword ptr [rax+rax+00h]
0x18037493e  mov     esi, r12d
0x180374941  mov     rcx, rdi; hdc
0x180374944  call    cs:__imp_DeleteDC
0x18037494b  nop     dword ptr [rax+rax+00h]
0x180374950  mov     eax, esi
0x180374952  mov     rcx, [rbp+40h+var_48]
0x180374956  xor     rcx, rsp; StackCookie
0x180374959  call    __security_check_cookie
0x18037495e  add     rsp, 108h
0x180374965  pop     r15
0x180374967  pop     r14
0x180374969  pop     r13
0x18037496b  pop     r12
0x18037496d  pop     rdi
0x18037496e  pop     rsi
0x18037496f  pop     rbx
0x180374970  pop     rbp
0x180374971  retn
```
