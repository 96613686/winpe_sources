# Jot::CNoteFlagGalleryUser::GetNoteTagProperties(ulong *,ulong *,int *)

- ea: `0x1400aa278`
- end: `0x1400aa5f9`
- name: `?GetNoteTagProperties@CNoteFlagGalleryUser@Jot@@AEAAXPEAK0PEAH@Z`
- size: `897`
- prototype: `void __fastcall(Jot::CNoteFlagGalleryUser *__hidden this, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14008c0f0`

## callees

- `0x140052c10`
- `0x140057580`
- `0x14009b1a0`
- `0x1400a9cc4`
- `0x1400aa278`

## import_xrefs

- `onmain!?priNoteTagResource@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400aa4f6`
- `onmain!?priHighlight@PropertySpace_Jot11@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400aa571`
- `onmain!?priFontColor@PropertySpace_Jot11@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400aa4c0`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400aa4cb`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400aa501`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400aa57c`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400aa4cb`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400aa501`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400aa57c`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400aa3e2`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400aa3e2`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x1400aa2e4`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x1400aa403`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x1400aa52f`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x1400aa2e4`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x1400aa403`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x1400aa52f`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x1400aa311`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x1400aa33f`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x1400aa42f`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x1400aa311`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x1400aa33f`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x1400aa42f`
- `USER32!GetSysColor` at `0x1400aa4af`
- `USER32!GetSysColor` at `0x1400aa4af`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400aa4e1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400aa517`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400aa592`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400aa4e1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400aa517`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400aa592`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Jot::CNoteFlagGalleryUser::GetNoteTagProperties(
        Jot::CNoteFlagGalleryUser *this,
        unsigned int *a2,
        unsigned int *a3,
        int *a4)
{
  char v7; // di
  MsoCF *v8; // rcx
  struct MsoCF::IActionContext *v9; // rbx
  struct MsoCF::IActionManager *v10; // rax
  MsoCF *v11; // rcx
  struct MsoCF::IActionContext *v12; // rbx
  struct MsoCF::IActionManager *v13; // rax
  int v14; // eax
  MsoCF *v15; // rcx
  struct MsoCF::IActionContext *v16; // rbx
  struct MsoCF::IActionManager *v17; // rax
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  int v19; // [rsp+38h] [rbp-18h]
  int v20; // [rsp+40h] [rbp-10h] BYREF
  struct MsoCF::IPropertySet *v21; // [rsp+48h] [rbp-8h]
  struct MsoCF::IActionContext *v22; // [rsp+70h] [rbp+20h] BYREF
  struct MsoCF::IPropertySet *v23; // [rsp+78h] [rbp+28h] BYREF

  v18 = 0;
  v19 = 0;
  v7 = 0;
  v22 = 0;
  (*(void (__fastcall **)(_QWORD, struct MsoCF::IActionContext **))(**(_QWORD **)(*((_QWORD *)this + 31) + 104LL) + 80LL))(
    *(_QWORD *)(*((_QWORD *)this + 31) + 104LL),
    &v22);
  if ( a2 )
  {
    MsoCF::CreatePropertySet(&v23, 0);
    MsoCF::CActionPropertySet::CActionPropertySet((MsoCF::CActionPropertySet *)&v20, 0x20219u, v23);
    if ( MsoCF::CActionPropertySet::CanExecute((MsoCF::CActionPropertySet *)&v20, v22)
      && (v7 = MsoCF::CActionPropertySet::Execute((MsoCF::CActionPropertySet *)&v20, v22)) != 0 )
    {
      MsoCF::IPropertySet::GetProperty(
        v23,
        Jot::PropertySpace_Jot11::priHighlight,
        (struct MsoCF::CPropertyValue *)&v18);
      if ( v19 != 8716326 )
      {
        CrashWithRecovery(0x65756E71u, 0);
        __debugbreak();
      }
      *a2 = v18;
    }
    else
    {
      *a2 = -1;
    }
    if ( v21 )
      (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
    if ( v23 )
      (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( a3 )
  {
    MsoCF::CreatePropertySet(&v23, 0);
    v20 = 131595;
    v8 = v23;
    v21 = v23;
    if ( v23 )
      (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v23 + 8LL))(v23);
    v9 = v22;
    v10 = MsoCF::TheActionManager(v8);
    if ( (*(unsigned __int8 (__fastcall **)(struct MsoCF::IActionManager *, int *, struct MsoCF::IActionContext *, _QWORD))(*(_QWORD *)v10 + 176LL))(
           v10,
           &v20,
           v9,
           0) )
    {
      v12 = v22;
      v13 = MsoCF::TheActionManager(v11);
      v7 = (*(__int64 (__fastcall **)(struct MsoCF::IActionManager *, int *, struct MsoCF::IActionContext *, _QWORD))(*(_QWORD *)v13 + 168LL))(
             v13,
             &v20,
             v12,
             0);
    }
    if ( v7 )
    {
      MsoCF::IPropertySet::GetProperty(
        v23,
        Jot::PropertySpace_Jot11::priFontColor,
        (struct MsoCF::CPropertyValue *)&v18);
      if ( v19 != 8716326 )
      {
        CrashWithRecovery(0x65756E71u, 0);
        __debugbreak();
      }
      v14 = v18;
      *a3 = v18;
    }
    else
    {
      *a3 = -16777216;
      v14 = -16777216;
    }
    if ( v14 == -16777216 )
      *a3 = GetSysColor(8);
    if ( v21 )
      (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
    if ( v23 )
      (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( a4 )
  {
    MsoCF::CreatePropertySet(&v23, 0);
    v20 = 131608;
    v15 = v23;
    v21 = v23;
    if ( v23 )
      (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v23 + 8LL))(v23);
    v16 = v22;
    v17 = MsoCF::TheActionManager(v15);
    if ( (*(unsigned __int8 (__fastcall **)(struct MsoCF::IActionManager *, int *, struct MsoCF::IActionContext *, _QWORD))(*(_QWORD *)v17 + 176LL))(
           v17,
           &v20,
           v16,
           0) )
    {
      v7 = MsoCF::CActionPropertySet::Execute((MsoCF::CActionPropertySet *)&v20, v22);
    }
    if ( v7 )
    {
      MsoCF::IPropertySet::GetProperty(
        v23,
        Jot::PropertySpace_JotMain::priNoteTagResource,
        (struct MsoCF::CPropertyValue *)&v18);
      if ( v19 != 8716322 )
      {
        CrashWithRecovery(0x65756E71u, 0);
        __debugbreak();
      }
      *a4 = v18;
    }
    else
    {
      *a4 = -1;
    }
    if ( v21 )
      (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
    if ( v23 )
      (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( v22 )
    (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v22 + 16LL))(v22);
  if ( (v19 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v18);
}

```

## disassembly

```asm
0x1400aa278  mov     [rsp-18h+arg_10], rbx
0x1400aa27d  mov     [rsp-18h+arg_18], rsi
0x1400aa282  push    rbp
0x1400aa283  push    rdi
0x1400aa284  push    r14
0x1400aa286  mov     rbp, rsp
0x1400aa289  sub     rsp, 50h
0x1400aa28d  mov     r14, r9
0x1400aa290  mov     rsi, r8
0x1400aa293  mov     rbx, rdx
0x1400aa296  mov     [rbp+var_20], 0
0x1400aa29e  mov     [rbp+var_18], 0
0x1400aa2a5  xor     dil, dil
0x1400aa2a8  mov     [rbp+arg_0], 0
0x1400aa2b0  mov     rax, [rcx+0F8h]
0x1400aa2b7  mov     rcx, [rax+68h]
0x1400aa2bb  mov     rax, [rcx]
0x1400aa2be  lea     rdx, [rbp+arg_0]
0x1400aa2c2  mov     rax, [rax+50h]
0x1400aa2c6  call    cs:__guard_dispatch_icall_fptr
0x1400aa2cc  test    rbx, rbx
0x1400aa2cf  jnz     loc_1400AA529
0x1400aa2d5  test    rsi, rsi
0x1400aa2d8  jz      loc_1400AA3B6
0x1400aa2de  xor     edx, edx
0x1400aa2e0  lea     rcx, [rbp+arg_8]
0x1400aa2e4  call    cs:__imp_?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet *)
0x1400aa2ea  nop
0x1400aa2eb  mov     [rbp+var_10], 2020Bh
0x1400aa2f2  mov     rcx, [rbp+arg_8]
0x1400aa2f6  mov     [rbp+var_8], rcx
0x1400aa2fa  test    rcx, rcx
0x1400aa2fd  jz      short loc_1400AA30D
0x1400aa2ff  mov     rax, [rcx]
0x1400aa302  mov     rax, [rax+8]
0x1400aa306  call    cs:__guard_dispatch_icall_fptr
0x1400aa30c  nop
0x1400aa30d  mov     rbx, [rbp+arg_0]
0x1400aa311  call    cs:__imp_?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ; MsoCF::TheActionManager(void)
0x1400aa317  mov     r10, rax
0x1400aa31a  mov     rcx, [rax]
0x1400aa31d  mov     rax, [rcx+0B0h]
0x1400aa324  xor     r9d, r9d
0x1400aa327  mov     r8, rbx
0x1400aa32a  lea     rdx, [rbp+var_10]
0x1400aa32e  mov     rcx, r10
0x1400aa331  call    cs:__guard_dispatch_icall_fptr
0x1400aa337  test    al, al
0x1400aa339  jz      short loc_1400AA368
0x1400aa33b  mov     rbx, [rbp+arg_0]
0x1400aa33f  call    cs:__imp_?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ; MsoCF::TheActionManager(void)
0x1400aa345  mov     r10, rax
0x1400aa348  mov     rcx, [rax]
0x1400aa34b  mov     rax, [rcx+0A8h]
0x1400aa352  xor     r9d, r9d
0x1400aa355  mov     r8, rbx
0x1400aa358  lea     rdx, [rbp+var_10]
0x1400aa35c  mov     rcx, r10
0x1400aa35f  call    cs:__guard_dispatch_icall_fptr
0x1400aa365  mov     dil, al
0x1400aa368  mov     ebx, 0FF000000h
0x1400aa36d  test    dil, dil
0x1400aa370  jnz     loc_1400AA4BC
0x1400aa376  mov     [rsi], ebx
0x1400aa378  mov     eax, ebx
0x1400aa37a  cmp     eax, ebx
0x1400aa37c  jz      loc_1400AA4AA
0x1400aa382  mov     rcx, [rbp+var_8]
0x1400aa386  test    rcx, rcx
0x1400aa389  jz      short loc_1400AA398
0x1400aa38b  mov     rax, [rcx]
0x1400aa38e  mov     rax, [rax+10h]
0x1400aa392  call    cs:__guard_dispatch_icall_fptr
0x1400aa398  mov     [rbp+var_8], 0
0x1400aa3a0  mov     rcx, [rbp+arg_8]
0x1400aa3a4  test    rcx, rcx
0x1400aa3a7  jz      short loc_1400AA3B6
0x1400aa3a9  mov     rax, [rcx]
0x1400aa3ac  mov     rax, [rax+10h]
0x1400aa3b0  call    cs:__guard_dispatch_icall_fptr
0x1400aa3b6  test    r14, r14
0x1400aa3b9  jnz     short loc_1400AA3FD
0x1400aa3bb  mov     rcx, [rbp+arg_0]
0x1400aa3bf  test    rcx, rcx
0x1400aa3c2  jz      short loc_1400AA3D2
0x1400aa3c4  mov     rax, [rcx]
0x1400aa3c7  mov     rax, [rax+10h]
0x1400aa3cb  call    cs:__guard_dispatch_icall_fptr
0x1400aa3d1  nop
0x1400aa3d2  mov     edx, [rbp+var_18]
0x1400aa3d5  mov     eax, edx
0x1400aa3d7  shr     eax, 19h
0x1400aa3da  test    al, 1
0x1400aa3dc  jz      short loc_1400AA3E8
0x1400aa3de  lea     rcx, [rbp+var_20]
0x1400aa3e2  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400aa3e8  lea     r11, [rsp+50h+var_s0]
0x1400aa3ed  mov     rbx, [r11+30h]
0x1400aa3f1  mov     rsi, [r11+38h]
0x1400aa3f5  mov     rsp, r11
0x1400aa3f8  pop     r14
0x1400aa3fa  pop     rdi
0x1400aa3fb  pop     rbp
0x1400aa3fc  retn
0x1400aa3fd  xor     edx, edx
0x1400aa3ff  lea     rcx, [rbp+arg_8]
0x1400aa403  call    cs:__imp_?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet *)
0x1400aa409  mov     [rbp+var_10], 20218h
0x1400aa410  mov     rcx, [rbp+arg_8]
0x1400aa414  mov     [rbp+var_8], rcx
0x1400aa418  test    rcx, rcx
0x1400aa41b  jz      short loc_1400AA42B
0x1400aa41d  mov     rax, [rcx]
0x1400aa420  mov     rax, [rax+8]
0x1400aa424  call    cs:__guard_dispatch_icall_fptr
0x1400aa42a  nop
0x1400aa42b  mov     rbx, [rbp+arg_0]
0x1400aa42f  call    cs:__imp_?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ; MsoCF::TheActionManager(void)
0x1400aa435  mov     r10, rax
0x1400aa438  mov     rcx, [rax]
0x1400aa43b  mov     rax, [rcx+0B0h]
0x1400aa442  xor     r9d, r9d
0x1400aa445  mov     r8, rbx
0x1400aa448  lea     rdx, [rbp+var_10]
0x1400aa44c  mov     rcx, r10
0x1400aa44f  call    cs:__guard_dispatch_icall_fptr
0x1400aa455  test    al, al
0x1400aa457  jnz     loc_1400AA5E3
0x1400aa45d  test    dil, dil
0x1400aa460  jnz     loc_1400AA4F2
0x1400aa466  mov     dword ptr [r14], 0FFFFFFFFh
0x1400aa46d  mov     rcx, [rbp+var_8]
0x1400aa471  test    rcx, rcx
0x1400aa474  jz      short loc_1400AA483
0x1400aa476  mov     rax, [rcx]
0x1400aa479  mov     rax, [rax+10h]
0x1400aa47d  call    cs:__guard_dispatch_icall_fptr
0x1400aa483  mov     [rbp+var_8], 0
0x1400aa48b  mov     rcx, [rbp+arg_8]
0x1400aa48f  test    rcx, rcx
0x1400aa492  jz      loc_1400AA3BB
0x1400aa498  mov     rax, [rcx]
0x1400aa49b  mov     rax, [rax+10h]
0x1400aa49f  call    cs:__guard_dispatch_icall_fptr
0x1400aa4a5  jmp     loc_1400AA3BB
0x1400aa4aa  mov     ecx, 8; nIndex
0x1400aa4af  call    cs:__imp_GetSysColor
0x1400aa4b5  mov     [rsi], eax
0x1400aa4b7  jmp     loc_1400AA382
0x1400aa4bc  lea     r8, [rbp+var_20]
0x1400aa4c0  mov     rdx, cs:__imp_?priFontColor@PropertySpace_Jot11@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_Jot11::priFontColor
0x1400aa4c7  mov     rcx, [rbp+arg_8]
0x1400aa4cb  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400aa4d1  cmp     [rbp+var_18], 850026h
0x1400aa4d8  jz      short loc_1400AA4E8
0x1400aa4da  xor     edx, edx
0x1400aa4dc  mov     ecx, 65756E71h
0x1400aa4e1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400aa4e7  int     3; Trap to Debugger
0x1400aa4e8  mov     eax, dword ptr [rbp+var_20]
0x1400aa4eb  mov     [rsi], eax
0x1400aa4ed  jmp     loc_1400AA37A
0x1400aa4f2  lea     r8, [rbp+var_20]
0x1400aa4f6  mov     rdx, cs:__imp_?priNoteTagResource@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priNoteTagResource
0x1400aa4fd  mov     rcx, [rbp+arg_8]
0x1400aa501  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400aa507  cmp     [rbp+var_18], 850022h
0x1400aa50e  jz      short loc_1400AA51E
0x1400aa510  xor     edx, edx
0x1400aa512  mov     ecx, 65756E71h
0x1400aa517  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400aa51d  int     3; Trap to Debugger
0x1400aa51e  mov     eax, dword ptr [rbp+var_20]
0x1400aa521  mov     [r14], eax
0x1400aa524  jmp     loc_1400AA46D
0x1400aa529  xor     edx, edx
0x1400aa52b  lea     rcx, [rbp+arg_8]
0x1400aa52f  call    cs:__imp_?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet *)
0x1400aa535  nop
0x1400aa536  mov     r8, [rbp+arg_8]; struct MsoCF::IPropertySet *
0x1400aa53a  mov     edx, 20219h; unsigned int
0x1400aa53f  lea     rcx, [rbp+var_10]; this
0x1400aa543  call    ??0CActionPropertySet@MsoCF@@QEAA@IPEAUIPropertySet@1@@Z; MsoCF::CActionPropertySet::CActionPropertySet(uint,MsoCF::IPropertySet *)
0x1400aa548  mov     rdx, [rbp+arg_0]; struct MsoCF::IActionContext *
0x1400aa54c  lea     rcx, [rbp+var_10]; this
0x1400aa550  call    ?CanExecute@CActionPropertySet@MsoCF@@QEBA_NPEAUIActionContext@2@@Z; MsoCF::CActionPropertySet::CanExecute(MsoCF::IActionContext *)
0x1400aa555  test    al, al
0x1400aa557  jz      short loc_1400AA5A0
0x1400aa559  mov     rdx, [rbp+arg_0]; struct MsoCF::IActionContext *
0x1400aa55d  lea     rcx, [rbp+var_10]; this
0x1400aa561  call    ?Execute@CActionPropertySet@MsoCF@@QEAA_NPEAUIActionContext@2@@Z; MsoCF::CActionPropertySet::Execute(MsoCF::IActionContext *)
0x1400aa566  mov     dil, al
0x1400aa569  test    al, al
0x1400aa56b  jz      short loc_1400AA5A0
0x1400aa56d  lea     r8, [rbp+var_20]
0x1400aa571  mov     rdx, cs:__imp_?priHighlight@PropertySpace_Jot11@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_Jot11::priHighlight
0x1400aa578  mov     rcx, [rbp+arg_8]
0x1400aa57c  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400aa582  cmp     [rbp+var_18], 850026h
0x1400aa589  jz      short loc_1400AA599
0x1400aa58b  xor     edx, edx
0x1400aa58d  mov     ecx, 65756E71h
0x1400aa592  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400aa598  int     3; Trap to Debugger
0x1400aa599  mov     eax, dword ptr [rbp+var_20]
0x1400aa59c  mov     [rbx], eax
0x1400aa59e  jmp     short loc_1400AA5A6
0x1400aa5a0  mov     dword ptr [rbx], 0FFFFFFFFh
0x1400aa5a6  mov     rcx, [rbp+var_8]
0x1400aa5aa  test    rcx, rcx
0x1400aa5ad  jz      short loc_1400AA5BC
0x1400aa5af  mov     rax, [rcx]
0x1400aa5b2  mov     rax, [rax+10h]
0x1400aa5b6  call    cs:__guard_dispatch_icall_fptr
0x1400aa5bc  mov     [rbp+var_8], 0
0x1400aa5c4  mov     rcx, [rbp+arg_8]
0x1400aa5c8  test    rcx, rcx
0x1400aa5cb  jz      loc_1400AA2D5
0x1400aa5d1  mov     rax, [rcx]
0x1400aa5d4  mov     rax, [rax+10h]
0x1400aa5d8  call    cs:__guard_dispatch_icall_fptr
0x1400aa5de  jmp     loc_1400AA2D5
0x1400aa5e3  mov     rdx, [rbp+arg_0]; struct MsoCF::IActionContext *
0x1400aa5e7  lea     rcx, [rbp+var_10]; this
0x1400aa5eb  call    ?Execute@CActionPropertySet@MsoCF@@QEAA_NPEAUIActionContext@2@@Z; MsoCF::CActionPropertySet::Execute(MsoCF::IActionContext *)
0x1400aa5f0  mov     dil, al
0x1400aa5f3  jmp     loc_1400AA45D
```
