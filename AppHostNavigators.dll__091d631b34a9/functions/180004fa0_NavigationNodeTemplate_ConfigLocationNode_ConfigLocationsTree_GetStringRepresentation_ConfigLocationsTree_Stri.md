# NavigationNodeTemplate<ConfigLocationNode,ConfigLocationsTree>::GetStringRepresentation(ConfigLocationsTree *,StringRepresentationType,STRU &)

- ea: `0x180004fa0`
- end: `0x18000516a`
- name: `?GetStringRepresentation@?$NavigationNodeTemplate@VConfigLocationNode@@VConfigLocationsTree@@@@UEAAXPEAVConfigLocationsTree@@W4StringRepresentationType@@AEAVSTRU@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(NavigationNodeBase *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b7a0`

## callees

- `0x180004728`
- `0x180004fa0`
- `0x180011200`
- `0x180012608`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800050bd`
- `msvcrt!wcschr` at `0x1800050bd`

## string_xrefs

- `0x1800050d5`: `*[compare-string-ordinal(name(),`

## pseudocode

```c
__int64 __fastcall NavigationNodeTemplate<ConfigLocationNode,ConfigLocationsTree>::GetStringRepresentation(
        NavigationNodeBase *this,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 result; // rax
  unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rdi
  _DWORD *v11; // rax
  const wchar_t *v12; // rcx
  unsigned __int16 *v13; // r12
  struct AppHostNameTable *v14; // rax
  const unsigned __int16 *Prefix; // rax
  wchar_t *v16; // rax
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18[3]; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int16 *v19[15]; // [rsp+48h] [rbp-21h] BYREF
  int pExceptionObject; // [rsp+D0h] [rbp+67h] BYREF

  result = (*(__int64 (__fastcall **)(NavigationNodeBase *))(*(_QWORD *)this + 16LL))(this);
  if ( !result )
  {
    **(_WORD **)(a4 + 8) = 0;
    *(_DWORD *)(a4 + 16) = 0;
    return result;
  }
  (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)result + 72LL))(result, a2, a3, a4);
  v9 = (unsigned __int16 *)&qword_1800181B0;
  if ( !a3 )
    goto LABEL_11;
  if ( !*(_DWORD *)(a4 + 16) )
  {
    v10 = (unsigned __int16 *)&qword_1800181B0;
    goto LABEL_12;
  }
  if ( a3 == 1 )
  {
LABEL_11:
    v10 = L"/";
LABEL_12:
    if ( !a3 )
    {
      v11 = (_DWORD *)(*(__int64 (__fastcall **)(NavigationNodeBase *, unsigned __int16 **))(*(_QWORD *)this + 8LL))(
                        this,
                        v18);
      v12 = L"@";
      if ( *v11 != 2 )
        v12 = &qword_1800181B0;
      v9 = (unsigned __int16 *)v12;
    }
    goto LABEL_16;
  }
  if ( a3 == 2 )
    v10 = L"\\";
  else
    v10 = L"/";
LABEL_16:
  v13 = (unsigned __int16 *)*((_QWORD *)this + 3);
  if ( a3
    || XmlString::IsNCName(*((const unsigned __int16 **)this + 2))
    && (v14 = (struct AppHostNameTable *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2),
        Prefix = NavigationNodeBase::GetPrefix(this, v14),
        XmlString::IsNCName(Prefix)) )
  {
    v18[0] = v10;
    v18[1] = v9;
    v18[2] = v13;
    result = STRU::AuxAppend((STRU *)a4, (const unsigned __int16 *const *const)v18, 3u);
    if ( (int)result < 0 )
    {
      pExceptionObject = result;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v16 = wcschr(v13, 0x27u);
    v19[0] = v10;
    v19[1] = v9;
    v19[4] = v13;
    v19[2] = L"*[compare-string-ordinal(name(),";
    v17 = L"\"";
    if ( !v16 )
      v17 = L"'";
    v19[3] = v17;
    v19[5] = v17;
    v19[6] = L",false())=0]";
    result = STRU::AuxAppend((STRU *)a4, (const unsigned __int16 *const *const)v19, 7u);
    if ( (int)result < 0 )
    {
      pExceptionObject = result;
      throw (long *)&pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004fa0  push    rbp
0x180004fa2  push    rbx
0x180004fa3  push    rsi
0x180004fa4  push    rdi
0x180004fa5  push    r12
0x180004fa7  push    r13
0x180004fa9  push    r14
0x180004fab  push    r15
0x180004fad  lea     rbp, [rsp-1Fh]
0x180004fb2  sub     rsp, 88h
0x180004fb9  mov     rax, [rcx]
0x180004fbc  mov     r14, r9
0x180004fbf  mov     esi, r8d
0x180004fc2  mov     r13, rdx
0x180004fc5  mov     r15, rcx
0x180004fc8  mov     rax, [rax+10h]
0x180004fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd1  mov     rcx, rax
0x180004fd4  test    rax, rax
0x180004fd7  jnz     short loc_180004FF8
0x180004fd9  mov     rcx, [r14+8]
0x180004fdd  mov     [rcx], ax
0x180004fe0  mov     [r14+10h], eax
0x180004fe4  add     rsp, 88h
0x180004feb  pop     r15
0x180004fed  pop     r14
0x180004fef  pop     r13
0x180004ff1  pop     r12
0x180004ff3  pop     rdi
0x180004ff4  pop     rsi
0x180004ff5  pop     rbx
0x180004ff6  pop     rbp
0x180004ff7  retn
0x180004ff8  mov     rax, [rax]
0x180004ffb  mov     r9, r14
0x180004ffe  mov     r8d, esi
0x180005001  mov     rdx, r13
0x180005004  mov     rax, [rax+48h]
0x180005008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500d  lea     rbx, qword_1800181B0
0x180005014  test    esi, esi
0x180005016  jz      short loc_180005046
0x180005018  cmp     dword ptr [r14+10h], 0
0x18000501d  jz      short loc_180005041
0x18000501f  mov     ecx, esi
0x180005021  test    esi, esi
0x180005023  jz      short loc_180005046
0x180005025  sub     ecx, 1
0x180005028  jz      short loc_180005046
0x18000502a  cmp     ecx, 1
0x18000502d  jz      short loc_180005038
0x18000502f  lea     rdi, asc_180018280; "/"
0x180005036  jmp     short loc_180005075
0x180005038  lea     rdi, asc_18001827C; "\\"
0x18000503f  jmp     short loc_180005075
0x180005041  mov     rdi, rbx
0x180005044  jmp     short loc_18000504D
0x180005046  lea     rdi, asc_180018280; "/"
0x18000504d  test    esi, esi
0x18000504f  jnz     short loc_180005075
0x180005051  mov     rax, [r15]
0x180005054  lea     rdx, [rbp+57h+var_90]
0x180005058  mov     rcx, r15
0x18000505b  mov     rax, [rax+8]
0x18000505f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005064  lea     rcx, asc_180018284; "@"
0x18000506b  cmp     dword ptr [rax], 2
0x18000506e  cmovnz  rcx, rbx
0x180005072  mov     rbx, rcx
0x180005075  mov     r12, [r15+18h]
0x180005079  test    esi, esi
0x18000507b  jnz     loc_180005130
0x180005081  mov     rcx, [r15+10h]; unsigned __int16 *
0x180005085  call    ?IsNCName@XmlString@@SA_NPEBG@Z; XmlString::IsNCName(ushort const *)
0x18000508a  test    al, al
0x18000508c  jz      short loc_1800050B5
0x18000508e  mov     rax, [r13+0]
0x180005092  mov     rcx, r13
0x180005095  mov     rax, [rax+10h]
0x180005099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509e  mov     rdx, rax; struct AppHostNameTable *
0x1800050a1  mov     rcx, r15; this
0x1800050a4  call    ?GetPrefix@NavigationNodeBase@@QEAAPEBGPEAVAppHostNameTable@@@Z; NavigationNodeBase::GetPrefix(AppHostNameTable *)
0x1800050a9  mov     rcx, rax; unsigned __int16 *
0x1800050ac  call    ?IsNCName@XmlString@@SA_NPEBG@Z; XmlString::IsNCName(ushort const *)
0x1800050b1  test    al, al
0x1800050b3  jnz     short loc_180005130
0x1800050b5  mov     edx, 27h ; '''; Ch
0x1800050ba  mov     rcx, r12; Str
0x1800050bd  call    cs:__imp_wcschr
0x1800050c3  lea     rdx, asc_180018288; "'"
0x1800050ca  mov     [rbp+57h+var_78], rdi
0x1800050ce  test    rax, rax
0x1800050d1  mov     [rbp+57h+var_70], rbx
0x1800050d5  lea     rax, aCompareStringO; "*[compare-string-ordinal(name(),"
0x1800050dc  mov     [rbp+57h+var_58], r12
0x1800050e0  mov     [rbp+57h+var_68], rax
0x1800050e4  lea     rcx, asc_18001828C; "\""
0x1800050eb  cmovz   rcx, rdx
0x1800050ef  lea     rax, aFalse0; ",false())=0]"
0x1800050f6  mov     [rbp+57h+var_60], rcx
0x1800050fa  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x1800050fe  mov     [rbp+57h+var_50], rcx
0x180005102  mov     r8d, 7; unsigned __int64
0x180005108  mov     rcx, r14; this
0x18000510b  mov     [rbp+57h+var_48], rax
0x18000510f  call    ?AuxAppend@STRU@@AEAAJQEBQEBG_K@Z; STRU::AuxAppend(ushort const * const * const,unsigned __int64)
0x180005114  test    eax, eax
0x180005116  jns     loc_180004FE4
0x18000511c  lea     rdx, _TI1J; pThrowInfo
0x180005123  mov     [rbp+57h+pExceptionObject], eax
0x180005126  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000512a  call    _CxxThrowException_0
0x180005130  mov     r8d, 3; unsigned __int64
0x180005136  mov     [rbp+57h+var_90], rdi
0x18000513a  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x18000513e  mov     [rbp+57h+var_88], rbx
0x180005142  mov     rcx, r14; this
0x180005145  mov     [rbp+57h+var_80], r12
0x180005149  call    ?AuxAppend@STRU@@AEAAJQEBQEBG_K@Z; STRU::AuxAppend(ushort const * const * const,unsigned __int64)
0x18000514e  test    eax, eax
0x180005150  jns     loc_180004FE4
0x180005156  lea     rdx, _TI1J; pThrowInfo
0x18000515d  mov     [rbp+57h+pExceptionObject], eax
0x180005160  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180005164  call    _CxxThrowException_0
```
