# CreateTaskMemWStrFromStr

- ea: `0x1400489c4`
- end: `0x140048b3e`
- name: `CreateTaskMemWStrFromStr`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140048bc8`

## callees

- `0x140028044`
- `0x1400489c4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140048a5b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140048aaf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140048ae3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140048a5b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140048aaf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140048ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140048a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140048ab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140048a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140048ab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048b1f`

## string_xrefs

- `0x140048a27`: `onecoreuap\base\appmodel\search\common\pkmutild\propvarcvt.cxx`

## pseudocode

```c
__int64 __fastcall CreateTaskMemWStrFromStr(__int64 a1, const CHAR *a2, WCHAR **a3)
{
  __int64 v5; // rax
  unsigned int v6; // r15d
  unsigned int cchWideChar; // r12d
  WCHAR *v8; // rax
  WCHAR *v9; // rbp
  unsigned int v10; // ebx
  WCHAR *v12; // rdi
  signed int LastError; // eax
  signed int v14; // eax
  int lpWideCharStr; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a2 && a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = v5 + 1;
    cchWideChar = v6 / 0xA + v6;
    v8 = (WCHAR *)CoTaskMemAlloc(2LL * cchWideChar);
    v9 = v8;
    if ( !v8 )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AF,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\propvarcvt.cxx",
        (const char *)0x8007000ELL,
        lpWideCharStr);
      return v10;
    }
    if ( MultiByteToWideChar(0, 0, a2, v6, v8, cchWideChar) )
    {
      v10 = 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 == -2147024774 )
      {
        MultiByteToWideChar(0, 0, a2, v6, 0, 0);
        v12 = (WCHAR *)CoTaskMemAlloc(2LL * (v6 / 0xA + v6));
        CoTaskMemFree(v9);
        if ( !v12 )
          return (unsigned int)-2147024882;
        if ( MultiByteToWideChar(0, 0, a2, v6, v12, cchWideChar) )
        {
          v10 = 0;
        }
        else
        {
          v14 = GetLastError();
          v10 = v14;
          if ( v14 > 0 )
            v10 = (unsigned __int16)v14 | 0x80070000;
        }
LABEL_11:
        if ( (v10 & 0x80000000) != 0 )
          CoTaskMemFree(v12);
        else
          *a3 = v12;
        return v10;
      }
    }
    v12 = v9;
    goto LABEL_11;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1400489c4  push    rbx
0x1400489c6  push    rbp
0x1400489c7  push    rsi
0x1400489c8  push    rdi
0x1400489c9  push    r12
0x1400489cb  push    r14
0x1400489cd  push    r15
0x1400489cf  sub     rsp, 30h
0x1400489d3  mov     r14, r8
0x1400489d6  mov     rsi, rdx
0x1400489d9  test    rdx, rdx
0x1400489dc  jz      loc_140048B2A
0x1400489e2  test    r8, r8
0x1400489e5  jz      loc_140048B2A
0x1400489eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400489ef  inc     rax
0x1400489f2  cmp     byte ptr [rdx+rax], 0
0x1400489f6  jnz     short loc_1400489EF
0x1400489f8  lea     r15d, [rax+1]
0x1400489fc  mov     eax, 0CCCCCCCDh
0x140048a01  mul     r15d
0x140048a04  shr     edx, 3
0x140048a07  lea     r12d, [rdx+r15]
0x140048a0b  mov     edi, r12d
0x140048a0e  add     rdi, rdi
0x140048a11  mov     rcx, rdi; cb
0x140048a14  call    cs:__imp_CoTaskMemAlloc
0x140048a1a  mov     rbp, rax
0x140048a1d  test    rax, rax
0x140048a20  jnz     short loc_140048A47
0x140048a22  mov     rcx, [rsp+68h]; this
0x140048a27  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\search\\com"...
0x140048a2e  mov     ebx, 8007000Eh
0x140048a33  mov     edx, 5AFh; void *
0x140048a38  mov     r9d, ebx; char *
0x140048a3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140048a40  mov     eax, ebx
0x140048a42  jmp     loc_140048B2F
0x140048a47  mov     [rsp+68h+cchWideChar], r12d; cchWideChar
0x140048a4c  mov     r9d, r15d; cbMultiByte
0x140048a4f  mov     r8, rsi; lpMultiByteStr
0x140048a52  mov     [rsp+68h+lpWideCharStr], rbp; lpWideCharStr
0x140048a57  xor     edx, edx; dwFlags
0x140048a59  xor     ecx, ecx; CodePage
0x140048a5b  call    cs:__imp_MultiByteToWideChar
0x140048a61  test    eax, eax
0x140048a63  jz      short loc_140048A77
0x140048a65  xor     ebx, ebx
0x140048a67  mov     rdi, rbp
0x140048a6a  test    ebx, ebx
0x140048a6c  js      loc_140048B1C
0x140048a72  mov     [r14], rdi
0x140048a75  jmp     short loc_140048A40
0x140048a77  call    cs:__imp_GetLastError
0x140048a7d  mov     ebx, eax
0x140048a7f  test    eax, eax
0x140048a81  jle     short loc_140048A8C
0x140048a83  movzx   ebx, ax
0x140048a86  or      ebx, 80070000h
0x140048a8c  cmp     ebx, 8007007Ah
0x140048a92  jnz     short loc_140048A67
0x140048a94  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x140048a9c  mov     r9d, r15d; cbMultiByte
0x140048a9f  mov     r8, rsi; lpMultiByteStr
0x140048aa2  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x140048aab  xor     edx, edx; dwFlags
0x140048aad  xor     ecx, ecx; CodePage
0x140048aaf  call    cs:__imp_MultiByteToWideChar
0x140048ab5  mov     rcx, rdi; cb
0x140048ab8  call    cs:__imp_CoTaskMemAlloc
0x140048abe  mov     rcx, rbp; pv
0x140048ac1  mov     rdi, rax
0x140048ac4  call    cs:__imp_CoTaskMemFree
0x140048aca  test    rdi, rdi
0x140048acd  jz      short loc_140048B12
0x140048acf  mov     [rsp+68h+cchWideChar], r12d; cchWideChar
0x140048ad4  mov     r9d, r15d; cbMultiByte
0x140048ad7  mov     r8, rsi; lpMultiByteStr
0x140048ada  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x140048adf  xor     edx, edx; dwFlags
0x140048ae1  xor     ecx, ecx; CodePage
0x140048ae3  call    cs:__imp_MultiByteToWideChar
0x140048ae9  test    eax, eax
0x140048aeb  jz      short loc_140048AF4
0x140048aed  xor     ebx, ebx
0x140048aef  jmp     loc_140048A6A
0x140048af4  call    cs:__imp_GetLastError
0x140048afa  mov     ebx, eax
0x140048afc  test    eax, eax
0x140048afe  jle     loc_140048A6A
0x140048b04  movzx   ebx, ax
0x140048b07  or      ebx, 80070000h
0x140048b0d  jmp     loc_140048A6A
0x140048b12  mov     ebx, 8007000Eh
0x140048b17  jmp     loc_140048A40
0x140048b1c  mov     rcx, rdi; pv
0x140048b1f  call    cs:__imp_CoTaskMemFree
0x140048b25  jmp     loc_140048A40
0x140048b2a  mov     eax, 80004003h
0x140048b2f  add     rsp, 30h
0x140048b33  pop     r15
0x140048b35  pop     r14
0x140048b37  pop     r12
0x140048b39  pop     rdi
0x140048b3a  pop     rsi
0x140048b3b  pop     rbp
0x140048b3c  pop     rbx
0x140048b3d  retn
```
