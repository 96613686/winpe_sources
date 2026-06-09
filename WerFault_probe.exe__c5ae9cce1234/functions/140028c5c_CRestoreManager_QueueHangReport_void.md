# CRestoreManager::QueueHangReport(void)

- ea: `0x140028c5c`
- end: `0x140028f8e`
- name: `?QueueHangReport@CRestoreManager@@QEAAJXZ`
- size: `818`
- prototype: `__int64 __fastcall(CRestoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400280fc`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000b4cc`
- `0x14001444c`
- `0x140014474`
- `0x14001a1d4`
- `0x14001ac44`
- `0x140028c5c`
- `0x14002a364`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140028d4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140028da5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140028d4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140028da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028dc1`
- `wer!WerReportSubmit` at `0x140028f35`
- `wer!WerReportSubmit` at `0x140028f35`
- `wer!WerReportCreate` at `0x140028ebd`
- `wer!WerReportCreate` at `0x140028ebd`
- `wer!WerReportCloseHandle` at `0x140028ea1`
- `wer!WerReportCloseHandle` at `0x140028f67`
- `wer!WerReportCloseHandle` at `0x140028ea1`
- `wer!WerReportCloseHandle` at `0x140028f67`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRestoreManager::QueueHangReport(CRestoreManager *this)
{
  unsigned int v2; // ebx
  int ApplicationName; // eax
  DWORD LastError; // eax
  DWORD v5; // eax
  const wchar_t *v6; // rax
  __int64 v7; // r11
  __int64 v8; // rcx
  const wchar_t *v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r8
  wchar_t *v12; // rax
  wchar_t v13; // r10
  wchar_t *v14; // rcx
  const wchar_t *v15; // rcx
  wchar_t *v16; // rax
  wchar_t v17; // r8
  wchar_t *v18; // rcx
  HREPORT v19; // rcx
  HRESULT v20; // eax
  CUserModeHangReport *v21; // rcx
  __int64 v22; // rdx
  HREPORT hReportHandle; // [rsp+20h] [rbp-E0h] BYREF
  struct _WER_REPORT_INFORMATION pReportInformation; // [rsp+30h] [rbp-D0h] BYREF
  char v26; // [rsp+8D0h] [rbp+7D0h] BYREF
  char v27; // [rsp+950h] [rbp+850h] BYREF

  hReportHandle = 0;
  memset_0(&pReportInformation, 0, 0x9C8u);
  if ( !*((_DWORD *)this + 320) )
  {
    v2 = 1;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids);
    }
    goto LABEL_45;
  }
  pReportInformation.dwSize = 2504;
  ApplicationName = CProcessInformation::GetApplicationName(
                      *((CProcessInformation **)this + 15),
                      pReportInformation.wzApplicationName,
                      0x80u);
  if ( ApplicationName < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids,
      (unsigned int)ApplicationName);
  }
  if ( !LoadStringW(g_instance, 0x26B2u, pReportInformation.wzFriendlyEventName, 128)
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, LastError);
  }
  if ( !LoadStringW(g_instance, 0x26B3u, pReportInformation.wzDescription, 512)
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, v5);
  }
  v6 = CProcessInformation::AppFileName(*((CProcessInformation **)this + 15));
  StringCchCopyW(pReportInformation.wzApplicationPath, 0x104u, v6);
  v7 = 2147483646;
  v8 = 2147483646;
  v9 = L"windows";
  v10 = 64;
  v11 = 64;
  v12 = (wchar_t *)&v26;
  do
  {
    if ( !v8 )
      break;
    v13 = *v9;
    if ( !*v9 )
      break;
    ++v9;
    *v12++ = v13;
    --v8;
    --v11;
  }
  while ( v11 );
  v14 = v12 - 1;
  if ( v11 )
    v14 = v12;
  *v14 = 0;
  v15 = L"windows8";
  v16 = (wchar_t *)&v27;
  do
  {
    if ( !v7 )
      break;
    v17 = *v15;
    if ( !*v15 )
      break;
    ++v15;
    *v16++ = v17;
    --v7;
    --v10;
  }
  while ( v10 );
  v18 = v16 - 1;
  if ( v10 )
    v18 = v16;
  *v18 = 0;
  v19 = hReportHandle;
  hReportHandle = 0;
  if ( v19 )
    WerReportCloseHandle(v19);
  v20 = WerReportCreate(L"AppHangB1", WerReportApplicationHang, &pReportInformation, &hReportHandle);
  v2 = v20;
  if ( v20 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_45;
    }
    v22 = 27;
    goto LABEL_35;
  }
  v20 = CUserHangSignature::SetWerReportSignature((PCWSTR)this + 64, hReportHandle);
  v2 = v20;
  if ( v20 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_45;
    }
    v22 = 28;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v21 + 2), v22, &WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, (unsigned int)v20);
    goto LABEL_45;
  }
  v20 = WerReportSubmit(hReportHandle, WerConsentNotAsked, 4u, 0);
  v2 = v20;
  if ( v20 >= 0 )
  {
    v2 = 0;
    goto LABEL_45;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v22 = 29;
    goto LABEL_35;
  }
LABEL_45:
  if ( hReportHandle )
    WerReportCloseHandle(hReportHandle);
  return v2;
}

```

## disassembly

```asm
0x140028c5c  push    rbp
0x140028c5e  push    rbx
0x140028c5f  push    rsi
0x140028c60  push    rdi
0x140028c61  push    r14
0x140028c63  push    r15
0x140028c65  lea     rbp, [rsp-918h]
0x140028c6d  sub     rsp, 0A18h
0x140028c74  mov     rax, cs:__security_cookie
0x140028c7b  xor     rax, rsp
0x140028c7e  mov     [rbp+940h+var_40], rax
0x140028c85  mov     r14, rcx
0x140028c88  xor     r15d, r15d
0x140028c8b  mov     [rsp+0A40h+hReportHandle], r15
0x140028c90  mov     ebx, 9C8h
0x140028c95  mov     r8d, ebx; Size
0x140028c98  xor     edx, edx; Val
0x140028c9a  lea     rcx, [rsp+0A40h+pReportInformation]; void *
0x140028c9f  call    memset_0
0x140028ca4  cmp     [r14+500h], r15d
0x140028cab  jnz     short loc_140028CEA
0x140028cad  lea     ebx, [r15+1]
0x140028cb1  lea     rdi, WPP_GLOBAL_Control
0x140028cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140028cbf  cmp     rcx, rdi
0x140028cc2  jz      loc_140028F5D
0x140028cc8  test    byte ptr [rcx+1Ch], 4
0x140028ccc  jz      loc_140028F5D
0x140028cd2  lea     edx, [rbx+16h]
0x140028cd5  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x140028cdc  mov     rcx, [rcx+10h]
0x140028ce0  call    WPP_SF_
0x140028ce5  jmp     loc_140028F5D
0x140028cea  mov     [rsp+0A40h+pReportInformation.dwSize], ebx
0x140028cee  mov     ebx, 80h
0x140028cf3  mov     r8d, ebx; unsigned int
0x140028cf6  lea     rdx, [rbp+940h+pReportInformation.wzApplicationName]; wchar_t *
0x140028cfd  mov     rcx, [r14+78h]; this
0x140028d01  call    ?GetApplicationName@CProcessInformation@@QEAAJPEA_WI@Z; CProcessInformation::GetApplicationName(wchar_t *,uint)
0x140028d06  lea     rsi, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x140028d0d  lea     rdi, WPP_GLOBAL_Control
0x140028d14  test    eax, eax
0x140028d16  jns     short loc_140028D3C
0x140028d18  mov     rcx, cs:WPP_GLOBAL_Control
0x140028d1f  cmp     rcx, rdi
0x140028d22  jz      short loc_140028D3C
0x140028d24  test    byte ptr [rcx+1Ch], 2
0x140028d28  jz      short loc_140028D3C
0x140028d2a  lea     edx, [rbx-68h]
0x140028d2d  mov     r9d, eax
0x140028d30  mov     r8, rsi
0x140028d33  mov     rcx, [rcx+10h]
0x140028d37  call    WPP_SF_d
0x140028d3c  mov     r9d, ebx; cchBufferMax
0x140028d3f  lea     r8, [rbp+940h+pReportInformation.wzFriendlyEventName]; lpBuffer
0x140028d43  mov     edx, 26B2h; uID
0x140028d48  mov     rcx, cs:?g_instance@@3PEAUHINSTANCE__@@EA; hInstance
0x140028d4f  call    cs:__imp_LoadStringW
0x140028d55  test    eax, eax
0x140028d57  jnz     short loc_140028D8C
0x140028d59  mov     rax, cs:WPP_GLOBAL_Control
0x140028d60  cmp     rax, rdi
0x140028d63  jz      short loc_140028D8C
0x140028d65  test    byte ptr [rax+1Ch], 2
0x140028d69  jz      short loc_140028D8C
0x140028d6b  call    cs:__imp_GetLastError
0x140028d71  mov     edx, 19h
0x140028d76  mov     r9d, eax
0x140028d79  mov     r8, rsi
0x140028d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028d83  mov     rcx, [rcx+10h]
0x140028d87  call    WPP_SF_d
0x140028d8c  mov     r9d, 200h; cchBufferMax
0x140028d92  lea     r8, [rbp+940h+pReportInformation.wzDescription]; lpBuffer
0x140028d99  mov     edx, 26B3h; uID
0x140028d9e  mov     rcx, cs:?g_instance@@3PEAUHINSTANCE__@@EA; hInstance
0x140028da5  call    cs:__imp_LoadStringW
0x140028dab  test    eax, eax
0x140028dad  jnz     short loc_140028DE2
0x140028daf  mov     rax, cs:WPP_GLOBAL_Control
0x140028db6  cmp     rax, rdi
0x140028db9  jz      short loc_140028DE2
0x140028dbb  test    byte ptr [rax+1Ch], 2
0x140028dbf  jz      short loc_140028DE2
0x140028dc1  call    cs:__imp_GetLastError
0x140028dc7  mov     edx, 1Ah
0x140028dcc  mov     r9d, eax
0x140028dcf  mov     r8, rsi
0x140028dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140028dd9  mov     rcx, [rcx+10h]
0x140028ddd  call    WPP_SF_d
0x140028de2  mov     rcx, [r14+78h]; this
0x140028de6  call    ?AppFileName@CProcessInformation@@AEAAPEB_WXZ; CProcessInformation::AppFileName(void)
0x140028deb  mov     r8, rax; wchar_t *
0x140028dee  mov     edx, 104h; unsigned __int64
0x140028df3  lea     rcx, [rbp+940h+pReportInformation.wzApplicationPath]; wchar_t *
0x140028dfa  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140028dff  mov     r11d, 7FFFFFFEh
0x140028e05  mov     ecx, r11d
0x140028e08  lea     r9, aWindows; "windows"
0x140028e0f  mov     edx, 40h ; '@'
0x140028e14  mov     r8d, edx
0x140028e17  lea     rax, [rbp+940h+var_170]
0x140028e1e  test    rcx, rcx
0x140028e21  jz      short loc_140028E42
0x140028e23  movzx   r10d, word ptr [r9]
0x140028e27  test    r10w, r10w
0x140028e2b  jz      short loc_140028E42
0x140028e2d  add     r9, 2
0x140028e31  mov     [rax], r10w
0x140028e35  add     rax, 2
0x140028e39  dec     rcx
0x140028e3c  sub     r8, 1
0x140028e40  jnz     short loc_140028E1E
0x140028e42  lea     rcx, [rax-2]
0x140028e46  test    r8, r8
0x140028e49  cmovnz  rcx, rax
0x140028e4d  mov     [rcx], r15w
0x140028e51  lea     rcx, aWindows8; "windows8"
0x140028e58  lea     rax, [rbp+940h+var_F0]
0x140028e5f  test    r11, r11
0x140028e62  jz      short loc_140028E83
0x140028e64  movzx   r8d, word ptr [rcx]
0x140028e68  test    r8w, r8w
0x140028e6c  jz      short loc_140028E83
0x140028e6e  add     rcx, 2
0x140028e72  mov     [rax], r8w
0x140028e76  add     rax, 2
0x140028e7a  dec     r11
0x140028e7d  sub     rdx, 1
0x140028e81  jnz     short loc_140028E5F
0x140028e83  lea     rcx, [rax-2]
0x140028e87  test    rdx, rdx
0x140028e8a  cmovnz  rcx, rax
0x140028e8e  mov     [rcx], r15w
0x140028e92  mov     rcx, [rsp+0A40h+hReportHandle]; hReportHandle
0x140028e97  mov     [rsp+0A40h+hReportHandle], r15
0x140028e9c  test    rcx, rcx
0x140028e9f  jz      short loc_140028EA7
0x140028ea1  call    cs:__imp_WerReportCloseHandle
0x140028ea7  lea     r9, [rsp+0A40h+hReportHandle]; phReportHandle
0x140028eac  lea     r8, [rsp+0A40h+pReportInformation]; pReportInformation
0x140028eb1  mov     edx, 3; repType
0x140028eb6  lea     rcx, aApphangb1; "AppHangB1"
0x140028ebd  call    cs:__imp_WerReportCreate
0x140028ec3  mov     ebx, eax
0x140028ec5  test    eax, eax
0x140028ec7  jns     short loc_140028EF5
0x140028ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x140028ed0  cmp     rcx, rdi
0x140028ed3  jz      loc_140028F5D
0x140028ed9  test    byte ptr [rcx+1Ch], 1
0x140028edd  jz      short loc_140028F5D
0x140028edf  mov     edx, 1Bh
0x140028ee4  mov     r9d, eax
0x140028ee7  mov     r8, rsi
0x140028eea  mov     rcx, [rcx+10h]
0x140028eee  call    WPP_SF_d
0x140028ef3  jmp     short loc_140028F5D
0x140028ef5  lea     rcx, [r14+80h]; pwzValue
0x140028efc  mov     rdx, [rsp+0A40h+hReportHandle]; hReportHandle
0x140028f01  call    ?SetWerReportSignature@CUserHangSignature@@QEAAJPEAX@Z; CUserHangSignature::SetWerReportSignature(void *)
0x140028f06  mov     ebx, eax
0x140028f08  test    eax, eax
0x140028f0a  jns     short loc_140028F25
0x140028f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028f13  cmp     rcx, rdi
0x140028f16  jz      short loc_140028F5D
0x140028f18  test    byte ptr [rcx+1Ch], 1
0x140028f1c  jz      short loc_140028F5D
0x140028f1e  mov     edx, 1Ch
0x140028f23  jmp     short loc_140028EE4
0x140028f25  xor     r9d, r9d; pSubmitResult
0x140028f28  lea     edx, [r9+1]; consent
0x140028f2c  lea     r8d, [r9+4]; dwFlags
0x140028f30  mov     rcx, [rsp+0A40h+hReportHandle]; hReportHandle
0x140028f35  call    cs:__imp_WerReportSubmit
0x140028f3b  mov     ebx, eax
0x140028f3d  test    eax, eax
0x140028f3f  jns     short loc_140028F5A
0x140028f41  mov     rcx, cs:WPP_GLOBAL_Control
0x140028f48  cmp     rcx, rdi
0x140028f4b  jz      short loc_140028F5D
0x140028f4d  test    byte ptr [rcx+1Ch], 1
0x140028f51  jz      short loc_140028F5D
0x140028f53  mov     edx, 1Dh
0x140028f58  jmp     short loc_140028EE4
0x140028f5a  mov     ebx, r15d
0x140028f5d  mov     rcx, [rsp+0A40h+hReportHandle]; hReportHandle
0x140028f62  test    rcx, rcx
0x140028f65  jz      short loc_140028F6D
0x140028f67  call    cs:__imp_WerReportCloseHandle
0x140028f6d  mov     eax, ebx
0x140028f6f  mov     rcx, [rbp+940h+var_40]
0x140028f76  xor     rcx, rsp; StackCookie
0x140028f79  call    __security_check_cookie
0x140028f7e  add     rsp, 0A18h
0x140028f85  pop     r15
0x140028f87  pop     r14
0x140028f89  pop     rdi
0x140028f8a  pop     rsi
0x140028f8b  pop     rbx
0x140028f8c  pop     rbp
0x140028f8d  retn
```
