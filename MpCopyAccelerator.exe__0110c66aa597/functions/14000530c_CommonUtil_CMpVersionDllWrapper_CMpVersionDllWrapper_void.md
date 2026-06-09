# CommonUtil::CMpVersionDllWrapper::CMpVersionDllWrapper(void)

- ea: `0x14000530c`
- end: `0x14000549b`
- name: `??0CMpVersionDllWrapper@CommonUtil@@QEAA@XZ`
- size: `399`
- prototype: `__int64 __fastcall(CommonUtil::CMpVersionDllWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400055f0`

## callees

- `0x140002e74`
- `0x140003c50`
- `0x140003de4`
- `0x14000530c`
- `0x140005c20`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140005455`
- `KERNEL32!FreeLibrary` at `0x140005455`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CommonUtil::CMpVersionDllWrapper *__fastcall CommonUtil::CMpVersionDllWrapper::CMpVersionDllWrapper(
        HMODULE *this,
        __int64 a2,
        const wchar_t *a3)
{
  int v4; // eax
  int LoadedProcAddress; // eax
  const char *v6; // r9
  int v7; // eax
  const char *v8; // r9
  int v9; // eax
  const char *v10; // r9
  int v11; // eax
  int v12; // eax
  HMODULE v13; // rcx
  bool v15; // [rsp+20h] [rbp-40h]
  bool v16; // [rsp+20h] [rbp-40h]
  bool v17; // [rsp+20h] [rbp-40h]
  HMODULE v18; // [rsp+30h] [rbp-30h] BYREF
  HINSTANCE v19; // [rsp+38h] [rbp-28h] BYREF
  int v20; // [rsp+40h] [rbp-20h]
  int v21; // [rsp+44h] [rbp-1Ch]
  int v22; // [rsp+48h] [rbp-18h]
  int v23; // [rsp+4Ch] [rbp-14h]

  *this = 0;
  v18 = 0;
  v19 = (HINSTANCE)0x73007200650076LL;
  v20 = 7274601;
  v21 = 3014766;
  v22 = 7077988;
  v23 = 108;
  v4 = CommonUtil::UtilLoadSystemLibrary((CommonUtil *)&v18, &v19, a3);
  if ( v4 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v4);
  LoadedProcAddress = CommonUtil::UtilRawGetLoadedProcAddress(
                        (CommonUtil *)&off_14003B128,
                        (__int64 (**)(void))&v19,
                        "GetFileVersionInfoSizeExW",
                        0,
                        0);
  LOBYTE(v6) = 1;
  if ( LoadedProcAddress >= 0 )
  {
    v11 = CommonUtil::UtilRawGetLoadedProcAddress(
            (CommonUtil *)&off_14003B130,
            (__int64 (**)(void))&v19,
            "GetFileVersionInfoExW",
            v6,
            v15);
    if ( v11 < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v11);
  }
  else
  {
    off_14003B128 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
    v7 = CommonUtil::UtilRawGetLoadedProcAddress(
           (CommonUtil *)off_14003B110,
           (__int64 (**)(void))&v19,
           "GetFileVersionInfoSizeW",
           v6,
           v15);
    if ( v7 < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v7);
    LOBYTE(v8) = 1;
    v9 = CommonUtil::UtilRawGetLoadedProcAddress(
           (CommonUtil *)off_14003B118,
           (__int64 (**)(void))&v19,
           "GetFileVersionInfoW",
           v8,
           v16);
    if ( v9 < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v9);
  }
  LOBYTE(v10) = 1;
  v12 = CommonUtil::UtilRawGetLoadedProcAddress(
          (CommonUtil *)off_14003B120,
          (__int64 (**)(void))&v19,
          "VerQueryValueW",
          v10,
          v17);
  if ( v12 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v12);
  v13 = *this;
  *this = v18;
  v18 = v13;
  if ( v13 )
    FreeLibrary(v13);
  return (CommonUtil::CMpVersionDllWrapper *)this;
}

```

## disassembly

```asm
0x14000530c  mov     [rsp-8+arg_8], rbx
0x140005311  mov     [rsp-8+arg_10], rdi
0x140005316  push    rbp
0x140005317  mov     rbp, rsp
0x14000531a  sub     rsp, 60h
0x14000531e  mov     rax, cs:__security_cookie
0x140005325  xor     rax, rsp
0x140005328  mov     [rbp+var_10], rax
0x14000532c  mov     rbx, rcx
0x14000532f  mov     [rbp+var_38], rcx
0x140005333  xor     edi, edi
0x140005335  mov     [rcx], rdi
0x140005338  mov     [rbp+var_30], rdi
0x14000533c  mov     dword ptr [rbp+var_28], 650076h
0x140005343  mov     dword ptr [rbp+var_28+4], 730072h
0x14000534a  mov     [rbp+var_20], 6F0069h
0x140005351  mov     [rbp+var_1C], 2E006Eh
0x140005358  mov     [rbp+var_18], 6C0064h
0x14000535f  mov     [rbp+var_14], 6Ch ; 'l'
0x140005366  lea     rdx, [rbp+var_28]; HINSTANCE *
0x14000536a  lea     rcx, [rbp+var_30]; this
0x14000536e  call    ?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z; CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,wchar_t const *)
0x140005373  mov     ecx, eax; this
0x140005375  shr     eax, 1Fh
0x140005378  test    al, al
0x14000537a  jnz     loc_140005489
0x140005380  mov     [rbp+var_40], dil
0x140005384  xor     r9d, r9d; char *
0x140005387  lea     r8, aGetfileversion_1; "GetFileVersionInfoSizeExW"
0x14000538e  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x140005392  lea     rcx, off_14003B128; this
0x140005399  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEB_WPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),wchar_t const *,char const *,bool)
0x14000539e  shr     eax, 1Fh
0x1400053a1  mov     r9b, 1; char *
0x1400053a4  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x1400053a8  test    al, al
0x1400053aa  jz      short loc_140005403
0x1400053ac  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x1400053b3  mov     cs:off_14003B128, rax
0x1400053ba  lea     r8, aGetfileversion_0; "GetFileVersionInfoSizeW"
0x1400053c1  lea     rcx, off_14003B110; this
0x1400053c8  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEB_WPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),wchar_t const *,char const *,bool)
0x1400053cd  mov     ecx, eax; this
0x1400053cf  shr     eax, 1Fh
0x1400053d2  test    al, al
0x1400053d4  jnz     loc_14000548F
0x1400053da  mov     r9b, 1; char *
0x1400053dd  lea     r8, aGetfileversion_2; "GetFileVersionInfoW"
0x1400053e4  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x1400053e8  lea     rcx, off_14003B118; this
0x1400053ef  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEB_WPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),wchar_t const *,char const *,bool)
0x1400053f4  mov     ecx, eax; this
0x1400053f6  shr     eax, 1Fh
0x1400053f9  test    al, al
0x1400053fb  jnz     loc_140005483
0x140005401  jmp     short loc_14000541F
0x140005403  lea     r8, aGetfileversion; "GetFileVersionInfoExW"
0x14000540a  lea     rcx, off_14003B130; this
0x140005411  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEB_WPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),wchar_t const *,char const *,bool)
0x140005416  mov     ecx, eax; this
0x140005418  shr     eax, 1Fh
0x14000541b  test    al, al
0x14000541d  jnz     short loc_140005495
0x14000541f  mov     r9b, 1; char *
0x140005422  lea     r8, aVerqueryvaluew; "VerQueryValueW"
0x140005429  lea     rdx, [rbp+var_28]; __int64 (**)(void)
0x14000542d  lea     rcx, off_14003B120; this
0x140005434  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEB_WPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),wchar_t const *,char const *,bool)
0x140005439  mov     ecx, eax; this
0x14000543b  shr     eax, 1Fh
0x14000543e  test    al, al
0x140005440  jnz     short loc_14000547D
0x140005442  mov     rcx, [rbx]; hLibModule
0x140005445  mov     rdx, [rbp+var_30]
0x140005449  mov     [rbx], rdx
0x14000544c  mov     [rbp+var_30], rcx
0x140005450  test    rcx, rcx
0x140005453  jz      short loc_14000545C
0x140005455  call    cs:__imp_FreeLibrary
0x14000545b  nop
0x14000545c  mov     rax, rbx
0x14000545f  mov     rcx, [rbp+var_10]
0x140005463  xor     rcx, rsp; StackCookie
0x140005466  call    __security_check_cookie
0x14000546b  lea     r11, [rsp+60h+var_s0]
0x140005470  mov     rbx, [r11+18h]
0x140005474  mov     rdi, [r11+20h]
0x140005478  mov     rsp, r11
0x14000547b  pop     rbp
0x14000547c  retn
0x14000547d  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x140005483  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x140005489  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x14000548f  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x140005495  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```
