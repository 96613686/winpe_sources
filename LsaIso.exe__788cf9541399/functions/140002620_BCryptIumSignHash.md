# BCryptIumSignHash

- ea: `0x140002620`
- end: `0x140002907`
- name: `BCryptIumSignHash`
- size: `743`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x140002080`
- `0x1400021f0`
- `0x140002620`
- `0x1400083a8`
- `0x14000a650`
- `0x14001193c`
- `0x140011964`
- `0x140011b74`
- `0x140011f58`
- `0x140038cea`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400028b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400028b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002820`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002820`
- `bcrypt!BCryptSignHash` at `0x1400028aa`
- `bcrypt!BCryptSignHash` at `0x1400028aa`

## pseudocode

```c
__int64 __fastcall BCryptIumSignHash(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        UCHAR *a4,
        ULONG cbInput,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG a9)
{
  const wchar_t **v9; // rbp
  __int64 result; // rax
  unsigned int v15; // ebx
  PVOID *v16; // rcx
  struct _BCRYPT_ISO_OBJECT *v17; // rax
  __int64 v18; // r8
  RTL_SRWLOCK *v19; // rsi
  ULONG dwFlags; // r14d
  const wchar_t *v21; // rbp
  int v22; // r8d
  const wchar_t *v23; // r9
  int v24; // eax
  void *v25; // rdx
  struct BCRYPTIUM_CONTEXT *v26; // [rsp+80h] [rbp+18h] BYREF

  v9 = 0;
  if ( a3 )
    v9 = *(const wchar_t ***)(a3 + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  v26 = 0;
  result = BCryptIumContextManagerGetContext(a1, &v26);
  v15 = result;
  if ( (int)result < 0 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return result;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_38;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      254,
      &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
      (unsigned int)result);
    goto LABEL_37;
  }
  v17 = LookupBCryptIsoObject(v26, a2, 0x42494F4Bu);
  v19 = (RTL_SRWLOCK *)v17;
  if ( v17 )
  {
    if ( (*((_DWORD *)v17 + 4) & 0x70) != 0 )
    {
      v15 = -1073741637;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          256,
          &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
          3221225659LL);
    }
    else
    {
      dwFlags = a9;
      if ( (a9 & 8) == 0
        || !v9
        || (v21 = *v9, !wcsncmp_0(v21, L"SHA256", 7u))
        || !wcsncmp_0(v21, L"SHA384", 7u)
        || !wcsncmp_0(v21, L"SHA512", 7u) )
      {
        AcquireSRWLockShared(v19 + 5);
        v24 = IsAlgorithmHandleSupported(v19, dwFlags, 0);
        v15 = v24;
        if ( v24 >= 0 )
        {
          v25 = 0;
          if ( a3 )
            v25 = *(void **)(a3 + 8);
          v15 = BCryptSignHash(v19[1].Ptr, v25, a4, cbInput, pbOutput, cbOutput, pcbResult, dwFlags);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            259,
            &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
            (unsigned int)v24);
        }
        ReleaseSRWLockShared(v19 + 5);
      }
      else
      {
        v15 = -1073741637;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = L"<NULL>";
          if ( v21 )
            LODWORD(v23) = (_DWORD)v21;
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, v22, (_DWORD)v23, 187);
        }
      }
    }
    BCryptIumDereferenceObject(v19);
    goto LABEL_37;
  }
  v15 = -1073741816;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_38;
    WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, v18, a2, -1073741816);
LABEL_37:
    v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_38:
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
      WPP_SF_d(v16[2], 261, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v15);
  }
  return v15;
}

```

## disassembly

```asm
0x140002620  mov     [rsp+arg_8], rbx
0x140002625  push    rbp
0x140002626  push    rdi
0x140002627  push    r12
0x140002629  push    r14
0x14000262b  push    r15
0x14000262d  sub     rsp, 40h
0x140002631  xor     ebp, ebp
0x140002633  mov     r15, r9
0x140002636  mov     rdi, r8
0x140002639  mov     r14, rdx
0x14000263c  mov     rbx, rcx
0x14000263f  test    r8, r8
0x140002642  jz      short loc_140002648
0x140002644  mov     rbp, [r8+8]
0x140002648  mov     rcx, cs:WPP_GLOBAL_Control
0x14000264f  lea     r12, WPP_GLOBAL_Control
0x140002656  cmp     rcx, r12
0x140002659  jz      short loc_140002676
0x14000265b  test    byte ptr [rcx+1Ch], 4
0x14000265f  jz      short loc_140002676
0x140002661  mov     rcx, [rcx+10h]
0x140002665  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000266c  mov     edx, 0FDh
0x140002671  call    WPP_SF_
0x140002676  lea     rdx, [rsp+68h+arg_10]
0x14000267e  mov     [rsp+68h+arg_0], rsi
0x140002683  mov     rcx, rbx
0x140002686  mov     [rsp+68h+arg_10], 0
0x140002692  call    BCryptIumContextManagerGetContext
0x140002697  mov     ebx, eax
0x140002699  test    eax, eax
0x14000269b  jns     short loc_1400026D4
0x14000269d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026a4  cmp     rcx, r12
0x1400026a7  jz      loc_1400028F0
0x1400026ad  test    byte ptr [rcx+1Ch], 4
0x1400026b1  jz      loc_1400028CB
0x1400026b7  mov     rcx, [rcx+10h]
0x1400026bb  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x1400026c2  mov     edx, 0FEh
0x1400026c7  mov     r9d, eax
0x1400026ca  call    WPP_SF_d
0x1400026cf  jmp     loc_1400028C4
0x1400026d4  mov     rcx, [rsp+68h+arg_10]; struct BCRYPTIUM_CONTEXT *
0x1400026dc  mov     r8d, 42494F4Bh; unsigned int
0x1400026e2  mov     rdx, r14; unsigned __int64
0x1400026e5  call    ?LookupBCryptIsoObject@@YAPEAU_BCRYPT_ISO_OBJECT@@PEAUBCRYPTIUM_CONTEXT@@_KK@Z; LookupBCryptIsoObject(BCRYPTIUM_CONTEXT *,unsigned __int64,ulong)
0x1400026ea  mov     rsi, rax
0x1400026ed  test    rax, rax
0x1400026f0  jnz     short loc_14000272B
0x1400026f2  mov     ebx, 0C0000008h
0x1400026f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026fe  cmp     rcx, r12
0x140002701  jz      loc_1400028EE
0x140002707  test    byte ptr [rcx+1Ch], 1
0x14000270b  jz      loc_1400028CB
0x140002711  mov     rcx, [rcx+10h]
0x140002715  mov     edx, 0FFh
0x14000271a  mov     r9, r14
0x14000271d  mov     dword ptr [rsp+68h+pbOutput], ebx
0x140002721  call    WPP_SF_ID
0x140002726  jmp     loc_1400028C4
0x14000272b  mov     eax, [rax+10h]
0x14000272e  test    al, 70h
0x140002730  jz      short loc_14000276E
0x140002732  mov     ebx, 0C00000BBh
0x140002737  mov     rcx, cs:WPP_GLOBAL_Control
0x14000273e  cmp     rcx, r12
0x140002741  jz      loc_1400028BC
0x140002747  test    byte ptr [rcx+1Ch], 1
0x14000274b  jz      loc_1400028BC
0x140002751  mov     rcx, [rcx+10h]
0x140002755  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000275c  mov     edx, 100h
0x140002761  mov     r9d, ebx
0x140002764  call    WPP_SF_d
0x140002769  jmp     loc_1400028BC
0x14000276e  mov     r14d, [rsp+68h+arg_40]
0x140002776  test    r14b, 8
0x14000277a  jz      loc_14000281C
0x140002780  test    rbp, rbp
0x140002783  jz      loc_14000281C
0x140002789  mov     rbp, [rbp+0]
0x14000278d  lea     rdx, aSha256; "SHA256"
0x140002794  mov     rcx, rbp; String1
0x140002797  mov     r8d, 7; MaxCount
0x14000279d  call    wcsncmp_0
0x1400027a2  test    eax, eax
0x1400027a4  jz      short loc_14000281C
0x1400027a6  mov     r8d, 7; MaxCount
0x1400027ac  lea     rdx, aSha384; "SHA384"
0x1400027b3  mov     rcx, rbp; String1
0x1400027b6  call    wcsncmp_0
0x1400027bb  test    eax, eax
0x1400027bd  jz      short loc_14000281C
0x1400027bf  mov     r8d, 7; MaxCount
0x1400027c5  lea     rdx, aSha512; "SHA512"
0x1400027cc  mov     rcx, rbp; String1
0x1400027cf  call    wcsncmp_0
0x1400027d4  test    eax, eax
0x1400027d6  jz      short loc_14000281C
0x1400027d8  mov     ebx, 0C00000BBh
0x1400027dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400027e4  cmp     rcx, r12
0x1400027e7  jz      loc_1400028BC
0x1400027ed  test    byte ptr [rcx+1Ch], 1
0x1400027f1  jz      loc_1400028BC
0x1400027f7  mov     rcx, [rcx+10h]
0x1400027fb  lea     r9, aNull_2; "<NULL>"
0x140002802  test    rbp, rbp
0x140002805  mov     dword ptr [rsp+68h+pbOutput], ebx
0x140002809  mov     edx, 101h
0x14000280e  cmovnz  r9, rbp
0x140002812  call    WPP_SF_Sd
0x140002817  jmp     loc_1400028BC
0x14000281c  lea     rcx, [rsi+28h]; SRWLock
0x140002820  call    cs:__imp_AcquireSRWLockShared
0x140002826  xor     r8d, r8d
0x140002829  mov     edx, r14d
0x14000282c  mov     rcx, rsi
0x14000282f  call    IsAlgorithmHandleSupported
0x140002834  mov     ebx, eax
0x140002836  test    eax, eax
0x140002838  jns     short loc_140002866
0x14000283a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002841  cmp     rcx, r12
0x140002844  jz      short loc_1400028B2
0x140002846  test    byte ptr [rcx+1Ch], 1
0x14000284a  jz      short loc_1400028B2
0x14000284c  mov     rcx, [rcx+10h]
0x140002850  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140002857  mov     edx, 103h
0x14000285c  mov     r9d, eax
0x14000285f  call    WPP_SF_d
0x140002864  jmp     short loc_1400028B2
0x140002866  xor     edx, edx
0x140002868  test    rdi, rdi
0x14000286b  jz      short loc_140002871
0x14000286d  mov     rdx, [rdi+8]; pPaddingInfo
0x140002871  mov     rax, [rsp+68h+arg_38]
0x140002879  mov     r8, r15; pbInput
0x14000287c  mov     r9d, [rsp+68h+cbInput]; cbInput
0x140002884  mov     rcx, [rsi+8]; hKey
0x140002888  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x14000288d  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140002892  mov     eax, [rsp+68h+arg_30]
0x140002899  mov     [rsp+68h+cbOutput], eax; cbOutput
0x14000289d  mov     rax, [rsp+68h+arg_28]
0x1400028a5  mov     [rsp+68h+pbOutput], rax; pbOutput
0x1400028aa  call    cs:__imp_BCryptSignHash
0x1400028b0  mov     ebx, eax
0x1400028b2  lea     rcx, [rsi+28h]; SRWLock
0x1400028b6  call    cs:__imp_ReleaseSRWLockShared
0x1400028bc  mov     rcx, rsi; hMem
0x1400028bf  call    ?BCryptIumDereferenceObject@@YAXPEAU_BCRYPT_ISO_OBJECT@@@Z; BCryptIumDereferenceObject(_BCRYPT_ISO_OBJECT *)
0x1400028c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028cb  cmp     rcx, r12
0x1400028ce  jz      short loc_1400028EE
0x1400028d0  test    byte ptr [rcx+1Ch], 4
0x1400028d4  jz      short loc_1400028EE
0x1400028d6  mov     rcx, [rcx+10h]
0x1400028da  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x1400028e1  mov     edx, 105h
0x1400028e6  mov     r9d, ebx
0x1400028e9  call    WPP_SF_d
0x1400028ee  mov     eax, ebx
0x1400028f0  mov     rsi, [rsp+68h+arg_0]
0x1400028f5  mov     rbx, [rsp+68h+arg_8]
0x1400028fa  add     rsp, 40h
0x1400028fe  pop     r15
0x140002900  pop     r14
0x140002902  pop     r12
0x140002904  pop     rdi
0x140002905  pop     rbp
0x140002906  retn
```
