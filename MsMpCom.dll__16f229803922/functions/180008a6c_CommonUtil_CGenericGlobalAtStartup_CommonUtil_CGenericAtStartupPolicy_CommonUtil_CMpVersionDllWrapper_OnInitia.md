# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitializeCallback(void *)

- ea: `0x180008a6c`
- end: `0x180008bce`
- name: `?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008e98`

## callees

- `0x180007304`
- `0x1800074fc`
- `0x180007c10`
- `0x180008a6c`
- `0x180009440`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180008b86`
- `KERNEL32!FreeLibrary` at `0x180008b86`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
         (CommonUtil *)&off_180012060,
         (__int64 (**)(void))&v19,
         "GetFileVersionInfoSizeExW",
         v5,
         0) >= 0 )
  {
    LoadedProcAddress = CommonUtil::UtilRawGetLoadedProcAddress(
                          (CommonUtil *)&off_180012048,
                          (__int64 (**)(void))&v19,
                          "GetFileVersionInfoExW",
                          v6,
                          v15);
    if ( LoadedProcAddress < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)LoadedProcAddress);
  }
  else
  {
    off_180012060 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
    v7 = CommonUtil::UtilRawGetLoadedProcAddress(
           (CommonUtil *)off_180012058,
           (__int64 (**)(void))&v19,
           "GetFileVersionInfoSizeW",
           v6,
           v15);
    if ( v7 < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v7);
    v9 = CommonUtil::UtilRawGetLoadedProcAddress(
           (CommonUtil *)&off_180012068,
           (__int64 (**)(void))&v19,
           "GetFileVersionInfoW",
           v8,
           v16);
    if ( v9 < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v9);
  }
  v12 = CommonUtil::UtilRawGetLoadedProcAddress(
          (CommonUtil *)off_180012050,
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
0x180008a6c  mov     [rsp-8+arg_8], rbx
0x180008a71  push    rbp
0x180008a72  mov     rbp, rsp
0x180008a75  sub     rsp, 60h
0x180008a79  mov     rax, cs:__security_cookie
0x180008a80  xor     rax, rsp
0x180008a83  mov     [rbp+var_10], rax
0x180008a87  mov     rbx, rcx
0x180008a8a  mov     [rbp+var_30], rcx
0x180008a8e  mov     qword ptr [rcx], 0
0x180008a95  mov     [rbp+var_38], 0
0x180008a9d  mov     dword ptr [rbp+var_28], 650076h
0x180008aa4  mov     dword ptr [rbp+var_28+4], 730072h
0x180008aab  mov     [rbp+var_20], 6F0069h
0x180008ab2  mov     [rbp+var_1C], 2E006Eh
0x180008ab9  mov     [rbp+var_18], 6C0064h
0x180008ac0  mov     [rbp+var_14], 6Ch ; 'l'
0x180008ac7  lea     rdx, [rbp+var_28]; HINSTANCE *
0x180008acb  lea     rcx, [rbp+var_38]; this
0x180008acf  call    ?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBG@Z; CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,ushort const *)
0x180008ad4  test    eax, eax
0x180008ad6  js      loc_180008BB6
0x180008adc  mov     [rbp+var_40], 0
0x180008ae0  lea     r8, aGetfileversion_1; "GetFileVersionInfoSizeExW"
0x180008ae7  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x180008aeb  lea     rcx, off_180012060; this
0x180008af2  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x180008af7  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x180008afb  test    eax, eax
0x180008afd  jns     short loc_180008B45
0x180008aff  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x180008b06  mov     cs:off_180012060, rax
0x180008b0d  lea     r8, aGetfileversion_0; "GetFileVersionInfoSizeW"
0x180008b14  lea     rcx, off_180012058; this
0x180008b1b  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x180008b20  test    eax, eax
0x180008b22  js      loc_180008BBE
0x180008b28  lea     r8, aGetfileversion_2; "GetFileVersionInfoW"
0x180008b2f  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x180008b33  lea     rcx, off_180012068; this
0x180008b3a  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x180008b3f  test    eax, eax
0x180008b41  js      short loc_180008BAE
0x180008b43  jmp     short loc_180008B5C
0x180008b45  lea     r8, aGetfileversion; "GetFileVersionInfoExW"
0x180008b4c  lea     rcx, off_180012048; this
0x180008b53  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x180008b58  test    eax, eax
0x180008b5a  js      short loc_180008BC6
0x180008b5c  lea     r8, aVerqueryvaluew; "VerQueryValueW"
0x180008b63  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x180008b67  lea     rcx, off_180012050; this
0x180008b6e  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)
0x180008b73  test    eax, eax
0x180008b75  js      short loc_180008BA6
0x180008b77  mov     rax, [rbp+var_38]
0x180008b7b  mov     rcx, [rbx]; hLibModule
0x180008b7e  mov     [rbx], rax
0x180008b81  test    rcx, rcx
0x180008b84  jz      short loc_180008B8D
0x180008b86  call    cs:__imp_FreeLibrary
0x180008b8c  nop
0x180008b8d  xor     eax, eax
0x180008b8f  mov     rcx, [rbp+var_10]
0x180008b93  xor     rcx, rsp; StackCookie
0x180008b96  call    __security_check_cookie
0x180008b9b  mov     rbx, [rsp+60h+arg_8]
0x180008ba0  add     rsp, 60h
0x180008ba4  pop     rbp
0x180008ba5  retn
0x180008ba6  mov     ecx, eax; this
0x180008ba8  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x180008bae  mov     ecx, eax; this
0x180008bb0  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x180008bb6  mov     ecx, eax; this
0x180008bb8  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x180008bbe  mov     ecx, eax; this
0x180008bc0  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x180008bc6  mov     ecx, eax; this
0x180008bc8  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```
