# Art::Path2D::FIsUprightRectangle(void)

- ea: `0x18025d5e0`
- end: `0x18025db01`
- name: `?FIsUprightRectangle@Path2D@Art@@QEBA_NXZ`
- size: `1313`
- prototype: `bool __fastcall(Art::Path2D *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1801a31b0`
- `0x1802ff230`

## callees

- `0x1800704f0`
- `0x1801dbc00`
- `0x18024aaa0`
- `0x18025d56c`
- `0x18025d5e0`
- `0x18025db04`
- `0x180279050`
- `0x1804eafe0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x18025d926`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025d96e`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025d9b6`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025d9fe`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025da48`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025da92`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025d926`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025d96e`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025d9b6`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025d9fe`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025da48`
- `VCRUNTIME140!__std_type_info_compare` at `0x18025da92`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d636`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d65b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d680`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d6a9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d6d2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d6f2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d716`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d73a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d636`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d65b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d680`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d6a9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d6d2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d6f2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d716`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18025d73a`

## pseudocode

```c
bool __fastcall Art::Path2D::FIsUprightRectangle(Art::Path2D *this)
{
  __int64 v3; // r15
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rbp
  __int64 v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // r8
  _QWORD *v10; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // r8
  _QWORD *v15; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // r8
  _QWORD *v20; // rdx
  bool v21; // al
  __int64 v22; // rcx
  __int64 v23; // rdx
  _QWORD *v24; // r8
  _QWORD *v25; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  _QWORD *v29; // r8
  _QWORD *v30; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdx
  _QWORD *v34; // r8
  _QWORD *v35; // rdx
  bool v36; // al
  unsigned __int8 (__fastcall *v37)(__int64, __int64); // rax
  unsigned __int8 (__fastcall *v38)(__int64, __int64); // rax
  unsigned __int8 (__fastcall *v39)(__int64, __int64); // rax
  unsigned __int8 (__fastcall *v40)(__int64, __int64); // rax
  unsigned __int8 (__fastcall *v41)(__int64, __int64); // rax
  unsigned __int8 (__fastcall *v42)(__int64, __int64); // rax

  if ( *((_DWORD *)this + 4) != 5
    || !(unsigned __int8)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(*((_QWORD *)this + 1)) )
  {
    return 0;
  }
  if ( *((_DWORD *)this + 4) <= 1u )
  {
    CrashWithRecovery(0x1E892498u, 0);
    __debugbreak();
  }
  if ( !(unsigned __int8)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(*((_QWORD *)this + 1) + 16LL) )
    return 0;
  if ( *((_DWORD *)this + 4) <= 2u )
  {
    CrashWithRecovery(0x1E892498u, 0);
    __debugbreak();
  }
  if ( !(unsigned __int8)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(*((_QWORD *)this + 1) + 32LL) )
    return 0;
  if ( *((_DWORD *)this + 4) <= 3u )
  {
    CrashWithRecovery(0x1E892498u, 0);
    __debugbreak();
  }
  if ( !(unsigned __int8)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(*((_QWORD *)this + 1) + 48LL) )
    return 0;
  if ( *((_DWORD *)this + 4) <= 4u )
  {
    CrashWithRecovery(0x1E892498u, 0);
    __debugbreak();
  }
  if ( !(unsigned __int8)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::Close>(*((_QWORD *)this + 1) + 64LL) )
    return 0;
  if ( !*((_DWORD *)this + 4) )
    CrashWithRecovery(0x1E892498u, 0);
  v3 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::MoveTo>(*((_QWORD *)this + 1));
  if ( *((_DWORD *)this + 4) <= 1u )
  {
    CrashWithRecovery(0x1E892498u, 0);
    __debugbreak();
  }
  v4 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(*((_QWORD *)this + 1) + 16LL);
  if ( *((_DWORD *)this + 4) <= 2u )
  {
    CrashWithRecovery(0x1E892498u, 0);
    __debugbreak();
  }
  v5 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(*((_QWORD *)this + 1) + 32LL);
  if ( *((_DWORD *)this + 4) <= 3u )
  {
    CrashWithRecovery(0x1E892498u, 0);
    __debugbreak();
  }
  if ( (v6 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(*((_QWORD *)this + 1) + 48LL),
        v7 = *(_QWORD *)(v4 + 8),
        (v8 = *(_QWORD *)(v3 + 8)) == 0)
    || !v7
    || v8 != v7
    && (*(_QWORD *)(v8 + 48) == *(_QWORD *)(v7 + 48)
     || (v9 = *(_QWORD **)v8, v10 = *(_QWORD **)v7, v9 != *(_QWORD **)v7)
     && (v9[1] == v10[1] || (unsigned int)__std_type_info_compare(*v9 + 8LL, *v10 + 8LL)))
    || (v37 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v3 + 8) + 24LL)) == 0
    || !v37(v3, v4) )
  {
    v12 = *(_QWORD *)(v4 + 24);
    v13 = *(_QWORD *)(v3 + 24);
    if ( !v13 )
      return 0;
    if ( !v12 )
      return 0;
    if ( v13 != v12 )
    {
      if ( *(_QWORD *)(v13 + 48) == *(_QWORD *)(v12 + 48) )
        return 0;
      v14 = *(_QWORD **)v13;
      v15 = *(_QWORD **)v12;
      if ( v14 != *(_QWORD **)v12 && (v14[1] == v15[1] || (unsigned int)__std_type_info_compare(*v14 + 8LL, *v15 + 8LL)) )
        return 0;
    }
    v40 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v3 + 24) + 24LL);
    if ( !v40 || !v40(v3 + 16, v4 + 16) )
      return 0;
  }
  v21 = 0;
  v17 = *(_QWORD *)(v5 + 8);
  v18 = *(_QWORD *)(v4 + 8);
  if ( v18 )
  {
    if ( v17 )
    {
      if ( v18 == v17
        || *(_QWORD *)(v18 + 48) != *(_QWORD *)(v17 + 48)
        && ((v19 = *(_QWORD **)v18, v20 = *(_QWORD **)v17, v19 == *(_QWORD **)v17)
         || v19[1] != v20[1] && !(unsigned int)__std_type_info_compare(*v19 + 8LL, *v20 + 8LL)) )
      {
        v38 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v4 + 8) + 24LL);
        if ( v38 )
        {
          if ( v38(v4, v5) )
            v21 = 1;
        }
      }
    }
  }
  if ( !v21 && (unsigned __int8)Art::AdjCoord::operator!=(v4 + 16, v5 + 16) )
    return 0;
  if ( (v22 = *(_QWORD *)(v6 + 8), (v23 = *(_QWORD *)(v5 + 8)) == 0)
    || !v22
    || v23 != v22
    && (*(_QWORD *)(v23 + 48) == *(_QWORD *)(v22 + 48)
     || (v24 = *(_QWORD **)v23, v25 = *(_QWORD **)v22, v24 != *(_QWORD **)v22)
     && (v24[1] == v25[1] || (unsigned int)__std_type_info_compare(*v24 + 8LL, *v25 + 8LL)))
    || (v39 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v5 + 8) + 24LL)) == 0
    || !v39(v5, v6) )
  {
    v27 = *(_QWORD *)(v6 + 24);
    v28 = *(_QWORD *)(v5 + 24);
    if ( !v28 )
      return 0;
    if ( !v27 )
      return 0;
    if ( v28 != v27 )
    {
      if ( *(_QWORD *)(v28 + 48) == *(_QWORD *)(v27 + 48) )
        return 0;
      v29 = *(_QWORD **)v28;
      v30 = *(_QWORD **)v27;
      if ( v29 != *(_QWORD **)v27 && (v29[1] == v30[1] || (unsigned int)__std_type_info_compare(*v29 + 8LL, *v30 + 8LL)) )
        return 0;
    }
    v41 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v5 + 24) + 24LL);
    if ( !v41 || !v41(v5 + 16, v6 + 16) )
      return 0;
  }
  v36 = 0;
  v32 = *(_QWORD *)(v3 + 8);
  v33 = *(_QWORD *)(v6 + 8);
  if ( v33 )
  {
    if ( v32 )
    {
      if ( v33 == v32
        || *(_QWORD *)(v33 + 48) != *(_QWORD *)(v32 + 48)
        && ((v34 = *(_QWORD **)v33, v35 = *(_QWORD **)v32, v34 == *(_QWORD **)v32)
         || v34[1] != v35[1] && !(unsigned int)__std_type_info_compare(*v34 + 8LL, *v35 + 8LL)) )
      {
        v42 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v6 + 8) + 24LL);
        if ( v42 )
        {
          if ( v42(v6, v3) )
            v36 = 1;
        }
      }
    }
  }
  return v36 || !(unsigned __int8)Art::AdjCoord::operator!=(v6 + 16, v3 + 16);
}

```

## disassembly

```asm
0x18025d5e0  mov     [rsp+arg_0], rbx
0x18025d5e5  mov     [rsp+arg_8], rbp
0x18025d5ea  mov     [rsp+arg_10], rsi
0x18025d5ef  push    rdi
0x18025d5f0  push    r14
0x18025d5f2  push    r15
0x18025d5f4  sub     rsp, 20h
0x18025d5f8  mov     rbx, rcx
0x18025d5fb  cmp     dword ptr [rcx+10h], 5
0x18025d5ff  jz      short loc_18025D61C
0x18025d601  xor     al, al
0x18025d603  mov     rbx, [rsp+38h+arg_0]
0x18025d608  mov     rbp, [rsp+38h+arg_8]
0x18025d60d  mov     rsi, [rsp+38h+arg_10]
0x18025d612  add     rsp, 20h
0x18025d616  pop     r15
0x18025d618  pop     r14
0x18025d61a  pop     rdi
0x18025d61b  retn
0x18025d61c  mov     rcx, [rcx+8]
0x18025d620  call    ??$Is@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(void)
0x18025d625  test    al, al
0x18025d627  jz      short loc_18025D601
0x18025d629  cmp     dword ptr [rbx+10h], 1
0x18025d62d  ja      short loc_18025D63D
0x18025d62f  xor     edx, edx
0x18025d631  mov     ecx, 1E892498h
0x18025d636  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18025d63c  int     3; Trap to Debugger
0x18025d63d  mov     rcx, [rbx+8]
0x18025d641  add     rcx, 10h
0x18025d645  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x18025d64a  test    al, al
0x18025d64c  jz      short loc_18025D601
0x18025d64e  cmp     dword ptr [rbx+10h], 2
0x18025d652  ja      short loc_18025D662
0x18025d654  xor     edx, edx
0x18025d656  mov     ecx, 1E892498h
0x18025d65b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18025d661  int     3; Trap to Debugger
0x18025d662  mov     rcx, [rbx+8]
0x18025d666  add     rcx, 20h ; ' '
0x18025d66a  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x18025d66f  test    al, al
0x18025d671  jz      short loc_18025D601
0x18025d673  cmp     dword ptr [rbx+10h], 3
0x18025d677  ja      short loc_18025D687
0x18025d679  xor     edx, edx
0x18025d67b  mov     ecx, 1E892498h
0x18025d680  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18025d686  int     3; Trap to Debugger
0x18025d687  mov     rcx, [rbx+8]
0x18025d68b  add     rcx, 30h ; '0'
0x18025d68f  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x18025d694  test    al, al
0x18025d696  jz      loc_18025D601
0x18025d69c  cmp     dword ptr [rbx+10h], 4
0x18025d6a0  ja      short loc_18025D6B0
0x18025d6a2  xor     edx, edx
0x18025d6a4  mov     ecx, 1E892498h
0x18025d6a9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18025d6af  int     3; Trap to Debugger
0x18025d6b0  mov     rcx, [rbx+8]
0x18025d6b4  add     rcx, 40h ; '@'
0x18025d6b8  call    ??$Is@UClose@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::Close>(void)
0x18025d6bd  test    al, al
0x18025d6bf  jz      loc_18025D601
0x18025d6c5  cmp     dword ptr [rbx+10h], 0
0x18025d6c9  ja      short loc_18025D6D9
0x18025d6cb  xor     edx, edx
0x18025d6cd  mov     ecx, 1E892498h
0x18025d6d2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18025d6d8  nop
0x18025d6d9  mov     rcx, [rbx+8]
0x18025d6dd  call    ??$Get@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DMoveTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::MoveTo>(void)
0x18025d6e2  mov     r15, rax
0x18025d6e5  cmp     dword ptr [rbx+10h], 1
0x18025d6e9  ja      short loc_18025D6F9
0x18025d6eb  xor     edx, edx
0x18025d6ed  mov     ecx, 1E892498h
0x18025d6f2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18025d6f8  int     3; Trap to Debugger
0x18025d6f9  mov     rcx, [rbx+8]
0x18025d6fd  add     rcx, 10h
0x18025d701  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x18025d706  mov     rsi, rax
0x18025d709  cmp     dword ptr [rbx+10h], 2
0x18025d70d  ja      short loc_18025D71D
0x18025d70f  xor     edx, edx
0x18025d711  mov     ecx, 1E892498h
0x18025d716  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18025d71c  int     3; Trap to Debugger
0x18025d71d  mov     rcx, [rbx+8]
0x18025d721  add     rcx, 20h ; ' '
0x18025d725  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x18025d72a  mov     rdi, rax
0x18025d72d  cmp     dword ptr [rbx+10h], 3
0x18025d731  ja      short loc_18025D741
0x18025d733  xor     edx, edx
0x18025d735  mov     ecx, 1E892498h
0x18025d73a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18025d740  int     3; Trap to Debugger
0x18025d741  mov     rcx, [rbx+8]
0x18025d745  add     rcx, 30h ; '0'
0x18025d749  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x18025d74e  mov     rbp, rax
0x18025d751  mov     rcx, [rsi+8]
0x18025d755  mov     rdx, [r15+8]
0x18025d759  test    rdx, rdx
0x18025d75c  jz      short loc_18025D793
0x18025d75e  test    rcx, rcx
0x18025d761  jz      short loc_18025D793
0x18025d763  cmp     rdx, rcx
0x18025d766  jz      loc_18025D934
0x18025d76c  mov     rax, [rcx+30h]
0x18025d770  cmp     [rdx+30h], rax
0x18025d774  jz      short loc_18025D793
0x18025d776  mov     r8, [rdx]
0x18025d779  mov     rdx, [rcx]
0x18025d77c  cmp     r8, rdx
0x18025d77f  jz      loc_18025D934
0x18025d785  mov     rax, [rdx+8]
0x18025d789  cmp     [r8+8], rax
0x18025d78d  jnz     loc_18025D918
0x18025d793  xor     al, al
0x18025d795  test    al, al
0x18025d797  jnz     short loc_18025D7E5
0x18025d799  mov     rcx, [rsi+18h]
0x18025d79d  mov     rdx, [r15+18h]
0x18025d7a1  test    rdx, rdx
0x18025d7a4  jz      short loc_18025D7DB
0x18025d7a6  test    rcx, rcx
0x18025d7a9  jz      short loc_18025D7DB
0x18025d7ab  cmp     rdx, rcx
0x18025d7ae  jz      loc_18025DA0C
0x18025d7b4  mov     rax, [rcx+30h]
0x18025d7b8  cmp     [rdx+30h], rax
0x18025d7bc  jz      short loc_18025D7DB
0x18025d7be  mov     r8, [rdx]
0x18025d7c1  mov     rdx, [rcx]
0x18025d7c4  cmp     r8, rdx
0x18025d7c7  jz      loc_18025DA0C
0x18025d7cd  mov     rax, [rdx+8]
0x18025d7d1  cmp     [r8+8], rax
0x18025d7d5  jnz     loc_18025D9F0
0x18025d7db  xor     al, al
0x18025d7dd  test    al, al
0x18025d7df  jz      loc_18025D601
0x18025d7e5  mov     rcx, [rdi+8]
0x18025d7e9  mov     rdx, [rsi+8]
0x18025d7ed  test    rdx, rdx
0x18025d7f0  jz      short loc_18025D827
0x18025d7f2  test    rcx, rcx
0x18025d7f5  jz      short loc_18025D827
0x18025d7f7  cmp     rdx, rcx
0x18025d7fa  jz      loc_18025D97C
0x18025d800  mov     rax, [rcx+30h]
0x18025d804  cmp     [rdx+30h], rax
0x18025d808  jz      short loc_18025D827
0x18025d80a  mov     r8, [rdx]
0x18025d80d  mov     rdx, [rcx]
0x18025d810  cmp     r8, rdx
0x18025d813  jz      loc_18025D97C
0x18025d819  mov     rax, [rdx+8]
0x18025d81d  cmp     [r8+8], rax
0x18025d821  jnz     loc_18025D960
0x18025d827  xor     al, al
0x18025d829  test    al, al
0x18025d82b  jz      loc_18025DACC
0x18025d831  mov     rcx, [rbp+8]
0x18025d835  mov     rdx, [rdi+8]
0x18025d839  test    rdx, rdx
0x18025d83c  jz      short loc_18025D873
0x18025d83e  test    rcx, rcx
0x18025d841  jz      short loc_18025D873
0x18025d843  cmp     rdx, rcx
0x18025d846  jz      loc_18025D9C4
0x18025d84c  mov     rax, [rcx+30h]
0x18025d850  cmp     [rdx+30h], rax
0x18025d854  jz      short loc_18025D873
0x18025d856  mov     r8, [rdx]
0x18025d859  mov     rdx, [rcx]
0x18025d85c  cmp     r8, rdx
0x18025d85f  jz      loc_18025D9C4
0x18025d865  mov     rax, [rdx+8]
0x18025d869  cmp     [r8+8], rax
0x18025d86d  jnz     loc_18025D9A8
0x18025d873  xor     al, al
0x18025d875  test    al, al
0x18025d877  jnz     short loc_18025D8C5
0x18025d879  mov     rcx, [rbp+18h]
0x18025d87d  mov     rdx, [rdi+18h]
0x18025d881  test    rdx, rdx
0x18025d884  jz      short loc_18025D8BB
0x18025d886  test    rcx, rcx
0x18025d889  jz      short loc_18025D8BB
0x18025d88b  cmp     rdx, rcx
0x18025d88e  jz      loc_18025DA56
0x18025d894  mov     rax, [rcx+30h]
0x18025d898  cmp     [rdx+30h], rax
0x18025d89c  jz      short loc_18025D8BB
0x18025d89e  mov     r8, [rdx]
0x18025d8a1  mov     rdx, [rcx]
0x18025d8a4  cmp     r8, rdx
0x18025d8a7  jz      loc_18025DA56
0x18025d8ad  mov     rax, [rdx+8]
0x18025d8b1  cmp     [r8+8], rax
0x18025d8b5  jnz     loc_18025DA3A
0x18025d8bb  xor     al, al
0x18025d8bd  test    al, al
0x18025d8bf  jz      loc_18025D601
0x18025d8c5  mov     rcx, [r15+8]
0x18025d8c9  mov     rdx, [rbp+8]
0x18025d8cd  test    rdx, rdx
0x18025d8d0  jz      short loc_18025D907
0x18025d8d2  test    rcx, rcx
0x18025d8d5  jz      short loc_18025D907
0x18025d8d7  cmp     rdx, rcx
0x18025d8da  jz      loc_18025DAA0
0x18025d8e0  mov     rax, [rcx+30h]
0x18025d8e4  cmp     [rdx+30h], rax
0x18025d8e8  jz      short loc_18025D907
0x18025d8ea  mov     r8, [rdx]
0x18025d8ed  mov     rdx, [rcx]
0x18025d8f0  cmp     r8, rdx
0x18025d8f3  jz      loc_18025DAA0
0x18025d8f9  mov     rax, [rdx+8]
0x18025d8fd  cmp     [r8+8], rax
0x18025d901  jnz     loc_18025DA84
0x18025d907  xor     al, al
0x18025d909  test    al, al
0x18025d90b  jz      loc_18025DAE6
0x18025d911  mov     al, 1
0x18025d913  jmp     loc_18025D603
0x18025d918  mov     rcx, [r8]
0x18025d91b  mov     rdx, [rdx]
0x18025d91e  add     rdx, 8
0x18025d922  add     rcx, 8
0x18025d926  call    cs:__imp___std_type_info_compare
0x18025d92c  test    eax, eax
0x18025d92e  jnz     loc_18025D793
0x18025d934  mov     rax, [r15+8]
0x18025d938  mov     rax, [rax+18h]
0x18025d93c  test    rax, rax
0x18025d93f  jz      loc_18025D793
0x18025d945  mov     rdx, rsi
0x18025d948  mov     rcx, r15
0x18025d94b  call    cs:__guard_dispatch_icall_fptr
0x18025d951  test    al, al
0x18025d953  jz      loc_18025D793
0x18025d959  mov     al, 1
0x18025d95b  jmp     loc_18025D795
0x18025d960  mov     rcx, [r8]
0x18025d963  mov     rdx, [rdx]
0x18025d966  add     rdx, 8
0x18025d96a  add     rcx, 8
0x18025d96e  call    cs:__imp___std_type_info_compare
0x18025d974  test    eax, eax
0x18025d976  jnz     loc_18025D827
0x18025d97c  mov     rax, [rsi+8]
0x18025d980  mov     rax, [rax+18h]
0x18025d984  test    rax, rax
0x18025d987  jz      loc_18025D827
0x18025d98d  mov     rdx, rdi
0x18025d990  mov     rcx, rsi
0x18025d993  call    cs:__guard_dispatch_icall_fptr
0x18025d999  test    al, al
0x18025d99b  jz      loc_18025D827
0x18025d9a1  mov     al, 1
0x18025d9a3  jmp     loc_18025D829
0x18025d9a8  mov     rcx, [r8]
0x18025d9ab  mov     rdx, [rdx]
0x18025d9ae  add     rdx, 8
0x18025d9b2  add     rcx, 8
0x18025d9b6  call    cs:__imp___std_type_info_compare
0x18025d9bc  test    eax, eax
0x18025d9be  jnz     loc_18025D873
0x18025d9c4  mov     rax, [rdi+8]
0x18025d9c8  mov     rax, [rax+18h]
0x18025d9cc  test    rax, rax
0x18025d9cf  jz      loc_18025D873
0x18025d9d5  mov     rdx, rbp
0x18025d9d8  mov     rcx, rdi
0x18025d9db  call    cs:__guard_dispatch_icall_fptr
0x18025d9e1  test    al, al
0x18025d9e3  jz      loc_18025D873
0x18025d9e9  mov     al, 1
0x18025d9eb  jmp     loc_18025D875
0x18025d9f0  mov     rcx, [r8]
0x18025d9f3  mov     rdx, [rdx]
0x18025d9f6  add     rdx, 8
0x18025d9fa  add     rcx, 8
0x18025d9fe  call    cs:__imp___std_type_info_compare
0x18025da04  test    eax, eax
0x18025da06  jnz     loc_18025D7DB
0x18025da0c  mov     rax, [r15+18h]
0x18025da10  mov     rax, [rax+18h]
0x18025da14  test    rax, rax
0x18025da17  jz      loc_18025D7DB
0x18025da1d  lea     rdx, [rsi+10h]
  ... truncated ...
```
