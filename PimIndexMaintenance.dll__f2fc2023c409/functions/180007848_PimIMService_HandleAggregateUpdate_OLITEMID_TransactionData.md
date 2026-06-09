# PimIMService::HandleAggregateUpdate(OLITEMID *,TransactionData *)

- ea: `0x180007848`
- end: `0x180007962`
- name: `?HandleAggregateUpdate@PimIMService@@AEAAJPEAUOLITEMID@@PEAUTransactionData@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, struct OLITEMID *, struct TransactionData *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000bb20`

## callees

- `0x180002da8`
- `0x180007848`
- `0x18000c790`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800078a9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007914`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::HandleAggregateUpdate(
        PimIMService *this,
        struct OLITEMID *a2,
        struct TransactionData *a3)
{
  __int64 v4; // xmm0_8
  __int64 v5; // rax
  int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // edi
  __int64 (__fastcall *v11)(PimIMService *, __int64, struct TransactionData *, __int64 *); // rax
  int v12; // ebx
  __int64 v13; // r9
  unsigned int v14; // [rsp+30h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-18h]

  v4 = *(_QWORD *)a2;
  v16 = *((_DWORD *)a2 + 2);
  v5 = *(_QWORD *)this;
  v15 = v4;
  v14 = 0;
  v7 = (*(__int64 (__fastcall **)(PimIMService *, __int64 *, unsigned int *))(v5 + 184))(this, &v15, &v14);
  v9 = v7;
  if ( v7 < 0 )
  {
    Log_HREvent(
      (unsigned int)v7,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2616);
    return v9;
  }
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x10) != 0 )
    McTemplateU0qq_EventWriteTransfer(v8, PIMIndex_RebuildIndexes_Aggregate_Oid, v16, v14);
  v11 = *(__int64 (__fastcall **)(PimIMService *, __int64, struct TransactionData *, __int64 *))(*(_QWORD *)this + 160LL);
  if ( v14 )
  {
    v12 = v11(this, 2, a3, &v15);
    if ( v12 < 0 )
    {
      v13 = 2636;
      goto LABEL_8;
    }
  }
  else
  {
    v12 = v11(this, 4, a3, &v15);
    if ( v12 < 0 )
    {
      v13 = 2627;
LABEL_8:
      Log_HREvent(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        v13);
      return (unsigned int)v12;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007848  mov     r11, rsp
0x18000784b  mov     [r11+10h], rbx
0x18000784f  mov     [r11+20h], rsi
0x180007853  push    rdi
0x180007854  sub     rsp, 50h
0x180007858  mov     rax, cs:__security_cookie
0x18000785f  xor     rax, rsp
0x180007862  mov     [rsp+58h+var_10], rax
0x180007867  mov     eax, [rdx+8]
0x18000786a  mov     rsi, r8
0x18000786d  movsd   xmm0, qword ptr [rdx]
0x180007871  lea     r8, [r11-28h]
0x180007875  mov     [rsp+58h+var_18], eax
0x180007879  lea     rdx, [r11-20h]
0x18000787d  mov     rax, [rcx]
0x180007880  mov     rbx, rcx
0x180007883  movsd   [rsp+58h+var_20], xmm0
0x180007889  mov     [rsp+58h+var_28], 0
0x180007891  mov     rax, [rax+0B8h]
0x180007898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000789d  mov     edi, eax
0x18000789f  test    eax, eax
0x1800078a1  jns     short loc_1800078C3
0x1800078a3  mov     r9d, 0A38h
0x1800078a9  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800078b0  mov     edx, 1
0x1800078b5  mov     ecx, eax
0x1800078b7  call    Log_HREvent
0x1800078bc  mov     eax, edi
0x1800078be  jmp     loc_180007945
0x1800078c3  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 10h
0x1800078ca  jz      short loc_1800078E2
0x1800078cc  mov     r9d, [rsp+58h+var_28]
0x1800078d1  lea     rdx, PIMIndex_RebuildIndexes_Aggregate_Oid
0x1800078d8  mov     r8d, [rsp+58h+var_18]
0x1800078dd  call    McTemplateU0qq_EventWriteTransfer
0x1800078e2  cmp     [rsp+58h+var_28], 0
0x1800078e7  lea     r9, [rsp+58h+var_20]
0x1800078ec  mov     rax, [rbx]
0x1800078ef  mov     r8, rsi
0x1800078f2  mov     rcx, rbx
0x1800078f5  mov     rax, [rax+0A0h]
0x1800078fc  jnz     short loc_18000792B
0x1800078fe  mov     edx, 4
0x180007903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007908  mov     ebx, eax
0x18000790a  test    eax, eax
0x18000790c  jns     short loc_180007943
0x18000790e  mov     r9d, 0A43h
0x180007914  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000791b  mov     edx, 1
0x180007920  mov     ecx, ebx
0x180007922  call    Log_HREvent
0x180007927  mov     eax, ebx
0x180007929  jmp     short loc_180007945
0x18000792b  mov     edx, 2
0x180007930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007935  mov     ebx, eax
0x180007937  test    eax, eax
0x180007939  jns     short loc_180007943
0x18000793b  mov     r9d, 0A4Ch
0x180007941  jmp     short loc_180007914
0x180007943  xor     eax, eax
0x180007945  mov     rcx, [rsp+58h+var_10]
0x18000794a  xor     rcx, rsp; StackCookie
0x18000794d  call    __security_check_cookie
0x180007952  mov     rbx, [rsp+58h+arg_8]
0x180007957  mov     rsi, [rsp+58h+arg_18]
0x18000795c  add     rsp, 50h
0x180007960  pop     rdi
0x180007961  retn
```
