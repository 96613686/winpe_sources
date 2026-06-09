# ReceiveTextMessageTask::_CreateStoreMessage(ISmMessageSMS * *)

- ea: `0x180008168`
- end: `0x1800088d4`
- name: `?_CreateStoreMessage@ReceiveTextMessageTask@@AEAAJPEAPEAUISmMessageSMS@@@Z`
- size: `1900`
- prototype: `__int64 __fastcall(ReceiveTextMessageTask *__hidden this, struct ISmMessageSMS **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180009120`

## callees

- `0x18000266c`
- `0x1800044dc`
- `0x180008168`
- `0x1800093e4`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800081c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008226`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800081c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008226`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800085f1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800085f1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800086de`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800086de`

## string_xrefs

- `0x1800081d5`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008238`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008286`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x1800082d8`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008347`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x1800083bf`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x18000845a`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x18000853b`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008596`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008638`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x18000882b`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`

## pseudocode

```c
__int64 __fastcall ReceiveTextMessageTask::_CreateStoreMessage(ReceiveTextMessageTask *this, struct ISmMessageSMS **a2)
{
  HRESULT v4; // eax
  signed int v5; // edi
  void (*v6)(void); // rax
  HRESULT v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // ebx
  __int64 v12; // r12
  int v13; // eax
  unsigned int v14; // r14d
  void (*v15)(void); // rax
  int v16; // eax
  int v17; // eax
  void (*v18)(void); // rax
  void (*v19)(void); // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  FILETIME *v22; // rax
  signed int LastError; // eax
  struct ISmMessageSMS *v24; // rcx
  struct ISmMessageSMS *v25; // [rsp+40h] [rbp-39h] BYREF
  LPVOID v26; // [rsp+48h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-29h] BYREF
  __int64 v28; // [rsp+58h] [rbp-21h] BYREF
  __int64 v29; // [rsp+60h] [rbp-19h] BYREF
  void *v30; // [rsp+68h] [rbp-11h] BYREF
  __int16 *v31; // [rsp+70h] [rbp-9h]
  __int16 v32; // [rsp+78h] [rbp-1h] BYREF
  __int64 v33; // [rsp+7Ah] [rbp+1h]
  int v34; // [rsp+82h] [rbp+9h]
  __int16 v35; // [rsp+86h] [rbp+Dh]
  struct _FILETIME v36; // [rsp+88h] [rbp+Fh] BYREF
  FILETIME FileTime; // [rsp+90h] [rbp+17h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+98h] [rbp+1Fh] BYREF

  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7,
         0,
         0x17u,
         &GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c,
         &ppv);
  v5 = v4;
  if ( v4 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v4,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
LABEL_3:
    if ( !ppv )
      return (unsigned int)v5;
    v6 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
LABEL_5:
    v6();
    return (unsigned int)v5;
  }
  v26 = 0;
  v8 = CoCreateInstance(
         &GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a,
         0,
         0x17u,
         &GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6,
         &v26);
  v5 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v8,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
LABEL_9:
    if ( v26 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
    goto LABEL_3;
  }
  v9 = *((_QWORD *)this + 5);
  v10 = *(_DWORD *)(v9 + 136);
  if ( (v10 - 1 <= 8 || v10 >= 0x65) && v10 - 101 > 0x63 )
  {
    v11 = -2147418113;
    Log_HREvent_0(
      2147549183LL,
      0,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
LABEL_98:
    if ( v26 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v11;
  }
  v12 = *(_QWORD *)(v9 + 24);
  v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _QWORD, _DWORD))(*(_QWORD *)v26 + 24LL))(
          v26,
          v12,
          1,
          v10,
          0);
  v14 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v13,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( !v26 )
    {
LABEL_19:
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v14;
    }
    v15 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
LABEL_18:
    v15();
    goto LABEL_19;
  }
  v28 = 0;
  v16 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64 *))(*(_QWORD *)ppv + 48LL))(ppv, v26, &v28);
  v14 = v16;
  if ( v16 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v16,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( !v26 )
      goto LABEL_19;
    v15 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
    goto LABEL_18;
  }
  v29 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, LPVOID, __int64 *))(*(_QWORD *)v28 + 120LL))(
          v28,
          0,
          1,
          v10,
          v26,
          &v29);
  v5 = v17;
  if ( v17 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v17,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( !v29 )
      goto LABEL_31;
    v18 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
    goto LABEL_30;
  }
  v25 = 0;
  if ( !v29
    || ((**(void (__fastcall ***)(__int64, GUID *, struct ISmMessageSMS **))v29)(
          v29,
          &GUID_0ba6a6c2_14db_456a_a2bf_c4de45d6a8a6,
          &v25),
        !v25) )
  {
    v11 = -2147024809;
    Log_HREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
LABEL_92:
    if ( v25 )
      (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    goto LABEL_98;
  }
  v5 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *, _QWORD))(*(_QWORD *)v25 + 120LL))(
         v25,
         *(_QWORD *)(*((_QWORD *)this + 5) + 56LL));
  if ( v5 < 0
    || (v5 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *, __int64))(*(_QWORD *)v25 + 504LL))(v25, v12), v5 < 0)
    || *(_DWORD *)(*((_QWORD *)this + 5) + 132LL)
    && (v5 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v25 + 472LL))(v25), v5 < 0) )
  {
    Log_HREvent_0(
      (unsigned int)v5,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( !v25 )
    {
LABEL_39:
      if ( !v29 )
      {
LABEL_31:
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        goto LABEL_9;
      }
      v18 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
LABEL_30:
      v18();
      goto LABEL_31;
    }
    v19 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
LABEL_38:
    v19();
    goto LABEL_39;
  }
  v20 = *((_QWORD *)this + 5);
  v33 = 0;
  v35 = 0;
  v30 = &v32;
  v31 = &v32;
  v32 = 0;
  v34 = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v30,
                           *(_QWORD *)(v20 + 88)) )
  {
    v21 = 0;
    v11 = -2147024882;
    goto LABEL_46;
  }
  if ( v30 != v31 )
  {
    v5 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v25 + 952LL))(v25);
    if ( v5 < 0 )
      goto LABEL_50;
  }
  v22 = (FILETIME *)*((_QWORD *)this + 5);
  SystemTime = 0;
  FileTime = v22[15];
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent_0((unsigned int)v5, 0, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
    if ( v5 < 0 )
    {
      Log_HREvent_0(
        (unsigned int)v5,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
      if ( v30 != &v32 )
        operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
      if ( v25 )
        (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v26 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
      if ( !ppv )
        return (unsigned int)v5;
      v6 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
      goto LABEL_5;
    }
  }
  v36 = 0;
  SystemTimeToFileTime(&SystemTime, &v36);
  v5 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *, struct _FILETIME))(*(_QWORD *)v25 + 144LL))(v25, v36);
  if ( v5 < 0
    || *(_DWORD *)(*((_QWORD *)this + 5) + 128LL)
    && ((v5 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *, __int64))(*(_QWORD *)v25 + 352LL))(v25, 1), v5 < 0)
     || (v5 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *, __int64))(*(_QWORD *)v25 + 368LL))(v25, 1), v5 < 0)) )
  {
LABEL_50:
    Log_HREvent_0(
      (unsigned int)v5,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v30 != &v32 )
      operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v25 )
      goto LABEL_39;
    v19 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
    goto LABEL_38;
  }
  if ( !a2 )
  {
    v21 = 1;
    v11 = -2147467261;
LABEL_46:
    Log_HREvent_0(
      v11,
      v21,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v30 != &v32 )
      operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_92;
  }
  v24 = v25;
  *a2 = v25;
  if ( v24 )
  {
    (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v24 + 8LL))(v24);
    v24 = v25;
  }
  if ( v30 != &v32 )
  {
    operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
    v24 = v25;
  }
  if ( v24 )
    (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v26 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x180008168  mov     [rsp-8+arg_10], rbx
0x18000816d  mov     [rsp-8+arg_18], rsi
0x180008172  push    rbp
0x180008173  push    rdi
0x180008174  push    r12
0x180008176  push    r14
0x180008178  push    r15
0x18000817a  lea     rbp, [rsp-37h]
0x18000817f  sub     rsp, 0B0h
0x180008186  mov     rax, cs:__security_cookie
0x18000818d  xor     rax, rsp
0x180008190  mov     [rbp+57h+var_28], rax
0x180008194  mov     r15, rdx
0x180008197  mov     [rbp+57h+var_80], 0
0x18000819f  mov     rsi, rcx
0x1800081a2  lea     rax, [rbp+57h+var_80]
0x1800081a6  mov     ebx, 17h
0x1800081ab  mov     [rsp+0D0h+ppv], rax; ppv
0x1800081b0  mov     r8d, ebx; dwClsContext
0x1800081b3  lea     r9, _GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c; riid
0x1800081ba  xor     edx, edx; pUnkOuter
0x1800081bc  lea     rcx, _GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7; rclsid
0x1800081c3  call    cs:__imp_CoCreateInstance
0x1800081c9  mov     edi, eax
0x1800081cb  test    eax, eax
0x1800081cd  jns     short loc_180008202
0x1800081cf  mov     r9d, 0A3h
0x1800081d5  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800081dc  lea     edx, [rbx-16h]
0x1800081df  mov     ecx, eax
0x1800081e1  call    Log_HREvent_0
0x1800081e6  mov     rcx, [rbp+57h+var_80]
0x1800081ea  test    rcx, rcx
0x1800081ed  jz      short loc_1800081FB
0x1800081ef  mov     rax, [rcx]
0x1800081f2  mov     rax, [rax+10h]
0x1800081f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081fb  mov     eax, edi
0x1800081fd  jmp     loc_1800088AC
0x180008202  lea     rax, [rbp+57h+var_88]
0x180008206  mov     [rbp+57h+var_88], 0
0x18000820e  lea     r9, _GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6; riid
0x180008215  mov     [rsp+0D0h+ppv], rax; ppv
0x18000821a  mov     r8d, ebx; dwClsContext
0x18000821d  lea     rcx, _GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a; rclsid
0x180008224  xor     edx, edx; pUnkOuter
0x180008226  call    cs:__imp_CoCreateInstance
0x18000822c  mov     edi, eax
0x18000822e  test    eax, eax
0x180008230  jns     short loc_180008262
0x180008232  mov     r9d, 0A6h
0x180008238  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000823f  mov     edx, 1
0x180008244  mov     ecx, eax
0x180008246  call    Log_HREvent_0
0x18000824b  mov     rcx, [rbp+57h+var_88]
0x18000824f  test    rcx, rcx
0x180008252  jz      short loc_1800081E6
0x180008254  mov     rax, [rcx]
0x180008257  mov     rax, [rax+10h]
0x18000825b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008260  jmp     short loc_1800081E6
0x180008262  mov     rcx, [rsi+28h]
0x180008266  mov     edi, [rcx+88h]
0x18000826c  lea     eax, [rdi-1]
0x18000826f  cmp     eax, 8
0x180008272  jbe     short loc_180008279
0x180008274  cmp     edi, 65h ; 'e'
0x180008277  jb      short loc_1800082A1
0x180008279  lea     eax, [rdi-65h]
0x18000827c  cmp     eax, 63h ; 'c'
0x18000827f  jbe     short loc_1800082A1
0x180008281  mov     ebx, 8000FFFFh
0x180008286  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000828d  mov     ecx, ebx
0x18000828f  mov     r9d, 0A9h
0x180008295  xor     edx, edx
0x180008297  call    Log_HREvent_0
0x18000829c  jmp     loc_180008880
0x1800082a1  mov     r12, [rcx+18h]
0x1800082a5  mov     ebx, 1
0x1800082aa  mov     rcx, [rbp+57h+var_88]
0x1800082ae  mov     r9d, edi
0x1800082b1  mov     r8d, ebx
0x1800082b4  mov     dword ptr [rsp+0D0h+ppv], 0
0x1800082bc  mov     rdx, r12
0x1800082bf  mov     rax, [rcx]
0x1800082c2  mov     rax, [rax+18h]
0x1800082c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082cb  mov     r14d, eax
0x1800082ce  test    eax, eax
0x1800082d0  jns     short loc_18000831A
0x1800082d2  mov     r9d, 0ACh
0x1800082d8  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800082df  mov     edx, ebx
0x1800082e1  mov     ecx, eax
0x1800082e3  call    Log_HREvent_0
0x1800082e8  mov     rcx, [rbp+57h+var_88]
0x1800082ec  test    rcx, rcx
0x1800082ef  jz      short loc_1800082FD
0x1800082f1  mov     rdx, [rcx]
0x1800082f4  mov     rax, [rdx+10h]
0x1800082f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082fd  mov     rcx, [rbp+57h+var_80]
0x180008301  test    rcx, rcx
0x180008304  jz      short loc_180008312
0x180008306  mov     rax, [rcx]
0x180008309  mov     rax, [rax+10h]
0x18000830d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008312  mov     eax, r14d
0x180008315  jmp     loc_1800088AC
0x18000831a  mov     rcx, [rbp+57h+var_80]
0x18000831e  lea     r8, [rbp+57h+var_78]
0x180008322  mov     rdx, [rbp+57h+var_88]
0x180008326  mov     [rbp+57h+var_78], 0
0x18000832e  mov     rax, [rcx]
0x180008331  mov     rax, [rax+30h]
0x180008335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000833a  mov     r14d, eax
0x18000833d  test    eax, eax
0x18000833f  jns     short loc_180008381
0x180008341  mov     r9d, 0AFh
0x180008347  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000834e  mov     edx, ebx
0x180008350  mov     ecx, eax
0x180008352  call    Log_HREvent_0
0x180008357  mov     rcx, [rbp+57h+var_78]
0x18000835b  test    rcx, rcx
0x18000835e  jz      short loc_18000836C
0x180008360  mov     rdx, [rcx]
0x180008363  mov     rax, [rdx+10h]
0x180008367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000836c  mov     rcx, [rbp+57h+var_88]
0x180008370  test    rcx, rcx
0x180008373  jz      short loc_1800082FD
0x180008375  mov     rax, [rcx]
0x180008378  mov     rax, [rax+10h]
0x18000837c  jmp     loc_1800082F8
0x180008381  mov     rdx, [rbp+57h+var_88]
0x180008385  lea     r8, [rbp+57h+var_70]
0x180008389  mov     rcx, [rbp+57h+var_78]
0x18000838d  mov     r9d, edi
0x180008390  mov     [rsp+0D0h+var_A8], r8
0x180008395  mov     r8d, ebx
0x180008398  mov     [rbp+57h+var_70], 0
0x1800083a0  mov     [rsp+0D0h+ppv], rdx
0x1800083a5  xor     edx, edx
0x1800083a7  mov     rax, [rcx]
0x1800083aa  mov     rax, [rax+78h]
0x1800083ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083b3  mov     edi, eax
0x1800083b5  test    eax, eax
0x1800083b7  jns     short loc_180008402
0x1800083b9  mov     r9d, 0B2h
0x1800083bf  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800083c6  mov     edx, ebx
0x1800083c8  mov     ecx, eax
0x1800083ca  call    Log_HREvent_0
0x1800083cf  mov     rcx, [rbp+57h+var_70]
0x1800083d3  test    rcx, rcx
0x1800083d6  jz      short loc_1800083E4
0x1800083d8  mov     rdx, [rcx]
0x1800083db  mov     rax, [rdx+10h]
0x1800083df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083e4  mov     rcx, [rbp+57h+var_78]
0x1800083e8  test    rcx, rcx
0x1800083eb  jz      loc_18000824B
0x1800083f1  mov     rax, [rcx]
0x1800083f4  mov     rax, [rax+10h]
0x1800083f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083fd  jmp     loc_18000824B
0x180008402  mov     rcx, [rbp+57h+var_70]
0x180008406  mov     [rbp+57h+var_90], 0
0x18000840e  test    rcx, rcx
0x180008411  jz      loc_180008826
0x180008417  mov     rax, [rcx]
0x18000841a  lea     r8, [rbp+57h+var_90]
0x18000841e  lea     rdx, _GUID_0ba6a6c2_14db_456a_a2bf_c4de45d6a8a6
0x180008425  mov     rax, [rax]
0x180008428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842d  mov     rcx, [rbp+57h+var_90]
0x180008431  test    rcx, rcx
0x180008434  jz      loc_180008826
0x18000843a  mov     rax, [rcx]
0x18000843d  mov     rdx, [rsi+28h]
0x180008441  mov     rax, [rax+78h]
0x180008445  mov     rdx, [rdx+38h]
0x180008449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000844e  mov     edi, eax
0x180008450  test    eax, eax
0x180008452  jns     short loc_180008498
0x180008454  mov     r9d, 0B8h
0x18000845a  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008461  mov     edx, ebx
0x180008463  mov     ecx, edi
0x180008465  call    Log_HREvent_0
0x18000846a  mov     rcx, [rbp+57h+var_90]
0x18000846e  test    rcx, rcx
0x180008471  jz      short loc_18000847F
0x180008473  mov     rdx, [rcx]
0x180008476  mov     rax, [rdx+10h]
0x18000847a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000847f  mov     rcx, [rbp+57h+var_70]
0x180008483  test    rcx, rcx
0x180008486  jz      loc_1800083E4
0x18000848c  mov     rax, [rcx]
0x18000848f  mov     rax, [rax+10h]
0x180008493  jmp     loc_1800083DF
0x180008498  mov     rcx, [rbp+57h+var_90]
0x18000849c  mov     rdx, r12
0x18000849f  mov     rax, [rcx]
0x1800084a2  mov     rax, [rax+1F8h]
0x1800084a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ae  mov     edi, eax
0x1800084b0  test    eax, eax
0x1800084b2  jns     short loc_1800084BC
0x1800084b4  mov     r9d, 0BAh
0x1800084ba  jmp     short loc_18000845A
0x1800084bc  mov     rax, [rsi+28h]
0x1800084c0  mov     edx, [rax+84h]
0x1800084c6  test    edx, edx
0x1800084c8  jz      short loc_1800084EE
0x1800084ca  mov     rcx, [rbp+57h+var_90]
0x1800084ce  mov     rax, [rcx]
0x1800084d1  mov     rax, [rax+1D8h]
0x1800084d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084dd  mov     edi, eax
0x1800084df  test    eax, eax
0x1800084e1  jns     short loc_1800084EE
0x1800084e3  mov     r9d, 0BFh
0x1800084e9  jmp     loc_18000845A
0x1800084ee  mov     rdx, [rsi+28h]
0x1800084f2  lea     rcx, [rbp+57h+var_68]
0x1800084f6  xor     eax, eax
0x1800084f8  mov     [rbp+57h+var_56], 0
0x180008500  mov     [rbp+57h+var_4A], ax
0x180008504  lea     rax, [rbp+57h+var_58]
0x180008508  mov     [rbp+57h+var_68], rax
0x18000850c  lea     rax, [rbp+57h+var_58]
0x180008510  mov     [rbp+57h+var_60], rax
0x180008514  xor     eax, eax
0x180008516  mov     [rbp+57h+var_58], ax
0x18000851a  mov     [rbp+57h+var_4E], 0
0x180008521  mov     rdx, [rdx+58h]
0x180008525  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000852a  test    al, al
0x18000852c  jnz     short loc_18000856B
0x18000852e  mov     r9d, 0C3h
0x180008534  xor     edx, edx
0x180008536  mov     ebx, 8007000Eh
0x18000853b  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008542  mov     ecx, ebx
0x180008544  call    Log_HREvent_0
0x180008549  mov     rcx, [rbp+57h+var_68]; void *
0x18000854d  lea     rax, [rbp+57h+var_58]
0x180008551  cmp     rcx, rax
0x180008554  jz      loc_180008841
0x18000855a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008561  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008566  jmp     loc_180008841
0x18000856b  mov     rdx, [rbp+57h+var_68]
0x18000856f  cmp     rdx, [rbp+57h+var_60]
0x180008573  jz      short loc_1800085D6
0x180008575  mov     rcx, [rbp+57h+var_90]
0x180008579  mov     rax, [rcx]
0x18000857c  mov     rax, [rax+3B8h]
0x180008583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008588  mov     edi, eax
0x18000858a  test    eax, eax
0x18000858c  jns     short loc_1800085D6
0x18000858e  mov     r9d, 0C6h
0x180008594  mov     edx, ebx
0x180008596  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000859d  mov     ecx, edi
0x18000859f  call    Log_HREvent_0
0x1800085a4  mov     rcx, [rbp+57h+var_68]; void *
0x1800085a8  lea     rax, [rbp+57h+var_58]
0x1800085ac  cmp     rcx, rax
0x1800085af  jz      short loc_1800085BD
0x1800085b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800085b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800085bd  mov     rcx, [rbp+57h+var_90]
0x1800085c1  test    rcx, rcx
0x1800085c4  jz      loc_18000847F
0x1800085ca  mov     rax, [rcx]
0x1800085cd  mov     rax, [rax+10h]
0x1800085d1  jmp     loc_18000847A
0x1800085d6  mov     rax, [rsi+28h]
0x1800085da  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800085de  xorps   xmm0, xmm0
0x1800085e1  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800085e5  mov     rcx, [rax+78h]
0x1800085e9  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rcx
0x1800085ed  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x1800085f1  call    cs:__imp_FileTimeToSystemTime
0x1800085f7  test    eax, eax
0x1800085f9  jnz     loc_1800086CE
0x1800085ff  call    cs:__imp_GetLastError
0x180008605  mov     edi, eax
0x180008607  test    eax, eax
  ... truncated ...
```
