# MakeLogFileName

- ea: `0x180025db4`
- end: `0x180025e7e`
- name: `MakeLogFileName`
- size: `202`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180025ad4`
- `0x1800260a4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180006214`
- `0x1800078f8`
- `0x180008854`
- `0x1800182b0`
- `0x180025db4`

## string_xrefs

- `0x180025de4`: `service.%u.etl`

## pseudocode

```c
__int64 __fastcall MakeLogFileName(__int64 a1, __int64 a2, unsigned int a3)
{
  int v4; // edi
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-108h] BYREF
  wchar_t v7[16]; // [rsp+100h] [rbp-38h] BYREF

  v4 = StringCchPrintfW(v7, 0xEu, L"service.%u.etl", a3);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_4a7bb80c34923429700e535c78fe3875_Traceguids,
        (unsigned int)v4);
    HResultException::HResultException((HResultException *)pExceptionObject, v4);
    throw (HResultException *)pExceptionObject;
  }
  std::wstring::wstring(a1, v7);
  return a1;
}

```

## disassembly

```asm
0x180025db4  mov     r11, rsp
0x180025db7  mov     [r11+10h], rbx
0x180025dbb  push    rdi
0x180025dbc  sub     rsp, 130h
0x180025dc3  mov     rax, cs:__security_cookie
0x180025dca  xor     rax, rsp
0x180025dcd  mov     [rsp+138h+var_18], rax
0x180025dd5  mov     rbx, rcx
0x180025dd8  mov     [rsp+138h+var_110], rcx
0x180025ddd  mov     r9d, r8d
0x180025de0  lea     rcx, [r11-38h]; wchar_t *
0x180025de4  lea     r8, aServiceUEtl; "service.%u.etl"
0x180025deb  mov     edx, 0Eh; unsigned __int64
0x180025df0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180025df5  mov     edi, eax
0x180025df7  test    eax, eax
0x180025df9  jns     short loc_180025E4A
0x180025dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e02  lea     rax, WPP_GLOBAL_Control
0x180025e09  cmp     rcx, rax
0x180025e0c  jz      short loc_180025E2C
0x180025e0e  cmp     byte ptr [rcx+19h], 2
0x180025e12  jb      short loc_180025E2C
0x180025e14  mov     rcx, [rcx+10h]
0x180025e18  lea     r8, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids
0x180025e1f  mov     edx, 0Ah
0x180025e24  mov     r9d, edi
0x180025e27  call    WPP_SF_d
0x180025e2c  mov     edx, edi; int
0x180025e2e  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180025e33  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180025e38  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180025e3f  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180025e44  call    _CxxThrowException_0
0x180025e4a  lea     rdx, [rsp+138h+var_38]
0x180025e52  mov     rcx, rbx
0x180025e55  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180025e5a  mov     rax, rbx
0x180025e5d  mov     rcx, [rsp+138h+var_18]
0x180025e65  xor     rcx, rsp; StackCookie
0x180025e68  call    __security_check_cookie
0x180025e6d  mov     rbx, [rsp+138h+arg_8]
0x180025e75  add     rsp, 130h
0x180025e7c  pop     rdi
0x180025e7d  retn
```
