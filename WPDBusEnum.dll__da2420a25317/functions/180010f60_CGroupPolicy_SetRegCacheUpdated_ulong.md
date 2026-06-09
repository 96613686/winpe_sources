# CGroupPolicy::SetRegCacheUpdated(ulong)

- ea: `0x180010f60`
- end: `0x180011002`
- name: `?SetRegCacheUpdated@CGroupPolicy@@IEAAJK@Z`
- size: `162`
- prototype: `__int64 __fastcall(CGroupPolicy *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180008128`

## callees

- `0x180001730`
- `0x180007160`
- `0x1800097d0`
- `0x18000a192`
- `0x180010f60`

## string_xrefs

- `0x180010f93`: `RegCacheState`
- `0x180010fce`: `RegCacheUpdated`

## pseudocode

```c
LSTATUS __fastcall CGroupPolicy::SetRegCacheUpdated(CGroupPolicy *this)
{
  LSTATUS result; // eax
  __int64 v2; // rdx
  BYTE v3[16]; // [rsp+40h] [rbp-238h] BYREF
  unsigned __int16 v4[264]; // [rsp+50h] [rbp-228h] BYREF

  *(_DWORD *)v3 = 0;
  memset_0(v4, 0, 0x208u);
  result = StringCchPrintfW(v4, 0x104u, L"%ws\\%ws", L"SYSTEM\\CurrentControlSet\\Control\\Storage", L"RegCacheState");
  if ( result >= 0 )
    return WPDLibSetRegistryValue(0, v2, v4, L"RegCacheUpdated", 4u, v3, 4u);
  return result;
}

```

## disassembly

```asm
0x180010f60  sub     rsp, 278h
0x180010f67  mov     rax, cs:__security_cookie
0x180010f6e  xor     rax, rsp
0x180010f71  mov     [rsp+278h+var_18], rax
0x180010f79  xor     edx, edx; Val
0x180010f7b  mov     dword ptr [rsp+278h+var_238], 0
0x180010f83  mov     r8d, 208h; Size
0x180010f89  lea     rcx, [rsp+278h+var_228]; void *
0x180010f8e  call    memset_0
0x180010f93  lea     rax, aRegcachestate; "RegCacheState"
0x180010f9a  mov     edx, 104h; unsigned __int64
0x180010f9f  lea     r9, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x180010fa6  mov     [rsp+278h+var_258], rax
0x180010fab  lea     r8, aWsWs; "%ws\\%ws"
0x180010fb2  lea     rcx, [rsp+278h+var_228]; unsigned __int16 *
0x180010fb7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010fbc  test    eax, eax
0x180010fbe  js      short loc_180010FEA
0x180010fc0  mov     ecx, 4
0x180010fc5  lea     rax, [rsp+278h+var_238]
0x180010fca  mov     [rsp+278h+var_248], ecx
0x180010fce  lea     r9, aRegcacheupdate; "RegCacheUpdated"
0x180010fd5  mov     [rsp+278h+var_250], rax
0x180010fda  lea     r8, [rsp+278h+var_228]
0x180010fdf  mov     dword ptr [rsp+278h+var_258], ecx
0x180010fe3  xor     ecx, ecx
0x180010fe5  call    WPDLibSetRegistryValue
0x180010fea  mov     rcx, [rsp+278h+var_18]
0x180010ff2  xor     rcx, rsp; StackCookie
0x180010ff5  call    __security_check_cookie
0x180010ffa  add     rsp, 278h
0x180011001  retn
```
