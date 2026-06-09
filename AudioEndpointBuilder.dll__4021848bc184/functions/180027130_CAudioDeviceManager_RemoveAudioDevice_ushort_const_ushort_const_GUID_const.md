# CAudioDeviceManager::RemoveAudioDevice(ushort const *,ushort const *,_GUID const *)

- ea: `0x180027130`
- end: `0x18002749d`
- name: `?RemoveAudioDevice@CAudioDeviceManager@@QEAAJPEBG0PEBU_GUID@@@Z`
- size: `877`
- prototype: `__int64 __fastcall(CAudioDeviceManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003630`
- `0x1800588e0`

## callees

- `0x180010da8`
- `0x180024864`
- `0x180027130`
- `0x180033444`
- `0x18003e920`
- `0x18003f7a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800273fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800273fc`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x1800273e9`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x1800273e9`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180027430`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180027465`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180027430`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180027465`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x1800273ae`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x1800273ae`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002729a`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002729a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180027176`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180027176`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180027258`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180027258`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002722c`
- `DEVOBJ!DevObjGetClassDevs` at `0x180027271`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002722c`
- `DEVOBJ!DevObjGetClassDevs` at `0x180027271`
- `DEVOBJ!DevObjDeleteDevice` at `0x1800272bb`
- `DEVOBJ!DevObjDeleteDevice` at `0x180027414`
- `DEVOBJ!DevObjDeleteDevice` at `0x1800272bb`
- `DEVOBJ!DevObjDeleteDevice` at `0x180027414`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800272fb`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800272fb`

## string_xrefs

- `0x1800271b8`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x1800271e3`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18002723d`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180027444`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
__int64 __fastcall CAudioDeviceManager::RemoveAudioDevice(
        CAudioDeviceManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  __int64 DeviceInfoList; // rax
  const char *v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned int LastError; // ebx
  __int64 v12; // rdx
  __int64 v13; // rax
  const char *v14; // r9
  unsigned int v15; // edi
  unsigned int i; // esi
  __int64 v18; // rax
  unsigned int j; // edi
  __int64 Property; // rax
  const char *v21; // r9
  int v22; // [rsp+20h] [rbp-E0h]
  int v23[2]; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v27[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+88h] [rbp-78h] BYREF
  DEVPROPKEY v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+A4h] [rbp-5Ch]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  int v32; // [rsp+B0h] [rbp-50h]
  int v33; // [rsp+B4h] [rbp-4Ch]
  _WORD *v34; // [rsp+B8h] [rbp-48h]
  __int128 v35; // [rsp+C0h] [rbp-40h] BYREF
  int v36; // [rsp+D0h] [rbp-30h]
  int v37; // [rsp+D4h] [rbp-2Ch]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  _WORD v39[200]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v26 = DeviceInfoList;
  v9 = DeviceInfoList;
  memset(v27, 0, sizeof(v27));
  if ( !a2 && !a3 )
  {
    v10 = 3704;
LABEL_6:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)0x80070057LL,
      v22);
LABEL_40:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v26);
    return LastError;
  }
  if ( !a4 )
  {
    v10 = 3707;
    goto LABEL_6;
  }
  if ( DeviceInfoList == -1 )
  {
    v12 = 3709;
LABEL_9:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
                  v8);
    goto LABEL_40;
  }
  v13 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 - *(_QWORD *)&a4->Data1;
  if ( *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 == *(_QWORD *)&a4->Data1 )
    v13 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 - *(_QWORD *)a4->Data4;
  if ( v13 )
  {
    if ( !(unsigned int)DevObjGetClassDevs(v9, a4, a3, 16, 0, 0) )
    {
      v12 = 3736;
      goto LABEL_9;
    }
LABEL_19:
    for ( i = 0; ; ++i )
    {
      LODWORD(v27[0]) = 48;
      if ( !(unsigned int)DevObjEnumDeviceInfo(v9, i, v27) )
        break;
      if ( a3 )
      {
        if ( !(unsigned int)DevObjDeleteDevice(v9, v27, 0, 0) )
        {
          v12 = 3746;
          goto LABEL_9;
        }
      }
      else
      {
        memset_0(v39, 0, sizeof(v39));
        if ( (unsigned int)DevObjGetDeviceInstanceId(v9, v27, v39, 200, 0) )
        {
          v36 = 8;
          v35 = PKEY_SWD_EndpointId_Retained;
          v29 = DEVPKEY_Device_InstanceId;
          v18 = -1;
          v24 = 0;
          v25 = 0;
          v37 = 0;
          v38 = 0;
          v28 = 131074;
          v30 = 0;
          v31 = 0;
          v32 = 18;
          do
            ++v18;
          while ( v39[v18] );
          v33 = 2 * v18 + 2;
          v34 = v39;
          v23[0] = 1;
          if ( (int)DevGetObjects(1, 0, 1, &v35, *(_QWORD *)v23, &v28, &v24, &v25) >= 0 )
          {
            for ( j = 0; j < v24; ++j )
            {
              Property = DevFindProperty(
                           &PKEY_SWD_EndpointId_Retained,
                           0,
                           0,
                           *(unsigned int *)(32LL * j + v25 + 16),
                           *(_QWORD *)(32LL * j + v25 + 24));
              if ( *(_DWORD *)(Property + 32) == 18
                && !(unsigned int)_o__wcsicmp(*(_QWORD *)(Property + 40), a2)
                && !(unsigned int)DevObjDeleteDevice(v9, v27, 0, 0) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0xED9,
                              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
                              v21);
                if ( v25 )
                  DevFreeObjects(v24);
                goto LABEL_40;
              }
            }
          }
          if ( v25 )
            ((void (*)(void))DevFreeObjects)();
        }
      }
    }
    LastError = 0;
    goto LABEL_40;
  }
  if ( (unsigned int)DevObjGetClassDevs(v9, &GUID_c166523c_fe0c_4a94_a586_f1a80cfbbf3e, 0, 0, 0, 0) )
    goto LABEL_19;
  v15 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xE88,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
          v14);
  if ( v9 )
    DevObjDestroyDeviceInfoList(v9);
  return v15;
}

```

## disassembly

```asm
0x180027130  push    rbp
0x180027132  push    rbx
0x180027133  push    rsi
0x180027134  push    rdi
0x180027135  push    r12
0x180027137  push    r14
0x180027139  push    r15
0x18002713b  lea     rbp, [rsp-180h]
0x180027143  sub     rsp, 280h
0x18002714a  mov     rax, cs:__security_cookie
0x180027151  xor     rax, rsp
0x180027154  mov     [rbp+1B0h+var_40], rax
0x18002715b  mov     rdi, r9
0x18002715e  mov     r14, r8
0x180027161  mov     r15, rdx
0x180027164  xor     r12d, r12d
0x180027167  xor     r9d, r9d
0x18002716a  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x18002716f  xor     r8d, r8d
0x180027172  xor     edx, edx
0x180027174  xor     ecx, ecx
0x180027176  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002717c  xorps   xmm0, xmm0
0x18002717f  mov     [rsp+2B0h+var_260], rax
0x180027184  mov     rbx, rax
0x180027187  movups  [rsp+2B0h+var_258], xmm0
0x18002718c  movups  [rsp+2B0h+var_248], xmm0
0x180027191  movups  [rsp+2B0h+var_238], xmm0
0x180027196  test    r15, r15
0x180027199  jnz     short loc_1800271A7
0x18002719b  test    r14, r14
0x18002719e  jnz     short loc_1800271A7
0x1800271a0  mov     edx, 0E78h
0x1800271a5  jmp     short loc_1800271B1
0x1800271a7  test    rdi, rdi
0x1800271aa  jnz     short loc_1800271D1
0x1800271ac  mov     edx, 0E7Bh; void *
0x1800271b1  mov     rcx, [rbp+1B8h]; this
0x1800271b8  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x1800271bf  mov     ebx, 80070057h
0x1800271c4  mov     r9d, ebx; char *
0x1800271c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800271cc  jmp     loc_180027470
0x1800271d1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800271d5  jnz     short loc_1800271F6
0x1800271d7  mov     edx, 0E7Dh; void *
0x1800271dc  mov     rcx, [rbp+1B8h]; this
0x1800271e3  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x1800271ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800271ef  mov     ebx, eax
0x1800271f1  jmp     loc_180027470
0x1800271f6  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800271fd  sub     rax, [rdi]
0x180027200  jnz     short loc_18002720D
0x180027202  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180027209  sub     rax, [rdi+8]
0x18002720d  mov     [rsp+2B0h+var_288], r12
0x180027212  mov     rcx, rbx
0x180027215  mov     qword ptr [rsp+2B0h+var_290], r12
0x18002721a  test    rax, rax
0x18002721d  jnz     short loc_180027265
0x18002721f  xor     r9d, r9d
0x180027222  lea     rdx, _GUID_c166523c_fe0c_4a94_a586_f1a80cfbbf3e
0x180027229  xor     r8d, r8d
0x18002722c  call    cs:__imp_DevObjGetClassDevs
0x180027232  test    eax, eax
0x180027234  jnz     short loc_180027285
0x180027236  mov     rcx, [rbp+1B8h]; this
0x18002723d  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180027244  mov     edx, 0E88h; void *
0x180027249  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002724e  mov     edi, eax
0x180027250  test    rbx, rbx
0x180027253  jz      short loc_18002725E
0x180027255  mov     rcx, rbx
0x180027258  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002725e  mov     eax, edi
0x180027260  jmp     loc_18002747C
0x180027265  mov     r9d, 10h
0x18002726b  mov     r8, r14
0x18002726e  mov     rdx, rdi
0x180027271  call    cs:__imp_DevObjGetClassDevs
0x180027277  test    eax, eax
0x180027279  jnz     short loc_180027285
0x18002727b  mov     edx, 0E98h
0x180027280  jmp     loc_1800271DC
0x180027285  mov     esi, r12d
0x180027288  lea     r8, [rsp+2B0h+var_258]
0x18002728d  mov     dword ptr [rsp+2B0h+var_258], 30h ; '0'
0x180027295  mov     edx, esi
0x180027297  mov     rcx, rbx
0x18002729a  call    cs:__imp_DevObjEnumDeviceInfo
0x1800272a0  test    eax, eax
0x1800272a2  jz      loc_18002746D
0x1800272a8  test    r14, r14
0x1800272ab  jz      short loc_1800272D3
0x1800272ad  xor     r9d, r9d
0x1800272b0  lea     rdx, [rsp+2B0h+var_258]
0x1800272b5  xor     r8d, r8d
0x1800272b8  mov     rcx, rbx
0x1800272bb  call    cs:__imp_DevObjDeleteDevice
0x1800272c1  test    eax, eax
0x1800272c3  jnz     loc_180027436
0x1800272c9  mov     edx, 0EA2h
0x1800272ce  jmp     loc_1800271DC
0x1800272d3  xor     edx, edx; Val
0x1800272d5  lea     rcx, [rbp+1B0h+var_1D0]; void *
0x1800272d9  mov     r8d, 190h; Size
0x1800272df  call    memset_0
0x1800272e4  mov     r9d, 0C8h
0x1800272ea  mov     qword ptr [rsp+2B0h+var_290], r12
0x1800272ef  lea     r8, [rbp+1B0h+var_1D0]
0x1800272f3  mov     rcx, rbx
0x1800272f6  lea     rdx, [rsp+2B0h+var_258]
0x1800272fb  call    cs:__imp_DevObjGetDeviceInstanceId
0x180027301  test    eax, eax
0x180027303  jz      loc_180027436
0x180027309  mov     eax, cs:dword_18006FE48
0x18002730f  lea     rcx, [rbp+1B0h+var_1D0]
0x180027313  movups  xmm0, cs:PKEY_SWD_EndpointId_Retained
0x18002731a  mov     [rbp+1B0h+var_1E0], eax
0x18002731d  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x180027323  movups  [rbp+1B0h+var_1F0], xmm0
0x180027327  mov     [rbp+1B0h+var_210], eax
0x18002732a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002732e  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180027335  mov     [rsp+2B0h+var_270], r12d
0x18002733a  mov     [rsp+2B0h+var_268], r12
0x18002733f  movups  [rbp+1B0h+var_220], xmm0
0x180027343  mov     [rbp+1B0h+var_1DC], r12d
0x180027347  mov     [rbp+1B0h+var_1D8], r12
0x18002734b  mov     [rbp+1B0h+var_228], 20002h
0x180027352  mov     [rbp+1B0h+var_20C], r12d
0x180027356  mov     [rbp+1B0h+var_208], r12
0x18002735a  mov     [rbp+1B0h+var_200], 12h
0x180027361  inc     rax
0x180027364  cmp     [rcx+rax*2], r12w
0x180027369  jnz     short loc_180027361
0x18002736b  lea     eax, ds:2[rax*2]
0x180027372  xor     edx, edx
0x180027374  mov     [rbp+1B0h+var_1FC], eax
0x180027377  lea     r9, [rbp+1B0h+var_1F0]
0x18002737b  lea     rax, [rbp+1B0h+var_1D0]
0x18002737f  mov     [rbp+1B0h+var_1F8], rax
0x180027383  lea     rax, [rsp+2B0h+var_268]
0x180027388  mov     [rsp+2B0h+var_278], rax
0x18002738d  lea     ecx, [rdx+1]
0x180027390  lea     rax, [rsp+2B0h+var_270]
0x180027395  mov     r8d, ecx
0x180027398  mov     [rsp+2B0h+var_280], rax
0x18002739d  lea     rax, [rbp+1B0h+var_228]
0x1800273a1  mov     [rsp+2B0h+var_288], rax
0x1800273a6  mov     [rsp+2B0h+var_290], 1
0x1800273ae  call    cs:__imp_DevGetObjects
0x1800273b4  test    eax, eax
0x1800273b6  js      short loc_180027422
0x1800273b8  mov     edi, r12d
0x1800273bb  mov     ecx, [rsp+2B0h+var_270]
0x1800273bf  cmp     edi, ecx
0x1800273c1  jnb     short loc_180027426
0x1800273c3  mov     r9, [rsp+2B0h+var_268]
0x1800273c8  xor     r8d, r8d
0x1800273cb  mov     ecx, edi
0x1800273cd  xor     edx, edx
0x1800273cf  shl     rcx, 5
0x1800273d3  mov     rax, [rcx+r9+18h]
0x1800273d8  mov     r9d, [rcx+r9+10h]
0x1800273dd  lea     rcx, PKEY_SWD_EndpointId_Retained
0x1800273e4  mov     qword ptr [rsp+2B0h+var_290], rax
0x1800273e9  call    cs:__imp_DevFindProperty
0x1800273ef  cmp     dword ptr [rax+20h], 12h
0x1800273f3  jnz     short loc_18002741E
0x1800273f5  mov     rcx, [rax+28h]
0x1800273f9  mov     rdx, r15
0x1800273fc  call    cs:__imp__o__wcsicmp
0x180027402  test    eax, eax
0x180027404  jnz     short loc_18002741E
0x180027406  xor     r9d, r9d
0x180027409  lea     rdx, [rsp+2B0h+var_258]
0x18002740e  xor     r8d, r8d
0x180027411  mov     rcx, rbx
0x180027414  call    cs:__imp_DevObjDeleteDevice
0x18002741a  test    eax, eax
0x18002741c  jz      short loc_18002743D
0x18002741e  inc     edi
0x180027420  jmp     short loc_1800273BB
0x180027422  mov     ecx, [rsp+2B0h+var_270]
0x180027426  mov     rdx, [rsp+2B0h+var_268]
0x18002742b  test    rdx, rdx
0x18002742e  jz      short loc_180027436
0x180027430  call    cs:__imp_DevFreeObjects
0x180027436  inc     esi
0x180027438  jmp     loc_180027288
0x18002743d  mov     rcx, [rbp+1B8h]; this
0x180027444  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18002744b  mov     edx, 0ED9h; void *
0x180027450  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027455  mov     rdx, [rsp+2B0h+var_268]
0x18002745a  mov     ebx, eax
0x18002745c  test    rdx, rdx
0x18002745f  jz      short loc_180027470
0x180027461  mov     ecx, [rsp+2B0h+var_270]
0x180027465  call    cs:__imp_DevFreeObjects
0x18002746b  jmp     short loc_180027470
0x18002746d  mov     ebx, r12d
0x180027470  lea     rcx, [rsp+2B0h+var_260]
0x180027475  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x18002747a  mov     eax, ebx
0x18002747c  mov     rcx, [rbp+1B0h+var_40]
0x180027483  xor     rcx, rsp; StackCookie
0x180027486  call    __security_check_cookie
0x18002748b  add     rsp, 280h
0x180027492  pop     r15
0x180027494  pop     r14
0x180027496  pop     r12
0x180027498  pop     rdi
0x180027499  pop     rsi
0x18002749a  pop     rbx
0x18002749b  pop     rbp
0x18002749c  retn
```
