# mfsensorgroup_utils::UnregisterObject(_GUID const &)

- ea: `0x1800661d4`
- end: `0x18006629f`
- name: `?UnregisterObject@mfsensorgroup_utils@@YAJAEBU_GUID@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(mfsensorgroup_utils *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180065c20`

## callees

- `0x180005fa0`
- `0x180044f30`
- `0x180045900`
- `0x180065c38`
- `0x1800661d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006623f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006623f`

## pseudocode

```c
__int64 __fastcall mfsensorgroup_utils::UnregisterObject(mfsensorgroup_utils *this, const struct _GUID *a2)
{
  mfsensorgroup_utils *v2; // rcx
  unsigned __int16 *v3; // r8
  int v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  unsigned __int64 v8; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v8 = 0;
  v4 = mfsensorgroup_utils::CreateObjectKeyName(v2, SubKey, v3, &v8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 < 0 && g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids, 0, v5);
  }
  else if ( g_wppLevels )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids, 0, v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800661d4  push    rbx
0x1800661d6  sub     rsp, 260h
0x1800661dd  mov     rax, cs:__security_cookie
0x1800661e4  xor     rax, rsp
0x1800661e7  mov     [rsp+268h+var_18], rax
0x1800661ef  xor     edx, edx; Val
0x1800661f1  lea     rcx, [rsp+268h+SubKey]; void *
0x1800661f6  mov     r8d, 208h; Size
0x1800661fc  call    memset_0
0x180066201  lea     r9, [rsp+268h+var_238]; unsigned __int64
0x180066206  mov     [rsp+268h+var_238], 0
0x18006620f  lea     rdx, [rsp+268h+SubKey]; struct _GUID *
0x180066214  call    ?CreateObjectKeyName@mfsensorgroup_utils@@YAJAEBU_GUID@@PEAG_KPEA_K@Z; mfsensorgroup_utils::CreateObjectKeyName(_GUID const &,ushort *,unsigned __int64,unsigned __int64 *)
0x180066219  mov     ebx, eax
0x18006621b  test    eax, eax
0x18006621d  jns     short loc_180066233
0x18006621f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066226  jb      short loc_180066284
0x180066228  mov     edx, 1Fh
0x18006622d  mov     [rsp+268h+var_248], eax
0x180066231  jmp     short loc_18006626A
0x180066233  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x180066238  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006623f  call    cs:__imp_RegDeleteTreeW
0x180066245  mov     ebx, eax
0x180066247  test    eax, eax
0x180066249  jle     short loc_180066254
0x18006624b  movzx   ebx, ax
0x18006624e  or      ebx, 80070000h
0x180066254  test    ebx, ebx
0x180066256  jns     short loc_180066284
0x180066258  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006625f  jb      short loc_180066284
0x180066261  mov     edx, 20h ; ' '
0x180066266  mov     [rsp+268h+var_248], ebx
0x18006626a  mov     rcx, cs:WPP_GLOBAL_Control
0x180066271  lea     r8, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids
0x180066278  xor     r9d, r9d
0x18006627b  mov     rcx, [rcx+10h]
0x18006627f  call    WPP_SF_qD
0x180066284  mov     eax, ebx
0x180066286  mov     rcx, [rsp+268h+var_18]
0x18006628e  xor     rcx, rsp; StackCookie
0x180066291  call    __security_check_cookie
0x180066296  add     rsp, 260h
0x18006629d  pop     rbx
0x18006629e  retn
```
