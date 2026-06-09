# VerifyHashAlgIsSHA256OrHigher(wchar_t const *)

- ea: `0x14002d58c`
- end: `0x14002d6ee`
- name: `?VerifyHashAlgIsSHA256OrHigher@@YAJPEB_W@Z`
- size: `354`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002b38c`

## callees

- `0x140008de4`
- `0x14000cd68`
- `0x14001104c`
- `0x1400154b4`
- `0x14002d58c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14002d62e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14002d65b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14002d684`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14002d62e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14002d65b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14002d684`

## pseudocode

```c
__int64 __fastcall VerifyHashAlgIsSHA256OrHigher(const wchar_t *a1, wchar_t a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  const WCHAR *v4; // rbx
  int lpString2; // [rsp+20h] [rbp-48h]
  void *lpMem; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v8; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  lpMem = 0;
  LODWORD(v8) = 0;
  v2 = StringArrayFromDelimitedString(a1, a2, (wchar_t ***)&lpMem, (unsigned int *)&v8);
  if ( v2 >= 0 )
  {
    if ( (_DWORD)v8 == 2 )
    {
      v4 = (const WCHAR *)*((_QWORD *)lpMem + 1);
      if ( L"SHA256" == v4
        || v4
        && (CompareStringW(0x7Fu, 1u, L"SHA256", -1, v4, -1) == 2
         || L"SHA384" == v4
         || CompareStringW(0x7Fu, 1u, L"SHA384", -1, v4, -1) == 2
         || L"SHA512" == v4
         || CompareStringW(0x7Fu, 1u, L"SHA512", -1, v4, -1) == 2) )
      {
        v2 = 0;
        goto LABEL_16;
      }
      WUTrace(0, 0, 32, 1, 0, L"Hash Algorithm is lesser than SHA256. Algorithm Used:%ws");
      v3 = 3743;
    }
    else
    {
      v3 = 3733;
    }
    v2 = -2145078525;
  }
  else
  {
    v3 = 3731;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\wutrust\\lib\\trust.cpp",
    (const char *)(unsigned int)v2,
    lpString2);
LABEL_16:
  SusFreePtrArray(lpMem, (unsigned int)v8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002d58c  mov     r11, rsp
0x14002d58f  mov     [r11+10h], rbx
0x14002d593  push    rsi
0x14002d594  sub     rsp, 60h
0x14002d598  mov     rax, cs:__security_cookie
0x14002d59f  xor     rax, rsp
0x14002d5a2  mov     [rsp+68h+var_18], rax
0x14002d5a7  lea     r9, [r11-20h]; unsigned int *
0x14002d5ab  mov     qword ptr [r11-28h], 0
0x14002d5b3  lea     r8, [r11-28h]; wchar_t ***
0x14002d5b7  mov     dword ptr [rsp+68h+var_20], 0
0x14002d5bf  call    ?StringArrayFromDelimitedString@@YAJPEB_W_WPEAPEAPEA_WPEAK@Z; StringArrayFromDelimitedString(wchar_t const *,wchar_t,wchar_t * * *,ulong *)
0x14002d5c4  mov     ebx, eax
0x14002d5c6  test    eax, eax
0x14002d5c8  jns     short loc_14002D5D1
0x14002d5ca  mov     edx, 0E93h
0x14002d5cf  jmp     short loc_14002D5E2
0x14002d5d1  cmp     dword ptr [rsp+68h+var_20], 2
0x14002d5d6  jz      short loc_14002D5FB
0x14002d5d8  mov     edx, 0E95h; void *
0x14002d5dd  mov     ebx, 8024B303h
0x14002d5e2  mov     rcx, [rsp+68h]; this
0x14002d5e7  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x14002d5ee  mov     r9d, ebx; char *
0x14002d5f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d5f6  jmp     loc_14002D6C6
0x14002d5fb  mov     rax, [rsp+68h+lpMem]
0x14002d600  lea     r8, aSha256; "SHA256"
0x14002d607  mov     rbx, [rax+8]
0x14002d60b  cmp     r8, rbx
0x14002d60e  jz      loc_14002D6C4
0x14002d614  test    rbx, rbx
0x14002d617  jz      short loc_14002D68F
0x14002d619  or      esi, 0FFFFFFFFh
0x14002d61c  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14002d620  mov     r9d, esi; cchCount1
0x14002d623  mov     [rsp+68h+lpString2], rbx; lpString2
0x14002d628  lea     edx, [rsi+2]; dwCmpFlags
0x14002d62b  lea     ecx, [rdx+7Eh]; Locale
0x14002d62e  call    cs:__imp_CompareStringW
0x14002d634  cmp     eax, 2
0x14002d637  jz      loc_14002D6C4
0x14002d63d  lea     r8, aSha384; "SHA384"
0x14002d644  cmp     r8, rbx
0x14002d647  jz      short loc_14002D6C4
0x14002d649  lea     edx, [rsi+2]; dwCmpFlags
0x14002d64c  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14002d650  lea     ecx, [rdx+7Eh]; Locale
0x14002d653  mov     [rsp+68h+lpString2], rbx; lpString2
0x14002d658  mov     r9d, esi; cchCount1
0x14002d65b  call    cs:__imp_CompareStringW
0x14002d661  cmp     eax, 2
0x14002d664  jz      short loc_14002D6C4
0x14002d666  lea     r8, aSha512; "SHA512"
0x14002d66d  cmp     r8, rbx
0x14002d670  jz      short loc_14002D6C4
0x14002d672  lea     edx, [rsi+2]; dwCmpFlags
0x14002d675  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14002d679  lea     ecx, [rdx+7Eh]; Locale
0x14002d67c  mov     [rsp+68h+lpString2], rbx; lpString2
0x14002d681  mov     r9d, esi; cchCount1
0x14002d684  call    cs:__imp_CompareStringW
0x14002d68a  cmp     eax, 2
0x14002d68d  jz      short loc_14002D6C4
0x14002d68f  xor     edx, edx
0x14002d691  mov     [rsp+68h+var_38], rbx
0x14002d696  lea     rax, aHashAlgorithmI; "Hash Algorithm is lesser than SHA256. A"...
0x14002d69d  xor     ecx, ecx
0x14002d69f  mov     qword ptr [rsp+68h+cchCount2], rax
0x14002d6a4  mov     [rsp+68h+lpString2], 0
0x14002d6ad  lea     r9d, [rdx+1]
0x14002d6b1  lea     r8d, [rdx+20h]
0x14002d6b5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002d6ba  mov     edx, 0E9Fh
0x14002d6bf  jmp     loc_14002D5DD
0x14002d6c4  xor     ebx, ebx
0x14002d6c6  mov     edx, dword ptr [rsp+68h+var_20]; unsigned __int64
0x14002d6ca  mov     rcx, [rsp+68h+lpMem]; lpMem
0x14002d6cf  call    ?SusFreePtrArray@@YAXPEAX_K@Z; SusFreePtrArray(void *,unsigned __int64)
0x14002d6d4  mov     eax, ebx
0x14002d6d6  mov     rcx, [rsp+68h+var_18]
0x14002d6db  xor     rcx, rsp; StackCookie
0x14002d6de  call    __security_check_cookie
0x14002d6e3  mov     rbx, [rsp+68h+arg_8]
0x14002d6e8  add     rsp, 60h
0x14002d6ec  pop     rsi
0x14002d6ed  retn
```
