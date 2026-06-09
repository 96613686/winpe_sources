# WdipExpandVariables

- ea: `0x180008dd8`
- end: `0x180008e98`
- name: `WdipExpandVariables`
- size: `192`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, LPCWSTR lpSrc)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007d30`
- `0x180008474`
- `0x1800152c4`
- `0x180017040`

## callees

- `0x180008dd8`
- `0x180009090`
- `0x180009fb0`
- `0x18000bc1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e16`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008e0c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008e0c`

## string_xrefs

- `0x180008e6f`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`

## pseudocode

```c
__int64 __fastcall WdipExpandVariables(unsigned __int16 *a1, unsigned __int64 a2, LPCWSTR lpSrc)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  int v7; // r8d
  int v8; // eax
  char Args[4]; // [rsp+20h] [rbp-838h]
  WCHAR Dst[1024]; // [rsp+30h] [rbp-828h] BYREF

  if ( !ExpandEnvironmentStringsW(lpSrc, Dst, 0x400u) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (v6 & 0x80000000) != 0 )
    {
      v7 = 137;
      *(_DWORD *)Args = (unsigned __int16)v6;
LABEL_8:
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
        (__int64)L"WdipExpandVariables",
        v7,
        (const wchar_t *)L"Error = %d",
        *(_DWORD *)Args);
      return v6;
    }
  }
  v8 = StringCchCopyW(a1, a2, Dst);
  v6 = v8;
  if ( v8 < 0 )
  {
    v7 = 140;
    *(_DWORD *)Args = (unsigned __int16)v8;
    goto LABEL_8;
  }
  return v6;
}

```

## disassembly

```asm
0x180008dd8  push    rbx
0x180008dda  push    rsi
0x180008ddb  push    rdi
0x180008ddc  sub     rsp, 840h
0x180008de3  mov     rax, cs:__security_cookie
0x180008dea  xor     rax, rsp
0x180008ded  mov     [rsp+858h+var_28], rax
0x180008df5  mov     rax, r8
0x180008df8  mov     rsi, rdx
0x180008dfb  mov     rdi, rcx
0x180008dfe  lea     rdx, [rsp+858h+Dst]; lpDst
0x180008e03  mov     rcx, rax; lpSrc
0x180008e06  mov     r8d, 400h; nSize
0x180008e0c  call    cs:__imp_ExpandEnvironmentStringsW
0x180008e12  test    eax, eax
0x180008e14  jnz     short loc_180008E3E
0x180008e16  call    cs:__imp_GetLastError
0x180008e1c  mov     ebx, eax
0x180008e1e  test    eax, eax
0x180008e20  jle     short loc_180008E2B
0x180008e22  movzx   ebx, ax
0x180008e25  or      ebx, 80070000h
0x180008e2b  test    ebx, ebx
0x180008e2d  jns     short loc_180008E3E
0x180008e2f  movzx   eax, bx
0x180008e32  mov     r8d, 89h
0x180008e38  mov     dword ptr [rsp+858h+Args], eax
0x180008e3c  jmp     short loc_180008E61
0x180008e3e  lea     r8, [rsp+858h+Dst]; unsigned __int16 *
0x180008e43  mov     rdx, rsi; unsigned __int64
0x180008e46  mov     rcx, rdi; unsigned __int16 *
0x180008e49  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008e4e  mov     ebx, eax
0x180008e50  test    eax, eax
0x180008e52  jns     short loc_180008E7B
0x180008e54  movzx   ecx, ax
0x180008e57  mov     r8d, 8Ch; int
0x180008e5d  mov     dword ptr [rsp+858h+Args], ecx; Args
0x180008e61  lea     r9, aErrorD; "Error = %d"
0x180008e68  lea     rdx, aWdipexpandvari; "WdipExpandVariables"
0x180008e6f  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008e76  call    WdipTraceError
0x180008e7b  mov     eax, ebx
0x180008e7d  mov     rcx, [rsp+858h+var_28]
0x180008e85  xor     rcx, rsp; StackCookie
0x180008e88  call    __security_check_cookie
0x180008e8d  add     rsp, 840h
0x180008e94  pop     rdi
0x180008e95  pop     rsi
0x180008e96  pop     rbx
0x180008e97  retn
```
