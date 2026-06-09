# FSNotificationToMediaEvent(__MIDL___MIDL_itf_fsclienttypes_0000_0000_0015 const &,IMFMediaEvent * *)

- ea: `0x180055d3c`
- end: `0x180056354`
- name: `?FSNotificationToMediaEvent@@YAJAEBU__MIDL___MIDL_itf_fsclienttypes_0000_0000_0015@@PEAPEAUIMFMediaEvent@@@Z`
- size: `1560`
- prototype: `__int64 __fastcall(const struct __MIDL___MIDL_itf_fsclienttypes_0000_0000_0015 *, struct IMFMediaEvent **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b5710`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009cc0`
- `0x180017bb4`
- `0x1800552b8`
- `0x180055d3c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056328`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056328`
- `MFPlat!MFCreateMediaEvent` at `0x180055e59`
- `MFPlat!MFCreateMediaEvent` at `0x180055f4d`
- `MFPlat!MFCreateMediaEvent` at `0x18005600d`
- `MFPlat!MFCreateMediaEvent` at `0x18005626e`
- `MFPlat!MFCreateMediaEvent` at `0x180055e59`
- `MFPlat!MFCreateMediaEvent` at `0x180055f4d`
- `MFPlat!MFCreateMediaEvent` at `0x18005600d`
- `MFPlat!MFCreateMediaEvent` at `0x18005626e`

## pseudocode

```c
__int64 __fastcall FSNotificationToMediaEvent(
        const struct __MIDL___MIDL_itf_fsclienttypes_0000_0000_0015 *a1,
        struct IMFMediaEvent **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  MediaEventType v6; // esi
  HRESULT v7; // r14d
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // r8
  VARTYPE v28; // cx
  GUID v29; // xmm0
  __int64 v30; // rdx
  IMFMediaEvent *ppEvent; // [rsp+30h] [rbp-40h] BYREF
  struct tagPROPVARIANT pvValue; // [rsp+38h] [rbp-38h] BYREF
  GUID guidExtendedType; // [rsp+50h] [rbp-20h] BYREF

  guidExtendedType = GUID_00000000_0000_0000_0000_000000000000;
  ppEvent = 0;
  memset(&pvValue, 0, sizeof(pvValue));
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 119, &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids);
  if ( !a2 )
  {
    v4 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_90;
    v5 = 120;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids, 0, v4);
LABEL_90:
    if ( byte_18010EC4D )
    {
      v30 = 136;
LABEL_94:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v30,
        &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids,
        (unsigned int)v4);
      goto LABEL_95;
    }
    goto LABEL_95;
  }
  v4 = 0;
  v6 = 0;
  *a2 = 0;
  v7 = 0;
  v8 = *(_DWORD *)a1;
  if ( *(int *)a1 > 6 )
  {
    v15 = v8 - 7;
    if ( !v15 || (v16 = v15 - 1) == 0 )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
      v13 = MFCreateMediaEvent(2u, &MF_DEVICESOURCE_EXCLUSIVECONTROL_STATUS_CHANGED, 0, 0, &ppEvent);
      v4 = v13;
      if ( v13 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_90;
        v14 = 121;
        goto LABEL_85;
      }
      v13 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, bool))ppEvent->lpVtbl->SetUINT32)(
              ppEvent,
              &MF_DEVSOURCE_ATTRIBUTE_EXCLUSIVECONTROL_ACQUIRED,
              *(_DWORD *)a1 == 7);
      v4 = v13;
      if ( v13 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_90;
        v14 = 122;
LABEL_85:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids, 0, v13);
        goto LABEL_90;
      }
      goto LABEL_16;
    }
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( !v18 )
      {
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
        v13 = MFCreateMediaEvent(2u, &MF_DEVICESOURCE_MT_CHANGEREQUEST, 0, 0, &ppEvent);
        v4 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_90;
          v14 = 123;
          goto LABEL_85;
        }
        v13 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, _QWORD))ppEvent->lpVtbl->SetUINT64)(
                ppEvent,
                &MF_STREAM_DEVICECONTROL_SOURCETOKEN,
                *((_QWORD *)a1 + 1));
        v4 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_90;
          v14 = 124;
          goto LABEL_85;
        }
        v13 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, _QWORD))ppEvent->lpVtbl->SetUINT64)(
                ppEvent,
                &MF_DEVICESOURCE_MT_CHANGEREQUEST_TOKEN,
                *((_QWORD *)a1 + 3));
        v4 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_90;
          v14 = 125;
          goto LABEL_85;
        }
        v13 = ((__int64 (__fastcall *)(IMFMediaEvent *, const IID *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
                ppEvent,
                &MF_DEVICESTREAM_STREAM_ID,
                *((unsigned int *)a1 + 10));
        v4 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_90;
          v14 = 126;
          goto LABEL_85;
        }
        v13 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
                ppEvent,
                &MF_DEVICESOURCE_CHANGEREQUEST_MEDIATYPEINDEX,
                *((unsigned int *)a1 + 11));
        v4 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_90;
          v14 = 127;
          goto LABEL_85;
        }
        goto LABEL_16;
      }
      if ( v18 == 1 )
      {
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
        v13 = MFCreateMediaEvent(2u, &MF_DEVICESOURCE_MT_CHANGEREQUEST_COMPLETED, 0, 0, &ppEvent);
        v4 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_90;
          v14 = 128;
          goto LABEL_85;
        }
        v13 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, _QWORD))ppEvent->lpVtbl->SetUINT64)(
                ppEvent,
                &MF_DEVICESOURCE_MT_CHANGEREQUEST_TOKEN,
                *((_QWORD *)a1 + 3));
        v4 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_90;
          v14 = 129;
          goto LABEL_85;
        }
        v13 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
                ppEvent,
                &MF_DEVICESOURCE_MT_CHANGEREQUEST_APPROVE,
                *((unsigned int *)a1 + 4));
        v4 = v13;
        if ( v13 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_90;
          v14 = 130;
          goto LABEL_85;
        }
        goto LABEL_16;
      }
      goto LABEL_30;
    }
    v20 = *((_DWORD *)a1 + 4);
    v7 = *((_DWORD *)a1 + 5);
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( !v21 )
      {
        v6 = 1;
        goto LABEL_16;
      }
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( v26 )
              {
                if ( v26 == 1 )
                {
                  if ( *((_WORD *)a1 + 13) > 0x1F2u )
                  {
                    v4 = -2147024809;
                    if ( !g_wppLevels )
                      goto LABEL_90;
                    v5 = 131;
                    goto LABEL_6;
                  }
                  v27 = *((unsigned __int16 *)a1 + 13);
                  v28 = *((_WORD *)a1 + 12);
                  guidExtendedType = (GUID)MF_FRAMESERVER_VCAMEVENT_EXTENDED_CUSTOM_EVENT;
                  v13 = FSBlobToPropVariant(v28, (unsigned __int8 *)a1 + 28, v27, &pvValue);
                  v4 = v13;
                  if ( v13 < 0 )
                  {
                    if ( !g_wppLevels )
                      goto LABEL_90;
                    v14 = 132;
                    goto LABEL_85;
                  }
                  v6 = 2;
                  goto LABEL_16;
                }
                goto LABEL_79;
              }
              v29 = (GUID)MF_FRAMESERVER_VCAMEVENT_EXTENDED_PIPELINE_SHUTDOWN;
            }
            else
            {
              v29 = (GUID)MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_UNINITIALIZE;
            }
          }
          else
          {
            v29 = (GUID)MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_STOP;
          }
        }
        else
        {
          v29 = (GUID)MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_START;
        }
      }
      else
      {
        v29 = (GUID)MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_INITIALIZE;
      }
      v6 = 2;
      guidExtendedType = v29;
      goto LABEL_16;
    }
LABEL_79:
    v6 = 1;
    guidExtendedType = GUID_00000000_0000_0000_0000_000000000000;
    if ( v7 < 0 )
      goto LABEL_16;
    v7 = -1072875845;
    if ( !byte_18010EC4D )
      goto LABEL_16;
    v19 = 133;
LABEL_32:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v19, &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids, 3222091451LL);
    goto LABEL_16;
  }
  if ( v8 != 6 )
  {
    if ( !v8 )
    {
      v7 = -1072875845;
      goto LABEL_16;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      v7 = *((_DWORD *)a1 + 4);
      v6 = 1;
      goto LABEL_16;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      v6 = 800;
      v7 = -1072873822;
      goto LABEL_16;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v6 = 801;
      v7 = -1072873821;
      goto LABEL_16;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v6 = 950;
      pvValue.vt = 19;
      pvValue.lVal = *((_DWORD *)a1 + 4);
      goto LABEL_16;
    }
    if ( v12 != 1 )
    {
LABEL_30:
      v6 = 1;
      v7 = -1072875845;
      if ( !byte_18010EC4D )
        goto LABEL_16;
      v19 = 134;
      goto LABEL_32;
    }
  }
LABEL_16:
  if ( !ppEvent )
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
    v13 = MFCreateMediaEvent(v6, &guidExtendedType, v7, (const PROPVARIANT *)&pvValue, &ppEvent);
    v4 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_90;
      v14 = 135;
      goto LABEL_85;
    }
  }
  *a2 = ppEvent;
  ppEvent = 0;
  if ( v4 < 0 )
    goto LABEL_90;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v30 = 137;
    goto LABEL_94;
  }
LABEL_95:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppEvent);
  PropVariantClear((PROPVARIANT *)&pvValue);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180055d3c  mov     [rsp-38h+arg_10], rbx
0x180055d41  push    rbp
0x180055d42  push    rsi
0x180055d43  push    rdi
0x180055d44  push    r12
0x180055d46  push    r13
0x180055d48  push    r14
0x180055d4a  push    r15
0x180055d4c  mov     rbp, rsp
0x180055d4f  sub     rsp, 70h
0x180055d53  mov     rax, cs:__security_cookie
0x180055d5a  xor     rax, rsp
0x180055d5d  mov     [rbp+var_10], rax
0x180055d61  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180055d68  xor     eax, eax
0x180055d6a  xorps   xmm1, xmm1
0x180055d6d  mov     [rbp+var_28], rax
0x180055d71  movdqu  xmmword ptr [rbp+guidExtendedType.Data1], xmm0
0x180055d76  mov     [rbp+var_40], rax
0x180055d7a  mov     r12, rdx
0x180055d7d  movups  xmmword ptr [rbp+pvValue], xmm1
0x180055d81  mov     r15, rcx
0x180055d84  cmp     cs:byte_18010EC4D, 8
0x180055d8b  lea     r13, WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids
0x180055d92  jb      short loc_180055DAD
0x180055d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d9b  lea     edx, [rax+77h]
0x180055d9e  mov     r8, r13
0x180055da1  mov     rcx, [rcx+0D8h]
0x180055da8  call    WPP_SF_
0x180055dad  test    r12, r12
0x180055db0  jnz     short loc_180055DEB
0x180055db2  mov     ebx, 80004003h
0x180055db7  lea     edi, [r12+1]
0x180055dbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180055dc3  jb      loc_1800562E4
0x180055dc9  lea     edx, [rdi+77h]
0x180055dcc  mov     dword ptr [rsp+70h+ppEvent], ebx
0x180055dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180055dd7  xor     r9d, r9d
0x180055dda  mov     r8, r13
0x180055ddd  mov     rcx, [rcx+10h]
0x180055de1  call    WPP_SF_qD
0x180055de6  jmp     loc_1800562E4
0x180055deb  xor     ebx, ebx
0x180055ded  xor     esi, esi
0x180055def  mov     [r12], rbx
0x180055df3  xor     r14d, r14d
0x180055df6  mov     ecx, [r15]
0x180055df9  lea     edi, [rbx+1]
0x180055dfc  cmp     ecx, 6
0x180055dff  jg      loc_180055ECA
0x180055e05  jz      short loc_180055E2F
0x180055e07  test    ecx, ecx
0x180055e09  jz      loc_180055EBF
0x180055e0f  sub     ecx, edi
0x180055e11  jz      loc_180055EB4
0x180055e17  sub     ecx, edi
0x180055e19  jz      loc_180055EA4
0x180055e1f  sub     ecx, edi
0x180055e21  jz      short loc_180055E97
0x180055e23  sub     ecx, edi
0x180055e25  jz      short loc_180055E80
0x180055e27  cmp     ecx, edi
0x180055e29  jnz     loc_180055EEF
0x180055e2f  cmp     [rbp+var_40], 0
0x180055e34  jnz     loc_1800562D0
0x180055e3a  lea     rcx, [rbp+var_40]
0x180055e3e  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180055e43  lea     rax, [rbp+var_40]
0x180055e47  mov     r8d, r14d; hrStatus
0x180055e4a  lea     r9, [rbp+pvValue]; pvValue
0x180055e4e  mov     [rsp+70h+ppEvent], rax; ppEvent
0x180055e53  lea     rdx, [rbp+guidExtendedType]; guidExtendedType
0x180055e57  mov     ecx, esi; met
0x180055e59  call    cs:__imp_MFCreateMediaEvent
0x180055e5f  mov     ebx, eax
0x180055e61  test    eax, eax
0x180055e63  jns     loc_1800562D0
0x180055e69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180055e70  jb      loc_1800562E4
0x180055e76  mov     edx, 87h
0x180055e7b  jmp     loc_180056288
0x180055e80  mov     eax, 13h
0x180055e85  mov     esi, 3B6h
0x180055e8a  mov     word ptr [rbp+pvValue], ax
0x180055e8e  mov     eax, [r15+10h]
0x180055e92  mov     dword ptr [rbp+pvValue+8], eax
0x180055e95  jmp     short loc_180055E2F
0x180055e97  mov     esi, 321h
0x180055e9c  mov     r14d, 0C00D3EA3h
0x180055ea2  jmp     short loc_180055E2F
0x180055ea4  mov     esi, 320h
0x180055ea9  mov     r14d, 0C00D3EA2h
0x180055eaf  jmp     loc_180055E2F
0x180055eb4  mov     r14d, [r15+10h]
0x180055eb8  mov     esi, edi
0x180055eba  jmp     loc_180055E2F
0x180055ebf  mov     r14d, 0C00D36BBh
0x180055ec5  jmp     loc_180055E2F
0x180055eca  sub     ecx, 7
0x180055ecd  jz      loc_18005624B
0x180055ed3  sub     ecx, edi
0x180055ed5  jz      loc_18005624B
0x180055edb  sub     ecx, edi
0x180055edd  jz      loc_180056120
0x180055ee3  sub     ecx, edi
0x180055ee5  jz      loc_180055FEA
0x180055eeb  cmp     ecx, edi
0x180055eed  jz      short loc_180055F2A
0x180055eef  mov     esi, edi
0x180055ef1  mov     r14d, 0C00D36BBh
0x180055ef7  cmp     cs:byte_18010EC4D, dil
0x180055efe  jb      loc_180055E2F
0x180055f04  mov     edx, 86h
0x180055f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f10  mov     r9d, 0C00D36BBh
0x180055f16  mov     r8, r13
0x180055f19  mov     rcx, [rcx+0D8h]
0x180055f20  call    WPP_SF_d
0x180055f25  jmp     loc_180055E2F
0x180055f2a  lea     rcx, [rbp+var_40]
0x180055f2e  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180055f33  xor     r9d, r9d; pvValue
0x180055f36  lea     rax, [rbp+var_40]
0x180055f3a  xor     r8d, r8d; hrStatus
0x180055f3d  mov     [rsp+70h+ppEvent], rax; ppEvent
0x180055f42  lea     rdx, MF_DEVICESOURCE_MT_CHANGEREQUEST_COMPLETED; guidExtendedType
0x180055f49  lea     ecx, [r9+2]; met
0x180055f4d  call    cs:__imp_MFCreateMediaEvent
0x180055f53  mov     ebx, eax
0x180055f55  test    eax, eax
0x180055f57  jns     short loc_180055F70
0x180055f59  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180055f60  jb      loc_1800562E4
0x180055f66  mov     edx, 80h
0x180055f6b  jmp     loc_180056288
0x180055f70  mov     rcx, [rbp+var_40]
0x180055f74  lea     rdx, MF_DEVICESOURCE_MT_CHANGEREQUEST_TOKEN
0x180055f7b  mov     r8, [r15+18h]
0x180055f7f  mov     rax, [rcx]
0x180055f82  mov     rax, [rax+0B0h]
0x180055f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f8e  mov     ebx, eax
0x180055f90  test    eax, eax
0x180055f92  jns     short loc_180055FAB
0x180055f94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180055f9b  jb      loc_1800562E4
0x180055fa1  mov     edx, 81h
0x180055fa6  jmp     loc_180056288
0x180055fab  mov     rcx, [rbp+var_40]
0x180055faf  lea     rdx, MF_DEVICESOURCE_MT_CHANGEREQUEST_APPROVE
0x180055fb6  mov     r8d, [r15+10h]
0x180055fba  mov     rax, [rcx]
0x180055fbd  mov     rax, [rax+0A8h]
0x180055fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fc9  mov     ebx, eax
0x180055fcb  test    eax, eax
0x180055fcd  jns     loc_180055E2F
0x180055fd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180055fda  jb      loc_1800562E4
0x180055fe0  mov     edx, 82h
0x180055fe5  jmp     loc_180056288
0x180055fea  lea     rcx, [rbp+var_40]
0x180055fee  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180055ff3  xor     r9d, r9d; pvValue
0x180055ff6  lea     rax, [rbp+var_40]
0x180055ffa  xor     r8d, r8d; hrStatus
0x180055ffd  mov     [rsp+70h+ppEvent], rax; ppEvent
0x180056002  lea     rdx, MF_DEVICESOURCE_MT_CHANGEREQUEST; guidExtendedType
0x180056009  lea     ecx, [r9+2]; met
0x18005600d  call    cs:__imp_MFCreateMediaEvent
0x180056013  mov     ebx, eax
0x180056015  test    eax, eax
0x180056017  jns     short loc_180056030
0x180056019  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180056020  jb      loc_1800562E4
0x180056026  mov     edx, 7Bh ; '{'
0x18005602b  jmp     loc_180056288
0x180056030  mov     rcx, [rbp+var_40]
0x180056034  lea     rdx, MF_STREAM_DEVICECONTROL_SOURCETOKEN
0x18005603b  mov     r8, [r15+8]
0x18005603f  mov     rax, [rcx]
0x180056042  mov     rax, [rax+0B0h]
0x180056049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005604e  mov     ebx, eax
0x180056050  test    eax, eax
0x180056052  jns     short loc_18005606B
0x180056054  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18005605b  jb      loc_1800562E4
0x180056061  mov     edx, 7Ch ; '|'
0x180056066  jmp     loc_180056288
0x18005606b  mov     rcx, [rbp+var_40]
0x18005606f  lea     rdx, MF_DEVICESOURCE_MT_CHANGEREQUEST_TOKEN
0x180056076  mov     r8, [r15+18h]
0x18005607a  mov     rax, [rcx]
0x18005607d  mov     rax, [rax+0B0h]
0x180056084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056089  mov     ebx, eax
0x18005608b  test    eax, eax
0x18005608d  jns     short loc_1800560A6
0x18005608f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180056096  jb      loc_1800562E4
0x18005609c  mov     edx, 7Dh ; '}'
0x1800560a1  jmp     loc_180056288
0x1800560a6  mov     rcx, [rbp+var_40]
0x1800560aa  lea     rdx, MF_DEVICESTREAM_STREAM_ID
0x1800560b1  mov     r8d, [r15+28h]
0x1800560b5  mov     rax, [rcx]
0x1800560b8  mov     rax, [rax+0A8h]
0x1800560bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560c4  mov     ebx, eax
0x1800560c6  test    eax, eax
0x1800560c8  jns     short loc_1800560E1
0x1800560ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800560d1  jb      loc_1800562E4
0x1800560d7  mov     edx, 7Eh ; '~'
0x1800560dc  jmp     loc_180056288
0x1800560e1  mov     rcx, [rbp+var_40]
0x1800560e5  lea     rdx, MF_DEVICESOURCE_CHANGEREQUEST_MEDIATYPEINDEX
0x1800560ec  mov     r8d, [r15+2Ch]
0x1800560f0  mov     rax, [rcx]
0x1800560f3  mov     rax, [rax+0A8h]
0x1800560fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560ff  mov     ebx, eax
0x180056101  test    eax, eax
0x180056103  jns     loc_180055E2F
0x180056109  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180056110  jb      loc_1800562E4
0x180056116  mov     edx, 7Fh
0x18005611b  jmp     loc_180056288
0x180056120  mov     ecx, [r15+10h]
0x180056124  mov     r14d, [r15+14h]
0x180056128  test    ecx, ecx
0x18005612a  jz      loc_180056217
0x180056130  sub     ecx, edi
0x180056132  jz      loc_180056210
0x180056138  sub     ecx, edi
0x18005613a  jz      loc_1800561FA
0x180056140  sub     ecx, edi
0x180056142  jz      loc_1800561F1
0x180056148  sub     ecx, edi
0x18005614a  jz      loc_1800561E8
0x180056150  sub     ecx, edi
0x180056152  jz      loc_1800561DF
0x180056158  sub     ecx, edi
0x18005615a  jz      short loc_1800561D6
0x18005615c  cmp     ecx, edi
0x18005615e  jnz     loc_180056217
0x180056164  mov     eax, 1F2h
0x180056169  cmp     ax, [r15+1Ah]
0x18005616e  jnb     short loc_18005618C
0x180056170  mov     ebx, 80070057h
0x180056175  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18005617c  jb      loc_1800562E4
0x180056182  mov     edx, 83h
0x180056187  jmp     loc_180055DCC
0x18005618c  movups  xmm0, cs:MF_FRAMESERVER_VCAMEVENT_EXTENDED_CUSTOM_EVENT
0x180056193  movzx   r8d, word ptr [r15+1Ah]; unsigned int
0x180056198  lea     rdx, [r15+1Ch]; unsigned __int8 *
0x18005619c  movzx   ecx, word ptr [r15+18h]; unsigned __int16
0x1800561a1  lea     r9, [rbp+pvValue]; struct tagPROPVARIANT *
0x1800561a5  movdqu  xmmword ptr [rbp+guidExtendedType.Data1], xmm0
0x1800561aa  call    ?FSBlobToPropVariant@@YAJGPEAEKAEAUtagPROPVARIANT@@@Z; FSBlobToPropVariant(ushort,uchar *,ulong,tagPROPVARIANT &)
0x1800561af  mov     ebx, eax
0x1800561b1  test    eax, eax
0x1800561b3  jns     short loc_1800561CC
0x1800561b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800561bc  jb      loc_1800562E4
0x1800561c2  mov     edx, 84h
0x1800561c7  jmp     loc_180056288
0x1800561cc  mov     esi, 2
0x1800561d1  jmp     loc_180055E2F
0x1800561d6  movups  xmm0, cs:MF_FRAMESERVER_VCAMEVENT_EXTENDED_PIPELINE_SHUTDOWN
0x1800561dd  jmp     short loc_180056201
0x1800561df  movups  xmm0, cs:MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_UNINITIALIZE
0x1800561e6  jmp     short loc_180056201
0x1800561e8  movups  xmm0, cs:MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_STOP
0x1800561ef  jmp     short loc_180056201
0x1800561f1  movups  xmm0, cs:MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_START
0x1800561f8  jmp     short loc_180056201
0x1800561fa  movups  xmm0, cs:MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_INITIALIZE
0x180056201  mov     esi, 2
0x180056206  movdqu  xmmword ptr [rbp+guidExtendedType.Data1], xmm0
0x18005620b  jmp     loc_180055E2F
0x180056210  mov     esi, edi
0x180056212  jmp     loc_180055E2F
0x180056217  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18005621e  mov     esi, edi
0x180056220  movdqu  xmmword ptr [rbp+guidExtendedType.Data1], xmm0
0x180056225  test    r14d, r14d
0x180056228  js      loc_180055E2F
0x18005622e  mov     r14d, 0C00D36BBh
0x180056234  cmp     cs:byte_18010EC4D, dil
0x18005623b  jb      loc_180055E2F
0x180056241  mov     edx, 85h
0x180056246  jmp     loc_180055F09
0x18005624b  lea     rcx, [rbp+var_40]
0x18005624f  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180056254  xor     r9d, r9d; pvValue
  ... truncated ...
```
