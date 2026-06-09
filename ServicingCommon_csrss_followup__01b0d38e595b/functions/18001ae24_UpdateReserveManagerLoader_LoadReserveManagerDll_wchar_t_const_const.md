# UpdateReserveManagerLoader::LoadReserveManagerDll(wchar_t const * const)

- ea: `0x18001ae24`
- end: `0x18001aef8`
- name: `?LoadReserveManagerDll@UpdateReserveManagerLoader@@QEAAJQEB_W@Z`
- size: `212`
- prototype: `int(UpdateReserveManagerLoader *__hidden this, const wchar_t *const)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18001ad90`
- `0x180074490`

## callees

- `0x180004a8c`
- `0x18001ae24`
- `0x18001d694`
- `0x180020440`
- `0x180023664`
- `0x18004194c`
- `0x180074344`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001aea0`
- `KERNEL32!LoadLibraryExW` at `0x18001aea0`

## string_xrefs

- `0x18001ae76`: `onecore\base\servicing\updatereservemanager\loaderlib\updatereservemanagerloader.cpp`
- `0x18001aec4`: `onecore\base\servicing\updatereservemanager\loaderlib\updatereservemanagerloader.cpp`

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
0x18001ae24  mov     r11, rsp
0x18001ae27  mov     [r11+18h], rbx
0x18001ae2b  mov     [r11+20h], rsi
0x18001ae2f  push    rdi
0x18001ae30  sub     rsp, 40h
0x18001ae34  mov     rsi, rcx
0x18001ae37  mov     rax, rdx
0x18001ae3a  xor     ecx, ecx
0x18001ae3c  lea     rdx, [r11-28h]; struct _LUNICODE_STRING *
0x18001ae40  xorps   xmm0, xmm0
0x18001ae43  movups  xmmword ptr [rsp+48h+var_28], xmm0; int
0x18001ae48  mov     [r11-18h], rcx
0x18001ae4c  mov     rcx, rax; wchar_t *
0x18001ae4f  call    ?GetStackPath@AutoSsShim@Windows@@SAJQEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@0PEB_K@Z; Windows::AutoSsShim::GetStackPath(wchar_t const * const,Windows::Auto<_LUNICODE_STRING> *,wchar_t const * const,unsigned __int64 const *)
0x18001ae54  mov     edi, eax
0x18001ae56  cmp     eax, 8007007Eh
0x18001ae5b  jnz     short loc_18001AE64
0x18001ae5d  mov     ebx, 800F0970h
0x18001ae62  jmp     short loc_18001AEDB
0x18001ae64  mov     ebx, 8007051Ah
0x18001ae69  cmp     edi, ebx
0x18001ae6b  jz      short loc_18001AEDB
0x18001ae6d  test    edi, edi
0x18001ae6f  jns     short loc_18001AE8E
0x18001ae71  mov     rcx, [rsp+48h]; this
0x18001ae76  lea     r8, aOnecoreBaseSer_2; "onecore\\base\\servicing\\updatereserve"...
0x18001ae7d  mov     r9d, edi; char *
0x18001ae80  mov     edx, 8Eh; void *
0x18001ae85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae8a  mov     ebx, edi
0x18001ae8c  jmp     short loc_18001AEDB
0x18001ae8e  lea     rcx, [rsp+48h+var_28]
0x18001ae93  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x18001ae98  mov     rcx, rax; lpLibFileName
0x18001ae9b  xor     r8d, r8d; dwFlags
0x18001ae9e  xor     edx, edx; hFile
0x18001aea0  call    cs:__imp_LoadLibraryExW
0x18001aea7  nop     dword ptr [rax+rax+00h]
0x18001aeac  mov     rdx, rax
0x18001aeaf  lea     rcx, [rsi+8]
0x18001aeb3  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x18001aeb8  cmp     qword ptr [rsi+8], 0
0x18001aebd  jnz     short loc_18001AED9
0x18001aebf  mov     rcx, [rsp+48h]; this
0x18001aec4  lea     r8, aOnecoreBaseSer_2; "onecore\\base\\servicing\\updatereserve"...
0x18001aecb  mov     edx, 91h; void *
0x18001aed0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001aed5  mov     ebx, eax
0x18001aed7  jmp     short loc_18001AEDB
0x18001aed9  xor     ebx, ebx
0x18001aedb  lea     rcx, [rsp+48h+var_28]
0x18001aee0  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18001aee5  mov     rsi, [rsp+48h+arg_18]
0x18001aeea  mov     eax, ebx
0x18001aeec  mov     rbx, [rsp+48h+arg_10]
0x18001aef1  add     rsp, 40h
0x18001aef5  pop     rdi
0x18001aef6  retn
```
