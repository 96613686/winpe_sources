# winrt::Microsoft::Windows::Workloads::implementation::BrokerMakeAvailableOperation(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180022dd0`
- end: `0x1800230c4`
- name: `?BrokerMakeAvailableOperation@implementation@Workloads@Windows@Microsoft@winrt@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `756`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, const OLECHAR *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001000`
- `0x180004a20`
- `0x1800119b0`
- `0x180022dd0`
- `0x180034ef0`
- `0x180035060`
- `0x18003509c`
- `0x180036140`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180023065`
- `KERNEL32!SetEvent` at `0x180023065`
- `OLEAUT32!__imp_SysAllocString` at `0x180022eb4`
- `OLEAUT32!__imp_SysAllocString` at `0x180022f22`
- `OLEAUT32!__imp_SysAllocString` at `0x180022eb4`
- `OLEAUT32!__imp_SysAllocString` at `0x180022f22`
- `OLEAUT32!__imp_SysFreeString` at `0x180022ff8`
- `OLEAUT32!__imp_SysFreeString` at `0x180023033`
- `OLEAUT32!__imp_SysFreeString` at `0x180022ff8`
- `OLEAUT32!__imp_SysFreeString` at `0x180023033`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::BrokerMakeAvailableOperation(
        PTP_CALLBACK_INSTANCE Instance,
        const OLECHAR *Context,
        PTP_WORK Work)
{
  const wchar_t *v3; // rdi
  const wchar_t *v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  const OLECHAR *v8; // rdi
  BSTR *v9; // rbx
  BSTR v10; // rax
  const OLECHAR *v11; // r14
  BSTR *v12; // rdi
  BSTR v13; // rax
  int v14; // ebp
  const wchar_t *v15; // r15
  const wchar_t *v16; // r14
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  BSTR v20; // rcx
  BSTR v21; // rcx
  const wchar_t *v22; // [rsp+40h] [rbp-48h] BYREF
  const wchar_t *v23[2]; // [rsp+48h] [rbp-40h] BYREF
  char v24; // [rsp+58h] [rbp-30h]
  const OLECHAR *v25; // [rsp+60h] [rbp-28h] BYREF

  if ( !Context )
LABEL_46:
    winrt::throw_last_error(Instance);
  v25 = Context;
  *((_DWORD *)Context + 26) = -2147467259;
  v23[1] = (const wchar_t *)&v25;
  v24 = 1;
  v3 = Context + 20;
  if ( *((_QWORD *)Context + 8) > 7u )
    v3 = *(const wchar_t **)v3;
  v4 = Context + 4;
  if ( *((_QWORD *)Context + 4) > 7u )
    v4 = *(const wchar_t **)v4;
  v5 = TraceLogger::Provider();
  if ( *(_DWORD *)v5 > 5u )
  {
    v22 = v3;
    v23[0] = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      (__int64)v5,
      (unsigned __int8 *)word_18004D6A2,
      v6,
      v7,
      v23,
      &v22);
  }
  v8 = v25 + 4;
  if ( *((_QWORD *)v25 + 4) > 7u )
    v8 = *(const OLECHAR **)v8;
  v9 = (BSTR *)operator new(0x18u);
  v23[0] = (const wchar_t *)v9;
  if ( v9 )
  {
    *(_OWORD *)v9 = 0;
    v9[2] = 0;
    v9[1] = 0;
    *((_DWORD *)v9 + 4) = 1;
    v10 = SysAllocString(v8);
    *v9 = v10;
    if ( !v10 && v8 )
      goto LABEL_44;
  }
  else
  {
    v9 = 0;
  }
  v23[0] = (const wchar_t *)v9;
  if ( !v9 )
  {
    _com_issue_error(2147942414LL);
    JUMPOUT(0x1800230C3LL);
  }
  v11 = v25 + 20;
  if ( *((_QWORD *)v25 + 8) > 7u )
    v11 = *(const OLECHAR **)v11;
  v12 = (BSTR *)operator new(0x18u);
  v22 = (const wchar_t *)v12;
  if ( v12 )
  {
    *(_OWORD *)v12 = 0;
    v12[2] = 0;
    v12[1] = 0;
    *((_DWORD *)v12 + 4) = 1;
    v13 = SysAllocString(v11);
    *v12 = v13;
    if ( !v13 && v11 )
      goto LABEL_45;
  }
  else
  {
    v12 = 0;
  }
  v22 = (const wchar_t *)v12;
  if ( !v12 )
  {
    _com_issue_error(2147942414LL);
LABEL_44:
    _com_issue_error(2147942414LL);
LABEL_45:
    _com_issue_error(2147942414LL);
    goto LABEL_46;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, BSTR, BSTR, _QWORD, _QWORD, _QWORD))(**(_QWORD **)v25 + 32LL))(
          *(_QWORD *)v25,
          *v9,
          *v12,
          *((_QWORD *)v25 + 9),
          *((_QWORD *)v25 + 10),
          *((_QWORD *)v25 + 11));
  v15 = v25 + 20;
  if ( *((_QWORD *)v25 + 8) > 7u )
    v15 = *(const wchar_t **)v15;
  v16 = v25 + 4;
  if ( *((_QWORD *)v25 + 4) > 7u )
    v16 = *(const wchar_t **)v16;
  v17 = TraceLogger::Provider();
  if ( *(_DWORD *)v17 > 5u )
  {
    v23[0] = v15;
    v22 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      (__int64)v17,
      (unsigned __int8 *)&dword_18004D654,
      v18,
      v19,
      &v22,
      v23);
  }
  *((_DWORD *)v25 + 26) = v14;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 4, 0xFFFFFFFF) == 1 )
  {
    if ( *v12 )
    {
      SysFreeString(*v12);
      *v12 = 0;
    }
    v20 = v12[1];
    if ( v20 )
    {
      operator delete(v20);
      v12[1] = 0;
    }
    operator delete(v12);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 4, 0xFFFFFFFF) == 1 )
  {
    if ( *v9 )
    {
      SysFreeString(*v9);
      *v9 = 0;
    }
    v21 = v9[1];
    if ( v21 )
    {
      operator delete(v21);
      v9[1] = 0;
    }
    operator delete(v9);
  }
  SetEvent(*((HANDLE *)v25 + 12));
}

```

## disassembly

```asm
0x180022dd0  mov     [rsp+arg_0], rbx
0x180022dd5  mov     [rsp+arg_10], rbp
0x180022dda  mov     [rsp+arg_18], rsi
0x180022ddf  push    rdi
0x180022de0  push    r14
0x180022de2  push    r15
0x180022de4  sub     rsp, 70h
0x180022de8  mov     rax, cs:__security_cookie
0x180022def  xor     rax, rsp
0x180022df2  mov     [rsp+88h+var_20], rax
0x180022df7  test    rdx, rdx
0x180022dfa  jz      loc_1800230B3
0x180022e00  mov     [rsp+88h+var_28], rdx
0x180022e05  mov     dword ptr [rdx+68h], 80004005h
0x180022e0c  lea     rax, [rsp+88h+var_28]
0x180022e11  mov     [rsp+88h+var_38], rax
0x180022e16  mov     [rsp+88h+var_30], 1
0x180022e1b  lea     rdi, [rdx+28h]
0x180022e1f  cmp     qword ptr [rdi+18h], 7
0x180022e24  jbe     short loc_180022E29
0x180022e26  mov     rdi, [rdi]
0x180022e29  lea     rbx, [rdx+8]
0x180022e2d  cmp     qword ptr [rbx+18h], 7
0x180022e32  jbe     short loc_180022E37
0x180022e34  mov     rbx, [rbx]
0x180022e37  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180022e3c  cmp     dword ptr [rax], 5
0x180022e3f  jbe     short loc_180022E6E
0x180022e41  mov     [rsp+88h+var_48], rdi
0x180022e46  mov     [rsp+88h+var_40], rbx
0x180022e4b  lea     rcx, [rsp+88h+var_48]
0x180022e50  mov     [rsp+88h+var_60], rcx
0x180022e55  lea     rcx, [rsp+88h+var_40]
0x180022e5a  mov     [rsp+88h+var_68], rcx
0x180022e5f  lea     rdx, word_18004D6A2
0x180022e66  mov     rcx, rax
0x180022e69  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180022e6e  mov     rdi, [rsp+88h+var_28]
0x180022e73  add     rdi, 8
0x180022e77  cmp     qword ptr [rdi+18h], 7
0x180022e7c  jbe     short loc_180022E81
0x180022e7e  mov     rdi, [rdi]
0x180022e81  mov     ecx, 18h; Size
0x180022e86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022e8b  mov     rbx, rax
0x180022e8e  mov     [rsp+88h+var_40], rax
0x180022e93  xor     esi, esi
0x180022e95  test    rax, rax
0x180022e98  jz      short loc_180022ECD
0x180022e9a  xorps   xmm0, xmm0
0x180022e9d  xor     eax, eax
0x180022e9f  movups  xmmword ptr [rbx], xmm0
0x180022ea2  mov     [rbx+10h], rax
0x180022ea6  mov     [rbx+8], rsi
0x180022eaa  mov     dword ptr [rbx+10h], 1
0x180022eb1  mov     rcx, rdi; psz
0x180022eb4  call    cs:__imp_SysAllocString
0x180022eba  mov     [rbx], rax
0x180022ebd  test    rax, rax
0x180022ec0  jnz     short loc_180022ED0
0x180022ec2  test    rdi, rdi
0x180022ec5  jnz     loc_18002309D
0x180022ecb  jmp     short loc_180022ED0
0x180022ecd  mov     rbx, rsi
0x180022ed0  mov     [rsp+88h+var_40], rbx
0x180022ed5  test    rbx, rbx
0x180022ed8  jz      loc_1800230B9
0x180022ede  mov     r14, [rsp+88h+var_28]
0x180022ee3  add     r14, 28h ; '('
0x180022ee7  cmp     qword ptr [r14+18h], 7
0x180022eec  jbe     short loc_180022EF1
0x180022eee  mov     r14, [r14]
0x180022ef1  mov     ecx, 18h; Size
0x180022ef6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022efb  mov     rdi, rax
0x180022efe  mov     [rsp+88h+var_48], rax
0x180022f03  test    rax, rax
0x180022f06  jz      short loc_180022F3B
0x180022f08  xorps   xmm0, xmm0
0x180022f0b  xor     eax, eax
0x180022f0d  movups  xmmword ptr [rdi], xmm0
0x180022f10  mov     [rdi+10h], rax
0x180022f14  mov     [rdi+8], rsi
0x180022f18  mov     dword ptr [rdi+10h], 1
0x180022f1f  mov     rcx, r14; psz
0x180022f22  call    cs:__imp_SysAllocString
0x180022f28  mov     [rdi], rax
0x180022f2b  test    rax, rax
0x180022f2e  jnz     short loc_180022F3E
0x180022f30  test    r14, r14
0x180022f33  jnz     loc_1800230A8
0x180022f39  jmp     short loc_180022F3E
0x180022f3b  mov     rdi, rsi
0x180022f3e  mov     [rsp+88h+var_48], rdi
0x180022f43  test    rdi, rdi
0x180022f46  jz      loc_180023092
0x180022f4c  mov     r9, [rsp+88h+var_28]
0x180022f51  mov     rcx, [r9]
0x180022f54  mov     rax, [rcx]
0x180022f57  mov     rdx, [r9+58h]
0x180022f5b  mov     [rsp+88h+var_60], rdx
0x180022f60  mov     rdx, [r9+50h]
0x180022f64  mov     [rsp+88h+var_68], rdx
0x180022f69  mov     r9, [r9+48h]
0x180022f6d  mov     r8, [rdi]
0x180022f70  mov     rdx, [rbx]
0x180022f73  mov     rax, [rax+20h]
0x180022f77  call    cs:__guard_dispatch_icall_fptr
0x180022f7d  mov     ebp, eax
0x180022f7f  mov     r14, [rsp+88h+var_28]
0x180022f84  lea     r15, [r14+28h]
0x180022f88  cmp     qword ptr [r15+18h], 7
0x180022f8d  jbe     short loc_180022F92
0x180022f8f  mov     r15, [r15]
0x180022f92  add     r14, 8
0x180022f96  cmp     qword ptr [r14+18h], 7
0x180022f9b  jbe     short loc_180022FA0
0x180022f9d  mov     r14, [r14]
0x180022fa0  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180022fa5  cmp     dword ptr [rax], 5
0x180022fa8  jbe     short loc_180022FD7
0x180022faa  mov     [rsp+88h+var_40], r15
0x180022faf  mov     [rsp+88h+var_48], r14
0x180022fb4  lea     rcx, [rsp+88h+var_40]
0x180022fb9  mov     [rsp+88h+var_60], rcx
0x180022fbe  lea     rcx, [rsp+88h+var_48]
0x180022fc3  mov     [rsp+88h+var_68], rcx
0x180022fc8  lea     rdx, dword_18004D654
0x180022fcf  mov     rcx, rax
0x180022fd2  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180022fd7  mov     rax, [rsp+88h+var_28]
0x180022fdc  mov     [rax+68h], ebp
0x180022fdf  mov     ebp, 0FFFFFFFFh
0x180022fe4  mov     eax, ebp
0x180022fe6  lock xadd [rdi+10h], eax
0x180022feb  cmp     eax, 1
0x180022fee  jnz     short loc_180023021
0x180022ff0  mov     rcx, [rdi]; bstrString
0x180022ff3  test    rcx, rcx
0x180022ff6  jz      short loc_180023001
0x180022ff8  call    cs:__imp_SysFreeString
0x180022ffe  mov     [rdi], rsi
0x180023001  mov     rcx, [rdi+8]; void *
0x180023005  test    rcx, rcx
0x180023008  jz      short loc_180023013
0x18002300a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002300f  mov     [rdi+8], rsi
0x180023013  mov     edx, 18h; unsigned __int64
0x180023018  mov     rcx, rdi; void *
0x18002301b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023020  nop
0x180023021  lock xadd [rbx+10h], ebp
0x180023026  cmp     ebp, 1
0x180023029  jnz     short loc_18002305C
0x18002302b  mov     rcx, [rbx]; bstrString
0x18002302e  test    rcx, rcx
0x180023031  jz      short loc_18002303C
0x180023033  call    cs:__imp_SysFreeString
0x180023039  mov     [rbx], rsi
0x18002303c  mov     rcx, [rbx+8]; void *
0x180023040  test    rcx, rcx
0x180023043  jz      short loc_18002304E
0x180023045  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002304a  mov     [rbx+8], rsi
0x18002304e  mov     edx, 18h; unsigned __int64
0x180023053  mov     rcx, rbx; void *
0x180023056  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002305b  nop
0x18002305c  mov     rcx, [rsp+88h+var_28]
0x180023061  mov     rcx, [rcx+60h]; hEvent
0x180023065  call    cs:__imp_SetEvent
0x18002306b  mov     rcx, [rsp+88h+var_20]
0x180023070  xor     rcx, rsp; StackCookie
0x180023073  call    __security_check_cookie
0x180023078  lea     r11, [rsp+88h+var_18]
0x18002307d  mov     rbx, [r11+20h]
0x180023081  mov     rbp, [r11+30h]
0x180023085  mov     rsi, [r11+38h]
0x180023089  mov     rsp, r11
0x18002308c  pop     r15
0x18002308e  pop     r14
0x180023090  pop     rdi
0x180023091  retn
0x180023092  mov     ecx, 8007000Eh; int
0x180023097  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002309c  nop
0x18002309d  mov     ecx, 8007000Eh; int
0x1800230a2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800230a7  nop
0x1800230a8  mov     ecx, 8007000Eh; int
0x1800230ad  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800230b2  nop
0x1800230b3  call    ?throw_last_error@winrt@@YAXXZ; winrt::throw_last_error(void)
0x1800230b9  mov     ecx, 8007000Eh; int
0x1800230be  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
