# TransientNotificationDetails::RuntimeClassInitialize(ITransientNotificationDetails *)

- ea: `0x180019f04`
- end: `0x18001a3c0`
- name: `?RuntimeClassInitialize@TransientNotificationDetails@@QEAAJPEAUITransientNotificationDetails@@@Z`
- size: `1212`
- prototype: `__int64 __fastcall(TransientNotificationDetails *__hidden this, struct ITransientNotificationDetails *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019e3c`

## callees

- `0x180004e38`
- `0x18000e090`
- `0x180011618`
- `0x180019f04`
- `0x18001a3c8`
- `0x18001a564`
- `0x18001bf30`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a20b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a20b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TransientNotificationDetails::RuntimeClassInitialize(
        TransientNotificationDetails *this,
        struct ITransientNotificationDetails *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(struct ITransientNotificationDetails *, LPVOID *); // rbx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct ITransientNotificationDetails *, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // [rsp+20h] [rbp-99h]
  int v27; // [rsp+20h] [rbp-99h]
  __int64 v28; // [rsp+50h] [rbp-69h] BYREF
  LPVOID v29; // [rsp+58h] [rbp-61h] BYREF
  int v30; // [rsp+60h] [rbp-59h] BYREF
  int v31; // [rsp+64h] [rbp-55h] BYREF
  unsigned int v32; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v33; // [rsp+6Ch] [rbp-4Dh] BYREF
  LPVOID pv; // [rsp+70h] [rbp-49h] BYREF
  __int64 v35; // [rsp+78h] [rbp-41h]
  __int64 v36; // [rsp+80h] [rbp-39h]
  __int128 v37; // [rsp+90h] [rbp-29h] BYREF
  char v38; // [rsp+A0h] [rbp-19h]
  __int128 v39; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v40; // [rsp+C0h] [rbp+7h] BYREF
  __int128 v41; // [rsp+D0h] [rbp+17h] BYREF
  __int128 v42; // [rsp+E0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v33 = 0;
  pv = 0;
  v35 = 0;
  v36 = 0;
  v32 = 0;
  v31 = 0;
  v41 = 0;
  v40 = 0;
  v42 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v4 = (*(__int64 (__fastcall **)(struct ITransientNotificationDetails *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
         a2,
         &v33);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
      (const char *)(unsigned int)v4,
      v26);
    goto LABEL_29;
  }
  v6 = *(__int64 (__fastcall **)(struct ITransientNotificationDetails *, LPVOID *))(*(_QWORD *)a2 + 32LL);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v35 = -1;
  v36 = -1;
  v7 = v6(a2, &pv);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
      (const char *)(unsigned int)v7,
      v26);
    goto LABEL_29;
  }
  v8 = (*(__int64 (__fastcall **)(struct ITransientNotificationDetails *, unsigned int *))(*(_QWORD *)a2 + 40LL))(
         a2,
         &v32);
  v5 = v8;
  if ( v8 < 0 )
  {
    v24 = (unsigned int)v8;
    v25 = 707;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
      (const char *)v24,
      v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v29);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    return v5;
  }
  v9 = (*(__int64 (__fastcall **)(struct ITransientNotificationDetails *, int *))(*(_QWORD *)a2 + 48LL))(a2, &v31);
  v5 = v9;
  if ( v9 < 0 )
  {
    v24 = (unsigned int)v9;
    v25 = 708;
    goto LABEL_46;
  }
  v10 = (*(__int64 (__fastcall **)(struct ITransientNotificationDetails *, __int128 *))(*(_QWORD *)a2 + 56LL))(a2, &v41);
  v5 = v10;
  if ( v10 < 0 )
  {
    v24 = (unsigned int)v10;
    v25 = 709;
    goto LABEL_46;
  }
  v11 = (*(__int64 (__fastcall **)(struct ITransientNotificationDetails *, __int128 *))(*(_QWORD *)a2 + 72LL))(a2, &v40);
  v5 = v11;
  if ( v11 < 0 )
  {
    v24 = (unsigned int)v11;
    v25 = 710;
    goto LABEL_46;
  }
  v12 = (*(__int64 (__fastcall **)(struct ITransientNotificationDetails *, __int128 *))(*(_QWORD *)a2 + 80LL))(a2, &v42);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
      (const char *)(unsigned int)v12,
      v26);
LABEL_29:
    if ( v29 )
      CoTaskMemFree(v29);
    if ( pv )
      CoTaskMemFree(pv);
    return v5;
  }
  v13 = (*(__int64 (__fastcall **)(struct ITransientNotificationDetails *, int *))(*(_QWORD *)a2 + 96LL))(a2, &v30);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
      (const char *)(unsigned int)v13,
      v26);
    goto LABEL_29;
  }
  v14 = *(_QWORD *)a2;
  *(_QWORD *)&v37 = &v29;
  *((_QWORD *)&v37 + 1) = 0;
  v38 = 1;
  v5 = (*(__int64 (__fastcall **)(struct ITransientNotificationDetails *, char *))(v14 + 104))(a2, (char *)&v37 + 8);
  if ( v38 )
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      v37,
      *((_QWORD *)&v37 + 1));
  if ( (v5 & 0x80000000) != 0 )
  {
    v24 = v5;
    v25 = 713;
    goto LABEL_46;
  }
  v15 = *(__int64 (__fastcall **)(struct ITransientNotificationDetails *, __int64 *))(*(_QWORD *)a2 + 112LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v16 = v15(a2, &v28);
  v5 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
      (const char *)(unsigned int)v16,
      v26);
    v23 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_29;
  }
  v39 = v40;
  v37 = v41;
  v17 = TransientNotificationDetails::RuntimeClassInitialize(this, v33, pv, v32, v31, &v37, &v39, v30, v29, v28, v28);
  v5 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
      (const char *)(unsigned int)v17,
      v27);
    v22 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    goto LABEL_29;
  }
  v18 = (*(__int64 (__fastcall **)(char *, __int128 *))(*((_QWORD *)this + 4) + 88LL))((char *)this + 32, &v42);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
      (const char *)(unsigned int)v18,
      v27);
    v21 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_29;
  }
  v19 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( v29 )
    CoTaskMemFree(v29);
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180019f04  mov     [rsp-8+arg_10], rbx
0x180019f09  mov     [rsp-8+arg_18], rsi
0x180019f0e  push    rbp
0x180019f0f  push    rdi
0x180019f10  push    r14
0x180019f12  lea     rbp, [rsp-47h]
0x180019f17  sub     rsp, 100h
0x180019f1e  mov     rax, cs:__security_cookie
0x180019f25  xor     rax, rsp
0x180019f28  mov     [rbp+57h+var_20], rax
0x180019f2c  mov     rdi, rdx
0x180019f2f  mov     rsi, rcx
0x180019f32  xor     r14d, r14d
0x180019f35  mov     [rbp+57h+var_A4], r14d
0x180019f39  mov     [rbp+57h+pv], r14
0x180019f3d  mov     [rbp+57h+var_98], r14
0x180019f41  mov     [rbp+57h+var_90], r14
0x180019f45  mov     [rbp+57h+var_A8], r14d
0x180019f49  mov     [rbp+57h+var_AC], r14d
0x180019f4d  xorps   xmm0, xmm0
0x180019f50  movups  [rbp+57h+var_40], xmm0
0x180019f54  xorps   xmm1, xmm1
0x180019f57  movups  [rbp+57h+var_50], xmm1
0x180019f5b  movups  [rbp+57h+var_30], xmm0
0x180019f5f  mov     [rbp+57h+var_B0], r14d
0x180019f63  mov     [rbp+57h+var_B8], r14
0x180019f67  mov     [rbp+57h+var_C0], r14
0x180019f6b  mov     rax, [rdx]
0x180019f6e  lea     rdx, [rbp+57h+var_A4]
0x180019f72  mov     rcx, rdi
0x180019f75  mov     rax, [rax+18h]
0x180019f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f7e  mov     ebx, eax
0x180019f80  test    eax, eax
0x180019f82  js      loc_18001A2B5
0x180019f88  mov     rax, [rdi]
0x180019f8b  mov     rbx, [rax+20h]
0x180019f8f  mov     rcx, [rbp+57h+pv]; pv
0x180019f93  test    rcx, rcx
0x180019f96  jz      short loc_180019FA2
0x180019f98  call    cs:__imp_CoTaskMemFree
0x180019f9e  mov     [rbp+57h+pv], r14
0x180019fa2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019fa6  mov     [rbp+57h+var_98], rax
0x180019faa  mov     [rbp+57h+var_90], rax
0x180019fae  lea     rdx, [rbp+57h+pv]
0x180019fb2  mov     rcx, rdi
0x180019fb5  mov     rax, rbx
0x180019fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fbd  mov     ebx, eax
0x180019fbf  test    eax, eax
0x180019fc1  js      loc_18001A325
0x180019fc7  mov     rax, [rdi]
0x180019fca  lea     rdx, [rbp+57h+var_A8]
0x180019fce  mov     rcx, rdi
0x180019fd1  mov     rax, [rax+28h]
0x180019fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fda  mov     ebx, eax
0x180019fdc  test    eax, eax
0x180019fde  js      loc_18001A35D
0x180019fe4  mov     rax, [rdi]
0x180019fe7  lea     rdx, [rbp+57h+var_AC]
0x180019feb  mov     rcx, rdi
0x180019fee  mov     rax, [rax+30h]
0x180019ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ff7  mov     ebx, eax
0x180019ff9  test    eax, eax
0x180019ffb  js      loc_18001A367
0x18001a001  mov     rax, [rdi]
0x18001a004  lea     rdx, [rbp+57h+var_40]
0x18001a008  mov     rcx, rdi
0x18001a00b  mov     rax, [rax+38h]
0x18001a00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a014  mov     ebx, eax
0x18001a016  test    eax, eax
0x18001a018  js      loc_18001A371
0x18001a01e  mov     rax, [rdi]
0x18001a021  lea     rdx, [rbp+57h+var_50]
0x18001a025  mov     rcx, rdi
0x18001a028  mov     rax, [rax+48h]
0x18001a02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a031  mov     ebx, eax
0x18001a033  test    eax, eax
0x18001a035  js      loc_18001A37B
0x18001a03b  mov     rax, [rdi]
0x18001a03e  lea     rdx, [rbp+57h+var_30]
0x18001a042  mov     rcx, rdi
0x18001a045  mov     rax, [rax+50h]
0x18001a049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a04e  mov     ebx, eax
0x18001a050  test    eax, eax
0x18001a052  js      loc_18001A27D
0x18001a058  mov     rax, [rdi]
0x18001a05b  lea     rdx, [rbp+57h+var_B0]
0x18001a05f  mov     rcx, rdi
0x18001a062  mov     rax, [rax+60h]
0x18001a066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a06b  mov     ebx, eax
0x18001a06d  test    eax, eax
0x18001a06f  js      loc_18001A2ED
0x18001a075  mov     rax, [rdi]
0x18001a078  lea     rcx, [rbp+57h+var_B8]
0x18001a07c  mov     qword ptr [rbp+57h+var_80], rcx
0x18001a080  mov     qword ptr [rbp+57h+var_80+8], r14
0x18001a084  mov     [rbp+57h+var_70], 1
0x18001a088  lea     rdx, [rbp+57h+var_80+8]
0x18001a08c  mov     rcx, rdi
0x18001a08f  mov     rax, [rax+68h]
0x18001a093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a098  mov     ebx, eax
0x18001a09a  cmp     [rbp+57h+var_70], r14b
0x18001a09e  jz      short loc_18001A0AD
0x18001a0a0  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x18001a0a4  mov     rcx, qword ptr [rbp+57h+var_80]
0x18001a0a8  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x18001a0ad  test    ebx, ebx
0x18001a0af  js      loc_18001A385
0x18001a0b5  mov     rax, [rdi]
0x18001a0b8  mov     rbx, [rax+70h]
0x18001a0bc  lea     rcx, [rbp+57h+var_C0]
0x18001a0c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a0c5  lea     rdx, [rbp+57h+var_C0]
0x18001a0c9  mov     rcx, rdi
0x18001a0cc  mov     rax, rbx
0x18001a0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0d4  mov     ebx, eax
0x18001a0d6  test    eax, eax
0x18001a0d8  js      loc_18001A248
0x18001a0de  mov     rax, [rbp+57h+var_C0]
0x18001a0e2  mov     rcx, [rbp+57h+var_B8]
0x18001a0e6  mov     r10d, [rbp+57h+var_B0]
0x18001a0ea  mov     r11d, [rbp+57h+var_AC]
0x18001a0ee  movaps  xmm0, [rbp+57h+var_50]
0x18001a0f2  movdqa  [rbp+57h+var_60], xmm0
0x18001a0f7  movaps  xmm1, [rbp+57h+var_40]
0x18001a0fb  movdqa  [rbp+57h+var_80], xmm1
0x18001a100  mov     [rsp+110h+var_C8], rax
0x18001a105  mov     [rsp+110h+var_D0], rcx
0x18001a10a  mov     [rsp+110h+var_D8], r10d
0x18001a10f  lea     rax, [rbp+57h+var_60]
0x18001a113  mov     [rsp+110h+var_E0], rax
0x18001a118  lea     rax, [rbp+57h+var_80]
0x18001a11c  mov     [rsp+110h+var_E8], rax
0x18001a121  mov     [rsp+110h+var_F0], r11d; int
0x18001a126  mov     r9d, [rbp+57h+var_A8]
0x18001a12a  mov     r8, [rbp+57h+pv]
0x18001a12e  mov     edx, [rbp+57h+var_A4]
0x18001a131  mov     rcx, rsi
0x18001a134  call    ?RuntimeClassInitialize@TransientNotificationDetails@@QEAAJKPEBGHHU_GUID@@1W4WpnToastNotificationPriority@@PEBDPEAUIScheduledNotification@@@Z; TransientNotificationDetails::RuntimeClassInitialize(ulong,ushort const *,int,int,_GUID,_GUID,WpnToastNotificationPriority,char const *,IScheduledNotification *)
0x18001a139  mov     ebx, eax
0x18001a13b  test    eax, eax
0x18001a13d  js      loc_18001A213
0x18001a143  lea     rcx, [rsi+20h]
0x18001a147  mov     rax, [rcx]
0x18001a14a  lea     rdx, [rbp+57h+var_30]
0x18001a14e  mov     rax, [rax+58h]
0x18001a152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a157  mov     ebx, eax
0x18001a159  test    eax, eax
0x18001a15b  js      short loc_18001A1CF
0x18001a15d  mov     rcx, [rbp+57h+var_C0]
0x18001a161  test    rcx, rcx
0x18001a164  jz      short loc_18001A177
0x18001a166  mov     [rbp+57h+var_C0], r14
0x18001a16a  mov     rax, [rcx]
0x18001a16d  mov     rax, [rax+10h]
0x18001a171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a176  nop
0x18001a177  mov     rcx, [rbp+57h+var_B8]; pv
0x18001a17b  test    rcx, rcx
0x18001a17e  jz      short loc_18001A187
0x18001a180  call    cs:__imp_CoTaskMemFree
0x18001a186  nop
0x18001a187  mov     rcx, [rbp+57h+pv]; pv
0x18001a18b  test    rcx, rcx
0x18001a18e  jz      short loc_18001A196
0x18001a190  call    cs:__imp_CoTaskMemFree
0x18001a196  xor     eax, eax
0x18001a198  jmp     short loc_18001A1AB
0x18001a19a  mov     rcx, [rbp+57h+pv]; pv
0x18001a19e  test    rcx, rcx
0x18001a1a1  jz      short loc_18001A1A9
0x18001a1a3  call    cs:__imp_CoTaskMemFree
0x18001a1a9  mov     eax, ebx
0x18001a1ab  mov     rcx, [rbp+57h+var_20]
0x18001a1af  xor     rcx, rsp; StackCookie
0x18001a1b2  call    __security_check_cookie
0x18001a1b7  lea     r11, [rsp+110h+var_10]
0x18001a1bf  mov     rbx, [r11+30h]
0x18001a1c3  mov     rsi, [r11+38h]
0x18001a1c7  mov     rsp, r11
0x18001a1ca  pop     r14
0x18001a1cc  pop     rdi
0x18001a1cd  pop     rbp
0x18001a1ce  retn
0x18001a1cf  mov     rcx, [rbp+5Fh]; this
0x18001a1d3  mov     r9d, ebx; char *
0x18001a1d6  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a1dd  mov     edx, 2D5h; void *
0x18001a1e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a1e7  nop
0x18001a1e8  mov     rcx, [rbp+57h+var_C0]
0x18001a1ec  test    rcx, rcx
0x18001a1ef  jz      short loc_18001A202
0x18001a1f1  mov     [rbp+57h+var_C0], r14
0x18001a1f5  mov     rax, [rcx]
0x18001a1f8  mov     rax, [rax+10h]
0x18001a1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a201  nop
0x18001a202  mov     rcx, [rbp+57h+var_B8]; pv
0x18001a206  test    rcx, rcx
0x18001a209  jz      short loc_18001A19A
0x18001a20b  call    cs:__imp_CoTaskMemFree
0x18001a211  jmp     short loc_18001A19A
0x18001a213  mov     rcx, [rbp+5Fh]; this
0x18001a217  mov     r9d, ebx; char *
0x18001a21a  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a221  mov     edx, 2D4h; void *
0x18001a226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a22b  nop
0x18001a22c  mov     rcx, [rbp+57h+var_C0]
0x18001a230  test    rcx, rcx
0x18001a233  jz      short loc_18001A246
0x18001a235  mov     [rbp+57h+var_C0], r14
0x18001a239  mov     rax, [rcx]
0x18001a23c  mov     rax, [rax+10h]
0x18001a240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a245  nop
0x18001a246  jmp     short loc_18001A202
0x18001a248  mov     rcx, [rbp+5Fh]; this
0x18001a24c  mov     r9d, ebx; char *
0x18001a24f  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a256  mov     edx, 2CAh; void *
0x18001a25b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a260  nop
0x18001a261  mov     rcx, [rbp+57h+var_C0]
0x18001a265  test    rcx, rcx
0x18001a268  jz      short loc_18001A27B
0x18001a26a  mov     [rbp+57h+var_C0], r14
0x18001a26e  mov     rax, [rcx]
0x18001a271  mov     rax, [rax+10h]
0x18001a275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a27a  nop
0x18001a27b  jmp     short loc_18001A202
0x18001a27d  mov     rcx, [rbp+5Fh]; this
0x18001a281  mov     r9d, ebx; char *
0x18001a284  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a28b  mov     edx, 2C7h; void *
0x18001a290  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a295  nop
0x18001a296  mov     rcx, [rbp+57h+var_C0]
0x18001a29a  test    rcx, rcx
0x18001a29d  jz      short loc_18001A2B0
0x18001a29f  mov     [rbp+57h+var_C0], r14
0x18001a2a3  mov     rax, [rcx]
0x18001a2a6  mov     rax, [rax+10h]
0x18001a2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2af  nop
0x18001a2b0  jmp     loc_18001A202
0x18001a2b5  mov     rcx, [rbp+5Fh]; this
0x18001a2b9  mov     r9d, ebx; char *
0x18001a2bc  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a2c3  mov     edx, 2C1h; void *
0x18001a2c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2cd  nop
0x18001a2ce  mov     rcx, [rbp+57h+var_C0]
0x18001a2d2  test    rcx, rcx
0x18001a2d5  jz      short loc_18001A2E8
0x18001a2d7  mov     [rbp+57h+var_C0], r14
0x18001a2db  mov     rax, [rcx]
0x18001a2de  mov     rax, [rax+10h]
0x18001a2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2e7  nop
0x18001a2e8  jmp     loc_18001A202
0x18001a2ed  mov     rcx, [rbp+5Fh]; this
0x18001a2f1  mov     r9d, ebx; char *
0x18001a2f4  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a2fb  mov     edx, 2C8h; void *
0x18001a300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a305  nop
0x18001a306  mov     rcx, [rbp+57h+var_C0]
0x18001a30a  test    rcx, rcx
0x18001a30d  jz      short loc_18001A320
0x18001a30f  mov     [rbp+57h+var_C0], r14
0x18001a313  mov     rax, [rcx]
0x18001a316  mov     rax, [rax+10h]
0x18001a31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a31f  nop
0x18001a320  jmp     loc_18001A202
0x18001a325  mov     rcx, [rbp+5Fh]; this
0x18001a329  mov     r9d, ebx; char *
0x18001a32c  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a333  mov     edx, 2C2h; void *
0x18001a338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a33d  nop
0x18001a33e  mov     rcx, [rbp+57h+var_C0]
0x18001a342  test    rcx, rcx
0x18001a345  jz      short loc_18001A358
0x18001a347  mov     [rbp+57h+var_C0], r14
0x18001a34b  mov     rax, [rcx]
  ... truncated ...
```
