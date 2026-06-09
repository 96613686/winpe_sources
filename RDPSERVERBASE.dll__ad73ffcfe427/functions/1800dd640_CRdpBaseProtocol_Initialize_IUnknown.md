# CRdpBaseProtocol::Initialize(IUnknown *)

- ea: `0x1800dd640`
- end: `0x1800ddfde`
- name: `?Initialize@CRdpBaseProtocol@@UEAAJPEAUIUnknown@@@Z`
- size: `2462`
- prototype: `__int64 __fastcall(CRdpBaseProtocol *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800df910`

## callees

- `0x18000ce04`
- `0x18000f660`
- `0x180010d14`
- `0x180010d44`
- `0x18003b118`
- `0x180044000`
- `0x180076090`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x180079d2c`
- `0x18007a404`
- `0x18007f6b0`
- `0x1800dd640`
- `0x1800ddff0`
- `0x1800e1a20`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800dd7cc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800dd7cc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dd7e4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dd7e4`
- `OLEAUT32!__imp_VariantInit` at `0x1800dd675`
- `OLEAUT32!__imp_VariantInit` at `0x1800dd675`
- `OLEAUT32!__imp_VariantClear` at `0x1800dd861`
- `OLEAUT32!__imp_VariantClear` at `0x1800dd861`

## string_xrefs

- `0x1800ddaf2`: `Failed to create wire encoder`
- `0x1800ddb53`: `Failed to create Bitmap encoder`
- `0x1800ddcc1`: `Failed to create RDP Caps`

## pseudocode

```c
__int64 __fastcall CRdpBaseProtocol::Initialize(CRdpBaseProtocol *this, struct IUnknown *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  int Instance; // ebx
  unsigned int v7; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // rcx
  _WORD *v11; // rbx
  __int64 v12; // r11
  int v13; // r12d
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rdx
  _DWORD *v19; // r12
  const wchar_t *v20; // r13
  const wchar_t *v21; // rbx
  unsigned int v22; // eax
  _DWORD *v23; // r12
  const wchar_t *v24; // rbx
  unsigned int v25; // eax
  _DWORD *v26; // rbx
  unsigned int v27; // eax
  _QWORD *v28; // r12
  unsigned int v29; // eax
  _QWORD *v30; // rbx
  char *v31; // r12
  unsigned int v32; // eax
  _DWORD *v33; // rax
  _DWORD *v34; // rbx
  __int64 v35; // rcx
  unsigned int v36; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  DWORD nSize; // [rsp+90h] [rbp+40h] BYREF
  struct IUnknown *v40; // [rsp+98h] [rbp+48h]
  __int64 v41; // [rsp+A0h] [rbp+50h] BYREF

  v40 = a2;
  v41 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRdpBaseProtocol *)((char *)this + 128)) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 14;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147467259);
LABEL_7:
    Instance = -2147467259;
    goto LABEL_126;
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRdpBaseProtocol *)((char *)this + 10712)) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 15;
    goto LABEL_6;
  }
  *((_DWORD *)this + 15) |= 2u;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
               a2,
               &IID_IRDPCollection,
               &v41);
  if ( Instance >= 0 )
  {
    v10 = v41;
    v11 = (_WORD *)((char *)this + 11004);
    *((_WORD *)this + 5502) = 0;
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v10 + 24LL))(
           v10,
           L"GfxPipeline::ServerName",
           &pvarg) >= 0 )
    {
      if ( SysStringLen(pvarg.bstrVal) - 1 <= 0xE )
      {
        v13 = StringCchCopyW((unsigned __int16 *)this + 5502, 0x10u, pvarg.bstrVal);
        if ( v13 >= 0 )
        {
          *((_WORD *)this + v12 + 5502) = 0;
        }
        else
        {
          *v11 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
              v14,
              v13);
          }
        }
      }
    }
    else
    {
      nSize = 16;
      if ( !GetComputerNameW((LPWSTR)this + 5502, &nSize) )
        *v11 = 0;
    }
    VariantClear(&pvarg);
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v41 + 48LL))(
           v41,
           L"RDP::EventLog::Session",
           &IID_IGfxPipelineEventLogCallback,
           (char *)this + 120) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids, v15);
    }
    *((_QWORD *)this + 70) = 0;
    *((_QWORD *)this + 19) = (char *)this + 168;
    v16 = 0;
    *((_DWORD *)this + 40) = 10;
    *((_QWORD *)this + 21) = 0;
    do
    {
      v17 = v16 + 2 * v16 + 1;
      ++v16;
      v18 = *((_QWORD *)this + 19) + 8 * v17;
      *(_QWORD *)(v18 + 8) = *((_QWORD *)this + 18);
      *((_QWORD *)this + 18) = v18;
    }
    while ( v16 != 16 );
    v19 = (_DWORD *)((char *)this + 10564);
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)v41 + 32LL))(
           v41,
           L"GfxPipeline::ForceRemoteFXProfile",
           (char *)this + 10564) < 0 )
      *v19 = 0;
    v20 = L"TRUE";
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v21 = L"TRUE";
      if ( !*v19 )
        v21 = L"FALSE";
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
        v22,
        (__int64)v21);
    }
    v23 = (_DWORD *)((char *)this + 10552);
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)v41 + 32LL))(
           v41,
           L"GfxPipeline::ForceLyncMCUProfile",
           (char *)this + 10552) < 0 )
      *v23 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v24 = L"TRUE";
      if ( !*v23 )
        v24 = L"FALSE";
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
        v25,
        (__int64)v24);
    }
    v26 = (_DWORD *)((char *)this + 10556);
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)v41 + 32LL))(
           v41,
           L"GfxPipeline::ForceLyncProfile",
           (char *)this + 10556) < 0 )
      *v26 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      if ( !*v26 )
        v20 = L"FALSE";
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
        v27,
        (__int64)v20);
    }
    Instance = RDPSERVERBASE_CreateInstance(v40, &CLSID_RDPWireEncoder, &IID_IRDPWireEncoder, (void **)this + 1329);
    if ( Instance >= 0 )
    {
      v28 = (_QWORD *)((char *)this + 10624);
      Instance = RDPSERVERBASE_CreateInstance(
                   v40,
                   &CLSID_RDPBitmapEncoder,
                   &IID_IRDPBitmapEncoder,
                   (void **)this + 1328);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v28 + 24LL))(*v28, *((_QWORD *)this + 1329));
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v28)(
                       *v28,
                       &IID_IRDPCursorEncoder,
                       (char *)this + 10640);
          if ( Instance >= 0 )
          {
            Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v28)(
                         *v28,
                         &IID_IRDPOrderEncoder,
                         (char *)this + 10648);
            if ( Instance >= 0 )
            {
              Instance = RDPSERVERBASE_CreateInstance(v40, &CLSID_RDPCaps, &IID_IRDPCaps, (void **)this + 1332);
              if ( Instance >= 0 )
              {
                if ( !(unsigned int)CTSCriticalSection::Initialize((CRdpBaseProtocol *)((char *)this + 10416)) )
                {
                  Instance = -2147467259;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      30,
                      (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
                      v29,
                      (__int64)"Failed to initialize network queue estimator",
                      5);
                  }
                  goto LABEL_126;
                }
                v30 = operator new(0x78u);
                if ( v30 )
                {
                  v30[3] = "RdpGfxEchoChannelHandler";
                  *((_DWORD *)v30 + 8) = -607474739;
                  *((_DWORD *)v30 + 9) = 1;
                  v30[1] = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
                  v30[2] = &CTSUnknown::`vftable'{for `CTSObject'};
                  *((_DWORD *)v30 + 12) = 0;
                  v30[5] = v30 + 1;
                  *v30 = &RdpGfxEchoChannelHandler::`vftable';
                  v30[1] = &CRDPENCVCChannelInfo::`vftable'{for `INonDelegatingUnknown'};
                  v30[2] = &RdpGfxEchoChannelHandler::`vftable'{for `CTSObject'};
                  v30[7] = 0;
                  v30[8] = 0;
                  v30[9] = 0;
                  *((_DWORD *)v30 + 20) = 0;
                  *((_DWORD *)v30 + 24) = 0;
                  v30[11] = 0;
                  v30[13] = 0;
                  v30[14] = 0;
                }
                else
                {
                  v30 = 0;
                }
                v31 = (char *)this + 10680;
                if ( v30 != *((_QWORD **)this + 1335) )
                {
                  TCntPtr<ClearCompressor>::SafeRelease((char *)this + 10680);
                  *(_QWORD *)v31 = v30;
                  TCntPtr<CaProgressiveSurfaceContext>::SafeAddRef((char *)this + 10680);
                }
                if ( *(_QWORD *)v31 )
                {
                  Instance = RdpGfxEchoChannelHandler::Initialize((RdpGfxEchoChannelHandler *)(*(_QWORD *)v31 + 16LL));
                  if ( Instance < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v8 = 32;
                      v9 = "Failed to initialize echo channel handler";
                      goto LABEL_125;
                    }
                    goto LABEL_126;
                  }
                  v33 = operator new(0x78u);
                  v34 = v33;
                  if ( v33 )
                  {
                    v33[8] = -607474739;
                    *((_QWORD *)v33 + 3) = "MouseCursorChannel";
                    v33[9] = 1;
                    *((_QWORD *)v33 + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
                    *((_QWORD *)v33 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
                    v33[12] = 0;
                    *((_QWORD *)v33 + 5) = v33 + 2;
                    *(_QWORD *)v33 = &MouseCursorChannel::`vftable';
                    *((_QWORD *)v33 + 1) = &CRDPENCVCChannelInfo::`vftable'{for `INonDelegatingUnknown'};
                    *((_QWORD *)v33 + 2) = &MouseCursorChannel::`vftable'{for `CTSObject'};
                    *((_QWORD *)v33 + 7) = 0;
                    v33[16] = 0;
                    v33[20] = 0;
                    *((_QWORD *)v33 + 9) = 0;
                    *((_QWORD *)v33 + 12) = 0;
                    *((_QWORD *)v33 + 11) = &CCapsServerImpl<MouseCursorChannel::MouseCursorServerCapsBase>::`vftable';
                    *((_QWORD *)v33 + 13) = 0;
                    *((_QWORD *)v33 + 14) = 0;
                  }
                  else
                  {
                    v34 = 0;
                  }
                  if ( v34 != *((_DWORD **)this + 13) )
                  {
                    TCntPtr<ClearCompressor>::SafeRelease((char *)this + 104);
                    *((_QWORD *)this + 13) = v34;
                    TCntPtr<CaProgressiveSurfaceContext>::SafeAddRef((char *)this + 104);
                  }
                  v35 = *((_QWORD *)this + 13);
                  if ( v35 )
                  {
                    Instance = MouseCursorChannel::Initialize((MouseCursorChannel *)(v35 + 16));
                    if ( Instance < 0
                      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v8 = 34;
                      v9 = "Failed to initialize MouseCursor channel handler";
                      goto LABEL_125;
                    }
                    goto LABEL_126;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_Ds(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      33,
                      (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
                      v36,
                      (__int64)"MouseCursorChannel");
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v32 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Ds(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    31,
                    (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
                    v32,
                    (__int64)"RdpGfxEchoChannelHandler");
                }
                Instance = -2147024882;
                goto LABEL_126;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v7 = RdpWppGetCurrentThreadActivityIdPrefix();
                v8 = 29;
                v9 = "Failed to create RDP Caps";
                goto LABEL_125;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v7 = RdpWppGetCurrentThreadActivityIdPrefix();
              v8 = 28;
              v9 = "Failed to QI for order encoder";
              goto LABEL_125;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = RdpWppGetCurrentThreadActivityIdPrefix();
            v8 = 27;
            v9 = "Failed to QI for cursor encoder";
            goto LABEL_125;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 26;
          v9 = "Failed to initialize bitmap encoder";
          goto LABEL_125;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 25;
        v9 = "Failed to create Bitmap encoder";
        goto LABEL_125;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 24;
      v9 = "Failed to create wire encoder";
      goto LABEL_125;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 17;
    v9 = "Failed to QI the platform context";
LABEL_125:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
      v7,
      (__int64)v9,
      Instance);
  }
LABEL_126:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v41);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800dd640  mov     [rsp-38h+arg_8], rdx
0x1800dd645  push    rbp
0x1800dd646  push    rbx
0x1800dd647  push    rdi
0x1800dd648  push    r12
0x1800dd64a  push    r13
0x1800dd64c  push    r14
0x1800dd64e  push    r15
0x1800dd650  mov     rbp, rsp
0x1800dd653  sub     rsp, 50h
0x1800dd657  mov     r14, rcx
0x1800dd65a  xorps   xmm0, xmm0
0x1800dd65d  xor     eax, eax
0x1800dd65f  lea     rcx, [rbp+pvarg]; pvarg
0x1800dd663  xor     r13d, r13d
0x1800dd666  mov     qword ptr [rbp+pvarg+10h], rax
0x1800dd66a  mov     [rbp+arg_10], r13
0x1800dd66e  mov     rbx, rdx
0x1800dd671  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800dd675  call    cs:__imp_VariantInit
0x1800dd67b  lea     rcx, [r14+80h]; this
0x1800dd682  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800dd687  test    eax, eax
0x1800dd689  jnz     short loc_1800DD6DF
0x1800dd68b  mov     rax, cs:WPP_GLOBAL_Control
0x1800dd692  lea     rdi, WPP_GLOBAL_Control
0x1800dd699  cmp     rax, rdi
0x1800dd69c  jz      short loc_1800DD6D5
0x1800dd69e  test    byte ptr [rax+1Ch], 8
0x1800dd6a2  jz      short loc_1800DD6D5
0x1800dd6a4  cmp     byte ptr [rax+19h], 2
0x1800dd6a8  jb      short loc_1800DD6D5
0x1800dd6aa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dd6af  lea     edx, [r13+0Eh]
0x1800dd6b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dd6ba  lea     r8, WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids
0x1800dd6c1  mov     r9d, eax
0x1800dd6c4  mov     dword ptr [rsp+50h+var_30], 80004005h
0x1800dd6cc  mov     rcx, [rcx+10h]
0x1800dd6d0  call    WPP_SF_Dd
0x1800dd6d5  mov     ebx, 80004005h
0x1800dd6da  jmp     loc_1800DDFC3
0x1800dd6df  lea     rcx, [r14+29D8h]; this
0x1800dd6e6  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800dd6eb  test    eax, eax
0x1800dd6ed  jnz     short loc_1800DD71A
0x1800dd6ef  mov     rax, cs:WPP_GLOBAL_Control
0x1800dd6f6  lea     rdi, WPP_GLOBAL_Control
0x1800dd6fd  cmp     rax, rdi
0x1800dd700  jz      short loc_1800DD6D5
0x1800dd702  test    byte ptr [rax+1Ch], 8
0x1800dd706  jz      short loc_1800DD6D5
0x1800dd708  cmp     byte ptr [rax+19h], 2
0x1800dd70c  jb      short loc_1800DD6D5
0x1800dd70e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dd713  mov     edx, 0Fh
0x1800dd718  jmp     short loc_1800DD6B3
0x1800dd71a  or      dword ptr [r14+3Ch], 2
0x1800dd71f  lea     r8, [rbp+arg_10]
0x1800dd723  mov     rax, [rbx]
0x1800dd726  lea     rdx, IID_IRDPCollection
0x1800dd72d  mov     rcx, rbx
0x1800dd730  mov     rax, [rax]
0x1800dd733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd738  mov     ebx, eax
0x1800dd73a  test    eax, eax
0x1800dd73c  jns     short loc_1800DD786
0x1800dd73e  mov     rax, cs:WPP_GLOBAL_Control
0x1800dd745  lea     rdi, WPP_GLOBAL_Control
0x1800dd74c  cmp     rax, rdi
0x1800dd74f  jz      loc_1800DDFC3
0x1800dd755  test    byte ptr [rax+1Ch], 8
0x1800dd759  jz      loc_1800DDFC3
0x1800dd75f  cmp     byte ptr [rax+19h], 2
0x1800dd763  jb      loc_1800DDFC3
0x1800dd769  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dd76e  mov     edx, 11h
0x1800dd773  lea     rcx, aFailedToQiTheP; "Failed to QI the platform context"
0x1800dd77a  lea     r8, WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids
0x1800dd781  jmp     loc_1800DDFA7
0x1800dd786  mov     rcx, [rbp+arg_10]
0x1800dd78a  lea     rbx, [r14+2AFCh]
0x1800dd791  mov     [rbx], r13w
0x1800dd795  lea     r8, [rbp+pvarg]
0x1800dd799  lea     rdx, aGfxpipelineSer; "GfxPipeline::ServerName"
0x1800dd7a0  mov     rax, [rcx]
0x1800dd7a3  mov     rax, [rax+18h]
0x1800dd7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd7ac  lea     rdi, WPP_GLOBAL_Control
0x1800dd7b3  lea     r15, WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids
0x1800dd7ba  test    eax, eax
0x1800dd7bc  jns     short loc_1800DD7E0
0x1800dd7be  lea     rdx, [rbp+nSize]; nSize
0x1800dd7c2  mov     [rbp+nSize], 10h
0x1800dd7c9  mov     rcx, rbx; lpBuffer
0x1800dd7cc  call    cs:__imp_GetComputerNameW
0x1800dd7d2  test    eax, eax
0x1800dd7d4  jnz     loc_1800DD85D
0x1800dd7da  mov     [rbx], r13w
0x1800dd7de  jmp     short loc_1800DD85D
0x1800dd7e0  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x1800dd7e4  call    cs:__imp_SysStringLen
0x1800dd7ea  mov     r11d, eax
0x1800dd7ed  lea     ecx, [r11-1]
0x1800dd7f1  cmp     ecx, 0Eh
0x1800dd7f4  ja      short loc_1800DD85D
0x1800dd7f6  mov     r8, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x1800dd7fa  mov     edx, 10h; unsigned __int64
0x1800dd7ff  mov     rcx, rbx; unsigned __int16 *
0x1800dd802  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800dd807  mov     r12d, eax
0x1800dd80a  test    eax, eax
0x1800dd80c  jns     short loc_1800DD854
0x1800dd80e  mov     [rbx], r13w
0x1800dd812  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dd819  cmp     rcx, rdi
0x1800dd81c  jz      short loc_1800DD85D
0x1800dd81e  test    dword ptr [rcx+1Ch], 100h
0x1800dd825  jz      short loc_1800DD85D
0x1800dd827  cmp     byte ptr [rcx+19h], 2
0x1800dd82b  jb      short loc_1800DD85D
0x1800dd82d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dd832  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dd839  mov     edx, 12h
0x1800dd83e  mov     r9d, eax
0x1800dd841  mov     dword ptr [rsp+50h+var_30], r12d
0x1800dd846  mov     r8, r15
0x1800dd849  mov     rcx, [rcx+10h]
0x1800dd84d  call    WPP_SF_Dd
0x1800dd852  jmp     short loc_1800DD85D
0x1800dd854  mov     [r14+r11*2+2AFCh], r13w
0x1800dd85d  lea     rcx, [rbp+pvarg]; pvarg
0x1800dd861  call    cs:__imp_VariantClear
0x1800dd867  mov     rcx, [rbp+arg_10]
0x1800dd86b  lea     r9, [r14+78h]
0x1800dd86f  lea     r8, IID_IGfxPipelineEventLogCallback
0x1800dd876  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x1800dd87d  mov     rax, [rcx]
0x1800dd880  mov     rax, [rax+30h]
0x1800dd884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd889  test    eax, eax
0x1800dd88b  jns     short loc_1800DD8C8
0x1800dd88d  mov     rax, cs:WPP_GLOBAL_Control
0x1800dd894  cmp     rax, rdi
0x1800dd897  jz      short loc_1800DD8C8
0x1800dd899  test    dword ptr [rax+1Ch], 100h
0x1800dd8a0  jz      short loc_1800DD8C8
0x1800dd8a2  cmp     byte ptr [rax+19h], 4
0x1800dd8a6  jb      short loc_1800DD8C8
0x1800dd8a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dd8ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dd8b4  mov     edx, 13h
0x1800dd8b9  mov     r9d, eax
0x1800dd8bc  mov     r8, r15
0x1800dd8bf  mov     rcx, [rcx+10h]
0x1800dd8c3  call    WPP_SF_d
0x1800dd8c8  mov     [r14+230h], r13
0x1800dd8cf  lea     rax, [r14+0A8h]
0x1800dd8d6  mov     [r14+98h], rax
0x1800dd8dd  mov     r8, r13
0x1800dd8e0  mov     dword ptr [r14+0A0h], 0Ah
0x1800dd8eb  mov     [rax], r13
0x1800dd8ee  mov     rax, [r14+98h]
0x1800dd8f5  lea     rdx, ds:1[r8*2]
0x1800dd8fd  add     rdx, r8
0x1800dd900  inc     r8
0x1800dd903  lea     rdx, [rax+rdx*8]
0x1800dd907  mov     rax, [r14+90h]
0x1800dd90e  mov     [rdx+8], rax
0x1800dd912  mov     [r14+90h], rdx
0x1800dd919  cmp     r8, 10h
0x1800dd91d  jnz     short loc_1800DD8EE
0x1800dd91f  mov     rcx, [rbp+arg_10]
0x1800dd923  lea     r12, [r14+2944h]
0x1800dd92a  mov     r8, r12
0x1800dd92d  lea     rdx, aGfxpipelineFor_0; "GfxPipeline::ForceRemoteFXProfile"
0x1800dd934  mov     rax, [rcx]
0x1800dd937  mov     rax, [rax+20h]
0x1800dd93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd940  test    eax, eax
0x1800dd942  jns     short loc_1800DD948
0x1800dd944  mov     [r12], r13d
0x1800dd948  mov     rax, cs:WPP_GLOBAL_Control
0x1800dd94f  lea     rcx, aFalse_0; "FALSE"
0x1800dd956  lea     r13, aTrue_0; "TRUE"
0x1800dd95d  cmp     rax, rdi
0x1800dd960  jz      short loc_1800DD9A2
0x1800dd962  test    dword ptr [rax+1Ch], 100h
0x1800dd969  jz      short loc_1800DD9A2
0x1800dd96b  cmp     byte ptr [rax+19h], 4
0x1800dd96f  jb      short loc_1800DD9A2
0x1800dd971  cmp     dword ptr [r12], 0
0x1800dd976  mov     rbx, r13
0x1800dd979  cmovz   rbx, rcx
0x1800dd97d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dd982  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dd989  mov     edx, 15h
0x1800dd98e  mov     r9d, eax
0x1800dd991  mov     [rsp+50h+var_30], rbx
0x1800dd996  mov     r8, r15
0x1800dd999  mov     rcx, [rcx+10h]
0x1800dd99d  call    WPP_SF_DS
0x1800dd9a2  mov     rcx, [rbp+arg_10]
0x1800dd9a6  lea     r12, [r14+2938h]
0x1800dd9ad  mov     r8, r12
0x1800dd9b0  lea     rdx, aGfxpipelineFor_1; "GfxPipeline::ForceLyncMCUProfile"
0x1800dd9b7  mov     rax, [rcx]
0x1800dd9ba  mov     rax, [rax+20h]
0x1800dd9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd9c3  test    eax, eax
0x1800dd9c5  jns     short loc_1800DD9CF
0x1800dd9c7  mov     dword ptr [r12], 0
0x1800dd9cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800dd9d6  cmp     rax, rdi
0x1800dd9d9  jz      short loc_1800DDA24
0x1800dd9db  test    dword ptr [rax+1Ch], 100h
0x1800dd9e2  jz      short loc_1800DDA24
0x1800dd9e4  cmp     byte ptr [rax+19h], 4
0x1800dd9e8  jb      short loc_1800DDA24
0x1800dd9ea  cmp     dword ptr [r12], 0
0x1800dd9ef  mov     rbx, r13
0x1800dd9f2  lea     r12, aFalse_0; "FALSE"
0x1800dd9f9  cmovz   rbx, r12
0x1800dd9fd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dda02  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dda09  mov     edx, 16h
0x1800dda0e  mov     r9d, eax
0x1800dda11  mov     [rsp+50h+var_30], rbx
0x1800dda16  mov     r8, r15
0x1800dda19  mov     rcx, [rcx+10h]
0x1800dda1d  call    WPP_SF_DS
0x1800dda22  jmp     short loc_1800DDA2B
0x1800dda24  lea     r12, aFalse_0; "FALSE"
0x1800dda2b  mov     rcx, [rbp+arg_10]
0x1800dda2f  lea     rbx, [r14+293Ch]
0x1800dda36  mov     r8, rbx
0x1800dda39  lea     rdx, aGfxpipelineFor; "GfxPipeline::ForceLyncProfile"
0x1800dda40  mov     rax, [rcx]
0x1800dda43  mov     rax, [rax+20h]
0x1800dda47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dda4c  test    eax, eax
0x1800dda4e  jns     short loc_1800DDA56
0x1800dda50  mov     dword ptr [rbx], 0
0x1800dda56  mov     rax, cs:WPP_GLOBAL_Control
0x1800dda5d  cmp     rax, rdi
0x1800dda60  jz      short loc_1800DDA9D
0x1800dda62  test    dword ptr [rax+1Ch], 100h
0x1800dda69  jz      short loc_1800DDA9D
0x1800dda6b  cmp     byte ptr [rax+19h], 4
0x1800dda6f  jb      short loc_1800DDA9D
0x1800dda71  cmp     dword ptr [rbx], 0
0x1800dda74  cmovz   r13, r12
0x1800dda78  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dda7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dda84  mov     edx, 17h
0x1800dda89  mov     r9d, eax
0x1800dda8c  mov     [rsp+50h+var_30], r13
0x1800dda91  mov     r8, r15
0x1800dda94  mov     rcx, [rcx+10h]
0x1800dda98  call    WPP_SF_DS
0x1800dda9d  mov     rcx, [rbp+arg_8]
0x1800ddaa1  lea     r13, [r14+2988h]
0x1800ddaa8  mov     r9, r13
0x1800ddaab  lea     r8, IID_IRDPWireEncoder
0x1800ddab2  lea     rdx, CLSID_RDPWireEncoder
0x1800ddab9  call    RDPSERVERBASE_CreateInstance
0x1800ddabe  mov     ebx, eax
0x1800ddac0  test    eax, eax
0x1800ddac2  jns     short loc_1800DDAFE
0x1800ddac4  mov     rax, cs:WPP_GLOBAL_Control
0x1800ddacb  cmp     rax, rdi
0x1800ddace  jz      loc_1800DDFC3
0x1800ddad4  test    byte ptr [rax+1Ch], 8
0x1800ddad8  jz      loc_1800DDFC3
0x1800ddade  cmp     byte ptr [rax+19h], 2
0x1800ddae2  jb      loc_1800DDFC3
0x1800ddae8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ddaed  mov     edx, 18h
0x1800ddaf2  lea     rcx, aFailedToCreate_21; "Failed to create wire encoder"
0x1800ddaf9  jmp     loc_1800DDFA4
0x1800ddafe  mov     rcx, [rbp+arg_8]
0x1800ddb02  lea     r12, [r14+2980h]
0x1800ddb09  mov     r9, r12
0x1800ddb0c  lea     r8, IID_IRDPBitmapEncoder
0x1800ddb13  lea     rdx, CLSID_RDPBitmapEncoder
0x1800ddb1a  call    RDPSERVERBASE_CreateInstance
0x1800ddb1f  mov     ebx, eax
0x1800ddb21  test    eax, eax
0x1800ddb23  jns     short loc_1800DDB5F
0x1800ddb25  mov     rax, cs:WPP_GLOBAL_Control
0x1800ddb2c  cmp     rax, rdi
0x1800ddb2f  jz      loc_1800DDFC3
0x1800ddb35  test    byte ptr [rax+1Ch], 8
0x1800ddb39  jz      loc_1800DDFC3
0x1800ddb3f  cmp     byte ptr [rax+19h], 2
0x1800ddb43  jb      loc_1800DDFC3
0x1800ddb49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ddb4e  mov     edx, 19h
0x1800ddb53  lea     rcx, aFailedToCreate_131; "Failed to create Bitmap encoder"
0x1800ddb5a  jmp     loc_1800DDFA4
  ... truncated ...
```
