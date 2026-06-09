# GEL::ITech::PrepareImageForRendering(GEL::Image const &,Math::TRect<double> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> &,Gfx::RenderingPolicySet const &,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &,bool,bool,bool)

- ea: `0x1800d2150`
- end: `0x1800d2afd`
- name: `?PrepareImageForRendering@ITech@GEL@@SA?AV?$TCntPtr@$$CBUIImage@GEL@@@Ofc@@AEBVImage@2@AEBU?$TRect@N@Math@@AEAU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@7@AEBVRenderingPolicySet@Gfx@@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@7@_N55@Z`
- size: `2477`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config`

## callers

- `0x1800d1020`

## callees

- `0x180009ee4`
- `0x180018b30`
- `0x18001bf60`
- `0x18001ec50`
- `0x180020198`
- `0x180025200`
- `0x180025360`
- `0x1800503b0`
- `0x180057e70`
- `0x18006eed0`
- `0x18007f438`
- `0x180090490`
- `0x180092a58`
- `0x1800d0a70`
- `0x1800d1b50`
- `0x1800d2150`
- `0x1800d2b00`
- `0x1800d2d90`
- `0x1800d2dd0`
- `0x1800d3490`
- `0x1800dcec0`
- `0x1800dfdc0`
- `0x1800e10e8`
- `0x18016e194`
- `0x180186470`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800d2a66`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800d2ad6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800d2a66`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800d2ad6`
- `GDI32!DeleteObject` at `0x1800d26db`
- `GDI32!DeleteObject` at `0x1800d27ab`
- `GDI32!DeleteObject` at `0x1800d26db`
- `GDI32!DeleteObject` at `0x1800d27ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
const struct GEL::IImage **__fastcall GEL::ITech::PrepareImageForRendering(
        const struct GEL::IImage **a1,
        const struct GEL::IImage *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        __int64 *a6,
        __int64 a7,
        char a8,
        char a9)
{
  int v9; // edi
  _QWORD *v10; // rsi
  char v15; // r15
  __int64 v16; // rdx
  int v17; // eax
  char v18; // cl
  double Height; // xmm0_8
  int v20; // ebx
  __int64 v21; // rdx
  double Width; // xmm0_8
  double *Size; // rax
  HDC v24; // rdx
  double v25; // xmm6_8
  double v26; // xmm1_8
  int v27; // esi
  double v28; // xmm2_8
  int v29; // ecx
  const struct GEL::IImage *v30; // rbx
  unsigned __int8 *v31; // rsi
  __int64 v32; // r15
  __int64 v33; // rdx
  __int64 v34; // rax
  const struct GEL::IImage **v35; // rax
  double v36; // xmm1_8
  double v37; // xmm0_8
  __int64 v39; // r13
  unsigned int v40; // r8d
  unsigned __int8 *v41; // r15
  unsigned __int128 v42; // rax
  HDC v43; // rdx
  char *v44; // rsi
  unsigned int v45; // edi
  unsigned __int8 *v46; // r10
  _BYTE *v47; // r14
  __int64 v48; // r15
  __int64 v49; // r13
  int v50; // r11d
  int v51; // r9d
  unsigned int v52; // eax
  unsigned int v53; // ecx
  double v54; // xmm1_8
  double v55; // xmm0_8
  int v56; // edi
  int v57; // eax
  void *v58; // rsi
  const struct GEL::IImage **v59; // rax
  const struct GEL::IImage *v60; // rcx
  int v61; // edx
  int v62; // r8d
  int v63; // r10d
  int v64; // ecx
  int v65; // r11d
  __int64 v66; // rdx
  __int64 v67; // r8
  _BYTE *v68; // r9
  unsigned int v69; // eax
  unsigned int v70; // r10d
  unsigned int v71; // r11d
  char *v72; // r15
  __int64 v73; // r13
  double v74; // xmm7_8
  double v75; // xmm6_8
  double v76; // xmm1_8
  struct ARC::IFactory *BestFactoryForBitmapTarget; // [rsp+20h] [rbp-148h]
  unsigned int v78; // [rsp+28h] [rbp-140h]
  unsigned int v79; // [rsp+28h] [rbp-140h]
  HPALETTE v80; // [rsp+30h] [rbp-138h]
  HPALETTE v81; // [rsp+30h] [rbp-138h]
  char v82; // [rsp+40h] [rbp-128h]
  unsigned __int8 v83; // [rsp+40h] [rbp-128h]
  int v84; // [rsp+48h] [rbp-120h] BYREF
  int v85; // [rsp+4Ch] [rbp-11Ch]
  __int64 v86; // [rsp+50h] [rbp-118h] BYREF
  unsigned int v87; // [rsp+58h] [rbp-110h]
  unsigned __int8 *v88; // [rsp+60h] [rbp-108h] BYREF
  HGDIOBJ v89[2]; // [rsp+68h] [rbp-100h] BYREF
  HGDIOBJ ho[2]; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v91; // [rsp+88h] [rbp-E0h]
  int *v92; // [rsp+90h] [rbp-D8h]
  __int64 v93; // [rsp+98h] [rbp-D0h]
  void *v94; // [rsp+A0h] [rbp-C8h]
  const struct GEL::IImage *v95; // [rsp+B0h] [rbp-B8h]
  void *v96; // [rsp+B8h] [rbp-B0h]
  _BYTE v97[40]; // [rsp+C0h] [rbp-A8h] BYREF
  _QWORD *v98; // [rsp+E8h] [rbp-80h]
  char v101; // [rsp+1A0h] [rbp+38h]
  unsigned __int8 v102; // [rsp+1A0h] [rbp+38h]

  v15 = 0;
  if ( !GEL::Image::IsRaster(a2) && !GEL::Image::SupportsRenderingMethod(a2, 2u) )
  {
    GEL::AccessImageResource::AccessImageResource((GEL::AccessImageResource *)v97, a2, 0);
    if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v98 + 8LL))(v98) )
    {
      v10 = v98;
      if ( v98 )
        _castguard_slow_path_check_user_handled(*v98, 73968, 0);
      else
        v10 = 0;
      v9 = *((_DWORD *)v10 + 25);
      v87 = v9 & 0xFFFCDFED;
      v17 = 512;
      if ( v9 != 512 )
      {
LABEL_7:
        v101 = 0;
LABEL_8:
        if ( (v9 & v17) != 0 || (v18 = 1, (v9 & 0x80000) == 0) )
          v18 = 0;
        if ( v18 || (v9 & 0x40000) != 0 )
          v15 = 1;
        v82 = v15;
        Height = Math::TRect<double>::GetHeight(a3, v16);
        v20 = (int)ceil_0(Height);
        Width = Math::TRect<double>::GetWidth(a3, v21);
        v84 = (int)ceil_0(Width);
        v85 = v20;
        Size = (double *)Math::TRect<Math::TUnits<double,Math::DevicePixels>>::GetSize(a4, ho);
        v25 = *((float *)v10 + 24) * Size[1];
        v26 = *((float *)v10 + 23) * *Size;
        v27 = v84;
        v28 = (double)v84;
        if ( v26 > (double)v84 )
        {
          v29 = v85;
        }
        else
        {
          v29 = v85;
          if ( v25 <= (double)v85 )
            goto LABEL_14;
        }
        v74 = (double)v29;
        v75 = v25 / (double)v29;
        v76 = v26 / v28;
        if ( v75 <= v76 )
          v75 = v76;
        v27 = (int)ceil_0(v75 * v28);
        v84 = v27;
        v29 = (int)ceil_0(v74 * v75);
        v85 = v29;
LABEL_14:
        v30 = 0;
        v95 = 0;
        if ( v101 || v15 )
        {
          v32 = (__int64)a5;
        }
        else
        {
          v86 = *a6;
          BestFactoryForBitmapTarget = Gfx::GetBestFactoryForBitmapTarget((Gfx *)8, (unsigned int)v24);
          Gfx::IBitmapTarget::Create(
            (unsigned int)&v88,
            (unsigned int)&v84,
            (unsigned int)&v86,
            1,
            (__int64)BestFactoryForBitmapTarget,
            8);
          v31 = v88;
          v88 = 0;
          v94 = v31;
          ho[0] = a2;
          v32 = (__int64)a5;
          ho[1] = a5;
          v91 = a4;
          v92 = &v84;
          sub_1800D2B00(v31, v33, ho);
          v34 = (*(__int64 (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v31 + 464LL))(v31);
          v35 = (const struct GEL::IImage **)GEL::IImage::Create(&v86, v34);
          v30 = *v35;
          *v35 = 0;
          v95 = v30;
          if ( v86 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 8LL))(v86);
          if ( !v87 )
          {
            v36 = (double)v84;
            v37 = (double)v85;
            *(_QWORD *)a4 = 0;
            *(_QWORD *)(a4 + 8) = 0;
            *(double *)(a4 + 16) = v36;
            *(double *)(a4 + 24) = v37;
            *a1 = v30;
            if ( v31 )
              (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v31 + 8LL))(v31);
            GEL::AccessImageResource::~AccessImageResource((GEL::AccessImageResource *)v97);
            return a1;
          }
          if ( v31 )
            (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v31 + 8LL))(v31);
          v29 = v85;
          v27 = v84;
        }
        v39 = (unsigned int)(v27 * v29);
        *(_OWORD *)v89 = 0;
        Ofc::CDIBSection::Create((Ofc::CDIBSection *)v89, v24, 32, v27, v29, v78, v80);
        if ( !v89[0] || !v89[1] )
        {
          MsoShipAssertTagProc(2627406);
          Ofc::CHResultException::ThrowTag(-2147024882, 0x28174Fu);
          return a1;
        }
        sub_18007F438((__int64)v89, a2, &v84, (double *)a4, -1, v32);
        v41 = (unsigned __int8 *)v89[1];
        v86 = (unsigned int)v39;
        v42 = (unsigned int)v39 * (unsigned __int128)4uLL;
        if ( !is_mul_ok((unsigned int)v39, 4u) )
          *(_QWORD *)&v42 = -1;
        v94 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)v42, *((unsigned __int64 *)&v42 + 1), v40);
        v96 = v94;
        v44 = (char *)v94;
        v45 = v9 & 0xFFF4DFED;
        v87 = 925707;
        if ( v82 )
        {
          *(_OWORD *)ho = 0;
          Ofc::CDIBSection::Create((Ofc::CDIBSection *)ho, v43, 32, v84, v85, v79, v81);
          if ( ho[0] && ho[1] )
          {
            sub_18007F438((__int64)ho, a2, &v84, (double *)a4, 0, (__int64)a5);
            v87 = 2498570;
            if ( (_DWORD)v39 )
            {
              v46 = v41 + 1;
              v88 = v41 + 1;
              v47 = (char *)ho[1] + 1;
              v48 = (char *)v41 - (char *)ho[1];
              v49 = v86;
              do
              {
                v50 = (unsigned __int8)v47[1];
                v51 = v46[1];
                if ( v45 )
                {
                  v61 = (unsigned __int8)v47[1];
                  v62 = (unsigned __int8)*v47;
                  v63 = *v46;
                  v64 = (unsigned __int8)*(v47 - 1);
                  v65 = (unsigned __int8)v47[v48 - 1];
                  BYTE2(v86) = (unsigned int)(v51 + v61) >> 1;
                  BYTE1(v86) = (unsigned int)(v62 + v63) >> 1;
                  LOBYTE(v86) = (unsigned int)(v65 + v64) >> 1;
                  BYTE3(v86) = ~(unsigned __int8)((v63 + v51 + v65 - v64 - v61 - v62) / 3);
                  *(_DWORD *)v44 = v86;
                  v46 = v88;
                }
                else
                {
                  v83 = *v46 - *v47;
                  v102 = v47[v48 - 1] - *(v47 - 1);
                  if ( (_BYTE)v50 == (_BYTE)v51 )
                  {
                    LOBYTE(v52) = v46[1];
                  }
                  else
                  {
                    LOBYTE(v52) = v50 - v51 - 1;
                    if ( (_BYTE)v50 - (_BYTE)v51 != 1 )
                      v52 = (((unsigned __int8)v52 >> 1) + 255 * v50) / (unsigned int)(unsigned __int8)v52;
                  }
                  v44[2] = v52;
                  LOBYTE(v52) = *v46;
                  if ( *v47 != *v46 )
                  {
                    if ( *v47 - (_BYTE)v52 == 1 )
                      LOBYTE(v52) = 0;
                    else
                      v52 = (((unsigned __int8)(*v47 - v52 - 1) >> 1) + 255 * (unsigned int)(unsigned __int8)*v47)
                          / (unsigned __int8)(*v47 - v52 - 1);
                  }
                  v44[1] = v52;
                  LOBYTE(v53) = v47[v48 - 1];
                  if ( *(v47 - 1) != (_BYTE)v53 )
                  {
                    if ( *(v47 - 1) - (_BYTE)v53 == 1 )
                      LOBYTE(v53) = 0;
                    else
                      v53 = (((unsigned __int8)(*(v47 - 1) - v53 - 1) >> 1)
                           + 255 * (unsigned int)(unsigned __int8)*(v47 - 1))
                          / (unsigned __int8)(*(v47 - 1) - v53 - 1);
                  }
                  *v44 = v53;
                  v44[3] = ~(unsigned __int8)((v83 + v102 + (unsigned int)(unsigned __int8)(v51 - v50)) / 3);
                }
                v46 += 4;
                v88 = v46;
                v47 += 4;
                v44 += 4;
                --v49;
              }
              while ( v49 );
            }
            if ( ho[0] )
              DeleteObject(ho[0]);
LABEL_55:
            v54 = (double)v84;
            v55 = (double)v85;
            *(_QWORD *)a4 = 0;
            *(_QWORD *)(a4 + 8) = 0;
            *(double *)(a4 + 16) = v54;
            *(double *)(a4 + 24) = v55;
            v56 = Gfx::GELPixelFormatToAlphaMode(v87);
            v57 = Gfx::GELPixelFormatToPixelFormat(v87);
            v58 = v94;
            v59 = (const struct GEL::IImage **)GEL::IImage::Create(
                                                 (unsigned int)&v88,
                                                 (_DWORD)v94,
                                                 v84,
                                                 v85,
                                                 4 * v84,
                                                 v57,
                                                 v56,
                                                 (__int64)a6);
            v60 = *v59;
            *v59 = 0;
            *a1 = v60;
            if ( v88 )
              (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v88 + 8LL))(v88);
            operator delete(v58);
            if ( v89[0] )
            {
              DeleteObject(v89[0]);
              *(_OWORD *)v89 = 0;
            }
            if ( v30 )
              (*(void (__fastcall **)(const struct GEL::IImage *))(*(_QWORD *)v30 + 8LL))(v30);
            GEL::AccessImageResource::~AccessImageResource((GEL::AccessImageResource *)v97);
            return a1;
          }
          MsoShipAssertTagProc(2627406);
          Ofc::CHResultException::ThrowTag(-2147024882, 0x28174Fu);
LABEL_88:
          if ( (unsigned __int8)*(v68 - 1)
             + (unsigned __int8)*(v68 - 2)
             + (unsigned __int8)*(v68 - 3)
             - *(v41 - 1)
             - v41[1] != *v41
            && *v68 == 0xFF )
          {
            v44[2] = (unsigned __int8)v70 >> 1;
            v44[1] = (unsigned __int8)v71 >> 1;
            LOBYTE(v66) = (unsigned __int8)v66 >> 1;
            *v44 = v66;
            v44[3] = 127;
          }
          while ( 1 )
          {
            v41 += 4;
            v44 += 4;
            v68 += 4;
            if ( !--v39 )
              break;
LABEL_69:
            v69 = (unsigned __int8)*v68;
            v44[3] = v69;
            v67 = v69;
            v70 = (unsigned int)(((v69 * v41[1] + 127) * (unsigned __int64)v45) >> 32) >> 7;
            v44[2] = v70;
            v71 = (unsigned int)(((v69 * *v41 + 127) * (unsigned __int64)v45) >> 32) >> 7;
            v44[1] = v71;
            v66 = (unsigned int)(((v69 * *(v41 - 1) + 127) * (unsigned __int64)v45) >> 32) >> 7;
            *v44 = v66;
            if ( a9 )
              goto LABEL_88;
          }
        }
        else
        {
          if ( v101 )
          {
            if ( (_DWORD)v39 )
            {
              v72 = (char *)(v41 + 1);
              v73 = v86;
              do
              {
                v44[2] = v72[1];
                v44[1] = *v72;
                *v44 = *(v72 - 1);
                v44[3] = -1;
                v72 += 4;
                v44 += 4;
                --v73;
              }
              while ( v73 );
            }
            goto LABEL_55;
          }
          GEL::IImage::TReadLock_<ARC::Pixel32>::TReadLock_<ARC::Pixel32>(ho, v30);
          if ( (_DWORD)v39 )
          {
            ++v41;
            v68 = (char *)ho[0] + 3;
            v45 = -2139062143;
            v39 = v86;
            goto LABEL_69;
          }
        }
        if ( v93 )
          (*(void (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v93 + 8LL))(v93, v66, v67, v68);
        (*(void (__fastcall **)(int *, __int64, __int64, _BYTE *))(*(_QWORD *)v92 + 8LL))(v92, v66, v67, v68);
        goto LABEL_55;
      }
    }
    else
    {
      Ofc::CInvalidParamException::ThrowTag(0x13DA54Du);
    }
    v101 = 1;
    if ( a8 )
      goto LABEL_8;
    goto LABEL_7;
  }
  *a1 = a2;
  if ( a2 )
    (**(void (__fastcall ***)(const struct GEL::IImage *))a2)(a2);
  return a1;
}

```

## disassembly

```asm
0x1800d2150  mov     rax, rsp
0x1800d2153  mov     [rax+10h], rbx
0x1800d2157  mov     [rax+20h], rsi
0x1800d215b  mov     [rax+18h], r8
0x1800d215f  mov     [rax+8], rcx
0x1800d2163  push    rdi
0x1800d2164  push    r12
0x1800d2166  push    r13
0x1800d2168  push    r14
0x1800d216a  push    r15
0x1800d216c  sub     rsp, 140h
0x1800d2173  movaps  xmmword ptr [rax-38h], xmm6
0x1800d2177  movaps  xmmword ptr [rax-48h], xmm7
0x1800d217b  movaps  xmmword ptr [rax-58h], xmm8
0x1800d2180  movaps  xmmword ptr [rax-68h], xmm9
0x1800d2185  mov     r12, r9
0x1800d2188  mov     rbx, r8
0x1800d218b  mov     r14, rdx
0x1800d218e  mov     r13, rcx
0x1800d2191  xor     r15d, r15d
0x1800d2194  mov     rcx, rdx; this
0x1800d2197  call    ?IsRaster@Image@GEL@@UEBA_NXZ; GEL::Image::IsRaster(void)
0x1800d219c  test    al, al
0x1800d219e  jnz     loc_1800D2483
0x1800d21a4  lea     edx, [r15+2]; unsigned int
0x1800d21a8  mov     rcx, r14; this
0x1800d21ab  call    ?SupportsRenderingMethod@Image@GEL@@QEBA_NI@Z; GEL::Image::SupportsRenderingMethod(uint)
0x1800d21b0  test    al, al
0x1800d21b2  jnz     loc_1800D2483
0x1800d21b8  xor     r8d, r8d; struct GEL::ITech *
0x1800d21bb  mov     rdx, r14; struct GEL::IImage *
0x1800d21be  lea     rcx, [rsp+168h+var_A8]; this
0x1800d21c6  call    ??0AccessImageResource@GEL@@QEAA@AEBUIImage@1@PEBUITech@1@@Z; GEL::AccessImageResource::AccessImageResource(GEL::IImage const &,GEL::ITech const *)
0x1800d21cb  mov     rcx, [rsp+168h+var_80]
0x1800d21d3  mov     rax, [rcx]
0x1800d21d6  mov     rax, [rax+8]
0x1800d21da  call    cs:__guard_dispatch_icall_fptr
0x1800d21e0  test    eax, eax
0x1800d21e2  jz      loc_1800D29D0
0x1800d21e8  mov     rsi, [rsp+168h+var_80]
0x1800d21f0  test    rsi, rsi
0x1800d21f3  jnz     loc_1800D2461
0x1800d21f9  mov     esi, r15d
0x1800d21fc  mov     edi, [rsi+64h]
0x1800d21ff  mov     eax, edi
0x1800d2201  and     eax, 0FFFCDFEDh
0x1800d2206  mov     [rsp+168h+var_110], eax
0x1800d220a  mov     eax, 200h
0x1800d220f  cmp     edi, eax
0x1800d2211  jz      loc_1800D29DA
0x1800d2217  mov     [rsp+168h+arg_30], r15b
0x1800d221f  test    eax, edi
0x1800d2221  jz      loc_1800D29F5
0x1800d2227  mov     cl, r15b
0x1800d222a  mov     eax, edi
0x1800d222c  and     eax, 40000h
0x1800d2231  test    cl, cl
0x1800d2233  jz      loc_1800D2476
0x1800d2239  mov     r15b, 1
0x1800d223c  mov     [rsp+168h+var_128], r15b
0x1800d2241  mov     rcx, rbx
0x1800d2244  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x1800d2249  call    ceil_0
0x1800d224e  cvttsd2si rbx, xmm0
0x1800d2253  mov     rcx, [rsp+168h+arg_10]
0x1800d225b  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x1800d2260  call    ceil_0
0x1800d2265  cvttsd2si rax, xmm0
0x1800d226a  mov     [rsp+168h+var_120], eax
0x1800d226e  mov     [rsp+168h+var_11C], ebx
0x1800d2272  lea     rdx, [rsp+168h+ho]
0x1800d2277  mov     rcx, r12
0x1800d227a  call    ?GetSize@?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@QEBA?AU?$TSize@V?$TUnits@NUDevicePixels@Math@@@Math@@@2@XZ; Math::TRect<Math::TUnits<double,Math::DevicePixels>>::GetSize(void)
0x1800d227f  movss   xmm6, dword ptr [rsi+60h]
0x1800d2284  cvtps2pd xmm6, xmm6
0x1800d2287  mulsd   xmm6, qword ptr [rax+8]
0x1800d228c  movss   xmm1, dword ptr [rsi+5Ch]
0x1800d2291  cvtps2pd xmm1, xmm1
0x1800d2294  mulsd   xmm1, qword ptr [rax]
0x1800d2298  mov     esi, [rsp+168h+var_120]
0x1800d229c  xorps   xmm2, xmm2
0x1800d229f  cvtsi2sd xmm2, rsi
0x1800d22a4  comisd  xmm1, xmm2
0x1800d22a8  ja      loc_1800D2A06
0x1800d22ae  mov     ecx, [rsp+168h+var_11C]
0x1800d22b2  xorps   xmm0, xmm0
0x1800d22b5  cvtsi2sd xmm0, rcx
0x1800d22ba  comisd  xmm6, xmm0
0x1800d22be  ja      loc_1800D2A0A
0x1800d22c4  xor     ebx, ebx
0x1800d22c6  mov     [rsp+168h+var_B8], rbx
0x1800d22ce  cmp     [rsp+168h+arg_30], bl
0x1800d22d5  jnz     loc_1800D24A0
0x1800d22db  test    r15b, r15b
0x1800d22de  jnz     loc_1800D24A0
0x1800d22e4  mov     rax, [rsp+168h+arg_28]
0x1800d22ec  movss   xmm0, dword ptr [rax]
0x1800d22f0  movss   dword ptr [rsp+168h+var_118], xmm0
0x1800d22f6  movss   xmm1, dword ptr [rax+4]
0x1800d22fb  movss   dword ptr [rsp+168h+var_118+4], xmm1
0x1800d2301  mov     ebx, 8
0x1800d2306  mov     ecx, ebx; this
0x1800d2308  call    ?GetBestFactoryForBitmapTarget@Gfx@@YAAEAUIFactory@ARC@@I@Z; Gfx::GetBestFactoryForBitmapTarget(uint)
0x1800d230d  mov     [rsp+168h+var_140], ebx; unsigned int
0x1800d2311  mov     qword ptr [rsp+168h+var_148], rax
0x1800d2316  lea     r9d, [rbx-7]
0x1800d231a  lea     r8, [rsp+168h+var_118]
0x1800d231f  lea     rdx, [rsp+168h+var_120]
0x1800d2324  lea     rcx, [rsp+168h+var_108]
0x1800d2329  call    ?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@AEAUIFactory@9@I@Z; Gfx::IBitmapTarget::Create(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::TConvertibleDPI2<float> const &,ARC::AlphaMode,ARC::IFactory &,uint)
0x1800d232e  mov     rsi, [rsp+168h+var_108]
0x1800d2333  mov     [rsp+168h+var_108], 0
0x1800d233c  mov     [rsp+168h+var_C8], rsi
0x1800d2344  mov     [rsp+168h+ho], r14
0x1800d2349  mov     r15, [rsp+168h+arg_20]
0x1800d2351  mov     [rsp+168h+ho+8], r15
0x1800d2359  mov     [rsp+168h+var_E0], r12
0x1800d2361  lea     rax, [rsp+168h+var_120]
0x1800d2366  mov     [rsp+168h+var_D8], rax
0x1800d236e  lea     r8, [rsp+168h+ho]
0x1800d2373  mov     rcx, rsi
0x1800d2376  call    sub_1800D2B00
0x1800d237b  mov     rax, [rsi]
0x1800d237e  mov     rcx, rsi
0x1800d2381  mov     rax, [rax+1D0h]
0x1800d2388  call    cs:__guard_dispatch_icall_fptr
0x1800d238e  mov     rdx, rax
0x1800d2391  lea     rcx, [rsp+168h+var_118]
0x1800d2396  call    ?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z; GEL::IImage::Create(ARC::IPlatformBitmap &)
0x1800d239b  mov     rbx, [rax]
0x1800d239e  mov     qword ptr [rax], 0
0x1800d23a5  mov     [rsp+168h+var_B8], rbx
0x1800d23ad  mov     rcx, [rsp+168h+var_118]
0x1800d23b2  test    rcx, rcx
0x1800d23b5  jz      short loc_1800D23C4
0x1800d23b7  mov     rax, [rcx]
0x1800d23ba  mov     rax, [rax+8]
0x1800d23be  call    cs:__guard_dispatch_icall_fptr
0x1800d23c4  cmp     [rsp+168h+var_110], 0
0x1800d23c9  jnz     loc_1800D24AA
0x1800d23cf  mov     eax, [rsp+168h+var_120]
0x1800d23d3  xorps   xmm1, xmm1
0x1800d23d6  cvtsi2sd xmm1, rax
0x1800d23db  mov     eax, [rsp+168h+var_11C]
0x1800d23df  xorps   xmm0, xmm0
0x1800d23e2  cvtsi2sd xmm0, rax
0x1800d23e7  mov     qword ptr [r12], 0
0x1800d23ef  mov     qword ptr [r12+8], 0
0x1800d23f8  movsd   qword ptr [r12+10h], xmm1
0x1800d23ff  movsd   qword ptr [r12+18h], xmm0
0x1800d2406  mov     [r13+0], rbx
0x1800d240a  test    rsi, rsi
0x1800d240d  jz      short loc_1800D2420
0x1800d240f  mov     rax, [rsi]
0x1800d2412  mov     rcx, rsi
0x1800d2415  mov     rax, [rax+8]
0x1800d2419  call    cs:__guard_dispatch_icall_fptr
0x1800d241f  nop
0x1800d2420  lea     rcx, [rsp+168h+var_A8]; this
0x1800d2428  call    ??1AccessImageResource@GEL@@QEAA@XZ; GEL::AccessImageResource::~AccessImageResource(void)
0x1800d242d  mov     rax, r13
0x1800d2430  lea     r11, [rsp+168h+var_28]
0x1800d2438  mov     rbx, [r11+38h]
0x1800d243c  mov     rsi, [r11+48h]
0x1800d2440  movaps  xmm6, xmmword ptr [r11-10h]
0x1800d2445  movaps  xmm7, xmmword ptr [r11-20h]
0x1800d244a  movaps  xmm8, xmmword ptr [r11-30h]
0x1800d244f  movaps  xmm9, xmmword ptr [r11-40h]
0x1800d2454  mov     rsp, r11
0x1800d2457  pop     r15
0x1800d2459  pop     r14
0x1800d245b  pop     r13
0x1800d245d  pop     r12
0x1800d245f  pop     rdi
0x1800d2460  retn
0x1800d2461  xor     r8d, r8d
0x1800d2464  mov     edx, 120F0h
0x1800d2469  mov     rcx, [rsi]
0x1800d246c  call    __castguard_slow_path_check_user_handled
0x1800d2471  jmp     loc_1800D21FC
0x1800d2476  test    eax, eax
0x1800d2478  jz      loc_1800D223C
0x1800d247e  jmp     loc_1800D2239
0x1800d2483  mov     [r13+0], r14
0x1800d2487  test    r14, r14
0x1800d248a  jz      short loc_1800D249B
0x1800d248c  mov     rax, [r14]
0x1800d248f  mov     rcx, r14
0x1800d2492  mov     rax, [rax]
0x1800d2495  call    cs:__guard_dispatch_icall_fptr
0x1800d249b  mov     rax, r13
0x1800d249e  jmp     short loc_1800D2430
0x1800d24a0  mov     r15, [rsp+168h+arg_20]
0x1800d24a8  jmp     short loc_1800D24C7
0x1800d24aa  test    rsi, rsi
0x1800d24ad  jz      short loc_1800D24BF
0x1800d24af  mov     rax, [rsi]
0x1800d24b2  mov     rcx, rsi
0x1800d24b5  mov     rax, [rax+8]
0x1800d24b9  call    cs:__guard_dispatch_icall_fptr
0x1800d24bf  mov     ecx, [rsp+168h+var_11C]
0x1800d24c3  mov     esi, [rsp+168h+var_120]
0x1800d24c7  mov     r13d, ecx
0x1800d24ca  imul    r13d, esi
0x1800d24ce  xorps   xmm0, xmm0
0x1800d24d1  movdqu  xmmword ptr [rsp+168h+var_100], xmm0
0x1800d24d7  mov     [rsp+168h+var_148], ecx; int
0x1800d24db  mov     r9d, esi; int
0x1800d24de  mov     r8d, 20h ; ' '; int
0x1800d24e4  lea     rcx, [rsp+168h+var_100]; this
0x1800d24e9  call    ?Create@CDIBSection@Ofc@@QEAAXPEAUHDC__@@HHHIPEAUHPALETTE__@@@Z; Ofc::CDIBSection::Create(HDC__ *,int,int,int,uint,HPALETTE__ *)
0x1800d24ee  cmp     [rsp+168h+var_100], 0
0x1800d24f4  jz      loc_1800D2AD1
0x1800d24fa  cmp     [rsp+168h+var_100+8], 0
0x1800d2500  jz      loc_1800D2AD1
0x1800d2506  mov     qword ptr [rsp+168h+var_140], r15; unsigned int
0x1800d250b  mov     [rsp+168h+var_148], 0FFFFFFFFh
0x1800d2513  mov     r9, r12
0x1800d2516  lea     r8, [rsp+168h+var_120]
0x1800d251b  mov     rdx, r14
0x1800d251e  lea     rcx, [rsp+168h+var_100]
0x1800d2523  call    sub_18007F438
0x1800d2528  mov     r15, [rsp+168h+var_100+8]
0x1800d252d  mov     ecx, r13d
0x1800d2530  mov     [rsp+168h+var_118], rcx
0x1800d2535  mov     eax, 4
0x1800d253a  mul     rcx
0x1800d253d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d2544  cmovb   rax, rcx
0x1800d2548  mov     rcx, rax; this
0x1800d254b  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800d2550  mov     [rsp+168h+var_C8], rax
0x1800d2558  mov     [rsp+168h+var_B0], rax
0x1800d2560  mov     rsi, rax
0x1800d2563  and     edi, 0FFF4DFEDh
0x1800d2569  mov     [rsp+168h+var_110], 0E200Bh
0x1800d2571  cmp     [rsp+168h+var_128], 0
0x1800d2576  jz      loc_1800D28B2
0x1800d257c  xorps   xmm0, xmm0
0x1800d257f  movdqu  xmmword ptr [rsp+168h+ho], xmm0
0x1800d2585  mov     eax, [rsp+168h+var_11C]
0x1800d2589  mov     [rsp+168h+var_148], eax; int
0x1800d258d  mov     r9d, [rsp+168h+var_120]; int
0x1800d2592  mov     r8d, 20h ; ' '; int
0x1800d2598  lea     rcx, [rsp+168h+ho]; this
0x1800d259d  call    ?Create@CDIBSection@Ofc@@QEAAXPEAUHDC__@@HHHIPEAUHPALETTE__@@@Z; Ofc::CDIBSection::Create(HDC__ *,int,int,int,uint,HPALETTE__ *)
0x1800d25a2  nop
0x1800d25a3  xor     ecx, ecx
0x1800d25a5  cmp     [rsp+168h+ho], rcx
0x1800d25aa  jz      loc_1800D2A61
0x1800d25b0  cmp     [rsp+168h+ho+8], rcx
0x1800d25b8  jz      loc_1800D2A61
0x1800d25be  mov     rax, [rsp+168h+arg_20]
0x1800d25c6  mov     qword ptr [rsp+168h+var_140], rax
0x1800d25cb  mov     [rsp+168h+var_148], ecx
0x1800d25cf  mov     r9, r12
0x1800d25d2  lea     r8, [rsp+168h+var_120]
0x1800d25d7  mov     rdx, r14
0x1800d25da  lea     rcx, [rsp+168h+ho]
0x1800d25df  call    sub_18007F438
0x1800d25e4  mov     [rsp+168h+var_110], 26200Ah
0x1800d25ec  test    r13d, r13d
0x1800d25ef  jz      loc_1800D26D1
0x1800d25f5  lea     r10, [r15+1]
0x1800d25f9  mov     [rsp+168h+var_108], r10
0x1800d25fe  mov     rax, [rsp+168h+ho+8]
0x1800d2606  lea     r14, [rax+1]
0x1800d260a  sub     r15, rax
0x1800d260d  mov     r13, [rsp+168h+var_118]
0x1800d2612  movzx   r11d, byte ptr [r14+1]
0x1800d2617  movzx   r9d, byte ptr [r10+1]
0x1800d261c  test    edi, edi
0x1800d261e  jnz     loc_1800D284A
0x1800d2624  mov     al, [r10]
0x1800d2627  sub     al, [r14]
0x1800d262a  mov     [rsp+168h+var_128], al
0x1800d262e  mov     al, [r15+r14-1]
0x1800d2633  sub     al, [r14-1]
0x1800d2637  mov     [rsp+168h+arg_30], al
0x1800d263e  cmp     r11b, r9b
0x1800d2641  jz      loc_1800D27E5
0x1800d2647  mov     al, r11b
0x1800d264a  sub     al, r9b
0x1800d264d  sub     al, 1
0x1800d264f  jnz     loc_1800D27ED
0x1800d2655  mov     [rsi+2], al
0x1800d2658  mov     al, [r10]
0x1800d265b  cmp     [r14], al
0x1800d265e  jz      short loc_1800D2670
0x1800d2660  mov     cl, [r14]
0x1800d2663  sub     cl, al
0x1800d2665  sub     cl, 1
0x1800d2668  jnz     loc_1800D2809
0x1800d266e  xor     al, al
0x1800d2670  mov     [rsi+1], al
0x1800d2673  mov     cl, [r15+r14-1]
0x1800d2678  cmp     [r14-1], cl
0x1800d267c  jz      short loc_1800D268E
0x1800d267e  mov     al, [r14-1]
0x1800d2682  sub     al, cl
  ... truncated ...
```
