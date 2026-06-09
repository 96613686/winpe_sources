# GetCertificateHashString(uchar *,ulong,ushort *,ulong)

- ea: `0x180026bbc`
- end: `0x180026cd6`
- name: `?GetCertificateHashString@@YAJPEAEKPEAGK@Z`
- size: `282`
- prototype: `__int64 __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ac00`

## callees

- `0x180003460`
- `0x180026bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c3c`
- `CRYPT32!CertCreateCertificateContext` at `0x180026bf7`
- `CRYPT32!CertCreateCertificateContext` at `0x180026bf7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180026c32`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180026c32`
- `CRYPT32!CertFreeCertificateContext` at `0x180026c54`
- `CRYPT32!CertFreeCertificateContext` at `0x180026c61`
- `CRYPT32!CertFreeCertificateContext` at `0x180026c54`
- `CRYPT32!CertFreeCertificateContext` at `0x180026c61`

## pseudocode

```c
signed int __fastcall GetCertificateHashString(BYTE *pbCertEncoded, DWORD cbCertEncoded, unsigned __int16 *a3)
{
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v5; // rdi
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int i; // r8d
  __int16 v10; // cx
  char v11; // dl
  __int16 v12; // cx
  DWORD pcbData; // [rsp+20h] [rbp-38h] BYREF
  __int128 pvData; // [rsp+28h] [rbp-30h] BYREF
  int v15; // [rsp+38h] [rbp-20h]

  pcbData = 20;
  v15 = 0;
  pvData = 0;
  CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
  v5 = CertificateContext;
  if ( CertificateContext )
  {
    if ( CertGetCertificateContextProperty(CertificateContext, 3u, &pvData, &pcbData) )
    {
      CertFreeCertificateContext(v5);
      for ( i = 0; (unsigned int)i < 0x14; ++i )
      {
        v10 = 87;
        v11 = *((_BYTE *)&pvData + i);
        if ( (v11 & 0xF0u) <= 0x90 )
          v10 = 48;
        *a3 = (*((unsigned __int8 *)&pvData + i) >> 4) + v10;
        a3 += 2;
        v12 = 87;
        if ( (v11 & 0xFu) <= 9 )
          v12 = 48;
        *(a3 - 1) = (v11 & 0xF) + v12;
      }
      result = 0;
      *a3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      CertFreeCertificateContext(v5);
      return v8;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180026bbc  mov     [rsp+arg_18], rbx
0x180026bc1  push    rdi
0x180026bc2  sub     rsp, 50h
0x180026bc6  mov     rax, cs:__security_cookie
0x180026bcd  xor     rax, rsp
0x180026bd0  mov     [rsp+58h+var_18], rax
0x180026bd5  xor     eax, eax
0x180026bd7  mov     [rsp+58h+pcbData], 14h
0x180026bdf  mov     rbx, r8
0x180026be2  mov     [rsp+58h+var_20], eax
0x180026be6  mov     r8d, edx; cbCertEncoded
0x180026be9  xorps   xmm0, xmm0
0x180026bec  mov     rdx, rcx; pbCertEncoded
0x180026bef  lea     ecx, [rax+1]; dwCertEncodingType
0x180026bf2  movups  [rsp+58h+pvData], xmm0
0x180026bf7  call    cs:__imp_CertCreateCertificateContext
0x180026bfd  mov     rdi, rax
0x180026c00  test    rax, rax
0x180026c03  jnz     short loc_180026C20
0x180026c05  call    cs:__imp_GetLastError
0x180026c0b  test    eax, eax
0x180026c0d  jle     loc_180026CBE
0x180026c13  movzx   eax, ax
0x180026c16  or      eax, 80070000h
0x180026c1b  jmp     loc_180026CBE
0x180026c20  lea     r9, [rsp+58h+pcbData]; pcbData
0x180026c25  mov     edx, 3; dwPropId
0x180026c2a  lea     r8, [rsp+58h+pvData]; pvData
0x180026c2f  mov     rcx, rdi; pCertContext
0x180026c32  call    cs:__imp_CertGetCertificateContextProperty
0x180026c38  test    eax, eax
0x180026c3a  jnz     short loc_180026C5E
0x180026c3c  call    cs:__imp_GetLastError
0x180026c42  mov     ebx, eax
0x180026c44  test    eax, eax
0x180026c46  jle     short loc_180026C51
0x180026c48  movzx   ebx, ax
0x180026c4b  or      ebx, 80070000h
0x180026c51  mov     rcx, rdi; pCertContext
0x180026c54  call    cs:__imp_CertFreeCertificateContext
0x180026c5a  mov     eax, ebx
0x180026c5c  jmp     short loc_180026CBE
0x180026c5e  mov     rcx, rdi; pCertContext
0x180026c61  call    cs:__imp_CertFreeCertificateContext
0x180026c67  xor     r8d, r8d
0x180026c6a  lea     r9d, [r8+57h]
0x180026c6e  lea     r10d, [r8+30h]
0x180026c72  movsxd  rax, r8d
0x180026c75  mov     ecx, r9d
0x180026c78  movzx   edx, byte ptr [rsp+rax+58h+pvData]
0x180026c7d  mov     al, dl
0x180026c7f  and     al, 0F0h
0x180026c81  cmp     al, 90h
0x180026c83  mov     eax, edx
0x180026c85  cmovbe  cx, r10w
0x180026c8a  shr     eax, 4
0x180026c8d  add     cx, ax
0x180026c90  mov     al, dl
0x180026c92  mov     [rbx], cx
0x180026c95  and     al, 0Fh
0x180026c97  cmp     al, 9
0x180026c99  lea     rbx, [rbx+4]
0x180026c9d  mov     ecx, r9d
0x180026ca0  cmovbe  cx, r10w
0x180026ca5  and     dx, 0Fh
0x180026ca9  add     cx, dx
0x180026cac  inc     r8d
0x180026caf  mov     [rbx-2], cx
0x180026cb3  cmp     r8d, 14h
0x180026cb7  jb      short loc_180026C72
0x180026cb9  xor     eax, eax
0x180026cbb  mov     [rbx], ax
0x180026cbe  mov     rcx, [rsp+58h+var_18]
0x180026cc3  xor     rcx, rsp; StackCookie
0x180026cc6  call    __security_check_cookie
0x180026ccb  mov     rbx, [rsp+58h+arg_18]
0x180026cd0  add     rsp, 50h
0x180026cd4  pop     rdi
0x180026cd5  retn
```
