# CReport::TryReportLock(void)

- ea: `0x180073970`
- end: `0x180073d1e`
- name: `?TryReportLock@CReport@@QEAAJXZ`
- size: `942`
- prototype: `__int64 __fastcall(CReport *__hidden this)`
- caller_count: `8`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18001a60c`
- `0x18004015c`
- `0x1800674a0`
- `0x18006ad10`
- `0x18006fc08`
- `0x1800740c4`
- `0x1800742a4`
- `0x180076ab0`

## callees

- `0x180004bb4`
- `0x180007e34`
- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x180015520`
- `0x18001dc24`
- `0x18001fe24`
- `0x18002c198`
- `0x18003bf14`
- `0x180045bdc`
- `0x180046d74`
- `0x180050db0`
- `0x1800517cc`
- `0x18005b8d1`
- `0x180073970`
- `0x1800a9fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073ad4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800739be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800739be`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180073ac3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180073ac3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073c8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073c8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CReport::TryReportLock(CReport *this)
{
  unsigned int v2; // edi
  int UniqueIdentifier; // ebx
  wchar_t *v4; // rcx
  __int64 v5; // rdx
  HANDLE *v6; // r14
  HANDLE MutexW; // rax
  signed int LastError; // eax
  const wchar_t *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  char *v17; // [rsp+20h] [rbp-E0h] BYREF
  char v18; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpName[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE Src[1408]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v21; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v22[38]; // [rsp+5D2h] [rbp+4D2h] BYREF
  int v23; // [rsp+5F8h] [rbp+4F8h]
  unsigned int v24; // [rsp+5FCh] [rbp+4FCh]
  __int64 v25; // [rsp+680h] [rbp+580h]
  _DWORD v26[12]; // [rsp+B50h] [rbp+A50h] BYREF
  wchar_t v27[680]; // [rsp+B80h] [rbp+A80h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpName);
  v17 = (char *)this + 46576;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 46576));
  v2 = 1;
  v18 = 1;
  if ( !(unsigned int)CReport::IsReportLocked(this) )
  {
    if ( (*((_DWORD *)this + 1654) & 0x200000) != 0 )
      goto LABEL_49;
    UniqueIdentifier = CReport::GetUniqueIdentifier(this, 0);
    if ( UniqueIdentifier < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_46;
      v5 = 325;
      goto LABEL_11;
    }
    UniqueIdentifier = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                         lpName,
                         L"Global\\%ls",
                         *((_QWORD *)this + 735));
    if ( UniqueIdentifier < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_46;
      v5 = 326;
      goto LABEL_11;
    }
    v6 = (HANDLE *)((char *)this + 46552);
    MutexW = CreateMutexW(0, 1, lpName[0]);
    tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46552, MutexW);
    LastError = GetLastError();
    UniqueIdentifier = LastError;
    if ( LastError > 0 )
      UniqueIdentifier = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned __int64)*v6 + 1 <= 1 && UniqueIdentifier == -2147024891 )
    {
      v21 = 0;
      memset_0(v22, 0, 0x576u);
      memset_0(Src, 0, 0x578u);
      memcpy_0(v26, Src, 0x578u);
      v26[0] = 91751760;
      v26[10] = -1073741822;
      UniqueIdentifier = StringCchCopyW(v27, 0x40u, *((const wchar_t **)this + 735));
      if ( UniqueIdentifier < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_46;
        v5 = 327;
        goto LABEL_11;
      }
      UniqueIdentifier = UtilSendMessageToWersvc(v9, (struct _WERSVC_MSG *)v26, (struct _WERSVC_MSG *)&v21, 0);
      if ( UniqueIdentifier < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_46;
        v5 = 328;
LABEL_11:
        WPP_SF_d(
          *((_QWORD *)v4 + 2),
          v5,
          WPP_6898268820d636d20e115db2eaa75970_Traceguids,
          (unsigned int)UniqueIdentifier);
        goto LABEL_46;
      }
      if ( v23 != -1073741824 )
      {
        v12 = v24;
        UniqueIdentifier = v24 | 0x10000000;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        {
LABEL_40:
          if ( UniqueIdentifier >= 0 )
          {
LABEL_48:
            v2 = UniqueIdentifier;
            goto LABEL_49;
          }
LABEL_46:
          tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46552, 0);
          goto LABEL_48;
        }
        v14 = 329;
LABEL_39:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v12);
        goto LABEL_40;
      }
      v15 = v25;
      if ( !v25 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v10, 0, v11);
        v15 = v25;
      }
      tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46552, v15);
    }
    if ( (unsigned __int64)*v6 + 1 > 1 )
    {
      if ( WaitForSingleObject(*v6, 0) != 258 )
      {
        UniqueIdentifier = 0;
        goto LABEL_48;
      }
      UniqueIdentifier = -2147024713;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 331, WPP_6898268820d636d20e115db2eaa75970_Traceguids);
      goto LABEL_46;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_40;
    v14 = 330;
    v12 = (unsigned int)UniqueIdentifier;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, WPP_6898268820d636d20e115db2eaa75970_Traceguids);
  v2 = 0;
LABEL_49:
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v17);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpName);
  return v2;
}

```

## disassembly

```asm
0x180073970  mov     [rsp-8+arg_8], rbx
0x180073975  mov     [rsp-8+arg_10], rsi
0x18007397a  push    rbp
0x18007397b  push    rdi
0x18007397c  push    r14
0x18007397e  lea     rbp, [rsp-0FE0h]
0x180073986  mov     eax, 10E0h
0x18007398b  call    _alloca_probe
0x180073990  sub     rsp, rax
0x180073993  mov     rax, cs:__security_cookie
0x18007399a  xor     rax, rsp
0x18007399d  mov     [rbp+0FF0h+var_20], rax
0x1800739a4  mov     rsi, rcx
0x1800739a7  lea     rcx, [rsp+10F0h+lpName]; void *
0x1800739ac  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800739b1  nop
0x1800739b2  lea     rcx, [rsi+0B5F0h]; lpCriticalSection
0x1800739b9  mov     [rsp+10F0h+var_10D0], rcx
0x1800739be  call    cs:__imp_EnterCriticalSection
0x1800739c4  mov     edi, 1
0x1800739c9  mov     [rsp+10F0h+var_10C8], dil
0x1800739ce  mov     rcx, rsi; this
0x1800739d1  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x1800739d6  test    eax, eax
0x1800739d8  jz      short loc_180073A0F
0x1800739da  lea     rax, WPP_GLOBAL_Control
0x1800739e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800739e8  cmp     rcx, rax
0x1800739eb  jz      short loc_180073A08
0x1800739ed  test    byte ptr [rcx+1Ch], 4
0x1800739f1  jz      short loc_180073A08
0x1800739f3  mov     edx, 144h
0x1800739f8  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x1800739ff  mov     rcx, [rcx+10h]
0x180073a03  call    WPP_SF_
0x180073a08  xor     edi, edi
0x180073a0a  jmp     loc_180073CE0
0x180073a0f  test    dword ptr [rsi+19D8h], 200000h
0x180073a19  jnz     loc_180073CE0
0x180073a1f  xor     edx, edx
0x180073a21  mov     rcx, rsi
0x180073a24  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180073a29  mov     ebx, eax
0x180073a2b  test    eax, eax
0x180073a2d  jns     short loc_180073A6D
0x180073a2f  lea     rax, WPP_GLOBAL_Control
0x180073a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a3d  cmp     rcx, rax
0x180073a40  jz      loc_180073CCC
0x180073a46  test    [rcx+1Ch], dil
0x180073a4a  jz      loc_180073CCC
0x180073a50  mov     edx, 145h
0x180073a55  mov     r9d, ebx
0x180073a58  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073a5f  mov     rcx, [rcx+10h]
0x180073a63  call    WPP_SF_d
0x180073a68  jmp     loc_180073CCC
0x180073a6d  mov     r8, [rsi+16F8h]
0x180073a74  lea     rdx, aGlobalLs; "Global\\%ls"
0x180073a7b  lea     rcx, [rsp+10F0h+lpName]
0x180073a80  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180073a85  mov     ebx, eax
0x180073a87  test    eax, eax
0x180073a89  jns     short loc_180073AB3
0x180073a8b  lea     rax, WPP_GLOBAL_Control
0x180073a92  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a99  cmp     rcx, rax
0x180073a9c  jz      loc_180073CCC
0x180073aa2  test    [rcx+1Ch], dil
0x180073aa6  jz      loc_180073CCC
0x180073aac  mov     edx, 146h
0x180073ab1  jmp     short loc_180073A55
0x180073ab3  lea     r14, [rsi+0B5D8h]
0x180073aba  mov     r8, [rsp+10F0h+lpName]; lpName
0x180073abf  mov     edx, edi; bInitialOwner
0x180073ac1  xor     ecx, ecx; lpMutexAttributes
0x180073ac3  call    cs:__imp_CreateMutexW
0x180073ac9  mov     rdx, rax
0x180073acc  mov     rcx, r14
0x180073acf  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180073ad4  call    cs:__imp_GetLastError
0x180073ada  mov     ebx, eax
0x180073adc  test    eax, eax
0x180073ade  jle     short loc_180073AE9
0x180073ae0  movzx   ebx, ax
0x180073ae3  or      ebx, 80070000h
0x180073ae9  mov     rax, [r14]
0x180073aec  add     rax, rdi
0x180073aef  cmp     rax, rdi
0x180073af2  ja      loc_180073C47
0x180073af8  cmp     ebx, 80070005h
0x180073afe  jnz     loc_180073C47
0x180073b04  xor     eax, eax
0x180073b06  mov     [rbp+0FF0h+var_B20], ax
0x180073b0d  xor     edx, edx; Val
0x180073b0f  mov     r8d, 576h; Size
0x180073b15  lea     rcx, [rbp+0FF0h+var_B1E]; void *
0x180073b1c  call    memset_0
0x180073b21  mov     ebx, 578h
0x180073b26  mov     r8d, ebx; Size
0x180073b29  xor     edx, edx; Val
0x180073b2b  lea     rcx, [rsp+10F0h+Src]; void *
0x180073b30  call    memset_0
0x180073b35  lea     rcx, [rbp+0FF0h+var_5A0]; void *
0x180073b3c  lea     rdx, [rsp+10F0h+Src]; Src
0x180073b41  mov     r8d, ebx; Size
0x180073b44  call    memcpy_0
0x180073b49  mov     [rbp+0FF0h+var_5A0], 5780550h
0x180073b53  mov     [rbp+0FF0h+var_578], 0C0000002h
0x180073b5d  mov     r8, [rsi+16F8h]; wchar_t *
0x180073b64  mov     edx, 40h ; '@'; unsigned __int64
0x180073b69  lea     rcx, [rbp+0FF0h+var_570]; wchar_t *
0x180073b70  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180073b75  mov     ebx, eax
0x180073b77  test    eax, eax
0x180073b79  jns     short loc_180073BA6
0x180073b7b  lea     rax, WPP_GLOBAL_Control
0x180073b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180073b89  cmp     rcx, rax
0x180073b8c  jz      loc_180073CCC
0x180073b92  test    [rcx+1Ch], dil
0x180073b96  jz      loc_180073CCC
0x180073b9c  mov     edx, 147h
0x180073ba1  jmp     loc_180073A55
0x180073ba6  xor     r9d, r9d; unsigned int
0x180073ba9  lea     r8, [rbp+0FF0h+var_B20]; struct _WERSVC_MSG *
0x180073bb0  lea     rdx, [rbp+0FF0h+var_5A0]; struct _WERSVC_MSG *
0x180073bb7  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x180073bbc  mov     ebx, eax
0x180073bbe  test    eax, eax
0x180073bc0  jns     short loc_180073BED
0x180073bc2  lea     rax, WPP_GLOBAL_Control
0x180073bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180073bd0  cmp     rcx, rax
0x180073bd3  jz      loc_180073CCC
0x180073bd9  test    [rcx+1Ch], dil
0x180073bdd  jz      loc_180073CCC
0x180073be3  mov     edx, 148h
0x180073be8  jmp     loc_180073A55
0x180073bed  cmp     [rbp+0FF0h+var_AF8], 0C0000000h
0x180073bf7  jz      short loc_180073C27
0x180073bf9  mov     r9d, [rbp+0FF0h+var_AF4]
0x180073c00  mov     ebx, r9d
0x180073c03  bts     ebx, 1Ch
0x180073c07  lea     rax, WPP_GLOBAL_Control
0x180073c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c15  cmp     rcx, rax
0x180073c18  jz      short loc_180073C84
0x180073c1a  test    [rcx+1Ch], dil
0x180073c1e  jz      short loc_180073C84
0x180073c20  mov     edx, 149h
0x180073c25  jmp     short loc_180073C74
0x180073c27  mov     rdx, [rbp+0FF0h+var_A70]
0x180073c2e  test    rdx, rdx
0x180073c31  jnz     short loc_180073C3F
0x180073c33  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180073c38  mov     rdx, [rbp+0FF0h+var_A70]
0x180073c3f  mov     rcx, r14
0x180073c42  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180073c47  mov     rcx, [r14]; hHandle
0x180073c4a  lea     rax, [rcx+1]
0x180073c4e  cmp     rax, rdi
0x180073c51  ja      short loc_180073C8A
0x180073c53  lea     rax, WPP_GLOBAL_Control
0x180073c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c61  cmp     rcx, rax
0x180073c64  jz      short loc_180073C84
0x180073c66  test    [rcx+1Ch], dil
0x180073c6a  jz      short loc_180073C84
0x180073c6c  mov     edx, 14Ah
0x180073c71  mov     r9d, ebx
0x180073c74  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073c7b  mov     rcx, [rcx+10h]
0x180073c7f  call    WPP_SF_d
0x180073c84  test    ebx, ebx
0x180073c86  jns     short loc_180073CDE
0x180073c88  jmp     short loc_180073CCC
0x180073c8a  xor     edx, edx; dwMilliseconds
0x180073c8c  call    cs:__imp_WaitForSingleObject
0x180073c92  cmp     eax, 102h
0x180073c97  jnz     short loc_180073CDC
0x180073c99  mov     ebx, 800700B7h
0x180073c9e  lea     rax, WPP_GLOBAL_Control
0x180073ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180073cac  cmp     rcx, rax
0x180073caf  jz      short loc_180073CCC
0x180073cb1  test    byte ptr [rcx+1Ch], 4
0x180073cb5  jz      short loc_180073CCC
0x180073cb7  mov     edx, 14Bh
0x180073cbc  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073cc3  mov     rcx, [rcx+10h]
0x180073cc7  call    WPP_SF_
0x180073ccc  lea     rcx, [rsi+0B5D8h]
0x180073cd3  xor     edx, edx
0x180073cd5  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180073cda  jmp     short loc_180073CDE
0x180073cdc  xor     ebx, ebx
0x180073cde  mov     edi, ebx
0x180073ce0  lea     rcx, [rsp+10F0h+var_10D0]
0x180073ce5  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x180073cea  nop
0x180073ceb  lea     rcx, [rsp+10F0h+lpName]; void *
0x180073cf0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180073cf5  mov     eax, edi
0x180073cf7  mov     rcx, [rbp+0FF0h+var_20]
0x180073cfe  xor     rcx, rsp; StackCookie
0x180073d01  call    __security_check_cookie
0x180073d06  lea     r11, [rsp+10F0h+var_10]
0x180073d0e  mov     rbx, [r11+28h]
0x180073d12  mov     rsi, [r11+30h]
0x180073d16  mov     rsp, r11
0x180073d19  pop     r14
0x180073d1b  pop     rdi
0x180073d1c  pop     rbp
0x180073d1d  retn
```
