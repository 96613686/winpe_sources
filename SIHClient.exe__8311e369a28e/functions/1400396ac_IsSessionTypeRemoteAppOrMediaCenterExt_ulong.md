# IsSessionTypeRemoteAppOrMediaCenterExt(ulong)

- ea: `0x1400396ac`
- end: `0x1400397db`
- name: `?IsSessionTypeRemoteAppOrMediaCenterExt@@YAHK@Z`
- size: `303`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003854c`

## callees

- `0x140008de4`
- `0x14000d7e4`
- `0x140018db4`
- `0x1400396ac`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400397bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400397bb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140039770`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400397a4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140039770`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400397a4`

## string_xrefs

- `0x14003972e`: `C:\__w\1\s\src\Client\Engine\lib\susenginelib\tscompat.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsSessionTypeRemoteAppOrMediaCenterExt(WUSystemInterfaceHelper *a1)
{
  unsigned int v1; // edi
  int WUSystemInterface; // eax
  int v3; // ebx
  __int64 v4; // rdx
  unsigned int v5; // ebx
  int lpString2; // [rsp+20h] [rbp-28h]
  PCNZWCH lpString1; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = (unsigned int)a1;
  lpString1 = 0;
  WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(a1);
  v3 = WUSystemInterface;
  if ( WUSystemInterface < 0 )
  {
    v4 = 749;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
      (const char *)(unsigned int)WUSystemInterface,
      lpString2);
    goto LABEL_7;
  }
  WUSystemInterface = (*(__int64 (__fastcall **)(__int64, _QWORD, PCNZWCH *))(*(_QWORD *)g_WUSystemInterface + 464LL))(
                        g_WUSystemInterface,
                        v1,
                        &lpString1);
  v3 = WUSystemInterface;
  if ( WUSystemInterface < 0 )
  {
    v4 = 750;
    goto LABEL_3;
  }
  v3 = 0;
LABEL_7:
  if ( v3 >= 0 )
  {
    v5 = 1;
    if ( lpString1 == L"RemoteApp"
      || lpString1 && CompareStringW(0x7Fu, 1u, lpString1, -1, L"RemoteApp", -1) == 2
      || lpString1 == L"MediaCenterExt"
      || lpString1 && CompareStringW(0x7Fu, 1u, lpString1, -1, L"MediaCenterExt", -1) == 2 )
    {
      goto LABEL_16;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x61,
      (int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\tscompat.cpp",
      (const char *)(unsigned int)v3);
  }
  v5 = 0;
LABEL_16:
  if ( lpString1 )
    CoTaskMemFree((LPVOID)lpString1);
  return v5;
}

```

## disassembly

```asm
0x1400396ac  mov     [rsp+arg_8], rbx
0x1400396b1  push    rdi
0x1400396b2  sub     rsp, 40h
0x1400396b6  mov     rax, cs:__security_cookie
0x1400396bd  xor     rax, rsp
0x1400396c0  mov     [rsp+48h+var_10], rax
0x1400396c5  mov     edi, ecx
0x1400396c7  mov     [rsp+48h+lpString1], 0
0x1400396d0  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x1400396d5  mov     ebx, eax
0x1400396d7  test    eax, eax
0x1400396d9  jns     short loc_1400396F6
0x1400396db  mov     edx, 2EDh; void *
0x1400396e0  lea     r8, aCW1SSrcClientL_16; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x1400396e7  mov     r9d, eax; char *
0x1400396ea  mov     rcx, [rsp+48h]; this
0x1400396ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400396f4  jmp     short loc_140039722
0x1400396f6  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x1400396fd  mov     rax, [rcx]
0x140039700  lea     r8, [rsp+48h+lpString1]
0x140039705  mov     edx, edi
0x140039707  mov     rax, [rax+1D0h]
0x14003970e  call    _guard_dispatch_icall
0x140039713  mov     ebx, eax
0x140039715  test    eax, eax
0x140039717  jns     short loc_140039720
0x140039719  mov     edx, 2EEh
0x14003971e  jmp     short loc_1400396E0
0x140039720  xor     ebx, ebx
0x140039722  mov     rcx, [rsp+48h]; this
0x140039727  test    ebx, ebx
0x140039729  jns     short loc_140039741
0x14003972b  mov     r9d, ebx; char *
0x14003972e  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140039735  mov     edx, 61h ; 'a'; void *
0x14003973a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003973f  jmp     short loc_1400397AF
0x140039741  mov     r8, [rsp+48h+lpString1]; lpString1
0x140039746  lea     rax, aRemoteapp; "RemoteApp"
0x14003974d  mov     ebx, 1
0x140039752  cmp     r8, rax
0x140039755  jz      short loc_1400397B1
0x140039757  or      edi, 0FFFFFFFFh
0x14003975a  test    r8, r8
0x14003975d  jz      short loc_14003977B
0x14003975f  mov     [rsp+48h+cchCount2], edi; cchCount2
0x140039763  mov     [rsp+48h+lpString2], rax; lpString2
0x140039768  mov     r9d, edi; cchCount1
0x14003976b  mov     edx, ebx; dwCmpFlags
0x14003976d  lea     ecx, [rbx+7Eh]; Locale
0x140039770  call    cs:__imp_CompareStringW
0x140039776  cmp     eax, 2
0x140039779  jz      short loc_1400397B1
0x14003977b  mov     r8, [rsp+48h+lpString1]; lpString1
0x140039780  lea     rax, aMediacenterext; "MediaCenterExt"
0x140039787  cmp     r8, rax
0x14003978a  jz      short loc_1400397B1
0x14003978c  test    r8, r8
0x14003978f  jz      short loc_1400397AF
0x140039791  mov     [rsp+48h+cchCount2], edi; cchCount2
0x140039795  mov     [rsp+48h+lpString2], rax; lpString2
0x14003979a  mov     r9d, edi; cchCount1
0x14003979d  mov     edx, ebx; dwCmpFlags
0x14003979f  mov     ecx, 7Fh; Locale
0x1400397a4  call    cs:__imp_CompareStringW
0x1400397aa  cmp     eax, 2
0x1400397ad  jz      short loc_1400397B1
0x1400397af  xor     ebx, ebx
0x1400397b1  mov     rcx, [rsp+48h+lpString1]; pv
0x1400397b6  test    rcx, rcx
0x1400397b9  jz      short loc_1400397C1
0x1400397bb  call    cs:__imp_CoTaskMemFree
0x1400397c1  mov     eax, ebx
0x1400397c3  mov     rcx, [rsp+48h+var_10]
0x1400397c8  xor     rcx, rsp; StackCookie
0x1400397cb  call    __security_check_cookie
0x1400397d0  mov     rbx, [rsp+48h+arg_8]
0x1400397d5  add     rsp, 40h
0x1400397d9  pop     rdi
0x1400397da  retn
```
