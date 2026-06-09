# AipCreatePackagedProcessByLaunchContract_AppExtension(void *,void *,ushort const *,ushort *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_APPINFO_STARTUPINFO_STDHANDLES *,ushort const *,_APPINFO_PROCESS_INFORMATION *)

- ea: `0x18002e8bc`
- end: `0x18002ebe4`
- name: `?AipCreatePackagedProcessByLaunchContract_AppExtension@@YAJPEAX0PEBGPEAG111K11PEAU_APPINFO_STARTUPINFO@@PEAU_APPINFO_STARTUPINFO_STDHANDLES@@1PEAU_APPINFO_PROCESS_INFORMATION@@@Z`
- size: `808`
- prototype: `__int64 __fastcall(void *, void *, unsigned __int16 *, unsigned __int16 *, WCHAR *applicationUserModelId, LPCWCH lpString1, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 *, struct _APPINFO_STARTUPINFO *, struct _APPINFO_STARTUPINFO_STDHANDLES *, unsigned __int16 *, struct _APPINFO_PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003cca0`

## callees

- `0x18000720c`
- `0x180009d50`
- `0x18000bd90`
- `0x18000c410`
- `0x180018dbc`
- `0x18002e8bc`
- `0x18002ed98`
- `0x18003c5b4`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e987`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e987`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18002ea39`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18002ea39`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002ea74`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002ea74`

## string_xrefs

- `0x18002e949`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002e9f8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002ea51`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002eb81`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002e980`: `com.microsoft.windows.ai.mcpServer`

## pseudocode

```c
__int64 __fastcall AipCreatePackagedProcessByLaunchContract_AppExtension(
        void *a1,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        WCHAR *applicationUserModelId,
        LPCWCH lpString1,
        const unsigned __int16 *a7,
        unsigned int a8,
        const unsigned __int16 *a9,
        unsigned __int16 *a10,
        struct _APPINFO_STARTUPINFO *a11,
        struct _APPINFO_STARTUPINFO_STDHANDLES *a12,
        unsigned __int16 *a13,
        struct _APPINFO_PROCESS_INFORMATION *a14)
{
  __int64 v18; // rdx
  unsigned int v19; // ebx
  unsigned int ClientInformation; // ebx
  LONG v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-130h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-130h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-130h]
  unsigned int bIgnoreCasec; // [rsp+20h] [rbp-130h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+D0h] [rbp-80h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+D4h] [rbp-7Ch] BYREF
  unsigned __int64 v31; // [rsp+D8h] [rbp-78h] BYREF
  __int64 v32; // [rsp+E0h] [rbp-70h] BYREF
  __int64 v33; // [rsp+E8h] [rbp-68h] BYREF
  __int64 *v34; // [rsp+F0h] [rbp-60h] BYREF
  void *v35; // [rsp+F8h] [rbp-58h] BYREF
  char v36; // [rsp+100h] [rbp-50h]
  struct _APPINFO_PROCESS_INFORMATION *v37; // [rsp+108h] [rbp-48h]
  struct _APPINFO_STARTUPINFO *v38; // [rsp+110h] [rbp-40h]
  unsigned __int16 *v39; // [rsp+118h] [rbp-38h]
  unsigned __int16 *v40; // [rsp+120h] [rbp-30h]
  __int64 *v41; // [rsp+128h] [rbp-28h] BYREF
  void *v42; // [rsp+130h] [rbp-20h] BYREF
  char v43; // [rsp+138h] [rbp-18h]
  _QWORD v44[4]; // [rsp+140h] [rbp-10h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+160h] [rbp+10h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+1F0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+188h]

  v40 = a10;
  v38 = a11;
  v39 = a13;
  v37 = a14;
  if ( lpString1 )
  {
    if ( !a7 )
    {
      v18 = 10800;
      goto LABEL_3;
    }
    if ( CompareStringOrdinal(lpString1, -1, L"com.microsoft.windows.ai.mcpServer", -1, 1) != 2 )
    {
      v18 = 10803;
      goto LABEL_3;
    }
    v33 = 0;
    v41 = &v32;
    v32 = 0;
    v34 = &v33;
    v42 = 0;
    v43 = 1;
    v35 = 0;
    v36 = 1;
    ClientInformation = AiGetClientInformation(a1, &v35, &v42, 0, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v34);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v41);
    if ( ClientInformation )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2A52,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)ClientInformation,
              bIgnoreCasea);
    }
    else
    {
      packageFamilyNameLength = 65;
      packageRelativeApplicationIdLength = 65;
      v21 = ParseApplicationUserModelId(
              applicationUserModelId,
              &packageFamilyNameLength,
              packageFamilyName,
              &packageRelativeApplicationIdLength,
              packageRelativeApplicationId);
      v19 = v21;
      if ( v21 >= 0 )
      {
        v31 = 0;
        v21 = UMgrQueryUserContext(a2, &v31);
        v19 = v21;
        if ( v21 >= 0 )
        {
          v44[0] = *(_QWORD *)a12;
          v44[1] = *((_QWORD *)a12 + 1);
          v44[2] = *((_QWORD *)a12 + 2);
          v34 = 0;
          v35 = 0;
          v23 = AipLaunchProcessWithIdentityImplementation(
                  a1,
                  a3,
                  a4,
                  0,
                  0xC080400u,
                  v40,
                  v39,
                  v38,
                  (struct _STARTUPINFO_STDHANDLES *)v44,
                  0,
                  0,
                  packageFamilyName,
                  applicationUserModelId,
                  0,
                  0xFFFFFFFF,
                  0x1010u,
                  3,
                  0,
                  v31,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  (void **)v37);
          if ( v23 )
          {
            v19 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x2A92,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    (const char *)v23,
                    bIgnoreCasec);
            wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v34);
          }
          else
          {
            wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v34);
            v19 = 0;
          }
          goto LABEL_18;
        }
        v22 = 10850;
      }
      else
      {
        v22 = 10844;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v21,
        bIgnoreCaseb);
    }
LABEL_18:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
    return v19;
  }
  v18 = 10799;
LABEL_3:
  v19 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
    (const char *)0x80070057LL,
    bIgnoreCase);
  return v19;
}

```

## disassembly

```asm
0x18002e8bc  push    rbp
0x18002e8be  push    rbx
0x18002e8bf  push    rsi
0x18002e8c0  push    rdi
0x18002e8c1  push    r12
0x18002e8c3  push    r13
0x18002e8c5  push    r14
0x18002e8c7  push    r15
0x18002e8c9  lea     rbp, [rsp-148h]
0x18002e8d1  sub     rsp, 298h
0x18002e8d8  mov     rax, cs:__security_cookie
0x18002e8df  xor     rax, rsp
0x18002e8e2  mov     [rbp+180h+var_50], rax
0x18002e8e9  mov     rax, [rbp+180h+arg_48]
0x18002e8f0  mov     r14, rcx
0x18002e8f3  mov     rcx, [rbp+180h+lpString1]; lpString1
0x18002e8fa  xor     ebx, ebx
0x18002e8fc  mov     r15, [rbp+180h+arg_58]
0x18002e903  mov     r13, r9
0x18002e906  mov     rdi, [rbp+180h+applicationUserModelId]
0x18002e90d  mov     r12, r8
0x18002e910  mov     [rbp+180h+var_1B0], rax
0x18002e914  mov     rsi, rdx
0x18002e917  mov     rax, [rbp+180h+arg_50]
0x18002e91e  mov     [rbp+180h+var_1C0], rax
0x18002e922  mov     rax, [rbp+180h+arg_60]
0x18002e929  mov     [rbp+180h+var_1B8], rax
0x18002e92d  mov     rax, [rbp+180h+arg_68]
0x18002e934  mov     [rbp+180h+var_1C8], rax
0x18002e938  test    rcx, rcx
0x18002e93b  jnz     short loc_18002E962
0x18002e93d  mov     edx, 2A2Fh; void *
0x18002e942  mov     rcx, [rbp+188h]; this
0x18002e949  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e950  mov     ebx, 80070057h
0x18002e955  mov     r9d, ebx; char *
0x18002e958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e95d  jmp     loc_18002EBBF
0x18002e962  cmp     [rbp+180h+arg_30], rbx
0x18002e969  jnz     short loc_18002E972
0x18002e96b  mov     edx, 2A30h
0x18002e970  jmp     short loc_18002E942
0x18002e972  or      edx, 0FFFFFFFFh; cchCount1
0x18002e975  mov     [rsp+2D0h+bIgnoreCase], 1; bIgnoreCase
0x18002e97d  mov     r9d, edx; cchCount2
0x18002e980  lea     r8, aComMicrosoftWi; "com.microsoft.windows.ai.mcpServer"
0x18002e987  call    cs:__imp_CompareStringOrdinal
0x18002e98d  cmp     eax, 2
0x18002e990  jz      short loc_18002E999
0x18002e992  mov     edx, 2A33h
0x18002e997  jmp     short loc_18002E942
0x18002e999  lea     rax, [rbp+180h+var_1F0]
0x18002e99d  mov     [rbp+180h+var_1E8], rbx
0x18002e9a1  mov     [rbp+180h+var_1A8], rax
0x18002e9a5  lea     r8, [rbp+180h+var_1A0]; void **
0x18002e9a9  lea     rax, [rbp+180h+var_1E8]
0x18002e9ad  mov     [rbp+180h+var_1F0], rbx
0x18002e9b1  xor     r9d, r9d; unsigned int *
0x18002e9b4  mov     [rbp+180h+var_1E0], rax
0x18002e9b8  lea     rdx, [rbp+180h+var_1D8]; void **
0x18002e9bc  mov     [rbp+180h+var_1A0], rbx
0x18002e9c0  mov     rcx, r14; void *
0x18002e9c3  mov     [rbp+180h+var_198], 1
0x18002e9c7  mov     [rbp+180h+var_1D8], rbx
0x18002e9cb  mov     [rbp+180h+var_1D0], 1
0x18002e9cf  mov     qword ptr [rsp+2D0h+bIgnoreCase], rbx; unsigned int
0x18002e9d4  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18002e9d9  lea     rcx, [rbp+180h+var_1E0]
0x18002e9dd  mov     ebx, eax
0x18002e9df  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002e9e4  lea     rcx, [rbp+180h+var_1A8]
0x18002e9e8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002e9ed  test    ebx, ebx
0x18002e9ef  jz      short loc_18002EA13
0x18002e9f1  mov     rcx, [rbp+188h]; this
0x18002e9f8  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e9ff  mov     r9d, ebx; char *
0x18002ea02  mov     edx, 2A52h; void *
0x18002ea07  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002ea0c  mov     ebx, eax
0x18002ea0e  jmp     loc_18002EBAD
0x18002ea13  mov     eax, 41h ; 'A'
0x18002ea18  lea     r9, [rbp+180h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18002ea1c  mov     [rbp+180h+packageFamilyNameLength], eax
0x18002ea1f  lea     r8, [rbp+180h+packageFamilyName]; packageFamilyName
0x18002ea23  mov     [rbp+180h+packageRelativeApplicationIdLength], eax
0x18002ea26  lea     rdx, [rbp+180h+packageFamilyNameLength]; packageFamilyNameLength
0x18002ea2a  lea     rax, [rbp+180h+packageRelativeApplicationId]
0x18002ea31  mov     rcx, rdi; applicationUserModelId
0x18002ea34  mov     qword ptr [rsp+2D0h+bIgnoreCase], rax; int
0x18002ea39  call    cs:__imp_ParseApplicationUserModelId
0x18002ea3f  mov     ebx, eax
0x18002ea41  test    eax, eax
0x18002ea43  jns     short loc_18002EA65
0x18002ea45  mov     edx, 2A5Ch; void *
0x18002ea4a  mov     rcx, [rbp+188h]; this
0x18002ea51  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002ea58  mov     r9d, eax; char *
0x18002ea5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ea60  jmp     loc_18002EBAD
0x18002ea65  lea     rdx, [rbp+180h+var_1F8]
0x18002ea69  mov     [rbp+180h+var_1F8], 0
0x18002ea71  mov     rcx, rsi
0x18002ea74  call    cs:__imp_UMgrQueryUserContext
0x18002ea7a  xor     esi, esi
0x18002ea7c  mov     ebx, eax
0x18002ea7e  test    eax, eax
0x18002ea80  jns     short loc_18002EA89
0x18002ea82  mov     edx, 2A62h
0x18002ea87  jmp     short loc_18002EA4A
0x18002ea89  mov     rax, [r15]
0x18002ea8c  xor     r9d, r9d; unsigned int
0x18002ea8f  mov     rdx, [rbp+180h+var_1C8]
0x18002ea93  mov     r8, r13; unsigned __int16 *
0x18002ea96  movzx   ecx, word ptr [rbp+180h+arg_38]
0x18002ea9d  mov     [rsp+2D0h+var_208], rdx; struct _APPINFO_PROCESS_INFORMATION *
0x18002eaa5  mov     rdx, r12; unsigned __int16 *
0x18002eaa8  mov     [rsp+2D0h+var_210], rsi; enum UACPROMPT_POLICY *
0x18002eab0  mov     [rsp+2D0h+var_218], rsi; int *
0x18002eab8  mov     [rsp+2D0h+var_220], rsi; char *
0x18002eac0  mov     [rsp+2D0h+var_228], rsi; unsigned __int64
0x18002eac8  mov     [rsp+2D0h+var_230], rsi; struct _GUID *
0x18002ead0  mov     [rsp+2D0h+var_238], rsi; unsigned __int64 *
0x18002ead8  mov     [rbp+180h+var_190], rax
0x18002eadc  mov     rax, [r15+8]
0x18002eae0  mov     [rbp+180h+var_188], rax
0x18002eae4  mov     rax, [r15+10h]
0x18002eae8  mov     [rbp+180h+var_180], rax
0x18002eaec  mov     rax, [rbp+180h+var_1F8]
0x18002eaf0  mov     [rsp+2D0h+var_240], rax; unsigned __int64
0x18002eaf8  lea     rax, [rbp+180h+packageFamilyName]
0x18002eafc  mov     [rsp+2D0h+var_248], rsi; void *
0x18002eb04  shl     ecx, 10h
0x18002eb07  or      ecx, 3
0x18002eb0a  mov     [rbp+180h+var_1E0], rsi
0x18002eb0e  mov     [rsp+2D0h+var_250], ecx; unsigned int
0x18002eb15  mov     rcx, r14; void *
0x18002eb18  mov     [rsp+2D0h+var_258], 1010h; unsigned int
0x18002eb20  mov     [rsp+2D0h+var_260], 0FFFFFFFFh; unsigned int
0x18002eb28  mov     [rsp+2D0h+var_268], rsi; unsigned __int64
0x18002eb2d  mov     [rsp+2D0h+var_270], rdi; unsigned __int16 *
0x18002eb32  mov     [rsp+2D0h+var_278], rax; unsigned __int16 *
0x18002eb37  lea     rax, [rbp+180h+var_190]
0x18002eb3b  mov     [rsp+2D0h+var_280], rsi; unsigned __int64
0x18002eb40  mov     [rsp+2D0h+var_288], rsi; unsigned __int16 **
0x18002eb45  mov     [rsp+2D0h+var_290], rax; struct _STARTUPINFO_STDHANDLES *
0x18002eb4a  mov     rax, [rbp+180h+var_1C0]
0x18002eb4e  mov     [rsp+2D0h+var_298], rax; struct _APPINFO_STARTUPINFO *
0x18002eb53  mov     rax, [rbp+180h+var_1B8]
0x18002eb57  mov     [rsp+2D0h+var_2A0], rax; unsigned __int16 *
0x18002eb5c  mov     rax, [rbp+180h+var_1B0]
0x18002eb60  mov     [rsp+2D0h+var_2A8], rax; unsigned __int16 *
0x18002eb65  mov     [rsp+2D0h+bIgnoreCase], 0C080400h; unsigned int
0x18002eb6d  mov     [rbp+180h+var_1D8], rsi
0x18002eb71  call    ?AipLaunchProcessWithIdentityImplementation@@YAKPEAXPEBGPEAGKK11PEAU_APPINFO_STARTUPINFO@@PEAU_STARTUPINFO_STDHANDLES@@PEAPEAG_K116KKK06PEA_KPEAU_GUID@@6PEBDPEAHPEAW4UACPROMPT_POLICY@@PEAU_APPINFO_PROCESS_INFORMATION@@@Z; AipLaunchProcessWithIdentityImplementation(void *,ushort const *,ushort *,ulong,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_STARTUPINFO_STDHANDLES *,ushort * *,unsigned __int64,ushort const *,ushort const *,unsigned __int64,ulong,ulong,ulong,void *,unsigned __int64,unsigned __int64 *,_GUID *,unsigned __int64,char const *,int *,UACPROMPT_POLICY *,_APPINFO_PROCESS_INFORMATION *)
0x18002eb76  test    eax, eax
0x18002eb78  jz      short loc_18002EBA2
0x18002eb7a  mov     rcx, [rbp+188h]; this
0x18002eb81  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002eb88  mov     r9d, eax; char *
0x18002eb8b  mov     edx, 2A92h; void *
0x18002eb90  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002eb95  lea     rcx, [rbp+180h+var_1E0]
0x18002eb99  mov     ebx, eax
0x18002eb9b  call    ?reset@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18002eba0  jmp     short loc_18002EBAD
0x18002eba2  lea     rcx, [rbp+180h+var_1E0]
0x18002eba6  call    ?reset@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18002ebab  mov     ebx, esi
0x18002ebad  lea     rcx, [rbp+180h+var_1F0]
0x18002ebb1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002ebb6  lea     rcx, [rbp+180h+var_1E8]
0x18002ebba  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002ebbf  mov     eax, ebx
0x18002ebc1  mov     rcx, [rbp+180h+var_50]
0x18002ebc8  xor     rcx, rsp; StackCookie
0x18002ebcb  call    __security_check_cookie
0x18002ebd0  add     rsp, 298h
0x18002ebd7  pop     r15
0x18002ebd9  pop     r14
0x18002ebdb  pop     r13
0x18002ebdd  pop     r12
0x18002ebdf  pop     rdi
0x18002ebe0  pop     rsi
0x18002ebe1  pop     rbx
0x18002ebe2  pop     rbp
0x18002ebe3  retn
```
