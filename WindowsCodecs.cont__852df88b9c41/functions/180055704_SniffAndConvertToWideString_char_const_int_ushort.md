# SniffAndConvertToWideString(char const *,int *,ushort * *)

- ea: `0x180055704`
- end: `0x180055827`
- name: `?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z`
- size: `291`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800555a0`
- `0x1800aec68`

## callees

- `0x180055704`
- `0x180055830`
- `0x180055878`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800557bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800557bf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005578b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005578b`

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
0x180055704  mov     rax, rsp
0x180055707  push    rbx
0x180055708  push    rbp
0x180055709  push    rsi
0x18005570a  push    rdi
0x18005570b  push    r14
0x18005570d  sub     rsp, 30h
0x180055711  xor     ebx, ebx
0x180055713  mov     rdi, r8
0x180055716  mov     [r8], rbx
0x180055719  mov     rsi, rdx
0x18005571c  mov     [rax+8], ebx
0x18005571f  mov     rbp, rcx
0x180055722  mov     [rax+18h], ebx
0x180055725  test    rcx, rcx
0x180055728  jz      short loc_180055799
0x18005572a  lea     r9, [rax+8]; int *
0x18005572e  lea     r8, [rax+18h]; unsigned int *
0x180055732  call    ?DetectStringCodePageAndMaxLength@@YAJPEBDPEAHPEAI1@Z; DetectStringCodePageAndMaxLength(char const *,int *,uint *,int *)
0x180055737  mov     ebx, eax
0x180055739  test    eax, eax
0x18005573b  js      loc_1800557CE
0x180055741  movsxd  r14, [rsp+58h+arg_0]
0x180055746  mov     eax, 2
0x18005574b  mul     r14
0x18005574e  mov     [rsp+58h+arg_18], 0
0x180055757  test    rdx, rdx
0x18005575a  jnz     short loc_1800557D9
0x18005575c  mov     rdx, rdi; void **
0x18005575f  mov     rcx, rax; Size
0x180055762  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180055767  mov     ebx, eax
0x180055769  test    eax, eax
0x18005576b  js      short loc_1800557AC
0x18005576d  mov     rax, [rdi]
0x180055770  test    rsi, rsi
0x180055773  jz      short loc_1800557A6
0x180055775  mov     r9d, [rsi]; cbMultiByte
0x180055778  mov     ecx, [rsp+58h+CodePage]; CodePage
0x18005577c  mov     r8, rbp; lpMultiByteStr
0x18005577f  mov     [rsp+58h+cchWideChar], r14d; cchWideChar
0x180055784  xor     edx, edx; dwFlags
0x180055786  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x18005578b  call    cs:__imp_MultiByteToWideChar
0x180055791  test    eax, eax
0x180055793  jz      short loc_1800557F5
0x180055795  test    ebx, ebx
0x180055797  js      short loc_1800557BC
0x180055799  mov     eax, ebx
0x18005579b  add     rsp, 30h
0x18005579f  pop     r14
0x1800557a1  pop     rdi
0x1800557a2  pop     rsi
0x1800557a3  pop     rbp
0x1800557a4  pop     rbx
0x1800557a5  retn
0x1800557a6  or      r9d, 0FFFFFFFFh
0x1800557aa  jmp     short loc_180055778
0x1800557ac  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800557b3  jz      short loc_1800557EB
0x1800557b5  mov     ecx, eax; int
0x1800557b7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800557bc  mov     rcx, [rdi]; pv
0x1800557bf  call    cs:__imp_CoTaskMemFree
0x1800557c5  mov     qword ptr [rdi], 0
0x1800557cc  jmp     short loc_180055799
0x1800557ce  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800557d5  jnz     short loc_1800557B5
0x1800557d7  jmp     short loc_1800557BC
0x1800557d9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800557e0  mov     ebx, 80070216h
0x1800557e5  jz      short loc_1800557BC
0x1800557e7  mov     ecx, ebx
0x1800557e9  jmp     short loc_1800557B7
0x1800557eb  test    eax, eax
0x1800557ed  jns     loc_18005576D
0x1800557f3  jmp     short loc_1800557BC
0x1800557f5  call    cs:__imp_GetLastError
0x1800557fb  mov     ebx, eax
0x1800557fd  test    eax, eax
0x1800557ff  jle     short loc_18005580A
0x180055801  movzx   ebx, ax
0x180055804  or      ebx, 80070000h
0x18005580a  test    ebx, ebx
0x18005580c  jns     short loc_180055799
0x18005580e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180055815  jz      loc_180055795
0x18005581b  mov     ecx, ebx; int
0x18005581d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180055822  jmp     loc_180055795
```
