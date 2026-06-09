# CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(DP_COM<IPopupCommand> const &)

- ea: `0x18000a4c0`
- end: `0x18000a611`
- name: `?Append@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBV?$DP_COM@UIPopupCommand@@@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000a6d0`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000a2cc`
- `0x18000a340`
- `0x18000a4c0`
- `0x18000af78`
- `0x180022968`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // rbp
  unsigned int v5; // edi
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // edi
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // r8d
  __int64 v15; // rbx
  __int64 v16; // rdi
  __int64 v17; // rbp
  __int64 v18; // rcx
  int v20; // [rsp+40h] [rbp+8h] BYREF
  int v21; // [rsp+50h] [rbp+18h] BYREF

  v2 = *(int *)(a1 + 4);
  v21 = 0;
  if ( (int)v2 < 0 )
  {
    v5 = -2147418113;
    v6 = 2147549183LL;
LABEL_5:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_29;
  }
  v7 = SafeAdd<int>(v2, (__int64)a2, &v21);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = (unsigned int)v7;
    goto LABEL_5;
  }
  v9 = *(_DWORD *)a1;
  if ( *(int *)a1 >= 0 )
  {
    if ( v21 <= v9 )
    {
      v10 = 0;
      goto LABEL_22;
    }
    v20 = *(_DWORD *)a1;
    do
    {
      if ( v9 )
      {
        v12 = SafeMul<int>(v9, v8, &v20);
        v10 = v12;
        if ( v12 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
        v9 = v20;
      }
      else
      {
        v9 = 32;
        v10 = 0;
        v20 = 32;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
      if ( v10 < 0 )
      {
        v11 = (unsigned int)v10;
        goto LABEL_21;
      }
    }
    while ( v9 < v21 );
    v13 = CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::SetSize(
            a1,
            (unsigned int)v9);
    v10 = v13;
    if ( v13 >= 0 )
      goto LABEL_22;
    v11 = (unsigned int)v13;
  }
  else
  {
    v10 = -2147418113;
    v11 = 2147549183LL;
  }
LABEL_21:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v10 < 0 )
  {
    v5 = v10;
    v6 = (unsigned int)v10;
    goto LABEL_5;
  }
  v14 = *(_DWORD *)(a1 + 4);
  if ( (int)v2 < v14 )
    memmove_0(
      (void *)(*(_QWORD *)(a1 + 8) + 8 * v2 + 8),
      (const void *)(*(_QWORD *)(a1 + 8) + 8 * v2),
      8LL * (v14 - (int)v2));
  v15 = v2;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v2) = 0;
  v16 = *(_QWORD *)(a1 + 8);
  v17 = *a2;
  *a2 = 0;
  v18 = *(_QWORD *)(v16 + 8 * v15);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  *(_QWORD *)(v16 + 8 * v15) = v17;
  ++*(_DWORD *)(a1 + 4);
  v5 = 0;
LABEL_29:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18000a4c0  mov     [rsp+arg_8], rbx
0x18000a4c5  mov     [rsp+arg_18], rbp
0x18000a4ca  push    rsi
0x18000a4cb  push    rdi
0x18000a4cc  push    r14
0x18000a4ce  sub     rsp, 20h
0x18000a4d2  movsxd  rbp, dword ptr [rcx+4]
0x18000a4d6  mov     r14, rdx
0x18000a4d9  mov     [rsp+38h+arg_10], 0
0x18000a4e1  mov     rsi, rcx
0x18000a4e4  test    ebp, ebp
0x18000a4e6  jns     short loc_18000A4F1
0x18000a4e8  mov     edi, 8000FFFFh
0x18000a4ed  mov     ecx, edi
0x18000a4ef  jmp     short loc_18000A505
0x18000a4f1  lea     r8, [rsp+38h+arg_10]
0x18000a4f6  mov     ecx, ebp
0x18000a4f8  call    ??$SafeAdd@H@@YAJHHPEAH@Z; SafeAdd<int>(int,int,int *)
0x18000a4fd  mov     edi, eax
0x18000a4ff  test    eax, eax
0x18000a501  jns     short loc_18000A50F
0x18000a503  mov     ecx, eax
0x18000a505  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a50a  jmp     loc_18000A5F5
0x18000a50f  mov     edi, [rsi]
0x18000a511  test    edi, edi
0x18000a513  jns     short loc_18000A520
0x18000a515  mov     edi, 8000FFFFh
0x18000a51a  mov     ebx, edi
0x18000a51c  mov     ecx, edi
0x18000a51e  jmp     short loc_18000A583
0x18000a520  cmp     [rsp+38h+arg_10], edi
0x18000a524  jg      short loc_18000A52A
0x18000a526  xor     ebx, ebx
0x18000a528  jmp     short loc_18000A588
0x18000a52a  mov     [rsp+38h+arg_0], edi
0x18000a52e  test    edi, edi
0x18000a530  jnz     short loc_18000A53F
0x18000a532  mov     edi, 20h ; ' '
0x18000a537  xor     ebx, ebx
0x18000a539  mov     [rsp+38h+arg_0], edi
0x18000a53d  jmp     short loc_18000A55C
0x18000a53f  lea     r8, [rsp+38h+arg_0]
0x18000a544  mov     ecx, edi
0x18000a546  call    ??$SafeMul@H@@YAJHHPEAH@Z; SafeMul<int>(int,int,int *)
0x18000a54b  mov     ebx, eax
0x18000a54d  test    eax, eax
0x18000a54f  jns     short loc_18000A558
0x18000a551  mov     ecx, eax
0x18000a553  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a558  mov     edi, [rsp+38h+arg_0]
0x18000a55c  mov     ecx, ebx
0x18000a55e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a563  test    ebx, ebx
0x18000a565  js      short loc_18000A581
0x18000a567  cmp     edi, [rsp+38h+arg_10]
0x18000a56b  jl      short loc_18000A52E
0x18000a56d  mov     edx, edi
0x18000a56f  mov     rcx, rsi
0x18000a572  call    ?SetSize@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18000a577  mov     ebx, eax
0x18000a579  test    eax, eax
0x18000a57b  jns     short loc_18000A588
0x18000a57d  mov     ecx, eax
0x18000a57f  jmp     short loc_18000A583
0x18000a581  mov     ecx, ebx
0x18000a583  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a588  mov     ecx, ebx
0x18000a58a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a58f  test    ebx, ebx
0x18000a591  jns     short loc_18000A59C
0x18000a593  mov     edi, ebx
0x18000a595  mov     ecx, ebx
0x18000a597  jmp     loc_18000A505
0x18000a59c  mov     r8d, [rsi+4]
0x18000a5a0  cmp     ebp, r8d
0x18000a5a3  jge     short loc_18000A5C0
0x18000a5a5  mov     rcx, [rsi+8]
0x18000a5a9  sub     r8d, ebp
0x18000a5ac  movsxd  r8, r8d
0x18000a5af  shl     r8, 3; Size
0x18000a5b3  lea     rdx, [rcx+rbp*8]; Src
0x18000a5b7  lea     rcx, [rdx+8]; void *
0x18000a5bb  call    memmove_0
0x18000a5c0  mov     rax, [rsi+8]
0x18000a5c4  xor     ecx, ecx
0x18000a5c6  mov     rbx, rbp
0x18000a5c9  mov     [rax+rbp*8], rcx
0x18000a5cd  mov     rdi, [rsi+8]
0x18000a5d1  mov     rbp, [r14]
0x18000a5d4  mov     [r14], rcx
0x18000a5d7  mov     rcx, [rdi+rbx*8]
0x18000a5db  test    rcx, rcx
0x18000a5de  jz      short loc_18000A5EC
0x18000a5e0  mov     rax, [rcx]
0x18000a5e3  mov     rax, [rax+10h]
0x18000a5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ec  mov     [rdi+rbx*8], rbp
0x18000a5f0  inc     dword ptr [rsi+4]
0x18000a5f3  xor     edi, edi
0x18000a5f5  mov     ecx, edi
0x18000a5f7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a5fc  mov     rbx, [rsp+38h+arg_8]
0x18000a601  mov     eax, edi
0x18000a603  mov     rbp, [rsp+38h+arg_18]
0x18000a608  add     rsp, 20h
0x18000a60c  pop     r14
0x18000a60e  pop     rdi
0x18000a60f  pop     rsi
0x18000a610  retn
```
