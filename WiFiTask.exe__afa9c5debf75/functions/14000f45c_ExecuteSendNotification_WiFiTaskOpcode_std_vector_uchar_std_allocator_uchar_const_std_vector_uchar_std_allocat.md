# ExecuteSendNotification(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000f45c`
- end: `0x14000fc49`
- name: `?ExecuteSendNotification@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `2029`
- prototype: `__int64 __fastcall(__int64, const WCHAR **, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x1400016a0`
- `0x140002168`
- `0x14000a800`
- `0x14000bf20`
- `0x14000e868`
- `0x14000e908`
- `0x14000f45c`
- `0x140010178`
- `0x140010d80`
- `0x140012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x14000f6fb`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x14000f6fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000f97b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000f97b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000fb03`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000fb03`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f507`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fb51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fb51`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x14000f736`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x14000f736`

## string_xrefs

- `0x14000f8b3`: `<toast launch="%s"><visual><binding template="ToastGeneric">%s<text id="1">%s</text><text id="2">%s</text></binding></visual><actions>%s</actions></toast>`

## pseudocode

```c
__int64 __fastcall ExecuteSendNotification(__int64 a1, const WCHAR **a2, __int64 a3)
{
  const WCHAR *v4; // r13
  __int64 v5; // rbx
  HRESULT v6; // eax
  int v7; // r8d
  int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _DWORD *v11; // rdx
  __int64 v12; // r12
  unsigned __int64 v13; // rcx
  _DWORD *v14; // rax
  unsigned __int64 v15; // rdi
  _DWORD *v16; // rdi
  HANDLE EventW; // r12
  __int64 *v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  int v21; // eax
  DWORD v22; // eax
  char v24[8]; // [rsp+A0h] [rbp-1AD8h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-1AD0h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp-1AC8h] BYREF
  int v27; // [rsp+B8h] [rbp-1AC0h] BYREF
  HANDLE v28; // [rsp+C0h] [rbp-1AB8h] BYREF
  __int64 v29; // [rsp+C8h] [rbp-1AB0h] BYREF
  __int64 v30; // [rsp+D0h] [rbp-1AA8h] BYREF
  __int64 v31; // [rsp+D8h] [rbp-1AA0h] BYREF
  _DWORD *v32; // [rsp+E0h] [rbp-1A98h] BYREF
  int v33; // [rsp+E8h] [rbp-1A90h]
  __int64 v34; // [rsp+F0h] [rbp-1A88h]
  _BYTE v35[12]; // [rsp+F8h] [rbp-1A80h]
  _OWORD v36[2]; // [rsp+108h] [rbp-1A70h] BYREF
  __int16 v37; // [rsp+128h] [rbp-1A50h]
  WCHAR pszOutBuf; // [rsp+130h] [rbp-1A48h] BYREF
  char v39[526]; // [rsp+132h] [rbp-1A46h] BYREF
  unsigned __int16 v40[512]; // [rsp+340h] [rbp-1838h] BYREF
  unsigned __int16 v41[512]; // [rsp+740h] [rbp-1438h] BYREF
  unsigned __int16 v42[2048]; // [rsp+B40h] [rbp-1038h] BYREF

  v4 = *a2;
  ppv = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v5 = 0;
  v34 = 0;
  *(_QWORD *)&v35[4] = 0;
  memset_0(v42, 0, sizeof(v42));
  v27 = 0;
  v28 = 0;
  v6 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &ppv);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_78;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 10;
    goto LABEL_6;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 48LL))(ppv, &v29);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_78;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 11;
    goto LABEL_6;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64))(*(_QWORD *)v29 + 40LL))(
         v29,
         L"Windows.SystemToast.WiFiNetworkManager",
         0x200000,
         1);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_78;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 12;
    goto LABEL_6;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v31);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_78;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 13;
    goto LABEL_6;
  }
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v31)(
         v31,
         &GUID_2a2e31bb_eecc_4c86_9178_5a6dea632d12,
         &v30);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_78;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 14;
    goto LABEL_6;
  }
  *(_DWORD *)v35 = 0;
  memset(v36, 0, sizeof(v36));
  v37 = 0;
  _o__itow_s(*(unsigned int *)v4, v36, 17, 10);
  pszOutBuf = 0;
  memset_0(v39, 0, 0x206u);
  v6 = SHLoadIndirectString(v4 + 1538, &pszOutBuf, 0x104u, 0);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_78;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 15;
    goto LABEL_6;
  }
  memset_0(v41, 0, sizeof(v41));
  v6 = StringCchPrintfW(v41, 0x200u, L"<image src=\"%s\" placement=\"%s\" alt=\"\"/>", &pszOutBuf, L"AppLogoOverride");
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_78;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 16;
    goto LABEL_6;
  }
  memset_0(v40, 0, sizeof(v40));
  if ( v4 != (const WCHAR *)-2052LL )
  {
    if ( v4[1026] )
    {
      v6 = StringCchPrintfW(v40, 0x200u, L"<action content=\"%s\" arguments=\"%s\"/>");
      v8 = v6;
      if ( v6 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_78;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_72;
        v10 = 17;
        goto LABEL_6;
      }
    }
  }
  v6 = StringCchPrintfW(
         v42,
         0x800u,
         L"<toast launch=\"%s\"><visual><binding template=\"ToastGeneric\">%s<text id=\"1\">%s</text><text id=\"2\">%s</te"
          "xt></binding></visual><actions>%s</actions></toast>",
         v36,
         v41,
         v4 + 2,
         v4 + 514,
         v40);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v24[0] = 0;
    v11 = *(_DWORD **)a3;
    v12 = *(_QWORD *)(a3 + 8);
    v13 = v12 - *(_QWORD *)a3;
    if ( v13 <= 8 )
    {
      if ( v13 >= 8 )
        goto LABEL_55;
      if ( *(_QWORD *)(a3 + 16) - (_QWORD)v11 < 8u )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          std::vector<unsigned char>::_Resize_reallocate<unsigned char>(a3, v11, v24);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            LODWORD(v25) = -2147024888;
            v8 = -2147024888;
            v5 = v34;
            EventW = v28;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_14000FB22);
            goto LABEL_68;
          }
        }
LABEL_55:
        v16 = *(_DWORD **)a3;
        v32 = *(_DWORD **)a3;
        EventW = CreateEventW(0, 1, 0, 0);
        v28 = EventW;
        if ( !EventW )
        {
          v8 = -2147024888;
LABEL_68:
          v9 = WPP_GLOBAL_Control;
          goto LABEL_69;
        }
        *v16 = *(_DWORD *)v4;
        v18 = (__int64 *)Microsoft::WRL::Details::Make<ToastFeedback,void * &,SendNotificationOperationResult * &>(
                           &v25,
                           &v28,
                           &v32);
        v19 = *v18;
        *v18 = 0;
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
          v5 = v19;
          v34 = v19;
        }
        v20 = v25;
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v32 = *(_DWORD **)v35;
        v33 = *(_DWORD *)&v35[8];
        v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, int, unsigned __int16 *, _OWORD *, _QWORD, _DWORD **, _DWORD, _DWORD, _QWORD, __int64, _QWORD, _DWORD, int, _QWORD, int *))(*(_QWORD *)v30 + 256LL))(
                v30,
                L"System",
                L"Windows.SystemToast.WiFiNetworkManager",
                0,
                1,
                v42,
                v36,
                0,
                &v32,
                0,
                0,
                0,
                v5,
                0,
                0,
                1,
                0,
                &v27);
        v8 = v21;
        if ( v21 >= 0 )
        {
          v22 = WaitForSingleObject(EventW, 0x7530u);
          v9 = WPP_GLOBAL_Control;
          if ( v22 )
            v8 = -2147023436;
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              &WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids,
              (unsigned int)v21);
            goto LABEL_68;
          }
        }
LABEL_69:
        if ( EventW )
        {
          CloseHandle(EventW);
          goto LABEL_71;
        }
        goto LABEL_72;
      }
      v15 = 8 - v13;
      memset_0(*(void **)(a3 + 8), 0, 8 - v13);
      v14 = (_DWORD *)(v15 + v12);
    }
    else
    {
      v14 = v11 + 2;
    }
    *(_QWORD *)(a3 + 8) = v14;
    goto LABEL_55;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_78;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 18;
LABEL_6:
    WPP_SF_d(v9[2], v10, &WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids, (unsigned int)v6);
LABEL_71:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_72:
  if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 25) >= 4u && (*((_BYTE *)v9 + 28) & 1) != 0 )
    WPP_SF_SD(v9[2], 20, v7, (int)v36, v8);
  if ( v8 >= 0 )
  {
    v8 = 0;
    goto LABEL_80;
  }
LABEL_78:
  if ( (v8 & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)v8;
LABEL_80:
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000f45c  mov     [rsp+arg_0], rbx
0x14000f461  push    rsi
0x14000f462  push    rdi
0x14000f463  push    r12
0x14000f465  push    r13
0x14000f467  push    r14
0x14000f469  mov     eax, 1B50h
0x14000f46e  call    _alloca_probe
0x14000f473  sub     rsp, rax
0x14000f476  mov     rax, cs:__security_cookie
0x14000f47d  xor     rax, rsp
0x14000f480  mov     [rsp+1B78h+var_38], rax
0x14000f488  mov     r14, r8
0x14000f48b  mov     r13, [rdx]
0x14000f48e  xor     esi, esi
0x14000f490  mov     [rsp+1B78h+var_1AC8], rsi
0x14000f498  mov     [rsp+1B78h+var_1AA0], rsi
0x14000f4a0  mov     [rsp+1B78h+var_1AA8], rsi
0x14000f4a8  mov     [rsp+1B78h+var_1AB0], rsi
0x14000f4b0  mov     ebx, esi
0x14000f4b2  mov     [rsp+1B78h+var_1A88], rbx
0x14000f4ba  mov     [rsp+1B78h+var_1A80+4], rsi
0x14000f4c2  xor     edx, edx; Val
0x14000f4c4  mov     r8d, 1000h; Size
0x14000f4ca  lea     rcx, [rsp+1B78h+var_1038]; void *
0x14000f4d2  call    memset_0
0x14000f4d7  mov     [rsp+1B78h+var_1AC0], esi
0x14000f4de  mov     [rsp+1B78h+var_1AB8], rsi
0x14000f4e6  lea     rax, [rsp+1B78h+var_1AC8]
0x14000f4ee  mov     [rsp+1B78h+ppv], rax; ppv
0x14000f4f3  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x14000f4fa  xor     edx, edx; pUnkOuter
0x14000f4fc  lea     r8d, [rsi+4]; dwClsContext
0x14000f500  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x14000f507  call    cs:__imp_CoCreateInstance
0x14000f50d  mov     edi, eax
0x14000f50f  test    eax, eax
0x14000f511  jns     short loc_14000F559
0x14000f513  lea     r14, WPP_GLOBAL_Control
0x14000f51a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f521  cmp     rcx, r14
0x14000f524  jz      loc_14000FB91
0x14000f52a  cmp     byte ptr [rcx+19h], 4
0x14000f52e  jb      loc_14000FB5E
0x14000f534  test    byte ptr [rcx+1Ch], 1
0x14000f538  jz      loc_14000FB5E
0x14000f53e  lea     edx, [rsi+0Ah]
0x14000f541  mov     r9d, eax
0x14000f544  lea     r8, WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids
0x14000f54b  mov     rcx, [rcx+10h]
0x14000f54f  call    WPP_SF_d
0x14000f554  jmp     loc_14000FB57
0x14000f559  mov     rcx, [rsp+1B78h+var_1AC8]
0x14000f561  mov     rax, [rcx]
0x14000f564  lea     rdx, [rsp+1B78h+var_1AB0]
0x14000f56c  mov     rax, [rax+30h]
0x14000f570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f575  mov     edi, eax
0x14000f577  test    eax, eax
0x14000f579  jns     short loc_14000F5AD
0x14000f57b  lea     r14, WPP_GLOBAL_Control
0x14000f582  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f589  cmp     rcx, r14
0x14000f58c  jz      loc_14000FB91
0x14000f592  cmp     byte ptr [rcx+19h], 4
0x14000f596  jb      loc_14000FB5E
0x14000f59c  test    byte ptr [rcx+1Ch], 1
0x14000f5a0  jz      loc_14000FB5E
0x14000f5a6  mov     edx, 0Bh
0x14000f5ab  jmp     short loc_14000F541
0x14000f5ad  mov     rcx, [rsp+1B78h+var_1AB0]
0x14000f5b5  mov     rax, [rcx]
0x14000f5b8  mov     r9d, 1
0x14000f5be  mov     r8d, 200000h
0x14000f5c4  lea     rdx, aWindowsSystemt; "Windows.SystemToast.WiFiNetworkManager"
0x14000f5cb  mov     rax, [rax+28h]
0x14000f5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5d4  mov     edi, eax
0x14000f5d6  test    eax, eax
0x14000f5d8  jns     short loc_14000F60F
0x14000f5da  lea     r14, WPP_GLOBAL_Control
0x14000f5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5e8  cmp     rcx, r14
0x14000f5eb  jz      loc_14000FB91
0x14000f5f1  cmp     byte ptr [rcx+19h], 4
0x14000f5f5  jb      loc_14000FB5E
0x14000f5fb  test    byte ptr [rcx+1Ch], 1
0x14000f5ff  jz      loc_14000FB5E
0x14000f605  mov     edx, 0Ch
0x14000f60a  jmp     loc_14000F541
0x14000f60f  mov     rcx, [rsp+1B78h+var_1AC8]
0x14000f617  mov     rax, [rcx]
0x14000f61a  lea     rdx, [rsp+1B78h+var_1AA0]
0x14000f622  mov     rax, [rax+18h]
0x14000f626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f62b  mov     edi, eax
0x14000f62d  test    eax, eax
0x14000f62f  jns     short loc_14000F666
0x14000f631  lea     r14, WPP_GLOBAL_Control
0x14000f638  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f63f  cmp     rcx, r14
0x14000f642  jz      loc_14000FB91
0x14000f648  cmp     byte ptr [rcx+19h], 4
0x14000f64c  jb      loc_14000FB5E
0x14000f652  test    byte ptr [rcx+1Ch], 1
0x14000f656  jz      loc_14000FB5E
0x14000f65c  mov     edx, 0Dh
0x14000f661  jmp     loc_14000F541
0x14000f666  mov     rcx, [rsp+1B78h+var_1AA0]
0x14000f66e  mov     rax, [rcx]
0x14000f671  lea     r8, [rsp+1B78h+var_1AA8]
0x14000f679  lea     rdx, _GUID_2a2e31bb_eecc_4c86_9178_5a6dea632d12
0x14000f680  mov     rax, [rax]
0x14000f683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f688  mov     edi, eax
0x14000f68a  test    eax, eax
0x14000f68c  jns     short loc_14000F6C3
0x14000f68e  lea     r14, WPP_GLOBAL_Control
0x14000f695  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f69c  cmp     rcx, r14
0x14000f69f  jz      loc_14000FB91
0x14000f6a5  cmp     byte ptr [rcx+19h], 4
0x14000f6a9  jb      loc_14000FB5E
0x14000f6af  test    byte ptr [rcx+1Ch], 1
0x14000f6b3  jz      loc_14000FB5E
0x14000f6b9  mov     edx, 0Eh
0x14000f6be  jmp     loc_14000F541
0x14000f6c3  mov     dword ptr [rsp+1B78h+var_1A80], esi
0x14000f6ca  xorps   xmm0, xmm0
0x14000f6cd  xor     eax, eax
0x14000f6cf  movups  [rsp+1B78h+var_1A70], xmm0
0x14000f6d7  movups  [rsp+1B78h+var_1A60], xmm0
0x14000f6df  mov     [rsp+1B78h+var_1A50], ax
0x14000f6e7  lea     r9d, [rax+0Ah]
0x14000f6eb  lea     r8d, [rax+11h]
0x14000f6ef  lea     rdx, [rsp+1B78h+var_1A70]
0x14000f6f7  mov     ecx, [r13+0]
0x14000f6fb  call    cs:__imp__o__itow_s
0x14000f701  mov     [rsp+1B78h+pszOutBuf], si
0x14000f709  xor     edx, edx; Val
0x14000f70b  mov     r8d, 206h; Size
0x14000f711  lea     rcx, [rsp+1B78h+var_1A46]; void *
0x14000f719  call    memset_0
0x14000f71e  lea     rcx, [r13+0C04h]; pszSource
0x14000f725  xor     r9d, r9d; ppvReserved
0x14000f728  mov     r8d, 104h; cchOutBuf
0x14000f72e  lea     rdx, [rsp+1B78h+pszOutBuf]; pszOutBuf
0x14000f736  call    cs:__imp_SHLoadIndirectString
0x14000f73c  mov     edi, eax
0x14000f73e  test    eax, eax
0x14000f740  jns     short loc_14000F777
0x14000f742  lea     r14, WPP_GLOBAL_Control
0x14000f749  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f750  cmp     rcx, r14
0x14000f753  jz      loc_14000FB91
0x14000f759  cmp     byte ptr [rcx+19h], 4
0x14000f75d  jb      loc_14000FB5E
0x14000f763  test    byte ptr [rcx+1Ch], 1
0x14000f767  jz      loc_14000FB5E
0x14000f76d  mov     edx, 0Fh
0x14000f772  jmp     loc_14000F541
0x14000f777  mov     r12d, 400h
0x14000f77d  mov     r8d, r12d; Size
0x14000f780  xor     edx, edx; Val
0x14000f782  lea     rcx, [rsp+1B78h+var_1438]; void *
0x14000f78a  call    memset_0
0x14000f78f  lea     rax, aApplogooverrid; "AppLogoOverride"
0x14000f796  mov     [rsp+1B78h+ppv], rax
0x14000f79b  lea     r9, [rsp+1B78h+pszOutBuf]
0x14000f7a3  lea     r8, aImageSrcSPlace; "<image src=\"%s\" placement=\"%s\" alt="...
0x14000f7aa  mov     edx, 200h; unsigned __int64
0x14000f7af  lea     rcx, [rsp+1B78h+var_1438]; unsigned __int16 *
0x14000f7b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f7bc  mov     edi, eax
0x14000f7be  test    eax, eax
0x14000f7c0  jns     short loc_14000F7F7
0x14000f7c2  lea     r14, WPP_GLOBAL_Control
0x14000f7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7d0  cmp     rcx, r14
0x14000f7d3  jz      loc_14000FB91
0x14000f7d9  cmp     byte ptr [rcx+19h], 4
0x14000f7dd  jb      loc_14000FB5E
0x14000f7e3  test    byte ptr [rcx+1Ch], 1
0x14000f7e7  jz      loc_14000FB5E
0x14000f7ed  mov     edx, 10h
0x14000f7f2  jmp     loc_14000F541
0x14000f7f7  mov     r8, r12; Size
0x14000f7fa  xor     edx, edx; Val
0x14000f7fc  lea     rcx, [rsp+1B78h+var_1838]; void *
0x14000f804  call    memset_0
0x14000f809  lea     r9, [r13+804h]
0x14000f810  test    r9, r9
0x14000f813  jz      short loc_14000F87C
0x14000f815  cmp     [r9], si
0x14000f819  jz      short loc_14000F87C
0x14000f81b  lea     rax, [rsp+1B78h+var_1A70]
0x14000f823  mov     [rsp+1B78h+ppv], rax
0x14000f828  lea     r8, aActionContentS; "<action content=\"%s\" arguments=\"%s\""...
0x14000f82f  mov     edx, 200h; unsigned __int64
0x14000f834  lea     rcx, [rsp+1B78h+var_1838]; unsigned __int16 *
0x14000f83c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f841  mov     edi, eax
0x14000f843  test    eax, eax
0x14000f845  jns     short loc_14000F87C
0x14000f847  lea     r14, WPP_GLOBAL_Control
0x14000f84e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f855  cmp     rcx, r14
0x14000f858  jz      loc_14000FB91
0x14000f85e  cmp     byte ptr [rcx+19h], 4
0x14000f862  jb      loc_14000FB5E
0x14000f868  test    byte ptr [rcx+1Ch], 1
0x14000f86c  jz      loc_14000FB5E
0x14000f872  mov     edx, 11h
0x14000f877  jmp     loc_14000F541
0x14000f87c  lea     rax, [r13+404h]
0x14000f883  lea     rcx, [r13+4]
0x14000f887  lea     rdx, [rsp+1B78h+var_1838]
0x14000f88f  mov     [rsp+1B78h+var_1B40], rdx
0x14000f894  mov     [rsp+1B78h+var_1B48], rax
0x14000f899  mov     [rsp+1B78h+var_1B50], rcx
0x14000f89e  lea     rax, [rsp+1B78h+var_1438]
0x14000f8a6  mov     [rsp+1B78h+ppv], rax
0x14000f8ab  lea     r9, [rsp+1B78h+var_1A70]
0x14000f8b3  lea     r8, aToastLaunchSVi; "<toast launch=\"%s\"><visual><binding t"...
0x14000f8ba  mov     edx, 800h; unsigned __int64
0x14000f8bf  lea     rcx, [rsp+1B78h+var_1038]; unsigned __int16 *
0x14000f8c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f8cc  mov     edi, eax
0x14000f8ce  test    eax, eax
0x14000f8d0  jns     short loc_14000F907
0x14000f8d2  lea     r14, WPP_GLOBAL_Control
0x14000f8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8e0  cmp     rcx, r14
0x14000f8e3  jz      loc_14000FB91
0x14000f8e9  cmp     byte ptr [rcx+19h], 4
0x14000f8ed  jb      loc_14000FB5E
0x14000f8f3  test    byte ptr [rcx+1Ch], 1
0x14000f8f7  jz      loc_14000FB5E
0x14000f8fd  mov     edx, 12h
0x14000f902  jmp     loc_14000F541
0x14000f907  mov     [rsp+1B78h+var_1AD8], sil
0x14000f90f  mov     rdx, [r14]
0x14000f912  mov     r12, [r14+8]
0x14000f916  mov     rcx, r12
0x14000f919  sub     rcx, rdx
0x14000f91c  mov     edi, 8
0x14000f921  cmp     rcx, rdi
0x14000f924  jbe     short loc_14000F92C
0x14000f926  lea     rax, [rdx+8]
0x14000f92a  jmp     short loc_14000F960
0x14000f92c  jnb     short loc_14000F964
0x14000f92e  mov     rax, [r14+10h]
0x14000f932  sub     rax, rdx
0x14000f935  cmp     rax, rdi
0x14000f938  jnb     short loc_14000F94C
0x14000f93a  lea     r8, [rsp+1B78h+var_1AD8]
0x14000f942  mov     rcx, r14
0x14000f945  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x14000f94a  jmp     short loc_14000F964
0x14000f94c  sub     rdi, rcx
0x14000f94f  mov     r8, rdi; Size
0x14000f952  xor     edx, edx; Val
0x14000f954  mov     rcx, r12; void *
0x14000f957  call    memset_0
0x14000f95c  lea     rax, [rdi+r12]
0x14000f960  mov     [r14+8], rax
0x14000f964  mov     rdi, [r14]
0x14000f967  mov     [rsp+1B78h+var_1A98], rdi
0x14000f96f  xor     r9d, r9d; lpName
0x14000f972  xor     r8d, r8d; bInitialState
0x14000f975  lea     edx, [r9+1]; bManualReset
0x14000f979  xor     ecx, ecx; lpEventAttributes
0x14000f97b  call    cs:__imp_CreateEventW
0x14000f981  mov     r12, rax
0x14000f984  mov     [rsp+1B78h+var_1AB8], rax
0x14000f98c  test    rax, rax
0x14000f98f  jnz     short loc_14000F99B
0x14000f991  mov     edi, 80070008h
0x14000f996  jmp     loc_14000FB3B
0x14000f99b  mov     eax, [r13+0]
0x14000f99f  mov     [rdi], eax
0x14000f9a1  lea     r8, [rsp+1B78h+var_1A98]
0x14000f9a9  lea     rdx, [rsp+1B78h+var_1AB8]
0x14000f9b1  lea     rcx, [rsp+1B78h+var_1AD0]
0x14000f9b9  call    ??$Make@VToastFeedback@@AEAPEAXAEAPEAUSendNotificationOperationResult@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VToastFeedback@@@12@AEAPEAXAEAPEAUSendNotificationOperationResult@@@Z; Microsoft::WRL::Details::Make<ToastFeedback,void * &,SendNotificationOperationResult * &>(void * &,SendNotificationOperationResult * &)
0x14000f9be  mov     rdi, [rax]
0x14000f9c1  mov     [rax], rsi
0x14000f9c4  test    rdi, rdi
0x14000f9c7  jz      short loc_14000F9E3
0x14000f9c9  mov     rax, [rdi]
0x14000f9cc  mov     rcx, rdi
0x14000f9cf  mov     rax, [rax+8]
0x14000f9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f9d8  mov     rbx, rdi
0x14000f9db  mov     [rsp+1B78h+var_1A88], rbx
0x14000f9e3  mov     rcx, [rsp+1B78h+var_1AD0]
0x14000f9eb  test    rcx, rcx
0x14000f9ee  jz      short loc_14000FA05
0x14000f9f0  mov     [rsp+1B78h+var_1AD0], rsi
0x14000f9f8  mov     rax, [rcx]
  ... truncated ...
```
