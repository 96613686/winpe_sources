# wil::reg::open_unique_key_nothrow(HKEY__ *,wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)

- ea: `0x1800238ec`
- end: `0x18002399f`
- name: `?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z`
- size: `179`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180022678`
- `0x180022af4`
- `0x180023530`

## callees

- `0x1800079a4`
- `0x1800238ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023908`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023908`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002391b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002391b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002396b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002396b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023913`

## string_xrefs

- `0x18002398d`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
LSTATUS __fastcall wil::reg::open_unique_key_nothrow(__int64 a1, const WCHAR *a2, HKEY *a3, const char *a4)
{
  HKEY v4; // rbp
  int v5; // edi
  DWORD LastError; // ebx
  int v9; // edi
  int v10; // edi
  REGSAM v11; // r9d
  LSTATUS result; // eax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = *a3;
  v5 = (int)a4;
  if ( *a3 )
  {
    LastError = GetLastError();
    RegCloseKey(v4);
    SetLastError(LastError);
  }
  *a3 = 0;
  if ( v5 )
  {
    v9 = v5 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x77,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
            a4);
        v11 = 983359;
      }
      else
      {
        v11 = 131353;
      }
    }
    else
    {
      v11 = 983103;
    }
  }
  else
  {
    v11 = 131097;
  }
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v11, a3);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800238ec  push    rbx
0x1800238ee  push    rbp
0x1800238ef  push    rsi
0x1800238f0  push    rdi
0x1800238f1  push    r14
0x1800238f3  sub     rsp, 30h
0x1800238f7  mov     rbp, [r8]
0x1800238fa  mov     edi, r9d
0x1800238fd  mov     rsi, r8
0x180023900  mov     r14, rdx
0x180023903  test    rbp, rbp
0x180023906  jz      short loc_180023921
0x180023908  call    cs:__imp_GetLastError
0x18002390e  mov     rcx, rbp; hKey
0x180023911  mov     ebx, eax
0x180023913  call    cs:__imp_RegCloseKey
0x180023919  mov     ecx, ebx; dwErrCode
0x18002391b  call    cs:__imp_SetLastError
0x180023921  mov     qword ptr [rsi], 0
0x180023928  test    edi, edi
0x18002392a  jz      short loc_180023953
0x18002392c  sub     edi, 1
0x18002392f  jz      short loc_18002394B
0x180023931  sub     edi, 1
0x180023934  jz      short loc_180023943
0x180023936  cmp     edi, 1
0x180023939  jnz     short loc_180023988
0x18002393b  mov     r9d, 0F013Fh
0x180023941  jmp     short loc_180023959
0x180023943  mov     r9d, 20119h
0x180023949  jmp     short loc_180023959
0x18002394b  mov     r9d, 0F003Fh
0x180023951  jmp     short loc_180023959
0x180023953  mov     r9d, 20019h; samDesired
0x180023959  xor     r8d, r8d; ulOptions
0x18002395c  mov     [rsp+58h+phkResult], rsi; phkResult
0x180023961  mov     rdx, r14; lpSubKey
0x180023964  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002396b  call    cs:__imp_RegOpenKeyExW
0x180023971  test    eax, eax
0x180023973  jle     short loc_18002397D
0x180023975  movzx   eax, ax
0x180023978  or      eax, 80070000h
0x18002397d  add     rsp, 30h
0x180023981  pop     r14
0x180023983  pop     rdi
0x180023984  pop     rsi
0x180023985  pop     rbp
0x180023986  pop     rbx
0x180023987  retn
0x180023988  mov     rcx, [rsp+58h]; this
0x18002398d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023994  mov     edx, 77h ; 'w'; void *
0x180023999  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
