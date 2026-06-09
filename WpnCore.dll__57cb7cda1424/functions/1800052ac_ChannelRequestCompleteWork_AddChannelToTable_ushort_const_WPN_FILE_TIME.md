# ChannelRequestCompleteWork::AddChannelToTable(ushort const *,_WPN_FILE_TIME &)

- ea: `0x1800052ac`
- end: `0x180005677`
- name: `?AddChannelToTable@ChannelRequestCompleteWork@@AEAAJPEBGAEAU_WPN_FILE_TIME@@@Z`
- size: `971`
- prototype: `int(ChannelRequestCompleteWork *__hidden this, const unsigned __int16 *, struct _WPN_FILE_TIME *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004ba0`

## callees

- `0x180004e38`
- `0x180005070`
- `0x1800052ac`
- `0x18000568c`
- `0x180005c9c`
- `0x180005d94`
- `0x18000e5f4`
- `0x180011618`
- `0x18002bf64`
- `0x18002c22c`
- `0x18002d610`
- `0x18009cf0c`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800055e7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800055e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005320`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005531`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800052db`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800052db`

## string_xrefs

- `0x1800052ed`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`
- `0x1800053e9`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`
- `0x18000547a`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`
- `0x180005513`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`
- `0x1800055f7`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`
- `0x180005664`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ChannelRequestCompleteWork::AddChannelToTable(
        ChannelRequestCompleteWork *this,
        struct INotificationDatabase *a2,
        struct _WPN_FILE_TIME *a3)
{
  BOOL v6; // eax
  const char *v7; // r9
  char *v8; // rdi
  char *v9; // rdx
  _QWORD *v10; // rdx
  int v11; // eax
  __int64 v12; // rbx
  int v13; // ebx
  unsigned __int16 **v14; // r9
  int v15; // eax
  void *v16; // rdx
  int v17; // ecx
  const char *v18; // r9
  int v19; // ebx
  void *v20; // rbx
  WpnDatabaseHelpers *v21; // rcx
  unsigned __int16 *v22; // rcx
  wil::details *v23; // rcx
  wil::details *v24; // rcx
  __int64 result; // rax
  struct IWNSChannelDetails *v26; // r9
  int updated; // eax
  int v28; // ecx
  int v29; // r14d
  int v30; // [rsp+20h] [rbp-78h]
  struct _FILETIME v31; // [rsp+40h] [rbp-58h] BYREF
  wil::details *v32; // [rsp+48h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-48h] BYREF
  wil::details *v34; // [rsp+58h] [rbp-40h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-38h] BYREF
  wil::details *v36; // [rsp+68h] [rbp-30h] BYREF
  wil::details *v37; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  WpnDatabaseHelpers *v39; // [rsp+A0h] [rbp+8h] BYREF
  struct INotificationDatabase *v40; // [rsp+A8h] [rbp+10h] BYREF
  unsigned __int16 *v41; // [rsp+B8h] [rbp+20h] BYREF

  v40 = a2;
  v31 = 0;
  v6 = SystemTimeToFileTime((const SYSTEMTIME *)((char *)this + 84), &v31);
  try
  {
    if ( !v6 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
        v7);
    *(_DWORD *)a3 = 1;
    *(struct _FILETIME *)((char *)a3 + 4) = v31;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    pv = 0;
    WpnGetDeviceVersionFromRegistry((unsigned __int64 *)&pv);
    v8 = (char *)this + 16;
    if ( *((_QWORD *)this + 5) <= 7u )
      v9 = (char *)this + 16;
    else
      v9 = *(char **)v8;
    ConvertUtf16ToUtf8(&v32, v9);
    v10 = (_QWORD *)((char *)this + 48);
    if ( *((_QWORD *)this + 9) > 7u )
      v10 = (_QWORD *)*v10;
    ConvertUtf16ToUtf8(&v34, v10);
    v41 = 0;
    v36 = v34;
    v37 = v32;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    v11 = Microsoft::WRL::Details::MakeAndInitialize<WNSChannelDetails,IWNSChannelDetails,unsigned short const * &,char *,char *,_FILETIME &,_FILETIME &,unsigned __int64 &>(
            (unsigned int)&v41,
            (unsigned int)&v40,
            (unsigned int)&v37,
            (unsigned int)&v36,
            (__int64)&SystemTimeAsFileTime,
            (__int64)&v31,
            (__int64)&pv);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
        (const char *)(unsigned int)v11,
        v30);
    v39 = 0;
    v12 = *((_QWORD *)this + 13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v13 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, WpnDatabaseHelpers **))(v12 + 144))(
            *(_QWORD *)(v12 + 144),
            &GUID_145e48ec_626a_4302_9000_36e8172c6d29,
            &v39);
    if ( v13 >= 0 && !v39 )
    {
      v13 = -2143420155;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x400,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)0x803E0105LL,
        v30);
    }
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
        (const char *)(unsigned int)v13,
        v30);
    pv = 0;
    if ( (unsigned int)WpnDatabaseHelpers::GetAppForChannelId(v39, v32, (const char *)&pv, v14) == -2147023728 )
    {
      v15 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, struct INotificationDatabase *, unsigned __int16 *))(*(_QWORD *)v39 + 280LL))(
              v39,
              a2,
              v41);
      v19 = v15;
      if ( (byte_18015DE45 & 2) != 0 )
      {
        if ( *((_QWORD *)this + 5) > 7u )
          v8 = *(char **)v8;
        McTemplateU0zzd_EventWriteTransfer(v17, (unsigned int)WPNEND_CHANNEL_ADDED, (_DWORD)v8, (_DWORD)a2, v15);
      }
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
          (const char *)(unsigned int)v19,
          v30);
      v20 = pv;
    }
    else
    {
      v20 = pv;
      if ( (unsigned int)_o__wcsicmp(a2, pv) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
          (const char *)0x80070057LL,
          v30);
      updated = WpnDatabaseHelpers::UpdateChannelForApp(v39, a2, v41, v26);
      v29 = updated;
      if ( (byte_18015DE45 & 2) != 0 )
      {
        if ( *((_QWORD *)v8 + 3) > 7u )
          v8 = *(char **)v8;
        McTemplateU0zzd_EventWriteTransfer(v28, (unsigned int)WPNEND_CHANNEL_UPDATED, (_DWORD)v8, (_DWORD)a2, updated);
      }
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
          (const char *)(unsigned int)v29,
          v30);
    }
    if ( v20 )
      CoTaskMemFree(v20);
    v21 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(WpnDatabaseHelpers *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v34;
    v34 = 0;
    if ( v23 )
      wil::details::FreeProcessHeap(v23, v16);
    v24 = v32;
    v32 = 0;
    if ( v24 )
      wil::details::FreeProcessHeap(v24, v16);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v39) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xEE,
                     (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
                     v18);
    return (unsigned int)v39;
  }
  return result;
}

```

## disassembly

```asm
0x1800052ac  mov     rax, rsp
0x1800052af  mov     [rax+18h], rbx
0x1800052b3  mov     [rax+10h], rdx
0x1800052b7  push    rsi
0x1800052b8  push    rdi
0x1800052b9  push    r14
0x1800052bb  sub     rsp, 80h
0x1800052c2  mov     rbx, r8
0x1800052c5  mov     rsi, rdx
0x1800052c8  mov     r14, rcx
0x1800052cb  mov     qword ptr [rax-58h], 0
0x1800052d3  add     rcx, 54h ; 'T'; lpSystemTime
0x1800052d7  lea     rdx, [rax-58h]; lpFileTime
0x1800052db  call    cs:__imp_SystemTimeToFileTime
0x1800052e1  mov     rcx, [rsp+98h]; this
0x1800052e9  test    eax, eax
0x1800052eb  jnz     short loc_1800052FE
0x1800052ed  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800052f4  mov     edx, 0BCh; void *
0x1800052f9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800052fe  mov     dword ptr [rbx], 1
0x180005304  mov     eax, [rsp+98h+var_58]
0x180005308  mov     [rbx+4], eax
0x18000530b  mov     eax, [rsp+98h+var_54]
0x18000530f  mov     [rbx+8], eax
0x180005312  mov     qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000531b  lea     rcx, [rsp+98h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005320  call    cs:__imp_GetSystemTimeAsFileTime
0x180005326  mov     [rsp+98h+pv], 0
0x18000532f  lea     rcx, [rsp+98h+pv]; unsigned __int64 *
0x180005334  call    ?WpnGetDeviceVersionFromRegistry@@YAXPEA_K@Z; WpnGetDeviceVersionFromRegistry(unsigned __int64 *)
0x180005339  lea     rdi, [r14+10h]
0x18000533d  cmp     qword ptr [rdi+18h], 7
0x180005342  jbe     short loc_180005349
0x180005344  mov     rdx, [rdi]
0x180005347  jmp     short loc_18000534C
0x180005349  mov     rdx, rdi
0x18000534c  lea     rcx, [rsp+98h+var_50]
0x180005351  call    ?ConvertUtf16ToUtf8@@YA?AV?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@PEBG@Z; ConvertUtf16ToUtf8(ushort const *)
0x180005356  nop
0x180005357  lea     rdx, [r14+30h]
0x18000535b  cmp     qword ptr [rdx+18h], 7
0x180005360  jbe     short loc_180005365
0x180005362  mov     rdx, [rdx]
0x180005365  lea     rcx, [rsp+98h+var_40]
0x18000536a  call    ?ConvertUtf16ToUtf8@@YA?AV?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@PEBG@Z; ConvertUtf16ToUtf8(ushort const *)
0x18000536f  nop
0x180005370  mov     [rsp+98h+arg_18], 0
0x18000537c  mov     rax, [rsp+98h+var_40]
0x180005381  mov     [rsp+98h+var_30], rax
0x180005386  mov     rax, [rsp+98h+var_50]
0x18000538b  mov     [rsp+98h+var_28], rax
0x180005390  lea     rcx, [rsp+98h+arg_18]
0x180005398  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000539d  lea     rax, [rsp+98h+pv]
0x1800053a2  mov     [rsp+98h+var_68], rax
0x1800053a7  lea     rax, [rsp+98h+var_58]
0x1800053ac  mov     [rsp+98h+var_70], rax
0x1800053b1  lea     rax, [rsp+98h+SystemTimeAsFileTime]
0x1800053b6  mov     qword ptr [rsp+98h+var_78], rax; int
0x1800053bb  lea     r9, [rsp+98h+var_30]
0x1800053c0  lea     r8, [rsp+98h+var_28]
0x1800053c5  lea     rdx, [rsp+98h+arg_8]
0x1800053cd  lea     rcx, [rsp+98h+arg_18]
0x1800053d5  call    ??$MakeAndInitialize@VWNSChannelDetails@@UIWNSChannelDetails@@AEAPEBGPEADPEADAEAU_FILETIME@@AEAU3@AEA_K@Details@WRL@Microsoft@@YAJPEAPEAUIWNSChannelDetails@@AEAPEBG$$QEAPEAD2AEAU_FILETIME@@3AEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<WNSChannelDetails,IWNSChannelDetails,ushort const * &,char *,char *,_FILETIME &,_FILETIME &,unsigned __int64 &>(IWNSChannelDetails * *,ushort const * &,char * &&,char * &&,_FILETIME &,_FILETIME &,unsigned __int64 &)
0x1800053da  mov     rcx, [rsp+98h]; this
0x1800053e2  test    eax, eax
0x1800053e4  jns     short loc_1800053FA
0x1800053e6  mov     r9d, eax; char *
0x1800053e9  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800053f0  mov     edx, 0D3h; void *
0x1800053f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800053fa  mov     [rsp+98h+arg_0], 0
0x180005406  mov     rbx, [r14+68h]
0x18000540a  lea     rcx, [rsp+98h+arg_0]
0x180005412  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005417  nop
0x180005418  mov     rcx, [rbx+90h]
0x18000541f  mov     rax, [rcx]
0x180005422  lea     r8, [rsp+98h+arg_0]
0x18000542a  lea     rdx, _GUID_145e48ec_626a_4302_9000_36e8172c6d29
0x180005431  mov     rax, [rax]
0x180005434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005439  mov     ebx, eax
0x18000543b  test    eax, eax
0x18000543d  js      short loc_18000546B
0x18000543f  cmp     [rsp+98h+arg_0], 0
0x180005448  jnz     short loc_18000546B
0x18000544a  mov     rcx, [rsp+98h]; this
0x180005452  mov     ebx, 803E0105h
0x180005457  mov     r9d, ebx; char *
0x18000545a  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005461  mov     edx, 400h; void *
0x180005466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000546b  mov     rcx, [rsp+98h]; this
0x180005473  test    ebx, ebx
0x180005475  jns     short loc_18000548C
0x180005477  mov     r9d, ebx; char *
0x18000547a  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005481  mov     edx, 0D6h; void *
0x180005486  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000548c  mov     [rsp+98h+pv], 0
0x180005495  lea     r8, [rsp+98h+pv]; char *
0x18000549a  mov     rdx, [rsp+98h+var_50]; struct INotificationDatabase *
0x18000549f  mov     rcx, [rsp+98h+arg_0]; this
0x1800054a7  call    ?GetAppForChannelId@WpnDatabaseHelpers@@YAJPEAUINotificationDatabase@@PEBDPEAPEAG@Z; WpnDatabaseHelpers::GetAppForChannelId(INotificationDatabase *,char const *,ushort * *)
0x1800054ac  cmp     eax, 80070490h
0x1800054b1  jnz     loc_1800055D4
0x1800054b7  mov     rcx, [rsp+98h+arg_0]
0x1800054bf  mov     rax, [rcx]
0x1800054c2  mov     r8, [rsp+98h+arg_18]
0x1800054ca  mov     rdx, rsi
0x1800054cd  mov     rax, [rax+118h]
0x1800054d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d9  mov     ebx, eax
0x1800054db  test    cs:byte_18015DE45, 2
0x1800054e2  jz      short loc_180005504
0x1800054e4  cmp     qword ptr [rdi+18h], 7
0x1800054e9  jbe     short loc_1800054EE
0x1800054eb  mov     rdi, [rdi]
0x1800054ee  mov     [rsp+98h+var_78], ebx; int
0x1800054f2  mov     r9, rsi
0x1800054f5  mov     r8, rdi
0x1800054f8  lea     rdx, WPNEND_CHANNEL_ADDED
0x1800054ff  call    McTemplateU0zzd_EventWriteTransfer
0x180005504  mov     rcx, [rsp+98h]; this
0x18000550c  test    ebx, ebx
0x18000550e  jns     short loc_180005524
0x180005510  mov     r9d, ebx; char *
0x180005513  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000551a  mov     edx, 0E0h; void *
0x18000551f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005524  mov     rbx, [rsp+98h+pv]
0x180005529  test    rbx, rbx
0x18000552c  jz      short loc_180005538
0x18000552e  mov     rcx, rbx; pv
0x180005531  call    cs:__imp_CoTaskMemFree
0x180005537  nop
0x180005538  mov     rcx, [rsp+98h+arg_0]
0x180005540  test    rcx, rcx
0x180005543  jz      short loc_18000555E
0x180005545  mov     [rsp+98h+arg_0], 0
0x180005551  mov     rax, [rcx]
0x180005554  mov     rax, [rax+10h]
0x180005558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000555d  nop
0x18000555e  mov     rcx, [rsp+98h+arg_18]
0x180005566  test    rcx, rcx
0x180005569  jz      short loc_180005584
0x18000556b  mov     [rsp+98h+arg_18], 0
0x180005577  mov     rax, [rcx]
0x18000557a  mov     rax, [rax+10h]
0x18000557e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005583  nop
0x180005584  mov     rcx, [rsp+98h+var_40]; this
0x180005589  mov     [rsp+98h+var_40], 0
0x180005592  test    rcx, rcx
0x180005595  jz      short loc_18000559D
0x180005597  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000559c  nop
0x18000559d  mov     rcx, [rsp+98h+var_50]; this
0x1800055a2  mov     [rsp+98h+var_50], 0
0x1800055ab  test    rcx, rcx
0x1800055ae  jz      short loc_1800055B5
0x1800055b0  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800055b5  xor     eax, eax
0x1800055b7  jmp     short loc_1800055C0
0x1800055b9  mov     eax, dword ptr [rsp+98h+arg_0]
0x1800055c0  mov     rbx, [rsp+98h+arg_10]
0x1800055c8  add     rsp, 80h
0x1800055cf  pop     r14
0x1800055d1  pop     rdi
0x1800055d2  pop     rsi
0x1800055d3  retn
0x1800055d4  mov     r14, [rsp+98h]
0x1800055dc  mov     rbx, [rsp+98h+pv]
0x1800055e1  mov     rdx, rbx
0x1800055e4  mov     rcx, rsi
0x1800055e7  call    cs:__imp__o__wcsicmp
0x1800055ed  test    eax, eax
0x1800055ef  jz      short loc_18000560B
0x1800055f1  mov     r9d, 80070057h; char *
0x1800055f7  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800055fe  mov     edx, 0E5h; void *
0x180005603  mov     rcx, r14; this
0x180005606  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000560b  mov     r8, [rsp+98h+arg_18]; unsigned __int16 *
0x180005613  mov     rdx, rsi; struct INotificationDatabase *
0x180005616  mov     rcx, [rsp+98h+arg_0]; this
0x18000561e  call    ?UpdateChannelForApp@WpnDatabaseHelpers@@YAJPEAUINotificationDatabase@@PEBGPEAUIWNSChannelDetails@@@Z; WpnDatabaseHelpers::UpdateChannelForApp(INotificationDatabase *,ushort const *,IWNSChannelDetails *)
0x180005623  mov     r14d, eax
0x180005626  test    cs:byte_18015DE45, 2
0x18000562d  jz      short loc_180005650
0x18000562f  cmp     qword ptr [rdi+18h], 7
0x180005634  jbe     short loc_180005639
0x180005636  mov     rdi, [rdi]
0x180005639  mov     [rsp+98h+var_78], r14d; int
0x18000563e  mov     r9, rsi
0x180005641  mov     r8, rdi
0x180005644  lea     rdx, WPNEND_CHANNEL_UPDATED
0x18000564b  call    McTemplateU0zzd_EventWriteTransfer
0x180005650  mov     rcx, [rsp+98h]; this
0x180005658  test    r14d, r14d
0x18000565b  jns     loc_180005529
0x180005661  mov     r9d, r14d; char *
0x180005664  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000566b  mov     edx, 0E9h; void *
0x180005670  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
