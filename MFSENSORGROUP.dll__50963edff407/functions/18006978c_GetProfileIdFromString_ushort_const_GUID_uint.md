# GetProfileIdFromString(ushort const *,_GUID *,uint *)

- ea: `0x18006978c`
- end: `0x180069a85`
- name: `?GetProfileIdFromString@@YAJPEBGPEAU_GUID@@PEAI@Z`
- size: `761`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCLSID pclsid, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068590`
- `0x180069f34`

## callees

- `0x180005fa0`
- `0x18000d1f0`
- `0x180015e80`
- `0x180044f30`
- `0x180045360`
- `0x180045900`
- `0x18006978c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006995f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180069981`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800699a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800699bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800699de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800699fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006995f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180069981`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800699a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800699bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800699de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800699fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180069a30`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180069a30`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180069a66`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180069a66`
- `MFPlat!MFTraceError` at `0x1800698ed`
- `MFPlat!MFTraceError` at `0x1800698ed`

## pseudocode

```c
__int64 __fastcall GetProfileIdFromString(const unsigned __int16 *a1, LPCLSID pclsid, unsigned int *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned __int64 v9; // r10
  __int64 v10; // rdx
  OLECHAR *v11; // r14
  unsigned __int64 i; // rcx
  unsigned __int64 v13; // rdx
  GUID v14; // xmm0
  unsigned __int64 v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[264]; // [rsp+40h] [rbp-C0h] BYREF

  v16[0] = 0;
  memset_0(sz, 0, 0x208u);
  if ( a1 )
  {
    if ( !pclsid )
    {
      v6 = -2147467261;
      v7 = -2147467261;
      if ( !g_wppLevels )
        return v7;
      v8 = 11;
      goto LABEL_4;
    }
    if ( !a3 )
    {
      v6 = -2147467261;
      v7 = -2147467261;
      if ( !g_wppLevels )
        return v7;
      v8 = 12;
      goto LABEL_4;
    }
    *a3 = 0;
    v6 = StringCchLengthW(a1, 0x7FFFFFFFu, v16);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        return v7;
      v8 = 13;
      goto LABEL_4;
    }
    v6 = StringCchLengthW(a1, v9, v16);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        return v7;
      v8 = 14;
      goto LABEL_4;
    }
    if ( !v16[0] )
    {
      v10 = 65;
LABEL_19:
      v7 = -2147024809;
      MFTraceError(
        "avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp",
        v10,
        "GetProfileIdFromString",
        0,
        -2147024809,
        1);
      return v7;
    }
    if ( v16[0] >= 0x104 )
    {
      v10 = 66;
      goto LABEL_19;
    }
    v11 = 0;
    StringCchCopyW(sz, 0x104u, a1);
    for ( i = 0; i < v16[0]; ++i )
    {
      v13 = i;
      if ( sz[i] == 44 )
      {
        if ( v13 >= 260 )
          _report_rangecheckfailure();
        sz[i] = 0;
        v11 = &sz[v13 + 1];
      }
    }
    if ( (unsigned int)_o__wcsicmp(sz, L"KSCAMERAPROFILE_VideoRecording") )
    {
      if ( (unsigned int)_o__wcsicmp(sz, L"KSCAMERAPROFILE_HighQualityPhoto") )
      {
        if ( (unsigned int)_o__wcsicmp(sz, L"KSCAMERAPROFILE_BalancedVideoAndPhoto") )
        {
          if ( (unsigned int)_o__wcsicmp(sz, L"KSCAMERAPROFILE_VideoConferencing") )
          {
            if ( (unsigned int)_o__wcsicmp(sz, L"KSCAMERAPROFILE_PhotoSequence") )
            {
              if ( (unsigned int)_o__wcsicmp(sz, L"KSCAMERAPROFILE_FaceAuth_Mode") )
              {
                v6 = CLSIDFromString(sz, pclsid);
                v7 = v6;
                if ( v6 < 0 )
                {
                  if ( !g_wppLevels )
                    return v7;
                  v8 = 15;
                  goto LABEL_4;
                }
                goto LABEL_42;
              }
              v14 = GUID_81361b22_700b_4546_a2d4_c52e907bfc27;
            }
            else
            {
              v14 = GUID_02399d9d_4ee8_49ba_bc07_5ff156531413;
            }
          }
          else
          {
            v14 = GUID_c5444a88_e1bf_4597_b2dd_9e1ead864bb8;
          }
        }
        else
        {
          v14 = GUID_6b52b017_42c7_4a21_bfe3_23f009149887;
        }
      }
      else
      {
        v14 = GUID_32440725_961b_4ca3_b5b2_854e719d9e1b;
      }
    }
    else
    {
      v14 = GUID_a0e517e8_8f8c_4f6f_9a57_46fc2f647ec0;
    }
    *pclsid = v14;
LABEL_42:
    if ( v11 && *v11 )
    {
      v16[0] = 0;
      *a3 = _o__wcstoui64(v11, v16, 10);
    }
    return v7;
  }
  v6 = -2147024809;
  v7 = -2147024809;
  if ( g_wppLevels )
  {
    v8 = 10;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids, 0, v6);
  }
  return v7;
}

```

## disassembly

```asm
0x18006978c  push    rbp
0x18006978e  push    rbx
0x18006978f  push    rdi
0x180069790  push    r12
0x180069792  push    r13
0x180069794  push    r14
0x180069796  push    r15
0x180069798  lea     rbp, [rsp-160h]
0x1800697a0  sub     rsp, 260h
0x1800697a7  mov     rax, cs:__security_cookie
0x1800697ae  xor     rax, rsp
0x1800697b1  mov     [rbp+190h+var_40], rax
0x1800697b8  mov     r12, r8
0x1800697bb  mov     rdi, rdx
0x1800697be  mov     r15, rcx
0x1800697c1  xor     r13d, r13d
0x1800697c4  xor     edx, edx; Val
0x1800697c6  mov     [rsp+290h+var_260], r13
0x1800697cb  mov     r8d, 208h; Size
0x1800697d1  lea     rcx, [rsp+290h+sz]; void *
0x1800697d6  call    memset_0
0x1800697db  test    r15, r15
0x1800697de  jnz     short loc_18006981B
0x1800697e0  mov     eax, 80070057h
0x1800697e5  mov     ebx, eax
0x1800697e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800697ee  jb      loc_180069A3A
0x1800697f4  lea     edx, [r13+0Ah]
0x1800697f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800697ff  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x180069806  xor     r9d, r9d
0x180069809  mov     [rsp+290h+var_270], eax
0x18006980d  mov     rcx, [rcx+10h]
0x180069811  call    WPP_SF_qD
0x180069816  jmp     loc_180069A3A
0x18006981b  test    rdi, rdi
0x18006981e  jnz     short loc_180069839
0x180069820  mov     eax, 80004003h
0x180069825  mov     ebx, eax
0x180069827  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006982e  jb      loc_180069A3A
0x180069834  lea     edx, [rdi+0Bh]
0x180069837  jmp     short loc_1800697F8
0x180069839  test    r12, r12
0x18006983c  jnz     short loc_180069859
0x18006983e  mov     eax, 80004003h
0x180069843  mov     ebx, eax
0x180069845  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006984c  jb      loc_180069A3A
0x180069852  lea     edx, [r12+0Ch]
0x180069857  jmp     short loc_1800697F8
0x180069859  mov     r10d, 7FFFFFFFh
0x18006985f  mov     [r12], r13d
0x180069863  mov     edx, r10d; unsigned __int64
0x180069866  lea     r8, [rsp+290h+var_260]; unsigned __int64 *
0x18006986b  mov     rcx, r15; unsigned __int16 *
0x18006986e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180069873  mov     ebx, eax
0x180069875  test    eax, eax
0x180069877  jns     short loc_180069890
0x180069879  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069880  jb      loc_180069A3A
0x180069886  mov     edx, 0Dh
0x18006988b  jmp     loc_1800697F8
0x180069890  lea     r8, [rsp+290h+var_260]; unsigned __int64 *
0x180069895  mov     rdx, r10; unsigned __int64
0x180069898  mov     rcx, r15; unsigned __int16 *
0x18006989b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800698a0  mov     ebx, eax
0x1800698a2  test    eax, eax
0x1800698a4  jns     short loc_1800698BD
0x1800698a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800698ad  jb      loc_180069A3A
0x1800698b3  mov     edx, 0Eh
0x1800698b8  jmp     loc_1800697F8
0x1800698bd  cmp     [rsp+290h+var_260], r13
0x1800698c2  jnz     short loc_1800698F8
0x1800698c4  mov     edx, 41h ; 'A'
0x1800698c9  mov     eax, 80070057h
0x1800698ce  mov     [rsp+290h+var_268], 1
0x1800698d6  lea     r8, aGetprofileidfr; "GetProfileIdFromString"
0x1800698dd  mov     [rsp+290h+var_270], eax
0x1800698e1  xor     r9d, r9d
0x1800698e4  lea     rcx, aAvcoreMfCoreMe; "avcore\\mf\\core\\mediasource\\profiles"...
0x1800698eb  mov     ebx, eax
0x1800698ed  call    cs:__imp_MFTraceError
0x1800698f3  jmp     loc_180069A3A
0x1800698f8  mov     edx, 104h; unsigned __int64
0x1800698fd  cmp     [rsp+290h+var_260], rdx
0x180069902  jb      short loc_18006990B
0x180069904  mov     edx, 42h ; 'B'
0x180069909  jmp     short loc_1800698C9
0x18006990b  mov     r8, r15; unsigned __int16 *
0x18006990e  lea     rcx, [rsp+290h+sz]; unsigned __int16 *
0x180069913  mov     r14, r13
0x180069916  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006991b  mov     rcx, r13
0x18006991e  cmp     rcx, [rsp+290h+var_260]
0x180069923  jnb     short loc_180069953
0x180069925  lea     rdx, [rcx+rcx]
0x180069929  cmp     [rsp+rdx+290h+sz], 2Ch ; ','
0x18006992f  jnz     short loc_180069948
0x180069931  cmp     rdx, 208h
0x180069938  jnb     short loc_18006994D
0x18006993a  lea     r14, [rsp+290h+var_24E]
0x18006993f  mov     [rsp+rdx+290h+sz], r13w
0x180069945  add     r14, rdx
0x180069948  inc     rcx
0x18006994b  jmp     short loc_18006991E
0x18006994d  call    __report_rangecheckfailure
0x180069953  lea     rdx, aKscameraprofil_16; "KSCAMERAPROFILE_VideoRecording"
0x18006995a  lea     rcx, [rsp+290h+sz]
0x18006995f  call    cs:__imp__o__wcsicmp
0x180069965  test    eax, eax
0x180069967  jnz     short loc_180069975
0x180069969  movups  xmm0, xmmword ptr cs:_GUID_a0e517e8_8f8c_4f6f_9a57_46fc2f647ec0.Data1
0x180069970  jmp     loc_180069A0E
0x180069975  lea     rdx, aKscameraprofil_1; "KSCAMERAPROFILE_HighQualityPhoto"
0x18006997c  lea     rcx, [rsp+290h+sz]
0x180069981  call    cs:__imp__o__wcsicmp
0x180069987  test    eax, eax
0x180069989  jnz     short loc_180069994
0x18006998b  movups  xmm0, xmmword ptr cs:_GUID_32440725_961b_4ca3_b5b2_854e719d9e1b.Data1
0x180069992  jmp     short loc_180069A0E
0x180069994  lea     rdx, aKscameraprofil_11; "KSCAMERAPROFILE_BalancedVideoAndPhoto"
0x18006999b  lea     rcx, [rsp+290h+sz]
0x1800699a0  call    cs:__imp__o__wcsicmp
0x1800699a6  test    eax, eax
0x1800699a8  jnz     short loc_1800699B3
0x1800699aa  movups  xmm0, xmmword ptr cs:_GUID_6b52b017_42c7_4a21_bfe3_23f009149887.Data1
0x1800699b1  jmp     short loc_180069A0E
0x1800699b3  lea     rdx, aKscameraprofil_20; "KSCAMERAPROFILE_VideoConferencing"
0x1800699ba  lea     rcx, [rsp+290h+sz]
0x1800699bf  call    cs:__imp__o__wcsicmp
0x1800699c5  test    eax, eax
0x1800699c7  jnz     short loc_1800699D2
0x1800699c9  movups  xmm0, xmmword ptr cs:_GUID_c5444a88_e1bf_4597_b2dd_9e1ead864bb8.Data1
0x1800699d0  jmp     short loc_180069A0E
0x1800699d2  lea     rdx, aKscameraprofil_2; "KSCAMERAPROFILE_PhotoSequence"
0x1800699d9  lea     rcx, [rsp+290h+sz]
0x1800699de  call    cs:__imp__o__wcsicmp
0x1800699e4  test    eax, eax
0x1800699e6  jnz     short loc_1800699F1
0x1800699e8  movups  xmm0, xmmword ptr cs:_GUID_02399d9d_4ee8_49ba_bc07_5ff156531413.Data1
0x1800699ef  jmp     short loc_180069A0E
0x1800699f1  lea     rdx, aKscameraprofil_8; "KSCAMERAPROFILE_FaceAuth_Mode"
0x1800699f8  lea     rcx, [rsp+290h+sz]
0x1800699fd  call    cs:__imp__o__wcsicmp
0x180069a03  test    eax, eax
0x180069a05  jnz     short loc_180069A5E
0x180069a07  movups  xmm0, xmmword ptr cs:_GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data1
0x180069a0e  movdqu  xmmword ptr [rdi], xmm0
0x180069a12  test    r14, r14
0x180069a15  jz      short loc_180069A3A
0x180069a17  cmp     [r14], r13w
0x180069a1b  jz      short loc_180069A3A
0x180069a1d  mov     r8d, 0Ah
0x180069a23  mov     [rsp+290h+var_260], r13
0x180069a28  lea     rdx, [rsp+290h+var_260]
0x180069a2d  mov     rcx, r14
0x180069a30  call    cs:__imp__o__wcstoui64
0x180069a36  mov     [r12], eax
0x180069a3a  mov     eax, ebx
0x180069a3c  mov     rcx, [rbp+190h+var_40]
0x180069a43  xor     rcx, rsp; StackCookie
0x180069a46  call    __security_check_cookie
0x180069a4b  add     rsp, 260h
0x180069a52  pop     r15
0x180069a54  pop     r14
0x180069a56  pop     r13
0x180069a58  pop     r12
0x180069a5a  pop     rdi
0x180069a5b  pop     rbx
0x180069a5c  pop     rbp
0x180069a5d  retn
0x180069a5e  mov     rdx, rdi; pclsid
0x180069a61  lea     rcx, [rsp+290h+sz]; lpsz
0x180069a66  call    cs:__imp_CLSIDFromString
0x180069a6c  mov     ebx, eax
0x180069a6e  test    eax, eax
0x180069a70  jns     short loc_180069A12
0x180069a72  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069a79  jb      short loc_180069A3A
0x180069a7b  mov     edx, 0Fh
0x180069a80  jmp     loc_1800697F8
```
