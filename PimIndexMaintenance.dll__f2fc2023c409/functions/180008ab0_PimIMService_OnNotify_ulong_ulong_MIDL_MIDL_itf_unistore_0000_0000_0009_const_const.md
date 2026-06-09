# PimIMService::OnNotify(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0000_0009 const * const *)

- ea: `0x180008ab0`
- end: `0x180008d97`
- name: `?OnNotify@PimIMService@@UEAAJKKPEBQEBU__MIDL___MIDL_itf_unistore_0000_0000_0009@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, unsigned int, unsigned int, const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x180003468`
- `0x180004430`
- `0x1800047f4`
- `0x180005528`
- `0x1800067c0`
- `0x1800086a0`
- `0x180008ab0`
- `0x18000a670`
- `0x18000c5b8`
- `0x18000c734`
- `0x18000d63c`
- `0x180021240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008c87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008c87`

## string_xrefs

- `0x180008b53`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180008bcc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::OnNotify(
        RTL_SRWLOCK *this,
        __int64 a2,
        __int64 a3,
        const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *a4)
{
  unsigned int v5; // r14d
  char v6; // si
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  PimIMService *v14; // rcx
  __int64 v15; // r8
  __int64 i; // rsi
  const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *v17; // rbx
  const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *v18; // r8
  void *v19; // rax
  RTL_SRWLOCK *j; // rax
  void *v21; // rax
  int v23; // [rsp+40h] [rbp-30h] BYREF
  int v24; // [rsp+44h] [rbp-2Ch] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-28h] BYREF
  RTL_SRWLOCK *v26; // [rsp+50h] [rbp-20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+58h] [rbp-18h] BYREF

  v5 = a3;
  v23 = 0;
  v6 = a2;
  v24 = 0;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      (const EVENT_DESCRIPTOR *)ON_EVENT_START,
      a3,
      1u,
      &v27);
  v25[1] = 1;
  if ( v5 && !a4 )
  {
    v8 = -2147024809;
    v9 = 561;
    v10 = 2147942487LL;
    v11 = 0;
LABEL_8:
    Log_HREvent(
      v10,
      v11,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v9);
    goto LABEL_41;
  }
  v12 = FailOnServiceShutdown((__int64)this, a2, a3);
  v8 = v12;
  if ( v12 < 0 )
  {
    v9 = 562;
    v11 = 1;
    v10 = (unsigned int)v12;
    goto LABEL_8;
  }
  if ( LODWORD(this[3].Ptr) )
  {
    if ( (v6 & 8) != 0
      && (v5 = 0, v23 = 1, v24 = 1, (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x20) != 0) )
    {
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
        (const EVENT_DESCRIPTOR *)PIMIndex_LostEvent,
        v15,
        1u,
        &v27);
    }
    else
    {
      for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
      {
        v17 = &a4[i];
        if ( **(_DWORD **)v17 == 0x40000000 )
          Log_AssertionEvent(
            v14,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            580);
        v18 = *v17;
        v27.Ptr = 0;
        v27.Size = 0;
        v27.Size = *((_DWORD *)v18 + 2);
        v14 = (PimIMService *)*((unsigned int *)v18 + 3);
        HIDWORD(v27.Ptr) = (_DWORD)v14;
        LODWORD(v27.Ptr) = *((_DWORD *)v18 + 4);
        if ( (_DWORD)v14 == 0x10000 )
        {
          if ( ((*(_DWORD *)v18 - 4) & 0xFFFFFFFB) == 0 )
          {
            v23 = 1;
            if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x20) != 0 )
              McTemplateU0q_EventWriteTransfer(v14, PIMIndex_StoreEvent, *(unsigned int *)v18);
          }
        }
        else if ( (_DWORD)v14 == 196609 && *(_DWORD *)v18 != 32 )
        {
          if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
          {
            v19 = _t_address();
            EtwTraceMessage(&ETWMESSAGE, v19, &v27.Size, 4, &v27, 4, 0, -1);
          }
          v24 = 1;
          PimIMService::CollectWobTickets((PimIMService *)&this[-26], v13, &a4[i]);
          if ( !v23 )
          {
            v26 = this + 4;
            AcquireSRWLockShared(this + 4);
            for ( j = (RTL_SRWLOCK *)this[5].Ptr; j != &this[5]; j = (RTL_SRWLOCK *)j->Ptr )
            {
              if ( LODWORD(v27.Ptr) == LODWORD(j[3].Ptr) )
                goto LABEL_27;
            }
            v23 = 1;
LABEL_27:
            auto_SRWLockBase<_RTL_SRWLOCK,&void AcquireSRWLockShared(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *)>::~auto_SRWLockBase<_RTL_SRWLOCK,&void AcquireSRWLockShared(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *)>(&v26);
          }
        }
        if ( v24 && v23 )
          break;
      }
    }
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
    {
      v21 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v21, &v23, 4, &v24, 4, 0, -1);
    }
    if ( v23 )
      PimIMService::SubmitTpWork(v14, (struct TpWorkInfo *)&this[42]);
    if ( v24 )
      PimIMService::SubmitTpWork(v14, (struct TpWorkInfo *)&this[44]);
  }
  v8 = 0;
LABEL_41:
  tlx::_UndoSolo__lambda_614c041a7937988862e7bb3e26b09ad1___::__UndoSolo__lambda_614c041a7937988862e7bb3e26b09ad1___(v25);
  return v8;
}

```

## disassembly

```asm
0x180008ab0  mov     [rsp-28h+arg_8], rbx
0x180008ab5  mov     [rsp-28h+arg_10], rsi
0x180008aba  push    rbp
0x180008abb  push    rdi
0x180008abc  push    r13
0x180008abe  push    r14
0x180008ac0  push    r15
0x180008ac2  mov     rbp, rsp
0x180008ac5  sub     rsp, 70h
0x180008ac9  mov     rax, cs:__security_cookie
0x180008ad0  xor     rax, rsp
0x180008ad3  mov     [rbp+var_8], rax
0x180008ad7  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x180008ade  mov     r15, r9
0x180008ae1  mov     r14d, r8d
0x180008ae4  mov     [rbp+var_30], 0
0x180008aeb  mov     esi, edx
0x180008aed  mov     [rbp+var_2C], 0
0x180008af4  mov     rdi, rcx
0x180008af7  mov     r13d, 1
0x180008afd  jz      short loc_180008B1E
0x180008aff  lea     rax, [rbp+var_18]
0x180008b03  mov     r9d, r13d
0x180008b06  lea     rdx, ON_EVENT_START
0x180008b0d  mov     [rsp+70h+var_50], rax
0x180008b12  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180008b19  call    McGenEventWrite_EventWriteTransfer
0x180008b1e  mov     [rbp+var_27], r13b
0x180008b22  test    r14d, r14d
0x180008b25  jz      short loc_180008B3D
0x180008b27  test    r15, r15
0x180008b2a  jnz     short loc_180008B3D
0x180008b2c  mov     ebx, 80070057h
0x180008b31  mov     r9d, 231h
0x180008b37  mov     ecx, ebx
0x180008b39  xor     edx, edx
0x180008b3b  jmp     short loc_180008B53
0x180008b3d  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x180008b42  mov     ebx, eax
0x180008b44  test    eax, eax
0x180008b46  jns     short loc_180008B64
0x180008b48  mov     r9d, 232h
0x180008b4e  mov     edx, r13d
0x180008b51  mov     ecx, eax
0x180008b53  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008b5a  call    Log_HREvent
0x180008b5f  jmp     loc_180008D67
0x180008b64  cmp     dword ptr [rdi+18h], 0
0x180008b68  jz      loc_180008D65
0x180008b6e  test    sil, 8
0x180008b72  jz      short loc_180008BAC
0x180008b74  xor     r14d, r14d
0x180008b77  mov     [rbp+var_30], r13d
0x180008b7b  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 20h
0x180008b82  mov     [rbp+var_2C], r13d
0x180008b86  jz      short loc_180008BAC
0x180008b88  lea     rax, [rbp+var_18]
0x180008b8c  mov     r9d, r13d
0x180008b8f  lea     rdx, PIMIndex_LostEvent
0x180008b96  mov     [rsp+70h+var_50], rax
0x180008b9b  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180008ba2  call    McGenEventWrite_EventWriteTransfer
0x180008ba7  jmp     loc_180008CF6
0x180008bac  xor     esi, esi
0x180008bae  test    r14d, r14d
0x180008bb1  jz      loc_180008CF6
0x180008bb7  lea     rbx, [r15+rsi*8]
0x180008bbb  mov     rax, [rbx]
0x180008bbe  cmp     dword ptr [rax], 40000000h
0x180008bc4  jnz     short loc_180008BD8
0x180008bc6  mov     r8d, 244h
0x180008bcc  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008bd3  call    Log_AssertionEvent
0x180008bd8  mov     r8, [rbx]
0x180008bdb  xor     eax, eax
0x180008bdd  mov     [rbp+var_18], rax
0x180008be1  mov     [rbp+var_10], eax
0x180008be4  mov     eax, [r8+8]
0x180008be8  mov     [rbp+var_10], eax
0x180008beb  mov     ecx, [r8+0Ch]
0x180008bef  mov     dword ptr [rbp+var_18+4], ecx
0x180008bf2  mov     eax, [r8+10h]
0x180008bf6  mov     dword ptr [rbp+var_18], eax
0x180008bf9  cmp     ecx, 10000h
0x180008bff  jz      loc_180008CB5
0x180008c05  cmp     ecx, 30001h
0x180008c0b  jnz     loc_180008CDE
0x180008c11  cmp     dword ptr [r8], 20h ; ' '
0x180008c15  jz      loc_180008CDE
0x180008c1b  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x180008c22  jz      short loc_180008C66
0x180008c24  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180008c29  mov     [rsp+70h+var_38], 0FFFFFFFFFFFFFFFFh
0x180008c32  lea     r8, [rbp+var_10]
0x180008c36  mov     rdx, rax; void *
0x180008c39  mov     [rsp+70h+var_40], 0
0x180008c42  lea     rax, [rbp+var_18]
0x180008c46  mov     [rsp+70h+var_48], 4
0x180008c4f  mov     r9d, 4
0x180008c55  mov     [rsp+70h+var_50], rax
0x180008c5a  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180008c61  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180008c66  lea     rcx, [rdi-0D0h]; this
0x180008c6d  mov     [rbp+var_2C], r13d
0x180008c71  mov     r8, rbx; struct __MIDL___MIDL_itf_unistore_0000_0000_0009 **
0x180008c74  call    ?CollectWobTickets@PimIMService@@AEAAXKQEBQEBU__MIDL___MIDL_itf_unistore_0000_0000_0009@@@Z; PimIMService::CollectWobTickets(ulong,__MIDL___MIDL_itf_unistore_0000_0000_0009 const * const * const)
0x180008c79  cmp     [rbp+var_30], 0
0x180008c7d  jnz     short loc_180008CDE
0x180008c7f  lea     rcx, [rdi+20h]; SRWLock
0x180008c83  mov     [rbp+var_20], rcx
0x180008c87  call    cs:__imp_AcquireSRWLockShared
0x180008c8d  mov     edx, dword ptr [rbp+var_18]
0x180008c90  lea     rcx, [rdi+28h]
0x180008c94  mov     rax, [rcx]
0x180008c97  cmp     rax, rcx
0x180008c9a  jz      short loc_180008CA6
0x180008c9c  cmp     edx, [rax+18h]
0x180008c9f  jz      short loc_180008CAA
0x180008ca1  mov     rax, [rax]
0x180008ca4  jmp     short loc_180008C97
0x180008ca6  mov     [rbp+var_30], r13d
0x180008caa  lea     rcx, [rbp+var_20]
0x180008cae  call    ??1?$auto_SRWLockBase@U_RTL_SRWLOCK@@$1?AcquireSRWLockShared@@YAXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@Z@@QEAA@XZ; auto_SRWLockBase<_RTL_SRWLOCK,&AcquireSRWLockShared(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *)>::~auto_SRWLockBase<_RTL_SRWLOCK,&AcquireSRWLockShared(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *)>(void)
0x180008cb3  jmp     short loc_180008CDE
0x180008cb5  mov     eax, [r8]
0x180008cb8  sub     eax, 4
0x180008cbb  test    eax, 0FFFFFFFBh
0x180008cc0  jnz     short loc_180008CDE
0x180008cc2  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 20h
0x180008cc9  mov     [rbp+var_30], r13d
0x180008ccd  jz      short loc_180008CDE
0x180008ccf  mov     r8d, [r8]
0x180008cd2  lea     rdx, PIMIndex_StoreEvent
0x180008cd9  call    McTemplateU0q_EventWriteTransfer
0x180008cde  cmp     [rbp+var_2C], 0
0x180008ce2  jz      short loc_180008CEA
0x180008ce4  cmp     [rbp+var_30], 0
0x180008ce8  jnz     short loc_180008CF6
0x180008cea  add     esi, r13d
0x180008ced  cmp     esi, r14d
0x180008cf0  jb      loc_180008BB7
0x180008cf6  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x180008cfd  jz      short loc_180008D41
0x180008cff  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180008d04  mov     [rsp+70h+var_38], 0FFFFFFFFFFFFFFFFh
0x180008d0d  lea     r8, [rbp+var_30]
0x180008d11  mov     rdx, rax; void *
0x180008d14  mov     [rsp+70h+var_40], 0
0x180008d1d  lea     rax, [rbp+var_2C]
0x180008d21  mov     [rsp+70h+var_48], 4
0x180008d2a  mov     r9d, 4
0x180008d30  mov     [rsp+70h+var_50], rax
0x180008d35  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180008d3c  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180008d41  cmp     [rbp+var_30], 0
0x180008d45  jz      short loc_180008D53
0x180008d47  lea     rdx, [rdi+150h]; struct TpWorkInfo *
0x180008d4e  call    ?SubmitTpWork@PimIMService@@QEAAXPEAUTpWorkInfo@@@Z; PimIMService::SubmitTpWork(TpWorkInfo *)
0x180008d53  cmp     [rbp+var_2C], 0
0x180008d57  jz      short loc_180008D65
0x180008d59  lea     rdx, [rdi+160h]; struct TpWorkInfo *
0x180008d60  call    ?SubmitTpWork@PimIMService@@QEAAXPEAUTpWorkInfo@@@Z; PimIMService::SubmitTpWork(TpWorkInfo *)
0x180008d65  xor     ebx, ebx
0x180008d67  lea     rcx, [rbp+var_28]
0x180008d6b  call    tlx___UndoSolo__lambda_614c041a7937988862e7bb3e26b09ad1_______UndoSolo__lambda_614c041a7937988862e7bb3e26b09ad1___
0x180008d70  mov     eax, ebx
0x180008d72  mov     rcx, [rbp+var_8]
0x180008d76  xor     rcx, rsp; StackCookie
0x180008d79  call    __security_check_cookie
0x180008d7e  lea     r11, [rsp+70h+var_s0]
0x180008d83  mov     rbx, [r11+38h]
0x180008d87  mov     rsi, [r11+40h]
0x180008d8b  mov     rsp, r11
0x180008d8e  pop     r15
0x180008d90  pop     r14
0x180008d92  pop     r13
0x180008d94  pop     rdi
0x180008d95  pop     rbp
0x180008d96  retn
```
