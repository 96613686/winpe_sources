# GetEkPubFromNCrypt(uchar *,uint *)

- ea: `0x180040c54`
- end: `0x180040dbe`
- name: `?GetEkPubFromNCrypt@@YAJPEAEPEAI@Z`
- size: `362`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800408c0`

## callees

- `0x180007894`
- `0x180007900`
- `0x180040c54`
- `0x180041cf4`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180040da9`
- `ncrypt!NCryptFreeObject` at `0x180040da9`
- `ncrypt!NCryptOpenStorageProvider` at `0x180040c9d`
- `ncrypt!NCryptOpenStorageProvider` at `0x180040c9d`
- `ncrypt!NCryptGetProperty` at `0x180040cd1`
- `ncrypt!NCryptGetProperty` at `0x180040d13`
- `ncrypt!NCryptGetProperty` at `0x180040cd1`
- `ncrypt!NCryptGetProperty` at `0x180040d13`

## pseudocode

```c
__int64 __fastcall GetEkPubFromNCrypt(unsigned __int8 *a1, unsigned int *a2)
{
  SECURITY_STATUS Property; // ebx
  BYTE *v5; // rsi
  __int64 v6; // rcx
  unsigned __int8 *v7; // rax
  _OWORD *v8; // rsi
  __int128 v9; // xmm1
  DWORD cbOutput; // [rsp+50h] [rbp+8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+60h] [rbp+18h] BYREF

  cbOutput = 0;
  hObject = 0;
  if ( a1 && a2 )
  {
    *a2 = 0;
    Property = NCryptOpenStorageProvider(&hObject, L"Microsoft Platform Crypto Provider", 0);
    if ( Property >= 0 )
    {
      Property = NCryptGetProperty(hObject, L"PCP_RSA_EKPUB", 0, 0, &cbOutput, 0);
      if ( Property >= 0 )
      {
        v5 = (BYTE *)operator new(cbOutput);
        Property = NCryptGetProperty(hObject, L"PCP_RSA_EKPUB", v5, cbOutput, &cbOutput, 0);
        if ( Property < 0 )
        {
          if ( v5 )
            operator delete(v5);
        }
        else
        {
          v6 = 2;
          *a2 = 256;
          v7 = a1;
          v8 = v5 + 27;
          do
          {
            *(_OWORD *)v7 = *v8;
            *((_OWORD *)v7 + 1) = v8[1];
            *((_OWORD *)v7 + 2) = v8[2];
            *((_OWORD *)v7 + 3) = v8[3];
            *((_OWORD *)v7 + 4) = v8[4];
            *((_OWORD *)v7 + 5) = v8[5];
            *((_OWORD *)v7 + 6) = v8[6];
            v9 = v8[7];
            v8 += 8;
            *((_OWORD *)v7 + 7) = v9;
            v7 += 128;
            --v6;
          }
          while ( v6 );
          SetEKPubInUEFI(a1, a2);
        }
      }
    }
  }
  else
  {
    Property = -2147024809;
  }
  if ( hObject )
    NCryptFreeObject(hObject);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180040c54  mov     rax, rsp
0x180040c57  mov     [rax+10h], rbx
0x180040c5b  push    rbp
0x180040c5c  push    rsi
0x180040c5d  push    rdi
0x180040c5e  sub     rsp, 30h
0x180040c62  mov     dword ptr [rax+8], 0
0x180040c69  mov     rdi, rdx
0x180040c6c  mov     qword ptr [rax+18h], 0
0x180040c74  mov     rbp, rcx
0x180040c77  test    rcx, rcx
0x180040c7a  jz      loc_180040D9A
0x180040c80  test    rdx, rdx
0x180040c83  jz      loc_180040D9A
0x180040c89  mov     dword ptr [rdx], 0
0x180040c8f  lea     rcx, [rax+18h]; phProvider
0x180040c93  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180040c9a  xor     r8d, r8d; dwFlags
0x180040c9d  call    cs:__imp_NCryptOpenStorageProvider
0x180040ca3  mov     ebx, eax
0x180040ca5  test    eax, eax
0x180040ca7  js      loc_180040D9F
0x180040cad  mov     rcx, [rsp+48h+hObject]; hObject
0x180040cb2  lea     rax, [rsp+48h+cbOutput]
0x180040cb7  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180040cbf  lea     rdx, aPcpRsaEkpub; "PCP_RSA_EKPUB"
0x180040cc6  xor     r9d, r9d; cbOutput
0x180040cc9  mov     [rsp+48h+pcbResult], rax; pcbResult
0x180040cce  xor     r8d, r8d; pbOutput
0x180040cd1  call    cs:__imp_NCryptGetProperty
0x180040cd7  mov     ebx, eax
0x180040cd9  test    eax, eax
0x180040cdb  js      loc_180040D9F
0x180040ce1  mov     ecx, [rsp+48h+cbOutput]; Size
0x180040ce5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040cea  mov     r9d, [rsp+48h+cbOutput]; cbOutput
0x180040cef  lea     rdx, aPcpRsaEkpub; "PCP_RSA_EKPUB"
0x180040cf6  mov     rcx, [rsp+48h+hObject]; hObject
0x180040cfb  mov     rsi, rax
0x180040cfe  lea     rax, [rsp+48h+cbOutput]
0x180040d03  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180040d0b  mov     r8, rsi; pbOutput
0x180040d0e  mov     [rsp+48h+pcbResult], rax; pcbResult
0x180040d13  call    cs:__imp_NCryptGetProperty
0x180040d19  mov     ebx, eax
0x180040d1b  test    eax, eax
0x180040d1d  js      short loc_180040D8B
0x180040d1f  mov     ecx, 2
0x180040d24  mov     dword ptr [rdi], 100h
0x180040d2a  mov     rax, rbp
0x180040d2d  add     rsi, 1Bh
0x180040d31  lea     edx, [rcx+7Eh]
0x180040d34  movups  xmm0, xmmword ptr [rsi]
0x180040d37  movups  xmmword ptr [rax], xmm0
0x180040d3a  movups  xmm1, xmmword ptr [rsi+10h]
0x180040d3e  movups  xmmword ptr [rax+10h], xmm1
0x180040d42  movups  xmm0, xmmword ptr [rsi+20h]
0x180040d46  movups  xmmword ptr [rax+20h], xmm0
0x180040d4a  movups  xmm1, xmmword ptr [rsi+30h]
0x180040d4e  movups  xmmword ptr [rax+30h], xmm1
0x180040d52  movups  xmm0, xmmword ptr [rsi+40h]
0x180040d56  movups  xmmword ptr [rax+40h], xmm0
0x180040d5a  movups  xmm1, xmmword ptr [rsi+50h]
0x180040d5e  movups  xmmword ptr [rax+50h], xmm1
0x180040d62  movups  xmm0, xmmword ptr [rsi+60h]
0x180040d66  movups  xmmword ptr [rax+60h], xmm0
0x180040d6a  movups  xmm1, xmmword ptr [rsi+70h]
0x180040d6e  add     rsi, rdx
0x180040d71  movups  xmmword ptr [rax+70h], xmm1
0x180040d75  add     rax, rdx
0x180040d78  sub     rcx, 1
0x180040d7c  jnz     short loc_180040D34
0x180040d7e  mov     rdx, rdi; unsigned int *
0x180040d81  mov     rcx, rbp; unsigned __int8 *
0x180040d84  call    ?SetEKPubInUEFI@@YAJPEAEPEAI@Z; SetEKPubInUEFI(uchar *,uint *)
0x180040d89  jmp     short loc_180040D9F
0x180040d8b  test    rsi, rsi
0x180040d8e  jz      short loc_180040D9F
0x180040d90  mov     rcx, rsi; Block
0x180040d93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040d98  jmp     short loc_180040D9F
0x180040d9a  mov     ebx, 80070057h
0x180040d9f  mov     rcx, [rsp+48h+hObject]; hObject
0x180040da4  test    rcx, rcx
0x180040da7  jz      short loc_180040DAF
0x180040da9  call    cs:__imp_NCryptFreeObject
0x180040daf  mov     eax, ebx
0x180040db1  mov     rbx, [rsp+48h+arg_8]
0x180040db6  add     rsp, 30h
0x180040dba  pop     rdi
0x180040dbb  pop     rsi
0x180040dbc  pop     rbp
0x180040dbd  retn
```
