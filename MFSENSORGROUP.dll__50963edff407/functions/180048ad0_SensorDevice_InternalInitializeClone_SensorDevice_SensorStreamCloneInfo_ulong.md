# SensorDevice::InternalInitializeClone(SensorDevice *,SensorStreamCloneInfo *,ulong)

- ea: `0x180048ad0`
- end: `0x1800490fc`
- name: `?InternalInitializeClone@SensorDevice@@IEAAJPEAV1@PEAUSensorStreamCloneInfo@@K@Z`
- size: `1580`
- prototype: `__int64 __fastcall(SensorDevice *__hidden this, struct SensorDevice *, struct SensorStreamCloneInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cd18`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x1800099b4`
- `0x18000c2ec`
- `0x18000f5a0`
- `0x1800133fc`
- `0x18001c854`
- `0x18001c96c`
- `0x180028d34`
- `0x180028eb4`
- `0x18002f3cc`
- `0x1800338b0`
- `0x180037220`
- `0x18003ccec`
- `0x180048ad0`
- `0x18004a98c`
- `0x180059200`
- `0x180077010`

## import_xrefs

- `MFPlat!MFGetAttributesAsBlob` at `0x180048ddb`
- `MFPlat!MFGetAttributesAsBlob` at `0x180048ddb`
- `MFPlat!MFCreateAttributes` at `0x180048c4a`
- `MFPlat!MFCreateAttributes` at `0x180048c4a`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180048ca3`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180048ca3`

## pseudocode

```c
__int64 __fastcall SensorDevice::InternalInitializeClone(
        SensorDevice *this,
        struct SensorDevice *a2,
        struct SensorStreamCloneInfo *a3)
{
  int i; // esi
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  HRESULT v11; // eax
  __int64 v12; // rdx
  UINT32 v13; // ebx
  __int64 v14; // rsi
  signed int v15; // r12d
  __int64 j; // r14
  __int64 v17; // rdx
  __int64 v18; // rdx
  void **unique; // rax
  UINT8 *v20; // r14
  char *v21; // r13
  char *v22; // r8
  int v23; // eax
  int v24; // edx
  __int64 v25; // r13
  _OWORD *v26; // rax
  __int64 v27; // rdx
  UINT8 *v28; // rcx
  __int128 v29; // xmm1
  BlobTrace *v30; // rax
  const char *String; // rax
  char v32; // al
  IMFAttributes *v33; // rdx
  __int64 v34; // rdx
  int *v36; // [rsp+28h] [rbp-81h]
  int v37; // [rsp+60h] [rbp-49h] BYREF
  __int64 v38; // [rsp+68h] [rbp-41h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+70h] [rbp-39h] BYREF
  UINT32 pcbBufSize; // [rsp+78h] [rbp-31h] BYREF
  int v41; // [rsp+7Ch] [rbp-2Dh]
  UINT8 *v42; // [rsp+80h] [rbp-29h] BYREF
  int v43; // [rsp+88h] [rbp-21h]
  char *v44; // [rsp+90h] [rbp-19h]
  void **v45; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v46[96]; // [rsp+A0h] [rbp-9h] BYREF
  UINT32 cInitialSize; // [rsp+128h] [rbp+7Fh] BYREF

  v43 = 0;
  cInitialSize = 0;
  v42 = 0;
  pcbBufSize = 0;
  ppMFAttributes = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 27), 166, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, a2, 1);
  for ( i = 0; !i; i = 1 )
  {
    v7 = *((_DWORD *)a2 + 52);
    v38 = 0;
    v8 = SensorStream::CreateSensorStreamFromStream(
           *(_QWORD *)a3,
           0,
           v7,
           *((_QWORD *)a3 + 4),
           (__int64)a3 + 8,
           (SensorStream *)v36,
           &v38);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 167;
LABEL_10:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v8);
      }
LABEL_11:
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v38);
      goto LABEL_67;
    }
    if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((__int64 *)this + 14, v38) )
    {
      v8 = -2147024882;
      v9 = -2147024882;
      if ( g_wppLevels )
      {
        v10 = 168;
        goto LABEL_10;
      }
      goto LABEL_11;
    }
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v38);
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, UINT32 *))(**((_QWORD **)a2 + 12) + 240LL))(
          *((_QWORD *)a2 + 12),
          &cInitialSize);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_67;
    v12 = 169;
    goto LABEL_17;
  }
  v13 = cInitialSize;
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v11 = MFCreateAttributes(&ppMFAttributes, v13);
  v9 = v11;
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, IMFAttributes *))(**((_QWORD **)a2 + 12) + 256LL))(
            *((_QWORD *)a2 + 12),
            ppMFAttributes);
    v9 = v11;
    if ( v11 >= 0 )
    {
      v11 = MFGetAttributesAsBlobSize(ppMFAttributes, &pcbBufSize);
      v9 = v11;
      if ( v11 >= 0 )
      {
        v14 = (int)pcbBufSize;
        if ( pcbBufSize > 0x7FFFFFFF )
        {
          v9 = -2147024362;
          if ( g_wppLevels )
          {
            v18 = 173;
LABEL_66:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v18,
              &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
              this,
              v9);
          }
        }
        else
        {
          if ( (int)pcbBufSize < 2147483063 )
          {
            v15 = pcbBufSize + 584;
            for ( j = 0; (unsigned int)j < *((_DWORD *)this + 30); j = (unsigned int)(j + 1) )
            {
              v17 = *((_QWORD *)this + 14);
              v37 = 0;
              v11 = SensorDevice::SerializeStreamAttributes(
                      this,
                      *(struct IMFAttributes **)(v17 + 8 * j),
                      j,
                      0,
                      0,
                      &v37);
              v9 = v11;
              if ( v11 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_67;
                v12 = 175;
                goto LABEL_17;
              }
              if ( v37 < 0 )
              {
                v9 = -1072875845;
                if ( !g_wppLevels )
                  goto LABEL_67;
                v18 = 176;
                goto LABEL_66;
              }
              v15 += v37;
            }
            unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v38, v15);
            wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
              (void **)&v42,
              unique);
            wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v38);
            v20 = v42;
            if ( v42 )
            {
              v21 = (char *)(v42 + 584);
              v11 = MFGetAttributesAsBlob(ppMFAttributes, v42 + 584, v14);
              v9 = v11;
              if ( v11 >= 0 )
              {
                v22 = &v21[v14];
                v44 = &v21[v14];
                v23 = v15 - v14 - 584;
                v24 = 0;
                LODWORD(v38) = v23;
                v25 = 0;
                while ( 1 )
                {
                  v41 = v24;
                  if ( (unsigned int)v25 >= *((_DWORD *)this + 30) )
                    break;
                  v37 = 0;
                  if ( v23 - v24 <= 0 )
                  {
                    v11 = -2147024888;
                    v9 = -2147024888;
                    if ( !g_wppLevels )
                      goto LABEL_67;
                    v12 = 179;
                    goto LABEL_17;
                  }
                  v11 = SensorDevice::SerializeStreamAttributes(
                          this,
                          *(struct IMFAttributes **)(*((_QWORD *)this + 14) + 8 * v25),
                          v25,
                          (unsigned __int8 *)&v22[v24],
                          v23 - v24,
                          &v37);
                  v9 = v11;
                  if ( v11 < 0 )
                  {
                    if ( !g_wppLevels )
                      goto LABEL_67;
                    v12 = 180;
                    goto LABEL_17;
                  }
                  v24 = v37 + v41;
                  v23 = v38;
                  v25 = (unsigned int)(v25 + 1);
                  v22 = v44;
                }
                v26 = (_OWORD *)*((_QWORD *)a2 + 10);
                v27 = 4;
                v28 = v20;
                do
                {
                  *(_OWORD *)v28 = *v26;
                  *((_OWORD *)v28 + 1) = v26[1];
                  *((_OWORD *)v28 + 2) = v26[2];
                  *((_OWORD *)v28 + 3) = v26[3];
                  *((_OWORD *)v28 + 4) = v26[4];
                  *((_OWORD *)v28 + 5) = v26[5];
                  *((_OWORD *)v28 + 6) = v26[6];
                  v29 = v26[7];
                  v26 += 8;
                  *((_OWORD *)v28 + 7) = v29;
                  v28 += 128;
                  --v27;
                }
                while ( v27 );
                *(_OWORD *)v28 = *v26;
                *((_OWORD *)v28 + 1) = v26[1];
                *((_OWORD *)v28 + 2) = v26[2];
                *((_OWORD *)v28 + 3) = v26[3];
                *((_QWORD *)v28 + 8) = *((_QWORD *)v26 + 8);
                *((_DWORD *)v20 + 4) = v15;
                *((_DWORD *)v20 + 5) = v14;
                *((_DWORD *)v20 + 6) = *((_DWORD *)this + 30);
                if ( (unsigned __int8)byte_18008D62D < 8u )
                {
                  v32 = v43;
                }
                else
                {
                  v30 = BlobTrace::BlobTrace((BlobTrace *)&v45, v20 + 552, 0x20u);
                  String = FSString::GetString((BlobTrace *)((char *)v30 + 8));
                  WPP_SF_qiiddddSs(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    *(_QWORD *)v20,
                    *((_QWORD *)v20 + 1),
                    *((_DWORD *)v20 + 4),
                    *((_DWORD *)v20 + 5),
                    *((_DWORD *)v20 + 6),
                    *((_DWORD *)v20 + 7),
                    (__int64)(v20 + 32),
                    (__int64)String);
                  v32 = 1;
                }
                if ( (v32 & 1) != 0 )
                {
                  v45 = &BlobTrace::`vftable';
                  FSString::~FSString((FSString *)v46);
                }
                v33 = ppMFAttributes;
                *((_QWORD *)this + 20) = *((_QWORD *)a2 + 20);
                *((_DWORD *)this + 44) = -1;
                *((_DWORD *)this + 45) = -1;
                *((_DWORD *)this + 51) = -1;
                *((_QWORD *)this + 23) = 0;
                *((_QWORD *)this + 24) = 0;
                *((_WORD *)this + 100) = 1;
                *((_WORD *)this + 112) = 257;
                *((_DWORD *)this + 52) = *((_DWORD *)a2 + 52);
                *((_DWORD *)this + 18) = *((_DWORD *)a2 + 18);
                ComSmartPtr<IMFCameraProfileValidation>::operator=((_QWORD *)this + 12, (__int64)v33);
                wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::swap(
                  (char *)this + 80,
                  &v42);
                *((_DWORD *)this + 22) = v15;
                if ( (unsigned __int8)byte_18008D62D >= 8u )
                {
                  v34 = 183;
                  goto LABEL_69;
                }
                goto LABEL_70;
              }
              if ( !g_wppLevels )
                goto LABEL_67;
              v12 = 178;
            }
            else
            {
              v11 = -2147024882;
              v9 = -2147024882;
              if ( !g_wppLevels )
                goto LABEL_67;
              v12 = 177;
            }
            goto LABEL_17;
          }
          v11 = -2147024888;
          v9 = -2147024888;
          if ( g_wppLevels )
          {
            v12 = 174;
            goto LABEL_17;
          }
        }
      }
      else if ( g_wppLevels )
      {
        v12 = 172;
        goto LABEL_17;
      }
    }
    else if ( g_wppLevels )
    {
      v12 = 171;
      goto LABEL_17;
    }
  }
  else if ( g_wppLevels )
  {
    v12 = 170;
LABEL_17:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v11);
  }
LABEL_67:
  if ( byte_18008D62D )
  {
    v34 = 182;
LABEL_69:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v34, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v9);
  }
LABEL_70:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v42);
  return v9;
}

```

## disassembly

```asm
0x180048ad0  mov     [rsp-8+cInitialSize], r9d
0x180048ad5  push    rbp
0x180048ad6  push    rbx
0x180048ad7  push    rsi
0x180048ad8  push    rdi
0x180048ad9  push    r12
0x180048adb  push    r13
0x180048add  push    r14
0x180048adf  push    r15
0x180048ae1  lea     rbp, [rsp-1Fh]
0x180048ae6  sub     rsp, 0C8h
0x180048aed  xor     r12d, r12d
0x180048af0  mov     r14, r8
0x180048af3  mov     [rbp+57h+var_78], r12d
0x180048af7  mov     r15, rdx
0x180048afa  mov     [rbp+57h+cInitialSize], r12d
0x180048afe  mov     rdi, rcx
0x180048b01  mov     [rbp+57h+var_80], r12
0x180048b05  mov     [rbp+57h+pcbBufSize], r12d
0x180048b09  mov     [rbp+57h+ppMFAttributes], r12
0x180048b0d  cmp     cs:byte_18008D62D, 8
0x180048b14  lea     r13d, [r12+1]
0x180048b19  jb      short loc_180048B47
0x180048b1b  mov     r9, rcx
0x180048b1e  mov     dword ptr [rsp+100h+var_D8], r13d
0x180048b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b2a  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x180048b31  mov     edx, 0A6h
0x180048b36  mov     qword ptr [rsp+100h+var_E0], r15
0x180048b3b  mov     rcx, [rcx+0D8h]
0x180048b42  call    WPP_SF_qqD
0x180048b47  mov     esi, r12d
0x180048b4a  cmp     esi, r13d
0x180048b4d  jnb     loc_180048C00
0x180048b53  mov     r8d, [r15+0D0h]
0x180048b5a  lea     rdx, [rbp+57h+var_98]
0x180048b5e  mov     qword ptr [rsp+100h+var_D0], rdx
0x180048b63  mov     edx, esi
0x180048b65  mov     eax, esi
0x180048b67  mov     [rbp+57h+var_98], r12
0x180048b6b  lea     rcx, [rax+rax*4]
0x180048b6f  mov     r9, [r14+rcx*8+20h]
0x180048b74  lea     rax, [r14+8]
0x180048b78  lea     rax, [rax+rcx*8]
0x180048b7c  mov     rcx, [r14+rcx*8]
0x180048b80  mov     qword ptr [rsp+100h+var_E0], rax
0x180048b85  call    ?CreateSensorStreamFromStream@SensorStream@@SAJPEAUIMFSensorStream@@KJPEAUIMFAttributes@@AEAV?$CTUnkArray@UIMFMediaType@@@@AEBU_GUID@@PEAPEAX@Z; SensorStream::CreateSensorStreamFromStream(IMFSensorStream *,ulong,long,IMFAttributes *,CTUnkArray<IMFMediaType> &,_GUID const &,void * *)
0x180048b8a  mov     ebx, eax
0x180048b8c  test    eax, eax
0x180048b8e  js      short loc_180048BF0
0x180048b90  mov     rdx, [rbp+57h+var_98]
0x180048b94  lea     rcx, [rdi+70h]
0x180048b98  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x180048b9d  test    eax, eax
0x180048b9f  jz      short loc_180048BAF
0x180048ba1  lea     rcx, [rbp+57h+var_98]
0x180048ba5  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180048baa  add     esi, r13d
0x180048bad  jmp     short loc_180048B4A
0x180048baf  mov     eax, 8007000Eh
0x180048bb4  mov     ebx, eax
0x180048bb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048bbd  jb      short loc_180048BE2
0x180048bbf  mov     edx, 0A8h
0x180048bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180048bcb  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x180048bd2  mov     r9, rdi
0x180048bd5  mov     dword ptr [rsp+100h+var_E0], eax
0x180048bd9  mov     rcx, [rcx+10h]
0x180048bdd  call    WPP_SF_qD
0x180048be2  lea     rcx, [rbp+57h+var_98]
0x180048be6  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180048beb  jmp     loc_1800490A5
0x180048bf0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048bf7  jb      short loc_180048BE2
0x180048bf9  mov     edx, 0A7h
0x180048bfe  jmp     short loc_180048BC4
0x180048c00  mov     rcx, [r15+60h]
0x180048c04  lea     rdx, [rbp+57h+cInitialSize]
0x180048c08  mov     rax, [rcx]
0x180048c0b  mov     rax, [rax+0F0h]
0x180048c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c17  mov     ebx, eax
0x180048c19  test    eax, eax
0x180048c1b  jns     short loc_180048C38
0x180048c1d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048c24  jb      loc_1800490A5
0x180048c2a  mov     edx, 0A9h
0x180048c2f  mov     dword ptr [rsp+100h+var_E0], eax
0x180048c33  jmp     loc_18004908B
0x180048c38  mov     ebx, [rbp+57h+cInitialSize]
0x180048c3b  lea     rcx, [rbp+57h+ppMFAttributes]
0x180048c3f  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x180048c44  mov     edx, ebx; cInitialSize
0x180048c46  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x180048c4a  call    cs:__imp_MFCreateAttributes
0x180048c50  mov     ebx, eax
0x180048c52  test    eax, eax
0x180048c54  jns     short loc_180048C6A
0x180048c56  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048c5d  jb      loc_1800490A5
0x180048c63  mov     edx, 0AAh
0x180048c68  jmp     short loc_180048C2F
0x180048c6a  mov     rcx, [r15+60h]
0x180048c6e  mov     rdx, [rbp+57h+ppMFAttributes]
0x180048c72  mov     rax, [rcx]
0x180048c75  mov     rax, [rax+100h]
0x180048c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c81  mov     ebx, eax
0x180048c83  test    eax, eax
0x180048c85  jns     short loc_180048C9B
0x180048c87  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048c8e  jb      loc_1800490A5
0x180048c94  mov     edx, 0ABh
0x180048c99  jmp     short loc_180048C2F
0x180048c9b  mov     rcx, [rbp+57h+ppMFAttributes]; pAttributes
0x180048c9f  lea     rdx, [rbp+57h+pcbBufSize]; pcbBufSize
0x180048ca3  call    cs:__imp_MFGetAttributesAsBlobSize
0x180048ca9  mov     ebx, eax
0x180048cab  test    eax, eax
0x180048cad  jns     short loc_180048CC6
0x180048caf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048cb6  jb      loc_1800490A5
0x180048cbc  mov     edx, 0ACh
0x180048cc1  jmp     loc_180048C2F
0x180048cc6  movsxd  rsi, [rbp+57h+pcbBufSize]
0x180048cca  cmp     esi, 7FFFFFFFh
0x180048cd0  ja      loc_180049074
0x180048cd6  cmp     esi, 7FFFFDB7h
0x180048cdc  jl      short loc_180048CFC
0x180048cde  mov     eax, 80070008h
0x180048ce3  mov     ebx, eax
0x180048ce5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048cec  jb      loc_1800490A5
0x180048cf2  mov     edx, 0AEh
0x180048cf7  jmp     loc_180048C2F
0x180048cfc  lea     r12d, [rsi+248h]
0x180048d03  xor     r14d, r14d
0x180048d06  cmp     r14d, [rdi+78h]
0x180048d0a  jnb     short loc_180048D82
0x180048d0c  mov     rdx, [rdi+70h]
0x180048d10  lea     rcx, [rbp+57h+var_A0]
0x180048d14  mov     [rsp+100h+var_D8], rcx; int *
0x180048d19  xor     r9d, r9d; unsigned __int8 *
0x180048d1c  mov     r8d, r14d; unsigned int
0x180048d1f  mov     [rbp+57h+var_A0], 0
0x180048d26  mov     rcx, rdi; this
0x180048d29  mov     dword ptr [rsp+100h+var_E0], 0; int
0x180048d31  mov     rdx, [rdx+r14*8]; struct IMFAttributes *
0x180048d35  call    ?SerializeStreamAttributes@SensorDevice@@IEAAJPEAUIMFAttributes@@KPEAEJPEAJ@Z; SensorDevice::SerializeStreamAttributes(IMFAttributes *,ulong,uchar *,long,long *)
0x180048d3a  mov     ebx, eax
0x180048d3c  test    eax, eax
0x180048d3e  js      short loc_180048D6B
0x180048d40  mov     eax, [rbp+57h+var_A0]
0x180048d43  test    eax, eax
0x180048d45  js      short loc_180048D4F
0x180048d47  add     r12d, eax
0x180048d4a  add     r14d, r13d
0x180048d4d  jmp     short loc_180048D06
0x180048d4f  mov     ebx, 0C00D36BBh
0x180048d54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048d5b  jb      loc_1800490A5
0x180048d61  mov     edx, 0B0h
0x180048d66  jmp     loc_180049087
0x180048d6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048d72  jb      loc_1800490A5
0x180048d78  mov     edx, 0AFh
0x180048d7d  jmp     loc_180048C2F
0x180048d82  movsxd  rdx, r12d
0x180048d85  lea     rcx, [rbp+57h+var_98]
0x180048d89  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180048d8e  mov     rdx, rax
0x180048d91  lea     rcx, [rbp+57h+var_80]
0x180048d95  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180048d9a  lea     rcx, [rbp+57h+var_98]
0x180048d9e  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180048da3  mov     r14, [rbp+57h+var_80]
0x180048da7  test    r14, r14
0x180048daa  jnz     short loc_180048DCA
0x180048dac  mov     eax, 8007000Eh
0x180048db1  mov     ebx, eax
0x180048db3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048dba  jb      loc_1800490A5
0x180048dc0  mov     edx, 0B1h
0x180048dc5  jmp     loc_180048C2F
0x180048dca  mov     rcx, [rbp+57h+ppMFAttributes]; pAttributes
0x180048dce  lea     r13, [r14+248h]
0x180048dd5  mov     rdx, r13; pBuf
0x180048dd8  mov     r8d, esi; cbBufSize
0x180048ddb  call    cs:__imp_MFGetAttributesAsBlob
0x180048de1  mov     ebx, eax
0x180048de3  test    eax, eax
0x180048de5  jns     short loc_180048E04
0x180048de7  mov     r13d, 1
0x180048ded  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048df4  jb      loc_1800490A5
0x180048dfa  mov     edx, 0B2h
0x180048dff  jmp     loc_180048C2F
0x180048e04  lea     r8, [rsi+r13]
0x180048e08  mov     eax, r12d
0x180048e0b  sub     eax, esi
0x180048e0d  mov     [rbp+57h+var_70], r8
0x180048e11  sub     eax, 248h
0x180048e16  xor     edx, edx
0x180048e18  mov     dword ptr [rbp+57h+var_98], eax
0x180048e1b  xor     r13d, r13d
0x180048e1e  mov     [rbp+57h+var_84], edx
0x180048e21  cmp     r13d, [rdi+78h]
0x180048e25  jnb     loc_180048EB9
0x180048e2b  mov     ecx, eax
0x180048e2d  mov     [rbp+57h+var_A0], 0
0x180048e34  sub     ecx, edx
0x180048e36  test    ecx, ecx
0x180048e38  jle     short loc_180048E95
0x180048e3a  movsxd  r9, edx
0x180048e3d  mov     rdx, [rdi+70h]
0x180048e41  add     r9, r8; unsigned __int8 *
0x180048e44  lea     r8, [rbp+57h+var_A0]
0x180048e48  mov     [rsp+100h+var_D8], r8; int *
0x180048e4d  mov     r8d, r13d; unsigned int
0x180048e50  mov     dword ptr [rsp+100h+var_E0], ecx; int
0x180048e54  mov     rcx, rdi; this
0x180048e57  mov     rdx, [rdx+r13*8]; struct IMFAttributes *
0x180048e5b  call    ?SerializeStreamAttributes@SensorDevice@@IEAAJPEAUIMFAttributes@@KPEAEJPEAJ@Z; SensorDevice::SerializeStreamAttributes(IMFAttributes *,ulong,uchar *,long,long *)
0x180048e60  mov     ebx, eax
0x180048e62  test    eax, eax
0x180048e64  js      short loc_180048E78
0x180048e66  mov     edx, [rbp+57h+var_84]
0x180048e69  add     edx, [rbp+57h+var_A0]
0x180048e6c  mov     eax, dword ptr [rbp+57h+var_98]
0x180048e6f  inc     r13d
0x180048e72  mov     r8, [rbp+57h+var_70]
0x180048e76  jmp     short loc_180048E1E
0x180048e78  mov     r13d, 1
0x180048e7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048e85  jb      loc_1800490A5
0x180048e8b  mov     edx, 0B4h
0x180048e90  jmp     loc_180048C2F
0x180048e95  mov     eax, 80070008h
0x180048e9a  mov     ebx, eax
0x180048e9c  mov     r13d, 1
0x180048ea2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180048ea9  jb      loc_1800490A5
0x180048eaf  mov     edx, 0B3h
0x180048eb4  jmp     loc_180048C2F
0x180048eb9  mov     rax, [r15+50h]
0x180048ebd  mov     edx, 4
0x180048ec2  mov     rcx, r14
0x180048ec5  lea     r8d, [rdx+7Ch]
0x180048ec9  movups  xmm0, xmmword ptr [rax]
0x180048ecc  movups  xmmword ptr [rcx], xmm0
0x180048ecf  movups  xmm1, xmmword ptr [rax+10h]
0x180048ed3  movups  xmmword ptr [rcx+10h], xmm1
0x180048ed7  movups  xmm0, xmmword ptr [rax+20h]
0x180048edb  movups  xmmword ptr [rcx+20h], xmm0
0x180048edf  movups  xmm1, xmmword ptr [rax+30h]
0x180048ee3  movups  xmmword ptr [rcx+30h], xmm1
0x180048ee7  movups  xmm0, xmmword ptr [rax+40h]
0x180048eeb  movups  xmmword ptr [rcx+40h], xmm0
0x180048eef  movups  xmm1, xmmword ptr [rax+50h]
0x180048ef3  movups  xmmword ptr [rcx+50h], xmm1
0x180048ef7  movups  xmm0, xmmword ptr [rax+60h]
0x180048efb  movups  xmmword ptr [rcx+60h], xmm0
0x180048eff  movups  xmm1, xmmword ptr [rax+70h]
0x180048f03  add     rax, r8
0x180048f06  movups  xmmword ptr [rcx+70h], xmm1
0x180048f0a  add     rcx, r8
0x180048f0d  sub     rdx, 1
0x180048f11  jnz     short loc_180048EC9
0x180048f13  movups  xmm0, xmmword ptr [rax]
0x180048f16  movups  xmmword ptr [rcx], xmm0
0x180048f19  movups  xmm1, xmmword ptr [rax+10h]
0x180048f1d  movups  xmmword ptr [rcx+10h], xmm1
0x180048f21  movups  xmm0, xmmword ptr [rax+20h]
0x180048f25  movups  xmmword ptr [rcx+20h], xmm0
0x180048f29  movups  xmm1, xmmword ptr [rax+30h]
0x180048f2d  movups  xmmword ptr [rcx+30h], xmm1
0x180048f31  mov     rax, [rax+40h]
0x180048f35  mov     [rcx+40h], rax
0x180048f39  mov     [r14+10h], r12d
0x180048f3d  mov     [r14+14h], esi
0x180048f41  mov     eax, [rdi+78h]
0x180048f44  mov     [r14+18h], eax
0x180048f48  cmp     cs:byte_18008D62D, 8
0x180048f4f  jb      short loc_180048FCC
0x180048f51  lea     rdx, [r14+228h]; void *
0x180048f58  mov     r8d, 20h ; ' '; unsigned int
0x180048f5e  lea     rcx, [rbp+57h+var_68]; this
0x180048f62  call    ??0BlobTrace@@QEAA@PEAXK@Z; BlobTrace::BlobTrace(void *,ulong)
0x180048f67  lea     rcx, [rax+8]; this
0x180048f6b  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180048f70  mov     [rsp+100h+var_A8], rax; __int64
0x180048f75  lea     rcx, [r14+20h]
0x180048f79  mov     eax, [r14+1Ch]
0x180048f7d  mov     r9, rdi
0x180048f80  mov     [rsp+100h+var_B0], rcx; __int64
0x180048f85  mov     rcx, cs:WPP_GLOBAL_Control
0x180048f8c  mov     dword ptr [rsp+100h+var_B8], eax; char
0x180048f90  mov     eax, [r14+18h]
0x180048f94  mov     dword ptr [rsp+100h+var_C0], eax; char
  ... truncated ...
```
