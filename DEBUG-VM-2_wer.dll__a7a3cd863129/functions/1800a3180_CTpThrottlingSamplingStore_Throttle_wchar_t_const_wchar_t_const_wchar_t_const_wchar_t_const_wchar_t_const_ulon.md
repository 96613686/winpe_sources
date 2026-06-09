# CTpThrottlingSamplingStore::Throttle(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,int)

- ea: `0x1800a3180`
- end: `0x1800a3478`
- name: `?Throttle@CTpThrottlingSamplingStore@@SAJPEB_W0000KH@Z`
- size: `760`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, LPCWSTR lpValueName, unsigned int, enum THROTTLE_NAMESPACE_LEVEL *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009f884`

## callees

- `0x18000bc10`
- `0x18000c390`
- `0x18000dad0`
- `0x18000e7fc`
- `0x180013a20`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x180027344`
- `0x1800a2d44`
- `0x1800a2f38`
- `0x1800a3180`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a335f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a335f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a33e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a33e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a3437`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a3437`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a340c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a340c`

## pseudocode

```c
__int64 __fastcall CTpThrottlingSamplingStore::Throttle(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        LPCWSTR lpValueName,
        unsigned int a6,
        enum THROTTLE_NAMESPACE_LEVEL *a7)
{
  unsigned __int64 v11; // r13
  signed int ThrottlingState; // ebx
  const WCHAR *v13; // r12
  int v14; // edi
  __int64 v15; // rax
  unsigned __int64 v16; // r9
  HKEY *phkResult; // rax
  bool v18; // cf
  LSTATUS v19; // eax
  bool v20; // cc
  enum THROTTLE_NAMESPACE_LEVEL *samDesired; // [rsp+28h] [rbp-69h]
  DWORD dwDisposition; // [rsp+50h] [rbp-41h] BYREF
  int v24; // [rsp+54h] [rbp-3Dh] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-31h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[12]; // [rsp+70h] [rbp-21h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  v11 = a6;
  hKey = 0;
  *(_QWORD *)Data = 0;
  SystemTimeAsFileTime = 0;
  dwDisposition = 0;
  if ( a6 - 1 <= 0x3E7 || a6 == -1 )
  {
    v13 = lpValueName;
    a6 = 0;
    v24 = 0;
    ThrottlingState = CTpThrottlingSamplingStore::GetThrottlingState(a1, a2, a3, a4, lpValueName, (int)a7, (int *)&a6);
    if ( ThrottlingState >= 0 )
    {
      ThrottlingState = CTpThrottlingSamplingStore::GetSamplingState(a1, a2, a3, a4, &v24, samDesired);
      if ( ThrottlingState >= 0 && !a6 )
      {
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                lpSubKey,
                                L"SOFTWARE\\Microsoft\\TelemetryClient\\ThrottleStore")
          && (!a1
           || !*a1
           || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
           && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 a1))
          && (!a2
           || !*a2
           || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
           && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 a2))
          && (!a3
           || !*a3
           || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
           && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 a3))
          && (!a4
           || !*a4
           || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
           && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 a4)) )
        {
          if ( lpValueName && *lpValueName )
          {
            v14 = 0;
          }
          else
          {
            v14 = 1;
            v13 = L"ThrottleExpiryTime";
          }
          if ( (_DWORD)v11 == -1 )
          {
            v15 = -1;
          }
          else
          {
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            ThrottlingState = ULongLongMult(v11, 0xC92A69C000uLL, (unsigned __int64 *)Data);
            if ( ThrottlingState < 0 )
              goto LABEL_44;
            v15 = v16 + *(_QWORD *)Data;
            if ( v16 + *(_QWORD *)Data < v16 )
            {
              ThrottlingState = -2147024362;
              *(_QWORD *)Data = -1;
              goto LABEL_44;
            }
            ThrottlingState = 0;
          }
          *(_QWORD *)Data = v15;
          phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
          v18 = (_DWORD)a7 != 0;
          LODWORD(a7) = -(int)a7;
          v19 = RegCreateKeyExW(
                  (HKEY)(v18 - 0x7FFFFFFFLL),
                  lpSubKey[0],
                  0,
                  0,
                  0,
                  0xF013Fu,
                  0,
                  phkResult,
                  &dwDisposition);
          v20 = v19 <= 0;
          if ( v19
            || v14 && dwDisposition == 2 && (v19 = RegDeleteTreeW(hKey, 0), v20 = v19 <= 0, v19)
            || (v19 = RegSetValueExW(hKey, v13, 0, 0xBu, Data, 8u), v20 = v19 <= 0, v19) )
          {
            if ( v20 )
              ThrottlingState = v19;
            else
              ThrottlingState = (unsigned __int16)v19 | 0x80070000;
          }
        }
        else
        {
          ThrottlingState = -2147024882;
        }
      }
    }
  }
  else
  {
    ThrottlingState = -2147024809;
  }
LABEL_44:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  return (unsigned int)ThrottlingState;
}

```

## disassembly

```asm
0x1800a3180  push    rbp
0x1800a3182  push    rbx
0x1800a3183  push    rsi
0x1800a3184  push    rdi
0x1800a3185  push    r12
0x1800a3187  push    r13
0x1800a3189  push    r14
0x1800a318b  push    r15
0x1800a318d  lea     rbp, [rsp-7]
0x1800a3192  sub     rsp, 98h
0x1800a3199  mov     rdi, rcx
0x1800a319c  mov     r15, r9
0x1800a319f  lea     rcx, [rbp+3Fh+lpSubKey]; void *
0x1800a31a3  mov     r14, r8
0x1800a31a6  mov     rsi, rdx
0x1800a31a9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a31ae  mov     r13d, [rbp+3Fh+arg_28]
0x1800a31b2  xor     ecx, ecx
0x1800a31b4  mov     [rbp+3Fh+hKey], rcx
0x1800a31b8  mov     qword ptr [rbp+3Fh+Data], rcx
0x1800a31bc  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800a31c0  lea     eax, [r13-1]
0x1800a31c4  mov     [rbp+3Fh+dwDisposition], ecx
0x1800a31c7  cmp     eax, 3E7h
0x1800a31cc  jbe     short loc_1800A31DE
0x1800a31ce  cmp     r13d, 0FFFFFFFFh
0x1800a31d2  jz      short loc_1800A31DE
0x1800a31d4  mov     ebx, 80070057h
0x1800a31d9  jmp     loc_1800A3450
0x1800a31de  mov     r12, [rbp+3Fh+lpValueName]
0x1800a31e2  lea     rax, [rbp+3Fh+arg_28]
0x1800a31e6  mov     [rsp+0D0h+lpSecurityAttributes], rax; int *
0x1800a31eb  mov     r9, r15; wchar_t *
0x1800a31ee  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x1800a31f1  mov     r8, r14; wchar_t *
0x1800a31f4  mov     [rbp+3Fh+arg_28], ecx
0x1800a31f7  mov     rdx, rsi; wchar_t *
0x1800a31fa  mov     [rbp+3Fh+var_7C], ecx
0x1800a31fd  mov     rcx, rdi; wchar_t *
0x1800a3200  mov     dword ptr [rsp+0D0h+samDesired], eax; enum THROTTLE_NAMESPACE_LEVEL *
0x1800a3204  mov     qword ptr [rsp+0D0h+dwOptions], r12; lpValueName
0x1800a3209  call    ?GetThrottlingState@CTpThrottlingSamplingStore@@CAJPEB_W0000HPEAH@Z; CTpThrottlingSamplingStore::GetThrottlingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int *)
0x1800a320e  mov     ebx, eax
0x1800a3210  xor     eax, eax
0x1800a3212  test    ebx, ebx
0x1800a3214  js      loc_1800A3450
0x1800a321a  lea     rax, [rbp+3Fh+var_7C]
0x1800a321e  mov     r9, r15; wchar_t *
0x1800a3221  mov     r8, r14; wchar_t *
0x1800a3224  mov     qword ptr [rsp+0D0h+dwOptions], rax; int *
0x1800a3229  mov     rdx, rsi; wchar_t *
0x1800a322c  mov     rcx, rdi; wchar_t *
0x1800a322f  call    ?GetSamplingState@CTpThrottlingSamplingStore@@CAJPEB_W000PEAHPEAW4THROTTLE_NAMESPACE_LEVEL@@@Z; CTpThrottlingSamplingStore::GetSamplingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int *,THROTTLE_NAMESPACE_LEVEL *)
0x1800a3234  mov     ebx, eax
0x1800a3236  xor     eax, eax
0x1800a3238  test    ebx, ebx
0x1800a323a  js      loc_1800A3450
0x1800a3240  cmp     [rbp+3Fh+arg_28], eax
0x1800a3243  jnz     loc_1800A3450
0x1800a3249  lea     rdx, aSoftwareMicros_30; "SOFTWARE\\Microsoft\\TelemetryClient\\T"...
0x1800a3250  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a3254  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800a3259  xor     ecx, ecx
0x1800a325b  test    al, al
0x1800a325d  jnz     short loc_1800A3269
0x1800a325f  mov     ebx, 8007000Eh
0x1800a3264  jmp     loc_1800A3450
0x1800a3269  test    rdi, rdi
0x1800a326c  jz      short loc_1800A3297
0x1800a326e  cmp     [rdi], cx
0x1800a3271  jz      short loc_1800A3297
0x1800a3273  mov     edx, 5Ch ; '\'
0x1800a3278  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a327c  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a3281  test    al, al
0x1800a3283  jz      short loc_1800A325F
0x1800a3285  mov     rdx, rdi
0x1800a3288  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a328c  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a3291  xor     ecx, ecx
0x1800a3293  test    al, al
0x1800a3295  jz      short loc_1800A325F
0x1800a3297  test    rsi, rsi
0x1800a329a  jz      short loc_1800A32C7
0x1800a329c  cmp     [rsi], cx
0x1800a329f  jz      short loc_1800A32C7
0x1800a32a1  mov     edx, 5Ch ; '\'
0x1800a32a6  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a32aa  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a32af  test    al, al
0x1800a32b1  jz      short loc_1800A325F
0x1800a32b3  mov     rdx, rsi
0x1800a32b6  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a32ba  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a32bf  xor     esi, esi
0x1800a32c1  test    al, al
0x1800a32c3  jnz     short loc_1800A32C9
0x1800a32c5  jmp     short loc_1800A325F
0x1800a32c7  xor     esi, esi
0x1800a32c9  test    r14, r14
0x1800a32cc  jz      short loc_1800A32FE
0x1800a32ce  cmp     [r14], si
0x1800a32d2  jz      short loc_1800A32FE
0x1800a32d4  mov     edx, 5Ch ; '\'
0x1800a32d9  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a32dd  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a32e2  test    al, al
0x1800a32e4  jz      loc_1800A325F
0x1800a32ea  mov     rdx, r14
0x1800a32ed  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a32f1  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a32f6  test    al, al
0x1800a32f8  jz      loc_1800A325F
0x1800a32fe  test    r15, r15
0x1800a3301  jz      short loc_1800A3333
0x1800a3303  cmp     [r15], si
0x1800a3307  jz      short loc_1800A3333
0x1800a3309  mov     edx, 5Ch ; '\'
0x1800a330e  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a3312  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a3317  test    al, al
0x1800a3319  jz      loc_1800A325F
0x1800a331f  mov     rdx, r15
0x1800a3322  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a3326  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a332b  test    al, al
0x1800a332d  jz      loc_1800A325F
0x1800a3333  test    r12, r12
0x1800a3336  jz      short loc_1800A3343
0x1800a3338  cmp     [r12], si
0x1800a333d  jz      short loc_1800A3343
0x1800a333f  mov     edi, esi
0x1800a3341  jmp     short loc_1800A334F
0x1800a3343  mov     edi, 1
0x1800a3348  lea     r12, aThrottleexpiry; "ThrottleExpiryTime"
0x1800a334f  cmp     r13d, 0FFFFFFFFh
0x1800a3353  jnz     short loc_1800A335B
0x1800a3355  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3359  jmp     short loc_1800A339B
0x1800a335b  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a335f  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a3365  mov     r9, qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime]
0x1800a3369  lea     r8, [rbp+3Fh+Data]; unsigned __int64 *
0x1800a336d  mov     rcx, r13; unsigned __int64
0x1800a3370  mov     rdx, 0C92A69C000h; unsigned __int64
0x1800a337a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800a337f  mov     ebx, eax
0x1800a3381  test    eax, eax
0x1800a3383  js      loc_1800A3450
0x1800a3389  mov     rax, qword ptr [rbp+3Fh+Data]
0x1800a338d  add     rax, r9
0x1800a3390  cmp     rax, r9
0x1800a3393  jb      loc_1800A3443
0x1800a3399  mov     ebx, esi
0x1800a339b  lea     rcx, [rbp+3Fh+hKey]
0x1800a339f  mov     qword ptr [rbp+3Fh+Data], rax
0x1800a33a3  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800a33a8  neg     dword ptr [rbp+3Fh+arg_30]
0x1800a33ab  lea     rdx, [rbp+3Fh+dwDisposition]
0x1800a33af  mov     [rsp+0D0h+lpdwDisposition], rdx; lpdwDisposition
0x1800a33b4  mov     rdx, [rbp+3Fh+lpSubKey]; lpSubKey
0x1800a33b8  sbb     rcx, rcx
0x1800a33bb  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800a33c0  neg     rcx
0x1800a33c3  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800a33c8  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800a33cf  mov     dword ptr [rsp+0D0h+samDesired], 0F013Fh; samDesired
0x1800a33d7  xor     r9d, r9d; lpClass
0x1800a33da  xor     r8d, r8d; Reserved
0x1800a33dd  mov     [rsp+0D0h+dwOptions], esi; dwOptions
0x1800a33e1  call    cs:__imp_RegCreateKeyExW
0x1800a33e7  test    eax, eax
0x1800a33e9  jz      short loc_1800A33FC
0x1800a33eb  jg      short loc_1800A33F1
0x1800a33ed  mov     ebx, eax
0x1800a33ef  jmp     short loc_1800A3450
0x1800a33f1  movzx   ebx, ax
0x1800a33f4  or      ebx, 80070000h
0x1800a33fa  jmp     short loc_1800A3450
0x1800a33fc  test    edi, edi
0x1800a33fe  jz      short loc_1800A3416
0x1800a3400  cmp     [rbp+3Fh+dwDisposition], 2
0x1800a3404  jnz     short loc_1800A3416
0x1800a3406  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800a340a  xor     edx, edx; lpSubKey
0x1800a340c  call    cs:__imp_RegDeleteTreeW
0x1800a3412  test    eax, eax
0x1800a3414  jnz     short loc_1800A33EB
0x1800a3416  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800a341a  lea     rax, [rbp+3Fh+Data]
0x1800a341e  mov     dword ptr [rsp+0D0h+samDesired], 8; cbData
0x1800a3426  mov     r9d, 0Bh; dwType
0x1800a342c  xor     r8d, r8d; Reserved
0x1800a342f  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x1800a3434  mov     rdx, r12; lpValueName
0x1800a3437  call    cs:__imp_RegSetValueExW
0x1800a343d  test    eax, eax
0x1800a343f  jz      short loc_1800A3450
0x1800a3441  jmp     short loc_1800A33EB
0x1800a3443  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3447  mov     ebx, 80070216h
0x1800a344c  mov     qword ptr [rbp+3Fh+Data], rax
0x1800a3450  lea     rcx, [rbp+3Fh+hKey]
0x1800a3454  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800a3459  lea     rcx, [rbp+3Fh+lpSubKey]; void *
0x1800a345d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a3462  mov     eax, ebx
0x1800a3464  add     rsp, 98h
0x1800a346b  pop     r15
0x1800a346d  pop     r14
0x1800a346f  pop     r13
0x1800a3471  pop     r12
0x1800a3473  pop     rdi
0x1800a3474  pop     rsi
0x1800a3475  pop     rbx
0x1800a3476  pop     rbp
0x1800a3477  retn
```
