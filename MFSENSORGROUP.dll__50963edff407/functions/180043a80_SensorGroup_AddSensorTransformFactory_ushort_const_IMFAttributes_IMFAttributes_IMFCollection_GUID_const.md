# SensorGroup::AddSensorTransformFactory(ushort const *,IMFAttributes *,IMFAttributes *,IMFCollection *,_GUID const &)

- ea: `0x180043a80`
- end: `0x1800441bb`
- name: `?AddSensorTransformFactory@SensorGroup@@UEAAJPEBGPEAUIMFAttributes@@1PEAUIMFCollection@@AEBU_GUID@@@Z`
- size: `1851`
- prototype: `__int64 __fastcall(SensorGroup *this, const unsigned __int16 *, struct IMFAttributes *, struct IMFAttributes *, struct IMFCollection *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800057e4`
- `0x180005820`
- `0x180005fa0`
- `0x180008f9c`
- `0x180009a20`
- `0x18001bd24`
- `0x18001c854`
- `0x18001c96c`
- `0x1800231c8`
- `0x180023c94`
- `0x18002f4e4`
- `0x180043a80`
- `0x1800441c4`
- `0x180044adc`
- `0x180044f30`
- `0x180077010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043c51`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043c51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044193`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044193`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043acb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043acb`
- `MFPlat!MFCreateAttributes` at `0x180043de3`
- `MFPlat!MFCreateAttributes` at `0x180043de3`

## pseudocode

```c
__int64 __fastcall SensorGroup::AddSensorTransformFactory(
        SensorGroup *this,
        const unsigned __int16 *a2,
        struct IMFAttributes *a3,
        struct IMFAttributes *a4,
        struct IMFCollection *a5,
        const struct _GUID *a6)
{
  int v10; // eax
  int v11; // edi
  __int64 v12; // rdx
  const char *String; // rax
  SensorDeviceId *v14; // rax
  SensorDeviceId *v15; // rax
  SensorDeviceId *v16; // r12
  HRESULT v17; // eax
  __int64 v18; // rdx
  __int64 i; // rdi
  __int64 v20; // rdx
  bool v21; // zf
  struct IMFAttributesVtbl *lpVtbl; // rax
  UINT32 v23; // edx
  __int64 v24; // r15
  __int64 v25; // rdx
  UINT32 cInitialSize; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-85h] BYREF
  struct IMFSensorGroupIdInternal *v29; // [rsp+48h] [rbp-81h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-79h] BYREF
  int v31; // [rsp+58h] [rbp-71h] BYREF
  struct IMFSensorDeviceInternal *v32; // [rsp+60h] [rbp-69h] BYREF
  __int64 v33; // [rsp+68h] [rbp-61h] BYREF
  const unsigned __int16 *v34; // [rsp+70h] [rbp-59h]
  struct IMFCollection *v35; // [rsp+78h] [rbp-51h]
  __int64 v36; // [rsp+80h] [rbp-49h] BYREF
  const struct _GUID *v37; // [rsp+88h] [rbp-41h]
  _BYTE v38[24]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-21h]
  GUID v40; // [rsp+B0h] [rbp-19h] BYREF

  v35 = a5;
  v37 = a6;
  v34 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  ppMFAttributes = 0;
  v33 = 0;
  v29 = 0;
  v32 = 0;
  v31 = 0;
  cInitialSize = 0;
  v36 = 0;
  v40 = GUID_00000000_0000_0000_0000_000000000000;
  if ( !a2 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    if ( g_wppLevels )
    {
      v12 = 78;
      goto LABEL_97;
    }
    goto LABEL_98;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    if ( g_wppLevels )
    {
      v12 = 79;
      goto LABEL_97;
    }
    goto LABEL_98;
  }
  if ( !v35 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    if ( g_wppLevels )
    {
      v12 = 80;
      goto LABEL_97;
    }
    goto LABEL_98;
  }
  v28 = *((_DWORD *)this + 50);
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
  {
    GuidTrace::GuidTrace((GuidTrace *)v38, a6);
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      String = (const char *)v39;
      if ( !v39 )
        String = FSString::GetString((FSString *)v38);
      WPP_SF_qSs(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)a2, (__int64)String);
    }
    FSString::~FSString((FSString *)v38);
  }
  v14 = (SensorDeviceId *)operator new(0x30u);
  if ( v14 )
  {
    v15 = SensorDeviceId::SensorDeviceId(v14);
    v16 = v15;
    if ( v15 )
    {
      v17 = SensorDeviceId::Initialize(v15, a2);
      v11 = v17;
      if ( v17 < 0 )
      {
        if ( g_wppLevels )
        {
          v18 = 83;
          goto LABEL_91;
        }
        goto LABEL_92;
      }
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= v28 )
        {
          v17 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(**((_QWORD **)this + 21) + 48LL))(
                  *((_QWORD *)this + 21),
                  &v40);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 85;
            goto LABEL_91;
          }
          v17 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **))this + 21))(
                  *((_QWORD *)this + 21),
                  &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7,
                  &v29);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 86;
            goto LABEL_91;
          }
          v17 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, const unsigned __int16 *))(*(_QWORD *)v29 + 64LL))(
                  v29,
                  v34);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 87;
            goto LABEL_91;
          }
          v17 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, GUID *))(*(_QWORD *)v29 + 72LL))(
                  v29,
                  &v40);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 88;
            goto LABEL_91;
          }
          v17 = ((__int64 (__fastcall *)(struct IMFAttributes *, UINT32 *))a3->lpVtbl->GetCount)(a3, &cInitialSize);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 89;
            goto LABEL_91;
          }
          if ( a4 )
          {
            lpVtbl = a4->lpVtbl;
            v28 = 0;
            v17 = ((__int64 (__fastcall *)(struct IMFAttributes *, unsigned int *))lpVtbl->GetCount)(a4, &v28);
            v11 = v17;
            if ( v17 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_92;
              v18 = 90;
              goto LABEL_91;
            }
            v23 = v28 + cInitialSize;
            cInitialSize += v28;
          }
          else
          {
            v23 = cInitialSize;
          }
          v17 = MFCreateAttributes(&ppMFAttributes, v23);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 91;
            goto LABEL_91;
          }
          v17 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a3->lpVtbl->CopyAllItems)(
                  a3,
                  ppMFAttributes);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 92;
            goto LABEL_91;
          }
          if ( a4 )
          {
            v17 = MergeAttributes(a4, ppMFAttributes, 1, 0);
            v11 = v17;
            if ( v17 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_92;
              v18 = 93;
              goto LABEL_91;
            }
          }
          v17 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
                  ppMFAttributes,
                  MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE,
                  4);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 94;
            goto LABEL_91;
          }
          v17 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, const struct _GUID *))ppMFAttributes->lpVtbl->SetGUID)(
                  ppMFAttributes,
                  MF_SENSORTRANSFORM_FACTORYCLSID,
                  v37);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 95;
            goto LABEL_91;
          }
          v17 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD))(*(_QWORD *)v29 + 192LL))(
                  v29,
                  14,
                  0);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 96;
            goto LABEL_91;
          }
          v17 = SensorDevice::CreateSensorDeviceInternal(v29, 0, &v32);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 97;
            goto LABEL_91;
          }
          v17 = (*(__int64 (__fastcall **)(struct IMFSensorDeviceInternal *, struct IMFCollection *, const unsigned __int16 *, IMFAttributes *, _QWORD, _QWORD, int *))(*(_QWORD *)v32 + 24LL))(
                  v32,
                  v35,
                  v34,
                  ppMFAttributes,
                  *((unsigned int *)this + 40),
                  0,
                  &v31);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 98;
            goto LABEL_91;
          }
          v17 = (**(__int64 (__fastcall ***)(struct IMFSensorDeviceInternal *, GUID *, __int64 *))v32)(
                  v32,
                  &GUID_fb9f48f2_2a18_4e28_9730_786f30f04dc4,
                  &v33);
          v11 = v17;
          if ( v17 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_92;
            v18 = 99;
            goto LABEL_91;
          }
          if ( (unsigned int)CTUnkArray<IMFSensorDevice>::Add((char *)this + 88, v33) )
          {
            v24 = *((unsigned int *)this + 50);
            if ( (unsigned int)CTEntryArray<SensorDeviceId *>::SetSize((char *)this + 192, (unsigned int)(v24 + 1)) )
            {
              *(_QWORD *)(*((_QWORD *)this + 24) + 8 * v24) = v16;
              (*(void (__fastcall **)(SensorDeviceId *))(*(_QWORD *)v16 + 8LL))(v16);
              v10 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v29 + 192LL))(
                      v29,
                      3,
                      0,
                      &v36,
                      0);
              v11 = v10;
              if ( v10 >= 0 )
              {
                if ( v36 )
                {
                  *(_DWORD *)(v36 + 84) = *((_DWORD *)this + 24);
                  *((_DWORD *)this + 40) += v31;
                  goto LABEL_93;
                }
                v11 = -1072875850;
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    (unsigned int)(v36 + 102),
                    &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
                    (char *)this - 8,
                    -1072875850);
              }
              else
              {
                if ( !g_wppLevels )
                  goto LABEL_98;
                v12 = 101;
LABEL_97:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v12,
                  &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
                  (char *)this - 8,
                  v10);
              }
              goto LABEL_98;
            }
          }
          v17 = -2147024882;
          v11 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_92;
          v18 = 100;
LABEL_91:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v18,
            &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
            (char *)this - 8,
            v17);
LABEL_92:
          (*(void (__fastcall **)(SensorDeviceId *))(*(_QWORD *)v16 + 16LL))(v16);
          if ( v11 < 0 )
            goto LABEL_98;
LABEL_93:
          if ( (unsigned __int8)byte_18008D62D >= 8u )
          {
            v25 = 104;
            goto LABEL_100;
          }
          goto LABEL_101;
        }
        v20 = *((_QWORD *)v16 + 3);
        if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 24) + 8 * i) + 24LL) )
        {
          if ( !v20 )
            continue;
          v21 = (unsigned int)_o__wcsicmp() == 0;
        }
        else
        {
          v21 = v20 == 0;
        }
        if ( v21 )
        {
          v11 = -1072875844;
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              84,
              &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
              (char *)this - 8,
              -1072875844);
          goto LABEL_92;
        }
      }
    }
  }
  v10 = -2147024882;
  v11 = -2147024882;
  if ( g_wppLevels )
  {
    v12 = 82;
    goto LABEL_97;
  }
LABEL_98:
  if ( byte_18008D62D )
  {
    v25 = 103;
LABEL_100:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v25,
      &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
      (char *)this - 8,
      v11);
  }
LABEL_101:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v32);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v29);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v33);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180043a80  push    rbp
0x180043a82  push    rbx
0x180043a83  push    rsi
0x180043a84  push    rdi
0x180043a85  push    r12
0x180043a87  push    r13
0x180043a89  push    r14
0x180043a8b  push    r15
0x180043a8d  lea     rbp, [rsp-0Fh]
0x180043a92  sub     rsp, 0D8h
0x180043a99  mov     rax, cs:__security_cookie
0x180043aa0  xor     rax, rsp
0x180043aa3  mov     [rbp+47h+var_50], rax
0x180043aa7  mov     rax, [rbp+47h+arg_20]
0x180043aab  mov     r14, rcx
0x180043aae  mov     r12, [rbp+47h+arg_28]
0x180043ab2  add     rcx, 18h; lpCriticalSection
0x180043ab6  mov     [rbp+47h+var_98], rax
0x180043aba  mov     r15, r9
0x180043abd  mov     [rbp+47h+var_88], r12
0x180043ac1  mov     r13, r8
0x180043ac4  mov     rdi, rdx
0x180043ac7  mov     [rbp+47h+var_A0], rdx
0x180043acb  call    cs:__imp_EnterCriticalSection
0x180043ad1  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180043ad8  xor     eax, eax
0x180043ada  lea     rsi, [r14-8]
0x180043ade  mov     [rbp+47h+ppMFAttributes], rax
0x180043ae2  mov     [rbp+47h+var_A8], rax
0x180043ae6  mov     [rsp+110h+var_C8], rax
0x180043aeb  mov     [rbp+47h+var_B0], rax
0x180043aef  mov     [rbp+47h+var_B8], eax
0x180043af2  mov     [rsp+110h+cInitialSize], eax
0x180043af6  mov     [rbp+47h+var_90], rax
0x180043afa  movdqu  [rbp+47h+var_60], xmm0
0x180043aff  test    rdi, rdi
0x180043b02  jnz     short loc_180043B22
0x180043b04  mov     eax, 80070057h
0x180043b09  mov     edi, eax
0x180043b0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043b12  jb      loc_18004413B
0x180043b18  mov     edx, 4Eh ; 'N'
0x180043b1d  jmp     loc_18004411D
0x180043b22  test    r13, r13
0x180043b25  jnz     short loc_180043B44
0x180043b27  mov     eax, 80070057h
0x180043b2c  mov     edi, eax
0x180043b2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043b35  jb      loc_18004413B
0x180043b3b  lea     edx, [r13+4Fh]
0x180043b3f  jmp     loc_18004411D
0x180043b44  cmp     [rbp+47h+var_98], rax
0x180043b48  jnz     short loc_180043B68
0x180043b4a  mov     eax, 80070057h
0x180043b4f  mov     edi, eax
0x180043b51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043b58  jb      loc_18004413B
0x180043b5e  mov     edx, 50h ; 'P'
0x180043b63  jmp     loc_18004411D
0x180043b68  cmp     cs:byte_18008D62D, 10h
0x180043b6f  mov     eax, [rsi+0D0h]
0x180043b75  mov     [rsp+110h+var_CC], eax
0x180043b79  jb      short loc_180043BD7
0x180043b7b  mov     rdx, r12; struct _GUID *
0x180043b7e  lea     rcx, [rbp+47h+var_80]; this
0x180043b82  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180043b87  cmp     cs:byte_18008D62D, 8
0x180043b8e  jb      short loc_180043BCE
0x180043b90  mov     rax, [rbp+47h+var_68]
0x180043b94  test    rax, rax
0x180043b97  jnz     short loc_180043BA2
0x180043b99  lea     rcx, [rbp+47h+var_80]; this
0x180043b9d  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180043ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180043ba9  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x180043bb0  mov     [rsp+110h+var_E8], rax; __int64
0x180043bb5  mov     edx, 51h ; 'Q'
0x180043bba  mov     r9, rsi
0x180043bbd  mov     [rsp+110h+var_F0], rdi; __int64
0x180043bc2  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180043bc9  call    WPP_SF_qSs
0x180043bce  lea     rcx, [rbp+47h+var_80]; this
0x180043bd2  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180043bd7  mov     ecx, 30h ; '0'; Size
0x180043bdc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043be1  test    rax, rax
0x180043be4  jz      loc_180044108
0x180043bea  mov     rcx, rax; this
0x180043bed  call    ??0SensorDeviceId@@QEAA@XZ; SensorDeviceId::SensorDeviceId(void)
0x180043bf2  mov     r12, rax
0x180043bf5  test    rax, rax
0x180043bf8  jz      loc_180044108
0x180043bfe  mov     rdx, rdi; unsigned __int16 *
0x180043c01  mov     rcx, rax; this
0x180043c04  call    ?Initialize@SensorDeviceId@@QEAAJPEBG@Z; SensorDeviceId::Initialize(ushort const *)
0x180043c09  mov     edi, eax
0x180043c0b  test    eax, eax
0x180043c0d  jns     short loc_180043C26
0x180043c0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043c16  jb      loc_1800440E4
0x180043c1c  mov     edx, 53h ; 'S'
0x180043c21  jmp     loc_1800440C6
0x180043c26  xor     edi, edi
0x180043c28  cmp     edi, [rsp+110h+var_CC]
0x180043c2c  jnb     short loc_180043C84
0x180043c2e  mov     rax, [r14+0C0h]
0x180043c35  mov     rdx, [r12+18h]
0x180043c3a  mov     rcx, [rax+rdi*8]
0x180043c3e  mov     rcx, [rcx+18h]
0x180043c42  test    rcx, rcx
0x180043c45  jnz     short loc_180043C4C
0x180043c47  test    rdx, rdx
0x180043c4a  jmp     short loc_180043C59
0x180043c4c  test    rdx, rdx
0x180043c4f  jz      short loc_180043C60
0x180043c51  call    cs:__imp__o__wcsicmp
0x180043c57  test    eax, eax
0x180043c59  setz    al
0x180043c5c  test    al, al
0x180043c5e  jnz     short loc_180043C64
0x180043c60  inc     edi
0x180043c62  jmp     short loc_180043C28
0x180043c64  mov     edi, 0C00D36BCh
0x180043c69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043c70  jb      loc_1800440E4
0x180043c76  mov     edx, 54h ; 'T'
0x180043c7b  mov     dword ptr [rsp+110h+var_F0], edi
0x180043c7f  jmp     loc_1800440CA
0x180043c84  mov     rcx, [r14+0A8h]
0x180043c8b  lea     rdx, [rbp+47h+var_60]
0x180043c8f  mov     rax, [rcx]
0x180043c92  mov     rax, [rax+30h]
0x180043c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c9b  mov     edi, eax
0x180043c9d  test    eax, eax
0x180043c9f  jns     short loc_180043CB8
0x180043ca1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043ca8  jb      loc_1800440E4
0x180043cae  mov     edx, 55h ; 'U'
0x180043cb3  jmp     loc_1800440C6
0x180043cb8  mov     rcx, [r14+0A8h]
0x180043cbf  lea     r8, [rsp+110h+var_C8]
0x180043cc4  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180043ccb  mov     rax, [rcx]
0x180043cce  mov     rax, [rax]
0x180043cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cd6  mov     edi, eax
0x180043cd8  test    eax, eax
0x180043cda  jns     short loc_180043CF3
0x180043cdc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043ce3  jb      loc_1800440E4
0x180043ce9  mov     edx, 56h ; 'V'
0x180043cee  jmp     loc_1800440C6
0x180043cf3  mov     rcx, [rsp+110h+var_C8]
0x180043cf8  mov     rdx, [rbp+47h+var_A0]
0x180043cfc  mov     rax, [rcx]
0x180043cff  mov     rax, [rax+40h]
0x180043d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d08  mov     edi, eax
0x180043d0a  test    eax, eax
0x180043d0c  jns     short loc_180043D25
0x180043d0e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043d15  jb      loc_1800440E4
0x180043d1b  mov     edx, 57h ; 'W'
0x180043d20  jmp     loc_1800440C6
0x180043d25  mov     rcx, [rsp+110h+var_C8]
0x180043d2a  lea     rdx, [rbp+47h+var_60]
0x180043d2e  mov     rax, [rcx]
0x180043d31  mov     rax, [rax+48h]
0x180043d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d3a  mov     edi, eax
0x180043d3c  test    eax, eax
0x180043d3e  jns     short loc_180043D57
0x180043d40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043d47  jb      loc_1800440E4
0x180043d4d  mov     edx, 58h ; 'X'
0x180043d52  jmp     loc_1800440C6
0x180043d57  mov     rax, [r13+0]
0x180043d5b  lea     rdx, [rsp+110h+cInitialSize]
0x180043d60  mov     rcx, r13
0x180043d63  mov     rax, [rax+0F0h]
0x180043d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d6f  mov     edi, eax
0x180043d71  test    eax, eax
0x180043d73  jns     short loc_180043D8C
0x180043d75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043d7c  jb      loc_1800440E4
0x180043d82  mov     edx, 59h ; 'Y'
0x180043d87  jmp     loc_1800440C6
0x180043d8c  test    r15, r15
0x180043d8f  jz      short loc_180043DDB
0x180043d91  mov     rax, [r15]
0x180043d94  lea     rdx, [rsp+110h+var_CC]
0x180043d99  mov     rcx, r15
0x180043d9c  mov     [rsp+110h+var_CC], 0
0x180043da4  mov     rax, [rax+0F0h]
0x180043dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043db0  mov     edi, eax
0x180043db2  test    eax, eax
0x180043db4  jns     short loc_180043DCD
0x180043db6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043dbd  jb      loc_1800440E4
0x180043dc3  mov     edx, 5Ah ; 'Z'
0x180043dc8  jmp     loc_1800440C6
0x180043dcd  mov     edx, [rsp+110h+cInitialSize]
0x180043dd1  add     edx, [rsp+110h+var_CC]
0x180043dd5  mov     [rsp+110h+cInitialSize], edx
0x180043dd9  jmp     short loc_180043DDF
0x180043ddb  mov     edx, [rsp+110h+cInitialSize]; cInitialSize
0x180043ddf  lea     rcx, [rbp+47h+ppMFAttributes]; ppMFAttributes
0x180043de3  call    cs:__imp_MFCreateAttributes
0x180043de9  mov     edi, eax
0x180043deb  test    eax, eax
0x180043ded  jns     short loc_180043E06
0x180043def  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043df6  jb      loc_1800440E4
0x180043dfc  mov     edx, 5Bh ; '['
0x180043e01  jmp     loc_1800440C6
0x180043e06  mov     rax, [r13+0]
0x180043e0a  mov     rcx, r13
0x180043e0d  mov     rdx, [rbp+47h+ppMFAttributes]
0x180043e11  mov     rax, [rax+100h]
0x180043e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e1d  mov     edi, eax
0x180043e1f  test    eax, eax
0x180043e21  jns     short loc_180043E3A
0x180043e23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043e2a  jb      loc_1800440E4
0x180043e30  mov     edx, 5Ch ; '\'
0x180043e35  jmp     loc_1800440C6
0x180043e3a  test    r15, r15
0x180043e3d  jz      short loc_180043E6E
0x180043e3f  mov     rdx, [rbp+47h+ppMFAttributes]; struct IMFAttributes *
0x180043e43  xor     r9d, r9d; struct IMFAttributes **
0x180043e46  mov     r8b, 1; bool
0x180043e49  mov     rcx, r15; struct IMFAttributes *
0x180043e4c  call    ?MergeAttributes@@YAJPEAUIMFAttributes@@0_NPEAPEAU1@@Z; MergeAttributes(IMFAttributes *,IMFAttributes *,bool,IMFAttributes * *)
0x180043e51  mov     edi, eax
0x180043e53  test    eax, eax
0x180043e55  jns     short loc_180043E6E
0x180043e57  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043e5e  jb      loc_1800440E4
0x180043e64  mov     edx, 5Dh ; ']'
0x180043e69  jmp     loc_1800440C6
0x180043e6e  mov     rcx, [rbp+47h+ppMFAttributes]
0x180043e72  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE
0x180043e79  mov     r8d, 4
0x180043e7f  mov     rax, [rcx]
0x180043e82  mov     rax, [rax+0A8h]
0x180043e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e8e  mov     edi, eax
0x180043e90  test    eax, eax
0x180043e92  jns     short loc_180043EAB
0x180043e94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043e9b  jb      loc_1800440E4
0x180043ea1  mov     edx, 5Eh ; '^'
0x180043ea6  jmp     loc_1800440C6
0x180043eab  mov     rcx, [rbp+47h+ppMFAttributes]
0x180043eaf  lea     rdx, MF_SENSORTRANSFORM_FACTORYCLSID
0x180043eb6  mov     r8, [rbp+47h+var_88]
0x180043eba  mov     rax, [rcx]
0x180043ebd  mov     rax, [rax+0C0h]
0x180043ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ec9  mov     edi, eax
0x180043ecb  test    eax, eax
0x180043ecd  jns     short loc_180043EE6
0x180043ecf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043ed6  jb      loc_1800440E4
0x180043edc  mov     edx, 5Fh ; '_'
0x180043ee1  jmp     loc_1800440C6
0x180043ee6  mov     rcx, [rsp+110h+var_C8]
0x180043eeb  xor     r9d, r9d
0x180043eee  xor     r8d, r8d
0x180043ef1  mov     [rsp+110h+var_F0], 0
0x180043efa  mov     rax, [rcx]
0x180043efd  lea     edx, [r9+0Eh]
0x180043f01  mov     rax, [rax+0C0h]
0x180043f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f0d  mov     edi, eax
0x180043f0f  test    eax, eax
0x180043f11  jns     short loc_180043F2A
0x180043f13  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043f1a  jb      loc_1800440E4
0x180043f20  mov     edx, 60h ; '`'
0x180043f25  jmp     loc_1800440C6
0x180043f2a  mov     rcx, [rsp+110h+var_C8]; struct IMFSensorGroupIdInternal *
0x180043f2f  lea     r8, [rbp+47h+var_B0]; struct IMFSensorDeviceInternal **
0x180043f33  xor     edx, edx; unsigned __int16 *
0x180043f35  call    ?CreateSensorDeviceInternal@SensorDevice@@SAJPEAUIMFSensorGroupIdInternal@@PEBGPEAPEAUIMFSensorDeviceInternal@@@Z; SensorDevice::CreateSensorDeviceInternal(IMFSensorGroupIdInternal *,ushort const *,IMFSensorDeviceInternal * *)
0x180043f3a  mov     edi, eax
0x180043f3c  test    eax, eax
0x180043f3e  jns     short loc_180043F57
0x180043f40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043f47  jb      loc_1800440E4
0x180043f4d  mov     edx, 61h ; 'a'
0x180043f52  jmp     loc_1800440C6
0x180043f57  mov     rcx, [rbp+47h+var_B0]
0x180043f5b  mov     r9, [rbp+47h+ppMFAttributes]
0x180043f5f  mov     r8, [rbp+47h+var_A0]
0x180043f63  mov     rdx, [rbp+47h+var_98]
  ... truncated ...
```
