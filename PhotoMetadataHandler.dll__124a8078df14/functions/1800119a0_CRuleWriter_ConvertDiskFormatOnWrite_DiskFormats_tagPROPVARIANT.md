# CRuleWriter::ConvertDiskFormatOnWrite(DiskFormats,tagPROPVARIANT *)

- ea: `0x1800119a0`
- end: `0x180011b16`
- name: `?ConvertDiskFormatOnWrite@CRuleWriter@@MEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `374`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c4c0`

## callees

- `0x180007d90`
- `0x1800119a0`
- `0x1800129d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011acd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011af9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011acd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011af9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a93`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800119f4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180011a89`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800119f4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180011a89`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRuleWriter::ConvertDiskFormatOnWrite(__int64 a1, int a2, PROPVARIANT *a3)
{
  LPSTR v4; // rdi
  unsigned int v5; // eax
  size_t cbMultiByte; // r14
  signed int LastError; // eax
  signed int v8; // ebx
  int v9; // eax
  signed int v10; // eax
  PROPVARIANT pvar; // [rsp+40h] [rbp-20h] BYREF
  LPSTR lpMultiByteStr; // [rsp+98h] [rbp+38h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  v4 = 0;
  lpMultiByteStr = 0;
  if ( a2 != 3 )
  {
    v8 = 0;
    goto LABEL_22;
  }
  v5 = WideCharToMultiByte(0xFDE9u, 0, a3->bstrVal, -1, 0, 0, 0, 0);
  cbMultiByte = v5;
  if ( v5 )
    goto LABEL_8;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 >= 0 )
  {
LABEL_8:
    v9 = CoTaskMemAllocWithInit(cbMultiByte, (void **)&lpMultiByteStr);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v9);
      v4 = lpMultiByteStr;
      goto LABEL_12;
    }
    v4 = lpMultiByteStr;
    if ( WideCharToMultiByte(0xFDE9u, 0, a3->bstrVal, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
      goto LABEL_20;
    v10 = GetLastError();
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    if ( v8 >= 0 )
    {
LABEL_20:
      pvar.vt = 30;
      pvar.hVal.QuadPart = (LONGLONG)v4;
      PropVariantClear(a3);
      *a3 = pvar;
      memset(&pvar, 0, sizeof(pvar));
      goto LABEL_22;
    }
    if ( g_doStackCaptures )
      goto LABEL_7;
  }
  else if ( g_doStackCaptures )
  {
LABEL_7:
    DoStackCapture(v8);
  }
LABEL_12:
  CoTaskMemFree(v4);
LABEL_22:
  PropVariantClear(&pvar);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800119a0  mov     r11, rsp
0x1800119a3  mov     [r11+8], rbx
0x1800119a7  mov     [r11+10h], rsi
0x1800119ab  push    rbp
0x1800119ac  push    rdi
0x1800119ad  push    r14
0x1800119af  mov     rbp, rsp
0x1800119b2  sub     rsp, 60h
0x1800119b6  mov     rsi, r8
0x1800119b9  xorps   xmm0, xmm0
0x1800119bc  xor     eax, eax
0x1800119be  movups  xmmword ptr [rbp+pvar], xmm0
0x1800119c2  mov     qword ptr [rbp+pvar+10h], rax
0x1800119c6  xor     edi, edi
0x1800119c8  mov     [rbp+arg_18], rdi
0x1800119cc  cmp     edx, 3
0x1800119cf  jnz     loc_180011AF3
0x1800119d5  mov     [r11-40h], rdi
0x1800119d9  mov     [r11-48h], rdi
0x1800119dd  mov     [rsp+60h+cbMultiByte], edi; cbMultiByte
0x1800119e1  mov     [r11-58h], rdi
0x1800119e5  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800119e9  mov     r8, [r8+8]; lpWideCharStr
0x1800119ed  xor     edx, edx; dwFlags
0x1800119ef  mov     ecx, 0FDE9h; CodePage
0x1800119f4  call    cs:__imp_WideCharToMultiByte
0x1800119fa  mov     r14d, eax
0x1800119fd  test    eax, eax
0x1800119ff  jnz     short loc_180011A2B
0x180011a01  call    cs:__imp_GetLastError
0x180011a07  mov     ebx, eax
0x180011a09  test    eax, eax
0x180011a0b  jle     short loc_180011A16
0x180011a0d  movzx   ebx, ax
0x180011a10  or      ebx, 80070000h
0x180011a16  test    ebx, ebx
0x180011a18  jns     short loc_180011A2B
0x180011a1a  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180011a20  jz      short loc_180011A50
0x180011a22  mov     ecx, ebx; int
0x180011a24  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011a29  jmp     short loc_180011A50
0x180011a2b  mov     rcx, r14; Size
0x180011a2e  lea     rdx, [rbp+arg_18]; void **
0x180011a32  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180011a37  mov     ebx, eax
0x180011a39  test    eax, eax
0x180011a3b  jns     short loc_180011A62
0x180011a3d  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180011a43  jz      short loc_180011A5E
0x180011a45  mov     ecx, eax; int
0x180011a47  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011a4c  mov     rdi, [rbp+arg_18]
0x180011a50  mov     rcx, rdi; pv
0x180011a53  call    cs:__imp_CoTaskMemFree
0x180011a59  jmp     loc_180011AF5
0x180011a5e  test    eax, eax
0x180011a60  js      short loc_180011A4C
0x180011a62  mov     [rsp+60h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180011a67  mov     [rsp+60h+lpDefaultChar], rdi; lpDefaultChar
0x180011a6c  mov     [rsp+60h+cbMultiByte], r14d; cbMultiByte
0x180011a71  mov     rdi, [rbp+arg_18]
0x180011a75  mov     [rsp+60h+lpMultiByteStr], rdi; lpMultiByteStr
0x180011a7a  or      r9d, 0FFFFFFFFh; cchWideChar
0x180011a7e  mov     r8, [rsi+8]; lpWideCharStr
0x180011a82  xor     edx, edx; dwFlags
0x180011a84  mov     ecx, 0FDE9h; CodePage
0x180011a89  call    cs:__imp_WideCharToMultiByte
0x180011a8f  test    eax, eax
0x180011a91  jnz     short loc_180011ABD
0x180011a93  call    cs:__imp_GetLastError
0x180011a99  mov     ebx, eax
0x180011a9b  test    eax, eax
0x180011a9d  jle     short loc_180011AA8
0x180011a9f  movzx   ebx, ax
0x180011aa2  or      ebx, 80070000h
0x180011aa8  test    ebx, ebx
0x180011aaa  jns     short loc_180011ABD
0x180011aac  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011ab3  jnz     loc_180011A22
0x180011ab9  test    ebx, ebx
0x180011abb  js      short loc_180011A50
0x180011abd  mov     eax, 1Eh
0x180011ac2  mov     word ptr [rbp+pvar], ax
0x180011ac6  mov     qword ptr [rbp+pvar+8], rdi
0x180011aca  mov     rcx, rsi; pvar
0x180011acd  call    cs:__imp_PropVariantClear
0x180011ad3  movups  xmm0, xmmword ptr [rbp+pvar]
0x180011ad7  movups  xmmword ptr [rsi], xmm0
0x180011ada  movsd   xmm1, qword ptr [rbp+pvar+10h]
0x180011adf  movsd   qword ptr [rsi+10h], xmm1
0x180011ae4  xorps   xmm0, xmm0
0x180011ae7  xor     eax, eax
0x180011ae9  movups  xmmword ptr [rbp+pvar], xmm0
0x180011aed  mov     qword ptr [rbp+pvar+10h], rax
0x180011af1  jmp     short loc_180011AF5
0x180011af3  xor     ebx, ebx
0x180011af5  lea     rcx, [rbp+pvar]; pvar
0x180011af9  call    cs:__imp_PropVariantClear
0x180011aff  mov     eax, ebx
0x180011b01  lea     r11, [rsp+60h+var_s0]
0x180011b06  mov     rbx, [r11+20h]
0x180011b0a  mov     rsi, [r11+28h]
0x180011b0e  mov     rsp, r11
0x180011b11  pop     r14
0x180011b13  pop     rdi
0x180011b14  pop     rbp
0x180011b15  retn
```
