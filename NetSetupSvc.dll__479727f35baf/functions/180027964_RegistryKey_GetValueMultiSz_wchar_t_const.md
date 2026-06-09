# RegistryKey::GetValueMultiSz(wchar_t const *)

- ea: `0x180027964`
- end: `0x180027a4a`
- name: `?GetValueMultiSz@RegistryKey@@QEBA?AVMultiSz@@PEB_W@Z`
- size: `230`
- prototype: `__int64 __fastcall(HKEY *, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002789c`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008854`
- `0x18000d974`
- `0x18002498c`
- `0x18002729c`
- `0x180027964`
- `0x180029e78`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetValueMultiSz(HKEY *a1, __int64 a2, const WCHAR *a3)
{
  int v3; // edi
  _DWORD v6[4]; // [rsp+30h] [rbp-108h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-F8h] BYREF
  _QWORD v8[3]; // [rsp+110h] [rbp-28h] BYREF

  v3 = (int)a3;
  v6[1] = HIDWORD(a2);
  v6[0] = 0;
  RegistryKey::GetValueBlob(a1, v8, a3, v6, 0);
  if ( v6[0] != 7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
        v3,
        v6[0]);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147023267);
    throw (HResultException *)pExceptionObject;
  }
  MultiSz::MultiSz(a2, v8);
  std::vector<unsigned char>::_Tidy((__int64)v8);
  return a2;
}

```

## disassembly

```asm
0x180027964  mov     r11, rsp
0x180027967  mov     [r11+20h], rbx
0x18002796b  push    rdi
0x18002796c  sub     rsp, 130h
0x180027973  mov     rax, cs:__security_cookie
0x18002797a  xor     rax, rsp
0x18002797d  mov     [rsp+138h+var_10], rax
0x180027985  mov     rdi, r8
0x180027988  mov     rbx, rdx
0x18002798b  mov     [rsp+138h+var_108], rdx
0x180027990  xor     eax, eax
0x180027992  mov     dword ptr [rsp+138h+var_108], eax
0x180027996  mov     [rsp+138h+var_118], eax
0x18002799a  lea     r9, [rsp+138h+var_108]
0x18002799f  lea     rdx, [r11-28h]
0x1800279a3  call    ?GetValueBlob@RegistryKey@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAKW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBlob(wchar_t const *,ulong *,RegistryKey::MissingValueDisposition)
0x1800279a8  nop
0x1800279a9  mov     eax, dword ptr [rsp+138h+var_108]
0x1800279ad  cmp     eax, 7
0x1800279b0  jz      short loc_180027A08
0x1800279b2  lea     rdx, WPP_GLOBAL_Control
0x1800279b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279c0  cmp     rcx, rdx
0x1800279c3  jz      short loc_1800279E7
0x1800279c5  cmp     byte ptr [rcx+19h], 2
0x1800279c9  jb      short loc_1800279E7
0x1800279cb  mov     edx, 23h ; '#'
0x1800279d0  mov     [rsp+138h+var_118], eax
0x1800279d4  mov     r9, rdi
0x1800279d7  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x1800279de  mov     rcx, [rcx+10h]
0x1800279e2  call    WPP_SF_Sd
0x1800279e7  mov     edx, 8007065Dh; int
0x1800279ec  lea     rcx, [rsp+138h+pExceptionObject]; this
0x1800279f1  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800279f6  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800279fd  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180027a02  call    _CxxThrowException_0
0x180027a08  lea     rdx, [rsp+138h+var_28]
0x180027a10  mov     rcx, rbx
0x180027a13  call    ??0MultiSz@@QEAA@$$QEAV?$vector@EV?$allocator@E@std@@@std@@@Z; MultiSz::MultiSz(std::vector<uchar> &&)
0x180027a18  nop
0x180027a19  lea     rcx, [rsp+138h+var_28]
0x180027a21  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180027a26  mov     rax, rbx
0x180027a29  mov     rcx, [rsp+138h+var_10]
0x180027a31  xor     rcx, rsp; StackCookie
0x180027a34  call    __security_check_cookie
0x180027a39  mov     rbx, [rsp+138h+arg_18]
0x180027a41  add     rsp, 130h
0x180027a48  pop     rdi
0x180027a49  retn
```
