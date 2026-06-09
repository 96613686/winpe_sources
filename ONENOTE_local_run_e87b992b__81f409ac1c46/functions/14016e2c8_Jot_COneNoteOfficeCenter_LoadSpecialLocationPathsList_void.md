# Jot::COneNoteOfficeCenter::LoadSpecialLocationPathsList(void)

- ea: `0x14016e2c8`
- end: `0x14016e618`
- name: `?LoadSpecialLocationPathsList@COneNoteOfficeCenter@Jot@@AEAAXXZ`
- size: `848`
- prototype: `void __fastcall(Jot::COneNoteOfficeCenter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14016da48`

## callees

- `0x14003f250`
- `0x140048a58`
- `0x140054290`
- `0x140056ac0`
- `0x140057580`
- `0x1400b6fe4`
- `0x1400c6790`
- `0x14016e2c8`

## import_xrefs

- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x14016e3bd`
- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x14016e3bd`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x14016e459`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x14016e459`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14016e544`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14016e544`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14016e3c8`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14016e3c8`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x14016e310`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x14016e310`
- `mso40uiWin32Client!__imp_?Create@FlexListView@FlexUI@@SA_NPEAUIFlexList@2@PEAPEAV12@@Z` at `0x14016e596`
- `mso40uiWin32Client!__imp_?Create@FlexListView@FlexUI@@SA_NPEAUIFlexList@2@PEAPEAV12@@Z` at `0x14016e596`
- `mso40uiWin32Client!__imp_?Create@DataSource@FlexUI@@SA_NPEAUIDataSourceData@2@PEAVDataSourceDescription@2@PEAUIFlexMemoryManager@2@PEAPEAV12@@Z` at `0x14016e337`
- `mso40uiWin32Client!__imp_?Create@DataSource@FlexUI@@SA_NPEAUIDataSourceData@2@PEAVDataSourceDescription@2@PEAUIFlexMemoryManager@2@PEAPEAV12@@Z` at `0x14016e337`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14016e38c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14016e426`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14016e513`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14016e38c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14016e426`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14016e513`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x14016e3f6`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x14016e4e3`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x14016e3f6`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x14016e4e3`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x14016e35d`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x14016e35d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14016e3dd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14016e4ca`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14016e3dd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14016e4ca`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14016e4ad`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14016e4ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Jot::COneNoteOfficeCenter::LoadSpecialLocationPathsList(struct FlexUI::DataSourceDescription **this)
{
  __int64 *v2; // rsi
  __m128i v3; // xmm6
  struct DataSource *v4; // rbx
  const wchar_t *v5; // rax
  struct DataSource *v6; // rbx
  __int64 v7; // rax
  const wchar_t *v8; // rbx
  __int64 v9; // rdi
  struct DataSource *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rdx
  struct FlexUI::FlexListView *v13; // rcx
  struct DataSource *v14; // [rsp+38h] [rbp-D0h] BYREF
  NetUI::BaseValue *v15; // [rsp+40h] [rbp-C8h] BYREF
  NetUI::BaseValue *v16; // [rsp+48h] [rbp-C0h] BYREF
  struct FlexUI::FlexListView *v17; // [rsp+50h] [rbp-B8h] BYREF
  struct FlexUI::FlexList *v18; // [rsp+58h] [rbp-B0h] BYREF
  NetUI::BaseValue *v19; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-A0h] BYREF
  int v21; // [rsp+70h] [rbp-98h]
  _BYTE v22[368]; // [rsp+78h] [rbp-90h] BYREF

  v18 = 0;
  FlexUI::FlexList::Create(3u, &v18);
  v2 = &qword_14025A5B0;
  do
  {
    v3 = *(__m128i *)v2;
    v14 = 0;
    FlexUI::DataSource::Create(0, this[6], 0, &v14);
    v4 = v14;
    if ( v14 )
    {
      v19 = 0;
      FlexUI::FlexValue::CreateInt32(_mm_cvtsi128_si32(v3), (struct FlexUI::FlexValueSP *)&v19);
      if ( v19 )
      {
        ((void (__fastcall *)(struct DataSource *, _QWORD, _QWORD))v4->lpVtbl->addDataSourceListener)(v4, 0, 0);
        if ( v19 )
          NetUI::BaseValue::Release(v19);
      }
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v22);
      Jot::CWzInBuffer::SetFromResource(
        (Jot::CWzInBuffer *)v22,
        *((HINSTANCE *)Jot::CJotApp::s_pSingletonJotApp + 62),
        _mm_cvtsi128_si32(_mm_srli_si128(v3, 4)));
      v5 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v22);
      v6 = v14;
      if ( v14 )
      {
        v15 = 0;
        FlexUI::FlexValue::CreateString(v5, (struct FlexUI::FlexValueSP *)&v15);
        if ( v15 )
        {
          ((void (__fastcall *)(struct DataSource *, _QWORD, __int64))v6->lpVtbl->addDataSourceListener)(v6, 0, 1);
          if ( v15 )
            NetUI::BaseValue::Release(v15);
        }
        v15 = 0;
      }
      else
      {
        MsoShipAssertTagProc(7997248);
      }
      v20 = 0;
      v21 = 0;
      MsoCF::IPropertySet::GetProperty(
        this[13],
        (const struct MsoCF::PropertyInfo *)_mm_srli_si128(v3, 8).m128i_i64[0],
        (struct MsoCF::CPropertyValue *)&v20);
      if ( v21 == 117899322 && v20 )
      {
        v7 = (*(_DWORD *)(v20 + 4) >> 1) & 0x1FFFFFFF;
        v8 = (const wchar_t *)(v20 + 8);
        if ( v20 != -8 )
        {
          if ( !(_DWORD)v7 || (v9 = v20 + 8 + 2 * v7, _std_find_trivial_2(v20 + 8, v9, 0) == v9) )
          {
            CrashWithRecovery(0x1F46100Du, 0);
            __debugbreak();
          }
        }
      }
      else
      {
        v8 = (const wchar_t *)&`MsoCF::String<MsoCF::WzTraits>::TheEmptyString'::`2'::c_empty;
      }
      v10 = v14;
      if ( v14 )
      {
        v16 = 0;
        FlexUI::FlexValue::CreateString(v8, (struct FlexUI::FlexValueSP *)&v16);
        if ( v16 )
        {
          ((void (__fastcall *)(struct DataSource *, _QWORD, __int64))v10->lpVtbl->addDataSourceListener)(v10, 0, 2);
          if ( v16 )
            NetUI::BaseValue::Release(v16);
        }
        v16 = 0;
      }
      else
      {
        MsoShipAssertTagProc(7997248);
      }
      FlexUI::RefCountTypeListSP<FlexUI::IDataSource,FlexUI::TypeTraits<FlexUI::IDataSource *>>::Add(&v18, v11, v14);
      if ( (v21 & 0x2000000) != 0 )
        MsoCF::CPropertyData::FreeAndZero_ComplexType(&v20);
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v22);
      v4 = v14;
    }
    if ( v4 )
      ((void (__fastcall *)(struct DataSource *))v4->lpVtbl->Release)(v4);
    v2 += 2;
  }
  while ( v2 != (__int64 *)&Jot::PropertySpace_JotExe::priUserPrefQuickNoteSectionPath );
  v17 = 0;
  if ( FlexUI::FlexListView::Create(v18, &v17) )
    FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IFlexList *>,FlexUI::IFlexList *>(this[12], v12, 79, v17);
  v13 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(struct FlexUI::FlexListView *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v18 )
    (*(void (__fastcall **)(struct FlexUI::FlexList *))(*(_QWORD *)v18 + 16LL))(v18);
}

```

## disassembly

```asm
0x14016e2c8  mov     rax, rsp
0x14016e2cb  mov     [rax+10h], rbx
0x14016e2cf  mov     [rax+18h], rsi
0x14016e2d3  push    rbp
0x14016e2d4  push    rdi
0x14016e2d5  push    r14
0x14016e2d7  lea     rbp, [rax-118h]
0x14016e2de  sub     rsp, 200h
0x14016e2e5  movaps  xmmword ptr [rax-28h], xmm6
0x14016e2e9  mov     rax, cs:__security_cookie
0x14016e2f0  xor     rax, rsp
0x14016e2f3  mov     [rbp+110h+var_30], rax
0x14016e2fa  mov     r14, rcx
0x14016e2fd  mov     [rsp+210h+var_1C0], 0
0x14016e306  lea     rdx, [rsp+210h+var_1C0]
0x14016e30b  mov     ecx, 3
0x14016e310  call    cs:__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z; FlexUI::FlexList::Create(uint,FlexUI::FlexList * *)
0x14016e316  lea     rsi, qword_14025A5B0
0x14016e31d  movups  xmm6, xmmword ptr [rsi]
0x14016e320  mov     [rsp+210h+var_1E0], 0
0x14016e329  lea     r9, [rsp+210h+var_1E0]
0x14016e32e  xor     r8d, r8d
0x14016e331  mov     rdx, [r14+30h]
0x14016e335  xor     ecx, ecx
0x14016e337  call    cs:__imp_?Create@DataSource@FlexUI@@SA_NPEAUIDataSourceData@2@PEAVDataSourceDescription@2@PEAUIFlexMemoryManager@2@PEAPEAV12@@Z; FlexUI::DataSource::Create(FlexUI::IDataSourceData *,FlexUI::DataSourceDescription *,FlexUI::IFlexMemoryManager *,FlexUI::DataSource * *)
0x14016e33d  mov     rbx, [rsp+210h+var_1E0]
0x14016e342  test    rbx, rbx
0x14016e345  jz      loc_14016E55A
0x14016e34b  mov     [rsp+210h+var_1B8], 0
0x14016e354  lea     rdx, [rsp+210h+var_1B8]
0x14016e359  movd    ecx, xmm6
0x14016e35d  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x14016e363  mov     r9, [rsp+210h+var_1B8]
0x14016e368  test    r9, r9
0x14016e36b  jz      short loc_14016E392
0x14016e36d  mov     rax, [rbx]
0x14016e370  xor     r8d, r8d
0x14016e373  xor     edx, edx
0x14016e375  mov     rcx, rbx
0x14016e378  mov     rax, [rax+30h]
0x14016e37c  call    cs:__guard_dispatch_icall_fptr
0x14016e382  mov     rcx, [rsp+210h+var_1B8]
0x14016e387  test    rcx, rcx
0x14016e38a  jz      short loc_14016E392
0x14016e38c  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x14016e392  lea     rcx, [rsp+210h+var_1A0]
0x14016e397  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x14016e39c  movdqa  xmm0, xmm6
0x14016e3a0  psrldq  xmm0, 4
0x14016e3a5  movd    r8d, xmm0
0x14016e3aa  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14016e3b1  mov     rdx, [rdx+1F0h]
0x14016e3b8  lea     rcx, [rsp+210h+var_1A0]
0x14016e3bd  call    cs:__imp_?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer::SetFromResource(HINSTANCE__ *,uint)
0x14016e3c3  lea     rcx, [rsp+210h+var_1A0]
0x14016e3c8  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x14016e3ce  mov     rbx, [rsp+210h+var_1E0]
0x14016e3d3  test    rbx, rbx
0x14016e3d6  jnz     short loc_14016E3E5
0x14016e3d8  mov     ecx, 7A0740h
0x14016e3dd  call    cs:__imp_MsoShipAssertTagProc
0x14016e3e3  jmp     short loc_14016E435
0x14016e3e5  mov     [rsp+210h+var_1D8], 0
0x14016e3ee  lea     rdx, [rsp+210h+var_1D8]
0x14016e3f3  mov     rcx, rax
0x14016e3f6  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x14016e3fc  mov     r9, [rsp+210h+var_1D8]
0x14016e401  test    r9, r9
0x14016e404  jz      short loc_14016E42C
0x14016e406  mov     rax, [rbx]
0x14016e409  xor     edx, edx
0x14016e40b  lea     r8d, [rdx+1]
0x14016e40f  mov     rcx, rbx
0x14016e412  mov     rax, [rax+30h]
0x14016e416  call    cs:__guard_dispatch_icall_fptr
0x14016e41c  mov     rcx, [rsp+210h+var_1D8]
0x14016e421  test    rcx, rcx
0x14016e424  jz      short loc_14016E42C
0x14016e426  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x14016e42c  mov     [rsp+210h+var_1D8], 0
0x14016e435  mov     [rsp+210h+var_1B0], 0
0x14016e43e  mov     [rsp+210h+var_1A8], 0
0x14016e446  lea     r8, [rsp+210h+var_1B0]
0x14016e44b  psrldq  xmm6, 8
0x14016e450  movq    rdx, xmm6
0x14016e455  mov     rcx, [r14+68h]
0x14016e459  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x14016e45f  cmp     [rsp+210h+var_1A8], 707003Ah
0x14016e467  jnz     short loc_14016E4B4
0x14016e469  mov     rcx, [rsp+210h+var_1B0]
0x14016e46e  test    rcx, rcx
0x14016e471  jz      short loc_14016E4B4
0x14016e473  mov     eax, [rcx+4]
0x14016e476  shr     eax, 1
0x14016e478  and     eax, 1FFFFFFFh
0x14016e47d  lea     rbx, [rcx+8]
0x14016e481  test    rbx, rbx
0x14016e484  jz      short loc_14016E4BB
0x14016e486  cmp     eax, 1
0x14016e489  jb      short loc_14016E4A6
0x14016e48b  add     rcx, 8
0x14016e48f  lea     rdi, [rcx+rax*2]
0x14016e493  xor     r8d, r8d
0x14016e496  mov     rdx, rdi
0x14016e499  mov     rcx, rbx
0x14016e49c  call    __std_find_trivial_2
0x14016e4a1  cmp     rax, rdi
0x14016e4a4  jnz     short loc_14016E4BB
0x14016e4a6  xor     edx, edx
0x14016e4a8  mov     ecx, 1F46100Dh
0x14016e4ad  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x14016e4b3  int     3; Trap to Debugger
0x14016e4b4  lea     rbx, ?c_empty@?1??TheEmptyString@?$String@UWzTraits@MsoCF@@@MsoCF@@SA?AV23@XZ@4QB_WB; wchar_t const near * const `MsoCF::String<MsoCF::WzTraits>::TheEmptyString(void)'::`2'::c_empty
0x14016e4bb  mov     rdi, [rsp+210h+var_1E0]
0x14016e4c0  test    rdi, rdi
0x14016e4c3  jnz     short loc_14016E4D2
0x14016e4c5  mov     ecx, 7A0740h
0x14016e4ca  call    cs:__imp_MsoShipAssertTagProc
0x14016e4d0  jmp     short loc_14016E522
0x14016e4d2  mov     [rsp+210h+var_1D0], 0
0x14016e4db  lea     rdx, [rsp+210h+var_1D0]
0x14016e4e0  mov     rcx, rbx
0x14016e4e3  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x14016e4e9  mov     r9, [rsp+210h+var_1D0]
0x14016e4ee  test    r9, r9
0x14016e4f1  jz      short loc_14016E519
0x14016e4f3  mov     rax, [rdi]
0x14016e4f6  xor     edx, edx
0x14016e4f8  lea     r8d, [rdx+2]
0x14016e4fc  mov     rcx, rdi
0x14016e4ff  mov     rax, [rax+30h]
0x14016e503  call    cs:__guard_dispatch_icall_fptr
0x14016e509  mov     rcx, [rsp+210h+var_1D0]
0x14016e50e  test    rcx, rcx
0x14016e511  jz      short loc_14016E519
0x14016e513  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x14016e519  mov     [rsp+210h+var_1D0], 0
0x14016e522  mov     r8, [rsp+210h+var_1E0]
0x14016e527  lea     rcx, [rsp+210h+var_1C0]
0x14016e52c  call    ?Add@?$RefCountTypeListSP@UIDataSource@FlexUI@@V?$TypeTraits@PEAUIDataSource@FlexUI@@@2@@FlexUI@@QEAA_NPEAXPEAUIDataSource@2@@Z; FlexUI::RefCountTypeListSP<FlexUI::IDataSource,FlexUI::TypeTraits<FlexUI::IDataSource *>>::Add(void *,FlexUI::IDataSource *)
0x14016e531  nop
0x14016e532  mov     edx, [rsp+210h+var_1A8]
0x14016e536  mov     eax, edx
0x14016e538  shr     eax, 19h
0x14016e53b  test    al, 1
0x14016e53d  jz      short loc_14016E54B
0x14016e53f  lea     rcx, [rsp+210h+var_1B0]
0x14016e544  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14016e54a  nop
0x14016e54b  lea     rcx, [rsp+210h+var_1A0]
0x14016e550  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x14016e555  mov     rbx, [rsp+210h+var_1E0]
0x14016e55a  test    rbx, rbx
0x14016e55d  jz      short loc_14016E56F
0x14016e55f  mov     rax, [rbx]
0x14016e562  mov     rcx, rbx
0x14016e565  mov     rax, [rax+10h]
0x14016e569  call    cs:__guard_dispatch_icall_fptr
0x14016e56f  add     rsi, 10h
0x14016e573  lea     rax, ?priUserPrefQuickNoteSectionPath@PropertySpace_JotExe@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotExe::priUserPrefQuickNoteSectionPath
0x14016e57a  cmp     rsi, rax
0x14016e57d  jnz     loc_14016E31D
0x14016e583  mov     [rsp+210h+var_1C8], 0
0x14016e58c  lea     rdx, [rsp+210h+var_1C8]
0x14016e591  mov     rcx, [rsp+210h+var_1C0]
0x14016e596  call    cs:__imp_?Create@FlexListView@FlexUI@@SA_NPEAUIFlexList@2@PEAPEAV12@@Z; FlexUI::FlexListView::Create(FlexUI::IFlexList *,FlexUI::FlexListView * *)
0x14016e59c  test    al, al
0x14016e59e  jz      short loc_14016E5B4
0x14016e5a0  mov     r9, [rsp+210h+var_1C8]
0x14016e5a5  mov     r8d, 4Fh ; 'O'
0x14016e5ab  mov     rcx, [r14+60h]
0x14016e5af  call    ??$DataSourceSetImpl@V?$TypeTraits@PEAUIFlexList@FlexUI@@@FlexUI@@PEAUIFlexList@2@@FlexUI@@YA_NPEAUIDataSource@0@IHPEAUIFlexList@0@PEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<FlexUI::IFlexList *>,FlexUI::IFlexList *>(FlexUI::IDataSource *,uint,int,FlexUI::IFlexList *,void *)
0x14016e5b4  mov     rcx, [rsp+210h+var_1C8]
0x14016e5b9  test    rcx, rcx
0x14016e5bc  jz      short loc_14016E5D5
0x14016e5be  mov     [rsp+210h+var_1C8], 0
0x14016e5c7  mov     rax, [rcx]
0x14016e5ca  mov     rax, [rax+10h]
0x14016e5ce  call    cs:__guard_dispatch_icall_fptr
0x14016e5d4  nop
0x14016e5d5  mov     rcx, [rsp+210h+var_1C0]
0x14016e5da  test    rcx, rcx
0x14016e5dd  jz      short loc_14016E5EC
0x14016e5df  mov     rax, [rcx]
0x14016e5e2  mov     rax, [rax+10h]
0x14016e5e6  call    cs:__guard_dispatch_icall_fptr
0x14016e5ec  mov     rcx, [rbp+110h+var_30]
0x14016e5f3  xor     rcx, rsp; StackCookie
0x14016e5f6  call    __security_check_cookie
0x14016e5fb  lea     r11, [rsp+210h+var_10]
0x14016e603  mov     rbx, [r11+28h]
0x14016e607  mov     rsi, [r11+30h]
0x14016e60b  movaps  xmm6, xmmword ptr [r11-10h]
0x14016e610  mov     rsp, r11
0x14016e613  pop     r14
0x14016e615  pop     rdi
0x14016e616  pop     rbp
0x14016e617  retn
```
