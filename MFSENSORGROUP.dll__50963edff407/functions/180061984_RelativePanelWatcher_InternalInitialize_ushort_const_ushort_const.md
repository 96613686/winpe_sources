# RelativePanelWatcher::InternalInitialize(ushort const *,ushort const *)

- ea: `0x180061984`
- end: `0x180061e59`
- name: `?InternalInitialize@RelativePanelWatcher@@AEAAJPEBG0@Z`
- size: `1237`
- prototype: `int(RelativePanelWatcher *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800611bc`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000d1f0`
- `0x180015e80`
- `0x18002c008`
- `0x180044b1c`
- `0x180044f30`
- `0x18004a560`
- `0x1800506f8`
- `0x180060a88`
- `0x180061984`
- `0x18006263c`
- `0x180062814`
- `0x180062b6c`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061c2d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061c2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061de9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180061c43`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180061c43`

## pseudocode

```c
__int64 __fastcall RelativePanelWatcher::InternalInitialize(
        RelativePanelWatcher *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int ActivationFactory; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  char *v11; // rbx
  unsigned __int16 *v12; // rax
  char *v13; // rbx
  unsigned __int16 *v14; // rax
  int DevicePanelID; // eax
  int v16; // eax
  __int64 v17; // rcx
  HRESULT v18; // eax
  __int64 (__fastcall ***v19)(__int64, GUID *, __int64 *); // rcx
  _QWORD *v20; // rbx
  __int64 v21; // rax
  __int64 (__fastcall *v22)(_QWORD *, HSTRING_HEADER *, _QWORD); // rsi
  __int64 (__fastcall ***v23)(__int64, GUID *, __int64 *); // rsi
  DWORD v24; // edx
  int v25; // r8d
  int v26; // eax
  __int64 v27; // rcx
  const WCHAR *v28; // rcx
  int DevicePhysicalDeviceLocation; // eax
  _QWORD *v31; // [rsp+40h] [rbp-19h] BYREF
  __int64 (__fastcall ***v32)(__int64, GUID *, __int64 *); // [rsp+48h] [rbp-11h] BYREF
  HSTRING v33[2]; // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF

  hstringHeader.Reserved.Reserved1 = 0;
  *(_OWORD *)v33 = 0;
  v32 = 0;
  v31 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)a2, (__int64)a3);
  ActivationFactory = StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)&hstringHeader);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_58;
    v10 = 46;
    goto LABEL_6;
  }
  v11 = (char *)hstringHeader.Reserved.Reserved1 + 1;
  v12 = (unsigned __int16 *)operator new[](saturated_mul((unsigned __int64)hstringHeader.Reserved.Reserved1 + 1, 2u));
  *((_QWORD *)this + 9) = v12;
  if ( v12 )
  {
    ActivationFactory = StringCchCopyW(v12, (unsigned __int64)v11, a2);
    v9 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = StringCchLengthW(a3, 0x7FFFFFFFu, (unsigned __int64 *)&hstringHeader);
      v9 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v13 = (char *)hstringHeader.Reserved.Reserved1 + 1;
        v14 = (unsigned __int16 *)operator new[](saturated_mul((unsigned __int64)hstringHeader.Reserved.Reserved1 + 1, 2u));
        *((_QWORD *)this + 10) = v14;
        if ( v14 )
        {
          ActivationFactory = StringCchCopyW(v14, (unsigned __int64)v13, a3);
          v9 = ActivationFactory;
          if ( ActivationFactory >= 0 )
          {
            DevicePanelID = RelativePanelHelper::GetDevicePanelID(*((LPCWSTR *)this + 10), v33);
            if ( DevicePanelID >= 0 )
            {
              v16 = RelativePanelHelper::GetDevicePanelID(*((LPCWSTR *)this + 9), &v33[1]);
              if ( v16 >= 0 )
              {
                v17 = (__int64)v31;
                v31 = 0;
                if ( v17 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                string = 0;
                v18 = WindowsCreateStringReference(
                        L"Windows.Internal.System.RelativePanelDirectionTracker",
                        0x35u,
                        &hstringHeader,
                        &string);
                if ( v18 < 0 )
                {
                  RaiseException(v18, 1u, 0, 0);
                  __debugbreak();
                }
                ActivationFactory = RoGetActivationFactory(string, &GUID_99c485f5_da7a_4075_8f5a_883d146c4d91, &v31);
                v9 = ActivationFactory;
                if ( ActivationFactory < 0 )
                {
                  if ( g_wppLevels )
                  {
                    v10 = 54;
                    goto LABEL_6;
                  }
                  goto LABEL_58;
                }
                v19 = v32;
                v20 = v31;
                v21 = *v31;
                v32 = 0;
                v22 = *(__int64 (__fastcall **)(_QWORD *, HSTRING_HEADER *, _QWORD))(v21 + 48);
                if ( v19 )
                  ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v19)[2])(v19);
                *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)v33;
                ActivationFactory = v22(v20, &hstringHeader, &v32);
                v9 = ActivationFactory;
                if ( ActivationFactory < 0 )
                {
                  if ( g_wppLevels )
                  {
                    v10 = 55;
                    goto LABEL_6;
                  }
                  goto LABEL_58;
                }
                wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset((char *)this + 96);
                v23 = v32;
                v26 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *>(
                        v32,
                        v24,
                        v25);
                if ( v26 < 0
                  || (v26 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), char *))(*v23)[8])(
                              v23,
                              (char *)this + 96),
                      v26 < 0) )
                {
                  if ( (unsigned __int8)byte_18008D62D >= 8u )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 27),
                      56,
                      &WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids,
                      this,
                      v26);
                  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset((char *)this + 96);
                }
              }
              else if ( (unsigned __int8)byte_18008D62D >= 8u )
              {
                WPP_SF_qSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  53,
                  (unsigned int)&WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids,
                  (_DWORD)this,
                  (__int64)a2,
                  v16);
              }
            }
            else if ( (unsigned __int8)byte_18008D62D >= 8u )
            {
              WPP_SF_qSD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                52,
                (unsigned int)&WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids,
                (_DWORD)this,
                (__int64)a3,
                DevicePanelID);
            }
            v27 = *((_QWORD *)this + 12);
            if ( v27 )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 48LL))(
                                    v27,
                                    (char *)this + 88);
              v9 = ActivationFactory;
              if ( ActivationFactory < 0 && g_wppLevels )
              {
                v10 = 57;
                goto LABEL_6;
              }
            }
            else
            {
              v28 = (const WCHAR *)*((_QWORD *)this + 9);
              LODWORD(hstringHeader.Reserved.Reserved1) = 0;
              DevicePhysicalDeviceLocation = RelativePanelHelper::GetDevicePhysicalDeviceLocation(
                                               v28,
                                               (unsigned int *)&hstringHeader);
              v9 = DevicePhysicalDeviceLocation;
              if ( DevicePhysicalDeviceLocation >= 0 )
              {
                if ( LODWORD(hstringHeader.Reserved.Reserved1) == 4 )
                {
                  *((_DWORD *)this + 22) = 1;
                }
                else if ( LODWORD(hstringHeader.Reserved.Reserved1) == 5 )
                {
                  *((_DWORD *)this + 22) = 2;
                }
                else
                {
                  *((_DWORD *)this + 22) = 0;
                }
              }
              else
              {
                if ( (unsigned __int8)byte_18008D62D >= 8u )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    58,
                    &WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids,
                    this,
                    DevicePhysicalDeviceLocation);
                v9 = 0;
              }
            }
            goto LABEL_58;
          }
          if ( g_wppLevels )
          {
            v10 = 51;
            goto LABEL_6;
          }
        }
        else
        {
          ActivationFactory = -2147024882;
          v9 = -2147024882;
          if ( g_wppLevels )
          {
            v10 = 50;
            goto LABEL_6;
          }
        }
      }
      else if ( g_wppLevels )
      {
        v10 = 49;
        goto LABEL_6;
      }
    }
    else if ( g_wppLevels )
    {
      v10 = 48;
      goto LABEL_6;
    }
  }
  else
  {
    ActivationFactory = -2147024882;
    v9 = -2147024882;
    if ( g_wppLevels )
    {
      v10 = 47;
LABEL_6:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids,
        this,
        ActivationFactory);
    }
  }
LABEL_58:
  if ( v33[0] )
    WindowsDeleteString(v33[0]);
  if ( v33[1] )
    WindowsDeleteString(v33[1]);
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    WPP_SF_qDdq(*((_QWORD *)WPP_GLOBAL_Control + 27), v7, v8, this, v9, *((_DWORD *)this + 22), *((_QWORD *)this + 12));
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v31);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v32);
  return v9;
}

```

## disassembly

```asm
0x180061984  mov     [rsp-8+arg_18], rbx
0x180061989  push    rbp
0x18006198a  push    rsi
0x18006198b  push    rdi
0x18006198c  push    r12
0x18006198e  push    r14
0x180061990  lea     rbp, [rsp-37h]
0x180061995  sub     rsp, 90h
0x18006199c  mov     rax, cs:__security_cookie
0x1800619a3  xor     rax, rsp
0x1800619a6  mov     [rbp+57h+var_30], rax
0x1800619aa  xorps   xmm0, xmm0
0x1800619ad  mov     qword ptr [rbp+57h+hstringHeader.Reserved], 0
0x1800619b5  movdqa  xmmword ptr [rbp+57h+var_60], xmm0
0x1800619ba  mov     rsi, r8
0x1800619bd  mov     r14, rdx
0x1800619c0  mov     [rbp+57h+var_68], 0
0x1800619c8  mov     rdi, rcx
0x1800619cb  mov     [rbp+57h+var_70], 0
0x1800619d3  cmp     cs:byte_18008D62D, 10h
0x1800619da  lea     r12, WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids
0x1800619e1  jb      short loc_180061A0B
0x1800619e3  mov     r9, rcx
0x1800619e6  mov     [rsp+0B0h+var_88], r8; __int64
0x1800619eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800619f2  mov     edx, 2Dh ; '-'
0x1800619f7  mov     r8, r12
0x1800619fa  mov     [rsp+0B0h+var_90], r14; __int64
0x1800619ff  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180061a06  call    WPP_SF_qSS
0x180061a0b  lea     r8, [rbp+57h+hstringHeader]; unsigned __int64 *
0x180061a0f  mov     edx, 7FFFFFFFh; unsigned __int64
0x180061a14  mov     rcx, r14; unsigned __int16 *
0x180061a17  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180061a1c  mov     ebx, eax
0x180061a1e  test    eax, eax
0x180061a20  jns     short loc_180061A53
0x180061a22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061a29  jb      loc_180061DD1
0x180061a2f  mov     edx, 2Eh ; '.'
0x180061a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a3b  mov     r9, rdi
0x180061a3e  mov     r8, r12
0x180061a41  mov     dword ptr [rsp+0B0h+var_90], eax
0x180061a45  mov     rcx, [rcx+10h]
0x180061a49  call    WPP_SF_qD
0x180061a4e  jmp     loc_180061DD1
0x180061a53  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180061a57  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180061a5e  inc     rbx
0x180061a61  mov     eax, 2
0x180061a66  mul     rbx
0x180061a69  cmovb   rax, rcx
0x180061a6d  mov     rcx, rax; unsigned __int64
0x180061a70  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180061a75  mov     [rdi+48h], rax
0x180061a79  test    rax, rax
0x180061a7c  jnz     short loc_180061A99
0x180061a7e  mov     eax, 8007000Eh
0x180061a83  mov     ebx, eax
0x180061a85  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061a8c  jb      loc_180061DD1
0x180061a92  mov     edx, 2Fh ; '/'
0x180061a97  jmp     short loc_180061A34
0x180061a99  mov     r8, r14; unsigned __int16 *
0x180061a9c  mov     rdx, rbx; unsigned __int64
0x180061a9f  mov     rcx, rax; unsigned __int16 *
0x180061aa2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061aa7  mov     ebx, eax
0x180061aa9  test    eax, eax
0x180061aab  jns     short loc_180061AC4
0x180061aad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061ab4  jb      loc_180061DD1
0x180061aba  mov     edx, 30h ; '0'
0x180061abf  jmp     loc_180061A34
0x180061ac4  lea     r8, [rbp+57h+hstringHeader]; unsigned __int64 *
0x180061ac8  mov     edx, 7FFFFFFFh; unsigned __int64
0x180061acd  mov     rcx, rsi; unsigned __int16 *
0x180061ad0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180061ad5  mov     ebx, eax
0x180061ad7  test    eax, eax
0x180061ad9  jns     short loc_180061AF2
0x180061adb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061ae2  jb      loc_180061DD1
0x180061ae8  mov     edx, 31h ; '1'
0x180061aed  jmp     loc_180061A34
0x180061af2  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180061af6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180061afd  inc     rbx
0x180061b00  mov     eax, 2
0x180061b05  mul     rbx
0x180061b08  cmovb   rax, rcx
0x180061b0c  mov     rcx, rax; unsigned __int64
0x180061b0f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180061b14  mov     [rdi+50h], rax
0x180061b18  test    rax, rax
0x180061b1b  jnz     short loc_180061B3B
0x180061b1d  mov     eax, 8007000Eh
0x180061b22  mov     ebx, eax
0x180061b24  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061b2b  jb      loc_180061DD1
0x180061b31  mov     edx, 32h ; '2'
0x180061b36  jmp     loc_180061A34
0x180061b3b  mov     r8, rsi; unsigned __int16 *
0x180061b3e  mov     rdx, rbx; unsigned __int64
0x180061b41  mov     rcx, rax; unsigned __int16 *
0x180061b44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061b49  mov     ebx, eax
0x180061b4b  test    eax, eax
0x180061b4d  jns     short loc_180061B66
0x180061b4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061b56  jb      loc_180061DD1
0x180061b5c  mov     edx, 33h ; '3'
0x180061b61  jmp     loc_180061A34
0x180061b66  mov     rcx, [rdi+50h]; pszDeviceInterface
0x180061b6a  lea     rdx, [rbp+57h+var_60]; HSTRING *
0x180061b6e  call    ?GetDevicePanelID@RelativePanelHelper@@SAJPEBGPEAPEAUHSTRING__@@@Z; RelativePanelHelper::GetDevicePanelID(ushort const *,HSTRING__ * *)
0x180061b73  test    eax, eax
0x180061b75  jns     short loc_180061B94
0x180061b77  cmp     cs:byte_18008D62D, 8
0x180061b7e  jb      loc_180061D2C
0x180061b84  mov     dword ptr [rsp+0B0h+var_88], eax
0x180061b88  mov     edx, 34h ; '4'
0x180061b8d  mov     [rsp+0B0h+var_90], rsi
0x180061b92  jmp     short loc_180061BC0
0x180061b94  mov     rcx, [rdi+48h]; pszDeviceInterface
0x180061b98  lea     rdx, [rbp+57h+var_60+8]; HSTRING *
0x180061b9c  call    ?GetDevicePanelID@RelativePanelHelper@@SAJPEBGPEAPEAUHSTRING__@@@Z; RelativePanelHelper::GetDevicePanelID(ushort const *,HSTRING__ * *)
0x180061ba1  test    eax, eax
0x180061ba3  jns     short loc_180061BDE
0x180061ba5  cmp     cs:byte_18008D62D, 8
0x180061bac  jb      loc_180061D2C
0x180061bb2  mov     dword ptr [rsp+0B0h+var_88], eax
0x180061bb6  mov     edx, 35h ; '5'
0x180061bbb  mov     [rsp+0B0h+var_90], r14
0x180061bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180061bc7  mov     r9, rdi
0x180061bca  mov     r8, r12
0x180061bcd  mov     rcx, [rcx+0D8h]
0x180061bd4  call    WPP_SF_qSD
0x180061bd9  jmp     loc_180061D2C
0x180061bde  mov     rcx, [rbp+57h+var_70]
0x180061be2  mov     [rbp+57h+var_70], 0
0x180061bea  test    rcx, rcx
0x180061bed  jz      short loc_180061BFB
0x180061bef  mov     rax, [rcx]
0x180061bf2  mov     rax, [rax+10h]
0x180061bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bfb  lea     r9, [rbp+57h+string]; string
0x180061bff  mov     [rbp+57h+string], 0
0x180061c07  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180061c0b  mov     edx, 35h ; '5'; length
0x180061c10  lea     rcx, ?RuntimeClass_Windows_Internal_System_RelativePanelDirectionTracker@@3QBGB; "Windows.Internal.System.RelativePanelDi"...
0x180061c17  call    cs:__imp_WindowsCreateStringReference
0x180061c1d  test    eax, eax
0x180061c1f  jns     short loc_180061C34
0x180061c21  xor     r9d, r9d; lpArguments
0x180061c24  xor     r8d, r8d; nNumberOfArguments
0x180061c27  mov     ecx, eax; dwExceptionCode
0x180061c29  lea     edx, [r9+1]; dwExceptionFlags
0x180061c2d  call    cs:__imp_RaiseException
0x180061c33  int     3; Trap to Debugger
0x180061c34  mov     rcx, [rbp+57h+string]
0x180061c38  lea     r8, [rbp+57h+var_70]
0x180061c3c  lea     rdx, _GUID_99c485f5_da7a_4075_8f5a_883d146c4d91
0x180061c43  call    cs:__imp_RoGetActivationFactory
0x180061c49  mov     ebx, eax
0x180061c4b  test    eax, eax
0x180061c4d  jns     short loc_180061C66
0x180061c4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061c56  jb      loc_180061DD1
0x180061c5c  mov     edx, 36h ; '6'
0x180061c61  jmp     loc_180061A34
0x180061c66  mov     rcx, [rbp+57h+var_68]
0x180061c6a  mov     rbx, [rbp+57h+var_70]
0x180061c6e  mov     rax, [rbx]
0x180061c71  mov     [rbp+57h+var_68], 0
0x180061c79  mov     rsi, [rax+30h]
0x180061c7d  test    rcx, rcx
0x180061c80  jz      short loc_180061C8E
0x180061c82  mov     rdx, [rcx]
0x180061c85  mov     rax, [rdx+10h]
0x180061c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c8e  movaps  xmm0, xmmword ptr [rbp+57h+var_60]
0x180061c92  lea     r8, [rbp+57h+var_68]
0x180061c96  lea     rdx, [rbp+57h+hstringHeader]
0x180061c9a  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180061c9f  mov     rcx, rbx
0x180061ca2  mov     rax, rsi
0x180061ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061caa  mov     ebx, eax
0x180061cac  test    eax, eax
0x180061cae  jns     short loc_180061CC7
0x180061cb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061cb7  jb      loc_180061DD1
0x180061cbd  mov     edx, 37h ; '7'
0x180061cc2  jmp     loc_180061A34
0x180061cc7  lea     rbx, [rdi+60h]
0x180061ccb  mov     rcx, rbx
0x180061cce  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180061cd3  mov     rsi, [rbp+57h+var_68]
0x180061cd7  mov     rcx, rsi
0x180061cda  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180061cdf  test    eax, eax
0x180061ce1  js      short loc_180061CF9
0x180061ce3  mov     rax, [rsi]
0x180061ce6  mov     rdx, rbx
0x180061ce9  mov     rcx, rsi
0x180061cec  mov     rax, [rax+40h]
0x180061cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061cf5  test    eax, eax
0x180061cf7  jns     short loc_180061D2C
0x180061cf9  cmp     cs:byte_18008D62D, 8
0x180061d00  jb      short loc_180061D24
0x180061d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180061d09  mov     edx, 38h ; '8'
0x180061d0e  mov     r9, rdi
0x180061d11  mov     dword ptr [rsp+0B0h+var_90], eax
0x180061d15  mov     r8, r12
0x180061d18  mov     rcx, [rcx+0D8h]
0x180061d1f  call    WPP_SF_qD
0x180061d24  mov     rcx, rbx
0x180061d27  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180061d2c  mov     rcx, [rdi+60h]
0x180061d30  test    rcx, rcx
0x180061d33  jz      short loc_180061D62
0x180061d35  mov     rax, [rcx]
0x180061d38  lea     rdx, [rdi+58h]
0x180061d3c  mov     rax, [rax+30h]
0x180061d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061d45  mov     ebx, eax
0x180061d47  test    eax, eax
0x180061d49  jns     loc_180061DD1
0x180061d4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061d56  jb      short loc_180061DD1
0x180061d58  mov     edx, 39h ; '9'
0x180061d5d  jmp     loc_180061A34
0x180061d62  mov     rcx, [rdi+48h]; pszDeviceInterface
0x180061d66  lea     rdx, [rbp+57h+hstringHeader]; unsigned int *
0x180061d6a  mov     dword ptr [rbp+57h+hstringHeader.Reserved], 0
0x180061d71  call    ?GetDevicePhysicalDeviceLocation@RelativePanelHelper@@SAJPEBGPEAI@Z; RelativePanelHelper::GetDevicePhysicalDeviceLocation(ushort const *,uint *)
0x180061d76  mov     ebx, eax
0x180061d78  test    eax, eax
0x180061d7a  jns     short loc_180061DAB
0x180061d7c  cmp     cs:byte_18008D62D, 8
0x180061d83  jb      short loc_180061DA7
0x180061d85  mov     rcx, cs:WPP_GLOBAL_Control
0x180061d8c  mov     edx, 3Ah ; ':'
0x180061d91  mov     r9, rdi
0x180061d94  mov     dword ptr [rsp+0B0h+var_90], eax
0x180061d98  mov     r8, r12
0x180061d9b  mov     rcx, [rcx+0D8h]
0x180061da2  call    WPP_SF_qD
0x180061da7  xor     ebx, ebx
0x180061da9  jmp     short loc_180061DD1
0x180061dab  mov     eax, dword ptr [rbp+57h+hstringHeader.Reserved]
0x180061dae  sub     eax, 4
0x180061db1  jz      short loc_180061DCA
0x180061db3  cmp     eax, 1
0x180061db6  jz      short loc_180061DC1
0x180061db8  mov     dword ptr [rdi+58h], 0
0x180061dbf  jmp     short loc_180061DD1
0x180061dc1  mov     dword ptr [rdi+58h], 2
0x180061dc8  jmp     short loc_180061DD1
0x180061dca  mov     dword ptr [rdi+58h], 1
0x180061dd1  mov     rcx, [rbp+57h+var_60]; string
0x180061dd5  test    rcx, rcx
0x180061dd8  jz      short loc_180061DE0
0x180061dda  call    cs:__imp_WindowsDeleteString
0x180061de0  mov     rcx, [rbp+57h+var_60+8]; string
0x180061de4  test    rcx, rcx
0x180061de7  jz      short loc_180061DEF
0x180061de9  call    cs:__imp_WindowsDeleteString
0x180061def  cmp     cs:byte_18008D62D, 10h
0x180061df6  jb      short loc_180061E22
0x180061df8  mov     rax, [rdi+60h]
0x180061dfc  mov     r9, rdi
0x180061dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180061e06  mov     [rsp+0B0h+var_80], rax
0x180061e0b  mov     eax, [rdi+58h]
0x180061e0e  mov     dword ptr [rsp+0B0h+var_88], eax
0x180061e12  mov     rcx, [rcx+0D8h]
0x180061e19  mov     dword ptr [rsp+0B0h+var_90], ebx
0x180061e1d  call    WPP_SF_qDdq
0x180061e22  lea     rcx, [rbp+57h+var_70]
0x180061e26  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180061e2b  lea     rcx, [rbp+57h+var_68]
0x180061e2f  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180061e34  mov     eax, ebx
0x180061e36  mov     rcx, [rbp+57h+var_30]
0x180061e3a  xor     rcx, rsp; StackCookie
0x180061e3d  call    __security_check_cookie
0x180061e42  mov     rbx, [rsp+0B0h+arg_18]
0x180061e4a  add     rsp, 90h
0x180061e51  pop     r14
0x180061e53  pop     r12
0x180061e55  pop     rdi
0x180061e56  pop     rsi
0x180061e57  pop     rbp
0x180061e58  retn
  ... truncated ...
```
