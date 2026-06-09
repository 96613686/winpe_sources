# GetProcessName(void *)

- ea: `0x180022dec`
- end: `0x180022e89`
- name: `?GetProcessName@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800125fc`
- `0x180013530`
- `0x18001b10c`

## callees

- `0x180003ab0`
- `0x180011fb0`
- `0x180022a74`
- `0x180022dec`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x180022e4d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x180022e4d`
- `api-ms-win-core-psapi-ansi-l1-1-0!QueryFullProcessImageNameA` at `0x180022e3e`
- `api-ms-win-core-psapi-ansi-l1-1-0!QueryFullProcessImageNameA` at `0x180022e3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetProcessName(__int64 a1)
{
  HANDLE v2; // r10
  LPSTR FileNameA; // rax
  __int64 v4; // r8
  DWORD dwSize; // [rsp+24h] [rbp-134h] BYREF
  __int64 v7; // [rsp+28h] [rbp-130h]
  CHAR ExeName[272]; // [rsp+30h] [rbp-128h] BYREF

  v7 = a1;
  std::string::string(a1);
  dwSize = 260;
  if ( QueryFullProcessImageNameA(v2, 0, ExeName, &dwSize) )
  {
    FileNameA = PathFindFileNameA(ExeName);
    v4 = -1;
    do
      ++v4;
    while ( FileNameA[v4] );
    std::string::_Append<char>(a1, FileNameA);
  }
  return a1;
}

```

## disassembly

```asm
0x180022dec  push    rbx
0x180022dee  sub     rsp, 150h
0x180022df5  mov     rax, cs:__security_cookie
0x180022dfc  xor     rax, rsp
0x180022dff  mov     [rsp+158h+var_18], rax
0x180022e07  mov     r10, rdx
0x180022e0a  mov     rbx, rcx
0x180022e0d  mov     [rsp+158h+var_130], rcx
0x180022e12  mov     [rsp+158h+var_138], 0
0x180022e1a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180022e1f  mov     [rsp+158h+var_138], 1
0x180022e27  mov     [rsp+158h+dwSize], 104h
0x180022e2f  lea     r9, [rsp+158h+dwSize]; lpdwSize
0x180022e34  lea     r8, [rsp+158h+ExeName]; lpExeName
0x180022e39  xor     edx, edx; dwFlags
0x180022e3b  mov     rcx, r10; hProcess
0x180022e3e  call    cs:__imp_QueryFullProcessImageNameA
0x180022e44  test    eax, eax
0x180022e46  jz      short loc_180022E6C
0x180022e48  lea     rcx, [rsp+158h+ExeName]; pszPath
0x180022e4d  call    cs:__imp_PathFindFileNameA
0x180022e53  or      r8, 0FFFFFFFFFFFFFFFFh
0x180022e57  inc     r8
0x180022e5a  cmp     byte ptr [rax+r8], 0
0x180022e5f  jnz     short loc_180022E57
0x180022e61  mov     rdx, rax
0x180022e64  mov     rcx, rbx
0x180022e67  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180022e6c  mov     rax, rbx
0x180022e6f  mov     rcx, [rsp+158h+var_18]
0x180022e77  xor     rcx, rsp; StackCookie
0x180022e7a  call    __security_check_cookie
0x180022e7f  add     rsp, 150h
0x180022e86  pop     rbx
0x180022e87  retn
```
