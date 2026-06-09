# CExtensionList::_RecordUsageDataLastWriteTime(void)

- ea: `0x180069d44`
- end: `0x180069de8`
- name: `?_RecordUsageDataLastWriteTime@CExtensionList@@AEAAJXZ`
- size: `164`
- prototype: `__int64 __fastcall(CExtensionList *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180066a30`
- `0x180068ef4`

## callees

- `0x180043c30`
- `0x180061b4c`
- `0x180067430`
- `0x180068c24`
- `0x180069d44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180069d8f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180069d8f`

## pseudocode

```c
__int64 __fastcall CExtensionList::_RecordUsageDataLastWriteTime(CExtensionList *this)
{
  const unsigned __int16 *v2; // rcx
  int v3; // ebx
  LPOLESTR lpsz; // [rsp+30h] [rbp-28h] BYREF
  IID rclsid; // [rsp+38h] [rbp-20h] BYREF

  v2 = (const unsigned __int16 *)*((_QWORD *)this + 9);
  rclsid = 0;
  v3 = UAGetLoggerIDByContractID(v2, &rclsid);
  if ( v3 >= 0 )
  {
    lpsz = 0;
    v3 = StringFromCLSID(&rclsid, &lpsz);
    if ( v3 >= 0 )
      v3 = _GetRegKeyLastWriteTime(
             HKEY_CURRENT_USER,
             (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\UserAssist",
             (__int64)lpsz,
             1,
             (PFILETIME)this + 14);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpsz);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180069d44  mov     [rsp+arg_8], rbx
0x180069d49  push    rdi
0x180069d4a  sub     rsp, 50h
0x180069d4e  mov     rax, cs:__security_cookie
0x180069d55  xor     rax, rsp
0x180069d58  mov     [rsp+58h+var_10], rax
0x180069d5d  mov     rdi, rcx
0x180069d60  lea     rdx, [rsp+58h+rclsid]; struct _GUID *
0x180069d65  mov     rcx, [rcx+48h]; unsigned __int16 *
0x180069d69  xorps   xmm0, xmm0
0x180069d6c  movups  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x180069d71  call    ?UAGetLoggerIDByContractID@@YAJPEBGPEAU_GUID@@@Z; UAGetLoggerIDByContractID(ushort const *,_GUID *)
0x180069d76  mov     ebx, eax
0x180069d78  test    eax, eax
0x180069d7a  js      short loc_180069DCE
0x180069d7c  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x180069d81  mov     [rsp+58h+lpsz], 0
0x180069d8a  lea     rcx, [rsp+58h+rclsid]; rclsid
0x180069d8f  call    cs:__imp_StringFromCLSID
0x180069d95  mov     ebx, eax
0x180069d97  test    eax, eax
0x180069d99  js      short loc_180069DC4
0x180069d9b  mov     r8, [rsp+58h+lpsz]
0x180069da0  lea     rax, [rdi+70h]
0x180069da4  mov     r9d, 1
0x180069daa  mov     [rsp+58h+var_38], rax
0x180069daf  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180069db6  mov     rcx, 0FFFFFFFF80000001h
0x180069dbd  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x180069dc2  mov     ebx, eax
0x180069dc4  lea     rcx, [rsp+58h+lpsz]
0x180069dc9  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180069dce  mov     eax, ebx
0x180069dd0  mov     rcx, [rsp+58h+var_10]
0x180069dd5  xor     rcx, rsp; StackCookie
0x180069dd8  call    __security_check_cookie
0x180069ddd  mov     rbx, [rsp+58h+arg_8]
0x180069de2  add     rsp, 50h
0x180069de6  pop     rdi
0x180069de7  retn
```
