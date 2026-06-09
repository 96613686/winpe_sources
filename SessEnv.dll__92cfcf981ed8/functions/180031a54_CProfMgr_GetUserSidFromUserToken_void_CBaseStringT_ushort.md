# CProfMgr::GetUserSidFromUserToken(void *,CBaseStringT<ushort> &)

- ea: `0x180031a54`
- end: `0x180031b55`
- name: `?GetUserSidFromUserToken@CProfMgr@@AEAAJPEAXAEAV?$CBaseStringT@G@@@Z`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002da0`
- `0x180031f00`

## callees

- `0x180003f30`
- `0x18003114c`
- `0x1800318f8`
- `0x180031a54`
- `0x180032754`
- `0x18003279c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b3d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180031ac3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180031ac3`

## string_xrefs

- `0x180031a73`: `CProfMgr::GetUserSidFromUserToken`
- `0x180031b24`: `CProfMgr::GetUserSidFromUserToken`
- `0x180031a7a`: `hTokenUser`
- `0x180031b1d`: `Get SID string failed: 0x%x in %s`
- `0x180031b11`: `strUserSID.Set() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CProfMgr::GetUserSidFromUserToken(void *a1, void *a2, __int64 a3)
{
  int UserSid; // ebx
  LPWSTR v5; // rdi
  int v6; // eax
  PSID Sid; // [rsp+30h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp+10h] BYREF

  Sid = a1;
  if ( !a2 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "hTokenUser", "CProfMgr::GetUserSidFromUserToken");
    return (unsigned int)-2147024809;
  }
  v5 = 0;
  Sid = 0;
  UserSid = GetUserSid(a2, &Sid);
  if ( UserSid < 0 )
    goto LABEL_11;
  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    UserSid = 0;
  }
  else
  {
    UserSid = ResultFromKnownLastError();
    if ( UserSid < 0 )
      goto LABEL_8;
  }
  v5 = StringSid;
LABEL_8:
  ResultFromHeapFree(Sid);
  if ( UserSid >= 0 )
  {
    *(_DWORD *)(a3 + 16) = 0;
    *(_DWORD *)(a3 + 8) = 0;
    v6 = CBaseStringT<unsigned short>::Append(a3, (__int64)v5);
    UserSid = v6;
    if ( v6 < 0 )
      _DbgPrintMessage(8, "strUserSID.Set() failed: 0x%x in %s", (unsigned int)v6, "CProfMgr::GetUserSidFromUserToken");
    goto LABEL_12;
  }
LABEL_11:
  _DbgPrintMessage(8, "Get SID string failed: 0x%x in %s", (unsigned int)UserSid, "CProfMgr::GetUserSidFromUserToken");
LABEL_12:
  if ( v5 )
    LocalFree(v5);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180031a54  mov     [rsp+arg_10], rbx
0x180031a59  mov     [rsp+arg_18], rsi
0x180031a5e  mov     [rsp+Sid], rcx
0x180031a63  push    rdi
0x180031a64  sub     rsp, 20h
0x180031a68  mov     rsi, r8
0x180031a6b  mov     rax, rdx
0x180031a6e  test    rdx, rdx
0x180031a71  jnz     short loc_180031A9A
0x180031a73  lea     r9, aCprofmgrGetuse_0; "CProfMgr::GetUserSidFromUserToken"
0x180031a7a  lea     r8, aHtokenuser; "hTokenUser"
0x180031a81  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180031a88  lea     ecx, [rax+8]; int
0x180031a8b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031a90  mov     ebx, 80070057h
0x180031a95  jmp     loc_180031B43
0x180031a9a  xor     edi, edi
0x180031a9c  lea     rdx, [rsp+28h+Sid]; void **
0x180031aa1  mov     rcx, rax; TokenHandle
0x180031aa4  mov     [rsp+28h+Sid], rdi
0x180031aa9  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180031aae  mov     ebx, eax
0x180031ab0  test    eax, eax
0x180031ab2  js      short loc_180031B1A
0x180031ab4  mov     rcx, [rsp+28h+Sid]; Sid
0x180031ab9  lea     rdx, [rsp+28h+StringSid]; StringSid
0x180031abe  mov     [rsp+28h+StringSid], rdi
0x180031ac3  call    cs:__imp_ConvertSidToStringSidW
0x180031ac9  test    eax, eax
0x180031acb  jz      short loc_180031AD1
0x180031acd  xor     ebx, ebx
0x180031acf  jmp     short loc_180031ADC
0x180031ad1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180031ad6  mov     ebx, eax
0x180031ad8  test    eax, eax
0x180031ada  js      short loc_180031AE1
0x180031adc  mov     rdi, [rsp+28h+StringSid]
0x180031ae1  mov     rcx, [rsp+28h+Sid]; lpMem
0x180031ae6  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180031aeb  test    ebx, ebx
0x180031aed  js      short loc_180031B1A
0x180031aef  mov     rdx, rdi
0x180031af2  mov     dword ptr [rsi+10h], 0
0x180031af9  mov     rcx, rsi
0x180031afc  mov     dword ptr [rsi+8], 0
0x180031b03  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x180031b08  mov     ebx, eax
0x180031b0a  test    eax, eax
0x180031b0c  jns     short loc_180031B35
0x180031b0e  mov     r8d, eax
0x180031b11  lea     rdx, aStrusersidSetF; "strUserSID.Set() failed: 0x%x in %s"
0x180031b18  jmp     short loc_180031B24
0x180031b1a  mov     r8d, ebx
0x180031b1d  lea     rdx, aGetSidStringFa; "Get SID string failed: 0x%x in %s"
0x180031b24  lea     r9, aCprofmgrGetuse_0; "CProfMgr::GetUserSidFromUserToken"
0x180031b2b  mov     ecx, 8; int
0x180031b30  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031b35  test    rdi, rdi
0x180031b38  jz      short loc_180031B43
0x180031b3a  mov     rcx, rdi; hMem
0x180031b3d  call    cs:__imp_LocalFree
0x180031b43  mov     rsi, [rsp+28h+arg_18]
0x180031b48  mov     eax, ebx
0x180031b4a  mov     rbx, [rsp+28h+arg_10]
0x180031b4f  add     rsp, 20h
0x180031b53  pop     rdi
0x180031b54  retn
```
