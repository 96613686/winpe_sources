# PimIMService::TranslateChange(_SQLCEPROPVAL,PO_CHANGETYPE &,USOID &,_SQLCEPROPVAL,PO_CHANGETYPE &,USOID &)

- ea: `0x18000a780`
- end: `0x18000a991`
- name: `?TranslateChange@PimIMService@@UEAAJU_SQLCEPROPVAL@@AEAW4PO_CHANGETYPE@@AEAUUSOID@@012@Z`
- size: `529`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002da8`
- `0x1800067c0`
- `0x180006bac`
- `0x18000a780`
- `0x18000c5b8`
- `0x180022010`

## string_xrefs

- `0x18000a7e8`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000a87c`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::TranslateChange(
        PimIMService *a1,
        __int64 a2,
        _DWORD *a3,
        struct USOID *a4,
        __int64 a5,
        PimIMService *a6,
        struct USOID *a7)
{
  int *v7; // rdi
  __int16 v8; // ax
  struct IPOutlookApp3 **v9; // rsi
  __int64 v13; // rbp
  _WORD *v14; // rbx
  int v15; // r12d
  int AggregateID; // ebx
  __int64 v17; // r9
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // r15d
  void *v22; // rax
  __int64 v23; // r8
  PimIMService *v24; // rcx
  int v25; // edx
  struct USOID *v26; // r9
  void *v27; // rax
  __int64 v28; // r8
  __int16 v29; // [rsp+78h] [rbp+10h]
  int v30; // [rsp+80h] [rbp+18h] BYREF

  v7 = (int *)(a2 + 8);
  *a3 = 0;
  v8 = *(_WORD *)(a2 + 6) & 0x300;
  v9 = (struct IPOutlookApp3 **)((char *)a1 + 216);
  v29 = v8;
  if ( v8 )
  {
    v13 = a5;
    v14 = (_WORD *)(a5 + 6);
    goto LABEL_18;
  }
  v15 = *v7;
  AggregateID = PimIMService::GetAggregateID(a1, *v7, *v9, a4);
  if ( AggregateID < 0 )
  {
    v17 = 2277;
LABEL_5:
    Log_HREvent(
      (unsigned int)AggregateID,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v17);
    return (unsigned int)AggregateID;
  }
  v13 = a5;
  v14 = (_WORD *)(a5 + 6);
  if ( (*(_WORD *)(a5 + 6) & 0x300) == 0 && *(_DWORD *)(a5 + 8) == v15 )
  {
    *a3 = 2;
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) == 0 )
      goto LABEL_17;
    goto LABEL_16;
  }
  v19 = *(_QWORD *)a1;
  v30 = 0;
  v20 = (*(__int64 (__fastcall **)(PimIMService *, struct USOID *, int *))(v19 + 184))(a1, a4, &v30);
  v21 = v20;
  if ( v20 < 0 )
  {
    Log_HREvent(
      (unsigned int)v20,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2291);
    return v21;
  }
  if ( v30 )
  {
    *a3 = 2;
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
    {
LABEL_16:
      v22 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v22, v23, 4, 0, -1);
    }
  }
  else
  {
    *a3 = 4;
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
      goto LABEL_16;
  }
LABEL_17:
  v8 = v29;
LABEL_18:
  v24 = a6;
  *(_DWORD *)a6 = 0;
  if ( (*v14 & 0x300) == 0 && (v8 || *(_DWORD *)(v13 + 8) != *v7) )
  {
    v25 = *(_DWORD *)(v13 + 8);
    v26 = a7;
    *(_DWORD *)v24 = 2;
    AggregateID = PimIMService::GetAggregateID(v24, v25, *v9, v26);
    if ( AggregateID < 0 )
    {
      v17 = 2319;
      goto LABEL_5;
    }
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
    {
      v27 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v27, v28, 4, 0, -1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a780  mov     [rsp+arg_0], rbx
0x18000a785  push    rbp
0x18000a786  push    rsi
0x18000a787  push    rdi
0x18000a788  push    r12
0x18000a78a  push    r13
0x18000a78c  push    r14
0x18000a78e  push    r15
0x18000a790  sub     rsp, 30h
0x18000a794  xor     r12d, r12d
0x18000a797  lea     rdi, [rdx+8]
0x18000a79b  mov     eax, 300h
0x18000a7a0  mov     [r8], r12d
0x18000a7a3  and     ax, [rdx+6]
0x18000a7a7  lea     rsi, [rcx+0D8h]
0x18000a7ae  mov     [rsp+68h+arg_8], eax
0x18000a7b2  mov     r13, r9
0x18000a7b5  mov     r14, r8
0x18000a7b8  mov     r15, rcx
0x18000a7bb  jz      short loc_18000A7CE
0x18000a7bd  mov     rbp, [rsp+68h+arg_20]
0x18000a7c5  lea     rbx, [rbp+6]
0x18000a7c9  jmp     loc_18000A8F7
0x18000a7ce  mov     r12d, [rdi]
0x18000a7d1  mov     edx, r12d; unsigned int
0x18000a7d4  mov     r8, [rsi]; struct IPOutlookApp3 *
0x18000a7d7  call    ?GetAggregateID@PimIMService@@AEAAJKPEAUIPOutlookApp3@@AEAUUSOID@@@Z; PimIMService::GetAggregateID(ulong,IPOutlookApp3 *,USOID &)
0x18000a7dc  mov     ebx, eax
0x18000a7de  test    eax, eax
0x18000a7e0  jns     short loc_18000A802
0x18000a7e2  mov     r9d, 8E5h
0x18000a7e8  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a7ef  mov     edx, 1
0x18000a7f4  mov     ecx, ebx
0x18000a7f6  call    Log_HREvent
0x18000a7fb  mov     eax, ebx
0x18000a7fd  jmp     loc_18000A97C
0x18000a802  mov     rbp, [rsp+68h+arg_20]
0x18000a80a  mov     eax, 300h
0x18000a80f  lea     rbx, [rbp+6]
0x18000a813  test    [rbx], ax
0x18000a816  jnz     short loc_18000A847
0x18000a818  cmp     [rbp+8], r12d
0x18000a81c  jnz     short loc_18000A847
0x18000a81e  mov     dword ptr [r14], 2
0x18000a825  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18000a82c  jz      short loc_18000A83F
0x18000a82e  lea     r8, [r13+8]
0x18000a832  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18000a837  xor     r12d, r12d
0x18000a83a  jmp     loc_18000A8D0
0x18000a83f  xor     r12d, r12d
0x18000a842  jmp     loc_18000A8F3
0x18000a847  mov     rax, [r15]
0x18000a84a  lea     r8, [rsp+68h+arg_10]
0x18000a852  xor     r12d, r12d
0x18000a855  mov     rdx, r13
0x18000a858  mov     rcx, r15
0x18000a85b  mov     [rsp+68h+arg_10], r12d
0x18000a863  mov     rax, [rax+0B8h]
0x18000a86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a86f  mov     r15d, eax
0x18000a872  test    eax, eax
0x18000a874  jns     short loc_18000A897
0x18000a876  mov     r9d, 8F3h
0x18000a87c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a883  lea     edx, [r12+1]
0x18000a888  mov     ecx, eax
0x18000a88a  call    Log_HREvent
0x18000a88f  mov     eax, r15d
0x18000a892  jmp     loc_18000A97C
0x18000a897  cmp     [rsp+68h+arg_10], r12d
0x18000a89f  jnz     short loc_18000A8B7
0x18000a8a1  mov     dword ptr [r14], 4
0x18000a8a8  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18000a8af  jz      short loc_18000A8F3
0x18000a8b1  lea     r8, [r13+8]
0x18000a8b5  jmp     short loc_18000A8CB
0x18000a8b7  mov     dword ptr [r14], 2
0x18000a8be  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18000a8c5  jz      short loc_18000A8F3
0x18000a8c7  lea     r8, [r13+8]
0x18000a8cb  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18000a8d0  mov     [rsp+68h+var_40], 0FFFFFFFFFFFFFFFFh
0x18000a8d9  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18000a8e0  mov     rdx, rax; void *
0x18000a8e3  mov     [rsp+68h+var_48], r12
0x18000a8e8  mov     r9d, 4
0x18000a8ee  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18000a8f3  mov     eax, [rsp+68h+arg_8]
0x18000a8f7  mov     rcx, [rsp+68h+arg_28]; this
0x18000a8ff  mov     edx, 300h
0x18000a904  mov     [rcx], r12d
0x18000a907  test    [rbx], dx
0x18000a90a  jnz     short loc_18000A97A
0x18000a90c  test    ax, ax
0x18000a90f  jnz     short loc_18000A918
0x18000a911  mov     eax, [rdi]
0x18000a913  cmp     [rbp+8], eax
0x18000a916  jz      short loc_18000A97A
0x18000a918  mov     rdi, [rsp+68h+arg_30]
0x18000a920  mov     edx, [rbp+8]; unsigned int
0x18000a923  mov     r9, rdi; struct USOID *
0x18000a926  mov     dword ptr [rcx], 2
0x18000a92c  mov     r8, [rsi]; struct IPOutlookApp3 *
0x18000a92f  call    ?GetAggregateID@PimIMService@@AEAAJKPEAUIPOutlookApp3@@AEAUUSOID@@@Z; PimIMService::GetAggregateID(ulong,IPOutlookApp3 *,USOID &)
0x18000a934  mov     ebx, eax
0x18000a936  test    eax, eax
0x18000a938  jns     short loc_18000A945
0x18000a93a  mov     r9d, 90Fh
0x18000a940  jmp     loc_18000A7E8
0x18000a945  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18000a94c  jz      short loc_18000A97A
0x18000a94e  lea     r8, [rdi+8]
0x18000a952  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18000a957  mov     rdx, rax; void *
0x18000a95a  mov     [rsp+68h+var_40], 0FFFFFFFFFFFFFFFFh
0x18000a963  mov     r9d, 4
0x18000a969  mov     [rsp+68h+var_48], r12
0x18000a96e  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18000a975  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18000a97a  xor     eax, eax
0x18000a97c  mov     rbx, [rsp+68h+arg_0]
0x18000a981  add     rsp, 30h
0x18000a985  pop     r15
0x18000a987  pop     r14
0x18000a989  pop     r13
0x18000a98b  pop     r12
0x18000a98d  pop     rdi
0x18000a98e  pop     rsi
0x18000a98f  pop     rbp
0x18000a990  retn
```
