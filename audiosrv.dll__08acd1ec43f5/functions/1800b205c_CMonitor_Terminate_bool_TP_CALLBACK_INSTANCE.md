# CMonitor::Terminate(bool,_TP_CALLBACK_INSTANCE *)

- ea: `0x1800b205c`
- end: `0x1800b22d8`
- name: `?Terminate@CMonitor@@AEAAX_NPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `636`
- prototype: `void(CMonitor *__hidden this, bool, struct _TP_CALLBACK_INSTANCE *)`
- caller_count: `7`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800635dc`
- `0x1800c8878`
- `0x180129be4`
- `0x18012bddc`
- `0x18012be2c`
- `0x18012ca70`
- `0x18012e030`

## callees

- `0x180036368`
- `0x18003840c`
- `0x18005c154`
- `0x1800b205c`
- `0x1800e7b40`
- `0x18012c644`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b22cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b22cd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b211a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b211a`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x1800b2288`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x1800b2288`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b21af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b21ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b2220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b21af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b21ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b2220`

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
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
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
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
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
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
        }
        SetEventWhenCallbackReturns(a3, *((HANDLE *)this + 24));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
        }
        SetEvent(*((HANDLE *)this + 24));
      }
    }
  }
}

```

## disassembly

```asm
0x1800b205c  push    rbx
0x1800b205e  push    rbp
0x1800b205f  push    rdi
0x1800b2060  push    r14
0x1800b2062  push    r15
0x1800b2064  sub     rsp, 30h
0x1800b2068  mov     r15, r8
0x1800b206b  mov     bl, dl
0x1800b206d  mov     rdi, rcx
0x1800b2070  cmp     dword ptr [rcx+48h], 6
0x1800b2074  jz      loc_1800B212B
0x1800b207a  test    dl, dl
0x1800b207c  jz      short loc_1800B2088
0x1800b207e  cmp     dword ptr [rcx+48h], 5
0x1800b2082  jz      loc_1800B212B
0x1800b2088  lea     rdx, [rcx+20h]; struct _RTL_CRITICAL_SECTION *
0x1800b208c  lea     rcx, [rsp+58h+var_38]; this
0x1800b2091  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x1800b2096  nop
0x1800b2097  cmp     dword ptr [rdi+48h], 6
0x1800b209b  jz      loc_1800B2121
0x1800b20a1  cmp     dword ptr [rdi+48h], 5
0x1800b20a5  jnz     short loc_1800B20B5
0x1800b20a7  test    bl, bl
0x1800b20a9  jz      short loc_1800B20B5
0x1800b20ab  cmp     qword ptr [rdi+0C8h], 0
0x1800b20b3  jnz     short loc_1800B2121
0x1800b20b5  mov     dword ptr [rdi+48h], 5
0x1800b20bc  test    bl, bl
0x1800b20be  jz      short loc_1800B2137
0x1800b20c0  cmp     qword ptr [rdi+0C8h], 0
0x1800b20c8  jz      short loc_1800B2137
0x1800b20ca  lea     rbp, WPP_GLOBAL_Control
0x1800b20d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b20d8  cmp     rcx, rbp
0x1800b20db  jz      short loc_1800B2104
0x1800b20dd  test    dword ptr [rcx+1Ch], 800000h
0x1800b20e4  jz      short loc_1800B2104
0x1800b20e6  cmp     byte ptr [rcx+19h], 4
0x1800b20ea  jb      short loc_1800B2104
0x1800b20ec  mov     edx, 13h
0x1800b20f1  mov     r9, rdi
0x1800b20f4  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800b20fb  mov     rcx, [rcx+10h]
0x1800b20ff  call    WPP_SF_q
0x1800b2104  mov     rax, [rdi]
0x1800b2107  mov     rcx, rdi
0x1800b210a  mov     rax, [rax+8]
0x1800b210e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2113  mov     rcx, [rdi+0C8h]; pwk
0x1800b211a  call    cs:__imp_SubmitThreadpoolWork
0x1800b2120  nop
0x1800b2121  lea     rcx, [rsp+58h+var_38]; this
0x1800b2126  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800b212b  add     rsp, 30h
0x1800b212f  pop     r15
0x1800b2131  pop     r14
0x1800b2133  pop     rdi
0x1800b2134  pop     rbp
0x1800b2135  pop     rbx
0x1800b2136  retn
0x1800b2137  lea     rcx, [rsp+58h+var_38]; this
0x1800b213c  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800b2141  lea     rbp, WPP_GLOBAL_Control
0x1800b2148  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b214f  cmp     rcx, rbp
0x1800b2152  jz      short loc_1800B217B
0x1800b2154  test    dword ptr [rcx+1Ch], 800000h
0x1800b215b  jz      short loc_1800B217B
0x1800b215d  cmp     byte ptr [rcx+19h], 4
0x1800b2161  jb      short loc_1800B217B
0x1800b2163  mov     edx, 14h
0x1800b2168  mov     r9, rdi
0x1800b216b  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800b2172  mov     rcx, [rcx+10h]
0x1800b2176  call    WPP_SF_q
0x1800b217b  mov     rcx, [rdi+78h]
0x1800b217f  test    rcx, rcx
0x1800b2182  jz      short loc_1800B21AB
0x1800b2184  lea     rbx, [rdi+90h]
0x1800b218b  mov     rax, [rcx]
0x1800b218e  mov     rdx, [rbx]
0x1800b2191  mov     rax, [rax+58h]
0x1800b2195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b219a  lea     rcx, [rdi+78h]
0x1800b219e  call    ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
0x1800b21a3  mov     rcx, rbx
0x1800b21a6  call    ?Release@?$CComPtrBase@VCMonitorNotification@CMonitor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<CMonitor::CMonitorNotification>::Release(void)
0x1800b21ab  mov     rcx, [rdi+70h]; pv
0x1800b21af  call    cs:__imp_CoTaskMemFree
0x1800b21b5  mov     qword ptr [rdi+70h], 0
0x1800b21bd  lea     rcx, [rdi+68h]
0x1800b21c1  call    ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
0x1800b21c6  mov     rcx, [rdi+60h]; pv
0x1800b21ca  call    cs:__imp_CoTaskMemFree
0x1800b21d0  mov     qword ptr [rdi+60h], 0
0x1800b21d8  lea     r14, [rdi+0A8h]
0x1800b21df  mov     rcx, [r14]
0x1800b21e2  test    rcx, rcx
0x1800b21e5  jz      short loc_1800B220D
0x1800b21e7  lea     rbx, [rdi+0B0h]
0x1800b21ee  mov     rax, [rcx]
0x1800b21f1  mov     rdx, [rbx]
0x1800b21f4  mov     rax, [rax+58h]
0x1800b21f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b21fd  mov     rcx, r14
0x1800b2200  call    ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
0x1800b2205  mov     rcx, rbx
0x1800b2208  call    ?Release@?$CComPtrBase@VCMonitorNotification@CMonitor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<CMonitor::CMonitorNotification>::Release(void)
0x1800b220d  lea     rcx, [rdi+0A0h]
0x1800b2214  call    ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
0x1800b2219  mov     rcx, [rdi+98h]; pv
0x1800b2220  call    cs:__imp_CoTaskMemFree
0x1800b2226  mov     qword ptr [rdi+98h], 0
0x1800b2231  mov     dword ptr [rdi+48h], 6
0x1800b2238  cmp     qword ptr [rdi+0C0h], 0
0x1800b2240  jz      loc_1800B212B
0x1800b2246  test    r15, r15
0x1800b2249  jz      short loc_1800B2293
0x1800b224b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2252  cmp     rcx, rbp
0x1800b2255  jz      short loc_1800B227E
0x1800b2257  test    dword ptr [rcx+1Ch], 800000h
0x1800b225e  jz      short loc_1800B227E
0x1800b2260  cmp     byte ptr [rcx+19h], 4
0x1800b2264  jb      short loc_1800B227E
0x1800b2266  mov     edx, 15h
0x1800b226b  mov     r9, rdi
0x1800b226e  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800b2275  mov     rcx, [rcx+10h]
0x1800b2279  call    WPP_SF_q
0x1800b227e  mov     rdx, [rdi+0C0h]; evt
0x1800b2285  mov     rcx, r15; pci
0x1800b2288  call    cs:__imp_SetEventWhenCallbackReturns
0x1800b228e  jmp     loc_1800B212B
0x1800b2293  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b229a  cmp     rcx, rbp
0x1800b229d  jz      short loc_1800B22C6
0x1800b229f  test    dword ptr [rcx+1Ch], 800000h
0x1800b22a6  jz      short loc_1800B22C6
0x1800b22a8  cmp     byte ptr [rcx+19h], 4
0x1800b22ac  jb      short loc_1800B22C6
0x1800b22ae  mov     edx, 16h
0x1800b22b3  mov     r9, rdi
0x1800b22b6  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800b22bd  mov     rcx, [rcx+10h]
0x1800b22c1  call    WPP_SF_q
0x1800b22c6  mov     rcx, [rdi+0C0h]; hEvent
0x1800b22cd  call    cs:__imp_SetEvent
0x1800b22d3  jmp     loc_1800B212B
```
