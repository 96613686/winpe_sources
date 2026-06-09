# Utility::GetProgramDataPath(void)

- ea: `0x18004e93c`
- end: `0x18004eaac`
- name: `?GetProgramDataPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b994`

## callees

- `0x1800150ac`
- `0x180045480`
- `0x18004869c`
- `0x18004e93c`
- `0x18004eab4`
- `0x180059920`
- `0x180059cd0`
- `0x180059f2c`
- `0x180059f94`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18004e9ed`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004e9ed`
- `SHELL32!SHGetFolderPathW` at `0x18004ea17`
- `SHELL32!SHGetFolderPathW` at `0x18004ea17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Utility::GetProgramDataPath(__int64 a1)
{
  __int64 v2; // rbx
  __int64 *v3; // rsi
  _QWORD v5[4]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-238h] BYREF

  v5[2] = -2;
  v5[0] = a1;
  v2 = -1;
  v3 = &qword_1801841E8;
  if ( dword_1801841E0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801841E0);
    if ( dword_1801841E0 == -1 )
    {
      std::wstring::wstring(&qword_1801841E8);
      atexit(Utility::GetProgramDataPath_::_2_::_dynamic_atexit_destructor_for__programDataPath__);
      Init_thread_footer(&dword_1801841E0);
    }
  }
  if ( byte_1801817E6 )
  {
    AcquireSRWLockExclusive(&stru_180183E58);
    v5[0] = &stru_180183E58;
    if ( byte_1801817E6 && SHGetFolderPathW(0, 35, 0, 0, pszPath) >= 0 )
    {
      do
        ++v2;
      while ( pszPath[v2] );
      std::wstring::_Assign<unsigned short>(&qword_1801841E8, pszPath);
      byte_1801817E6 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v5);
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  if ( (unsigned __int64)qword_180184200 > 7 )
    v3 = (__int64 *)qword_1801841E8;
  std::wstring::_Construct<2,unsigned short const *>(a1, v3, qword_1801841F8);
  return a1;
}

```

## disassembly

```asm
0x18004e93c  mov     rax, rsp
0x18004e93f  push    rsi
0x18004e940  push    rdi
0x18004e941  push    r14
0x18004e943  sub     rsp, 270h
0x18004e94a  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18004e953  mov     [rax+10h], rbx
0x18004e957  mov     [rax+18h], rbp
0x18004e95b  mov     rax, cs:__security_cookie
0x18004e962  xor     rax, rsp
0x18004e965  mov     [rsp+288h+var_28], rax
0x18004e96d  mov     rdi, rcx
0x18004e970  mov     [rsp+288h+var_258], rcx
0x18004e975  xor     r14d, r14d
0x18004e978  mov     ecx, cs:_tls_index
0x18004e97e  mov     rax, gs:58h
0x18004e987  mov     edx, 4
0x18004e98c  mov     rax, [rax+rcx*8]
0x18004e990  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004e994  lea     rsi, qword_1801841E8
0x18004e99b  mov     eax, [rdx+rax]
0x18004e99e  cmp     cs:dword_1801841E0, eax
0x18004e9a4  jle     short loc_18004E9DA
0x18004e9a6  lea     rcx, dword_1801841E0
0x18004e9ad  call    _Init_thread_header
0x18004e9b2  cmp     cs:dword_1801841E0, ebx
0x18004e9b8  jnz     short loc_18004E9DA
0x18004e9ba  mov     rcx, rsi
0x18004e9bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004e9c2  lea     rcx, _Utility__GetProgramDataPath____2____dynamic_atexit_destructor_for__programDataPath__; void (__cdecl *)()
0x18004e9c9  call    atexit
0x18004e9ce  lea     rcx, dword_1801841E0
0x18004e9d5  call    _Init_thread_footer
0x18004e9da  cmp     cs:byte_1801817E6, r14b
0x18004e9e1  jz      short loc_18004EA51
0x18004e9e3  lea     rbp, stru_180183E58
0x18004e9ea  mov     rcx, rbp; SRWLock
0x18004e9ed  call    cs:__imp_AcquireSRWLockExclusive
0x18004e9f3  mov     [rsp+288h+var_258], rbp
0x18004e9f8  cmp     cs:byte_1801817E6, r14b
0x18004e9ff  jz      short loc_18004EA47
0x18004ea01  lea     rax, [rsp+288h+var_238]
0x18004ea06  mov     [rsp+288h+pszPath], rax; pszPath
0x18004ea0b  xor     r9d, r9d; dwFlags
0x18004ea0e  xor     r8d, r8d; hToken
0x18004ea11  lea     edx, [r9+23h]; csidl
0x18004ea15  xor     ecx, ecx; hwnd
0x18004ea17  call    cs:__imp_SHGetFolderPathW
0x18004ea1d  test    eax, eax
0x18004ea1f  js      short loc_18004EA47
0x18004ea21  lea     rax, [rsp+288h+var_238]
0x18004ea26  inc     rbx
0x18004ea29  cmp     [rax+rbx*2], r14w
0x18004ea2e  jnz     short loc_18004EA26
0x18004ea30  mov     r8, rbx
0x18004ea33  lea     rdx, [rsp+288h+var_238]
0x18004ea38  mov     rcx, rsi
0x18004ea3b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004ea40  mov     cs:byte_1801817E6, r14b
0x18004ea47  lea     rcx, [rsp+288h+var_258]
0x18004ea4c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004ea51  xorps   xmm0, xmm0
0x18004ea54  movups  xmmword ptr [rdi], xmm0
0x18004ea57  mov     [rdi+10h], r14
0x18004ea5b  mov     [rdi+18h], r14
0x18004ea5f  cmp     cs:qword_180184200, 7
0x18004ea67  cmova   rsi, cs:qword_1801841E8
0x18004ea6f  mov     r8, cs:qword_1801841F8
0x18004ea76  mov     rdx, rsi
0x18004ea79  mov     rcx, rdi
0x18004ea7c  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18004ea81  mov     rax, rdi
0x18004ea84  mov     rcx, [rsp+288h+var_28]
0x18004ea8c  xor     rcx, rsp; StackCookie
0x18004ea8f  call    __security_check_cookie
0x18004ea94  lea     r11, [rsp+288h+var_18]
0x18004ea9c  mov     rbx, [r11+28h]
0x18004eaa0  mov     rbp, [r11+30h]
0x18004eaa4  mov     rsp, r11
0x18004eaa7  pop     r14
0x18004eaa9  pop     rdi
0x18004eaaa  pop     rsi
0x18004eaab  retn
```
