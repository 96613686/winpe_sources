# CMediaUiRequestSubscriber::DoSubscribe(long (*)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong),void *)

- ea: `0x1800764e4`
- end: `0x180076693`
- name: `?DoSubscribe@CMediaUiRequestSubscriber@@AEAAJP6AJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z2@Z`
- size: `431`
- prototype: `__int64 __fastcall(CMediaUiRequestSubscriber *__hidden this, int (*)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004c87c`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x1800764e4`
- `0x18007669c`
- `0x1800893b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076578`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076658`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076578`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076658`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076563`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076539`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18007652f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18007652f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180076523`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180076523`
- `ntdll!NtQueryWnfStateData` at `0x1800765c4`
- `ntdll!NtQueryWnfStateData` at `0x1800765c4`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180076630`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180076630`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMediaUiRequestSubscriber::DoSubscribe(
        CMediaUiRequestSubscriber *this,
        int (*a2)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int),
        void *a3)
{
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  struct _WNF_STATE_NAME v8; // rdx
  int v9; // ebx
  unsigned int v10; // r8d
  struct _WNF_TYPE_ID *v11; // r9
  unsigned int v13; // [rsp+44h] [rbp-1044h] BYREF
  char *v14; // [rsp+48h] [rbp-1040h]
  _BYTE v15[4096]; // [rsp+50h] [rbp-1038h] BYREF

  if ( *((_BYTE *)this + 16) || *((_DWORD *)this + 5) )
  {
    v7 = -2147019873;
    goto LABEL_16;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, (DWORD *)this + 6) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_12;
  }
  v14 = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_BYTE *)this + 16) )
  {
    v7 = -2147019873;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
LABEL_16:
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    return v7;
  }
  v13 = 0;
  memset_0(v15, 0, sizeof(v15));
  v9 = NtQueryWnfStateData(this, 0, 0, &v13);
  if ( v9 >= 0 )
  {
    *((_QWORD *)this + 9) = Windows::Networking::UX::Internal::WlanInterface::s_WnfUIEventCallback;
    *((_QWORD *)this + 10) = a3;
    v9 = CMediaUiRequestSubscriber::InterfaceMappingCallback(this, v8, v10, v11, v15, v15, 0x1000u);
    if ( v9 >= 0 )
    {
      v9 = RtlSubscribeWnfStateChangeNotification(
             (char *)this + 8,
             *(_QWORD *)this,
             v13,
             CMediaUiRequestSubscriber::InterfaceMappingCallbackThunk,
             this,
             0,
             0,
             4);
      if ( v9 >= 0 )
      {
        v7 = 0;
        *((_BYTE *)this + 16) = 1;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        return v7;
      }
    }
  }
  v7 = v9 | 0x10000000;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
LABEL_12:
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_16;
  return v7;
}

```

## disassembly

```asm
0x1800764e4  push    rbx
0x1800764e6  push    rbp
0x1800764e7  push    rsi
0x1800764e8  push    rdi
0x1800764e9  mov     eax, 1068h
0x1800764ee  call    _alloca_probe
0x1800764f3  sub     rsp, rax
0x1800764f6  mov     rax, cs:__security_cookie
0x1800764fd  xor     rax, rsp
0x180076500  mov     [rsp+1088h+var_38], rax
0x180076508  mov     rbp, r8
0x18007650b  mov     rdi, rcx
0x18007650e  cmp     byte ptr [rcx+10h], 0
0x180076512  jnz     loc_180076660
0x180076518  mov     eax, [rcx+14h]
0x18007651b  test    eax, eax
0x18007651d  jnz     loc_180076660
0x180076523  call    cs:__imp_GetCurrentProcessId
0x180076529  lea     rdx, [rdi+18h]; pSessionId
0x18007652d  mov     ecx, eax; dwProcessId
0x18007652f  call    cs:__imp_ProcessIdToSessionId
0x180076535  test    eax, eax
0x180076537  jnz     short loc_180076557
0x180076539  call    cs:__imp_GetLastError
0x18007653f  mov     ebx, eax
0x180076541  test    eax, eax
0x180076543  jle     loc_180076649
0x180076549  movzx   ebx, ax
0x18007654c  or      ebx, 80070000h
0x180076552  jmp     loc_180076649
0x180076557  lea     rsi, [rdi+20h]
0x18007655b  mov     [rsp+1088h+var_1040], rsi
0x180076560  mov     rcx, rsi; lpCriticalSection
0x180076563  call    cs:__imp_EnterCriticalSection
0x180076569  nop
0x18007656a  cmp     byte ptr [rdi+10h], 0
0x18007656e  jz      short loc_180076583
0x180076570  mov     ebx, 8007139Fh
0x180076575  mov     rcx, rsi; lpCriticalSection
0x180076578  call    cs:__imp_LeaveCriticalSection
0x18007657e  jmp     loc_180076665
0x180076583  mov     [rsp+1088h+var_1044], 0
0x18007658b  mov     ebx, 1000h
0x180076590  mov     r8d, ebx; Size
0x180076593  xor     edx, edx; Val
0x180076595  lea     rcx, [rsp+1088h+var_1038]; void *
0x18007659a  call    memset_0
0x18007659f  mov     [rsp+1088h+var_1048], ebx
0x1800765a3  lea     rax, [rsp+1088h+var_1048]
0x1800765a8  mov     [rsp+1088h+var_1060], rax
0x1800765ad  lea     rax, [rsp+1088h+var_1038]
0x1800765b2  mov     [rsp+1088h+var_1068], rax; void *
0x1800765b7  lea     r9, [rsp+1088h+var_1044]
0x1800765bc  xor     r8d, r8d
0x1800765bf  xor     edx, edx
0x1800765c1  mov     rcx, rdi
0x1800765c4  call    cs:__imp_NtQueryWnfStateData
0x1800765ca  mov     ebx, eax
0x1800765cc  test    eax, eax
0x1800765ce  js      short loc_18007663C
0x1800765d0  lea     rax, ?s_WnfUIEventCallback@WlanInterface@Internal@UX@Networking@Windows@@KAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Windows::Networking::UX::Internal::WlanInterface::s_WnfUIEventCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800765d7  mov     [rdi+48h], rax
0x1800765db  mov     [rdi+50h], rbp
0x1800765df  mov     eax, [rsp+1088h+var_1048]
0x1800765e3  mov     [rsp+1088h+var_1058], eax; unsigned int
0x1800765e7  lea     rax, [rsp+1088h+var_1038]
0x1800765ec  mov     [rsp+1088h+var_1060], rax; void *
0x1800765f1  mov     rcx, rdi; this
0x1800765f4  call    ?InterfaceMappingCallback@CMediaUiRequestSubscriber@@AEAAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CMediaUiRequestSubscriber::InterfaceMappingCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800765f9  mov     ebx, eax
0x1800765fb  test    eax, eax
0x1800765fd  js      short loc_18007663C
0x1800765ff  lea     rcx, [rdi+8]
0x180076603  mov     [rsp+1088h+var_1050], 4
0x18007660b  mov     [rsp+1088h+var_1058], 0
0x180076613  mov     [rsp+1088h+var_1060], 0
0x18007661c  mov     [rsp+1088h+var_1068], rdi
0x180076621  lea     r9, ?InterfaceMappingCallbackThunk@CMediaUiRequestSubscriber@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CMediaUiRequestSubscriber::InterfaceMappingCallbackThunk(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180076628  mov     r8d, [rsp+1088h+var_1044]
0x18007662d  mov     rdx, [rdi]
0x180076630  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180076636  mov     ebx, eax
0x180076638  test    eax, eax
0x18007663a  jns     short loc_18007664F
0x18007663c  bts     ebx, 1Ch
0x180076640  mov     rcx, rsi; lpCriticalSection
0x180076643  call    cs:__imp_LeaveCriticalSection
0x180076649  test    ebx, ebx
0x18007664b  jns     short loc_180076675
0x18007664d  jmp     short loc_180076665
0x18007664f  xor     ebx, ebx
0x180076651  mov     byte ptr [rdi+10h], 1
0x180076655  mov     rcx, rsi; lpCriticalSection
0x180076658  call    cs:__imp_LeaveCriticalSection
0x18007665e  jmp     short loc_180076675
0x180076660  mov     ebx, 8007139Fh
0x180076665  mov     qword ptr [rdi+48h], 0
0x18007666d  mov     qword ptr [rdi+50h], 0
0x180076675  mov     eax, ebx
0x180076677  mov     rcx, [rsp+1088h+var_38]
0x18007667f  xor     rcx, rsp; StackCookie
0x180076682  call    __security_check_cookie
0x180076687  add     rsp, 1068h
0x18007668e  pop     rdi
0x18007668f  pop     rsi
0x180076690  pop     rbp
0x180076691  pop     rbx
0x180076692  retn
```
