# CRestoreManager::QueueHangReport(void)

- ea: `0x14002a770`
- end: `0x14002aac4`
- name: `?QueueHangReport@CRestoreManager@@QEAAJXZ`
- size: `852`
- prototype: `__int64 __fastcall(CRestoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x140029bb0`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000b50c`
- `0x140014ee4`
- `0x140014f14`
- `0x14001b1b4`
- `0x14001bc7c`
- `0x14001e46c`
- `0x14002a770`
- `0x14002bf68`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14002a863`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14002a8c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14002a863`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14002a8c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a8e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a8e7`
- `wer!WerReportSubmit` at `0x14002aa5e`
- `wer!WerReportSubmit` at `0x14002aa5e`
- `wer!WerReportCreate` at `0x14002a9dc`
- `wer!WerReportCreate` at `0x14002a9dc`
- `wer!WerReportCloseHandle` at `0x14002aa96`
- `wer!WerReportCloseHandle` at `0x14002aa96`

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
  HREPORT *v19; // rax
  HRESULT v20; // eax
  CUserModeHangReport *v21; // rcx
  __int64 v22; // rdx
  HREPORT hReportHandle[2]; // [rsp+20h] [rbp-E0h] BYREF
  struct _WER_REPORT_INFORMATION pReportInformation; // [rsp+30h] [rbp-D0h] BYREF
  char v26; // [rsp+8D0h] [rbp+7D0h] BYREF
  char v27; // [rsp+950h] [rbp+850h] BYREF

  hReportHandle[0] = 0;
  memset_0(&pReportInformation, 0, 0x9C8u);
  if ( !*((_DWORD *)this + 320) )
  {
    v2 = 1;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids);
    }
    goto LABEL_43;
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
      WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids,
      (unsigned int)ApplicationName);
  }
  if ( !LoadStringW(g_instance, 0x26B2u, pReportInformation.wzFriendlyEventName, 128)
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, LastError);
  }
  if ( !LoadStringW(g_instance, 0x26B3u, pReportInformation.wzDescription, 512)
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, v5);
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
  v19 = (HREPORT *)tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long WerReportCloseHandle(void *),0>>(hReportHandle);
  v20 = WerReportCreate(L"AppHangB1", WerReportApplicationHang, &pReportInformation, v19);
  v2 = v20;
  if ( v20 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_43;
    }
    v22 = 27;
    goto LABEL_33;
  }
  v20 = CUserHangSignature::SetWerReportSignature((PCWSTR)this + 64, hReportHandle[0]);
  v2 = v20;
  if ( v20 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_43;
    }
    v22 = 28;
LABEL_33:
    WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, (unsigned int)v20);
    goto LABEL_43;
  }
  v20 = WerReportSubmit(hReportHandle[0], WerConsentNotAsked, 4u, 0);
  v2 = v20;
  if ( v20 >= 0 )
  {
    v2 = 0;
    goto LABEL_43;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v22 = 29;
    goto LABEL_33;
  }
LABEL_43:
  if ( hReportHandle[0] )
    WerReportCloseHandle(hReportHandle[0]);
  return v2;
}

```

## disassembly

```asm
0x14002a770  push    rbp
0x14002a772  push    rbx
0x14002a773  push    rsi
0x14002a774  push    rdi
0x14002a775  push    r14
0x14002a777  push    r15
0x14002a779  lea     rbp, [rsp-918h]
0x14002a781  sub     rsp, 0A18h
0x14002a788  mov     rax, cs:__security_cookie
0x14002a78f  xor     rax, rsp
0x14002a792  mov     [rbp+940h+var_40], rax
0x14002a799  mov     r14, rcx
0x14002a79c  xor     r15d, r15d
0x14002a79f  mov     [rsp+0A40h+hReportHandle], r15
0x14002a7a4  mov     ebx, 9C8h
0x14002a7a9  mov     r8d, ebx; Size
0x14002a7ac  xor     edx, edx; Val
0x14002a7ae  lea     rcx, [rsp+0A40h+pReportInformation]; void *
0x14002a7b3  call    memset_0
0x14002a7b8  cmp     [r14+500h], r15d
0x14002a7bf  jnz     short loc_14002A7FE
0x14002a7c1  lea     ebx, [r15+1]
0x14002a7c5  lea     rdi, WPP_GLOBAL_Control
0x14002a7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a7d3  cmp     rcx, rdi
0x14002a7d6  jz      loc_14002AA8C
0x14002a7dc  test    byte ptr [rcx+1Ch], 4
0x14002a7e0  jz      loc_14002AA8C
0x14002a7e6  lea     edx, [rbx+16h]
0x14002a7e9  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002a7f0  mov     rcx, [rcx+10h]
0x14002a7f4  call    WPP_SF_
0x14002a7f9  jmp     loc_14002AA8C
0x14002a7fe  mov     [rsp+0A40h+pReportInformation.dwSize], ebx
0x14002a802  mov     ebx, 80h
0x14002a807  mov     r8d, ebx; unsigned int
0x14002a80a  lea     rdx, [rbp+940h+pReportInformation.wzApplicationName]; wchar_t *
0x14002a811  mov     rcx, [r14+78h]; this
0x14002a815  call    ?GetApplicationName@CProcessInformation@@QEAAJPEA_WI@Z; CProcessInformation::GetApplicationName(wchar_t *,uint)
0x14002a81a  lea     rsi, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002a821  lea     rdi, WPP_GLOBAL_Control
0x14002a828  test    eax, eax
0x14002a82a  jns     short loc_14002A850
0x14002a82c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a833  cmp     rcx, rdi
0x14002a836  jz      short loc_14002A850
0x14002a838  test    byte ptr [rcx+1Ch], 2
0x14002a83c  jz      short loc_14002A850
0x14002a83e  lea     edx, [rbx-68h]
0x14002a841  mov     r9d, eax
0x14002a844  mov     r8, rsi
0x14002a847  mov     rcx, [rcx+10h]
0x14002a84b  call    WPP_SF_d
0x14002a850  mov     r9d, ebx; cchBufferMax
0x14002a853  lea     r8, [rbp+940h+pReportInformation.wzFriendlyEventName]; lpBuffer
0x14002a857  mov     edx, 26B2h; uID
0x14002a85c  mov     rcx, cs:?g_instance@@3PEAUHINSTANCE__@@EA; hInstance
0x14002a863  call    cs:__imp_LoadStringW
0x14002a86a  nop     dword ptr [rax+rax+00h]
0x14002a86f  test    eax, eax
0x14002a871  jnz     short loc_14002A8AC
0x14002a873  mov     rax, cs:WPP_GLOBAL_Control
0x14002a87a  cmp     rax, rdi
0x14002a87d  jz      short loc_14002A8AC
0x14002a87f  test    byte ptr [rax+1Ch], 2
0x14002a883  jz      short loc_14002A8AC
0x14002a885  call    cs:__imp_GetLastError
0x14002a88c  nop     dword ptr [rax+rax+00h]
0x14002a891  mov     edx, 19h
0x14002a896  mov     r9d, eax
0x14002a899  mov     r8, rsi
0x14002a89c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a8a3  mov     rcx, [rcx+10h]
0x14002a8a7  call    WPP_SF_d
0x14002a8ac  mov     r9d, 200h; cchBufferMax
0x14002a8b2  lea     r8, [rbp+940h+pReportInformation.wzDescription]; lpBuffer
0x14002a8b9  mov     edx, 26B3h; uID
0x14002a8be  mov     rcx, cs:?g_instance@@3PEAUHINSTANCE__@@EA; hInstance
0x14002a8c5  call    cs:__imp_LoadStringW
0x14002a8cc  nop     dword ptr [rax+rax+00h]
0x14002a8d1  test    eax, eax
0x14002a8d3  jnz     short loc_14002A90E
0x14002a8d5  mov     rax, cs:WPP_GLOBAL_Control
0x14002a8dc  cmp     rax, rdi
0x14002a8df  jz      short loc_14002A90E
0x14002a8e1  test    byte ptr [rax+1Ch], 2
0x14002a8e5  jz      short loc_14002A90E
0x14002a8e7  call    cs:__imp_GetLastError
0x14002a8ee  nop     dword ptr [rax+rax+00h]
0x14002a8f3  mov     edx, 1Ah
0x14002a8f8  mov     r9d, eax
0x14002a8fb  mov     r8, rsi
0x14002a8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a905  mov     rcx, [rcx+10h]
0x14002a909  call    WPP_SF_d
0x14002a90e  mov     rcx, [r14+78h]; this
0x14002a912  call    ?AppFileName@CProcessInformation@@AEAAPEB_WXZ; CProcessInformation::AppFileName(void)
0x14002a917  mov     r8, rax; wchar_t *
0x14002a91a  mov     edx, 104h; unsigned __int64
0x14002a91f  lea     rcx, [rbp+940h+pReportInformation.wzApplicationPath]; wchar_t *
0x14002a926  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14002a92b  mov     r11d, 7FFFFFFEh
0x14002a931  mov     ecx, r11d
0x14002a934  lea     r9, aWindows; "windows"
0x14002a93b  mov     edx, 40h ; '@'
0x14002a940  mov     r8d, edx
0x14002a943  lea     rax, [rbp+940h+var_170]
0x14002a94a  test    rcx, rcx
0x14002a94d  jz      short loc_14002A96E
0x14002a94f  movzx   r10d, word ptr [r9]
0x14002a953  test    r10w, r10w
0x14002a957  jz      short loc_14002A96E
0x14002a959  add     r9, 2
0x14002a95d  mov     [rax], r10w
0x14002a961  add     rax, 2
0x14002a965  dec     rcx
0x14002a968  sub     r8, 1
0x14002a96c  jnz     short loc_14002A94A
0x14002a96e  lea     rcx, [rax-2]
0x14002a972  test    r8, r8
0x14002a975  cmovnz  rcx, rax
0x14002a979  mov     [rcx], r15w
0x14002a97d  lea     rcx, aWindows8; "windows8"
0x14002a984  lea     rax, [rbp+940h+var_F0]
0x14002a98b  test    r11, r11
0x14002a98e  jz      short loc_14002A9AF
0x14002a990  movzx   r8d, word ptr [rcx]
0x14002a994  test    r8w, r8w
0x14002a998  jz      short loc_14002A9AF
0x14002a99a  add     rcx, 2
0x14002a99e  mov     [rax], r8w
0x14002a9a2  add     rax, 2
0x14002a9a6  dec     r11
0x14002a9a9  sub     rdx, 1
0x14002a9ad  jnz     short loc_14002A98B
0x14002a9af  lea     rcx, [rax-2]
0x14002a9b3  test    rdx, rdx
0x14002a9b6  cmovnz  rcx, rax
0x14002a9ba  mov     [rcx], r15w
0x14002a9be  lea     rcx, [rsp+0A40h+hReportHandle]
0x14002a9c3  call    ??$replace@U?$handle_traits@PEAXP6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (*)(void *),&WerReportCloseHandle(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&WerReportCloseHandle(void *),0>> &)
0x14002a9c8  mov     r9, rax; phReportHandle
0x14002a9cb  lea     r8, [rsp+0A40h+pReportInformation]; pReportInformation
0x14002a9d0  mov     edx, 3; repType
0x14002a9d5  lea     rcx, aApphangb1; "AppHangB1"
0x14002a9dc  call    cs:__imp_WerReportCreate
0x14002a9e3  nop     dword ptr [rax+rax+00h]
0x14002a9e8  mov     ebx, eax
0x14002a9ea  test    eax, eax
0x14002a9ec  jns     short loc_14002AA1E
0x14002a9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a9f5  cmp     rcx, rdi
0x14002a9f8  jz      loc_14002AA8C
0x14002a9fe  test    byte ptr [rcx+1Ch], 1
0x14002aa02  jz      loc_14002AA8C
0x14002aa08  mov     edx, 1Bh
0x14002aa0d  mov     r9d, eax
0x14002aa10  mov     r8, rsi
0x14002aa13  mov     rcx, [rcx+10h]
0x14002aa17  call    WPP_SF_d
0x14002aa1c  jmp     short loc_14002AA8C
0x14002aa1e  lea     rcx, [r14+80h]; pwzValue
0x14002aa25  mov     rdx, [rsp+0A40h+hReportHandle]; hReportHandle
0x14002aa2a  call    ?SetWerReportSignature@CUserHangSignature@@QEAAJPEAX@Z; CUserHangSignature::SetWerReportSignature(void *)
0x14002aa2f  mov     ebx, eax
0x14002aa31  test    eax, eax
0x14002aa33  jns     short loc_14002AA4E
0x14002aa35  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa3c  cmp     rcx, rdi
0x14002aa3f  jz      short loc_14002AA8C
0x14002aa41  test    byte ptr [rcx+1Ch], 1
0x14002aa45  jz      short loc_14002AA8C
0x14002aa47  mov     edx, 1Ch
0x14002aa4c  jmp     short loc_14002AA0D
0x14002aa4e  xor     r9d, r9d; pSubmitResult
0x14002aa51  lea     edx, [r9+1]; consent
0x14002aa55  lea     r8d, [r9+4]; dwFlags
0x14002aa59  mov     rcx, [rsp+0A40h+hReportHandle]; hReportHandle
0x14002aa5e  call    cs:__imp_WerReportSubmit
0x14002aa65  nop     dword ptr [rax+rax+00h]
0x14002aa6a  mov     ebx, eax
0x14002aa6c  test    eax, eax
0x14002aa6e  jns     short loc_14002AA89
0x14002aa70  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa77  cmp     rcx, rdi
0x14002aa7a  jz      short loc_14002AA8C
0x14002aa7c  test    byte ptr [rcx+1Ch], 1
0x14002aa80  jz      short loc_14002AA8C
0x14002aa82  mov     edx, 1Dh
0x14002aa87  jmp     short loc_14002AA0D
0x14002aa89  mov     ebx, r15d
0x14002aa8c  mov     rcx, [rsp+0A40h+hReportHandle]; hReportHandle
0x14002aa91  test    rcx, rcx
0x14002aa94  jz      short loc_14002AAA2
0x14002aa96  call    cs:__imp_WerReportCloseHandle
0x14002aa9d  nop     dword ptr [rax+rax+00h]
0x14002aaa2  mov     eax, ebx
0x14002aaa4  mov     rcx, [rbp+940h+var_40]
0x14002aaab  xor     rcx, rsp; StackCookie
0x14002aaae  call    __security_check_cookie
0x14002aab3  add     rsp, 0A18h
0x14002aaba  pop     r15
0x14002aabc  pop     r14
0x14002aabe  pop     rdi
0x14002aabf  pop     rsi
0x14002aac0  pop     rbx
0x14002aac1  pop     rbp
0x14002aac2  retn
```
