# CReport::ThrottleCurrentEvent(ulong)

- ea: `0x180073680`
- end: `0x18007396a`
- name: `?ThrottleCurrentEvent@CReport@@QEAAJK@Z`
- size: `746`
- prototype: `__int64 __fastcall(CReport *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024998`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x180013730`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x18001fe24`
- `0x180073680`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180073726`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180073726`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073823`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073823`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073806`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073806`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073856`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800738c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073856`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800738c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073876`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800738e9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073876`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800738e9`

## pseudocode

```c
__int64 __fastcall CReport::ThrottleCurrentEvent(CReport *this, int a2)
{
  bool v4; // zf
  int v5; // ebx
  __int64 v6; // rsi
  __int64 i; // rbx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LPCWSTR lpSubKey[5]; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+28h] BYREF
  int v17; // [rsp+A8h] [rbp+30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+38h] BYREF
  struct _FILETIME Data; // [rsp+B8h] [rbp+40h] BYREF

  SystemTimeAsFileTime = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  v4 = *((_DWORD *)this + 1468) == 3;
  hKey = 0;
  Data = 0;
  v17 = a2;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 293, WPP_6898268820d636d20e115db2eaa75970_Traceguids);
    goto LABEL_5;
  }
  v6 = *((_QWORD *)this + 70);
  if ( (unsigned int)(a2 - 315360001) <= 0xED33FCFD )
    v17 = 315360000;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 2 )
    {
      v5 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
             lpSubKey,
             L"%s\\%s\\%s",
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             L"Throttling",
             *((_QWORD *)this + 70));
      if ( v5 >= 0 )
      {
        phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
        Key = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0, 0, 0x20106u, 0, phkResult, 0);
        if ( Key || !hKey )
        {
          v5 = ERROR_HR_FROM_WIN32(Key);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_34;
          v9 = 296;
        }
        else
        {
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          Data = SystemTimeAsFileTime;
          v12 = RegSetValueExW(hKey, L"LastTime", 0, 0xBu, (const BYTE *)&Data, 8u);
          if ( v12 )
          {
            v5 = ERROR_HR_FROM_WIN32(v12);
            RegDeleteKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_34;
            v9 = 297;
          }
          else
          {
            v13 = RegSetValueExW(hKey, L"Duration", 0, 4u, (const BYTE *)&v17, 4u);
            if ( !v13 )
            {
              v5 = 0;
              goto LABEL_34;
            }
            v5 = ERROR_HR_FROM_WIN32(v13);
            RegDeleteKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_34;
            v9 = 298;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_34;
        v9 = 295;
      }
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_6898268820d636d20e115db2eaa75970_Traceguids, (unsigned int)v5);
      goto LABEL_34;
    }
    if ( !(unsigned int)_o__wcsicmp(v6, off_1800AF140[i]) )
      break;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v6);
LABEL_5:
  v5 = -2147019873;
LABEL_34:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180073680  push    rbp
0x180073682  push    rbx
0x180073683  push    rsi
0x180073684  push    rdi
0x180073685  mov     rbp, rsp
0x180073688  sub     rsp, 78h
0x18007368c  mov     rdi, rcx
0x18007368f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180073697  lea     rcx, [rbp+lpSubKey]; void *
0x18007369b  mov     ebx, edx
0x18007369d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800736a2  cmp     dword ptr [rdi+16F0h], 3
0x1800736a9  mov     [rbp+hKey], 0
0x1800736b1  mov     [rbp+Data], 0
0x1800736b9  mov     [rbp+arg_8], ebx
0x1800736bc  jnz     short loc_1800736F6
0x1800736be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736c5  lea     rax, WPP_GLOBAL_Control
0x1800736cc  cmp     rcx, rax
0x1800736cf  jz      short loc_1800736EC
0x1800736d1  test    byte ptr [rcx+1Ch], 1
0x1800736d5  jz      short loc_1800736EC
0x1800736d7  mov     rcx, [rcx+10h]
0x1800736db  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x1800736e2  mov     edx, 125h
0x1800736e7  call    WPP_SF_
0x1800736ec  mov     ebx, 8007139Fh
0x1800736f1  jmp     loc_18007394D
0x1800736f6  mov     rsi, [rdi+230h]
0x1800736fd  lea     eax, [rbx-12CC0301h]
0x180073703  cmp     eax, 0ED33FCFDh
0x180073708  ja      short loc_180073711
0x18007370a  mov     [rbp+arg_8], 12CC0300h
0x180073711  xor     ebx, ebx
0x180073713  cmp     ebx, 2
0x180073716  jnb     short loc_180073767
0x180073718  lea     rax, off_1800AF140; "APPCRASH"
0x18007371f  mov     rcx, rsi
0x180073722  mov     rdx, [rax+rbx*8]
0x180073726  call    cs:__imp__o__wcsicmp
0x18007372c  test    eax, eax
0x18007372e  jz      short loc_180073734
0x180073730  inc     ebx
0x180073732  jmp     short loc_180073713
0x180073734  mov     rcx, cs:WPP_GLOBAL_Control
0x18007373b  lea     rax, WPP_GLOBAL_Control
0x180073742  cmp     rcx, rax
0x180073745  jz      short loc_1800736EC
0x180073747  test    byte ptr [rcx+1Ch], 1
0x18007374b  jz      short loc_1800736EC
0x18007374d  mov     rcx, [rcx+10h]
0x180073751  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073758  mov     edx, 126h
0x18007375d  mov     r9, rsi
0x180073760  call    WPP_SF_S
0x180073765  jmp     short loc_1800736EC
0x180073767  mov     rax, [rdi+230h]
0x18007376e  lea     r9, aThrottling; "Throttling"
0x180073775  lea     r8, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x18007377c  mov     qword ptr [rsp+78h+dwOptions], rax
0x180073781  lea     rdx, aSSS; "%s\\%s\\%s"
0x180073788  lea     rcx, [rbp+lpSubKey]
0x18007378c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180073791  mov     ebx, eax
0x180073793  test    eax, eax
0x180073795  jns     short loc_1800737C2
0x180073797  mov     rcx, cs:WPP_GLOBAL_Control
0x18007379e  lea     rax, WPP_GLOBAL_Control
0x1800737a5  cmp     rcx, rax
0x1800737a8  jz      loc_18007394D
0x1800737ae  test    byte ptr [rcx+1Ch], 1
0x1800737b2  jz      loc_18007394D
0x1800737b8  mov     edx, 127h
0x1800737bd  jmp     loc_18007393A
0x1800737c2  lea     rcx, [rbp+hKey]
0x1800737c6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800737cb  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800737cf  mov     rdi, 0FFFFFFFF80000001h
0x1800737d6  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800737df  xor     r9d, r9d; lpClass
0x1800737e2  mov     [rsp+78h+phkResult], rax; phkResult
0x1800737e7  xor     r8d, r8d; Reserved
0x1800737ea  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800737f3  mov     rcx, rdi; hKey
0x1800737f6  mov     [rsp+78h+samDesired], 20106h; samDesired
0x1800737fe  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180073806  call    cs:__imp_RegCreateKeyExW
0x18007380c  test    eax, eax
0x18007380e  jnz     loc_180073913
0x180073814  cmp     [rbp+hKey], 0
0x180073819  jz      loc_180073913
0x18007381f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180073823  call    cs:__imp_GetSystemTimeAsFileTime
0x180073829  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18007382d  lea     rdx, aLasttime; "LastTime"
0x180073834  mov     rcx, [rbp+hKey]; hKey
0x180073838  mov     r9d, 0Bh; dwType
0x18007383e  mov     [rbp+Data], rax
0x180073842  xor     r8d, r8d; Reserved
0x180073845  lea     rax, [rbp+Data]
0x180073849  mov     [rsp+78h+samDesired], 8; cbData
0x180073851  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180073856  call    cs:__imp_RegSetValueExW
0x18007385c  test    eax, eax
0x18007385e  jz      short loc_1800738A7
0x180073860  mov     ecx, eax; unsigned int
0x180073862  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180073867  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18007386b  mov     rcx, rdi; hKey
0x18007386e  xor     r9d, r9d; Reserved
0x180073871  xor     r8d, r8d; samDesired
0x180073874  mov     ebx, eax
0x180073876  call    cs:__imp_RegDeleteKeyExW
0x18007387c  mov     rcx, cs:WPP_GLOBAL_Control
0x180073883  lea     rax, WPP_GLOBAL_Control
0x18007388a  cmp     rcx, rax
0x18007388d  jz      loc_18007394D
0x180073893  test    byte ptr [rcx+1Ch], 1
0x180073897  jz      loc_18007394D
0x18007389d  mov     edx, 129h
0x1800738a2  jmp     loc_18007393A
0x1800738a7  mov     rcx, [rbp+hKey]; hKey
0x1800738ab  lea     rax, [rbp+arg_8]
0x1800738af  mov     r9d, 4; dwType
0x1800738b5  lea     rdx, aDuration; "Duration"
0x1800738bc  mov     [rsp+78h+samDesired], r9d; cbData
0x1800738c1  xor     r8d, r8d; Reserved
0x1800738c4  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1800738c9  call    cs:__imp_RegSetValueExW
0x1800738cf  test    eax, eax
0x1800738d1  jz      short loc_18007390F
0x1800738d3  mov     ecx, eax; unsigned int
0x1800738d5  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800738da  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800738de  mov     rcx, rdi; hKey
0x1800738e1  xor     r9d, r9d; Reserved
0x1800738e4  xor     r8d, r8d; samDesired
0x1800738e7  mov     ebx, eax
0x1800738e9  call    cs:__imp_RegDeleteKeyExW
0x1800738ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800738f6  lea     rax, WPP_GLOBAL_Control
0x1800738fd  cmp     rcx, rax
0x180073900  jz      short loc_18007394D
0x180073902  test    byte ptr [rcx+1Ch], 1
0x180073906  jz      short loc_18007394D
0x180073908  mov     edx, 12Ah
0x18007390d  jmp     short loc_18007393A
0x18007390f  xor     ebx, ebx
0x180073911  jmp     short loc_18007394D
0x180073913  mov     ecx, eax; unsigned int
0x180073915  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18007391a  mov     ebx, eax
0x18007391c  mov     rcx, cs:WPP_GLOBAL_Control
0x180073923  lea     rax, WPP_GLOBAL_Control
0x18007392a  cmp     rcx, rax
0x18007392d  jz      short loc_18007394D
0x18007392f  test    byte ptr [rcx+1Ch], 1
0x180073933  jz      short loc_18007394D
0x180073935  mov     edx, 128h
0x18007393a  mov     rcx, [rcx+10h]
0x18007393e  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073945  mov     r9d, ebx
0x180073948  call    WPP_SF_d
0x18007394d  lea     rcx, [rbp+hKey]
0x180073951  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180073956  lea     rcx, [rbp+lpSubKey]; void *
0x18007395a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007395f  mov     eax, ebx
0x180073961  add     rsp, 78h
0x180073965  pop     rdi
0x180073966  pop     rsi
0x180073967  pop     rbx
0x180073968  pop     rbp
0x180073969  retn
```
