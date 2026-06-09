# Jot::CRecordingControlProgressLabel::GetValue(int,FlexUI::FlexValueSP &)

- ea: `0x1400d1ec0`
- end: `0x1400d21d2`
- name: `?GetValue@CRecordingControlProgressLabel@Jot@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z`
- size: `786`
- prototype: `bool __fastcall(Jot::CRecordingControlProgressLabel *__hidden this, int, struct FlexUI::FlexValueSP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14003f250`
- `0x1400488d0`
- `0x140048a58`
- `0x140054290`
- `0x140056ac0`
- `0x140057580`
- `0x1400d1ec0`

## import_xrefs

- `onmain!?SetEmpty@CWzInBuffer@Jot@@QEAAXXZ` at `0x1400d1fd2`
- `onmain!?SetEmpty@CWzInBuffer@Jot@@QEAAXXZ` at `0x1400d2141`
- `onmain!?SetEmpty@CWzInBuffer@Jot@@QEAAXXZ` at `0x1400d1fd2`
- `onmain!?SetEmpty@CWzInBuffer@Jot@@QEAAXXZ` at `0x1400d2141`
- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x1400d2162`
- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x1400d2162`
- `onmain!?priQueryDisplayText@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400d201d`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400d2029`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400d2029`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400d20a8`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400d20a8`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x1400d2090`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x1400d2090`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400d20b3`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400d216f`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400d20b3`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400d216f`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x1400d1f7b`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x1400d1f7b`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x1400d1fd8`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x1400d1fd8`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1400d1f4d`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1400d1f4d`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400d20bf`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400d217b`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400d20bf`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400d217b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400d2081`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400d2120`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400d2081`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400d2120`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400d20d5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400d20d5`

## pseudocode

```c
bool __fastcall Jot::CRecordingControlProgressLabel::GetValue(
        Jot::CRecordingControlProgressLabel *this,
        unsigned int a2,
        struct FlexUI::FlexValueSP *a3)
{
  __int64 v4; // r9
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  __int64 v10; // rdx
  char v11; // al
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 *v15; // rax
  MsoCF *v16; // rcx
  struct MsoCF::IActionManager *v17; // rax
  __int64 v18; // rax
  const wchar_t *v19; // rsi
  const wchar_t *v20; // rax
  void *v21; // rdx
  bool String; // di
  const wchar_t *v23; // rax
  bool v24; // bl
  __int64 v25; // rcx
  wchar_t *v26; // [rsp+30h] [rbp-D0h] BYREF
  int v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  MsoCF::IPropertySet *v29; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v30[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[40]; // [rsp+70h] [rbp-90h] BYREF
  Mso::Memory *v32; // [rsp+98h] [rbp-68h]
  char v33; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v34[368]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = a2;
  if ( a2 && (v6 = a2 - 11) != 0 && (v7 = v6 - 1) != 0 )
  {
    v8 = v7 - 113;
    if ( v8 )
    {
      v9 = v8 - 2;
      if ( v9 )
      {
        v10 = v9 - 1077936008;
        if ( !(_DWORD)v10 )
        {
          v11 = (*(__int64 (__fastcall **)(Jot::CRecordingControlProgressLabel *, __int64, struct FlexUI::FlexValueSP *, __int64))(*(_QWORD *)this + 144LL))(
                  this,
                  v10,
                  a3,
                  v4);
          return FlexUI::FlexValue::CreateBoolean(v11, a3);
        }
        if ( (_DWORD)v10 == 4194305 )
        {
          v11 = (*(__int64 (__fastcall **)(Jot::CRecordingControlProgressLabel *, __int64, struct FlexUI::FlexValueSP *, __int64))(*(_QWORD *)this + 152LL))(
                  this,
                  v10,
                  a3,
                  v4);
          return FlexUI::FlexValue::CreateBoolean(v11, a3);
        }
        return 0;
      }
      if ( !*((_QWORD *)this + 4) )
        return 0;
      v29 = 0;
      v28 = 132956;
      MsoCF::CreatePropertySet((MsoCF *)&v29, 0, a3);
      v13 = 0;
      v14 = *(_QWORD *)(*((_QWORD *)this + 4) + 112LL);
      if ( v14 )
      {
        v15 = (__int64 *)(*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v14 + 32LL))(v14, &v26);
        v13 = *v15;
        *v15 = 0;
        if ( v26 )
          (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v30);
      Jot::CWzInBuffer::SetEmpty((Jot::CWzInBuffer *)v30);
      v17 = MsoCF::TheActionManager(v16);
      if ( (*(unsigned __int8 (__fastcall **)(struct MsoCF::IActionManager *, int *, __int64, _QWORD))(*(_QWORD *)v17 + 168LL))(
             v17,
             &v28,
             v13,
             0) )
      {
        v26 = 0;
        v27 = 0;
        MsoCF::IPropertySet::GetProperty(
          v29,
          Jot::PropertySpace_JotMain::priQueryDisplayText,
          (struct MsoCF::CPropertyValue *)&v26);
        if ( v27 != 117899322 || !v26 )
        {
          CrashWithRecovery(0x65756F6Eu, 0);
          __debugbreak();
        }
        v18 = (*((_DWORD *)v26 + 1) >> 1) & 0x1FFFFFFF;
        v19 = v26 + 4;
        if ( v26 != (wchar_t *)-8LL
          && (!(_DWORD)v18 || (const wchar_t *)_std_find_trivial_2(v26 + 4, &v19[v18], 0) == &v19[v18]) )
        {
          CrashWithRecovery(0x1F46100Du, 0);
          __debugbreak();
        }
        Jot::CWzInBuffer::CopyWz((Jot::CWzInBuffer *)v30, v19);
        if ( (v27 & 0x2000000) != 0 )
          MsoCF::CPropertyData::FreeAndZero_ComplexType(&v26);
      }
      v20 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v30);
      String = FlexUI::FlexValue::CreateString(v20, a3);
      if ( v32 != (Mso::Memory *)&v33 )
        Mso::Memory::Free(v32, v21);
      std::wstring::~wstring(v31);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      if ( v29 )
        (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v29 + 16LL))(v29);
      return String;
    }
    else
    {
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v34);
      Jot::CWzInBuffer::SetEmpty((Jot::CWzInBuffer *)v34);
      Jot::CWzInBuffer::SetFromResource(
        (Jot::CWzInBuffer *)v34,
        *((HINSTANCE *)Jot::CJotApp::s_pSingletonJotApp + 62),
        0xAA51504F);
      v23 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v34);
      v24 = FlexUI::FlexValue::CreateString(v23, a3);
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v34);
      return v24;
    }
  }
  else
  {
    v25 = *((_QWORD *)this + 2);
    return !v25
        || (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 40LL))(v25, (unsigned int)v4) != 0;
  }
}

```

## disassembly

```asm
0x1400d1ec0  push    rbp
0x1400d1ec2  push    rbx
0x1400d1ec3  push    rsi
0x1400d1ec4  push    rdi
0x1400d1ec5  push    r14
0x1400d1ec7  lea     rbp, [rsp-240h]
0x1400d1ecf  sub     rsp, 340h
0x1400d1ed6  mov     rax, cs:__security_cookie
0x1400d1edd  xor     rax, rsp
0x1400d1ee0  mov     [rbp+260h+var_30], rax
0x1400d1ee7  mov     r14, r8
0x1400d1eea  mov     r9d, edx
0x1400d1eed  mov     rdi, rcx
0x1400d1ef0  test    edx, edx
0x1400d1ef2  jz      loc_1400D2193
0x1400d1ef8  sub     edx, 0Bh
0x1400d1efb  jz      loc_1400D2193
0x1400d1f01  sub     edx, 1
0x1400d1f04  jz      loc_1400D2193
0x1400d1f0a  sub     edx, 71h ; 'q'
0x1400d1f0d  jz      loc_1400D212E
0x1400d1f13  sub     edx, 2
0x1400d1f16  jz      short loc_1400D1F58
0x1400d1f18  sub     edx, 403FFF88h
0x1400d1f1e  jz      short loc_1400D1F38
0x1400d1f20  cmp     edx, 400001h
0x1400d1f26  jnz     loc_1400D2127
0x1400d1f2c  mov     rax, [rcx]
0x1400d1f2f  mov     rax, [rax+98h]
0x1400d1f36  jmp     short loc_1400D1F42
0x1400d1f38  mov     rax, [rcx]
0x1400d1f3b  mov     rax, [rax+90h]
0x1400d1f42  call    cs:__guard_dispatch_icall_fptr
0x1400d1f48  mov     cl, al
0x1400d1f4a  mov     rdx, r14
0x1400d1f4d  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1400d1f53  jmp     loc_1400D21B5
0x1400d1f58  cmp     qword ptr [rcx+20h], 0
0x1400d1f5d  jz      loc_1400D2127
0x1400d1f63  mov     [rsp+360h+var_318], 0
0x1400d1f6c  mov     [rsp+360h+var_320], 2075Ch
0x1400d1f74  xor     edx, edx
0x1400d1f76  lea     rcx, [rsp+360h+var_318]
0x1400d1f7b  call    cs:__imp_?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet * *,MsoCF::IPropertySet *)
0x1400d1f81  xor     ebx, ebx
0x1400d1f83  mov     rax, [rdi+20h]
0x1400d1f87  mov     rcx, [rax+70h]
0x1400d1f8b  test    rcx, rcx
0x1400d1f8e  jz      short loc_1400D1FC3
0x1400d1f90  mov     rax, [rcx]
0x1400d1f93  lea     rdx, [rsp+360h+var_330]
0x1400d1f98  mov     rax, [rax+20h]
0x1400d1f9c  call    cs:__guard_dispatch_icall_fptr
0x1400d1fa2  mov     rbx, [rax]
0x1400d1fa5  mov     qword ptr [rax], 0
0x1400d1fac  mov     rcx, [rsp+360h+var_330]
0x1400d1fb1  test    rcx, rcx
0x1400d1fb4  jz      short loc_1400D1FC3
0x1400d1fb6  mov     rax, [rcx]
0x1400d1fb9  mov     rax, [rax+10h]
0x1400d1fbd  call    cs:__guard_dispatch_icall_fptr
0x1400d1fc3  lea     rcx, [rsp+360h+var_310]
0x1400d1fc8  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x1400d1fcd  lea     rcx, [rsp+360h+var_310]
0x1400d1fd2  call    cs:__imp_?SetEmpty@CWzInBuffer@Jot@@QEAAXXZ; Jot::CWzInBuffer::SetEmpty(void)
0x1400d1fd8  call    cs:__imp_?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ; MsoCF::TheActionManager(void)
0x1400d1fde  mov     r10, rax
0x1400d1fe1  mov     rcx, [rax]
0x1400d1fe4  mov     rax, [rcx+0A8h]
0x1400d1feb  xor     r9d, r9d
0x1400d1fee  mov     r8, rbx
0x1400d1ff1  lea     rdx, [rsp+360h+var_320]
0x1400d1ff6  mov     rcx, r10
0x1400d1ff9  call    cs:__guard_dispatch_icall_fptr
0x1400d1fff  test    al, al
0x1400d2001  jz      loc_1400D20AE
0x1400d2007  mov     [rsp+360h+var_330], 0
0x1400d2010  mov     [rsp+360h+var_328], 0
0x1400d2018  lea     r8, [rsp+360h+var_330]
0x1400d201d  mov     rdx, cs:__imp_?priQueryDisplayText@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priQueryDisplayText
0x1400d2024  mov     rcx, [rsp+360h+var_318]
0x1400d2029  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400d202f  cmp     [rsp+360h+var_328], 707003Ah
0x1400d2037  jnz     loc_1400D2119
0x1400d203d  mov     rcx, [rsp+360h+var_330]
0x1400d2042  test    rcx, rcx
0x1400d2045  jz      loc_1400D2119
0x1400d204b  mov     eax, [rcx+4]
0x1400d204e  shr     eax, 1
0x1400d2050  and     eax, 1FFFFFFFh
0x1400d2055  lea     rsi, [rcx+8]
0x1400d2059  test    rsi, rsi
0x1400d205c  jz      short loc_1400D2088
0x1400d205e  cmp     eax, 1
0x1400d2061  jb      short loc_1400D207A
0x1400d2063  lea     rdi, [rsi+rax*2]
0x1400d2067  xor     r8d, r8d
0x1400d206a  mov     rdx, rdi
0x1400d206d  mov     rcx, rsi
0x1400d2070  call    __std_find_trivial_2
0x1400d2075  cmp     rax, rdi
0x1400d2078  jnz     short loc_1400D2088
0x1400d207a  xor     edx, edx
0x1400d207c  mov     ecx, 1F46100Dh
0x1400d2081  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400d2087  int     3; Trap to Debugger
0x1400d2088  mov     rdx, rsi
0x1400d208b  lea     rcx, [rsp+360h+var_310]
0x1400d2090  call    cs:__imp_?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x1400d2096  mov     edx, [rsp+360h+var_328]
0x1400d209a  mov     eax, edx
0x1400d209c  shr     eax, 19h
0x1400d209f  test    al, 1
0x1400d20a1  jz      short loc_1400D20AE
0x1400d20a3  lea     rcx, [rsp+360h+var_330]
0x1400d20a8  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400d20ae  lea     rcx, [rsp+360h+var_310]
0x1400d20b3  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1400d20b9  mov     rcx, rax
0x1400d20bc  mov     rdx, r14
0x1400d20bf  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1400d20c5  mov     dil, al
0x1400d20c8  lea     rax, [rbp+260h+var_2B0]
0x1400d20cc  mov     rcx, [rbp+260h+var_2C8]
0x1400d20d0  cmp     rcx, rax
0x1400d20d3  jz      short loc_1400D20DB
0x1400d20d5  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1400d20db  lea     rcx, [rsp+360h+var_2F0]; void *
0x1400d20e0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d20e5  test    rbx, rbx
0x1400d20e8  jz      short loc_1400D20FA
0x1400d20ea  mov     rax, [rbx]
0x1400d20ed  mov     rcx, rbx
0x1400d20f0  mov     rax, [rax+10h]
0x1400d20f4  call    cs:__guard_dispatch_icall_fptr
0x1400d20fa  mov     rcx, [rsp+360h+var_318]
0x1400d20ff  test    rcx, rcx
0x1400d2102  jz      short loc_1400D2111
0x1400d2104  mov     rax, [rcx]
0x1400d2107  mov     rax, [rax+10h]
0x1400d210b  call    cs:__guard_dispatch_icall_fptr
0x1400d2111  mov     al, dil
0x1400d2114  jmp     loc_1400D21B5
0x1400d2119  xor     edx, edx
0x1400d211b  mov     ecx, 65756F6Eh
0x1400d2120  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400d2126  int     3; Trap to Debugger
0x1400d2127  xor     al, al
0x1400d2129  jmp     loc_1400D21B5
0x1400d212e  lea     rcx, [rbp+260h+var_1A0]
0x1400d2135  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x1400d213a  lea     rcx, [rbp+260h+var_1A0]
0x1400d2141  call    cs:__imp_?SetEmpty@CWzInBuffer@Jot@@QEAAXXZ; Jot::CWzInBuffer::SetEmpty(void)
0x1400d2147  mov     r8d, 0AA51504Fh
0x1400d214d  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1400d2154  mov     rdx, [rdx+1F0h]
0x1400d215b  lea     rcx, [rbp+260h+var_1A0]
0x1400d2162  call    cs:__imp_?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer::SetFromResource(HINSTANCE__ *,uint)
0x1400d2168  lea     rcx, [rbp+260h+var_1A0]
0x1400d216f  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1400d2175  mov     rcx, rax
0x1400d2178  mov     rdx, r14
0x1400d217b  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1400d2181  mov     bl, al
0x1400d2183  lea     rcx, [rbp+260h+var_1A0]
0x1400d218a  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x1400d218f  mov     al, bl
0x1400d2191  jmp     short loc_1400D21B5
0x1400d2193  mov     rcx, [rcx+10h]
0x1400d2197  test    rcx, rcx
0x1400d219a  jz      short loc_1400D21B3
0x1400d219c  mov     rax, [rcx]
0x1400d219f  mov     edx, r9d
0x1400d21a2  mov     rax, [rax+28h]
0x1400d21a6  call    cs:__guard_dispatch_icall_fptr
0x1400d21ac  test    al, al
0x1400d21ae  setnz   al
0x1400d21b1  jmp     short loc_1400D21B5
0x1400d21b3  mov     al, 1
0x1400d21b5  mov     rcx, [rbp+260h+var_30]
0x1400d21bc  xor     rcx, rsp; StackCookie
0x1400d21bf  call    __security_check_cookie
0x1400d21c4  add     rsp, 340h
0x1400d21cb  pop     r14
0x1400d21cd  pop     rdi
0x1400d21ce  pop     rsi
0x1400d21cf  pop     rbx
0x1400d21d0  pop     rbp
0x1400d21d1  retn
```
