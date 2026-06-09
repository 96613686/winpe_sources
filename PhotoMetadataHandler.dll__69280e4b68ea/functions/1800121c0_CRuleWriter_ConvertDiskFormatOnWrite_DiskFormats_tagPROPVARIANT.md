# CRuleWriter::ConvertDiskFormatOnWrite(DiskFormats,tagPROPVARIANT *)

- ea: `0x1800121c0`
- end: `0x180012361`
- name: `?ConvertDiskFormatOnWrite@CRuleWriter@@MEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `417`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d1f0`

## callees

- `0x1800096a0`
- `0x1800121c0`
- `0x1800132dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001230b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001233d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001230b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001233d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001227f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001227f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122cb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012214`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800122bb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012214`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800122bb`

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
0x1800121c0  mov     r11, rsp
0x1800121c3  mov     [r11+8], rbx
0x1800121c7  mov     [r11+10h], rsi
0x1800121cb  push    rbp
0x1800121cc  push    rdi
0x1800121cd  push    r14
0x1800121cf  mov     rbp, rsp
0x1800121d2  sub     rsp, 60h
0x1800121d6  mov     rsi, r8
0x1800121d9  xorps   xmm0, xmm0
0x1800121dc  xor     eax, eax
0x1800121de  movups  xmmword ptr [rbp+pvar], xmm0
0x1800121e2  mov     qword ptr [rbp+pvar+10h], rax
0x1800121e6  xor     edi, edi
0x1800121e8  mov     [rbp+arg_18], rdi
0x1800121ec  cmp     edx, 3
0x1800121ef  jnz     loc_180012337
0x1800121f5  mov     [r11-40h], rdi
0x1800121f9  mov     [r11-48h], rdi
0x1800121fd  mov     [rsp+60h+cbMultiByte], edi; cbMultiByte
0x180012201  mov     [r11-58h], rdi
0x180012205  or      r9d, 0FFFFFFFFh; cchWideChar
0x180012209  mov     r8, [r8+8]; lpWideCharStr
0x18001220d  xor     edx, edx; dwFlags
0x18001220f  mov     ecx, 0FDE9h; CodePage
0x180012214  call    cs:__imp_WideCharToMultiByte
0x18001221b  nop     dword ptr [rax+rax+00h]
0x180012220  mov     r14d, eax
0x180012223  test    eax, eax
0x180012225  jnz     short loc_180012257
0x180012227  call    cs:__imp_GetLastError
0x18001222e  nop     dword ptr [rax+rax+00h]
0x180012233  mov     ebx, eax
0x180012235  test    eax, eax
0x180012237  jle     short loc_180012242
0x180012239  movzx   ebx, ax
0x18001223c  or      ebx, 80070000h
0x180012242  test    ebx, ebx
0x180012244  jns     short loc_180012257
0x180012246  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18001224c  jz      short loc_18001227C
0x18001224e  mov     ecx, ebx; int
0x180012250  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012255  jmp     short loc_18001227C
0x180012257  mov     rcx, r14; Size
0x18001225a  lea     rdx, [rbp+arg_18]; void **
0x18001225e  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180012263  mov     ebx, eax
0x180012265  test    eax, eax
0x180012267  jns     short loc_180012294
0x180012269  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18001226f  jz      short loc_180012290
0x180012271  mov     ecx, eax; int
0x180012273  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012278  mov     rdi, [rbp+arg_18]
0x18001227c  mov     rcx, rdi; pv
0x18001227f  call    cs:__imp_CoTaskMemFree
0x180012286  nop     dword ptr [rax+rax+00h]
0x18001228b  jmp     loc_180012339
0x180012290  test    eax, eax
0x180012292  js      short loc_180012278
0x180012294  mov     [rsp+60h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180012299  mov     [rsp+60h+lpDefaultChar], rdi; lpDefaultChar
0x18001229e  mov     [rsp+60h+cbMultiByte], r14d; cbMultiByte
0x1800122a3  mov     rdi, [rbp+arg_18]
0x1800122a7  mov     [rsp+60h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800122ac  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800122b0  mov     r8, [rsi+8]; lpWideCharStr
0x1800122b4  xor     edx, edx; dwFlags
0x1800122b6  mov     ecx, 0FDE9h; CodePage
0x1800122bb  call    cs:__imp_WideCharToMultiByte
0x1800122c2  nop     dword ptr [rax+rax+00h]
0x1800122c7  test    eax, eax
0x1800122c9  jnz     short loc_1800122FB
0x1800122cb  call    cs:__imp_GetLastError
0x1800122d2  nop     dword ptr [rax+rax+00h]
0x1800122d7  mov     ebx, eax
0x1800122d9  test    eax, eax
0x1800122db  jle     short loc_1800122E6
0x1800122dd  movzx   ebx, ax
0x1800122e0  or      ebx, 80070000h
0x1800122e6  test    ebx, ebx
0x1800122e8  jns     short loc_1800122FB
0x1800122ea  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800122f1  jnz     loc_18001224E
0x1800122f7  test    ebx, ebx
0x1800122f9  js      short loc_18001227C
0x1800122fb  mov     eax, 1Eh
0x180012300  mov     word ptr [rbp+pvar], ax
0x180012304  mov     qword ptr [rbp+pvar+8], rdi
0x180012308  mov     rcx, rsi; pvar
0x18001230b  call    cs:__imp_PropVariantClear
0x180012312  nop     dword ptr [rax+rax+00h]
0x180012317  movups  xmm0, xmmword ptr [rbp+pvar]
0x18001231b  movups  xmmword ptr [rsi], xmm0
0x18001231e  movsd   xmm1, qword ptr [rbp+pvar+10h]
0x180012323  movsd   qword ptr [rsi+10h], xmm1
0x180012328  xorps   xmm0, xmm0
0x18001232b  xor     eax, eax
0x18001232d  movups  xmmword ptr [rbp+pvar], xmm0
0x180012331  mov     qword ptr [rbp+pvar+10h], rax
0x180012335  jmp     short loc_180012339
0x180012337  xor     ebx, ebx
0x180012339  lea     rcx, [rbp+pvar]; pvar
0x18001233d  call    cs:__imp_PropVariantClear
0x180012344  nop     dword ptr [rax+rax+00h]
0x180012349  mov     eax, ebx
0x18001234b  lea     r11, [rsp+60h+var_s0]
0x180012350  mov     rbx, [r11+20h]
0x180012354  mov     rsi, [r11+28h]
0x180012358  mov     rsp, r11
0x18001235b  pop     r14
0x18001235d  pop     rdi
0x18001235e  pop     rbp
0x18001235f  retn
```
