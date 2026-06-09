# IkeCopyIkeV2Sa

- ea: `0x1800e0b80`
- end: `0x1800e1020`
- name: `IkeCopyIkeV2Sa`
- size: `1184`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800e1028`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180003c7c`
- `0x180003cf0`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x180077b6c`
- `0x1800c0b90`
- `0x1800e0b80`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x1800e0c5f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800e0c72`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800e0c5f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800e0c72`

## string_xrefs

- `0x1800e0d55`: `Copying and refing mobike context`
- `0x1800e0bb7`: `IkeCopyIkeV2Sa`
- `0x1800e0fdd`: `IkeCopyIkeV2Sa`
- `0x1800e0fe9`: `IkeCopyIkeV2Sa`

## pseudocode

```c
__int64 __fastcall IkeCopyIkeV2Sa(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // r15
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  const CERT_CONTEXT *v10; // rcx
  const CERT_CONTEXT *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r15
  __int64 v14; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int TlsMmLuid; // eax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  _OWORD *v27; // rax
  _OWORD *v28; // rcx
  __int64 v30; // [rsp+40h] [rbp-79h] BYREF
  __int64 v31; // [rsp+48h] [rbp-71h] BYREF
  __int64 v32; // [rsp+50h] [rbp-69h] BYREF
  __int64 v33; // [rsp+58h] [rbp-61h] BYREF
  char v34[32]; // [rsp+60h] [rbp-59h] BYREF
  __int64 *v35; // [rsp+80h] [rbp-39h]
  __int64 v36; // [rsp+88h] [rbp-31h]
  char v37[16]; // [rsp+90h] [rbp-29h] BYREF
  const char *v38; // [rsp+A0h] [rbp-19h]
  __int64 v39; // [rsp+A8h] [rbp-11h]
  __int64 *v40; // [rsp+B0h] [rbp-9h]
  __int64 v41; // [rsp+B8h] [rbp-1h]
  __int64 *v42; // [rsp+C0h] [rbp+7h]
  __int64 v43; // [rsp+C8h] [rbp+Fh]
  __int64 *v44; // [rsp+D0h] [rbp+17h]
  __int64 v45; // [rsp+D8h] [rbp+1Fh]

  TraceLogHelper("IkeCopyIkeV2Sa", 1);
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 1104) + 40LL);
  v5 = WfpMemAlloc(0x58u, 8u);
  if ( !v5 )
  {
    v6 = *(_QWORD *)(*(_QWORD *)(a2 + 1104) + 40LL);
    *(_DWORD *)(v6 + 24) = *(_DWORD *)(v4 + 24);
    *(_DWORD *)(v6 + 80) = *(_DWORD *)(v4 + 80);
    v5 = WfpBufferCopy(*(void **)(v4 + 56), *(unsigned int *)(v4 + 48));
    if ( !v5 )
    {
      *(_DWORD *)(v6 + 48) = *(_DWORD *)(v4 + 48);
      v5 = WfpBufferCopy(*(void **)(v4 + 72), *(unsigned int *)(v4 + 64));
      if ( !v5 )
      {
        *(_DWORD *)(v6 + 64) = *(_DWORD *)(v4 + 64);
        v10 = *(const CERT_CONTEXT **)(v4 + 32);
        if ( v10 )
          *(_QWORD *)(v6 + 32) = CertDuplicateCertificateContext(v10);
        v11 = *(const CERT_CONTEXT **)(v4 + 40);
        if ( v11 )
          *(_QWORD *)(v6 + 40) = CertDuplicateCertificateContext(v11);
        *(_DWORD *)(a2 + 592) |= 0x40000u;
        *(_DWORD *)(a1 + 592) &= ~0x40000u;
        v12 = *(_QWORD *)(a2 + 1104);
        *(_DWORD *)(v12 + 168) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 168LL);
        v13 = *(_QWORD *)(*(_QWORD *)(a1 + 1104) + 176LL);
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            TlsPeerAddr = IkeGetTlsPeerAddr(v12);
            TlsMmLuid = IkeGetTlsMmLuid(v17, v16, v18, v19);
            WPP_SF_iSqqq(
              v14,
              18,
              (unsigned int)WPP_639729265dbb3b0803814a57dbffdef8_Traceguids,
              TlsMmLuid,
              TlsPeerAddr,
              v13,
              a1,
              a2);
          }
          if ( (unsigned int)dword_180173278 > 4 )
          {
            v30 = IkeGetTlsMmLuid(v12, v7, v8, v9);
            v35 = &v30;
            v36 = 8;
            v22 = IkeGetTlsPeerAddr(v21);
            tlgCreate1Sz_wchar_t(v37, v22);
            v23 = *(_QWORD *)(a1 + 1104);
            v38 = "Copying and refing mobike context";
            v39 = 34;
            v24 = *(_QWORD *)(v23 + 176);
            v40 = &v31;
            v42 = &v32;
            v44 = &v33;
            v31 = v24;
            v41 = 8;
            v32 = a1;
            v43 = 8;
            v33 = a2;
            v45 = 8;
            tlgWriteTransfer_EtwEventWriteTransfer(
              (__int64)&dword_180173278,
              (unsigned __int8 *)&dword_18016127C,
              v25,
              v26,
              8,
              (__int64)v34);
          }
          *(_QWORD *)(*(_QWORD *)(a2 + 1104) + 176LL) = *(_QWORD *)(*(_QWORD *)(a1 + 1104) + 176LL);
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(a1 + 1104) + 176LL) + 248LL));
        }
        *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 280LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 280LL);
        *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 280LL) = 0;
        v27 = *(_OWORD **)(a1 + 1104);
        v28 = *(_OWORD **)(a2 + 1104);
        v28[18] = v27[18];
        v28[19] = v27[19];
        v28[20] = v27[20];
        *(_OWORD *)(*(_QWORD *)(a2 + 1104) + 296LL) = 0;
        v5 = WfpBufferCopy(
               *(void **)(*(_QWORD *)(a1 + 1104) + 304LL),
               *(unsigned int *)(*(_QWORD *)(a1 + 1104) + 296LL));
        if ( !v5 )
        {
          *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 296LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 296LL);
          *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 404LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 404LL);
          *(_QWORD *)(*(_QWORD *)(a2 + 1104) + 480LL) = *(_QWORD *)(*(_QWORD *)(a1 + 1104) + 480LL);
          *(_QWORD *)(*(_QWORD *)(a2 + 1104) + 488LL) = *(_QWORD *)(*(_QWORD *)(a1 + 1104) + 488LL);
          *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 500LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 500LL);
          *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 504LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 504LL);
          *(_QWORD *)(*(_QWORD *)(a2 + 1104) + 552LL) = *(_QWORD *)(*(_QWORD *)(a1 + 1104) + 552LL);
          *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 564LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 564LL);
          *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 568LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 568LL);
          *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 572LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 572LL);
          *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 576LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 576LL);
          if ( *(_QWORD *)(a1 + 520) )
            v5 = IkeCopyBlob(a2 + 512, a1 + 512);
        }
      }
    }
  }
  TraceLogHelper("IkeCopyIkeV2Sa", 0);
  return IkeReturnError(v5, "IkeCopyIkeV2Sa");
}

```

## disassembly

```asm
0x1800e0b80  mov     [rsp-8+arg_10], rbx
0x1800e0b85  mov     [rsp-8+arg_18], rsi
0x1800e0b8a  push    rbp
0x1800e0b8b  push    rdi
0x1800e0b8c  push    r13
0x1800e0b8e  push    r14
0x1800e0b90  push    r15
0x1800e0b92  lea     rbp, [rsp-37h]
0x1800e0b97  sub     rsp, 0F0h
0x1800e0b9e  mov     rax, cs:__security_cookie
0x1800e0ba5  xor     rax, rsp
0x1800e0ba8  mov     [rbp+57h+var_30], rax
0x1800e0bac  mov     r14, rdx
0x1800e0baf  mov     rsi, rcx
0x1800e0bb2  mov     edx, 1
0x1800e0bb7  lea     rcx, aIkecopyikev2sa; "IkeCopyIkeV2Sa"
0x1800e0bbe  call    TraceLogHelper
0x1800e0bc3  mov     rax, [rsi+450h]
0x1800e0bca  mov     r13d, 8
0x1800e0bd0  mov     r8, [r14+450h]
0x1800e0bd7  mov     edx, r13d; dwFlags
0x1800e0bda  add     r8, 28h ; '('
0x1800e0bde  mov     rbx, [rax+28h]
0x1800e0be2  lea     ecx, [r13+50h]; dwBytes
0x1800e0be6  call    WfpMemAlloc
0x1800e0beb  mov     rdi, rax
0x1800e0bee  test    rax, rax
0x1800e0bf1  jnz     loc_1800E0FDB
0x1800e0bf7  mov     rax, [r14+450h]
0x1800e0bfe  mov     r15, [rax+28h]
0x1800e0c02  mov     eax, [rbx+18h]
0x1800e0c05  mov     [r15+18h], eax
0x1800e0c09  lea     r9, [r15+38h]
0x1800e0c0d  mov     eax, [rbx+50h]
0x1800e0c10  mov     [r15+50h], eax
0x1800e0c14  mov     edx, [rbx+30h]; Size
0x1800e0c17  mov     rcx, [rbx+38h]; Src
0x1800e0c1b  call    WfpBufferCopy
0x1800e0c20  mov     rdi, rax
0x1800e0c23  test    rax, rax
0x1800e0c26  jnz     loc_1800E0FDB
0x1800e0c2c  mov     eax, [rbx+30h]
0x1800e0c2f  lea     r9, [r15+48h]
0x1800e0c33  mov     [r15+30h], eax
0x1800e0c37  mov     edx, [rbx+40h]; Size
0x1800e0c3a  mov     rcx, [rbx+48h]; Src
0x1800e0c3e  call    WfpBufferCopy
0x1800e0c43  mov     rdi, rax
0x1800e0c46  test    rax, rax
0x1800e0c49  jnz     loc_1800E0FDB
0x1800e0c4f  mov     eax, [rbx+40h]
0x1800e0c52  mov     [r15+40h], eax
0x1800e0c56  mov     rcx, [rbx+20h]; pCertContext
0x1800e0c5a  test    rcx, rcx
0x1800e0c5d  jz      short loc_1800E0C69
0x1800e0c5f  call    cs:__imp_CertDuplicateCertificateContext
0x1800e0c65  mov     [r15+20h], rax
0x1800e0c69  mov     rcx, [rbx+28h]; pCertContext
0x1800e0c6d  test    rcx, rcx
0x1800e0c70  jz      short loc_1800E0C7C
0x1800e0c72  call    cs:__imp_CertDuplicateCertificateContext
0x1800e0c78  mov     [r15+28h], rax
0x1800e0c7c  bts     dword ptr [r14+250h], 12h
0x1800e0c85  btr     dword ptr [rsi+250h], 12h
0x1800e0c8d  mov     rax, [rsi+450h]
0x1800e0c94  mov     rcx, [r14+450h]
0x1800e0c9b  mov     eax, [rax+0A8h]
0x1800e0ca1  mov     [rcx+0A8h], eax
0x1800e0ca7  mov     rax, [rsi+450h]
0x1800e0cae  mov     r15, [rax+0B0h]
0x1800e0cb5  test    r15, r15
0x1800e0cb8  jz      loc_1800E0DF1
0x1800e0cbe  mov     rdi, cs:WPP_GLOBAL_Control
0x1800e0cc5  lea     rax, WPP_GLOBAL_Control
0x1800e0ccc  cmp     rdi, rax
0x1800e0ccf  jz      short loc_1800E0D19
0x1800e0cd1  cmp     byte ptr [rdi+19h], 4
0x1800e0cd5  jb      short loc_1800E0D19
0x1800e0cd7  test    byte ptr [rdi+1Ch], 10h
0x1800e0cdb  jz      short loc_1800E0D19
0x1800e0cdd  mov     rdi, [rdi+10h]
0x1800e0ce1  call    IkeGetTlsPeerAddr
0x1800e0ce6  mov     rbx, rax
0x1800e0ce9  call    IkeGetTlsMmLuid
0x1800e0cee  mov     [rsp+110h+var_D8], r14
0x1800e0cf3  lea     r8, WPP_639729265dbb3b0803814a57dbffdef8_Traceguids
0x1800e0cfa  mov     [rsp+110h+var_E0], rsi
0x1800e0cff  mov     r9, rax
0x1800e0d02  mov     [rsp+110h+var_E8], r15
0x1800e0d07  mov     edx, 12h
0x1800e0d0c  mov     rcx, rdi
0x1800e0d0f  mov     [rsp+110h+var_F0], rbx
0x1800e0d14  call    WPP_SF_iSqqq
0x1800e0d19  mov     eax, cs:dword_180173278
0x1800e0d1f  cmp     eax, 4
0x1800e0d22  jbe     loc_1800E0DC0
0x1800e0d28  call    IkeGetTlsMmLuid
0x1800e0d2d  mov     [rbp+57h+var_D0], rax
0x1800e0d31  lea     rax, [rbp+57h+var_D0]
0x1800e0d35  mov     [rbp+57h+var_90], rax
0x1800e0d39  mov     [rbp+57h+var_88], r13
0x1800e0d3d  call    IkeGetTlsPeerAddr
0x1800e0d42  mov     rdx, rax
0x1800e0d45  lea     rcx, [rbp+57h+var_80]
0x1800e0d49  call    _tlgCreate1Sz_wchar_t
0x1800e0d4e  mov     rax, [rsi+450h]
0x1800e0d55  lea     rcx, aCopyingAndRefi; "Copying and refing mobike context"
0x1800e0d5c  mov     [rbp+57h+var_70], rcx
0x1800e0d60  lea     rdx, dword_18016127C
0x1800e0d67  mov     [rbp+57h+var_68], 22h ; '"'
0x1800e0d6f  mov     rcx, [rax+0B0h]
0x1800e0d76  lea     rax, [rbp+57h+var_C8]
0x1800e0d7a  mov     [rbp+57h+var_60], rax
0x1800e0d7e  lea     rax, [rbp+57h+var_C0]
0x1800e0d82  mov     [rbp+57h+var_50], rax
0x1800e0d86  lea     rax, [rbp+57h+var_B8]
0x1800e0d8a  mov     [rbp+57h+var_40], rax
0x1800e0d8e  lea     rax, [rbp+57h+var_B0]
0x1800e0d92  mov     [rbp+57h+var_C8], rcx
0x1800e0d96  lea     rcx, dword_180173278
0x1800e0d9d  mov     [rsp+110h+var_E8], rax
0x1800e0da2  mov     dword ptr [rsp+110h+var_F0], r13d
0x1800e0da7  mov     [rbp+57h+var_58], r13
0x1800e0dab  mov     [rbp+57h+var_C0], rsi
0x1800e0daf  mov     [rbp+57h+var_48], r13
0x1800e0db3  mov     [rbp+57h+var_B8], r14
0x1800e0db7  mov     [rbp+57h+var_38], r13
0x1800e0dbb  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800e0dc0  mov     rax, [rsi+450h]
0x1800e0dc7  mov     rcx, [r14+450h]
0x1800e0dce  mov     rax, [rax+0B0h]
0x1800e0dd5  mov     [rcx+0B0h], rax
0x1800e0ddc  mov     rax, [rsi+450h]
0x1800e0de3  mov     rcx, [rax+0B0h]
0x1800e0dea  lock inc dword ptr [rcx+0F8h]
0x1800e0df1  mov     rax, [rsi+450h]
0x1800e0df8  mov     rcx, [r14+450h]
0x1800e0dff  mov     eax, [rax+118h]
0x1800e0e05  mov     [rcx+118h], eax
0x1800e0e0b  mov     rax, [rsi+450h]
0x1800e0e12  mov     dword ptr [rax+118h], 0
0x1800e0e1c  mov     rax, [rsi+450h]
0x1800e0e23  mov     rcx, [r14+450h]
0x1800e0e2a  movups  xmm0, xmmword ptr [rax+120h]
0x1800e0e31  movups  xmmword ptr [rcx+120h], xmm0
0x1800e0e38  movups  xmm1, xmmword ptr [rax+130h]
0x1800e0e3f  movups  xmmword ptr [rcx+130h], xmm1
0x1800e0e46  movups  xmm0, xmmword ptr [rax+140h]
0x1800e0e4d  movups  xmmword ptr [rcx+140h], xmm0
0x1800e0e54  mov     rax, [r14+450h]
0x1800e0e5b  xorps   xmm0, xmm0
0x1800e0e5e  movups  xmmword ptr [rax+128h], xmm0
0x1800e0e65  mov     rcx, [rsi+450h]
0x1800e0e6c  mov     r9, [r14+450h]
0x1800e0e73  add     r9, 130h
0x1800e0e7a  mov     edx, [rcx+128h]; Size
0x1800e0e80  mov     rcx, [rcx+130h]; Src
0x1800e0e87  call    WfpBufferCopy
0x1800e0e8c  mov     rdi, rax
0x1800e0e8f  test    rax, rax
0x1800e0e92  jnz     loc_1800E0FDB
0x1800e0e98  mov     rax, [rsi+450h]
0x1800e0e9f  mov     rcx, [r14+450h]
0x1800e0ea6  mov     eax, [rax+128h]
0x1800e0eac  mov     [rcx+128h], eax
0x1800e0eb2  mov     rax, [rsi+450h]
0x1800e0eb9  mov     rcx, [r14+450h]
0x1800e0ec0  mov     eax, [rax+194h]
0x1800e0ec6  mov     [rcx+194h], eax
0x1800e0ecc  mov     rax, [rsi+450h]
0x1800e0ed3  mov     rcx, [r14+450h]
0x1800e0eda  mov     rax, [rax+1E0h]
0x1800e0ee1  mov     [rcx+1E0h], rax
0x1800e0ee8  mov     rax, [rsi+450h]
0x1800e0eef  mov     rcx, [r14+450h]
0x1800e0ef6  mov     rax, [rax+1E8h]
0x1800e0efd  mov     [rcx+1E8h], rax
0x1800e0f04  mov     rax, [rsi+450h]
0x1800e0f0b  mov     rcx, [r14+450h]
0x1800e0f12  mov     eax, [rax+1F4h]
0x1800e0f18  mov     [rcx+1F4h], eax
0x1800e0f1e  mov     rax, [rsi+450h]
0x1800e0f25  mov     rcx, [r14+450h]
0x1800e0f2c  mov     eax, [rax+1F8h]
0x1800e0f32  mov     [rcx+1F8h], eax
0x1800e0f38  mov     rax, [rsi+450h]
0x1800e0f3f  mov     rcx, [r14+450h]
0x1800e0f46  mov     rax, [rax+228h]
0x1800e0f4d  mov     [rcx+228h], rax
0x1800e0f54  mov     rax, [rsi+450h]
0x1800e0f5b  mov     rcx, [r14+450h]
0x1800e0f62  mov     eax, [rax+234h]
0x1800e0f68  mov     [rcx+234h], eax
0x1800e0f6e  mov     rax, [rsi+450h]
0x1800e0f75  mov     rcx, [r14+450h]
0x1800e0f7c  mov     eax, [rax+238h]
0x1800e0f82  mov     [rcx+238h], eax
0x1800e0f88  mov     rax, [rsi+450h]
0x1800e0f8f  mov     rcx, [r14+450h]
0x1800e0f96  mov     eax, [rax+23Ch]
0x1800e0f9c  mov     [rcx+23Ch], eax
0x1800e0fa2  mov     rax, [rsi+450h]
0x1800e0fa9  mov     rcx, [r14+450h]
0x1800e0fb0  mov     eax, [rax+240h]
0x1800e0fb6  mov     [rcx+240h], eax
0x1800e0fbc  cmp     [rsi+208h], rdi
0x1800e0fc3  jz      short loc_1800E0FDB
0x1800e0fc5  lea     rdx, [rsi+200h]
0x1800e0fcc  lea     rcx, [r14+200h]
0x1800e0fd3  call    IkeCopyBlob
0x1800e0fd8  mov     rdi, rax
0x1800e0fdb  xor     edx, edx
0x1800e0fdd  lea     rcx, aIkecopyikev2sa; "IkeCopyIkeV2Sa"
0x1800e0fe4  call    TraceLogHelper
0x1800e0fe9  lea     rdx, aIkecopyikev2sa; "IkeCopyIkeV2Sa"
0x1800e0ff0  mov     rcx, rdi
0x1800e0ff3  call    IkeReturnError
0x1800e0ff8  mov     rcx, [rbp+57h+var_30]
0x1800e0ffc  xor     rcx, rsp; StackCookie
0x1800e0fff  call    __security_check_cookie
0x1800e1004  lea     r11, [rsp+110h+var_20]
0x1800e100c  mov     rbx, [r11+40h]
0x1800e1010  mov     rsi, [r11+48h]
0x1800e1014  mov     rsp, r11
0x1800e1017  pop     r15
0x1800e1019  pop     r14
0x1800e101b  pop     r13
0x1800e101d  pop     rdi
0x1800e101e  pop     rbp
0x1800e101f  retn
```
