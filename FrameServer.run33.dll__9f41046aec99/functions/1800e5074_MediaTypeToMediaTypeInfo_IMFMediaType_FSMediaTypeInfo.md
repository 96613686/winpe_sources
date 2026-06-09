# MediaTypeToMediaTypeInfo(IMFMediaType *,FSMediaTypeInfo *)

- ea: `0x1800e5074`
- end: `0x1800e552c`
- name: `?MediaTypeToMediaTypeInfo@@YAJPEAUIMFMediaType@@PEAUFSMediaTypeInfo@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(struct IMFMediaType *, struct FSMediaTypeInfo *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ab700`
- `0x1800d98b0`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009608`
- `0x180009b5c`
- `0x180009cc0`
- `0x180009d00`
- `0x180024200`
- `0x1800268a8`
- `0x18004d714`
- `0x18004d748`
- `0x18004da70`
- `0x18004db3c`
- `0x18004db80`
- `0x1800e5074`
- `0x1800e55fc`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e54fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e54fb`
- `MFPlat!MFCreateMFVideoFormatFromMFMediaType` at `0x1800e523a`
- `MFPlat!MFCreateMFVideoFormatFromMFMediaType` at `0x1800e523a`
- `MFPlat!MFGetUncompressedVideoFormat` at `0x1800e52ce`
- `MFPlat!MFGetUncompressedVideoFormat` at `0x1800e52ce`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x1800e5300`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x1800e5300`

## pseudocode

```c
__int64 __fastcall MediaTypeToMediaTypeInfo(struct IMFMediaType *a1, struct FSMediaTypeInfo *a2)
{
  char v2; // di
  int v5; // r15d
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  DWORD *v9; // rsi
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  MediaTypeTracer *v11; // rax
  const char *String; // rax
  HRESULT v13; // eax
  __int64 v14; // rdx
  MFVIDEOFORMAT *v15; // rcx
  MediaTypeTracer *v16; // rax
  const char *v17; // rax
  int v18; // edi
  int v19; // esi
  __int64 v20; // rbx
  GuidTrace *v21; // rax
  const char *v22; // rax
  LONG pStride; // [rsp+60h] [rbp-69h] BYREF
  UINT32 pcbSize; // [rsp+64h] [rbp-65h] BYREF
  __int64 v26; // [rsp+68h] [rbp-61h] BYREF
  MFVIDEOFORMAT *ppMFVF; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v28[56]; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v29[56]; // [rsp+B0h] [rbp-19h] BYREF
  GUID Buf1; // [rsp+E8h] [rbp+1Fh] BYREF

  v2 = 0;
  pcbSize = 0;
  ppMFVF = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  if ( a1 )
  {
    if ( !a2 )
    {
      v5 = -2147467261;
      if ( !g_wppLevels )
        goto LABEL_49;
      v6 = 12;
      goto LABEL_4;
    }
    *(_OWORD *)a2 = 0;
    *((_OWORD *)a2 + 1) = 0;
    *((_QWORD *)a2 + 4) = 0;
    v7 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a1->lpVtbl->GetGUID)(
           a1,
           &MF_MT_MAJOR_TYPE,
           &Buf1);
    v5 = v7;
    if ( v7 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_49;
      v8 = 13;
LABEL_48:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids, 0, v7);
      goto LABEL_49;
    }
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, char *))a1->lpVtbl->GetGUID)(
           a1,
           &MF_MT_SUBTYPE,
           (char *)a2 + 16) < 0 )
      *((GUID *)a2 + 1) = GUID_00000000_0000_0000_0000_000000000000;
    v9 = (DWORD *)((char *)a2 + 32);
    if ( (int)MFGetAttribute2UINT32asUINT64(a1, &MF_MT_FRAME_SIZE, (char *)a2 + 32, (char *)a2 + 36) < 0 )
    {
      *v9 = 0;
      *((_DWORD *)a2 + 9) = 0;
    }
    if ( memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
    {
      if ( !memcmp_0(&Buf1, &MFMediaType_Image, 0x10u) )
      {
        *((_DWORD *)a2 + 2) = 1;
        goto LABEL_49;
      }
      if ( !memcmp_0(&Buf1, &MFMediaType_MultiplexedFrames, 0x10u) )
      {
        *((_DWORD *)a2 + 2) = 2;
        goto LABEL_49;
      }
      if ( !memcmp_0(&Buf1, &MFMediaType_Perception, 0x10u) )
      {
        *((_DWORD *)a2 + 2) = 3;
        goto LABEL_49;
      }
      if ( !memcmp_0(&Buf1, &MFMediaType_Stream, 0x10u) )
      {
        *((_DWORD *)a2 + 2) = 5;
        goto LABEL_49;
      }
      if ( !memcmp_0(&Buf1, &MFMediaType_Metadata, 0x10u) )
      {
        *((_DWORD *)a2 + 2) = 4;
        goto LABEL_49;
      }
      v7 = -1072875852;
      v5 = -1072875852;
      if ( !g_wppLevels )
        goto LABEL_49;
      v8 = 17;
      goto LABEL_48;
    }
    lpVtbl = a1->lpVtbl;
    v26 = 0;
    pStride = 0;
    if ( ((__int64 (__fastcall *)(struct IMFMediaType *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a1,
           &GUID_b99f381f_a8f9_47a2_a5af_ca3a225a3890,
           &v26) >= 0 )
    {
      v15 = (MFVIDEOFORMAT *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 304LL))(v26);
    }
    else
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v11 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v28, a1);
        String = FSString::GetString((MediaTypeTracer *)((char *)v11 + 8));
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, &WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids, String);
        v2 = 1;
      }
      if ( (v2 & 1) != 0 )
        MediaTypeTracer::~MediaTypeTracer((MediaTypeTracer *)v28);
      v13 = MFCreateMFVideoFormatFromMFMediaType(a1, &ppMFVF, &pcbSize);
      v5 = v13;
      if ( v13 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 15;
LABEL_24:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids, 0, v13);
          goto LABEL_25;
        }
        goto LABEL_25;
      }
      v15 = ppMFVF;
    }
    if ( v15 )
    {
      *((_DWORD *)a2 + 2) = 0;
      *((_DWORD *)a2 + 1) |= (LODWORD(v15->videoInfo.VideoFlags) >> 19) & 1;
      *((_DWORD *)a2 + 3) = MFGetUncompressedVideoFormat(v15);
      if ( !(unsigned int)MFGetAttributeUINT32(a1, &MF_MT_COMPRESSED, 0)
        && *v9
        && MFGetStrideForBitmapInfoHeader(*((_DWORD *)a2 + 3), *v9, &pStride) >= 0
        && pStride )
      {
        *((_DWORD *)a2 + 1) |= 2u;
      }
      goto LABEL_25;
    }
    v13 = -1072875852;
    v5 = -1072875852;
    if ( g_wppLevels )
    {
      v14 = 16;
      goto LABEL_24;
    }
LABEL_25:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v26);
    goto LABEL_49;
  }
  v5 = -2147024809;
  if ( g_wppLevels )
  {
    v6 = 11;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids, 0, v5);
  }
LABEL_49:
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u && a1 && a2 )
  {
    if ( v5 >= 0 )
    {
      v16 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v29, a1);
      v17 = FSString::GetString((MediaTypeTracer *)((char *)v16 + 8));
      v18 = *((_DWORD *)a2 + 9);
      v19 = *((_DWORD *)a2 + 8);
      v20 = (__int64)v17;
      v21 = GuidTrace::GuidTrace((GuidTrace *)v28, (const struct _GUID *)a2 + 1);
      v22 = GuidTrace::GetString(v21);
      WPP_SF_DDDDDsDDs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        *(_DWORD *)a2,
        *((_DWORD *)a2 + 1),
        *((_DWORD *)a2 + 2),
        *((_DWORD *)a2 + 3),
        (__int64)v22,
        v19,
        v18,
        v20);
      FSString::~FSString((FSString *)v28);
      MediaTypeTracer::~MediaTypeTracer((MediaTypeTracer *)v29);
    }
    else if ( byte_18010EC4D )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        18,
        &WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids,
        (unsigned int)v5);
    }
  }
  if ( ppMFVF )
    CoTaskMemFree(ppMFVF);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e5074  mov     [rsp-8+arg_10], rbx
0x1800e5079  mov     [rsp-8+arg_18], rsi
0x1800e507e  push    rbp
0x1800e507f  push    rdi
0x1800e5080  push    r12
0x1800e5082  push    r14
0x1800e5084  push    r15
0x1800e5086  lea     rbp, [rsp-37h]
0x1800e508b  sub     rsp, 100h
0x1800e5092  mov     rax, cs:__security_cookie
0x1800e5099  xor     rax, rsp
0x1800e509c  mov     [rbp+57h+var_28], rax
0x1800e50a0  xor     edi, edi
0x1800e50a2  mov     r14, rdx
0x1800e50a5  mov     [rbp+57h+pcbSize], edi
0x1800e50a8  mov     rbx, rcx
0x1800e50ab  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800e50b2  mov     [rbp+57h+pcbSize], edi
0x1800e50b5  mov     [rbp+57h+ppMFVF], rdi
0x1800e50b9  movdqu  [rbp+57h+Buf1], xmm0
0x1800e50be  test    rcx, rcx
0x1800e50c1  jnz     short loc_1800E50E3
0x1800e50c3  mov     r15d, 80070057h
0x1800e50c9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e50d0  jb      loc_1800E5410
0x1800e50d6  lea     edx, [rcx+0Bh]
0x1800e50d9  mov     dword ptr [rsp+120h+var_100], r15d
0x1800e50de  jmp     loc_1800E53F6
0x1800e50e3  test    r14, r14
0x1800e50e6  jnz     short loc_1800E5101
0x1800e50e8  mov     r15d, 80004003h
0x1800e50ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e50f5  jb      loc_1800E5410
0x1800e50fb  lea     edx, [r14+0Ch]
0x1800e50ff  jmp     short loc_1800E50D9
0x1800e5101  xor     eax, eax
0x1800e5103  lea     r8, [rbp+57h+Buf1]
0x1800e5107  xorps   xmm0, xmm0
0x1800e510a  movups  xmmword ptr [rdx], xmm0
0x1800e510d  movups  xmmword ptr [rdx+10h], xmm0
0x1800e5111  mov     [rdx+20h], rax
0x1800e5115  lea     rdx, MF_MT_MAJOR_TYPE
0x1800e511c  mov     rax, [rcx]
0x1800e511f  mov     rax, [rax+50h]
0x1800e5123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5128  mov     r15d, eax
0x1800e512b  test    eax, eax
0x1800e512d  jns     short loc_1800E5146
0x1800e512f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e5136  jb      loc_1800E5410
0x1800e513c  mov     edx, 0Dh
0x1800e5141  jmp     loc_1800E53F2
0x1800e5146  mov     rax, [rbx]
0x1800e5149  lea     r8, [r14+10h]
0x1800e514d  lea     rdx, MF_MT_SUBTYPE
0x1800e5154  mov     rcx, rbx
0x1800e5157  mov     rax, [rax+50h]
0x1800e515b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5160  test    eax, eax
0x1800e5162  jns     short loc_1800E5171
0x1800e5164  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800e516b  movdqu  xmmword ptr [r14+10h], xmm0
0x1800e5171  lea     rsi, [r14+20h]
0x1800e5175  mov     rcx, rbx
0x1800e5178  mov     r8, rsi
0x1800e517b  lea     r9, [r14+24h]
0x1800e517f  lea     rdx, MF_MT_FRAME_SIZE
0x1800e5186  call    MFGetAttribute2UINT32asUINT64
0x1800e518b  test    eax, eax
0x1800e518d  jns     short loc_1800E5195
0x1800e518f  mov     [rsi], edi
0x1800e5191  mov     [r14+24h], edi
0x1800e5195  mov     r8d, 10h; Size
0x1800e519b  lea     rdx, MFMediaType_Video; Buf2
0x1800e51a2  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800e51a6  call    memcmp_0
0x1800e51ab  test    eax, eax
0x1800e51ad  jnz     loc_1800E5322
0x1800e51b3  mov     rax, [rbx]
0x1800e51b6  lea     r8, [rbp+57h+var_B8]
0x1800e51ba  lea     rdx, _GUID_b99f381f_a8f9_47a2_a5af_ca3a225a3890
0x1800e51c1  mov     [rbp+57h+var_B8], rdi
0x1800e51c5  mov     rcx, rbx
0x1800e51c8  mov     [rbp+57h+pStride], edi
0x1800e51cb  mov     rax, [rax]
0x1800e51ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e51d3  test    eax, eax
0x1800e51d5  jns     loc_1800E5287
0x1800e51db  cmp     cs:byte_18010EC4D, 8
0x1800e51e2  jb      short loc_1800E5220
0x1800e51e4  mov     rdx, rbx; struct IMFMediaType *
0x1800e51e7  lea     rcx, [rbp+57h+var_A8]; this
0x1800e51eb  call    ??0MediaTypeTracer@@QEAA@PEAUIMFMediaType@@@Z; MediaTypeTracer::MediaTypeTracer(IMFMediaType *)
0x1800e51f0  lea     rcx, [rax+8]; this
0x1800e51f4  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800e51f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5200  lea     r8, WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids
0x1800e5207  mov     edx, 0Eh
0x1800e520c  mov     r9, rax
0x1800e520f  mov     rcx, [rcx+0D8h]
0x1800e5216  call    WPP_SF_s
0x1800e521b  mov     edi, 1
0x1800e5220  test    dil, 1
0x1800e5224  jz      short loc_1800E522F
0x1800e5226  lea     rcx, [rbp+57h+var_A8]; this
0x1800e522a  call    ??1MediaTypeTracer@@UEAA@XZ; MediaTypeTracer::~MediaTypeTracer(void)
0x1800e522f  lea     r8, [rbp+57h+pcbSize]; pcbSize
0x1800e5233  mov     rcx, rbx; pMFType
0x1800e5236  lea     rdx, [rbp+57h+ppMFVF]; ppMFVF
0x1800e523a  call    cs:__imp_MFCreateMFVideoFormatFromMFMediaType
0x1800e5240  mov     r15d, eax
0x1800e5243  test    eax, eax
0x1800e5245  jns     short loc_1800E5281
0x1800e5247  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e524e  jb      short loc_1800E5273
0x1800e5250  mov     edx, 0Fh
0x1800e5255  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e525c  lea     r8, WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids
0x1800e5263  xor     r9d, r9d
0x1800e5266  mov     dword ptr [rsp+120h+var_100], eax
0x1800e526a  mov     rcx, [rcx+10h]
0x1800e526e  call    WPP_SF_qD
0x1800e5273  lea     rcx, [rbp+57h+var_B8]; void *
0x1800e5277  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e527c  jmp     loc_1800E5410
0x1800e5281  mov     rcx, [rbp+57h+ppMFVF]
0x1800e5285  jmp     short loc_1800E529D
0x1800e5287  mov     rcx, [rbp+57h+var_B8]
0x1800e528b  mov     rax, [rcx]
0x1800e528e  mov     rax, [rax+130h]
0x1800e5295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e529a  mov     rcx, rax; pVideoFormat
0x1800e529d  test    rcx, rcx
0x1800e52a0  jnz     short loc_1800E52B8
0x1800e52a2  mov     eax, 0C00D36B4h
0x1800e52a7  mov     r15d, eax
0x1800e52aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e52b1  jb      short loc_1800E5273
0x1800e52b3  lea     edx, [rcx+10h]
0x1800e52b6  jmp     short loc_1800E5255
0x1800e52b8  mov     dword ptr [r14+8], 0
0x1800e52c0  mov     eax, [rcx+70h]
0x1800e52c3  shr     rax, 13h
0x1800e52c7  and     eax, 1
0x1800e52ca  or      [r14+4], eax
0x1800e52ce  call    cs:__imp_MFGetUncompressedVideoFormat
0x1800e52d4  xor     r8d, r8d
0x1800e52d7  lea     rdx, MF_MT_COMPRESSED
0x1800e52de  mov     rcx, rbx
0x1800e52e1  mov     [r14+0Ch], eax
0x1800e52e5  call    MFGetAttributeUINT32
0x1800e52ea  test    eax, eax
0x1800e52ec  jnz     short loc_1800E5273
0x1800e52ee  mov     edx, [rsi]; dwWidth
0x1800e52f0  test    edx, edx
0x1800e52f2  jz      loc_1800E5273
0x1800e52f8  mov     ecx, [r14+0Ch]; format
0x1800e52fc  lea     r8, [rbp+57h+pStride]; pStride
0x1800e5300  call    cs:__imp_MFGetStrideForBitmapInfoHeader
0x1800e5306  test    eax, eax
0x1800e5308  js      loc_1800E5273
0x1800e530e  cmp     [rbp+57h+pStride], 0
0x1800e5312  jz      loc_1800E5273
0x1800e5318  or      dword ptr [r14+4], 2
0x1800e531d  jmp     loc_1800E5273
0x1800e5322  mov     r8d, 10h; Size
0x1800e5328  lea     rdx, MFMediaType_Image; Buf2
0x1800e532f  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800e5333  call    memcmp_0
0x1800e5338  test    eax, eax
0x1800e533a  jnz     short loc_1800E5349
0x1800e533c  mov     dword ptr [r14+8], 1
0x1800e5344  jmp     loc_1800E5410
0x1800e5349  mov     r8d, 10h; Size
0x1800e534f  lea     rdx, MFMediaType_MultiplexedFrames; Buf2
0x1800e5356  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800e535a  call    memcmp_0
0x1800e535f  test    eax, eax
0x1800e5361  jnz     short loc_1800E5370
0x1800e5363  mov     dword ptr [r14+8], 2
0x1800e536b  jmp     loc_1800E5410
0x1800e5370  mov     r8d, 10h; Size
0x1800e5376  lea     rdx, MFMediaType_Perception; Buf2
0x1800e537d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800e5381  call    memcmp_0
0x1800e5386  test    eax, eax
0x1800e5388  jnz     short loc_1800E5394
0x1800e538a  mov     dword ptr [r14+8], 3
0x1800e5392  jmp     short loc_1800E5410
0x1800e5394  mov     r8d, 10h; Size
0x1800e539a  lea     rdx, MFMediaType_Stream; Buf2
0x1800e53a1  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800e53a5  call    memcmp_0
0x1800e53aa  test    eax, eax
0x1800e53ac  jnz     short loc_1800E53B8
0x1800e53ae  mov     dword ptr [r14+8], 5
0x1800e53b6  jmp     short loc_1800E5410
0x1800e53b8  mov     r8d, 10h; Size
0x1800e53be  lea     rdx, MFMediaType_Metadata; Buf2
0x1800e53c5  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800e53c9  call    memcmp_0
0x1800e53ce  test    eax, eax
0x1800e53d0  jnz     short loc_1800E53DC
0x1800e53d2  mov     dword ptr [r14+8], 4
0x1800e53da  jmp     short loc_1800E5410
0x1800e53dc  mov     eax, 0C00D36B4h
0x1800e53e1  mov     r15d, eax
0x1800e53e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e53eb  jb      short loc_1800E5410
0x1800e53ed  mov     edx, 11h
0x1800e53f2  mov     dword ptr [rsp+120h+var_100], eax
0x1800e53f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e53fd  lea     r8, WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids
0x1800e5404  xor     r9d, r9d
0x1800e5407  mov     rcx, [rcx+10h]
0x1800e540b  call    WPP_SF_qD
0x1800e5410  mov     al, cs:byte_18010EC4D
0x1800e5416  cmp     al, 10h
0x1800e5418  jb      loc_1800E54F2
0x1800e541e  test    rbx, rbx
0x1800e5421  jz      loc_1800E54F2
0x1800e5427  test    r14, r14
0x1800e542a  jz      loc_1800E54F2
0x1800e5430  test    r15d, r15d
0x1800e5433  jns     short loc_1800E5464
0x1800e5435  cmp     al, 1
0x1800e5437  jb      loc_1800E54F2
0x1800e543d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5444  lea     r8, WPP_eb0ef5b3a6393a3215315c852881d531_Traceguids
0x1800e544b  mov     edx, 12h
0x1800e5450  mov     r9d, r15d
0x1800e5453  mov     rcx, [rcx+0D8h]
0x1800e545a  call    WPP_SF_d
0x1800e545f  jmp     loc_1800E54F2
0x1800e5464  mov     rdx, rbx; struct IMFMediaType *
0x1800e5467  lea     rcx, [rbp+57h+var_70]; this
0x1800e546b  call    ??0MediaTypeTracer@@QEAA@PEAUIMFMediaType@@@Z; MediaTypeTracer::MediaTypeTracer(IMFMediaType *)
0x1800e5470  lea     rcx, [rax+8]; this
0x1800e5474  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800e5479  mov     edi, [r14+24h]
0x1800e547d  lea     rcx, [rbp+57h+var_A8]; this
0x1800e5481  mov     esi, [r14+20h]
0x1800e5485  lea     rdx, [r14+10h]; struct _GUID *
0x1800e5489  mov     rbx, rax
0x1800e548c  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800e5491  mov     rcx, rax; this
0x1800e5494  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800e5499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e54a0  mov     r9d, r15d
0x1800e54a3  mov     [rsp+120h+var_C8], rbx; __int64
0x1800e54a8  mov     dword ptr [rsp+120h+var_D0], edi; char
0x1800e54ac  mov     dword ptr [rsp+120h+var_D8], esi; char
0x1800e54b0  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800e54b7  mov     [rsp+120h+var_E0], rax; __int64
0x1800e54bc  mov     eax, [r14+0Ch]
0x1800e54c0  mov     dword ptr [rsp+120h+var_E8], eax; char
0x1800e54c4  mov     eax, [r14+8]
0x1800e54c8  mov     dword ptr [rsp+120h+var_F0], eax; char
0x1800e54cc  mov     eax, [r14+4]
0x1800e54d0  mov     dword ptr [rsp+120h+var_F8], eax; char
0x1800e54d4  mov     eax, [r14]
0x1800e54d7  mov     dword ptr [rsp+120h+var_100], eax; char
0x1800e54db  call    WPP_SF_DDDDDsDDs
0x1800e54e0  lea     rcx, [rbp+57h+var_A8]; this
0x1800e54e4  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800e54e9  lea     rcx, [rbp+57h+var_70]; this
0x1800e54ed  call    ??1MediaTypeTracer@@UEAA@XZ; MediaTypeTracer::~MediaTypeTracer(void)
0x1800e54f2  mov     rcx, [rbp+57h+ppMFVF]; pv
0x1800e54f6  test    rcx, rcx
0x1800e54f9  jz      short loc_1800E5501
0x1800e54fb  call    cs:__imp_CoTaskMemFree
0x1800e5501  mov     eax, r15d
0x1800e5504  mov     rcx, [rbp+57h+var_28]
0x1800e5508  xor     rcx, rsp; StackCookie
0x1800e550b  call    __security_check_cookie
0x1800e5510  lea     r11, [rsp+120h+var_20]
0x1800e5518  mov     rbx, [r11+40h]
0x1800e551c  mov     rsi, [r11+48h]
0x1800e5520  mov     rsp, r11
0x1800e5523  pop     r15
0x1800e5525  pop     r14
0x1800e5527  pop     r12
0x1800e5529  pop     rdi
0x1800e552a  pop     rbp
0x1800e552b  retn
```
