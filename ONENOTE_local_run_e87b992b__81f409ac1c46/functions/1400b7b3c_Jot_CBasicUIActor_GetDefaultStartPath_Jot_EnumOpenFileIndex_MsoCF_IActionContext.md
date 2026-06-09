# Jot::CBasicUIActor::GetDefaultStartPath(Jot::EnumOpenFileIndex,MsoCF::IActionContext *)

- ea: `0x1400b7b3c`
- end: `0x1400b7ec9`
- name: `?GetDefaultStartPath@CBasicUIActor@Jot@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4EnumOpenFileIndex@2@PEAUIActionContext@MsoCF@@@Z`
- size: `909`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400b72f0`

## callees

- `0x140012050`
- `0x140040888`
- `0x1400488d0`
- `0x140052c10`
- `0x140054290`
- `0x140056ac0`
- `0x140057580`
- `0x1400b7b3c`
- `0x1400e7980`

## import_xrefs

- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x1400b7c05`
- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x1400b7c05`
- `onmain!?FGetMyDocumentsFolder@Jot@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1400b7bf2`
- `onmain!?FGetMyDocumentsFolder@Jot@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1400b7c61`
- `onmain!?FGetMyDocumentsFolder@Jot@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1400b7bf2`
- `onmain!?FGetMyDocumentsFolder@Jot@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1400b7c61`
- `onmain!?RegReadWz@Jot@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBU_msoreg@@@Z` at `0x1400b7b88`
- `onmain!?RegReadWz@Jot@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBU_msoreg@@@Z` at `0x1400b7b88`
- `onmain!?priFilepath@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400b7d5e`
- `onmain!?priContext@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400b7cb7`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400b7d69`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400b7d69`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b7de2`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b7e2a`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b7e80`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b7de2`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b7e2a`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b7e80`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b7d07`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b7dbf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b7e39`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b7d07`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b7dbf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b7e39`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Jot::CBasicUIActor::GetDefaultStartPath(
        __int64 a1,
        unsigned int a2,
        struct MsoCF::IActionContext *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  void (__fastcall ***v9)(_QWORD, GUID *, struct MsoCF::IActionContext **); // rcx
  char v10; // al
  int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rsi
  struct MsoCF::IActionContext *v15; // [rsp+20h] [rbp-49h] BYREF
  void (__fastcall ***v16)(_QWORD, GUID *, struct MsoCF::IActionContext **); // [rsp+28h] [rbp-41h] BYREF
  int v17; // [rsp+30h] [rbp-39h]
  int v18; // [rsp+38h] [rbp-31h] BYREF
  __int64 v19; // [rsp+40h] [rbp-29h]
  __int128 v20; // [rsp+50h] [rbp-19h] BYREF
  __m128i si128; // [rsp+60h] [rbp-9h]
  char v22; // [rsp+70h] [rbp+7h]
  int v23; // [rsp+78h] [rbp+Fh] BYREF
  MsoCF::IPropertySet *v24; // [rsp+80h] [rbp+17h]

  v15 = (struct MsoCF::IActionContext *)a1;
  v6 = 5LL * (int)a2;
  if ( (*((_BYTE *)&Jot::CBasicUIActor::s_rgOpenFile + 8 * v6 + 20) & 0x20) != 0 )
  {
    Jot::RegReadWz(&v20, *((_QWORD *)&Jot::CBasicUIActor::s_rgOpenFile + v6 + 4));
    if ( v22 )
    {
      if ( si128.m128i_i64[0] )
      {
        *(_OWORD *)a1 = v20;
        *(__m128i *)(a1 + 16) = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v20) = 0;
LABEL_5:
        std::wstring::~wstring(&v20);
        return a1;
      }
      std::wstring::`scalar deleting destructor'(&v20);
    }
  }
  if ( a2 == 5 )
  {
    v20 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v20) = 0;
    if ( (unsigned __int8)Jot::FGetMyDocumentsFolder(&v20) )
    {
      v7 = Jot::LoadStringFromTheResourceDll(&v23, 1258855830);
      std::operator+<wchar_t>(a1, &v20, v7);
      std::wstring::~wstring(&v23);
      goto LABEL_5;
    }
    std::wstring::~wstring(&v20);
  }
  if ( a2 <= 0x13 )
  {
    v8 = 540674;
    if ( _bittest(&v8, a2) )
    {
      v20 = 0;
      si128.m128i_i64[0] = 0;
      si128.m128i_i64[1] = 7;
      LOWORD(v20) = 0;
      if ( (unsigned __int8)Jot::FGetMyDocumentsFolder(&v20) && si128.m128i_i64[0] )
      {
        *(_OWORD *)a1 = v20;
        *(__m128i *)(a1 + 16) = si128;
        si128.m128i_i64[0] = 0;
        si128.m128i_i64[1] = 7;
        LOWORD(v20) = 0;
        goto LABEL_5;
      }
      std::wstring::~wstring(&v20);
    }
  }
  v19 = 0;
  v18 = 131847;
  if ( MsoCF::CActionPropertySet::Execute((MsoCF::CActionPropertySet *)&v18, a3) )
  {
    v9 = 0;
    v16 = 0;
    if ( v19
      && (v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v19 + 48LL))(
                  v19,
                  Jot::PropertySpace_JotMain::priContext,
                  &v16),
          v9 = v16,
          v10) )
    {
      v11 = *((_DWORD *)&Jot::PropertySpace_JotMain::priContext + 1);
    }
    else
    {
      v11 = 0;
    }
    v17 = v11;
    if ( v11 != 185729042 )
    {
      CrashWithRecovery(0x65756F73u, 0);
      __debugbreak();
    }
    if ( v9 )
    {
      v15 = 0;
      (**v9)(v9, &GUID_21cf30b4_febe_466e_b6f4_1a5e08a66132, &v15);
      v24 = 0;
      v23 = 131848;
      if ( MsoCF::CActionPropertySet::Execute((MsoCF::CActionPropertySet *)&v23, v15) )
      {
        *(_QWORD *)&v20 = 0;
        DWORD2(v20) = 0;
        MsoCF::IPropertySet::GetProperty(
          v24,
          Jot::PropertySpace_JotMain::priFilepath,
          (struct MsoCF::CPropertyValue *)&v20);
        if ( DWORD2(v20) == 117899322 && (_QWORD)v20 )
        {
          v12 = (*(_DWORD *)(v20 + 4) >> 1) & 0x1FFFFFFF;
          v13 = v20 + 8;
          if ( (_QWORD)v20 != -8 && (!(_DWORD)v12 || _std_find_trivial_2(v20 + 8, v13 + 2 * v12, 0) == v13 + 2 * v12) )
          {
            CrashWithRecovery(0x1F46100Du, 0);
            __debugbreak();
          }
          std::wstring::wstring(a1, v13);
          if ( (DWORD2(v20) & 0x2000000) != 0 )
            MsoCF::CPropertyData::FreeAndZero_ComplexType(&v20);
          if ( v24 )
            (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v24 + 16LL))(v24);
          v24 = 0;
          if ( v15 )
            (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v15 + 16LL))(v15);
          if ( (v17 & 0x2000000) != 0 )
            MsoCF::CPropertyData::FreeAndZero_ComplexType(&v16);
          goto LABEL_49;
        }
        CrashWithRecovery(0x65756F6Eu, 0);
      }
      if ( v24 )
        (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v24 + 16LL))(v24);
      v24 = 0;
      if ( v15 )
        (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v15 + 16LL))(v15);
      v11 = v17;
    }
    if ( (v11 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v16);
  }
  std::wstring::wstring(a1, &psz);
LABEL_49:
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return a1;
}

```

## disassembly

```asm
0x1400b7b3c  push    rbp
0x1400b7b3e  push    rbx
0x1400b7b3f  push    rsi
0x1400b7b40  push    rdi
0x1400b7b41  push    r14
0x1400b7b43  lea     rbp, [rsp-37h]
0x1400b7b48  sub     rsp, 0A0h
0x1400b7b4f  mov     rax, cs:__security_cookie
0x1400b7b56  xor     rax, rsp
0x1400b7b59  mov     [rbp+57h+var_28], rax
0x1400b7b5d  mov     rsi, r8
0x1400b7b60  movsxd  rbx, edx
0x1400b7b63  mov     rdi, rcx
0x1400b7b66  mov     [rbp+57h+var_A0], rcx
0x1400b7b6a  xor     r14d, r14d
0x1400b7b6d  lea     rdx, [rbx+rbx*4]
0x1400b7b71  lea     rax, ?s_rgOpenFile@CBasicUIActor@Jot@@0QBUOpenFileData@2@B; Jot::OpenFileData const near * const Jot::CBasicUIActor::s_rgOpenFile
0x1400b7b78  test    byte ptr [rax+rdx*8+14h], 20h
0x1400b7b7d  jz      short loc_1400B7BD0
0x1400b7b7f  mov     rdx, [rax+rdx*8+20h]
0x1400b7b84  lea     rcx, [rbp+57h+var_70]
0x1400b7b88  call    cs:__imp_?RegReadWz@Jot@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBU_msoreg@@@Z; Jot::RegReadWz(_msoreg const *)
0x1400b7b8e  cmp     [rbp+57h+var_50], r14b
0x1400b7b92  jz      short loc_1400B7BD0
0x1400b7b94  lea     rcx, [rbp+57h+var_70]; void *
0x1400b7b98  cmp     qword ptr [rbp+57h+var_60], r14
0x1400b7b9c  jz      short loc_1400B7BC9
0x1400b7b9e  movups  xmm0, [rbp+57h+var_70]
0x1400b7ba2  movups  xmmword ptr [rdi], xmm0
0x1400b7ba5  movups  xmm1, [rbp+57h+var_60]
0x1400b7ba9  movups  xmmword ptr [rdi+10h], xmm1
0x1400b7bad  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1400b7bb5  movdqu  [rbp+57h+var_60], xmm0
0x1400b7bba  mov     word ptr [rbp+57h+var_70], r14w
0x1400b7bbf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b7bc4  jmp     loc_1400B7EAC
0x1400b7bc9  xor     edx, edx
0x1400b7bcb  call    ??_G?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x1400b7bd0  cmp     ebx, 5
0x1400b7bd3  jnz     short loc_1400B7C35
0x1400b7bd5  xorps   xmm0, xmm0
0x1400b7bd8  movups  [rbp+57h+var_70], xmm0
0x1400b7bdc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400b7be4  movdqu  [rbp+57h+var_60], xmm1
0x1400b7be9  mov     word ptr [rbp+57h+var_70], r14w
0x1400b7bee  lea     rcx, [rbp+57h+var_70]
0x1400b7bf2  call    cs:__imp_?FGetMyDocumentsFolder@Jot@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Jot::FGetMyDocumentsFolder(std::wstring &)
0x1400b7bf8  test    al, al
0x1400b7bfa  jz      short loc_1400B7C2C
0x1400b7bfc  mov     edx, 4B089D96h
0x1400b7c01  lea     rcx, [rbp+57h+var_48]
0x1400b7c05  call    cs:__imp_?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x1400b7c0b  nop
0x1400b7c0c  mov     r8, rax
0x1400b7c0f  lea     rdx, [rbp+57h+var_70]
0x1400b7c13  mov     rcx, rdi
0x1400b7c16  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<wchar_t>(std::wstring const &,std::wstring &&)
0x1400b7c1b  nop
0x1400b7c1c  lea     rcx, [rbp+57h+var_48]; void *
0x1400b7c20  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b7c25  nop
0x1400b7c26  lea     rcx, [rbp+57h+var_70]
0x1400b7c2a  jmp     short loc_1400B7BBF
0x1400b7c2c  lea     rcx, [rbp+57h+var_70]; void *
0x1400b7c30  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b7c35  cmp     ebx, 13h
0x1400b7c38  ja      short loc_1400B7C98
0x1400b7c3a  mov     eax, 84002h
0x1400b7c3f  bt      eax, ebx
0x1400b7c42  jnb     short loc_1400B7C98
0x1400b7c44  xorps   xmm0, xmm0
0x1400b7c47  movups  [rbp+57h+var_70], xmm0
0x1400b7c4b  mov     qword ptr [rbp+57h+var_60], r14
0x1400b7c4f  mov     ebx, 7
0x1400b7c54  mov     qword ptr [rbp+57h+var_60+8], rbx
0x1400b7c58  mov     word ptr [rbp+57h+var_70], r14w
0x1400b7c5d  lea     rcx, [rbp+57h+var_70]
0x1400b7c61  call    cs:__imp_?FGetMyDocumentsFolder@Jot@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Jot::FGetMyDocumentsFolder(std::wstring &)
0x1400b7c67  test    al, al
0x1400b7c69  jz      short loc_1400B7C8F
0x1400b7c6b  cmp     qword ptr [rbp+57h+var_60], r14
0x1400b7c6f  jz      short loc_1400B7C8F
0x1400b7c71  movups  xmm0, [rbp+57h+var_70]
0x1400b7c75  movups  xmmword ptr [rdi], xmm0
0x1400b7c78  movups  xmm1, [rbp+57h+var_60]
0x1400b7c7c  movups  xmmword ptr [rdi+10h], xmm1
0x1400b7c80  mov     qword ptr [rbp+57h+var_60], r14
0x1400b7c84  mov     qword ptr [rbp+57h+var_60+8], rbx
0x1400b7c88  mov     word ptr [rbp+57h+var_70], r14w
0x1400b7c8d  jmp     short loc_1400B7C26
0x1400b7c8f  lea     rcx, [rbp+57h+var_70]; void *
0x1400b7c93  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b7c98  mov     [rbp+57h+var_80], r14
0x1400b7c9c  mov     [rbp+57h+var_88], 20307h
0x1400b7ca3  mov     rdx, rsi; struct MsoCF::IActionContext *
0x1400b7ca6  lea     rcx, [rbp+57h+var_88]; this
0x1400b7caa  call    ?Execute@CActionPropertySet@MsoCF@@QEAA_NPEAUIActionContext@2@@Z; MsoCF::CActionPropertySet::Execute(MsoCF::IActionContext *)
0x1400b7caf  test    al, al
0x1400b7cb1  jz      loc_1400B7E86
0x1400b7cb7  mov     rbx, cs:__imp_?priContext@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priContext
0x1400b7cbe  mov     r9, [rbp+57h+var_80]
0x1400b7cc2  mov     rcx, r14
0x1400b7cc5  mov     [rbp+57h+var_98], rcx
0x1400b7cc9  test    r9, r9
0x1400b7ccc  jz      short loc_1400B7CF2
0x1400b7cce  mov     rax, [r9]
0x1400b7cd1  lea     r8, [rbp+57h+var_98]
0x1400b7cd5  mov     rdx, rbx
0x1400b7cd8  mov     rcx, r9
0x1400b7cdb  mov     rax, [rax+30h]
0x1400b7cdf  call    cs:__guard_dispatch_icall_fptr
0x1400b7ce5  mov     rcx, [rbp+57h+var_98]
0x1400b7ce9  test    al, al
0x1400b7ceb  jz      short loc_1400B7CF2
0x1400b7ced  mov     edx, [rbx+4]
0x1400b7cf0  jmp     short loc_1400B7CF5
0x1400b7cf2  mov     edx, r14d
0x1400b7cf5  mov     [rbp+57h+var_90], edx
0x1400b7cf8  cmp     edx, 0B120012h
0x1400b7cfe  jz      short loc_1400B7D0E
0x1400b7d00  xor     edx, edx
0x1400b7d02  mov     ecx, 65756F73h
0x1400b7d07  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400b7d0d  int     3; Trap to Debugger
0x1400b7d0e  test    rcx, rcx
0x1400b7d11  jz      loc_1400B7E73
0x1400b7d17  mov     [rbp+57h+var_A0], r14
0x1400b7d1b  mov     rax, [rcx]
0x1400b7d1e  lea     r8, [rbp+57h+var_A0]
0x1400b7d22  lea     rdx, _GUID_21cf30b4_febe_466e_b6f4_1a5e08a66132
0x1400b7d29  mov     rax, [rax]
0x1400b7d2c  call    cs:__guard_dispatch_icall_fptr
0x1400b7d32  mov     [rbp+57h+var_40], r14
0x1400b7d36  mov     [rbp+57h+var_48], 20308h
0x1400b7d3d  mov     rdx, [rbp+57h+var_A0]; struct MsoCF::IActionContext *
0x1400b7d41  lea     rcx, [rbp+57h+var_48]; this
0x1400b7d45  call    ?Execute@CActionPropertySet@MsoCF@@QEAA_NPEAUIActionContext@2@@Z; MsoCF::CActionPropertySet::Execute(MsoCF::IActionContext *)
0x1400b7d4a  test    al, al
0x1400b7d4c  jz      loc_1400B7E40
0x1400b7d52  mov     qword ptr [rbp+57h+var_70], r14
0x1400b7d56  mov     dword ptr [rbp+57h+var_70+8], r14d
0x1400b7d5a  lea     r8, [rbp+57h+var_70]
0x1400b7d5e  mov     rdx, cs:__imp_?priFilepath@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priFilepath
0x1400b7d65  mov     rcx, [rbp+57h+var_40]
0x1400b7d69  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400b7d6f  cmp     dword ptr [rbp+57h+var_70+8], 707003Ah
0x1400b7d76  jnz     loc_1400B7E32
0x1400b7d7c  mov     rcx, qword ptr [rbp+57h+var_70]
0x1400b7d80  test    rcx, rcx
0x1400b7d83  jz      loc_1400B7E32
0x1400b7d89  mov     eax, [rcx+4]
0x1400b7d8c  shr     eax, 1
0x1400b7d8e  and     eax, 1FFFFFFFh
0x1400b7d93  lea     rsi, [rcx+8]
0x1400b7d97  test    rsi, rsi
0x1400b7d9a  jz      short loc_1400B7DC6
0x1400b7d9c  cmp     eax, 1
0x1400b7d9f  jb      short loc_1400B7DB8
0x1400b7da1  lea     rbx, [rsi+rax*2]
0x1400b7da5  xor     r8d, r8d
0x1400b7da8  mov     rdx, rbx
0x1400b7dab  mov     rcx, rsi
0x1400b7dae  call    __std_find_trivial_2
0x1400b7db3  cmp     rax, rbx
0x1400b7db6  jnz     short loc_1400B7DC6
0x1400b7db8  xor     edx, edx
0x1400b7dba  mov     ecx, 1F46100Dh
0x1400b7dbf  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400b7dc5  int     3; Trap to Debugger
0x1400b7dc6  mov     rdx, rsi
0x1400b7dc9  mov     rcx, rdi
0x1400b7dcc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400b7dd1  nop
0x1400b7dd2  mov     edx, dword ptr [rbp+57h+var_70+8]
0x1400b7dd5  mov     eax, edx
0x1400b7dd7  shr     eax, 19h
0x1400b7dda  test    al, 1
0x1400b7ddc  jz      short loc_1400B7DE9
0x1400b7dde  lea     rcx, [rbp+57h+var_70]
0x1400b7de2  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400b7de8  nop
0x1400b7de9  mov     rcx, [rbp+57h+var_40]
0x1400b7ded  test    rcx, rcx
0x1400b7df0  jz      short loc_1400B7DFF
0x1400b7df2  mov     rax, [rcx]
0x1400b7df5  mov     rax, [rax+10h]
0x1400b7df9  call    cs:__guard_dispatch_icall_fptr
0x1400b7dff  mov     [rbp+57h+var_40], r14
0x1400b7e03  mov     rcx, [rbp+57h+var_A0]
0x1400b7e07  test    rcx, rcx
0x1400b7e0a  jz      short loc_1400B7E1A
0x1400b7e0c  mov     rax, [rcx]
0x1400b7e0f  mov     rax, [rax+10h]
0x1400b7e13  call    cs:__guard_dispatch_icall_fptr
0x1400b7e19  nop
0x1400b7e1a  mov     edx, [rbp+57h+var_90]
0x1400b7e1d  mov     eax, edx
0x1400b7e1f  shr     eax, 19h
0x1400b7e22  test    al, 1
0x1400b7e24  jz      short loc_1400B7E96
0x1400b7e26  lea     rcx, [rbp+57h+var_98]
0x1400b7e2a  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400b7e30  jmp     short loc_1400B7E96
0x1400b7e32  xor     edx, edx
0x1400b7e34  mov     ecx, 65756F6Eh
0x1400b7e39  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400b7e3f  nop
0x1400b7e40  mov     rcx, [rbp+57h+var_40]
0x1400b7e44  test    rcx, rcx
0x1400b7e47  jz      short loc_1400B7E56
0x1400b7e49  mov     rax, [rcx]
0x1400b7e4c  mov     rax, [rax+10h]
0x1400b7e50  call    cs:__guard_dispatch_icall_fptr
0x1400b7e56  mov     [rbp+57h+var_40], r14
0x1400b7e5a  mov     rcx, [rbp+57h+var_A0]
0x1400b7e5e  test    rcx, rcx
0x1400b7e61  jz      short loc_1400B7E70
0x1400b7e63  mov     rax, [rcx]
0x1400b7e66  mov     rax, [rax+10h]
0x1400b7e6a  call    cs:__guard_dispatch_icall_fptr
0x1400b7e70  mov     edx, [rbp+57h+var_90]
0x1400b7e73  mov     eax, edx
0x1400b7e75  shr     eax, 19h
0x1400b7e78  test    al, 1
0x1400b7e7a  jz      short loc_1400B7E86
0x1400b7e7c  lea     rcx, [rbp+57h+var_98]
0x1400b7e80  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400b7e86  lea     rdx, psz
0x1400b7e8d  mov     rcx, rdi
0x1400b7e90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400b7e95  nop
0x1400b7e96  mov     rcx, [rbp+57h+var_80]
0x1400b7e9a  test    rcx, rcx
0x1400b7e9d  jz      short loc_1400B7EAC
0x1400b7e9f  mov     rax, [rcx]
0x1400b7ea2  mov     rax, [rax+10h]
0x1400b7ea6  call    cs:__guard_dispatch_icall_fptr
0x1400b7eac  mov     rax, rdi
0x1400b7eaf  mov     rcx, [rbp+57h+var_28]
0x1400b7eb3  xor     rcx, rsp; StackCookie
0x1400b7eb6  call    __security_check_cookie
0x1400b7ebb  add     rsp, 0A0h
0x1400b7ec2  pop     r14
0x1400b7ec4  pop     rdi
0x1400b7ec5  pop     rsi
0x1400b7ec6  pop     rbx
0x1400b7ec7  pop     rbp
0x1400b7ec8  retn
```
