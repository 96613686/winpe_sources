# MpLicensing::MpLicensing(ushort const *)

- ea: `0x1800d9184`
- end: `0x1800d94a4`
- name: `??0MpLicensing@@QEAA@PEBG@Z`
- size: `800`
- prototype: `MpLicensing *__fastcall(MpLicensing *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting`

## callers

- `0x1800cd524`

## callees

- `0x180004710`
- `0x180004b64`
- `0x180005188`
- `0x180010ff0`
- `0x180011018`
- `0x18001b458`
- `0x18001ca28`
- `0x18001ca48`
- `0x18001caa0`
- `0x180033f9c`
- `0x180066fb8`
- `0x1800ced08`
- `0x1800d8f50`
- `0x1800d901c`
- `0x1800d9184`
- `0x1800d94ac`
- `0x1800d94d8`
- `0x1800d98e0`
- `0x1800d9a78`
- `0x1800d9ae0`
- `0x1800d9bb0`
- `0x1800d9f44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800d926d`
- `KERNEL32!GetLastError` at `0x1800d938e`
- `KERNEL32!GetLastError` at `0x1800d926d`
- `KERNEL32!GetLastError` at `0x1800d938e`
- `KERNEL32!LoadLibraryExW` at `0x1800d922a`
- `KERNEL32!LoadLibraryExW` at `0x1800d9373`
- `KERNEL32!LoadLibraryExW` at `0x1800d922a`
- `KERNEL32!LoadLibraryExW` at `0x1800d9373`

## string_xrefs

- `0x1800d920a`: `\MsMpLics.dll`
- `0x1800d9353`: `\MsMpLics.dll`

## pseudocode

```c
MpLicensing *__fastcall MpLicensing::MpLicensing(MpLicensing *this, const unsigned __int16 *a2)
{
  CWString *v4; // rax
  CWString *v5; // rsi
  const WCHAR *v6; // rax
  HMODULE Library; // rax
  __int64 v8; // r13
  signed int LastError; // eax
  __int64 v10; // rax
  __int64 v11; // rdx
  size_t N; // rax
  int v13; // r8d
  int v14; // r9d
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r8
  char *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r11
  __int64 v20; // rax
  __int64 v21; // r8
  size_t v22; // rdx
  __int64 v23; // r10
  __int64 v24; // r11
  const WCHAR *v25; // rax
  HMODULE v26; // rax
  signed int v27; // eax
  unsigned int v28; // edi
  __int64 v29; // rax
  __int64 v30; // r10
  HINSTANCE v31; // rcx
  __int64 v33; // [rsp+30h] [rbp-50h] BYREF
  void *v34; // [rsp+38h] [rbp-48h]
  CWString *v35; // [rsp+40h] [rbp-40h]
  MpLicensing *v36; // [rsp+48h] [rbp-38h]
  _BYTE pExceptionObject[32]; // [rsp+50h] [rbp-30h] BYREF

  v36 = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v33 = 0;
  v34 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids);
    CError::CError((CError *)pExceptionObject, -2147024809);
    throw (CError *)pExceptionObject;
  }
  v4 = (CWString *)operator new(0x58u);
  v5 = CWString::CWString(v4, a2);
  v35 = v5;
  CSmartPtr<CWString,VolatileOps<CWString>>::_AddRef(v5);
  if ( v5 )
  {
    std::wstring::append((char *)v5 + 16, L"\\MsMpLics.dll");
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v5 + 16);
    Library = LoadLibraryExW(v6, 0, 2u);
    CAutoHandle<HINSTANCE__ *,&void _HMODULE_Finalizer(HINSTANCE__ *,void *)>::operator=(&v33, Library);
    if ( !v33 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v5 + 16);
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids,
          LastError,
          v8);
      }
      std::wstring::wstring(pExceptionObject, a2);
      CWString::assign(v5, pExceptionObject);
      std::wstring::_Tidy_deallocate(pExceptionObject);
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v5 + 16);
      N = std::_WChar_traits<unsigned short>::length(L"/\\", v11, v10);
      v15 = std::_Traits_find_last_of<std::char_traits<unsigned short>>(v13, *((_QWORD *)v5 + 4), v13, v14, N);
      if ( v15 != -1 )
      {
        v16 = *((_QWORD *)v5 + 4);
        v17 = (char *)v5 + 16;
        if ( v15 > v16 )
        {
          if ( v15 - v16 > *((_QWORD *)v5 + 5) - v16 )
          {
            std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
              v17,
              v15 - v16,
              v16,
              v15 - v16);
          }
          else
          {
            *((_QWORD *)v5 + 4) = v15;
            v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
            wmemset((wchar_t *)(v20 + 2 * v21), v22, v22);
            *(_WORD *)(v23 + 2 * v24) = 0;
          }
        }
        else
        {
          *((_QWORD *)v5 + 4) = v15;
          v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
          *(_WORD *)(v18 + 2 * v19) = 0;
        }
        std::wstring::append((char *)v5 + 16, L"\\MsMpLics.dll");
        v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v5 + 16);
        v26 = LoadLibraryExW(v25, 0, 2u);
        CAutoHandle<HINSTANCE__ *,&void _HMODULE_Finalizer(HINSTANCE__ *,void *)>::operator=(&v33, v26);
        if ( !v33 )
        {
          v27 = GetLastError();
          v28 = v27;
          if ( v27 > 0 )
            v28 = (unsigned __int16)v27 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v5 + 16);
            WPP_SF_dS(
              *(_QWORD *)(v30 + 16),
              18,
              (unsigned int)&WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids,
              v28,
              v29);
          }
          CError::CError((CError *)pExceptionObject, v28);
          throw (CError *)pExceptionObject;
        }
      }
    }
    CAutoHandle<HINSTANCE__ *,&void _HMODULE_Finalizer(HINSTANCE__ *,void *)>::operator=(
      (char *)this + 8,
      _InterlockedExchange64(&v33, 0));
    CSmartPtr<CWString,VolatileOps<CWString>>::operator=(this, v5);
  }
  CSmartPtr<CWString,VolatileOps<CWString>>::_Release(v5);
  v31 = (HINSTANCE)_InterlockedExchange64(&v33, 0);
  _HMODULE_Finalizer(v31, v34);
  return this;
}

```

## disassembly

```asm
0x1800d9184  mov     [rsp-38h+arg_10], rbx
0x1800d9189  push    rbp
0x1800d918a  push    rsi
0x1800d918b  push    rdi
0x1800d918c  push    r12
0x1800d918e  push    r13
0x1800d9190  push    r14
0x1800d9192  push    r15
0x1800d9194  mov     rbp, rsp
0x1800d9197  sub     rsp, 80h
0x1800d919e  mov     rax, cs:__security_cookie
0x1800d91a5  xor     rax, rsp
0x1800d91a8  mov     [rbp+var_10], rax
0x1800d91ac  mov     r12, rdx
0x1800d91af  mov     rdi, rcx
0x1800d91b2  mov     [rbp+var_38], rcx
0x1800d91b6  xor     r13d, r13d
0x1800d91b9  mov     [rcx], r13
0x1800d91bc  mov     [rcx+8], r13
0x1800d91c0  mov     [rcx+10h], r13
0x1800d91c4  mov     [rbp+var_50], r13
0x1800d91c8  mov     [rbp+var_48], r13
0x1800d91cc  test    rdx, rdx
0x1800d91cf  jz      loc_1800D9457
0x1800d91d5  lea     ecx, [r13+58h]; Size
0x1800d91d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d91de  mov     [rbp+var_40], rax
0x1800d91e2  mov     rdx, r12; unsigned __int16 *
0x1800d91e5  mov     rcx, rax; this
0x1800d91e8  call    ??0CWString@@QEAA@PEBG@Z; CWString::CWString(ushort const *)
0x1800d91ed  mov     rsi, rax
0x1800d91f0  mov     [rbp+var_40], rax
0x1800d91f4  mov     rcx, rax
0x1800d91f7  call    ?_AddRef@?$CSmartPtr@VCWString@@V?$VolatileOps@VCWString@@@@@@KAXPEBVCWString@@@Z; CSmartPtr<CWString,VolatileOps<CWString>>::_AddRef(CWString const *)
0x1800d91fc  nop
0x1800d91fd  test    rsi, rsi
0x1800d9200  jz      loc_1800D9413
0x1800d9206  lea     rbx, [rsi+10h]
0x1800d920a  lea     rdx, aMsmplicsDll_0; "\\MsMpLics.dll"
0x1800d9211  mov     rcx, rbx
0x1800d9214  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800d9219  mov     rcx, rbx
0x1800d921c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d9221  xor     edx, edx; hFile
0x1800d9223  lea     r8d, [r13+2]; dwFlags
0x1800d9227  mov     rcx, rax; lpLibFileName
0x1800d922a  call    cs:__imp_LoadLibraryExW
0x1800d9230  mov     rdx, rax
0x1800d9233  lea     rcx, [rbp+var_50]
0x1800d9237  call    ??4?$CAutoHandle@PEAUHINSTANCE__@@$1?_HMODULE_Finalizer@@YAXPEAU1@PEAX@Z@@QEAAAEAV0@PEAUHINSTANCE__@@@Z; CAutoHandle<HINSTANCE__ *,&_HMODULE_Finalizer(HINSTANCE__ *,void *)>::operator=(HINSTANCE__ *)
0x1800d923c  mov     rax, [rbp+var_50]
0x1800d9240  test    rax, rax
0x1800d9243  jnz     loc_1800D93F7
0x1800d9249  lea     r14, WPP_GLOBAL_Control
0x1800d9250  mov     rax, cs:WPP_GLOBAL_Control
0x1800d9257  cmp     rax, r14
0x1800d925a  jz      short loc_1800D92A6
0x1800d925c  test    byte ptr [rax+1Ch], 10h
0x1800d9260  jz      short loc_1800D92A6
0x1800d9262  mov     rcx, rbx
0x1800d9265  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d926a  mov     r13, rax
0x1800d926d  call    cs:__imp_GetLastError
0x1800d9273  test    eax, eax
0x1800d9275  jle     short loc_1800D927F
0x1800d9277  movzx   eax, ax
0x1800d927a  or      eax, 80070000h
0x1800d927f  mov     edx, 11h
0x1800d9284  mov     [rsp+80h+N], r13
0x1800d9289  mov     r9d, eax
0x1800d928c  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x1800d9293  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d929a  mov     rcx, [rcx+10h]
0x1800d929e  call    WPP_SF_dS
0x1800d92a3  xor     r13d, r13d
0x1800d92a6  mov     rdx, r12
0x1800d92a9  lea     rcx, [rbp+pExceptionObject]
0x1800d92ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d92b2  nop
0x1800d92b3  lea     rdx, [rbp+pExceptionObject]
0x1800d92b7  mov     rcx, rsi
0x1800d92ba  call    ?assign@CWString@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; CWString::assign(std::wstring const &)
0x1800d92bf  nop
0x1800d92c0  lea     rcx, [rbp+pExceptionObject]
0x1800d92c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d92c9  mov     rcx, rbx
0x1800d92cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d92d1  mov     r8, rax
0x1800d92d4  lea     rcx, asc_1801083FC; "/\\"
0x1800d92db  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800d92e0  mov     [rsp+80h+N], rax; N
0x1800d92e5  mov     rdx, [rbx+10h]; int
0x1800d92e9  mov     rcx, r8; int
0x1800d92ec  call    ??$_Traits_find_last_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x1800d92f1  mov     r11, rax
0x1800d92f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d92f8  jz      loc_1800D93F7
0x1800d92fe  mov     r8, [rbx+10h]
0x1800d9302  mov     rcx, rbx
0x1800d9305  cmp     rax, r8
0x1800d9308  ja      short loc_1800D931A
0x1800d930a  mov     [rbx+10h], rax
0x1800d930e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d9313  mov     [rax+r11*2], r13w
0x1800d9318  jmp     short loc_1800D9353
0x1800d931a  mov     rdx, r11
0x1800d931d  sub     rdx, r8
0x1800d9320  mov     rax, [rbx+18h]
0x1800d9324  sub     rax, r8
0x1800d9327  cmp     rdx, rax
0x1800d932a  ja      short loc_1800D934B
0x1800d932c  mov     [rbx+10h], r11
0x1800d9330  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d9335  mov     r10, rax
0x1800d9338  lea     rcx, [rax+r8*2]; S
0x1800d933c  mov     r8, rdx; N
0x1800d933f  call    wmemset
0x1800d9344  mov     [r10+r11*2], r13w
0x1800d9349  jmp     short loc_1800D9353
0x1800d934b  mov     r9, rdx
0x1800d934e  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x1800d9353  lea     rdx, aMsmplicsDll_0; "\\MsMpLics.dll"
0x1800d935a  mov     rcx, rbx
0x1800d935d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800d9362  mov     rcx, rbx
0x1800d9365  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d936a  xor     edx, edx; hFile
0x1800d936c  lea     r8d, [rdx+2]; dwFlags
0x1800d9370  mov     rcx, rax; lpLibFileName
0x1800d9373  call    cs:__imp_LoadLibraryExW
0x1800d9379  mov     rdx, rax
0x1800d937c  lea     rcx, [rbp+var_50]
0x1800d9380  call    ??4?$CAutoHandle@PEAUHINSTANCE__@@$1?_HMODULE_Finalizer@@YAXPEAU1@PEAX@Z@@QEAAAEAV0@PEAUHINSTANCE__@@@Z; CAutoHandle<HINSTANCE__ *,&_HMODULE_Finalizer(HINSTANCE__ *,void *)>::operator=(HINSTANCE__ *)
0x1800d9385  mov     rax, [rbp+var_50]
0x1800d9389  test    rax, rax
0x1800d938c  jnz     short loc_1800D93F7
0x1800d938e  call    cs:__imp_GetLastError
0x1800d9394  mov     edi, eax
0x1800d9396  test    eax, eax
0x1800d9398  jle     short loc_1800D93A3
0x1800d939a  movzx   edi, ax
0x1800d939d  or      edi, 80070000h
0x1800d93a3  mov     r10, cs:WPP_GLOBAL_Control
0x1800d93aa  cmp     r10, r14
0x1800d93ad  jz      short loc_1800D93DB
0x1800d93af  test    byte ptr [r10+1Ch], 2
0x1800d93b4  jz      short loc_1800D93DB
0x1800d93b6  mov     rcx, rbx
0x1800d93b9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d93be  mov     edx, 12h
0x1800d93c3  mov     [rsp+80h+N], rax
0x1800d93c8  mov     r9d, edi
0x1800d93cb  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x1800d93d2  mov     rcx, [r10+10h]
0x1800d93d6  call    WPP_SF_dS
0x1800d93db  mov     edx, edi; int
0x1800d93dd  lea     rcx, [rbp+pExceptionObject]; this
0x1800d93e1  call    ??0CError@@QEAA@J@Z; CError::CError(long)
0x1800d93e6  lea     rdx, _TI3?AVCError@@; pThrowInfo
0x1800d93ed  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d93f1  call    _CxxThrowException_0
0x1800d93f7  mov     rdx, r13
0x1800d93fa  xchg    rdx, [rbp+var_50]
0x1800d93fe  lea     rcx, [rdi+8]
0x1800d9402  call    ??4?$CAutoHandle@PEAUHINSTANCE__@@$1?_HMODULE_Finalizer@@YAXPEAU1@PEAX@Z@@QEAAAEAV0@PEAUHINSTANCE__@@@Z; CAutoHandle<HINSTANCE__ *,&_HMODULE_Finalizer(HINSTANCE__ *,void *)>::operator=(HINSTANCE__ *)
0x1800d9407  mov     rdx, rsi
0x1800d940a  mov     rcx, rdi
0x1800d940d  call    ??4?$CSmartPtr@VCWString@@V?$VolatileOps@VCWString@@@@@@QEAAAEAV0@PEBVCWString@@@Z; CSmartPtr<CWString,VolatileOps<CWString>>::operator=(CWString const *)
0x1800d9412  nop
0x1800d9413  mov     rcx, rsi
0x1800d9416  call    ?_Release@?$CSmartPtr@VCWString@@V?$VolatileOps@VCWString@@@@@@KAXPEBVCWString@@@Z; CSmartPtr<CWString,VolatileOps<CWString>>::_Release(CWString const *)
0x1800d941b  nop
0x1800d941c  mov     rcx, r13
0x1800d941f  xchg    rcx, [rbp+var_50]; HINSTANCE
0x1800d9423  mov     rdx, [rbp+var_48]; void *
0x1800d9427  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x1800d942c  nop
0x1800d942d  mov     rax, rdi
0x1800d9430  mov     rcx, [rbp+var_10]
0x1800d9434  xor     rcx, rsp; StackCookie
0x1800d9437  call    __security_check_cookie
0x1800d943c  mov     rbx, [rsp+80h+arg_10]
0x1800d9444  add     rsp, 80h
0x1800d944b  pop     r15
0x1800d944d  pop     r14
0x1800d944f  pop     r13
0x1800d9451  pop     r12
0x1800d9453  pop     rdi
0x1800d9454  pop     rsi
0x1800d9455  pop     rbp
0x1800d9456  retn
0x1800d9457  lea     r14, WPP_GLOBAL_Control
0x1800d945e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9465  cmp     rcx, r14
0x1800d9468  jz      short loc_1800D9485
0x1800d946a  test    byte ptr [rcx+1Ch], 1
0x1800d946e  jz      short loc_1800D9485
0x1800d9470  mov     edx, 13h
0x1800d9475  lea     r8, WPP_7d2f5a35d66339ecd53fcdceb18a5c1b_Traceguids
0x1800d947c  mov     rcx, [rcx+10h]
0x1800d9480  call    WPP_SF_
0x1800d9485  mov     edx, 80070057h; int
0x1800d948a  lea     rcx, [rbp+pExceptionObject]; this
0x1800d948e  call    ??0CError@@QEAA@J@Z; CError::CError(long)
0x1800d9493  lea     rdx, _TI3?AVCError@@; pThrowInfo
0x1800d949a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d949e  call    _CxxThrowException_0
```
