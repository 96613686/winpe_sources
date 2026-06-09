# SdbpGetPathAppPatch

- ea: `0x140040970`
- end: `0x140040a56`
- name: `SdbpGetPathAppPatch`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1400052f0`
- `0x140005470`
- `0x14002d5c0`
- `0x14002d6a0`

## callees

- `0x1400079f0`
- `0x14003e364`
- `0x1400403cc`
- `0x140040970`
- `0x140040a5c`

## string_xrefs

- `0x140040a32`: `AslPathToSystemPathBuf failed [%x]`
- `0x140040a23`: `AslPathCombine failed [%x]`
- `0x140040a3f`: `SdbpGetPathAppPatch`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppPatch(_WORD *a1, unsigned __int64 a2, const wchar_t *a3)
{
  const wchar_t *v3; // r10
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  wchar_t pszSrc[16]; // [rsp+30h] [rbp-258h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-238h] BYREF

  v3 = a3;
  wcscpy(pszSrc, L"\\AppPatch");
  if ( a2 < 0xA )
    return 3221225507LL;
  *a1 = 0;
  pszDest[0] = 0;
  if ( !a3 )
    v3 = &::pszSrc;
  v7 = AslPathCombine(pszSrc, v3, pszDest, 0x104u);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = "AslPathCombine failed [%x]";
    v10 = 953;
LABEL_10:
    AslLogCallPrintf(1, "SdbpGetPathAppPatch", v10, v9, v7);
    return v8;
  }
  v7 = AslPathToSystemPathBuf(a1, a2, pszDest);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = "AslPathToSystemPathBuf failed [%x]";
    v10 = 959;
    goto LABEL_10;
  }
  return v8;
}

```

## disassembly

```asm
0x140040970  push    rbx
0x140040972  push    rsi
0x140040973  push    rdi
0x140040974  sub     rsp, 270h
0x14004097b  mov     rax, cs:__security_cookie
0x140040982  xor     rax, rsp
0x140040985  mov     [rsp+288h+var_28], rax
0x14004098d  mov     eax, dword ptr cs:aApppatch_0+10h; "h"
0x140040993  mov     r10, r8
0x140040996  mov     [rsp+288h+var_248], eax
0x14004099a  mov     rsi, rdx
0x14004099d  mov     rdi, rcx
0x1400409a0  movups  xmm0, xmmword ptr cs:aApppatch_0; "\\AppPatch"
0x1400409a7  movups  xmmword ptr [rsp+288h+pszSrc], xmm0
0x1400409ac  cmp     rdx, 0Ah
0x1400409b0  jnb     short loc_1400409D3
0x1400409b2  mov     eax, 0C0000023h
0x1400409b7  mov     rcx, [rsp+288h+var_28]
0x1400409bf  xor     rcx, rsp; StackCookie
0x1400409c2  call    __security_check_cookie
0x1400409c7  add     rsp, 270h
0x1400409ce  pop     rdi
0x1400409cf  pop     rsi
0x1400409d0  pop     rbx
0x1400409d1  retn
0x1400409d3  xor     eax, eax
0x1400409d5  lea     r8, [rsp+288h+pszDest]; pszDest
0x1400409da  mov     [rcx], ax
0x1400409dd  test    r10, r10
0x1400409e0  mov     [rsp+288h+pszDest], ax
0x1400409e5  lea     rcx, [rsp+288h+pszSrc]; pszSrc
0x1400409ea  lea     rax, pszSrc
0x1400409f1  mov     r9d, 104h; cchDest
0x1400409f7  cmovz   r10, rax
0x1400409fb  mov     rdx, r10; NTSTRSAFE_PCWSTR
0x1400409fe  call    AslPathCombine
0x140040a03  mov     ebx, eax
0x140040a05  test    eax, eax
0x140040a07  js      short loc_140040A23
0x140040a09  lea     r8, [rsp+288h+pszDest]
0x140040a0e  mov     rdx, rsi
0x140040a11  mov     rcx, rdi
0x140040a14  call    AslPathToSystemPathBuf
0x140040a19  mov     ebx, eax
0x140040a1b  test    eax, eax
0x140040a1d  js      short loc_140040A32
0x140040a1f  mov     eax, ebx
0x140040a21  jmp     short loc_1400409B7
0x140040a23  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140040a2a  mov     r8d, 3B9h
0x140040a30  jmp     short loc_140040A3F
0x140040a32  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x140040a39  mov     r8d, 3BFh
0x140040a3f  lea     rdx, aSdbpgetpathapp_0; "SdbpGetPathAppPatch"
0x140040a46  mov     [rsp+288h+var_268], eax
0x140040a4a  mov     ecx, 1
0x140040a4f  call    AslLogCallPrintf
0x140040a54  jmp     short loc_140040A1F
```
