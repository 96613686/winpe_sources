# BdeSvcLogEventResumeFailure(void *,long)

- ea: `0x180039cb4`
- end: `0x18003a3d2`
- name: `?BdeSvcLogEventResumeFailure@@YAXPEAXJ@Z`
- size: `1822`
- prototype: `void __fastcall(void *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180032b74`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180034070`
- `0x180034d28`
- `0x180039cb4`
- `0x18006a26c`
- `0x18006a4bc`
- `0x18006a594`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e6c`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180039d75`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180039e43`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180039d75`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180039e43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039de2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039de2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a39e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a39e`
- `FVEAPI!FveGetIdentity` at `0x180039e93`
- `FVEAPI!FveGetIdentity` at `0x180039e93`
- `FVEAPI!FveGetVolumeNameW` at `0x180039d2a`
- `FVEAPI!FveGetVolumeNameW` at `0x180039d2a`

## string_xrefs

- `0x180039f6b`: `VolumePath`
- `0x18003a085`: `VolumePath`
- `0x18003a1a1`: `VolumePath`
- `0x18003a2d1`: `VolumePath`

## pseudocode

```c
void __fastcall BdeSvcLogEventResumeFailure(void *a1, int a2)
{
  const unsigned __int16 *v4; // rdx
  unsigned __int16 *v5; // rdi
  int VolumeNameW; // eax
  __int64 v7; // r9
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD v10; // eax
  WCHAR *v11; // rax
  DWORD LastError; // eax
  int Identity; // eax
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rdx
  int v16; // r10d
  const unsigned __int16 *v17; // rdx
  int v18; // r10d
  const unsigned __int16 *v19; // rdx
  unsigned int v20; // [rsp+20h] [rbp-E0h]
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  unsigned int v22; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+40h] [rbp-C0h]
  DWORD cchReturnLength; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v30; // [rsp+58h] [rbp-A8h]
  _QWORD ***v31; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD ***v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+70h] [rbp-90h] BYREF
  _QWORD ***v34; // [rsp+78h] [rbp-88h] BYREF
  _QWORD ***v35; // [rsp+80h] [rbp-80h]
  const wchar_t *v36; // [rsp+88h] [rbp-78h]
  const wchar_t *v37; // [rsp+90h] [rbp-70h]
  GUID *v38; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  _QWORD **v40; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD **v41; // [rsp+B0h] [rbp-50h]
  const wchar_t *v42; // [rsp+B8h] [rbp-48h]
  const wchar_t *v43; // [rsp+C0h] [rbp-40h]
  GUID *v44; // [rsp+C8h] [rbp-38h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  _QWORD **v46; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD **v47; // [rsp+E0h] [rbp-20h]
  __int128 v48; // [rsp+E8h] [rbp-18h]
  __int128 v49; // [rsp+F8h] [rbp-8h]
  _QWORD *v50; // [rsp+108h] [rbp+8h] BYREF
  _QWORD *v51; // [rsp+110h] [rbp+10h]
  __int128 v52; // [rsp+118h] [rbp+18h]
  __int128 v53; // [rsp+128h] [rbp+28h]
  int v54; // [rsp+138h] [rbp+38h] BYREF
  DWORD v55; // [rsp+13Ch] [rbp+3Ch] BYREF
  GUID v56; // [rsp+140h] [rbp+40h] BYREF
  WCHAR szVolumeName[264]; // [rsp+150h] [rbp+50h] BYREF

  memset_0(szVolumeName, 0, 0x208u);
  v54 = 260;
  v5 = 0;
  cchReturnLength = 0;
  v56 = GUID_NULL;
  if ( a1 )
  {
    VolumeNameW = FveGetVolumeNameW(a1, &v54, szVolumeName);
    v7 = (unsigned int)VolumeNameW;
    if ( VolumeNameW >= 0 )
    {
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, &cchReturnLength)
        || (v10 = GetLastError(), v7 = v10, v10 == 234) )
      {
        v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchReturnLength);
        v5 = v11;
        if ( v11 )
        {
          v55 = 0;
          if ( GetVolumePathNamesForVolumeNameW(szVolumeName, v11, cchReturnLength, &v55) )
          {
            Identity = FveGetIdentity(a1, &v56);
            v7 = (unsigned int)Identity;
            if ( Identity < 0 )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v9 = 14;
                goto LABEL_23;
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            LastError = GetLastError();
            v9 = 13;
            v7 = LastError;
            v8 = WPP_GLOBAL_Control;
            goto LABEL_23;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b49306262e623cc86cddd9e33f8f13e1_Traceguids);
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v9 = 11;
          goto LABEL_23;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 10;
LABEL_23:
        WPP_SF_d(v8[2], v9, WPP_b49306262e623cc86cddd9e33f8f13e1_Traceguids, v7);
      }
    }
  }
  if ( a2 == -2144862148 || a2 == -2144862143 )
  {
    v29 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v42 = L"IdentityGuid";
    v43 = L"GUID";
    v44 = &v56;
    v45 = 16;
    v41 = &v31;
    v31 = &v40;
    v52 = 0;
    v53 = 0;
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v50, v4, L"VolumePath", szVolumeName, v20);
    v51 = &v40;
    v40 = &v50;
    v48 = 0;
    v49 = 0;
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v46, v19, L"VolumeDriveLetter", v5, v24);
    v47 = &v50;
    v50 = &v46;
    v33 = a2;
    v36 = L"hr";
    v37 = L"HRESULT";
    v38 = (GUID *)&v33;
    v39 = 4;
    v34 = &v31;
    v35 = &v46;
    v46 = &v34;
    v32 = &v34;
    v30 = FVEAPI_OP_RESUME_TPM_LOCKED_OUT_FAILURE;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v25, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v29);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v25);
  }
  else
  {
    v29 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    if ( a2 == -2144272336 )
    {
      v42 = L"IdentityGuid";
      v43 = L"GUID";
      v44 = &v56;
      v45 = 16;
      v41 = &v31;
      v31 = &v40;
      v52 = 0;
      v53 = 0;
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v50, v4, L"VolumePath", szVolumeName, v20);
      v51 = &v40;
      v40 = &v50;
      v48 = 0;
      v49 = 0;
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v46, v17, L"VolumeDriveLetter", v5, v23);
      v47 = &v50;
      v50 = &v46;
      v33 = v18;
      v36 = L"hr";
      v37 = L"HRESULT";
      v38 = (GUID *)&v33;
      v39 = 4;
      v34 = &v31;
      v35 = &v46;
      v46 = &v34;
      v32 = &v34;
      v30 = FVEAPI_OP_RESUME_ON_BOOTABLE_MEDIA_FAILURE;
      FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v25, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v29);
      FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v25);
    }
    else
    {
      if ( a2 == -2144272293 )
      {
        v42 = L"IdentityGuid";
        v43 = L"GUID";
        v44 = &v56;
        v45 = 16;
        v41 = &v31;
        v31 = &v40;
        v52 = 0;
        v53 = 0;
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v50, v4, L"VolumePath", szVolumeName, v20);
        v51 = &v40;
        v40 = &v50;
        v48 = 0;
        v49 = 0;
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v46, v15, L"VolumeDriveLetter", v5, v22);
        v47 = &v50;
        v50 = &v46;
        v33 = v16;
        v36 = L"hr";
        v37 = L"HRESULT";
        v38 = (GUID *)&v33;
        v39 = 4;
        v34 = &v31;
        v35 = &v46;
        v46 = &v34;
        v32 = &v34;
        v30 = FVEAPI_OP_RESUME_GROUP_POLICY_CONFLICT_FAILURE;
      }
      else
      {
        v36 = L"IdentityGuid";
        v37 = L"GUID";
        v38 = &v56;
        v39 = 16;
        v35 = &v31;
        v31 = &v34;
        v48 = 0;
        v49 = 0;
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v46, v4, L"VolumePath", szVolumeName, v20);
        v47 = &v34;
        v34 = &v46;
        v52 = 0;
        v53 = 0;
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v50, v14, L"VolumeDriveLetter", v5, v21);
        v51 = &v46;
        v46 = &v50;
        v33 = a2;
        v42 = L"hr";
        v43 = L"HRESULT";
        v44 = (GUID *)&v33;
        v45 = 4;
        v40 = &v31;
        v41 = &v50;
        v50 = &v40;
        v32 = &v40;
        v30 = FVEAPI_OP_RESUME_FAILURE;
      }
      FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v25, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v29);
      FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v25);
    }
  }
  LocalFree(v5);
}

```

## disassembly

```asm
0x180039cb4  mov     [rsp-8+arg_10], rbx
0x180039cb9  mov     [rsp-8+arg_18], rsi
0x180039cbe  push    rbp
0x180039cbf  push    rdi
0x180039cc0  push    r14
0x180039cc2  lea     rbp, [rsp-270h]
0x180039cca  sub     rsp, 370h
0x180039cd1  mov     rax, cs:__security_cookie
0x180039cd8  xor     rax, rsp
0x180039cdb  mov     [rbp+280h+var_20], rax
0x180039ce2  mov     ebx, edx
0x180039ce4  mov     rsi, rcx
0x180039ce7  xor     edx, edx; Val
0x180039ce9  mov     r8d, 208h; Size
0x180039cef  lea     rcx, [rbp+280h+szVolumeName]; void *
0x180039cf3  call    memset_0
0x180039cf8  mov     [rbp+280h+var_248], 104h
0x180039cff  xor     r14d, r14d
0x180039d02  mov     edi, r14d
0x180039d05  mov     [rsp+380h+cchReturnLength], r14d
0x180039d0a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180039d11  movdqu  [rbp+280h+var_240], xmm0
0x180039d16  test    rsi, rsi
0x180039d19  jz      loc_180039ED4
0x180039d1f  lea     r8, [rbp+280h+szVolumeName]
0x180039d23  lea     rdx, [rbp+280h+var_248]
0x180039d27  mov     rcx, rsi
0x180039d2a  call    cs:__imp_FveGetVolumeNameW
0x180039d31  nop     dword ptr [rax+rax+00h]
0x180039d36  mov     r9d, eax
0x180039d39  test    eax, eax
0x180039d3b  jns     short loc_180039D67
0x180039d3d  lea     rax, WPP_GLOBAL_Control
0x180039d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180039d4b  cmp     rcx, rax
0x180039d4e  jz      loc_180039ED4
0x180039d54  test    byte ptr [rcx+1Ch], 2
0x180039d58  jz      loc_180039ED4
0x180039d5e  lea     edx, [r14+0Ah]
0x180039d62  jmp     loc_180039EC4
0x180039d67  lea     r9, [rsp+380h+cchReturnLength]; lpcchReturnLength
0x180039d6c  xor     r8d, r8d; cchBufferLength
0x180039d6f  xor     edx, edx; lpszVolumePathNames
0x180039d71  lea     rcx, [rbp+280h+szVolumeName]; lpszVolumeName
0x180039d75  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180039d7c  nop     dword ptr [rax+rax+00h]
0x180039d81  test    eax, eax
0x180039d83  jnz     short loc_180039DD6
0x180039d85  call    cs:__imp_GetLastError
0x180039d8c  nop     dword ptr [rax+rax+00h]
0x180039d91  mov     r9d, eax
0x180039d94  cmp     eax, 0EAh
0x180039d99  jz      short loc_180039DD6
0x180039d9b  lea     rax, WPP_GLOBAL_Control
0x180039da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180039da9  cmp     rcx, rax
0x180039dac  jz      loc_180039ED4
0x180039db2  test    byte ptr [rcx+1Ch], 2
0x180039db6  jz      loc_180039ED4
0x180039dbc  mov     edx, 0Bh
0x180039dc1  lea     r8, WPP_b49306262e623cc86cddd9e33f8f13e1_Traceguids
0x180039dc8  mov     rcx, [rcx+10h]
0x180039dcc  call    WPP_SF_d
0x180039dd1  jmp     loc_180039ED4
0x180039dd6  mov     edx, [rsp+380h+cchReturnLength]
0x180039dda  add     rdx, rdx; uBytes
0x180039ddd  mov     ecx, 40h ; '@'; uFlags
0x180039de2  call    cs:__imp_LocalAlloc
0x180039de9  nop     dword ptr [rax+rax+00h]
0x180039dee  mov     rdi, rax
0x180039df1  test    rax, rax
0x180039df4  jnz     short loc_180039E2F
0x180039df6  lea     rax, WPP_GLOBAL_Control
0x180039dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e04  cmp     rcx, rax
0x180039e07  jz      loc_180039ED4
0x180039e0d  test    byte ptr [rcx+1Ch], 2
0x180039e11  jz      loc_180039ED4
0x180039e17  lea     edx, [rdi+0Ch]
0x180039e1a  lea     r8, WPP_b49306262e623cc86cddd9e33f8f13e1_Traceguids
0x180039e21  mov     rcx, [rcx+10h]
0x180039e25  call    WPP_SF_
0x180039e2a  jmp     loc_180039ED4
0x180039e2f  mov     [rbp+280h+var_244], r14d
0x180039e33  lea     r9, [rbp+280h+var_244]; lpcchReturnLength
0x180039e37  mov     r8d, [rsp+380h+cchReturnLength]; cchBufferLength
0x180039e3c  mov     rdx, rax; lpszVolumePathNames
0x180039e3f  lea     rcx, [rbp+280h+szVolumeName]; lpszVolumeName
0x180039e43  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180039e4a  nop     dword ptr [rax+rax+00h]
0x180039e4f  test    eax, eax
0x180039e51  jnz     short loc_180039E8C
0x180039e53  lea     rax, WPP_GLOBAL_Control
0x180039e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e61  cmp     rcx, rax
0x180039e64  jz      short loc_180039ED4
0x180039e66  test    byte ptr [rcx+1Ch], 2
0x180039e6a  jz      short loc_180039ED4
0x180039e6c  call    cs:__imp_GetLastError
0x180039e73  nop     dword ptr [rax+rax+00h]
0x180039e78  mov     edx, 0Dh
0x180039e7d  mov     r9d, eax
0x180039e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e87  jmp     loc_180039DC1
0x180039e8c  lea     rdx, [rbp+280h+var_240]
0x180039e90  mov     rcx, rsi
0x180039e93  call    cs:__imp_FveGetIdentity
0x180039e9a  nop     dword ptr [rax+rax+00h]
0x180039e9f  mov     r9d, eax
0x180039ea2  test    eax, eax
0x180039ea4  jns     short loc_180039ED4
0x180039ea6  lea     rax, WPP_GLOBAL_Control
0x180039ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180039eb4  cmp     rcx, rax
0x180039eb7  jz      short loc_180039ED4
0x180039eb9  test    byte ptr [rcx+1Ch], 2
0x180039ebd  jz      short loc_180039ED4
0x180039ebf  mov     edx, 0Eh
0x180039ec4  lea     r8, WPP_b49306262e623cc86cddd9e33f8f13e1_Traceguids
0x180039ecb  mov     rcx, [rcx+10h]
0x180039ecf  call    WPP_SF_d
0x180039ed4  cmp     ebx, 8028003Ch
0x180039eda  jz      loc_18003A271
0x180039ee0  cmp     ebx, 80280041h
0x180039ee6  jz      loc_18003A271
0x180039eec  mov     r10d, 80310030h
0x180039ef2  mov     [rsp+380h+var_330], r14
0x180039ef7  mov     [rsp+380h+var_350], r14
0x180039efc  mov     [rsp+380h+var_348], r14
0x180039f01  mov     [rsp+380h+var_340], r14
0x180039f06  cmp     ebx, r10d
0x180039f09  jz      loc_18003A155
0x180039f0f  mov     r10d, 8031005Bh
0x180039f15  cmp     ebx, r10d
0x180039f18  jz      loc_18003A039
0x180039f1e  lea     rax, aIdentityguid; "IdentityGuid"
0x180039f25  lea     rcx, aGuid; "GUID"
0x180039f2c  lea     r8, [rbp+280h+var_240]
0x180039f30  mov     [rbp+280h+var_2F8], rax
0x180039f34  mov     [rbp+280h+var_2F0], rcx
0x180039f38  mov     [rbp+280h+var_2E8], r8
0x180039f3c  mov     [rbp+280h+var_2E0], 10h
0x180039f44  lea     rax, [rsp+380h+var_320]
0x180039f49  mov     [rbp+280h+var_300], rax
0x180039f4d  lea     rax, [rsp+380h+var_308]
0x180039f52  mov     [rsp+380h+var_320], rax
0x180039f57  xorps   xmm0, xmm0
0x180039f5a  movdqu  [rbp+280h+var_298], xmm0
0x180039f5f  xorps   xmm1, xmm1
0x180039f62  movdqu  [rbp+280h+var_288], xmm1
0x180039f67  lea     r9, [rbp+280h+szVolumeName]; unsigned __int16 *
0x180039f6b  lea     r8, aVolumepath; "VolumePath"
0x180039f72  lea     rcx, [rbp+280h+var_2A8]; struct _FVEAPI_EVENT_DATA *
0x180039f76  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x180039f7b  lea     rcx, [rsp+380h+var_308]
0x180039f80  mov     [rbp+280h+var_2A0], rcx
0x180039f84  lea     rax, [rbp+280h+var_2A8]
0x180039f88  mov     [rsp+380h+var_308], rax
0x180039f8d  xorps   xmm0, xmm0
0x180039f90  movdqu  [rbp+280h+var_268], xmm0
0x180039f95  xorps   xmm1, xmm1
0x180039f98  movdqu  [rbp+280h+var_258], xmm1
0x180039f9d  mov     r9, rdi; unsigned __int16 *
0x180039fa0  lea     r8, aVolumedrivelet; "VolumeDriveLetter"
0x180039fa7  lea     rcx, [rbp+280h+var_278]; struct _FVEAPI_EVENT_DATA *
0x180039fab  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x180039fb0  lea     rcx, [rbp+280h+var_2A8]
0x180039fb4  mov     [rbp+280h+var_270], rcx
0x180039fb8  lea     rax, [rbp+280h+var_278]
0x180039fbc  mov     [rbp+280h+var_2A8], rax
0x180039fc0  mov     [rsp+380h+var_310], ebx
0x180039fc4  lea     rax, aHr; "hr"
0x180039fcb  lea     rcx, aHresult; "HRESULT"
0x180039fd2  lea     r8, [rsp+380h+var_310]
0x180039fd7  mov     [rbp+280h+var_2C8], rax
0x180039fdb  mov     [rbp+280h+var_2C0], rcx
0x180039fdf  mov     [rbp+280h+var_2B8], r8
0x180039fe3  mov     [rbp+280h+var_2B0], 4
0x180039feb  lea     rax, [rsp+380h+var_320]
0x180039ff0  mov     [rbp+280h+var_2D8], rax
0x180039ff4  lea     rax, [rbp+280h+var_278]
0x180039ff8  mov     [rbp+280h+var_2D0], rax
0x180039ffc  lea     rax, [rbp+280h+var_2D8]
0x18003a000  mov     [rbp+280h+var_278], rax
0x18003a004  lea     rax, [rbp+280h+var_2D8]
0x18003a008  mov     [rsp+380h+var_318], rax
0x18003a00d  lea     rax, FVEAPI_OP_RESUME_FAILURE
0x18003a014  mov     [rsp+380h+var_328], rax
0x18003a019  lea     rdx, [rsp+380h+var_330]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x18003a01e  lea     rcx, [rsp+380h+var_350]; this
0x18003a023  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x18003a028  nop
0x18003a029  lea     rcx, [rsp+380h+var_350]; this
0x18003a02e  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x18003a033  nop
0x18003a034  jmp     loc_18003A39B
0x18003a039  lea     rax, aIdentityguid; "IdentityGuid"
0x18003a040  lea     rcx, aGuid; "GUID"
0x18003a047  lea     r8, [rbp+280h+var_240]
0x18003a04b  mov     [rbp+280h+var_2C8], rax
0x18003a04f  mov     [rbp+280h+var_2C0], rcx
0x18003a053  mov     [rbp+280h+var_2B8], r8
0x18003a057  mov     [rbp+280h+var_2B0], 10h
0x18003a05f  lea     rax, [rsp+380h+var_320]
0x18003a064  mov     [rbp+280h+var_2D0], rax
0x18003a068  lea     rax, [rbp+280h+var_2D8]
0x18003a06c  mov     [rsp+380h+var_320], rax
0x18003a071  xorps   xmm0, xmm0
0x18003a074  movdqu  [rbp+280h+var_268], xmm0
0x18003a079  xorps   xmm1, xmm1
0x18003a07c  movdqu  [rbp+280h+var_258], xmm1
0x18003a081  lea     r9, [rbp+280h+szVolumeName]; unsigned __int16 *
0x18003a085  lea     r8, aVolumepath; "VolumePath"
0x18003a08c  lea     rcx, [rbp+280h+var_278]; struct _FVEAPI_EVENT_DATA *
0x18003a090  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x18003a095  lea     rcx, [rbp+280h+var_2D8]
0x18003a099  mov     [rbp+280h+var_270], rcx
0x18003a09d  lea     rax, [rbp+280h+var_278]
0x18003a0a1  mov     [rbp+280h+var_2D8], rax
0x18003a0a5  xorps   xmm0, xmm0
0x18003a0a8  movdqu  [rbp+280h+var_298], xmm0
0x18003a0ad  xorps   xmm1, xmm1
0x18003a0b0  movdqu  [rbp+280h+var_288], xmm1
0x18003a0b5  mov     r9, rdi; unsigned __int16 *
0x18003a0b8  lea     r8, aVolumedrivelet; "VolumeDriveLetter"
0x18003a0bf  lea     rcx, [rbp+280h+var_2A8]; struct _FVEAPI_EVENT_DATA *
0x18003a0c3  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x18003a0c8  lea     rcx, [rbp+280h+var_278]
0x18003a0cc  mov     [rbp+280h+var_2A0], rcx
0x18003a0d0  lea     rax, [rbp+280h+var_2A8]
0x18003a0d4  mov     [rbp+280h+var_278], rax
0x18003a0d8  mov     [rsp+380h+var_310], r10d
0x18003a0dd  lea     rax, aHr; "hr"
0x18003a0e4  lea     rcx, aHresult; "HRESULT"
0x18003a0eb  lea     r8, [rsp+380h+var_310]
0x18003a0f0  mov     [rbp+280h+var_2F8], rax
0x18003a0f4  mov     [rbp+280h+var_2F0], rcx
0x18003a0f8  mov     [rbp+280h+var_2E8], r8
0x18003a0fc  mov     [rbp+280h+var_2E0], 4
0x18003a104  lea     rax, [rsp+380h+var_320]
0x18003a109  mov     [rsp+380h+var_308], rax
0x18003a10e  lea     rax, [rbp+280h+var_2A8]
0x18003a112  mov     [rbp+280h+var_300], rax
0x18003a116  lea     rax, [rsp+380h+var_308]
0x18003a11b  mov     [rbp+280h+var_2A8], rax
0x18003a11f  lea     rax, [rsp+380h+var_308]
0x18003a124  mov     [rsp+380h+var_318], rax
0x18003a129  lea     rax, FVEAPI_OP_RESUME_GROUP_POLICY_CONFLICT_FAILURE
0x18003a130  mov     [rsp+380h+var_328], rax
0x18003a135  lea     rdx, [rsp+380h+var_330]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x18003a13a  lea     rcx, [rsp+380h+var_350]; this
0x18003a13f  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x18003a144  nop
0x18003a145  lea     rcx, [rsp+380h+var_350]; this
0x18003a14a  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x18003a14f  nop
0x18003a150  jmp     loc_18003A39B
0x18003a155  lea     rax, aIdentityguid; "IdentityGuid"
0x18003a15c  lea     rcx, aGuid; "GUID"
0x18003a163  lea     r8, [rbp+280h+var_240]
0x18003a167  mov     [rbp+280h+var_2C8], rax
0x18003a16b  mov     [rbp+280h+var_2C0], rcx
0x18003a16f  mov     [rbp+280h+var_2B8], r8
0x18003a173  mov     [rbp+280h+var_2B0], 10h
0x18003a17b  lea     rax, [rsp+380h+var_320]
0x18003a180  mov     [rbp+280h+var_2D0], rax
0x18003a184  lea     rax, [rbp+280h+var_2D8]
0x18003a188  mov     [rsp+380h+var_320], rax
0x18003a18d  xorps   xmm0, xmm0
0x18003a190  movdqu  [rbp+280h+var_268], xmm0
0x18003a195  xorps   xmm1, xmm1
0x18003a198  movdqu  [rbp+280h+var_258], xmm1
0x18003a19d  lea     r9, [rbp+280h+szVolumeName]; unsigned __int16 *
0x18003a1a1  lea     r8, aVolumepath; "VolumePath"
0x18003a1a8  lea     rcx, [rbp+280h+var_278]; struct _FVEAPI_EVENT_DATA *
0x18003a1ac  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x18003a1b1  lea     rcx, [rbp+280h+var_2D8]
0x18003a1b5  mov     [rbp+280h+var_270], rcx
0x18003a1b9  lea     rax, [rbp+280h+var_278]
0x18003a1bd  mov     [rbp+280h+var_2D8], rax
0x18003a1c1  xorps   xmm0, xmm0
0x18003a1c4  movdqu  [rbp+280h+var_298], xmm0
0x18003a1c9  xorps   xmm1, xmm1
0x18003a1cc  movdqu  [rbp+280h+var_288], xmm1
0x18003a1d1  mov     r9, rdi; unsigned __int16 *
0x18003a1d4  lea     r8, aVolumedrivelet; "VolumeDriveLetter"
0x18003a1db  lea     rcx, [rbp+280h+var_2A8]; struct _FVEAPI_EVENT_DATA *
0x18003a1df  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x18003a1e4  lea     rcx, [rbp+280h+var_278]
0x18003a1e8  mov     [rbp+280h+var_2A0], rcx
0x18003a1ec  lea     rax, [rbp+280h+var_2A8]
0x18003a1f0  mov     [rbp+280h+var_278], rax
0x18003a1f4  mov     [rsp+380h+var_310], r10d
0x18003a1f9  lea     rax, aHr; "hr"
0x18003a200  lea     rcx, aHresult; "HRESULT"
0x18003a207  lea     r8, [rsp+380h+var_310]
0x18003a20c  mov     [rbp+280h+var_2F8], rax
0x18003a210  mov     [rbp+280h+var_2F0], rcx
0x18003a214  mov     [rbp+280h+var_2E8], r8
0x18003a218  mov     [rbp+280h+var_2E0], 4
  ... truncated ...
```
