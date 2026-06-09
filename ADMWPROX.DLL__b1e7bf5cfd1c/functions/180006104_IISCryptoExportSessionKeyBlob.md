# IISCryptoExportSessionKeyBlob

- ea: `0x180006104`
- end: `0x1800063ad`
- name: `IISCryptoExportSessionKeyBlob`
- size: `681`
- prototype: `__int64 __fastcall(struct _IC_BLOB **, unsigned __int64, HCRYPTKEY, HCRYPTKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180005480`

## callees

- `0x18000478c`
- `0x180004808`
- `0x180004870`
- `0x180006104`
- `0x180006918`
- `0x180006a3c`
- `0x180006a98`
- `0x180007234`

## import_xrefs

- `ADVAPI32!CryptSignHashA` at `0x180006323`
- `ADVAPI32!CryptSignHashA` at `0x180006323`
- `ADVAPI32!CryptHashData` at `0x1800062c1`
- `ADVAPI32!CryptHashData` at `0x1800062c1`
- `ADVAPI32!CryptExportKey` at `0x180006190`
- `ADVAPI32!CryptExportKey` at `0x18000623b`
- `ADVAPI32!CryptExportKey` at `0x180006190`
- `ADVAPI32!CryptExportKey` at `0x18000623b`
- `ole32!CoTaskMemFree` at `0x180006383`
- `ole32!CoTaskMemFree` at `0x180006383`

## string_xrefs

- `0x1800061b8`: `IISCryptoExportSessionKeyBlob.CryptExportKey (advapi32.dll) failed err=0x%x.\n`
- `0x180006298`: `IISCryptoExportSessionKeyBlob.IISCryptoCreateHash failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IISCryptoExportSessionKeyBlob(struct _IC_BLOB **a1, unsigned __int64 a2, HCRYPTKEY a3, HCRYPTKEY a4)
{
  __int64 result; // rax
  struct _IC_BLOB *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int HashLength; // eax
  struct _IC_BLOB *Blob; // rax
  const BYTE *v14; // r13
  unsigned int v15; // eax
  int Hash; // eax
  unsigned int v17; // eax
  unsigned int LastError; // eax
  DWORD dwDataLen; // [rsp+30h] [rbp-18h] BYREF
  DWORD pdwSigLen; // [rsp+34h] [rbp-14h] BYREF
  HCRYPTHASH hHash[2]; // [rsp+38h] [rbp-10h] BYREF

  dwDataLen = 0;
  pdwSigLen = 0;
  if ( dword_18000FC34 )
  {
    hHash[0] = 0;
    v9 = 0;
    if ( CryptExportKey(a3, a4, 1u, 0, 0, &dwDataLen) )
    {
      HashLength = IcpGetHashLength(&pdwSigLen, a2);
      v11 = HashLength;
      if ( HashLength >= 0 )
      {
        Blob = IcpCreateBlob(0x624B6349u, dwDataLen, pdwSigLen);
        v9 = Blob;
        if ( Blob )
        {
          v14 = (const BYTE *)Blob + 16;
          if ( CryptExportKey(a3, a4, 1u, 0, (BYTE *)Blob + 16, &dwDataLen) )
          {
            Hash = IISCryptoCreateHash(hHash, a2);
            v11 = Hash;
            if ( Hash >= 0 )
            {
              if ( !hHash[0] )
              {
                v11 = -2147467259;
LABEL_32:
                CoTaskMemFree(v9);
                return v11;
              }
              if ( CryptHashData(hHash[0], v14, dwDataLen, 0) )
              {
                if ( CryptSignHashA(
                       hHash[0],
                       2u,
                       0,
                       0,
                       (BYTE *)v9 + ((*((_DWORD *)v9 + 2) + 7) & 0xFFFFFFF8) + 16,
                       &pdwSigLen) )
                {
                  IISCryptoDestroyHash(hHash[0]);
                  result = 0;
                  *a1 = v9;
                  return result;
                }
                LastError = IcpGetLastError();
                v11 = LastError;
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    (struct _DEBUG_PRINTS *)g_pDebug,
                    "inetsrv\\iis\\mb\\crypto\\key.cxx",
                    0x25Cu,
                    "IISCryptoExportSessionKeyBlob",
                    "IISCryptoExportSessionKeyBlob.CryptSignHash failed err=0x%x.\n",
                    LastError);
              }
              else
              {
                v17 = IcpGetLastError();
                v11 = v17;
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    (struct _DEBUG_PRINTS *)g_pDebug,
                    "inetsrv\\iis\\mb\\crypto\\key.cxx",
                    0x24Du,
                    "IISCryptoExportSessionKeyBlob",
                    "IISCryptoExportSessionKeyBlob.CryptHashData failed err=0x%x.\n",
                    v17);
              }
            }
            else if ( (g_dwDebugFlags & 3) != 0 )
            {
              PuDbgPrint(
                (struct _DEBUG_PRINTS *)g_pDebug,
                "inetsrv\\iis\\mb\\crypto\\key.cxx",
                0x233u,
                "IISCryptoExportSessionKeyBlob",
                "IISCryptoExportSessionKeyBlob.IISCryptoCreateHash failed err=0x%x.\n",
                Hash);
            }
          }
          else
          {
            v15 = IcpGetLastError();
            v11 = v15;
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                (struct _DEBUG_PRINTS *)g_pDebug,
                "inetsrv\\iis\\mb\\crypto\\key.cxx",
                0x223u,
                "IISCryptoExportSessionKeyBlob",
                "IISCryptoExportSessionKeyBlob.CryptExportKey failed err=0x%x.\n",
                v15);
          }
        }
        else
        {
          v11 = -2147024888;
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\key.cxx",
          0x201u,
          "IISCryptoExportSessionKeyBlob",
          "IISCryptoExportSessionKeyBlob.IcpGetHashLength failed err=0x%x.\n",
          HashLength);
      }
    }
    else
    {
      v10 = IcpGetLastError();
      v11 = v10;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\key.cxx",
          0x1F3u,
          "IISCryptoExportSessionKeyBlob",
          "IISCryptoExportSessionKeyBlob.CryptExportKey (advapi32.dll) failed err=0x%x.\n",
          v10);
    }
    if ( hHash[0] )
      IISCryptoDestroyHash(hHash[0]);
    if ( !v9 )
      return v11;
    goto LABEL_32;
  }
  if ( a2 == 1984918096 && a3 == 1800627539 && a4 == 1801020747 )
    return IISCryptoCreateCleartextBlob(a1, &word_18000C47E, 1);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x180006104  push    rbp
0x180006106  push    rbx
0x180006107  push    rsi
0x180006108  push    rdi
0x180006109  push    r12
0x18000610b  push    r13
0x18000610d  push    r14
0x18000610f  push    r15
0x180006111  mov     rbp, rsp
0x180006114  sub     rsp, 48h
0x180006118  xor     ebx, ebx
0x18000611a  mov     r14, r9
0x18000611d  cmp     cs:dword_18000FC34, ebx
0x180006123  mov     r15, r8
0x180006126  mov     rsi, rdx
0x180006129  mov     [rbp+dwDataLen], ebx
0x18000612c  mov     r12, rcx
0x18000612f  mov     [rbp+pdwSigLen], ebx
0x180006132  jnz     short loc_18000616E
0x180006134  cmp     rdx, 764F7250h
0x18000613b  jnz     short loc_180006164
0x18000613d  cmp     r8, 6B536553h
0x180006144  jnz     short loc_180006164
0x180006146  cmp     r9, 6B59654Bh
0x18000614d  jnz     short loc_180006164
0x18000614f  lea     r8d, [rbx+1]
0x180006153  lea     rdx, word_18000C47E
0x18000615a  call    IISCryptoCreateCleartextBlob
0x18000615f  jmp     loc_18000639C
0x180006164  mov     eax, 80070057h
0x180006169  jmp     loc_18000639C
0x18000616e  xor     r9d, r9d; dwFlags
0x180006171  mov     [rbp+hHash], rbx
0x180006175  lea     rax, [rbp+dwDataLen]
0x180006179  mov     rdx, r14; hExpKey
0x18000617c  mov     [rsp+48h+pdwDataLen], rax; pdwDataLen
0x180006181  mov     rcx, r15; hKey
0x180006184  mov     rdi, rbx
0x180006187  mov     [rsp+48h+pbData], rbx; pbData
0x18000618c  lea     r8d, [r9+1]; dwBlobType
0x180006190  call    cs:__imp_CryptExportKey
0x180006196  test    eax, eax
0x180006198  jnz     short loc_1800061C4
0x18000619a  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18000619f  test    byte ptr cs:g_dwDebugFlags, 3
0x1800061a6  mov     ebx, eax
0x1800061a8  jz      loc_18000636D
0x1800061ae  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x1800061b2  mov     r8d, 1F3h
0x1800061b8  lea     rax, aIiscryptoexpor_7; "IISCryptoExportSessionKeyBlob.CryptExpo"...
0x1800061bf  jmp     loc_18000634E
0x1800061c4  mov     rdx, rsi; unsigned __int64
0x1800061c7  lea     rcx, [rbp+pdwSigLen]; unsigned int *
0x1800061cb  call    ?IcpGetHashLength@@YAJPEAK_K@Z; IcpGetHashLength(ulong *,unsigned __int64)
0x1800061d0  mov     ebx, eax
0x1800061d2  test    eax, eax
0x1800061d4  jns     short loc_1800061F9
0x1800061d6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800061dd  jz      loc_18000636D
0x1800061e3  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x1800061e7  mov     r8d, 201h
0x1800061ed  lea     rax, aIiscryptoexpor_0; "IISCryptoExportSessionKeyBlob.IcpGetHas"...
0x1800061f4  jmp     loc_18000634E
0x1800061f9  mov     r8d, [rbp+pdwSigLen]; unsigned int
0x1800061fd  mov     ecx, 624B6349h; unsigned int
0x180006202  mov     edx, [rbp+dwDataLen]; unsigned int
0x180006205  call    ?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z; IcpCreateBlob(ulong,ulong,ulong)
0x18000620a  mov     rdi, rax
0x18000620d  test    rax, rax
0x180006210  jnz     short loc_18000621C
0x180006212  mov     ebx, 80070008h
0x180006217  jmp     loc_18000636D
0x18000621c  lea     r13, [rax+10h]
0x180006220  xor     r9d, r9d; dwFlags
0x180006223  lea     rax, [rbp+dwDataLen]
0x180006227  mov     rdx, r14; hExpKey
0x18000622a  mov     [rsp+48h+pdwDataLen], rax; pdwDataLen
0x18000622f  mov     rcx, r15; hKey
0x180006232  mov     [rsp+48h+pbData], r13; pbData
0x180006237  lea     r8d, [r9+1]; dwBlobType
0x18000623b  call    cs:__imp_CryptExportKey
0x180006241  test    eax, eax
0x180006243  jnz     short loc_18000626F
0x180006245  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18000624a  test    byte ptr cs:g_dwDebugFlags, 3
0x180006251  mov     ebx, eax
0x180006253  jz      loc_18000636D
0x180006259  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x18000625d  mov     r8d, 223h
0x180006263  lea     rax, aIiscryptoexpor; "IISCryptoExportSessionKeyBlob.CryptExpo"...
0x18000626a  jmp     loc_18000634E
0x18000626f  mov     rdx, rsi; hProv
0x180006272  lea     rcx, [rbp+hHash]; phHash
0x180006276  call    IISCryptoCreateHash
0x18000627b  mov     ebx, eax
0x18000627d  test    eax, eax
0x18000627f  jns     short loc_1800062A4
0x180006281  test    byte ptr cs:g_dwDebugFlags, 3
0x180006288  jz      loc_18000636D
0x18000628e  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x180006292  mov     r8d, 233h
0x180006298  lea     rax, aIiscryptoexpor_6; "IISCryptoExportSessionKeyBlob.IISCrypto"...
0x18000629f  jmp     loc_18000634E
0x1800062a4  mov     rcx, [rbp+hHash]; hHash
0x1800062a8  test    rcx, rcx
0x1800062ab  jnz     short loc_1800062B7
0x1800062ad  mov     ebx, 80004005h
0x1800062b2  jmp     loc_180006380
0x1800062b7  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x1800062bb  xor     r9d, r9d; dwFlags
0x1800062be  mov     rdx, r13; pbData
0x1800062c1  call    cs:__imp_CryptHashData
0x1800062c7  test    eax, eax
0x1800062c9  jnz     short loc_1800062F2
0x1800062cb  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x1800062d0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800062d7  mov     ebx, eax
0x1800062d9  jz      loc_18000636D
0x1800062df  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x1800062e3  mov     r8d, 24Dh
0x1800062e9  lea     rax, aIiscryptoexpor_3; "IISCryptoExportSessionKeyBlob.CryptHash"...
0x1800062f0  jmp     short loc_18000634E
0x1800062f2  mov     eax, [rdi+8]
0x1800062f5  mov     ecx, 0FFFFFFF8h
0x1800062fa  add     eax, 7
0x1800062fd  xor     r9d, r9d; dwFlags
0x180006300  and     rax, rcx
0x180006303  xor     r8d, r8d; szDescription
0x180006306  add     rax, 10h
0x18000630a  lea     rcx, [rbp+pdwSigLen]
0x18000630e  mov     [rsp+48h+pdwDataLen], rcx; pdwSigLen
0x180006313  add     rax, rdi
0x180006316  mov     rcx, [rbp+hHash]; hHash
0x18000631a  lea     edx, [r9+2]; dwKeySpec
0x18000631e  mov     [rsp+48h+pbData], rax; pbSignature
0x180006323  call    cs:__imp_CryptSignHashA
0x180006329  test    eax, eax
0x18000632b  jnz     short loc_18000638D
0x18000632d  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180006332  test    byte ptr cs:g_dwDebugFlags, 3
0x180006339  mov     ebx, eax
0x18000633b  jz      short loc_18000636D
0x18000633d  mov     dword ptr [rsp+48h+pdwDataLen], eax; char
0x180006341  mov     r8d, 25Ch; unsigned int
0x180006347  lea     rax, aIiscryptoexpor_1; "IISCryptoExportSessionKeyBlob.CryptSign"...
0x18000634e  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180006355  lea     r9, aIiscryptoexpor_5; "IISCryptoExportSessionKeyBlob"
0x18000635c  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x180006363  mov     [rsp+48h+pbData], rax; char *
0x180006368  call    PuDbgPrint
0x18000636d  mov     rcx, [rbp+hHash]
0x180006371  test    rcx, rcx
0x180006374  jz      short loc_18000637B
0x180006376  call    IISCryptoDestroyHash
0x18000637b  test    rdi, rdi
0x18000637e  jz      short loc_180006389
0x180006380  mov     rcx, rdi; pv
0x180006383  call    cs:__imp_CoTaskMemFree
0x180006389  mov     eax, ebx
0x18000638b  jmp     short loc_18000639C
0x18000638d  mov     rcx, [rbp+hHash]
0x180006391  call    IISCryptoDestroyHash
0x180006396  xor     eax, eax
0x180006398  mov     [r12], rdi
0x18000639c  add     rsp, 48h
0x1800063a0  pop     r15
0x1800063a2  pop     r14
0x1800063a4  pop     r13
0x1800063a6  pop     r12
0x1800063a8  pop     rdi
0x1800063a9  pop     rsi
0x1800063aa  pop     rbx
0x1800063ab  pop     rbp
0x1800063ac  retn
```
