# IISCryptoExportPublicKeyBlob

- ea: `0x180005f7c`
- end: `0x1800060fb`
- name: `IISCryptoExportPublicKeyBlob`
- size: `383`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004eb4`
- `0x180005988`

## callees

- `0x18000478c`
- `0x180004808`
- `0x180004870`
- `0x180005f7c`
- `0x180007234`

## import_xrefs

- `ADVAPI32!CryptExportKey` at `0x180005fff`
- `ADVAPI32!CryptExportKey` at `0x18000608f`
- `ADVAPI32!CryptExportKey` at `0x180005fff`
- `ADVAPI32!CryptExportKey` at `0x18000608f`
- `ole32!CoTaskMemFree` at `0x1800060dc`
- `ole32!CoTaskMemFree` at `0x1800060dc`

## pseudocode

```c
__int64 __fastcall IISCryptoExportPublicKeyBlob(struct _IC_BLOB **a1, __int64 a2, HCRYPTKEY a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  struct _IC_BLOB *Blob; // rax
  struct _IC_BLOB *v9; // rdi
  unsigned int LastError; // eax
  HCRYPTKEY v11; // [rsp+50h] [rbp+18h] BYREF
  DWORD pdwDataLen; // [rsp+58h] [rbp+20h] BYREF

  v11 = a3;
  pdwDataLen = 0;
  if ( dword_18000FC34 )
  {
    if ( CryptExportKey(a3, 0, 6u, 0, 0, &pdwDataLen) )
    {
      Blob = IcpCreateBlob(1649435465, pdwDataLen, 0);
      v9 = Blob;
      if ( Blob )
      {
        if ( CryptExportKey(a3, 0, 6u, 0, (BYTE *)Blob + 16, &pdwDataLen) )
        {
          *a1 = v9;
          return 0;
        }
        LastError = IcpGetLastError();
        v7 = LastError;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\key.cxx",
            0x543u,
            "IISCryptoExportPublicKeyBlob",
            "IISCryptoExportPublicKeyBlob.CryptExportKey failed err=0x%x.\n",
            LastError);
        CoTaskMemFree(v9);
      }
      else
      {
        return 8;
      }
    }
    else
    {
      v6 = IcpGetLastError();
      v7 = v6;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\key.cxx",
          0x521u,
          "IISCryptoExportPublicKeyBlob",
          "IISCryptoExportPublicKeyBlob.CryptExportKey failed err=0x%x.\n",
          v6);
    }
    return v7;
  }
  if ( a2 == 1984918096 && (a3 == 1801020747 || a3 == 1799842131) )
    return IISCryptoCreateCleartextBlob(a1, &v11, 8u);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x180005f7c  mov     rax, rsp
0x180005f7f  mov     [rax+8], rbx
0x180005f83  mov     [rax+10h], rsi
0x180005f87  mov     [rax+18h], r8
0x180005f8b  push    rdi
0x180005f8c  sub     rsp, 30h
0x180005f90  cmp     cs:dword_18000FC34, 0
0x180005f97  mov     rbx, r8
0x180005f9a  mov     rsi, rcx
0x180005f9d  mov     dword ptr [rax+20h], 0
0x180005fa4  jnz     short loc_180005FE0
0x180005fa6  cmp     rdx, 764F7250h
0x180005fad  jnz     short loc_180005FD6
0x180005faf  cmp     rbx, 6B59654Bh
0x180005fb6  jz      short loc_180005FC1
0x180005fb8  cmp     rbx, 6B476953h
0x180005fbf  jnz     short loc_180005FD6
0x180005fc1  mov     r8d, 8
0x180005fc7  lea     rdx, [rsp+38h+arg_10]
0x180005fcc  call    IISCryptoCreateCleartextBlob
0x180005fd1  jmp     loc_1800060EB
0x180005fd6  mov     eax, 80070057h
0x180005fdb  jmp     loc_1800060EB
0x180005fe0  xor     r9d, r9d; dwFlags
0x180005fe3  lea     rax, [rsp+38h+arg_18]
0x180005fe8  mov     [rsp+38h+pdwDataLen], rax; pdwDataLen
0x180005fed  xor     edx, edx; hExpKey
0x180005fef  mov     rcx, rbx; hKey
0x180005ff2  mov     [rsp+38h+pbData], 0; pbData
0x180005ffb  lea     r8d, [r9+6]; dwBlobType
0x180005fff  call    cs:__imp_CryptExportKey
0x180006005  test    eax, eax
0x180006007  jnz     short loc_180006052
0x180006009  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18000600e  test    byte ptr cs:g_dwDebugFlags, 3
0x180006015  mov     ebx, eax
0x180006017  jz      loc_1800060E2
0x18000601d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180006024  lea     r9, aIiscryptoexpor_2; "IISCryptoExportPublicKeyBlob"
0x18000602b  mov     dword ptr [rsp+38h+pdwDataLen], eax; char
0x18000602f  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x180006036  lea     rax, aIiscryptoexpor_4; "IISCryptoExportPublicKeyBlob.CryptExpor"...
0x18000603d  mov     r8d, 521h; unsigned int
0x180006043  mov     [rsp+38h+pbData], rax; char *
0x180006048  call    PuDbgPrint
0x18000604d  jmp     loc_1800060E2
0x180006052  mov     edx, [rsp+38h+arg_18]; unsigned int
0x180006056  xor     r8d, r8d; unsigned int
0x180006059  mov     ecx, 62506349h; unsigned int
0x18000605e  call    ?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z; IcpCreateBlob(ulong,ulong,ulong)
0x180006063  mov     rdi, rax
0x180006066  test    rax, rax
0x180006069  jnz     short loc_180006070
0x18000606b  lea     ebx, [rax+8]
0x18000606e  jmp     short loc_1800060E2
0x180006070  xor     r9d, r9d; dwFlags
0x180006073  lea     rcx, [rsp+38h+arg_18]
0x180006078  mov     [rsp+38h+pdwDataLen], rcx; pdwDataLen
0x18000607d  add     rax, 10h
0x180006081  xor     edx, edx; hExpKey
0x180006083  mov     [rsp+38h+pbData], rax; pbData
0x180006088  mov     rcx, rbx; hKey
0x18000608b  lea     r8d, [r9+6]; dwBlobType
0x18000608f  call    cs:__imp_CryptExportKey
0x180006095  test    eax, eax
0x180006097  jnz     short loc_1800060E6
0x180006099  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18000609e  test    byte ptr cs:g_dwDebugFlags, 3
0x1800060a5  mov     ebx, eax
0x1800060a7  jz      short loc_1800060D9
0x1800060a9  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800060b0  lea     r9, aIiscryptoexpor_2; "IISCryptoExportPublicKeyBlob"
0x1800060b7  mov     dword ptr [rsp+38h+pdwDataLen], eax; char
0x1800060bb  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x1800060c2  lea     rax, aIiscryptoexpor_4; "IISCryptoExportPublicKeyBlob.CryptExpor"...
0x1800060c9  mov     r8d, 543h; unsigned int
0x1800060cf  mov     [rsp+38h+pbData], rax; char *
0x1800060d4  call    PuDbgPrint
0x1800060d9  mov     rcx, rdi; pv
0x1800060dc  call    cs:__imp_CoTaskMemFree
0x1800060e2  mov     eax, ebx
0x1800060e4  jmp     short loc_1800060EB
0x1800060e6  mov     [rsi], rdi
0x1800060e9  xor     eax, eax
0x1800060eb  mov     rbx, [rsp+38h+arg_0]
0x1800060f0  mov     rsi, [rsp+38h+arg_8]
0x1800060f5  add     rsp, 30h
0x1800060f9  pop     rdi
0x1800060fa  retn
```
