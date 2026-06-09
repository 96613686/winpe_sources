# CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Insert(int,CComObjectActivationT<CEmptyType> *)

- ea: `0x180014ba0`
- end: `0x180014cd3`
- name: `?Insert@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHPEAU?$CComObjectActivationT@VCEmptyType@@@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014800`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000a2cc`
- `0x18000a340`
- `0x180014ba0`
- `0x1800168c4`
- `0x180022968`

## pseudocode

```c
__int64 __fastcall CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbp
  int v5; // ecx
  unsigned int v7; // edi
  int v8; // ecx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // edi
  int v12; // ebx
  int v13; // ecx
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  int v18; // [rsp+40h] [rbp+8h] BYREF
  int v19; // [rsp+58h] [rbp+20h] BYREF

  v4 = (int)a2;
  v5 = *(_DWORD *)(a1 + 4);
  v19 = 0;
  if ( v5 < 0 )
  {
    v7 = -2147418113;
    v8 = -2147418113;
LABEL_5:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_27;
  }
  v9 = SafeAdd<int>(v5, a2, &v19);
  v7 = v9;
  if ( v9 < 0 )
  {
    v8 = v9;
    goto LABEL_5;
  }
  v11 = *(_DWORD *)a1;
  if ( *(int *)a1 >= 0 )
  {
    if ( v19 <= v11 )
    {
      v12 = 0;
      goto LABEL_22;
    }
    v18 = *(_DWORD *)a1;
    do
    {
      if ( v11 )
      {
        v14 = SafeMul<int>(v11, v10, &v18);
        v12 = v14;
        if ( v14 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
        v11 = v18;
      }
      else
      {
        v11 = 32;
        v12 = 0;
        v18 = 32;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
      if ( v12 < 0 )
      {
        v13 = v12;
        goto LABEL_21;
      }
    }
    while ( v11 < v19 );
    v15 = CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(
            a1,
            (unsigned int)v11);
    v12 = v15;
    if ( v15 >= 0 )
      goto LABEL_22;
    v13 = v15;
  }
  else
  {
    v12 = -2147418113;
    v13 = -2147418113;
  }
LABEL_21:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
  if ( v12 < 0 )
  {
    v7 = v12;
    v8 = v12;
    goto LABEL_5;
  }
  v16 = *(_DWORD *)(a1 + 4);
  if ( (int)v4 < v16 )
    memmove_0(
      (void *)(*(_QWORD *)(a1 + 8) + 8 * v4 + 8),
      (const void *)(*(_QWORD *)(a1 + 8) + 8 * v4),
      8LL * (v16 - (int)v4));
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4) = a3;
  ++*(_DWORD *)(a1 + 4);
  v7 = 0;
LABEL_27:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return v7;
}

```

## disassembly

```asm
0x180014ba0  mov     [rsp+arg_8], rbx
0x180014ba5  mov     [rsp+arg_10], rbp
0x180014baa  push    rsi
0x180014bab  push    rdi
0x180014bac  push    r14
0x180014bae  sub     rsp, 20h
0x180014bb2  mov     rsi, rcx
0x180014bb5  movsxd  rbp, edx
0x180014bb8  mov     ecx, [rcx+4]
0x180014bbb  mov     r14, r8
0x180014bbe  mov     [rsp+38h+arg_18], 0
0x180014bc6  test    ecx, ecx
0x180014bc8  jns     short loc_180014BD3
0x180014bca  mov     edi, 8000FFFFh
0x180014bcf  mov     ecx, edi
0x180014bd1  jmp     short loc_180014BE5
0x180014bd3  lea     r8, [rsp+38h+arg_18]
0x180014bd8  call    ??$SafeAdd@H@@YAJHHPEAH@Z; SafeAdd<int>(int,int,int *)
0x180014bdd  mov     edi, eax
0x180014bdf  test    eax, eax
0x180014be1  jns     short loc_180014BEF
0x180014be3  mov     ecx, eax
0x180014be5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014bea  jmp     loc_180014CB7
0x180014bef  mov     edi, [rsi]
0x180014bf1  test    edi, edi
0x180014bf3  jns     short loc_180014C00
0x180014bf5  mov     edi, 8000FFFFh
0x180014bfa  mov     ebx, edi
0x180014bfc  mov     ecx, edi
0x180014bfe  jmp     short loc_180014C63
0x180014c00  cmp     [rsp+38h+arg_18], edi
0x180014c04  jg      short loc_180014C0A
0x180014c06  xor     ebx, ebx
0x180014c08  jmp     short loc_180014C68
0x180014c0a  mov     [rsp+38h+arg_0], edi
0x180014c0e  test    edi, edi
0x180014c10  jnz     short loc_180014C1F
0x180014c12  mov     edi, 20h ; ' '
0x180014c17  xor     ebx, ebx
0x180014c19  mov     [rsp+38h+arg_0], edi
0x180014c1d  jmp     short loc_180014C3C
0x180014c1f  lea     r8, [rsp+38h+arg_0]
0x180014c24  mov     ecx, edi
0x180014c26  call    ??$SafeMul@H@@YAJHHPEAH@Z; SafeMul<int>(int,int,int *)
0x180014c2b  mov     ebx, eax
0x180014c2d  test    eax, eax
0x180014c2f  jns     short loc_180014C38
0x180014c31  mov     ecx, eax
0x180014c33  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014c38  mov     edi, [rsp+38h+arg_0]
0x180014c3c  mov     ecx, ebx
0x180014c3e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180014c43  test    ebx, ebx
0x180014c45  js      short loc_180014C61
0x180014c47  cmp     edi, [rsp+38h+arg_18]
0x180014c4b  jl      short loc_180014C0E
0x180014c4d  mov     edx, edi
0x180014c4f  mov     rcx, rsi
0x180014c52  call    ?SetSize@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180014c57  mov     ebx, eax
0x180014c59  test    eax, eax
0x180014c5b  jns     short loc_180014C68
0x180014c5d  mov     ecx, eax
0x180014c5f  jmp     short loc_180014C63
0x180014c61  mov     ecx, ebx
0x180014c63  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014c68  mov     ecx, ebx
0x180014c6a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180014c6f  test    ebx, ebx
0x180014c71  jns     short loc_180014C7C
0x180014c73  mov     edi, ebx
0x180014c75  mov     ecx, ebx
0x180014c77  jmp     loc_180014BE5
0x180014c7c  mov     ecx, [rsi+4]
0x180014c7f  mov     rbx, rbp
0x180014c82  cmp     ebp, ecx
0x180014c84  jge     short loc_180014CA0
0x180014c86  mov     rax, [rsi+8]
0x180014c8a  sub     ecx, ebp
0x180014c8c  movsxd  r8, ecx
0x180014c8f  shl     r8, 3; Size
0x180014c93  lea     rdx, [rax+rbp*8]; Src
0x180014c97  lea     rcx, [rdx+8]; void *
0x180014c9b  call    memmove_0
0x180014ca0  mov     rax, [rsi+8]
0x180014ca4  xor     ecx, ecx
0x180014ca6  mov     [rax+rbx*8], rcx
0x180014caa  mov     rax, [rsi+8]
0x180014cae  mov     [rax+rbx*8], r14
0x180014cb2  inc     dword ptr [rsi+4]
0x180014cb5  xor     edi, edi
0x180014cb7  mov     ecx, edi
0x180014cb9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180014cbe  mov     rbx, [rsp+38h+arg_8]
0x180014cc3  mov     eax, edi
0x180014cc5  mov     rbp, [rsp+38h+arg_10]
0x180014cca  add     rsp, 20h
0x180014cce  pop     r14
0x180014cd0  pop     rdi
0x180014cd1  pop     rsi
0x180014cd2  retn
```
