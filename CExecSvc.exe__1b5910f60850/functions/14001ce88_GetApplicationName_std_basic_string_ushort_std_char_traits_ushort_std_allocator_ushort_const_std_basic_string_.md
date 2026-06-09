# GetApplicationName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14001ce88`
- end: `0x14001d47a`
- name: `?GetApplicationName@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@00@Z`
- size: `1522`
- prototype: `_QWORD *__fastcall(_QWORD *Src, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140016cc0`

## callees

- `0x140002310`
- `0x140002698`
- `0x140002ecc`
- `0x140003bc0`
- `0x140003ce0`
- `0x140003e3c`
- `0x140003ea4`
- `0x140006790`
- `0x1400068ac`
- `0x1400073c4`
- `0x140008160`
- `0x140012bec`
- `0x1400133d4`
- `0x140015f94`
- `0x14001aec4`
- `0x14001ce88`
- `0x14001d480`
- `0x14001d630`
- `0x14001d75c`

## string_xrefs

- `0x14001d13b`: `onecore\vm\compute\service\cexec\lib\pathhandling.cpp`
- `0x14001d2ec`: `onecore\vm\compute\service\cexec\lib\pathhandling.cpp`

## pseudocode

```c
_QWORD *__fastcall GetApplicationName(_QWORD *Src, _QWORD *a2, __int64 a3)
{
  __int64 v6; // r14
  unsigned __int64 v7; // rdx
  __int128 *p_Srca; // rcx
  __int128 *v9; // rax
  unsigned __int64 v10; // rdx
  __int128 *v11; // rcx
  unsigned __int64 v12; // rcx
  _WORD *v13; // rdi
  unsigned __int64 i; // rcx
  unsigned __int64 v15; // rax
  _WORD *v16; // rcx
  _QWORD *v17; // rsi
  char *v18; // rdi
  __int64 trivial_2; // rax
  __int64 v20; // rdx
  WCHAR *v21; // rdi
  unsigned int v22; // eax
  unsigned __int64 v23; // r12
  __int64 v24; // r9
  unsigned __int64 v25; // rcx
  char *v26; // r13
  wchar_t *v27; // rdi
  __int64 first_of_trivial_pos_2; // rax
  unsigned __int64 v29; // rdi
  unsigned __int64 v30; // r12
  const wchar_t *v31; // rcx
  size_t v32; // r8
  unsigned __int64 v33; // r8
  _QWORD *v34; // rdx
  unsigned int v35; // eax
  WCHAR *v36; // rax
  char **v37; // rsi
  unsigned __int64 v38; // rcx
  char *v39; // rdx
  unsigned __int64 v40; // rcx
  char *v41; // rdx
  unsigned __int64 v42; // rax
  __int64 v43; // rax
  char j; // [rsp+30h] [rbp-D0h]
  _OWORD v46[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v47; // [rsp+60h] [rbp-A0h]
  _BYTE v48[256]; // [rsp+70h] [rbp-90h] BYREF
  __int128 Srca; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v50; // [rsp+180h] [rbp+80h]
  unsigned __int64 v51; // [rsp+188h] [rbp+88h]
  WCHAR FileName[8]; // [rsp+190h] [rbp+90h] BYREF
  __m128i si128; // [rsp+1A0h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v47 = Src;
  v6 = -1;
  if ( dword_14003A6F8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 16LL) )
  {
    Init_thread_header(&dword_14003A6F8);
    if ( dword_14003A6F8 == -1 )
    {
      GetSystemPaths();
      atexit(GetApplicationName_::_2_::_dynamic_atexit_destructor_for__systemPaths__);
      Init_thread_footer(&dword_14003A6F8);
    }
  }
  Srca = 0;
  v50 = 0;
  v51 = 7;
  LOWORD(Srca) = 0;
  if ( *(_QWORD *)(a3 + 16) )
  {
    std::wstring::operator+=(&Srca);
    v7 = v50;
    p_Srca = &Srca;
    if ( v50 >= v51 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Srca);
    }
    else
    {
      ++v50;
      if ( v51 > 7 )
        p_Srca = (__int128 *)Srca;
      *(_DWORD *)((char *)p_Srca + 2 * v7) = 59;
    }
  }
  std::wstring::operator+=(&Srca);
  std::wstring::operator+=(&Srca);
  v9 = &Srca;
  if ( v51 > 7 )
    v9 = (__int128 *)Srca;
  if ( *((_WORD *)v9 + v50 - 1) == 59 )
  {
    v10 = --v50;
    v11 = &Srca;
    if ( v51 > 7 )
      v11 = (__int128 *)Srca;
    *((_WORD *)v11 + v10) = 0;
  }
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 7;
  *(_WORD *)Src = 0;
  *((_OWORD *)Src + 2) = 0;
  Src[6] = 0;
  Src[7] = 7;
  *((_WORD *)Src + 16) = 0;
  v12 = Src[2];
  if ( v12 < 0x104 )
  {
    if ( 260 - v12 > 7 - v12 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(Src);
      goto LABEL_23;
    }
    Src[2] = 260;
    v13 = (_WORD *)Src + v12;
    if ( 260 != v12 )
    {
      for ( i = 260 - v12; i; --i )
        *v13++ = 0;
    }
  }
  else
  {
    Src[2] = 260;
  }
  *((_WORD *)Src + 260) = 0;
LABEL_23:
  v15 = a2[2];
  if ( v15 && (a2[3] <= 7u ? (v16 = a2) : (v16 = (_WORD *)*a2), *v16 == 34) )
  {
    if ( a2[3] <= 7u )
      v17 = a2;
    else
      v17 = (_QWORD *)*a2;
    if ( v15 > 1 )
    {
      v18 = (char *)v17 + 2 * v15;
      trivial_2 = _std_find_trivial_2((char *)v17 + 2, v18, 34);
      if ( (char *)trivial_2 != v18 )
        v6 = (trivial_2 - (__int64)v17) >> 1;
    }
    *(_OWORD *)FileName = 0;
    si128 = 0;
    v20 = a2[2];
    if ( !v20 )
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    if ( v20 - 1 >= (unsigned __int64)(v6 - 1) )
      v20 = v6;
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    std::wstring::_Construct<1,unsigned short const *>(FileName, (char *)a2 + 2, v20 - 1);
    v21 = FileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v21 = *(WCHAR **)FileName;
    v22 = SearchPathForExe(FileName, &Srca, (char *)Src);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\pathhandling.cpp",
      (const char *)v22,
      (unsigned int)"%ws",
      (const char *)v21);
  }
  else
  {
    *(_OWORD *)FileName = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    FileName[0] = 0;
    v23 = 0;
    v24 = 87;
    for ( j = 0; ; j = 1 )
    {
      v25 = a2[2];
      if ( v23 >= v25 )
        break;
      v26 = a2[3] <= 7u ? (char *)a2 : (char *)*a2;
      v27 = (wchar_t *)&v26[2 * v23];
      if ( v25 - v23 + 2 < 0x10 )
      {
        v30 = (unsigned __int64)&v26[2 * v25];
        memset_0(v48, 0, sizeof(v48));
        v31 = L" \t";
        v32 = 2;
        while ( *v31 < 0x100u )
        {
          v48[*(unsigned __int8 *)v31++] = 1;
          if ( v31 == L"" )
          {
            while ( (unsigned __int64)v27 < v30 )
            {
              if ( *v27 < 0x100u && v48[*v27] )
                goto LABEL_68;
              ++v27;
            }
            goto LABEL_59;
          }
        }
        while ( (unsigned __int64)v27 < v30 )
        {
          if ( wmemchr(L" \t", *v27, v32) )
          {
LABEL_68:
            v29 = ((char *)v27 - v26) >> 1;
            goto LABEL_60;
          }
          v27 = (wchar_t *)((char *)v27 + v32);
        }
LABEL_59:
        v29 = -1;
      }
      else
      {
        first_of_trivial_pos_2 = _std_find_first_of_trivial_pos_2(&v26[2 * v23], v25 - v23, L" \t", 2);
        v29 = first_of_trivial_pos_2 + v23;
        if ( first_of_trivial_pos_2 == -1 )
          v29 = -1;
      }
LABEL_60:
      v33 = a2[2];
      if ( v33 >= v29 )
        v33 = v29;
      if ( a2[3] <= 7u )
        v34 = a2;
      else
        v34 = (_QWORD *)*a2;
      std::wstring::_Assign<unsigned short>(FileName, v34, v33);
      v23 = v29 + 1;
      if ( v29 == -1 )
        v23 = -1;
      v35 = SearchPathForExe(FileName, &Srca, (char *)Src);
      v24 = v35;
      if ( !v35 )
        break;
    }
    v36 = FileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v36 = *(WCHAR **)FileName;
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\pathhandling.cpp",
      (const char *)v24,
      (unsigned int)"%ws",
      (const char *)v36);
    v37 = (char **)(Src + 4);
    if ( j )
    {
      v38 = Src[6];
      if ( v38 >= Src[7] )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src + 4);
      }
      else
      {
        Src[6] = v38 + 1;
        if ( Src[7] <= 7u )
          v39 = (char *)(Src + 4);
        else
          v39 = *v37;
        *(_DWORD *)&v39[2 * v38] = 34;
      }
      std::wstring::operator+=(Src + 4);
      v40 = Src[6];
      if ( v40 >= Src[7] )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src + 4);
      }
      else
      {
        Src[6] = v40 + 1;
        if ( Src[7] <= 7u )
          v41 = (char *)(Src + 4);
        else
          v41 = *v37;
        *(_DWORD *)&v41[2 * v40] = 34;
      }
      memset(v46, 0, sizeof(v46));
      v42 = a2[2];
      if ( v42 < si128.m128i_i64[0] )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      v43 = v42 - si128.m128i_i64[0];
      if ( v43 != -1 )
        v6 = v43;
      if ( a2[3] > 7u )
        a2 = (_QWORD *)*a2;
      std::wstring::_Construct<1,unsigned short const *>(v46, (char *)a2 + 2 * si128.m128i_i64[0], v6);
      std::wstring::operator+=(Src + 4);
      std::wstring::~wstring(v46);
    }
  }
  std::wstring::~wstring(FileName);
  std::wstring::~wstring(&Srca);
  return Src;
}

```

## disassembly

```asm
0x14001ce88  push    rbp
0x14001ce8a  push    rbx
0x14001ce8b  push    rsi
0x14001ce8c  push    rdi
0x14001ce8d  push    r12
0x14001ce8f  push    r13
0x14001ce91  push    r14
0x14001ce93  push    r15
0x14001ce95  lea     rbp, [rsp-0C8h]
0x14001ce9d  sub     rsp, 1C8h
0x14001cea4  mov     rax, cs:__security_cookie
0x14001ceab  xor     rax, rsp
0x14001ceae  mov     [rbp+100h+var_50], rax
0x14001ceb5  mov     rsi, r9
0x14001ceb8  mov     rdi, r8
0x14001cebb  mov     rbx, rdx
0x14001cebe  mov     r15, rcx
0x14001cec1  mov     [rsp+200h+var_1A0], rcx
0x14001cec6  xor     r13d, r13d
0x14001cec9  mov     [rsp+200h+var_1CC], r13d
0x14001cece  mov     ecx, 10h
0x14001ced3  mov     rax, gs:58h
0x14001cedc  mov     rax, [rax]
0x14001cedf  or      r14, 0FFFFFFFFFFFFFFFFh
0x14001cee3  mov     eax, [rcx+rax]
0x14001cee6  cmp     cs:dword_14003A6F8, eax
0x14001ceec  jg      loc_14001D438
0x14001cef2  xorps   xmm0, xmm0
0x14001cef5  movups  [rbp+100h+Src], xmm0
0x14001cef9  mov     [rbp+100h+var_80], r13
0x14001cf00  mov     r12d, 7
0x14001cf06  mov     [rbp+100h+var_78], r12
0x14001cf0d  mov     word ptr [rbp+100h+Src], r13w
0x14001cf12  cmp     [rdi+10h], r13
0x14001cf16  jz      short loc_14001CF63
0x14001cf18  mov     rdx, rdi
0x14001cf1b  lea     rcx, [rbp+100h+Src]; Src
0x14001cf1f  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14001cf24  mov     rdx, [rbp+100h+var_80]
0x14001cf2b  lea     rcx, [rbp+100h+Src]; Src
0x14001cf2f  lea     edi, [r12+34h]
0x14001cf34  cmp     rdx, [rbp+100h+var_78]
0x14001cf3b  jnb     short loc_14001CF59
0x14001cf3d  lea     rax, [rdx+1]
0x14001cf41  mov     [rbp+100h+var_80], rax
0x14001cf48  cmp     [rbp+100h+var_78], r12
0x14001cf4f  cmova   rcx, qword ptr [rbp+100h+Src]
0x14001cf54  mov     [rcx+rdx*2], edi
0x14001cf57  jmp     short loc_14001CF68
0x14001cf59  mov     r9d, edi
0x14001cf5c  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001cf61  jmp     short loc_14001CF68
0x14001cf63  mov     edi, 3Bh ; ';'
0x14001cf68  lea     rdx, xmmword_14003A700
0x14001cf6f  lea     rcx, [rbp+100h+Src]; Src
0x14001cf73  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14001cf78  mov     rdx, rsi
0x14001cf7b  lea     rcx, [rbp+100h+Src]; Src
0x14001cf7f  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14001cf84  lea     rax, [rbp+100h+Src]
0x14001cf88  cmp     [rbp+100h+var_78], r12
0x14001cf8f  cmova   rax, qword ptr [rbp+100h+Src]
0x14001cf94  mov     rdx, [rbp+100h+var_80]
0x14001cf9b  cmp     [rax+rdx*2-2], di
0x14001cfa0  jnz     short loc_14001CFC1
0x14001cfa2  dec     rdx
0x14001cfa5  mov     [rbp+100h+var_80], rdx
0x14001cfac  lea     rcx, [rbp+100h+Src]
0x14001cfb0  cmp     [rbp+100h+var_78], r12
0x14001cfb7  cmova   rcx, qword ptr [rbp+100h+Src]
0x14001cfbc  mov     [rcx+rdx*2], r13w
0x14001cfc1  xorps   xmm0, xmm0
0x14001cfc4  movups  xmmword ptr [r15], xmm0
0x14001cfc8  mov     [r15+10h], r13
0x14001cfcc  mov     [r15+18h], r12
0x14001cfd0  mov     [r15], r13w
0x14001cfd4  movups  xmmword ptr [r15+20h], xmm0
0x14001cfd9  mov     [r15+30h], r13
0x14001cfdd  mov     [r15+38h], r12
0x14001cfe1  mov     [r15+20h], r13w
0x14001cfe6  mov     [rsp+200h+var_1CC], 1
0x14001cfee  mov     rcx, [r15+10h]
0x14001cff2  mov     edi, 104h
0x14001cff7  cmp     rcx, rdi
0x14001cffa  jb      short loc_14001D002
0x14001cffc  mov     [r15+10h], rdi
0x14001d000  jmp     short loc_14001D02A
0x14001d002  mov     rdx, rdi
0x14001d005  sub     rdx, rcx
0x14001d008  mov     rax, r12
0x14001d00b  sub     rax, rcx
0x14001d00e  cmp     rdx, rax
0x14001d011  ja      short loc_14001D034
0x14001d013  mov     [r15+10h], rdi
0x14001d017  lea     rdi, [r15+rcx*2]
0x14001d01b  test    rdx, rdx
0x14001d01e  jz      short loc_14001D02A
0x14001d020  movzx   eax, r13w
0x14001d024  mov     rcx, rdx
0x14001d027  rep stosw
0x14001d02a  mov     [r15+208h], r13w
0x14001d032  jmp     short loc_14001D03F
0x14001d034  mov     r9, rdx
0x14001d037  mov     rcx, r15; Src
0x14001d03a  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x14001d03f  mov     rax, [rbx+10h]
0x14001d043  mov     edi, 22h ; '"'
0x14001d048  test    rax, rax
0x14001d04b  jz      loc_14001D152
0x14001d051  cmp     [rbx+18h], r12
0x14001d055  jbe     short loc_14001D05C
0x14001d057  mov     rcx, [rbx]
0x14001d05a  jmp     short loc_14001D05F
0x14001d05c  mov     rcx, rbx
0x14001d05f  cmp     [rcx], di
0x14001d062  jnz     loc_14001D152
0x14001d068  cmp     [rbx+18h], r12
0x14001d06c  jbe     short loc_14001D073
0x14001d06e  mov     rsi, [rbx]
0x14001d071  jmp     short loc_14001D076
0x14001d073  mov     rsi, rbx
0x14001d076  cmp     rax, 1
0x14001d07a  jbe     short loc_14001D0A0
0x14001d07c  lea     rdi, [rsi+rax*2]
0x14001d080  mov     r8d, 22h ; '"'
0x14001d086  lea     rcx, [rsi+2]
0x14001d08a  mov     rdx, rdi
0x14001d08d  call    __std_find_trivial_2
0x14001d092  cmp     rax, rdi
0x14001d095  jz      short loc_14001D0A0
0x14001d097  mov     r14, rax
0x14001d09a  sub     r14, rsi
0x14001d09d  sar     r14, 1
0x14001d0a0  xorps   xmm0, xmm0
0x14001d0a3  movups  xmmword ptr [rbp+100h+FileName], xmm0
0x14001d0aa  xorps   xmm1, xmm1
0x14001d0ad  movdqu  [rbp+100h+var_60], xmm1
0x14001d0b5  mov     rdx, [rbx+10h]
0x14001d0b9  cmp     rdx, 1
0x14001d0bd  jb      loc_14001D474
0x14001d0c3  lea     rcx, [rdx-1]
0x14001d0c7  lea     rax, [r14-1]
0x14001d0cb  cmp     rcx, rax
0x14001d0ce  cmovnb  rdx, r14
0x14001d0d2  lea     r8, [rdx-1]
0x14001d0d6  cmp     [rbx+18h], r12
0x14001d0da  jbe     short loc_14001D0DF
0x14001d0dc  mov     rbx, [rbx]
0x14001d0df  lea     rdx, [rbx+2]
0x14001d0e3  lea     rcx, [rbp+100h+FileName]
0x14001d0ea  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001d0ef  mov     [rsp+200h+var_1CC], 3
0x14001d0f7  lea     rdi, [rbp+100h+FileName]
0x14001d0fe  cmp     qword ptr [rbp+100h+var_60+8], r12
0x14001d105  cmova   rdi, qword ptr [rbp+100h+FileName]
0x14001d10d  mov     r8, r15; Src
0x14001d110  lea     rdx, [rbp+100h+Src]; lpPath
0x14001d114  lea     rcx, [rbp+100h+FileName]; lpFileName
0x14001d11b  call    ?SearchPathForExe@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@@Z; SearchPathForExe(std::wstring const &,std::wstring const &,std::wstring &)
0x14001d120  mov     rcx, [rbp+108h]; this
0x14001d127  mov     [rsp+200h+var_1D8], rdi; char *
0x14001d12c  lea     rdx, aWs; "%ws"
0x14001d133  mov     qword ptr [rsp+200h+var_1E0], rdx; unsigned int
0x14001d138  mov     r9d, eax; char *
0x14001d13b  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001d142  mov     edx, 7Ch ; '|'; void *
0x14001d147  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x14001d14c  nop
0x14001d14d  jmp     loc_14001D3F6
0x14001d152  xorps   xmm0, xmm0
0x14001d155  movups  xmmword ptr [rbp+100h+FileName], xmm0
0x14001d15c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001d164  movdqu  [rbp+100h+var_60], xmm1
0x14001d16c  mov     [rbp+100h+FileName], r13w
0x14001d174  mov     r12, r13
0x14001d177  mov     r9d, 57h ; 'W'; char *
0x14001d17d  mov     [rsp+200h+var_1D0], r13b
0x14001d182  mov     esi, 100h
0x14001d187  mov     rcx, [rbx+10h]
0x14001d18b  cmp     r12, rcx
0x14001d18e  jnb     loc_14001D2BD
0x14001d194  cmp     qword ptr [rbx+18h], 7
0x14001d199  jbe     short loc_14001D1A0
0x14001d19b  mov     r13, [rbx]
0x14001d19e  jmp     short loc_14001D1A3
0x14001d1a0  mov     r13, rbx
0x14001d1a3  lea     rdi, ds:0[r12*2]
0x14001d1ab  add     rdi, r13
0x14001d1ae  mov     rdx, rcx
0x14001d1b1  sub     rdx, r12
0x14001d1b4  lea     rax, [rdx+2]
0x14001d1b8  cmp     rax, 10h
0x14001d1bc  jb      short loc_14001D1E0
0x14001d1be  mov     r9d, 2
0x14001d1c4  lea     r8, S; " \t"
0x14001d1cb  mov     rcx, rdi
0x14001d1ce  call    __std_find_first_of_trivial_pos_2
0x14001d1d3  lea     rdi, [rax+r12]
0x14001d1d7  cmp     rax, r14
0x14001d1da  cmovz   rdi, rax
0x14001d1de  jmp     short loc_14001D23F
0x14001d1e0  lea     r12, ds:0[rcx*2]
0x14001d1e8  add     r12, r13
0x14001d1eb  mov     r8, rsi; Size
0x14001d1ee  xor     edx, edx; Val
0x14001d1f0  lea     rcx, [rsp+200h+var_190]; void *
0x14001d1f5  call    memset_0
0x14001d1fa  lea     rcx, S; " \t"
0x14001d201  mov     r8d, 2
0x14001d207  cmp     [rcx], si
0x14001d20a  jnb     short loc_14001D26D
0x14001d20c  movzx   eax, byte ptr [rcx]
0x14001d20f  mov     [rsp+rax+200h+var_190], 1
0x14001d214  add     rcx, r8
0x14001d217  lea     rax, S+4; ""
0x14001d21e  cmp     rcx, rax
0x14001d221  jnz     short loc_14001D207
0x14001d223  jmp     short loc_14001D237
0x14001d225  cmp     [rdi], si
0x14001d228  jnb     short loc_14001D234
0x14001d22a  movzx   eax, word ptr [rdi]
0x14001d22d  cmp     [rsp+rax+200h+var_190], 0
0x14001d232  jnz     short loc_14001D274
0x14001d234  add     rdi, r8
0x14001d237  cmp     rdi, r12
0x14001d23a  jb      short loc_14001D225
0x14001d23c  mov     rdi, r14
0x14001d23f  mov     r8, [rbx+10h]
0x14001d243  cmp     r8, rdi
0x14001d246  cmovnb  r8, rdi
0x14001d24a  cmp     qword ptr [rbx+18h], 7
0x14001d24f  jbe     short loc_14001D27C
0x14001d251  mov     rdx, [rbx]
0x14001d254  jmp     short loc_14001D27F
0x14001d256  movzx   edx, word ptr [rdi]; C
0x14001d259  lea     rcx, S; " \t"
0x14001d260  call    wmemchr
0x14001d265  test    rax, rax
0x14001d268  jnz     short loc_14001D274
0x14001d26a  add     rdi, r8
0x14001d26d  cmp     rdi, r12
0x14001d270  jb      short loc_14001D256
0x14001d272  jmp     short loc_14001D23C
0x14001d274  sub     rdi, r13
0x14001d277  sar     rdi, 1
0x14001d27a  jmp     short loc_14001D23F
0x14001d27c  mov     rdx, rbx
0x14001d27f  lea     rcx, [rbp+100h+FileName]
0x14001d286  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14001d28b  lea     r12, [rdi+1]
0x14001d28f  cmp     rdi, r14
0x14001d292  cmovz   r12, rdi
0x14001d296  mov     r8, r15; Src
0x14001d299  lea     rdx, [rbp+100h+Src]; lpPath
0x14001d29d  lea     rcx, [rbp+100h+FileName]; lpFileName
0x14001d2a4  call    ?SearchPathForExe@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@@Z; SearchPathForExe(std::wstring const &,std::wstring const &,std::wstring &)
0x14001d2a9  mov     r9d, eax
0x14001d2ac  xor     r13d, r13d
0x14001d2af  test    eax, eax
0x14001d2b1  jz      short loc_14001D2BD
0x14001d2b3  mov     [rsp+200h+var_1D0], 1
0x14001d2b8  jmp     loc_14001D187
0x14001d2bd  lea     rax, [rbp+100h+FileName]
0x14001d2c4  cmp     qword ptr [rbp+100h+var_60+8], 7
0x14001d2cc  cmova   rax, qword ptr [rbp+100h+FileName]
0x14001d2d4  mov     rcx, [rbp+108h]; this
0x14001d2db  mov     [rsp+200h+var_1D8], rax; char *
0x14001d2e0  lea     rdx, aWs; "%ws"
0x14001d2e7  mov     qword ptr [rsp+200h+var_1E0], rdx; unsigned int
0x14001d2ec  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001d2f3  mov     edx, 95h; void *
0x14001d2f8  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x14001d2fd  cmp     [rsp+200h+var_1D0], r13b
0x14001d302  lea     rsi, [r15+20h]
0x14001d306  jz      loc_14001D3F6
0x14001d30c  mov     rcx, [rsi+10h]
0x14001d310  cmp     rcx, [rsi+18h]
0x14001d314  jnb     short loc_14001D337
0x14001d316  lea     rax, [rcx+1]
0x14001d31a  mov     [rsi+10h], rax
0x14001d31e  cmp     qword ptr [rsi+18h], 7
0x14001d323  jbe     short loc_14001D32A
0x14001d325  mov     rdx, [rsi]
0x14001d328  jmp     short loc_14001D32D
0x14001d32a  mov     rdx, rsi
0x14001d32d  mov     edi, 22h ; '"'
0x14001d332  mov     [rdx+rcx*2], edi
0x14001d335  jmp     short loc_14001D347
0x14001d337  mov     edi, 22h ; '"'
0x14001d33c  mov     r9d, edi
0x14001d33f  mov     rcx, rsi; Src
0x14001d342  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001d347  lea     rdx, [rbp+100h+FileName]
0x14001d34e  mov     rcx, rsi; Src
0x14001d351  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14001d356  mov     rcx, [rsi+10h]
0x14001d35a  cmp     rcx, [rsi+18h]
0x14001d35e  jnb     short loc_14001D380
0x14001d360  lea     rax, [rcx+1]
0x14001d364  mov     [rsi+10h], rax
  ... truncated ...
```
