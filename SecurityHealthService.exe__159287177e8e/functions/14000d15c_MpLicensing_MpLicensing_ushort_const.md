# MpLicensing::MpLicensing(ushort const *)

- ea: `0x14000d15c`
- end: `0x14000d4ef`
- name: `??0MpLicensing@@QEAA@PEBG@Z`
- size: `915`
- prototype: `MpLicensing *__fastcall(MpLicensing *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x140007538`

## callees

- `0x1400015d0`
- `0x140001b9c`
- `0x140002050`
- `0x14000536c`
- `0x1400053f4`
- `0x14000cc78`
- `0x14000cf98`
- `0x14000d15c`
- `0x14000d5a8`
- `0x14000d630`
- `0x14000da08`
- `0x14000da90`
- `0x14000daa4`
- `0x14000dd0c`
- `0x14000ddc0`
- `0x14000df7c`
- `0x14000e348`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000d270`
- `KERNEL32!GetLastError` at `0x14000d42e`
- `KERNEL32!GetLastError` at `0x14000d270`
- `KERNEL32!GetLastError` at `0x14000d42e`
- `KERNEL32!LoadLibraryExW` at `0x14000d225`
- `KERNEL32!LoadLibraryExW` at `0x14000d36a`
- `KERNEL32!LoadLibraryExW` at `0x14000d225`
- `KERNEL32!LoadLibraryExW` at `0x14000d36a`

## pseudocode

```c
MpLicensing *__fastcall MpLicensing::MpLicensing(MpLicensing *this, const unsigned __int16 *a2)
{
  CWString *v4; // rax
  CWString *v5; // rax
  const WCHAR *v6; // rsi
  void (__fastcall ***v7)(_QWORD); // rcx
  const WCHAR *v8; // rbx
  const WCHAR *v9; // rcx
  HINSTANCE v10; // rax
  __int64 v11; // r12
  signed int LastError; // eax
  unsigned __int64 last_of; // rax
  unsigned __int64 v14; // rdi
  const WCHAR *v15; // rcx
  __int64 v16; // rcx
  const WCHAR *v17; // r8
  const WCHAR *v18; // rdi
  HINSTANCE v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  void (__fastcall ***v22)(_QWORD); // rcx
  char *v23; // rcx
  HINSTANCE v24; // rcx
  signed int v26; // eax
  unsigned int v27; // edi
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // r10
  __int64 v31; // [rsp+30h] [rbp-50h] BYREF
  void *v32; // [rsp+38h] [rbp-48h]
  _QWORD v33[2]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+50h] [rbp-30h] BYREF

  v33[1] = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v31 = 0;
  v32 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids);
    CError::CError((CError *)pExceptionObject, -2147024809);
    throw (CError *)pExceptionObject;
  }
  v4 = (CWString *)operator new(0x58u);
  v5 = CWString::CWString(v4, a2);
  v6 = (const WCHAR *)v5;
  v33[0] = v5;
  if ( v5 )
  {
    v7 = (void (__fastcall ***)(_QWORD))((char *)v5 + *(int *)(*(_QWORD *)v5 + 4LL));
    (**v7)(v7);
  }
  if ( v6 )
  {
    v8 = v6 + 8;
    std::wstring::append((void *)(v6 + 8));
    if ( *((_QWORD *)v6 + 5) <= 7u )
      v9 = v6 + 8;
    else
      v9 = *(const WCHAR **)v8;
    v10 = (HINSTANCE)_InterlockedExchange64(&v31, (__int64)LoadLibraryExW(v9, 0, 2u));
    _HMODULE_Finalizer(v10, v32);
    if ( !v31 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        if ( *((_QWORD *)v6 + 5) <= 7u )
          v11 = (__int64)(v6 + 8);
        else
          v11 = *(_QWORD *)v8;
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids,
          LastError,
          v11);
      }
      std::wstring::wstring(pExceptionObject, a2);
      CWString::assign(v6, pExceptionObject);
      std::wstring::~wstring(pExceptionObject);
      last_of = std::wstring::find_last_of(v6 + 8);
      if ( last_of != -1 )
      {
        v14 = *((_QWORD *)v6 + 4);
        if ( last_of > v14 )
        {
          v16 = last_of - v14;
          if ( last_of - v14 > *((_QWORD *)v6 + 5) - v14 )
          {
            std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>((void *)(v6 + 8));
          }
          else
          {
            *((_QWORD *)v6 + 4) = last_of;
            if ( *((_QWORD *)v6 + 5) <= 7u )
              v17 = v6 + 8;
            else
              v17 = *(const WCHAR **)v8;
            v18 = &v17[v14];
            if ( v16 )
            {
              while ( v16 )
              {
                *v18++ = 0;
                --v16;
              }
            }
            v17[last_of] = 0;
          }
        }
        else
        {
          *((_QWORD *)v6 + 4) = last_of;
          if ( *((_QWORD *)v6 + 5) <= 7u )
            v15 = v6 + 8;
          else
            v15 = *(const WCHAR **)v8;
          v15[last_of] = 0;
        }
        std::wstring::append((void *)(v6 + 8));
        if ( *((_QWORD *)v6 + 5) > 7u )
          v8 = *(const WCHAR **)v8;
        v19 = (HINSTANCE)_InterlockedExchange64(&v31, (__int64)LoadLibraryExW(v8, 0, 2u));
        _HMODULE_Finalizer(v19, v32);
        if ( !v31 )
        {
          v26 = GetLastError();
          v27 = v26;
          if ( v26 > 0 )
            v27 = (unsigned __int16)v26 | 0x80070000;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v28 = CSmartPtr<CWString,VolatileOps<CWString>>::operator->(v33);
            v29 = std::wstring::c_str(v28 + 16);
            WPP_SF_dS(
              *(_QWORD *)(v30 + 16),
              18,
              (unsigned int)&WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids,
              v27,
              v29);
          }
          CError::CError((CError *)pExceptionObject, v27);
          throw (CError *)pExceptionObject;
        }
      }
    }
    _HMODULE_Finalizer(
      (HINSTANCE)_InterlockedExchange64((volatile __int64 *)this + 1, _InterlockedExchange64(&v31, 0)),
      *((void **)this + 2));
    v20 = _InterlockedExchange64((volatile __int64 *)this, (__int64)v6);
    if ( v20 )
    {
      v21 = v20 + *(int *)(*(_QWORD *)v20 + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    }
    v22 = (void (__fastcall ***)(_QWORD))((char *)v6 + *(int *)(*(_QWORD *)v6 + 4LL));
    (**v22)(v22);
  }
  if ( v6 )
  {
    v23 = (char *)v6 + *(int *)(*(_QWORD *)v6 + 4LL);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))(v23);
  }
  v24 = (HINSTANCE)_InterlockedExchange64(&v31, 0);
  _HMODULE_Finalizer(v24, v32);
  return this;
}

```

## disassembly

```asm
0x14000d15c  mov     [rsp-28h+arg_10], rbx
0x14000d161  mov     [rsp-28h+arg_18], rsi
0x14000d166  push    rbp
0x14000d167  push    rdi
0x14000d168  push    r12
0x14000d16a  push    r14
0x14000d16c  push    r15
0x14000d16e  mov     rbp, rsp
0x14000d171  sub     rsp, 80h
0x14000d178  mov     rax, cs:__security_cookie
0x14000d17f  xor     rax, rsp
0x14000d182  mov     [rbp+var_10], rax
0x14000d186  mov     rdi, rdx
0x14000d189  mov     r14, rcx
0x14000d18c  mov     [rbp+var_38], rcx
0x14000d190  mov     qword ptr [rcx], 0
0x14000d197  mov     qword ptr [rcx+8], 0
0x14000d19f  mov     qword ptr [rcx+10h], 0
0x14000d1a7  mov     [rbp+var_50], 0
0x14000d1af  mov     [rbp+var_48], 0
0x14000d1b7  test    rdx, rdx
0x14000d1ba  jz      loc_14000D4A2
0x14000d1c0  mov     ecx, 58h ; 'X'; Size
0x14000d1c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d1ca  mov     [rbp+var_40], rax
0x14000d1ce  mov     rdx, rdi; unsigned __int16 *
0x14000d1d1  mov     rcx, rax; this
0x14000d1d4  call    ??0CWString@@QEAA@PEBG@Z; CWString::CWString(ushort const *)
0x14000d1d9  mov     rsi, rax
0x14000d1dc  mov     [rbp+var_40], rax
0x14000d1e0  test    rax, rax
0x14000d1e3  jz      short loc_14000D1FB
0x14000d1e5  mov     rax, [rax]
0x14000d1e8  movsxd  rcx, dword ptr [rax+4]
0x14000d1ec  add     rcx, rsi
0x14000d1ef  mov     rax, [rcx]
0x14000d1f2  mov     rax, [rax]
0x14000d1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d1fa  nop
0x14000d1fb  test    rsi, rsi
0x14000d1fe  jz      loc_14000D3D7
0x14000d204  lea     rbx, [rsi+10h]
0x14000d208  mov     rcx, rbx; Src
0x14000d20b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14000d210  cmp     qword ptr [rbx+18h], 7
0x14000d215  jbe     short loc_14000D21C
0x14000d217  mov     rcx, [rbx]
0x14000d21a  jmp     short loc_14000D21F
0x14000d21c  mov     rcx, rbx; lpLibFileName
0x14000d21f  xor     edx, edx; hFile
0x14000d221  lea     r8d, [rdx+2]; dwFlags
0x14000d225  call    cs:__imp_LoadLibraryExW
0x14000d22b  xchg    rax, [rbp+var_50]
0x14000d22f  mov     rdx, [rbp+var_48]; void *
0x14000d233  mov     rcx, rax; HINSTANCE
0x14000d236  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x14000d23b  mov     rax, [rbp+var_50]
0x14000d23f  test    rax, rax
0x14000d242  jnz     loc_14000D38D
0x14000d248  lea     r15, WPP_GLOBAL_Control
0x14000d24f  mov     rax, cs:WPP_GLOBAL_Control
0x14000d256  cmp     rax, r15
0x14000d259  jz      short loc_14000D2A6
0x14000d25b  test    byte ptr [rax+1Ch], 10h
0x14000d25f  jz      short loc_14000D2A6
0x14000d261  cmp     qword ptr [rbx+18h], 7
0x14000d266  jbe     short loc_14000D26D
0x14000d268  mov     r12, [rbx]
0x14000d26b  jmp     short loc_14000D270
0x14000d26d  mov     r12, rbx
0x14000d270  call    cs:__imp_GetLastError
0x14000d276  test    eax, eax
0x14000d278  jle     short loc_14000D282
0x14000d27a  movzx   eax, ax
0x14000d27d  or      eax, 80070000h
0x14000d282  mov     edx, 11h
0x14000d287  mov     [rsp+80h+var_60], r12
0x14000d28c  mov     r9d, eax
0x14000d28f  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x14000d296  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d29d  mov     rcx, [rcx+10h]
0x14000d2a1  call    WPP_SF_dS
0x14000d2a6  mov     rdx, rdi
0x14000d2a9  lea     rcx, [rbp+pExceptionObject]
0x14000d2ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000d2b2  nop
0x14000d2b3  lea     rdx, [rbp+pExceptionObject]
0x14000d2b7  mov     rcx, rsi
0x14000d2ba  call    ?assign@CWString@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; CWString::assign(std::wstring const &)
0x14000d2bf  nop
0x14000d2c0  lea     rcx, [rbp+pExceptionObject]
0x14000d2c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d2c9  mov     rcx, rbx
0x14000d2cc  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x14000d2d1  mov     rdx, rax
0x14000d2d4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d2d8  jz      loc_14000D38D
0x14000d2de  mov     rdi, [rbx+10h]
0x14000d2e2  cmp     rax, rdi
0x14000d2e5  ja      short loc_14000D302
0x14000d2e7  mov     [rbx+10h], rax
0x14000d2eb  cmp     qword ptr [rbx+18h], 7
0x14000d2f0  jbe     short loc_14000D2F7
0x14000d2f2  mov     rcx, [rbx]
0x14000d2f5  jmp     short loc_14000D2FA
0x14000d2f7  mov     rcx, rbx
0x14000d2fa  xor     eax, eax
0x14000d2fc  mov     [rcx+rdx*2], ax
0x14000d300  jmp     short loc_14000D34F
0x14000d302  mov     rcx, rdx
0x14000d305  sub     rcx, rdi
0x14000d308  mov     rax, [rbx+18h]
0x14000d30c  sub     rax, rdi
0x14000d30f  cmp     rcx, rax
0x14000d312  ja      short loc_14000D341
0x14000d314  mov     [rbx+10h], rdx
0x14000d318  cmp     qword ptr [rbx+18h], 7
0x14000d31d  jbe     short loc_14000D324
0x14000d31f  mov     r8, [rbx]
0x14000d322  jmp     short loc_14000D327
0x14000d324  mov     r8, rbx
0x14000d327  lea     rdi, [r8+rdi*2]
0x14000d32b  test    rcx, rcx
0x14000d32e  jz      short loc_14000D338
0x14000d330  xor     eax, eax
0x14000d332  movzx   eax, ax
0x14000d335  rep stosw
0x14000d338  xor     eax, eax
0x14000d33a  mov     [r8+rdx*2], ax
0x14000d33f  jmp     short loc_14000D34F
0x14000d341  mov     r9, rcx
0x14000d344  mov     rdx, rcx
0x14000d347  mov     rcx, rbx; Src
0x14000d34a  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x14000d34f  mov     rcx, rbx; Src
0x14000d352  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14000d357  cmp     qword ptr [rbx+18h], 7
0x14000d35c  jbe     short loc_14000D361
0x14000d35e  mov     rbx, [rbx]
0x14000d361  xor     edx, edx; hFile
0x14000d363  lea     r8d, [rdx+2]; dwFlags
0x14000d367  mov     rcx, rbx; lpLibFileName
0x14000d36a  call    cs:__imp_LoadLibraryExW
0x14000d370  xchg    rax, [rbp+var_50]
0x14000d374  mov     rdx, [rbp+var_48]; void *
0x14000d378  mov     rcx, rax; HINSTANCE
0x14000d37b  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x14000d380  mov     rax, [rbp+var_50]
0x14000d384  test    rax, rax
0x14000d387  jz      loc_14000D42E
0x14000d38d  xor     ecx, ecx
0x14000d38f  xchg    rcx, [rbp+var_50]
0x14000d393  xchg    rcx, [r14+8]; HINSTANCE
0x14000d397  mov     rdx, [r14+10h]; void *
0x14000d39b  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x14000d3a0  mov     rdx, rsi
0x14000d3a3  xchg    rdx, [r14]
0x14000d3a6  test    rdx, rdx
0x14000d3a9  jz      short loc_14000D3C1
0x14000d3ab  mov     rax, [rdx]
0x14000d3ae  movsxd  rcx, dword ptr [rax+4]
0x14000d3b2  add     rcx, rdx
0x14000d3b5  mov     rax, [rcx]
0x14000d3b8  mov     rax, [rax+8]
0x14000d3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3c1  mov     rax, [rsi]
0x14000d3c4  movsxd  rcx, dword ptr [rax+4]
0x14000d3c8  add     rcx, rsi
0x14000d3cb  mov     rax, [rcx]
0x14000d3ce  mov     rax, [rax]
0x14000d3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3d6  nop
0x14000d3d7  test    rsi, rsi
0x14000d3da  jz      short loc_14000D3F3
0x14000d3dc  mov     rax, [rsi]
0x14000d3df  movsxd  rcx, dword ptr [rax+4]
0x14000d3e3  add     rcx, rsi
0x14000d3e6  mov     rax, [rcx]
0x14000d3e9  mov     rax, [rax+8]
0x14000d3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3f2  nop
0x14000d3f3  xor     ecx, ecx
0x14000d3f5  xchg    rcx, [rbp+var_50]; HINSTANCE
0x14000d3f9  mov     rdx, [rbp+var_48]; void *
0x14000d3fd  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x14000d402  nop
0x14000d403  mov     rax, r14
0x14000d406  mov     rcx, [rbp+var_10]
0x14000d40a  xor     rcx, rsp; StackCookie
0x14000d40d  call    __security_check_cookie
0x14000d412  lea     r11, [rsp+80h+var_s0]
0x14000d41a  mov     rbx, [r11+40h]
0x14000d41e  mov     rsi, [r11+48h]
0x14000d422  mov     rsp, r11
0x14000d425  pop     r15
0x14000d427  pop     r14
0x14000d429  pop     r12
0x14000d42b  pop     rdi
0x14000d42c  pop     rbp
0x14000d42d  retn
0x14000d42e  call    cs:__imp_GetLastError
0x14000d434  nop
0x14000d435  mov     edi, eax
0x14000d437  test    eax, eax
0x14000d439  jle     short loc_14000D444
0x14000d43b  movzx   edi, ax
0x14000d43e  or      edi, 80070000h
0x14000d444  mov     r10, cs:WPP_GLOBAL_Control
0x14000d44b  cmp     r10, r15
0x14000d44e  jz      short loc_14000D486
0x14000d450  test    byte ptr [r10+1Ch], 2
0x14000d455  jz      short loc_14000D486
0x14000d457  lea     rcx, [rbp+var_40]
0x14000d45b  call    ??C?$CSmartPtr@VCWString@@V?$VolatileOps@VCWString@@@@@@QEAAPEAVCWString@@XZ; CSmartPtr<CWString,VolatileOps<CWString>>::operator->(void)
0x14000d460  lea     rcx, [rax+10h]
0x14000d464  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14000d469  mov     edx, 12h
0x14000d46e  mov     [rsp+80h+var_60], rax
0x14000d473  mov     r9d, edi
0x14000d476  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x14000d47d  mov     rcx, [r10+10h]
0x14000d481  call    WPP_SF_dS
0x14000d486  mov     edx, edi; int
0x14000d488  lea     rcx, [rbp+pExceptionObject]; this
0x14000d48c  call    ??0CError@@QEAA@J@Z; CError::CError(long)
0x14000d491  lea     rdx, _TI3?AVCError@@; pThrowInfo
0x14000d498  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000d49c  call    _CxxThrowException_0
0x14000d4a2  lea     r15, WPP_GLOBAL_Control
0x14000d4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d4b0  cmp     rcx, r15
0x14000d4b3  jz      short loc_14000D4D0
0x14000d4b5  test    byte ptr [rcx+1Ch], 1
0x14000d4b9  jz      short loc_14000D4D0
0x14000d4bb  mov     edx, 13h
0x14000d4c0  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x14000d4c7  mov     rcx, [rcx+10h]
0x14000d4cb  call    WPP_SF_
0x14000d4d0  mov     edx, 80070057h; int
0x14000d4d5  lea     rcx, [rbp+pExceptionObject]; this
0x14000d4d9  call    ??0CError@@QEAA@J@Z; CError::CError(long)
0x14000d4de  lea     rdx, _TI3?AVCError@@; pThrowInfo
0x14000d4e5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000d4e9  call    _CxxThrowException_0
```
