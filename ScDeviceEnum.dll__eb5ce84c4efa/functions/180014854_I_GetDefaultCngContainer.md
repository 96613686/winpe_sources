# I_GetDefaultCngContainer

- ea: `0x180014854`
- end: `0x180014c99`
- name: `I_GetDefaultCngContainer`
- size: `1093`
- prototype: `__int64 __fastcall(_QWORD *, BYTE **)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800135d0`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180014854`
- `0x18001bfd4`
- `0x18001cb0c`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014bed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014bed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014b1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014b1c`
- `ncrypt!NCryptGetProperty` at `0x180014abf`
- `ncrypt!NCryptGetProperty` at `0x180014b8c`
- `ncrypt!NCryptGetProperty` at `0x180014abf`
- `ncrypt!NCryptGetProperty` at `0x180014b8c`
- `ncrypt!NCryptOpenKey` at `0x180014a90`
- `ncrypt!NCryptOpenKey` at `0x180014a90`
- `ncrypt!NCryptFreeObject` at `0x180014c26`
- `ncrypt!NCryptFreeObject` at `0x180014c26`

## pseudocode

```c
__int64 __fastcall I_GetDefaultCngContainer(_QWORD *a1, BYTE **a2)
{
  unsigned int Property; // esi
  __int64 v5; // r14
  __int64 v6; // rdi
  unsigned __int64 v7; // rdi
  wchar_t *p_pcbResult; // rbx
  __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  unsigned __int64 v12; // rcx
  wchar_t *v13; // rax
  DWORD v14; // edi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rcx
  BYTE *v22; // r14
  __int64 v23; // rcx
  NCRYPT_KEY_HANDLE v24; // rcx
  char v25; // al
  __int64 v27; // [rsp+0h] [rbp-30h] BYREF
  DWORD dwFlags[2]; // [rsp+20h] [rbp-10h]
  DWORD pcbResult; // [rsp+30h] [rbp+0h] BYREF
  NCRYPT_KEY_HANDLE phKey[2]; // [rsp+38h] [rbp+8h] BYREF

  pcbResult = 0;
  Property = 0;
  phKey[0] = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(*a1 + 2 * v6) );
  v7 = 2 * v6 + 12;
  p_pcbResult = 0;
  if ( !v7
    || v7 > g_ulMaxStackAllocSize
    || v7 + g_ulAdditionalProbeSize + 8 < v7
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_15;
  }
  v9 = v7 + 23;
  if ( v7 + 23 <= v7 + 8 )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
  v11 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
  p_pcbResult = (wchar_t *)&pcbResult;
  if ( &v27 == (__int64 *)-48LL || (pcbResult = 1801679955, (p_pcbResult = (wchar_t *)phKey) == 0) )
  {
LABEL_15:
    v12 = v7 + 8;
    if ( v7 + 8 >= v7 )
    {
      v13 = (wchar_t *)((__int64 (*)(void))g_pfnAllocate)();
      p_pcbResult = v13;
      if ( !v13 )
        goto LABEL_19;
      *(_DWORD *)v13 = 1885431112;
      p_pcbResult = v13 + 4;
    }
    if ( !p_pcbResult )
    {
LABEL_19:
      WppTraceIndent(v12, 2);
      v14 = 8;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_54;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 122;
LABEL_23:
        WPP_SF_s(v15[2], v16, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_51;
      }
      goto LABEL_51;
    }
  }
  do
    ++v5;
  while ( *(_WORD *)(*a1 + 2 * v5) );
  if ( StringCchPrintfW(p_pcbResult, v5 + 6, L"\\\\.\\%s\\") < 0 )
  {
    v14 = 0;
    Property = 8;
    goto LABEL_51;
  }
  v14 = I_SetupNCryptStorageProvider(a1);
  if ( v14 )
  {
    WppTraceIndent(v17, 2);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v19 = 123;
    dwFlags[0] = v14;
    goto LABEL_32;
  }
  Property = NCryptOpenKey(a1[17], phKey, p_pcbResult, 0, 0x40u);
  if ( Property )
    goto LABEL_51;
  Property = NCryptGetProperty(phKey[0], L"Unique Name", 0, 0, &pcbResult, 0x40u);
  if ( Property )
  {
    WppTraceIndent(v20, 2);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v19 = 124;
    dwFlags[0] = Property;
LABEL_32:
    WPP_SF_sd(v18[2], v19, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, dwFlags[0]);
    goto LABEL_51;
  }
  v22 = (BYTE *)HeapAlloc(hHeap, 8u, pcbResult);
  if ( v22 )
  {
    Property = NCryptGetProperty(phKey[0], L"Unique Name", v22, pcbResult, &pcbResult, 0x40u);
    if ( Property )
    {
      WppTraceIndent(v23, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          Property);
      }
      HeapFree(hHeap, 0, v22);
    }
    else
    {
      *a2 = v22;
    }
    goto LABEL_51;
  }
  WppTraceIndent(v21, 2);
  v14 = 8;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 125;
    goto LABEL_23;
  }
LABEL_51:
  if ( p_pcbResult && *((_DWORD *)p_pcbResult - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_54:
  v24 = phKey[0];
  if ( phKey[0] )
    NCryptFreeObject(phKey[0]);
  WppTraceIndent(v24, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v25 = Property;
    if ( v14 )
      v25 = v14;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      127,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v25);
  }
  if ( v14 )
    return v14;
  return Property;
}

```

## disassembly

```asm
0x180014854  push    rbp
0x180014856  push    rbx
0x180014857  push    rsi
0x180014858  push    rdi
0x180014859  push    r12
0x18001485b  push    r13
0x18001485d  push    r14
0x18001485f  push    r15
0x180014861  sub     rsp, 58h
0x180014865  lea     rbp, [rsp+30h]
0x18001486a  mov     rax, cs:__security_cookie
0x180014871  xor     rax, rbp
0x180014874  mov     [rbp+60h+var_48], rax
0x180014878  xor     r13d, r13d
0x18001487b  mov     r12, rdx
0x18001487e  xor     edx, edx
0x180014880  mov     [rbp+60h+pcbResult], r13d
0x180014884  mov     esi, r13d
0x180014887  mov     [rbp+60h+phKey], r13
0x18001488b  mov     r15, rcx
0x18001488e  call    WppTraceIndent
0x180014893  mov     rcx, cs:WPP_GLOBAL_Control
0x18001489a  lea     rax, WPP_GLOBAL_Control
0x1800148a1  cmp     rcx, rax
0x1800148a4  jz      short loc_1800148CD
0x1800148a6  test    byte ptr [rcx+1Ch], 2
0x1800148aa  jz      short loc_1800148CD
0x1800148ac  cmp     byte ptr [rcx+19h], 5
0x1800148b0  jb      short loc_1800148CD
0x1800148b2  mov     r9, cs:WPP_pszIndent
0x1800148b9  lea     edx, [r13+79h]
0x1800148bd  mov     rcx, [rcx+10h]
0x1800148c1  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800148c8  call    WPP_SF_s
0x1800148cd  mov     rax, [r15]
0x1800148d0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800148d4  mov     rdi, r14
0x1800148d7  inc     rdi
0x1800148da  cmp     [rax+rdi*2], r13w
0x1800148df  jnz     short loc_1800148D7
0x1800148e1  lea     rdi, ds:0Ch[rdi*2]
0x1800148e9  mov     rbx, r13
0x1800148ec  test    rdi, rdi
0x1800148ef  jz      short loc_180014956
0x1800148f1  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800148f8  ja      short loc_180014956
0x1800148fa  mov     rcx, cs:g_ulAdditionalProbeSize
0x180014901  add     rcx, 8
0x180014905  add     rcx, rdi
0x180014908  cmp     rcx, rdi
0x18001490b  jb      short loc_180014956
0x18001490d  call    VerifyStackAvailable
0x180014912  test    eax, eax
0x180014914  jz      short loc_180014956
0x180014916  lea     rax, [rdi+8]
0x18001491a  lea     rcx, [rax+0Fh]
0x18001491e  cmp     rcx, rax
0x180014921  ja      short loc_18001492D
0x180014923  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001492d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180014931  mov     rax, rcx
0x180014934  call    _alloca_probe
0x180014939  sub     rsp, rcx
0x18001493c  lea     rbx, [rsp+90h+pcbResult]
0x180014941  test    rbx, rbx
0x180014944  jz      short loc_180014956
0x180014946  mov     dword ptr [rbx], 6B637453h
0x18001494c  add     rbx, 8
0x180014950  jnz     loc_1800149DB
0x180014956  lea     rcx, [rdi+8]
0x18001495a  cmp     rcx, rdi
0x18001495d  jb      short loc_18001497D
0x18001495f  mov     rax, cs:g_pfnAllocate
0x180014966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001496b  mov     rbx, rax
0x18001496e  test    rax, rax
0x180014971  jz      short loc_180014982
0x180014973  mov     dword ptr [rax], 70616548h
0x180014979  add     rbx, 8
0x18001497d  test    rbx, rbx
0x180014980  jnz     short loc_1800149DB
0x180014982  mov     edx, 2
0x180014987  call    WppTraceIndent
0x18001498c  mov     edi, 8
0x180014991  mov     rcx, cs:WPP_GLOBAL_Control
0x180014998  lea     r15, WPP_GLOBAL_Control
0x18001499f  cmp     rcx, r15
0x1800149a2  jz      loc_180014C1D
0x1800149a8  test    byte ptr [rcx+1Ch], 1
0x1800149ac  jz      loc_180014C00
0x1800149b2  cmp     byte ptr [rcx+19h], 2
0x1800149b6  jb      loc_180014C00
0x1800149bc  lea     edx, [rdi+72h]
0x1800149bf  mov     r9, cs:WPP_pszIndent
0x1800149c6  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800149cd  mov     rcx, [rcx+10h]
0x1800149d1  call    WPP_SF_s
0x1800149d6  jmp     loc_180014C00
0x1800149db  mov     r9, [r15]
0x1800149de  inc     r14
0x1800149e1  cmp     [r9+r14*2], r13w
0x1800149e6  jnz     short loc_1800149DE
0x1800149e8  lea     rdx, [r14+6]; cchDest
0x1800149ec  mov     rcx, rbx; pszDest
0x1800149ef  lea     r8, aS; "\\\\.\\%s\\"
0x1800149f6  call    StringCchPrintfW
0x1800149fb  test    eax, eax
0x1800149fd  jns     short loc_180014A0C
0x1800149ff  mov     edi, r13d
0x180014a02  mov     esi, 8
0x180014a07  jmp     loc_180014BF9
0x180014a0c  mov     rcx, r15
0x180014a0f  call    I_SetupNCryptStorageProvider
0x180014a14  mov     edi, eax
0x180014a16  test    eax, eax
0x180014a18  jz      short loc_180014A74
0x180014a1a  mov     edx, 2
0x180014a1f  call    WppTraceIndent
0x180014a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a2b  lea     r15, WPP_GLOBAL_Control
0x180014a32  cmp     rcx, r15
0x180014a35  jz      loc_180014C00
0x180014a3b  test    byte ptr [rcx+1Ch], 1
0x180014a3f  jz      loc_180014C00
0x180014a45  cmp     byte ptr [rcx+19h], 2
0x180014a49  jb      loc_180014C00
0x180014a4f  mov     edx, 7Bh ; '{'
0x180014a54  mov     [rsp+90h+dwFlags], edi
0x180014a58  mov     r9, cs:WPP_pszIndent
0x180014a5f  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180014a66  mov     rcx, [rcx+10h]
0x180014a6a  call    WPP_SF_sd
0x180014a6f  jmp     loc_180014C00
0x180014a74  mov     rcx, [r15+88h]; hProvider
0x180014a7b  lea     rdx, [rbp+60h+phKey]; phKey
0x180014a7f  mov     r14d, 40h ; '@'
0x180014a85  xor     r9d, r9d; dwLegacyKeySpec
0x180014a88  mov     r8, rbx; pszKeyName
0x180014a8b  mov     [rsp+90h+dwFlags], r14d; dwFlags
0x180014a90  call    cs:__imp_NCryptOpenKey
0x180014a96  mov     esi, eax
0x180014a98  test    eax, eax
0x180014a9a  jnz     loc_180014BF9
0x180014aa0  mov     rcx, [rbp+60h+phKey]; hObject
0x180014aa4  lea     rax, [rbp+60h+pcbResult]
0x180014aa8  mov     [rsp+90h+var_68], r14d; dwFlags
0x180014aad  lea     rdx, aUniqueName; "Unique Name"
0x180014ab4  xor     r9d, r9d; cbOutput
0x180014ab7  mov     qword ptr [rsp+90h+dwFlags], rax; pcbResult
0x180014abc  xor     r8d, r8d; pbOutput
0x180014abf  call    cs:__imp_NCryptGetProperty
0x180014ac5  mov     esi, eax
0x180014ac7  test    eax, eax
0x180014ac9  jz      short loc_180014B0C
0x180014acb  lea     edx, [r14-3Eh]
0x180014acf  call    WppTraceIndent
0x180014ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180014adb  lea     r15, WPP_GLOBAL_Control
0x180014ae2  cmp     rcx, r15
0x180014ae5  jz      loc_180014C00
0x180014aeb  test    byte ptr [rcx+1Ch], 1
0x180014aef  jz      loc_180014C00
0x180014af5  cmp     byte ptr [rcx+19h], 2
0x180014af9  jb      loc_180014C00
0x180014aff  lea     edx, [r14+3Ch]
0x180014b03  mov     [rsp+90h+dwFlags], esi
0x180014b07  jmp     loc_180014A58
0x180014b0c  mov     r8d, [rbp+60h+pcbResult]; dwBytes
0x180014b10  mov     edx, 8; dwFlags
0x180014b15  mov     rcx, cs:hHeap; hHeap
0x180014b1c  call    cs:__imp_HeapAlloc
0x180014b22  mov     r14, rax
0x180014b25  test    rax, rax
0x180014b28  jnz     short loc_180014B69
0x180014b2a  lea     edx, [rax+2]
0x180014b2d  call    WppTraceIndent
0x180014b32  lea     edi, [r14+8]
0x180014b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b3d  lea     r15, WPP_GLOBAL_Control
0x180014b44  cmp     rcx, r15
0x180014b47  jz      loc_180014C00
0x180014b4d  test    byte ptr [rcx+1Ch], 1
0x180014b51  jz      loc_180014C00
0x180014b57  cmp     byte ptr [rcx+19h], 2
0x180014b5b  jb      loc_180014C00
0x180014b61  lea     edx, [rdi+75h]
0x180014b64  jmp     loc_1800149BF
0x180014b69  mov     r9d, [rbp+60h+pcbResult]; cbOutput
0x180014b6d  lea     rax, [rbp+60h+pcbResult]
0x180014b71  mov     rcx, [rbp+60h+phKey]; hObject
0x180014b75  lea     rdx, aUniqueName; "Unique Name"
0x180014b7c  mov     [rsp+90h+var_68], 40h ; '@'; dwFlags
0x180014b84  mov     r8, r14; pbOutput
0x180014b87  mov     qword ptr [rsp+90h+dwFlags], rax; pcbResult
0x180014b8c  call    cs:__imp_NCryptGetProperty
0x180014b92  mov     esi, eax
0x180014b94  test    eax, eax
0x180014b96  jz      short loc_180014BF5
0x180014b98  mov     edx, 2
0x180014b9d  call    WppTraceIndent
0x180014ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ba9  lea     r15, WPP_GLOBAL_Control
0x180014bb0  cmp     rcx, r15
0x180014bb3  jz      short loc_180014BE1
0x180014bb5  test    byte ptr [rcx+1Ch], 1
0x180014bb9  jz      short loc_180014BE1
0x180014bbb  cmp     byte ptr [rcx+19h], 2
0x180014bbf  jb      short loc_180014BE1
0x180014bc1  mov     r9, cs:WPP_pszIndent
0x180014bc8  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180014bcf  mov     rcx, [rcx+10h]
0x180014bd3  mov     edx, 7Eh ; '~'
0x180014bd8  mov     [rsp+90h+dwFlags], esi
0x180014bdc  call    WPP_SF_sd
0x180014be1  mov     rcx, cs:hHeap; hHeap
0x180014be8  mov     r8, r14; lpMem
0x180014beb  xor     edx, edx; dwFlags
0x180014bed  call    cs:__imp_HeapFree
0x180014bf3  jmp     short loc_180014C00
0x180014bf5  mov     [r12], r14
0x180014bf9  lea     r15, WPP_GLOBAL_Control
0x180014c00  test    rbx, rbx
0x180014c03  jz      short loc_180014C1D
0x180014c05  lea     rcx, [rbx-8]
0x180014c09  cmp     dword ptr [rcx], 70616548h
0x180014c0f  jnz     short loc_180014C1D
0x180014c11  mov     rax, cs:g_pfnFree
0x180014c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c1d  mov     rcx, [rbp+60h+phKey]; hObject
0x180014c21  test    rcx, rcx
0x180014c24  jz      short loc_180014C2C
0x180014c26  call    cs:__imp_NCryptFreeObject
0x180014c2c  mov     edx, 1
0x180014c31  call    WppTraceIndent
0x180014c36  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c3d  cmp     rcx, r15
0x180014c40  jz      short loc_180014C75
0x180014c42  test    byte ptr [rcx+1Ch], 2
0x180014c46  jz      short loc_180014C75
0x180014c48  cmp     byte ptr [rcx+19h], 5
0x180014c4c  jb      short loc_180014C75
0x180014c4e  mov     r9, cs:WPP_pszIndent
0x180014c55  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180014c5c  mov     rcx, [rcx+10h]
0x180014c60  test    edi, edi
0x180014c62  mov     eax, esi
0x180014c64  mov     edx, 7Fh
0x180014c69  cmovnz  eax, edi
0x180014c6c  mov     [rsp+90h+dwFlags], eax
0x180014c70  call    WPP_SF_sd
0x180014c75  test    edi, edi
0x180014c77  cmovnz  esi, edi
0x180014c7a  mov     eax, esi
0x180014c7c  mov     rcx, [rbp+60h+var_48]
0x180014c80  xor     rcx, rbp; StackCookie
0x180014c83  call    __security_check_cookie
0x180014c88  lea     rsp, [rbp+28h]
0x180014c8c  pop     r15
0x180014c8e  pop     r14
0x180014c90  pop     r13
0x180014c92  pop     r12
0x180014c94  pop     rdi
0x180014c95  pop     rsi
0x180014c96  pop     rbx
0x180014c97  pop     rbp
0x180014c98  retn
```
