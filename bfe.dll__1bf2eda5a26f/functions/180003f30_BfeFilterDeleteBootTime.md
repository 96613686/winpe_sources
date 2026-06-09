# BfeFilterDeleteBootTime

- ea: `0x180003f30`
- end: `0x1800040a5`
- name: `BfeFilterDeleteBootTime`
- size: `373`
- prototype: `__int64 __fastcall(unsigned int **, HKEY)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180003f30`
- `0x180004850`
- `0x1800049f8`
- `0x18001236c`
- `0x180018b74`
- `0x180058b30`
- `0x180066f44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003ff0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003ff0`

## string_xrefs

- `0x180004000`: `RegDeleteValueW`
- `0x180004066`: `BfeFilterDeleteBootTime`
- `0x180004057`: `BfeRegDeleteValue`

## pseudocode

```c
__int64 __fastcall BfeFilterDeleteBootTime(unsigned int **a1, HKEY a2)
{
  unsigned int *v2; // r9
  __int64 v3; // rbx
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rax
  int v10; // [rsp+20h] [rbp-D8h]
  int v11; // [rsp+28h] [rbp-D0h]
  int v12; // [rsp+30h] [rbp-C8h]
  int v13; // [rsp+38h] [rbp-C0h]
  int v14; // [rsp+40h] [rbp-B8h]
  int v15; // [rsp+48h] [rbp-B0h]
  int v16; // [rsp+50h] [rbp-A8h]
  int v17; // [rsp+58h] [rbp-A0h]
  int v18; // [rsp+60h] [rbp-98h]
  int v19; // [rsp+68h] [rbp-90h]
  wchar_t pszDest[40]; // [rsp+70h] [rbp-88h] BYREF

  v2 = *a1;
  v3 = 0;
  if ( ((*a1)[8] & 2) != 0 )
  {
    v19 = *((unsigned __int8 *)v2 + 15);
    v18 = *((unsigned __int8 *)v2 + 14);
    v17 = *((unsigned __int8 *)v2 + 13);
    v16 = *((unsigned __int8 *)v2 + 12);
    v15 = *((unsigned __int8 *)v2 + 11);
    v14 = *((unsigned __int8 *)v2 + 10);
    v13 = *((unsigned __int8 *)v2 + 9);
    v12 = *((unsigned __int8 *)v2 + 8);
    v11 = *((unsigned __int16 *)v2 + 3);
    v10 = *((unsigned __int16 *)v2 + 2);
    StringCchPrintfW(
      pszDest,
      0x27u,
      L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
      *v2,
      v10,
      v11,
      v12,
      v13,
      v14,
      v15,
      v16,
      v17,
      v18,
      v19);
    BfeCallGetSysTxn();
    v3 = 0;
    v6 = RegDeleteValueW(a2, pszDest);
    if ( (v6 & 0xFFFFFFFD) != 0 && (v8 = WfpReportSysErrorAsWinError(v7, "RegDeleteValueW", v6), (v3 = v8) != 0) )
    {
      WfpReportError(v8, "BfeRegDeleteValue");
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
0x180003f30  mov     [rsp+arg_10], rbx
0x180003f35  push    rbp
0x180003f36  push    rsi
0x180003f37  push    rdi
0x180003f38  push    r14
0x180003f3a  push    r15
0x180003f3c  sub     rsp, 0D0h
0x180003f43  mov     rax, cs:__security_cookie
0x180003f4a  xor     rax, rsp
0x180003f4d  mov     [rsp+0F8h+var_38], rax
0x180003f55  mov     r9, [rcx]
0x180003f58  xor     ebx, ebx
0x180003f5a  mov     r15, rdx
0x180003f5d  mov     r14, rcx
0x180003f60  test    byte ptr [r9+20h], 2
0x180003f65  jz      loc_18000402D
0x180003f6b  movzx   ecx, byte ptr [r9+0Eh]
0x180003f70  movzx   edx, byte ptr [r9+0Dh]
0x180003f75  movzx   r8d, byte ptr [r9+0Ch]
0x180003f7a  movzx   eax, byte ptr [r9+0Fh]
0x180003f7f  movzx   r10d, byte ptr [r9+0Bh]
0x180003f84  movzx   r11d, byte ptr [r9+0Ah]
0x180003f89  movzx   ebx, byte ptr [r9+9]
0x180003f8e  movzx   edi, byte ptr [r9+8]
0x180003f93  movzx   esi, word ptr [r9+6]
0x180003f98  movzx   ebp, word ptr [r9+4]
0x180003f9d  mov     r9d, [r9]
0x180003fa0  mov     [rsp+0F8h+var_90], eax
0x180003fa4  mov     [rsp+0F8h+var_98], ecx
0x180003fa8  lea     rcx, [rsp+0F8h+pszDest]; pszDest
0x180003fad  mov     [rsp+0F8h+var_A0], edx
0x180003fb1  mov     edx, 27h ; '''; cchDest
0x180003fb6  mov     [rsp+0F8h+var_A8], r8d
0x180003fbb  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180003fc2  mov     [rsp+0F8h+var_B0], r10d
0x180003fc7  mov     [rsp+0F8h+var_B8], r11d
0x180003fcc  mov     [rsp+0F8h+var_C0], ebx
0x180003fd0  mov     [rsp+0F8h+var_C8], edi
0x180003fd4  mov     dword ptr [rsp+0F8h+var_D0], esi
0x180003fd8  mov     dword ptr [rsp+0F8h+var_D8], ebp
0x180003fdc  call    StringCchPrintfW
0x180003fe1  call    BfeCallGetSysTxn
0x180003fe6  lea     rdx, [rsp+0F8h+pszDest]; lpValueName
0x180003feb  mov     rcx, r15; hKey
0x180003fee  xor     ebx, ebx
0x180003ff0  call    cs:__imp_RegDeleteValueW
0x180003ff6  test    eax, 0FFFFFFFDh
0x180003ffb  jz      short loc_180004014
0x180003ffd  mov     r8d, eax
0x180004000  lea     rdx, aRegdeletevalue; "RegDeleteValueW"
0x180004007  call    WfpReportSysErrorAsWinError
0x18000400c  mov     rbx, rax
0x18000400f  test    rax, rax
0x180004012  jnz     short loc_180004057
0x180004014  mov     rcx, cs:WPP_GLOBAL_Control
0x18000401b  lea     rax, WPP_GLOBAL_Control
0x180004022  cmp     rcx, rax
0x180004025  jz      short loc_18000402D
0x180004027  cmp     byte ptr [rcx+19h], 4
0x18000402b  jnb     short loc_180004077
0x18000402d  mov     rax, rbx
0x180004030  mov     rcx, [rsp+0F8h+var_38]
0x180004038  xor     rcx, rsp; StackCookie
0x18000403b  call    __security_check_cookie
0x180004040  mov     rbx, [rsp+0F8h+arg_10]
0x180004048  add     rsp, 0D0h
0x18000404f  pop     r15
0x180004051  pop     r14
0x180004053  pop     rdi
0x180004054  pop     rsi
0x180004055  pop     rbp
0x180004056  retn
0x180004057  lea     rdx, aBferegdeleteva; "BfeRegDeleteValue"
0x18000405e  mov     rcx, rbx
0x180004061  call    WfpReportError
0x180004066  lea     rdx, aBfefilterdelet; "BfeFilterDeleteBootTime"
0x18000406d  mov     rcx, rbx
0x180004070  call    WfpReportError
0x180004075  jmp     short loc_18000402D
0x180004077  test    byte ptr [rcx+1Ch], 2
0x18000407b  jz      short loc_18000402D
0x18000407d  mov     r9, [r14]
0x180004080  mov     edx, 18h
0x180004085  mov     rcx, [rcx+10h]
0x180004089  mov     r8, [r9+0B0h]
0x180004090  lea     r10, [r9+40h]
0x180004094  mov     [rsp+0F8h+var_D0], r8
0x180004099  mov     [rsp+0F8h+var_D8], r10
0x18000409e  call    WPP_SF__guid__guid_I
0x1800040a3  jmp     short loc_18000402D
```
