# AVCTPService::PopulateProfiles(void)

- ea: `0x1800269f4`
- end: `0x180026cd7`
- name: `?PopulateProfiles@AVCTPService@@AEAAXXZ`
- size: `739`
- prototype: `void __fastcall(AVCTPService *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800260d0`

## callees

- `0x180001dd0`
- `0x1800021dc`
- `0x18000de78`
- `0x180019c68`
- `0x180019d20`
- `0x1800266f8`
- `0x1800269f4`
- `0x1800270e4`
- `0x180029dc8`
- `0x18003381c`
- `0x18004c668`
- `0x18004c698`
- `0x18004c738`
- `0x18004c8d0`
- `0x18004c9a8`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b50`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026ac7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026b56`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026ac7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026b56`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180026ad5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180026b64`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180026ad5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180026b64`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026abd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026abd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026afd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026afd`

## string_xrefs

- `0x180026a23`: `SYSTEM\CurrentControlSet\Services\BthAvctpSvc\Parameters\Profiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall AVCTPService::PopulateProfiles(volatile signed __int32 **this, __int64 a2, bool a3)
{
  HKEY v4; // rax
  __int64 v5; // r8
  HKEY v6; // rsi
  int v7; // r14d
  char v8; // di
  const unsigned __int16 *v9; // rax
  bool v10; // r8
  HKEY v11; // rbx
  __int16 Dword; // r12
  const OLECHAR *v13; // rax
  int v14; // r8d
  const unsigned __int16 *v15; // rax
  AVCTPProfileUser *v16; // r10
  AVCTPProfileUser *v17; // r12
  void (__fastcall *v18)(struct IBtAVCTPProfileInterface *, AVCTPProfileUser *, __int64, _QWORD); // rbx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // rcx
  struct IBtAVCTPProfileInterface **v22; // rax
  __int64 v23; // r8
  _UNKNOWN **v24; // rdx
  int ppv; // [rsp+20h] [rbp-79h]
  struct IBtAVCTPProfileInterface *v26; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v27[2]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v28[8]; // [rsp+68h] [rbp-31h] BYREF
  std::_Ref_count_base *v29; // [rsp+70h] [rbp-29h]
  _BYTE v30[16]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v31; // [rsp+88h] [rbp-11h]
  GUID pclsid; // [rsp+98h] [rbp-1h] BYREF
  _BYTE v33[32]; // [rsp+A8h] [rbp+Fh] BYREF

  v4 = RegHelperOpenKey(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Profiles",
         a3);
  v6 = v4;
  if ( v4 )
  {
    v7 = 0;
    RegHelperGetSubKey(v30, v4, v5, 0);
    if ( v31 )
    {
      v8 = 1;
      while ( 1 )
      {
        v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
        v11 = RegHelperOpenKey(v6, v9, v10);
        RegHelperGetString(v33, v11);
        Dword = RegHelperGetDword(v11, 0, L"ProfileID", 0);
        RegHelperCloseKey(v11);
        pclsid = 0;
        v13 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
        if ( CLSIDFromString(v13, &pclsid) < 0 )
        {
          if ( !IsDebuggerPresent() )
            goto LABEL_18;
          DebugBreak();
        }
        v26 = 0;
        if ( CoCreateInstance(&pclsid, 0, 0x17u, &GUID_f7b743e7_b737_4ab7_b762_33d9fddcfdd9, (LPVOID *)&v26) < 0 || !v26 )
          break;
        v27[1] = operator new(0x448u);
        v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
        v17 = AVCTPProfileUser::AVCTPProfileUser(v16, Dword, v15, v26, this);
        if ( !v17 )
        {
          GetLastError();
          if ( !IsDebuggerPresent() )
LABEL_18:
            __fastfail(7u);
          DebugBreak();
        }
        v18 = *(void (__fastcall **)(struct IBtAVCTPProfileInterface *, AVCTPProfileUser *, __int64, _QWORD))(*(_QWORD *)v26 + 24LL);
        v19 = (_QWORD *)Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton>>::Instance(v28);
        v20 = (_QWORD *)Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton::Get(*v19, v27);
        v18(v26, v17, 4, *v20);
        v21 = v27[0];
        if ( v27[0] )
        {
          v27[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        if ( v29 )
          std::_Ref_count_base::_Decref(v29);
        v22 = (struct IBtAVCTPProfileInterface **)operator new(0x18u);
        v22[2] = 0;
        *v22 = v26;
        v22[1] = v17;
        v22[2] = (struct IBtAVCTPProfileInterface *)this[26];
        this[26] = (volatile signed __int32 *)v22;
        std::wstring::_Tidy_deallocate(v33);
        std::wstring::_Tidy_deallocate(v30);
        RegHelperGetSubKey(v30, v6, v23, (unsigned int)++v7);
        if ( !v31 )
          goto LABEL_27;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        v8 = 0;
      }
      v24 = &WPP_RECORDER_INITIALIZED;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v24) = v8;
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v24,
          v14,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          ppv);
      }
      std::wstring::_Tidy_deallocate(v33);
    }
LABEL_27:
    std::wstring::_Tidy_deallocate(v30);
    RegHelperCloseKey(v6);
  }
}

```

## disassembly

```asm
0x1800269f4  mov     [rsp-8+arg_8], rbx
0x1800269f9  mov     [rsp-8+arg_10], rsi
0x1800269fe  push    rbp
0x1800269ff  push    rdi
0x180026a00  push    r12
0x180026a02  push    r14
0x180026a04  push    r15
0x180026a06  lea     rbp, [rsp-37h]
0x180026a0b  sub     rsp, 0D0h
0x180026a12  mov     rax, cs:__security_cookie
0x180026a19  xor     rax, rsp
0x180026a1c  mov     [rbp+57h+var_28], rax
0x180026a20  mov     r15, rcx
0x180026a23  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Bt"...
0x180026a2a  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180026a31  call    ?RegHelperOpenKey@@YAPEAUHKEY__@@PEAU1@PEBG_N@Z; RegHelperOpenKey(HKEY__ *,ushort const *,bool)
0x180026a36  mov     rsi, rax
0x180026a39  test    rax, rax
0x180026a3c  jz      loc_180026CAF
0x180026a42  xor     r14d, r14d
0x180026a45  xor     r9d, r9d
0x180026a48  mov     rdx, rax
0x180026a4b  lea     rcx, [rbp+57h+var_78]
0x180026a4f  call    ?RegHelperGetSubKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBGK@Z; RegHelperGetSubKey(HKEY__ *,ushort const *,ulong)
0x180026a54  nop
0x180026a55  cmp     [rbp+57h+var_68], r14
0x180026a59  jz      loc_180026C9E
0x180026a5f  lea     edi, [r14+1]
0x180026a63  lea     rcx, [rbp+57h+var_78]
0x180026a67  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026a6c  mov     rdx, rax; unsigned __int16 *
0x180026a6f  mov     rcx, rsi; HKEY
0x180026a72  call    ?RegHelperOpenKey@@YAPEAUHKEY__@@PEAU1@PEBG_N@Z; RegHelperOpenKey(HKEY__ *,ushort const *,bool)
0x180026a77  mov     rbx, rax
0x180026a7a  mov     rdx, rax
0x180026a7d  lea     rcx, [rbp+57h+var_48]
0x180026a81  call    ?RegHelperGetString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1@Z; RegHelperGetString(HKEY__ *,ushort const *,ushort const *)
0x180026a86  nop
0x180026a87  xor     r9d, r9d; unsigned int
0x180026a8a  lea     r8, aProfileid; "ProfileID"
0x180026a91  xor     edx, edx; unsigned __int16 *
0x180026a93  mov     rcx, rbx; HKEY
0x180026a96  call    ?RegHelperGetDword@@YAKPEAUHKEY__@@PEBG1K@Z; RegHelperGetDword(HKEY__ *,ushort const *,ushort const *,ulong)
0x180026a9b  mov     r12d, eax
0x180026a9e  mov     rcx, rbx; HKEY
0x180026aa1  call    ?RegHelperCloseKey@@YAXPEAUHKEY__@@@Z; RegHelperCloseKey(HKEY__ *)
0x180026aa6  xorps   xmm0, xmm0
0x180026aa9  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180026aad  lea     rcx, [rbp+57h+var_78]
0x180026ab1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026ab6  mov     rcx, rax; lpsz
0x180026ab9  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180026abd  call    cs:__imp_CLSIDFromString
0x180026ac3  test    eax, eax
0x180026ac5  jns     short loc_180026ADB
0x180026ac7  call    cs:__imp_IsDebuggerPresent
0x180026acd  test    eax, eax
0x180026acf  jz      loc_180026C33
0x180026ad5  call    cs:__imp_DebugBreak
0x180026adb  mov     [rbp+57h+var_A0], 0
0x180026ae3  lea     rax, [rbp+57h+var_A0]
0x180026ae7  mov     qword ptr [rsp+0F0h+ppv], rax; ppv
0x180026aec  lea     r9, _GUID_f7b743e7_b737_4ab7_b762_33d9fddcfdd9; riid
0x180026af3  xor     edx, edx; pUnkOuter
0x180026af5  lea     r8d, [rdx+17h]; dwClsContext
0x180026af9  lea     rcx, [rbp+57h+pclsid]; rclsid
0x180026afd  call    cs:__imp_CoCreateInstance
0x180026b03  test    eax, eax
0x180026b05  js      loc_180026C3A
0x180026b0b  cmp     [rbp+57h+var_A0], 0
0x180026b10  jz      loc_180026C3A
0x180026b16  mov     ecx, 448h; Size
0x180026b1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026b20  mov     r10, rax
0x180026b23  mov     [rbp+57h+var_90], rax
0x180026b27  lea     rcx, [rbp+57h+var_48]
0x180026b2b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026b30  mov     r8, rax; unsigned __int16 *
0x180026b33  mov     qword ptr [rsp+0F0h+ppv], r15; struct AVCTPService *
0x180026b38  mov     r9, [rbp+57h+var_A0]; struct IBtAVCTPProfileInterface *
0x180026b3c  movzx   edx, r12w; unsigned __int16
0x180026b40  mov     rcx, r10; this
0x180026b43  call    ??0AVCTPProfileUser@@QEAA@GPEBGPEAUIBtAVCTPProfileInterface@@PEAVAVCTPService@@@Z; AVCTPProfileUser::AVCTPProfileUser(ushort,ushort const *,IBtAVCTPProfileInterface *,AVCTPService *)
0x180026b48  mov     r12, rax
0x180026b4b  test    rax, rax
0x180026b4e  jnz     short loc_180026B6A
0x180026b50  call    cs:__imp_GetLastError
0x180026b56  call    cs:__imp_IsDebuggerPresent
0x180026b5c  test    eax, eax
0x180026b5e  jz      loc_180026C33
0x180026b64  call    cs:__imp_DebugBreak
0x180026b6a  mov     rcx, [rbp+57h+var_A0]
0x180026b6e  mov     rax, [rcx]
0x180026b71  mov     rbx, [rax+18h]
0x180026b75  lea     rcx, [rbp+57h+var_88]
0x180026b79  call    ?Instance@?$SingletonWithFactory@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@@Foundation@45@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton>>::Instance(void)
0x180026b7e  nop
0x180026b7f  lea     rdx, [rbp+57h+var_98]
0x180026b83  mov     rcx, [rax]
0x180026b86  call    ?Get@AvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@QEAA?AV?$ComPtr@UIBthAvMediaController@@@WRL@5@XZ; Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton::Get(void)
0x180026b8b  nop
0x180026b8c  mov     r9, [rax]
0x180026b8f  mov     r8d, 4
0x180026b95  mov     rdx, r12
0x180026b98  mov     rcx, [rbp+57h+var_A0]
0x180026b9c  mov     rax, rbx
0x180026b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ba4  nop
0x180026ba5  mov     rcx, [rbp+57h+var_98]
0x180026ba9  test    rcx, rcx
0x180026bac  jz      short loc_180026BC3
0x180026bae  mov     [rbp+57h+var_98], 0
0x180026bb6  mov     rax, [rcx]
0x180026bb9  mov     rax, [rax+10h]
0x180026bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bc2  nop
0x180026bc3  mov     rcx, [rbp+57h+var_80]; this
0x180026bc7  test    rcx, rcx
0x180026bca  jz      short loc_180026BD1
0x180026bcc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180026bd1  mov     ecx, 18h; Size
0x180026bd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026bdb  mov     qword ptr [rax+10h], 0
0x180026be3  mov     rcx, [rbp+57h+var_A0]
0x180026be7  mov     [rax], rcx
0x180026bea  mov     [rax+8], r12
0x180026bee  mov     rcx, [r15+0D0h]
0x180026bf5  mov     [rax+10h], rcx
0x180026bf9  mov     [r15+0D0h], rax
0x180026c00  lea     rcx, [rbp+57h+var_48]
0x180026c04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026c09  nop
0x180026c0a  lea     rcx, [rbp+57h+var_78]
0x180026c0e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026c13  add     r14d, edi
0x180026c16  mov     r9d, r14d
0x180026c19  mov     rdx, rsi
0x180026c1c  lea     rcx, [rbp+57h+var_78]
0x180026c20  call    ?RegHelperGetSubKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBGK@Z; RegHelperGetSubKey(HKEY__ *,ushort const *,ulong)
0x180026c25  nop
0x180026c26  cmp     [rbp+57h+var_68], 0
0x180026c2b  jnz     loc_180026A63
0x180026c31  jmp     short loc_180026C9E
0x180026c33  mov     ecx, 7
0x180026c38  int     29h; Win8: RtlFailFast(ecx)
0x180026c3a  lea     rdx, WPP_GLOBAL_Control
0x180026c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c48  cmp     rcx, rdx
0x180026c4b  jz      short loc_180026C59
0x180026c4d  test    [rcx+1Ch], dil
0x180026c51  jz      short loc_180026C59
0x180026c53  cmp     byte ptr [rcx+19h], 4
0x180026c57  jnb     short loc_180026C5C
0x180026c59  xor     dil, dil
0x180026c5c  lea     rdx, WPP_RECORDER_INITIALIZED
0x180026c63  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x180026c6a  setnz   r8b
0x180026c6e  test    dil, dil
0x180026c71  jnz     short loc_180026C78
0x180026c73  test    r8b, r8b
0x180026c76  jz      short loc_180026C94
0x180026c78  mov     [rsp+0F0h+var_B0], eax
0x180026c7c  mov     [rsp+0F0h+var_C0], 12h
0x180026c83  mov     r9, [rcx+28h]
0x180026c87  mov     dl, dil
0x180026c8a  mov     rcx, [rcx+10h]
0x180026c8e  call    WPP_RECORDER_AND_TRACE_SF_d
0x180026c93  nop
0x180026c94  lea     rcx, [rbp+57h+var_48]
0x180026c98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026c9d  nop
0x180026c9e  lea     rcx, [rbp+57h+var_78]
0x180026ca2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026ca7  mov     rcx, rsi; HKEY
0x180026caa  call    ?RegHelperCloseKey@@YAXPEAUHKEY__@@@Z; RegHelperCloseKey(HKEY__ *)
0x180026caf  mov     rcx, [rbp+57h+var_28]
0x180026cb3  xor     rcx, rsp; StackCookie
0x180026cb6  call    __security_check_cookie
0x180026cbb  lea     r11, [rsp+0F0h+var_20]
0x180026cc3  mov     rbx, [r11+38h]
0x180026cc7  mov     rsi, [r11+40h]
0x180026ccb  mov     rsp, r11
0x180026cce  pop     r15
0x180026cd0  pop     r14
0x180026cd2  pop     r12
0x180026cd4  pop     rdi
0x180026cd5  pop     rbp
0x180026cd6  retn
```
