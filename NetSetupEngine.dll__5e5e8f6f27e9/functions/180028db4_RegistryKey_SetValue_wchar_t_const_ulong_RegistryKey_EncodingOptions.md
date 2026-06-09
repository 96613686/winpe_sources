# RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)

- ea: `0x180028db4`
- end: `0x180028eb6`
- name: `?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001c010`
- `0x18001f3ec`
- `0x180028c28`
- `0x180029bb0`
- `0x18002a0a0`
- `0x180041334`
- `0x1800418b4`
- `0x180042444`
- `0x180052d50`
- `0x180052f18`
- `0x18005e3d8`
- `0x18005e670`
- `0x18005ea10`
- `0x18006a7d8`
- `0x18006a958`
- `0x180076a30`
- `0x18007cc20`

## callees

- `0x180028db4`
- `0x180052698`
- `0x180052cc4`
- `0x180065035`
- `0x18007f840`
- `0x18007fc44`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028e4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028e4c`

## pseudocode

```c
void __fastcall RegistryKey::SetValue(RegistryKey *a1, const wchar_t *a2, int a3, int a4)
{
  LSTATUS v6; // ebx
  BYTE pExceptionObject[208]; // [rsp+30h] [rbp-128h] BYREF
  BYTE Data[8]; // [rsp+100h] [rbp-58h] BYREF
  wchar_t v9[32]; // [rsp+108h] [rbp-50h] BYREF

  *(_DWORD *)Data = a3;
  if ( a4 )
  {
    if ( a4 == 1 )
    {
      swprintf_s<30>(v9, L"%u");
      RegistryKey::SetValue(a1, a2, v9);
    }
  }
  else
  {
    v6 = RegSetValueExW(*(HKEY *)a1, a2, 0, 4u, Data, 4u);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (_DWORD)a2,
          Data[0],
          v6);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
      throw (Win32Exception *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180028db4  mov     r11, rsp
0x180028db7  mov     [r11+20h], rbx
0x180028dbb  push    rdi
0x180028dbc  sub     rsp, 150h
0x180028dc3  mov     rax, cs:__security_cookie
0x180028dca  xor     rax, rsp
0x180028dcd  mov     [rsp+158h+var_10], rax
0x180028dd5  mov     [r11-58h], r8d
0x180028dd9  mov     rdi, rdx
0x180028ddc  mov     rbx, rcx
0x180028ddf  test    r9d, r9d
0x180028de2  jz      short loc_180028E2E
0x180028de4  cmp     r9d, 1
0x180028de8  jnz     short loc_180028E0D
0x180028dea  lea     rdx, aU; "%u"
0x180028df1  lea     rcx, [r11-50h]
0x180028df5  call    ??$swprintf_s@$0BO@@@YAHAEAY0BO@_WPEB_WZZ; swprintf_s<30>(wchar_t (&)[30],wchar_t const *,...)
0x180028dfa  lea     r8, [rsp+158h+var_50]; wchar_t *
0x180028e02  mov     rdx, rdi; wchar_t *
0x180028e05  mov     rcx, rbx; this
0x180028e08  call    ?SetValue@RegistryKey@@QEBAXPEB_W0@Z; RegistryKey::SetValue(wchar_t const *,wchar_t const *)
0x180028e0d  mov     rcx, [rsp+158h+var_10]
0x180028e15  xor     rcx, rsp; StackCookie
0x180028e18  call    __security_check_cookie
0x180028e1d  mov     rbx, [rsp+158h+arg_18]
0x180028e25  add     rsp, 150h
0x180028e2c  pop     rdi
0x180028e2d  retn
0x180028e2e  mov     rcx, [rcx]; hKey
0x180028e31  lea     rax, [rsp+158h+Data]
0x180028e39  mov     r9d, 4; dwType
0x180028e3f  xor     r8d, r8d; Reserved
0x180028e42  mov     [rsp+158h+cbData], r9d; cbData
0x180028e47  mov     [rsp+158h+lpData], rax; lpData
0x180028e4c  call    cs:__imp_RegSetValueExW
0x180028e52  mov     ebx, eax
0x180028e54  test    eax, eax
0x180028e56  jz      short loc_180028E0D
0x180028e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e5f  lea     rax, WPP_GLOBAL_Control
0x180028e66  cmp     rcx, rax
0x180028e69  jz      short loc_180028E98
0x180028e6b  cmp     byte ptr [rcx+19h], 2
0x180028e6f  jb      short loc_180028E98
0x180028e71  mov     eax, dword ptr [rsp+158h+Data]
0x180028e78  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180028e7f  mov     rcx, [rcx+10h]
0x180028e83  mov     edx, 27h ; '''
0x180028e88  mov     [rsp+158h+cbData], ebx
0x180028e8c  mov     r9, rdi
0x180028e8f  mov     dword ptr [rsp+158h+lpData], eax
0x180028e93  call    WPP_SF_SDD
0x180028e98  mov     edx, ebx; int
0x180028e9a  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180028e9f  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180028ea4  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180028eab  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180028eb0  call    _CxxThrowException_0
```
