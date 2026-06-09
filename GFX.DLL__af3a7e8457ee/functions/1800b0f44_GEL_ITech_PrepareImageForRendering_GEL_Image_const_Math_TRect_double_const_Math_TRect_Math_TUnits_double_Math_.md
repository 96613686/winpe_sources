# GEL::ITech::PrepareImageForRendering(GEL::Image const &,Math::TRect<double> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> &,Gfx::RenderingPolicySet const &,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &,bool,bool,bool)

- ea: `0x1800b0f44`
- end: `0x1800b18f3`
- name: `?PrepareImageForRendering@ITech@GEL@@SA?AV?$TCntPtr@$$CBUIImage@GEL@@@Ofc@@AEBVImage@2@AEBU?$TRect@N@Math@@AEAU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@7@AEBVRenderingPolicySet@Gfx@@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@7@_N55@Z`
- size: `2479`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config`

## callers

- `0x1800afdd8`

## callees

- `0x1800098ac`
- `0x180018a7c`
- `0x18001d7d0`
- `0x18001df20`
- `0x18001ffb4`
- `0x180024f30`
- `0x180024f60`
- `0x18004f980`
- `0x1800573f0`
- `0x180062088`
- `0x1800786fc`
- `0x1800b0900`
- `0x1800b0f44`
- `0x1800b2120`
- `0x1800b2160`
- `0x1800b21a0`
- `0x1800b21e4`
- `0x1800d33a4`
- `0x1800d7b90`
- `0x1800d9b60`
- `0x1800da250`
- `0x1800dc27c`
- `0x18010df2c`
- `0x180169bd0`
- `0x1801828e0`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800b185c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800b18cc`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800b185c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800b18cc`
- `GDI32!DeleteObject` at `0x1800b14d1`
- `GDI32!DeleteObject` at `0x1800b15a1`
- `GDI32!DeleteObject` at `0x1800b14d1`
- `GDI32!DeleteObject` at `0x1800b15a1`

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
          sub_1800B2120(v31, v33, ho);
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
        sub_180062088((__int64)v89, a2, &v84, (double *)a4, -1, v32);
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
            sub_180062088((__int64)ho, a2, &v84, (double *)a4, 0, (__int64)a5);
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
0x1800b0f44  mov     rax, rsp
0x1800b0f47  mov     [rax+10h], rbx
0x1800b0f4b  mov     [rax+20h], rsi
0x1800b0f4f  mov     [rax+18h], r8
0x1800b0f53  mov     [rax+8], rcx
0x1800b0f57  push    rdi
0x1800b0f58  push    r12
0x1800b0f5a  push    r13
0x1800b0f5c  push    r14
0x1800b0f5e  push    r15
0x1800b0f60  sub     rsp, 140h
0x1800b0f67  movaps  xmmword ptr [rax-38h], xmm6
0x1800b0f6b  movaps  xmmword ptr [rax-48h], xmm7
0x1800b0f6f  movaps  xmmword ptr [rax-58h], xmm8
0x1800b0f74  movaps  xmmword ptr [rax-68h], xmm9
0x1800b0f79  mov     r12, r9
0x1800b0f7c  mov     rbx, r8
0x1800b0f7f  mov     r14, rdx
0x1800b0f82  mov     r13, rcx
0x1800b0f85  xor     r15d, r15d
0x1800b0f88  mov     rcx, rdx; this
0x1800b0f8b  call    ?IsRaster@Image@GEL@@UEBA_NXZ; GEL::Image::IsRaster(void)
0x1800b0f90  test    al, al
0x1800b0f92  jnz     loc_1800B1277
0x1800b0f98  lea     edx, [r15+2]; unsigned int
0x1800b0f9c  mov     rcx, r14; this
0x1800b0f9f  call    ?SupportsRenderingMethod@Image@GEL@@QEBA_NI@Z; GEL::Image::SupportsRenderingMethod(uint)
0x1800b0fa4  test    al, al
0x1800b0fa6  jnz     loc_1800B1277
0x1800b0fac  xor     r8d, r8d; struct GEL::ITech *
0x1800b0faf  mov     rdx, r14; struct GEL::IImage *
0x1800b0fb2  lea     rcx, [rsp+168h+var_A8]; this
0x1800b0fba  call    ??0AccessImageResource@GEL@@QEAA@AEBUIImage@1@PEBUITech@1@@Z; GEL::AccessImageResource::AccessImageResource(GEL::IImage const &,GEL::ITech const *)
0x1800b0fbf  mov     rcx, [rsp+168h+var_80]
0x1800b0fc7  mov     rax, [rcx]
0x1800b0fca  mov     rax, [rax+8]
0x1800b0fce  call    cs:__guard_dispatch_icall_fptr
0x1800b0fd4  test    eax, eax
0x1800b0fd6  jz      loc_1800B17C6
0x1800b0fdc  mov     rsi, [rsp+168h+var_80]
0x1800b0fe4  test    rsi, rsi
0x1800b0fe7  jnz     loc_1800B1255
0x1800b0fed  mov     esi, r15d
0x1800b0ff0  mov     edi, [rsi+64h]
0x1800b0ff3  mov     eax, edi
0x1800b0ff5  and     eax, 0FFFCDFEDh
0x1800b0ffa  mov     [rsp+168h+var_110], eax
0x1800b0ffe  mov     eax, 200h
0x1800b1003  cmp     edi, eax
0x1800b1005  jz      loc_1800B17D0
0x1800b100b  mov     [rsp+168h+arg_30], r15b
0x1800b1013  test    eax, edi
0x1800b1015  jz      loc_1800B17EB
0x1800b101b  mov     cl, r15b
0x1800b101e  mov     eax, edi
0x1800b1020  and     eax, 40000h
0x1800b1025  test    cl, cl
0x1800b1027  jz      loc_1800B126A
0x1800b102d  mov     r15b, 1
0x1800b1030  mov     [rsp+168h+var_128], r15b
0x1800b1035  mov     rcx, rbx
0x1800b1038  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x1800b103d  call    ceil_0
0x1800b1042  cvttsd2si rbx, xmm0
0x1800b1047  mov     rcx, [rsp+168h+arg_10]
0x1800b104f  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x1800b1054  call    ceil_0
0x1800b1059  cvttsd2si rax, xmm0
0x1800b105e  mov     [rsp+168h+var_120], eax
0x1800b1062  mov     [rsp+168h+var_11C], ebx
0x1800b1066  lea     rdx, [rsp+168h+ho]
0x1800b106b  mov     rcx, r12
0x1800b106e  call    ?GetSize@?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@QEBA?AU?$TSize@V?$TUnits@NUDevicePixels@Math@@@Math@@@2@XZ; Math::TRect<Math::TUnits<double,Math::DevicePixels>>::GetSize(void)
0x1800b1073  movss   xmm6, dword ptr [rsi+60h]
0x1800b1078  cvtps2pd xmm6, xmm6
0x1800b107b  mulsd   xmm6, qword ptr [rax+8]
0x1800b1080  movss   xmm1, dword ptr [rsi+5Ch]
0x1800b1085  cvtps2pd xmm1, xmm1
0x1800b1088  mulsd   xmm1, qword ptr [rax]
0x1800b108c  mov     esi, [rsp+168h+var_120]
0x1800b1090  xorps   xmm2, xmm2
0x1800b1093  cvtsi2sd xmm2, rsi
0x1800b1098  comisd  xmm1, xmm2
0x1800b109c  ja      loc_1800B17FC
0x1800b10a2  mov     ecx, [rsp+168h+var_11C]
0x1800b10a6  xorps   xmm0, xmm0
0x1800b10a9  cvtsi2sd xmm0, rcx
0x1800b10ae  comisd  xmm6, xmm0
0x1800b10b2  ja      loc_1800B1800
0x1800b10b8  xor     ebx, ebx
0x1800b10ba  mov     [rsp+168h+var_B8], rbx
0x1800b10c2  cmp     [rsp+168h+arg_30], bl
0x1800b10c9  jnz     loc_1800B1294
0x1800b10cf  test    r15b, r15b
0x1800b10d2  jnz     loc_1800B1294
0x1800b10d8  mov     rax, [rsp+168h+arg_28]
0x1800b10e0  movss   xmm0, dword ptr [rax]
0x1800b10e4  movss   dword ptr [rsp+168h+var_118], xmm0
0x1800b10ea  movss   xmm1, dword ptr [rax+4]
0x1800b10ef  movss   dword ptr [rsp+168h+var_118+4], xmm1
0x1800b10f5  mov     ebx, 8
0x1800b10fa  mov     ecx, ebx; this
0x1800b10fc  call    ?GetBestFactoryForBitmapTarget@Gfx@@YAAEAUIFactory@ARC@@I@Z; Gfx::GetBestFactoryForBitmapTarget(uint)
0x1800b1101  mov     [rsp+168h+var_140], ebx; unsigned int
0x1800b1105  mov     qword ptr [rsp+168h+var_148], rax
0x1800b110a  lea     r9d, [rbx-7]
0x1800b110e  lea     r8, [rsp+168h+var_118]
0x1800b1113  lea     rdx, [rsp+168h+var_120]
0x1800b1118  lea     rcx, [rsp+168h+var_108]
0x1800b111d  call    ?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@AEAUIFactory@9@I@Z; Gfx::IBitmapTarget::Create(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::TConvertibleDPI2<float> const &,ARC::AlphaMode,ARC::IFactory &,uint)
0x1800b1122  mov     rsi, [rsp+168h+var_108]
0x1800b1127  mov     [rsp+168h+var_108], 0
0x1800b1130  mov     [rsp+168h+var_C8], rsi
0x1800b1138  mov     [rsp+168h+ho], r14
0x1800b113d  mov     r15, [rsp+168h+arg_20]
0x1800b1145  mov     [rsp+168h+ho+8], r15
0x1800b114d  mov     [rsp+168h+var_E0], r12
0x1800b1155  lea     rax, [rsp+168h+var_120]
0x1800b115a  mov     [rsp+168h+var_D8], rax
0x1800b1162  lea     r8, [rsp+168h+ho]
0x1800b1167  mov     rcx, rsi
0x1800b116a  call    sub_1800B2120
0x1800b116f  mov     rax, [rsi]
0x1800b1172  mov     rcx, rsi
0x1800b1175  mov     rax, [rax+1D0h]
0x1800b117c  call    cs:__guard_dispatch_icall_fptr
0x1800b1182  mov     rdx, rax
0x1800b1185  lea     rcx, [rsp+168h+var_118]
0x1800b118a  call    ?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z; GEL::IImage::Create(ARC::IPlatformBitmap &)
0x1800b118f  mov     rbx, [rax]
0x1800b1192  mov     qword ptr [rax], 0
0x1800b1199  mov     [rsp+168h+var_B8], rbx
0x1800b11a1  mov     rcx, [rsp+168h+var_118]
0x1800b11a6  test    rcx, rcx
0x1800b11a9  jz      short loc_1800B11B8
0x1800b11ab  mov     rax, [rcx]
0x1800b11ae  mov     rax, [rax+8]
0x1800b11b2  call    cs:__guard_dispatch_icall_fptr
0x1800b11b8  cmp     [rsp+168h+var_110], 0
0x1800b11bd  jnz     loc_1800B129E
0x1800b11c3  mov     eax, [rsp+168h+var_120]
0x1800b11c7  xorps   xmm1, xmm1
0x1800b11ca  cvtsi2sd xmm1, rax
0x1800b11cf  mov     eax, [rsp+168h+var_11C]
0x1800b11d3  xorps   xmm0, xmm0
0x1800b11d6  cvtsi2sd xmm0, rax
0x1800b11db  mov     qword ptr [r12], 0
0x1800b11e3  mov     qword ptr [r12+8], 0
0x1800b11ec  movsd   qword ptr [r12+10h], xmm1
0x1800b11f3  movsd   qword ptr [r12+18h], xmm0
0x1800b11fa  mov     [r13+0], rbx
0x1800b11fe  test    rsi, rsi
0x1800b1201  jz      short loc_1800B1214
0x1800b1203  mov     rax, [rsi]
0x1800b1206  mov     rcx, rsi
0x1800b1209  mov     rax, [rax+8]
0x1800b120d  call    cs:__guard_dispatch_icall_fptr
0x1800b1213  nop
0x1800b1214  lea     rcx, [rsp+168h+var_A8]; this
0x1800b121c  call    ??1AccessImageResource@GEL@@QEAA@XZ; GEL::AccessImageResource::~AccessImageResource(void)
0x1800b1221  mov     rax, r13
0x1800b1224  lea     r11, [rsp+168h+var_28]
0x1800b122c  mov     rbx, [r11+38h]
0x1800b1230  mov     rsi, [r11+48h]
0x1800b1234  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b1239  movaps  xmm7, xmmword ptr [r11-20h]
0x1800b123e  movaps  xmm8, xmmword ptr [r11-30h]
0x1800b1243  movaps  xmm9, xmmword ptr [r11-40h]
0x1800b1248  mov     rsp, r11
0x1800b124b  pop     r15
0x1800b124d  pop     r14
0x1800b124f  pop     r13
0x1800b1251  pop     r12
0x1800b1253  pop     rdi
0x1800b1254  retn
0x1800b1255  xor     r8d, r8d
0x1800b1258  mov     edx, 120F0h
0x1800b125d  mov     rcx, [rsi]
0x1800b1260  call    __castguard_slow_path_check_user_handled
0x1800b1265  jmp     loc_1800B0FF0
0x1800b126a  test    eax, eax
0x1800b126c  jz      loc_1800B1030
0x1800b1272  jmp     loc_1800B102D
0x1800b1277  mov     [r13+0], r14
0x1800b127b  test    r14, r14
0x1800b127e  jz      short loc_1800B128F
0x1800b1280  mov     rax, [r14]
0x1800b1283  mov     rcx, r14
0x1800b1286  mov     rax, [rax]
0x1800b1289  call    cs:__guard_dispatch_icall_fptr
0x1800b128f  mov     rax, r13
0x1800b1292  jmp     short loc_1800B1224
0x1800b1294  mov     r15, [rsp+168h+arg_20]
0x1800b129c  jmp     short loc_1800B12BB
0x1800b129e  test    rsi, rsi
0x1800b12a1  jz      short loc_1800B12B3
0x1800b12a3  mov     rax, [rsi]
0x1800b12a6  mov     rcx, rsi
0x1800b12a9  mov     rax, [rax+8]
0x1800b12ad  call    cs:__guard_dispatch_icall_fptr
0x1800b12b3  mov     ecx, [rsp+168h+var_11C]
0x1800b12b7  mov     esi, [rsp+168h+var_120]
0x1800b12bb  mov     r13d, ecx
0x1800b12be  imul    r13d, esi
0x1800b12c2  xorps   xmm0, xmm0
0x1800b12c5  movdqu  xmmword ptr [rsp+168h+var_100], xmm0
0x1800b12cb  mov     [rsp+168h+var_148], ecx; int
0x1800b12cf  mov     r9d, esi; int
0x1800b12d2  mov     r8d, 20h ; ' '; int
0x1800b12d8  lea     rcx, [rsp+168h+var_100]; this
0x1800b12dd  call    ?Create@CDIBSection@Ofc@@QEAAXPEAUHDC__@@HHHIPEAUHPALETTE__@@@Z; Ofc::CDIBSection::Create(HDC__ *,int,int,int,uint,HPALETTE__ *)
0x1800b12e2  cmp     [rsp+168h+var_100], 0
0x1800b12e8  jz      loc_1800B18C7
0x1800b12ee  xchg    ax, ax
0x1800b12f0  cmp     [rsp+168h+var_100+8], 0
0x1800b12f6  jz      loc_1800B18C7
0x1800b12fc  mov     qword ptr [rsp+168h+var_140], r15; unsigned int
0x1800b1301  mov     [rsp+168h+var_148], 0FFFFFFFFh
0x1800b1309  mov     r9, r12
0x1800b130c  lea     r8, [rsp+168h+var_120]
0x1800b1311  mov     rdx, r14
0x1800b1314  lea     rcx, [rsp+168h+var_100]
0x1800b1319  call    sub_180062088
0x1800b131e  mov     r15, [rsp+168h+var_100+8]
0x1800b1323  mov     ecx, r13d
0x1800b1326  mov     [rsp+168h+var_118], rcx
0x1800b132b  mov     eax, 4
0x1800b1330  mul     rcx
0x1800b1333  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b133a  cmovb   rax, rcx
0x1800b133e  mov     rcx, rax; this
0x1800b1341  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800b1346  mov     [rsp+168h+var_C8], rax
0x1800b134e  mov     [rsp+168h+var_B0], rax
0x1800b1356  mov     rsi, rax
0x1800b1359  and     edi, 0FFF4DFEDh
0x1800b135f  mov     [rsp+168h+var_110], 0E200Bh
0x1800b1367  cmp     [rsp+168h+var_128], 0
0x1800b136c  jz      loc_1800B16A8
0x1800b1372  xorps   xmm0, xmm0
0x1800b1375  movdqu  xmmword ptr [rsp+168h+ho], xmm0
0x1800b137b  mov     eax, [rsp+168h+var_11C]
0x1800b137f  mov     [rsp+168h+var_148], eax; int
0x1800b1383  mov     r9d, [rsp+168h+var_120]; int
0x1800b1388  mov     r8d, 20h ; ' '; int
0x1800b138e  lea     rcx, [rsp+168h+ho]; this
0x1800b1393  call    ?Create@CDIBSection@Ofc@@QEAAXPEAUHDC__@@HHHIPEAUHPALETTE__@@@Z; Ofc::CDIBSection::Create(HDC__ *,int,int,int,uint,HPALETTE__ *)
0x1800b1398  nop
0x1800b1399  xor     ecx, ecx
0x1800b139b  cmp     [rsp+168h+ho], rcx
0x1800b13a0  jz      loc_1800B1857
0x1800b13a6  cmp     [rsp+168h+ho+8], rcx
0x1800b13ae  jz      loc_1800B1857
0x1800b13b4  mov     rax, [rsp+168h+arg_20]
0x1800b13bc  mov     qword ptr [rsp+168h+var_140], rax
0x1800b13c1  mov     [rsp+168h+var_148], ecx
0x1800b13c5  mov     r9, r12
0x1800b13c8  lea     r8, [rsp+168h+var_120]
0x1800b13cd  mov     rdx, r14
0x1800b13d0  lea     rcx, [rsp+168h+ho]
0x1800b13d5  call    sub_180062088
0x1800b13da  mov     [rsp+168h+var_110], 26200Ah
0x1800b13e2  test    r13d, r13d
0x1800b13e5  jz      loc_1800B14C7
0x1800b13eb  lea     r10, [r15+1]
0x1800b13ef  mov     [rsp+168h+var_108], r10
0x1800b13f4  mov     rax, [rsp+168h+ho+8]
0x1800b13fc  lea     r14, [rax+1]
0x1800b1400  sub     r15, rax
0x1800b1403  mov     r13, [rsp+168h+var_118]
0x1800b1408  movzx   r11d, byte ptr [r14+1]
0x1800b140d  movzx   r9d, byte ptr [r10+1]
0x1800b1412  test    edi, edi
0x1800b1414  jnz     loc_1800B1640
0x1800b141a  mov     al, [r10]
0x1800b141d  sub     al, [r14]
0x1800b1420  mov     [rsp+168h+var_128], al
0x1800b1424  mov     al, [r15+r14-1]
0x1800b1429  sub     al, [r14-1]
0x1800b142d  mov     [rsp+168h+arg_30], al
0x1800b1434  cmp     r11b, r9b
0x1800b1437  jz      loc_1800B15DB
0x1800b143d  mov     al, r11b
0x1800b1440  sub     al, r9b
0x1800b1443  sub     al, 1
0x1800b1445  jnz     loc_1800B15E3
0x1800b144b  mov     [rsi+2], al
0x1800b144e  mov     al, [r10]
0x1800b1451  cmp     [r14], al
0x1800b1454  jz      short loc_1800B1466
0x1800b1456  mov     cl, [r14]
0x1800b1459  sub     cl, al
0x1800b145b  sub     cl, 1
0x1800b145e  jnz     loc_1800B15FF
0x1800b1464  xor     al, al
0x1800b1466  mov     [rsi+1], al
0x1800b1469  mov     cl, [r15+r14-1]
0x1800b146e  cmp     [r14-1], cl
0x1800b1472  jz      short loc_1800B1484
0x1800b1474  mov     al, [r14-1]
  ... truncated ...
```
