# SdbpGetPathCustomSdbPreRS3

- ea: `0x140005470`
- end: `0x1400055cd`
- name: `SdbpGetPathCustomSdbPreRS3`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x140005470`
- `0x1400079f0`
- `0x14002d830`
- `0x14003e364`
- `0x140040970`
- `0x140040a5c`

## string_xrefs

- `0x140005587`: `AslPathCombine failed [%x]`
- `0x14000552f`: `SdbpGetPathCustomSdbPreRS3`

## pseudocode

```c
__int64 __fastcall SdbpGetPathCustomSdbPreRS3(_WORD *a1, unsigned __int64 a2, const wchar_t *a3, __int64 a4)
{
  int ProcessHostGuestArchitectures; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  wchar_t *v12; // rcx
  int v13; // [rsp+20h] [rbp-E0h]
  __int16 v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v15; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h]
  wchar_t v18; // [rsp+44h] [rbp-BCh]
  wchar_t pszSrc[20]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t pszDest[264]; // [rsp+70h] [rbp-90h] BYREF

  v16 = *(_QWORD *)L"Custom";
  v17 = *(_DWORD *)L"om";
  v18 = aCustom[6];
  wcscpy(pszSrc, L"Custom\\Custom64");
  if ( a2 < 7 )
    return 3221225507LL;
  *a1 = 0;
  pszDest[0] = 0;
  v15 = -1;
  v14[0] = -1;
  ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v15, v14, a4);
  v9 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures >= 0 )
  {
    if ( v14[0] == 9 || (v12 = (wchar_t *)&v16, v14[0] == 12) )
      v12 = pszSrc;
    if ( !a3 )
      a3 = &::pszSrc;
    ProcessHostGuestArchitectures = AslPathCombine(v12, a3, pszDest, 0x104u);
    v9 = ProcessHostGuestArchitectures;
    if ( ProcessHostGuestArchitectures >= 0 )
      return (unsigned int)SdbpGetPathAppPatch(a1, a2, pszDest);
    v10 = "AslPathCombine failed [%x]";
    v11 = 1253;
  }
  else
  {
    v10 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
    v11 = 1239;
  }
  v13 = ProcessHostGuestArchitectures;
  AslLogCallPrintf(1, "SdbpGetPathCustomSdbPreRS3", v11, v10, v13);
  return v9;
}

```

## disassembly

```asm
0x140005470  push    rbp
0x140005472  push    rbx
0x140005473  push    rsi
0x140005474  push    rdi
0x140005475  push    r14
0x140005477  push    r15
0x140005479  lea     rbp, [rsp-198h]
0x140005481  sub     rsp, 298h
0x140005488  mov     rax, cs:__security_cookie
0x14000548f  xor     rax, rsp
0x140005492  mov     [rbp+1C0h+var_40], rax
0x140005499  movsd   xmm0, qword ptr cs:aCustom; "Custom"
0x1400054a1  mov     r14, r9
0x1400054a4  mov     eax, dword ptr cs:aCustom+8; "om"
0x1400054aa  mov     rdi, r8
0x1400054ad  movsd   [rsp+2C0h+var_288], xmm0
0x1400054b3  mov     r15, rdx
0x1400054b6  mov     [rsp+2C0h+var_280], eax
0x1400054ba  mov     rsi, rcx
0x1400054bd  movzx   eax, word ptr cs:aCustom+0Ch; ""
0x1400054c4  mov     [rsp+2C0h+var_27C], ax
0x1400054c9  movups  xmm0, xmmword ptr cs:aCustomCustom64; "Custom\\Custom64"
0x1400054d0  movups  xmm1, xmmword ptr cs:aCustomCustom64+10h; "ustom64"
0x1400054d7  movups  xmmword ptr [rsp+2C0h+pszSrc], xmm0
0x1400054dc  movups  [rsp+2C0h+var_268], xmm1
0x1400054e1  cmp     rdx, 7
0x1400054e5  jnb     short loc_1400054F1
0x1400054e7  mov     eax, 0C0000023h
0x1400054ec  jmp     loc_1400055AD
0x1400054f1  xor     eax, eax
0x1400054f3  lea     rdx, [rsp+2C0h+var_290]
0x1400054f8  mov     [rcx], ax
0x1400054fb  mov     r8, r14
0x1400054fe  mov     [rsp+2C0h+pszDest], ax
0x140005503  lea     rcx, [rsp+2C0h+var_28C]
0x140005508  mov     eax, 0FFFFh
0x14000550d  mov     [rsp+2C0h+var_28C], ax
0x140005512  mov     [rsp+2C0h+var_290], ax
0x140005517  call    SdbpGetProcessHostGuestArchitectures
0x14000551c  mov     ebx, eax
0x14000551e  test    eax, eax
0x140005520  jns     short loc_140005546
0x140005522  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x140005529  mov     r8d, 4D7h
0x14000552f  lea     rdx, aSdbpgetpathcus_0; "SdbpGetPathCustomSdbPreRS3"
0x140005536  mov     [rsp+2C0h+var_2A0], eax
0x14000553a  mov     ecx, 1
0x14000553f  call    AslLogCallPrintf
0x140005544  jmp     short loc_1400055AB
0x140005546  cmp     [rsp+2C0h+var_290], 9
0x14000554c  jz      short loc_14000555B
0x14000554e  cmp     [rsp+2C0h+var_290], 0Ch
0x140005554  lea     rcx, [rsp+2C0h+var_288]
0x140005559  jnz     short loc_140005560
0x14000555b  lea     rcx, [rsp+2C0h+pszSrc]; pszSrc
0x140005560  lea     rax, pszSrc
0x140005567  test    rdi, rdi
0x14000556a  mov     r9d, 104h; cchDest
0x140005570  lea     r8, [rsp+2C0h+pszDest]; pszDest
0x140005575  cmovz   rdi, rax
0x140005579  mov     rdx, rdi; NTSTRSAFE_PCWSTR
0x14000557c  call    AslPathCombine
0x140005581  mov     ebx, eax
0x140005583  test    eax, eax
0x140005585  jns     short loc_140005596
0x140005587  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14000558e  mov     r8d, 4E5h
0x140005594  jmp     short loc_14000552F
0x140005596  mov     r9, r14
0x140005599  lea     r8, [rsp+2C0h+pszDest]
0x14000559e  mov     rdx, r15
0x1400055a1  mov     rcx, rsi
0x1400055a4  call    SdbpGetPathAppPatch
0x1400055a9  mov     ebx, eax
0x1400055ab  mov     eax, ebx
0x1400055ad  mov     rcx, [rbp+1C0h+var_40]
0x1400055b4  xor     rcx, rsp; StackCookie
0x1400055b7  call    __security_check_cookie
0x1400055bc  add     rsp, 298h
0x1400055c3  pop     r15
0x1400055c5  pop     r14
0x1400055c7  pop     rdi
0x1400055c8  pop     rsi
0x1400055c9  pop     rbx
0x1400055ca  pop     rbp
0x1400055cb  retn
```
