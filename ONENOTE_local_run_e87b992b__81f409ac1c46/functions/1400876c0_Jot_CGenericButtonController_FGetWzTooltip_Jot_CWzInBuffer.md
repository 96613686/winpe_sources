# Jot::CGenericButtonController::FGetWzTooltip(Jot::CWzInBuffer &)

- ea: `0x1400876c0`
- end: `0x140087b8c`
- name: `?FGetWzTooltip@CGenericButtonController@Jot@@UEAA_NAEAVCWzInBuffer@2@@Z`
- size: `1228`
- prototype: `bool(Jot::CGenericButtonController *__hidden this, struct Jot::CWzInBuffer *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14003f250`
- `0x140041f58`
- `0x140048a58`
- `0x140054290`
- `0x140056ac0`
- `0x140057580`
- `0x1400876c0`
- `0x140088144`
- `0x140103288`

## import_xrefs

- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x140087960`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x140087960`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400877a8`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400877f4`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14008793e`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140087980`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400877a8`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400877f4`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14008793e`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140087980`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140087925`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140087925`
- `onmain!?priTcid@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140087a34`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x140087813`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x140087813`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x14008785d`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x14008785d`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x140087758`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x140087a22`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x140087a76`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x140087758`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x140087a22`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x140087a76`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140087952`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140087af4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140087b58`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140087b85`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140087952`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140087af4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140087b58`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140087b85`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Jot::CGenericButtonController::FGetWzTooltip(
        Jot::CGenericButtonController *this,
        struct Jot::CWzInBuffer *a2,
        struct MsoCF::IPropertySet *a3)
{
  __int64 *v3; // rdi
  char v6; // bl
  int v7; // ecx
  __int64 v8; // r8
  unsigned int v9; // r14d
  __int64 v10; // rax
  unsigned int v11; // ebx
  unsigned int v12; // edi
  __int64 v13; // rsi
  unsigned int Tcid; // eax
  bool v15; // bl
  MsoCF *v17; // rcx
  __int64 v18; // rbx
  struct MsoCF::IActionManager *v19; // rax
  unsigned int v20; // edx
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 v23; // rax
  const wchar_t *v24; // rdi
  bool v25; // zf
  const struct MsoCF::PropertyInfo *v26; // rbx
  unsigned int v27; // r14d
  __int64 v28; // rax
  unsigned int v29; // ebx
  unsigned int v30; // edi
  __int64 v31; // rsi
  unsigned int v32; // eax
  __int64 v33; // rcx
  int v34; // r8d
  __int64 v35; // rax
  struct MsoCF::IActionContext *v36; // [rsp+30h] [rbp-D0h]
  bool v37; // [rsp+38h] [rbp-C8h]
  __int64 *v38; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+48h] [rbp-B8h]
  unsigned int v40[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v44; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v45[368]; // [rsp+80h] [rbp-80h] BYREF

  v6 = 0;
  v38 = 0;
  v39 = 0;
  v7 = *(_DWORD *)(*((_QWORD *)this + 5) + 40LL);
  if ( v7 )
  {
    v44 = 0;
    v42 = 0;
    v41 = v7;
    MsoCF::CreatePropertySet((MsoCF *)&v42, 0, a3);
    v3 = v42;
    v44 = v42;
    (*(void (__fastcall **)(__int64 *))(*v42 + 8))(v42);
    MsoCF::AFrame::GetExecuteContext(*((_QWORD *)this + 4), &v43, *(unsigned int *)(*((_QWORD *)this + 5) + 20LL));
    if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 16LL) & 8) != 0 )
    {
      v40[0] = OfficeSpace::DataSourceBase::GetTcid(this);
      (*(void (__fastcall **)(__int64 *, _QWORD, unsigned int *))(*v3 + 56))(
        v3,
        Jot::PropertySpace_JotMain::priTcid,
        v40);
    }
    v18 = v43;
    v19 = MsoCF::TheActionManager(v17);
    if ( (*(unsigned __int8 (__fastcall **)(struct MsoCF::IActionManager *, int *, __int64, _QWORD))(*(_QWORD *)v19 + 168LL))(
           v19,
           &v41,
           v18,
           0) )
    {
      goto LABEL_33;
    }
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v42 )
      (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
    v42 = 0;
    if ( !v3 )
      goto LABEL_10;
    v21 = *v3;
    v22 = v3;
  }
  else
  {
    while ( 1 )
    {
      v8 = *((_QWORD *)this + 5);
      if ( *(_DWORD *)(v8 + 60) )
        break;
      if ( !v6 )
        goto LABEL_10;
      if ( v39 == 117899322 )
      {
        v3 = v38;
        if ( v38 )
        {
          v23 = (*((_DWORD *)v38 + 1) >> 1) & 0x1FFFFFFF;
          v24 = (const wchar_t *)(v38 + 1);
          if ( v38 != (__int64 *)-8LL
            && (!(_DWORD)v23 || (const wchar_t *)_std_find_trivial_2(v24, &v24[v23], 0) == &v24[v23]) )
          {
            CrashWithRecovery(0x1F46100Du, 0);
            JUMPOUT(0x140087B8BLL);
          }
          Jot::CWzInBuffer::CopyWz(a2, v24);
          v25 = (v39 & 0x2000000) == 0;
          goto LABEL_29;
        }
      }
      CrashWithRecovery(0x65756F6Eu, 0);
LABEL_33:
      v26 = MsoCF::LookupProperty((MsoCF *)*(unsigned int *)(*((_QWORD *)this + 5) + 44LL), v20);
      if ( (v39 & 0x2000000) != 0 )
        MsoCF::CPropertyData::FreeAndZero_ComplexType(&v38);
      else
        v38 = 0;
      if ( v3
        && (*(unsigned __int8 (__fastcall **)(__int64 *, const struct MsoCF::PropertyInfo *, __int64 **))(*v3 + 48))(
             v3,
             v26,
             &v38) )
      {
        v39 = *((_DWORD *)v26 + 1);
      }
      else
      {
        v39 = 0;
      }
      if ( v39 != 117899322 || (v6 = 1, !v38) )
        v6 = 0;
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      if ( v42 )
        (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
      v42 = 0;
      if ( v3 )
        (*(void (__fastcall **)(__int64 *))(*v3 + 16))(v3);
    }
    MsoCF::AFrame::GetExecuteContext(*((_QWORD *)this + 4), v40, *(unsigned int *)(v8 + 20));
    if ( !v6 )
    {
      v9 = v40[0];
      v10 = *((_QWORD *)this + 5);
      v11 = *(_DWORD *)(v10 + 64);
      v12 = *(_DWORD *)(v10 + 60);
      v13 = *((_QWORD *)this + 2);
      Tcid = OfficeSpace::DataSourceBase::GetTcid(this);
      LOBYTE(v36) = 0;
      v15 = Jot::FGetTooltipWithAccel(
              a2,
              (struct Jot::CWzInBuffer *)Tcid,
              v13,
              (struct OfficeSpace::IControl *)v12,
              v11,
              v9,
              v36,
              v37);
      if ( *(_QWORD *)v40 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
      if ( (v39 & 0x2000000) != 0 )
        MsoCF::CPropertyData::FreeAndZero_ComplexType(&v38);
      return v15;
    }
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v45);
    v27 = v40[0];
    v28 = *((_QWORD *)this + 5);
    v29 = *(_DWORD *)(v28 + 64);
    v30 = *(_DWORD *)(v28 + 60);
    v31 = *((_QWORD *)this + 2);
    v32 = OfficeSpace::DataSourceBase::GetTcid(this);
    LOBYTE(v36) = 1;
    if ( Jot::FGetTooltipWithAccel(
           (Jot *)v45,
           (struct Jot::CWzInBuffer *)v32,
           v31,
           (struct OfficeSpace::IControl *)v30,
           v29,
           v27,
           v36,
           v37) )
    {
      if ( v39 == 117899322 && v38 )
      {
        v35 = (*((_DWORD *)v38 + 1) >> 1) & 0x1FFFFFFF;
        v44 = v38 + 1;
        if ( v38 != (__int64 *)-8LL
          && (!(_DWORD)v35 || _std_find_trivial_2(v38 + 1, (char *)v38 + 2 * v35 + 8, 0) == v33 + 2 * v35) )
        {
          CrashWithRecovery(0x1F46100Du, 0);
          __debugbreak();
        }
        Jot::CWzInBuffer::SetFromPattern<MsoCF::String<MsoCF::WzTraits>,Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>>(
          (_DWORD)a2,
          *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
          v34,
          (unsigned int)&v44,
          (__int64)v45);
        Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v45);
        if ( *(_QWORD *)v40 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
        v25 = (v39 & 0x2000000) == 0;
LABEL_29:
        if ( !v25 )
          MsoCF::CPropertyData::FreeAndZero_ComplexType(&v38);
        return 1;
      }
      CrashWithRecovery(0x65756F6Eu, 0);
    }
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v45);
    v22 = *(__int64 **)v40;
    if ( !*(_QWORD *)v40 )
      goto LABEL_10;
    v21 = **(_QWORD **)v40;
  }
  (*(void (__fastcall **)(__int64 *))(v21 + 16))(v22);
LABEL_10:
  if ( (v39 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v38);
  return 0;
}

```

## disassembly

```asm
0x1400876c0  mov     [rsp-8+arg_10], rbx
0x1400876c5  push    rbp
0x1400876c6  push    rsi
0x1400876c7  push    rdi
0x1400876c8  push    r12
0x1400876ca  push    r13
0x1400876cc  push    r14
0x1400876ce  push    r15
0x1400876d0  lea     rbp, [rsp-100h]
0x1400876d8  sub     rsp, 200h
0x1400876df  mov     rax, cs:__security_cookie
0x1400876e6  xor     rax, rsp
0x1400876e9  mov     [rbp+130h+var_40], rax
0x1400876f0  mov     r12, rdx
0x1400876f3  mov     r15, rcx
0x1400876f6  xor     r13d, r13d
0x1400876f9  mov     bl, r13b
0x1400876fc  mov     [rsp+230h+var_1F0], r13
0x140087701  mov     [rsp+230h+var_1E8], r13d
0x140087706  mov     rax, [rcx+28h]
0x14008770a  mov     ecx, [rax+28h]
0x14008770d  mov     esi, 707003Ah
0x140087712  test    ecx, ecx
0x140087714  jnz     loc_1400877FE
0x14008771a  mov     r8, [r15+28h]
0x14008771e  cmp     [r8+3Ch], r13d
0x140087722  jz      loc_1400877DA
0x140087728  mov     r8d, [r8+14h]
0x14008772c  lea     rdx, [rsp+230h+var_1E0]
0x140087731  mov     rcx, [r15+20h]
0x140087735  call    ?GetExecuteContext@AFrame@MsoCF@@QEAA?AV?$CIPtr@UIActionContext@MsoCF@@U12@@2@W4FrameExecuteContextID@2@@Z; MsoCF::AFrame::GetExecuteContext(MsoCF::FrameExecuteContextID)
0x14008773a  test    bl, bl
0x14008773c  jnz     loc_140087A57
0x140087742  mov     r14, qword ptr [rsp+230h+var_1E0]
0x140087747  mov     rax, [r15+28h]
0x14008774b  mov     ebx, [rax+40h]
0x14008774e  mov     edi, [rax+3Ch]
0x140087751  mov     rsi, [r15+10h]
0x140087755  mov     rcx, r15
0x140087758  call    cs:__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ; OfficeSpace::DataSourceBase::GetTcid(void)
0x14008775e  mov     byte ptr [rsp+230h+var_200], r13b; struct MsoCF::IActionContext *
0x140087763  mov     qword ptr [rsp+230h+var_208], r14; unsigned int
0x140087768  mov     [rsp+230h+var_210], ebx; unsigned int
0x14008776c  mov     r9d, edi; struct OfficeSpace::IControl *
0x14008776f  mov     r8, rsi; int
0x140087772  mov     edx, eax; struct Jot::CWzInBuffer *
0x140087774  mov     rcx, r12; this
0x140087777  call    ?FGetTooltipWithAccel@Jot@@YA_NAEAVCWzInBuffer@1@HPEAUIControl@OfficeSpace@@IIPEAUIActionContext@MsoCF@@_N@Z; Jot::FGetTooltipWithAccel(Jot::CWzInBuffer &,int,OfficeSpace::IControl *,uint,uint,MsoCF::IActionContext *,bool)
0x14008777c  mov     bl, al
0x14008777e  mov     rcx, qword ptr [rsp+230h+var_1E0]
0x140087783  test    rcx, rcx
0x140087786  jz      short loc_140087796
0x140087788  mov     rax, [rcx]
0x14008778b  mov     rax, [rax+10h]
0x14008778f  call    cs:__guard_dispatch_icall_fptr
0x140087795  nop
0x140087796  mov     edx, [rsp+230h+var_1E8]
0x14008779a  mov     eax, edx
0x14008779c  shr     eax, 19h
0x14008779f  test    al, 1
0x1400877a1  jz      short loc_1400877AE
0x1400877a3  lea     rcx, [rsp+230h+var_1F0]
0x1400877a8  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400877ae  mov     al, bl
0x1400877b0  mov     rcx, [rbp+130h+var_40]
0x1400877b7  xor     rcx, rsp; StackCookie
0x1400877ba  call    __security_check_cookie
0x1400877bf  mov     rbx, [rsp+230h+arg_10]
0x1400877c7  add     rsp, 200h
0x1400877ce  pop     r15
0x1400877d0  pop     r14
0x1400877d2  pop     r13
0x1400877d4  pop     r12
0x1400877d6  pop     rdi
0x1400877d7  pop     rsi
0x1400877d8  pop     rbp
0x1400877d9  retn
0x1400877da  test    bl, bl
0x1400877dc  jnz     loc_1400878DB
0x1400877e2  mov     edx, [rsp+230h+var_1E8]
0x1400877e6  mov     eax, edx
0x1400877e8  shr     eax, 19h
0x1400877eb  test    al, 1
0x1400877ed  jz      short loc_1400877FA
0x1400877ef  lea     rcx, [rsp+230h+var_1F0]
0x1400877f4  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400877fa  xor     al, al
0x1400877fc  jmp     short loc_1400877B0
0x1400877fe  mov     [rsp+230h+var_1C0], r13
0x140087803  mov     [rsp+230h+var_1D0], r13
0x140087808  mov     [rsp+230h+var_1D8], ecx
0x14008780c  xor     edx, edx
0x14008780e  lea     rcx, [rsp+230h+var_1D0]
0x140087813  call    cs:__imp_?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet * *,MsoCF::IPropertySet *)
0x140087819  mov     rdi, [rsp+230h+var_1D0]
0x14008781e  mov     [rsp+230h+var_1C0], rdi
0x140087823  mov     rax, [rdi]
0x140087826  mov     rcx, rdi
0x140087829  mov     rax, [rax+8]
0x14008782d  call    cs:__guard_dispatch_icall_fptr
0x140087833  mov     rax, [r15+28h]
0x140087837  mov     r8d, [rax+14h]
0x14008783b  lea     rdx, [rsp+230h+var_1C8]
0x140087840  mov     rcx, [r15+20h]
0x140087844  call    ?GetExecuteContext@AFrame@MsoCF@@QEAA?AV?$CIPtr@UIActionContext@MsoCF@@U12@@2@W4FrameExecuteContextID@2@@Z; MsoCF::AFrame::GetExecuteContext(MsoCF::FrameExecuteContextID)
0x140087849  nop
0x14008784a  mov     rax, [r15+28h]
0x14008784e  test    byte ptr [rax+10h], 8
0x140087852  jnz     loc_140087A1F
0x140087858  mov     rbx, [rsp+230h+var_1C8]
0x14008785d  call    cs:__imp_?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ; MsoCF::TheActionManager(void)
0x140087863  mov     rcx, rax
0x140087866  mov     rax, [rax]
0x140087869  xor     r9d, r9d
0x14008786c  mov     r8, rbx
0x14008786f  lea     rdx, [rsp+230h+var_1D8]
0x140087874  mov     rax, [rax+0A8h]
0x14008787b  call    cs:__guard_dispatch_icall_fptr
0x140087881  test    al, al
0x140087883  jnz     loc_140087959
0x140087889  mov     rcx, [rsp+230h+var_1C8]
0x14008788e  test    rcx, rcx
0x140087891  jz      short loc_1400878A1
0x140087893  mov     rax, [rcx]
0x140087896  mov     rax, [rax+10h]
0x14008789a  call    cs:__guard_dispatch_icall_fptr
0x1400878a0  nop
0x1400878a1  mov     rcx, [rsp+230h+var_1D0]
0x1400878a6  test    rcx, rcx
0x1400878a9  jz      short loc_1400878B8
0x1400878ab  mov     rax, [rcx]
0x1400878ae  mov     rax, [rax+10h]
0x1400878b2  call    cs:__guard_dispatch_icall_fptr
0x1400878b8  mov     [rsp+230h+var_1D0], r13
0x1400878bd  test    rdi, rdi
0x1400878c0  jz      loc_1400877E2
0x1400878c6  mov     rax, [rdi]
0x1400878c9  mov     rcx, rdi
0x1400878cc  mov     rax, [rax+10h]
0x1400878d0  call    cs:__guard_dispatch_icall_fptr
0x1400878d6  jmp     loc_1400877E2
0x1400878db  cmp     [rsp+230h+var_1E8], esi
0x1400878df  jnz     short loc_14008794B
0x1400878e1  mov     rdi, [rsp+230h+var_1F0]
0x1400878e6  test    rdi, rdi
0x1400878e9  jz      short loc_14008794B
0x1400878eb  mov     eax, [rdi+4]
0x1400878ee  shr     eax, 1
0x1400878f0  and     eax, 1FFFFFFFh
0x1400878f5  add     rdi, 8
0x1400878f9  jz      short loc_14008791F
0x1400878fb  cmp     eax, 1
0x1400878fe  jb      loc_140087B7E
0x140087904  lea     rbx, [rdi+rax*2]
0x140087908  xor     r8d, r8d
0x14008790b  mov     rdx, rbx
0x14008790e  mov     rcx, rdi
0x140087911  call    __std_find_trivial_2
0x140087916  cmp     rax, rbx
0x140087919  jz      loc_140087B7E
0x14008791f  mov     rdx, rdi
0x140087922  mov     rcx, r12
0x140087925  call    cs:__imp_?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x14008792b  mov     edx, [rsp+230h+var_1E8]
0x14008792f  mov     ecx, edx
0x140087931  shr     ecx, 19h
0x140087934  test    cl, 1
0x140087937  jz      short loc_140087944
0x140087939  lea     rcx, [rsp+230h+var_1F0]
0x14008793e  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140087944  mov     al, 1
0x140087946  jmp     loc_1400877B0
0x14008794b  xor     edx, edx
0x14008794d  mov     ecx, 65756F6Eh
0x140087952  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140087958  nop
0x140087959  mov     rax, [r15+28h]
0x14008795d  mov     ecx, [rax+2Ch]
0x140087960  call    cs:__imp_?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z; MsoCF::LookupProperty(uint)
0x140087966  mov     rbx, rax
0x140087969  mov     edx, [rsp+230h+var_1E8]
0x14008796d  mov     ecx, edx
0x14008796f  shr     ecx, 19h
0x140087972  test    cl, 1
0x140087975  jz      loc_140087A4D
0x14008797b  lea     rcx, [rsp+230h+var_1F0]
0x140087980  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140087986  test    rdi, rdi
0x140087989  jz      loc_140087A18
0x14008798f  mov     rax, [rdi]
0x140087992  lea     r8, [rsp+230h+var_1F0]
0x140087997  mov     rdx, rbx
0x14008799a  mov     rcx, rdi
0x14008799d  mov     rax, [rax+30h]
0x1400879a1  call    cs:__guard_dispatch_icall_fptr
0x1400879a7  test    al, al
0x1400879a9  jz      short loc_140087A18
0x1400879ab  mov     eax, [rbx+4]
0x1400879ae  mov     [rsp+230h+var_1E8], eax
0x1400879b2  cmp     [rsp+230h+var_1E8], esi
0x1400879b6  jnz     short loc_140087A13
0x1400879b8  cmp     [rsp+230h+var_1F0], r13
0x1400879bd  mov     bl, 1
0x1400879bf  jz      short loc_140087A13
0x1400879c1  mov     rcx, [rsp+230h+var_1C8]
0x1400879c6  test    rcx, rcx
0x1400879c9  jz      short loc_1400879D9
0x1400879cb  mov     rax, [rcx]
0x1400879ce  mov     rax, [rax+10h]
0x1400879d2  call    cs:__guard_dispatch_icall_fptr
0x1400879d8  nop
0x1400879d9  mov     rcx, [rsp+230h+var_1D0]
0x1400879de  test    rcx, rcx
0x1400879e1  jz      short loc_1400879F0
0x1400879e3  mov     rax, [rcx]
0x1400879e6  mov     rax, [rax+10h]
0x1400879ea  call    cs:__guard_dispatch_icall_fptr
0x1400879f0  mov     [rsp+230h+var_1D0], r13
0x1400879f5  test    rdi, rdi
0x1400879f8  jz      loc_14008771A
0x1400879fe  mov     rax, [rdi]
0x140087a01  mov     rcx, rdi
0x140087a04  mov     rax, [rax+10h]
0x140087a08  call    cs:__guard_dispatch_icall_fptr
0x140087a0e  jmp     loc_14008771A
0x140087a13  mov     bl, r13b
0x140087a16  jmp     short loc_1400879C1
0x140087a18  mov     [rsp+230h+var_1E8], r13d
0x140087a1d  jmp     short loc_1400879B2
0x140087a1f  mov     rcx, r15
0x140087a22  call    cs:__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ; OfficeSpace::DataSourceBase::GetTcid(void)
0x140087a28  mov     [rsp+230h+var_1E0], eax
0x140087a2c  mov     rax, [rdi]
0x140087a2f  lea     r8, [rsp+230h+var_1E0]
0x140087a34  mov     rdx, cs:__imp_?priTcid@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priTcid
0x140087a3b  mov     rcx, rdi
0x140087a3e  mov     rax, [rax+38h]
0x140087a42  call    cs:__guard_dispatch_icall_fptr
0x140087a48  jmp     loc_140087858
0x140087a4d  mov     [rsp+230h+var_1F0], r13
0x140087a52  jmp     loc_140087986
0x140087a57  lea     rcx, [rbp+130h+var_1B0]
0x140087a5b  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x140087a60  mov     r14, qword ptr [rsp+230h+var_1E0]
0x140087a65  mov     rax, [r15+28h]
0x140087a69  mov     ebx, [rax+40h]
0x140087a6c  mov     edi, [rax+3Ch]
0x140087a6f  mov     rsi, [r15+10h]
0x140087a73  mov     rcx, r15
0x140087a76  call    cs:__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ; OfficeSpace::DataSourceBase::GetTcid(void)
0x140087a7c  mov     byte ptr [rsp+230h+var_200], 1; struct MsoCF::IActionContext *
0x140087a81  mov     qword ptr [rsp+230h+var_208], r14; unsigned int
0x140087a86  mov     [rsp+230h+var_210], ebx; unsigned int
0x140087a8a  mov     r9d, edi; struct OfficeSpace::IControl *
0x140087a8d  mov     r8, rsi; int
0x140087a90  mov     edx, eax; struct Jot::CWzInBuffer *
0x140087a92  lea     rcx, [rbp+130h+var_1B0]; this
0x140087a96  call    ?FGetTooltipWithAccel@Jot@@YA_NAEAVCWzInBuffer@1@HPEAUIControl@OfficeSpace@@IIPEAUIActionContext@MsoCF@@_N@Z; Jot::FGetTooltipWithAccel(Jot::CWzInBuffer &,int,OfficeSpace::IControl *,uint,uint,MsoCF::IActionContext *,bool)
0x140087a9b  test    al, al
0x140087a9d  jz      loc_140087B5F
0x140087aa3  cmp     [rsp+230h+var_1E8], 707003Ah
0x140087aab  jnz     loc_140087B51
0x140087ab1  mov     rcx, [rsp+230h+var_1F0]
0x140087ab6  test    rcx, rcx
0x140087ab9  jz      loc_140087B51
0x140087abf  mov     eax, [rcx+4]
0x140087ac2  shr     eax, 1
0x140087ac4  and     eax, 1FFFFFFFh
0x140087ac9  add     rcx, 8
0x140087acd  mov     [rsp+230h+var_1C0], rcx
0x140087ad2  jz      short loc_140087AFB
0x140087ad4  cmp     eax, 1
0x140087ad7  jb      short loc_140087AED
0x140087ad9  lea     rbx, [rcx+rax*2]
0x140087add  xor     r8d, r8d
0x140087ae0  mov     rdx, rbx
0x140087ae3  call    __std_find_trivial_2
0x140087ae8  cmp     rax, rbx
0x140087aeb  jnz     short loc_140087AFB
0x140087aed  xor     edx, edx
0x140087aef  mov     ecx, 1F46100Dh
0x140087af4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140087afa  int     3; Trap to Debugger
0x140087afb  mov     rax, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x140087b02  lea     rcx, [rbp+130h+var_1B0]
0x140087b06  mov     qword ptr [rsp+230h+var_210], rcx
0x140087b0b  lea     r9, [rsp+230h+var_1C0]
0x140087b10  mov     rdx, [rax+1F0h]
0x140087b17  mov     rcx, r12
0x140087b1a  call    ??$SetFromPattern@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@IAEBV?$String@UWzTraits@MsoCF@@@MsoCF@@AEBV?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@1@@Z; Jot::CWzInBuffer::SetFromPattern<MsoCF::String<MsoCF::WzTraits>,Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>>(HINSTANCE__ *,uint,MsoCF::String<MsoCF::WzTraits> const &,Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128> const &)
0x140087b1f  nop
0x140087b20  lea     rcx, [rbp+130h+var_1B0]
0x140087b24  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x140087b29  mov     rcx, qword ptr [rsp+230h+var_1E0]
0x140087b2e  test    rcx, rcx
0x140087b31  jz      short loc_140087B41
0x140087b33  mov     rax, [rcx]
0x140087b36  mov     rax, [rax+10h]
0x140087b3a  call    cs:__guard_dispatch_icall_fptr
0x140087b40  nop
  ... truncated ...
```
