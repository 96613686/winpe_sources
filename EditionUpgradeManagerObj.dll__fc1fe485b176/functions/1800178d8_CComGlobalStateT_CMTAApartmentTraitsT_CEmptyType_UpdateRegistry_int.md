# CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::UpdateRegistry(int)

- ea: `0x1800178d8`
- end: `0x180017a39`
- name: `?UpdateRegistry@?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@QEAAJH@Z`
- size: `353`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017cb0`
- `0x180017cf0`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x1800156d0`
- `0x180015864`
- `0x180016078`
- `0x180016bcc`
- `0x180016d34`
- `0x1800178d8`

## pseudocode

```c
__int64 __fastcall CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::UpdateRegistry(__int64 a1, int a2)
{
  void *v2; // rsi
  int v3; // ebx
  __int64 v4; // rdi
  int v6; // r14d
  unsigned int *v7; // rcx
  int v8; // eax
  GUID *v9; // rcx
  int v10; // eax
  int v11; // r13d
  __int64 *v12; // rcx
  int v13; // eax
  int v14; // r12d
  int v15; // ecx
  __int64 v16; // rdi
  int *v17; // rcx
  int v18; // eax
  GUID *v19; // rcx

  v2 = CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState;
  v3 = 0;
  v4 = 0;
  v6 = *((_DWORD *)CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
       + 3);
  if ( v6 > 0 )
  {
    while ( 1 )
    {
      v7 = *(unsigned int **)(*((_QWORD *)v2 + 2) + 8 * v4);
      v8 = a2
         ? CComObjectRegistrationT<CEmptyType>::Register(v7)
         : CComObjectRegistrationT<CEmptyType>::Unregister((int *)v7);
      v3 = v8;
      if ( v8 < 0 )
        break;
      v4 = (unsigned int)(v4 + 1);
      if ( (int)v4 >= v6 )
        goto LABEL_9;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
  }
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v3 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
    goto LABEL_39;
  }
  v9 = (GUID *)*((_QWORD *)v2 + 6);
  if ( v9 )
  {
    v10 = CComTypeLibraryRegistrationT<CEmptyType>::Register(v9, a2);
    v3 = v10;
    if ( v10 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
  }
  else
  {
    v3 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v3 >= 0 )
  {
    v12 = (__int64 *)*((_QWORD *)v2 + 5);
    if ( v12 )
    {
      if ( a2 )
        v13 = CComAppIdRegistrationT<CEmptyType>::Register(v12);
      else
        v13 = CComAppIdRegistrationT<CEmptyType>::Unregister(v12);
      v3 = v13;
      if ( v13 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
    }
    else
    {
      v3 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
    if ( v3 >= 0 )
      goto LABEL_39;
    v11 = 1;
  }
  else
  {
    v11 = 0;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
  v14 = *((_DWORD *)v2 + 3);
  v15 = 0;
  v16 = 0;
  if ( v14 > 0 )
  {
    while ( 1 )
    {
      v17 = *(int **)(*((_QWORD *)v2 + 2) + 8 * v16);
      v18 = a2
          ? CComObjectRegistrationT<CEmptyType>::Unregister(v17)
          : CComObjectRegistrationT<CEmptyType>::Register((unsigned int *)v17);
      v15 = v18;
      if ( v18 < 0 )
        break;
      v16 = (unsigned int)(v16 + 1);
      if ( (int)v16 >= v14 )
        goto LABEL_34;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
  }
LABEL_34:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
  if ( v11 )
  {
    v19 = (GUID *)*((_QWORD *)v2 + 6);
    if ( v19 )
    {
      LODWORD(v19) = CComTypeLibraryRegistrationT<CEmptyType>::Register(v19, a2 == 0);
      if ( (int)v19 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((int)v19);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((int)v19);
  }
LABEL_39:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800178d8  push    rbx
0x1800178da  push    rbp
0x1800178db  push    rsi
0x1800178dc  push    rdi
0x1800178dd  push    r12
0x1800178df  push    r13
0x1800178e1  push    r14
0x1800178e3  push    r15
0x1800178e5  sub     rsp, 28h
0x1800178e9  mov     rsi, cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x1800178f0  xor     ebx, ebx
0x1800178f2  xor     edi, edi
0x1800178f4  mov     ebp, edx
0x1800178f6  mov     r14d, [rsi+0Ch]
0x1800178fa  test    r14d, r14d
0x1800178fd  jle     short loc_18001792D
0x1800178ff  mov     rax, [rsi+10h]
0x180017903  mov     rcx, [rax+rdi*8]
0x180017907  test    ebp, ebp
0x180017909  jz      short loc_180017912
0x18001790b  call    ?Register@?$CComObjectRegistrationT@VCEmptyType@@@@QEAAJXZ; CComObjectRegistrationT<CEmptyType>::Register(void)
0x180017910  jmp     short loc_180017917
0x180017912  call    ?Unregister@?$CComObjectRegistrationT@VCEmptyType@@@@QEAAJXZ; CComObjectRegistrationT<CEmptyType>::Unregister(void)
0x180017917  mov     ebx, eax
0x180017919  test    eax, eax
0x18001791b  js      short loc_180017926
0x18001791d  inc     edi
0x18001791f  cmp     edi, r14d
0x180017922  jl      short loc_1800178FF
0x180017924  jmp     short loc_18001792D
0x180017926  mov     ecx, eax
0x180017928  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001792d  mov     ecx, ebx
0x18001792f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017934  test    ebx, ebx
0x180017936  jns     short loc_180017944
0x180017938  mov     ecx, ebx
0x18001793a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001793f  jmp     loc_180017A1F
0x180017944  mov     rcx, [rsi+30h]; libID
0x180017948  test    rcx, rcx
0x18001794b  jnz     short loc_180017951
0x18001794d  xor     ebx, ebx
0x18001794f  jmp     short loc_180017965
0x180017951  mov     edx, ebp
0x180017953  call    ?Register@?$CComTypeLibraryRegistrationT@VCEmptyType@@@@QEAAJH@Z; CComTypeLibraryRegistrationT<CEmptyType>::Register(int)
0x180017958  mov     ebx, eax
0x18001795a  test    eax, eax
0x18001795c  jns     short loc_180017965
0x18001795e  mov     ecx, eax
0x180017960  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017965  mov     ecx, ebx
0x180017967  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001796c  test    ebx, ebx
0x18001796e  jns     short loc_180017975
0x180017970  xor     r13d, r13d
0x180017973  jmp     short loc_1800179B0
0x180017975  mov     rcx, [rsi+28h]
0x180017979  test    rcx, rcx
0x18001797c  jnz     short loc_180017982
0x18001797e  xor     ebx, ebx
0x180017980  jmp     short loc_18001799F
0x180017982  test    ebp, ebp
0x180017984  jz      short loc_18001798D
0x180017986  call    ?Register@?$CComAppIdRegistrationT@VCEmptyType@@@@QEAAJXZ; CComAppIdRegistrationT<CEmptyType>::Register(void)
0x18001798b  jmp     short loc_180017992
0x18001798d  call    ?Unregister@?$CComAppIdRegistrationT@VCEmptyType@@@@QEAAJXZ; CComAppIdRegistrationT<CEmptyType>::Unregister(void)
0x180017992  mov     ebx, eax
0x180017994  test    eax, eax
0x180017996  jns     short loc_18001799F
0x180017998  mov     ecx, eax
0x18001799a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001799f  mov     ecx, ebx
0x1800179a1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800179a6  test    ebx, ebx
0x1800179a8  jns     short loc_180017A1F
0x1800179aa  mov     r13d, 1
0x1800179b0  mov     ecx, ebx
0x1800179b2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800179b7  mov     r12d, [rsi+0Ch]
0x1800179bb  xor     ecx, ecx
0x1800179bd  xor     edi, edi
0x1800179bf  test    r12d, r12d
0x1800179c2  jle     short loc_1800179F0
0x1800179c4  mov     rax, [rsi+10h]
0x1800179c8  mov     rcx, [rax+rdi*8]
0x1800179cc  test    ebp, ebp
0x1800179ce  jnz     short loc_1800179D7
0x1800179d0  call    ?Register@?$CComObjectRegistrationT@VCEmptyType@@@@QEAAJXZ; CComObjectRegistrationT<CEmptyType>::Register(void)
0x1800179d5  jmp     short loc_1800179DC
0x1800179d7  call    ?Unregister@?$CComObjectRegistrationT@VCEmptyType@@@@QEAAJXZ; CComObjectRegistrationT<CEmptyType>::Unregister(void)
0x1800179dc  mov     ecx, eax
0x1800179de  test    eax, eax
0x1800179e0  js      short loc_1800179EB
0x1800179e2  inc     edi
0x1800179e4  cmp     edi, r12d
0x1800179e7  jl      short loc_1800179C4
0x1800179e9  jmp     short loc_1800179F0
0x1800179eb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800179f0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800179f5  test    r13d, r13d
0x1800179f8  jz      short loc_180017A1F
0x1800179fa  mov     rcx, [rsi+30h]; libID
0x1800179fe  xor     edx, edx
0x180017a00  test    ebp, ebp
0x180017a02  setz    dl
0x180017a05  test    rcx, rcx
0x180017a08  jz      short loc_180017A1A
0x180017a0a  call    ?Register@?$CComTypeLibraryRegistrationT@VCEmptyType@@@@QEAAJH@Z; CComTypeLibraryRegistrationT<CEmptyType>::Register(int)
0x180017a0f  mov     ecx, eax
0x180017a11  test    eax, eax
0x180017a13  jns     short loc_180017A1A
0x180017a15  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017a1a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017a1f  mov     ecx, ebx
0x180017a21  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017a26  mov     eax, ebx
0x180017a28  add     rsp, 28h
0x180017a2c  pop     r15
0x180017a2e  pop     r14
0x180017a30  pop     r13
0x180017a32  pop     r12
0x180017a34  pop     rdi
0x180017a35  pop     rsi
0x180017a36  pop     rbp
0x180017a37  pop     rbx
0x180017a38  retn
```
