# PimIMService::CollectChanges(SyncPartnerData const &,OLITEMID &,IUnknown * *,int,utl::vector<OLITEMID,utl::allocator<OLITEMID>> &,utl::vector<ChangeInfo,utl::allocator<ChangeInfo>> &)

- ea: `0x18000523c`
- end: `0x18000551f`
- name: `?CollectChanges@PimIMService@@AEAAJAEBUSyncPartnerData@@AEAUOLITEMID@@PEAPEAUIUnknown@@HAEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@AEAV?$vector@UChangeInfo@@V?$allocator@UChangeInfo@@@utl@@@6@@Z`
- size: `739`
- prototype: `__int64 __fastcall(void *, __int64 *, __int64 *, _QWORD *, int, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ab48`

## callees

- `0x180002da8`
- `0x180003d88`
- `0x18000428c`
- `0x18000523c`
- `0x180005d3c`
- `0x1800065a8`
- `0x1800067c0`
- `0x180006c5c`
- `0x180009b40`
- `0x18000c5b8`
- `0x18000c6dc`
- `0x18000c790`
- `0x18000d63c`
- `0x180022010`

## string_xrefs

- `0x180005298`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180005308`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000540b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180005465`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::CollectChanges(
        void *a1,
        __int64 *a2,
        __int64 *a3,
        _QWORD *a4,
        int a5,
        _QWORD *a6,
        _QWORD *a7)
{
  _QWORD *v7; // r12
  int v8; // eax
  __int64 v10; // r8
  int v11; // eax
  unsigned int v12; // ebx
  _QWORD *v14; // rdi
  SyncSessionHandle *v15; // rbx
  int v16; // esi
  __int64 v17; // r9
  _QWORD *v18; // r14
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // esi
  int v23; // eax
  unsigned int v24; // r15d
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // r14d
  char v29; // al
  void *v30; // rax
  __int64 v31; // [rsp+40h] [rbp-38h] BYREF
  int v32; // [rsp+48h] [rbp-30h]
  void *Block; // [rsp+80h] [rbp+8h] BYREF
  __int64 v34; // [rsp+90h] [rbp+18h]

  Block = a1;
  v7 = a4;
  v8 = *((_DWORD *)a3 + 2);
  v31 = *a3;
  v32 = v8;
  v10 = *a4;
  Block = 0;
  v11 = SyncSessionHandle::CreateInstance(a2, &v31, v10, &Block);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( *v7 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
      *v7 = 0;
    }
    v14 = a6;
    v15 = (SyncSessionHandle *)Block;
    v16 = SyncSessionHandle::SetExceptions(Block, a6);
    if ( v16 >= 0 )
    {
      v18 = a7;
      v14[1] = *v14;
      v18[1] = *v18;
      if ( a5 )
      {
LABEL_22:
        v34 = (__int64)(v18[1] - *v18) >> 5;
        if ( v34 )
        {
          v25 = 1;
        }
        else
        {
          v25 = 2;
          v7 = 0;
        }
        v26 = SyncSessionHandle::EndSyncSession(v15, v25, v7);
        v28 = v26;
        if ( v26 >= 0 )
        {
          v29 = Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits;
          if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x20) != 0 )
          {
            McTemplateU0qq_EventWriteTransfer(
              v27,
              PIMIndex_NumberOfContacts_Enum,
              (unsigned int)v34,
              *((unsigned int *)a2 + 7));
            v29 = Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits;
          }
          if ( (v29 & 4) != 0 )
          {
            v30 = _t_address();
            EtwTraceMessage(&ETWMESSAGE, v30, &a5);
          }
          if ( v15 )
            tlx::_delete<SyncSessionHandle>(v15);
          return 0;
        }
        else
        {
          Log_HREvent(
            (unsigned int)v26,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            1764);
          if ( v15 )
            tlx::_delete<SyncSessionHandle>(v15);
          return v28;
        }
      }
      else
      {
        while ( 1 )
        {
          v16 = FailOnServiceShutdown();
          if ( v16 < 0 )
          {
            v17 = 1736;
            goto LABEL_9;
          }
          v19 = *a2;
          Block = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v19 + 128LL))(v19, &Block);
          v22 = v20;
          if ( v20 >= 0 && v20 != 1 )
          {
            if ( Block )
            {
              v23 = PimIMService::GetChangeInfo(v21, Block, v18);
              v24 = v23;
              if ( v23 < 0 )
                break;
            }
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&Block);
          if ( v22 )
          {
            if ( v22 != 1 && (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 8) != 0 )
              McTemplateU0d_EventWriteTransfer(
                &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
                PIMIndex_ErrorGettingNextChange,
                v22);
            goto LABEL_22;
          }
        }
        Log_HREvent(
          (unsigned int)v23,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
          1744);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&Block);
        if ( v15 )
          tlx::_delete<SyncSessionHandle>(v15);
        return v24;
      }
    }
    else
    {
      v17 = 1721;
LABEL_9:
      Log_HREvent(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        v17);
      if ( v15 )
        tlx::_delete<SyncSessionHandle>(v15);
      return (unsigned int)v16;
    }
  }
  else
  {
    Log_HREvent(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      1712);
    if ( Block )
      tlx::_delete<SyncSessionHandle>((SyncSessionHandle *)Block);
    return v12;
  }
}

```

## disassembly

```asm
0x18000523c  mov     r11, rsp
0x18000523f  mov     [r11+10h], rbx
0x180005243  mov     [r11+20h], rsi
0x180005247  mov     [r11+8], rcx
0x18000524b  push    rdi
0x18000524c  push    r12
0x18000524e  push    r13
0x180005250  push    r14
0x180005252  push    r15
0x180005254  sub     rsp, 50h
0x180005258  movsd   xmm0, qword ptr [r8]
0x18000525d  mov     r12, r9
0x180005260  mov     eax, [r8+8]
0x180005264  lea     r9, [r11+8]
0x180005268  mov     r13, rdx
0x18000526b  movsd   [rsp+78h+var_38], xmm0
0x180005271  xor     r15d, r15d
0x180005274  mov     [rsp+78h+var_30], eax
0x180005278  mov     r8, [r12]
0x18000527c  lea     rdx, [r11-38h]
0x180005280  mov     rcx, r13
0x180005283  mov     [r11+8], r15
0x180005287  call    ?CreateInstance@SyncSessionHandle@@SAJAEBUSyncPartnerData@@UOLITEMID@@PEAUIUnknown@@PEAPEAV1@@Z; SyncSessionHandle::CreateInstance(SyncPartnerData const &,OLITEMID,IUnknown *,SyncSessionHandle * *)
0x18000528c  mov     ebx, eax
0x18000528e  test    eax, eax
0x180005290  jns     short loc_1800052C3
0x180005292  mov     r9d, 6B0h
0x180005298  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000529f  lea     edx, [r15+1]
0x1800052a3  mov     ecx, eax
0x1800052a5  call    Log_HREvent
0x1800052aa  mov     rcx, [rsp+78h+Block]; Block
0x1800052b2  test    rcx, rcx
0x1800052b5  jz      short loc_1800052BC
0x1800052b7  call    ??$_delete@VSyncSessionHandle@@@tlx@@YAXPEAVSyncSessionHandle@@@Z; tlx::_delete<SyncSessionHandle>(SyncSessionHandle *)
0x1800052bc  mov     eax, ebx
0x1800052be  jmp     loc_180005505
0x1800052c3  mov     rcx, [r12]
0x1800052c7  test    rcx, rcx
0x1800052ca  jz      short loc_1800052DC
0x1800052cc  mov     rax, [rcx]
0x1800052cf  mov     rax, [rax+10h]
0x1800052d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d8  mov     [r12], r15
0x1800052dc  mov     rdi, [rsp+78h+arg_28]
0x1800052e4  mov     rbx, [rsp+78h+Block]
0x1800052ec  mov     rdx, rdi
0x1800052ef  mov     rcx, rbx
0x1800052f2  call    ?SetExceptions@SyncSessionHandle@@QEAAJAEBV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z; SyncSessionHandle::SetExceptions(utl::vector<OLITEMID,utl::allocator<OLITEMID>> const &)
0x1800052f7  mov     esi, eax
0x1800052f9  test    eax, eax
0x1800052fb  jns     short loc_18000532A
0x1800052fd  mov     r9d, 6B9h
0x180005303  mov     edx, 1
0x180005308  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000530f  mov     ecx, esi
0x180005311  call    Log_HREvent
0x180005316  test    rbx, rbx
0x180005319  jz      short loc_180005323
0x18000531b  mov     rcx, rbx; Block
0x18000531e  call    ??$_delete@VSyncSessionHandle@@@tlx@@YAXPEAVSyncSessionHandle@@@Z; tlx::_delete<SyncSessionHandle>(SyncSessionHandle *)
0x180005323  mov     eax, esi
0x180005325  jmp     loc_180005505
0x18000532a  mov     rax, [rdi]
0x18000532d  mov     r14, [rsp+78h+arg_30]
0x180005335  mov     [rdi+8], rax
0x180005339  mov     edi, 1
0x18000533e  mov     rax, [r14]
0x180005341  mov     [r14+8], rax
0x180005345  cmp     [rsp+78h+arg_20], r15d
0x18000534d  jnz     loc_1800053E2
0x180005353  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x180005358  mov     esi, eax
0x18000535a  test    eax, eax
0x18000535c  js      loc_18000543E
0x180005362  mov     rcx, [r13+0]
0x180005366  lea     rdx, [rsp+78h+Block]
0x18000536e  mov     [rsp+78h+Block], r15
0x180005376  mov     rax, [rcx]
0x180005379  mov     rax, [rax+80h]
0x180005380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005385  mov     esi, eax
0x180005387  test    eax, eax
0x180005389  js      short loc_1800053AE
0x18000538b  cmp     eax, edi
0x18000538d  jz      short loc_1800053AE
0x18000538f  mov     rdx, [rsp+78h+Block]
0x180005397  test    rdx, rdx
0x18000539a  jz      short loc_1800053AE
0x18000539c  mov     r8, r14
0x18000539f  call    ?GetChangeInfo@PimIMService@@AEAAJPEAUIPOChangeInfo@@AEAV?$vector@UChangeInfo@@V?$allocator@UChangeInfo@@@utl@@@utl@@@Z; PimIMService::GetChangeInfo(IPOChangeInfo *,utl::vector<ChangeInfo,utl::allocator<ChangeInfo>> &)
0x1800053a4  mov     r15d, eax
0x1800053a7  test    eax, eax
0x1800053a9  js      short loc_180005405
0x1800053ab  xor     r15d, r15d
0x1800053ae  lea     rcx, [rsp+78h+Block]
0x1800053b6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800053bb  test    esi, esi
0x1800053bd  jz      short loc_180005353
0x1800053bf  cmp     esi, edi
0x1800053c1  jz      short loc_1800053E2
0x1800053c3  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 8
0x1800053ca  jz      short loc_1800053E2
0x1800053cc  mov     r8d, esi
0x1800053cf  lea     rdx, PIMIndex_ErrorGettingNextChange
0x1800053d6  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x1800053dd  call    McTemplateU0d_EventWriteTransfer
0x1800053e2  mov     rax, [r14+8]
0x1800053e6  mov     rsi, rbx
0x1800053e9  sub     rax, [r14]
0x1800053ec  sar     rax, 5
0x1800053f0  mov     [rsp+78h+arg_10], rax
0x1800053f8  test    rax, rax
0x1800053fb  jnz     short loc_18000544B
0x1800053fd  lea     edx, [rax+2]
0x180005400  mov     r12, r15
0x180005403  jmp     short loc_18000544D
0x180005405  mov     r9d, 6D0h
0x18000540b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005412  mov     edx, edi
0x180005414  mov     ecx, r15d
0x180005417  call    Log_HREvent
0x18000541c  lea     rcx, [rsp+78h+Block]
0x180005424  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005429  test    rbx, rbx
0x18000542c  jz      short loc_180005436
0x18000542e  mov     rcx, rbx; Block
0x180005431  call    ??$_delete@VSyncSessionHandle@@@tlx@@YAXPEAVSyncSessionHandle@@@Z; tlx::_delete<SyncSessionHandle>(SyncSessionHandle *)
0x180005436  mov     eax, r15d
0x180005439  jmp     loc_180005505
0x18000543e  mov     r9d, 6C8h
0x180005444  mov     edx, edi
0x180005446  jmp     loc_180005308
0x18000544b  mov     edx, edi
0x18000544d  mov     r8, r12
0x180005450  mov     rcx, rsi
0x180005453  call    ?EndSyncSession@SyncSessionHandle@@QEAAJW4PO_SYNCSESSION_OUTCOME@@PEAPEAUIUnknown@@@Z; SyncSessionHandle::EndSyncSession(PO_SYNCSESSION_OUTCOME,IUnknown * *)
0x180005458  mov     r14d, eax
0x18000545b  test    eax, eax
0x18000545d  jns     short loc_180005487
0x18000545f  mov     r9d, 6E4h
0x180005465  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000546c  mov     edx, edi
0x18000546e  mov     ecx, eax
0x180005470  call    Log_HREvent
0x180005475  test    rsi, rsi
0x180005478  jz      short loc_180005482
0x18000547a  mov     rcx, rbx; Block
0x18000547d  call    ??$_delete@VSyncSessionHandle@@@tlx@@YAXPEAVSyncSessionHandle@@@Z; tlx::_delete<SyncSessionHandle>(SyncSessionHandle *)
0x180005482  mov     eax, r14d
0x180005485  jmp     short loc_180005505
0x180005487  mov     eax, cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits
0x18000548d  test    al, 20h
0x18000548f  jz      short loc_1800054AF
0x180005491  mov     r9d, [r13+1Ch]
0x180005495  lea     rdx, PIMIndex_NumberOfContacts_Enum
0x18000549c  mov     r8d, dword ptr [rsp+78h+arg_10]
0x1800054a4  call    McTemplateU0qq_EventWriteTransfer
0x1800054a9  mov     eax, cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits
0x1800054af  mov     r9d, 4
0x1800054b5  test    r9b, al
0x1800054b8  jz      short loc_1800054F6
0x1800054ba  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800054bf  mov     [rsp+78h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800054c8  lea     r8, [rsp+78h+arg_20]
0x1800054d0  mov     rdx, rax; void *
0x1800054d3  mov     [rsp+78h+var_48], r15
0x1800054d8  lea     rax, [rsp+78h+arg_10]
0x1800054e0  mov     [rsp+78h+var_50], r9
0x1800054e5  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800054ec  mov     [rsp+78h+var_58], rax
0x1800054f1  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x1800054f6  test    rsi, rsi
0x1800054f9  jz      short loc_180005503
0x1800054fb  mov     rcx, rbx; Block
0x1800054fe  call    ??$_delete@VSyncSessionHandle@@@tlx@@YAXPEAVSyncSessionHandle@@@Z; tlx::_delete<SyncSessionHandle>(SyncSessionHandle *)
0x180005503  xor     eax, eax
0x180005505  lea     r11, [rsp+78h+var_28]
0x18000550a  mov     rbx, [r11+38h]
0x18000550e  mov     rsi, [r11+48h]
0x180005512  mov     rsp, r11
0x180005515  pop     r15
0x180005517  pop     r14
0x180005519  pop     r13
0x18000551b  pop     r12
0x18000551d  pop     rdi
0x18000551e  retn
```
