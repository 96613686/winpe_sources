# FSMVirtualCamera::InternalValidateInfo(FSMVCamCreationInfo const &,ushort const *)

- ea: `0x180022880`
- end: `0x180022b0f`
- name: `?InternalValidateInfo@FSMVirtualCamera@@IEAAJAEBUFSMVCamCreationInfo@@PEBG@Z`
- size: `655`
- prototype: `__int64 __fastcall(FSMVirtualCamera *__hidden this, const struct FSMVCamCreationInfo *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002354c`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000d62c`
- `0x180022708`
- `0x180022880`
- `0x180025bf0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022a72`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022a72`

## pseudocode

```c
__int64 __fastcall FSMVirtualCamera::InternalValidateInfo(
        const WCHAR **this,
        const struct FSMVCamCreationInfo *a2,
        const char *a3)
{
  __int64 v6; // rcx
  const char *v7; // rdi
  const char *v8; // r8
  const char *v9; // rax
  const char *v10; // rax
  int v11; // edi
  __int64 v12; // rdx
  int v13; // eax
  const WCHAR *v14; // r8
  int v15; // ecx
  __int64 v16; // rdx
  unsigned __int8 Level; // al
  __int64 v18; // rdx

  v7 = L"<nullptr>";
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v8 = L"<nullptr>";
    if ( *(_QWORD *)(v6 + 464) != *(_QWORD *)(v6 + 472) )
      v8 = *(const char **)(v6 + 464);
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      213,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      v6,
      (__int64)v8);
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qddd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      214,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      this,
      *(_DWORD *)a2,
      *((_DWORD *)a2 + 1),
      *((_DWORD *)a2 + 2));
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v9 = L"<nullptr>";
    if ( *((_QWORD *)a2 + 2) )
      v9 = (const char *)*((_QWORD *)a2 + 2);
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      215,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (_DWORD)this,
      (__int64)v9);
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v10 = L"<nullptr>";
    if ( *((_QWORD *)a2 + 3) )
      v10 = (const char *)*((_QWORD *)a2 + 3);
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      216,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (_DWORD)this,
      (__int64)v10);
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    if ( a3 )
      v7 = a3;
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      217,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (_DWORD)this,
      (__int64)v7);
  }
  v11 = FSMVirtualCamera::InternalValidateData((FSMVirtualCamera *)this);
  if ( v11 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
LABEL_42:
      Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
LABEL_43:
      if ( Level )
      {
        v18 = 223;
        goto LABEL_45;
      }
      return (unsigned int)v11;
    }
    v12 = 218;
LABEL_22:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v11);
    goto LABEL_42;
  }
  if ( *((_DWORD *)this + 36) != *(_DWORD *)a2
    || *((_DWORD *)this + 37) != *((_DWORD *)a2 + 1)
    || (v13 = *((_DWORD *)this + 38), v13 != *((_DWORD *)a2 + 2)) )
  {
    v11 = -1072873843;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_42;
    v16 = 219;
    goto LABEL_41;
  }
  if ( !v13 )
  {
    v14 = this[50];
    if ( v14 == this[51] )
    {
      v11 = -1072873843;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_42;
      v16 = 220;
LABEL_41:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v15);
      goto LABEL_42;
    }
    if ( !a3 )
    {
      v11 = -2147024809;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_42;
      v12 = 221;
      goto LABEL_22;
    }
    if ( CompareStringOrdinal((LPCWCH)a3, -1, v14, -1, 1) != 2 )
    {
      v11 = -1072873843;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v16 = 222;
        goto LABEL_41;
      }
    }
  }
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( v11 < 0 )
    goto LABEL_43;
  if ( Level >= 8u )
  {
    v18 = 224;
LABEL_45:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v18, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180022880  push    rbx
0x180022882  push    rbp
0x180022883  push    rsi
0x180022884  push    rdi
0x180022885  push    r14
0x180022887  sub     rsp, 40h
0x18002288b  mov     rbp, r8
0x18002288e  mov     rsi, rdx
0x180022891  mov     rbx, rcx
0x180022894  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022899  lea     rdi, aNullptr; "<nullptr>"
0x1800228a0  lea     r14, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x1800228a7  cmp     al, 8
0x1800228a9  jb      short loc_1800228E3
0x1800228ab  mov     rax, [rcx+1D0h]
0x1800228b2  mov     r9, rcx
0x1800228b5  cmp     rax, [rcx+1D8h]
0x1800228bc  mov     r8, rdi
0x1800228bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228c6  mov     edx, 0D5h
0x1800228cb  cmovnz  r8, rax
0x1800228cf  mov     qword ptr [rsp+68h+bIgnoreCase], r8
0x1800228d4  mov     r8, r14
0x1800228d7  mov     rcx, [rcx+0D8h]
0x1800228de  call    WPP_SF_qS
0x1800228e3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800228e8  cmp     al, 8
0x1800228ea  jb      short loc_18002291E
0x1800228ec  mov     eax, [rsi+8]
0x1800228ef  mov     edx, 0D6h
0x1800228f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228fb  mov     r9, rbx
0x1800228fe  mov     [rsp+68h+var_38], eax
0x180022902  mov     r8, r14
0x180022905  mov     eax, [rsi+4]
0x180022908  mov     [rsp+68h+var_40], eax
0x18002290c  mov     eax, [rsi]
0x18002290e  mov     rcx, [rcx+0D8h]
0x180022915  mov     [rsp+68h+bIgnoreCase], eax
0x180022919  call    WPP_SF_qddd
0x18002291e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022923  cmp     al, 8
0x180022925  jb      short loc_180022957
0x180022927  mov     rcx, cs:WPP_GLOBAL_Control
0x18002292e  mov     rax, rdi
0x180022931  cmp     qword ptr [rsi+10h], 0
0x180022936  mov     edx, 0D7h
0x18002293b  mov     r9, rbx
0x18002293e  mov     r8, r14
0x180022941  cmovnz  rax, [rsi+10h]
0x180022946  mov     rcx, [rcx+0D8h]
0x18002294d  mov     qword ptr [rsp+68h+bIgnoreCase], rax
0x180022952  call    WPP_SF_qS
0x180022957  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18002295c  cmp     al, 8
0x18002295e  jb      short loc_180022990
0x180022960  mov     rcx, cs:WPP_GLOBAL_Control
0x180022967  mov     rax, rdi
0x18002296a  cmp     qword ptr [rsi+18h], 0
0x18002296f  mov     edx, 0D8h
0x180022974  mov     r9, rbx
0x180022977  mov     r8, r14
0x18002297a  cmovnz  rax, [rsi+18h]
0x18002297f  mov     rcx, [rcx+0D8h]
0x180022986  mov     qword ptr [rsp+68h+bIgnoreCase], rax
0x18002298b  call    WPP_SF_qS
0x180022990  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022995  cmp     al, 8
0x180022997  jb      short loc_1800229C3
0x180022999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229a0  test    rbp, rbp
0x1800229a3  mov     edx, 0D9h
0x1800229a8  mov     r9, rbx
0x1800229ab  cmovnz  rdi, rbp
0x1800229af  mov     r8, r14
0x1800229b2  mov     qword ptr [rsp+68h+bIgnoreCase], rdi
0x1800229b7  mov     rcx, [rcx+0D8h]
0x1800229be  call    WPP_SF_qS
0x1800229c3  mov     rcx, rbx; this
0x1800229c6  call    ?InternalValidateData@FSMVirtualCamera@@IEAAJXZ; FSMVirtualCamera::InternalValidateData(void)
0x1800229cb  mov     edi, eax
0x1800229cd  test    eax, eax
0x1800229cf  jns     short loc_1800229EC
0x1800229d1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800229d6  cmp     al, 1
0x1800229d8  jb      loc_180022AD7
0x1800229de  mov     edx, 0DAh
0x1800229e3  mov     [rsp+68h+bIgnoreCase], edi
0x1800229e7  jmp     loc_180022AC1
0x1800229ec  mov     eax, [rsi]
0x1800229ee  cmp     [rbx+90h], eax
0x1800229f4  jnz     loc_180022AA8
0x1800229fa  mov     eax, [rsi+4]
0x1800229fd  cmp     [rbx+94h], eax
0x180022a03  jnz     loc_180022AA8
0x180022a09  mov     eax, [rbx+98h]
0x180022a0f  cmp     eax, [rsi+8]
0x180022a12  jnz     loc_180022AA8
0x180022a18  test    eax, eax
0x180022a1a  jnz     short loc_180022A94
0x180022a1c  mov     r8, [rbx+190h]; lpString2
0x180022a23  cmp     r8, [rbx+198h]
0x180022a2a  jnz     short loc_180022A47
0x180022a2c  mov     ecx, 0C00D3E8Dh
0x180022a31  mov     edi, ecx
0x180022a33  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022a38  cmp     al, 1
0x180022a3a  jb      loc_180022AD7
0x180022a40  mov     edx, 0DCh
0x180022a45  jmp     short loc_180022ABD
0x180022a47  test    rbp, rbp
0x180022a4a  jnz     short loc_180022A61
0x180022a4c  mov     edi, 80070057h
0x180022a51  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022a56  cmp     al, 1
0x180022a58  jb      short loc_180022AD7
0x180022a5a  mov     edx, 0DDh
0x180022a5f  jmp     short loc_1800229E3
0x180022a61  or      edx, 0FFFFFFFFh; cchCount1
0x180022a64  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180022a6c  mov     r9d, edx; cchCount2
0x180022a6f  mov     rcx, rbp; lpString1
0x180022a72  call    cs:__imp_CompareStringOrdinal
0x180022a78  cmp     eax, 2
0x180022a7b  jz      short loc_180022A94
0x180022a7d  mov     ecx, 0C00D3E8Dh
0x180022a82  mov     edi, ecx
0x180022a84  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022a89  cmp     al, 1
0x180022a8b  jb      short loc_180022A94
0x180022a8d  mov     edx, 0DEh
0x180022a92  jmp     short loc_180022ABD
0x180022a94  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022a99  test    edi, edi
0x180022a9b  js      short loc_180022ADC
0x180022a9d  cmp     al, 8
0x180022a9f  jb      short loc_180022B02
0x180022aa1  mov     edx, 0E0h
0x180022aa6  jmp     short loc_180022AE5
0x180022aa8  mov     ecx, 0C00D3E8Dh
0x180022aad  mov     edi, ecx
0x180022aaf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022ab4  cmp     al, 1
0x180022ab6  jb      short loc_180022AD7
0x180022ab8  mov     edx, 0DBh
0x180022abd  mov     [rsp+68h+bIgnoreCase], ecx
0x180022ac1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ac8  mov     r9, rbx
0x180022acb  mov     r8, r14
0x180022ace  mov     rcx, [rcx+10h]
0x180022ad2  call    WPP_SF_qD
0x180022ad7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022adc  cmp     al, 1
0x180022ade  jb      short loc_180022B02
0x180022ae0  mov     edx, 0DFh
0x180022ae5  mov     rcx, cs:WPP_GLOBAL_Control
0x180022aec  mov     r9, rbx
0x180022aef  mov     r8, r14
0x180022af2  mov     [rsp+68h+bIgnoreCase], edi
0x180022af6  mov     rcx, [rcx+0D8h]
0x180022afd  call    WPP_SF_qD
0x180022b02  mov     eax, edi
0x180022b04  add     rsp, 40h
0x180022b08  pop     r14
0x180022b0a  pop     rdi
0x180022b0b  pop     rsi
0x180022b0c  pop     rbp
0x180022b0d  pop     rbx
0x180022b0e  retn
```
