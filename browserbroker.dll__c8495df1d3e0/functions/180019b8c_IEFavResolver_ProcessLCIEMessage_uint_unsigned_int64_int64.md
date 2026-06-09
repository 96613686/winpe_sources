# IEFavResolver::ProcessLCIEMessage(uint,unsigned __int64,__int64)

- ea: `0x180019b8c`
- end: `0x18001a166`
- name: `?ProcessLCIEMessage@IEFavResolver@@QEAA_JI_K_J@Z`
- size: `1498`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b520`

## callees

- `0x180001e20`
- `0x180002ce0`
- `0x1800037ac`
- `0x180006cc4`
- `0x18000dc74`
- `0x180016948`
- `0x180016a9c`
- `0x180016fa8`
- `0x1800173a8`
- `0x180017508`
- `0x1800179f0`
- `0x180017ff4`
- `0x1800181d4`
- `0x180018528`
- `0x180019724`
- `0x180019b8c`
- `0x18001a53c`
- `0x18001a80c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180019f47`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180019f47`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x180019e15`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x180019e6e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x180019e15`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x180019e6e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180019e02`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180019fb6`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180019e02`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180019fb6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019de7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019e57`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019f99`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019de7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019e57`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019f99`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019e3e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019e3e`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x180019ff4`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x180019ff4`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x180019cb1`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x180019d2f`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x180019dad`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x180019ef0`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x180019cb1`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x180019d2f`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x180019dad`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x180019ef0`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x180019bf6`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x180019bf6`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019c0d`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019c1b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019c29`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019c33`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019f37`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a10b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a115`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019c0d`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019c1b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019c29`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019c33`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180019f37`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a10b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a115`

## string_xrefs

- `0x18001a154`: `onecoreuap\inetcore\spartan\desktopbroker\iefavresolver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IEFavResolver::ProcessLCIEMessage(IEFavResolver *this, __int64 a2, int a3, __int64 a4)
{
  unsigned int v4; // esi
  __int128 v7; // xmm6
  __int128 v8; // xmm7
  char v9; // r14
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  struct _IsoMessage *v17; // rbx
  DWORD nNumberOfBytesToWrite; // r10d
  struct _IsoMessage *v19; // rbx
  int started; // eax
  struct _IsoMessage *v21; // rbx
  unsigned int *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  struct _IsoMessage *v26; // rbx
  IEFavResolver *v27; // rcx
  unsigned int v28; // r8d
  IEFavResolver *v29; // rcx
  unsigned int v30; // r8d
  int lpBuffer; // [rsp+28h] [rbp-E0h]
  int v33; // [rsp+48h] [rbp-C0h] BYREF
  char v34; // [rsp+4Ch] [rbp-BCh] BYREF
  LPSTREAM ppstm; // [rsp+50h] [rbp-B8h] BYREF
  struct _IsoMessage *v36; // [rsp+58h] [rbp-B0h] BYREF
  LPSTREAM v37; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v38[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v39[3]; // [rsp+70h] [rbp-98h] BYREF
  char v40; // [rsp+88h] [rbp-80h]
  int v41; // [rsp+8Ch] [rbp-7Ch]
  WCHAR pszMore[264]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR v43[264]; // [rsp+2A8h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+510h] [rbp+408h]

  v4 = a4;
  if ( a4 )
  {
    v36 = 0;
    if ( (int)IsoGetMessageBufferAddress(a4, 1, 0, &v36, 0) >= 0 )
    {
      v7 = *((_OWORD *)v36 + 1);
      v8 = *(_OWORD *)GlobalThreadState();
      *(_OWORD *)&v39[1] = v8;
      v9 = *((_BYTE *)GlobalThreadState() + 16);
      v40 = v9;
      *(_OWORD *)GlobalThreadState() = v7;
      *((_BYTE *)GlobalThreadState() + 16) = 1;
      v41 = 1;
      v10 = a3 - 3511;
      if ( !v10 )
      {
        *((_DWORD *)this + 2) = *((_DWORD *)v36 + 1);
        goto LABEL_54;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        v26 = v36;
        if ( VerifyUntrusted_IsoMessage_ExactSize(v4, 0xCA0u) && *((_DWORD *)v26 + 1) == *((_DWORD *)this + 2) )
        {
          memset_0(pszMore, 0, 0x208u);
          if ( IEFavResolver::GetRelativePathFromFullUnifiedPath(v27, (const unsigned __int16 *)v26 + 314, v28, pszMore) >= 0 )
          {
            switch ( *((_DWORD *)v26 + 8) )
            {
              case 1:
                IEFavResolver::AddFavorite(
                  (WCHAR *)this,
                  (const unsigned __int16 *)v26 + 574,
                  (const unsigned __int16 *)v26 + 834,
                  (const unsigned __int16 *)v26 + 314,
                  *((unsigned __int8 *)v26 + 3228),
                  0);
                break;
              case 2:
                memset_0(v43, 0, 0x208u);
                if ( IEFavResolver::GetRelativePathFromFullUnifiedPath(
                       v29,
                       (const unsigned __int16 *)v26 + 1094,
                       v30,
                       v43) >= 0 )
                  IEFavResolver::UpdateFavorite(
                    this,
                    (const unsigned __int16 *)v26 + 1354,
                    v43,
                    (const unsigned __int16 *)v26 + 574,
                    pszMore,
                    *((unsigned __int8 *)v26 + 3228));
                break;
              case 3:
                IEFavResolver::DeleteFavorite(
                  (WCHAR *)this,
                  (const unsigned __int16 *)v26 + 1354,
                  pszMore,
                  *((unsigned __int8 *)v26 + 3228));
                break;
            }
          }
        }
        goto LABEL_54;
      }
      v12 = v11 - 5;
      if ( v12 )
      {
        v13 = v12 - 3;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 4;
            if ( v15 )
            {
              v16 = v15 - 2;
              if ( v16 )
              {
                if ( v16 == 1 )
                {
                  v17 = v36;
                  if ( *((_DWORD *)v36 + 1) == *((_DWORD *)this + 2) )
                  {
                    v33 = 0;
                    if ( VerifyUntrusted_IsoMessage_MinSize(v4, 0x640u, (unsigned int *)&v33)
                      && VerifyUntrusted_IsoMessage_ComputedSize<LCIE_FAVORITES_SYNC_FAVICON_DATA_MSG &>(
                           v33,
                           *((_DWORD *)v17 + 398)) )
                    {
                      IEFavResolver::HandleFaviconData(
                        this,
                        (const unsigned __int16 *)v17 + 16,
                        (const unsigned __int16 *)v17 + 276,
                        (const unsigned __int16 *)v17 + 536,
                        (char *)v17 + 1596,
                        nNumberOfBytesToWrite);
                    }
                  }
                }
              }
              else
              {
                v19 = v36;
                if ( *((_DWORD *)v36 + 1) == *((_DWORD *)this + 2) )
                {
                  v33 = 0;
                  if ( VerifyUntrusted_IsoMessage_MinSize(v4, 0x640u, (unsigned int *)&v33)
                    && VerifyUntrusted_IsoMessage_ComputedSize<LCIE_FAVORITES_SYNC_FAVICON_DATA_MSG &>(
                         v33,
                         *((_DWORD *)v19 + 398)) )
                  {
                    IEFavResolver::HandleFaviconRequest(
                      this,
                      (const unsigned __int16 *)v19 + 16,
                      (const unsigned __int16 *)v19 + 276);
                  }
                }
              }
            }
            else
            {
              started = IEFavResolver::StartFavoriteMonitoring(this);
              if ( started < 0 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0xB5,
                  (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\iefavresolver.cpp",
                  (const char *)(unsigned int)started,
                  lpBuffer);
            }
            goto LABEL_54;
          }
          v21 = v36;
          if ( *((_DWORD *)v36 + 1) == *((_DWORD *)this + 2) )
          {
            v33 = 0;
            if ( VerifyUntrusted_IsoMessage_MinSize(v4, 0x2Cu, (unsigned int *)&v33)
              && *((_DWORD *)v21 + 9) < 0xFFFFFFD4
              && v33 == *((_DWORD *)v21 + 9) + 44 )
            {
              ppstm = 0;
              if ( CreateStreamOnHGlobal(0, 1, &ppstm) >= 0
                && IStream_Write(ppstm, (char *)v21 + 40, *((_DWORD *)v21 + 9)) >= 0 )
              {
                IStream_Reset(ppstm);
                LODWORD(v39[0]) = *((_DWORD *)v21 + 8);
                if ( (int)IEFavResolver::ApplyFullScanResultFromEdge((WCHAR *)this, ppstm, v39[0]) >= 0 )
                {
                  Sleep(0x7D0u);
                  v37 = 0;
                  if ( CreateStreamOnHGlobal(0, 1, &v37) >= 0 )
                  {
                    v38[0] = 0;
                    IStream_Reset(ppstm);
                    IEFavResolver::ApplyOrderFromEdgeRecursively(
                      this,
                      ppstm,
                      (unsigned int *)v39,
                      L"ROOT",
                      (unsigned __int16 *)&pszSubkey,
                      &v37,
                      v38);
                  }
                  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&v37);
                }
              }
LABEL_42:
              ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppstm);
            }
          }
        }
        else
        {
          IEFavResolver::PerformFullScanOnIEFavorites(this);
        }
LABEL_54:
        *(_OWORD *)GlobalThreadState() = v8;
        *((_BYTE *)GlobalThreadState() + 16) = v9;
        return 0;
      }
      v22 = (unsigned int *)v36;
      if ( *((_DWORD *)v36 + 1) != *((_DWORD *)this + 2) )
        goto LABEL_54;
      v33 = 0;
      if ( !VerifyUntrusted_IsoMessage_MinSize(v4, 0x234u, (unsigned int *)&v33)
        || v22[139] >= 0xFFFFFDCC
        || v33 != v22[139] + 564 )
      {
        goto LABEL_54;
      }
      if ( (unsigned int)dword_18003F000 > 5 )
      {
        v37 = (LPSTREAM)(v22 + 8);
        v34 = 1;
        v39[0] = (__int64)GlobalThreadState();
        *(_QWORD *)v38 = IEConfiguration_GetCLSID(268435459);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
          v23,
          (__int64)word_180036352,
          v24,
          v25,
          (__int64 *)v38,
          v39,
          (__int64)&v34,
          (const WCHAR **)&v37);
      }
      ppstm = 0;
      if ( CreateStreamOnHGlobal(0, 1, &ppstm) >= 0 && IStream_Write(ppstm, v22 + 140, v22[139]) >= 0 )
        IEFavResolver::ApplyFavoriteOrder(this, (unsigned __int16 *)v22 + 16, ppstm, v22[138]);
      goto LABEL_42;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019b8c  mov     rax, rsp
0x180019b8f  mov     [rax+10h], rbx
0x180019b93  push    rbp
0x180019b94  push    rsi
0x180019b95  push    rdi
0x180019b96  push    r12
0x180019b98  push    r14
0x180019b9a  lea     rbp, [rax-408h]
0x180019ba1  sub     rsp, 4E0h
0x180019ba8  movaps  xmmword ptr [rax-38h], xmm6
0x180019bac  movaps  xmmword ptr [rax-48h], xmm7
0x180019bb0  mov     rax, cs:__security_cookie
0x180019bb7  xor     rax, rsp
0x180019bba  mov     [rbp+400h+var_50], rax
0x180019bc1  mov     rsi, r9
0x180019bc4  mov     rbx, r8
0x180019bc7  mov     rdi, rcx
0x180019bca  test    r9, r9
0x180019bcd  jz      loc_18001A11F
0x180019bd3  mov     [rsp+500h+var_4B0], 0
0x180019bdc  mov     [rsp+500h+lpBuffer], 0; int
0x180019be5  lea     r9, [rsp+500h+var_4B0]
0x180019bea  xor     r8d, r8d
0x180019bed  lea     r12d, [r8+1]
0x180019bf1  mov     edx, r12d
0x180019bf4  mov     ecx, esi
0x180019bf6  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x180019bfc  test    eax, eax
0x180019bfe  js      loc_18001A11F
0x180019c04  mov     rax, [rsp+500h+var_4B0]
0x180019c09  movups  xmm6, xmmword ptr [rax+10h]
0x180019c0d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019c13  movups  xmm7, xmmword ptr [rax]
0x180019c16  movups  xmmword ptr [rsp+500h+var_498+8], xmm7
0x180019c1b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019c21  mov     r14b, [rax+10h]
0x180019c25  mov     [rbp+400h+var_480], r14b
0x180019c29  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019c2f  movdqu  xmmword ptr [rax], xmm6
0x180019c33  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019c39  mov     [rax+10h], r12b
0x180019c3d  mov     [rbp+400h+var_47C], r12d
0x180019c41  sub     ebx, 0DB7h
0x180019c47  jz      loc_18001A100
0x180019c4d  sub     ebx, r12d
0x180019c50  jz      loc_180019FE8
0x180019c56  sub     ebx, 5
0x180019c59  jz      loc_180019ECB
0x180019c5f  sub     ebx, 3
0x180019c62  jz      loc_180019EBE
0x180019c68  sub     ebx, r12d
0x180019c6b  jz      loc_180019D88
0x180019c71  sub     ebx, 4
0x180019c74  jz      loc_180019D6C
0x180019c7a  sub     ebx, 2
0x180019c7d  jz      loc_180019D0A
0x180019c83  cmp     ebx, r12d
0x180019c86  jnz     loc_18001A10B
0x180019c8c  mov     rbx, [rsp+500h+var_4B0]
0x180019c91  mov     eax, [rdi+8]
0x180019c94  cmp     [rbx+4], eax
0x180019c97  jnz     loc_18001A10B
0x180019c9d  mov     dword ptr [rsp+500h+var_4C0], 0
0x180019ca5  lea     r8, [rsp+500h+var_4C0]
0x180019caa  mov     edx, 640h
0x180019caf  mov     ecx, esi
0x180019cb1  call    cs:__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z; VerifyUntrusted_IsoMessage_MinSize(ulong,ulong,ulong *)
0x180019cb7  test    al, al
0x180019cb9  jz      loc_18001A10B
0x180019cbf  mov     r10d, [rbx+638h]
0x180019cc6  mov     edx, r10d
0x180019cc9  mov     ecx, dword ptr [rsp+500h+var_4C0]
0x180019ccd  call    ??$VerifyUntrusted_IsoMessage_ComputedSize@AEAULCIE_FAVORITES_SYNC_FAVICON_DATA_MSG@@@@YA_NKK@Z; VerifyUntrusted_IsoMessage_ComputedSize<LCIE_FAVORITES_SYNC_FAVICON_DATA_MSG &>(ulong,ulong)
0x180019cd2  test    al, al
0x180019cd4  jz      loc_18001A10B
0x180019cda  lea     rax, [rbx+63Ch]
0x180019ce1  lea     r9, [rbx+430h]; unsigned __int16 *
0x180019ce8  lea     r8, [rbx+228h]; unsigned __int16 *
0x180019cef  lea     rdx, [rbx+20h]; unsigned __int16 *
0x180019cf3  mov     [rsp+500h+nNumberOfBytesToWrite], r10d; nNumberOfBytesToWrite
0x180019cf8  mov     [rsp+500h+lpBuffer], rax; lpBuffer
0x180019cfd  mov     rcx, rdi; this
0x180019d00  call    ?HandleFaviconData@IEFavResolver@@AEAAJPEBG00PEAEK@Z; IEFavResolver::HandleFaviconData(ushort const *,ushort const *,ushort const *,uchar *,ulong)
0x180019d05  jmp     loc_18001A10B
0x180019d0a  mov     rbx, [rsp+500h+var_4B0]
0x180019d0f  mov     eax, [rdi+8]
0x180019d12  cmp     [rbx+4], eax
0x180019d15  jnz     loc_18001A10B
0x180019d1b  mov     dword ptr [rsp+500h+var_4C0], 0
0x180019d23  lea     r8, [rsp+500h+var_4C0]
0x180019d28  mov     edx, 640h
0x180019d2d  mov     ecx, esi
0x180019d2f  call    cs:__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z; VerifyUntrusted_IsoMessage_MinSize(ulong,ulong,ulong *)
0x180019d35  test    al, al
0x180019d37  jz      loc_18001A10B
0x180019d3d  mov     edx, [rbx+638h]
0x180019d43  mov     ecx, dword ptr [rsp+500h+var_4C0]
0x180019d47  call    ??$VerifyUntrusted_IsoMessage_ComputedSize@AEAULCIE_FAVORITES_SYNC_FAVICON_DATA_MSG@@@@YA_NKK@Z; VerifyUntrusted_IsoMessage_ComputedSize<LCIE_FAVORITES_SYNC_FAVICON_DATA_MSG &>(ulong,ulong)
0x180019d4c  test    al, al
0x180019d4e  jz      loc_18001A10B
0x180019d54  lea     r8, [rbx+228h]; unsigned __int16 *
0x180019d5b  lea     rdx, [rbx+20h]; unsigned __int16 *
0x180019d5f  mov     rcx, rdi; this
0x180019d62  call    ?HandleFaviconRequest@IEFavResolver@@AEAAJPEBG0@Z; IEFavResolver::HandleFaviconRequest(ushort const *,ushort const *)
0x180019d67  jmp     loc_18001A10B
0x180019d6c  mov     rcx, rdi; this
0x180019d6f  call    ?StartFavoriteMonitoring@IEFavResolver@@AEAAJXZ; IEFavResolver::StartFavoriteMonitoring(void)
0x180019d74  mov     rcx, [rbp+408h]; this
0x180019d7b  test    eax, eax
0x180019d7d  js      loc_18001A151
0x180019d83  jmp     loc_18001A10B
0x180019d88  mov     rbx, [rsp+500h+var_4B0]
0x180019d8d  mov     eax, [rdi+8]
0x180019d90  cmp     [rbx+4], eax
0x180019d93  jnz     loc_18001A10B
0x180019d99  mov     dword ptr [rsp+500h+var_4C0], 0
0x180019da1  lea     r8, [rsp+500h+var_4C0]
0x180019da6  mov     edx, 2Ch ; ','
0x180019dab  mov     ecx, esi
0x180019dad  call    cs:__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z; VerifyUntrusted_IsoMessage_MinSize(ulong,ulong,ulong *)
0x180019db3  test    al, al
0x180019db5  jz      loc_18001A10B
0x180019dbb  mov     eax, [rbx+24h]
0x180019dbe  add     eax, 2Ch ; ','
0x180019dc1  cmp     eax, 2Ch ; ','
0x180019dc4  jb      loc_18001A10B
0x180019dca  cmp     dword ptr [rsp+500h+var_4C0], eax
0x180019dce  jnz     loc_18001A10B
0x180019dd4  mov     [rsp+500h+ppstm], 0
0x180019ddd  lea     r8, [rsp+500h+ppstm]; ppstm
0x180019de2  mov     edx, r12d; fDeleteOnRelease
0x180019de5  xor     ecx, ecx; hGlobal
0x180019de7  call    cs:__imp_CreateStreamOnHGlobal
0x180019ded  test    eax, eax
0x180019def  js      loc_180019EB9
0x180019df5  lea     rdx, [rbx+28h]; pv
0x180019df9  mov     r8d, [rbx+24h]; cb
0x180019dfd  mov     rcx, [rsp+500h+ppstm]; pstm
0x180019e02  call    cs:__imp_IStream_Write
0x180019e08  test    eax, eax
0x180019e0a  js      loc_180019EB9
0x180019e10  mov     rcx, [rsp+500h+ppstm]; pstm
0x180019e15  call    cs:__imp_IStream_Reset
0x180019e1b  mov     r8d, [rbx+20h]; unsigned int
0x180019e1f  mov     dword ptr [rsp+500h+var_498], r8d
0x180019e24  mov     rdx, [rsp+500h+ppstm]; pstm
0x180019e29  mov     rcx, rdi; this
0x180019e2c  call    ?ApplyFullScanResultFromEdge@IEFavResolver@@AEAAJPEAUIStream@@K@Z; IEFavResolver::ApplyFullScanResultFromEdge(IStream *,ulong)
0x180019e31  test    eax, eax
0x180019e33  js      loc_180019EB9
0x180019e39  mov     ecx, 7D0h; dwMilliseconds
0x180019e3e  call    cs:__imp_Sleep
0x180019e44  mov     [rsp+500h+var_4A8], 0
0x180019e4d  lea     r8, [rsp+500h+var_4A8]; ppstm
0x180019e52  mov     edx, r12d; fDeleteOnRelease
0x180019e55  xor     ecx, ecx; hGlobal
0x180019e57  call    cs:__imp_CreateStreamOnHGlobal
0x180019e5d  test    eax, eax
0x180019e5f  js      short loc_180019EAE
0x180019e61  mov     [rsp+500h+var_4A0], 0
0x180019e69  mov     rcx, [rsp+500h+ppstm]; pstm
0x180019e6e  call    cs:__imp_IStream_Reset
0x180019e74  lea     rax, [rsp+500h+var_4A0]
0x180019e79  mov     [rsp+500h+var_4D0], rax; unsigned int *
0x180019e7e  lea     rax, [rsp+500h+var_4A8]
0x180019e83  mov     qword ptr [rsp+500h+nNumberOfBytesToWrite], rax; struct IStream **
0x180019e88  lea     rax, pszSubkey
0x180019e8f  mov     [rsp+500h+lpBuffer], rax; unsigned __int16 *
0x180019e94  lea     r9, aRoot_0; "ROOT"
0x180019e9b  lea     r8, [rsp+500h+var_498]; unsigned int *
0x180019ea0  mov     rdx, [rsp+500h+ppstm]; struct IStream *
0x180019ea5  mov     rcx, rdi; this
0x180019ea8  call    ?ApplyOrderFromEdgeRecursively@IEFavResolver@@AEAAXPEAUIStream@@PEAKPEAG2PEAPEAU2@1@Z; IEFavResolver::ApplyOrderFromEdgeRecursively(IStream *,ulong *,ushort *,ushort *,IStream * *,ulong *)
0x180019ead  nop
0x180019eae  lea     rcx, [rsp+500h+var_4A8]
0x180019eb3  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180019eb8  nop
0x180019eb9  jmp     loc_180019FD9
0x180019ebe  mov     rcx, rdi; this
0x180019ec1  call    ?PerformFullScanOnIEFavorites@IEFavResolver@@AEAAJXZ; IEFavResolver::PerformFullScanOnIEFavorites(void)
0x180019ec6  jmp     loc_18001A10B
0x180019ecb  mov     rbx, [rsp+500h+var_4B0]
0x180019ed0  mov     eax, [rdi+8]
0x180019ed3  cmp     [rbx+4], eax
0x180019ed6  jnz     loc_18001A10B
0x180019edc  mov     dword ptr [rsp+500h+var_4C0], 0
0x180019ee4  lea     r8, [rsp+500h+var_4C0]
0x180019ee9  mov     edx, 234h
0x180019eee  mov     ecx, esi
0x180019ef0  call    cs:__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z; VerifyUntrusted_IsoMessage_MinSize(ulong,ulong,ulong *)
0x180019ef6  test    al, al
0x180019ef8  jz      loc_18001A10B
0x180019efe  mov     eax, [rbx+22Ch]
0x180019f04  add     eax, 234h
0x180019f09  cmp     eax, 234h
0x180019f0e  jb      loc_18001A10B
0x180019f14  cmp     dword ptr [rsp+500h+var_4C0], eax
0x180019f18  jnz     loc_18001A10B
0x180019f1e  mov     eax, cs:dword_18003F000
0x180019f24  cmp     eax, 5
0x180019f27  jbe     short loc_180019F86
0x180019f29  lea     rax, [rbx+20h]
0x180019f2d  mov     [rsp+500h+var_4A8], rax
0x180019f32  mov     byte ptr [rsp+500h+var_4C0+4], r12b
0x180019f37  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019f3d  mov     qword ptr [rsp+500h+var_498], rax
0x180019f42  mov     ecx, 10000003h
0x180019f47  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180019f4d  mov     qword ptr [rsp+500h+var_4A0], rax
0x180019f52  lea     rax, [rsp+500h+var_4A8]
0x180019f57  mov     qword ptr [rsp+500h+var_4C8], rax
0x180019f5c  lea     rax, [rsp+500h+var_4C0+4]
0x180019f61  mov     [rsp+500h+var_4D0], rax
0x180019f66  lea     rax, [rsp+500h+var_498]
0x180019f6b  mov     qword ptr [rsp+500h+nNumberOfBytesToWrite], rax
0x180019f70  lea     rax, [rsp+500h+var_4A0]
0x180019f75  mov     [rsp+500h+lpBuffer], rax
0x180019f7a  lea     rdx, word_180036352
0x180019f81  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180019f86  mov     [rsp+500h+ppstm], 0
0x180019f8f  lea     r8, [rsp+500h+ppstm]; ppstm
0x180019f94  mov     edx, r12d; fDeleteOnRelease
0x180019f97  xor     ecx, ecx; hGlobal
0x180019f99  call    cs:__imp_CreateStreamOnHGlobal
0x180019f9f  test    eax, eax
0x180019fa1  js      short loc_180019FD9
0x180019fa3  lea     rdx, [rbx+230h]; pv
0x180019faa  mov     r8d, [rbx+22Ch]; cb
0x180019fb1  mov     rcx, [rsp+500h+ppstm]; pstm
0x180019fb6  call    cs:__imp_IStream_Write
0x180019fbc  test    eax, eax
0x180019fbe  js      short loc_180019FD9
0x180019fc0  lea     rdx, [rbx+20h]; unsigned __int16 *
0x180019fc4  mov     r9d, [rbx+228h]; unsigned int
0x180019fcb  mov     r8, [rsp+500h+ppstm]; struct IStream *
0x180019fd0  mov     rcx, rdi; this
0x180019fd3  call    ?ApplyFavoriteOrder@IEFavResolver@@AEAAJPEAGPEAUIStream@@K@Z; IEFavResolver::ApplyFavoriteOrder(ushort *,IStream *,ulong)
0x180019fd8  nop
0x180019fd9  lea     rcx, [rsp+500h+ppstm]
0x180019fde  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180019fe3  jmp     loc_18001A10B
0x180019fe8  mov     rbx, [rsp+500h+var_4B0]
0x180019fed  mov     edx, 0CA0h
0x180019ff2  mov     ecx, esi
0x180019ff4  call    cs:__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z; VerifyUntrusted_IsoMessage_ExactSize(ulong,ulong)
0x180019ffa  test    al, al
0x180019ffc  jz      loc_18001A10B
0x18001a002  mov     eax, [rdi+8]
0x18001a005  cmp     [rbx+4], eax
0x18001a008  jnz     loc_18001A10B
0x18001a00e  mov     r12d, 208h
0x18001a014  mov     r8d, r12d; Size
0x18001a017  xor     edx, edx; Val
0x18001a019  lea     rcx, [rbp+400h+pszMore]; void *
0x18001a01d  call    memset_0
0x18001a022  lea     rsi, [rbx+274h]
0x18001a029  lea     r9, [rbp+400h+pszMore]; unsigned __int16 *
0x18001a02d  mov     rdx, rsi; unsigned __int16 *
0x18001a030  call    ?GetRelativePathFromFullUnifiedPath@IEFavResolver@@AEAAJPEBGIPEAG@Z; IEFavResolver::GetRelativePathFromFullUnifiedPath(ushort const *,uint,ushort *)
0x18001a035  test    eax, eax
0x18001a037  js      loc_18001A10B
0x18001a03d  mov     ecx, [rbx+20h]
0x18001a040  sub     ecx, 1
0x18001a043  jz      loc_18001A0D2
0x18001a049  sub     ecx, 1
0x18001a04c  jz      short loc_18001A077
0x18001a04e  cmp     ecx, 1
0x18001a051  jnz     loc_18001A10B
0x18001a057  movzx   r9d, byte ptr [rbx+0C9Ch]; int
0x18001a05f  lea     rdx, [rbx+0A94h]; unsigned __int16 *
0x18001a066  lea     r8, [rbp+400h+pszMore]; pszMore
0x18001a06a  mov     rcx, rdi; this
0x18001a06d  call    ?DeleteFavorite@IEFavResolver@@QEAAJPEBG0H@Z; IEFavResolver::DeleteFavorite(ushort const *,ushort const *,int)
0x18001a072  jmp     loc_18001A10B
0x18001a077  mov     r8, r12; Size
0x18001a07a  xor     edx, edx; Val
0x18001a07c  lea     rcx, [rbp+400h+var_260]; void *
0x18001a083  call    memset_0
0x18001a088  lea     rdx, [rbx+88Ch]; unsigned __int16 *
0x18001a08f  lea     r9, [rbp+400h+var_260]; unsigned __int16 *
0x18001a096  call    ?GetRelativePathFromFullUnifiedPath@IEFavResolver@@AEAAJPEBGIPEAG@Z; IEFavResolver::GetRelativePathFromFullUnifiedPath(ushort const *,uint,ushort *)
0x18001a09b  test    eax, eax
0x18001a09d  js      short loc_18001A10B
0x18001a09f  movzx   eax, byte ptr [rbx+0C9Ch]
0x18001a0a6  lea     r9, [rbx+47Ch]; unsigned __int16 *
0x18001a0ad  lea     rdx, [rbx+0A94h]; unsigned __int16 *
0x18001a0b4  mov     [rsp+500h+nNumberOfBytesToWrite], eax; int
0x18001a0b8  lea     rax, [rbp+400h+pszMore]
0x18001a0bc  mov     [rsp+500h+lpBuffer], rax; PCWSTR
0x18001a0c1  lea     r8, [rbp+400h+var_260]; pszMore
0x18001a0c8  mov     rcx, rdi; this
0x18001a0cb  call    ?UpdateFavorite@IEFavResolver@@QEAAJPEBG000H@Z; IEFavResolver::UpdateFavorite(ushort const *,ushort const *,ushort const *,ushort const *,int)
0x18001a0d0  jmp     short loc_18001A10B
0x18001a0d2  movzx   eax, byte ptr [rbx+0C9Ch]
0x18001a0d9  lea     r8, [rbx+684h]; unsigned __int16 *
0x18001a0e0  lea     rdx, [rbx+47Ch]; unsigned __int16 *
0x18001a0e7  mov     [rsp+500h+nNumberOfBytesToWrite], 0; int
0x18001a0ef  mov     dword ptr [rsp+500h+lpBuffer], eax; int
0x18001a0f3  mov     r9, rsi; unsigned __int16 *
0x18001a0f6  mov     rcx, rdi; this
  ... truncated ...
```
