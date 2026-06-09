# SniffAndConvertToWideString(char const *,int *,ushort * *)

- ea: `0x18004a994`
- end: `0x18004aad2`
- name: `?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z`
- size: `318`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004a828`
- `0x18004ff44`

## callees

- `0x18004a994`
- `0x18004aad8`
- `0x18004ab28`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa5a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004aa1f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004aa1f`

## pseudocode

```c
__int64 __fastcall SniffAndConvertToWideString(LPCCH lpMultiByteStr, int *a2, unsigned __int16 **a3)
{
  unsigned int v3; // ebx
  int v7; // eax
  int cchWideChar; // r14d
  int v9; // r9d
  int v11; // ecx
  signed int LastError; // eax
  int v13; // [rsp+60h] [rbp+8h] BYREF
  UINT CodePage; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h]

  v3 = 0;
  *a3 = 0;
  v13 = 0;
  CodePage = 0;
  if ( !lpMultiByteStr )
    return v3;
  v7 = DetectStringCodePageAndMaxLength(lpMultiByteStr, a2, &CodePage, &v13);
  v3 = v7;
  if ( v7 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_14;
    goto LABEL_12;
  }
  cchWideChar = v13;
  v15 = 0;
  if ( !is_mul_ok(v13, 2u) )
  {
    v3 = -2147024362;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_14;
    v11 = -2147024362;
    goto LABEL_13;
  }
  v7 = CoTaskMemAllocWithInit(2LL * v13, (void **)a3);
  v3 = v7;
  if ( v7 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_14;
LABEL_12:
    v11 = v7;
LABEL_13:
    DoStackCapture(v11);
    goto LABEL_14;
  }
  if ( a2 )
    v9 = *a2;
  else
    v9 = -1;
  if ( MultiByteToWideChar(CodePage, 0, lpMultiByteStr, v9, *a3, cchWideChar) )
  {
LABEL_8:
    if ( (v3 & 0x80000000) == 0 )
      return v3;
LABEL_14:
    CoTaskMemFree(*a3);
    *a3 = 0;
    return v3;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v3);
    goto LABEL_8;
  }
  return v3;
}

```

## disassembly

```asm
0x18004a994  mov     rax, rsp
0x18004a997  push    rbx
0x18004a998  push    rbp
0x18004a999  push    rsi
0x18004a99a  push    rdi
0x18004a99b  push    r14
0x18004a99d  sub     rsp, 30h
0x18004a9a1  xor     ebx, ebx
0x18004a9a3  mov     rdi, r8
0x18004a9a6  mov     [r8], rbx
0x18004a9a9  mov     rsi, rdx
0x18004a9ac  mov     [rax+8], ebx
0x18004a9af  mov     rbp, rcx
0x18004a9b2  mov     [rax+18h], ebx
0x18004a9b5  test    rcx, rcx
0x18004a9b8  jz      short loc_18004AA33
0x18004a9ba  lea     r9, [rax+8]; int *
0x18004a9be  lea     r8, [rax+18h]; unsigned int *
0x18004a9c2  call    ?DetectStringCodePageAndMaxLength@@YAJPEBDPEAHPEAI1@Z; DetectStringCodePageAndMaxLength(char const *,int *,uint *,int *)
0x18004a9c7  mov     ebx, eax
0x18004a9c9  test    eax, eax
0x18004a9cb  js      loc_18004AA6F
0x18004a9d1  movsxd  r14, [rsp+58h+arg_0]
0x18004a9d6  mov     eax, 2
0x18004a9db  mul     r14
0x18004a9de  mov     [rsp+58h+arg_18], 0
0x18004a9e7  test    rdx, rdx
0x18004a9ea  jnz     loc_18004AA7A
0x18004a9f0  mov     rdx, rdi; void **
0x18004a9f3  mov     rcx, rax; Size
0x18004a9f6  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18004a9fb  mov     ebx, eax
0x18004a9fd  test    eax, eax
0x18004a9ff  js      short loc_18004AA47
0x18004aa01  mov     rax, [rdi]
0x18004aa04  test    rsi, rsi
0x18004aa07  jz      short loc_18004AA41
0x18004aa09  mov     r9d, [rsi]; cbMultiByte
0x18004aa0c  mov     ecx, [rsp+58h+CodePage]; CodePage
0x18004aa10  mov     r8, rbp; lpMultiByteStr
0x18004aa13  mov     [rsp+58h+cchWideChar], r14d; cchWideChar
0x18004aa18  xor     edx, edx; dwFlags
0x18004aa1a  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x18004aa1f  call    cs:__imp_MultiByteToWideChar
0x18004aa26  nop     dword ptr [rax+rax+00h]
0x18004aa2b  test    eax, eax
0x18004aa2d  jz      short loc_18004AA96
0x18004aa2f  test    ebx, ebx
0x18004aa31  js      short loc_18004AA57
0x18004aa33  mov     eax, ebx
0x18004aa35  add     rsp, 30h
0x18004aa39  pop     r14
0x18004aa3b  pop     rdi
0x18004aa3c  pop     rsi
0x18004aa3d  pop     rbp
0x18004aa3e  pop     rbx
0x18004aa3f  retn
0x18004aa41  or      r9d, 0FFFFFFFFh
0x18004aa45  jmp     short loc_18004AA0C
0x18004aa47  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004aa4e  jz      short loc_18004AA8C
0x18004aa50  mov     ecx, eax; int
0x18004aa52  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004aa57  mov     rcx, [rdi]; pv
0x18004aa5a  call    cs:__imp_CoTaskMemFree
0x18004aa61  nop     dword ptr [rax+rax+00h]
0x18004aa66  mov     qword ptr [rdi], 0
0x18004aa6d  jmp     short loc_18004AA33
0x18004aa6f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004aa76  jnz     short loc_18004AA50
0x18004aa78  jmp     short loc_18004AA57
0x18004aa7a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004aa81  mov     ebx, 80070216h
0x18004aa86  jz      short loc_18004AA57
0x18004aa88  mov     ecx, ebx
0x18004aa8a  jmp     short loc_18004AA52
0x18004aa8c  test    eax, eax
0x18004aa8e  jns     loc_18004AA01
0x18004aa94  jmp     short loc_18004AA57
0x18004aa96  call    cs:__imp_GetLastError
0x18004aa9d  nop     dword ptr [rax+rax+00h]
0x18004aaa2  mov     ebx, eax
0x18004aaa4  test    eax, eax
0x18004aaa6  jle     short loc_18004AAB1
0x18004aaa8  movzx   ebx, ax
0x18004aaab  or      ebx, 80070000h
0x18004aab1  test    ebx, ebx
0x18004aab3  jns     loc_18004AA33
0x18004aab9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004aac0  jz      loc_18004AA2F
0x18004aac6  mov     ecx, ebx; int
0x18004aac8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004aacd  jmp     loc_18004AA2F
```
