# GDIHelpers::AddBackgroundForIcon(HBITMAP__ *,ulong const &,tagSIZE const &,tagSIZE const &,tagSIZE const &,HBITMAP__ * *)

- ea: `0x1800ee8b0`
- end: `0x1800eeb6c`
- name: `?AddBackgroundForIcon@GDIHelpers@@YAJPEAUHBITMAP__@@AEBKAEBUtagSIZE@@22PEAPEAU2@@Z`
- size: `700`
- prototype: `__int64 __usercall@<rax>(HANDLE h@<rcx>, HBITMAP@<rdx>, const unsigned int *@<r8>, const struct tagSIZE *@<r9>, const struct tagSIZE *, const struct tagSIZE *, HBITMAP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006f02c`

## callees

- `0x1800340a0`
- `0x1800ee8b0`
- `0x1800eeb74`
- `0x180119c18`
- `0x18013f7d0`

## import_xrefs

- `GDI32!DeleteDC` at `0x1800eeaab`
- `GDI32!DeleteDC` at `0x1800eeab6`
- `GDI32!DeleteDC` at `0x1800eeb61`
- `GDI32!DeleteDC` at `0x1800eeaab`
- `GDI32!DeleteDC` at `0x1800eeab6`
- `GDI32!DeleteDC` at `0x1800eeb61`
- `GDI32!GdiAlphaBlend` at `0x1800eea83`
- `GDI32!GdiAlphaBlend` at `0x1800eea83`
- `GDI32!SelectObject` at `0x1800ee927`
- `GDI32!SelectObject` at `0x1800ee9b9`
- `GDI32!SelectObject` at `0x1800eea96`
- `GDI32!SelectObject` at `0x1800eeaa2`
- `GDI32!SelectObject` at `0x1800eeb58`
- `GDI32!SelectObject` at `0x1800ee927`
- `GDI32!SelectObject` at `0x1800ee9b9`
- `GDI32!SelectObject` at `0x1800eea96`
- `GDI32!SelectObject` at `0x1800eeaa2`
- `GDI32!SelectObject` at `0x1800eeb58`
- `GDI32!CreateCompatibleDC` at `0x1800ee8f7`
- `GDI32!CreateCompatibleDC` at `0x1800ee90f`
- `GDI32!CreateCompatibleDC` at `0x1800ee8f7`
- `GDI32!CreateCompatibleDC` at `0x1800ee90f`
- `GDI32!GetObjectW` at `0x1800ee946`
- `GDI32!GetObjectW` at `0x1800ee946`
- `GDI32!CreateDIBSection` at `0x1800ee9a1`
- `GDI32!CreateDIBSection` at `0x1800ee9a1`

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
  HDC v10; // rdi
  HDC v11; // rax
  HDC v12; // rbx
  HGDIOBJ v13; // r15
  const char *v14; // r9
  LONG v15; // eax
  HBITMAP v16; // rax
  HBITMAP v17; // rsi
  HGDIOBJ v18; // r14
  int v19; // ecx
  int v20; // eax
  int v21; // r9d
  const struct tagRECT *v22; // r8
  int cy; // r10d
  int cx; // r9d
  unsigned int LastError; // esi
  int hSection; // [rsp+20h] [rbp-C9h]
  unsigned int hSectiona; // [rsp+20h] [rbp-C9h]
  bool offset; // [rsp+28h] [rbp-C1h]
  void *ppvBits; // [rsp+68h] [rbp-81h] BYREF
  const struct tagSIZE *v32; // [rsp+70h] [rbp-79h]
  struct tagSIZE *v33; // [rsp+78h] [rbp-71h]
  _OWORD pv[2]; // [rsp+80h] [rbp-69h] BYREF
  struct HDC__ v35; // [rsp+A0h] [rbp-49h] BYREF
  int v36; // [rsp+A4h] [rbp-45h]
  int v37; // [rsp+A8h] [rbp-41h]
  int v38; // [rsp+ACh] [rbp-3Dh]
  BITMAPINFO pbmi; // [rsp+B0h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]

  v32 = a5;
  v33 = a6;
  CompatibleDC = CreateCompatibleDC(0);
  v10 = CompatibleDC;
  if ( !CompatibleDC )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"shell\\inc\\gdihelpers.h",
      (const char *)0x8007000ELL,
      hSection);
    return LastError;
  }
  v11 = CreateCompatibleDC(CompatibleDC);
  v12 = v11;
  if ( v11 )
  {
    memset(pv, 0, sizeof(pv));
    v13 = SelectObject(v11, h);
    if ( GetObjectW(h, 32, pv) )
    {
      v15 = *a3;
      memset(&pbmi.bmiHeader.biWidth, 0, 40);
      pbmi.bmiHeader.biWidth = v15;
      pbmi.bmiHeader.biHeight = a3[1];
      pbmi.bmiHeader.biSize = 44;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      ppvBits = 0;
      v16 = CreateDIBSection(v10, &pbmi, 0, &ppvBits, 0, 0);
      v17 = v16;
      if ( v16 )
      {
        v18 = SelectObject(v10, v16);
        v35.unused = (*a3 - a4->cx) / 2;
        v19 = a4->cx + v35.unused;
        v36 = (a3[1] - a4->cy) / 2;
        v20 = a4->cy + v36;
        v37 = v19;
        v21 = *a2;
        v38 = v20;
        GDIHelpers::FillRectARGB(v10, &v35, v22, v21, hSectiona, offset);
        cy = DWORD2(pv[0]);
        cx = DWORD1(pv[0]);
        if ( v32->cx < SDWORD1(pv[0]) )
          cx = v32->cx;
        if ( v32->cy < SDWORD2(pv[0]) )
          cy = v32->cy;
        GdiAlphaBlend(
          v10,
          (*a3 - cx) / 2,
          (a3[1] - cy) / 2,
          cx,
          cy,
          v12,
          0,
          0,
          SDWORD1(pv[0]),
          SDWORD2(pv[0]),
          (BLENDFUNCTION)33488896);
        *v33 = (struct tagSIZE)v17;
        SelectObject(v10, v18);
        SelectObject(v12, v13);
        DeleteDC(v12);
        LastError = 0;
        goto LABEL_10;
      }
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18D,
        (unsigned int)"shell\\inc\\gdihelpers.h",
        (const char *)0x8007000ELL,
        hSectiona);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x181,
                    (unsigned int)"shell\\inc\\gdihelpers.h",
                    v14);
    }
    SelectObject(v12, v13);
    DeleteDC(v12);
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"shell\\inc\\gdihelpers.h",
      (const char *)0x8007000ELL,
      hSection);
  }
LABEL_10:
  DeleteDC(v10);
  return LastError;
}

```

## disassembly

```asm
0x1800ee8b0  push    rbp
0x1800ee8b2  push    rbx
0x1800ee8b3  push    rsi
0x1800ee8b4  push    rdi
0x1800ee8b5  push    r12
0x1800ee8b7  push    r13
0x1800ee8b9  push    r14
0x1800ee8bb  push    r15
0x1800ee8bd  lea     rbp, [rsp-0Fh]
0x1800ee8c2  sub     rsp, 0F8h
0x1800ee8c9  mov     rax, cs:__security_cookie
0x1800ee8d0  xor     rax, rsp
0x1800ee8d3  mov     [rbp+47h+var_50], rax
0x1800ee8d7  mov     rax, [rbp+47h+arg_20]
0x1800ee8db  mov     rsi, rcx
0x1800ee8de  mov     [rbp+47h+var_C0], rax
0x1800ee8e2  xor     ecx, ecx; hdc
0x1800ee8e4  mov     rax, [rbp+47h+arg_28]
0x1800ee8e8  mov     r13, r9
0x1800ee8eb  mov     [rbp+47h+var_B8], rax
0x1800ee8ef  mov     r12, r8
0x1800ee8f2  mov     qword ptr [rsp+130h+var_D0.BlendOp], rdx
0x1800ee8f7  call    cs:__imp_CreateCompatibleDC
0x1800ee8fd  xor     r14d, r14d
0x1800ee900  mov     rdi, rax
0x1800ee903  test    rax, rax
0x1800ee906  jz      loc_1800EEADE
0x1800ee90c  mov     rcx, rax; hdc
0x1800ee90f  call    cs:__imp_CreateCompatibleDC
0x1800ee915  mov     rbx, rax
0x1800ee918  test    rax, rax
0x1800ee91b  jz      loc_1800EEAFD
0x1800ee921  mov     rdx, rsi; h
0x1800ee924  mov     rcx, rax; hdc
0x1800ee927  call    cs:__imp_SelectObject
0x1800ee92d  xorps   xmm0, xmm0
0x1800ee930  lea     r8, [rbp+47h+pv]; pv
0x1800ee934  lea     edx, [r14+20h]; c
0x1800ee938  mov     rcx, rsi; h
0x1800ee93b  movups  [rbp+47h+pv], xmm0
0x1800ee93f  mov     r15, rax
0x1800ee942  movups  [rbp+47h+var_A0], xmm0
0x1800ee946  call    cs:__imp_GetObjectW
0x1800ee94c  test    eax, eax
0x1800ee94e  jz      loc_1800EEB1C
0x1800ee954  xor     eax, eax
0x1800ee956  mov     [rsp+130h+offset], r14d; bool
0x1800ee95b  xorps   xmm0, xmm0
0x1800ee95e  mov     qword ptr [rbp+47h+pbmi.bmiHeader.biClrImportant], rax
0x1800ee962  mov     eax, [r12]
0x1800ee966  lea     r9, [rsp+130h+ppvBits]; ppvBits
0x1800ee96b  movups  xmmword ptr [rbp+47h+pbmi.bmiHeader.biWidth], xmm0
0x1800ee96f  mov     [rbp+47h+pbmi.bmiHeader.biWidth], eax
0x1800ee972  lea     rdx, [rbp+47h+pbmi]; pbmi
0x1800ee976  mov     eax, [r12+4]
0x1800ee97b  xor     r8d, r8d; usage
0x1800ee97e  mov     rcx, rdi; hdc
0x1800ee981  mov     [rbp+47h+pbmi.bmiHeader.biHeight], eax
0x1800ee984  mov     [rbp+47h+pbmi.bmiHeader.biSize], 2Ch ; ','
0x1800ee98b  movups  xmmword ptr [rbp+47h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800ee98f  mov     qword ptr [rbp+47h+pbmi.bmiHeader.biPlanes], 200001h
0x1800ee997  mov     [rsp+130h+ppvBits], r14
0x1800ee99c  mov     [rsp+130h+hSection], r14; int
0x1800ee9a1  call    cs:__imp_CreateDIBSection
0x1800ee9a7  mov     rsi, rax
0x1800ee9aa  test    rax, rax
0x1800ee9ad  jz      loc_1800EEB35
0x1800ee9b3  mov     rdx, rax; h
0x1800ee9b6  mov     rcx, rdi; hdc
0x1800ee9b9  call    cs:__imp_SelectObject
0x1800ee9bf  mov     r14, rax
0x1800ee9c2  mov     r9d, 2
0x1800ee9c8  mov     eax, [r12]
0x1800ee9cc  sub     eax, [r13+0]
0x1800ee9d0  cdq
0x1800ee9d1  idiv    r9d
0x1800ee9d4  mov     ecx, eax
0x1800ee9d6  mov     [rbp+47h+var_90.unused], eax
0x1800ee9d9  mov     eax, [r12+4]
0x1800ee9de  sub     eax, [r13+4]
0x1800ee9e2  add     ecx, [r13+0]
0x1800ee9e6  cdq
0x1800ee9e7  idiv    r9d
0x1800ee9ea  mov     r9, qword ptr [rsp+130h+var_D0.BlendOp]
0x1800ee9ef  lea     rdx, [rbp+47h+var_90]; HDC
0x1800ee9f3  mov     [rbp+47h+var_8C], eax
0x1800ee9f6  add     eax, [r13+4]
0x1800ee9fa  mov     [rbp+47h+var_88], ecx
0x1800ee9fd  mov     rcx, rdi; hdc
0x1800eea00  mov     r9d, [r9]; unsigned __int8
0x1800eea03  mov     [rbp+47h+var_84], eax
0x1800eea06  call    ?FillRectARGB@GDIHelpers@@YAXPEAUHDC__@@PEBUtagRECT@@EK_N@Z; GDIHelpers::FillRectARGB(HDC__ *,tagRECT const *,uchar,ulong,bool)
0x1800eea0b  mov     rax, [rbp+47h+var_C0]
0x1800eea0f  mov     r13d, 2
0x1800eea15  mov     ecx, dword ptr [rbp+47h+pv+8]
0x1800eea18  mov     r10d, ecx
0x1800eea1b  mov     r11d, dword ptr [rbp+47h+pv+4]
0x1800eea1f  mov     r9d, r11d
0x1800eea22  mov     dword ptr [rsp+130h+var_D0.BlendOp], 1FF0000h
0x1800eea2a  cmp     [rax], r11d
0x1800eea2d  cmovl   r9d, [rax]; wDest
0x1800eea31  cmp     [rax+4], ecx
0x1800eea34  cmovl   r10d, [rax+4]
0x1800eea39  mov     eax, [r12+4]
0x1800eea3e  sub     eax, r10d
0x1800eea41  cdq
0x1800eea42  idiv    r13d
0x1800eea45  mov     r8d, eax; yoriginDest
0x1800eea48  mov     eax, [r12]
0x1800eea4c  sub     eax, r9d
0x1800eea4f  cdq
0x1800eea50  idiv    r13d
0x1800eea53  mov     edx, eax; xoriginDest
0x1800eea55  mov     eax, dword ptr [rsp+130h+var_D0.BlendOp]
0x1800eea59  mov     dword ptr [rsp+130h+ftn.BlendOp], eax; ftn
0x1800eea5d  mov     [rsp+130h+hSrc], ecx; hSrc
0x1800eea61  mov     rcx, rdi; hdcDest
0x1800eea64  mov     [rsp+130h+wSrc], r11d; wSrc
0x1800eea69  mov     [rsp+130h+yoriginSrc], 0; yoriginSrc
0x1800eea71  mov     [rsp+130h+xoriginSrc], 0; xoriginSrc
0x1800eea79  mov     qword ptr [rsp+130h+offset], rbx; hdcSrc
0x1800eea7e  mov     dword ptr [rsp+130h+hSection], r10d; hDest
0x1800eea83  call    cs:__imp_GdiAlphaBlend
0x1800eea89  mov     rax, [rbp+47h+var_B8]
0x1800eea8d  mov     rdx, r14; h
0x1800eea90  mov     rcx, rdi; hdc
0x1800eea93  mov     [rax], rsi
0x1800eea96  call    cs:__imp_SelectObject
0x1800eea9c  mov     rdx, r15; h
0x1800eea9f  mov     rcx, rbx; hdc
0x1800eeaa2  call    cs:__imp_SelectObject
0x1800eeaa8  mov     rcx, rbx; hdc
0x1800eeaab  call    cs:__imp_DeleteDC
0x1800eeab1  xor     esi, esi
0x1800eeab3  mov     rcx, rdi; hdc
0x1800eeab6  call    cs:__imp_DeleteDC
0x1800eeabc  mov     eax, esi
0x1800eeabe  mov     rcx, [rbp+47h+var_50]
0x1800eeac2  xor     rcx, rsp; StackCookie
0x1800eeac5  call    __security_check_cookie
0x1800eeaca  add     rsp, 0F8h
0x1800eead1  pop     r15
0x1800eead3  pop     r14
0x1800eead5  pop     r13
0x1800eead7  pop     r12
0x1800eead9  pop     rdi
0x1800eeada  pop     rsi
0x1800eeadb  pop     rbx
0x1800eeadc  pop     rbp
0x1800eeadd  retn
0x1800eeade  mov     rcx, [rbp+4Fh]; this
0x1800eeae2  lea     r8, aShellIncGdihel; "shell\\inc\\gdihelpers.h"
0x1800eeae9  mov     esi, 8007000Eh
0x1800eeaee  mov     edx, 178h; void *
0x1800eeaf3  mov     r9d, esi; char *
0x1800eeaf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eeafb  jmp     short loc_1800EEABC
0x1800eeafd  mov     rcx, [rbp+4Fh]; this
0x1800eeb01  lea     r8, aShellIncGdihel; "shell\\inc\\gdihelpers.h"
0x1800eeb08  mov     esi, 8007000Eh
0x1800eeb0d  mov     edx, 17Bh; void *
0x1800eeb12  mov     r9d, esi; char *
0x1800eeb15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eeb1a  jmp     short loc_1800EEAB3
0x1800eeb1c  mov     rcx, [rbp+4Fh]; this
0x1800eeb20  lea     r8, aShellIncGdihel; "shell\\inc\\gdihelpers.h"
0x1800eeb27  mov     edx, 181h; void *
0x1800eeb2c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800eeb31  mov     esi, eax
0x1800eeb33  jmp     short loc_1800EEB52
0x1800eeb35  mov     rcx, [rbp+4Fh]; this
0x1800eeb39  lea     r8, aShellIncGdihel; "shell\\inc\\gdihelpers.h"
0x1800eeb40  mov     esi, 8007000Eh
0x1800eeb45  mov     edx, 18Dh; void *
0x1800eeb4a  mov     r9d, esi; char *
0x1800eeb4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eeb52  mov     rdx, r15; h
0x1800eeb55  mov     rcx, rbx; hdc
0x1800eeb58  call    cs:__imp_SelectObject
0x1800eeb5e  mov     rcx, rbx; hdc
0x1800eeb61  call    cs:__imp_DeleteDC
0x1800eeb67  jmp     loc_1800EEAB3
```
