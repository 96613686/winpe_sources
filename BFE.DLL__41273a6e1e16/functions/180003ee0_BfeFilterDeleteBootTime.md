# BfeFilterDeleteBootTime

- ea: `0x180003ee0`
- end: `0x180004068`
- name: `BfeFilterDeleteBootTime`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180003ee0`
- `0x180004070`
- `0x1800048a8`
- `0x180005238`
- `0x180012d8c`
- `0x1800197d0`
- `0x18005aa60`
- `0x18006944c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003fa0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003fa0`

## string_xrefs

- `0x180004026`: `BfeFilterDeleteBootTime`
- `0x180004006`: `RegDeleteValueW`
- `0x180004017`: `BfeRegDeleteValue`

## pseudocode

```c
__int64 __fastcall BfeFilterDeleteBootTime(unsigned int **a1, HKEY a2)
{
  unsigned int *v2; // r9
  __int64 v3; // rbx
  unsigned int v6; // eax
  __int64 v7; // rcx
  wchar_t pszDest[40]; // [rsp+70h] [rbp-88h] BYREF

  v3 = 0;
  if ( ((*a1)[8] & 2) != 0 )
  {
    v2 = *a1;
    StringCchPrintfW(
      pszDest,
      0x27u,
      L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
      *v2,
      *((unsigned __int16 *)v2 + 2),
      *((unsigned __int16 *)v2 + 3),
      *((unsigned __int8 *)v2 + 8),
      *((unsigned __int8 *)v2 + 9),
      *((unsigned __int8 *)v2 + 10),
      *((unsigned __int8 *)v2 + 11),
      *((unsigned __int8 *)v2 + 12),
      *((unsigned __int8 *)v2 + 13),
      *((unsigned __int8 *)v2 + 14),
      *((unsigned __int8 *)v2 + 15));
    BfeCallGetSysTxn();
    v3 = 0;
    v6 = RegDeleteValueW(a2, pszDest);
    if ( (v6 & 0xFFFFFFFD) != 0 )
      v3 = WfpReportSysErrorAsWinError(v7, "RegDeleteValueW", v6);
    BfeRegCloseKey(0);
    if ( v3 )
    {
      WfpReportError(v3, "BfeRegDeleteValue");
      WfpReportError(v3, "BfeFilterDeleteBootTime");
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF__guid__guid_I(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        *((_QWORD *)*a1 + 22),
        (unsigned int)*a1,
        (__int64)(*a1 + 16));
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180003ee0  mov     [rsp+arg_10], rbx
0x180003ee5  push    rbp
0x180003ee6  push    rsi
0x180003ee7  push    rdi
0x180003ee8  push    r14
0x180003eea  push    r15
0x180003eec  sub     rsp, 0D0h
0x180003ef3  mov     rax, cs:__security_cookie
0x180003efa  xor     rax, rsp
0x180003efd  mov     [rsp+0F8h+var_38], rax
0x180003f05  mov     r9, [rcx]
0x180003f08  xor     ebx, ebx
0x180003f0a  mov     r15, rdx
0x180003f0d  mov     r14, rcx
0x180003f10  test    byte ptr [r9+20h], 2
0x180003f15  jz      loc_180003FD8
0x180003f1b  movzx   ecx, byte ptr [r9+0Eh]
0x180003f20  movzx   edx, byte ptr [r9+0Dh]
0x180003f25  movzx   r8d, byte ptr [r9+0Ch]
0x180003f2a  movzx   eax, byte ptr [r9+0Fh]
0x180003f2f  movzx   r10d, byte ptr [r9+0Bh]
0x180003f34  movzx   r11d, byte ptr [r9+0Ah]
0x180003f39  movzx   ebx, byte ptr [r9+9]
0x180003f3e  movzx   edi, byte ptr [r9+8]
0x180003f43  movzx   esi, word ptr [r9+6]
0x180003f48  movzx   ebp, word ptr [r9+4]
0x180003f4d  mov     r9d, [r9]
0x180003f50  mov     [rsp+0F8h+var_90], eax
0x180003f54  mov     [rsp+0F8h+var_98], ecx
0x180003f58  lea     rcx, [rsp+0F8h+pszDest]; pszDest
0x180003f5d  mov     [rsp+0F8h+var_A0], edx
0x180003f61  mov     edx, 27h ; '''; cchDest
0x180003f66  mov     [rsp+0F8h+var_A8], r8d
0x180003f6b  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180003f72  mov     [rsp+0F8h+var_B0], r10d
0x180003f77  mov     [rsp+0F8h+var_B8], r11d
0x180003f7c  mov     [rsp+0F8h+var_C0], ebx
0x180003f80  mov     [rsp+0F8h+var_C8], edi
0x180003f84  mov     dword ptr [rsp+0F8h+var_D0], esi
0x180003f88  mov     dword ptr [rsp+0F8h+var_D8], ebp
0x180003f8c  call    StringCchPrintfW
0x180003f91  call    BfeCallGetSysTxn
0x180003f96  lea     rdx, [rsp+0F8h+pszDest]; lpValueName
0x180003f9b  mov     rcx, r15; hKey
0x180003f9e  xor     ebx, ebx
0x180003fa0  call    cs:__imp_RegDeleteValueW
0x180003fa7  nop     dword ptr [rax+rax+00h]
0x180003fac  test    eax, 0FFFFFFFDh
0x180003fb1  jnz     short loc_180004003
0x180003fb3  xor     ecx, ecx
0x180003fb5  call    BfeRegCloseKey
0x180003fba  test    rbx, rbx
0x180003fbd  jnz     short loc_180004017
0x180003fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fc6  lea     rax, WPP_GLOBAL_Control
0x180003fcd  cmp     rcx, rax
0x180003fd0  jz      short loc_180003FD8
0x180003fd2  cmp     byte ptr [rcx+19h], 4
0x180003fd6  jnb     short loc_180004037
0x180003fd8  mov     rax, rbx
0x180003fdb  mov     rcx, [rsp+0F8h+var_38]
0x180003fe3  xor     rcx, rsp; StackCookie
0x180003fe6  call    __security_check_cookie
0x180003feb  mov     rbx, [rsp+0F8h+arg_10]
0x180003ff3  add     rsp, 0D0h
0x180003ffa  pop     r15
0x180003ffc  pop     r14
0x180003ffe  pop     rdi
0x180003fff  pop     rsi
0x180004000  pop     rbp
0x180004001  retn
0x180004003  mov     r8d, eax
0x180004006  lea     rdx, aRegdeletevalue; "RegDeleteValueW"
0x18000400d  call    WfpReportSysErrorAsWinError
0x180004012  mov     rbx, rax
0x180004015  jmp     short loc_180003FB3
0x180004017  lea     rdx, aBferegdeleteva; "BfeRegDeleteValue"
0x18000401e  mov     rcx, rbx
0x180004021  call    WfpReportError
0x180004026  lea     rdx, aBfefilterdelet; "BfeFilterDeleteBootTime"
0x18000402d  mov     rcx, rbx
0x180004030  call    WfpReportError
0x180004035  jmp     short loc_180003FD8
0x180004037  test    byte ptr [rcx+1Ch], 2
0x18000403b  jz      short loc_180003FD8
0x18000403d  mov     r9, [r14]
0x180004040  mov     edx, 18h
0x180004045  mov     rcx, [rcx+10h]
0x180004049  mov     r8, [r9+0B0h]
0x180004050  lea     r10, [r9+40h]
0x180004054  mov     [rsp+0F8h+var_D0], r8
0x180004059  mov     [rsp+0F8h+var_D8], r10
0x18000405e  call    WPP_SF__guid__guid_I
0x180004063  jmp     loc_180003FD8
```
