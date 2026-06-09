# MakeStringW(ushort * *,ushort const *,...)

- ea: `0x180006764`
- end: `0x180006870`
- name: `?MakeStringW@@YAJPEAPEAGPEBGZZ`
- size: `268`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002200`
- `0x1800065c0`
- `0x180013694`
- `0x180018188`
- `0x18001a9b8`
- `0x18001b5b0`
- `0x18001c410`
- `0x180050274`
- `0x18005063c`
- `0x1800592a8`
- `0x1800594e0`
- `0x18006e22c`
- `0x180071a34`
- `0x180071fc8`
- `0x18007975c`

## callees

- `0x180006764`
- `0x18000d5f4`
- `0x18001156c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800067d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800067d8`
- `msvcrt!_vsnwprintf` at `0x180006806`
- `msvcrt!_vsnwprintf` at `0x180006806`

## string_xrefs

- `0x180006846`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x18000678a`: `MakeStringW (com\complus\dtc\shared\util\stringutil.cpp@63): MakeStringW, ppwszDestString != NULL`
- `0x18000679c`: `MakeStringW (com\complus\dtc\shared\util\stringutil.cpp@64): MakeStringW, pwszFormatString != NULL`

## pseudocode

```c
__int64 MakeStringW(unsigned __int16 **a1, const unsigned __int16 *a2, ...)
{
  _WORD *v4; // rbx
  SIZE_T v5; // r14
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rdi
  int v8; // eax
  int v9; // ecx
  unsigned int v10; // edi
  va_list Args; // [rsp+80h] [rbp+18h] BYREF

  va_start(Args, a2);
  if ( !a1 )
    DtcInternalErrorW(L"MakeStringW (com\\complus\\dtc\\shared\\util\\stringutil.cpp@63): MakeStringW, ppwszDestString != NULL");
  if ( !a2 )
    DtcInternalErrorW(L"MakeStringW (com\\complus\\dtc\\shared\\util\\stringutil.cpp@64): MakeStringW, pwszFormatString != NULL");
  *a1 = 0;
  v4 = 0;
  v5 = 128;
  while ( 1 )
  {
    v5 *= 2LL;
    CoTaskMemFree(v4);
    v4 = CoTaskMemAlloc(v5);
    if ( !v4 )
      break;
    v6 = v5 >> 1;
    if ( !(v5 >> 1) )
      goto LABEL_18;
    if ( v6 > 0x7FFFFFFF )
    {
      *v4 = 0;
LABEL_18:
      v10 = 0;
      *a1 = v4;
      return v10;
    }
    v7 = v6 - 1;
    v8 = _vsnwprintf(v4, v6 - 1, a2, Args);
    if ( v8 < 0 || v8 > v7 )
    {
      v9 = -2147024774;
    }
    else
    {
      v9 = 0;
      if ( v8 != v7 )
        goto LABEL_15;
    }
    v4[v7] = 0;
LABEL_15:
    if ( v9 != -2147024774 )
      goto LABEL_18;
  }
  v10 = -2147024882;
  TraceFileW(
    -2147024882,
    L"MakeStringW, StringCchVPrintfExW failed",
    L"com\\complus\\dtc\\shared\\util\\stringutil.cpp",
    0x4Fu);
  return v10;
}

```

## disassembly

```asm
0x180006764  mov     [rsp+arg_8], rdx
0x180006769  mov     qword ptr [rsp+Args], r8
0x18000676e  mov     [rsp+arg_18], r9
0x180006773  push    rbx
0x180006774  push    rbp
0x180006775  push    rsi
0x180006776  push    rdi
0x180006777  push    r12
0x180006779  push    r14
0x18000677b  sub     rsp, 38h
0x18000677f  mov     rbp, rdx
0x180006782  mov     rsi, rcx
0x180006785  test    rcx, rcx
0x180006788  jnz     short loc_180006797
0x18000678a  lea     rcx, aMakestringwCom; "MakeStringW (com\\complus\\dtc\\shared"...
0x180006791  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180006797  test    rbp, rbp
0x18000679a  jnz     short loc_1800067A9
0x18000679c  lea     rcx, aMakestringwCom_0; "MakeStringW (com\\complus\\dtc\\shared"...
0x1800067a3  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800067a9  mov     qword ptr [rcx], 0
0x1800067b0  lea     r12, [rsp+68h+Args]
0x1800067b8  mov     [rsp+68h+var_48], 0
0x1800067c1  xor     ebx, ebx
0x1800067c3  mov     r14d, 80h
0x1800067c9  mov     rcx, rbx; pv
0x1800067cc  add     r14, r14
0x1800067cf  call    cs:__imp_CoTaskMemFree
0x1800067d5  mov     rcx, r14; cb
0x1800067d8  call    cs:__imp_CoTaskMemAlloc
0x1800067de  mov     rbx, rax
0x1800067e1  test    rax, rax
0x1800067e4  jz      short loc_180006841
0x1800067e6  mov     rax, r14
0x1800067e9  shr     rax, 1
0x1800067ec  jz      short loc_18000683A
0x1800067ee  cmp     rax, 7FFFFFFFh
0x1800067f4  ja      short loc_180006835
0x1800067f6  lea     rdi, [rax-1]
0x1800067fa  mov     r9, r12; Args
0x1800067fd  mov     rdx, rdi; BufferCount
0x180006800  mov     r8, rbp; Format
0x180006803  mov     rcx, rbx; Buffer
0x180006806  call    cs:__imp__vsnwprintf
0x18000680c  test    eax, eax
0x18000680e  js      short loc_180006820
0x180006810  cdqe
0x180006812  cmp     rax, rdi
0x180006815  ja      short loc_180006820
0x180006817  xor     ecx, ecx
0x180006819  cmp     rax, rdi
0x18000681c  jz      short loc_180006825
0x18000681e  jmp     short loc_18000682B
0x180006820  mov     ecx, 8007007Ah
0x180006825  xor     eax, eax
0x180006827  mov     [rbx+rdi*2], ax
0x18000682b  cmp     ecx, 8007007Ah
0x180006831  jz      short loc_1800067C9
0x180006833  jmp     short loc_18000683A
0x180006835  xor     eax, eax
0x180006837  mov     [rbx], ax
0x18000683a  xor     edi, edi
0x18000683c  mov     [rsi], rbx
0x18000683f  jmp     short loc_180006861
0x180006841  mov     edi, 8007000Eh
0x180006846  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18000684d  mov     ecx, edi; int
0x18000684f  lea     rdx, aMakestringwStr; "MakeStringW, StringCchVPrintfExW failed"
0x180006856  mov     r9d, 4Fh ; 'O'; unsigned int
0x18000685c  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180006861  mov     eax, edi
0x180006863  add     rsp, 38h
0x180006867  pop     r14
0x180006869  pop     r12
0x18000686b  pop     rdi
0x18000686c  pop     rsi
0x18000686d  pop     rbp
0x18000686e  pop     rbx
0x18000686f  retn
```
