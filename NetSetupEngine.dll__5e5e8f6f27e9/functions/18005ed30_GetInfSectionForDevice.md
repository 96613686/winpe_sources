# GetInfSectionForDevice

- ea: `0x18005ed30`
- end: `0x18005eeba`
- name: `GetInfSectionForDevice`
- size: `394`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18005cff4`

## callees

- `0x1800177ec`
- `0x180029d20`
- `0x180029ff4`
- `0x18004490c`
- `0x18004546c`
- `0x18005ed30`
- `0x180067750`
- `0x1800810d0`

## import_xrefs

- `setupapi!SetupOpenInfFileW` at `0x18005edfe`
- `setupapi!SetupOpenInfFileW` at `0x18005edfe`
- `setupapi!SetupCloseInfFile` at `0x18005ee27`
- `setupapi!SetupCloseInfFile` at `0x18005ee27`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall GetInfSectionForDevice(wchar_t *a1, void **a2, _BOOL8 a3, void *a4)
{
  const WCHAR *v5; // rbx
  __int64 v7; // rdx
  HINF v8; // rax
  HINF v9; // rbx
  void *v10; // rcx
  void *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v16; // rdx
  _BYTE v17[32]; // [rsp+30h] [rbp-31h] BYREF
  _BYTE v18[16]; // [rsp+50h] [rbp-11h] BYREF
  _WORD v19[8]; // [rsp+60h] [rbp-1h] BYREF
  __int64 v20; // [rsp+70h] [rbp+Fh]
  __int64 v21; // [rsp+78h] [rbp+17h]
  _WORD v22[8]; // [rsp+80h] [rbp+1Fh] BYREF
  __int64 v23; // [rsp+90h] [rbp+2Fh]
  __int64 v24; // [rsp+98h] [rbp+37h]

  v5 = (const WCHAR *)a3;
  if ( *((_QWORD *)a1 + 3) >= 8u )
    a1 = *(wchar_t **)a1;
  NetSetupDevice::NetSetupDevice((NetSetupDevice *)v18, a1, a3);
  v24 = 7;
  v23 = 0;
  v22[0] = 0;
  v21 = 7;
  v20 = 0;
  v19[0] = 0;
  if ( (unsigned __int8)NetSetupDevice::GetStringProperty(v18, &DEVPKEY_Device_DriverInfPath, v5)
    && (unsigned __int8)NetSetupDevice::GetStringProperty(v18, &DEVPKEY_Device_DriverInfSection, v22) )
  {
    NetSetupDevice::GetStringProperty(v18, &DEVPKEY_Device_DriverInfSectionExt, v19);
    if ( *((_QWORD *)v5 + 3) >= 8u )
      v5 = *(const WCHAR **)v5;
    v8 = SetupOpenInfFileW(v5, 0, 2u, 0);
    v9 = v8;
    if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      Win32Exception::ThrowLastError();
    v10 = *a2;
    if ( v8 != *a2 )
    {
      if ( v10 )
        SetupCloseInfFile(v10);
      *a2 = v9;
    }
    v11 = (void *)std::operator+<wchar_t>(v17, v22, v19);
    std::wstring::operator=(a4, v11);
    LOBYTE(v12) = 1;
    std::wstring::_Tidy(v17, v12, 0);
    LOBYTE(v13) = 1;
    std::wstring::_Tidy(v19, v13, 0);
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v22, v14, 0);
    return 1;
  }
  else
  {
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(v19, v7, 0);
    LOBYTE(v16) = 1;
    std::wstring::_Tidy(v22, v16, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x18005ed30  mov     rax, rsp
0x18005ed33  push    rbp
0x18005ed34  push    rsi
0x18005ed35  push    rdi
0x18005ed36  lea     rbp, [rax-5Fh]
0x18005ed3a  sub     rsp, 0A0h
0x18005ed41  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18005ed49  mov     [rax+8], rbx
0x18005ed4d  mov     rax, cs:__security_cookie
0x18005ed54  xor     rax, rsp
0x18005ed57  mov     [rbp+57h+var_18], rax
0x18005ed5b  mov     rsi, r9
0x18005ed5e  mov     rbx, r8
0x18005ed61  mov     rdi, rdx
0x18005ed64  cmp     qword ptr [rcx+18h], 8
0x18005ed69  jb      short loc_18005ED6E
0x18005ed6b  mov     rcx, [rcx]
0x18005ed6e  mov     rdx, rcx; wchar_t *
0x18005ed71  lea     rcx, [rbp+57h+var_68]; this
0x18005ed75  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x18005ed7a  mov     ecx, 7
0x18005ed7f  mov     [rbp+57h+var_20], rcx
0x18005ed83  mov     [rbp+57h+var_28], 0
0x18005ed8b  xor     eax, eax
0x18005ed8d  mov     [rbp+57h+var_38], ax
0x18005ed91  mov     [rbp+57h+var_40], rcx
0x18005ed95  mov     [rbp+57h+var_48], rax
0x18005ed99  mov     [rbp+57h+var_58], ax
0x18005ed9d  mov     r8, rbx
0x18005eda0  lea     rdx, DEVPKEY_Device_DriverInfPath
0x18005eda7  lea     rcx, [rbp+57h+var_68]
0x18005edab  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x18005edb0  test    al, al
0x18005edb2  jz      loc_18005EE7C
0x18005edb8  lea     r8, [rbp+57h+var_38]
0x18005edbc  lea     rdx, DEVPKEY_Device_DriverInfSection
0x18005edc3  lea     rcx, [rbp+57h+var_68]
0x18005edc7  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x18005edcc  test    al, al
0x18005edce  jz      loc_18005EE7C
0x18005edd4  lea     r8, [rbp+57h+var_58]
0x18005edd8  lea     rdx, DEVPKEY_Device_DriverInfSectionExt
0x18005eddf  lea     rcx, [rbp+57h+var_68]
0x18005ede3  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x18005ede8  cmp     qword ptr [rbx+18h], 8
0x18005eded  jb      short loc_18005EDF2
0x18005edef  mov     rbx, [rbx]
0x18005edf2  xor     r9d, r9d; ErrorLine
0x18005edf5  xor     edx, edx; InfClass
0x18005edf7  lea     r8d, [r9+2]; InfStyle
0x18005edfb  mov     rcx, rbx; FileName
0x18005edfe  call    cs:__imp_SetupOpenInfFileW
0x18005ee04  mov     rbx, rax
0x18005ee07  lea     rcx, [rax+1]
0x18005ee0b  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18005ee12  jnz     short loc_18005EE1A
0x18005ee14  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
0x18005ee1a  mov     rcx, [rdi]; InfHandle
0x18005ee1d  cmp     rbx, rcx
0x18005ee20  jz      short loc_18005EE30
0x18005ee22  test    rcx, rcx
0x18005ee25  jz      short loc_18005EE2D
0x18005ee27  call    cs:__imp_SetupCloseInfFile
0x18005ee2d  mov     [rdi], rbx
0x18005ee30  lea     r8, [rbp+57h+var_58]
0x18005ee34  lea     rdx, [rbp+57h+var_38]
0x18005ee38  lea     rcx, [rbp+57h+var_88]
0x18005ee3c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@0@Z; std::operator+<wchar_t>(std::wstring const &,std::wstring const &)
0x18005ee41  mov     rdx, rax; Src
0x18005ee44  mov     rcx, rsi; void *
0x18005ee47  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005ee4c  xor     r8d, r8d
0x18005ee4f  mov     dl, 1
0x18005ee51  lea     rcx, [rbp+57h+var_88]
0x18005ee55  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18005ee5a  nop
0x18005ee5b  xor     r8d, r8d
0x18005ee5e  mov     dl, 1
0x18005ee60  lea     rcx, [rbp+57h+var_58]
0x18005ee64  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18005ee69  nop
0x18005ee6a  xor     r8d, r8d
0x18005ee6d  mov     dl, 1
0x18005ee6f  lea     rcx, [rbp+57h+var_38]
0x18005ee73  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18005ee78  mov     al, 1
0x18005ee7a  jmp     short loc_18005EE9B
0x18005ee7c  xor     r8d, r8d
0x18005ee7f  mov     dl, 1
0x18005ee81  lea     rcx, [rbp+57h+var_58]
0x18005ee85  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18005ee8a  nop
0x18005ee8b  xor     r8d, r8d
0x18005ee8e  mov     dl, 1
0x18005ee90  lea     rcx, [rbp+57h+var_38]
0x18005ee94  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18005ee99  xor     al, al
0x18005ee9b  mov     rcx, [rbp+57h+var_18]
0x18005ee9f  xor     rcx, rsp; StackCookie
0x18005eea2  call    __security_check_cookie
0x18005eea7  mov     rbx, [rsp+0B0h+arg_0]
0x18005eeaf  add     rsp, 0A0h
0x18005eeb6  pop     rdi
0x18005eeb7  pop     rsi
0x18005eeb8  pop     rbp
0x18005eeb9  retn
```
