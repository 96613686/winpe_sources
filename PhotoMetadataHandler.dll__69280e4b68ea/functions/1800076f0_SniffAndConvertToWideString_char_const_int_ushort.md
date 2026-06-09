# SniffAndConvertToWideString(char const *,int *,ushort * *)

- ea: `0x1800076f0`
- end: `0x180007982`
- name: `?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z`
- size: `658`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int *, LPVOID *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ca0`
- `0x180006fc0`
- `0x180008b7c`

## callees

- `0x1800076f0`
- `0x1800132dc`
- `0x180017408`
- `0x180017676`
- `0x1800176ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800077be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800077be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000778d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000778d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000790b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000790b`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000792c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000792c`

## pseudocode

```c
__int64 __fastcall SniffAndConvertToWideString(LPCCH lpMultiByteStr, int *a2, LPVOID *a3)
{
  __int64 result; // rax
  int cchWideChar; // ebp
  signed int v7; // ebx
  unsigned __int16 *v8; // rax
  signed int LastError_0; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  int *CodePage; // [rsp+58h] [rbp+10h] BYREF

  CodePage = a2;
  *a3 = 0;
  result = 0;
  if ( lpMultiByteStr )
  {
    LODWORD(CodePage) = 65001;
    cchWideChar = MultiByteToWideChar_0(0xFDE9u, 8u, lpMultiByteStr, -1, 0, 0);
    if ( cchWideChar )
      goto LABEL_7;
    LastError_0 = GetLastError_0();
    v7 = LastError_0;
    if ( LastError_0 > 0 )
      v7 = (unsigned __int16)LastError_0 | 0x80070000;
    if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147023783 )
    {
      SetLastError(0);
      v7 = 0;
      if ( !GetLocaleInfoEx(0, 0x20001004u, (LPWSTR)&CodePage, 2) )
      {
        v10 = GetLastError_0();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2003292268;
        if ( g_doStackCaptures )
          DoStackCapture(v7);
      }
      if ( v7 < 0 )
        goto LABEL_4;
      cchWideChar = MultiByteToWideChar_0((UINT)CodePage, 0, lpMultiByteStr, -1, 0, 0);
      if ( cchWideChar )
        goto LABEL_7;
      v11 = GetLastError_0();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      if ( v7 >= 0 )
      {
LABEL_7:
        if ( !is_mul_ok(cchWideChar, 2u) )
        {
          v7 = -2147024362;
          if ( !g_doStackCaptures )
          {
LABEL_9:
            CoTaskMemFree(*a3);
            *a3 = 0;
            return (unsigned int)v7;
          }
LABEL_15:
          DoStackCapture(v7);
          goto LABEL_9;
        }
        v8 = (unsigned __int16 *)CoTaskMemAlloc(2LL * cchWideChar);
        *a3 = v8;
        if ( !v8 )
        {
          v7 = -2147024882;
          if ( !g_doStackCaptures )
            goto LABEL_9;
          goto LABEL_15;
        }
        memset_0(v8, 0, 2LL * cchWideChar);
        if ( MultiByteToWideChar_0((UINT)CodePage, 0, lpMultiByteStr, -1, (LPWSTR)*a3, cchWideChar) )
          return 0;
        v12 = GetLastError_0();
        v7 = v12;
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        if ( v7 >= 0 )
          return (unsigned int)v7;
        if ( g_doStackCaptures )
LABEL_12:
          DoStackCapture(v7);
LABEL_5:
        if ( v7 >= 0 )
          return (unsigned int)v7;
        goto LABEL_9;
      }
      if ( !g_doStackCaptures )
      {
LABEL_4:
        if ( !g_doStackCaptures )
          goto LABEL_5;
        goto LABEL_12;
      }
    }
    else if ( !g_doStackCaptures )
    {
      goto LABEL_5;
    }
    DoStackCapture(v7);
    goto LABEL_4;
  }
  return result;
}

```

## disassembly

```asm
0x1800076f0  mov     [rsp+CodePage], rdx
0x1800076f5  push    rsi
0x1800076f6  push    rdi
0x1800076f7  push    r14
0x1800076f9  sub     rsp, 30h
0x1800076fd  xor     r14d, r14d
0x180007700  mov     rdi, r8
0x180007703  mov     [r8], r14
0x180007706  mov     rsi, rcx
0x180007709  mov     eax, r14d
0x18000770c  test    rcx, rcx
0x18000770f  jz      loc_1800077A8
0x180007715  mov     r8, rcx; lpMultiByteStr
0x180007718  mov     [rsp+48h+arg_10], rbx
0x18000771d  mov     ecx, 0FDE9h; CodePage
0x180007722  mov     [rsp+48h+cchWideChar], r14d; cchWideChar
0x180007727  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18000772d  mov     [rsp+48h+arg_18], rbp
0x180007732  mov     edx, 8; dwFlags
0x180007737  mov     dword ptr [rsp+48h+CodePage], 0FDE9h
0x18000773f  mov     ebx, r14d
0x180007742  mov     [rsp+48h+lpWideCharStr], r14; lpWideCharStr
0x180007747  call    MultiByteToWideChar_0
0x18000774c  mov     ebp, eax
0x18000774e  test    eax, eax
0x180007750  jz      loc_180007826
0x180007756  test    ebx, ebx
0x180007758  jns     short loc_180007769
0x18000775a  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180007761  jnz     short loc_1800077B2
0x180007763  test    ebx, ebx
0x180007765  js      short loc_18000778A
0x180007767  jmp     short loc_18000779C
0x180007769  movsxd  rcx, ebp
0x18000776c  mov     eax, 2
0x180007771  mul     rcx
0x180007774  mov     rbx, rax
0x180007777  test    rdx, rdx
0x18000777a  jz      short loc_1800077BB
0x18000777c  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180007783  mov     ebx, 80070216h
0x180007788  jnz     short loc_1800077E0
0x18000778a  mov     rcx, [rdi]; pv
0x18000778d  call    cs:__imp_CoTaskMemFree
0x180007794  nop     dword ptr [rax+rax+00h]
0x180007799  mov     [rdi], r14
0x18000779c  mov     eax, ebx
0x18000779e  mov     rbx, [rsp+48h+arg_10]
0x1800077a3  mov     rbp, [rsp+48h+arg_18]
0x1800077a8  add     rsp, 30h
0x1800077ac  pop     r14
0x1800077ae  pop     rdi
0x1800077af  pop     rsi
0x1800077b0  retn
0x1800077b2  mov     ecx, ebx; int
0x1800077b4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800077b9  jmp     short loc_180007763
0x1800077bb  mov     rcx, rbx; cb
0x1800077be  call    cs:__imp_CoTaskMemAlloc
0x1800077c5  nop     dword ptr [rax+rax+00h]
0x1800077ca  mov     [rdi], rax
0x1800077cd  test    rax, rax
0x1800077d0  jnz     short loc_1800077E9
0x1800077d2  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800077d9  mov     ebx, 8007000Eh
0x1800077de  jz      short loc_18000778A
0x1800077e0  mov     ecx, ebx; int
0x1800077e2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800077e7  jmp     short loc_18000778A
0x1800077e9  mov     r8, rbx; Size
0x1800077ec  xor     edx, edx; Val
0x1800077ee  mov     rcx, rax; void *
0x1800077f1  call    memset_0
0x1800077f6  mov     rax, [rdi]
0x1800077f9  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800077ff  mov     ecx, dword ptr [rsp+48h+CodePage]; CodePage
0x180007803  mov     r8, rsi; lpMultiByteStr
0x180007806  mov     [rsp+48h+cchWideChar], ebp; cchWideChar
0x18000780a  xor     edx, edx; dwFlags
0x18000780c  mov     [rsp+48h+lpWideCharStr], rax; lpWideCharStr
0x180007811  call    MultiByteToWideChar_0
0x180007816  test    eax, eax
0x180007818  jz      loc_1800078DB
0x18000781e  mov     eax, r14d
0x180007821  jmp     loc_18000779E
0x180007826  call    GetLastError_0
0x18000782b  mov     ebx, eax
0x18000782d  test    eax, eax
0x18000782f  jle     short loc_18000783A
0x180007831  movzx   ebx, ax
0x180007834  or      ebx, 80070000h
0x18000783a  mov     ecx, 80000000h
0x18000783f  lea     eax, [rbx+rcx]
0x180007842  test    ecx, eax
0x180007844  jnz     loc_180007909
0x18000784a  cmp     ebx, 80070459h
0x180007850  jz      loc_180007909
0x180007856  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18000785d  jz      loc_180007763
0x180007863  mov     ecx, ebx; int
0x180007865  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000786a  jmp     loc_18000775A
0x18000786f  call    GetLastError_0
0x180007874  mov     ebx, eax
0x180007876  test    eax, eax
0x180007878  jle     short loc_180007883
0x18000787a  movzx   ebx, ax
0x18000787d  or      ebx, 80070000h
0x180007883  test    ebx, ebx
0x180007885  mov     eax, 88982F94h
0x18000788a  cmovns  ebx, eax
0x18000788d  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180007894  jz      loc_180007940
0x18000789a  mov     ecx, ebx; int
0x18000789c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800078a1  jmp     loc_180007940
0x1800078a6  call    GetLastError_0
0x1800078ab  mov     ebx, eax
0x1800078ad  test    eax, eax
0x1800078af  jle     short loc_1800078BA
0x1800078b1  movzx   ebx, ax
0x1800078b4  or      ebx, 80070000h
0x1800078ba  test    ebx, ebx
0x1800078bc  jns     loc_180007769
0x1800078c2  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800078c9  jz      loc_180007975
0x1800078cf  mov     ecx, ebx; int
0x1800078d1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800078d6  jmp     loc_18000775A
0x1800078db  call    GetLastError_0
0x1800078e0  mov     ebx, eax
0x1800078e2  test    eax, eax
0x1800078e4  jle     short loc_1800078EF
0x1800078e6  movzx   ebx, ax
0x1800078e9  or      ebx, 80070000h
0x1800078ef  test    ebx, ebx
0x1800078f1  jns     loc_18000779C
0x1800078f7  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800078fe  jz      loc_180007763
0x180007904  jmp     loc_1800077B2
0x180007909  xor     ecx, ecx; dwErrCode
0x18000790b  call    cs:__imp_SetLastError
0x180007912  nop     dword ptr [rax+rax+00h]
0x180007917  mov     r9d, 2; cchData
0x18000791d  lea     r8, [rsp+48h+CodePage]; lpLCData
0x180007922  mov     edx, 20001004h; LCType
0x180007927  xor     ecx, ecx; lpLocaleName
0x180007929  mov     ebx, r14d
0x18000792c  call    cs:__imp_GetLocaleInfoEx
0x180007933  nop     dword ptr [rax+rax+00h]
0x180007938  test    eax, eax
0x18000793a  jz      loc_18000786F
0x180007940  test    ebx, ebx
0x180007942  js      loc_18000775A
0x180007948  mov     ecx, dword ptr [rsp+48h+CodePage]; CodePage
0x18000794c  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180007952  mov     [rsp+48h+cchWideChar], r14d; cchWideChar
0x180007957  mov     r8, rsi; lpMultiByteStr
0x18000795a  xor     edx, edx; dwFlags
0x18000795c  mov     [rsp+48h+lpWideCharStr], r14; lpWideCharStr
0x180007961  call    MultiByteToWideChar_0
0x180007966  mov     ebp, eax
0x180007968  test    eax, eax
0x18000796a  jnz     loc_180007756
0x180007970  jmp     loc_1800078A6
0x180007975  test    ebx, ebx
0x180007977  js      loc_18000775A
0x18000797d  jmp     loc_180007756
```
