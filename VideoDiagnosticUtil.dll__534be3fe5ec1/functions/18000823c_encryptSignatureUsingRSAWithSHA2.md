# encryptSignatureUsingRSAWithSHA2

- ea: `0x18000823c`
- end: `0x180008359`
- name: `encryptSignatureUsingRSAWithSHA2`
- size: `285`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800078e4`

## callees

- `0x18000823c`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800082c9`
- `ole32!CoTaskMemAlloc` at `0x1800082c9`
- `ole32!CoTaskMemFree` at `0x18000833d`
- `ole32!CoTaskMemFree` at `0x18000833d`
- `bcrypt!BCryptEncrypt` at `0x1800082b0`
- `bcrypt!BCryptEncrypt` at `0x180008323`
- `bcrypt!BCryptEncrypt` at `0x1800082b0`
- `bcrypt!BCryptEncrypt` at `0x180008323`

## pseudocode

```c
__int64 __fastcall encryptSignatureUsingRSAWithSHA2(
        PUCHAR pbInput,
        __int64 a2,
        ULONG *a3,
        UCHAR **a4,
        BCRYPT_KEY_HANDLE *a5)
{
  BCRYPT_KEY_HANDLE *v5; // r15
  UCHAR *pbOutput; // rbx
  NTSTATUS v10; // edi
  const wchar_t *pPaddingInfo; // [rsp+50h] [rbp-58h] BYREF
  __int128 v13; // [rsp+58h] [rbp-50h]
  SIZE_T cb; // [rsp+B8h] [rbp+10h] BYREF

  v5 = a5;
  pbOutput = 0;
  *a3 = 0;
  v13 = 0;
  pPaddingInfo = L"SHA512";
  LODWORD(cb) = 0;
  v10 = BCryptEncrypt(*v5, pbInput, 0x28u, &pPaddingInfo, 0, 0, 0, 0, (ULONG *)&cb, 4u);
  if ( v10 >= 0 )
  {
    pbOutput = (UCHAR *)CoTaskMemAlloc((unsigned int)cb);
    if ( pbOutput )
    {
      v10 = BCryptEncrypt(*v5, pbInput, 0x28u, &pPaddingInfo, 0, 0, pbOutput, cb, a3, 4u);
      if ( v10 >= 0 )
      {
        *a4 = pbOutput;
        pbOutput = 0;
      }
    }
    else
    {
      v10 = -2147024882;
    }
  }
  CoTaskMemFree(pbOutput);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000823c  mov     dword ptr [rsp+cb], edx
0x180008240  mov     r11, rsp
0x180008243  push    rbx
0x180008244  push    rbp
0x180008245  push    rsi
0x180008246  push    rdi
0x180008247  push    r14
0x180008249  push    r15
0x18000824b  sub     rsp, 78h
0x18000824f  mov     r15, [rsp+0A8h+arg_20]
0x180008257  lea     rax, aSha512; "SHA512"
0x18000825e  xor     ebx, ebx
0x180008260  mov     [rsp+0A8h+dwFlags], 4; dwFlags
0x180008268  mov     [r8], ebx
0x18000826b  xorps   xmm0, xmm0
0x18000826e  movdqu  [rsp+0A8h+var_50], xmm0
0x180008274  mov     [r11-58h], rax
0x180008278  mov     rsi, r9
0x18000827b  lea     rax, [r11+10h]
0x18000827f  mov     dword ptr [r11+10h], 0
0x180008287  mov     [r11-68h], rax
0x18000828b  lea     r9, [r11-58h]; pPaddingInfo
0x18000828f  mov     [rsp+0A8h+cbOutput], ebx; cbOutput
0x180008293  mov     r14, r8
0x180008296  mov     [r11-78h], rbx
0x18000829a  lea     r8d, [rbx+28h]; cbInput
0x18000829e  mov     rbp, rcx
0x1800082a1  mov     [rsp+0A8h+cbIV], ebx; cbIV
0x1800082a5  mov     rdx, rcx; pbInput
0x1800082a8  mov     [rsp+0A8h+pbIV], rbx; pbIV
0x1800082ad  mov     rcx, [r15]; hKey
0x1800082b0  call    cs:__imp_BCryptEncrypt
0x1800082b7  nop     dword ptr [rax+rax+00h]
0x1800082bc  mov     edi, eax
0x1800082be  test    eax, eax
0x1800082c0  js      short loc_18000833A
0x1800082c2  mov     ecx, dword ptr [rsp+0A8h+cb]; cb
0x1800082c9  call    cs:__imp_CoTaskMemAlloc
0x1800082d0  nop     dword ptr [rax+rax+00h]
0x1800082d5  mov     rbx, rax
0x1800082d8  test    rax, rax
0x1800082db  jnz     short loc_1800082E4
0x1800082dd  mov     edi, 8007000Eh
0x1800082e2  jmp     short loc_18000833A
0x1800082e4  mov     eax, dword ptr [rsp+0A8h+cb]
0x1800082eb  lea     r9, [rsp+0A8h+pPaddingInfo]; pPaddingInfo
0x1800082f0  mov     rcx, [r15]; hKey
0x1800082f3  mov     r8d, 28h ; '('; cbInput
0x1800082f9  mov     [rsp+0A8h+dwFlags], 4; dwFlags
0x180008301  mov     rdx, rbp; pbInput
0x180008304  mov     [rsp+0A8h+pcbResult], r14; pcbResult
0x180008309  mov     [rsp+0A8h+cbOutput], eax; cbOutput
0x18000830d  mov     [rsp+0A8h+pbOutput], rbx; pbOutput
0x180008312  mov     [rsp+0A8h+cbIV], 0; cbIV
0x18000831a  mov     [rsp+0A8h+pbIV], 0; pbIV
0x180008323  call    cs:__imp_BCryptEncrypt
0x18000832a  nop     dword ptr [rax+rax+00h]
0x18000832f  mov     edi, eax
0x180008331  test    eax, eax
0x180008333  js      short loc_18000833A
0x180008335  mov     [rsi], rbx
0x180008338  xor     ebx, ebx
0x18000833a  mov     rcx, rbx; pv
0x18000833d  call    cs:__imp_CoTaskMemFree
0x180008344  nop     dword ptr [rax+rax+00h]
0x180008349  mov     eax, edi
0x18000834b  add     rsp, 78h
0x18000834f  pop     r15
0x180008351  pop     r14
0x180008353  pop     rdi
0x180008354  pop     rsi
0x180008355  pop     rbp
0x180008356  pop     rbx
0x180008357  retn
```
