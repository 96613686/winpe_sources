# CTSCryptUtils::ImportSymmetricKey(ushort const *,uchar *,ulong)

- ea: `0x180042800`
- end: `0x180042a5a`
- name: `?ImportSymmetricKey@CTSCryptUtils@@QEAAJPEBGPEAEK@Z`
- size: `602`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *phKey, LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003a510`

## callees

- `0x18001a880`
- `0x180042420`
- `0x180042800`
- `0x18004301c`
- `0x180043070`
- `0x1800430f4`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800428cb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800428cb`
- `bcrypt!BCryptGetProperty` at `0x18004295e`
- `bcrypt!BCryptGetProperty` at `0x18004295e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180042a3d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180042a3d`
- `bcrypt!BCryptImportKey` at `0x1800429e6`
- `bcrypt!BCryptImportKey` at `0x1800429e6`

## pseudocode

```c
__int64 __fastcall CTSCryptUtils::ImportSymmetricKey(
        BCRYPT_KEY_HANDLE *phKey,
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        ULONG cbInput)
{
  int ActivityIdPrefix; // eax
  int v9; // r8d
  int v10; // edx
  const char *v11; // rcx
  int v12; // ebx
  NTSTATUS v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rdx
  ULONG *v17; // r14
  NTSTATUS Property; // ebx
  void *v19; // rax
  BCRYPT_ALG_HANDLE v20; // rcx
  NTSTATUS v21; // ebx
  ULONG dwFlags; // [rsp+28h] [rbp-50h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+88h] [rbp+10h] BYREF

  phAlgorithm = 0;
  pcbResult = 0;
  if ( !pszAlgId )
  {
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    v10 = 34;
    v11 = "pszAlgId";
LABEL_6:
    WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v9, ActivityIdPrefix, (__int64)v11);
LABEL_7:
    v12 = -2147024809;
    goto LABEL_33;
  }
  if ( !pbInput )
  {
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    v10 = 35;
    v11 = "pBlob";
    goto LABEL_6;
  }
  CTSCryptUtils::Clear((CTSCryptUtils *)phKey);
  v13 = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0);
  if ( v13 && (v12 = v13 | 0x10000000, v12 < 0) )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpX_GetActivityIdPrefix();
      v16 = 36;
LABEL_19:
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v15, v14, v12);
    }
  }
  else
  {
    v17 = (ULONG *)(phKey + 5);
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)phKey + 40, 4u, &pcbResult, 0);
    if ( Property && (v12 = Property | 0x10000000, v12 < 0) )
    {
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpX_GetActivityIdPrefix();
        v16 = 37;
        goto LABEL_19;
      }
    }
    else
    {
      v19 = operator new(*v17);
      dwFlags = *v17;
      v20 = phAlgorithm;
      phKey[4] = v19;
      v21 = BCryptImportKey(v20, 0, L"KeyDataBlob", phKey, (PUCHAR)v19, dwFlags, pbInput, cbInput, 0);
      if ( v21 && (v12 = v21 | 0x10000000, v12 < 0) )
      {
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpX_GetActivityIdPrefix();
          v16 = 38;
          goto LABEL_19;
        }
      }
      else
      {
        *((_DWORD *)phKey + 6) = 1;
        v12 = 0;
      }
    }
  }
LABEL_33:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180042800  mov     rax, rsp
0x180042803  mov     [rax+8], rbx
0x180042807  mov     [rax+18h], rbp
0x18004280b  push    rsi
0x18004280c  push    rdi
0x18004280d  push    r14
0x18004280f  sub     rsp, 60h
0x180042813  mov     ebp, r9d
0x180042816  mov     qword ptr [rax-28h], 0
0x18004281e  mov     rsi, r8
0x180042821  mov     dword ptr [rax+10h], 0
0x180042828  mov     rbx, rdx
0x18004282b  mov     rdi, rcx
0x18004282e  test    rdx, rdx
0x180042831  jnz     short loc_180042883
0x180042833  mov     rcx, cs:WPP_GLOBAL_Control
0x18004283a  lea     rax, WPP_GLOBAL_Control
0x180042841  cmp     rcx, rax
0x180042844  jz      short loc_180042879
0x180042846  test    byte ptr [rcx+1Ch], 8
0x18004284a  jz      short loc_180042879
0x18004284c  cmp     byte ptr [rcx+19h], 2
0x180042850  jb      short loc_180042879
0x180042852  call    RdpX_GetActivityIdPrefix
0x180042857  lea     edx, [rbx+22h]
0x18004285a  lea     rcx, aPszalgid; "pszAlgId"
0x180042861  mov     [rsp+78h+pcbResult], rcx
0x180042866  mov     r9d, eax
0x180042869  mov     rcx, cs:WPP_GLOBAL_Control
0x180042870  mov     rcx, [rcx+10h]
0x180042874  call    WPP_SF_Ds
0x180042879  mov     ebx, 80070057h
0x18004287e  jmp     loc_180042A31
0x180042883  test    rsi, rsi
0x180042886  jnz     short loc_1800428B8
0x180042888  mov     rcx, cs:WPP_GLOBAL_Control
0x18004288f  lea     rax, WPP_GLOBAL_Control
0x180042896  cmp     rcx, rax
0x180042899  jz      short loc_180042879
0x18004289b  test    byte ptr [rcx+1Ch], 8
0x18004289f  jz      short loc_180042879
0x1800428a1  cmp     byte ptr [rcx+19h], 2
0x1800428a5  jb      short loc_180042879
0x1800428a7  call    RdpX_GetActivityIdPrefix
0x1800428ac  lea     edx, [rsi+23h]
0x1800428af  lea     rcx, aPblob; "pBlob"
0x1800428b6  jmp     short loc_180042861
0x1800428b8  call    ?Clear@CTSCryptUtils@@QEAAXXZ; CTSCryptUtils::Clear(void)
0x1800428bd  xor     r9d, r9d; dwFlags
0x1800428c0  lea     rcx, [rsp+78h+phAlgorithm]; phAlgorithm
0x1800428c5  xor     r8d, r8d; pszImplementation
0x1800428c8  mov     rdx, rbx; pszAlgId
0x1800428cb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800428d1  mov     ebx, eax
0x1800428d3  test    eax, eax
0x1800428d5  jz      short loc_180042930
0x1800428d7  or      ebx, 10000000h
0x1800428dd  jge     short loc_180042930
0x1800428df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800428e6  lea     rax, WPP_GLOBAL_Control
0x1800428ed  cmp     rcx, rax
0x1800428f0  jz      loc_180042A31
0x1800428f6  test    byte ptr [rcx+1Ch], 8
0x1800428fa  jz      loc_180042A31
0x180042900  cmp     byte ptr [rcx+19h], 2
0x180042904  jb      loc_180042A31
0x18004290a  call    RdpX_GetActivityIdPrefix
0x18004290f  mov     edx, 24h ; '$'
0x180042914  mov     rcx, cs:WPP_GLOBAL_Control
0x18004291b  mov     r9d, eax
0x18004291e  mov     dword ptr [rsp+78h+pcbResult], ebx
0x180042922  mov     rcx, [rcx+10h]
0x180042926  call    WPP_SF_DD
0x18004292b  jmp     loc_180042A31
0x180042930  mov     rcx, [rsp+78h+phAlgorithm]; hObject
0x180042935  lea     rax, [rsp+78h+arg_8]
0x18004293d  lea     r14, [rdi+28h]
0x180042941  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180042949  mov     r8, r14; pbOutput
0x18004294c  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180042951  mov     r9d, 4; cbOutput
0x180042957  lea     rdx, aObjectlength; "ObjectLength"
0x18004295e  call    cs:__imp_BCryptGetProperty
0x180042964  mov     ebx, eax
0x180042966  test    eax, eax
0x180042968  jz      short loc_1800429AC
0x18004296a  or      ebx, 10000000h
0x180042970  jge     short loc_1800429AC
0x180042972  mov     rcx, cs:WPP_GLOBAL_Control
0x180042979  lea     rax, WPP_GLOBAL_Control
0x180042980  cmp     rcx, rax
0x180042983  jz      loc_180042A31
0x180042989  test    byte ptr [rcx+1Ch], 8
0x18004298d  jz      loc_180042A31
0x180042993  cmp     byte ptr [rcx+19h], 2
0x180042997  jb      loc_180042A31
0x18004299d  call    RdpX_GetActivityIdPrefix
0x1800429a2  mov     edx, 25h ; '%'
0x1800429a7  jmp     loc_180042914
0x1800429ac  mov     ecx, [r14]; Size
0x1800429af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800429b4  mov     ecx, [r14]
0x1800429b7  lea     r8, pszBlobType; "KeyDataBlob"
0x1800429be  mov     [rsp+78h+var_38], 0; dwFlags
0x1800429c6  mov     r9, rdi; phKey
0x1800429c9  mov     [rsp+78h+cbInput], ebp; cbInput
0x1800429cd  xor     edx, edx; hImportKey
0x1800429cf  mov     [rsp+78h+pbInput], rsi; pbInput
0x1800429d4  mov     [rsp+78h+dwFlags], ecx; cbKeyObject
0x1800429d8  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x1800429dd  mov     [rdi+20h], rax
0x1800429e1  mov     [rsp+78h+pcbResult], rax; pbKeyObject
0x1800429e6  call    cs:__imp_BCryptImportKey
0x1800429ec  mov     ebx, eax
0x1800429ee  test    eax, eax
0x1800429f0  jz      short loc_180042A28
0x1800429f2  or      ebx, 10000000h
0x1800429f8  jge     short loc_180042A28
0x1800429fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a01  lea     rax, WPP_GLOBAL_Control
0x180042a08  cmp     rcx, rax
0x180042a0b  jz      short loc_180042A31
0x180042a0d  test    byte ptr [rcx+1Ch], 8
0x180042a11  jz      short loc_180042A31
0x180042a13  cmp     byte ptr [rcx+19h], 2
0x180042a17  jb      short loc_180042A31
0x180042a19  call    RdpX_GetActivityIdPrefix
0x180042a1e  mov     edx, 26h ; '&'
0x180042a23  jmp     loc_180042914
0x180042a28  mov     dword ptr [rdi+18h], 1
0x180042a2f  xor     ebx, ebx
0x180042a31  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x180042a36  test    rcx, rcx
0x180042a39  jz      short loc_180042A43
0x180042a3b  xor     edx, edx; dwFlags
0x180042a3d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180042a43  lea     r11, [rsp+78h+var_18]
0x180042a48  mov     eax, ebx
0x180042a4a  mov     rbx, [r11+20h]
0x180042a4e  mov     rbp, [r11+30h]
0x180042a52  mov     rsp, r11
0x180042a55  pop     r14
0x180042a57  pop     rdi
0x180042a58  pop     rsi
0x180042a59  retn
```
