# LogonTrigger::UpdateUserAccessTime(ushort const *)

- ea: `0x180013c28`
- end: `0x180013cea`
- name: `?UpdateUserAccessTime@LogonTrigger@@QEAAJPEBG@Z`
- size: `194`
- prototype: `int(LogonTrigger *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180012b2c`
- `0x180012dc8`
- `0x1800133fc`

## callees

- `0x180005120`
- `0x18000ccd4`
- `0x180013c1c`
- `0x180013c28`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013c88`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013c88`

## string_xrefs

- `0x180013cbc`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LogonTrigger::UpdateUserAccessTime(LogonTrigger *this, const unsigned __int16 *a2)
{
  __int64 v3; // rdi
  int (__fastcall *v4)(__int64, const unsigned __int16 *, __int64 *); // rbx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, unsigned __int64); // rbx
  unsigned __int64 v7; // rax
  int v8; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v12; // [rsp+30h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  v3 = *((_QWORD *)this + 6);
  v4 = *(int (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v3 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  if ( v4(v3, a2, &v12) >= 0 )
  {
    v5 = v12;
    v6 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v12 + 56LL);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v7 = wil::FileTime::ToInt64(
           (wil::FileTime *)&SystemTimeAsFileTime,
           *(const struct _FILETIME **)&SystemTimeAsFileTime);
    v8 = v6(v5, v7);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xC6,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)(unsigned int)v8,
        v10);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return 0;
}

```

## disassembly

```asm
0x180013c28  mov     r11, rsp
0x180013c2b  mov     [r11+10h], rbx
0x180013c2f  mov     [r11+20h], rsi
0x180013c33  push    rdi; int
0x180013c34  sub     rsp, 20h
0x180013c38  mov     rsi, rdx
0x180013c3b  mov     qword ptr [r11+8], 0
0x180013c43  mov     rdi, [rcx+30h]
0x180013c47  mov     rax, [rdi]
0x180013c4a  mov     rbx, [rax+28h]
0x180013c4e  lea     rcx, [r11+8]
0x180013c52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c57  lea     r8, [rsp+28h+arg_0]
0x180013c5c  mov     rdx, rsi
0x180013c5f  mov     rcx, rdi
0x180013c62  mov     rax, rbx
0x180013c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c6a  test    eax, eax
0x180013c6c  js      short loc_180013CCE
0x180013c6e  mov     rdi, [rsp+28h+arg_0]
0x180013c73  mov     rax, [rdi]
0x180013c76  mov     rbx, [rax+38h]
0x180013c7a  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180013c83  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013c88  call    cs:__imp_GetSystemTimeAsFileTime
0x180013c8e  mov     rdx, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME *
0x180013c93  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], rdx
0x180013c98  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; this
0x180013c9d  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x180013ca2  mov     rdx, rax
0x180013ca5  mov     rcx, rdi
0x180013ca8  mov     rax, rbx
0x180013cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cb0  mov     rcx, [rsp+28h]; this
0x180013cb5  test    eax, eax
0x180013cb7  jns     short loc_180013CCE
0x180013cb9  mov     r9d, eax; char *
0x180013cbc  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180013cc3  mov     edx, 0C6h; void *
0x180013cc8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180013cce  lea     rcx, [rsp+28h+arg_0]
0x180013cd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013cd8  xor     eax, eax
0x180013cda  mov     rbx, [rsp+28h+arg_8]
0x180013cdf  mov     rsi, [rsp+28h+arg_18]
0x180013ce4  add     rsp, 20h
0x180013ce8  pop     rdi
0x180013ce9  retn
```
