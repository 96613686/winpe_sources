# GetConvertedTextForMatching(ulong,wchar_t const *,unsigned __int64,wchar_t *,unsigned __int64)

- ea: `0x18002910c`
- end: `0x180029269`
- name: `?GetConvertedTextForMatching@@YAJKPEB_W_KPEA_W1@Z`
- size: `349`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, unsigned __int64, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task`

## callers

- `0x180029570`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x180006844`
- `0x18002910c`
- `0x180029ed4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002917a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002917a`
- `api-ms-win-core-normalization-l1-1-0!NormalizeString` at `0x18002916e`
- `api-ms-win-core-normalization-l1-1-0!NormalizeString` at `0x18002916e`

## string_xrefs

- `0x180029219`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\languageutil.cpp`
- `0x180029235`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\languageutil.cpp`

## pseudocode

```c
__int64 __fastcall GetConvertedTextForMatching(__int64 a1, const wchar_t *a2, unsigned __int64 a3, wchar_t *a4)
{
  __int64 v7; // rsi
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rax
  WCHAR *v12; // rdx
  wchar_t *v13; // rcx
  wchar_t *v14; // rdx
  __int64 v15; // rdx
  int cwDstLength; // [rsp+20h] [rbp-838h]
  WCHAR DstString[1024]; // [rsp+30h] [rbp-828h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+858h] [rbp+0h]

  memset_0(DstString, 0, sizeof(DstString));
  if ( a3 > 0x7FFFFFFF )
  {
    v9 = -2147024809;
    v10 = 317;
    goto LABEL_19;
  }
  v7 = 1024;
  if ( NormalizeString(NormalizationC, a2, a3, DstString, 1024) <= 0 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      v10 = 323;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\languageutil.cpp",
        (const char *)v9,
        cwDstLength);
      v15 = 344;
      goto LABEL_20;
    }
  }
  v11 = 2147483646;
  v12 = DstString;
  v13 = a4;
  do
  {
    if ( !v11 )
      break;
    if ( !*v12 )
      break;
    *v13++ = *v12++;
    --v11;
    --v7;
  }
  while ( v7 );
  v14 = v13 - 1;
  v9 = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v14 = v13;
  *v14 = 0;
  if ( !v7 )
  {
    v15 = 350;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\languageutil.cpp",
      (const char *)v9,
      cwDstLength);
    return v9;
  }
  while ( *a4 )
    MapCharToBaseChar(a4++);
  return 0;
}

```

## disassembly

```asm
0x18002910c  mov     [rsp+arg_0], rbx
0x180029111  push    rbp
0x180029112  push    rsi
0x180029113  push    rdi
0x180029114  sub     rsp, 840h
0x18002911b  mov     rax, cs:__security_cookie
0x180029122  xor     rax, rsp
0x180029125  mov     [rsp+858h+var_28], rax
0x18002912d  mov     rbx, r8
0x180029130  lea     rcx, [rsp+858h+DstString]; void *
0x180029135  mov     rbp, rdx
0x180029138  mov     r8d, 800h; Size
0x18002913e  xor     edx, edx; Val
0x180029140  mov     rdi, r9
0x180029143  call    memset_0
0x180029148  cmp     rbx, 7FFFFFFFh
0x18002914f  ja      loc_180029207
0x180029155  mov     esi, 400h
0x18002915a  lea     r9, [rsp+858h+DstString]; lpDstString
0x18002915f  mov     r8d, ebx; cwSrcLength
0x180029162  mov     [rsp+858h+cwDstLength], esi; cwDstLength
0x180029166  mov     rdx, rbp; lpSrcString
0x180029169  mov     ecx, 1; NormForm
0x18002916e  call    cs:__imp_NormalizeString
0x180029174  xor     ebp, ebp
0x180029176  test    eax, eax
0x180029178  jg      short loc_18002919A
0x18002917a  call    cs:__imp_GetLastError
0x180029180  mov     ebx, eax
0x180029182  test    eax, eax
0x180029184  jle     short loc_18002918F
0x180029186  movzx   ebx, ax
0x180029189  or      ebx, 80070000h
0x18002918f  test    ebx, ebx
0x180029191  jns     short loc_18002919A
0x180029193  mov     edx, 143h
0x180029198  jmp     short loc_180029211
0x18002919a  mov     eax, 7FFFFFFEh
0x18002919f  lea     rdx, [rsp+858h+DstString]
0x1800291a4  mov     rcx, rdi
0x1800291a7  test    rax, rax
0x1800291aa  jz      short loc_1800291CB
0x1800291ac  movzx   r8d, word ptr [rdx]
0x1800291b0  test    r8w, r8w
0x1800291b4  jz      short loc_1800291CB
0x1800291b6  mov     [rcx], r8w
0x1800291ba  add     rdx, 2
0x1800291be  add     rcx, 2
0x1800291c2  dec     rax
0x1800291c5  sub     rsi, 1
0x1800291c9  jnz     short loc_1800291A7
0x1800291cb  mov     rax, rsi
0x1800291ce  lea     rdx, [rcx-2]
0x1800291d2  neg     rax
0x1800291d5  sbb     ebx, ebx
0x1800291d7  not     ebx
0x1800291d9  and     ebx, 8007007Ah
0x1800291df  test    rsi, rsi
0x1800291e2  cmovnz  rdx, rcx
0x1800291e6  mov     [rdx], bp
0x1800291e9  jnz     short loc_1800291FE
0x1800291eb  mov     edx, 15Eh
0x1800291f0  jmp     short loc_18002922D
0x1800291f2  mov     rcx, rdi; lpSrcStr
0x1800291f5  call    ?MapCharToBaseChar@@YAXPEA_W@Z; MapCharToBaseChar(wchar_t *)
0x1800291fa  add     rdi, 2
0x1800291fe  cmp     [rdi], bp
0x180029201  jnz     short loc_1800291F2
0x180029203  xor     eax, eax
0x180029205  jmp     short loc_180029246
0x180029207  mov     ebx, 80070057h
0x18002920c  mov     edx, 13Dh; void *
0x180029211  mov     rcx, [rsp+858h]; this
0x180029219  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180029220  mov     r9d, ebx; char *
0x180029223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029228  mov     edx, 158h; void *
0x18002922d  mov     rcx, [rsp+858h]; this
0x180029235  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18002923c  mov     r9d, ebx; char *
0x18002923f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029244  mov     eax, ebx
0x180029246  mov     rcx, [rsp+858h+var_28]
0x18002924e  xor     rcx, rsp; StackCookie
0x180029251  call    __security_check_cookie
0x180029256  mov     rbx, [rsp+858h+arg_0]
0x18002925e  add     rsp, 840h
0x180029265  pop     rdi
0x180029266  pop     rsi
0x180029267  pop     rbp
0x180029268  retn
```
