# Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(void)

- ea: `0x1800199c0`
- end: `0x180019acf`
- name: `?ProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@UEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceRelogger *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001320`
- `0x180015724`
- `0x180017648`
- `0x1800199c0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019a99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019a99`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(
        Microsoft::Windows::Performance::CEventTraceRelogger *this)
{
  int v3; // edi
  int v4; // r9d
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
    if ( (unsigned int)dword_18004AE58 > 2
      && (qword_18004AE68 & 0x20000000) != 0
      && (qword_18004AE70 & 0x20000000) == qword_18004AE70 )
    {
      v10 = v3;
      v11 = 623;
      v12 = "ProcessTraces";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_18004AE68,
        (unsigned int)byte_18004258B,
        0x20000000,
        v4,
        (__int64)&v12,
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
0x1800199c0  mov     [rsp+arg_18], rbx
0x1800199c5  push    rdi
0x1800199c6  sub     rsp, 60h
0x1800199ca  mov     rbx, rcx
0x1800199cd  cmp     dword ptr [rcx+10h], 1
0x1800199d1  jz      short loc_1800199DD
0x1800199d3  mov     eax, 8007139Fh
0x1800199d8  jmp     loc_180019AC0
0x1800199dd  lea     rcx, [rsp+68h+var_28]
0x1800199e2  call    ??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)
0x1800199e7  mov     rcx, rbx; this
0x1800199ea  call    ?InternalProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEventTraceRelogger::InternalProcessTraces(void)
0x1800199ef  mov     edi, eax
0x1800199f1  test    eax, eax
0x1800199f3  jns     short loc_180019A73
0x1800199f5  mov     ecx, cs:dword_18004AE58
0x1800199fb  cmp     ecx, 2
0x1800199fe  jbe     short loc_180019A6C
0x180019a00  mov     rdx, cs:qword_18004AE70
0x180019a07  mov     rcx, cs:qword_18004AE68
0x180019a0e  mov     r8d, 20000000h
0x180019a14  test    r8, rcx
0x180019a17  jz      short loc_180019A6C
0x180019a19  mov     rax, rdx
0x180019a1c  and     rax, r8
0x180019a1f  cmp     rax, rdx
0x180019a22  jnz     short loc_180019A6C
0x180019a24  mov     [rsp+68h+arg_0], edi
0x180019a28  mov     [rsp+68h+arg_8], 26Fh
0x180019a30  lea     rax, aProcesstraces; "ProcessTraces"
0x180019a37  mov     [rsp+68h+arg_10], rax
0x180019a3f  lea     rax, [rsp+68h+arg_0]
0x180019a44  mov     [rsp+68h+var_38], rax
0x180019a49  lea     rax, [rsp+68h+arg_8]
0x180019a4e  mov     [rsp+68h+var_40], rax
0x180019a53  lea     rax, [rsp+68h+arg_10]
0x180019a5b  mov     [rsp+68h+var_48], rax
0x180019a60  lea     rdx, byte_18004258B
0x180019a67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019a6c  mov     dword ptr [rbx+10h], 0
0x180019a73  mov     rcx, [rbx+18h]
0x180019a77  mov     rax, [rcx]
0x180019a7a  mov     edx, edi
0x180019a7c  mov     rax, [rax+68h]
0x180019a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a85  mov     ebx, eax
0x180019a87  mov     rdi, [rsp+68h+var_28]
0x180019a8c  test    rdi, rdi
0x180019a8f  jz      short loc_180019ABE
0x180019a91  mov     ecx, [rsp+68h+var_18]
0x180019a95  mov     [rsp+68h+arg_0], ecx
0x180019a99  call    cs:__imp_GetCurrentThread
0x180019aa0  nop     dword ptr [rax+rax+00h]
0x180019aa5  mov     rcx, rax
0x180019aa8  mov     r9d, 4
0x180019aae  lea     r8, [rsp+68h+arg_0]
0x180019ab3  xor     edx, edx
0x180019ab5  mov     rax, rdi
0x180019ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019abd  nop
0x180019abe  mov     eax, ebx
0x180019ac0  mov     rbx, [rsp+68h+arg_18]
0x180019ac8  add     rsp, 60h
0x180019acc  pop     rdi
0x180019acd  retn
```
