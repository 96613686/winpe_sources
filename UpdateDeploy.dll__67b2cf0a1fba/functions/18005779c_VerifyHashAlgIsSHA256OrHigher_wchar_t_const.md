# VerifyHashAlgIsSHA256OrHigher(wchar_t const *)

- ea: `0x18005779c`
- end: `0x1800578fe`
- name: `?VerifyHashAlgIsSHA256OrHigher@@YAJPEB_W@Z`
- size: `354`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180055eec`

## callees

- `0x180003180`
- `0x1800084d8`
- `0x18000dc1c`
- `0x1800110fc`
- `0x18005779c`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005783e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005786b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057894`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005783e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005786b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057894`

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
      lpString2 = 0;
      WUTrace(0, 0, 32, 1);
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
  SusFreePtrArray((void **)lpMem, (unsigned int)v8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005779c  mov     r11, rsp
0x18005779f  mov     [r11+10h], rbx
0x1800577a3  push    rsi
0x1800577a4  sub     rsp, 60h
0x1800577a8  mov     rax, cs:__security_cookie
0x1800577af  xor     rax, rsp
0x1800577b2  mov     [rsp+68h+var_18], rax
0x1800577b7  lea     r9, [r11-20h]; unsigned int *
0x1800577bb  mov     qword ptr [r11-28h], 0
0x1800577c3  lea     r8, [r11-28h]; wchar_t ***
0x1800577c7  mov     dword ptr [rsp+68h+var_20], 0
0x1800577cf  call    ?StringArrayFromDelimitedString@@YAJPEB_W_WPEAPEAPEA_WPEAK@Z; StringArrayFromDelimitedString(wchar_t const *,wchar_t,wchar_t * * *,ulong *)
0x1800577d4  mov     ebx, eax
0x1800577d6  test    eax, eax
0x1800577d8  jns     short loc_1800577E1
0x1800577da  mov     edx, 0E93h
0x1800577df  jmp     short loc_1800577F2
0x1800577e1  cmp     dword ptr [rsp+68h+var_20], 2
0x1800577e6  jz      short loc_18005780B
0x1800577e8  mov     edx, 0E95h; void *
0x1800577ed  mov     ebx, 8024B303h
0x1800577f2  mov     rcx, [rsp+68h]; this
0x1800577f7  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x1800577fe  mov     r9d, ebx; char *
0x180057801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057806  jmp     loc_1800578D6
0x18005780b  mov     rax, [rsp+68h+lpMem]
0x180057810  lea     r8, aSha256; "SHA256"
0x180057817  mov     rbx, [rax+8]
0x18005781b  cmp     r8, rbx
0x18005781e  jz      loc_1800578D4
0x180057824  test    rbx, rbx
0x180057827  jz      short loc_18005789F
0x180057829  or      esi, 0FFFFFFFFh
0x18005782c  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180057830  mov     r9d, esi; cchCount1
0x180057833  mov     [rsp+68h+lpString2], rbx; lpString2
0x180057838  lea     edx, [rsi+2]; dwCmpFlags
0x18005783b  lea     ecx, [rdx+7Eh]; Locale
0x18005783e  call    cs:__imp_CompareStringW
0x180057844  cmp     eax, 2
0x180057847  jz      loc_1800578D4
0x18005784d  lea     r8, aSha384; "SHA384"
0x180057854  cmp     r8, rbx
0x180057857  jz      short loc_1800578D4
0x180057859  lea     edx, [rsi+2]; dwCmpFlags
0x18005785c  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180057860  lea     ecx, [rdx+7Eh]; Locale
0x180057863  mov     [rsp+68h+lpString2], rbx; lpString2
0x180057868  mov     r9d, esi; cchCount1
0x18005786b  call    cs:__imp_CompareStringW
0x180057871  cmp     eax, 2
0x180057874  jz      short loc_1800578D4
0x180057876  lea     r8, aSha512; "SHA512"
0x18005787d  cmp     r8, rbx
0x180057880  jz      short loc_1800578D4
0x180057882  lea     edx, [rsi+2]; dwCmpFlags
0x180057885  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180057889  lea     ecx, [rdx+7Eh]; Locale
0x18005788c  mov     [rsp+68h+lpString2], rbx; lpString2
0x180057891  mov     r9d, esi; cchCount1
0x180057894  call    cs:__imp_CompareStringW
0x18005789a  cmp     eax, 2
0x18005789d  jz      short loc_1800578D4
0x18005789f  xor     edx, edx
0x1800578a1  mov     [rsp+68h+var_38], rbx
0x1800578a6  lea     rax, aHashAlgorithmI; "Hash Algorithm is lesser than SHA256. A"...
0x1800578ad  xor     ecx, ecx
0x1800578af  mov     qword ptr [rsp+68h+cchCount2], rax
0x1800578b4  mov     [rsp+68h+lpString2], 0
0x1800578bd  lea     r9d, [rdx+1]
0x1800578c1  lea     r8d, [rdx+20h]
0x1800578c5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800578ca  mov     edx, 0E9Fh
0x1800578cf  jmp     loc_1800577ED
0x1800578d4  xor     ebx, ebx
0x1800578d6  mov     edx, dword ptr [rsp+68h+var_20]; unsigned __int64
0x1800578da  mov     rcx, [rsp+68h+lpMem]; lpMem
0x1800578df  call    ?SusFreePtrArray@@YAXPEAX_K@Z; SusFreePtrArray(void *,unsigned __int64)
0x1800578e4  mov     eax, ebx
0x1800578e6  mov     rcx, [rsp+68h+var_18]
0x1800578eb  xor     rcx, rsp; StackCookie
0x1800578ee  call    __security_check_cookie
0x1800578f3  mov     rbx, [rsp+68h+arg_8]
0x1800578f8  add     rsp, 60h
0x1800578fc  pop     rsi
0x1800578fd  retn
```
