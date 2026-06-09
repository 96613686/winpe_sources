# Jot::CProofingUIBase::SetMisspelling(MsoCF::IPropertySet *)

- ea: `0x1400c0b00`
- end: `0x1400c0dba`
- name: `?SetMisspelling@CProofingUIBase@Jot@@AEAAXPEAUIPropertySet@MsoCF@@@Z`
- size: `698`
- prototype: `void __fastcall(Jot::CProofingUIBase *__hidden this, struct MsoCF::IPropertySet *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400c09cc`
- `0x14018cb70`

## callees

- `0x140054290`
- `0x140057580`
- `0x1400c0b00`

## import_xrefs

- `onmain!?priMisspelledWord@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400c0b4b`
- `onmain!?priSpellingSuggestions@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400c0b5f`
- `onmain!?priSpellingStatus@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400c0b87`
- `onmain!?priProofingErrorLabel@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400c0b73`
- `onmain!?priProofingErrorExplanation@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400c0b9b`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0b55`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0b69`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0b7d`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0b91`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0ba5`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0b55`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0b69`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0b7d`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0b91`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400c0ba5`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d2f`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d46`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d5d`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d74`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d8b`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d2f`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d46`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d5d`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d74`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400c0d8b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400c0bc7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400c0c89`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400c0cf6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400c0db3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400c0bc7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400c0c89`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400c0cf6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400c0db3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Jot::CProofingUIBase::SetMisspelling(Jot::CProofingUIBase *this, struct MsoCF::IPropertySet *a2)
{
  int v4; // r12d
  __int64 v5; // rax
  __int64 v6; // r14
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rbx
  char *v11; // r15
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // [rsp+40h] [rbp-29h] BYREF
  int v16; // [rsp+48h] [rbp-21h]
  __int64 v17; // [rsp+50h] [rbp-19h] BYREF
  int v18; // [rsp+58h] [rbp-11h]
  __int64 v19; // [rsp+60h] [rbp-9h] BYREF
  int v20; // [rsp+68h] [rbp-1h]
  char *v21; // [rsp+70h] [rbp+7h] BYREF
  int v22; // [rsp+78h] [rbp+Fh]
  __int64 v23; // [rsp+80h] [rbp+17h] BYREF
  int v24; // [rsp+88h] [rbp+1Fh]
  void (__fastcall *v25)(Jot::CProofingUIBase *, __int64, char *, __int64, __int64, int); // [rsp+E0h] [rbp+77h]

  v23 = 0;
  v24 = 0;
  v21 = 0;
  v22 = 0;
  v19 = 0;
  v20 = 0;
  v17 = 0;
  v18 = 0;
  v15 = 0;
  v16 = 0;
  MsoCF::IPropertySet::GetProperty(
    a2,
    Jot::PropertySpace_JotMain::priMisspelledWord,
    (struct MsoCF::CPropertyValue *)&v23);
  MsoCF::IPropertySet::GetProperty(
    a2,
    Jot::PropertySpace_JotMain::priSpellingSuggestions,
    (struct MsoCF::CPropertyValue *)&v21);
  MsoCF::IPropertySet::GetProperty(
    a2,
    Jot::PropertySpace_JotMain::priProofingErrorLabel,
    (struct MsoCF::CPropertyValue *)&v17);
  MsoCF::IPropertySet::GetProperty(
    a2,
    Jot::PropertySpace_JotMain::priSpellingStatus,
    (struct MsoCF::CPropertyValue *)&v19);
  MsoCF::IPropertySet::GetProperty(
    a2,
    Jot::PropertySpace_JotMain::priProofingErrorExplanation,
    (struct MsoCF::CPropertyValue *)&v15);
  v25 = *(void (__fastcall **)(Jot::CProofingUIBase *, __int64, char *, __int64, __int64, int))(*(_QWORD *)this + 24LL);
  if ( v20 != 8716322 )
  {
    CrashWithRecovery(0x65756E71u, 0);
    __debugbreak();
  }
  v4 = v19;
  if ( v16 != 117899322 || !v15 )
    goto LABEL_34;
  v5 = (*(_DWORD *)(v15 + 4) >> 1) & 0x1FFFFFFF;
  v6 = v15 + 8;
  if ( v15 != -8 )
  {
    if ( !(_DWORD)v5 )
      goto LABEL_22;
    v7 = v15 + 8 + 2 * v5;
    if ( _std_find_trivial_2(v15 + 8, v7, 0) == v7 )
      goto LABEL_22;
  }
  if ( v18 != 117899322 || !v17 )
    goto LABEL_34;
  v8 = (*(_DWORD *)(v17 + 4) >> 1) & 0x1FFFFFFF;
  v9 = v17 + 8;
  if ( v17 != -8 )
  {
    if ( !(_DWORD)v8 || (v10 = v17 + 8 + 2 * v8, _std_find_trivial_2(v17 + 8, v10, 0) == v10) )
    {
LABEL_22:
      CrashWithRecovery(0x1F46100Du, 0);
      __debugbreak();
    }
  }
  if ( (v22 & 0x4000000) == 0 )
  {
    CrashWithRecovery(0x65756E7Au, 0);
    __debugbreak();
  }
  v11 = (char *)&g_emptyAtom;
  if ( v21 )
    v11 = v21;
  if ( v24 != 117899322 || !v23 )
  {
LABEL_34:
    CrashWithRecovery(0x65756F6Eu, 0);
    JUMPOUT(0x1400C0DB9LL);
  }
  v12 = (*(_DWORD *)(v23 + 4) >> 1) & 0x1FFFFFFF;
  v13 = v23 + 8;
  if ( v23 != -8 )
  {
    if ( !(_DWORD)v12 )
      goto LABEL_22;
    v14 = v23 + 8 + 2 * v12;
    if ( _std_find_trivial_2(v23 + 8, v14, 0) == v14 )
      goto LABEL_22;
  }
  v25(this, v13, v11 + 8, v9, v6, v4);
  if ( (v16 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v15);
  if ( (v18 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v17);
  if ( (v20 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v19);
  if ( (v22 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v21);
  if ( (v24 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v23);
}

```

## disassembly

```asm
0x1400c0b00  mov     [rsp-8+arg_8], rbx
0x1400c0b05  push    rbp
0x1400c0b06  push    rsi
0x1400c0b07  push    rdi
0x1400c0b08  push    r12
0x1400c0b0a  push    r13
0x1400c0b0c  push    r14
0x1400c0b0e  push    r15
0x1400c0b10  lea     rbp, [rsp-27h]
0x1400c0b15  sub     rsp, 90h
0x1400c0b1c  mov     rbx, rdx
0x1400c0b1f  mov     r13, rcx
0x1400c0b22  xor     edi, edi
0x1400c0b24  mov     [rbp+57h+var_40], rdi
0x1400c0b28  mov     [rbp+57h+var_38], edi
0x1400c0b2b  mov     [rbp+57h+var_50], rdi
0x1400c0b2f  mov     [rbp+57h+var_48], edi
0x1400c0b32  mov     [rbp+57h+var_60], rdi
0x1400c0b36  mov     [rbp+57h+var_58], edi
0x1400c0b39  mov     [rbp+57h+var_70], rdi
0x1400c0b3d  mov     [rbp+57h+var_68], edi
0x1400c0b40  mov     [rbp+57h+var_80], rdi
0x1400c0b44  mov     [rbp+57h+var_78], edi
0x1400c0b47  lea     r8, [rbp+57h+var_40]
0x1400c0b4b  mov     rdx, cs:__imp_?priMisspelledWord@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priMisspelledWord
0x1400c0b52  mov     rcx, rbx
0x1400c0b55  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400c0b5b  lea     r8, [rbp+57h+var_50]
0x1400c0b5f  mov     rdx, cs:__imp_?priSpellingSuggestions@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priSpellingSuggestions
0x1400c0b66  mov     rcx, rbx
0x1400c0b69  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400c0b6f  lea     r8, [rbp+57h+var_70]
0x1400c0b73  mov     rdx, cs:__imp_?priProofingErrorLabel@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priProofingErrorLabel
0x1400c0b7a  mov     rcx, rbx
0x1400c0b7d  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400c0b83  lea     r8, [rbp+57h+var_60]
0x1400c0b87  mov     rdx, cs:__imp_?priSpellingStatus@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priSpellingStatus
0x1400c0b8e  mov     rcx, rbx
0x1400c0b91  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400c0b97  lea     r8, [rbp+57h+var_80]
0x1400c0b9b  mov     rdx, cs:__imp_?priProofingErrorExplanation@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priProofingErrorExplanation
0x1400c0ba2  mov     rcx, rbx
0x1400c0ba5  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400c0bab  mov     rax, [r13+0]
0x1400c0baf  mov     rax, [rax+18h]
0x1400c0bb3  mov     [rbp+57h+arg_10], rax
0x1400c0bb7  cmp     [rbp+57h+var_58], 850022h
0x1400c0bbe  jz      short loc_1400C0BCE
0x1400c0bc0  xor     edx, edx
0x1400c0bc2  mov     ecx, 65756E71h
0x1400c0bc7  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400c0bcd  int     3; Trap to Debugger
0x1400c0bce  mov     r12d, dword ptr [rbp+57h+var_60]
0x1400c0bd2  cmp     [rbp+57h+var_78], 707003Ah
0x1400c0bd9  jnz     loc_1400C0DAC
0x1400c0bdf  mov     rcx, [rbp+57h+var_80]
0x1400c0be3  test    rcx, rcx
0x1400c0be6  jz      loc_1400C0DAC
0x1400c0bec  mov     eax, [rcx+4]
0x1400c0bef  shr     eax, 1
0x1400c0bf1  and     eax, 1FFFFFFFh
0x1400c0bf6  lea     r14, [rcx+8]
0x1400c0bfa  test    r14, r14
0x1400c0bfd  jz      short loc_1400C0C27
0x1400c0bff  cmp     eax, 1
0x1400c0c02  jb      loc_1400C0CEF
0x1400c0c08  add     rcx, 8
0x1400c0c0c  lea     rbx, [rcx+rax*2]
0x1400c0c10  xor     r8d, r8d
0x1400c0c13  mov     rdx, rbx
0x1400c0c16  mov     rcx, r14
0x1400c0c19  call    __std_find_trivial_2
0x1400c0c1e  cmp     rax, rbx
0x1400c0c21  jz      loc_1400C0CEF
0x1400c0c27  cmp     [rbp+57h+var_68], 707003Ah
0x1400c0c2e  jnz     loc_1400C0DAC
0x1400c0c34  mov     rcx, [rbp+57h+var_70]
0x1400c0c38  test    rcx, rcx
0x1400c0c3b  jz      loc_1400C0DAC
0x1400c0c41  mov     eax, [rcx+4]
0x1400c0c44  shr     eax, 1
0x1400c0c46  and     eax, 1FFFFFFFh
0x1400c0c4b  lea     rsi, [rcx+8]
0x1400c0c4f  test    rsi, rsi
0x1400c0c52  jz      short loc_1400C0C78
0x1400c0c54  cmp     eax, 1
0x1400c0c57  jb      loc_1400C0CEF
0x1400c0c5d  add     rcx, 8
0x1400c0c61  lea     rbx, [rcx+rax*2]
0x1400c0c65  xor     r8d, r8d
0x1400c0c68  mov     rdx, rbx
0x1400c0c6b  mov     rcx, rsi
0x1400c0c6e  call    __std_find_trivial_2
0x1400c0c73  cmp     rax, rbx
0x1400c0c76  jz      short loc_1400C0CEF
0x1400c0c78  mov     eax, [rbp+57h+var_48]
0x1400c0c7b  shr     eax, 1Ah
0x1400c0c7e  test    al, 1
0x1400c0c80  jnz     short loc_1400C0C90
0x1400c0c82  xor     edx, edx
0x1400c0c84  mov     ecx, 65756E7Ah
0x1400c0c89  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400c0c8f  int     3; Trap to Debugger
0x1400c0c90  lea     r15, ?g_emptyAtom@@3VCEmptyOrZeroAtom@@A; CEmptyOrZeroAtom g_emptyAtom
0x1400c0c97  mov     rax, [rbp+57h+var_50]
0x1400c0c9b  test    rax, rax
0x1400c0c9e  cmovnz  r15, rax
0x1400c0ca2  cmp     [rbp+57h+var_38], 707003Ah
0x1400c0ca9  jnz     loc_1400C0DAC
0x1400c0caf  mov     rcx, [rbp+57h+var_40]
0x1400c0cb3  test    rcx, rcx
0x1400c0cb6  jz      loc_1400C0DAC
0x1400c0cbc  mov     eax, [rcx+4]
0x1400c0cbf  shr     eax, 1
0x1400c0cc1  and     eax, 1FFFFFFFh
0x1400c0cc6  lea     rdi, [rcx+8]
0x1400c0cca  test    rdi, rdi
0x1400c0ccd  jz      short loc_1400C0CFD
0x1400c0ccf  cmp     eax, 1
0x1400c0cd2  jb      short loc_1400C0CEF
0x1400c0cd4  add     rcx, 8
0x1400c0cd8  lea     rbx, [rcx+rax*2]
0x1400c0cdc  xor     r8d, r8d
0x1400c0cdf  mov     rdx, rbx
0x1400c0ce2  mov     rcx, rdi
0x1400c0ce5  call    __std_find_trivial_2
0x1400c0cea  cmp     rax, rbx
0x1400c0ced  jnz     short loc_1400C0CFD
0x1400c0cef  xor     edx, edx
0x1400c0cf1  mov     ecx, 1F46100Dh
0x1400c0cf6  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400c0cfc  int     3; Trap to Debugger
0x1400c0cfd  mov     [rsp+0C0h+var_98], r12d
0x1400c0d02  mov     [rsp+0C0h+var_A0], r14
0x1400c0d07  mov     r9, rsi
0x1400c0d0a  lea     r8, [r15+8]
0x1400c0d0e  mov     rdx, rdi
0x1400c0d11  mov     rcx, r13
0x1400c0d14  mov     rax, [rbp+57h+arg_10]
0x1400c0d18  call    cs:__guard_dispatch_icall_fptr
0x1400c0d1e  nop
0x1400c0d1f  mov     edx, [rbp+57h+var_78]
0x1400c0d22  mov     eax, edx
0x1400c0d24  shr     eax, 19h
0x1400c0d27  test    al, 1
0x1400c0d29  jz      short loc_1400C0D36
0x1400c0d2b  lea     rcx, [rbp+57h+var_80]
0x1400c0d2f  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400c0d35  nop
0x1400c0d36  mov     edx, [rbp+57h+var_68]
0x1400c0d39  mov     eax, edx
0x1400c0d3b  shr     eax, 19h
0x1400c0d3e  test    al, 1
0x1400c0d40  jz      short loc_1400C0D4D
0x1400c0d42  lea     rcx, [rbp+57h+var_70]
0x1400c0d46  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400c0d4c  nop
0x1400c0d4d  mov     edx, [rbp+57h+var_58]
0x1400c0d50  mov     eax, edx
0x1400c0d52  shr     eax, 19h
0x1400c0d55  test    al, 1
0x1400c0d57  jz      short loc_1400C0D64
0x1400c0d59  lea     rcx, [rbp+57h+var_60]
0x1400c0d5d  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400c0d63  nop
0x1400c0d64  mov     edx, [rbp+57h+var_48]
0x1400c0d67  mov     eax, edx
0x1400c0d69  shr     eax, 19h
0x1400c0d6c  test    al, 1
0x1400c0d6e  jz      short loc_1400C0D7B
0x1400c0d70  lea     rcx, [rbp+57h+var_50]
0x1400c0d74  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400c0d7a  nop
0x1400c0d7b  mov     edx, [rbp+57h+var_38]
0x1400c0d7e  mov     eax, edx
0x1400c0d80  shr     eax, 19h
0x1400c0d83  test    al, 1
0x1400c0d85  jz      short loc_1400C0D91
0x1400c0d87  lea     rcx, [rbp+57h+var_40]
0x1400c0d8b  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400c0d91  mov     rbx, [rsp+0C0h+arg_8]
0x1400c0d99  add     rsp, 90h
0x1400c0da0  pop     r15
0x1400c0da2  pop     r14
0x1400c0da4  pop     r13
0x1400c0da6  pop     r12
0x1400c0da8  pop     rdi
0x1400c0da9  pop     rsi
0x1400c0daa  pop     rbp
0x1400c0dab  retn
0x1400c0dac  xor     edx, edx
0x1400c0dae  mov     ecx, 65756F6Eh
0x1400c0db3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
