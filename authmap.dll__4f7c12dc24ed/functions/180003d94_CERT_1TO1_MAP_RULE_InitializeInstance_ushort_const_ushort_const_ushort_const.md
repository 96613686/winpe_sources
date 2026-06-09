# CERT_1TO1_MAP_RULE::InitializeInstance(ushort const *,ushort const *,ushort const *)

- ea: `0x180003d94`
- end: `0x180003f36`
- name: `?InitializeInstance@CERT_1TO1_MAP_RULE@@QEAAJPEBG00@Z`
- size: `418`
- prototype: `__int64 __fastcall(CERT_1TO1_MAP_RULE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800041f0`

## callees

- `0x180003d94`
- `0x180006d92`
- `0x180006dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ec1`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003de3`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003de3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003f0f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003f0f`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003e6d`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003e6d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003e25`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003e42`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003e25`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003e42`
- `iisutil!EncryptMemoryPassword` at `0x180003e55`
- `iisutil!EncryptMemoryPassword` at `0x180003e55`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f04`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f04`
- `iisutil!uudecode` at `0x180003e8f`
- `iisutil!uudecode` at `0x180003e8f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180003ef3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180003ef3`
- `CRYPT32!CertCreateCertificateContext` at `0x180003eaf`
- `CRYPT32!CertCreateCertificateContext` at `0x180003eaf`

## pseudocode

```c
__int64 __fastcall CERT_1TO1_MAP_RULE::InitializeInstance(
        CERT_1TO1_MAP_RULE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // ebx
  const CERT_CONTEXT *CertificateContext; // rax
  signed int LastError; // eax
  DWORD cbCertEncoded; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pcbData; // [rsp+24h] [rbp-DCh] BYREF
  _BYTE v14[32]; // [rsp+28h] [rbp-D8h] BYREF
  BYTE *pbCertEncoded; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+50h] [rbp-B0h]
  __int16 v17; // [rsp+54h] [rbp-ACh]
  _BYTE v18[32]; // [rsp+58h] [rbp-A8h] BYREF
  char *v19; // [rsp+78h] [rbp-88h]
  char v20; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v21[703]; // [rsp+91h] [rbp-6Fh] BYREF
  char v22[1008]; // [rsp+350h] [rbp+250h] BYREF

  pcbData = 0;
  STRA::STRA((STRA *)v18, v22, 0x3E8u);
  memset_0(v21, 0, sizeof(v21));
  v20 = 0;
  pbCertEncoded = (BYTE *)&v20;
  v16 = 704;
  v17 = 256;
  cbCertEncoded = 0;
  v8 = STRU::Copy((CERT_1TO1_MAP_RULE *)((char *)this + 8), a3);
  if ( v8 >= 0 )
  {
    v8 = STRU::Copy((CERT_1TO1_MAP_RULE *)((char *)this + 128), a4);
    if ( v8 >= 0 )
    {
      v8 = EncryptMemoryPassword((CERT_1TO1_MAP_RULE *)((char *)this + 128));
      if ( v8 >= 0 )
      {
        v8 = STRA::CopyW((STRA *)v18, a2);
        if ( v8 >= 0 )
        {
          if ( uudecode(v19, (struct BUFFER *)v14, &cbCertEncoded, 0) )
          {
            CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
            *((_QWORD *)this + 34) = CertificateContext;
            if ( CertificateContext
              && (pcbData = 20, CertGetCertificateContextProperty(CertificateContext, 3u, (char *)this + 248, &pcbData)) )
            {
              v8 = 0;
            }
            else
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              v8 = LastError;
            }
          }
          else
          {
            v8 = -2147467259;
          }
        }
      }
    }
  }
  BUFFER::~BUFFER((BUFFER *)v14);
  STRA::~STRA((STRA *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003d94  push    rbp
0x180003d96  push    rbx
0x180003d97  push    rsi
0x180003d98  push    rdi
0x180003d99  push    r14
0x180003d9b  push    r15
0x180003d9d  lea     rbp, [rsp-658h]
0x180003da5  sub     rsp, 758h
0x180003dac  mov     rax, cs:__security_cookie
0x180003db3  xor     rax, rsp
0x180003db6  mov     [rbp+680h+var_40], rax
0x180003dbd  mov     rbx, r8
0x180003dc0  mov     [rsp+780h+pcbData], 0
0x180003dc8  mov     r15, rdx
0x180003dcb  mov     rdi, rcx
0x180003dce  mov     r8d, 3E8h
0x180003dd4  lea     rdx, [rbp+680h+var_430]
0x180003ddb  lea     rcx, [rsp+780h+var_728]
0x180003de0  mov     r14, r9
0x180003de3  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180003de9  xor     edx, edx; Val
0x180003deb  lea     rcx, [rbp+680h+var_6EF]; void *
0x180003def  mov     r8d, 2BFh; Size
0x180003df5  call    memset_0
0x180003dfa  lea     rax, [rbp+680h+var_6F0]
0x180003dfe  mov     [rbp+680h+var_6F0], 0
0x180003e02  lea     rcx, [rdi+8]
0x180003e06  mov     [rsp+780h+pbCertEncoded], rax
0x180003e0b  mov     rdx, rbx
0x180003e0e  mov     [rsp+780h+var_730], 2C0h
0x180003e16  mov     [rsp+780h+var_72C], 100h
0x180003e1d  mov     [rsp+780h+cbCertEncoded], 0
0x180003e25  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003e2b  mov     ebx, eax
0x180003e2d  test    eax, eax
0x180003e2f  js      loc_180003EFF
0x180003e35  lea     rsi, [rdi+80h]
0x180003e3c  mov     rdx, r14
0x180003e3f  mov     rcx, rsi
0x180003e42  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003e48  mov     ebx, eax
0x180003e4a  test    eax, eax
0x180003e4c  js      loc_180003EFF
0x180003e52  mov     rcx, rsi
0x180003e55  call    cs:__imp_?EncryptMemoryPassword@@YAJPEAVSTRU@@@Z; EncryptMemoryPassword(STRU *)
0x180003e5b  mov     ebx, eax
0x180003e5d  test    eax, eax
0x180003e5f  js      loc_180003EFF
0x180003e65  mov     rdx, r15
0x180003e68  lea     rcx, [rsp+780h+var_728]
0x180003e6d  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180003e73  mov     ebx, eax
0x180003e75  test    eax, eax
0x180003e77  js      loc_180003EFF
0x180003e7d  mov     rcx, [rsp+780h+var_708]
0x180003e82  lea     r8, [rsp+780h+cbCertEncoded]
0x180003e87  xor     r9d, r9d
0x180003e8a  lea     rdx, [rsp+780h+var_758]
0x180003e8f  call    cs:__imp_?uudecode@@YAHPEADPEAVBUFFER@@PEAKH@Z; uudecode(char *,BUFFER *,ulong *,int)
0x180003e95  test    eax, eax
0x180003e97  jnz     short loc_180003EA0
0x180003e99  mov     ebx, 80004005h
0x180003e9e  jmp     short loc_180003EFF
0x180003ea0  mov     r8d, [rsp+780h+cbCertEncoded]; cbCertEncoded
0x180003ea5  mov     ecx, 1; dwCertEncodingType
0x180003eaa  mov     rdx, [rsp+780h+pbCertEncoded]; pbCertEncoded
0x180003eaf  call    cs:__imp_CertCreateCertificateContext
0x180003eb5  mov     [rdi+110h], rax
0x180003ebc  test    rax, rax
0x180003ebf  jnz     short loc_180003ED7
0x180003ec1  call    cs:__imp_GetLastError
0x180003ec7  test    eax, eax
0x180003ec9  jle     short loc_180003ED3
0x180003ecb  movzx   eax, ax
0x180003ece  or      eax, 80070000h
0x180003ed3  mov     ebx, eax
0x180003ed5  jmp     short loc_180003EFF
0x180003ed7  lea     r8, [rdi+0F8h]; pvData
0x180003ede  mov     [rsp+780h+pcbData], 14h
0x180003ee6  lea     r9, [rsp+780h+pcbData]; pcbData
0x180003eeb  mov     edx, 3; dwPropId
0x180003ef0  mov     rcx, rax; pCertContext
0x180003ef3  call    cs:__imp_CertGetCertificateContextProperty
0x180003ef9  test    eax, eax
0x180003efb  jz      short loc_180003EC1
0x180003efd  xor     ebx, ebx
0x180003eff  lea     rcx, [rsp+780h+var_758]
0x180003f04  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f0a  lea     rcx, [rsp+780h+var_728]
0x180003f0f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003f15  mov     eax, ebx
0x180003f17  mov     rcx, [rbp+680h+var_40]
0x180003f1e  xor     rcx, rsp; StackCookie
0x180003f21  call    __security_check_cookie
0x180003f26  add     rsp, 758h
0x180003f2d  pop     r15
0x180003f2f  pop     r14
0x180003f31  pop     rdi
0x180003f32  pop     rsi
0x180003f33  pop     rbx
0x180003f34  pop     rbp
0x180003f35  retn
```
