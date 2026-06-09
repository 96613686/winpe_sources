# wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)

- ea: `0x1800233ec`
- end: `0x1800234a2`
- name: `?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z`
- size: `182`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018758`
- `0x18001a038`
- `0x18001a154`
- `0x18001a570`
- `0x18001cce4`
- `0x18001cea8`
- `0x18001e2dc`
- `0x18001e450`
- `0x18001e518`
- `0x18001fd50`
- `0x180028844`
- `0x18002b864`
- `0x18002c454`
- `0x18002cf54`
- `0x18002d050`

## callees

- `0x180006cb8`
- `0x1800233ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023420`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002340d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002340d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002346c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002346c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023418`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023418`

## string_xrefs

- `0x180023490`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
LSTATUS __fastcall wil::reg::open_unique_key_nothrow(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult, const char *a4)
{
  HKEY v4; // rbp
  int v5; // edi
  DWORD LastError; // ebx
  int v10; // edi
  int v11; // edi
  REGSAM v12; // r9d
  LSTATUS result; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = *phkResult;
  v5 = (int)a4;
  if ( *phkResult )
  {
    LastError = GetLastError();
    RegCloseKey(v4);
    SetLastError(LastError);
  }
  *phkResult = 0;
  if ( v5 )
  {
    v10 = v5 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 != 1 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x77,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
            a4);
        v12 = 983359;
      }
      else
      {
        v12 = 131353;
      }
    }
    else
    {
      v12 = 983103;
    }
  }
  else
  {
    v12 = 131097;
  }
  result = RegOpenKeyExW(hKey, lpSubKey, 0, v12, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800233ec  push    rbx
0x1800233ee  push    rbp
0x1800233ef  push    rsi
0x1800233f0  push    rdi
0x1800233f1  push    r14
0x1800233f3  push    r15
0x1800233f5  sub     rsp, 38h
0x1800233f9  mov     rbp, [r8]
0x1800233fc  mov     edi, r9d
0x1800233ff  mov     rsi, r8
0x180023402  mov     r14, rdx
0x180023405  mov     r15, rcx
0x180023408  test    rbp, rbp
0x18002340b  jz      short loc_180023426
0x18002340d  call    cs:__imp_GetLastError
0x180023413  mov     rcx, rbp; hKey
0x180023416  mov     ebx, eax
0x180023418  call    cs:__imp_RegCloseKey
0x18002341e  mov     ecx, ebx; dwErrCode
0x180023420  call    cs:__imp_SetLastError
0x180023426  mov     qword ptr [rsi], 0
0x18002342d  test    edi, edi
0x18002342f  jz      short loc_180023458
0x180023431  sub     edi, 1
0x180023434  jz      short loc_180023450
0x180023436  sub     edi, 1
0x180023439  jz      short loc_180023448
0x18002343b  cmp     edi, 1
0x18002343e  jnz     short loc_18002348B
0x180023440  mov     r9d, 0F013Fh
0x180023446  jmp     short loc_18002345E
0x180023448  mov     r9d, 20119h
0x18002344e  jmp     short loc_18002345E
0x180023450  mov     r9d, 0F003Fh
0x180023456  jmp     short loc_18002345E
0x180023458  mov     r9d, 20019h; samDesired
0x18002345e  xor     r8d, r8d; ulOptions
0x180023461  mov     [rsp+68h+phkResult], rsi; phkResult
0x180023466  mov     rdx, r14; lpSubKey
0x180023469  mov     rcx, r15; hKey
0x18002346c  call    cs:__imp_RegOpenKeyExW
0x180023472  test    eax, eax
0x180023474  jle     short loc_18002347E
0x180023476  movzx   eax, ax
0x180023479  or      eax, 80070000h
0x18002347e  add     rsp, 38h
0x180023482  pop     r15
0x180023484  pop     r14
0x180023486  pop     rdi
0x180023487  pop     rsi
0x180023488  pop     rbp
0x180023489  pop     rbx
0x18002348a  retn
0x18002348b  mov     rcx, [rsp+68h]; this
0x180023490  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023497  mov     edx, 77h ; 'w'; void *
0x18002349c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
