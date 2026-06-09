# Uev::ConfigUtil::DeleteProfile(Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &)

- ea: `0x14006b1d0`
- end: `0x14006b373`
- name: `?DeleteProfile@ConfigUtil@Uev@@UEAA_NW4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAJ@Z`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000ba60`
- `0x14000c1cc`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x140025560`
- `0x14006b1d0`
- `0x14006ba18`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006b2c8`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b2c8`
- `ADVAPI32!RegDeleteKeyExW` at `0x14006b311`
- `ADVAPI32!RegDeleteKeyExW` at `0x14006b311`

## string_xrefs

- `0x14006b344`: `Attempting to use an invalid handle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall Uev::ConfigUtil::DeleteProfile(__int64 *a1, unsigned int a2, const WCHAR *a3, LSTATUS *a4)
{
  _QWORD *ConfigRoot; // rax
  _QWORD *v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // r14
  __int64 v12; // rax
  HKEY *v13; // rax
  HKEY hKey; // [rsp+30h] [rbp-79h] BYREF
  __int128 v16; // [rsp+38h] [rbp-71h] BYREF
  __int128 v17; // [rsp+48h] [rbp-61h]
  _QWORD v18[5]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+80h] [rbp-29h] BYREF

  *a4 = 2;
  if ( a2 - 2 <= 1 )
  {
    hKey = 0;
    ConfigRoot = (_QWORD *)Uev::ConfigUtil::GetConfigRoot((__int64)a1, (__int64)v18, a2);
    v9 = std::wstring::_Append<wchar_t>(ConfigRoot, L"\\", 1u);
    v16 = 0;
    v17 = 0;
    v16 = *(_OWORD *)v9;
    v17 = *((_OWORD *)v9 + 1);
    v9[2] = 0;
    v9[3] = 7;
    *(_WORD *)v9 = 0;
    v10 = std::operator+<wchar_t>((__int64)pExceptionObject, &v16);
    v11 = (const WCHAR *)v10;
    if ( *(_QWORD *)(v10 + 24) > 7u )
      v11 = *(const WCHAR **)v10;
    v12 = *a1;
    if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
      v13 = (HKEY *)(*(__int64 (__fastcall **)(__int64 *))(v12 + 40))(a1);
    else
      v13 = (HKEY *)(*(__int64 (__fastcall **)(__int64 *))(v12 + 32))(a1);
    *a4 = RegOpenKeyExW(*v13, v11, 0, 0x20119u, &hKey);
    std::wstring::_Tidy_deallocate(pExceptionObject);
    std::wstring::_Tidy_deallocate(&v16);
    std::wstring::_Tidy_deallocate(v18);
    if ( !*a4 )
    {
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(const WCHAR **)a3;
      if ( !hKey )
      {
        std::wstring::wstring(v18, L"Attempting to use an invalid handle.");
        Uev::SmartHandleException::SmartHandleException(pExceptionObject, v18);
        throw (Uev::SmartHandleException *)pExceptionObject;
      }
      *a4 = RegDeleteKeyExW(hKey, a3, 0x100u, 0);
    }
    Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
  }
  return *a4 == 0;
}

```

## disassembly

```asm
0x14006b1d0  push    rbp
0x14006b1d2  push    rbx
0x14006b1d3  push    rsi
0x14006b1d4  push    rdi
0x14006b1d5  push    r14
0x14006b1d7  push    r15
0x14006b1d9  lea     rbp, [rsp-2Fh]
0x14006b1de  sub     rsp, 0D8h
0x14006b1e5  mov     rax, cs:__security_cookie
0x14006b1ec  xor     rax, rsp
0x14006b1ef  mov     [rbp+57h+var_40], rax
0x14006b1f3  mov     rdi, r9
0x14006b1f6  mov     rbx, r8
0x14006b1f9  mov     r15d, edx
0x14006b1fc  mov     rsi, rcx
0x14006b1ff  mov     dword ptr [r9], 2
0x14006b206  lea     eax, [rdx-2]
0x14006b209  cmp     eax, 1
0x14006b20c  ja      loc_14006B322
0x14006b212  mov     [rbp+57h+hKey], 0
0x14006b21a  mov     r8d, edx
0x14006b21d  lea     rdx, [rbp+57h+var_A8]
0x14006b221  call    ?GetConfigRoot@ConfigUtil@Uev@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4SettingSource@2@@Z; Uev::ConfigUtil::GetConfigRoot(Uev::SettingSource)
0x14006b226  nop
0x14006b227  mov     r8d, 1
0x14006b22d  lea     rdx, SubBlock; "\\"
0x14006b234  mov     rcx, rax; Src
0x14006b237  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14006b23c  xorps   xmm0, xmm0
0x14006b23f  movups  [rbp+57h+var_C8], xmm0
0x14006b243  xorps   xmm1, xmm1
0x14006b246  movdqu  [rbp+57h+var_B8], xmm1
0x14006b24b  movups  xmm0, xmmword ptr [rax]
0x14006b24e  movups  [rbp+57h+var_C8], xmm0
0x14006b252  movups  xmm1, xmmword ptr [rax+10h]
0x14006b256  movups  [rbp+57h+var_B8], xmm1
0x14006b25a  mov     qword ptr [rax+10h], 0
0x14006b262  mov     qword ptr [rax+18h], 7
0x14006b26a  xor     ecx, ecx
0x14006b26c  mov     [rax], cx
0x14006b26f  lea     r8, ?profileKeyName@ConfigUtil@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::ConfigUtil::profileKeyName
0x14006b276  lea     rdx, [rbp+57h+var_C8]
0x14006b27a  lea     rcx, [rbp+57h+pExceptionObject]
0x14006b27e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x14006b283  mov     r14, rax
0x14006b286  cmp     qword ptr [rax+18h], 7
0x14006b28b  jbe     short loc_14006B290
0x14006b28d  mov     r14, [rax]
0x14006b290  lea     eax, [r15-1]
0x14006b294  mov     rcx, rsi
0x14006b297  test    eax, 0FFFFFFFDh
0x14006b29c  mov     rax, [rsi]
0x14006b29f  jz      short loc_14006B2A7
0x14006b2a1  mov     rax, [rax+28h]
0x14006b2a5  jmp     short loc_14006B2AB
0x14006b2a7  mov     rax, [rax+20h]
0x14006b2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b2b0  lea     rcx, [rbp+57h+hKey]
0x14006b2b4  mov     [rsp+100h+phkResult], rcx; phkResult
0x14006b2b9  mov     r9d, 20119h; samDesired
0x14006b2bf  xor     r8d, r8d; ulOptions
0x14006b2c2  mov     rdx, r14; lpSubKey
0x14006b2c5  mov     rcx, [rax]; hKey
0x14006b2c8  call    cs:__imp_RegOpenKeyExW
0x14006b2ce  mov     [rdi], eax
0x14006b2d0  lea     rcx, [rbp+57h+pExceptionObject]
0x14006b2d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006b2d9  nop
0x14006b2da  lea     rcx, [rbp+57h+var_C8]
0x14006b2de  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006b2e3  nop
0x14006b2e4  lea     rcx, [rbp+57h+var_A8]
0x14006b2e8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006b2ed  cmp     dword ptr [rdi], 0
0x14006b2f0  jnz     short loc_14006B319
0x14006b2f2  cmp     qword ptr [rbx+18h], 7
0x14006b2f7  jbe     short loc_14006B2FC
0x14006b2f9  mov     rbx, [rbx]
0x14006b2fc  mov     rcx, [rbp+57h+hKey]; hKey
0x14006b300  test    rcx, rcx
0x14006b303  jz      short loc_14006B344
0x14006b305  xor     r9d, r9d; Reserved
0x14006b308  mov     r8d, 100h; samDesired
0x14006b30e  mov     rdx, rbx; lpSubKey
0x14006b311  call    cs:__imp_RegDeleteKeyExW
0x14006b317  mov     [rdi], eax
0x14006b319  lea     rcx, [rbp+57h+hKey]
0x14006b31d  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14006b322  cmp     dword ptr [rdi], 0
0x14006b325  setz    al
0x14006b328  mov     rcx, [rbp+57h+var_40]
0x14006b32c  xor     rcx, rsp; StackCookie
0x14006b32f  call    __security_check_cookie
0x14006b334  add     rsp, 0D8h
0x14006b33b  pop     r15
0x14006b33d  pop     r14
0x14006b33f  pop     rdi
0x14006b340  pop     rsi
0x14006b341  pop     rbx
0x14006b342  pop     rbp
0x14006b343  retn
0x14006b344  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14006b34b  lea     rcx, [rbp+57h+var_A8]
0x14006b34f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006b354  nop
0x14006b355  lea     rdx, [rbp+57h+var_A8]
0x14006b359  lea     rcx, [rbp+57h+pExceptionObject]
0x14006b35d  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14006b362  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14006b369  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14006b36d  call    _CxxThrowException_0
```
