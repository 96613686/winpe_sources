# UpdateReserveManagerLoader::LoadReserveManagerDll(wchar_t const * const)

- ea: `0x180010b34`
- end: `0x180010c08`
- name: `?LoadReserveManagerDll@UpdateReserveManagerLoader@@QEAAJQEB_W@Z`
- size: `212`
- prototype: `__int64 __fastcall(UpdateReserveManagerLoader *this, wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18001e400`
- `0x1800746f0`

## callees

- `0x180002564`
- `0x180010b34`
- `0x18001e4fc`
- `0x18001e51c`
- `0x18003e8f8`
- `0x18003ea38`
- `0x1800745a4`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180010bb0`
- `KERNEL32!LoadLibraryExW` at `0x180010bb0`

## string_xrefs

- `0x180010b86`: `onecore\base\servicing\updatereservemanager\loaderlib\updatereservemanagerloader.cpp`
- `0x180010bd4`: `onecore\base\servicing\updatereservemanager\loaderlib\updatereservemanagerloader.cpp`

## pseudocode

```c
__int64 __fastcall UpdateReserveManagerLoader::LoadReserveManagerDll(UpdateReserveManagerLoader *this, wchar_t *a2)
{
  int StackPath; // eax
  unsigned int v4; // edi
  unsigned int LastError; // ebx
  const WCHAR *v6; // rax
  HMODULE Library; // rax
  const char *v8; // r9
  int v10[4]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_OWORD *)v10 = 0;
  v11 = 0;
  StackPath = Windows::AutoSsShim::GetStackPath(a2, (struct _LUNICODE_STRING *)v10);
  v4 = StackPath;
  if ( StackPath == -2147024770 )
  {
    LastError = -2146498192;
  }
  else
  {
    LastError = -2147023590;
    if ( StackPath != -2147023590 )
    {
      if ( StackPath >= 0 )
      {
        v6 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(v10);
        Library = LoadLibraryExW(v6, 0, 0);
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(
          (char *)this + 8,
          Library);
        if ( *((_QWORD *)this + 1) )
          LastError = 0;
        else
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x91,
                        (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\loaderlib\\updatereservemanagerloader.cpp",
                        v8);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\loaderlib\\updatereservemanagerloader.cpp",
          (const char *)(unsigned int)StackPath,
          v10[0]);
        LastError = v4;
      }
    }
  }
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v10);
  return LastError;
}

```

## disassembly

```asm
0x180010b34  mov     r11, rsp
0x180010b37  mov     [r11+18h], rbx
0x180010b3b  mov     [r11+20h], rsi
0x180010b3f  push    rdi
0x180010b40  sub     rsp, 40h
0x180010b44  mov     rsi, rcx
0x180010b47  mov     rax, rdx
0x180010b4a  xor     ecx, ecx
0x180010b4c  lea     rdx, [r11-28h]; struct _LUNICODE_STRING *
0x180010b50  xorps   xmm0, xmm0
0x180010b53  movups  xmmword ptr [rsp+48h+var_28], xmm0; int
0x180010b58  mov     [r11-18h], rcx
0x180010b5c  mov     rcx, rax; wchar_t *
0x180010b5f  call    ?GetStackPath@AutoSsShim@Windows@@SAJQEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@0PEB_K@Z; Windows::AutoSsShim::GetStackPath(wchar_t const * const,Windows::Auto<_LUNICODE_STRING> *,wchar_t const * const,unsigned __int64 const *)
0x180010b64  mov     edi, eax
0x180010b66  cmp     eax, 8007007Eh
0x180010b6b  jnz     short loc_180010B74
0x180010b6d  mov     ebx, 800F0970h
0x180010b72  jmp     short loc_180010BEB
0x180010b74  mov     ebx, 8007051Ah
0x180010b79  cmp     edi, ebx
0x180010b7b  jz      short loc_180010BEB
0x180010b7d  test    edi, edi
0x180010b7f  jns     short loc_180010B9E
0x180010b81  mov     rcx, [rsp+48h]; this
0x180010b86  lea     r8, aOnecoreBaseSer_2; "onecore\\base\\servicing\\updatereserve"...
0x180010b8d  mov     r9d, edi; char *
0x180010b90  mov     edx, 8Eh; void *
0x180010b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b9a  mov     ebx, edi
0x180010b9c  jmp     short loc_180010BEB
0x180010b9e  lea     rcx, [rsp+48h+var_28]
0x180010ba3  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x180010ba8  mov     rcx, rax; lpLibFileName
0x180010bab  xor     r8d, r8d; dwFlags
0x180010bae  xor     edx, edx; hFile
0x180010bb0  call    cs:__imp_LoadLibraryExW
0x180010bb7  nop     dword ptr [rax+rax+00h]
0x180010bbc  mov     rdx, rax
0x180010bbf  lea     rcx, [rsi+8]
0x180010bc3  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x180010bc8  cmp     qword ptr [rsi+8], 0
0x180010bcd  jnz     short loc_180010BE9
0x180010bcf  mov     rcx, [rsp+48h]; this
0x180010bd4  lea     r8, aOnecoreBaseSer_2; "onecore\\base\\servicing\\updatereserve"...
0x180010bdb  mov     edx, 91h; void *
0x180010be0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010be5  mov     ebx, eax
0x180010be7  jmp     short loc_180010BEB
0x180010be9  xor     ebx, ebx
0x180010beb  lea     rcx, [rsp+48h+var_28]
0x180010bf0  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180010bf5  mov     rsi, [rsp+48h+arg_18]
0x180010bfa  mov     eax, ebx
0x180010bfc  mov     rbx, [rsp+48h+arg_10]
0x180010c01  add     rsp, 40h
0x180010c05  pop     rdi
0x180010c06  retn
```
