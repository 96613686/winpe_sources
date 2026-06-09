# Broker::SystemTimer::WaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180010350`
- end: `0x180010488`
- name: `?WaitCallback@SystemTimer@Broker@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `312`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WAIT Wait, __int64 WaitResult)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000bba0`
- `0x18000bbf0`
- `0x18000cc04`
- `0x18000d1d4`
- `0x18000e70c`
- `0x18000ee60`
- `0x180010350`
- `0x180012dd0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800103c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800103c8`

## pseudocode

```c
void __fastcall Broker::SystemTimer::WaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // [rsp+30h] [rbp-39h] BYREF
  __int64 v8; // [rsp+38h] [rbp-31h] BYREF
  struct _RTL_SRWLOCK v9; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v10[24]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v11[32]; // [rsp+60h] [rbp-9h] BYREF
  struct _RTL_SRWLOCK *v12; // [rsp+80h] [rbp+17h]
  __int64 v13; // [rsp+88h] [rbp+1Fh]
  __int64 *v14; // [rsp+90h] [rbp+27h]
  __int64 v15; // [rsp+98h] [rbp+2Fh]
  int *v16; // [rsp+A0h] [rbp+37h]
  __int64 v17; // [rsp+A8h] [rbp+3Fh]

  if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v5,
      (__int64)qword_180020A48);
  std::_Func_class<void,>::operator()(Context + 32, Context, Wait, WaitResult);
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v10, (struct _RTL_SRWLOCK *)Context + 12);
  if ( *(_QWORD *)Context )
  {
    SetThreadpoolWait(*((PTP_WAIT *)Context + 1), *(HANDLE *)Context, 0);
    if ( (unsigned int)dword_180026058 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180026058, 1) )
      {
        v7 = (unsigned __int8)Context[24];
        v9.Ptr = *(PVOID *)Context;
        v16 = &v7;
        v14 = &v8;
        v12 = &v9;
        v8 = v6;
        v17 = 4;
        v15 = 8;
        v13 = 8;
        tlgWriteTransfer_EventWriteTransfer(&dword_180026058, &word_1800209C6, 0, 0, 5, v11);
      }
    }
  }
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v10);
}

```

## disassembly

```asm
0x180010350  mov     [rsp-8+arg_0], rbx
0x180010355  push    rbp
0x180010356  lea     rbp, [rsp-57h]
0x18001035b  sub     rsp, 0C0h
0x180010362  mov     rax, cs:__security_cookie
0x180010369  xor     rax, rsp
0x18001036c  mov     [rbp+57h+var_10], rax
0x180010370  mov     eax, cs:dword_180026058
0x180010376  mov     rbx, rdx
0x180010379  cmp     eax, 5
0x18001037c  jbe     short loc_18001039F
0x18001037e  mov     edx, 1
0x180010383  lea     rcx, dword_180026058
0x18001038a  call    _tlgKeywordOn
0x18001038f  test    al, al
0x180010391  jz      short loc_18001039F
0x180010393  lea     rdx, qword_180020A48
0x18001039a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001039f  lea     rcx, [rbx+20h]
0x1800103a3  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1800103a8  lea     rdx, [rbx+60h]; struct _RTL_SRWLOCK *
0x1800103ac  lea     rcx, [rbp+57h+var_78]; this
0x1800103b0  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x1800103b5  mov     rdx, [rbx]; h
0x1800103b8  test    rdx, rdx
0x1800103bb  jz      loc_180010462
0x1800103c1  mov     rcx, [rbx+8]; pwa
0x1800103c5  xor     r8d, r8d; pftTimeout
0x1800103c8  call    cs:__imp_SetThreadpoolWait
0x1800103ce  mov     eax, cs:dword_180026058
0x1800103d4  mov     r8, [rbx+10h]
0x1800103d8  cmp     eax, 5
0x1800103db  jbe     loc_180010462
0x1800103e1  mov     edx, 1
0x1800103e6  lea     rcx, dword_180026058
0x1800103ed  call    _tlgKeywordOn
0x1800103f2  test    al, al
0x1800103f4  jz      short loc_180010462
0x1800103f6  movzx   eax, byte ptr [rbx+18h]
0x1800103fa  lea     rdx, word_1800209C6
0x180010401  mov     [rbp+57h+var_90], eax
0x180010404  lea     rcx, dword_180026058
0x18001040b  mov     rax, [rbx]
0x18001040e  xor     r9d, r9d
0x180010411  mov     [rbp+57h+var_80], rax
0x180010415  lea     rax, [rbp+57h+var_90]
0x180010419  mov     [rbp+57h+var_20], rax
0x18001041d  lea     rax, [rbp+57h+var_88]
0x180010421  mov     [rbp+57h+var_30], rax
0x180010425  lea     rax, [rbp+57h+var_80]
0x180010429  mov     [rbp+57h+var_40], rax
0x18001042d  lea     rax, [rbp+57h+var_60]
0x180010431  mov     [rbp+57h+var_88], r8
0x180010435  xor     r8d, r8d
0x180010438  mov     [rsp+0C0h+var_98], rax
0x18001043d  mov     [rsp+0C0h+var_A0], 5
0x180010445  mov     [rbp+57h+var_18], 4
0x18001044d  mov     [rbp+57h+var_28], 8
0x180010455  mov     [rbp+57h+var_38], 8
0x18001045d  call    _tlgWriteTransfer_EventWriteTransfer
0x180010462  lea     rcx, [rbp+57h+var_78]; this
0x180010466  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18001046b  mov     rcx, [rbp+57h+var_10]
0x18001046f  xor     rcx, rsp; StackCookie
0x180010472  call    __security_check_cookie
0x180010477  mov     rbx, [rsp+0C0h+arg_0]
0x18001047f  add     rsp, 0C0h
0x180010486  pop     rbp
0x180010487  retn
```
