# Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(void)

- ea: `0x180018c40`
- end: `0x180018d48`
- name: `?ProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@UEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceRelogger *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001318`
- `0x180014c44`
- `0x180016a50`
- `0x180018c40`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018d19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018d19`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(
        Microsoft::Windows::Performance::CEventTraceRelogger *this)
{
  int v3; // edi
  __int64 v4; // r9
  unsigned int v5; // ebx
  void (__fastcall *v6)(HANDLE, _QWORD, int *, __int64); // rdi
  HANDLE CurrentThread; // rax
  void (__fastcall *v8[2])(HANDLE, _QWORD, int *, __int64); // [rsp+40h] [rbp-28h] BYREF
  int v9; // [rsp+50h] [rbp-18h]
  int v10; // [rsp+70h] [rbp+8h] BYREF
  int v11; // [rsp+78h] [rbp+10h] BYREF
  const char *v12; // [rsp+80h] [rbp+18h] BYREF

  if ( *((_DWORD *)this + 4) != 1 )
    return 2147947423LL;
  Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>((__int64)v8);
  v3 = Microsoft::Windows::Performance::CEventTraceRelogger::InternalProcessTraces(this);
  if ( v3 < 0 )
  {
    if ( (unsigned int)dword_180048E58 > 2
      && (qword_180048E68 & 0x20000000) != 0
      && (qword_180048E70 & 0x20000000) == qword_180048E70 )
    {
      v10 = v3;
      v11 = 623;
      v12 = "ProcessTraces";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180048E68,
        (__int64)byte_18004058B,
        0x20000000,
        v4,
        (const unsigned __int16 **)&v12,
        (__int64)&v11,
        (__int64)&v10);
    }
    *((_DWORD *)this + 4) = 0;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 104LL))(
         *((_QWORD *)this + 3),
         (unsigned int)v3);
  v6 = v8[0];
  if ( v8[0] )
  {
    v10 = v9;
    CurrentThread = GetCurrentThread();
    v6(CurrentThread, 0, &v10, 4);
  }
  return v5;
}

```

## disassembly

```asm
0x180018c40  mov     [rsp+arg_18], rbx
0x180018c45  push    rdi
0x180018c46  sub     rsp, 60h
0x180018c4a  mov     rbx, rcx
0x180018c4d  cmp     dword ptr [rcx+10h], 1
0x180018c51  jz      short loc_180018C5D
0x180018c53  mov     eax, 8007139Fh
0x180018c58  jmp     loc_180018D3A
0x180018c5d  lea     rcx, [rsp+68h+var_28]
0x180018c62  call    ??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)
0x180018c67  mov     rcx, rbx; this
0x180018c6a  call    ?InternalProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEventTraceRelogger::InternalProcessTraces(void)
0x180018c6f  mov     edi, eax
0x180018c71  test    eax, eax
0x180018c73  jns     short loc_180018CF3
0x180018c75  mov     ecx, cs:dword_180048E58
0x180018c7b  cmp     ecx, 2
0x180018c7e  jbe     short loc_180018CEC
0x180018c80  mov     rdx, cs:qword_180048E70
0x180018c87  mov     rcx, cs:qword_180048E68
0x180018c8e  mov     r8d, 20000000h
0x180018c94  test    r8, rcx
0x180018c97  jz      short loc_180018CEC
0x180018c99  mov     rax, rdx
0x180018c9c  and     rax, r8
0x180018c9f  cmp     rax, rdx
0x180018ca2  jnz     short loc_180018CEC
0x180018ca4  mov     [rsp+68h+arg_0], edi
0x180018ca8  mov     [rsp+68h+arg_8], 26Fh
0x180018cb0  lea     rax, aProcesstraces; "ProcessTraces"
0x180018cb7  mov     [rsp+68h+arg_10], rax
0x180018cbf  lea     rax, [rsp+68h+arg_0]
0x180018cc4  mov     [rsp+68h+var_38], rax
0x180018cc9  lea     rax, [rsp+68h+arg_8]
0x180018cce  mov     [rsp+68h+var_40], rax
0x180018cd3  lea     rax, [rsp+68h+arg_10]
0x180018cdb  mov     [rsp+68h+var_48], rax
0x180018ce0  lea     rdx, byte_18004058B
0x180018ce7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018cec  mov     dword ptr [rbx+10h], 0
0x180018cf3  mov     rcx, [rbx+18h]
0x180018cf7  mov     rax, [rcx]
0x180018cfa  mov     edx, edi
0x180018cfc  mov     rax, [rax+68h]
0x180018d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d05  mov     ebx, eax
0x180018d07  mov     rdi, [rsp+68h+var_28]
0x180018d0c  test    rdi, rdi
0x180018d0f  jz      short loc_180018D38
0x180018d11  mov     ecx, [rsp+68h+var_18]
0x180018d15  mov     [rsp+68h+arg_0], ecx
0x180018d19  call    cs:__imp_GetCurrentThread
0x180018d1f  mov     rcx, rax
0x180018d22  mov     r9d, 4
0x180018d28  lea     r8, [rsp+68h+arg_0]
0x180018d2d  xor     edx, edx
0x180018d2f  mov     rax, rdi
0x180018d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d37  nop
0x180018d38  mov     eax, ebx
0x180018d3a  mov     rbx, [rsp+68h+arg_18]
0x180018d42  add     rsp, 60h
0x180018d46  pop     rdi
0x180018d47  retn
```
