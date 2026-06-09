# CLockAction::IsDefaultLockApp(void)

- ea: `0x18008d6bc`
- end: `0x18008d831`
- name: `?IsDefaultLockApp@CLockAction@@AEAA_NXZ`
- size: `373`
- prototype: `bool __fastcall(CLockAction *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d448`

## callees

- `0x180008094`
- `0x18000ba40`
- `0x18000baa4`
- `0x180033480`
- `0x18008ab5c`
- `0x18008d6bc`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18008d82a`
- `KERNEL32!RaiseException` at `0x18008d82a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18008d6f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18008d6f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d74c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d7a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d74c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d7a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008d76f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008d76f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008d729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008d7fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008d729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008d7fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CLockAction::IsDefaultLockApp(HSTRING *this)
{
  HRESULT v2; // eax
  const WCHAR *StringRawBuffer; // rax
  unsigned int v4; // eax
  HKEY v5; // rbx
  char v6; // di
  const unsigned __int16 *v7; // rax
  int LockAppAndAppType; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  if ( !dword_1800D3F0C )
  {
    LODWORD(hKey) = 0;
    v2 = WindowsCompareStringOrdinal(this[31], 0, (INT32 *)&hKey);
    if ( v2 < 0 )
    {
      RaiseException(v2, 1u, 0, 0);
      JUMPOUT(0x18008D830LL);
    }
    if ( (_DWORD)hKey )
    {
      hKey = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(this[31], 0);
      v4 = RegOpenKeyExW(HKEY_USERS, StringRawBuffer, 0, 1u, &hKey);
      if ( v4 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x58E,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)v4,
          phkResult);
      }
      else
      {
        v5 = hKey;
        v6 = *((_BYTE *)this + 260);
        v7 = WindowsGetStringRawBuffer(this[31], 0);
        LockAppAndAppType = GetLockAppAndAppType(v7, v6, v5, 0, (enum LockAppType *)&dword_1800D3F0C, 0);
        if ( LockAppAndAppType < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x590,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
            (const char *)(unsigned int)LockAppAndAppType,
            phkResulta);
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  return dword_1800D3F0C == 1;
}

```

## disassembly

```asm
0x18008d6bc  mov     rax, rsp
0x18008d6bf  mov     [rax+8], rbx
0x18008d6c3  mov     [rax+20h], rsi
0x18008d6c7  push    rdi
0x18008d6c8  sub     rsp, 30h
0x18008d6cc  mov     rsi, rcx
0x18008d6cf  cmp     cs:dword_1800D3F0C, 0
0x18008d6d6  jnz     loc_18008D804
0x18008d6dc  mov     dword ptr [rax+10h], 0
0x18008d6e3  lea     r8, [rax+10h]; result
0x18008d6e7  xor     edx, edx; string2
0x18008d6e9  mov     rcx, [rcx+0F8h]; string1
0x18008d6f0  call    cs:__imp_WindowsCompareStringOrdinal
0x18008d6f6  test    eax, eax
0x18008d6f8  js      loc_18008D81E
0x18008d6fe  cmp     dword ptr [rsp+38h+hKey], 0
0x18008d703  jz      loc_18008D804
0x18008d709  mov     [rsp+38h+hKey], 0
0x18008d712  mov     rbx, [rsp+38h+hKey]
0x18008d717  test    rbx, rbx
0x18008d71a  jz      short loc_18008D73A
0x18008d71c  lea     rcx, [rsp+38h+arg_10]; this
0x18008d721  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008d726  mov     rcx, rbx; hKey
0x18008d729  call    cs:__imp_RegCloseKey
0x18008d72f  lea     rcx, [rsp+38h+arg_10]; this
0x18008d734  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18008d739  nop
0x18008d73a  mov     [rsp+38h+hKey], 0
0x18008d743  xor     edx, edx; length
0x18008d745  mov     rcx, [rsi+0F8h]; string
0x18008d74c  call    cs:__imp_WindowsGetStringRawBuffer
0x18008d752  lea     rcx, [rsp+38h+hKey]
0x18008d757  mov     [rsp+38h+phkResult], rcx; unsigned int
0x18008d75c  mov     r9d, 1; samDesired
0x18008d762  xor     r8d, r8d; ulOptions
0x18008d765  mov     rdx, rax; lpSubKey
0x18008d768  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18008d76f  call    cs:__imp_RegOpenKeyExW
0x18008d775  mov     rcx, [rsp+38h]; this
0x18008d77a  test    eax, eax
0x18008d77c  jz      short loc_18008D794
0x18008d77e  mov     r9d, eax; char *
0x18008d781  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18008d788  mov     edx, 58Eh; void *
0x18008d78d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18008d792  jmp     short loc_18008D7F3
0x18008d794  mov     rbx, [rsp+38h+hKey]
0x18008d799  mov     dil, [rsi+104h]
0x18008d7a0  xor     edx, edx; length
0x18008d7a2  mov     rcx, [rsi+0F8h]; string
0x18008d7a9  call    cs:__imp_WindowsGetStringRawBuffer
0x18008d7af  mov     [rsp+38h+var_10], 0; unsigned __int16 **
0x18008d7b8  lea     rcx, dword_1800D3F0C
0x18008d7bf  mov     [rsp+38h+phkResult], rcx; int
0x18008d7c4  xor     r9d, r9d; bool
0x18008d7c7  mov     r8, rbx; HKEY
0x18008d7ca  mov     dl, dil; bool
0x18008d7cd  mov     rcx, rax; unsigned __int16 *
0x18008d7d0  call    ?GetLockAppAndAppType@@YAJPEBG_NPEAUHKEY__@@1PEAW4LockAppType@@PEAPEAG@Z; GetLockAppAndAppType(ushort const *,bool,HKEY__ *,bool,LockAppType *,ushort * *)
0x18008d7d5  mov     rcx, [rsp+38h]; this
0x18008d7da  test    eax, eax
0x18008d7dc  jns     short loc_18008D7F3
0x18008d7de  mov     r9d, eax; char *
0x18008d7e1  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18008d7e8  mov     edx, 590h; void *
0x18008d7ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008d7f2  nop
0x18008d7f3  mov     rcx, [rsp+38h+hKey]; hKey
0x18008d7f8  test    rcx, rcx
0x18008d7fb  jz      short loc_18008D804
0x18008d7fd  call    cs:__imp_RegCloseKey
0x18008d803  nop
0x18008d804  cmp     cs:dword_1800D3F0C, 1
0x18008d80b  setz    al
0x18008d80e  mov     rbx, [rsp+38h+arg_0]
0x18008d813  mov     rsi, [rsp+38h+arg_18]
0x18008d818  add     rsp, 30h
0x18008d81c  pop     rdi
0x18008d81d  retn
0x18008d81e  xor     r9d, r9d; lpArguments
0x18008d821  xor     r8d, r8d; nNumberOfArguments
0x18008d824  lea     edx, [r9+1]; dwExceptionFlags
0x18008d828  mov     ecx, eax; dwExceptionCode
0x18008d82a  call    cs:__imp_RaiseException
```
