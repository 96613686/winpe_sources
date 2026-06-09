# ORegistryKey::Create(HKEY__ * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool,ORegistry::REGKEY_ACCESS_MODE,ulong,ulong)

- ea: `0x1800035bc`
- end: `0x1800036c2`
- name: `?Create@ORegistryKey@@AEAAKQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NW4REGKEY_ACCESS_MODE@ORegistry@@KK@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800033e0`

## callees

- `0x1800035bc`
- `0x180003bb0`
- `0x180003c70`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18000363d`
- `ADVAPI32!RegCreateKeyExW` at `0x18000363d`

## pseudocode

```c
__int64 __fastcall ORegistryKey::Create(__int64 a1, HKEY a2, const WCHAR *a3)
{
  __int64 v3; // rdi
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  int v8; // edx
  int v9; // r9d
  DWORD dwDisposition; // [rsp+50h] [rbp-3B8h] BYREF
  LSTATUS v12[3]; // [rsp+54h] [rbp-3B4h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+60h] [rbp-3A8h] BYREF

  v3 = a1 + 16;
  dwDisposition = 0;
  if ( *(_QWORD *)(a1 + 32) > 0xFFu )
  {
    OException::OException(pExceptionObject, a2, a3, a1 + 16);
    throw (OException *)pExceptionObject;
  }
  v6 = a3;
  if ( *((_QWORD *)a3 + 3) > 7u )
    v6 = *(const WCHAR **)a3;
  v7 = RegCreateKeyExW(a2, v6, 0, 0, 0, 0x3001Fu, 0, (PHKEY)(a1 + 48), &dwDisposition);
  v12[0] = v7;
  if ( v7 )
  {
    OException::OException((unsigned int)pExceptionObject, v8, v7, v9, v3, (__int64)a3, (__int64)v12);
    throw (OException *)pExceptionObject;
  }
  return dwDisposition;
}

```

## disassembly

```asm
0x1800035bc  mov     [rsp+arg_18], rbx
0x1800035c1  push    rdi
0x1800035c2  sub     rsp, 400h
0x1800035c9  mov     rax, cs:__security_cookie
0x1800035d0  xor     rax, rsp
0x1800035d3  mov     [rsp+408h+var_18], rax
0x1800035db  lea     rdi, [rcx+10h]
0x1800035df  mov     [rsp+408h+dwDisposition], 0
0x1800035e7  cmp     qword ptr [rdi+10h], 0FFh
0x1800035ef  mov     rbx, r8
0x1800035f2  mov     r10, rdx
0x1800035f5  ja      loc_1800036A3
0x1800035fb  cmp     qword ptr [r8+18h], 7
0x180003600  mov     rdx, rbx
0x180003603  jbe     short loc_180003608
0x180003605  mov     rdx, [r8]; lpSubKey
0x180003608  lea     rax, [rcx+30h]
0x18000360c  xor     r9d, r9d; lpClass
0x18000360f  lea     rcx, [rsp+408h+dwDisposition]
0x180003614  xor     r8d, r8d; Reserved
0x180003617  mov     [rsp+408h+lpdwDisposition], rcx; lpdwDisposition
0x18000361c  mov     rcx, r10; hKey
0x18000361f  mov     [rsp+408h+phkResult], rax; phkResult
0x180003624  mov     [rsp+408h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000362d  mov     [rsp+408h+samDesired], 3001Fh; samDesired
0x180003635  mov     [rsp+408h+dwOptions], 0; dwOptions
0x18000363d  call    cs:__imp_RegCreateKeyExW
0x180003643  mov     [rsp+408h+var_3B4], eax
0x180003647  test    eax, eax
0x180003649  jnz     short loc_180003670
0x18000364b  mov     eax, [rsp+408h+dwDisposition]
0x18000364f  mov     rcx, [rsp+408h+var_18]
0x180003657  xor     rcx, rsp; StackCookie
0x18000365a  call    __security_check_cookie
0x18000365f  mov     rbx, [rsp+408h+arg_18]
0x180003667  add     rsp, 400h
0x18000366e  pop     rdi
0x18000366f  retn
0x180003670  lea     rcx, [rsp+408h+var_3B4]
0x180003675  mov     r8d, eax
0x180003678  mov     [rsp+408h+lpSecurityAttributes], rcx
0x18000367d  lea     rcx, [rsp+408h+pExceptionObject]
0x180003682  mov     qword ptr [rsp+408h+samDesired], rbx
0x180003687  mov     qword ptr [rsp+408h+dwOptions], rdi
0x18000368c  call    ??$?0$0CK@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@K@OException@@QEAA@W4exceptionType@et@@IAEAY0CK@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2AEBK@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[42],std::wstring const &,std::wstring const &,ulong const &)
0x180003691  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180003698  lea     rcx, [rsp+408h+pExceptionObject]; pExceptionObject
0x18000369d  call    _CxxThrowException
0x1800036a3  mov     r9, rdi
0x1800036a6  lea     rcx, [rsp+408h+pExceptionObject]
0x1800036ab  call    ??$?0$0EC@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OException@@QEAA@W4exceptionType@et@@AEAY0EC@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OException::OException(et::exceptionType,wchar_t const (&)[66],std::wstring const &)
0x1800036b0  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800036b7  lea     rcx, [rsp+408h+pExceptionObject]; pExceptionObject
0x1800036bc  call    _CxxThrowException
```
