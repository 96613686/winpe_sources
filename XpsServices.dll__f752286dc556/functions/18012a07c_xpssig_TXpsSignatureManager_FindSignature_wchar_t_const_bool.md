# xpssig::TXpsSignatureManager::FindSignature(wchar_t const *,bool)

- ea: `0x18012a07c`
- end: `0x18012a20a`
- name: `?FindSignature@TXpsSignatureManager@xpssig@@QEAA?AV?$scope@PEAV?$UnknownOnlyLite@VTXpsSignature@xpssig@@V?$type_list@UIXpsSignature@@Vnull_type@win_mp_lib@@@win_mp_lib@@Vnull_type@4@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEB_W_N@Z`
- size: `398`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180129b80`
- `0x180129de0`
- `0x180129ed4`

## callees

- `0x180012450`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c20c4`
- `0x18012a07c`
- `0x18012a210`
- `0x180134b70`
- `0x1801359ce`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012a159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012a16d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012a159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012a16d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall xpssig::TXpsSignatureManager::FindSignature(__int64 a1, _QWORD *a2, unsigned __int16 *a3, char a4)
{
  int v8; // esi
  __int64 **i; // rbx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  void *v13; // rcx
  unsigned __int16 *v14; // rax
  int v15; // r8d
  int v16; // edx
  win_musl::Formatter *v17; // rax
  const wchar_t *v18; // rax
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h]
  _QWORD *v22; // [rsp+50h] [rbp-B0h]
  _BYTE v23[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v24[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+D0h] [rbp-30h] BYREF

  v22 = a2;
  *a2 = 0;
  v21 = 1;
  v8 = 0;
  for ( i = *(__int64 ***)(a1 + 40); i != *(__int64 ***)(a1 + 48); ++i )
  {
    pv = 0;
    v10 = *i;
    v11 = **i;
    pv = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v11 + 24))(v10, &pv);
    v13 = pv;
    if ( v12 >= 0 )
    {
      v14 = a3;
      do
      {
        v15 = *(unsigned __int16 *)((char *)v14 + (_BYTE *)pv - (_BYTE *)a3);
        v16 = *v14 - v15;
        if ( v16 )
          break;
        ++v14;
      }
      while ( v15 );
      if ( !v16 )
      {
        if ( !*a2 )
        {
          win_scope::scope<win_musl::UnknownOnlyLite<xpssig::TXpsSignature,win_mp_lib::type_list<IXpsSignature,win_mp_lib::null_type>,win_mp_lib::null_type> *,win_scope::const_policies<win_scope::com_policies>>::operator=(
            a2,
            i);
          v13 = pv;
        }
        if ( !a4 || (++v8, v8 >= 2) )
        {
          if ( v13 )
            CoTaskMemFree(v13);
          break;
        }
      }
    }
    if ( v13 )
      CoTaskMemFree(v13);
  }
  if ( v8 > 1 )
  {
    std::wstring::wstring(v23, L"Two or more signatures with same ID");
    v17 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v24, v23);
    v18 = win_musl::Formatter::c_str(v17);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x17Cu,
      -2142108792,
      (__int64)v18);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return a2;
}

```

## disassembly

```asm
0x18012a07c  mov     [rsp-8+arg_0], rbx
0x18012a081  mov     [rsp-8+arg_10], rsi
0x18012a086  push    rbp
0x18012a087  push    rdi
0x18012a088  push    r12
0x18012a08a  push    r14
0x18012a08c  push    r15
0x18012a08e  lea     rbp, [rsp-80h]
0x18012a093  sub     rsp, 180h
0x18012a09a  mov     rax, cs:__security_cookie
0x18012a0a1  xor     rax, rsp
0x18012a0a4  mov     [rbp+0A0h+var_30], rax
0x18012a0a8  mov     r15b, r9b
0x18012a0ab  mov     r12, r8
0x18012a0ae  mov     rdi, rdx
0x18012a0b1  mov     r14, rcx
0x18012a0b4  mov     [rsp+1A0h+var_150], rdx
0x18012a0b9  mov     [rsp+1A0h+var_158], 0
0x18012a0c1  mov     qword ptr [rdx], 0
0x18012a0c8  mov     [rsp+1A0h+var_158], 1
0x18012a0d0  xor     esi, esi
0x18012a0d2  mov     rbx, [rcx+28h]
0x18012a0d6  cmp     rbx, [r14+30h]
0x18012a0da  jz      loc_18012A173
0x18012a0e0  mov     [rsp+1A0h+pv], 0
0x18012a0e9  mov     rcx, [rbx]
0x18012a0ec  mov     rax, [rcx]
0x18012a0ef  mov     [rsp+1A0h+pv], 0
0x18012a0f8  lea     rdx, [rsp+1A0h+pv]
0x18012a0fd  mov     rax, [rax+18h]
0x18012a101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a106  mov     rcx, [rsp+1A0h+pv]
0x18012a10b  test    eax, eax
0x18012a10d  js      short loc_18012A154
0x18012a10f  mov     rax, r12
0x18012a112  mov     r9, rcx
0x18012a115  sub     r9, r12
0x18012a118  movzx   edx, word ptr [rax]
0x18012a11b  movzx   r8d, word ptr [rax+r9]
0x18012a120  sub     edx, r8d
0x18012a123  jnz     short loc_18012A12E
0x18012a125  add     rax, 2
0x18012a129  test    r8d, r8d
0x18012a12c  jnz     short loc_18012A118
0x18012a12e  test    edx, edx
0x18012a130  jnz     short loc_18012A154
0x18012a132  cmp     qword ptr [rdi], 0
0x18012a136  jnz     short loc_18012A148
0x18012a138  mov     rdx, rbx
0x18012a13b  mov     rcx, rdi
0x18012a13e  call    ??4?$scope@PEAV?$UnknownOnlyLite@VTXpsSignature@xpssig@@V?$type_list@UIXpsSignature@@Vnull_type@win_mp_lib@@@win_mp_lib@@Vnull_type@4@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAAAEAV01@AEBV01@@Z; win_scope::scope<win_musl::UnknownOnlyLite<xpssig::TXpsSignature,win_mp_lib::type_list<IXpsSignature,win_mp_lib::null_type>,win_mp_lib::null_type> *,win_scope::const_policies<win_scope::com_policies>>::operator=(win_scope::scope<win_musl::UnknownOnlyLite<xpssig::TXpsSignature,win_mp_lib::type_list<IXpsSignature,win_mp_lib::null_type>,win_mp_lib::null_type> *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18012a143  mov     rcx, [rsp+1A0h+pv]; pv
0x18012a148  test    r15b, r15b
0x18012a14b  jz      short loc_18012A168
0x18012a14d  inc     esi
0x18012a14f  cmp     esi, 2
0x18012a152  jge     short loc_18012A168
0x18012a154  test    rcx, rcx
0x18012a157  jz      short loc_18012A15F
0x18012a159  call    cs:__imp_CoTaskMemFree
0x18012a15f  add     rbx, 8
0x18012a163  jmp     loc_18012A0D6
0x18012a168  test    rcx, rcx
0x18012a16b  jz      short loc_18012A173
0x18012a16d  call    cs:__imp_CoTaskMemFree
0x18012a173  cmp     esi, 1
0x18012a176  jle     short loc_18012A1DE
0x18012a178  lea     rdx, aTwoOrMoreSigna; "Two or more signatures with same ID"
0x18012a17f  lea     rcx, [rsp+1A0h+var_148]
0x18012a184  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18012a189  nop
0x18012a18a  lea     rdx, [rsp+1A0h+var_148]
0x18012a18f  lea     rcx, [rbp+0A0h+var_120]
0x18012a193  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18012a198  nop
0x18012a199  mov     rcx, rax; this
0x18012a19c  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18012a1a1  mov     [rsp+1A0h+var_170], rax; __int64
0x18012a1a6  mov     [rsp+1A0h+var_178], 80520388h; int
0x18012a1ae  mov     [rsp+1A0h+var_180], 17Ch; unsigned int
0x18012a1b6  lea     r9, Src
0x18012a1bd  lea     r8, aNoFilename; "(no filename)"
0x18012a1c4  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18012a1c8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18012a1cd  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18012a1d4  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18012a1d8  call    _CxxThrowException_0
0x18012a1de  mov     rax, rdi
0x18012a1e1  mov     rcx, [rbp+0A0h+var_30]
0x18012a1e5  xor     rcx, rsp; StackCookie
0x18012a1e8  call    __security_check_cookie
0x18012a1ed  lea     r11, [rsp+1A0h+var_20]
0x18012a1f5  mov     rbx, [r11+30h]
0x18012a1f9  mov     rsi, [r11+40h]
0x18012a1fd  mov     rsp, r11
0x18012a200  pop     r15
0x18012a202  pop     r14
0x18012a204  pop     r12
0x18012a206  pop     rdi
0x18012a207  pop     rbp
0x18012a208  retn
```
