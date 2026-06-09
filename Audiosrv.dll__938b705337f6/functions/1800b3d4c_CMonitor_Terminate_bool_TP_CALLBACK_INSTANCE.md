# CMonitor::Terminate(bool,_TP_CALLBACK_INSTANCE *)

- ea: `0x1800b3d4c`
- end: `0x1800b3fc8`
- name: `?Terminate@CMonitor@@AEAAX_NPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `636`
- prototype: `void(CMonitor *__hidden this, bool, struct _TP_CALLBACK_INSTANCE *)`
- caller_count: `7`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063a6c`
- `0x1800ca864`
- `0x180129994`
- `0x18012bb8c`
- `0x18012bbdc`
- `0x18012c820`
- `0x18012dde0`

## callees

- `0x180036208`
- `0x1800382ac`
- `0x18005c5e4`
- `0x1800b3d4c`
- `0x1800e82c0`
- `0x18012c3f4`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b3fbd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b3fbd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b3e0a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b3e0a`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x1800b3f78`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x1800b3f78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3e9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3e9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3f10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMonitor::Terminate(CMonitor *this, char a2, struct _TP_CALLBACK_INSTANCE *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  _BYTE v8[56]; // [rsp+20h] [rbp-38h] BYREF

  if ( *((_DWORD *)this + 18) != 6 && (!a2 || *((_DWORD *)this + 18) != 5) )
  {
    ATL::CCritSecLock::CCritSecLock(
      (ATL::CCritSecLock *)v8,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 32),
      (bool)a3);
    if ( *((_DWORD *)this + 18) == 6 || *((_DWORD *)this + 18) == 5 && a2 && *((_QWORD *)this + 25) )
    {
LABEL_15:
      ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v8);
      return;
    }
    *((_DWORD *)this + 18) = 5;
    if ( a2 && *((_QWORD *)this + 25) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
      }
      (*(void (__fastcall **)(CMonitor *))(*(_QWORD *)this + 8LL))(this);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 25));
      goto LABEL_15;
    }
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v8);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
    }
    v6 = *((_QWORD *)this + 15);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 88LL))(v6, *((_QWORD *)this + 18));
      ATL::CComPtrBase<IPart>::Release((char *)this + 120);
      ATL::CComPtrBase<CMonitor::CMonitorNotification>::Release((char *)this + 144);
    }
    CoTaskMemFree(*((LPVOID *)this + 14));
    *((_QWORD *)this + 14) = 0;
    ATL::CComPtrBase<IPart>::Release((char *)this + 104);
    CoTaskMemFree(*((LPVOID *)this + 12));
    *((_QWORD *)this + 12) = 0;
    v7 = *((_QWORD *)this + 21);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 88LL))(v7, *((_QWORD *)this + 22));
      ATL::CComPtrBase<IPart>::Release((char *)this + 168);
      ATL::CComPtrBase<CMonitor::CMonitorNotification>::Release((char *)this + 176);
    }
    ATL::CComPtrBase<IPart>::Release((char *)this + 160);
    CoTaskMemFree(*((LPVOID *)this + 19));
    *((_QWORD *)this + 19) = 0;
    *((_DWORD *)this + 18) = 6;
    if ( *((_QWORD *)this + 24) )
    {
      if ( a3 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
        }
        SetEventWhenCallbackReturns(a3, *((HANDLE *)this + 24));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
        }
        SetEvent(*((HANDLE *)this + 24));
      }
    }
  }
}

```

## disassembly

```asm
0x1800b3d4c  push    rbx
0x1800b3d4e  push    rbp
0x1800b3d4f  push    rdi
0x1800b3d50  push    r14
0x1800b3d52  push    r15
0x1800b3d54  sub     rsp, 30h
0x1800b3d58  mov     r15, r8
0x1800b3d5b  mov     bl, dl
0x1800b3d5d  mov     rdi, rcx
0x1800b3d60  cmp     dword ptr [rcx+48h], 6
0x1800b3d64  jz      loc_1800B3E1B
0x1800b3d6a  test    dl, dl
0x1800b3d6c  jz      short loc_1800B3D78
0x1800b3d6e  cmp     dword ptr [rcx+48h], 5
0x1800b3d72  jz      loc_1800B3E1B
0x1800b3d78  lea     rdx, [rcx+20h]; struct _RTL_CRITICAL_SECTION *
0x1800b3d7c  lea     rcx, [rsp+58h+var_38]; this
0x1800b3d81  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x1800b3d86  nop
0x1800b3d87  cmp     dword ptr [rdi+48h], 6
0x1800b3d8b  jz      loc_1800B3E11
0x1800b3d91  cmp     dword ptr [rdi+48h], 5
0x1800b3d95  jnz     short loc_1800B3DA5
0x1800b3d97  test    bl, bl
0x1800b3d99  jz      short loc_1800B3DA5
0x1800b3d9b  cmp     qword ptr [rdi+0C8h], 0
0x1800b3da3  jnz     short loc_1800B3E11
0x1800b3da5  mov     dword ptr [rdi+48h], 5
0x1800b3dac  test    bl, bl
0x1800b3dae  jz      short loc_1800B3E27
0x1800b3db0  cmp     qword ptr [rdi+0C8h], 0
0x1800b3db8  jz      short loc_1800B3E27
0x1800b3dba  lea     rbp, WPP_GLOBAL_Control
0x1800b3dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3dc8  cmp     rcx, rbp
0x1800b3dcb  jz      short loc_1800B3DF4
0x1800b3dcd  test    dword ptr [rcx+1Ch], 800000h
0x1800b3dd4  jz      short loc_1800B3DF4
0x1800b3dd6  cmp     byte ptr [rcx+19h], 4
0x1800b3dda  jb      short loc_1800B3DF4
0x1800b3ddc  mov     edx, 13h
0x1800b3de1  mov     r9, rdi
0x1800b3de4  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800b3deb  mov     rcx, [rcx+10h]
0x1800b3def  call    WPP_SF_q
0x1800b3df4  mov     rax, [rdi]
0x1800b3df7  mov     rcx, rdi
0x1800b3dfa  mov     rax, [rax+8]
0x1800b3dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e03  mov     rcx, [rdi+0C8h]; pwk
0x1800b3e0a  call    cs:__imp_SubmitThreadpoolWork
0x1800b3e10  nop
0x1800b3e11  lea     rcx, [rsp+58h+var_38]; this
0x1800b3e16  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800b3e1b  add     rsp, 30h
0x1800b3e1f  pop     r15
0x1800b3e21  pop     r14
0x1800b3e23  pop     rdi
0x1800b3e24  pop     rbp
0x1800b3e25  pop     rbx
0x1800b3e26  retn
0x1800b3e27  lea     rcx, [rsp+58h+var_38]; this
0x1800b3e2c  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800b3e31  lea     rbp, WPP_GLOBAL_Control
0x1800b3e38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3e3f  cmp     rcx, rbp
0x1800b3e42  jz      short loc_1800B3E6B
0x1800b3e44  test    dword ptr [rcx+1Ch], 800000h
0x1800b3e4b  jz      short loc_1800B3E6B
0x1800b3e4d  cmp     byte ptr [rcx+19h], 4
0x1800b3e51  jb      short loc_1800B3E6B
0x1800b3e53  mov     edx, 14h
0x1800b3e58  mov     r9, rdi
0x1800b3e5b  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800b3e62  mov     rcx, [rcx+10h]
0x1800b3e66  call    WPP_SF_q
0x1800b3e6b  mov     rcx, [rdi+78h]
0x1800b3e6f  test    rcx, rcx
0x1800b3e72  jz      short loc_1800B3E9B
0x1800b3e74  lea     rbx, [rdi+90h]
0x1800b3e7b  mov     rax, [rcx]
0x1800b3e7e  mov     rdx, [rbx]
0x1800b3e81  mov     rax, [rax+58h]
0x1800b3e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e8a  lea     rcx, [rdi+78h]
0x1800b3e8e  call    ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
0x1800b3e93  mov     rcx, rbx
0x1800b3e96  call    ?Release@?$CComPtrBase@VCMonitorNotification@CMonitor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<CMonitor::CMonitorNotification>::Release(void)
0x1800b3e9b  mov     rcx, [rdi+70h]; pv
0x1800b3e9f  call    cs:__imp_CoTaskMemFree
0x1800b3ea5  mov     qword ptr [rdi+70h], 0
0x1800b3ead  lea     rcx, [rdi+68h]
0x1800b3eb1  call    ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
0x1800b3eb6  mov     rcx, [rdi+60h]; pv
0x1800b3eba  call    cs:__imp_CoTaskMemFree
0x1800b3ec0  mov     qword ptr [rdi+60h], 0
0x1800b3ec8  lea     r14, [rdi+0A8h]
0x1800b3ecf  mov     rcx, [r14]
0x1800b3ed2  test    rcx, rcx
0x1800b3ed5  jz      short loc_1800B3EFD
0x1800b3ed7  lea     rbx, [rdi+0B0h]
0x1800b3ede  mov     rax, [rcx]
0x1800b3ee1  mov     rdx, [rbx]
0x1800b3ee4  mov     rax, [rax+58h]
0x1800b3ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3eed  mov     rcx, r14
0x1800b3ef0  call    ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
0x1800b3ef5  mov     rcx, rbx
0x1800b3ef8  call    ?Release@?$CComPtrBase@VCMonitorNotification@CMonitor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<CMonitor::CMonitorNotification>::Release(void)
0x1800b3efd  lea     rcx, [rdi+0A0h]
0x1800b3f04  call    ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
0x1800b3f09  mov     rcx, [rdi+98h]; pv
0x1800b3f10  call    cs:__imp_CoTaskMemFree
0x1800b3f16  mov     qword ptr [rdi+98h], 0
0x1800b3f21  mov     dword ptr [rdi+48h], 6
0x1800b3f28  cmp     qword ptr [rdi+0C0h], 0
0x1800b3f30  jz      loc_1800B3E1B
0x1800b3f36  test    r15, r15
0x1800b3f39  jz      short loc_1800B3F83
0x1800b3f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3f42  cmp     rcx, rbp
0x1800b3f45  jz      short loc_1800B3F6E
0x1800b3f47  test    dword ptr [rcx+1Ch], 800000h
0x1800b3f4e  jz      short loc_1800B3F6E
0x1800b3f50  cmp     byte ptr [rcx+19h], 4
0x1800b3f54  jb      short loc_1800B3F6E
0x1800b3f56  mov     edx, 15h
0x1800b3f5b  mov     r9, rdi
0x1800b3f5e  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800b3f65  mov     rcx, [rcx+10h]
0x1800b3f69  call    WPP_SF_q
0x1800b3f6e  mov     rdx, [rdi+0C0h]; evt
0x1800b3f75  mov     rcx, r15; pci
0x1800b3f78  call    cs:__imp_SetEventWhenCallbackReturns
0x1800b3f7e  jmp     loc_1800B3E1B
0x1800b3f83  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3f8a  cmp     rcx, rbp
0x1800b3f8d  jz      short loc_1800B3FB6
0x1800b3f8f  test    dword ptr [rcx+1Ch], 800000h
0x1800b3f96  jz      short loc_1800B3FB6
0x1800b3f98  cmp     byte ptr [rcx+19h], 4
0x1800b3f9c  jb      short loc_1800B3FB6
0x1800b3f9e  mov     edx, 16h
0x1800b3fa3  mov     r9, rdi
0x1800b3fa6  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800b3fad  mov     rcx, [rcx+10h]
0x1800b3fb1  call    WPP_SF_q
0x1800b3fb6  mov     rcx, [rdi+0C0h]; hEvent
0x1800b3fbd  call    cs:__imp_SetEvent
0x1800b3fc3  jmp     loc_1800B3E1B
```
