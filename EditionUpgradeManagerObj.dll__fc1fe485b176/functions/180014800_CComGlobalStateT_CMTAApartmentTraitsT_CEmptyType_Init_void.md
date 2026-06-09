# CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::Init(void)

- ea: `0x180014800`
- end: `0x180014a15`
- name: `?Init@?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@AEAAJXZ`
- size: `533`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180012af4`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000a2cc`
- `0x18000a340`
- `0x18001356c`
- `0x180014800`
- `0x180014ba0`
- `0x1800168c4`
- `0x180022968`

## pseudocode

```c
__int64 __fastcall CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::Init(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  int v3; // r12d
  int v4; // ebx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // r15
  unsigned __int8 v10; // al
  int v11; // edi
  int v12; // eax
  __int64 v13; // r15
  __int64 v14; // r13
  int v15; // eax
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // edi
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  int v22; // r8d
  unsigned int v24; // [rsp+60h] [rbp+8h] BYREF
  int v25; // [rsp+68h] [rbp+10h] BYREF

  v2 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  v3 = 0;
  v4 = 0;
  *(_DWORD *)(a1 + 56) = 0;
  while ( v2 )
  {
    v6 = *(_DWORD *)(v2 + 8);
    if ( !v6 )
    {
      *(_QWORD *)(a1 + 40) = *(_QWORD *)(v2 + 16);
      goto LABEL_43;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      *(_QWORD *)(a1 + 48) = *(_QWORD *)(v2 + 16);
      goto LABEL_43;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      v13 = *(int *)(a1 + 12);
      v25 = 0;
      if ( (int)v13 < 0 )
      {
        v4 = -2147418113;
        goto LABEL_35;
      }
      v14 = *(_QWORD *)(v2 + 16);
      v15 = SafeAdd<int>(v13, a2, &v25);
      v4 = v15;
      if ( v15 < 0 )
      {
        v17 = v15;
        goto LABEL_17;
      }
      v18 = *(_DWORD *)(a1 + 8);
      if ( v18 < 0 )
      {
        v19 = -2147418113;
        v4 = -2147418113;
        goto LABEL_33;
      }
      if ( v25 > v18 )
      {
        v24 = *(_DWORD *)(a1 + 8);
        do
        {
          if ( v18 )
          {
            v20 = SafeMul<int>(v18, v16, (int *)&v24);
            v4 = v20;
            if ( v20 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
            v18 = v24;
          }
          else
          {
            v18 = 32;
            v4 = 0;
            v24 = 32;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
          if ( v4 < 0 )
          {
            v19 = v4;
            goto LABEL_33;
          }
        }
        while ( v18 < v25 );
        v21 = CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(
                a1 + 8,
                (unsigned int)v18);
        v4 = v21;
        if ( v21 >= 0 )
          goto LABEL_34;
        v19 = v21;
LABEL_33:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
      }
      else
      {
        v4 = 0;
      }
LABEL_34:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
      if ( v4 >= 0 )
      {
        v22 = *(_DWORD *)(a1 + 12);
        if ( (int)v13 < v22 )
          memmove_0(
            (void *)(*(_QWORD *)(a1 + 16) + 8 * v13 + 8),
            (const void *)(*(_QWORD *)(a1 + 16) + 8 * v13),
            8LL * (v22 - (int)v13));
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v13) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v13) = v14;
        ++*(_DWORD *)(a1 + 12);
        v4 = 0;
      }
      else
      {
LABEL_35:
        v17 = v4;
LABEL_17:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
      if ( v4 < 0 )
        goto LABEL_47;
      goto LABEL_43;
    }
    if ( v8 == 1 )
    {
      v9 = *(_QWORD *)(v2 + 16);
      v24 = 0;
      v4 = 0;
      v10 = CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(
              a1 + 24,
              (const void *)(v9 + 4),
              (int *)&v24);
      v11 = v10;
      if ( v10
        || (v12 = CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Insert(
                    a1 + 24,
                    v24,
                    v9),
            v4 = v12,
            v12 >= 0) )
      {
        v3 = v11 ^ 1;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
      if ( v4 < 0 )
        goto LABEL_47;
      if ( !v3 )
      {
        v4 = -2147418113;
LABEL_47:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
        break;
      }
      ++*(_DWORD *)(a1 + 56);
    }
LABEL_43:
    v2 = *(_QWORD *)v2;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014800  mov     [rsp+arg_10], rbx
0x180014805  push    rbp
0x180014806  push    rsi
0x180014807  push    rdi
0x180014808  push    r12
0x18001480a  push    r13
0x18001480c  push    r14
0x18001480e  push    r15
0x180014810  sub     rsp, 20h
0x180014814  mov     rsi, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18001481b  xor     r12d, r12d
0x18001481e  xor     ebx, ebx
0x180014820  mov     rbp, rcx
0x180014823  mov     [rcx+38h], ebx
0x180014826  jmp     loc_1800149E0
0x18001482b  mov     ecx, [rsi+8]
0x18001482e  test    ecx, ecx
0x180014830  jz      loc_1800149D5
0x180014836  sub     ecx, 1
0x180014839  jz      loc_1800149CB
0x18001483f  sub     ecx, 1
0x180014842  jz      short loc_1800148BA
0x180014844  cmp     ecx, 1
0x180014847  jnz     loc_1800149DD
0x18001484d  mov     r15, [rsi+10h]
0x180014851  lea     r8, [rsp+58h+arg_0]
0x180014856  lea     rcx, [rbp+18h]
0x18001485a  mov     [rsp+58h+arg_0], 0
0x180014862  xor     ebx, ebx
0x180014864  lea     rdx, [r15+4]
0x180014868  call    ?Find@?$CSortedArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NAEBU_GUID@@PEAH@Z; CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(_GUID const &,int *)
0x18001486d  movzx   edi, al
0x180014870  test    al, al
0x180014872  jnz     short loc_180014893
0x180014874  mov     edx, [rsp+58h+arg_0]
0x180014878  lea     rcx, [rbp+18h]
0x18001487c  mov     r8, r15
0x18001487f  call    ?Insert@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHPEAU?$CComObjectActivationT@VCEmptyType@@@@@Z; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Insert(int,CComObjectActivationT<CEmptyType> *)
0x180014884  mov     ebx, eax
0x180014886  test    eax, eax
0x180014888  jns     short loc_180014893
0x18001488a  mov     ecx, eax
0x18001488c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014891  jmp     short loc_18001489A
0x180014893  mov     r12d, edi
0x180014896  xor     r12d, 1
0x18001489a  mov     ecx, ebx
0x18001489c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800148a1  test    ebx, ebx
0x1800148a3  js      loc_1800149F0
0x1800148a9  test    r12d, r12d
0x1800148ac  jz      loc_1800149EB
0x1800148b2  inc     dword ptr [rbp+38h]
0x1800148b5  jmp     loc_1800149DD
0x1800148ba  movsxd  r15, dword ptr [rbp+0Ch]
0x1800148be  mov     [rsp+58h+arg_8], 0
0x1800148c6  test    r15d, r15d
0x1800148c9  jns     short loc_1800148D5
0x1800148cb  mov     ebx, 8000FFFFh
0x1800148d0  jmp     loc_18001497C
0x1800148d5  mov     r13, [rsi+10h]
0x1800148d9  lea     r8, [rsp+58h+arg_8]
0x1800148de  mov     ecx, r15d
0x1800148e1  call    ??$SafeAdd@H@@YAJHHPEAH@Z; SafeAdd<int>(int,int,int *)
0x1800148e6  mov     ebx, eax
0x1800148e8  test    eax, eax
0x1800148ea  jns     short loc_1800148F8
0x1800148ec  mov     ecx, eax
0x1800148ee  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800148f3  jmp     loc_1800149BE
0x1800148f8  mov     edi, [rbp+8]
0x1800148fb  test    edi, edi
0x1800148fd  jns     short loc_180014908
0x1800148ff  mov     ecx, 8000FFFFh
0x180014904  mov     ebx, ecx
0x180014906  jmp     short loc_18001496C
0x180014908  cmp     [rsp+58h+arg_8], edi
0x18001490c  jg      short loc_180014912
0x18001490e  xor     ebx, ebx
0x180014910  jmp     short loc_180014971
0x180014912  mov     [rsp+58h+arg_0], edi
0x180014916  test    edi, edi
0x180014918  jnz     short loc_180014927
0x18001491a  mov     edi, 20h ; ' '
0x18001491f  xor     ebx, ebx
0x180014921  mov     [rsp+58h+arg_0], edi
0x180014925  jmp     short loc_180014944
0x180014927  lea     r8, [rsp+58h+arg_0]
0x18001492c  mov     ecx, edi
0x18001492e  call    ??$SafeMul@H@@YAJHHPEAH@Z; SafeMul<int>(int,int,int *)
0x180014933  mov     ebx, eax
0x180014935  test    eax, eax
0x180014937  jns     short loc_180014940
0x180014939  mov     ecx, eax
0x18001493b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014940  mov     edi, [rsp+58h+arg_0]
0x180014944  mov     ecx, ebx
0x180014946  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001494b  test    ebx, ebx
0x18001494d  js      short loc_18001496A
0x18001494f  cmp     edi, [rsp+58h+arg_8]
0x180014953  jl      short loc_180014916
0x180014955  mov     edx, edi
0x180014957  lea     rcx, [rbp+8]
0x18001495b  call    ?SetSize@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180014960  mov     ebx, eax
0x180014962  test    eax, eax
0x180014964  jns     short loc_180014971
0x180014966  mov     ecx, eax
0x180014968  jmp     short loc_18001496C
0x18001496a  mov     ecx, ebx
0x18001496c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014971  mov     ecx, ebx
0x180014973  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180014978  test    ebx, ebx
0x18001497a  jns     short loc_180014983
0x18001497c  mov     ecx, ebx
0x18001497e  jmp     loc_1800148EE
0x180014983  mov     r8d, [rbp+0Ch]
0x180014987  cmp     r15d, r8d
0x18001498a  jge     short loc_1800149A7
0x18001498c  mov     rcx, [rbp+10h]
0x180014990  sub     r8d, r15d
0x180014993  movsxd  r8, r8d
0x180014996  shl     r8, 3; Size
0x18001499a  lea     rdx, [rcx+r15*8]; Src
0x18001499e  lea     rcx, [rdx+8]; void *
0x1800149a2  call    memmove_0
0x1800149a7  mov     rax, [rbp+10h]
0x1800149ab  xor     edx, edx
0x1800149ad  mov     [rax+r15*8], rdx
0x1800149b1  mov     rax, [rbp+10h]
0x1800149b5  mov     [rax+r15*8], r13
0x1800149b9  inc     dword ptr [rbp+0Ch]
0x1800149bc  xor     ebx, ebx
0x1800149be  mov     ecx, ebx
0x1800149c0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800149c5  test    ebx, ebx
0x1800149c7  js      short loc_1800149F0
0x1800149c9  jmp     short loc_1800149DD
0x1800149cb  mov     rax, [rsi+10h]
0x1800149cf  mov     [rbp+30h], rax
0x1800149d3  jmp     short loc_1800149DD
0x1800149d5  mov     rax, [rsi+10h]
0x1800149d9  mov     [rbp+28h], rax
0x1800149dd  mov     rsi, [rsi]
0x1800149e0  test    rsi, rsi
0x1800149e3  jnz     loc_18001482B
0x1800149e9  jmp     short loc_1800149F7
0x1800149eb  mov     ebx, 8000FFFFh
0x1800149f0  mov     ecx, ebx
0x1800149f2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800149f7  mov     ecx, ebx
0x1800149f9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800149fe  mov     eax, ebx
0x180014a00  mov     rbx, [rsp+58h+arg_10]
0x180014a05  add     rsp, 20h
0x180014a09  pop     r15
0x180014a0b  pop     r14
0x180014a0d  pop     r13
0x180014a0f  pop     r12
0x180014a11  pop     rdi
0x180014a12  pop     rsi
0x180014a13  pop     rbp
0x180014a14  retn
```
