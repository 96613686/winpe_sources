# Jot::CHyperlinkDialogListener::GetLinkFromClipboard(Jot::CWzInBuffer &,Jot::CWzInBuffer &,_GUID *)

- ea: `0x140085618`
- end: `0x14008586e`
- name: `?GetLinkFromClipboard@CHyperlinkDialogListener@Jot@@AEAAXAEAVCWzInBuffer@2@0PEAU_GUID@@@Z`
- size: `598`
- prototype: `void __fastcall(Jot::CHyperlinkDialogListener *__hidden this, struct Jot::CWzInBuffer *, struct Jot::CWzInBuffer *, struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140085290`
- `0x140118fd0`

## callees

- `0x140054290`
- `0x140057580`
- `0x140085618`
- `0x140085870`
- `0x14008708c`
- `0x1400d0768`
- `0x1400e4560`
- `0x1400f2a18`

## import_xrefs

- `onmain!?priFriendlyText@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14008579a`
- `onmain!?priClipboardLinkID@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140085696`
- `onmain!?priWzLink@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14008570c`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400856a0`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140085716`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400857a4`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400856a0`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140085716`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400857a4`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140085819`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140085830`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140085847`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140085819`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140085830`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140085847`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140085779`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140085803`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140085779`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140085803`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14008576c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400857f6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14008576c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400857f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Jot::CHyperlinkDialogListener::GetLinkFromClipboard(
        Jot::CBaseRootElement **this,
        struct Jot::CWzInBuffer *a2,
        struct Jot::CWzInBuffer *a3,
        struct _GUID *a4)
{
  struct MsoCF::AFrame *v8; // rdi
  void (__fastcall *v9)(struct MsoCF::AFrame *, __int64, struct MsoCF::IPropertySet *, __int64); // rbx
  struct MsoCF::IPropertySet *v10; // rax
  MsoCF::IPropertySet *v11; // rax
  __int64 v12; // rax
  const char *v13; // rdx
  MsoCF::IPropertySet *v14; // rax
  __int64 v15; // rax
  const wchar_t *v16; // rdi
  __int64 v17; // rbx
  MsoCF::IPropertySet *v18; // rax
  int v19; // edx
  __int64 v20; // rax
  const wchar_t *v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // [rsp+30h] [rbp-50h] BYREF
  int v24; // [rsp+38h] [rbp-48h]
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  int v26; // [rsp+48h] [rbp-38h]
  __int64 v27; // [rsp+50h] [rbp-30h] BYREF
  int v28; // [rsp+58h] [rbp-28h]
  _BYTE pExceptionObject[32]; // [rsp+60h] [rbp-20h] BYREF

  v8 = Jot::CBaseRootElement::UseFrame(this[5]);
  v9 = *(void (__fastcall **)(struct MsoCF::AFrame *, __int64, struct MsoCF::IPropertySet *, __int64))(*(_QWORD *)v8 + 64LL);
  v10 = Jot::CHyperlinkDialogListener::UseActionPropertySet((Jot::CHyperlinkDialogListener *)this);
  v9(v8, 132181, v10, 1);
  v23 = 0;
  v24 = 0;
  v11 = Jot::CHyperlinkDialogListener::UseActionPropertySet((Jot::CHyperlinkDialogListener *)this);
  MsoCF::IPropertySet::GetProperty(
    v11,
    Jot::PropertySpace_JotMain::priClipboardLinkID,
    (struct MsoCF::CPropertyValue *)&v23);
  if ( v23 && v24 == 117899327 )
  {
    v12 = MsoCF::CPropertyValue::UseAtom(&v23, 117899327);
    if ( (*(_DWORD *)(v12 + 4) & 0x3FFFFFFFu) < 0x10 )
    {
      std::length_error::length_error((std::length_error *)pExceptionObject, v13);
      throw (std::length_error *)pExceptionObject;
    }
    *a4 = *(struct _GUID *)(v12 + 8);
  }
  v27 = 0;
  v28 = 0;
  v14 = Jot::CHyperlinkDialogListener::UseActionPropertySet((Jot::CHyperlinkDialogListener *)this);
  MsoCF::IPropertySet::GetProperty(v14, Jot::PropertySpace_JotMain::priWzLink, (struct MsoCF::CPropertyValue *)&v27);
  if ( v28 == 117899322 && v27 )
  {
    v15 = (*(_DWORD *)(v27 + 4) >> 1) & 0x1FFFFFFF;
    v16 = (const wchar_t *)(v27 + 8);
    if ( v27 != -8 )
    {
      if ( !(_DWORD)v15 || (v17 = v27 + 8 + 2 * v15, _std_find_trivial_2(v27 + 8, v17, 0) == v17) )
      {
        CrashWithRecovery(0x1F46100Du, 0);
        __debugbreak();
      }
    }
    Jot::CWzInBuffer::CopyWz(a2, v16);
  }
  v25 = 0;
  v26 = 0;
  v18 = Jot::CHyperlinkDialogListener::UseActionPropertySet((Jot::CHyperlinkDialogListener *)this);
  MsoCF::IPropertySet::GetProperty(
    v18,
    Jot::PropertySpace_JotMain::priFriendlyText,
    (struct MsoCF::CPropertyValue *)&v25);
  v19 = v26;
  if ( v26 == 117899322 && v25 )
  {
    v20 = (*(_DWORD *)(v25 + 4) >> 1) & 0x1FFFFFFF;
    v21 = (const wchar_t *)(v25 + 8);
    if ( v25 != -8 )
    {
      if ( !(_DWORD)v20 || (v22 = v25 + 8 + 2 * v20, _std_find_trivial_2(v25 + 8, v22, 0) == v22) )
      {
        CrashWithRecovery(0x1F46100Du, 0);
        __debugbreak();
      }
    }
    Jot::CWzInBuffer::CopyWz(a3, v21);
    v19 = v26;
  }
  if ( (v19 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v25);
  if ( (v28 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v27);
  if ( (v24 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v23);
}

```

## disassembly

```asm
0x140085618  mov     rax, rsp
0x14008561b  mov     [rax+8], rbx
0x14008561f  mov     [rax+10h], rsi
0x140085623  mov     [rax+18h], rdi
0x140085627  mov     [rax+20h], r12
0x14008562b  push    rbp
0x14008562c  push    r14
0x14008562e  push    r15
0x140085630  mov     rbp, rsp
0x140085633  sub     rsp, 80h
0x14008563a  mov     r14, r9
0x14008563d  mov     r12, r8
0x140085640  mov     r15, rdx
0x140085643  mov     rsi, rcx
0x140085646  mov     rcx, [rcx+28h]; this
0x14008564a  call    ?UseFrame@CBaseRootElement@Jot@@QEAAPEAUAFrame@MsoCF@@XZ; Jot::CBaseRootElement::UseFrame(void)
0x14008564f  mov     rdi, rax
0x140085652  mov     r10, [rax]
0x140085655  mov     rbx, [r10+40h]
0x140085659  mov     rcx, rsi; this
0x14008565c  call    ?UseActionPropertySet@CHyperlinkDialogListener@Jot@@AEAAPEAUIPropertySet@MsoCF@@XZ; Jot::CHyperlinkDialogListener::UseActionPropertySet(void)
0x140085661  mov     r9d, 1
0x140085667  mov     r8, rax
0x14008566a  mov     edx, 20455h
0x14008566f  mov     rcx, rdi
0x140085672  mov     rax, rbx
0x140085675  call    cs:__guard_dispatch_icall_fptr
0x14008567b  mov     [rbp+var_50], 0
0x140085683  mov     [rbp+var_48], 0
0x14008568a  mov     rcx, rsi; this
0x14008568d  call    ?UseActionPropertySet@CHyperlinkDialogListener@Jot@@AEAAPEAUIPropertySet@MsoCF@@XZ; Jot::CHyperlinkDialogListener::UseActionPropertySet(void)
0x140085692  lea     r8, [rbp+var_50]
0x140085696  mov     rdx, cs:__imp_?priClipboardLinkID@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priClipboardLinkID
0x14008569d  mov     rcx, rax
0x1400856a0  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400856a6  mov     edx, 707003Fh
0x1400856ab  cmp     [rbp+var_50], 0
0x1400856b0  jz      short loc_1400856F1
0x1400856b2  cmp     [rbp+var_48], edx
0x1400856b5  jnz     short loc_1400856F1
0x1400856b7  lea     rcx, [rbp+var_50]
0x1400856bb  call    ?UseAtom@CPropertyValue@MsoCF@@QEBAPEAVIAtom@2@W4PropertyType@2@@Z; MsoCF::CPropertyValue::UseAtom(MsoCF::PropertyType)
0x1400856c0  mov     ecx, [rax+4]
0x1400856c3  and     ecx, 3FFFFFFFh
0x1400856c9  cmp     ecx, 10h
0x1400856cc  jnb     short loc_1400856E8
0x1400856ce  lea     rcx, [rbp+pExceptionObject]; this
0x1400856d2  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1400856d7  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1400856de  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400856e2  call    _CxxThrowException_0
0x1400856e8  movups  xmm0, xmmword ptr [rax+8]
0x1400856ec  movdqu  xmmword ptr [r14], xmm0
0x1400856f1  mov     [rbp+var_30], 0
0x1400856f9  mov     [rbp+var_28], 0
0x140085700  mov     rcx, rsi; this
0x140085703  call    ?UseActionPropertySet@CHyperlinkDialogListener@Jot@@AEAAPEAUIPropertySet@MsoCF@@XZ; Jot::CHyperlinkDialogListener::UseActionPropertySet(void)
0x140085708  lea     r8, [rbp+var_30]
0x14008570c  mov     rdx, cs:__imp_?priWzLink@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priWzLink
0x140085713  mov     rcx, rax
0x140085716  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x14008571c  mov     r14d, 1FFFFFFFh
0x140085722  cmp     [rbp+var_28], 707003Ah
0x140085729  jnz     short loc_14008577F
0x14008572b  mov     rcx, [rbp+var_30]
0x14008572f  test    rcx, rcx
0x140085732  jz      short loc_14008577F
0x140085734  mov     eax, [rcx+4]
0x140085737  shr     eax, 1
0x140085739  and     eax, r14d
0x14008573c  lea     rdi, [rcx+8]
0x140085740  test    rdi, rdi
0x140085743  jz      short loc_140085773
0x140085745  cmp     eax, 1
0x140085748  jb      short loc_140085765
0x14008574a  add     rcx, 8
0x14008574e  lea     rbx, [rcx+rax*2]
0x140085752  xor     r8d, r8d
0x140085755  mov     rdx, rbx
0x140085758  mov     rcx, rdi
0x14008575b  call    __std_find_trivial_2
0x140085760  cmp     rax, rbx
0x140085763  jnz     short loc_140085773
0x140085765  xor     edx, edx
0x140085767  mov     ecx, 1F46100Dh
0x14008576c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140085772  int     3; Trap to Debugger
0x140085773  mov     rdx, rdi
0x140085776  mov     rcx, r15
0x140085779  call    cs:__imp_?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x14008577f  mov     [rbp+var_40], 0
0x140085787  mov     [rbp+var_38], 0
0x14008578e  mov     rcx, rsi; this
0x140085791  call    ?UseActionPropertySet@CHyperlinkDialogListener@Jot@@AEAAPEAUIPropertySet@MsoCF@@XZ; Jot::CHyperlinkDialogListener::UseActionPropertySet(void)
0x140085796  lea     r8, [rbp+var_40]
0x14008579a  mov     rdx, cs:__imp_?priFriendlyText@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priFriendlyText
0x1400857a1  mov     rcx, rax
0x1400857a4  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400857aa  mov     edx, [rbp+var_38]
0x1400857ad  cmp     edx, 707003Ah
0x1400857b3  jnz     short loc_14008580C
0x1400857b5  mov     rcx, [rbp+var_40]
0x1400857b9  test    rcx, rcx
0x1400857bc  jz      short loc_14008580C
0x1400857be  mov     eax, [rcx+4]
0x1400857c1  shr     eax, 1
0x1400857c3  and     eax, r14d
0x1400857c6  lea     rdi, [rcx+8]
0x1400857ca  test    rdi, rdi
0x1400857cd  jz      short loc_1400857FD
0x1400857cf  cmp     eax, 1
0x1400857d2  jb      short loc_1400857EF
0x1400857d4  add     rcx, 8
0x1400857d8  lea     rbx, [rcx+rax*2]
0x1400857dc  xor     r8d, r8d
0x1400857df  mov     rdx, rbx
0x1400857e2  mov     rcx, rdi
0x1400857e5  call    __std_find_trivial_2
0x1400857ea  cmp     rax, rbx
0x1400857ed  jnz     short loc_1400857FD
0x1400857ef  xor     edx, edx
0x1400857f1  mov     ecx, 1F46100Dh
0x1400857f6  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400857fc  int     3; Trap to Debugger
0x1400857fd  mov     rdx, rdi
0x140085800  mov     rcx, r12
0x140085803  call    cs:__imp_?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x140085809  mov     edx, [rbp+var_38]
0x14008580c  mov     eax, edx
0x14008580e  shr     eax, 19h
0x140085811  test    al, 1
0x140085813  jz      short loc_140085820
0x140085815  lea     rcx, [rbp+var_40]
0x140085819  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14008581f  nop
0x140085820  mov     edx, [rbp+var_28]
0x140085823  mov     eax, edx
0x140085825  shr     eax, 19h
0x140085828  test    al, 1
0x14008582a  jz      short loc_140085837
0x14008582c  lea     rcx, [rbp+var_30]
0x140085830  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140085836  nop
0x140085837  mov     edx, [rbp+var_48]
0x14008583a  mov     eax, edx
0x14008583c  shr     eax, 19h
0x14008583f  test    al, 1
0x140085841  jz      short loc_14008584D
0x140085843  lea     rcx, [rbp+var_50]
0x140085847  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14008584d  lea     r11, [rsp+80h+var_s0]
0x140085855  mov     rbx, [r11+20h]
0x140085859  mov     rsi, [r11+28h]
0x14008585d  mov     rdi, [r11+30h]
0x140085861  mov     r12, [r11+38h]
0x140085865  mov     rsp, r11
0x140085868  pop     r15
0x14008586a  pop     r14
0x14008586c  pop     rbp
0x14008586d  retn
```
