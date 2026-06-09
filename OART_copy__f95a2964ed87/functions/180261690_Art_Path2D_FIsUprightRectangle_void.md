# Art::Path2D::FIsUprightRectangle(void)

- ea: `0x180261690`
- end: `0x180261bb1`
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
- `0x18024add0`
- `0x180261628`
- `0x180261690`
- `0x180261bb4`
- `0x180279050`
- `0x1804eafe0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x1802619d6`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261a1e`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261a66`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261aae`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261af8`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261b42`
- `VCRUNTIME140!__std_type_info_compare` at `0x1802619d6`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261a1e`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261a66`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261aae`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261af8`
- `VCRUNTIME140!__std_type_info_compare` at `0x180261b42`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802616e6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18026170b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180261730`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180261759`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180261782`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802617a2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802617c6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802617ea`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802616e6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18026170b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180261730`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180261759`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180261782`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802617a2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802617c6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802617ea`

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
0x180261690  mov     [rsp+arg_0], rbx
0x180261695  mov     [rsp+arg_8], rbp
0x18026169a  mov     [rsp+arg_10], rsi
0x18026169f  push    rdi
0x1802616a0  push    r14
0x1802616a2  push    r15
0x1802616a4  sub     rsp, 20h
0x1802616a8  mov     rbx, rcx
0x1802616ab  cmp     dword ptr [rcx+10h], 5
0x1802616af  jz      short loc_1802616CC
0x1802616b1  xor     al, al
0x1802616b3  mov     rbx, [rsp+38h+arg_0]
0x1802616b8  mov     rbp, [rsp+38h+arg_8]
0x1802616bd  mov     rsi, [rsp+38h+arg_10]
0x1802616c2  add     rsp, 20h
0x1802616c6  pop     r15
0x1802616c8  pop     r14
0x1802616ca  pop     rdi
0x1802616cb  retn
0x1802616cc  mov     rcx, [rcx+8]
0x1802616d0  call    ??$Is@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(void)
0x1802616d5  test    al, al
0x1802616d7  jz      short loc_1802616B1
0x1802616d9  cmp     dword ptr [rbx+10h], 1
0x1802616dd  ja      short loc_1802616ED
0x1802616df  xor     edx, edx
0x1802616e1  mov     ecx, 1E892498h
0x1802616e6  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1802616ec  int     3; Trap to Debugger
0x1802616ed  mov     rcx, [rbx+8]
0x1802616f1  add     rcx, 10h
0x1802616f5  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x1802616fa  test    al, al
0x1802616fc  jz      short loc_1802616B1
0x1802616fe  cmp     dword ptr [rbx+10h], 2
0x180261702  ja      short loc_180261712
0x180261704  xor     edx, edx
0x180261706  mov     ecx, 1E892498h
0x18026170b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180261711  int     3; Trap to Debugger
0x180261712  mov     rcx, [rbx+8]
0x180261716  add     rcx, 20h ; ' '
0x18026171a  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x18026171f  test    al, al
0x180261721  jz      short loc_1802616B1
0x180261723  cmp     dword ptr [rbx+10h], 3
0x180261727  ja      short loc_180261737
0x180261729  xor     edx, edx
0x18026172b  mov     ecx, 1E892498h
0x180261730  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180261736  int     3; Trap to Debugger
0x180261737  mov     rcx, [rbx+8]
0x18026173b  add     rcx, 30h ; '0'
0x18026173f  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x180261744  test    al, al
0x180261746  jz      loc_1802616B1
0x18026174c  cmp     dword ptr [rbx+10h], 4
0x180261750  ja      short loc_180261760
0x180261752  xor     edx, edx
0x180261754  mov     ecx, 1E892498h
0x180261759  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18026175f  int     3; Trap to Debugger
0x180261760  mov     rcx, [rbx+8]
0x180261764  add     rcx, 40h ; '@'
0x180261768  call    ??$Is@UClose@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::Close>(void)
0x18026176d  test    al, al
0x18026176f  jz      loc_1802616B1
0x180261775  cmp     dword ptr [rbx+10h], 0
0x180261779  ja      short loc_180261789
0x18026177b  xor     edx, edx
0x18026177d  mov     ecx, 1E892498h
0x180261782  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180261788  nop
0x180261789  mov     rcx, [rbx+8]
0x18026178d  call    ??$Get@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DMoveTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::MoveTo>(void)
0x180261792  mov     r15, rax
0x180261795  cmp     dword ptr [rbx+10h], 1
0x180261799  ja      short loc_1802617A9
0x18026179b  xor     edx, edx
0x18026179d  mov     ecx, 1E892498h
0x1802617a2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1802617a8  int     3; Trap to Debugger
0x1802617a9  mov     rcx, [rbx+8]
0x1802617ad  add     rcx, 10h
0x1802617b1  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x1802617b6  mov     rsi, rax
0x1802617b9  cmp     dword ptr [rbx+10h], 2
0x1802617bd  ja      short loc_1802617CD
0x1802617bf  xor     edx, edx
0x1802617c1  mov     ecx, 1E892498h
0x1802617c6  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1802617cc  int     3; Trap to Debugger
0x1802617cd  mov     rcx, [rbx+8]
0x1802617d1  add     rcx, 20h ; ' '
0x1802617d5  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x1802617da  mov     rdi, rax
0x1802617dd  cmp     dword ptr [rbx+10h], 3
0x1802617e1  ja      short loc_1802617F1
0x1802617e3  xor     edx, edx
0x1802617e5  mov     ecx, 1E892498h
0x1802617ea  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1802617f0  int     3; Trap to Debugger
0x1802617f1  mov     rcx, [rbx+8]
0x1802617f5  add     rcx, 30h ; '0'
0x1802617f9  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x1802617fe  mov     rbp, rax
0x180261801  mov     rcx, [rsi+8]
0x180261805  mov     rdx, [r15+8]
0x180261809  test    rdx, rdx
0x18026180c  jz      short loc_180261843
0x18026180e  test    rcx, rcx
0x180261811  jz      short loc_180261843
0x180261813  cmp     rdx, rcx
0x180261816  jz      loc_1802619E4
0x18026181c  mov     rax, [rcx+30h]
0x180261820  cmp     [rdx+30h], rax
0x180261824  jz      short loc_180261843
0x180261826  mov     r8, [rdx]
0x180261829  mov     rdx, [rcx]
0x18026182c  cmp     r8, rdx
0x18026182f  jz      loc_1802619E4
0x180261835  mov     rax, [rdx+8]
0x180261839  cmp     [r8+8], rax
0x18026183d  jnz     loc_1802619C8
0x180261843  xor     al, al
0x180261845  test    al, al
0x180261847  jnz     short loc_180261895
0x180261849  mov     rcx, [rsi+18h]
0x18026184d  mov     rdx, [r15+18h]
0x180261851  test    rdx, rdx
0x180261854  jz      short loc_18026188B
0x180261856  test    rcx, rcx
0x180261859  jz      short loc_18026188B
0x18026185b  cmp     rdx, rcx
0x18026185e  jz      loc_180261ABC
0x180261864  mov     rax, [rcx+30h]
0x180261868  cmp     [rdx+30h], rax
0x18026186c  jz      short loc_18026188B
0x18026186e  mov     r8, [rdx]
0x180261871  mov     rdx, [rcx]
0x180261874  cmp     r8, rdx
0x180261877  jz      loc_180261ABC
0x18026187d  mov     rax, [rdx+8]
0x180261881  cmp     [r8+8], rax
0x180261885  jnz     loc_180261AA0
0x18026188b  xor     al, al
0x18026188d  test    al, al
0x18026188f  jz      loc_1802616B1
0x180261895  mov     rcx, [rdi+8]
0x180261899  mov     rdx, [rsi+8]
0x18026189d  test    rdx, rdx
0x1802618a0  jz      short loc_1802618D7
0x1802618a2  test    rcx, rcx
0x1802618a5  jz      short loc_1802618D7
0x1802618a7  cmp     rdx, rcx
0x1802618aa  jz      loc_180261A2C
0x1802618b0  mov     rax, [rcx+30h]
0x1802618b4  cmp     [rdx+30h], rax
0x1802618b8  jz      short loc_1802618D7
0x1802618ba  mov     r8, [rdx]
0x1802618bd  mov     rdx, [rcx]
0x1802618c0  cmp     r8, rdx
0x1802618c3  jz      loc_180261A2C
0x1802618c9  mov     rax, [rdx+8]
0x1802618cd  cmp     [r8+8], rax
0x1802618d1  jnz     loc_180261A10
0x1802618d7  xor     al, al
0x1802618d9  test    al, al
0x1802618db  jz      loc_180261B7C
0x1802618e1  mov     rcx, [rbp+8]
0x1802618e5  mov     rdx, [rdi+8]
0x1802618e9  test    rdx, rdx
0x1802618ec  jz      short loc_180261923
0x1802618ee  test    rcx, rcx
0x1802618f1  jz      short loc_180261923
0x1802618f3  cmp     rdx, rcx
0x1802618f6  jz      loc_180261A74
0x1802618fc  mov     rax, [rcx+30h]
0x180261900  cmp     [rdx+30h], rax
0x180261904  jz      short loc_180261923
0x180261906  mov     r8, [rdx]
0x180261909  mov     rdx, [rcx]
0x18026190c  cmp     r8, rdx
0x18026190f  jz      loc_180261A74
0x180261915  mov     rax, [rdx+8]
0x180261919  cmp     [r8+8], rax
0x18026191d  jnz     loc_180261A58
0x180261923  xor     al, al
0x180261925  test    al, al
0x180261927  jnz     short loc_180261975
0x180261929  mov     rcx, [rbp+18h]
0x18026192d  mov     rdx, [rdi+18h]
0x180261931  test    rdx, rdx
0x180261934  jz      short loc_18026196B
0x180261936  test    rcx, rcx
0x180261939  jz      short loc_18026196B
0x18026193b  cmp     rdx, rcx
0x18026193e  jz      loc_180261B06
0x180261944  mov     rax, [rcx+30h]
0x180261948  cmp     [rdx+30h], rax
0x18026194c  jz      short loc_18026196B
0x18026194e  mov     r8, [rdx]
0x180261951  mov     rdx, [rcx]
0x180261954  cmp     r8, rdx
0x180261957  jz      loc_180261B06
0x18026195d  mov     rax, [rdx+8]
0x180261961  cmp     [r8+8], rax
0x180261965  jnz     loc_180261AEA
0x18026196b  xor     al, al
0x18026196d  test    al, al
0x18026196f  jz      loc_1802616B1
0x180261975  mov     rcx, [r15+8]
0x180261979  mov     rdx, [rbp+8]
0x18026197d  test    rdx, rdx
0x180261980  jz      short loc_1802619B7
0x180261982  test    rcx, rcx
0x180261985  jz      short loc_1802619B7
0x180261987  cmp     rdx, rcx
0x18026198a  jz      loc_180261B50
0x180261990  mov     rax, [rcx+30h]
0x180261994  cmp     [rdx+30h], rax
0x180261998  jz      short loc_1802619B7
0x18026199a  mov     r8, [rdx]
0x18026199d  mov     rdx, [rcx]
0x1802619a0  cmp     r8, rdx
0x1802619a3  jz      loc_180261B50
0x1802619a9  mov     rax, [rdx+8]
0x1802619ad  cmp     [r8+8], rax
0x1802619b1  jnz     loc_180261B34
0x1802619b7  xor     al, al
0x1802619b9  test    al, al
0x1802619bb  jz      loc_180261B96
0x1802619c1  mov     al, 1
0x1802619c3  jmp     loc_1802616B3
0x1802619c8  mov     rcx, [r8]
0x1802619cb  mov     rdx, [rdx]
0x1802619ce  add     rdx, 8
0x1802619d2  add     rcx, 8
0x1802619d6  call    cs:__imp___std_type_info_compare
0x1802619dc  test    eax, eax
0x1802619de  jnz     loc_180261843
0x1802619e4  mov     rax, [r15+8]
0x1802619e8  mov     rax, [rax+18h]
0x1802619ec  test    rax, rax
0x1802619ef  jz      loc_180261843
0x1802619f5  mov     rdx, rsi
0x1802619f8  mov     rcx, r15
0x1802619fb  call    cs:__guard_dispatch_icall_fptr
0x180261a01  test    al, al
0x180261a03  jz      loc_180261843
0x180261a09  mov     al, 1
0x180261a0b  jmp     loc_180261845
0x180261a10  mov     rcx, [r8]
0x180261a13  mov     rdx, [rdx]
0x180261a16  add     rdx, 8
0x180261a1a  add     rcx, 8
0x180261a1e  call    cs:__imp___std_type_info_compare
0x180261a24  test    eax, eax
0x180261a26  jnz     loc_1802618D7
0x180261a2c  mov     rax, [rsi+8]
0x180261a30  mov     rax, [rax+18h]
0x180261a34  test    rax, rax
0x180261a37  jz      loc_1802618D7
0x180261a3d  mov     rdx, rdi
0x180261a40  mov     rcx, rsi
0x180261a43  call    cs:__guard_dispatch_icall_fptr
0x180261a49  test    al, al
0x180261a4b  jz      loc_1802618D7
0x180261a51  mov     al, 1
0x180261a53  jmp     loc_1802618D9
0x180261a58  mov     rcx, [r8]
0x180261a5b  mov     rdx, [rdx]
0x180261a5e  add     rdx, 8
0x180261a62  add     rcx, 8
0x180261a66  call    cs:__imp___std_type_info_compare
0x180261a6c  test    eax, eax
0x180261a6e  jnz     loc_180261923
0x180261a74  mov     rax, [rdi+8]
0x180261a78  mov     rax, [rax+18h]
0x180261a7c  test    rax, rax
0x180261a7f  jz      loc_180261923
0x180261a85  mov     rdx, rbp
0x180261a88  mov     rcx, rdi
0x180261a8b  call    cs:__guard_dispatch_icall_fptr
0x180261a91  test    al, al
0x180261a93  jz      loc_180261923
0x180261a99  mov     al, 1
0x180261a9b  jmp     loc_180261925
0x180261aa0  mov     rcx, [r8]
0x180261aa3  mov     rdx, [rdx]
0x180261aa6  add     rdx, 8
0x180261aaa  add     rcx, 8
0x180261aae  call    cs:__imp___std_type_info_compare
0x180261ab4  test    eax, eax
0x180261ab6  jnz     loc_18026188B
0x180261abc  mov     rax, [r15+18h]
0x180261ac0  mov     rax, [rax+18h]
0x180261ac4  test    rax, rax
0x180261ac7  jz      loc_18026188B
0x180261acd  lea     rdx, [rsi+10h]
  ... truncated ...
```
