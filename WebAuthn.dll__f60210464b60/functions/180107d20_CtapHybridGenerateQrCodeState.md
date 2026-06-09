# CtapHybridGenerateQrCodeState

- ea: `0x180107d20`
- end: `0x180107ed4`
- name: `CtapHybridGenerateQrCodeState`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800aabc8`

## callees

- `0x18006b260`
- `0x18009b620`
- `0x180106ba4`
- `0x180106e98`
- `0x180107d20`
- `0x1801247e0`
- `0x180124844`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180107eb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180107eb4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180107e97`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180107e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107e46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107e7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107e46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107e7a`

## string_xrefs

- `0x180107d39`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CtapHybridGenerateQrCodeState(_QWORD *a1)
{
  _OWORD *v2; // rcx
  _OWORD *v3; // rax
  LPVOID v4; // rcx
  LPVOID v5; // rcx
  LPVOID v6; // rax
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  HLOCAL v10; // rbx
  SIZE_T v11; // rax
  _BYTE *i; // rcx
  const char *v13; // r9
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-18h] BYREF
  _OWORD *v16; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v18; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v20; // [rsp+50h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF

  try
  {
    if ( !a1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
        (const char *)0x80004003LL,
        v15);
    CtapHybridInternal::GenerateP256KeyPair(&v15);
    CtapHybridInternal::CreateSymetricSecret(&hMem);
    wil::make_unique_cotaskmem<_CTAPCBOR_RPC_HYBRID_QRCODE_STATE,>(&v18);
    wil::make_unique_cotaskmem<unsigned char [0]>(&v20, 104);
    v2 = v20;
    v3 = v16;
    *(_OWORD *)v20 = *v16;
    v2[1] = v3[1];
    v2[2] = v3[2];
    v2[3] = v3[3];
    v2[4] = v3[4];
    v2[5] = v3[5];
    *((_QWORD *)v2 + 12) = *((_QWORD *)v3 + 12);
    wil::make_unique_cotaskmem<unsigned char [0]>(&pv, 16);
    *(_OWORD *)pv = *(_OWORD *)hMem;
    v4 = v20;
    v20 = 0;
    *((_QWORD *)v18 + 1) = v4;
    *(_DWORD *)v18 = 104;
    v5 = pv;
    pv = 0;
    *((_QWORD *)v18 + 3) = v5;
    *((_DWORD *)v18 + 4) = 16;
    v6 = v18;
    v18 = 0;
    *a1 = v6;
    v7 = pv;
    pv = 0;
    if ( v7 )
      CoTaskMemFree(v7);
    v8 = v20;
    v20 = 0;
    if ( v8 )
      CoTaskMemFree(v8);
    v9 = v18;
    v18 = 0;
    if ( v9 )
      CoTaskMemFree(v9);
    v10 = hMem;
    hMem = 0;
    if ( v10 )
    {
      v11 = LocalSize(v10);
      for ( i = v10; v11; --v11 )
        *i++ = 0;
      LocalFree(v10);
    }
    std::tuple<wistd::unique_ptr<CtapHybridInternal::P256BCryptPrivateKey,wil::hlocal_secure_deleter>,wistd::unique_ptr<CtapHybridInternal::P256BCryptPublicKey,wil::hlocal_secure_deleter>>::~tuple<wistd::unique_ptr<CtapHybridInternal::P256BCryptPrivateKey,wil::hlocal_secure_deleter>,wistd::unique_ptr<CtapHybridInternal::P256BCryptPublicKey,wil::hlocal_secure_deleter>>(&v15);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x96,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180107d20  push    rbx
0x180107d22  sub     rsp, 30h
0x180107d26  mov     rbx, rcx
0x180107d29  mov     rcx, [rsp+38h]; this
0x180107d2e  test    rbx, rbx
0x180107d31  jnz     short loc_180107D4A
0x180107d33  mov     r9d, 80004003h; char *
0x180107d39  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180107d40  mov     edx, 81h; void *
0x180107d45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180107d4a  lea     rcx, [rsp+38h+var_18]
0x180107d4f  call    ?GenerateP256KeyPair@CtapHybridInternal@@YA?AV?$tuple@V?$unique_ptr@UP256BCryptPrivateKey@CtapHybridInternal@@Uhlocal_secure_deleter@wil@@@wistd@@V?$unique_ptr@UP256BCryptPublicKey@CtapHybridInternal@@Uhlocal_secure_deleter@wil@@@2@@std@@XZ; CtapHybridInternal::GenerateP256KeyPair(void)
0x180107d54  nop
0x180107d55  lea     rcx, [rsp+38h+hMem]
0x180107d5a  call    ?CreateSymetricSecret@CtapHybridInternal@@YA?AV?$unique_ptr@UQrSymetricSecret@CtapHybridInternal@@Uhlocal_secure_deleter@wil@@@wistd@@XZ; CtapHybridInternal::CreateSymetricSecret(void)
0x180107d5f  nop
0x180107d60  lea     rcx, [rsp+38h+arg_0]
0x180107d65  call    ??$make_unique_cotaskmem@U_CTAPCBOR_RPC_HYBRID_QRCODE_STATE@@$$V@wil@@YA?AV?$unique_ptr@U_CTAPCBOR_RPC_HYBRID_QRCODE_STATE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<_CTAPCBOR_RPC_HYBRID_QRCODE_STATE,>(void)
0x180107d6a  nop
0x180107d6b  mov     edx, 68h ; 'h'
0x180107d70  lea     rcx, [rsp+38h+arg_10]
0x180107d75  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x180107d7a  nop
0x180107d7b  mov     rcx, [rsp+38h+arg_10]
0x180107d80  mov     rax, [rsp+38h+var_10]
0x180107d85  movups  xmm0, xmmword ptr [rax]
0x180107d88  movups  xmmword ptr [rcx], xmm0
0x180107d8b  movups  xmm1, xmmword ptr [rax+10h]
0x180107d8f  movups  xmmword ptr [rcx+10h], xmm1
0x180107d93  movups  xmm0, xmmword ptr [rax+20h]
0x180107d97  movups  xmmword ptr [rcx+20h], xmm0
0x180107d9b  movups  xmm1, xmmword ptr [rax+30h]
0x180107d9f  movups  xmmword ptr [rcx+30h], xmm1
0x180107da3  movups  xmm0, xmmword ptr [rax+40h]
0x180107da7  movups  xmmword ptr [rcx+40h], xmm0
0x180107dab  movups  xmm1, xmmword ptr [rax+50h]
0x180107daf  movups  xmmword ptr [rcx+50h], xmm1
0x180107db3  movsd   xmm0, qword ptr [rax+60h]
0x180107db8  movsd   qword ptr [rcx+60h], xmm0
0x180107dbd  mov     edx, 10h
0x180107dc2  lea     rcx, [rsp+38h+pv]
0x180107dc7  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x180107dcc  mov     rax, [rsp+38h+hMem]
0x180107dd1  movups  xmm0, xmmword ptr [rax]
0x180107dd4  mov     rax, [rsp+38h+pv]
0x180107dd9  movdqu  xmmword ptr [rax], xmm0
0x180107ddd  mov     rcx, [rsp+38h+arg_10]
0x180107de2  mov     [rsp+38h+arg_10], 0
0x180107deb  mov     rax, [rsp+38h+arg_0]
0x180107df0  mov     [rax+8], rcx
0x180107df4  mov     rax, [rsp+38h+arg_0]
0x180107df9  mov     dword ptr [rax], 68h ; 'h'
0x180107dff  mov     rcx, [rsp+38h+pv]
0x180107e04  mov     [rsp+38h+pv], 0
0x180107e0d  mov     rax, [rsp+38h+arg_0]
0x180107e12  mov     [rax+18h], rcx
0x180107e16  mov     rax, [rsp+38h+arg_0]
0x180107e1b  mov     dword ptr [rax+10h], 10h
0x180107e22  mov     rax, [rsp+38h+arg_0]
0x180107e27  mov     [rsp+38h+arg_0], 0
0x180107e30  mov     [rbx], rax
0x180107e33  mov     rcx, [rsp+38h+pv]; pv
0x180107e38  mov     [rsp+38h+pv], 0
0x180107e41  test    rcx, rcx
0x180107e44  jz      short loc_180107E4D
0x180107e46  call    cs:__imp_CoTaskMemFree
0x180107e4c  nop
0x180107e4d  mov     rcx, [rsp+38h+arg_10]; pv
0x180107e52  mov     [rsp+38h+arg_10], 0
0x180107e5b  test    rcx, rcx
0x180107e5e  jz      short loc_180107E67
0x180107e60  call    cs:__imp_CoTaskMemFree
0x180107e66  nop
0x180107e67  mov     rcx, [rsp+38h+arg_0]; pv
0x180107e6c  mov     [rsp+38h+arg_0], 0
0x180107e75  test    rcx, rcx
0x180107e78  jz      short loc_180107E81
0x180107e7a  call    cs:__imp_CoTaskMemFree
0x180107e80  nop
0x180107e81  mov     rbx, [rsp+38h+hMem]
0x180107e86  mov     [rsp+38h+hMem], 0
0x180107e8f  test    rbx, rbx
0x180107e92  jz      short loc_180107EBB
0x180107e94  mov     rcx, rbx; hMem
0x180107e97  call    cs:__imp_LocalSize
0x180107e9d  mov     rcx, rbx
0x180107ea0  test    rax, rax
0x180107ea3  jz      short loc_180107EB1
0x180107ea5  mov     byte ptr [rcx], 0
0x180107ea8  inc     rcx
0x180107eab  sub     rax, 1
0x180107eaf  jnz     short loc_180107EA5
0x180107eb1  mov     rcx, rbx; hMem
0x180107eb4  call    cs:__imp_LocalFree
0x180107eba  nop
0x180107ebb  lea     rcx, [rsp+38h+var_18]
0x180107ec0  call    ??1?$tuple@V?$unique_ptr@UP256BCryptPrivateKey@CtapHybridInternal@@Uhlocal_secure_deleter@wil@@@wistd@@V?$unique_ptr@UP256BCryptPublicKey@CtapHybridInternal@@Uhlocal_secure_deleter@wil@@@2@@std@@QEAA@XZ; std::tuple<wistd::unique_ptr<CtapHybridInternal::P256BCryptPrivateKey,wil::hlocal_secure_deleter>,wistd::unique_ptr<CtapHybridInternal::P256BCryptPublicKey,wil::hlocal_secure_deleter>>::~tuple<wistd::unique_ptr<CtapHybridInternal::P256BCryptPrivateKey,wil::hlocal_secure_deleter>,wistd::unique_ptr<CtapHybridInternal::P256BCryptPublicKey,wil::hlocal_secure_deleter>>(void)
0x180107ec5  xor     eax, eax
0x180107ec7  jmp     short loc_180107ECD
0x180107ec9  mov     eax, dword ptr [rsp+38h+arg_0]
0x180107ecd  add     rsp, 30h
0x180107ed1  pop     rbx
0x180107ed2  retn
```
