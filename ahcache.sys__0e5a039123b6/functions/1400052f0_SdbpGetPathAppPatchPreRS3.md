# SdbpGetPathAppPatchPreRS3

- ea: `0x1400052f0`
- end: `0x14000545e`
- name: `SdbpGetPathAppPatchPreRS3`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x1400012f0`
- `0x1400052f0`
- `0x1400079f0`
- `0x14002d830`
- `0x14003e364`
- `0x140040970`
- `0x140040a5c`

## string_xrefs

- `0x140005415`: `AslPathCombine failed [%x]`
- `0x14000538a`: `SdbpGetPathAppPatchPreRS3`
- `0x1400053da`: `RtlStringCchCopyW failed to copy FileName [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppPatchPreRS3(_WORD *a1, unsigned __int64 a2, const wchar_t *a3, __int64 a4)
{
  NTSTATUS ProcessHostGuestArchitectures; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  NTSTATUS v12; // [rsp+20h] [rbp-E0h]
  __int16 v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v14; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t pszSrc[12]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF

  wcscpy(pszSrc, L"AppPath64");
  if ( a2 < 0xB )
    return 3221225507LL;
  pszDest[0] = 0;
  v14 = -1;
  v13[0] = -1;
  ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v14, v13, a4);
  v9 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures >= 0 )
  {
    if ( v13[0] == 9 || v13[0] == 12 )
    {
      if ( !a3 )
        a3 = &::pszSrc;
      ProcessHostGuestArchitectures = AslPathCombine(pszSrc, a3, pszDest, 0x104u);
      v9 = ProcessHostGuestArchitectures;
      if ( ProcessHostGuestArchitectures < 0 )
      {
        v10 = "AslPathCombine failed [%x]";
        v11 = 1018;
        goto LABEL_5;
      }
    }
    else
    {
      if ( !a3 )
        a3 = &::pszSrc;
      ProcessHostGuestArchitectures = RtlStringCchCopyW(pszDest, 0x104u, a3);
      v9 = ProcessHostGuestArchitectures;
      if ( ProcessHostGuestArchitectures < 0 )
      {
        v10 = "RtlStringCchCopyW failed to copy FileName [%x]";
        v11 = 1024;
        goto LABEL_5;
      }
    }
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, pszDest);
  }
  v10 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
  v11 = 1006;
LABEL_5:
  v12 = ProcessHostGuestArchitectures;
  AslLogCallPrintf(1, "SdbpGetPathAppPatchPreRS3", v11, v10, v12);
  return v9;
}

```

## disassembly

```asm
0x1400052f0  push    rbp
0x1400052f2  push    rbx
0x1400052f3  push    rsi
0x1400052f4  push    rdi
0x1400052f5  push    r14
0x1400052f7  push    r15
0x1400052f9  lea     rbp, [rsp-178h]
0x140005301  sub     rsp, 278h
0x140005308  mov     rax, cs:__security_cookie
0x14000530f  xor     rax, rsp
0x140005312  mov     [rbp+1A0h+var_40], rax
0x140005319  movsd   xmm1, qword ptr cs:aApppatch64+0Eh; "h64"
0x140005321  mov     rsi, r9
0x140005324  mov     rdi, r8
0x140005327  mov     r14, rdx
0x14000532a  mov     r15, rcx
0x14000532d  movups  xmm0, xmmword ptr cs:aApppatch64; "AppPatch64"
0x140005334  movups  xmmword ptr [rsp+2A0h+pszSrc], xmm0
0x140005339  movsd   qword ptr [rsp+2A0h+pszSrc+0Eh], xmm1
0x14000533f  cmp     rdx, 0Bh
0x140005343  jnb     short loc_14000534F
0x140005345  mov     eax, 0C0000023h
0x14000534a  jmp     loc_14000543E
0x14000534f  xor     eax, eax
0x140005351  lea     rdx, [rsp+2A0h+var_270]
0x140005356  mov     [rsp+2A0h+pszDest], ax
0x14000535b  lea     rcx, [rsp+2A0h+var_26C]
0x140005360  mov     eax, 0FFFFh
0x140005365  mov     r8, rsi
0x140005368  mov     [rsp+2A0h+var_26C], ax
0x14000536d  mov     [rsp+2A0h+var_270], ax
0x140005372  call    SdbpGetProcessHostGuestArchitectures
0x140005377  mov     ebx, eax
0x140005379  test    eax, eax
0x14000537b  jns     short loc_1400053A4
0x14000537d  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x140005384  mov     r8d, 3EEh
0x14000538a  lea     rdx, aSdbpgetpathapp; "SdbpGetPathAppPatchPreRS3"
0x140005391  mov     [rsp+2A0h+var_280], eax
0x140005395  mov     ecx, 1
0x14000539a  call    AslLogCallPrintf
0x14000539f  jmp     loc_14000543C
0x1400053a4  cmp     [rsp+2A0h+var_270], 9
0x1400053aa  jz      short loc_1400053E9
0x1400053ac  cmp     [rsp+2A0h+var_270], 0Ch
0x1400053b2  jz      short loc_1400053E9
0x1400053b4  lea     rax, pszSrc
0x1400053bb  test    rdi, rdi
0x1400053be  mov     edx, 104h; cchDest
0x1400053c3  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1400053c8  cmovz   rdi, rax
0x1400053cc  mov     r8, rdi; pszSrc
0x1400053cf  call    RtlStringCchCopyW
0x1400053d4  mov     ebx, eax
0x1400053d6  test    eax, eax
0x1400053d8  jns     short loc_140005427
0x1400053da  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed to copy FileNa"...
0x1400053e1  mov     r8d, 400h
0x1400053e7  jmp     short loc_14000538A
0x1400053e9  lea     rax, pszSrc
0x1400053f0  test    rdi, rdi
0x1400053f3  mov     r9d, 104h; cchDest
0x1400053f9  lea     r8, [rsp+2A0h+pszDest]; pszDest
0x1400053fe  cmovz   rdi, rax
0x140005402  lea     rcx, [rsp+2A0h+pszSrc]; pszSrc
0x140005407  mov     rdx, rdi; NTSTRSAFE_PCWSTR
0x14000540a  call    AslPathCombine
0x14000540f  mov     ebx, eax
0x140005411  test    eax, eax
0x140005413  jns     short loc_140005427
0x140005415  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14000541c  mov     r8d, 3FAh
0x140005422  jmp     loc_14000538A
0x140005427  mov     r9, rsi
0x14000542a  lea     r8, [rsp+2A0h+pszDest]
0x14000542f  mov     rdx, r14
0x140005432  mov     rcx, r15
0x140005435  call    SdbpGetPathAppPatch
0x14000543a  mov     ebx, eax
0x14000543c  mov     eax, ebx
0x14000543e  mov     rcx, [rbp+1A0h+var_40]
0x140005445  xor     rcx, rsp; StackCookie
0x140005448  call    __security_check_cookie
0x14000544d  add     rsp, 278h
0x140005454  pop     r15
0x140005456  pop     r14
0x140005458  pop     rdi
0x140005459  pop     rsi
0x14000545a  pop     rbx
0x14000545b  pop     rbp
0x14000545c  retn
```
