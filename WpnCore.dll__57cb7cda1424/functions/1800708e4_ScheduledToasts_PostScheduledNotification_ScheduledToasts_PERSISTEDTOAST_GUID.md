# ScheduledToasts::PostScheduledNotification(ScheduledToasts::_PERSISTEDTOAST *,_GUID *)

- ea: `0x1800708e4`
- end: `0x180070fb8`
- name: `?PostScheduledNotification@ScheduledToasts@@CAJPEAU_PERSISTEDTOAST@1@PEAU_GUID@@@Z`
- size: `1748`
- prototype: `__int64 __fastcall(struct ScheduledToasts::_PERSISTEDTOAST *, struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008e000`

## callees

- `0x180004e38`
- `0x18000c1cc`
- `0x18000e5f4`
- `0x18002ab88`
- `0x18002ccac`
- `0x1800708e4`
- `0x18009d1dc`
- `0x18009d8ec`
- `0x1800a1308`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070b5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070b5f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180070d18`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180070d18`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180070b1a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180070b1a`

## string_xrefs

- `0x180070942`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800709a4`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800709ed`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070a3b`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070b02`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070b3e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070c9a`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070cf4`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070d2d`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070def`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070e28`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070e9d`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180070bac`: `AdaptiveJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ScheduledToasts::PostScheduledNotification(
        struct ScheduledToasts::_PERSISTEDTOAST *a1,
        struct _GUID *a2)
{
  __int64 v4; // r14
  __int64 (__fastcall *v5)(__int64, _QWORD, GUID *, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rcx
  _BYTE *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  IStream *v18; // rbx
  int v19; // ecx
  int v20; // edx
  const wchar_t *v21; // rax
  int v22; // eax
  int v23; // eax
  HRESULT v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rcx
  ScheduledNotification *v29; // rcx
  __int64 v30; // rcx
  const char *v31; // r9
  __int64 v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v34; // rcx
  __int64 result; // rax
  int v36; // [rsp+20h] [rbp-188h]
  int v37; // [rsp+20h] [rbp-188h]
  int v38; // [rsp+20h] [rbp-188h]
  __int64 v39; // [rsp+58h] [rbp-150h] BYREF
  ScheduledNotification *v40; // [rsp+60h] [rbp-148h] BYREF
  __int64 v41; // [rsp+68h] [rbp-140h] BYREF
  __int64 v42; // [rsp+70h] [rbp-138h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-130h] BYREF
  __int64 v44; // [rsp+80h] [rbp-128h] BYREF
  __int64 v45; // [rsp+88h] [rbp-120h] BYREF
  int v46; // [rsp+90h] [rbp-118h] BYREF
  unsigned int v47; // [rsp+94h] [rbp-114h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp-110h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-108h] BYREF
  int v50[2]; // [rsp+A8h] [rbp-100h] BYREF
  ScheduledNotification *v51; // [rsp+B0h] [rbp-F8h] BYREF
  _QWORD v52[3]; // [rsp+B8h] [rbp-F0h] BYREF
  _QWORD v53[7]; // [rsp+D0h] [rbp-D8h] BYREF
  int v54; // [rsp+108h] [rbp-A0h]
  int v55; // [rsp+10Ch] [rbp-9Ch]
  struct _FILETIME v56; // [rsp+110h] [rbp-98h]
  __int64 v57; // [rsp+118h] [rbp-90h]
  __int64 LastBootTime; // [rsp+120h] [rbp-88h]
  char v59; // [rsp+128h] [rbp-80h]
  int v60; // [rsp+129h] [rbp-7Fh]
  __int16 v61; // [rsp+12Dh] [rbp-7Bh]
  char v62; // [rsp+12Fh] [rbp-79h]
  __int64 v63; // [rsp+130h] [rbp-78h]
  __int128 v64; // [rsp+138h] [rbp-70h]
  __int64 v65; // [rsp+148h] [rbp-60h]
  __int64 v66; // [rsp+150h] [rbp-58h]
  GUID pguid; // [rsp+160h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  Microsoft::WRL::Details::Make<PlatformFactory,>(&v49);
  try
  {
    v4 = v49;
    if ( !v49 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x514,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)0x80004003LL,
        v36);
    v44 = 0;
    v43 = 0;
    v42 = 0;
    v5 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v49 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v6 = v5(v4, 0, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, &v44);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x519,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v6,
        v36);
    v7 = v44;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v44 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    v9 = v8(v7, &v43);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v9,
        v36);
    v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
    v11 = **v43;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    v12 = v11(v10, &GUID_926516e8_d891_45bc_9de5_6959fb8ecac5, &v42);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v12,
        v36);
    v13 = *((_QWORD *)a1 + 4);
    v45 = v13;
    *(_QWORD *)v50 = v13;
    if ( (byte_18015DE45 & 1) != 0 )
      McTemplateU0zjm_EventWriteTransfer(
        HIDWORD(v13),
        (unsigned int)WPNEND_SCHEDULED_TOAST_TIMER,
        (_DWORD)a1 + 92,
        (_DWORD)a1 + 4,
        (__int64)v50);
    if ( a1 == (struct ScheduledToasts::_PERSISTEDTOAST *)-608LL )
    {
      v17 = 2147942487LL;
    }
    else
    {
      v14 = 5120;
      v15 = (char *)a1 + 608;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v14;
      }
      while ( v14 );
      v16 = (5120 - v14) & -(__int64)(v14 != 0);
      v17 = v14 == 0 ? 0x80070057 : 0;
      if ( v14 )
        goto LABEL_20;
    }
    LODWORD(v16) = 0;
LABEL_20:
    if ( (int)v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x529,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)v17,
        v36);
    v18 = SHCreateMemStream((const BYTE *)a1 + 608, v16);
    v52[1] = v18;
    if ( !v18 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x52D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)0x8007000ELL,
        v36);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( *((_DWORD *)a1 + 1532) )
    {
      v19 = *((_DWORD *)a1 + 1533);
      v20 = *((_DWORD *)a1 + 1534);
    }
    else
    {
      v19 = 0;
      v20 = 0;
    }
    v53[0] = 0;
    v53[1] = (char *)a1 + 92;
    v53[2] = L"toast";
    v21 = L"Xml";
    if ( *((_DWORD *)a1 + 1535) )
      v21 = L"AdaptiveJson";
    v53[3] = v21;
    v53[4] = v18;
    v53[5] = (char *)a1 + 5868;
    v53[6] = (char *)a1 + 5998;
    v54 = v19;
    v55 = v20;
    v56 = SystemTimeAsFileTime;
    v57 = 3;
    LastBootTime = GetLastBootTime();
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 1;
    v66 = 0;
    v41 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    v22 = Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(&v41, v53);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x546,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v22,
        v36);
    v40 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    v23 = Microsoft::WRL::Details::MakeAndInitialize<ScheduledNotification,ScheduledNotification,unsigned short const (&)[1],__int64 &,int &,__int64 &,unsigned int &>(
            &v40,
            &word_180124798,
            (__int64 *)a1 + 4,
            (int *)a1 + 12,
            (__int64 *)a1 + 5,
            (unsigned int *)a1 + 14);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v23,
        v37);
    pguid = 0;
    v24 = CoCreateGuid(&pguid);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x552,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v24,
        v37);
    v39 = 0;
    v51 = v40;
    v52[0] = 0;
    v46 = 0;
    v47 = 0;
    LODWORD(v45) = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v25 = Microsoft::WRL::Details::MakeAndInitialize<TransientNotificationDetails,TransientNotificationDetails,int,unsigned short const (&)[1],int,int &,_GUID &,_GUID &,enum WpnToastNotificationPriority,std::nullptr_t,ScheduledNotification *>(
            &v39,
            (unsigned int *)&v45,
            (__int64)&word_180124798,
            &v47,
            (_DWORD *)a1 + 1432,
            (__int128 *)a2,
            (__int128 *)&pguid,
            &v46,
            v52,
            (__int64 *)&v51);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x55F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v25,
        v38);
    v26 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)(v39 + 32) + 88LL))(v39 + 32, (char *)a1 + 4);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x561,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v26,
        v38);
    v27 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v42 + 328LL))(
            v42,
            (v41 + 32) & -(__int64)(v41 != 0),
            (v39 + 32) & -(__int64)(v39 != 0),
            2);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x564,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v27,
        0);
    v28 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(ScheduledNotification *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v18 + 16LL))(v18);
    v32 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
    if ( v43 )
    {
      v43 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v33)[2])(v33);
    }
    v34 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x568,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
                           v31);
  }
  return result;
}

```

## disassembly

```asm
0x1800708e4  mov     [rsp+arg_10], rbx
0x1800708e9  mov     [rsp+arg_18], rsi
0x1800708ee  push    rdi
0x1800708ef  push    r12
0x1800708f1  push    r13
0x1800708f3  push    r14
0x1800708f5  push    r15
0x1800708f7  sub     rsp, 180h
0x1800708fe  mov     rax, cs:__security_cookie
0x180070905  xor     rax, rsp
0x180070908  mov     [rsp+1A8h+var_38], rax
0x180070910  mov     r12, rdx
0x180070913  mov     rsi, rcx
0x180070916  lea     rcx, [rsp+1A8h+var_108]
0x18007091e  call    ??$Make@VPlatformFactory@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VPlatformFactory@@@12@XZ; Microsoft::WRL::Details::Make<PlatformFactory,>(void)
0x180070923  nop
0x180070924  mov     rcx, [rsp+1A8h]; this
0x18007092c  mov     r14, [rsp+1A8h+var_108]
0x180070934  xor     r13d, r13d
0x180070937  test    r14, r14
0x18007093a  jnz     short loc_180070953
0x18007093c  mov     r9d, 80004003h; char *
0x180070942  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070949  mov     edx, 514h; void *
0x18007094e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070953  mov     [rsp+1A8h+var_128], r13
0x18007095b  mov     [rsp+1A8h+var_130], r13
0x180070960  mov     [rsp+1A8h+var_138], r13
0x180070965  mov     rax, [r14]
0x180070968  mov     rbx, [rax+18h]
0x18007096c  lea     rcx, [rsp+1A8h+var_128]
0x180070974  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070979  lea     r9, [rsp+1A8h+var_128]
0x180070981  lea     r8, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x180070988  xor     edx, edx
0x18007098a  mov     rcx, r14
0x18007098d  mov     rax, rbx
0x180070990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070995  mov     rcx, [rsp+1A8h]; this
0x18007099d  test    eax, eax
0x18007099f  jns     short loc_1800709B5
0x1800709a1  mov     r9d, eax; char *
0x1800709a4  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800709ab  mov     edx, 519h; void *
0x1800709b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800709b5  mov     rdi, [rsp+1A8h+var_128]
0x1800709bd  mov     rax, [rdi]
0x1800709c0  mov     rbx, [rax+18h]
0x1800709c4  lea     rcx, [rsp+1A8h+var_130]
0x1800709c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800709ce  lea     rdx, [rsp+1A8h+var_130]
0x1800709d3  mov     rcx, rdi
0x1800709d6  mov     rax, rbx
0x1800709d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800709de  mov     rcx, [rsp+1A8h]; this
0x1800709e6  test    eax, eax
0x1800709e8  jns     short loc_1800709FF
0x1800709ea  mov     r9d, eax; char *
0x1800709ed  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800709f4  mov     edx, 51Ah; void *
0x1800709f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800709ff  mov     rbx, [rsp+1A8h+var_130]
0x180070a04  mov     rax, [rbx]
0x180070a07  mov     rdi, [rax]
0x180070a0a  lea     rcx, [rsp+1A8h+var_138]
0x180070a0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070a14  lea     r8, [rsp+1A8h+var_138]
0x180070a19  lea     rdx, _GUID_926516e8_d891_45bc_9de5_6959fb8ecac5
0x180070a20  mov     rcx, rbx
0x180070a23  mov     rax, rdi
0x180070a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070a2b  nop
0x180070a2c  mov     rcx, [rsp+1A8h]; this
0x180070a34  test    eax, eax
0x180070a36  jns     short loc_180070A4C
0x180070a38  mov     r9d, eax; char *
0x180070a3b  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070a42  mov     edx, 51Bh; void *
0x180070a47  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070a4c  mov     rax, [rsi+20h]
0x180070a50  mov     rcx, rax
0x180070a53  shr     rcx, 20h
0x180070a57  mov     dword ptr [rsp+1A8h+var_120+4], ecx
0x180070a5e  mov     dword ptr [rsp+1A8h+var_120], eax
0x180070a65  mov     rax, [rsp+1A8h+var_120]
0x180070a6d  mov     qword ptr [rsp+1A8h+var_100], rax
0x180070a75  test    cs:byte_18015DE45, 1
0x180070a7c  jz      short loc_180070A9F
0x180070a7e  lea     r8, [rsi+5Ch]
0x180070a82  lea     rax, [rsp+1A8h+var_100]
0x180070a8a  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x180070a8f  lea     r9, [rsi+4]
0x180070a93  lea     rdx, WPNEND_SCHEDULED_TOAST_TIMER
0x180070a9a  call    McTemplateU0zjm_EventWriteTransfer
0x180070a9f  lea     r10, [rsi+260h]
0x180070aa6  test    r10, r10
0x180070aa9  jz      short loc_180070AEC
0x180070aab  mov     edx, 1400h
0x180070ab0  mov     ecx, edx
0x180070ab2  mov     rax, r10
0x180070ab5  cmp     [rax], r13b
0x180070ab8  jz      short loc_180070AC3
0x180070aba  inc     rax
0x180070abd  sub     rcx, 1
0x180070ac1  jnz     short loc_180070AB5
0x180070ac3  mov     rax, rcx
0x180070ac6  sub     rdx, rcx
0x180070ac9  neg     rax
0x180070acc  sbb     r8, r8
0x180070acf  and     r8, rdx
0x180070ad2  mov     rax, rcx
0x180070ad5  neg     rax
0x180070ad8  sbb     r9d, r9d
0x180070adb  not     r9d
0x180070ade  and     r9d, 80070057h
0x180070ae5  test    rcx, rcx
0x180070ae8  jz      short loc_180070AF2
0x180070aea  jmp     short loc_180070AF5
0x180070aec  mov     r9d, 80070057h; char *
0x180070af2  mov     r8, r13
0x180070af5  mov     rcx, [rsp+1A8h]; this
0x180070afd  test    r9d, r9d
0x180070b00  jns     short loc_180070B14
0x180070b02  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070b09  mov     edx, 529h; void *
0x180070b0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070b14  mov     edx, r8d; cbInit
0x180070b17  mov     rcx, r10; pInit
0x180070b1a  call    cs:__imp_SHCreateMemStream
0x180070b20  mov     rbx, rax
0x180070b23  mov     [rsp+1A8h+var_E8], rax
0x180070b2b  mov     rcx, [rsp+1A8h]; this
0x180070b33  test    rax, rax
0x180070b36  jnz     short loc_180070B4F
0x180070b38  mov     r9d, 8007000Eh; char *
0x180070b3e  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070b45  mov     edx, 52Dh; void *
0x180070b4a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070b4f  mov     qword ptr [rsp+1A8h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180070b57  lea     rcx, [rsp+1A8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180070b5f  call    cs:__imp_GetSystemTimeAsFileTime
0x180070b65  cmp     [rsi+17F0h], r13d
0x180070b6c  jz      short loc_180070B7C
0x180070b6e  mov     ecx, [rsi+17F4h]
0x180070b74  mov     edx, [rsi+17F8h]
0x180070b7a  jmp     short loc_180070B82
0x180070b7c  mov     ecx, r13d
0x180070b7f  mov     edx, r13d
0x180070b82  mov     [rsp+1A8h+var_D8], r13
0x180070b8a  lea     rax, [rsi+5Ch]
0x180070b8e  mov     [rsp+1A8h+var_D0], rax
0x180070b96  lea     rax, aToast_0; "toast"
0x180070b9d  mov     [rsp+1A8h+var_C8], rax
0x180070ba5  lea     rax, aXml; "Xml"
0x180070bac  lea     r8, aAdaptivejson; "AdaptiveJson"
0x180070bb3  cmp     [rsi+17FCh], r13d
0x180070bba  cmovnz  rax, r8
0x180070bbe  mov     [rsp+1A8h+var_C0], rax
0x180070bc6  mov     [rsp+1A8h+var_B8], rbx
0x180070bce  lea     rax, [rsi+16ECh]
0x180070bd5  mov     [rsp+1A8h+var_B0], rax
0x180070bdd  lea     rax, [rsi+176Eh]
0x180070be4  mov     [rsp+1A8h+var_A8], rax
0x180070bec  mov     [rsp+1A8h+var_A0], ecx
0x180070bf3  mov     [rsp+1A8h+var_9C], edx
0x180070bfa  mov     rax, qword ptr [rsp+1A8h+SystemTimeAsFileTime.dwLowDateTime]
0x180070c02  mov     [rsp+1A8h+var_98], rax
0x180070c0a  mov     [rsp+1A8h+var_90], 3
0x180070c16  call    ?GetLastBootTime@@YA_JXZ; GetLastBootTime(void)
0x180070c1b  mov     [rsp+1A8h+var_88], rax
0x180070c23  mov     [rsp+1A8h+var_80], r13b
0x180070c2b  xor     eax, eax
0x180070c2d  mov     [rsp+1A8h+var_7F], eax
0x180070c34  mov     [rsp+1A8h+var_7B], ax
0x180070c3c  mov     [rsp+1A8h+var_79], al
0x180070c43  mov     [rsp+1A8h+var_78], r13
0x180070c4b  xorps   xmm0, xmm0
0x180070c4e  movups  [rsp+1A8h+var_70], xmm0
0x180070c56  mov     [rsp+1A8h+var_60], 1
0x180070c62  mov     [rsp+1A8h+var_58], r13
0x180070c6a  mov     [rsp+1A8h+var_140], r13
0x180070c6f  lea     rcx, [rsp+1A8h+var_140]
0x180070c74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070c79  lea     rdx, [rsp+1A8h+var_D8]
0x180070c81  lea     rcx, [rsp+1A8h+var_140]
0x180070c86  call    ??$MakeAndInitialize@VNotification@@V1@AEAUInitializer@1@@Details@WRL@Microsoft@@YAJPEAPEAVNotification@@AEAUInitializer@3@@Z; Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(Notification * *,Notification::Initializer &)
0x180070c8b  mov     rcx, [rsp+1A8h]; this
0x180070c93  test    eax, eax
0x180070c95  jns     short loc_180070CAB
0x180070c97  mov     r9d, eax; char *
0x180070c9a  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070ca1  mov     edx, 546h; void *
0x180070ca6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070cab  mov     [rsp+1A8h+var_148], r13
0x180070cb0  lea     rcx, [rsp+1A8h+var_148]
0x180070cb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070cba  lea     rax, [rsi+38h]
0x180070cbe  lea     rcx, [rsi+28h]
0x180070cc2  lea     r9, [rsi+30h]
0x180070cc6  mov     [rsp+1A8h+var_180], rax
0x180070ccb  mov     qword ptr [rsp+1A8h+var_188], rcx; int
0x180070cd0  lea     r8, [rsi+20h]
0x180070cd4  lea     rdx, word_180124798
0x180070cdb  lea     rcx, [rsp+1A8h+var_148]
0x180070ce0  call    ??$MakeAndInitialize@VScheduledNotification@@V1@AEAY00$$CBGAEA_JAEAHAEA_JAEAI@Details@WRL@Microsoft@@YAJPEAPEAVScheduledNotification@@AEAY00$$CBGAEA_JAEAH2AEAI@Z; Microsoft::WRL::Details::MakeAndInitialize<ScheduledNotification,ScheduledNotification,ushort const (&)[1],__int64 &,int &,__int64 &,uint &>(ScheduledNotification * *,ushort const (&)[1],__int64 &,int &,__int64 &,uint &)
0x180070ce5  mov     rcx, [rsp+1A8h]; this
0x180070ced  test    eax, eax
0x180070cef  jns     short loc_180070D05
0x180070cf1  mov     r9d, eax; char *
0x180070cf4  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070cfb  mov     edx, 54Fh; void *
0x180070d00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070d05  xorps   xmm0, xmm0
0x180070d08  movups  xmmword ptr [rsp+1A8h+pguid.Data1], xmm0
0x180070d10  lea     rcx, [rsp+1A8h+pguid]; pguid
0x180070d18  call    cs:__imp_CoCreateGuid
0x180070d1e  mov     rcx, [rsp+1A8h]; this
0x180070d26  test    eax, eax
0x180070d28  jns     short loc_180070D3E
0x180070d2a  mov     r9d, eax; char *
0x180070d2d  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070d34  mov     edx, 552h; void *
0x180070d39  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070d3e  mov     [rsp+1A8h+var_150], r13
0x180070d43  mov     rax, [rsp+1A8h+var_148]
0x180070d48  mov     [rsp+1A8h+var_F8], rax
0x180070d50  mov     [rsp+1A8h+var_F0], r13
0x180070d58  mov     [rsp+1A8h+var_118], r13d
0x180070d60  mov     [rsp+1A8h+var_114], r13d
0x180070d68  mov     dword ptr [rsp+1A8h+var_120], r13d
0x180070d70  lea     rcx, [rsp+1A8h+var_150]
0x180070d75  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070d7a  lea     rax, [rsi+1660h]
0x180070d81  lea     rcx, [rsp+1A8h+var_F8]
0x180070d89  mov     [rsp+1A8h+var_160], rcx
0x180070d8e  lea     rcx, [rsp+1A8h+var_F0]
0x180070d96  mov     [rsp+1A8h+var_168], rcx
0x180070d9b  lea     rcx, [rsp+1A8h+var_118]
0x180070da3  mov     [rsp+1A8h+var_170], rcx
0x180070da8  lea     rcx, [rsp+1A8h+pguid]
0x180070db0  mov     [rsp+1A8h+var_178], rcx
0x180070db5  mov     [rsp+1A8h+var_180], r12
0x180070dba  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x180070dbf  lea     r9, [rsp+1A8h+var_114]
0x180070dc7  lea     r8, word_180124798
0x180070dce  lea     rdx, [rsp+1A8h+var_120]
0x180070dd6  lea     rcx, [rsp+1A8h+var_150]
0x180070ddb  call    ??$MakeAndInitialize@VTransientNotificationDetails@@V1@HAEAY00$$CBGHAEAHAEAU_GUID@@AEAU2@W4WpnToastNotificationPriority@@$$TPEAVScheduledNotification@@@Details@WRL@Microsoft@@YAJPEAPEAVTransientNotificationDetails@@$$QEAHAEAY00$$CBG1AEAHAEAU_GUID@@4$$QEAW4WpnToastNotificationPriority@@$$QEA$$T$$QEAPEAVScheduledNotification@@@Z; Microsoft::WRL::Details::MakeAndInitialize<TransientNotificationDetails,TransientNotificationDetails,int,ushort const (&)[1],int,int &,_GUID &,_GUID &,WpnToastNotificationPriority,std::nullptr_t,ScheduledNotification *>(TransientNotificationDetails * *,int &&,ushort const (&)[1],int &&,int &,_GUID &,_GUID &,WpnToastNotificationPriority &&,$$T$$QEAPEAVScheduledNotification &&)
0x180070de0  mov     rcx, [rsp+1A8h]; this
0x180070de8  test    eax, eax
0x180070dea  jns     short loc_180070E00
0x180070dec  mov     r9d, eax; char *
0x180070def  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070df6  mov     edx, 55Fh; void *
0x180070dfb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070e00  mov     rcx, [rsp+1A8h+var_150]
0x180070e05  add     rcx, 20h ; ' '
0x180070e09  mov     rax, [rcx]
0x180070e0c  lea     rdx, [rsi+4]
0x180070e10  mov     rax, [rax+58h]
0x180070e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e19  mov     rcx, [rsp+1A8h]; this
0x180070e21  test    eax, eax
0x180070e23  jns     short loc_180070E39
0x180070e25  mov     r9d, eax; char *
0x180070e28  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070e2f  mov     edx, 561h; void *
0x180070e34  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070e39  mov     [rsp+1A8h+var_158], r13d
0x180070e3e  mov     r11, [rsp+1A8h+var_138]
0x180070e43  mov     rcx, [rsp+1A8h+var_150]
0x180070e48  mov     rdx, [rsp+1A8h+var_140]
0x180070e4d  mov     r10, [r11]
0x180070e50  lea     rax, [rcx+20h]
0x180070e54  neg     rcx
0x180070e57  sbb     r8, r8
0x180070e5a  and     r8, rax
0x180070e5d  lea     rax, [rdx+20h]
0x180070e61  neg     rdx
0x180070e64  sbb     rdx, rdx
0x180070e67  and     rdx, rax
0x180070e6a  lea     rax, [rsp+1A8h+var_158]
0x180070e6f  mov     [rsp+1A8h+var_180], rax
0x180070e74  mov     qword ptr [rsp+1A8h+var_188], r13; int
0x180070e79  mov     r9d, 2
0x180070e7f  mov     rcx, r11
0x180070e82  mov     rax, [r10+148h]
0x180070e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e8e  mov     rcx, [rsp+1A8h]; this
0x180070e96  test    eax, eax
0x180070e98  jns     short loc_180070EAF
0x180070e9a  mov     r9d, eax; char *
0x180070e9d  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070ea4  mov     edx, 564h; void *
0x180070ea9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070eaf  mov     rcx, [rsp+1A8h+var_150]
0x180070eb4  test    rcx, rcx
0x180070eb7  jz      short loc_180070ECB
0x180070eb9  mov     [rsp+1A8h+var_150], r13
0x180070ebe  mov     rax, [rcx]
  ... truncated ...
```
