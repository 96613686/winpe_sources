# RaCreateWellKnownSid

- ea: `0x1800044a0`
- end: `0x180004a48`
- name: `RaCreateWellKnownSid`
- size: `1448`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d590`

## callees

- `0x1800044a0`
- `0x180004cb0`
- `0x18000b774`
- `0x18000b800`
- `0x18000d8a4`
- `0x18000d8f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800044e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800045b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800044e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800045b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004551`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004599`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004683`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004551`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004599`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004683`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000456b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000469d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000456b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000469d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180004532`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800045f8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180004532`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800045f8`

## string_xrefs

- `0x18000464e`: `RaCreateWellKnownSid`
- `0x1800046c5`: `RaCreateWellKnownSid`
- `0x18000470f`: `RaCreateWellKnownSid`
- `0x180004763`: `RaCreateWellKnownSid`
- `0x1800047ca`: `RaCreateWellKnownSid`
- `0x1800047fa`: `RaCreateWellKnownSid`
- `0x180004884`: `RaCreateWellKnownSid`
- `0x1800048aa`: `RaCreateWellKnownSid`
- `0x1800048ee`: `RaCreateWellKnownSid`
- `0x180004936`: `RaCreateWellKnownSid`
- `0x180004966`: `RaCreateWellKnownSid`
- `0x180004a26`: `RaCreateWellKnownSid`

## pseudocode

```c
__int64 __fastcall RaCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, _QWORD *a2)
{
  DWORD v4; // esi
  HANDLE ProcessHeap; // rbx
  LPVOID v6; // rax
  int v7; // r8d
  void *v8; // rdi
  PVOID *v9; // rcx
  unsigned int v10; // ebx
  DWORD v11; // eax
  __int64 v12; // r8
  HANDLE v13; // rbx
  int v14; // edx
  int v15; // r8d
  SIZE_T v16; // r14
  DWORD v17; // esi
  HANDLE v18; // rbx
  LPVOID v19; // rax
  int v20; // r8d
  DWORD v22; // eax
  int v23; // r8d
  HANDLE v24; // rsi
  int v25; // edx
  int v26; // r8d
  DWORD v27; // eax
  int v28; // r8d
  DWORD LastError; // eax
  int v30; // r8d
  __int64 v31; // rdx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  DWORD v34; // eax
  int v35; // r8d
  DWORD v36; // eax
  int v37; // r8d
  DWORD v38; // eax
  int v39; // r8d
  DWORD cbSid; // [rsp+80h] [rbp+18h] BYREF

  cbSid = 0;
  v4 = 0;
  ProcessHeap = GetProcessHeap();
  if ( !ProcessHeap )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v30, (unsigned int)"RaCreateWellKnownSid", 118, LastError);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      v8 = 0;
      v10 = v4;
      goto LABEL_43;
    }
  }
  v6 = HeapAlloc(ProcessHeap, 8u, 0x44u);
  v8 = v6;
  if ( !v6 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v7, (unsigned int)"RaCreateWellKnownSid", 118, 68);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = 14;
LABEL_43:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
    {
      v31 = 19;
LABEL_69:
      WPP_SF_dD(v9[2], v31);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_sdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v7, (unsigned int)"RaCreateWellKnownSid", 118, (char)v6, 68);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = v4;
  if ( v4 )
    goto LABEL_43;
  if ( CreateWellKnownSid(WellKnownSidType, 0, v8, &cbSid) )
  {
LABEL_21:
    *a2 = v8;
    return v10;
  }
  v11 = GetLastError();
  v10 = v11;
  if ( v11 != 122 && v11 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v33 = 20;
LABEL_74:
      WPP_SF_DD(v32[2], v33, v12, (unsigned int)WellKnownSidType, v11);
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  v13 = GetProcessHeap();
  if ( v13 || (v34 = GetLastError()) == 0 )
  {
    if ( HeapFree(v13, 0, v8) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (unsigned int)"RaCreateWellKnownSid", 129, (char)v8);
    }
    else
    {
      v22 = GetLastError();
      if ( v22 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sdqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          v23,
          (unsigned int)"RaCreateWellKnownSid",
          129,
          (char)v8,
          v22);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v35, (unsigned int)"RaCreateWellKnownSid", 129, v34);
  }
  v16 = cbSid;
  v17 = 0;
  v18 = GetProcessHeap();
  if ( !v18 )
  {
    v36 = GetLastError();
    v17 = v36;
    if ( v36 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v37, (unsigned int)"RaCreateWellKnownSid", 131, v36);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      v8 = 0;
      v10 = v17;
      goto LABEL_27;
    }
  }
  v19 = HeapAlloc(v18, 8u, v16);
  v8 = v19;
  if ( !v19 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v20, (unsigned int)"RaCreateWellKnownSid", 131, v16);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = 14;
LABEL_27:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
    {
      v31 = 21;
      goto LABEL_69;
    }
LABEL_28:
    if ( !v8 )
      return v10;
    goto LABEL_29;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_sdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v20, (unsigned int)"RaCreateWellKnownSid", 131, (char)v19, v16);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = v17;
  if ( v17 )
    goto LABEL_27;
  if ( CreateWellKnownSid(WellKnownSidType, 0, v8, &cbSid) )
    goto LABEL_21;
  v11 = GetLastError();
  v10 = v11;
  if ( !v11 )
    goto LABEL_21;
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v33 = 22;
    goto LABEL_74;
  }
LABEL_29:
  v24 = GetProcessHeap();
  if ( v24 || (v38 = GetLastError()) == 0 )
  {
    if ( HeapFree(v24, 0, v8) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, (unsigned int)"RaCreateWellKnownSid", 148, (char)v8);
    }
    else
    {
      v27 = GetLastError();
      if ( v27 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sdqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          v28,
          (unsigned int)"RaCreateWellKnownSid",
          148,
          (char)v8,
          v27);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v39, (unsigned int)"RaCreateWellKnownSid", 148, v38);
  }
  return v10;
}

```

## disassembly

```asm
0x1800044a0  mov     [rsp+arg_0], rbx
0x1800044a5  mov     [rsp+arg_8], rbp
0x1800044aa  push    rsi
0x1800044ab  push    rdi
0x1800044ac  push    r12
0x1800044ae  push    r14
0x1800044b0  push    r15
0x1800044b2  sub     rsp, 40h
0x1800044b6  mov     r15, rdx
0x1800044b9  mov     [rsp+68h+cbSid], 0
0x1800044c4  mov     r12d, ecx
0x1800044c7  xor     esi, esi
0x1800044c9  call    cs:__imp_GetProcessHeap
0x1800044cf  mov     rbx, rax
0x1800044d2  test    rax, rax
0x1800044d5  jz      loc_180004736
0x1800044db  mov     edx, 8; dwFlags
0x1800044e0  mov     r8d, 44h ; 'D'; dwBytes
0x1800044e6  mov     rcx, rbx; hHeap
0x1800044e9  call    cs:__imp_HeapAlloc
0x1800044ef  mov     rdi, rax
0x1800044f2  test    rax, rax
0x1800044f5  jz      loc_1800047A8
0x1800044fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004502  lea     rbp, WPP_GLOBAL_Control
0x180004509  cmp     rcx, rbp
0x18000450c  jz      short loc_180004518
0x18000450e  test    byte ptr [rcx+1Ch], 2
0x180004512  jnz     loc_1800047F6
0x180004518  mov     ebx, esi
0x18000451a  test    esi, esi
0x18000451c  jnz     loc_18000478B
0x180004522  lea     r9, [rsp+68h+cbSid]; cbSid
0x18000452a  mov     r8, rdi; pSid
0x18000452d  xor     edx, edx; DomainSid
0x18000452f  mov     ecx, r12d; WellKnownSidType
0x180004532  call    cs:__imp_CreateWellKnownSid
0x180004538  test    eax, eax
0x18000453a  jnz     loc_180004606
0x180004540  call    cs:__imp_GetLastError
0x180004546  mov     ebx, eax
0x180004548  cmp     eax, 7Ah ; 'z'
0x18000454b  jnz     loc_18000482C
0x180004551  call    cs:__imp_GetProcessHeap
0x180004557  mov     rbx, rax
0x18000455a  test    rax, rax
0x18000455d  jz      loc_180004858
0x180004563  mov     r8, rdi; lpMem
0x180004566  xor     edx, edx; dwFlags
0x180004568  mov     rcx, rbx; hHeap
0x18000456b  call    cs:__imp_HeapFree
0x180004571  test    eax, eax
0x180004573  jz      loc_180004622
0x180004579  mov     rcx, cs:WPP_GLOBAL_Control
0x180004580  cmp     rcx, rbp
0x180004583  jz      short loc_18000458F
0x180004585  test    byte ptr [rcx+1Ch], 2
0x180004589  jnz     loc_1800048A6
0x18000458f  mov     r14d, [rsp+68h+cbSid]
0x180004597  xor     esi, esi
0x180004599  call    cs:__imp_GetProcessHeap
0x18000459f  mov     rbx, rax
0x1800045a2  test    rax, rax
0x1800045a5  jz      loc_1800048C8
0x1800045ab  mov     r8, r14; dwBytes
0x1800045ae  mov     edx, 8; dwFlags
0x1800045b3  mov     rcx, rbx; hHeap
0x1800045b6  call    cs:__imp_HeapAlloc
0x1800045bc  mov     rdi, rax
0x1800045bf  test    rax, rax
0x1800045c2  jz      loc_18000491B
0x1800045c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045cf  cmp     rcx, rbp
0x1800045d2  jz      short loc_1800045DE
0x1800045d4  test    byte ptr [rcx+1Ch], 2
0x1800045d8  jnz     loc_180004962
0x1800045de  mov     ebx, esi
0x1800045e0  test    esi, esi
0x1800045e2  jnz     loc_180004675
0x1800045e8  lea     r9, [rsp+68h+cbSid]; cbSid
0x1800045f0  mov     r8, rdi; pSid
0x1800045f3  xor     edx, edx; DomainSid
0x1800045f5  mov     ecx, r12d; WellKnownSidType
0x1800045f8  call    cs:__imp_CreateWellKnownSid
0x1800045fe  test    eax, eax
0x180004600  jz      loc_1800049B6
0x180004606  mov     [r15], rdi
0x180004609  mov     rbp, [rsp+68h+arg_8]
0x18000460e  mov     eax, ebx
0x180004610  mov     rbx, [rsp+68h+arg_0]
0x180004615  add     rsp, 40h
0x180004619  pop     r15
0x18000461b  pop     r14
0x18000461d  pop     r12
0x18000461f  pop     rdi
0x180004620  pop     rsi
0x180004621  retn
0x180004622  call    cs:__imp_GetLastError
0x180004628  test    eax, eax
0x18000462a  jz      loc_18000458F
0x180004630  mov     rcx, cs:WPP_GLOBAL_Control
0x180004637  cmp     rcx, rbp
0x18000463a  jz      loc_18000458F
0x180004640  test    byte ptr [rcx+1Ch], 4
0x180004644  jz      loc_18000458F
0x18000464a  mov     rcx, [rcx+10h]
0x18000464e  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x180004655  mov     [rsp+68h+var_38], eax
0x180004659  mov     edx, 0Fh
0x18000465e  mov     [rsp+68h+var_40], rdi
0x180004663  mov     [rsp+68h+var_48], 81h
0x18000466b  call    WPP_SF_sdqd
0x180004670  jmp     loc_18000458F
0x180004675  cmp     rcx, rbp
0x180004678  jnz     loc_180004995
0x18000467e  test    rdi, rdi
0x180004681  jz      short loc_180004609
0x180004683  call    cs:__imp_GetProcessHeap
0x180004689  mov     rsi, rax
0x18000468c  test    rax, rax
0x18000468f  jz      loc_1800049FA
0x180004695  mov     r8, rdi; lpMem
0x180004698  xor     edx, edx; dwFlags
0x18000469a  mov     rcx, rsi; hHeap
0x18000469d  call    cs:__imp_HeapFree
0x1800046a3  test    eax, eax
0x1800046a5  jz      short loc_1800046E3
0x1800046a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046ae  cmp     rcx, rbp
0x1800046b1  jz      loc_180004609
0x1800046b7  test    byte ptr [rcx+1Ch], 2
0x1800046bb  jz      loc_180004609
0x1800046c1  mov     rcx, [rcx+10h]
0x1800046c5  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x1800046cc  mov     [rsp+68h+var_40], rdi
0x1800046d1  mov     [rsp+68h+var_48], 94h
0x1800046d9  call    WPP_SF_sdq
0x1800046de  jmp     loc_180004609
0x1800046e3  call    cs:__imp_GetLastError
0x1800046e9  test    eax, eax
0x1800046eb  jz      loc_180004609
0x1800046f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046f8  cmp     rcx, rbp
0x1800046fb  jz      loc_180004609
0x180004701  test    byte ptr [rcx+1Ch], 4
0x180004705  jz      loc_180004609
0x18000470b  mov     rcx, [rcx+10h]
0x18000470f  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x180004716  mov     [rsp+68h+var_38], eax
0x18000471a  mov     edx, 0Fh
0x18000471f  mov     [rsp+68h+var_40], rdi
0x180004724  mov     [rsp+68h+var_48], 94h
0x18000472c  call    WPP_SF_sdqd
0x180004731  jmp     loc_180004609
0x180004736  call    cs:__imp_GetLastError
0x18000473c  mov     esi, eax
0x18000473e  test    eax, eax
0x180004740  jz      loc_1800044DB
0x180004746  mov     rcx, cs:WPP_GLOBAL_Control
0x18000474d  lea     rbp, WPP_GLOBAL_Control
0x180004754  cmp     rcx, rbp
0x180004757  jz      short loc_180004787
0x180004759  test    byte ptr [rcx+1Ch], 4
0x18000475d  jz      short loc_180004787
0x18000475f  mov     rcx, [rcx+10h]
0x180004763  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x18000476a  mov     dword ptr [rsp+68h+var_40], eax
0x18000476e  mov     edx, 0Ah
0x180004773  mov     [rsp+68h+var_48], 76h ; 'v'
0x18000477b  call    WPP_SF_sdd
0x180004780  mov     rcx, cs:WPP_GLOBAL_Control
0x180004787  xor     edi, edi
0x180004789  mov     ebx, esi
0x18000478b  cmp     rcx, rbp
0x18000478e  jz      loc_18000467E
0x180004794  test    byte ptr [rcx+1Ch], 4
0x180004798  jz      loc_18000467E
0x18000479e  mov     edx, 13h
0x1800047a3  jmp     loc_1800049A4
0x1800047a8  mov     esi, 0Eh
0x1800047ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047b4  lea     rbp, WPP_GLOBAL_Control
0x1800047bb  cmp     rcx, rbp
0x1800047be  jz      short loc_1800047F2
0x1800047c0  test    byte ptr [rcx+1Ch], 4
0x1800047c4  jz      short loc_1800047F2
0x1800047c6  mov     rcx, [rcx+10h]
0x1800047ca  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x1800047d1  mov     edx, 0Bh
0x1800047d6  mov     dword ptr [rsp+68h+var_40], 44h ; 'D'
0x1800047de  mov     [rsp+68h+var_48], 76h ; 'v'
0x1800047e6  call    WPP_SF_sdd
0x1800047eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047f2  mov     ebx, esi
0x1800047f4  jmp     short loc_18000478B
0x1800047f6  mov     rcx, [rcx+10h]
0x1800047fa  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x180004801  mov     [rsp+68h+var_38], 44h ; 'D'
0x180004809  mov     edx, 0Ch
0x18000480e  mov     [rsp+68h+var_40], rdi
0x180004813  mov     [rsp+68h+var_48], 76h ; 'v'
0x18000481b  call    WPP_SF_sdqd
0x180004820  mov     rcx, cs:WPP_GLOBAL_Control
0x180004827  jmp     loc_180004518
0x18000482c  test    eax, eax
0x18000482e  jz      loc_180004551
0x180004834  mov     rcx, cs:WPP_GLOBAL_Control
0x18000483b  cmp     rcx, rbp
0x18000483e  jz      loc_180004683
0x180004844  test    byte ptr [rcx+1Ch], 4
0x180004848  jz      loc_180004683
0x18000484e  mov     edx, 14h
0x180004853  jmp     loc_1800049E5
0x180004858  call    cs:__imp_GetLastError
0x18000485e  test    eax, eax
0x180004860  jz      loc_180004563
0x180004866  mov     rcx, cs:WPP_GLOBAL_Control
0x18000486d  cmp     rcx, rbp
0x180004870  jz      loc_18000458F
0x180004876  test    byte ptr [rcx+1Ch], 4
0x18000487a  jz      loc_18000458F
0x180004880  mov     rcx, [rcx+10h]
0x180004884  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x18000488b  mov     dword ptr [rsp+68h+var_40], eax
0x18000488f  mov     edx, 0Dh
0x180004894  mov     [rsp+68h+var_48], 81h
0x18000489c  call    WPP_SF_sdd
0x1800048a1  jmp     loc_18000458F
0x1800048a6  mov     rcx, [rcx+10h]
0x1800048aa  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x1800048b1  mov     [rsp+68h+var_40], rdi
0x1800048b6  mov     [rsp+68h+var_48], 81h
0x1800048be  call    WPP_SF_sdq
0x1800048c3  jmp     loc_18000458F
0x1800048c8  call    cs:__imp_GetLastError
0x1800048ce  mov     esi, eax
0x1800048d0  test    eax, eax
0x1800048d2  jz      loc_1800045AB
0x1800048d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048df  cmp     rcx, rbp
0x1800048e2  jz      short loc_180004912
0x1800048e4  test    byte ptr [rcx+1Ch], 4
0x1800048e8  jz      short loc_180004912
0x1800048ea  mov     rcx, [rcx+10h]
0x1800048ee  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x1800048f5  mov     dword ptr [rsp+68h+var_40], eax
0x1800048f9  mov     edx, 0Ah
0x1800048fe  mov     [rsp+68h+var_48], 83h
0x180004906  call    WPP_SF_sdd
0x18000490b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004912  xor     edi, edi
0x180004914  mov     ebx, esi
0x180004916  jmp     loc_180004675
0x18000491b  mov     esi, 0Eh
0x180004920  mov     rcx, cs:WPP_GLOBAL_Control
0x180004927  cmp     rcx, rbp
0x18000492a  jz      short loc_18000495B
0x18000492c  test    byte ptr [rcx+1Ch], 4
0x180004930  jz      short loc_18000495B
0x180004932  mov     rcx, [rcx+10h]
0x180004936  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x18000493d  mov     edx, 0Bh
0x180004942  mov     dword ptr [rsp+68h+var_40], r14d
0x180004947  mov     [rsp+68h+var_48], 83h
0x18000494f  call    WPP_SF_sdd
0x180004954  mov     rcx, cs:WPP_GLOBAL_Control
0x18000495b  mov     ebx, esi
0x18000495d  jmp     loc_180004675
0x180004962  mov     rcx, [rcx+10h]
0x180004966  lea     r9, aRacreatewellkn_0; "RaCreateWellKnownSid"
0x18000496d  mov     [rsp+68h+var_38], r14d
0x180004972  mov     edx, 0Ch
0x180004977  mov     [rsp+68h+var_40], rdi
0x18000497c  mov     [rsp+68h+var_48], 83h
0x180004984  call    WPP_SF_sdqd
0x180004989  mov     rcx, cs:WPP_GLOBAL_Control
0x180004990  jmp     loc_1800045DE
0x180004995  test    byte ptr [rcx+1Ch], 4
0x180004999  jz      loc_18000467E
0x18000499f  mov     edx, 15h
0x1800049a4  mov     rcx, [rcx+10h]
0x1800049a8  mov     [rsp+68h+var_48], esi
0x1800049ac  call    WPP_SF_dD
0x1800049b1  jmp     loc_18000467E
0x1800049b6  call    cs:__imp_GetLastError
0x1800049bc  mov     ebx, eax
0x1800049be  test    eax, eax
0x1800049c0  jz      loc_180004606
0x1800049c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049cd  cmp     rcx, rbp
0x1800049d0  jz      loc_180004683
0x1800049d6  test    byte ptr [rcx+1Ch], 4
0x1800049da  jz      loc_180004683
0x1800049e0  mov     edx, 16h
0x1800049e5  mov     rcx, [rcx+10h]
0x1800049e9  mov     r9d, r12d
0x1800049ec  mov     [rsp+68h+var_48], eax
0x1800049f0  call    WPP_SF_DD
0x1800049f5  jmp     loc_180004683
0x1800049fa  call    cs:__imp_GetLastError
  ... truncated ...
```
