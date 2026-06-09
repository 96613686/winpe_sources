# Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(void)

- ea: `0x180007790`
- end: `0x180007898`
- name: `?ProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@UEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceRelogger *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180003c24`
- `0x1800059a4`
- `0x180007790`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007869`

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
    if ( (unsigned int)dword_180036818 > 2
      && (qword_180036828 & 0x20000000) != 0
      && (qword_180036830 & 0x20000000) == qword_180036830 )
    {
      v10 = v3;
      v11 = 623;
      v12 = "ProcessTraces";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180036828,
        (__int64)byte_18002FB31,
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
0x180007790  mov     [rsp+arg_18], rbx
0x180007795  push    rdi
0x180007796  sub     rsp, 60h
0x18000779a  mov     rbx, rcx
0x18000779d  cmp     dword ptr [rcx+10h], 1
0x1800077a1  jz      short loc_1800077AD
0x1800077a3  mov     eax, 8007139Fh
0x1800077a8  jmp     loc_18000788A
0x1800077ad  lea     rcx, [rsp+68h+var_28]
0x1800077b2  call    ??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)
0x1800077b7  mov     rcx, rbx; this
0x1800077ba  call    ?InternalProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEventTraceRelogger::InternalProcessTraces(void)
0x1800077bf  mov     edi, eax
0x1800077c1  test    eax, eax
0x1800077c3  jns     short loc_180007843
0x1800077c5  mov     ecx, cs:dword_180036818
0x1800077cb  cmp     ecx, 2
0x1800077ce  jbe     short loc_18000783C
0x1800077d0  mov     rdx, cs:qword_180036830
0x1800077d7  mov     rcx, cs:qword_180036828
0x1800077de  mov     r8d, 20000000h
0x1800077e4  test    r8, rcx
0x1800077e7  jz      short loc_18000783C
0x1800077e9  mov     rax, rdx
0x1800077ec  and     rax, r8
0x1800077ef  cmp     rax, rdx
0x1800077f2  jnz     short loc_18000783C
0x1800077f4  mov     [rsp+68h+arg_0], edi
0x1800077f8  mov     [rsp+68h+arg_8], 26Fh
0x180007800  lea     rax, aProcesstraces; "ProcessTraces"
0x180007807  mov     [rsp+68h+arg_10], rax
0x18000780f  lea     rax, [rsp+68h+arg_0]
0x180007814  mov     [rsp+68h+var_38], rax
0x180007819  lea     rax, [rsp+68h+arg_8]
0x18000781e  mov     [rsp+68h+var_40], rax
0x180007823  lea     rax, [rsp+68h+arg_10]
0x18000782b  mov     [rsp+68h+var_48], rax
0x180007830  lea     rdx, byte_18002FB31
0x180007837  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000783c  mov     dword ptr [rbx+10h], 0
0x180007843  mov     rcx, [rbx+18h]
0x180007847  mov     rax, [rcx]
0x18000784a  mov     edx, edi
0x18000784c  mov     rax, [rax+68h]
0x180007850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007855  mov     ebx, eax
0x180007857  mov     rdi, [rsp+68h+var_28]
0x18000785c  test    rdi, rdi
0x18000785f  jz      short loc_180007888
0x180007861  mov     ecx, [rsp+68h+var_18]
0x180007865  mov     [rsp+68h+arg_0], ecx
0x180007869  call    cs:__imp_GetCurrentThread
0x18000786f  mov     rcx, rax
0x180007872  mov     r9d, 4
0x180007878  lea     r8, [rsp+68h+arg_0]
0x18000787d  xor     edx, edx
0x18000787f  mov     rax, rdi
0x180007882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007887  nop
0x180007888  mov     eax, ebx
0x18000788a  mov     rbx, [rsp+68h+arg_18]
0x180007892  add     rsp, 60h
0x180007896  pop     rdi
0x180007897  retn
```
