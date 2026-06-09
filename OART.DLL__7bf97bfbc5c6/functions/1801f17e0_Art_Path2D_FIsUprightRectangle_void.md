# Art::Path2D::FIsUprightRectangle(void)

- ea: `0x1801f17e0`
- end: `0x1801f1d01`
- name: `?FIsUprightRectangle@Path2D@Art@@QEBA_NXZ`
- size: `1313`
- prototype: `bool __fastcall(Art::Path2D *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1801a0370`
- `0x18062c120`

## callees

- `0x180071720`
- `0x1801f17e0`
- `0x1801f1d10`
- `0x1801f1d68`
- `0x1801f1d88`
- `0x1801f1de0`
- `0x1801f1e38`
- `0x1804b01f0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1b26`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1b6e`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1bb6`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1bfe`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1c48`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1c92`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1b26`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1b6e`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1bb6`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1bfe`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1c48`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801f1c92`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f1836`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f185b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f1880`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f18a9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f18d2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f18f2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f1916`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f193a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f1836`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f185b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f1880`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f18a9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f18d2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f18f2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f1916`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801f193a`

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
0x1801f17e0  mov     [rsp+arg_0], rbx
0x1801f17e5  mov     [rsp+arg_8], rbp
0x1801f17ea  mov     [rsp+arg_10], rsi
0x1801f17ef  push    rdi
0x1801f17f0  push    r14
0x1801f17f2  push    r15
0x1801f17f4  sub     rsp, 20h
0x1801f17f8  mov     rbx, rcx
0x1801f17fb  cmp     dword ptr [rcx+10h], 5
0x1801f17ff  jz      short loc_1801F181C
0x1801f1801  xor     al, al
0x1801f1803  mov     rbx, [rsp+38h+arg_0]
0x1801f1808  mov     rbp, [rsp+38h+arg_8]
0x1801f180d  mov     rsi, [rsp+38h+arg_10]
0x1801f1812  add     rsp, 20h
0x1801f1816  pop     r15
0x1801f1818  pop     r14
0x1801f181a  pop     rdi
0x1801f181b  retn
0x1801f181c  mov     rcx, [rcx+8]
0x1801f1820  call    ??$Is@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(void)
0x1801f1825  test    al, al
0x1801f1827  jz      short loc_1801F1801
0x1801f1829  cmp     dword ptr [rbx+10h], 1
0x1801f182d  ja      short loc_1801F183D
0x1801f182f  xor     edx, edx
0x1801f1831  mov     ecx, 1E892498h
0x1801f1836  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801f183c  int     3; Trap to Debugger
0x1801f183d  mov     rcx, [rbx+8]
0x1801f1841  add     rcx, 10h
0x1801f1845  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x1801f184a  test    al, al
0x1801f184c  jz      short loc_1801F1801
0x1801f184e  cmp     dword ptr [rbx+10h], 2
0x1801f1852  ja      short loc_1801F1862
0x1801f1854  xor     edx, edx
0x1801f1856  mov     ecx, 1E892498h
0x1801f185b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801f1861  int     3; Trap to Debugger
0x1801f1862  mov     rcx, [rbx+8]
0x1801f1866  add     rcx, 20h ; ' '
0x1801f186a  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x1801f186f  test    al, al
0x1801f1871  jz      short loc_1801F1801
0x1801f1873  cmp     dword ptr [rbx+10h], 3
0x1801f1877  ja      short loc_1801F1887
0x1801f1879  xor     edx, edx
0x1801f187b  mov     ecx, 1E892498h
0x1801f1880  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801f1886  int     3; Trap to Debugger
0x1801f1887  mov     rcx, [rbx+8]
0x1801f188b  add     rcx, 30h ; '0'
0x1801f188f  call    ??$Is@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::LineTo>(void)
0x1801f1894  test    al, al
0x1801f1896  jz      loc_1801F1801
0x1801f189c  cmp     dword ptr [rbx+10h], 4
0x1801f18a0  ja      short loc_1801F18B0
0x1801f18a2  xor     edx, edx
0x1801f18a4  mov     ecx, 1E892498h
0x1801f18a9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801f18af  int     3; Trap to Debugger
0x1801f18b0  mov     rcx, [rbx+8]
0x1801f18b4  add     rcx, 40h ; '@'
0x1801f18b8  call    ??$Is@UClose@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::Close>(void)
0x1801f18bd  test    al, al
0x1801f18bf  jz      loc_1801F1801
0x1801f18c5  cmp     dword ptr [rbx+10h], 0
0x1801f18c9  ja      short loc_1801F18D9
0x1801f18cb  xor     edx, edx
0x1801f18cd  mov     ecx, 1E892498h
0x1801f18d2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801f18d8  nop
0x1801f18d9  mov     rcx, [rbx+8]
0x1801f18dd  call    ??$Get@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DMoveTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::MoveTo>(void)
0x1801f18e2  mov     r15, rax
0x1801f18e5  cmp     dword ptr [rbx+10h], 1
0x1801f18e9  ja      short loc_1801F18F9
0x1801f18eb  xor     edx, edx
0x1801f18ed  mov     ecx, 1E892498h
0x1801f18f2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801f18f8  int     3; Trap to Debugger
0x1801f18f9  mov     rcx, [rbx+8]
0x1801f18fd  add     rcx, 10h
0x1801f1901  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x1801f1906  mov     rsi, rax
0x1801f1909  cmp     dword ptr [rbx+10h], 2
0x1801f190d  ja      short loc_1801F191D
0x1801f190f  xor     edx, edx
0x1801f1911  mov     ecx, 1E892498h
0x1801f1916  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801f191c  int     3; Trap to Debugger
0x1801f191d  mov     rcx, [rbx+8]
0x1801f1921  add     rcx, 20h ; ' '
0x1801f1925  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x1801f192a  mov     rdi, rax
0x1801f192d  cmp     dword ptr [rbx+10h], 3
0x1801f1931  ja      short loc_1801F1941
0x1801f1933  xor     edx, edx
0x1801f1935  mov     ecx, 1E892498h
0x1801f193a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801f1940  int     3; Trap to Debugger
0x1801f1941  mov     rcx, [rbx+8]
0x1801f1945  add     rcx, 30h ; '0'
0x1801f1949  call    ??$Get@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::LineTo>(void)
0x1801f194e  mov     rbp, rax
0x1801f1951  mov     rcx, [rsi+8]
0x1801f1955  mov     rdx, [r15+8]
0x1801f1959  test    rdx, rdx
0x1801f195c  jz      short loc_1801F1993
0x1801f195e  test    rcx, rcx
0x1801f1961  jz      short loc_1801F1993
0x1801f1963  cmp     rdx, rcx
0x1801f1966  jz      loc_1801F1B34
0x1801f196c  mov     rax, [rcx+30h]
0x1801f1970  cmp     [rdx+30h], rax
0x1801f1974  jz      short loc_1801F1993
0x1801f1976  mov     r8, [rdx]
0x1801f1979  mov     rdx, [rcx]
0x1801f197c  cmp     r8, rdx
0x1801f197f  jz      loc_1801F1B34
0x1801f1985  mov     rax, [rdx+8]
0x1801f1989  cmp     [r8+8], rax
0x1801f198d  jnz     loc_1801F1B18
0x1801f1993  xor     al, al
0x1801f1995  test    al, al
0x1801f1997  jnz     short loc_1801F19E5
0x1801f1999  mov     rcx, [rsi+18h]
0x1801f199d  mov     rdx, [r15+18h]
0x1801f19a1  test    rdx, rdx
0x1801f19a4  jz      short loc_1801F19DB
0x1801f19a6  test    rcx, rcx
0x1801f19a9  jz      short loc_1801F19DB
0x1801f19ab  cmp     rdx, rcx
0x1801f19ae  jz      loc_1801F1C0C
0x1801f19b4  mov     rax, [rcx+30h]
0x1801f19b8  cmp     [rdx+30h], rax
0x1801f19bc  jz      short loc_1801F19DB
0x1801f19be  mov     r8, [rdx]
0x1801f19c1  mov     rdx, [rcx]
0x1801f19c4  cmp     r8, rdx
0x1801f19c7  jz      loc_1801F1C0C
0x1801f19cd  mov     rax, [rdx+8]
0x1801f19d1  cmp     [r8+8], rax
0x1801f19d5  jnz     loc_1801F1BF0
0x1801f19db  xor     al, al
0x1801f19dd  test    al, al
0x1801f19df  jz      loc_1801F1801
0x1801f19e5  mov     rcx, [rdi+8]
0x1801f19e9  mov     rdx, [rsi+8]
0x1801f19ed  test    rdx, rdx
0x1801f19f0  jz      short loc_1801F1A27
0x1801f19f2  test    rcx, rcx
0x1801f19f5  jz      short loc_1801F1A27
0x1801f19f7  cmp     rdx, rcx
0x1801f19fa  jz      loc_1801F1B7C
0x1801f1a00  mov     rax, [rcx+30h]
0x1801f1a04  cmp     [rdx+30h], rax
0x1801f1a08  jz      short loc_1801F1A27
0x1801f1a0a  mov     r8, [rdx]
0x1801f1a0d  mov     rdx, [rcx]
0x1801f1a10  cmp     r8, rdx
0x1801f1a13  jz      loc_1801F1B7C
0x1801f1a19  mov     rax, [rdx+8]
0x1801f1a1d  cmp     [r8+8], rax
0x1801f1a21  jnz     loc_1801F1B60
0x1801f1a27  xor     al, al
0x1801f1a29  test    al, al
0x1801f1a2b  jz      loc_1801F1CCC
0x1801f1a31  mov     rcx, [rbp+8]
0x1801f1a35  mov     rdx, [rdi+8]
0x1801f1a39  test    rdx, rdx
0x1801f1a3c  jz      short loc_1801F1A73
0x1801f1a3e  test    rcx, rcx
0x1801f1a41  jz      short loc_1801F1A73
0x1801f1a43  cmp     rdx, rcx
0x1801f1a46  jz      loc_1801F1BC4
0x1801f1a4c  mov     rax, [rcx+30h]
0x1801f1a50  cmp     [rdx+30h], rax
0x1801f1a54  jz      short loc_1801F1A73
0x1801f1a56  mov     r8, [rdx]
0x1801f1a59  mov     rdx, [rcx]
0x1801f1a5c  cmp     r8, rdx
0x1801f1a5f  jz      loc_1801F1BC4
0x1801f1a65  mov     rax, [rdx+8]
0x1801f1a69  cmp     [r8+8], rax
0x1801f1a6d  jnz     loc_1801F1BA8
0x1801f1a73  xor     al, al
0x1801f1a75  test    al, al
0x1801f1a77  jnz     short loc_1801F1AC5
0x1801f1a79  mov     rcx, [rbp+18h]
0x1801f1a7d  mov     rdx, [rdi+18h]
0x1801f1a81  test    rdx, rdx
0x1801f1a84  jz      short loc_1801F1ABB
0x1801f1a86  test    rcx, rcx
0x1801f1a89  jz      short loc_1801F1ABB
0x1801f1a8b  cmp     rdx, rcx
0x1801f1a8e  jz      loc_1801F1C56
0x1801f1a94  mov     rax, [rcx+30h]
0x1801f1a98  cmp     [rdx+30h], rax
0x1801f1a9c  jz      short loc_1801F1ABB
0x1801f1a9e  mov     r8, [rdx]
0x1801f1aa1  mov     rdx, [rcx]
0x1801f1aa4  cmp     r8, rdx
0x1801f1aa7  jz      loc_1801F1C56
0x1801f1aad  mov     rax, [rdx+8]
0x1801f1ab1  cmp     [r8+8], rax
0x1801f1ab5  jnz     loc_1801F1C3A
0x1801f1abb  xor     al, al
0x1801f1abd  test    al, al
0x1801f1abf  jz      loc_1801F1801
0x1801f1ac5  mov     rcx, [r15+8]
0x1801f1ac9  mov     rdx, [rbp+8]
0x1801f1acd  test    rdx, rdx
0x1801f1ad0  jz      short loc_1801F1B07
0x1801f1ad2  test    rcx, rcx
0x1801f1ad5  jz      short loc_1801F1B07
0x1801f1ad7  cmp     rdx, rcx
0x1801f1ada  jz      loc_1801F1CA0
0x1801f1ae0  mov     rax, [rcx+30h]
0x1801f1ae4  cmp     [rdx+30h], rax
0x1801f1ae8  jz      short loc_1801F1B07
0x1801f1aea  mov     r8, [rdx]
0x1801f1aed  mov     rdx, [rcx]
0x1801f1af0  cmp     r8, rdx
0x1801f1af3  jz      loc_1801F1CA0
0x1801f1af9  mov     rax, [rdx+8]
0x1801f1afd  cmp     [r8+8], rax
0x1801f1b01  jnz     loc_1801F1C84
0x1801f1b07  xor     al, al
0x1801f1b09  test    al, al
0x1801f1b0b  jz      loc_1801F1CE6
0x1801f1b11  mov     al, 1
0x1801f1b13  jmp     loc_1801F1803
0x1801f1b18  mov     rcx, [r8]
0x1801f1b1b  mov     rdx, [rdx]
0x1801f1b1e  add     rdx, 8
0x1801f1b22  add     rcx, 8
0x1801f1b26  call    cs:__imp___std_type_info_compare
0x1801f1b2c  test    eax, eax
0x1801f1b2e  jnz     loc_1801F1993
0x1801f1b34  mov     rax, [r15+8]
0x1801f1b38  mov     rax, [rax+18h]
0x1801f1b3c  test    rax, rax
0x1801f1b3f  jz      loc_1801F1993
0x1801f1b45  mov     rdx, rsi
0x1801f1b48  mov     rcx, r15
0x1801f1b4b  call    cs:__guard_dispatch_icall_fptr
0x1801f1b51  test    al, al
0x1801f1b53  jz      loc_1801F1993
0x1801f1b59  mov     al, 1
0x1801f1b5b  jmp     loc_1801F1995
0x1801f1b60  mov     rcx, [r8]
0x1801f1b63  mov     rdx, [rdx]
0x1801f1b66  add     rdx, 8
0x1801f1b6a  add     rcx, 8
0x1801f1b6e  call    cs:__imp___std_type_info_compare
0x1801f1b74  test    eax, eax
0x1801f1b76  jnz     loc_1801F1A27
0x1801f1b7c  mov     rax, [rsi+8]
0x1801f1b80  mov     rax, [rax+18h]
0x1801f1b84  test    rax, rax
0x1801f1b87  jz      loc_1801F1A27
0x1801f1b8d  mov     rdx, rdi
0x1801f1b90  mov     rcx, rsi
0x1801f1b93  call    cs:__guard_dispatch_icall_fptr
0x1801f1b99  test    al, al
0x1801f1b9b  jz      loc_1801F1A27
0x1801f1ba1  mov     al, 1
0x1801f1ba3  jmp     loc_1801F1A29
0x1801f1ba8  mov     rcx, [r8]
0x1801f1bab  mov     rdx, [rdx]
0x1801f1bae  add     rdx, 8
0x1801f1bb2  add     rcx, 8
0x1801f1bb6  call    cs:__imp___std_type_info_compare
0x1801f1bbc  test    eax, eax
0x1801f1bbe  jnz     loc_1801F1A73
0x1801f1bc4  mov     rax, [rdi+8]
0x1801f1bc8  mov     rax, [rax+18h]
0x1801f1bcc  test    rax, rax
0x1801f1bcf  jz      loc_1801F1A73
0x1801f1bd5  mov     rdx, rbp
0x1801f1bd8  mov     rcx, rdi
0x1801f1bdb  call    cs:__guard_dispatch_icall_fptr
0x1801f1be1  test    al, al
0x1801f1be3  jz      loc_1801F1A73
0x1801f1be9  mov     al, 1
0x1801f1beb  jmp     loc_1801F1A75
0x1801f1bf0  mov     rcx, [r8]
0x1801f1bf3  mov     rdx, [rdx]
0x1801f1bf6  add     rdx, 8
0x1801f1bfa  add     rcx, 8
0x1801f1bfe  call    cs:__imp___std_type_info_compare
0x1801f1c04  test    eax, eax
0x1801f1c06  jnz     loc_1801F19DB
0x1801f1c0c  mov     rax, [r15+18h]
0x1801f1c10  mov     rax, [rax+18h]
0x1801f1c14  test    rax, rax
0x1801f1c17  jz      loc_1801F19DB
0x1801f1c1d  lea     rdx, [rsi+10h]
  ... truncated ...
```
