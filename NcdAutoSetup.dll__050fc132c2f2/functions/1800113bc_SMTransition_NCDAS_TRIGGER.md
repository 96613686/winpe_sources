# SMTransition(NCDAS_TRIGGER)

- ea: `0x1800113bc`
- end: `0x180011748`
- name: `?SMTransition@@YAJW4NCDAS_TRIGGER@@@Z`
- size: `908`
- prototype: `__int64 __fastcall(int)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c6e8`
- `0x18000cc24`
- `0x18000dee0`
- `0x180011750`
- `0x180012110`
- `0x1800123a0`
- `0x180012a40`

## callees

- `0x18000a644`
- `0x18000a66c`
- `0x18000a6cc`
- `0x18000a778`
- `0x180010fe4`
- `0x1800113bc`
- `0x180011e40`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011474`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011474`

## pseudocode

```c
__int64 __fastcall SMTransition(int a1)
{
  __int64 v1; // rdi
  _QWORD *v2; // rcx
  __int64 v3; // rbp
  int v4; // eax
  __int64 v5; // rsi
  int v6; // ebx
  __int64 (*v7)(void); // rsi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  bool v10; // zf
  __int64 (*v11)(void); // rsi
  __int64 (*v13)(void); // [rsp+68h] [rbp+10h] BYREF

  v1 = a1;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v13 = 0;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_S(v2[2], 33, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids, (&g_strTriggerName)[v1]);
    v2 = WPP_GLOBAL_Control;
  }
  if ( (int)v1 >= 6 )
  {
    v6 = -2147024809;
    goto LABEL_57;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_(v2[2], 34, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
  EnterCriticalSection(&g_StateMachine);
  v3 = dword_18001ADA8;
  v4 = SMGetNextState((unsigned int)v1, &v13);
  v5 = v4;
  if ( v4 == 5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)&WPP_d77279752c2730a2c88f617b9d74e821_Traceguids,
        (unsigned int)(&g_strTriggerName)[v1],
        (__int64)(&g_strStateName)[dword_18001ADA8]);
    v6 = -2147019873;
    goto LABEL_53;
  }
  v6 = 0;
  if ( v4 != (_DWORD)v3 )
  {
    if ( !(&g_StateExitFn)[v3] )
      goto LABEL_36;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids,
        (&g_strStateName)[v3]);
    v6 = ((__int64 (__fastcall *)(_QWORD))(&g_StateExitFn)[v3])((unsigned int)v1);
    if ( v6 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v9 = 40;
    }
    else
    {
LABEL_36:
      v10 = (&g_StateEntryFn)[v5] == 0;
      dword_18001ADA8 = v5;
      if ( v10 )
        goto LABEL_44;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids,
          (&g_strStateName)[v5]);
      v6 = ((__int64 (__fastcall *)(_QWORD))(&g_StateEntryFn)[v5])((unsigned int)v1);
      if ( v6 >= 0 )
      {
LABEL_44:
        v11 = v13;
        if ( !v13 )
          goto LABEL_53;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids,
            (&g_strTriggerName)[v1]);
        v6 = v11();
        if ( v6 >= 0 )
          goto LABEL_53;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_53;
        v9 = 44;
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_53;
        v9 = 42;
      }
    }
    goto LABEL_52;
  }
  v7 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)&WPP_d77279752c2730a2c88f617b9d74e821_Traceguids,
        (unsigned int)(&g_strTriggerName)[v1],
        (__int64)(&g_strStateName)[v3]);
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids,
      (&g_strTriggerName)[v1]);
  v6 = v7();
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = 37;
LABEL_52:
      WPP_SF_d(v8[2], v9, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
    }
  }
LABEL_53:
  LeaveCriticalSection(&g_StateMachine);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
LABEL_57:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 46, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800113bc  mov     [rsp+arg_0], rbx
0x1800113c1  mov     [rsp+arg_10], rbp
0x1800113c6  push    rsi
0x1800113c7  push    rdi
0x1800113c8  push    r13
0x1800113ca  push    r14
0x1800113cc  push    r15
0x1800113ce  sub     rsp, 30h
0x1800113d2  movsxd  rdi, ecx
0x1800113d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113dc  lea     r14, WPP_GLOBAL_Control
0x1800113e3  lea     r15, WPP_d77279752c2730a2c88f617b9d74e821_Traceguids
0x1800113ea  cmp     rcx, r14
0x1800113ed  jz      short loc_18001140D
0x1800113ef  test    byte ptr [rcx+1Ch], 20h
0x1800113f3  jz      short loc_18001140D
0x1800113f5  mov     rcx, [rcx+10h]
0x1800113f9  mov     edx, 20h ; ' '
0x1800113fe  mov     r8, r15
0x180011401  call    WPP_SF_
0x180011406  mov     rcx, cs:WPP_GLOBAL_Control
0x18001140d  mov     [rsp+58h+arg_8], 0
0x180011416  lea     r13, cs:180000000h
0x18001141d  cmp     rcx, r14
0x180011420  jz      short loc_180011448
0x180011422  test    byte ptr [rcx+1Ch], 8
0x180011426  jz      short loc_180011448
0x180011428  mov     r9, ds:rva ?g_strTriggerName@@3PAPEAGA[r13+rdi*8]; ushort * near * g_strTriggerName ...
0x180011430  mov     edx, 21h ; '!'
0x180011435  mov     rcx, [rcx+10h]
0x180011439  mov     r8, r15
0x18001143c  call    WPP_SF_S
0x180011441  mov     rcx, cs:WPP_GLOBAL_Control
0x180011448  cmp     edi, 6
0x18001144b  jge     loc_18001170E
0x180011451  cmp     rcx, r14
0x180011454  jz      short loc_18001146D
0x180011456  test    byte ptr [rcx+1Ch], 8
0x18001145a  jz      short loc_18001146D
0x18001145c  mov     rcx, [rcx+10h]
0x180011460  mov     edx, 22h ; '"'
0x180011465  mov     r8, r15
0x180011468  call    WPP_SF_
0x18001146d  lea     rcx, ?g_StateMachine@@3USTATE_MACHINE@@A; lpCriticalSection
0x180011474  call    cs:__imp_EnterCriticalSection
0x18001147a  movsxd  rbp, cs:dword_18001ADA8
0x180011481  lea     rdx, [rsp+58h+arg_8]
0x180011486  mov     ecx, edi
0x180011488  call    ?SMGetNextState@@YA?AW4NCDAS_STATE@@W4NCDAS_TRIGGER@@PEAP6AJXZ@Z; SMGetNextState(NCDAS_TRIGGER,long (**)(void))
0x18001148d  movsxd  rsi, eax
0x180011490  cmp     esi, 5
0x180011493  jnz     short loc_1800114DC
0x180011495  mov     rcx, cs:WPP_GLOBAL_Control
0x18001149c  cmp     rcx, r14
0x18001149f  jz      short loc_1800114D2
0x1800114a1  test    byte ptr [rcx+1Ch], 2
0x1800114a5  jz      short loc_1800114D2
0x1800114a7  movsxd  rax, cs:dword_18001ADA8
0x1800114ae  lea     edx, [rsi+1Eh]
0x1800114b1  mov     r9, ds:rva ?g_strTriggerName@@3PAPEAGA[r13+rdi*8]; ushort * near * g_strTriggerName ...
0x1800114b9  mov     r8, r15
0x1800114bc  mov     rcx, [rcx+10h]
0x1800114c0  mov     rax, ds:rva ?g_strStateName@@3PAPEAGA[r13+rax*8]; ushort * near * g_strStateName ...
0x1800114c8  mov     [rsp+58h+var_38], rax
0x1800114cd  call    WPP_SF_SS
0x1800114d2  mov     ebx, 8007139Fh
0x1800114d7  jmp     loc_1800116D5
0x1800114dc  xor     ebx, ebx
0x1800114de  cmp     esi, ebp
0x1800114e0  jnz     loc_180011594
0x1800114e6  mov     rsi, [rsp+58h+arg_8]
0x1800114eb  test    rsi, rsi
0x1800114ee  jz      short loc_18001154F
0x1800114f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114f7  cmp     rcx, r14
0x1800114fa  jz      short loc_180011519
0x1800114fc  test    byte ptr [rcx+1Ch], 8
0x180011500  jz      short loc_180011519
0x180011502  mov     r9, ds:rva ?g_strTriggerName@@3PAPEAGA[r13+rdi*8]; ushort * near * g_strTriggerName ...
0x18001150a  lea     edx, [rbx+24h]
0x18001150d  mov     rcx, [rcx+10h]
0x180011511  mov     r8, r15
0x180011514  call    WPP_SF_S
0x180011519  mov     rax, rsi
0x18001151c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011521  mov     ebx, eax
0x180011523  test    eax, eax
0x180011525  jns     loc_1800116D5
0x18001152b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011532  cmp     rcx, r14
0x180011535  jz      loc_1800116D5
0x18001153b  test    byte ptr [rcx+1Ch], 2
0x18001153f  jz      loc_1800116D5
0x180011545  mov     edx, 25h ; '%'
0x18001154a  jmp     loc_1800116C6
0x18001154f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011556  cmp     rcx, r14
0x180011559  jz      loc_1800116D5
0x18001155f  test    byte ptr [rcx+1Ch], 8
0x180011563  jz      loc_1800116D5
0x180011569  mov     rax, ds:rva ?g_strStateName@@3PAPEAGA[r13+rbp*8]; ushort * near * g_strStateName ...
0x180011571  mov     edx, 26h ; '&'
0x180011576  mov     r9, ds:rva ?g_strTriggerName@@3PAPEAGA[r13+rdi*8]; ushort * near * g_strTriggerName ...
0x18001157e  mov     r8, r15
0x180011581  mov     rcx, [rcx+10h]
0x180011585  mov     [rsp+58h+var_38], rax
0x18001158a  call    WPP_SF_SS
0x18001158f  jmp     loc_1800116D5
0x180011594  cmp     ds:rva ?g_StateExitFn@@3PAP6AJW4NCDAS_TRIGGER@@@ZA[r13+rbp*8], rbx; long (*near * g_StateExitFn)(NCDAS_TRIGGER) ...
0x18001159c  jz      short loc_180011602
0x18001159e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115a5  cmp     rcx, r14
0x1800115a8  jz      short loc_1800115C9
0x1800115aa  test    byte ptr [rcx+1Ch], 8
0x1800115ae  jz      short loc_1800115C9
0x1800115b0  mov     r9, ds:rva ?g_strStateName@@3PAPEAGA[r13+rbp*8]; ushort * near * g_strStateName ...
0x1800115b8  mov     edx, 27h ; '''
0x1800115bd  mov     rcx, [rcx+10h]
0x1800115c1  mov     r8, r15
0x1800115c4  call    WPP_SF_S
0x1800115c9  mov     rax, ds:(?g_StateExitFn@@3PAP6AJW4NCDAS_TRIGGER@@@ZA - 180000000h)[r13+rbp*8]; long (*near * g_StateExitFn)(NCDAS_TRIGGER)
0x1800115d1  mov     ecx, edi
0x1800115d3  call    _guard_dispatch_icall$thunk$10345483385596137414; StateExitFnWaitingForStart(NCDAS_TRIGGER) ...
0x1800115d8  mov     ebx, eax
0x1800115da  test    eax, eax
0x1800115dc  jns     short loc_180011602
0x1800115de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115e5  cmp     rcx, r14
0x1800115e8  jz      loc_1800116D5
0x1800115ee  test    byte ptr [rcx+1Ch], 2
0x1800115f2  jz      loc_1800116D5
0x1800115f8  mov     edx, 28h ; '('
0x1800115fd  jmp     loc_1800116C6
0x180011602  cmp     ds:rva ?g_StateEntryFn@@3PAP6AJW4NCDAS_TRIGGER@@@ZA[r13+rsi*8], 0; long (*near * g_StateEntryFn)(NCDAS_TRIGGER) ...
0x18001160b  mov     cs:dword_18001ADA8, esi
0x180011611  jz      short loc_18001166C
0x180011613  mov     rcx, cs:WPP_GLOBAL_Control
0x18001161a  cmp     rcx, r14
0x18001161d  jz      short loc_18001163E
0x18001161f  test    byte ptr [rcx+1Ch], 8
0x180011623  jz      short loc_18001163E
0x180011625  mov     r9, ds:rva ?g_strStateName@@3PAPEAGA[r13+rsi*8]; ushort * near * g_strStateName ...
0x18001162d  mov     edx, 29h ; ')'
0x180011632  mov     rcx, [rcx+10h]
0x180011636  mov     r8, r15
0x180011639  call    WPP_SF_S
0x18001163e  mov     rax, ds:rva ?g_StateEntryFn@@3PAP6AJW4NCDAS_TRIGGER@@@ZA[r13+rsi*8]; long (*near * g_StateEntryFn)(NCDAS_TRIGGER) ...
0x180011646  mov     ecx, edi
0x180011648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001164d  mov     ebx, eax
0x18001164f  test    eax, eax
0x180011651  jns     short loc_18001166C
0x180011653  mov     rcx, cs:WPP_GLOBAL_Control
0x18001165a  cmp     rcx, r14
0x18001165d  jz      short loc_1800116D5
0x18001165f  test    byte ptr [rcx+1Ch], 2
0x180011663  jz      short loc_1800116D5
0x180011665  mov     edx, 2Ah ; '*'
0x18001166a  jmp     short loc_1800116C6
0x18001166c  mov     rsi, [rsp+58h+arg_8]
0x180011671  test    rsi, rsi
0x180011674  jz      short loc_1800116D5
0x180011676  mov     rcx, cs:WPP_GLOBAL_Control
0x18001167d  cmp     rcx, r14
0x180011680  jz      short loc_1800116A1
0x180011682  test    byte ptr [rcx+1Ch], 8
0x180011686  jz      short loc_1800116A1
0x180011688  mov     r9, ds:rva ?g_strTriggerName@@3PAPEAGA[r13+rdi*8]; ushort * near * g_strTriggerName ...
0x180011690  mov     edx, 2Bh ; '+'
0x180011695  mov     rcx, [rcx+10h]
0x180011699  mov     r8, r15
0x18001169c  call    WPP_SF_S
0x1800116a1  mov     rax, rsi
0x1800116a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a9  mov     ebx, eax
0x1800116ab  test    eax, eax
0x1800116ad  jns     short loc_1800116D5
0x1800116af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116b6  cmp     rcx, r14
0x1800116b9  jz      short loc_1800116D5
0x1800116bb  test    byte ptr [rcx+1Ch], 2
0x1800116bf  jz      short loc_1800116D5
0x1800116c1  mov     edx, 2Ch ; ','
0x1800116c6  mov     rcx, [rcx+10h]
0x1800116ca  mov     r9d, eax
0x1800116cd  mov     r8, r15
0x1800116d0  call    WPP_SF_d
0x1800116d5  lea     rcx, ?g_StateMachine@@3USTATE_MACHINE@@A; lpCriticalSection
0x1800116dc  call    cs:__imp_LeaveCriticalSection
0x1800116e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116e9  cmp     rcx, r14
0x1800116ec  jz      short loc_18001172F
0x1800116ee  test    byte ptr [rcx+1Ch], 8
0x1800116f2  jz      short loc_180011713
0x1800116f4  mov     rcx, [rcx+10h]
0x1800116f8  mov     edx, 2Dh ; '-'
0x1800116fd  mov     r8, r15
0x180011700  call    WPP_SF_
0x180011705  mov     rcx, cs:WPP_GLOBAL_Control
0x18001170c  jmp     short loc_180011713
0x18001170e  mov     ebx, 80070057h
0x180011713  cmp     rcx, r14
0x180011716  jz      short loc_18001172F
0x180011718  test    byte ptr [rcx+1Ch], 20h
0x18001171c  jz      short loc_18001172F
0x18001171e  mov     rcx, [rcx+10h]
0x180011722  mov     edx, 2Eh ; '.'
0x180011727  mov     r8, r15
0x18001172a  call    WPP_SF_
0x18001172f  mov     rbp, [rsp+58h+arg_10]
0x180011734  mov     eax, ebx
0x180011736  mov     rbx, [rsp+58h+arg_0]
0x18001173b  add     rsp, 30h
0x18001173f  pop     r15
0x180011741  pop     r14
0x180011743  pop     r13
0x180011745  pop     rdi
0x180011746  pop     rsi
0x180011747  retn
```
