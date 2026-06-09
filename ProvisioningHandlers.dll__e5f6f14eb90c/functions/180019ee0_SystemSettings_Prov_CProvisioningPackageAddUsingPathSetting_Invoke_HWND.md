# SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::Invoke(HWND__ *)

- ea: `0x180019ee0`
- end: `0x18001a0d9`
- name: `?Invoke@CProvisioningPackageAddUsingPathSetting@Prov@SystemSettings@@MEAAJPEAUHWND__@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180001ba8`
- `0x180001c7c`
- `0x1800087ec`
- `0x18000f4fc`
- `0x18000f534`
- `0x180011248`
- `0x180019ee0`
- `0x18001fbfc`
- `0x1800200d0`
- `0x180020cd0`
- `0x180023efc`
- `0x18002474c`
- `0x180028860`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019f45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019f45`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::Invoke(
        SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting *this,
        HWND a2)
{
  char v3; // di
  HSTRING v4; // rcx
  unsigned int v5; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  CProvisioningSingleton *v9; // rcx
  __int64 last_of; // r8
  int v11; // ecx
  __int64 v12; // r8
  int v13; // r9d
  _QWORD *v14; // rax
  __int64 v15; // rdx
  int v17; // [rsp+20h] [rbp-E0h]
  UINT32 length; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD *v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v23[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v24; // [rsp+90h] [rbp-70h]
  _QWORD v25[5]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v26[96]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v3 = 0;
  v19 = 0;
  v4 = (HSTRING)*((_QWORD *)this + 27);
  if ( v4 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v4, &length);
    std::wstring::wstring(v25, StringRawBuffer);
    if ( length )
    {
      v8 = std::wstring::wstring(v22);
      ProvPackageInfo::ProvPackageInfo(v26, v8);
      *((_DWORD *)this + 56) = CProvisioningSingleton::InstallPackage(v9, (const struct ProvPackageInfo *)v26);
      last_of = std::wstring::find_last_of(v25);
      if ( (unsigned int)dword_18003E038 > 4
        && (unsigned __int8)tlgKeywordOn(&dword_18003E038, 0x400000000000LL, last_of) )
      {
        v21 = 0x2000000;
        v19 = *((_DWORD *)this + 56);
        v13 = -1;
        if ( v12 == -1 )
        {
          v14 = v25;
          if ( v25[3] >= 8u )
            v14 = (_QWORD *)v25[0];
        }
        else
        {
          v24 = 7;
          v23[2] = 0;
          LOWORD(v23[0]) = 0;
          std::wstring::assign(v23, v25, v12 + 1);
          v3 = 3;
          v14 = v23;
          if ( v24 >= 8 )
            v14 = (_QWORD *)v23[0];
        }
        v20 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v11,
          (unsigned int)byte_180036AE3,
          v12,
          v13,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v21);
        if ( (v3 & 1) != 0 )
        {
          LOBYTE(v15) = 1;
          std::wstring::_Tidy(v23, v15, 0);
        }
      }
      v5 = *((_DWORD *)this + 56);
      ProvPackageInfo::~ProvPackageInfo((ProvPackageInfo *)v26);
    }
    else
    {
      v5 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x442,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)0x8000FFFFLL,
        v17);
    }
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(v25, v7, 0);
  }
  else
  {
    v5 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43E,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)0x8000FFFFLL,
      v17);
  }
  return v5;
}

```

## disassembly

```asm
0x180019ee0  mov     [rsp-8+arg_8], rbx
0x180019ee5  mov     [rsp-8+arg_10], rdi
0x180019eea  push    rbp
0x180019eeb  lea     rbp, [rsp-30h]
0x180019ef0  sub     rsp, 130h
0x180019ef7  mov     rax, cs:__security_cookie
0x180019efe  xor     rax, rsp
0x180019f01  mov     [rbp+30h+var_10], rax
0x180019f05  mov     rbx, rcx
0x180019f08  xor     edi, edi
0x180019f0a  mov     [rsp+130h+var_EC], edi
0x180019f0e  mov     rcx, [rcx+0D8h]; string
0x180019f15  test    rcx, rcx
0x180019f18  jnz     short loc_180019F3C
0x180019f1a  mov     rcx, [rbp+38h]; this
0x180019f1e  mov     ebx, 8000FFFFh
0x180019f23  mov     r9d, ebx; char *
0x180019f26  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180019f2d  mov     edx, 43Eh; void *
0x180019f32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f37  jmp     loc_18001A0B5
0x180019f3c  mov     [rsp+130h+length], edi
0x180019f40  lea     rdx, [rsp+130h+length]; length
0x180019f45  call    cs:__imp_WindowsGetStringRawBuffer
0x180019f4c  nop     dword ptr [rax+rax+00h]
0x180019f51  mov     rdx, rax
0x180019f54  lea     rcx, [rbp+30h+var_98]
0x180019f58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180019f5d  nop
0x180019f5e  cmp     [rsp+130h+length], 0
0x180019f63  ja      short loc_180019F87
0x180019f65  mov     rcx, [rbp+38h]; this
0x180019f69  mov     ebx, 8000FFFFh
0x180019f6e  mov     r9d, ebx; char *
0x180019f71  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180019f78  mov     edx, 442h; void *
0x180019f7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f82  jmp     loc_18001A0A7
0x180019f87  lea     rdx, [rbp+30h+var_98]
0x180019f8b  lea     rcx, [rsp+130h+var_D8]
0x180019f90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180019f95  mov     rdx, rax
0x180019f98  lea     rcx, [rbp+30h+var_70]
0x180019f9c  call    ??0ProvPackageInfo@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProvPackageInfo::ProvPackageInfo(std::wstring)
0x180019fa1  nop
0x180019fa2  lea     rdx, [rbp+30h+var_70]; struct ProvPackageInfo *
0x180019fa6  call    ?InstallPackage@CProvisioningSingleton@@QEAAJAEBVProvPackageInfo@@@Z; CProvisioningSingleton::InstallPackage(ProvPackageInfo const &)
0x180019fab  mov     [rbx+0E0h], eax
0x180019fb1  lea     rcx, [rbp+30h+var_98]
0x180019fb5  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find_last_of(ushort const *,unsigned __int64)
0x180019fba  mov     r8, rax
0x180019fbd  mov     ecx, cs:dword_18003E038
0x180019fc3  cmp     ecx, 4
0x180019fc6  jbe     loc_18001A097
0x180019fcc  mov     rdx, 400000000000h
0x180019fd6  lea     rcx, dword_18003E038
0x180019fdd  call    _tlgKeywordOn
0x180019fe2  test    al, al
0x180019fe4  jz      loc_18001A097
0x180019fea  mov     [rsp+130h+var_E0], 2000000h
0x180019ff3  mov     eax, [rbx+0E0h]
0x180019ff9  mov     [rsp+130h+var_EC], eax
0x180019ffd  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001a001  cmp     r8, r9
0x18001a004  jz      short loc_18001A045
0x18001a006  mov     [rbp+30h+var_A0], 7
0x18001a00e  mov     [rbp+30h+var_A8], 0
0x18001a016  xor     eax, eax
0x18001a018  mov     word ptr [rsp+130h+var_B8], ax
0x18001a01d  inc     r8
0x18001a020  lea     rdx, [rbp+30h+var_98]
0x18001a024  lea     rcx, [rsp+130h+var_B8]
0x18001a029  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001a02e  mov     edi, 3
0x18001a033  lea     rax, [rsp+130h+var_B8]
0x18001a038  cmp     [rbp+30h+var_A0], 8
0x18001a03d  cmovnb  rax, [rsp+130h+var_B8]
0x18001a043  jmp     short loc_18001A053
0x18001a045  lea     rax, [rbp+30h+var_98]
0x18001a049  cmp     [rbp+30h+var_80], 8
0x18001a04e  cmovnb  rax, [rbp+30h+var_98]
0x18001a053  mov     [rsp+130h+var_E8], rax
0x18001a058  lea     rax, [rsp+130h+var_E0]
0x18001a05d  mov     [rsp+130h+var_100], rax
0x18001a062  lea     rax, [rsp+130h+var_EC]
0x18001a067  mov     [rsp+130h+var_108], rax
0x18001a06c  lea     rax, [rsp+130h+var_E8]
0x18001a071  mov     [rsp+130h+var_110], rax
0x18001a076  lea     rdx, byte_180036AE3
0x18001a07d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001a082  test    dil, 1
0x18001a086  jz      short loc_18001A097
0x18001a088  xor     r8d, r8d
0x18001a08b  mov     dl, 1
0x18001a08d  lea     rcx, [rsp+130h+var_B8]
0x18001a092  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001a097  mov     ebx, [rbx+0E0h]
0x18001a09d  lea     rcx, [rbp+30h+var_70]; this
0x18001a0a1  call    ??1ProvPackageInfo@@QEAA@XZ; ProvPackageInfo::~ProvPackageInfo(void)
0x18001a0a6  nop
0x18001a0a7  xor     r8d, r8d
0x18001a0aa  mov     dl, 1
0x18001a0ac  lea     rcx, [rbp+30h+var_98]
0x18001a0b0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001a0b5  mov     eax, ebx
0x18001a0b7  mov     rcx, [rbp+30h+var_10]
0x18001a0bb  xor     rcx, rsp; StackCookie
0x18001a0be  call    __security_check_cookie
0x18001a0c3  lea     r11, [rsp+130h+var_s0]
0x18001a0cb  mov     rbx, [r11+18h]
0x18001a0cf  mov     rdi, [r11+20h]
0x18001a0d3  mov     rsp, r11
0x18001a0d6  pop     rbp
0x18001a0d7  retn
```
