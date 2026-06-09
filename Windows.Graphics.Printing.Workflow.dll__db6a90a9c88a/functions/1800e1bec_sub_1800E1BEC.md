# sub_1800E1BEC

- ea: `0x1800e1bec`
- end: `0x1800e1f2b`
- name: `sub_1800E1BEC`
- size: `831`
- prototype: `__int64 __fastcall(DWORD *, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x1800dbf3c`
- `0x1800e22c8`

## callees

- `0x1800069c0`
- `0x180007554`
- `0x180018a10`
- `0x18001e200`
- `0x18001e224`
- `0x180029bec`
- `0x180029c0c`
- `0x180029ffc`
- `0x180046608`
- `0x1800677d4`
- `0x18009e20c`
- `0x1800d9f10`
- `0x1800de69c`
- `0x1800e0854`
- `0x1800e08a0`
- `0x1800e119c`
- `0x1800e1bec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800e1d6f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800e1d6f`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800e1c2e`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800e1c2e`
- `WINHTTP!WinHttpReadData` at `0x1800e1cb6`
- `WINHTTP!WinHttpReadData` at `0x1800e1cb6`

## string_xrefs

- `0x1800e1edc`: `Error reading HTTP response body: 0x%x, HttpRequestId: %d`
- `0x1800e1dc0`: `PrintCore::HttpRestChannel::_ReadHttpResponse`
- `0x1800e1ea2`: `PrintCore::HttpRestChannel::_ReadHttpResponse`
- `0x1800e1eec`: `PrintCore::HttpRestChannel::_ReadHttpResponse`

## pseudocode

```c
__int64 __fastcall sub_1800E1BEC(DWORD *a1, __int64 a2, __int64 *a3)
{
  unsigned int v6; // eax
  const wchar_t *v7; // rdx
  unsigned __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // r14
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r14
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  size_t v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // r14d
  unsigned int v24; // esi
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  unsigned int v29; // ebx
  __int64 v30; // [rsp+20h] [rbp-F8h]
  DWORD dwNumberOfBytesRead; // [rsp+40h] [rbp-D8h] BYREF
  unsigned int v32; // [rsp+44h] [rbp-D4h]
  int v33; // [rsp+48h] [rbp-D0h]
  DWORD *v34; // [rsp+50h] [rbp-C8h]
  __int64 v35; // [rsp+58h] [rbp-C0h]
  _BYTE v36[32]; // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v37[32]; // [rsp+80h] [rbp-98h] BYREF
  _BYTE v38[32]; // [rsp+A0h] [rbp-78h] BYREF
  _BYTE v39[32]; // [rsp+C0h] [rbp-58h] BYREF

  v34 = a1;
  v35 = a2;
  if ( !WinHttpReceiveResponse(**(HINTERNET **)(a2 + 32), 0) )
  {
    v6 = sub_1800DE69C();
    v7 = L"Error receiving HTTP response: 0x%x, HttpRequestId: %d";
LABEL_25:
    v29 = v6;
    sub_1800E08A0("PrintCore::HttpRestChannel::_ReadHttpResponse", v7, v6, *(unsigned int *)(a2 + 80));
    sub_1800D9F10(a2);
    return v29;
  }
  LODWORD(v8) = 0;
  dwNumberOfBytesRead = 0;
  do
  {
    v9 = *a3;
    v10 = a3[1];
    v11 = *a1;
    v12 = v10 + v11 - *a3;
    v13 = v10 - *a3;
    if ( v12 >= v13 )
    {
      if ( v12 <= v13 )
        goto LABEL_11;
      if ( v12 > a3[2] - v9 )
      {
        sub_18009E20C(a3);
        goto LABEL_11;
      }
      memset((void *)a3[1], 0, *a1);
      v14 = v11 + v10;
    }
    else
    {
      v14 = v12 + v9;
    }
    a3[1] = v14;
LABEL_11:
    if ( !WinHttpReadData(**(HINTERNET **)(a2 + 32), (LPVOID)(*a3 + (unsigned int)v8), *a1, &dwNumberOfBytesRead) )
    {
      v6 = sub_1800DE69C();
      v7 = L"Error reading HTTP response body: 0x%x, HttpRequestId: %d";
      goto LABEL_25;
    }
    v8 = dwNumberOfBytesRead + (unsigned int)v8;
  }
  while ( dwNumberOfBytesRead );
  v15 = *a3;
  v16 = a3[1];
  v17 = v16 - *a3;
  if ( v8 < v17 )
  {
    v18 = v15 + v8;
    goto LABEL_19;
  }
  if ( v8 > v17 )
  {
    if ( v8 <= a3[2] - v15 )
    {
      v19 = v8 - v17;
      memset((void *)a3[1], 0, v19);
      v18 = v19 + v16;
LABEL_19:
      a3[1] = v18;
    }
    else
    {
      sub_18009E20C(a3);
    }
  }
  sub_18001E224(v37, &psz);
  sub_1800E119C(v20, v39, a2, 19, v37);
  sub_180029FFC(v37);
  v21 = sub_180029C0C(v39);
  v22 = o__wtoi(v21);
  v23 = v22;
  v33 = v22;
  if ( v22 < 200 || (v24 = 0, v32 = 0, v22 >= 300) )
  {
    sub_1800677D4(v36, *a3, a3[1]);
    v25 = sub_180029BEC(v36);
    LODWORD(v30) = *(_DWORD *)(a2 + 80);
    sub_1800E08A0(
      "PrintCore::HttpRestChannel::_ReadHttpResponse",
      L"Error: server returned http status code %d and response: %S, HttpRequestId: %d",
      v23,
      v25,
      v30);
    v24 = v23 | 0x80190000;
    v32 = v23 | 0x80190000;
    sub_180018A10(v36);
  }
  sub_18001E200(v38);
  sub_18001E224(v36, L"X-MSEdge-Ref");
  v27 = sub_1800E119C(v26, v37, a2, 0xFFFF, v36);
  sub_180046608(v38, v27);
  sub_180029FFC(v37);
  sub_180029FFC(v36);
  sub_180029C0C(a2 + 48);
  sub_180029C0C(a1 + 2);
  sub_180029C0C(v38);
  sub_1800E0854(
    "PrintCore::HttpRestChannel::_ReadHttpResponse",
    L"HTTPStatusCode: %d, Request: %s %s, HttpRequestId: %d, Response TraceId: %s",
    v23);
  sub_180029FFC(v38);
  sub_180029FFC(v39);
  sub_1800D9F10(a2);
  return v24;
}

```

## disassembly

```asm
0x1800e1bec  mov     [rsp+arg_18], rbx
0x1800e1bf1  push    rsi
0x1800e1bf2  push    rdi
0x1800e1bf3  push    r12
0x1800e1bf5  push    r14
0x1800e1bf7  push    r15
0x1800e1bf9  sub     rsp, 0F0h
0x1800e1c00  mov     rax, cs:__security_cookie
0x1800e1c07  xor     rax, rsp
0x1800e1c0a  mov     [rsp+118h+var_38], rax
0x1800e1c12  mov     rbx, r8
0x1800e1c15  mov     rdi, rdx
0x1800e1c18  mov     r12, rcx
0x1800e1c1b  mov     [rsp+118h+var_C8], rcx
0x1800e1c20  mov     [rsp+118h+var_C0], rdx
0x1800e1c25  mov     rcx, [rdx+20h]
0x1800e1c29  xor     edx, edx; lpReserved
0x1800e1c2b  mov     rcx, [rcx]; hRequest
0x1800e1c2e  call    cs:WinHttpReceiveResponse
0x1800e1c34  test    eax, eax
0x1800e1c36  jnz     short loc_1800E1C49
0x1800e1c38  call    sub_1800DE69C
0x1800e1c3d  lea     rdx, aErrorReceiving; "Error receiving HTTP response: 0x%x, Ht"...
0x1800e1c44  jmp     loc_1800E1EE3
0x1800e1c49  xor     esi, esi
0x1800e1c4b  mov     [rsp+118h+dwNumberOfBytesRead], esi
0x1800e1c4f  mov     rcx, [rbx]
0x1800e1c52  mov     r14, [rbx+8]
0x1800e1c56  mov     r15d, [r12]
0x1800e1c5a  mov     edx, r15d
0x1800e1c5d  sub     rdx, rcx
0x1800e1c60  add     rdx, r14
0x1800e1c63  mov     rax, r14
0x1800e1c66  sub     rax, rcx
0x1800e1c69  cmp     rdx, rax
0x1800e1c6c  jnb     short loc_1800E1C74
0x1800e1c6e  lea     rax, [rdx+rcx]
0x1800e1c72  jmp     short loc_1800E1C9D
0x1800e1c74  jbe     short loc_1800E1CA1
0x1800e1c76  mov     rax, [rbx+10h]
0x1800e1c7a  sub     rax, rcx
0x1800e1c7d  cmp     rdx, rax
0x1800e1c80  jbe     short loc_1800E1C8C
0x1800e1c82  mov     rcx, rbx
0x1800e1c85  call    sub_18009E20C
0x1800e1c8a  jmp     short loc_1800E1CA1
0x1800e1c8c  mov     r8, r15; Size
0x1800e1c8f  xor     edx, edx; Val
0x1800e1c91  mov     rcx, r14; void *
0x1800e1c94  call    memset
0x1800e1c99  lea     rax, [r15+r14]
0x1800e1c9d  mov     [rbx+8], rax
0x1800e1ca1  mov     edx, esi
0x1800e1ca3  add     rdx, [rbx]; lpBuffer
0x1800e1ca6  mov     rcx, [rdi+20h]
0x1800e1caa  lea     r9, [rsp+118h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800e1caf  mov     r8d, [r12]; dwNumberOfBytesToRead
0x1800e1cb3  mov     rcx, [rcx]; hRequest
0x1800e1cb6  call    cs:WinHttpReadData
0x1800e1cbc  test    eax, eax
0x1800e1cbe  jz      loc_1800E1ED7
0x1800e1cc4  mov     eax, [rsp+118h+dwNumberOfBytesRead]
0x1800e1cc8  add     esi, eax
0x1800e1cca  test    eax, eax
0x1800e1ccc  jnz     short loc_1800E1C4F
0x1800e1cce  mov     rdx, [rbx]
0x1800e1cd1  mov     r14, [rbx+8]
0x1800e1cd5  mov     rcx, r14
0x1800e1cd8  sub     rcx, rdx
0x1800e1cdb  cmp     rsi, rcx
0x1800e1cde  jnb     short loc_1800E1CE6
0x1800e1ce0  lea     rax, [rdx+rsi]
0x1800e1ce4  jmp     short loc_1800E1D15
0x1800e1ce6  jbe     short loc_1800E1D19
0x1800e1ce8  mov     rax, [rbx+10h]
0x1800e1cec  sub     rax, rdx
0x1800e1cef  cmp     rsi, rax
0x1800e1cf2  jbe     short loc_1800E1D01
0x1800e1cf4  mov     rdx, rsi
0x1800e1cf7  mov     rcx, rbx
0x1800e1cfa  call    sub_18009E20C
0x1800e1cff  jmp     short loc_1800E1D19
0x1800e1d01  sub     rsi, rcx
0x1800e1d04  mov     r8, rsi; Size
0x1800e1d07  xor     edx, edx; Val
0x1800e1d09  mov     rcx, r14; void *
0x1800e1d0c  call    memset
0x1800e1d11  lea     rax, [rsi+r14]
0x1800e1d15  mov     [rbx+8], rax
0x1800e1d19  lea     rdx, psz
0x1800e1d20  lea     rcx, [rsp+118h+var_98]
0x1800e1d28  call    sub_18001E224
0x1800e1d2d  nop
0x1800e1d2e  lea     rax, [rsp+118h+var_98]
0x1800e1d36  mov     [rsp+118h+var_F8], rax
0x1800e1d3b  mov     r9d, 13h
0x1800e1d41  mov     r8, rdi
0x1800e1d44  lea     rdx, [rsp+118h+var_58]
0x1800e1d4c  call    sub_1800E119C
0x1800e1d51  nop
0x1800e1d52  lea     rcx, [rsp+118h+var_98]
0x1800e1d5a  call    sub_180029FFC
0x1800e1d5f  lea     rcx, [rsp+118h+var_58]
0x1800e1d67  call    sub_180029C0C
0x1800e1d6c  mov     rcx, rax
0x1800e1d6f  call    cs:_o__wtoi
0x1800e1d75  mov     r14d, eax
0x1800e1d78  mov     [rsp+118h+var_D0], eax
0x1800e1d7c  cmp     eax, 0C8h
0x1800e1d81  jl      short loc_1800E1D90
0x1800e1d83  xor     esi, esi
0x1800e1d85  mov     [rsp+118h+var_D4], esi
0x1800e1d89  cmp     eax, 12Ch
0x1800e1d8e  jl      short loc_1800E1DE3
0x1800e1d90  mov     r8, [rbx+8]
0x1800e1d94  mov     rdx, [rbx]
0x1800e1d97  lea     rcx, [rsp+118h+var_B8]
0x1800e1d9c  call    sub_1800677D4
0x1800e1da1  nop
0x1800e1da2  lea     rcx, [rsp+118h+var_B8]
0x1800e1da7  call    sub_180029BEC
0x1800e1dac  mov     r9, rax
0x1800e1daf  mov     eax, [rdi+50h]
0x1800e1db2  mov     dword ptr [rsp+118h+var_F8], eax
0x1800e1db6  mov     r8d, r14d
0x1800e1db9  lea     rdx, aErrorServerRet; "Error: server returned http status code"...
0x1800e1dc0  lea     rcx, aPrintcoreHttpr_4; "PrintCore::HttpRestChannel::_ReadHttpRe"...
0x1800e1dc7  call    sub_1800E08A0
0x1800e1dcc  mov     esi, r14d
0x1800e1dcf  or      esi, 80190000h
0x1800e1dd5  mov     [rsp+118h+var_D4], esi
0x1800e1dd9  lea     rcx, [rsp+118h+var_B8]
0x1800e1dde  call    sub_180018A10
0x1800e1de3  lea     rcx, [rsp+118h+var_78]
0x1800e1deb  call    sub_18001E200
0x1800e1df0  nop
0x1800e1df1  lea     rdx, aXMsedgeRef; "X-MSEdge-Ref"
0x1800e1df8  lea     rcx, [rsp+118h+var_B8]
0x1800e1dfd  call    sub_18001E224
0x1800e1e02  nop
0x1800e1e03  lea     rax, [rsp+118h+var_B8]
0x1800e1e08  mov     [rsp+118h+var_F8], rax
0x1800e1e0d  mov     r9d, 0FFFFh
0x1800e1e13  mov     r8, rdi
0x1800e1e16  lea     rdx, [rsp+118h+var_98]
0x1800e1e1e  call    sub_1800E119C
0x1800e1e23  mov     rdx, rax
0x1800e1e26  lea     rcx, [rsp+118h+var_78]
0x1800e1e2e  call    sub_180046608
0x1800e1e33  lea     rcx, [rsp+118h+var_98]
0x1800e1e3b  call    sub_180029FFC
0x1800e1e40  nop
0x1800e1e41  lea     rcx, [rsp+118h+var_B8]
0x1800e1e46  call    sub_180029FFC
0x1800e1e4b  nop
0x1800e1e4c  jmp     short loc_1800E1E61
0x1800e1e4e  mov     esi, [rsp+118h+var_D4]
0x1800e1e52  mov     r14d, [rsp+118h+var_D0]
0x1800e1e57  mov     rdi, [rsp+118h+var_C0]
0x1800e1e5c  mov     r12, [rsp+118h+var_C8]
0x1800e1e61  lea     rcx, [rdi+30h]
0x1800e1e65  call    sub_180029C0C
0x1800e1e6a  mov     rdx, rax
0x1800e1e6d  lea     rcx, [r12+8]
0x1800e1e72  call    sub_180029C0C
0x1800e1e77  mov     r9, rax
0x1800e1e7a  lea     rcx, [rsp+118h+var_78]
0x1800e1e82  call    sub_180029C0C
0x1800e1e87  mov     [rsp+118h+var_E8], rax
0x1800e1e8c  mov     ecx, [rdi+50h]
0x1800e1e8f  mov     [rsp+118h+var_F0], ecx
0x1800e1e93  mov     [rsp+118h+var_F8], rdx
0x1800e1e98  mov     r8d, r14d
0x1800e1e9b  lea     rdx, aHttpstatuscode; "HTTPStatusCode: %d, Request: %s %s, Htt"...
0x1800e1ea2  lea     rcx, aPrintcoreHttpr_4; "PrintCore::HttpRestChannel::_ReadHttpRe"...
0x1800e1ea9  call    sub_1800E0854
0x1800e1eae  nop
0x1800e1eaf  lea     rcx, [rsp+118h+var_78]
0x1800e1eb7  call    sub_180029FFC
0x1800e1ebc  nop
0x1800e1ebd  lea     rcx, [rsp+118h+var_58]
0x1800e1ec5  call    sub_180029FFC
0x1800e1eca  nop
0x1800e1ecb  mov     rcx, rdi
0x1800e1ece  call    sub_1800D9F10
0x1800e1ed3  mov     eax, esi
0x1800e1ed5  jmp     short loc_1800E1F03
0x1800e1ed7  call    sub_1800DE69C
0x1800e1edc  lea     rdx, aErrorReadingHt; "Error reading HTTP response body: 0x%x,"...
0x1800e1ee3  mov     ebx, eax
0x1800e1ee5  mov     r9d, [rdi+50h]
0x1800e1ee9  mov     r8d, eax
0x1800e1eec  lea     rcx, aPrintcoreHttpr_4; "PrintCore::HttpRestChannel::_ReadHttpRe"...
0x1800e1ef3  call    sub_1800E08A0
0x1800e1ef8  nop
0x1800e1ef9  mov     rcx, rdi
0x1800e1efc  call    sub_1800D9F10
0x1800e1f01  mov     eax, ebx
0x1800e1f03  mov     rcx, [rsp+118h+var_38]
0x1800e1f0b  xor     rcx, rsp; StackCookie
0x1800e1f0e  call    __security_check_cookie
0x1800e1f13  mov     rbx, [rsp+118h+arg_18]
0x1800e1f1b  add     rsp, 0F0h
0x1800e1f22  pop     r15
0x1800e1f24  pop     r14
0x1800e1f26  pop     r12
0x1800e1f28  pop     rdi
0x1800e1f29  pop     rsi
0x1800e1f2a  retn
```
