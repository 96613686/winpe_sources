# I_ReaderListCngPopulateCredsViaContainerEnumeration

- ea: `0x180016958`
- end: `0x180016d6e`
- name: `I_ReaderListCngPopulateCredsViaContainerEnumeration`
- size: `1046`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800135d0`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180016958`
- `0x180017f9c`
- `0x18001bfd4`
- `0x18001cb0c`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a00`
- `CRYPT32!CertOpenStore` at `0x1800169ee`
- `CRYPT32!CertOpenStore` at `0x1800169ee`
- `ncrypt!NCryptEnumKeys` at `0x180016bef`
- `ncrypt!NCryptEnumKeys` at `0x180016c59`
- `ncrypt!NCryptEnumKeys` at `0x180016bef`
- `ncrypt!NCryptEnumKeys` at `0x180016c59`
- `ncrypt!NCryptFreeBuffer` at `0x180016c35`
- `ncrypt!NCryptFreeBuffer` at `0x180016ccd`
- `ncrypt!NCryptFreeBuffer` at `0x180016cdc`
- `ncrypt!NCryptFreeBuffer` at `0x180016c35`
- `ncrypt!NCryptFreeBuffer` at `0x180016ccd`
- `ncrypt!NCryptFreeBuffer` at `0x180016cdc`
- `cryptngc!NgcQueryEffectiveCertPolicy` at `0x180016bc2`
- `cryptngc!NgcQueryEffectiveCertPolicy` at `0x180016bc2`

## pseudocode

```c
__int64 __fastcall I_ReaderListCngPopulateCredsViaContainerEnumeration(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v4; // r12d
  NCryptKeyName **p_ppKeyName; // rdi
  HCERTSTORE v8; // rax
  DWORD CngKey; // ebx
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int v12; // edx
  __int64 v13; // r15
  __int64 v14; // rsi
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  _DWORD *v21; // rax
  bool v22; // zf
  int v23; // eax
  int v24; // esi
  SECURITY_STATUS v25; // eax
  int v26; // r15d
  __int64 v27; // rcx
  NCRYPT_PROV_HANDLE v28; // rcx
  unsigned int v29; // eax
  NCryptKeyName *v30; // rcx
  char v31; // al
  __int64 v33; // [rsp+0h] [rbp-30h] BYREF
  void *pvPara; // [rsp+20h] [rbp-10h]
  int v35; // [rsp+30h] [rbp+0h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+38h] [rbp+8h] BYREF
  int v37; // [rsp+40h] [rbp+10h] BYREF
  PVOID ppEnumState; // [rsp+48h] [rbp+18h] BYREF
  int v39; // [rsp+50h] [rbp+20h] BYREF
  __int64 v40; // [rsp+58h] [rbp+28h]
  __int64 v41; // [rsp+60h] [rbp+30h]

  v40 = a2;
  ppEnumState = 0;
  v4 = 0;
  ppKeyName = 0;
  p_ppKeyName = 0;
  v35 = 0;
  v41 = a1;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v8 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  *(_QWORD *)(a3 + 168) = v8;
  if ( v8 )
  {
    CngKey = I_SetupNCryptStorageProvider(a3);
    if ( CngKey )
    {
      WppTraceIndent(v10, 2);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 144;
        LODWORD(pvPara) = CngKey;
LABEL_12:
        WPP_SF_sd(
          v11[2],
          v12,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          (char)pvPara);
      }
    }
    else
    {
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(*(_QWORD *)a3 + 2 * v14) );
      v15 = 2 * v14 + 12;
      if ( !v15 )
        goto LABEL_23;
      if ( v15 > g_ulMaxStackAllocSize )
        goto LABEL_23;
      v16 = v15 + g_ulAdditionalProbeSize + 8;
      if ( v16 < v15 || !(unsigned int)VerifyStackAvailable(v16, 0) )
        goto LABEL_23;
      v17 = v15 + 23;
      if ( v15 + 23 <= v15 + 8 )
        v17 = 0xFFFFFFFFFFFFFF0LL;
      v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
      v19 = alloca(v18);
      v20 = alloca(v18);
      p_ppKeyName = (NCryptKeyName **)&v35;
      if ( &v33 == (__int64 *)-48LL || (v35 = 1801679955, (p_ppKeyName = &ppKeyName) == 0) )
      {
LABEL_23:
        v18 = v15 + 8;
        if ( v15 + 8 >= v15 )
        {
          v21 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, _QWORD))g_pfnAllocate)(v18, 0);
          p_ppKeyName = (NCryptKeyName **)v21;
          if ( v21 )
          {
            *v21 = 1885431112;
            p_ppKeyName = (NCryptKeyName **)(v21 + 2);
          }
        }
      }
      if ( p_ppKeyName )
      {
        do
          ++v13;
        while ( *(_WORD *)(*(_QWORD *)a3 + 2 * v13) );
        if ( StringCchPrintfW((STRSAFE_LPWSTR)p_ppKeyName, v13 + 6, L"\\\\.\\%s\\") >= 0 )
        {
          v22 = *(_DWORD *)(a3 + 12) == 1024;
          v37 = 0;
          if ( v22 && (v39 = 0, v23 = NgcQueryEffectiveCertPolicy(0, &v37, &v39), v23 < 0) )
          {
            CngKey = v23;
          }
          else
          {
            v24 = 0;
            v25 = NCryptEnumKeys(*(_QWORD *)(a3 + 136), (LPCWSTR)p_ppKeyName, &ppKeyName, &ppEnumState, 0x40u);
            v26 = v40;
            v4 = v25;
            while ( 1 )
            {
              if ( v4 )
              {
                v29 = 0;
                *a4 = v24;
                if ( v4 != -2146893782 )
                  v29 = v4;
                v4 = v29;
                goto LABEL_49;
              }
              CngKey = I_ReaderListReadCngKey(v41, a3, (_DWORD)ppKeyName, v26, v37, (__int64)&v35);
              if ( CngKey == 8 )
                break;
              CngKey = 0;
              NCryptFreeBuffer(ppKeyName);
              v28 = *(_QWORD *)(a3 + 136);
              ppKeyName = 0;
              v4 = NCryptEnumKeys(v28, (LPCWSTR)p_ppKeyName, &ppKeyName, &ppEnumState, 0x40u);
              if ( v35 )
              {
                ++v24;
                v35 = 0;
              }
            }
            WppTraceIndent(v27, 2);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 146;
              LODWORD(pvPara) = 8;
              goto LABEL_12;
            }
          }
        }
        else
        {
          CngKey = 122;
        }
      }
      else
      {
        WppTraceIndent(v18, 2);
        CngKey = 8;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            145,
            &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent);
        }
      }
    }
  }
  else
  {
    CngKey = GetLastError();
  }
LABEL_49:
  if ( ppEnumState )
    NCryptFreeBuffer(ppEnumState);
  v30 = ppKeyName;
  if ( ppKeyName )
    NCryptFreeBuffer(ppKeyName);
  if ( p_ppKeyName )
  {
    v30 = (NCryptKeyName *)(p_ppKeyName - 1);
    if ( *((_DWORD *)p_ppKeyName - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  WppTraceIndent(v30, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v31 = CngKey;
    if ( !CngKey )
      v31 = v4;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      147,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v31);
  }
  if ( !CngKey )
    return v4;
  return CngKey;
}

```

## disassembly

```asm
0x180016958  push    rbp
0x18001695a  push    rbx
0x18001695b  push    rsi
0x18001695c  push    rdi
0x18001695d  push    r12
0x18001695f  push    r13
0x180016961  push    r14
0x180016963  push    r15
0x180016965  sub     rsp, 78h
0x180016969  lea     rbp, [rsp+30h]
0x18001696e  mov     rax, cs:__security_cookie
0x180016975  xor     rax, rbp
0x180016978  mov     [rbp+80h+var_48], rax
0x18001697c  xor     ebx, ebx
0x18001697e  mov     [rbp+80h+var_58], rdx
0x180016982  xor     edx, edx
0x180016984  mov     [rbp+80h+ppEnumState], rbx
0x180016988  mov     r12d, ebx
0x18001698b  mov     [rbp+80h+ppKeyName], rbx
0x18001698f  mov     edi, ebx
0x180016991  mov     [rbp+80h+var_80], ebx
0x180016994  mov     r13, r9
0x180016997  mov     [rbp+80h+var_50], rcx
0x18001699b  mov     r14, r8
0x18001699e  call    WppTraceIndent
0x1800169a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169aa  lea     rsi, WPP_GLOBAL_Control
0x1800169b1  cmp     rcx, rsi
0x1800169b4  jz      short loc_1800169DE
0x1800169b6  test    byte ptr [rcx+1Ch], 2
0x1800169ba  jz      short loc_1800169DE
0x1800169bc  cmp     byte ptr [rcx+19h], 5
0x1800169c0  jb      short loc_1800169DE
0x1800169c2  mov     r9, cs:WPP_pszIndent
0x1800169c9  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800169d0  mov     rcx, [rcx+10h]
0x1800169d4  mov     edx, 8Fh
0x1800169d9  call    WPP_SF_s
0x1800169de  xor     edx, edx; dwEncodingType
0x1800169e0  mov     [rsp+0B0h+pvPara], rbx; pvPara
0x1800169e5  xor     r9d, r9d; dwFlags
0x1800169e8  xor     r8d, r8d; hCryptProv
0x1800169eb  lea     ecx, [rdx+2]; lpszStoreProvider
0x1800169ee  call    cs:__imp_CertOpenStore
0x1800169f4  mov     [r14+0A8h], rax
0x1800169fb  test    rax, rax
0x1800169fe  jnz     short loc_180016A0D
0x180016a00  call    cs:__imp_GetLastError
0x180016a06  mov     ebx, eax
0x180016a08  jmp     loc_180016CC4
0x180016a0d  mov     rcx, r14
0x180016a10  call    I_SetupNCryptStorageProvider
0x180016a15  xor     edx, edx
0x180016a17  mov     ebx, eax
0x180016a19  test    eax, eax
0x180016a1b  jz      short loc_180016A70
0x180016a1d  mov     edx, 2
0x180016a22  call    WppTraceIndent
0x180016a27  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a2e  cmp     rcx, rsi
0x180016a31  jz      loc_180016CC4
0x180016a37  test    byte ptr [rcx+1Ch], 1
0x180016a3b  jz      loc_180016CC4
0x180016a41  cmp     byte ptr [rcx+19h], 2
0x180016a45  jb      loc_180016CC4
0x180016a4b  mov     edx, 90h
0x180016a50  mov     dword ptr [rsp+0B0h+pvPara], ebx
0x180016a54  mov     r9, cs:WPP_pszIndent
0x180016a5b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016a62  mov     rcx, [rcx+10h]
0x180016a66  call    WPP_SF_sd
0x180016a6b  jmp     loc_180016CC4
0x180016a70  mov     rax, [r14]
0x180016a73  or      r15, 0FFFFFFFFFFFFFFFFh
0x180016a77  mov     rsi, r15
0x180016a7a  inc     rsi
0x180016a7d  cmp     [rax+rsi*2], dx
0x180016a81  jnz     short loc_180016A7A
0x180016a83  lea     rsi, ds:0Ch[rsi*2]
0x180016a8b  test    rsi, rsi
0x180016a8e  jz      short loc_180016AF3
0x180016a90  cmp     rsi, cs:g_ulMaxStackAllocSize
0x180016a97  ja      short loc_180016AF3
0x180016a99  mov     rcx, cs:g_ulAdditionalProbeSize
0x180016aa0  add     rcx, 8
0x180016aa4  add     rcx, rsi
0x180016aa7  cmp     rcx, rsi
0x180016aaa  jb      short loc_180016AF3
0x180016aac  call    VerifyStackAvailable
0x180016ab1  xor     edx, edx
0x180016ab3  test    eax, eax
0x180016ab5  jz      short loc_180016AF3
0x180016ab7  lea     rax, [rsi+8]
0x180016abb  lea     rcx, [rax+0Fh]
0x180016abf  cmp     rcx, rax
0x180016ac2  ja      short loc_180016ACE
0x180016ac4  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180016ace  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180016ad2  mov     rax, rcx
0x180016ad5  call    _alloca_probe
0x180016ada  sub     rsp, rcx
0x180016add  lea     rdi, [rsp+0B0h+var_80]
0x180016ae2  test    rdi, rdi
0x180016ae5  jz      short loc_180016AF3
0x180016ae7  mov     dword ptr [rdi], 6B637453h
0x180016aed  add     rdi, 8
0x180016af1  jnz     short loc_180016B1C
0x180016af3  lea     rcx, [rsi+8]
0x180016af7  cmp     rcx, rsi
0x180016afa  jb      short loc_180016B1C
0x180016afc  mov     rax, cs:g_pfnAllocate
0x180016b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b08  xor     edx, edx
0x180016b0a  mov     rdi, rax
0x180016b0d  test    rax, rax
0x180016b10  jz      short loc_180016B1C
0x180016b12  mov     dword ptr [rax], 70616548h
0x180016b18  add     rdi, 8
0x180016b1c  test    rdi, rdi
0x180016b1f  jnz     short loc_180016B78
0x180016b21  lea     edx, [rdi+2]
0x180016b24  call    WppTraceIndent
0x180016b29  lea     ebx, [rdi+8]
0x180016b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b33  lea     rsi, WPP_GLOBAL_Control
0x180016b3a  cmp     rcx, rsi
0x180016b3d  jz      loc_180016CC4
0x180016b43  test    byte ptr [rcx+1Ch], 1
0x180016b47  jz      loc_180016CC4
0x180016b4d  cmp     byte ptr [rcx+19h], 2
0x180016b51  jb      loc_180016CC4
0x180016b57  mov     r9, cs:WPP_pszIndent
0x180016b5e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016b65  mov     rcx, [rcx+10h]
0x180016b69  mov     edx, 91h
0x180016b6e  call    WPP_SF_s
0x180016b73  jmp     loc_180016CC4
0x180016b78  mov     r9, [r14]
0x180016b7b  inc     r15
0x180016b7e  cmp     [r9+r15*2], dx
0x180016b83  jnz     short loc_180016B7B
0x180016b85  lea     rdx, [r15+6]; cchDest
0x180016b89  mov     rcx, rdi; pszDest
0x180016b8c  lea     r8, aS; "\\\\.\\%s\\"
0x180016b93  call    StringCchPrintfW
0x180016b98  test    eax, eax
0x180016b9a  jns     short loc_180016BA6
0x180016b9c  mov     ebx, 7Ah ; 'z'
0x180016ba1  jmp     loc_180016CBD
0x180016ba6  cmp     dword ptr [r14+0Ch], 400h
0x180016bae  mov     [rbp+80h+var_70], r12d
0x180016bb2  jnz     short loc_180016BD3
0x180016bb4  lea     r8, [rbp+80h+var_60]
0x180016bb8  mov     [rbp+80h+var_60], r12d
0x180016bbc  lea     rdx, [rbp+80h+var_70]
0x180016bc0  xor     ecx, ecx
0x180016bc2  call    cs:__imp_NgcQueryEffectiveCertPolicy
0x180016bc8  test    eax, eax
0x180016bca  jns     short loc_180016BD3
0x180016bcc  mov     ebx, eax
0x180016bce  jmp     loc_180016CBD
0x180016bd3  mov     rcx, [r14+88h]; hProvider
0x180016bda  lea     r9, [rbp+80h+ppEnumState]; ppEnumState
0x180016bde  xor     esi, esi
0x180016be0  mov     dword ptr [rsp+0B0h+pvPara], 40h ; '@'; dwFlags
0x180016be8  lea     r8, [rbp+80h+ppKeyName]; ppKeyName
0x180016bec  mov     rdx, rdi; pszScope
0x180016bef  call    cs:__imp_NCryptEnumKeys
0x180016bf5  mov     r15, [rbp+80h+var_58]
0x180016bf9  mov     r12d, eax
0x180016bfc  test    r12d, r12d
0x180016bff  jnz     loc_180016CA9
0x180016c05  mov     ecx, [rbp+80h+var_70]
0x180016c08  lea     rax, [rbp+80h+var_80]
0x180016c0c  mov     r8, [rbp+80h+ppKeyName]
0x180016c10  mov     r9, r15
0x180016c13  mov     [rsp+0B0h+var_88], rax
0x180016c18  mov     rdx, r14
0x180016c1b  mov     dword ptr [rsp+0B0h+pvPara], ecx
0x180016c1f  mov     rcx, [rbp+80h+var_50]
0x180016c23  call    I_ReaderListReadCngKey
0x180016c28  mov     ebx, eax
0x180016c2a  cmp     eax, 8
0x180016c2d  jz      short loc_180016C6E
0x180016c2f  mov     rcx, [rbp+80h+ppKeyName]; pvInput
0x180016c33  xor     ebx, ebx
0x180016c35  call    cs:__imp_NCryptFreeBuffer
0x180016c3b  mov     rcx, [r14+88h]; hProvider
0x180016c42  lea     r9, [rbp+80h+ppEnumState]; ppEnumState
0x180016c46  lea     r8, [rbp+80h+ppKeyName]; ppKeyName
0x180016c4a  mov     [rbp+80h+ppKeyName], rbx
0x180016c4e  mov     rdx, rdi; pszScope
0x180016c51  mov     dword ptr [rsp+0B0h+pvPara], 40h ; '@'; dwFlags
0x180016c59  call    cs:__imp_NCryptEnumKeys
0x180016c5f  mov     r12d, eax
0x180016c62  cmp     [rbp+80h+var_80], ebx
0x180016c65  jz      short loc_180016BFC
0x180016c67  inc     esi
0x180016c69  mov     [rbp+80h+var_80], ebx
0x180016c6c  jmp     short loc_180016BFC
0x180016c6e  mov     edx, 2
0x180016c73  call    WppTraceIndent
0x180016c78  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c7f  lea     rsi, WPP_GLOBAL_Control
0x180016c86  cmp     rcx, rsi
0x180016c89  jz      short loc_180016CC4
0x180016c8b  test    byte ptr [rcx+1Ch], 1
0x180016c8f  jz      short loc_180016CC4
0x180016c91  cmp     byte ptr [rcx+19h], 2
0x180016c95  jb      short loc_180016CC4
0x180016c97  mov     edx, 92h
0x180016c9c  mov     dword ptr [rsp+0B0h+pvPara], 8
0x180016ca4  jmp     loc_180016A54
0x180016ca9  xor     eax, eax
0x180016cab  mov     [r13+0], esi
0x180016caf  cmp     r12d, 8009002Ah
0x180016cb6  cmovnz  eax, r12d
0x180016cba  mov     r12d, eax
0x180016cbd  lea     rsi, WPP_GLOBAL_Control
0x180016cc4  mov     rcx, [rbp+80h+ppEnumState]; pvInput
0x180016cc8  test    rcx, rcx
0x180016ccb  jz      short loc_180016CD3
0x180016ccd  call    cs:__imp_NCryptFreeBuffer
0x180016cd3  mov     rcx, [rbp+80h+ppKeyName]; pvInput
0x180016cd7  test    rcx, rcx
0x180016cda  jz      short loc_180016CE2
0x180016cdc  call    cs:__imp_NCryptFreeBuffer
0x180016ce2  test    rdi, rdi
0x180016ce5  jz      short loc_180016CFF
0x180016ce7  lea     rcx, [rdi-8]
0x180016ceb  cmp     dword ptr [rcx], 70616548h
0x180016cf1  jnz     short loc_180016CFF
0x180016cf3  mov     rax, cs:g_pfnFree
0x180016cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cff  mov     edx, 1
0x180016d04  call    WppTraceIndent
0x180016d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d10  cmp     rcx, rsi
0x180016d13  jz      short loc_180016D49
0x180016d15  test    byte ptr [rcx+1Ch], 2
0x180016d19  jz      short loc_180016D49
0x180016d1b  cmp     byte ptr [rcx+19h], 5
0x180016d1f  jb      short loc_180016D49
0x180016d21  mov     r9, cs:WPP_pszIndent
0x180016d28  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016d2f  mov     rcx, [rcx+10h]
0x180016d33  test    ebx, ebx
0x180016d35  mov     eax, ebx
0x180016d37  mov     edx, 93h
0x180016d3c  cmovz   eax, r12d
0x180016d40  mov     dword ptr [rsp+0B0h+pvPara], eax
0x180016d44  call    WPP_SF_sd
0x180016d49  test    ebx, ebx
0x180016d4b  cmovz   ebx, r12d
0x180016d4f  mov     eax, ebx
0x180016d51  mov     rcx, [rbp+80h+var_48]
0x180016d55  xor     rcx, rbp; StackCookie
0x180016d58  call    __security_check_cookie
0x180016d5d  lea     rsp, [rbp+48h]
0x180016d61  pop     r15
0x180016d63  pop     r14
0x180016d65  pop     r13
0x180016d67  pop     r12
0x180016d69  pop     rdi
0x180016d6a  pop     rsi
0x180016d6b  pop     rbx
0x180016d6c  pop     rbp
0x180016d6d  retn
```
