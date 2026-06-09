# CompareResult(int *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ATL::CComVariant const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,__int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000c5fc`
- end: `0x18000c8c1`
- name: `?CompareResult@@YAXPEAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCComVariant@ATL@@1_J1@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000c974`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c190`
- `0x18000c5fc`
- `0x18000e0e4`
- `0x18003ffb4`
- `0x180040148`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `SHLWAPI!StrToInt64ExW` at `0x18000c7fa`
- `SHLWAPI!StrToInt64ExW` at `0x18000c7fa`

## string_xrefs

- `0x18000c6f2`: `CompareResult`
- `0x18000c823`: `CompareResult`
- `0x18000c85b`: `CompareResult`
- `0x18000c893`: `CompareResult`
- `0x18000c882`: `Wmi result type is not integer compatiable %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CompareResult(_DWORD *a1, const wchar_t *a2, unsigned __int16 *a3, __int64 a4, __int64 a5, __int64 a6)
{
  const wchar_t *v8; // rbx
  unsigned __int64 v10; // rdi
  const wchar_t *v11; // rcx
  size_t v12; // r8
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  PCWSTR *v18; // rax
  unsigned __int64 v19; // rsi
  size_t v20; // r8
  int v21; // ecx
  _WORD *v22; // rax
  unsigned __int64 v23; // rdx
  __int64 v24; // rbx
  const WCHAR *v25; // rcx
  PCWSTR *v26; // rax
  LONGLONG pllRet[2]; // [rsp+30h] [rbp-48h] BYREF
  PCWSTR pszString[2]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v29; // [rsp+50h] [rbp-28h]

  pllRet[1] = -2;
  v8 = a2;
  *a1 = 0;
  v10 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v11 = a2;
  else
    v11 = *(const wchar_t **)a2;
  v12 = *((_QWORD *)a2 + 2);
  if ( v10 > 7 )
    v12 = 7;
  if ( !wmemcmp(v11, L"wstring", v12) && v10 == 7 )
  {
    v13 = *a3;
    if ( (_WORD)v13 != 8 )
    {
      v14 = "Wmi result type is not string %d";
      v15 = 72;
LABEL_40:
      AslLogCallPrintf(1, "CompareResult", v15, v14, v13);
      return;
    }
    v16 = *((_QWORD *)a3 + 1);
    *(_OWORD *)pszString = 0;
    v29 = 0;
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(v16 + 2 * v17) );
    std::wstring::_Construct<1,unsigned short const *>(pszString, v16, v17);
    v18 = pszString;
    if ( *((_QWORD *)&v29 + 1) > 7u )
      v18 = (PCWSTR *)pszString[0];
    AslLogCallPrintf(3, "CompareResult", 77, "Wmi result str = %ws", v18);
    *a1 = AppCompatUtility::CompareStr(pszString, a4, a6);
    goto LABEL_35;
  }
  v19 = *((_QWORD *)v8 + 2);
  if ( *((_QWORD *)v8 + 3) > 7u )
    v8 = *(const wchar_t **)v8;
  v20 = v19;
  if ( v19 > 3 )
    v20 = 3;
  if ( !wmemcmp(v8, L"int", v20) && v19 == 3 )
  {
    if ( *a3 > 0x19u || (v21 = 50268428, !_bittest(&v21, *a3)) )
    {
      v13 = *a3;
      v14 = "Wmi result type is not integer compatiable %d";
      v15 = 88;
      goto LABEL_40;
    }
    pllRet[0] = 0;
    *(_OWORD *)pszString = 0;
    *(_QWORD *)&v29 = 0;
    *((_QWORD *)&v29 + 1) = 7;
    LOWORD(pszString[0]) = 0;
    v22 = (_WORD *)*((_QWORD *)a3 + 1);
    if ( *a3 == 8 )
    {
      v23 = -1;
      do
        ++v23;
      while ( v22[v23] );
      if ( v23 > 7 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(pszString);
      }
      else
      {
        *(_QWORD *)&v29 = v23;
        v24 = 2 * v23;
        memmove_0(pszString, v22, 2 * v23);
        *(_WORD *)((char *)pszString + v24) = 0;
      }
      v25 = (const WCHAR *)pszString;
      if ( *((_QWORD *)&v29 + 1) > 7u )
        v25 = pszString[0];
      if ( !StrToInt64ExW(v25, 1, pllRet) )
      {
        v26 = pszString;
        if ( *((_QWORD *)&v29 + 1) > 7u )
          v26 = (PCWSTR *)pszString[0];
        AslLogCallPrintf(1, "CompareResult", 104, "Convert WmiResultStr to integer failed, %ws", v26);
        goto LABEL_35;
      }
      v22 = (_WORD *)pllRet[0];
    }
    else
    {
      pllRet[0] = *((_QWORD *)a3 + 1);
    }
    AslLogCallPrintf(3, "CompareResult", 113, "Wmi result int64 = %lld", v22);
    *a1 = AppCompatUtility::CompareInt(pllRet[0], a5, a6);
LABEL_35:
    std::wstring::~wstring(pszString);
  }
}

```

## disassembly

```asm
0x18000c5fc  push    rbp
0x18000c5fe  push    rbx
0x18000c5ff  push    rsi
0x18000c600  push    rdi
0x18000c601  push    r12
0x18000c603  push    r13
0x18000c605  push    r14
0x18000c607  push    r15
0x18000c609  mov     rbp, rsp
0x18000c60c  sub     rsp, 78h
0x18000c610  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x18000c618  mov     rax, cs:__security_cookie
0x18000c61f  xor     rax, rsp
0x18000c622  mov     [rbp+var_18], rax
0x18000c626  mov     rsi, r9
0x18000c629  mov     r14, r8
0x18000c62c  mov     rbx, rdx
0x18000c62f  mov     r15, rcx
0x18000c632  mov     r12, [rbp+arg_28]
0x18000c636  xor     r13d, r13d
0x18000c639  mov     [rcx], r13d
0x18000c63c  mov     rdi, [rdx+10h]
0x18000c640  lea     eax, [r13+7]
0x18000c644  cmp     [rdx+18h], rax
0x18000c648  jbe     short loc_18000C64F
0x18000c64a  mov     rcx, [rdx]
0x18000c64d  jmp     short loc_18000C652
0x18000c64f  mov     rcx, rbx; S1
0x18000c652  mov     r8, rdi
0x18000c655  cmp     rdi, rax
0x18000c658  cmova   r8, rax; N
0x18000c65c  lea     rdx, aWstring; "wstring"
0x18000c663  call    wmemcmp
0x18000c668  test    eax, eax
0x18000c66a  jnz     loc_18000C719
0x18000c670  cmp     rdi, 7
0x18000c674  jnz     loc_18000C719
0x18000c67a  mov     eax, r13d
0x18000c67d  test    eax, eax
0x18000c67f  jnz     loc_18000C719
0x18000c685  movzx   eax, word ptr [r14]
0x18000c689  lea     ecx, [rdi+1]
0x18000c68c  cmp     cx, ax
0x18000c68f  jz      short loc_18000C6A1
0x18000c691  lea     r9, aWmiResultTypeI; "Wmi result type is not string %d"
0x18000c698  lea     r8d, [rdi+41h]
0x18000c69c  jmp     loc_18000C88F
0x18000c6a1  mov     rax, [r14+8]
0x18000c6a5  xorps   xmm0, xmm0
0x18000c6a8  movups  xmmword ptr [rbp+pszString], xmm0
0x18000c6ac  xorps   xmm1, xmm1
0x18000c6af  movdqu  [rbp+var_28], xmm1
0x18000c6b4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c6b8  inc     rdx
0x18000c6bb  cmp     [rax+rdx*2], r13w
0x18000c6c0  jnz     short loc_18000C6B8
0x18000c6c2  mov     r8, rdx
0x18000c6c5  mov     rdx, rax
0x18000c6c8  lea     rcx, [rbp+pszString]
0x18000c6cc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000c6d1  nop
0x18000c6d2  lea     rax, [rbp+pszString]
0x18000c6d6  cmp     qword ptr [rbp+var_28+8], 7
0x18000c6db  cmova   rax, [rbp+pszString]
0x18000c6e0  mov     [rsp+78h+var_58], rax
0x18000c6e5  lea     r9, aWmiResultStrWs; "Wmi result str = %ws"
0x18000c6ec  mov     r8d, 4Dh ; 'M'
0x18000c6f2  lea     rdx, aCompareresult; "CompareResult"
0x18000c6f9  lea     ecx, [r8-4Ah]
0x18000c6fd  call    AslLogCallPrintf
0x18000c702  mov     r8, r12
0x18000c705  mov     rdx, rsi
0x18000c708  lea     rcx, [rbp+pszString]
0x18000c70c  call    ?CompareStr@AppCompatUtility@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; AppCompatUtility::CompareStr(std::wstring const &,std::wstring const &,std::wstring const &)
0x18000c711  mov     [r15], eax
0x18000c714  jmp     loc_18000C834
0x18000c719  mov     rsi, [rbx+10h]
0x18000c71d  cmp     qword ptr [rbx+18h], 7
0x18000c722  jbe     short loc_18000C727
0x18000c724  mov     rbx, [rbx]
0x18000c727  mov     r8, rsi
0x18000c72a  mov     edi, 3
0x18000c72f  cmp     rsi, rdi
0x18000c732  cmova   r8, rdi; N
0x18000c736  lea     rdx, aInt; "int"
0x18000c73d  mov     rcx, rbx; S1
0x18000c740  call    wmemcmp
0x18000c745  test    eax, eax
0x18000c747  jnz     loc_18000C8A4
0x18000c74d  cmp     rsi, rdi
0x18000c750  jnz     loc_18000C8A4
0x18000c756  mov     eax, r13d
0x18000c759  test    eax, eax
0x18000c75b  jnz     loc_18000C8A4
0x18000c761  cmp     word ptr [r14], 19h
0x18000c766  ja      loc_18000C87E
0x18000c76c  movzx   eax, word ptr [r14]
0x18000c770  mov     ecx, 2FF090Ch
0x18000c775  bt      ecx, eax
0x18000c778  jnb     loc_18000C87E
0x18000c77e  mov     [rbp+pllRet], r13
0x18000c782  xorps   xmm0, xmm0
0x18000c785  movups  xmmword ptr [rbp+pszString], xmm0
0x18000c789  mov     qword ptr [rbp+var_28], r13
0x18000c78d  lea     esi, [rdi+4]
0x18000c790  mov     qword ptr [rbp+var_28+8], rsi
0x18000c794  mov     word ptr [rbp+pszString], r13w
0x18000c799  mov     rax, [r14+8]
0x18000c79d  lea     ecx, [rdi+5]
0x18000c7a0  cmp     cx, [r14]
0x18000c7a4  jnz     loc_18000C845
0x18000c7aa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c7ae  inc     rdx
0x18000c7b1  cmp     [rax+rdx*2], r13w
0x18000c7b6  jnz     short loc_18000C7AE
0x18000c7b8  lea     rcx, [rbp+pszString]; void *
0x18000c7bc  cmp     rdx, rsi
0x18000c7bf  ja      short loc_18000C7DC
0x18000c7c1  mov     qword ptr [rbp+var_28], rdx
0x18000c7c5  lea     rbx, [rdx+rdx]
0x18000c7c9  mov     r8, rbx; Size
0x18000c7cc  mov     rdx, rax; Src
0x18000c7cf  call    memmove_0
0x18000c7d4  mov     word ptr [rbp+rbx+pszString], r13w
0x18000c7da  jmp     short loc_18000C7E4
0x18000c7dc  mov     r9, rax
0x18000c7df  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000c7e4  lea     rcx, [rbp+pszString]
0x18000c7e8  cmp     qword ptr [rbp+var_28+8], rsi
0x18000c7ec  cmova   rcx, [rbp+pszString]; pszString
0x18000c7f1  lea     r8, [rbp+pllRet]; pllRet
0x18000c7f5  mov     edx, 1; dwFlags
0x18000c7fa  call    cs:__imp_StrToInt64ExW
0x18000c800  test    eax, eax
0x18000c802  jnz     short loc_18000C83F
0x18000c804  lea     rax, [rbp+pszString]
0x18000c808  cmp     qword ptr [rbp+var_28+8], rsi
0x18000c80c  cmova   rax, [rbp+pszString]
0x18000c811  mov     [rsp+78h+var_58], rax
0x18000c816  lea     r9, aConvertWmiresu; "Convert WmiResultStr to integer failed,"...
0x18000c81d  mov     r8d, 68h ; 'h'
0x18000c823  lea     rdx, aCompareresult; "CompareResult"
0x18000c82a  lea     ecx, [r8-67h]
0x18000c82e  call    AslLogCallPrintf
0x18000c833  nop
0x18000c834  lea     rcx, [rbp+pszString]; void *
0x18000c838  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c83d  jmp     short loc_18000C8A4
0x18000c83f  mov     rax, [rbp+pllRet]
0x18000c843  jmp     short loc_18000C849
0x18000c845  mov     [rbp+pllRet], rax
0x18000c849  mov     [rsp+78h+var_58], rax
0x18000c84e  lea     r9, aWmiResultInt64; "Wmi result int64 = %lld"
0x18000c855  mov     r8d, 71h ; 'q'
0x18000c85b  lea     rdx, aCompareresult; "CompareResult"
0x18000c862  mov     ecx, edi
0x18000c864  call    AslLogCallPrintf
0x18000c869  mov     r8, r12
0x18000c86c  mov     rdx, [rbp+arg_20]
0x18000c870  mov     rcx, [rbp+pllRet]
0x18000c874  call    ?CompareInt@AppCompatUtility@@YAH_J0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppCompatUtility::CompareInt(__int64,__int64,std::wstring const &)
0x18000c879  mov     [r15], eax
0x18000c87c  jmp     short loc_18000C834
0x18000c87e  movzx   eax, word ptr [r14]
0x18000c882  lea     r9, aWmiResultTypeI_0; "Wmi result type is not integer compatia"...
0x18000c889  mov     r8d, 58h ; 'X'
0x18000c88f  mov     dword ptr [rsp+78h+var_58], eax
0x18000c893  lea     rdx, aCompareresult; "CompareResult"
0x18000c89a  mov     ecx, 1
0x18000c89f  call    AslLogCallPrintf
0x18000c8a4  mov     rcx, [rbp+var_18]
0x18000c8a8  xor     rcx, rsp; StackCookie
0x18000c8ab  call    __security_check_cookie
0x18000c8b0  add     rsp, 78h
0x18000c8b4  pop     r15
0x18000c8b6  pop     r14
0x18000c8b8  pop     r13
0x18000c8ba  pop     r12
0x18000c8bc  pop     rdi
0x18000c8bd  pop     rsi
0x18000c8be  pop     rbx
0x18000c8bf  pop     rbp
0x18000c8c0  retn
```
