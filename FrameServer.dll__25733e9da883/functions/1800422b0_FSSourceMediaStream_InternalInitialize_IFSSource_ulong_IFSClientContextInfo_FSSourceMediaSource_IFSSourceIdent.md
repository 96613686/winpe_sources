# FSSourceMediaStream::InternalInitialize(IFSSource *,ulong,IFSClientContextInfo *,FSSourceMediaSource *,IFSSourceIdentity *)

- ea: `0x1800422b0`
- end: `0x180042a4f`
- name: `?InternalInitialize@FSSourceMediaStream@@MEAAJPEAUIFSSource@@KPEAUIFSClientContextInfo@@PEAVFSSourceMediaSource@@PEAUIFSSourceIdentity@@@Z`
- size: `1951`
- prototype: `int(FSSourceMediaStream *__hidden this, struct IFSSource *, unsigned int, struct IFSClientContextInfo *, struct FSSourceMediaSource *, struct IFSSourceIdentity *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800041f0`
- `0x180004f20`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000a880`
- `0x18000ad10`
- `0x180017ccc`
- `0x180017d90`
- `0x180018998`
- `0x180024200`
- `0x1800270fc`
- `0x1800422b0`
- `0x180045680`
- `0x180045ea8`
- `0x18004d714`
- `0x18004d748`
- `0x18004db3c`
- `0x18004db80`
- `0x18004f37c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800429b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800429b1`
- `MFPlat!MFCreateAttributes` at `0x1800423ed`
- `MFPlat!MFCreateAttributes` at `0x1800423ed`
- `MFPlat!MFCreateEventQueue` at `0x18004239d`
- `MFPlat!MFCreateEventQueue` at `0x18004239d`
- `MFPlat!MFCreateStreamDescriptor` at `0x18004269f`
- `MFPlat!MFCreateStreamDescriptor` at `0x18004269f`

## pseudocode

```c
__int64 __fastcall FSSourceMediaStream::InternalInitialize(
        FSSourceMediaStream *this,
        struct IFSSource *a2,
        __int64 a3,
        struct IFSClientContextInfo *a4,
        struct FSSourceMediaSource *a5,
        struct IFSSourceIdentity *a6)
{
  unsigned int v6; // r15d
  unsigned int v8; // r12d
  int v11; // edi
  IMFMediaType **v12; // r13
  FSString *v13; // rax
  const char *String; // rax
  HRESULT v15; // eax
  const struct std::nothrow_t *v16; // rdx
  int v17; // ebx
  __int64 v18; // rdx
  __int64 (__fastcall *v19)(struct IFSSource *, _QWORD, __int64 *); // rbx
  __int64 v20; // rdx
  int v21; // eax
  struct IMFMediaType *v22; // rdx
  MediaTypeTracer *v23; // rax
  const char *v24; // rax
  IMFStreamDescriptor *v25; // rcx
  GUID *v26; // rbx
  bool v27; // al
  IMFStreamDescriptor *v28; // rcx
  IMFStreamDescriptor *v29; // rdi
  HRESULT (__stdcall *SetUINT32)(IMFStreamDescriptor *, const GUID *const, UINT32); // rbx
  unsigned int v31; // eax
  bool v32; // bl
  IMFStreamDescriptor *v33; // rcx
  __int64 v34; // rdi
  struct IFSSourceIdentity *v35; // rcx
  DWORD v36; // eax
  _QWORD *v37; // rcx
  DWORD v38; // eax
  DWORD i; // edi
  __int64 v40; // rdx
  __int64 v41; // rdx
  DWORD dwStreamIdentifier; // [rsp+40h] [rbp-79h] BYREF
  struct IMFMediaType *v44; // [rsp+48h] [rbp-71h] BYREF
  IMFStreamDescriptor *ppDescriptor; // [rsp+50h] [rbp-69h] BYREF
  IMFMediaType **v46; // [rsp+58h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-59h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+68h] [rbp-51h] BYREF
  __int64 v49; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v50[24]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v51[112]; // [rsp+90h] [rbp-29h] BYREF
  DWORD cMediaTypes; // [rsp+110h] [rbp+57h] BYREF
  struct IFSClientContextInfo *v53; // [rsp+128h] [rbp+6Fh]

  v53 = a4;
  v6 = 0;
  v8 = a3;
  ppMFAttributes = 0;
  v49 = 0;
  ppDescriptor = 0;
  v11 = 0;
  pv = 0;
  v12 = 0;
  cMediaTypes = 0;
  dwStreamIdentifier = -1;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    WPP_SF_qqdq(*((_QWORD *)WPP_GLOBAL_Control + 27), a2, a3, this, a2, a3, a5);
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v13 = ClientContextInfoTrace::ClientContextInfoTrace((ClientContextInfoTrace *)v50, a4);
      String = FSString::GetString(v13);
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        87,
        (unsigned int)&WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids,
        (_DWORD)this,
        (__int64)String);
      v11 = 1;
    }
  }
  if ( (v11 & 1) != 0 )
  {
    v11 &= ~1u;
    FSString::~FSString((FSString *)v50, a2);
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 104);
  v15 = MFCreateEventQueue((IMFMediaEventQueue **)this + 13);
  v17 = v15;
  if ( v15 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v18 = 88;
    goto LABEL_9;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v15 = MFCreateAttributes(&ppMFAttributes, 0);
  v17 = v15;
  if ( v15 >= 0 )
  {
    v19 = *(__int64 (__fastcall **)(struct IFSSource *, _QWORD, __int64 *))(*(_QWORD *)a2 + 72LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v49);
    v15 = v19(a2, v8, &v49);
    v17 = v15;
    if ( v15 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(struct IFSSource *, _QWORD, DWORD *, LPVOID *))(*(_QWORD *)a2 + 80LL))(
              a2,
              v8,
              &cMediaTypes,
              &pv);
      v17 = v15;
      if ( v15 >= 0 )
      {
        v46 = (IMFMediaType **)operator new[](saturated_mul(cMediaTypes, 8u));
        v12 = v46;
        if ( v46 )
        {
          if ( cMediaTypes )
          {
            while ( 1 )
            {
              v44 = 0;
              v21 = FSCloneMediaType(*((struct IMFMediaType **)pv + v6), &v44);
              v17 = v21;
              if ( v21 < 0 )
                break;
              ((void (__fastcall *)(struct IMFMediaType *, __int64 *))v44->lpVtbl->DeleteItem)(
                v44,
                MF_MT_FSSourceTypeDecoded);
              ((void (__fastcall *)(struct IMFMediaType *, __int64 *))v44->lpVtbl->DeleteItem)(
                v44,
                MF_MT_SENSORSTREAM_PIPELINEMT_FLAGS);
              ((void (__fastcall *)(struct IMFMediaType *, __int64 *))v44->lpVtbl->DeleteItem)(
                v44,
                FSMediaType_CompressedPassthrough);
              if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((__int64)this + 216, (__int64)v44) )
              {
                v17 = -2147024882;
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    94,
                    &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids,
                    this,
                    -2147024882);
                goto LABEL_39;
              }
              v22 = v44;
              v46[v6] = v44;
              if ( (unsigned __int8)byte_18010EC4D >= 8u )
              {
                v11 |= 2u;
                v23 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v51, v22);
                v24 = FSString::GetString((MediaTypeTracer *)((char *)v23 + 8));
                WPP_SF_qDs(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  95,
                  (unsigned int)&WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids,
                  (_DWORD)this,
                  v6,
                  (__int64)v24);
              }
              if ( (v11 & 2) != 0 )
              {
                v11 &= ~2u;
                MediaTypeTracer::~MediaTypeTracer((MediaTypeTracer *)v51);
              }
              wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v44);
              if ( ++v6 >= cMediaTypes )
              {
                v12 = v46;
                goto LABEL_32;
              }
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                93,
                &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids,
                this,
                v21);
LABEL_39:
            wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v44);
            v12 = v46;
            goto LABEL_78;
          }
LABEL_32:
          v15 = (*(__int64 (__fastcall **)(struct IFSSource *, _QWORD, DWORD *))(*(_QWORD *)a2 + 432LL))(
                  a2,
                  v8,
                  &dwStreamIdentifier);
          v17 = v15;
          if ( v15 < 0 )
          {
            if ( g_wppLevels )
            {
              v18 = 96;
              goto LABEL_9;
            }
            goto LABEL_78;
          }
          v25 = ppDescriptor;
          ppDescriptor = 0;
          if ( v25 )
            ((void (__fastcall *)(IMFStreamDescriptor *))v25->lpVtbl->Release)(v25);
          v15 = MFCreateStreamDescriptor(dwStreamIdentifier, cMediaTypes, v12, &ppDescriptor);
          v17 = v15;
          if ( v15 < 0 )
          {
            if ( g_wppLevels )
            {
              v18 = 97;
              goto LABEL_9;
            }
            goto LABEL_78;
          }
          v26 = (GUID *)((char *)this + 152);
          if ( (*(int (__fastcall **)(__int64, const IID *, char *))(*(_QWORD *)v49 + 80LL))(
                 v49,
                 &MF_DEVICESTREAM_STREAM_CATEGORY,
                 (char *)this + 152) < 0 )
            *v26 = GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba;
          v27 = *(_QWORD *)&v26->Data1 == *(_QWORD *)&GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data1
             && *((_QWORD *)this + 20) == *(_QWORD *)GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data4
             || *(_QWORD *)&v26->Data1 == *(_QWORD *)&GUID_fb6c428a_0353_11d1_905f_0000c0cc16ba.Data1
             && *((_QWORD *)this + 20) == *(_QWORD *)GUID_fb6c428a_0353_11d1_905f_0000c0cc16ba.Data4;
          v28 = ppDescriptor;
          *((_BYTE *)this + 337) = v27;
          v15 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, const IID *, char *))v28->lpVtbl->SetGUID)(
                  v28,
                  &MF_DEVICESTREAM_STREAM_CATEGORY,
                  (char *)this + 152);
          v17 = v15;
          if ( v15 < 0 )
          {
            if ( g_wppLevels )
            {
              v18 = 98;
              goto LABEL_9;
            }
            goto LABEL_78;
          }
          v29 = ppDescriptor;
          SetUINT32 = ppDescriptor->lpVtbl->SetUINT32;
          v31 = MFGetAttributeUINT32(v49, MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES, 1);
          v15 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, __int64 *, _QWORD))SetUINT32)(
                  v29,
                  MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES,
                  v31);
          v17 = v15;
          if ( v15 < 0 )
          {
            if ( g_wppLevels )
            {
              v18 = 99;
              goto LABEL_9;
            }
            goto LABEL_78;
          }
          v15 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, IMFAttributes *))ppDescriptor->lpVtbl->CopyAllItems)(
                  ppDescriptor,
                  ppMFAttributes);
          v17 = v15;
          if ( v15 < 0 )
          {
            if ( g_wppLevels )
            {
              v18 = 100;
              goto LABEL_9;
            }
            goto LABEL_78;
          }
          v15 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
                  ppMFAttributes,
                  &MF_DEVICESTREAM_STREAM_ID,
                  dwStreamIdentifier);
          v17 = v15;
          if ( v15 < 0 )
          {
            if ( g_wppLevels )
            {
              v18 = 101;
              goto LABEL_9;
            }
            goto LABEL_78;
          }
          v46 = 0;
          v32 = *(_QWORD *)utl::list<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,utl::allocator<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>>::insert(
                             (char *)this + 248,
                             &v44,
                             *((_QWORD *)this + 31),
                             &v46) == 0;
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v46);
          if ( !v32 )
          {
            v15 = (*(__int64 (__fastcall **)(struct IFSSource *, _QWORD, _QWORD, unsigned __int64, char *))(*(_QWORD *)a2 + 152LL))(
                    a2,
                    v8,
                    0,
                    ((unsigned __int64)this + 32) & -(__int64)(this != 0),
                    (char *)this + 144);
            v17 = v15;
            if ( v15 >= 0 )
            {
              v33 = ppDescriptor;
              v34 = *((_QWORD *)this + 24);
              *((_QWORD *)this + 24) = ppDescriptor;
              if ( v33 )
                ((void (__fastcall *)(IMFStreamDescriptor *))v33->lpVtbl->AddRef)(v33);
              if ( v34 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(
                (__int64 *)this + 30,
                (__int64)ppMFAttributes);
              wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(
                (__int64 *)this + 16,
                (__int64)a5);
              wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(
                (__int64 *)this + 14,
                (__int64)a2);
              wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(
                (__int64 *)this + 15,
                (__int64)v53);
              v35 = a6;
              v36 = dwStreamIdentifier;
              *((_DWORD *)this + 34) = v8;
              *((_DWORD *)this + 35) = v36;
              if ( v35 && (*(unsigned int (__fastcall **)(struct IFSSourceIdentity *))(*(_QWORD *)v35 + 24LL))(v35) == 4 )
                *((_BYTE *)this + 440) = 1;
            }
            else if ( g_wppLevels )
            {
              v18 = 103;
              goto LABEL_9;
            }
            goto LABEL_78;
          }
          v17 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_78;
          v20 = 102;
        }
        else
        {
          v17 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_78;
          v20 = 92;
        }
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v20,
          &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids,
          this,
          -2147024882);
        goto LABEL_78;
      }
      if ( g_wppLevels )
      {
        v18 = 91;
        goto LABEL_9;
      }
    }
    else if ( g_wppLevels )
    {
      v18 = 90;
      goto LABEL_9;
    }
  }
  else if ( g_wppLevels )
  {
    v18 = 89;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids, this, v15);
  }
LABEL_78:
  v37 = pv;
  if ( pv )
  {
    v38 = cMediaTypes;
    for ( i = 0; i < v38; ++i )
    {
      v40 = v37[i];
      if ( v40 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40 + 16LL))(v37[i]);
        *((_QWORD *)pv + i) = 0;
        v37 = pv;
        v38 = cMediaTypes;
      }
    }
    CoTaskMemFree(v37);
    pv = 0;
  }
  if ( v12 )
    operator delete(v12, v16);
  if ( v17 >= 0 )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v41 = 105;
      goto LABEL_91;
    }
  }
  else if ( byte_18010EC4D )
  {
    v41 = 104;
LABEL_91:
    WPP_SF_qddd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v41,
      &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids,
      this,
      v17,
      dwStreamIdentifier,
      v8);
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppDescriptor);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v49);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800422b0  mov     [rsp-8+arg_8], rbx
0x1800422b5  mov     [rsp-8+arg_18], r9
0x1800422ba  push    rbp
0x1800422bb  push    rsi
0x1800422bc  push    rdi
0x1800422bd  push    r12
0x1800422bf  push    r13
0x1800422c1  push    r14
0x1800422c3  push    r15
0x1800422c5  lea     rbp, [rsp-17h]
0x1800422ca  sub     rsp, 0D0h
0x1800422d1  xor     r15d, r15d
0x1800422d4  mov     rbx, r9
0x1800422d7  mov     [rbp+47h+cMediaTypes], r15d
0x1800422db  mov     r12d, r8d
0x1800422de  mov     [rbp+47h+ppMFAttributes], r15
0x1800422e2  mov     r14, rdx
0x1800422e5  mov     [rbp+47h+var_90], r15
0x1800422e9  mov     rsi, rcx
0x1800422ec  mov     [rbp+47h+ppDescriptor], r15
0x1800422f0  mov     edi, r15d
0x1800422f3  mov     [rbp+47h+pv], r15
0x1800422f7  mov     r13d, r15d
0x1800422fa  mov     [rbp+47h+cMediaTypes], r15d
0x1800422fe  mov     [rbp+47h+dwStreamIdentifier], 0FFFFFFFFh
0x180042305  cmp     cs:byte_18010EC4D, 8
0x18004230c  jb      short loc_18004237E
0x18004230e  mov     rax, [rbp+47h+arg_20]
0x180042312  mov     r9, rcx
0x180042315  mov     rcx, cs:WPP_GLOBAL_Control
0x18004231c  mov     [rsp+100h+var_D0], rax
0x180042321  mov     dword ptr [rsp+100h+var_D8], r8d
0x180042326  mov     [rsp+100h+var_E0], rdx
0x18004232b  mov     rcx, [rcx+0D8h]
0x180042332  call    WPP_SF_qqdq
0x180042337  cmp     cs:byte_18010EC4D, 8
0x18004233e  jb      short loc_18004237E
0x180042340  mov     rdx, rbx; struct IFSClientContextInfo *
0x180042343  lea     rcx, [rbp+47h+var_88]; this
0x180042347  call    ??0ClientContextInfoTrace@@QEAA@PEAUIFSClientContextInfo@@@Z; ClientContextInfoTrace::ClientContextInfoTrace(IFSClientContextInfo *)
0x18004234c  mov     rcx, rax; this
0x18004234f  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180042354  mov     rcx, cs:WPP_GLOBAL_Control
0x18004235b  lea     edx, [r15+57h]
0x18004235f  mov     r9, rsi
0x180042362  mov     [rsp+100h+var_E0], rax
0x180042367  lea     r8, WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids
0x18004236e  mov     rcx, [rcx+0D8h]
0x180042375  call    WPP_SF_qs
0x18004237a  lea     edi, [r15+1]
0x18004237e  test    dil, 1
0x180042382  jz      short loc_180042390
0x180042384  and     edi, 0FFFFFFFEh
0x180042387  lea     rcx, [rbp+47h+var_88]; this
0x18004238b  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180042390  lea     rcx, [rsi+68h]
0x180042394  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180042399  lea     rcx, [rsi+68h]; ppMediaEventQueue
0x18004239d  call    cs:__imp_MFCreateEventQueue
0x1800423a3  mov     ebx, eax
0x1800423a5  test    eax, eax
0x1800423a7  jns     short loc_1800423DE
0x1800423a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800423b0  jb      loc_18004296E
0x1800423b6  mov     edx, 58h ; 'X'
0x1800423bb  mov     dword ptr [rsp+100h+var_E0], eax
0x1800423bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423c6  lea     r8, WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids
0x1800423cd  mov     r9, rsi
0x1800423d0  mov     rcx, [rcx+10h]
0x1800423d4  call    WPP_SF_qD
0x1800423d9  jmp     loc_18004296E
0x1800423de  lea     rcx, [rbp+47h+ppMFAttributes]
0x1800423e2  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800423e7  xor     edx, edx; cInitialSize
0x1800423e9  lea     rcx, [rbp+47h+ppMFAttributes]; ppMFAttributes
0x1800423ed  call    cs:__imp_MFCreateAttributes
0x1800423f3  mov     ebx, eax
0x1800423f5  test    eax, eax
0x1800423f7  jns     short loc_18004240D
0x1800423f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042400  jb      loc_18004296E
0x180042406  mov     edx, 59h ; 'Y'
0x18004240b  jmp     short loc_1800423BB
0x18004240d  mov     rax, [r14]
0x180042410  lea     rcx, [rbp+47h+var_90]
0x180042414  mov     rbx, [rax+48h]
0x180042418  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18004241d  lea     r8, [rbp+47h+var_90]
0x180042421  mov     edx, r12d
0x180042424  mov     rcx, r14
0x180042427  mov     rax, rbx
0x18004242a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004242f  mov     ebx, eax
0x180042431  test    eax, eax
0x180042433  jns     short loc_18004244C
0x180042435  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004243c  jb      loc_18004296E
0x180042442  mov     edx, 5Ah ; 'Z'
0x180042447  jmp     loc_1800423BB
0x18004244c  mov     rax, [r14]
0x18004244f  lea     r9, [rbp+47h+pv]
0x180042453  lea     r8, [rbp+47h+cMediaTypes]
0x180042457  mov     edx, r12d
0x18004245a  mov     rcx, r14
0x18004245d  mov     rax, [rax+50h]
0x180042461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042466  mov     ebx, eax
0x180042468  test    eax, eax
0x18004246a  jns     short loc_180042483
0x18004246c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042473  jb      loc_18004296E
0x180042479  mov     edx, 5Bh ; '['
0x18004247e  jmp     loc_1800423BB
0x180042483  mov     ecx, [rbp+47h+cMediaTypes]
0x180042486  mov     eax, 8
0x18004248b  mul     rcx
0x18004248e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180042495  cmovb   rax, rcx
0x180042499  mov     rcx, rax; unsigned __int64
0x18004249c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800424a1  mov     [rbp+47h+var_A8], rax
0x1800424a5  mov     r13, rax
0x1800424a8  test    rax, rax
0x1800424ab  jnz     short loc_1800424CD
0x1800424ad  mov     ecx, 8007000Eh
0x1800424b2  mov     ebx, ecx
0x1800424b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800424bb  jb      loc_18004296E
0x1800424c1  lea     edx, [rax+5Ch]
0x1800424c4  mov     dword ptr [rsp+100h+var_E0], ecx
0x1800424c8  jmp     loc_1800423BF
0x1800424cd  cmp     [rbp+47h+cMediaTypes], r15d
0x1800424d1  jbe     loc_1800425E5
0x1800424d7  mov     rcx, [rbp+47h+pv]
0x1800424db  lea     rdx, [rbp+47h+var_B8]; struct IMFMediaType **
0x1800424df  mov     [rbp+47h+var_B8], 0
0x1800424e7  mov     r13d, r15d
0x1800424ea  mov     rcx, [rcx+r13*8]; struct IMFMediaType *
0x1800424ee  call    ?FSCloneMediaType@@YAJPEAUIMFMediaType@@PEAPEAU1@@Z; FSCloneMediaType(IMFMediaType *,IMFMediaType * *)
0x1800424f3  mov     ebx, eax
0x1800424f5  test    eax, eax
0x1800424f7  js      loc_180042638
0x1800424fd  mov     rcx, [rbp+47h+var_B8]
0x180042501  lea     rdx, MF_MT_FSSourceTypeDecoded
0x180042508  mov     rax, [rcx]
0x18004250b  mov     rax, [rax+98h]
0x180042512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042517  mov     rcx, [rbp+47h+var_B8]
0x18004251b  lea     rdx, MF_MT_SENSORSTREAM_PIPELINEMT_FLAGS
0x180042522  mov     rax, [rcx]
0x180042525  mov     rax, [rax+98h]
0x18004252c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042531  mov     rcx, [rbp+47h+var_B8]
0x180042535  lea     rdx, FSMediaType_CompressedPassthrough
0x18004253c  mov     rax, [rcx]
0x18004253f  mov     rax, [rax+98h]
0x180042546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004254b  mov     rdx, [rbp+47h+var_B8]
0x18004254f  lea     rcx, [rsi+0D8h]
0x180042556  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x18004255b  test    eax, eax
0x18004255d  jz      loc_18004261D
0x180042563  mov     rax, [rbp+47h+var_A8]
0x180042567  mov     rdx, [rbp+47h+var_B8]; struct IMFMediaType *
0x18004256b  mov     [rax+r13*8], rdx
0x18004256f  cmp     cs:byte_18010EC4D, 8
0x180042576  jb      short loc_1800425B9
0x180042578  lea     rcx, [rbp+47h+var_70]; this
0x18004257c  or      edi, 2
0x18004257f  call    ??0MediaTypeTracer@@QEAA@PEAUIMFMediaType@@@Z; MediaTypeTracer::MediaTypeTracer(IMFMediaType *)
0x180042584  lea     rcx, [rax+8]; this
0x180042588  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18004258d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042594  lea     r8, WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids
0x18004259b  mov     [rsp+100h+var_D8], rax
0x1800425a0  mov     edx, 5Fh ; '_'
0x1800425a5  mov     r9, rsi
0x1800425a8  mov     dword ptr [rsp+100h+var_E0], r15d
0x1800425ad  mov     rcx, [rcx+0D8h]
0x1800425b4  call    WPP_SF_qDs
0x1800425b9  test    dil, 2
0x1800425bd  jz      short loc_1800425CB
0x1800425bf  and     edi, 0FFFFFFFDh
0x1800425c2  lea     rcx, [rbp+47h+var_70]; this
0x1800425c6  call    ??1MediaTypeTracer@@UEAA@XZ; MediaTypeTracer::~MediaTypeTracer(void)
0x1800425cb  lea     rcx, [rbp+47h+var_B8]; void *
0x1800425cf  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800425d4  inc     r15d
0x1800425d7  cmp     r15d, [rbp+47h+cMediaTypes]
0x1800425db  jb      loc_1800424D7
0x1800425e1  mov     r13, [rbp+47h+var_A8]
0x1800425e5  mov     rax, [r14]
0x1800425e8  lea     r8, [rbp+47h+dwStreamIdentifier]
0x1800425ec  mov     edx, r12d
0x1800425ef  mov     rcx, r14
0x1800425f2  mov     rax, [rax+1B0h]
0x1800425f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425fe  xor     r15d, r15d
0x180042601  mov     ebx, eax
0x180042603  test    eax, eax
0x180042605  jns     short loc_180042679
0x180042607  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004260e  jb      loc_18004296E
0x180042614  lea     edx, [r15+60h]
0x180042618  jmp     loc_1800423BB
0x18004261d  mov     ecx, 8007000Eh
0x180042622  mov     ebx, ecx
0x180042624  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004262b  jb      short loc_180042664
0x18004262d  mov     edx, 5Eh ; '^'
0x180042632  mov     dword ptr [rsp+100h+var_E0], ecx
0x180042636  jmp     short loc_18004264A
0x180042638  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004263f  jb      short loc_180042664
0x180042641  mov     edx, 5Dh ; ']'
0x180042646  mov     dword ptr [rsp+100h+var_E0], eax
0x18004264a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042651  lea     r8, WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids
0x180042658  mov     r9, rsi
0x18004265b  mov     rcx, [rcx+10h]
0x18004265f  call    WPP_SF_qD
0x180042664  lea     rcx, [rbp+47h+var_B8]; void *
0x180042668  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18004266d  mov     r13, [rbp+47h+var_A8]
0x180042671  xor     r15d, r15d
0x180042674  jmp     loc_18004296E
0x180042679  mov     rcx, [rbp+47h+ppDescriptor]
0x18004267d  mov     [rbp+47h+ppDescriptor], r15
0x180042681  test    rcx, rcx
0x180042684  jz      short loc_180042692
0x180042686  mov     rax, [rcx]
0x180042689  mov     rax, [rax+10h]
0x18004268d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042692  mov     edx, [rbp+47h+cMediaTypes]; cMediaTypes
0x180042695  lea     r9, [rbp+47h+ppDescriptor]; ppDescriptor
0x180042699  mov     ecx, [rbp+47h+dwStreamIdentifier]; dwStreamIdentifier
0x18004269c  mov     r8, r13; apMediaTypes
0x18004269f  call    cs:__imp_MFCreateStreamDescriptor
0x1800426a5  mov     ebx, eax
0x1800426a7  test    eax, eax
0x1800426a9  jns     short loc_1800426C2
0x1800426ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800426b2  jb      loc_18004296E
0x1800426b8  mov     edx, 61h ; 'a'
0x1800426bd  jmp     loc_1800423BB
0x1800426c2  mov     rcx, [rbp+47h+var_90]
0x1800426c6  lea     rbx, [rsi+98h]
0x1800426cd  mov     r8, rbx
0x1800426d0  lea     rdx, MF_DEVICESTREAM_STREAM_CATEGORY
0x1800426d7  mov     rax, [rcx]
0x1800426da  mov     rax, [rax+50h]
0x1800426de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426e3  test    eax, eax
0x1800426e5  jns     short loc_1800426F2
0x1800426e7  movups  xmm0, xmmword ptr cs:_GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba.Data1
0x1800426ee  movdqu  xmmword ptr [rbx], xmm0
0x1800426f2  mov     rax, [rbx]
0x1800426f5  cmp     rax, qword ptr cs:_GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data1
0x1800426fc  jnz     short loc_18004270B
0x1800426fe  mov     rax, [rbx+8]
0x180042702  cmp     rax, qword ptr cs:_GUID_38a0cd98_d49b_4ce8_b48a_344667a17830.Data4
0x180042709  jz      short loc_180042724
0x18004270b  mov     rax, [rbx]
0x18004270e  cmp     rax, qword ptr cs:_GUID_fb6c428a_0353_11d1_905f_0000c0cc16ba.Data1
0x180042715  jnz     short loc_180042728
0x180042717  mov     rax, [rbx+8]
0x18004271b  cmp     rax, qword ptr cs:_GUID_fb6c428a_0353_11d1_905f_0000c0cc16ba.Data4
0x180042722  jnz     short loc_180042728
0x180042724  mov     al, 1
0x180042726  jmp     short loc_18004272B
0x180042728  mov     al, r15b
0x18004272b  mov     rcx, [rbp+47h+ppDescriptor]
0x18004272f  lea     rdx, MF_DEVICESTREAM_STREAM_CATEGORY
0x180042736  mov     [rsi+151h], al
0x18004273c  mov     r8, rbx
0x18004273f  mov     rax, [rcx]
0x180042742  mov     rax, [rax+0C0h]
0x180042749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004274e  mov     ebx, eax
0x180042750  test    eax, eax
0x180042752  jns     short loc_18004276B
0x180042754  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004275b  jb      loc_18004296E
0x180042761  mov     edx, 62h ; 'b'
0x180042766  jmp     loc_1800423BB
0x18004276b  mov     rdi, [rbp+47h+ppDescriptor]
0x18004276f  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES
0x180042776  mov     rcx, [rbp+47h+var_90]
0x18004277a  mov     r8d, 1
0x180042780  mov     rax, [rdi]
0x180042783  mov     rbx, [rax+0A8h]
0x18004278a  call    MFGetAttributeUINT32
0x18004278f  mov     r8d, eax
0x180042792  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES
0x180042799  mov     rax, rbx
0x18004279c  mov     rcx, rdi
0x18004279f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427a4  mov     ebx, eax
0x1800427a6  test    eax, eax
  ... truncated ...
```
