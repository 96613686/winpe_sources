# Parser::Tokenizer::matchGUID(void)

- ea: `0x1800039e0`
- end: `0x180003c35`
- name: `?matchGUID@Tokenizer@Parser@@AEAA?AW4TokenKind@12@XZ`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003280`

## callees

- `0x1800039e0`
- `0x180003d54`
- `0x18002d888`
- `0x180043496`
- `0x1800434ba`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b24`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003aad`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003aad`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180003a95`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180003a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800436b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800436b2`

## string_xrefs

- `0x180003b88`: `com\complus\src\events\queryengine\parser.cpp`
- `0x180003bc2`: `com\complus\src\events\queryengine\parser.cpp`

## pseudocode

```c
void __fastcall __noreturn Parser::Tokenizer::matchGUID(__int64 a1)
{
  _WORD *v2; // rbx
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // rdi
  LPOLESTR v5; // rax
  __int64 v6; // rdi
  int v7; // ecx
  LPVOID v8; // rax
  size_t v9; // rdi
  __int64 v10; // [rsp+0h] [rbp-C8h] BYREF
  LPOLESTR lpsz; // [rsp+20h] [rbp-A8h] BYREF
  _WORD *v12; // [rsp+28h] [rbp-A0h]
  __int64 *v13; // [rsp+30h] [rbp-98h]
  __int64 v14; // [rsp+38h] [rbp-90h]
  GUID pclsid; // [rsp+40h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-78h] BYREF

  v13 = &v10;
  lpsz = 0;
  v12 = 0;
  pclsid = 0;
  v2 = *(_WORD **)a1;
  while ( 1 )
  {
    v12 = ++v2;
    if ( *v2 == 125 )
      break;
    if ( !*v2 )
    {
      while ( 1 )
      {
        local_unwind_0(v13, &loc_180003C29);
LABEL_18:
        InternalError(L"com\\complus\\src\\events\\queryengine\\parser.cpp", 0x11Bu, 0xC0001204, 0x10u);
        v5 = lpsz;
        if ( lpsz )
        {
LABEL_9:
          v6 = -1;
          do
            ++v6;
          while ( v5[v6] );
        }
        else
        {
          v6 = 0;
        }
        v14 = v6;
        v7 = *(_DWORD *)(a1 + 28);
        if ( ((v7 - 8) & 0xFFFFFFFC) == 0 && v7 != 10 )
          CoTaskMemFree(*(LPVOID *)(a1 + 40));
        *(_QWORD *)(a1 + 24) = 9;
        *(_DWORD *)(a1 + 28) = 9;
        *(_QWORD *)(a1 + 32) = (int)v6;
        v8 = CoTaskMemAlloc(saturated_mul((int)v6 + 1LL, 2u));
        *(_QWORD *)(a1 + 40) = v8;
        if ( !v8 )
          InternalError(L"com\\complus\\src\\events\\queryengine\\parser.cpp", 0x122u, 0xC0001204, 0x10u);
        v9 = 2LL * (int)v6;
        memcpy_0(*(void **)(a1 + 40), lpsz, v9);
        *(_WORD *)(v9 + *(_QWORD *)(a1 + 40)) = 0;
        *(_QWORD *)a1 = v2;
        local_unwind_0(v13, &loc_180003BFB);
      }
    }
  }
  v12 = ++v2;
  v3 = ((__int64)v2 - *(_QWORD *)a1) >> 1;
  if ( v3 > 0x27 )
  {
    local_unwind_0(v13, &loc_180003C2D);
  }
  else
  {
    v4 = v3;
    memcpy_0(sz, *(const void **)a1, 2 * v3);
    if ( v4 >= 40 )
      goto LABEL_22;
    sz[v4] = 0;
    if ( CLSIDFromString(sz, &pclsid) >= 0 )
    {
      StringFromCLSID(&pclsid, &lpsz);
      v5 = lpsz;
      if ( lpsz )
        goto LABEL_9;
      goto LABEL_18;
    }
  }
  local_unwind_0(v13, &loc_180003C31);
LABEL_22:
  _report_rangecheckfailure();
}

```

## disassembly

```asm
0x1800039e0  mov     [rsp+arg_8], rbx
0x1800039e5  mov     [rsp+arg_10], rsi
0x1800039ea  push    rdi
0x1800039eb  push    r14
0x1800039ed  push    r15
0x1800039ef  sub     rsp, 0B0h
0x1800039f6  mov     rax, cs:__security_cookie
0x1800039fd  xor     rax, rsp
0x180003a00  mov     [rsp+0C8h+var_28], rax
0x180003a08  mov     [rsp+0C8h+var_98], rsp
0x180003a0d  mov     rsi, rcx
0x180003a10  xor     r15d, r15d
0x180003a13  mov     [rsp+0C8h+lpsz], r15
0x180003a18  mov     [rsp+0C8h+var_A0], r15
0x180003a1d  xorps   xmm0, xmm0
0x180003a20  movups  xmmword ptr [rsp+0C8h+pclsid.Data1], xmm0
0x180003a25  mov     rbx, [rcx]
0x180003a28  add     rbx, 2
0x180003a2c  mov     [rsp+0C8h+var_A0], rbx
0x180003a31  movzx   eax, word ptr [rbx]
0x180003a34  cmp     ax, 7Dh ; '}'
0x180003a38  jz      short loc_180003A4B
0x180003a3a  test    ax, ax
0x180003a3d  jz      short loc_180003A41
0x180003a3f  jmp     short loc_180003A28
0x180003a41  cmp     ax, 7Dh ; '}'
0x180003a45  jnz     loc_180003B66
0x180003a4b  add     rbx, 2
0x180003a4f  mov     [rsp+0C8h+var_A0], rbx
0x180003a54  mov     rdx, [rcx]; Src
0x180003a57  mov     rax, rbx
0x180003a5a  sub     rax, rdx
0x180003a5d  sar     rax, 1
0x180003a60  cmp     rax, 27h ; '''
0x180003a64  ja      loc_180003BD3
0x180003a6a  lea     rdi, [rax+rax]
0x180003a6e  mov     r8, rdi; Size
0x180003a71  lea     rcx, [rsp+0C8h+sz]; void *
0x180003a76  call    memcpy_0
0x180003a7b  cmp     rdi, 50h ; 'P'
0x180003a7f  jnb     loc_180003BF5
0x180003a85  mov     [rsp+rdi+0C8h+sz], r15w
0x180003a8b  lea     rdx, [rsp+0C8h+pclsid]; pclsid
0x180003a90  lea     rcx, [rsp+0C8h+sz]; lpsz
0x180003a95  call    cs:__imp_CLSIDFromString
0x180003a9b  test    eax, eax
0x180003a9d  js      loc_180003BE4
0x180003aa3  lea     rdx, [rsp+0C8h+lpsz]; lplpsz
0x180003aa8  lea     rcx, [rsp+0C8h+pclsid]; rclsid
0x180003aad  call    cs:__imp_StringFromCLSID
0x180003ab3  mov     rax, [rsp+0C8h+lpsz]
0x180003ab8  test    rax, rax
0x180003abb  jz      loc_180003B77
0x180003ac1  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180003ac8  mov     rdi, r14
0x180003acb  nop     dword ptr [rax+rax+00h]
0x180003ad0  inc     rdi
0x180003ad3  cmp     word ptr [rax+rdi*2], 0
0x180003ad8  jnz     short loc_180003AD0
0x180003ada  mov     [rsp+0C8h+var_90], rdi
0x180003adf  mov     ecx, [rsi+1Ch]
0x180003ae2  lea     eax, [rcx-8]
0x180003ae5  test    eax, 0FFFFFFFCh
0x180003aea  jnz     short loc_180003AFB
0x180003aec  cmp     ecx, 0Ah
0x180003aef  jz      short loc_180003AFB
0x180003af1  mov     rcx, [rsi+28h]; pv
0x180003af5  call    cs:__imp_CoTaskMemFree
0x180003afb  mov     qword ptr [rsi+18h], 9
0x180003b03  mov     dword ptr [rsi+1Ch], 9
0x180003b0a  movsxd  rdi, edi
0x180003b0d  mov     [rsi+20h], rdi
0x180003b11  lea     rcx, [rdi+1]
0x180003b15  mov     eax, 2
0x180003b1a  mul     rcx
0x180003b1d  cmovb   rax, r14
0x180003b21  mov     rcx, rax; cb
0x180003b24  call    cs:__imp_CoTaskMemAlloc
0x180003b2a  mov     [rsi+28h], rax
0x180003b2e  test    rax, rax
0x180003b31  jz      short loc_180003BB1
0x180003b33  add     rdi, rdi
0x180003b36  mov     r8, rdi; Size
0x180003b39  mov     rdx, [rsp+0C8h+lpsz]; Src
0x180003b3e  mov     rcx, [rsi+28h]; void *
0x180003b42  call    memcpy_0
0x180003b47  mov     rcx, [rsi+28h]
0x180003b4b  mov     eax, r15d
0x180003b4e  mov     [rdi+rcx], ax
0x180003b52  mov     [rsi], rbx
0x180003b55  lea     rdx, loc_180003BFB
0x180003b5c  mov     rcx, [rsp+0C8h+var_98]
0x180003b61  call    _local_unwind_0
0x180003b66  lea     rdx, loc_180003C29
0x180003b6d  mov     rcx, [rsp+0C8h+var_98]
0x180003b72  call    _local_unwind_0
0x180003b77  mov     edx, 11Bh; unsigned int
0x180003b7c  mov     r9d, 10h; unsigned __int16
0x180003b82  mov     r8d, 0C0001204h; unsigned int
0x180003b88  lea     rcx, aComComplusSrcE_12; "com\\complus\\src\\events\\queryengine"...
0x180003b8f  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180003b94  mov     rax, [rsp+0C8h+lpsz]
0x180003b99  test    rax, rax
0x180003b9c  jnz     loc_180003AC1
0x180003ba2  mov     rdi, r15
0x180003ba5  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180003bac  jmp     loc_180003ADA
0x180003bb1  mov     edx, 122h; unsigned int
0x180003bb6  mov     r9d, 10h; unsigned __int16
0x180003bbc  mov     r8d, 0C0001204h; unsigned int
0x180003bc2  lea     rcx, aComComplusSrcE_12; "com\\complus\\src\\events\\queryengine"...
0x180003bc9  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180003bce  jmp     loc_180003B33
0x180003bd3  lea     rdx, loc_180003C2D
0x180003bda  mov     rcx, [rsp+0C8h+var_98]
0x180003bdf  call    _local_unwind_0
0x180003be4  lea     rdx, loc_180003C31
0x180003beb  mov     rcx, [rsp+0C8h+var_98]
0x180003bf0  call    _local_unwind_0
0x180003bf5  call    __report_rangecheckfailure
0x180003bfb  mov     eax, 9
0x180003c00  mov     rcx, [rsp+18h+arg_80]
0x180003c08  xor     rcx, rsp; StackCookie
0x180003c0b  call    __security_check_cookie
0x180003c10  lea     r11, [rsp+18h+arg_90]
0x180003c18  mov     rbx, [r11+28h]
0x180003c1c  mov     rsi, [r11+30h]
0x180003c20  mov     rsp, r11
0x180003c23  pop     r15
0x180003c25  pop     r14
0x180003c27  pop     rdi
0x180003c28  retn
0x180003c29  xor     eax, eax
0x180003c2b  jmp     short loc_180003C00
0x180003c2d  xor     eax, eax
0x180003c2f  jmp     short loc_180003C00
0x180003c31  xor     eax, eax
0x180003c33  jmp     short loc_180003C00
0x1800436a0  push    rbp
0x1800436a2  sub     rsp, 20h
0x1800436a6  mov     rbp, rdx
0x1800436a9  mov     rcx, [rbp+20h]; pv
0x1800436ad  test    rcx, rcx
0x1800436b0  jz      short loc_1800436B9
0x1800436b2  call    cs:__imp_CoTaskMemFree
0x1800436b8  nop
0x1800436b9  add     rsp, 20h
0x1800436bd  pop     rbp
0x1800436be  retn
```
