# PimIMService::ShouldHandleChange(SyncPartnerData const &,ChangeInfo const &,IPOItemMetadata * *,_SQLCEPROPVAL &,int &)

- ea: `0x18000a15c`
- end: `0x18000a40a`
- name: `?ShouldHandleChange@PimIMService@@QEAAJAEBUSyncPartnerData@@AEBUChangeInfo@@PEAPEAUIPOItemMetadata@@AEAU_SQLCEPROPVAL@@AEAH@Z`
- size: `686`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, const struct SyncPartnerData *, const struct ChangeInfo *, struct IPOItemMetadata **, struct _SQLCEPROPVAL *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007968`

## callees

- `0x180002da8`
- `0x180003468`
- `0x180003f0c`
- `0x1800067c0`
- `0x1800086a0`
- `0x18000a15c`
- `0x18000b5f4`
- `0x18000c5b8`
- `0x1800211e6`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x18000a1d5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000a292`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000a313`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::ShouldHandleChange(
        PimIMService *this,
        const struct SyncPartnerData *a2,
        const struct ChangeInfo *a3,
        struct IPOItemMetadata **a4,
        struct _SQLCEPROPVAL *a5,
        int *a6)
{
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdi
  void *v12; // rax
  __int64 (__fastcall *v14)(__int64, __int64, _DWORD *, _QWORD *); // rbx
  _QWORD *v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  _WORD *v19; // rbx
  void *v20; // rax
  __int64 v21; // rcx
  int v22; // ecx
  void *v23; // rax
  _WORD *v24; // [rsp+40h] [rbp-39h] BYREF
  int v25; // [rsp+48h] [rbp-31h] BYREF
  _DWORD v26[2]; // [rsp+50h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+58h] [rbp-21h] BYREF
  int *v28; // [rsp+68h] [rbp-11h]
  __int64 v29; // [rsp+70h] [rbp-9h]
  __int64 v30; // [rsp+78h] [rbp-1h]
  int v31; // [rsp+80h] [rbp+7h]
  int v32; // [rsp+84h] [rbp+Bh]

  *a6 = 0;
  *(_DWORD *)a5 = 806617107;
  *((_WORD *)a5 + 3) = 256;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, const struct ChangeInfo *, struct IPOItemMetadata **))(**((_QWORD **)a2 + 1) + 144LL))(
         *((_QWORD *)a2 + 1),
         0,
         12,
         a3,
         a4);
  v10 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2819);
    return v10;
  }
  v11 = (__int64)*a4;
  if ( v11 )
  {
    v26[0] = *((_DWORD *)a2 + 4);
    v26[1] = *((_DWORD *)a2 + 5);
    v24 = 0;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *, _QWORD *))(*(_QWORD *)v11 + 32LL);
    v15 = tlx::replace<_SQLCEPROPVAL,&void _LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(&v24);
    v16 = v14(v11, 2, v26, v15);
    v10 = v16;
    if ( v16 >= 0 )
    {
      v19 = v24;
      if ( (v24[15] & 0x300) != 0 )
        goto LABEL_22;
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
      {
        v20 = _t_address();
        EtwTraceMessage(&ETWMESSAGE, v20, a3, 4, v21, 4, 0, -1);
        v19 = v24;
      }
      if ( *((_DWORD *)v19 + 8) != 16 )
      {
        Log_AssertionEvent(
          v17,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
          2854);
        v19 = v24;
      }
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x20) != 0 )
      {
        v22 = *((_DWORD *)v19 + 8);
        v28 = &v25;
        v30 = *((_QWORD *)v19 + 5);
        v25 = v22;
        v31 = v22;
        v29 = 4;
        v32 = 0;
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
          (const EVENT_DESCRIPTOR *)PIMIndex_ProcessedContactVersion,
          v18,
          3u,
          &v27);
        v19 = v24;
      }
      if ( memcmp_0(*((const void **)v19 + 5), (char *)a3 + 16, *((unsigned int *)v19 + 8)) )
      {
LABEL_22:
        *(_OWORD *)a5 = *(_OWORD *)v19;
        *((_QWORD *)a5 + 2) = *((_QWORD *)v19 + 2);
        *(_DWORD *)a5 = 806617107;
      }
      else
      {
        if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
        {
          v23 = _t_address();
          EtwTraceMessage(&ETWMESSAGE, v23, 0, -1, 0, -1);
        }
        *a6 = 1;
      }
      v10 = 0;
    }
    else
    {
      Log_HREvent(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2843);
    }
    auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v24);
    return v10;
  }
  *((_WORD *)a5 + 3) = 256;
  if ( *((_DWORD *)a3 + 3) == 4 )
  {
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
    {
      v12 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v12, 0, -1, 0, -1);
    }
    *a6 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a15c  push    rbp
0x18000a15e  push    rbx
0x18000a15f  push    rsi
0x18000a160  push    rdi
0x18000a161  push    r12
0x18000a163  push    r14
0x18000a165  push    r15
0x18000a167  lea     rbp, [rsp-17h]
0x18000a16c  sub     rsp, 90h
0x18000a173  mov     rax, cs:__security_cookie
0x18000a17a  xor     rax, rsp
0x18000a17d  mov     [rbp+47h+var_38], rax
0x18000a181  mov     r14, [rbp+47h+arg_20]
0x18000a185  mov     rsi, rdx
0x18000a188  mov     r12, [rbp+47h+arg_28]
0x18000a18c  mov     rdi, r9
0x18000a18f  mov     [rsp+0C0h+var_A0], r9
0x18000a194  mov     r15, r8
0x18000a197  mov     r9, r8
0x18000a19a  mov     dword ptr [r12], 0
0x18000a1a2  mov     dword ptr [r14], 30140013h
0x18000a1a9  mov     word ptr [r14+6], 100h
0x18000a1b0  mov     rcx, [rdx+8]
0x18000a1b4  xor     edx, edx
0x18000a1b6  mov     rax, [rcx]
0x18000a1b9  lea     r8d, [rdx+0Ch]
0x18000a1bd  mov     rax, [rax+90h]
0x18000a1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c9  mov     ebx, eax
0x18000a1cb  test    eax, eax
0x18000a1cd  jns     short loc_18000A1ED
0x18000a1cf  mov     r9d, 0B03h
0x18000a1d5  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a1dc  mov     edx, 1
0x18000a1e1  mov     ecx, eax
0x18000a1e3  call    Log_HREvent
0x18000a1e8  jmp     loc_18000A3EA
0x18000a1ed  mov     rdi, [rdi]
0x18000a1f0  test    rdi, rdi
0x18000a1f3  jnz     short loc_18000A24B
0x18000a1f5  mov     edi, 4
0x18000a1fa  mov     word ptr [r14+6], 100h
0x18000a201  cmp     [r15+0Ch], edi
0x18000a205  jnz     short loc_18000A244
0x18000a207  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, dil
0x18000a20e  jz      short loc_18000A23C
0x18000a210  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18000a215  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a219  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18000a220  mov     [rsp+0C0h+var_98], rsi
0x18000a225  mov     r9, rsi
0x18000a228  mov     rdx, rax; void *
0x18000a22b  mov     [rsp+0C0h+var_A0], 0
0x18000a234  xor     r8d, r8d
0x18000a237  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18000a23c  mov     dword ptr [r12], 1
0x18000a244  xor     eax, eax
0x18000a246  jmp     loc_18000A3EC
0x18000a24b  mov     eax, [rsi+10h]
0x18000a24e  lea     rcx, [rbp+47h+var_80]
0x18000a252  mov     [rbp+47h+var_70], eax
0x18000a255  mov     eax, [rsi+14h]
0x18000a258  mov     [rbp+47h+var_6C], eax
0x18000a25b  mov     [rbp+47h+var_80], 0
0x18000a263  mov     rax, [rdi]
0x18000a266  mov     rbx, [rax+20h]
0x18000a26a  call    ??$replace@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SQLCEPROPVAL@@AEAV?$auto_array_ptr@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(tlx::auto_array_ptr<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)> &)
0x18000a26f  mov     r9, rax
0x18000a272  lea     r8, [rbp+47h+var_70]
0x18000a276  mov     rax, rbx
0x18000a279  mov     edx, 2
0x18000a27e  mov     rcx, rdi
0x18000a281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a286  mov     ebx, eax
0x18000a288  test    eax, eax
0x18000a28a  jns     short loc_18000A2AA
0x18000a28c  mov     r9d, 0B1Bh
0x18000a292  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a299  mov     edx, 1
0x18000a29e  mov     ecx, eax
0x18000a2a0  call    Log_HREvent
0x18000a2a5  jmp     loc_18000A3E1
0x18000a2aa  mov     rbx, [rbp+47h+var_80]
0x18000a2ae  mov     eax, 300h
0x18000a2b3  test    [rbx+1Eh], ax
0x18000a2b7  jnz     loc_18000A3C6
0x18000a2bd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a2c1  lea     edi, [rsi+5]
0x18000a2c4  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, dil
0x18000a2cb  jz      short loc_18000A307
0x18000a2cd  lea     rcx, [r15+8]
0x18000a2d1  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18000a2d6  mov     [rsp+0C0h+var_88], rsi
0x18000a2db  mov     rdx, rax; void *
0x18000a2de  mov     [rsp+0C0h+var_90], 0
0x18000a2e7  mov     r9d, edi
0x18000a2ea  mov     [rsp+0C0h+var_98], rdi
0x18000a2ef  mov     r8, r15
0x18000a2f2  mov     [rsp+0C0h+var_A0], rcx
0x18000a2f7  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18000a2fe  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18000a303  mov     rbx, [rbp+47h+var_80]
0x18000a307  cmp     dword ptr [rbx+20h], 10h
0x18000a30b  jz      short loc_18000A323
0x18000a30d  mov     r8d, 0B26h
0x18000a313  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a31a  call    Log_AssertionEvent
0x18000a31f  mov     rbx, [rbp+47h+var_80]
0x18000a323  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 20h
0x18000a32a  jz      short loc_18000A376
0x18000a32c  mov     ecx, [rbx+20h]
0x18000a32f  lea     rax, [rbp+47h+var_78]
0x18000a333  mov     [rbp+47h+var_58], rax
0x18000a337  lea     rdx, PIMIndex_ProcessedContactVersion
0x18000a33e  mov     rax, [rbx+28h]
0x18000a342  mov     r9d, 3
0x18000a348  mov     [rbp+47h+var_48], rax
0x18000a34c  lea     rax, [rbp+47h+var_68]
0x18000a350  mov     [rbp+47h+var_78], ecx
0x18000a353  mov     [rbp+47h+var_40], ecx
0x18000a356  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18000a35d  mov     [rsp+0C0h+var_A0], rax
0x18000a362  mov     [rbp+47h+var_50], rdi
0x18000a366  mov     [rbp+47h+var_3C], 0
0x18000a36d  call    McGenEventWrite_EventWriteTransfer
0x18000a372  mov     rbx, [rbp+47h+var_80]
0x18000a376  mov     r8d, [rbx+20h]; Size
0x18000a37a  lea     rdx, [r15+10h]; Buf2
0x18000a37e  mov     rcx, [rbx+28h]; Buf1
0x18000a382  call    memcmp_0
0x18000a387  test    eax, eax
0x18000a389  jnz     short loc_18000A3C6
0x18000a38b  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, dil
0x18000a392  jz      short loc_18000A3BC
0x18000a394  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18000a399  mov     rdx, rax; void *
0x18000a39c  mov     [rsp+0C0h+var_98], rsi
0x18000a3a1  mov     r9, rsi
0x18000a3a4  mov     [rsp+0C0h+var_A0], 0
0x18000a3ad  xor     r8d, r8d
0x18000a3b0  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18000a3b7  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18000a3bc  mov     dword ptr [r12], 1
0x18000a3c4  jmp     short loc_18000A3DF
0x18000a3c6  movups  xmm0, xmmword ptr [rbx]
0x18000a3c9  movups  xmmword ptr [r14], xmm0
0x18000a3cd  movsd   xmm1, qword ptr [rbx+10h]
0x18000a3d2  movsd   qword ptr [r14+10h], xmm1
0x18000a3d8  mov     dword ptr [r14], 30140013h
0x18000a3df  xor     ebx, ebx
0x18000a3e1  lea     rcx, [rbp+47h+var_80]
0x18000a3e5  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x18000a3ea  mov     eax, ebx
0x18000a3ec  mov     rcx, [rbp+47h+var_38]
0x18000a3f0  xor     rcx, rsp; StackCookie
0x18000a3f3  call    __security_check_cookie
0x18000a3f8  add     rsp, 90h
0x18000a3ff  pop     r15
0x18000a401  pop     r14
0x18000a403  pop     r12
0x18000a405  pop     rdi
0x18000a406  pop     rsi
0x18000a407  pop     rbx
0x18000a408  pop     rbp
0x18000a409  retn
```
