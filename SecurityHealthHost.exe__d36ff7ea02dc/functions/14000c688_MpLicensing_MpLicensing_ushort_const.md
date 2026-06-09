# MpLicensing::MpLicensing(ushort const *)

- ea: `0x14000c688`
- end: `0x14000ca1b`
- name: `??0MpLicensing@@QEAA@PEBG@Z`
- size: `915`
- prototype: `MpLicensing *__fastcall(MpLicensing *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x140005fdc`

## callees

- `0x1400015f0`
- `0x14000164c`
- `0x1400022f8`
- `0x140002550`
- `0x14000277c`
- `0x140002ec0`
- `0x140003018`
- `0x140003080`
- `0x14000c360`
- `0x14000c688`
- `0x14000ca24`
- `0x14000cdbc`
- `0x14000ce44`
- `0x14000d000`
- `0x14000d0b4`
- `0x14000d224`
- `0x14000d5e8`
- `0x140011010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000c751`
- `KERNEL32!LoadLibraryExW` at `0x14000c896`
- `KERNEL32!LoadLibraryExW` at `0x14000c751`
- `KERNEL32!LoadLibraryExW` at `0x14000c896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c95a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c95a`

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
0x14000c688  mov     [rsp-28h+arg_10], rbx
0x14000c68d  mov     [rsp-28h+arg_18], rsi
0x14000c692  push    rbp
0x14000c693  push    rdi
0x14000c694  push    r12
0x14000c696  push    r14
0x14000c698  push    r15
0x14000c69a  mov     rbp, rsp
0x14000c69d  sub     rsp, 80h
0x14000c6a4  mov     rax, cs:__security_cookie
0x14000c6ab  xor     rax, rsp
0x14000c6ae  mov     [rbp+var_10], rax
0x14000c6b2  mov     rdi, rdx
0x14000c6b5  mov     r14, rcx
0x14000c6b8  mov     [rbp+var_38], rcx
0x14000c6bc  mov     qword ptr [rcx], 0
0x14000c6c3  mov     qword ptr [rcx+8], 0
0x14000c6cb  mov     qword ptr [rcx+10h], 0
0x14000c6d3  mov     [rbp+var_50], 0
0x14000c6db  mov     [rbp+var_48], 0
0x14000c6e3  test    rdx, rdx
0x14000c6e6  jz      loc_14000C9CE
0x14000c6ec  mov     ecx, 58h ; 'X'; Size
0x14000c6f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000c6f6  mov     [rbp+var_40], rax
0x14000c6fa  mov     rdx, rdi; unsigned __int16 *
0x14000c6fd  mov     rcx, rax; this
0x14000c700  call    ??0CWString@@QEAA@PEBG@Z; CWString::CWString(ushort const *)
0x14000c705  mov     rsi, rax
0x14000c708  mov     [rbp+var_40], rax
0x14000c70c  test    rax, rax
0x14000c70f  jz      short loc_14000C727
0x14000c711  mov     rax, [rax]
0x14000c714  movsxd  rcx, dword ptr [rax+4]
0x14000c718  add     rcx, rsi
0x14000c71b  mov     rax, [rcx]
0x14000c71e  mov     rax, [rax]
0x14000c721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c726  nop
0x14000c727  test    rsi, rsi
0x14000c72a  jz      loc_14000C903
0x14000c730  lea     rbx, [rsi+10h]
0x14000c734  mov     rcx, rbx; Src
0x14000c737  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14000c73c  cmp     qword ptr [rbx+18h], 7
0x14000c741  jbe     short loc_14000C748
0x14000c743  mov     rcx, [rbx]
0x14000c746  jmp     short loc_14000C74B
0x14000c748  mov     rcx, rbx; lpLibFileName
0x14000c74b  xor     edx, edx; hFile
0x14000c74d  lea     r8d, [rdx+2]; dwFlags
0x14000c751  call    cs:__imp_LoadLibraryExW
0x14000c757  xchg    rax, [rbp+var_50]
0x14000c75b  mov     rdx, [rbp+var_48]; void *
0x14000c75f  mov     rcx, rax; HINSTANCE
0x14000c762  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x14000c767  mov     rax, [rbp+var_50]
0x14000c76b  test    rax, rax
0x14000c76e  jnz     loc_14000C8B9
0x14000c774  lea     r15, WPP_GLOBAL_Control
0x14000c77b  mov     rax, cs:WPP_GLOBAL_Control
0x14000c782  cmp     rax, r15
0x14000c785  jz      short loc_14000C7D2
0x14000c787  test    byte ptr [rax+1Ch], 10h
0x14000c78b  jz      short loc_14000C7D2
0x14000c78d  cmp     qword ptr [rbx+18h], 7
0x14000c792  jbe     short loc_14000C799
0x14000c794  mov     r12, [rbx]
0x14000c797  jmp     short loc_14000C79C
0x14000c799  mov     r12, rbx
0x14000c79c  call    cs:__imp_GetLastError
0x14000c7a2  test    eax, eax
0x14000c7a4  jle     short loc_14000C7AE
0x14000c7a6  movzx   eax, ax
0x14000c7a9  or      eax, 80070000h
0x14000c7ae  mov     edx, 11h
0x14000c7b3  mov     [rsp+80h+var_60], r12
0x14000c7b8  mov     r9d, eax
0x14000c7bb  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x14000c7c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c7c9  mov     rcx, [rcx+10h]
0x14000c7cd  call    WPP_SF_dS
0x14000c7d2  mov     rdx, rdi
0x14000c7d5  lea     rcx, [rbp+pExceptionObject]
0x14000c7d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000c7de  nop
0x14000c7df  lea     rdx, [rbp+pExceptionObject]
0x14000c7e3  mov     rcx, rsi
0x14000c7e6  call    ?assign@CWString@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; CWString::assign(std::wstring const &)
0x14000c7eb  nop
0x14000c7ec  lea     rcx, [rbp+pExceptionObject]
0x14000c7f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c7f5  mov     rcx, rbx
0x14000c7f8  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x14000c7fd  mov     rdx, rax
0x14000c800  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c804  jz      loc_14000C8B9
0x14000c80a  mov     rdi, [rbx+10h]
0x14000c80e  cmp     rax, rdi
0x14000c811  ja      short loc_14000C82E
0x14000c813  mov     [rbx+10h], rax
0x14000c817  cmp     qword ptr [rbx+18h], 7
0x14000c81c  jbe     short loc_14000C823
0x14000c81e  mov     rcx, [rbx]
0x14000c821  jmp     short loc_14000C826
0x14000c823  mov     rcx, rbx
0x14000c826  xor     eax, eax
0x14000c828  mov     [rcx+rdx*2], ax
0x14000c82c  jmp     short loc_14000C87B
0x14000c82e  mov     rcx, rdx
0x14000c831  sub     rcx, rdi
0x14000c834  mov     rax, [rbx+18h]
0x14000c838  sub     rax, rdi
0x14000c83b  cmp     rcx, rax
0x14000c83e  ja      short loc_14000C86D
0x14000c840  mov     [rbx+10h], rdx
0x14000c844  cmp     qword ptr [rbx+18h], 7
0x14000c849  jbe     short loc_14000C850
0x14000c84b  mov     r8, [rbx]
0x14000c84e  jmp     short loc_14000C853
0x14000c850  mov     r8, rbx
0x14000c853  lea     rdi, [r8+rdi*2]
0x14000c857  test    rcx, rcx
0x14000c85a  jz      short loc_14000C864
0x14000c85c  xor     eax, eax
0x14000c85e  movzx   eax, ax
0x14000c861  rep stosw
0x14000c864  xor     eax, eax
0x14000c866  mov     [r8+rdx*2], ax
0x14000c86b  jmp     short loc_14000C87B
0x14000c86d  mov     r9, rcx
0x14000c870  mov     rdx, rcx
0x14000c873  mov     rcx, rbx; Src
0x14000c876  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x14000c87b  mov     rcx, rbx; Src
0x14000c87e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14000c883  cmp     qword ptr [rbx+18h], 7
0x14000c888  jbe     short loc_14000C88D
0x14000c88a  mov     rbx, [rbx]
0x14000c88d  xor     edx, edx; hFile
0x14000c88f  lea     r8d, [rdx+2]; dwFlags
0x14000c893  mov     rcx, rbx; lpLibFileName
0x14000c896  call    cs:__imp_LoadLibraryExW
0x14000c89c  xchg    rax, [rbp+var_50]
0x14000c8a0  mov     rdx, [rbp+var_48]; void *
0x14000c8a4  mov     rcx, rax; HINSTANCE
0x14000c8a7  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x14000c8ac  mov     rax, [rbp+var_50]
0x14000c8b0  test    rax, rax
0x14000c8b3  jz      loc_14000C95A
0x14000c8b9  xor     ecx, ecx
0x14000c8bb  xchg    rcx, [rbp+var_50]
0x14000c8bf  xchg    rcx, [r14+8]; HINSTANCE
0x14000c8c3  mov     rdx, [r14+10h]; void *
0x14000c8c7  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x14000c8cc  mov     rdx, rsi
0x14000c8cf  xchg    rdx, [r14]
0x14000c8d2  test    rdx, rdx
0x14000c8d5  jz      short loc_14000C8ED
0x14000c8d7  mov     rax, [rdx]
0x14000c8da  movsxd  rcx, dword ptr [rax+4]
0x14000c8de  add     rcx, rdx
0x14000c8e1  mov     rax, [rcx]
0x14000c8e4  mov     rax, [rax+8]
0x14000c8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8ed  mov     rax, [rsi]
0x14000c8f0  movsxd  rcx, dword ptr [rax+4]
0x14000c8f4  add     rcx, rsi
0x14000c8f7  mov     rax, [rcx]
0x14000c8fa  mov     rax, [rax]
0x14000c8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c902  nop
0x14000c903  test    rsi, rsi
0x14000c906  jz      short loc_14000C91F
0x14000c908  mov     rax, [rsi]
0x14000c90b  movsxd  rcx, dword ptr [rax+4]
0x14000c90f  add     rcx, rsi
0x14000c912  mov     rax, [rcx]
0x14000c915  mov     rax, [rax+8]
0x14000c919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c91e  nop
0x14000c91f  xor     ecx, ecx
0x14000c921  xchg    rcx, [rbp+var_50]; HINSTANCE
0x14000c925  mov     rdx, [rbp+var_48]; void *
0x14000c929  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x14000c92e  nop
0x14000c92f  mov     rax, r14
0x14000c932  mov     rcx, [rbp+var_10]
0x14000c936  xor     rcx, rsp; StackCookie
0x14000c939  call    __security_check_cookie
0x14000c93e  lea     r11, [rsp+80h+var_s0]
0x14000c946  mov     rbx, [r11+40h]
0x14000c94a  mov     rsi, [r11+48h]
0x14000c94e  mov     rsp, r11
0x14000c951  pop     r15
0x14000c953  pop     r14
0x14000c955  pop     r12
0x14000c957  pop     rdi
0x14000c958  pop     rbp
0x14000c959  retn
0x14000c95a  call    cs:__imp_GetLastError
0x14000c960  nop
0x14000c961  mov     edi, eax
0x14000c963  test    eax, eax
0x14000c965  jle     short loc_14000C970
0x14000c967  movzx   edi, ax
0x14000c96a  or      edi, 80070000h
0x14000c970  mov     r10, cs:WPP_GLOBAL_Control
0x14000c977  cmp     r10, r15
0x14000c97a  jz      short loc_14000C9B2
0x14000c97c  test    byte ptr [r10+1Ch], 2
0x14000c981  jz      short loc_14000C9B2
0x14000c983  lea     rcx, [rbp+var_40]
0x14000c987  call    ??C?$CSmartPtr@VCWString@@V?$VolatileOps@VCWString@@@@@@QEAAPEAVCWString@@XZ; CSmartPtr<CWString,VolatileOps<CWString>>::operator->(void)
0x14000c98c  lea     rcx, [rax+10h]
0x14000c990  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14000c995  mov     edx, 12h
0x14000c99a  mov     [rsp+80h+var_60], rax
0x14000c99f  mov     r9d, edi
0x14000c9a2  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x14000c9a9  mov     rcx, [r10+10h]
0x14000c9ad  call    WPP_SF_dS
0x14000c9b2  mov     edx, edi; int
0x14000c9b4  lea     rcx, [rbp+pExceptionObject]; this
0x14000c9b8  call    ??0CError@@QEAA@J@Z; CError::CError(long)
0x14000c9bd  lea     rdx, _TI3?AVCError@@; pThrowInfo
0x14000c9c4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000c9c8  call    _CxxThrowException_0
0x14000c9ce  lea     r15, WPP_GLOBAL_Control
0x14000c9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c9dc  cmp     rcx, r15
0x14000c9df  jz      short loc_14000C9FC
0x14000c9e1  test    byte ptr [rcx+1Ch], 1
0x14000c9e5  jz      short loc_14000C9FC
0x14000c9e7  mov     edx, 13h
0x14000c9ec  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x14000c9f3  mov     rcx, [rcx+10h]
0x14000c9f7  call    WPP_SF_
0x14000c9fc  mov     edx, 80070057h; int
0x14000ca01  lea     rcx, [rbp+pExceptionObject]; this
0x14000ca05  call    ??0CError@@QEAA@J@Z; CError::CError(long)
0x14000ca0a  lea     rdx, _TI3?AVCError@@; pThrowInfo
0x14000ca11  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000ca15  call    _CxxThrowException_0
```
