# AudioQueueClient_CompleteStreamTransferRequest

- ea: `0x1400114e0`
- end: `0x14001170e`
- name: `AudioQueueClient_CompleteStreamTransferRequest`
- size: `558`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002d1b0`
- `0x14002d220`
- `0x14002db70`
- `0x14002de78`
- `0x14002e1a0`
- `0x14002e300`

## callees

- `0x140001198`
- `0x1400114e0`
- `0x14001ae00`

## pseudocode

```c
bool __fastcall AudioQueueClient_CompleteStreamTransferRequest(__int64 a1, int a2, __int64 a3, char a4, __int64 a5)
{
  char v9; // di
  __int64 v10; // rsi
  int *v11; // rbx
  int v12; // eax
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  char v18; // [rsp+50h] [rbp-21h]
  int v19; // [rsp+54h] [rbp-1Dh] BYREF
  int v20; // [rsp+58h] [rbp-19h] BYREF
  int v21; // [rsp+5Ch] [rbp-15h] BYREF
  int v22; // [rsp+60h] [rbp-11h] BYREF
  __int64 v23; // [rsp+68h] [rbp-9h] BYREF
  __int64 v24; // [rsp+70h] [rbp-1h] BYREF
  _QWORD v25[9]; // [rsp+78h] [rbp+7h] BYREF

  v9 = 1;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          a1,
          off_1400223C8);
  v11 = *(int **)v10;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(
    WdfDriverGlobals,
    *(_QWORD *)(*(_QWORD *)v10 + 40LL));
  v18 = *(_BYTE *)(v10 + 20);
  if ( !v18 )
  {
    if ( !a4
      || (v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2048))(
                  WdfDriverGlobals,
                  a1),
          v12 >= 0)
      || v12 == -1073741536 && a2 == -1073741536 )
    {
      if ( a2 >= 0 && a5 )
      {
        *((_QWORD *)v11 + 2) = a5;
        *((_QWORD *)v11 + 1) = *(_QWORD *)(v10 + 8) + *(unsigned int *)(v10 + 16);
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 128))(
        WdfDriverGlobals,
        *(_QWORD *)(*(_QWORD *)v10 + 48LL),
        a1);
      *(_BYTE *)(v10 + 20) = 1;
    }
    else
    {
      v9 = 0;
    }
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2536))(
    WdfDriverGlobals,
    *(_QWORD *)(*(_QWORD *)v10 + 40LL));
  v19 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, int *, _QWORD))(WdfFunctions_01015 + 1224))(
    WdfDriverGlobals,
    *((_QWORD *)v11 + 3),
    &v19,
    0);
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 112))(
          WdfDriverGlobals,
          *(_QWORD *)(*(_QWORD *)v10 + 48LL));
  v16 = v13 + v19;
  v19 += v13;
  if ( !v18 && v9 )
  {
    if ( (unsigned int)dword_140022000 > 5 )
    {
      v21 = v19;
      v23 = *((_QWORD *)v11 + 1);
      v24 = *((_QWORD *)v11 + 2);
      v22 = *v11;
      v20 = a2;
      v25[0] = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)&dword_14001EEDC,
        v14,
        v15,
        (__int64)v25,
        (__int64)&v22,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v20);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
      WdfDriverGlobals,
      a1,
      (unsigned int)a2,
      a3);
    v16 = v19;
  }
  return v16 != 0;
}

```

## disassembly

```asm
0x1400114e0  push    rbp
0x1400114e2  push    rbx
0x1400114e3  push    rsi
0x1400114e4  push    rdi
0x1400114e5  push    r12
0x1400114e7  push    r13
0x1400114e9  push    r14
0x1400114eb  push    r15
0x1400114ed  lea     rbp, [rsp-17h]
0x1400114f2  sub     rsp, 88h
0x1400114f9  mov     rax, cs:WdfFunctions_01015
0x140011500  mov     r14d, edx
0x140011503  mov     r13, r8
0x140011506  mov     r15, rcx
0x140011509  mov     r8, cs:off_1400223C8
0x140011510  mov     rdx, rcx
0x140011513  mov     rcx, cs:WdfDriverGlobals
0x14001151a  mov     r12b, r9b
0x14001151d  mov     rax, [rax+650h]
0x140011524  mov     dil, 1
0x140011527  call    _guard_dispatch_icall
0x14001152c  mov     rcx, cs:WdfFunctions_01015
0x140011533  mov     rsi, rax
0x140011536  mov     rbx, [rax]
0x140011539  mov     rax, [rcx+9E0h]
0x140011540  mov     rcx, cs:WdfDriverGlobals
0x140011547  mov     rdx, [rbx+28h]
0x14001154b  call    _guard_dispatch_icall
0x140011550  mov     al, [rsi+14h]
0x140011553  mov     [rbp+4Fh+var_70], al
0x140011556  test    al, al
0x140011558  jnz     short loc_1400115D8
0x14001155a  test    r12b, r12b
0x14001155d  jz      short loc_140011593
0x14001155f  mov     rax, cs:WdfFunctions_01015
0x140011566  mov     rdx, r15
0x140011569  mov     rcx, cs:WdfDriverGlobals
0x140011570  mov     rax, [rax+800h]
0x140011577  call    _guard_dispatch_icall
0x14001157c  test    eax, eax
0x14001157e  jns     short loc_140011593
0x140011580  mov     ecx, 0C0000120h
0x140011585  cmp     eax, ecx
0x140011587  jnz     short loc_14001158E
0x140011589  cmp     r14d, ecx
0x14001158c  jz      short loc_140011593
0x14001158e  xor     dil, dil
0x140011591  jmp     short loc_1400115D8
0x140011593  test    r14d, r14d
0x140011596  js      short loc_1400115B0
0x140011598  mov     rax, [rbp+4Fh+arg_20]
0x14001159c  test    rax, rax
0x14001159f  jz      short loc_1400115B0
0x1400115a1  mov     [rbx+10h], rax
0x1400115a5  mov     eax, [rsi+10h]
0x1400115a8  add     rax, [rsi+8]
0x1400115ac  mov     [rbx+8], rax
0x1400115b0  mov     rdx, [rsi]
0x1400115b3  mov     r8, r15
0x1400115b6  mov     rax, cs:WdfFunctions_01015
0x1400115bd  mov     rcx, cs:WdfDriverGlobals
0x1400115c4  mov     rdx, [rdx+30h]
0x1400115c8  mov     rax, [rax+80h]
0x1400115cf  call    _guard_dispatch_icall
0x1400115d4  mov     [rsi+14h], dil
0x1400115d8  mov     rdx, [rsi]
0x1400115db  mov     rax, cs:WdfFunctions_01015
0x1400115e2  mov     rcx, cs:WdfDriverGlobals
0x1400115e9  mov     rdx, [rdx+28h]
0x1400115ed  mov     rax, [rax+9E8h]
0x1400115f4  call    _guard_dispatch_icall
0x1400115f9  mov     rax, cs:WdfFunctions_01015
0x140011600  lea     r8, [rbp+4Fh+var_6C]
0x140011604  mov     rcx, cs:WdfDriverGlobals
0x14001160b  xor     r9d, r9d
0x14001160e  mov     [rbp+4Fh+var_6C], 0
0x140011615  mov     rdx, [rbx+18h]
0x140011619  mov     rax, [rax+4C8h]
0x140011620  call    _guard_dispatch_icall
0x140011625  mov     rdx, [rsi]
0x140011628  mov     rax, cs:WdfFunctions_01015
0x14001162f  mov     rcx, cs:WdfDriverGlobals
0x140011636  mov     rdx, [rdx+30h]
0x14001163a  mov     rax, [rax+70h]
0x14001163e  call    _guard_dispatch_icall
0x140011643  mov     ecx, [rbp+4Fh+var_6C]
0x140011646  add     ecx, eax
0x140011648  cmp     [rbp+4Fh+var_70], 0
0x14001164c  mov     [rbp+4Fh+var_6C], ecx
0x14001164f  jnz     loc_1400116F4
0x140011655  test    dil, dil
0x140011658  jz      loc_1400116F4
0x14001165e  mov     eax, cs:dword_140022000
0x140011664  cmp     eax, 5
0x140011667  jbe     short loc_1400116CE
0x140011669  mov     eax, [rbp+4Fh+var_6C]
0x14001166c  lea     rdx, dword_14001EEDC
0x140011673  mov     [rbp+4Fh+var_64], eax
0x140011676  mov     rax, [rbx+8]
0x14001167a  mov     [rbp+4Fh+var_58], rax
0x14001167e  mov     rax, [rbx+10h]
0x140011682  mov     [rbp+4Fh+var_50], rax
0x140011686  mov     eax, [rbx]
0x140011688  mov     [rbp+4Fh+var_60], eax
0x14001168b  lea     rax, [rbp+4Fh+var_68]
0x14001168f  mov     [rsp+0C0h+var_78], rax
0x140011694  lea     rax, [rbp+4Fh+var_64]
0x140011698  mov     [rsp+0C0h+var_80], rax
0x14001169d  lea     rax, [rbp+4Fh+var_58]
0x1400116a1  mov     [rsp+0C0h+var_88], rax
0x1400116a6  lea     rax, [rbp+4Fh+var_50]
0x1400116aa  mov     [rsp+0C0h+var_90], rax
0x1400116af  lea     rax, [rbp+4Fh+var_60]
0x1400116b3  mov     [rsp+0C0h+var_98], rax
0x1400116b8  lea     rax, [rbp+4Fh+var_48]
0x1400116bc  mov     [rsp+0C0h+var_A0], rax
0x1400116c1  mov     [rbp+4Fh+var_68], r14d
0x1400116c5  mov     [rbp+4Fh+var_48], r15
0x1400116c9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400116ce  mov     rax, cs:WdfFunctions_01015
0x1400116d5  mov     r9, r13
0x1400116d8  mov     rcx, cs:WdfDriverGlobals
0x1400116df  mov     r8d, r14d
0x1400116e2  mov     rdx, r15
0x1400116e5  mov     rax, [rax+848h]
0x1400116ec  call    _guard_dispatch_icall
0x1400116f1  mov     ecx, [rbp+4Fh+var_6C]
0x1400116f4  test    ecx, ecx
0x1400116f6  setnz   al
0x1400116f9  add     rsp, 88h
0x140011700  pop     r15
0x140011702  pop     r14
0x140011704  pop     r13
0x140011706  pop     r12
0x140011708  pop     rdi
0x140011709  pop     rsi
0x14001170a  pop     rbx
0x14001170b  pop     rbp
0x14001170c  retn
```
