# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitializeCallback(void *)

- ea: `0x1400102f0`
- end: `0x140010452`
- name: `?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z`
- size: `354`
- prototype: `__int64 __fastcall(HMODULE *, __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400015d0`
- `0x14000e508`
- `0x14000ed24`
- `0x14000ef14`
- `0x1400102f0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14001040a`
- `KERNEL32!FreeLibrary` at `0x14001040a`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitializeCallback(
        HMODULE *a1,
        __int64 a2,
        const unsigned __int16 *a3)
{
  int v4; // eax
  const char *v5; // r9
  const char *v6; // r9
  int v7; // eax
  const char *v8; // r9
  int v9; // eax
  const char *v10; // r9
  int LoadedProcAddress; // eax
  int v12; // eax
  HMODULE v13; // rcx
  bool v15; // [rsp+20h] [rbp-40h]
  bool v16; // [rsp+20h] [rbp-40h]
  bool v17; // [rsp+20h] [rbp-40h]
  _QWORD v18[2]; // [rsp+28h] [rbp-38h] BYREF
  HINSTANCE v19; // [rsp+38h] [rbp-28h] BYREF
  int v20; // [rsp+40h] [rbp-20h]
  int v21; // [rsp+44h] [rbp-1Ch]
  int v22; // [rsp+48h] [rbp-18h]
  int v23; // [rsp+4Ch] [rbp-14h]

  v18[1] = a1;
  *a1 = 0;
  v18[0] = 0;
  v19 = (HINSTANCE)0x73007200650076LL;
  v20 = 7274601;
  v21 = 3014766;
  v22 = 7077988;
  v23 = 108;
  v4 = CommonUtil::UtilLoadSystemLibrary((CommonUtil *)v18, &v19, a3);
  if ( v4 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v4);
  if ( CommonUtil::UtilRawGetLoadedProcAddress(
         (CommonUtil *)&off_14001B018,
         (__int64 (**)(void))&v19,
         "GetFileVersionInfoSizeExW",
         v5,
         0) >= 0 )
  {
    LoadedProcAddress = CommonUtil::UtilRawGetLoadedProcAddress(
                          (CommonUtil *)&off_14001B000,
                          (__int64 (**)(void))&v19,
                          "GetFileVersionInfoExW",
                          v6,
                          v15);
    if ( LoadedProcAddress < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)LoadedProcAddress);
  }
  else
  {
    off_14001B018 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
    v7 = CommonUtil::UtilRawGetLoadedProcAddress(
           (CommonUtil *)&off_14001B010,
           (__int64 (**)(void))&v19,
           "GetFileVersionInfoSizeW",
           v6,
           v15);
    if ( v7 < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v7);
    v9 = CommonUtil::UtilRawGetLoadedProcAddress(
           (CommonUtil *)&off_14001B020,
           (__int64 (**)(void))&v19,
           "GetFileVersionInfoW",
           v8,
           v16);
    if ( v9 < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v9);
  }
  v12 = CommonUtil::UtilRawGetLoadedProcAddress(
          (CommonUtil *)&off_14001B008,
          (__int64 (**)(void))&v19,
          "VerQueryValueW",
          v10,
          v17);
  if ( v12 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v12);
  v13 = *a1;
  *a1 = (HMODULE)v18[0];
  if ( v13 )
    FreeLibrary(v13);
  return 0;
}

```

## disassembly

```asm
0x1400102f0  mov     [rsp-8+arg_8], rbx
0x1400102f5  push    rbp
0x1400102f6  mov     rbp, rsp
0x1400102f9  sub     rsp, 60h
0x1400102fd  mov     rax, cs:__security_cookie
0x140010304  xor     rax, rsp
0x140010307  mov     [rbp+var_10], rax
0x14001030b  mov     rbx, rcx
0x14001030e  mov     [rbp+var_30], rcx
0x140010312  mov     qword ptr [rcx], 0
0x140010319  mov     [rbp+var_38], 0
0x140010321  mov     dword ptr [rbp+var_28], 650076h
0x140010328  mov     dword ptr [rbp+var_28+4], 730072h
0x14001032f  mov     [rbp+var_20], 6F0069h
0x140010336  mov     [rbp+var_1C], 2E006Eh
0x14001033d  mov     [rbp+var_18], 6C0064h
0x140010344  mov     [rbp+var_14], 6Ch ; 'l'
0x14001034b  lea     rdx, [rbp+var_28]; HINSTANCE *
0x14001034f  lea     rcx, [rbp+var_38]; this
0x140010353  call    ?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBG@Z; CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,ushort const *)
0x140010358  test    eax, eax
0x14001035a  js      loc_14001043A
0x140010360  mov     [rbp+var_40], 0
0x140010364  lea     r8, aGetfileversion_1; "GetFileVersionInfoSizeExW"
0x14001036b  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x14001036f  lea     rcx, off_14001B018; this
0x140010376  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x14001037b  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x14001037f  test    eax, eax
0x140010381  jns     short loc_1400103C9
0x140010383  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x14001038a  mov     cs:off_14001B018, rax
0x140010391  lea     r8, aGetfileversion_0; "GetFileVersionInfoSizeW"
0x140010398  lea     rcx, off_14001B010; this
0x14001039f  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x1400103a4  test    eax, eax
0x1400103a6  js      loc_140010442
0x1400103ac  lea     r8, aGetfileversion_2; "GetFileVersionInfoW"
0x1400103b3  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x1400103b7  lea     rcx, off_14001B020; this
0x1400103be  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x1400103c3  test    eax, eax
0x1400103c5  js      short loc_140010432
0x1400103c7  jmp     short loc_1400103E0
0x1400103c9  lea     r8, aGetfileversion; "GetFileVersionInfoExW"
0x1400103d0  lea     rcx, off_14001B000; this
0x1400103d7  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x1400103dc  test    eax, eax
0x1400103de  js      short loc_14001044A
0x1400103e0  lea     r8, aVerqueryvaluew; "VerQueryValueW"
0x1400103e7  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x1400103eb  lea     rcx, off_14001B008; this
0x1400103f2  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x1400103f7  test    eax, eax
0x1400103f9  js      short loc_14001042A
0x1400103fb  mov     rax, [rbp+var_38]
0x1400103ff  mov     rcx, [rbx]; hLibModule
0x140010402  mov     [rbx], rax
0x140010405  test    rcx, rcx
0x140010408  jz      short loc_140010411
0x14001040a  call    cs:__imp_FreeLibrary
0x140010410  nop
0x140010411  xor     eax, eax
0x140010413  mov     rcx, [rbp+var_10]
0x140010417  xor     rcx, rsp; StackCookie
0x14001041a  call    __security_check_cookie
0x14001041f  mov     rbx, [rsp+60h+arg_8]
0x140010424  add     rsp, 60h
0x140010428  pop     rbp
0x140010429  retn
0x14001042a  mov     ecx, eax; this
0x14001042c  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x140010432  mov     ecx, eax; this
0x140010434  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x14001043a  mov     ecx, eax; this
0x14001043c  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x140010442  mov     ecx, eax; this
0x140010444  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x14001044a  mov     ecx, eax; this
0x14001044c  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```
