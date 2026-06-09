# VerifyTrust(HWND__ *,ushort const *,ushort const *,ulong,ulong,int *)

- ea: `0x180013460`
- end: `0x180013687`
- name: `?VerifyTrust@@YAJPEAUHWND__@@PEBG1KKPEAH@Z`
- size: `551`
- prototype: `int(HWND, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180005ee0`

## callees

- `0x180001720`
- `0x1800021b8`
- `0x18000725c`
- `0x18001329c`
- `0x180013330`
- `0x180013460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013529`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001351a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001351a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013637`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x1800135fd`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x1800135fd`
- `WINTRUST!WinVerifyTrust` at `0x180013597`
- `WINTRUST!WinVerifyTrust` at `0x180013597`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1800135b3`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1800135b3`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800135e4`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800135e4`

## string_xrefs

- `0x180013533`: `Failed to open file %s error 0x%x`

## pseudocode

```c
__int64 __fastcall VerifyTrust(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        int *a6)
{
  HANDLE FileW; // rsi
  unsigned int v9; // edi
  BOOL v10; // r14d
  CRYPT_PROVIDER_DATA *v11; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  void **v14; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-99h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-91h]
  __int128 v18; // [rsp+40h] [rbp-79h] BYREF
  __int128 v19; // [rsp+50h] [rbp-69h]
  _DWORD pWVTData[10]; // [rsp+60h] [rbp-59h] BYREF
  __int128 *v21; // [rsp+88h] [rbp-31h]
  int v22; // [rsp+90h] [rbp-29h]
  HANDLE hStateData; // [rsp+98h] [rbp-21h]
  int v24; // [rsp+ACh] [rbp-Dh]
  GUID pgActionID; // [rsp+C0h] [rbp+7h] BYREF

  v18 = 0;
  v19 = 0;
  memset_0(pWVTData, 0, 0x58u);
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  *a6 = 0;
  AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 1u, 4u, L"VerifyTrust function called");
  FileW = CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(dwFlagsAndAttributes) = GetLastError();
    v9 = dwFlagsAndAttributes;
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      1u,
      2u,
      L"Failed to open file %s error 0x%x",
      a3,
      dwFlagsAndAttributes);
  }
  else
  {
    LODWORD(v18) = 32;
    *(_QWORD *)&v19 = FileW;
    *((_QWORD *)&v18 + 1) = a2;
    pWVTData[0] = 88;
    pWVTData[8] = 1;
    v24 = 1;
    pWVTData[6] = 2;
    v22 = 1;
    v21 = &v18;
    v9 = WinVerifyTrust(0, &pgActionID, pWVTData);
    v10 = hStateData != 0;
    if ( !v9 && hStateData )
    {
      v11 = WTHelperProvDataFromStateData(hStateData);
      if ( v11 )
      {
        ProvSignerFromChain = WTHelperGetProvSignerFromChain(v11, 0, 0, 0);
        if ( ProvSignerFromChain )
        {
          ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, 0);
          if ( ProvCertFromChain )
          {
            if ( (unsigned int)IsAuthenticodePublisherTrusted(ProvCertFromChain->pCert, v14) )
              *a6 = 1;
          }
          else
          {
            AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 1u, 2u, L"WTHelperGetProvCertFromChain FAILED");
          }
        }
        else
        {
          AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 1u, 2u, L"WTHelperGetProvSignerFromChain FAILED");
        }
      }
      else
      {
        AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 1u, 2u, L"Error getting Provider data from StateData");
      }
    }
    if ( v10 )
      CloseWVTStateData(hStateData);
    if ( FileW )
      CloseHandle(FileW);
  }
  dwCreationDisposition[0] = v9;
  AxISEvents::DebugMsg(
    (AxISEvents *)&qword_180021AD8,
    1u,
    4u,
    L"VerifyTrust function Returned with %0x",
    *(_QWORD *)dwCreationDisposition);
  return v9;
}

```

## disassembly

```asm
0x180013460  mov     [rsp-8+arg_0], rbx
0x180013465  mov     [rsp-8+arg_18], rsi
0x18001346a  push    rbp
0x18001346b  push    rdi
0x18001346c  push    r13
0x18001346e  push    r14
0x180013470  push    r15
0x180013472  lea     rbp, [rsp-27h]
0x180013477  sub     rsp, 0E0h
0x18001347e  mov     rax, cs:__security_cookie
0x180013485  xor     rax, rsp
0x180013488  mov     [rbp+47h+var_30], rax
0x18001348c  mov     r15, [rbp+47h+arg_28]
0x180013490  lea     rcx, [rbp+47h+pWVTData]; void *
0x180013494  xorps   xmm0, xmm0
0x180013497  mov     rdi, rdx
0x18001349a  xor     edx, edx; Val
0x18001349c  mov     rbx, r8
0x18001349f  movups  [rbp+47h+var_C0], xmm0
0x1800134a3  movups  [rbp+47h+var_B0], xmm0
0x1800134a7  lea     r8d, [rdx+58h]; Size
0x1800134ab  call    memset_0
0x1800134b0  mov     r8d, 4; unsigned __int8
0x1800134b6  mov     [rbp+47h+pgActionID.Data1], 0AAC56Bh
0x1800134bd  lea     r9, aVerifytrustFun_0; "VerifyTrust function called"
0x1800134c4  mov     dword ptr [rbp+47h+pgActionID.Data2], 11D0CD44h
0x1800134cb  lea     rcx, qword_180021AD8; this
0x1800134d2  mov     dword ptr [rbp+47h+pgActionID.Data4], 0C000C28Ch
0x1800134d9  mov     dword ptr [rbp+47h+pgActionID.Data4+4], 0EE95C24Fh
0x1800134e0  lea     r13d, [r8-3]
0x1800134e4  mov     dword ptr [r15], 0
0x1800134eb  mov     edx, r13d; unsigned int
0x1800134ee  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800134f3  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x1800134fc  xor     r9d, r9d; lpSecurityAttributes
0x1800134ff  mov     dword ptr [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180013507  mov     r8d, r13d; dwShareMode
0x18001350a  mov     edx, 80000000h; dwDesiredAccess
0x18001350f  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x180013517  mov     rcx, rbx; lpFileName
0x18001351a  call    cs:__imp_CreateFileW
0x180013520  mov     rsi, rax
0x180013523  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013527  jnz     short loc_180013559
0x180013529  call    cs:__imp_GetLastError
0x18001352f  mov     dword ptr [rsp+100h+dwFlagsAndAttributes], eax
0x180013533  lea     r9, aFailedToOpenFi; "Failed to open file %s error 0x%x"
0x18001353a  mov     edx, r13d; unsigned int
0x18001353d  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x180013542  lea     r8d, [r13+1]; unsigned __int8
0x180013546  mov     edi, eax
0x180013548  lea     rcx, qword_180021AD8; this
0x18001354f  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180013554  jmp     loc_18001363D
0x180013559  lea     rax, [rbp+47h+var_C0]
0x18001355d  mov     dword ptr [rbp+47h+var_C0], 20h ; ' '
0x180013564  xor     r14d, r14d
0x180013567  mov     qword ptr [rbp+47h+var_B0], rsi
0x18001356b  lea     r8, [rbp+47h+pWVTData]; pWVTData
0x18001356f  mov     qword ptr [rbp+47h+var_C0+8], rdi
0x180013573  lea     rdx, [rbp+47h+pgActionID]; pgActionID
0x180013577  mov     [rbp+47h+pWVTData], 58h ; 'X'
0x18001357e  xor     ecx, ecx; hwnd
0x180013580  mov     [rbp+47h+var_80], r13d
0x180013584  lea     ebx, [r14+2]
0x180013588  mov     [rbp+47h+var_54], r13d
0x18001358c  mov     [rbp+47h+var_88], ebx
0x18001358f  mov     [rbp+47h+var_70], r13d
0x180013593  mov     [rbp+47h+var_78], rax
0x180013597  call    cs:__imp_WinVerifyTrust
0x18001359d  mov     rcx, [rbp+47h+hStateData]; hStateData
0x1800135a1  mov     edi, eax
0x1800135a3  test    rcx, rcx
0x1800135a6  cmovnz  r14d, r13d
0x1800135aa  test    eax, eax
0x1800135ac  jnz     short loc_180013621
0x1800135ae  test    rcx, rcx
0x1800135b1  jz      short loc_180013621
0x1800135b3  call    cs:__imp_WTHelperProvDataFromStateData
0x1800135b9  test    rax, rax
0x1800135bc  jnz     short loc_1800135D9
0x1800135be  lea     r9, aErrorGettingPr; "Error getting Provider data from StateD"...
0x1800135c5  mov     r8d, ebx; unsigned __int8
0x1800135c8  lea     rcx, qword_180021AD8; this
0x1800135cf  mov     edx, r13d; unsigned int
0x1800135d2  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800135d7  jmp     short loc_180013621
0x1800135d9  xor     r9d, r9d; idxCounterSigner
0x1800135dc  xor     r8d, r8d; fCounterSigner
0x1800135df  xor     edx, edx; idxSigner
0x1800135e1  mov     rcx, rax; pProvData
0x1800135e4  call    cs:__imp_WTHelperGetProvSignerFromChain
0x1800135ea  test    rax, rax
0x1800135ed  jnz     short loc_1800135F8
0x1800135ef  lea     r9, aWthelpergetpro_1; "WTHelperGetProvSignerFromChain FAILED"
0x1800135f6  jmp     short loc_1800135C5
0x1800135f8  xor     edx, edx; idxCert
0x1800135fa  mov     rcx, rax; pSgnr
0x1800135fd  call    cs:__imp_WTHelperGetProvCertFromChain
0x180013603  test    rax, rax
0x180013606  jnz     short loc_180013611
0x180013608  lea     r9, aWthelpergetpro_2; "WTHelperGetProvCertFromChain FAILED"
0x18001360f  jmp     short loc_1800135C5
0x180013611  mov     rcx, [rax+8]; struct _CERT_CONTEXT *
0x180013615  call    ?IsAuthenticodePublisherTrusted@@YAHPEBU_CERT_CONTEXT@@PEAPEAX@Z; IsAuthenticodePublisherTrusted(_CERT_CONTEXT const *,void * *)
0x18001361a  test    eax, eax
0x18001361c  jz      short loc_180013621
0x18001361e  mov     [r15], r13d
0x180013621  test    r14d, r14d
0x180013624  jz      short loc_18001362F
0x180013626  mov     rcx, [rbp+47h+hStateData]; void *
0x18001362a  call    ?CloseWVTStateData@@YAXPEAX@Z; CloseWVTStateData(void *)
0x18001362f  test    rsi, rsi
0x180013632  jz      short loc_18001363D
0x180013634  mov     rcx, rsi; hObject
0x180013637  call    cs:__imp_CloseHandle
0x18001363d  lea     r9, aVerifytrustFun; "VerifyTrust function Returned with %0x"
0x180013644  mov     [rsp+100h+dwCreationDisposition], edi
0x180013648  mov     r8d, 4; unsigned __int8
0x18001364e  lea     rcx, qword_180021AD8; this
0x180013655  mov     edx, r13d; unsigned int
0x180013658  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18001365d  mov     eax, edi
0x18001365f  mov     rcx, [rbp+47h+var_30]
0x180013663  xor     rcx, rsp; StackCookie
0x180013666  call    __security_check_cookie
0x18001366b  lea     r11, [rsp+100h+var_20]
0x180013673  mov     rbx, [r11+30h]
0x180013677  mov     rsi, [r11+48h]
0x18001367b  mov     rsp, r11
0x18001367e  pop     r15
0x180013680  pop     r14
0x180013682  pop     r13
0x180013684  pop     rdi
0x180013685  pop     rbp
0x180013686  retn
```
