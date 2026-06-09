# VerifyTrust(HWND__ *,ushort const *,ushort const *,ulong,ulong,int *)

- ea: `0x140001af0`
- end: `0x140001cd8`
- name: `?VerifyTrust@@YAJPEAUHWND__@@PEBG1KKPEAH@Z`
- size: `488`
- prototype: `__int64 __fastcall(HWND hwnd, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400018f8`

## callees

- `0x1400016df`
- `0x140001a08`
- `0x140001af0`
- `0x140001d90`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140001b8e`
- `KERNEL32!CreateFileW` at `0x140001b8e`
- `KERNEL32!CloseHandle` at `0x140001cb2`
- `KERNEL32!CloseHandle` at `0x140001cb2`
- `KERNEL32!GetLastError` at `0x140001b9d`
- `KERNEL32!GetLastError` at `0x140001b9d`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x140001c10`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x140001c10`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x140001c26`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x140001c26`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x140001c36`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x140001c36`
- `WINTRUST!WinVerifyTrust` at `0x140001bf1`
- `WINTRUST!WinVerifyTrust` at `0x140001ca4`
- `WINTRUST!WinVerifyTrust` at `0x140001bf1`
- `WINTRUST!WinVerifyTrust` at `0x140001ca4`

## pseudocode

```c
__int64 __fastcall VerifyTrust(
        HWND hwnd,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        int *a6)
{
  HANDLE FileW; // rsi
  unsigned int v10; // edi
  LONG v11; // eax
  HANDLE v12; // rbx
  BOOL v13; // r14d
  CRYPT_PROVIDER_DATA *v14; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  void **v17; // rdx
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  _DWORD pWVTData[10]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 *v22; // [rsp+88h] [rbp-78h]
  int v23; // [rsp+90h] [rbp-70h]
  HANDLE hStateData; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+ACh] [rbp-54h]
  _DWORD v26[14]; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v27; // [rsp+F8h] [rbp-8h]
  GUID pgActionID; // [rsp+120h] [rbp+20h] BYREF
  GUID v29; // [rsp+130h] [rbp+30h] BYREF

  v19 = 0;
  v20 = 0;
  memset_0(pWVTData, 0, 0x58u);
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  *a6 = 0;
  FileW = CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    *((_QWORD *)&v19 + 1) = a2;
    LODWORD(v19) = 32;
    *(_QWORD *)&v20 = FileW;
    pWVTData[0] = 88;
    v22 = &v19;
    pWVTData[8] = 1;
    pWVTData[6] = 1;
    v25 = 1;
    v23 = 1;
    v11 = WinVerifyTrust(hwnd, &pgActionID, pWVTData);
    v12 = hStateData;
    v10 = v11;
    v13 = hStateData != 0;
    if ( !v11 && hStateData )
    {
      v14 = WTHelperProvDataFromStateData(hStateData);
      if ( v14 )
      {
        ProvSignerFromChain = WTHelperGetProvSignerFromChain(v14, 0, 0, 0);
        if ( ProvSignerFromChain )
        {
          ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, 0);
          if ( ProvCertFromChain )
          {
            if ( (unsigned int)IsAuthenticodePublisherTrusted(ProvCertFromChain->pCert, v17) )
              *a6 = 1;
          }
        }
      }
      v12 = hStateData;
    }
    if ( v13 )
    {
      v29.Data1 = 11191659;
      *(_DWORD *)&v29.Data2 = 298896708;
      *(_DWORD *)v29.Data4 = -1073692020;
      *(_DWORD *)&v29.Data4[4] = -292175281;
      memset_0(v26, 0, 0x58u);
      v26[0] = 88;
      v26[12] = 2;
      v27 = v12;
      WinVerifyTrust(0, &v29, v26);
    }
    if ( FileW )
      CloseHandle(FileW);
  }
  return v10;
}

```

## disassembly

```asm
0x140001af0  push    rbp
0x140001af2  push    rbx
0x140001af3  push    rsi
0x140001af4  push    rdi
0x140001af5  push    r12
0x140001af7  push    r14
0x140001af9  push    r15
0x140001afb  lea     rbp, [rsp-50h]
0x140001b00  sub     rsp, 150h
0x140001b07  mov     rax, cs:__security_cookie
0x140001b0e  xor     rax, rsp
0x140001b11  mov     [rbp+80h+var_40], rax
0x140001b15  mov     r12, [rbp+80h+arg_28]
0x140001b1c  xorps   xmm0, xmm0
0x140001b1f  mov     r15, rdx
0x140001b22  mov     rbx, r8
0x140001b25  xor     edx, edx; Val
0x140001b27  mov     rdi, rcx
0x140001b2a  lea     rcx, [rsp+180h+pWVTData]; void *
0x140001b2f  movups  [rsp+180h+var_140], xmm0
0x140001b34  lea     r8d, [rdx+58h]; Size
0x140001b38  movups  [rsp+180h+var_130], xmm0
0x140001b3d  call    memset_0
0x140001b42  xor     r9d, r9d; lpSecurityAttributes
0x140001b45  mov     [rsp+180h+hTemplateFile], 0; hTemplateFile
0x140001b4e  mov     [rsp+180h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140001b56  mov     edx, 80000000h; dwDesiredAccess
0x140001b5b  mov     rcx, rbx; lpFileName
0x140001b5e  mov     [rbp+80h+pgActionID.Data1], 0AAC56Bh
0x140001b65  mov     dword ptr [rbp+80h+pgActionID.Data2], 11D0CD44h
0x140001b6c  lea     r8d, [r9+1]; dwShareMode
0x140001b70  mov     dword ptr [rbp+80h+pgActionID.Data4], 0C000C28Ch
0x140001b77  mov     dword ptr [rbp+80h+pgActionID.Data4+4], 0EE95C24Fh
0x140001b7e  mov     dword ptr [r12], 0
0x140001b86  mov     [rsp+180h+dwCreationDisposition], 3; dwCreationDisposition
0x140001b8e  call    cs:__imp_CreateFileW
0x140001b94  mov     rsi, rax
0x140001b97  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140001b9b  jnz     short loc_140001BAA
0x140001b9d  call    cs:__imp_GetLastError
0x140001ba3  mov     edi, eax
0x140001ba5  jmp     loc_140001CB8
0x140001baa  mov     qword ptr [rsp+180h+var_140+8], r15
0x140001baf  lea     rax, [rsp+180h+var_140]
0x140001bb4  xor     r14d, r14d
0x140001bb7  mov     dword ptr [rsp+180h+var_140], 20h ; ' '
0x140001bbf  lea     r8, [rsp+180h+pWVTData]; pWVTData
0x140001bc4  mov     qword ptr [rsp+180h+var_130], rsi
0x140001bc9  lea     rdx, [rbp+80h+pgActionID]; pgActionID
0x140001bcd  mov     [rsp+180h+pWVTData], 58h ; 'X'
0x140001bd5  mov     rcx, rdi; hwnd
0x140001bd8  mov     [rbp+80h+var_F8], rax
0x140001bdc  lea     r15d, [r14+1]
0x140001be0  mov     [rbp+80h+var_100], r15d
0x140001be4  mov     [rsp+180h+var_108], r15d
0x140001be9  mov     [rbp+80h+var_D4], r15d
0x140001bed  mov     [rbp+80h+var_F0], r15d
0x140001bf1  call    cs:__imp_WinVerifyTrust
0x140001bf7  mov     rbx, [rbp+80h+hStateData]
0x140001bfb  mov     edi, eax
0x140001bfd  test    rbx, rbx
0x140001c00  cmovnz  r14d, r15d
0x140001c04  test    eax, eax
0x140001c06  jnz     short loc_140001C56
0x140001c08  test    rbx, rbx
0x140001c0b  jz      short loc_140001C56
0x140001c0d  mov     rcx, rbx; hStateData
0x140001c10  call    cs:__imp_WTHelperProvDataFromStateData
0x140001c16  test    rax, rax
0x140001c19  jz      short loc_140001C52
0x140001c1b  xor     r9d, r9d; idxCounterSigner
0x140001c1e  xor     r8d, r8d; fCounterSigner
0x140001c21  xor     edx, edx; idxSigner
0x140001c23  mov     rcx, rax; pProvData
0x140001c26  call    cs:__imp_WTHelperGetProvSignerFromChain
0x140001c2c  test    rax, rax
0x140001c2f  jz      short loc_140001C52
0x140001c31  xor     edx, edx; idxCert
0x140001c33  mov     rcx, rax; pSgnr
0x140001c36  call    cs:__imp_WTHelperGetProvCertFromChain
0x140001c3c  test    rax, rax
0x140001c3f  jz      short loc_140001C52
0x140001c41  mov     rcx, [rax+8]; struct _CERT_CONTEXT *
0x140001c45  call    ?IsAuthenticodePublisherTrusted@@YAHPEBU_CERT_CONTEXT@@PEAPEAX@Z; IsAuthenticodePublisherTrusted(_CERT_CONTEXT const *,void * *)
0x140001c4a  test    eax, eax
0x140001c4c  jz      short loc_140001C52
0x140001c4e  mov     [r12], r15d
0x140001c52  mov     rbx, [rbp+80h+hStateData]
0x140001c56  test    r14d, r14d
0x140001c59  jz      short loc_140001CAA
0x140001c5b  mov     r14d, 58h ; 'X'
0x140001c61  mov     [rbp+80h+var_50.Data1], 0AAC56Bh
0x140001c68  mov     r8d, r14d; Size
0x140001c6b  mov     dword ptr [rbp+80h+var_50.Data2], 11D0CD44h
0x140001c72  xor     edx, edx; Val
0x140001c74  mov     dword ptr [rbp+80h+var_50.Data4], 0C000C28Ch
0x140001c7b  lea     rcx, [rbp+80h+var_C0]; void *
0x140001c7f  mov     dword ptr [rbp+80h+var_50.Data4+4], 0EE95C24Fh
0x140001c86  call    memset_0
0x140001c8b  lea     r8, [rbp+80h+var_C0]; pWVTData
0x140001c8f  mov     [rbp+80h+var_C0], r14d
0x140001c93  lea     rdx, [rbp+80h+var_50]; pgActionID
0x140001c97  mov     [rbp+80h+var_90], 2
0x140001c9e  xor     ecx, ecx; hwnd
0x140001ca0  mov     [rbp+80h+var_88], rbx
0x140001ca4  call    cs:__imp_WinVerifyTrust
0x140001caa  test    rsi, rsi
0x140001cad  jz      short loc_140001CB8
0x140001caf  mov     rcx, rsi; hObject
0x140001cb2  call    cs:__imp_CloseHandle
0x140001cb8  mov     eax, edi
0x140001cba  mov     rcx, [rbp+80h+var_40]
0x140001cbe  xor     rcx, rsp; StackCookie
0x140001cc1  call    __security_check_cookie
0x140001cc6  add     rsp, 150h
0x140001ccd  pop     r15
0x140001ccf  pop     r14
0x140001cd1  pop     r12
0x140001cd3  pop     rdi
0x140001cd4  pop     rsi
0x140001cd5  pop     rbx
0x140001cd6  pop     rbp
0x140001cd7  retn
```
