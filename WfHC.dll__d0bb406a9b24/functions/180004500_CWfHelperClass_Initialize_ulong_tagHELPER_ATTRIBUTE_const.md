# CWfHelperClass::Initialize(ulong,tagHELPER_ATTRIBUTE * const)

- ea: `0x180004500`
- end: `0x180004836`
- name: `?Initialize@CWfHelperClass@@UEAAJKQEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(LPVOID *this, unsigned int, struct tagHELPER_ATTRIBUTE *const)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003b60`
- `0x180004500`
- `0x180006830`
- `0x180006ebc`
- `0x18000c168`
- `0x18000c57e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004542`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000463a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000463a`

## string_xrefs

- `0x1800047e8`: `serviceid`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::Initialize(LPVOID *this, unsigned int a2, struct tagHELPER_ATTRIBUTE *const a3)
{
  LPVOID *v5; // r12
  LPVOID *v6; // r13
  LPVOID *v7; // r15
  unsigned int v8; // ebp
  int v9; // eax
  unsigned int v10; // esi
  __int64 v11; // r9
  const struct tagHelperAttributeInfo near *const *v12; // rdi
  int v13; // r12d
  int v14; // r14d
  _DWORD *v15; // r15
  unsigned int v16; // esi
  int v17; // ebx
  __int64 v18; // rax
  bool v19; // zf
  _QWORD *v20; // r14
  unsigned int v21; // edi
  unsigned int v22; // ebx
  const wchar_t *v23; // rcx
  LPVOID v24; // r15
  unsigned int v25; // r14d
  unsigned int v26; // ebx
  __int64 v27; // rdi
  _QWORD *v28; // r14
  unsigned int v29; // edi
  const wchar_t *v30; // rcx
  LPVOID *v34; // [rsp+88h] [rbp+20h]

  v5 = this;
  CoCreateInstance(&CLSID_NDFEtw, 0, 1u, &IID_INDFEtw, this + 15);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)v5 + 4, 1, 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v6 = v5 + 3;
  v7 = v5 + 4;
  v34 = v5 + 4;
  if ( !a2 && !*(_DWORD *)v6 && !*v7 )
  {
    v8 = 0;
    goto LABEL_27;
  }
  v34 = v5 + 4;
  v9 = _attributes_array_t::Copy((_attributes_array_t *)(v5 + 3), a2, a3);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = (unsigned int)v9;
LABEL_22:
    CWfHelperClass::WriteToNdfEtw(v5, 2, L"Failed to Initialize. Error Code [0x%x]", v11);
    return v10;
  }
  v8 = 0;
  v12 = &CNetDiagHelperImpl::m_attrInfos;
  v13 = 0;
  if ( !a2 )
    goto LABEL_26;
  while ( v12 )
  {
    v14 = *((_DWORD *)v12 + 2);
    if ( !v14 )
      break;
    v15 = v6[1];
    if ( !v15 || (v16 = *(_DWORD *)v6, v17 = 0, !*(_DWORD *)v6) )
    {
LABEL_21:
      _attributes_array_t::FreeElements((_attributes_array_t *)v6);
      CoTaskMemFree(v6[1]);
      v6[1] = 0;
      *(_DWORD *)v6 = 0;
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v5 = this;
      v10 = -2147024809;
      v11 = 2147942487LL;
      goto LABEL_22;
    }
    while ( 1 )
    {
      if ( v15[36 * v17 + 2] != v14 )
        goto LABEL_20;
      v18 = *(_QWORD *)&v15[36 * v17];
      if ( !*v12 )
        break;
      if ( v18 )
      {
        v19 = wcsncmp_0(*(const wchar_t **)&v15[36 * v17], *(const wchar_t **)v12, 0xFFu) == 0;
        goto LABEL_19;
      }
LABEL_20:
      if ( ++v17 >= v16 )
        goto LABEL_21;
    }
    v19 = v18 == 0;
LABEL_19:
    if ( !v19 )
      goto LABEL_20;
    if ( ++v13 < a2 )
    {
      v12 += 2;
      continue;
    }
    break;
  }
  v7 = v34;
LABEL_26:
  v5 = this;
LABEL_27:
  v20 = *v7;
  v10 = 0;
  if ( *v7 && (v21 = *(_DWORD *)v6, v22 = 0, *(_DWORD *)v6) )
  {
    while ( 1 )
    {
      v23 = (const wchar_t *)v20[18 * v22];
      if ( v23 )
      {
        if ( !wcsncmp_0(v23, L"filterid", 0xFFu) )
          break;
      }
      if ( ++v22 >= v21 )
        goto LABEL_32;
    }
  }
  else
  {
LABEL_32:
    *((_DWORD *)v5 + 39) = 1;
  }
  if ( *((_DWORD *)v5 + 39) )
    goto LABEL_47;
  v24 = *v7;
  if ( !v24 )
    goto LABEL_39;
  v25 = *(_DWORD *)v6;
  v26 = 0;
  if ( !*(_DWORD *)v6 )
    goto LABEL_39;
  while ( 1 )
  {
    v27 = (__int64)v24 + 144 * v26;
    if ( *(_QWORD *)v27 )
    {
      if ( !wcsncmp_0(*(const wchar_t **)v27, L"providerguid", 0xFFu) )
        break;
    }
    if ( ++v26 >= v25 )
      goto LABEL_39;
  }
  if ( *(_DWORD *)(v27 + 8) == 11 )
  {
    if ( *(_DWORD *)(v27 + 16) != -557050166
      || *(_DWORD *)(v27 + 20) != 1128677171
      || *(_DWORD *)(v27 + 24) != -1265688898
      || *(_DWORD *)(v27 + 28) != 1648168878 )
    {
      v10 = -2147024809;
      CWfHelperClass::WriteToNdfEtw(v5, 2, L"Invalid ProviderID Parameter");
      return v10;
    }
    v7 = v34;
LABEL_47:
    v28 = *v7;
    if ( *v7 )
    {
      v29 = *(_DWORD *)v6;
      if ( *(_DWORD *)v6 )
      {
        while ( 1 )
        {
          v30 = (const wchar_t *)v28[18 * v8];
          if ( v30 )
          {
            if ( !wcsncmp_0(v30, L"serviceid", 0xFFu) )
              break;
          }
          if ( ++v8 >= v29 )
            return v10;
        }
        if ( LODWORD(v28[18 * v8 + 1]) == 10 && v28[18 * v8 + 2] )
          *((_DWORD *)v5 + 45) = 1;
      }
    }
  }
  else
  {
LABEL_39:
    v10 = -2147024809;
    CWfHelperClass::WriteToNdfEtw(v5, 2, L"ProviderID Not passed");
  }
  return v10;
}

```

## disassembly

```asm
0x180004500  mov     [rsp+arg_8], edx
0x180004504  mov     [rsp+arg_0], rcx
0x180004509  push    rbx
0x18000450a  push    rsi
0x18000450b  push    rdi
0x18000450c  push    r12
0x18000450e  push    r13
0x180004510  push    r14
0x180004512  push    r15
0x180004514  sub     rsp, 30h
0x180004518  lea     rax, [rcx+78h]
0x18000451c  mov     rbx, r8
0x18000451f  mov     r14d, edx
0x180004522  mov     [rsp+68h+ppv], rax; ppv
0x180004527  mov     r12, rcx
0x18000452a  lea     r9, IID_INDFEtw; riid
0x180004531  mov     edi, 1
0x180004536  lea     rcx, CLSID_NDFEtw; rclsid
0x18000453d  mov     r8d, edi; dwClsContext
0x180004540  xor     edx, edx; pUnkOuter
0x180004542  call    cs:__imp_CoCreateInstance
0x180004548  xor     eax, eax
0x18000454a  lock cmpxchg [r12+10h], edi
0x180004551  jz      short loc_180004558
0x180004553  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004558  mov     [rsp+68h+arg_10], rbp
0x180004560  lea     r13, [r12+18h]
0x180004565  lea     r15, [r13+8]
0x180004569  mov     [rsp+68h+arg_18], r15
0x180004571  test    r14d, r14d
0x180004574  jnz     short loc_180004589
0x180004576  cmp     [r13+0], r14d
0x18000457a  jnz     short loc_180004589
0x18000457c  cmp     qword ptr [r15], 0
0x180004580  jnz     short loc_180004589
0x180004582  xor     ebp, ebp
0x180004584  jmp     loc_180004693
0x180004589  mov     r8, rbx; struct tagHELPER_ATTRIBUTE *
0x18000458c  mov     [rsp+68h+arg_18], r15
0x180004594  mov     edx, r14d; unsigned int
0x180004597  mov     rcx, r13; this
0x18000459a  call    ?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z; _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)
0x18000459f  mov     esi, eax
0x1800045a1  test    eax, eax
0x1800045a3  jns     short loc_1800045AD
0x1800045a5  mov     r9d, eax
0x1800045a8  jmp     loc_18000465A
0x1800045ad  xor     ebp, ebp
0x1800045af  lea     rdi, ?m_attrInfos@CNetDiagHelperImpl@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CNetDiagHelperImpl::m_attrInfos
0x1800045b6  mov     r12d, ebp
0x1800045b9  test    r14d, r14d
0x1800045bc  jz      loc_18000468E
0x1800045c2  test    rdi, rdi
0x1800045c5  jz      loc_180004686
0x1800045cb  mov     r14d, [rdi+8]
0x1800045cf  test    r14d, r14d
0x1800045d2  jz      loc_180004686
0x1800045d8  mov     r15, [r13+8]
0x1800045dc  test    r15, r15
0x1800045df  jz      short loc_18000462E
0x1800045e1  mov     esi, [r13+0]
0x1800045e5  mov     ebx, ebp
0x1800045e7  test    esi, esi
0x1800045e9  jz      short loc_18000462E
0x1800045eb  nop     dword ptr [rax+rax+00h]
0x1800045f0  mov     eax, ebx
0x1800045f2  lea     rcx, [rax+rax*8]
0x1800045f6  add     rcx, rcx
0x1800045f9  cmp     [r15+rcx*8+8], r14d
0x1800045fe  jnz     short loc_180004628
0x180004600  mov     rdx, [rdi]; String2
0x180004603  mov     rax, [r15+rcx*8]
0x180004607  test    rdx, rdx
0x18000460a  jz      short loc_180004623
0x18000460c  test    rax, rax
0x18000460f  jz      short loc_180004628
0x180004611  mov     r8d, 0FFh; MaxCount
0x180004617  mov     rcx, rax; String1
0x18000461a  call    wcsncmp_0
0x18000461f  test    eax, eax
0x180004621  jmp     short loc_180004626
0x180004623  test    rax, rax
0x180004626  jz      short loc_180004673
0x180004628  inc     ebx
0x18000462a  cmp     ebx, esi
0x18000462c  jb      short loc_1800045F0
0x18000462e  mov     rcx, r13; this
0x180004631  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180004636  mov     rcx, [r13+8]; pv
0x18000463a  call    cs:__imp_CoTaskMemFree
0x180004640  mov     [r13+8], rbp
0x180004644  mov     [r13+0], ebp
0x180004648  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000464d  mov     r12, [rsp+68h+arg_0]
0x180004652  mov     esi, 80070057h
0x180004657  mov     r9d, esi
0x18000465a  lea     r8, aFailedToInitia; "Failed to Initialize. Error Code [0x%x]"
0x180004661  mov     edx, 2
0x180004666  mov     rcx, r12
0x180004669  call    ?WriteToNdfEtw@CWfHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ; CWfHelperClass::WriteToNdfEtw(tagNDFEventChannel,ushort const *,...)
0x18000466e  jmp     loc_18000481C
0x180004673  inc     r12d
0x180004676  cmp     r12d, [rsp+68h+arg_8]
0x18000467b  jnb     short loc_180004686
0x18000467d  add     rdi, 10h
0x180004681  jmp     loc_1800045C2
0x180004686  mov     r15, [rsp+68h+arg_18]
0x18000468e  mov     r12, [rsp+68h+arg_0]
0x180004693  mov     r14, [r15]
0x180004696  mov     esi, ebp
0x180004698  test    r14, r14
0x18000469b  jz      short loc_1800046DE
0x18000469d  mov     edi, [r13+0]
0x1800046a1  mov     ebx, ebp
0x1800046a3  test    edi, edi
0x1800046a5  jz      short loc_1800046DE
0x1800046a7  nop     word ptr [rax+rax+00000000h]
0x1800046b0  mov     eax, ebx
0x1800046b2  lea     rcx, [rax+rax*8]
0x1800046b6  add     rcx, rcx
0x1800046b9  mov     rcx, [r14+rcx*8]; String1
0x1800046bd  test    rcx, rcx
0x1800046c0  jz      short loc_1800046D8
0x1800046c2  mov     r8d, 0FFh; MaxCount
0x1800046c8  lea     rdx, aFilterid; "filterid"
0x1800046cf  call    wcsncmp_0
0x1800046d4  test    eax, eax
0x1800046d6  jz      short loc_1800046EA
0x1800046d8  inc     ebx
0x1800046da  cmp     ebx, edi
0x1800046dc  jb      short loc_1800046B0
0x1800046de  mov     dword ptr [r12+9Ch], 1
0x1800046ea  cmp     dword ptr [r12+9Ch], 0
0x1800046f3  jnz     loc_1800047B3
0x1800046f9  mov     r15, [r15]
0x1800046fc  test    r15, r15
0x1800046ff  jz      short loc_180004742
0x180004701  mov     r14d, [r13+0]
0x180004705  mov     ebx, ebp
0x180004707  test    r14d, r14d
0x18000470a  jz      short loc_180004742
0x18000470c  nop     dword ptr [rax+00h]
0x180004710  mov     eax, ebx
0x180004712  lea     rdi, [rax+rax*8]
0x180004716  shl     rdi, 4
0x18000471a  add     rdi, r15
0x18000471d  mov     rcx, [rdi]; String1
0x180004720  test    rcx, rcx
0x180004723  jz      short loc_18000473B
0x180004725  mov     r8d, 0FFh; MaxCount
0x18000472b  lea     rdx, aProviderguid; "providerguid"
0x180004732  call    wcsncmp_0
0x180004737  test    eax, eax
0x180004739  jz      short loc_180004760
0x18000473b  inc     ebx
0x18000473d  cmp     ebx, r14d
0x180004740  jb      short loc_180004710
0x180004742  lea     r8, aProvideridNotP; "ProviderID Not passed"
0x180004749  mov     edx, 2
0x18000474e  mov     rcx, r12
0x180004751  mov     esi, 80070057h
0x180004756  call    ?WriteToNdfEtw@CWfHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ; CWfHelperClass::WriteToNdfEtw(tagNDFEventChannel,ushort const *,...)
0x18000475b  jmp     loc_18000481C
0x180004760  cmp     dword ptr [rdi+8], 0Bh
0x180004764  jnz     short loc_180004742
0x180004766  cmp     dword ptr [rdi+10h], 0DECC16CAh
0x18000476d  jnz     short loc_180004790
0x18000476f  mov     eax, cs:dword_180011824
0x180004775  cmp     eax, [rdi+14h]
0x180004778  jnz     short loc_180004790
0x18000477a  mov     eax, dword ptr cs:qword_180011828
0x180004780  cmp     eax, [rdi+18h]
0x180004783  jnz     short loc_180004790
0x180004785  mov     eax, dword ptr cs:qword_180011828+4
0x18000478b  cmp     eax, [rdi+1Ch]
0x18000478e  jz      short loc_1800047AB
0x180004790  lea     r8, aInvalidProvide; "Invalid ProviderID Parameter"
0x180004797  mov     edx, 2
0x18000479c  mov     rcx, r12
0x18000479f  mov     esi, 80070057h
0x1800047a4  call    ?WriteToNdfEtw@CWfHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ; CWfHelperClass::WriteToNdfEtw(tagNDFEventChannel,ushort const *,...)
0x1800047a9  jmp     short loc_18000481C
0x1800047ab  mov     r15, [rsp+68h+arg_18]
0x1800047b3  mov     r14, [r15]
0x1800047b6  test    r14, r14
0x1800047b9  jz      short loc_18000481C
0x1800047bb  mov     edi, [r13+0]
0x1800047bf  test    edi, edi
0x1800047c1  jz      short loc_18000481C
0x1800047c3  nop     dword ptr [rax+00h]
0x1800047c7  nop     word ptr [rax+rax+00000000h]
0x1800047d0  mov     eax, ebp
0x1800047d2  lea     rbx, [rax+rax*8]
0x1800047d6  add     rbx, rbx
0x1800047d9  mov     rcx, [r14+rbx*8]; String1
0x1800047dd  test    rcx, rcx
0x1800047e0  jz      short loc_1800047F8
0x1800047e2  mov     r8d, 0FFh; MaxCount
0x1800047e8  lea     rdx, aServiceid; "serviceid"
0x1800047ef  call    wcsncmp_0
0x1800047f4  test    eax, eax
0x1800047f6  jz      short loc_180004800
0x1800047f8  inc     ebp
0x1800047fa  cmp     ebp, edi
0x1800047fc  jb      short loc_1800047D0
0x1800047fe  jmp     short loc_18000481C
0x180004800  cmp     dword ptr [r14+rbx*8+8], 0Ah
0x180004806  jnz     short loc_18000481C
0x180004808  cmp     qword ptr [r14+rbx*8+10h], 0
0x18000480e  jz      short loc_18000481C
0x180004810  mov     dword ptr [r12+0B4h], 1
0x18000481c  mov     rbp, [rsp+68h+arg_10]
0x180004824  mov     eax, esi
0x180004826  add     rsp, 30h
0x18000482a  pop     r15
0x18000482c  pop     r14
0x18000482e  pop     r13
0x180004830  pop     r12
0x180004832  pop     rdi
0x180004833  pop     rsi
0x180004834  pop     rbx
0x180004835  retn
```
