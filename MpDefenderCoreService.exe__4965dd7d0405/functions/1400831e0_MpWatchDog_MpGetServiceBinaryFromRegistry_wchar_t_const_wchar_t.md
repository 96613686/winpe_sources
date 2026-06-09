# MpWatchDog::MpGetServiceBinaryFromRegistry(wchar_t const *,wchar_t * *)

- ea: `0x1400831e0`
- end: `0x1400833d2`
- name: `?MpGetServiceBinaryFromRegistry@MpWatchDog@@YAJPEB_WPEAPEA_W@Z`
- size: `498`
- prototype: `__int64 __fastcall(MpWatchDog *__hidden this, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140082fb4`

## callees

- `0x1400121a8`
- `0x14001263c`
- `0x140014b10`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x1400831e0`
- `0x140085d94`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400832bb`
- `ADVAPI32!RegCloseKey` at `0x140083367`
- `ADVAPI32!RegCloseKey` at `0x1400832bb`
- `ADVAPI32!RegCloseKey` at `0x140083367`

## string_xrefs

- `0x14008321f`: `System\CurrentControlSet\Services\%ls`
- `0x1400832e8`: `ImagePath`

## pseudocode

```c
__int64 __fastcall MpWatchDog::MpGetServiceBinaryFromRegistry(MpWatchDog *this, wchar_t *a2, wchar_t **a3)
{
  const struct std::nothrow_t *v4; // rdx
  int v5; // ebx
  HKEY v7; // rbx
  int v8; // eax
  unsigned int v9; // esi
  const struct std::nothrow_t *v10; // rdx
  int ValueString; // eax
  const struct std::nothrow_t *v12; // rdx
  HKEY v13; // rax
  HKEY v14; // rcx
  HKEY v15; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF

  if ( a2 )
  {
    *(_QWORD *)a2 = 0;
    v15 = 0;
    v5 = CommonUtil::NewSprintfW(
           (CommonUtil *)&v15,
           (wchar_t **)L"System\\CurrentControlSet\\Services\\%ls",
           L"WinDefend");
    if ( v5 < 0 )
    {
      if ( v15 )
        operator delete(v15, v4);
      return (unsigned int)v5;
    }
    v7 = v15;
    hKey = 0;
    v8 = CommonUtil::UtilRegOpenKey(
           (CommonUtil *)&hKey,
           (HKEY *)0xFFFFFFFF80000002LL,
           (const WCHAR *)v15,
           (const wchar_t *)1);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          16,
          (unsigned int)WPP_fab25902b95537784195265cb25f9216_Traceguids,
          (_DWORD)v7,
          v8);
LABEL_10:
      if ( hKey )
        RegCloseKey(hKey);
      if ( v7 )
        operator delete(v7, v10);
      return v9;
    }
    v15 = 0;
    ValueString = CommonUtil::UtilRegGetValueString(hKey, L"ImagePath", &v15, 0, 0);
    v9 = ValueString;
    if ( ValueString < 0 )
    {
      v10 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          17,
          (unsigned int)WPP_fab25902b95537784195265cb25f9216_Traceguids,
          (_DWORD)v7,
          ValueString);
      if ( v15 )
        operator delete(v15, v10);
      goto LABEL_10;
    }
    v13 = v15;
    v14 = hKey;
    v15 = 0;
    *(_QWORD *)a2 = v13;
    if ( v14 )
      RegCloseKey(v14);
    if ( v7 )
      operator delete(v7, v12);
    return 0;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_fab25902b95537784195265cb25f9216_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1400831e0  mov     [rsp-8+arg_0], rbx
0x1400831e5  mov     [rsp-8+arg_10], rsi
0x1400831ea  mov     [rsp-8+arg_18], rdi
0x1400831ef  push    rbp
0x1400831f0  mov     rbp, rsp
0x1400831f3  sub     rsp, 50h
0x1400831f7  mov     rax, cs:__security_cookie
0x1400831fe  xor     rax, rsp
0x140083201  mov     [rbp+var_10], rax
0x140083205  mov     rdi, rdx
0x140083208  test    rdx, rdx
0x14008320b  jz      loc_14008337E
0x140083211  mov     qword ptr [rdx], 0
0x140083218  lea     r8, aWindefend; "WinDefend"
0x14008321f  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\%l"...
0x140083226  mov     [rbp+var_20], 0
0x14008322e  lea     rcx, [rbp+var_20]; this
0x140083232  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x140083237  mov     ebx, eax
0x140083239  test    eax, eax
0x14008323b  jns     short loc_140083252
0x14008323d  mov     rcx, [rbp+var_20]; void *
0x140083241  test    rcx, rcx
0x140083244  jz      short loc_14008324B
0x140083246  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008324b  mov     eax, ebx
0x14008324d  jmp     loc_1400833B1
0x140083252  mov     rbx, [rbp+var_20]
0x140083256  lea     rcx, [rbp+hKey]; this
0x14008325a  mov     r8, rbx; HKEY
0x14008325d  mov     [rbp+hKey], 0
0x140083265  mov     r9d, 1; wchar_t *
0x14008326b  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x140083272  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x140083277  mov     esi, eax
0x140083279  test    eax, eax
0x14008327b  jns     short loc_1400832D5
0x14008327d  mov     rcx, cs:WPP_GLOBAL_Control
0x140083284  lea     rdx, WPP_GLOBAL_Control
0x14008328b  cmp     rcx, rdx
0x14008328e  jz      short loc_1400832B2
0x140083290  test    byte ptr [rcx+1Ch], 1
0x140083294  jz      short loc_1400832B2
0x140083296  mov     rcx, [rcx+10h]
0x14008329a  lea     r8, WPP_fab25902b95537784195265cb25f9216_Traceguids
0x1400832a1  mov     edx, 10h
0x1400832a6  mov     dword ptr [rsp+50h+var_30], eax
0x1400832aa  mov     r9, rbx
0x1400832ad  call    WPP_SF_Sd
0x1400832b2  mov     rcx, [rbp+hKey]; hKey
0x1400832b6  test    rcx, rcx
0x1400832b9  jz      short loc_1400832C1
0x1400832bb  call    cs:__imp_RegCloseKey
0x1400832c1  test    rbx, rbx
0x1400832c4  jz      short loc_1400832CE
0x1400832c6  mov     rcx, rbx; void *
0x1400832c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400832ce  mov     eax, esi
0x1400832d0  jmp     loc_1400833B1
0x1400832d5  mov     rcx, [rbp+hKey]
0x1400832d9  lea     r8, [rbp+var_20]
0x1400832dd  xor     r9d, r9d
0x1400832e0  mov     [rbp+var_20], 0
0x1400832e8  lea     rdx, aImagepath; "ImagePath"
0x1400832ef  mov     [rsp+50h+var_30], 0
0x1400832f8  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x1400832fd  mov     esi, eax
0x1400832ff  test    eax, eax
0x140083301  jns     short loc_14008334F
0x140083303  mov     rcx, cs:WPP_GLOBAL_Control
0x14008330a  lea     rdx, WPP_GLOBAL_Control
0x140083311  cmp     rcx, rdx
0x140083314  jz      short loc_140083338
0x140083316  test    byte ptr [rcx+1Ch], 1
0x14008331a  jz      short loc_140083338
0x14008331c  mov     rcx, [rcx+10h]
0x140083320  lea     r8, WPP_fab25902b95537784195265cb25f9216_Traceguids
0x140083327  mov     edx, 11h
0x14008332c  mov     dword ptr [rsp+50h+var_30], eax
0x140083330  mov     r9, rbx
0x140083333  call    WPP_SF_Sd
0x140083338  mov     rcx, [rbp+var_20]; void *
0x14008333c  test    rcx, rcx
0x14008333f  jz      loc_1400832B2
0x140083345  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008334a  jmp     loc_1400832B2
0x14008334f  mov     rax, [rbp+var_20]
0x140083353  mov     rcx, [rbp+hKey]; hKey
0x140083357  mov     [rbp+var_20], 0
0x14008335f  mov     [rdi], rax
0x140083362  test    rcx, rcx
0x140083365  jz      short loc_14008336D
0x140083367  call    cs:__imp_RegCloseKey
0x14008336d  test    rbx, rbx
0x140083370  jz      short loc_14008337A
0x140083372  mov     rcx, rbx; void *
0x140083375  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008337a  xor     eax, eax
0x14008337c  jmp     short loc_1400833B1
0x14008337e  mov     rcx, cs:WPP_GLOBAL_Control
0x140083385  lea     rdx, WPP_GLOBAL_Control
0x14008338c  cmp     rcx, rdx
0x14008338f  jz      short loc_1400833AC
0x140083391  test    byte ptr [rcx+1Ch], 1
0x140083395  jz      short loc_1400833AC
0x140083397  mov     rcx, [rcx+10h]
0x14008339b  lea     r8, WPP_fab25902b95537784195265cb25f9216_Traceguids
0x1400833a2  mov     edx, 0Fh
0x1400833a7  call    WPP_SF_
0x1400833ac  mov     eax, 80070057h
0x1400833b1  mov     rcx, [rbp+var_10]
0x1400833b5  xor     rcx, rsp; StackCookie
0x1400833b8  call    __security_check_cookie
0x1400833bd  mov     rbx, [rsp+50h+arg_0]
0x1400833c2  mov     rsi, [rsp+50h+arg_10]
0x1400833c7  mov     rdi, [rsp+50h+arg_18]
0x1400833cc  add     rsp, 50h
0x1400833d0  pop     rbp
0x1400833d1  retn
```
