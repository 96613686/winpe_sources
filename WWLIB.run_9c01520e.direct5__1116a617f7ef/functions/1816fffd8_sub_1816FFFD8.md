# sub_1816FFFD8

- ea: `0x1816fffd8`
- end: `0x1817004a6`
- name: `sub_1816FFFD8`
- size: `1230`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1808e8bcc`

## callees

- `0x18007a080`
- `0x180908e70`
- `0x180908e78`
- `0x18090a640`
- `0x181364b40`
- `0x1816fffd8`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1817003ed`
- `KERNEL32!GlobalUnlock` at `0x1817003ed`
- `KERNEL32!GlobalLock` at `0x181700377`
- `KERNEL32!GlobalLock` at `0x181700377`
- `KERNEL32!GlobalAlloc` at `0x181700361`
- `KERNEL32!GlobalAlloc` at `0x181700361`
- `MSO!MSO_8886` at `0x181700257`
- `MSO!MSO_8886` at `0x181700257`
- `MSO!MSO_19372` at `0x1817002f3`
- `MSO!MSO_19372` at `0x1817002f3`
- `MSO!MSO_38231` at `0x18170030c`
- `MSO!MSO_38231` at `0x18170030c`
- `mso40uiWin32Client!mso40uiWin32Client_24569` at `0x1817003fa`
- `mso40uiWin32Client!mso40uiWin32Client_24569` at `0x1817003fa`
- `mso40uiWin32Client!mso40uiWin32Client_24614` at `0x181700056`
- `mso40uiWin32Client!mso40uiWin32Client_24614` at `0x181700056`
- `mso40uiWin32Client!mso40uiWin32Client_25756` at `0x18170024d`
- `mso40uiWin32Client!mso40uiWin32Client_25756` at `0x18170024d`
- `mso40uiWin32Client!__imp_mso40uiWin32Client_33790` at `0x181700462`
- `mso40uiWin32Client!__imp_mso40uiWin32Client_33790` at `0x181700462`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1817000cc`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1817000cc`
- `Mso20Win32Client!Mso20Win32Client_21639` at `0x181700346`
- `Mso20Win32Client!Mso20Win32Client_21639` at `0x181700346`
- `GDI32!DeleteObject` at `0x181700410`
- `GDI32!DeleteObject` at `0x181700410`
- `GDI32!SelectObject` at `0x1817001f9`
- `GDI32!SelectObject` at `0x181700423`
- `GDI32!SelectObject` at `0x1817001f9`
- `GDI32!SelectObject` at `0x181700423`
- `GDI32!DeleteEnhMetaFile` at `0x181700455`
- `GDI32!DeleteEnhMetaFile` at `0x181700455`
- `GDI32!PatBlt` at `0x18170021c`
- `GDI32!PatBlt` at `0x18170021c`
- `GDI32!DeleteDC` at `0x18170042c`
- `GDI32!DeleteDC` at `0x18170042c`
- `GDI32!GetEnhMetaFileHeader` at `0x1817000bd`
- `GDI32!GetEnhMetaFileHeader` at `0x1817000bd`
- `GDI32!CreateCompatibleDC` at `0x1817001db`
- `GDI32!CreateCompatibleDC` at `0x1817001db`
- `GDI32!CreateDIBSection` at `0x1817001c4`
- `GDI32!CreateDIBSection` at `0x1817001c4`
- `USER32!GetDC` at `0x181700197`
- `USER32!GetDC` at `0x181700197`
- `USER32!ReleaseDC` at `0x181700447`
- `USER32!ReleaseDC` at `0x181700447`

## pseudocode

```c
HGLOBAL __fastcall sub_1816FFFD8(int a1, __int64 a2)
{
  int v4; // edx
  int v5; // r8d
  HGLOBAL v6; // rbx
  HENHMETAFILE v7; // rax
  __int64 v8; // rcx
  HENHMETAFILE v9; // r15
  int v10; // edi
  unsigned int v11; // esi
  int v12; // r13d
  int v13; // r12d
  unsigned int v14; // r14d
  LONG v15; // ebx
  int v16; // eax
  unsigned int v17; // r15d
  HDC v18; // rdi
  HDC CompatibleDC; // rax
  HDC v20; // rdi
  unsigned int v21; // edi
  int v22; // eax
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rax
  unsigned int v30; // esi
  HGLOBAL v31; // rax
  void *v32; // rdi
  char *v33; // rax
  unsigned int v35; // [rsp+48h] [rbp-C0h]
  unsigned int v36; // [rsp+4Ch] [rbp-BCh]
  int v37; // [rsp+50h] [rbp-B8h]
  __int64 v38; // [rsp+58h] [rbp-B0h]
  HENHMETAFILE hmf; // [rsp+60h] [rbp-A8h]
  HGLOBAL v40; // [rsp+68h] [rbp-A0h]
  void *ppvBits; // [rsp+70h] [rbp-98h] BYREF
  HGDIOBJ h; // [rsp+78h] [rbp-90h]
  HGDIOBJ v43; // [rsp+80h] [rbp-88h]
  HDC hDC; // [rsp+88h] [rbp-80h]
  __int128 v45; // [rsp+90h] [rbp-78h] BYREF
  HDC hdc; // [rsp+A0h] [rbp-68h]
  BITMAPINFO pbmi; // [rsp+A8h] [rbp-60h] BYREF
  struct tagENHMETAHEADER EnhMetaHeader; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v49[176]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v50[256]; // [rsp+1F8h] [rbp+F0h] BYREF

  memset(&EnhMetaHeader, 0, sizeof(EnhMetaHeader));
  memset(&pbmi, 0, sizeof(pbmi));
  ppvBits = 0;
  v43 = 0;
  mso40uiWin32Client_24614(v50);
  memset(v49, 0, sizeof(v49));
  v6 = 0;
  v45 = 0;
  v40 = 0;
  if ( !*(_BYTE *)(a2 + 22) || (LOBYTE(v4) = 1, !*(_BYTE *)(a2 + 24)) )
    LOBYTE(v4) = 0;
  LOBYTE(v5) = 1;
  v7 = (HENHMETAFILE)sub_181364B40(a1, v4, v5, 0, 0);
  hmf = v7;
  if ( v7 )
  {
    if ( GetEnhMetaFileHeader(v7, 0x6Cu, &EnhMetaHeader) )
    {
      v10 = EnhMetaHeader.rclBounds.right - EnhMetaHeader.rclBounds.left + 1;
      v11 = EnhMetaHeader.rclBounds.bottom - EnhMetaHeader.rclBounds.top + 1;
      v12 = EnhMetaHeader.rclFrame.right - EnhMetaHeader.rclBounds.left + 1;
      v13 = EnhMetaHeader.rclFrame.bottom - EnhMetaHeader.rclBounds.top + 1;
      v35 = v10;
      if ( v10 > 0 && (int)v11 > 0 && v12 > 0 && v13 > 0 )
      {
        v14 = 44;
        v15 = 250;
        v38 = 0x2C000000FALL;
        v16 = sub_18007A080(44, (unsigned int)v10, v11);
        v17 = v16;
        if ( v16 < 250 )
        {
          v15 = v16;
          LODWORD(v38) = v16;
          v36 = v16;
          v37 = v16;
        }
        else
        {
          v14 = sub_18007A080(250, v11, (unsigned int)v10);
          HIDWORD(v38) = v14;
          v17 = 250;
          v36 = 250;
          v37 = 250;
        }
        pbmi.bmiHeader.biSize = 40;
        pbmi.bmiHeader.biWidth = v15;
        pbmi.bmiHeader.biHeight = v14;
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 1572865;
        hDC = GetDC(0);
        v18 = hDC;
        h = CreateDIBSection(hDC, &pbmi, 0, &ppvBits, 0, 0);
        if ( h )
        {
          CompatibleDC = CreateCompatibleDC(v18);
          hdc = CompatibleDC;
          v20 = CompatibleDC;
          if ( CompatibleDC )
          {
            v43 = SelectObject(CompatibleDC, h);
            PatBlt(v20, 0, 0, v15, v14, 0xF00021u);
            mso40uiWin32Client_25756(v50, v20, 0x800000, 0, 0, 0, 0, 10);
            MSO_8886(v49);
            v21 = 100 * EnhMetaHeader.szlMillimeters.cx;
            v22 = sub_18007A080(
                    (unsigned int)EnhMetaHeader.rclFrame.left,
                    (unsigned int)EnhMetaHeader.szlDevice.cx,
                    (unsigned int)(100 * EnhMetaHeader.szlMillimeters.cx));
            v23 = sub_18007A080(v17, (unsigned int)(v22 - EnhMetaHeader.rclBounds.left), v35);
            v24 = 100 * EnhMetaHeader.szlMillimeters.cy;
            LODWORD(v45) = v23;
            v25 = sub_18007A080(
                    (unsigned int)EnhMetaHeader.rclFrame.top,
                    (unsigned int)EnhMetaHeader.szlDevice.cy,
                    (unsigned int)(100 * EnhMetaHeader.szlMillimeters.cy));
            DWORD1(v45) = sub_18007A080(v14, (unsigned int)(v25 - EnhMetaHeader.rclBounds.top), v11);
            v26 = sub_18007A080((unsigned int)v12, (unsigned int)EnhMetaHeader.szlDevice.cx, v21);
            DWORD2(v45) = sub_18007A080(v36, v26, v35);
            v27 = sub_18007A080((unsigned int)v13, (unsigned int)EnhMetaHeader.szlDevice.cy, v24);
            HIDWORD(v45) = sub_18007A080(v14, v27, v11);
            MSO_19372(&v49[16], &v45, 0);
            v9 = hmf;
            if ( (unsigned int)MSO_38231(v50, v49, hmf) )
            {
              v28 = 4 * v14 * (3 * (v37 + 1) / 4);
              v29 = Mso20Win32Client_21639(1, 32, v28, 0);
              v30 = v29;
              if ( (unsigned int)v29 == v29 )
              {
                v31 = GlobalAlloc(2u, (unsigned int)v29);
                v40 = v31;
                v32 = v31;
                if ( v31 )
                {
                  v33 = (char *)GlobalLock(v31);
                  if ( v33 )
                  {
                    *(_WORD *)v33 = 1;
                    *((_WORD *)v33 + 1) = 0;
                    *((_DWORD *)v33 + 1) = v30 >> 1;
                    *((_WORD *)v33 + 4) = 9;
                    *((_WORD *)v33 + 5) = 4;
                    *(_QWORD *)(v33 + 12) = v38;
                    *((_WORD *)v33 + 10) = 8;
                    *((_WORD *)v33 + 11) = 2;
                    *((_DWORD *)v33 + 6) = v28;
                    *((_WORD *)v33 + 14) = 10;
                    *((_WORD *)v33 + 15) = 0;
                    memcpy(v33 + 32, ppvBits, v28);
                    GlobalUnlock(v32);
                  }
                }
              }
            }
            mso40uiWin32Client_24569(v50);
            v20 = hdc;
          }
          else
          {
            v9 = hmf;
          }
          DeleteObject(h);
          if ( v20 )
          {
            SelectObject(v20, v43);
            DeleteDC(v20);
          }
          v18 = hDC;
        }
        else
        {
          v9 = hmf;
        }
        if ( v18 )
          ReleaseDC(0, v18);
        v6 = v40;
        goto LABEL_31;
      }
      v8 = 1681275191;
    }
    else
    {
      v8 = 1681275190;
    }
    Mso20Win32Client_7228(v8);
    v9 = hmf;
LABEL_31:
    DeleteEnhMetaFile(v9);
  }
  mso40uiWin32Client_33790(v50);
  return v6;
}

```

## disassembly

```asm
0x1816fffd8  mov     rax, rsp
0x1816fffdb  mov     [rax+10h], rbx
0x1816fffdf  mov     [rax+18h], rsi
0x1816fffe3  mov     [rax+20h], rdi
0x1816fffe7  push    rbp
0x1816fffe8  push    r12
0x1816fffea  push    r13
0x1816fffec  push    r14
0x1816fffee  push    r15
0x1816ffff0  lea     rbp, [rax-228h]
0x1816ffff7  sub     rsp, 300h
0x1816ffffe  mov     rax, cs:__security_cookie
0x181700005  xor     rax, rsp
0x181700008  mov     [rbp+220h+var_30], rax
0x18170000f  mov     rdi, rdx
0x181700012  mov     rsi, rcx
0x181700015  mov     r12d, 6Ch ; 'l'
0x18170001b  lea     rcx, [rbp+220h+EnhMetaHeader]; void *
0x18170001f  mov     r8d, r12d; Size
0x181700022  xor     edx, edx; Val
0x181700024  call    memset
0x181700029  xorps   xmm0, xmm0
0x18170002c  lea     rcx, [rbp+220h+var_130]
0x181700033  xor     eax, eax
0x181700035  xor     r14d, r14d
0x181700038  movups  xmmword ptr [rbp+220h+pbmi.bmiHeader.biSize], xmm0
0x18170003c  mov     qword ptr [rbp+220h+pbmi.bmiHeader.biClrUsed], rax
0x181700040  movups  xmmword ptr [rbp+220h+pbmi.bmiHeader.biCompression], xmm0
0x181700044  mov     dword ptr [rbp+220h+pbmi.bmiColors.rgbBlue], eax
0x181700047  mov     [rsp+320h+var_2D0], r14
0x18170004c  mov     [rsp+320h+ppvBits], r14
0x181700051  mov     [rsp+320h+var_2A8], r14
0x181700056  call    cs:mso40uiWin32Client_24614
0x18170005c  xor     edx, edx; Val
0x18170005e  lea     r8d, [r12+44h]; Size
0x181700063  lea     rcx, [rbp+220h+var_1E0]; void *
0x181700067  call    memset
0x18170006c  lea     r15d, [r12-6Bh]
0x181700071  xorps   xmm0, xmm0
0x181700074  mov     ebx, r14d
0x181700077  movups  [rbp+220h+var_298], xmm0
0x18170007b  mov     [rsp+320h+var_2C0], rbx
0x181700080  cmp     [rdi+16h], r14b
0x181700084  jz      short loc_18170008F
0x181700086  mov     dl, r15b
0x181700089  cmp     [rdi+18h], r14b
0x18170008d  jnz     short loc_181700092
0x18170008f  mov     dl, r14b
0x181700092  xor     r9d, r9d
0x181700095  mov     [rsp+320h+hSection], r14
0x18170009a  mov     r8b, r15b
0x18170009d  mov     rcx, rsi
0x1817000a0  call    sub_181364B40
0x1817000a5  mov     [rsp+320h+hmf], rax
0x1817000aa  test    rax, rax
0x1817000ad  jz      loc_18170045B
0x1817000b3  lea     r8, [rbp+220h+EnhMetaHeader]; lpEnhMetaHeader
0x1817000b7  mov     edx, r12d; nSize
0x1817000ba  mov     rcx, rax; hemf
0x1817000bd  call    cs:GetEnhMetaFileHeader
0x1817000c3  test    eax, eax
0x1817000c5  jnz     short loc_1817000DC
0x1817000c7  mov     ecx, 64363936h
0x1817000cc  call    cs:Mso20Win32Client_7228
0x1817000d2  mov     r15, [rsp+320h+hmf]
0x1817000d7  jmp     loc_181700452
0x1817000dc  mov     edi, [rbp+220h+EnhMetaHeader.rclBounds.right]
0x1817000df  sub     edi, [rbp+220h+EnhMetaHeader.rclBounds.left]
0x1817000e2  mov     esi, [rbp+220h+EnhMetaHeader.rclBounds.bottom]
0x1817000e5  inc     edi
0x1817000e7  sub     esi, [rbp+220h+EnhMetaHeader.rclBounds.top]
0x1817000ea  mov     r13d, [rbp+220h+EnhMetaHeader.rclFrame.right]
0x1817000ee  add     esi, r15d
0x1817000f1  sub     r13d, [rbp+220h+EnhMetaHeader.rclBounds.left]
0x1817000f5  mov     r12d, [rbp+220h+EnhMetaHeader.rclFrame.bottom]
0x1817000f9  add     r13d, r15d
0x1817000fc  sub     r12d, [rbp+220h+EnhMetaHeader.rclBounds.top]
0x181700100  add     r12d, r15d
0x181700103  mov     [rsp+320h+var_2E0], edi
0x181700107  test    edi, edi
0x181700109  jle     loc_18170049B
0x18170010f  test    esi, esi
0x181700111  jle     loc_18170049B
0x181700117  test    r13d, r13d
0x18170011a  jle     loc_18170049B
0x181700120  test    r12d, r12d
0x181700123  jle     loc_18170049B
0x181700129  mov     r14d, 2Ch ; ','
0x18170012f  mov     ebx, 0FAh
0x181700134  mov     ecx, r14d
0x181700137  mov     dword ptr [rsp+320h+var_2D0], ebx
0x18170013b  mov     r8d, esi
0x18170013e  mov     dword ptr [rsp+320h+var_2D0+4], r14d
0x181700143  mov     edx, edi
0x181700145  call    sub_18007A080
0x18170014a  mov     r15d, eax
0x18170014d  cmp     eax, ebx
0x18170014f  jl      short loc_181700171
0x181700151  mov     r8d, edi
0x181700154  mov     edx, esi
0x181700156  mov     ecx, ebx
0x181700158  call    sub_18007A080
0x18170015d  mov     r14d, eax
0x181700160  mov     dword ptr [rsp+320h+var_2D0+4], eax
0x181700164  mov     r15d, ebx
0x181700167  mov     [rsp+320h+var_2DC], ebx
0x18170016b  mov     dword ptr [rsp+320h+var_2D8], ebx
0x18170016f  jmp     short loc_18170017F
0x181700171  mov     ebx, eax
0x181700173  mov     dword ptr [rsp+320h+var_2D0], eax
0x181700177  mov     [rsp+320h+var_2DC], eax
0x18170017b  mov     dword ptr [rsp+320h+var_2D8], eax
0x18170017f  xor     ecx, ecx; hWnd
0x181700181  mov     [rbp+220h+pbmi.bmiHeader.biSize], 28h ; '('
0x181700188  mov     [rbp+220h+pbmi.bmiHeader.biWidth], ebx
0x18170018b  mov     [rbp+220h+pbmi.bmiHeader.biHeight], r14d
0x18170018f  mov     qword ptr [rbp+220h+pbmi.bmiHeader.biPlanes], 180001h
0x181700197  call    cs:GetDC
0x18170019d  mov     [rsp+320h+offset], 0; offset
0x1817001a5  lea     r9, [rsp+320h+ppvBits]; ppvBits
0x1817001aa  mov     rcx, rax; hdc
0x1817001ad  mov     [rbp+220h+hDC], rax
0x1817001b1  xor     r8d, r8d; usage
0x1817001b4  mov     [rsp+320h+hSection], 0; hSection
0x1817001bd  lea     rdx, [rbp+220h+pbmi]; pbmi
0x1817001c1  mov     rdi, rax
0x1817001c4  call    cs:CreateDIBSection
0x1817001ca  mov     [rsp+320h+h], rax
0x1817001cf  test    rax, rax
0x1817001d2  jz      loc_181700438
0x1817001d8  mov     rcx, rdi; hdc
0x1817001db  call    cs:CreateCompatibleDC
0x1817001e1  mov     [rbp+220h+hdc], rax
0x1817001e5  mov     rdi, rax
0x1817001e8  test    rax, rax
0x1817001eb  jz      loc_181700406
0x1817001f1  mov     rdx, [rsp+320h+h]; h
0x1817001f6  mov     rcx, rax; hdc
0x1817001f9  call    cs:SelectObject
0x1817001ff  mov     r9d, ebx; w
0x181700202  mov     [rsp+320h+offset], 0F00021h; rop
0x18170020a  xor     r8d, r8d; y
0x18170020d  mov     [rsp+320h+var_2A8], rax
0x181700212  xor     edx, edx; x
0x181700214  mov     dword ptr [rsp+320h+hSection], r14d; h
0x181700219  mov     rcx, rdi; hdc
0x18170021c  call    cs:PatBlt
0x181700222  xor     eax, eax
0x181700224  mov     [rsp+320h+var_2E8], 0Ah
0x18170022c  mov     qword ptr [rsp+320h+var_2F0], rax
0x181700231  lea     rcx, [rbp+220h+var_130]
0x181700238  mov     qword ptr [rsp+320h+offset], rax
0x18170023d  xor     r9d, r9d
0x181700240  mov     r8d, 800000h
0x181700246  mov     dword ptr [rsp+320h+hSection], eax
0x18170024a  mov     rdx, rdi
0x18170024d  call    cs:mso40uiWin32Client_25756
0x181700253  lea     rcx, [rbp+220h+var_1E0]
0x181700257  call    cs:MSO_8886
0x18170025d  imul    edi, [rbp+220h+EnhMetaHeader.szlMillimeters.cx], 64h ; 'd'
0x181700261  mov     edx, [rbp+220h+EnhMetaHeader.szlDevice.cx]
0x181700264  mov     ecx, [rbp+220h+EnhMetaHeader.rclFrame.left]
0x181700267  mov     r8d, edi
0x18170026a  call    sub_18007A080
0x18170026f  sub     eax, [rbp+220h+EnhMetaHeader.rclBounds.left]
0x181700272  mov     ecx, r15d
0x181700275  mov     r8d, [rsp+320h+var_2E0]
0x18170027a  mov     edx, eax
0x18170027c  call    sub_18007A080
0x181700281  imul    ebx, [rbp+220h+EnhMetaHeader.szlMillimeters.cy], 64h ; 'd'
0x181700285  mov     edx, [rbp+220h+EnhMetaHeader.szlDevice.cy]
0x181700288  mov     ecx, [rbp+220h+EnhMetaHeader.rclFrame.top]
0x18170028b  mov     dword ptr [rbp+220h+var_298], eax
0x18170028e  mov     r8d, ebx
0x181700291  call    sub_18007A080
0x181700296  sub     eax, [rbp+220h+EnhMetaHeader.rclBounds.top]
0x181700299  mov     r8d, esi
0x18170029c  mov     edx, eax
0x18170029e  mov     ecx, r14d
0x1817002a1  call    sub_18007A080
0x1817002a6  mov     edx, [rbp+220h+EnhMetaHeader.szlDevice.cx]
0x1817002a9  mov     ecx, r13d
0x1817002ac  mov     r8d, edi
0x1817002af  mov     dword ptr [rbp+220h+var_298+4], eax
0x1817002b2  call    sub_18007A080
0x1817002b7  mov     ecx, [rsp+320h+var_2DC]
0x1817002bb  mov     edx, eax
0x1817002bd  mov     r8d, [rsp+320h+var_2E0]
0x1817002c2  call    sub_18007A080
0x1817002c7  mov     edx, [rbp+220h+EnhMetaHeader.szlDevice.cy]
0x1817002ca  mov     ecx, r12d
0x1817002cd  mov     r8d, ebx
0x1817002d0  mov     dword ptr [rbp+220h+var_298+8], eax
0x1817002d3  call    sub_18007A080
0x1817002d8  mov     edx, eax
0x1817002da  mov     ecx, r14d
0x1817002dd  mov     r8d, esi
0x1817002e0  call    sub_18007A080
0x1817002e5  lea     rdx, [rbp+220h+var_298]
0x1817002e9  mov     dword ptr [rbp+220h+var_298+0Ch], eax
0x1817002ec  lea     rcx, [rbp+220h+var_1D0]
0x1817002f0  xor     r8d, r8d
0x1817002f3  call    cs:MSO_19372
0x1817002f9  mov     r15, [rsp+320h+hmf]
0x1817002fe  lea     rdx, [rbp+220h+var_1E0]
0x181700302  mov     r8, r15
0x181700305  lea     rcx, [rbp+220h+var_130]
0x18170030c  call    cs:MSO_38231
0x181700312  xor     r12d, r12d
0x181700315  test    eax, eax
0x181700317  jz      loc_1817003F3
0x18170031d  mov     eax, dword ptr [rsp+320h+var_2D8]
0x181700321  lea     ecx, [r12+4]
0x181700326  inc     eax
0x181700328  xor     r9d, r9d
0x18170032b  lea     eax, [rax+rax*2]
0x18170032e  cdq
0x18170032f  idiv    ecx
0x181700331  lea     edx, [rcx+1Ch]
0x181700334  mov     ebx, eax
0x181700336  imul    ebx, r14d
0x18170033a  lea     ecx, [rdx-1Fh]
0x18170033d  shl     ebx, 2
0x181700340  mov     r8d, ebx
0x181700343  mov     r14d, ebx
0x181700346  call    cs:Mso20Win32Client_21639
0x18170034c  mov     esi, eax
0x18170034e  cmp     rsi, rax
0x181700351  jnz     loc_1817003F3
0x181700357  lea     r13d, [r12+2]
0x18170035c  mov     edx, esi; dwBytes
0x18170035e  mov     ecx, r13d; uFlags
0x181700361  call    cs:GlobalAlloc
0x181700367  mov     [rsp+320h+var_2C0], rax
0x18170036c  mov     rdi, rax
0x18170036f  test    rax, rax
0x181700372  jz      short loc_1817003F3
0x181700374  mov     rcx, rax; hMem
0x181700377  call    cs:GlobalLock
0x18170037d  mov     rcx, rax
0x181700380  test    rax, rax
0x181700383  jz      short loc_1817003F3
0x181700385  mov     word ptr [rax], 1
0x18170038a  lea     edx, [r12+4]
0x18170038f  mov     rax, [rsp+320h+var_2D0]
0x181700394  add     rcx, r13
0x181700397  shr     esi, 1
0x181700399  mov     r8d, r14d; Size
0x18170039c  mov     [rcx], r12w
0x1817003a0  add     rcx, r13
0x1817003a3  mov     [rcx], esi
0x1817003a5  add     rcx, rdx
0x1817003a8  mov     word ptr [rcx], 9
0x1817003ad  add     rcx, r13
0x1817003b0  mov     [rcx], dx
0x1817003b3  add     rcx, r13
0x1817003b6  mov     [rcx], rax
0x1817003b9  lea     eax, [rdx+4]
0x1817003bc  add     rcx, rax
0x1817003bf  mov     [rcx], ax
0x1817003c2  add     rcx, r13
0x1817003c5  mov     [rcx], r13w
0x1817003c9  add     rcx, r13
0x1817003cc  mov     [rcx], ebx
0x1817003ce  add     rcx, rdx
0x1817003d1  mov     word ptr [rcx], 0Ah
0x1817003d6  add     rcx, r13
0x1817003d9  mov     [rcx], r12w
0x1817003dd  add     rcx, r13; void *
0x1817003e0  mov     rdx, [rsp+320h+ppvBits]; Src
0x1817003e5  call    memcpy
0x1817003ea  mov     rcx, rdi; hMem
0x1817003ed  call    cs:GlobalUnlock
0x1817003f3  lea     rcx, [rbp+220h+var_130]
0x1817003fa  call    cs:mso40uiWin32Client_24569
0x181700400  mov     rdi, [rbp+220h+hdc]
0x181700404  jmp     short loc_18170040B
0x181700406  mov     r15, [rsp+320h+hmf]
0x18170040b  mov     rcx, [rsp+320h+h]; ho
0x181700410  call    cs:DeleteObject
0x181700416  test    rdi, rdi
0x181700419  jz      short loc_181700432
0x18170041b  mov     rdx, [rsp+320h+var_2A8]; h
0x181700420  mov     rcx, rdi; hdc
0x181700423  call    cs:SelectObject
0x181700429  mov     rcx, rdi; hdc
0x18170042c  call    cs:DeleteDC
0x181700432  mov     rdi, [rbp+220h+hDC]
0x181700436  jmp     short loc_18170043D
0x181700438  mov     r15, [rsp+320h+hmf]
0x18170043d  test    rdi, rdi
0x181700440  jz      short loc_18170044D
0x181700442  mov     rdx, rdi; hDC
0x181700445  xor     ecx, ecx; hWnd
0x181700447  call    cs:ReleaseDC
0x18170044d  mov     rbx, [rsp+320h+var_2C0]
0x181700452  mov     rcx, r15; hmf
0x181700455  call    cs:DeleteEnhMetaFile
0x18170045b  lea     rcx, [rbp+220h+var_130]
0x181700462  call    cs:__imp_mso40uiWin32Client_33790
  ... truncated ...
```
