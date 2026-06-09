# _lambda_fbdf1e2f07ec0700b0ab1e8e2fe2ad61_::operator()

- ea: `0x1800539e0`
- end: `0x180053adb`
- name: `_lambda_fbdf1e2f07ec0700b0ab1e8e2fe2ad61_::operator()`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053228`
- `0x180053bec`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x1800533d4`
- `0x1800539e0`
- `0x180054200`
- `0x1800586c6`
- `0x180058700`
- `0x18005e010`

## string_xrefs

- `0x180053a9e`: `Reader::Reader`

## pseudocode

```c
PVOID __fastcall lambda_fbdf1e2f07ec0700b0ab1e8e2fe2ad61_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID result; // rax
  __int64 v6; // rax
  char v7; // al
  int v8; // r8d
  _QWORD v9[2]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v10[64]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+80h] [rbp-18h] BYREF

  memset_0(v10, 0, sizeof(v10));
  if ( **(_BYTE **)a1 )
    v2 = ReportIndentTracker::Enter();
  else
    v2 = ReportIndentTracker::Exit();
  v9[0] = v10;
  v9[1] = &v11;
  LOBYTE(v4) = **(_BYTE **)a1 != 0 ? 62 : 60;
  ReportIndentTracker::Format(v9, v2, v3, v4);
  result = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v6 = _com_ptr_t<_com_IIID<ISmartCardClassExtension,&__s_GUID const _GUID_8f878c32_8cc1_4984_b09a_dee6dbb9d5f8>>::operator->(*(_QWORD *)(a1 + 8) + 40LL);
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
    return (PVOID)WPP_SF_ssl(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    11,
                    v8,
                    (unsigned int)v10,
                    (__int64)"Reader::Reader",
                    v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800539e0  push    rbx
0x1800539e2  sub     rsp, 90h
0x1800539e9  mov     rax, cs:__security_cookie
0x1800539f0  xor     rax, rsp
0x1800539f3  mov     [rsp+98h+var_18], rax
0x1800539fb  mov     rbx, rcx
0x1800539fe  xor     edx, edx; Val
0x180053a00  lea     r8d, [rdx+40h]; Size
0x180053a04  lea     rcx, [rsp+98h+var_58]; void *
0x180053a09  call    memset_0
0x180053a0e  mov     rax, [rbx]
0x180053a11  cmp     byte ptr [rax], 0
0x180053a14  jz      short loc_180053A1D
0x180053a16  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x180053a1b  jmp     short loc_180053A22
0x180053a1d  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x180053a22  mov     edx, eax
0x180053a24  lea     rax, [rsp+98h+var_58]
0x180053a29  mov     [rsp+98h+var_68], rax
0x180053a2e  lea     rax, [rsp+98h+var_18]
0x180053a36  mov     [rsp+98h+var_60], rax
0x180053a3b  mov     rax, [rbx]
0x180053a3e  mov     cl, [rax]
0x180053a40  neg     cl
0x180053a42  sbb     r9b, r9b
0x180053a45  and     r9b, 2
0x180053a49  add     r9b, 3Ch ; '<'
0x180053a4d  lea     rcx, [rsp+98h+var_68]
0x180053a52  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180053a57  lea     rcx, WPP_GLOBAL_Control
0x180053a5e  mov     rax, cs:WPP_GLOBAL_Control
0x180053a65  cmp     rax, rcx
0x180053a68  jz      short loc_180053AC0
0x180053a6a  test    byte ptr [rax+1Ch], 2
0x180053a6e  jz      short loc_180053AC0
0x180053a70  cmp     byte ptr [rax+19h], 5
0x180053a74  jb      short loc_180053AC0
0x180053a76  mov     rcx, [rbx+8]
0x180053a7a  add     rcx, 28h ; '('
0x180053a7e  call    ??C?$_com_ptr_t@V?$_com_IIID@UISmartCardClassExtension@@$1?_GUID_8f878c32_8cc1_4984_b09a_dee6dbb9d5f8@@3U__s_GUID@@B@@@@QEBAPEAUISmartCardClassExtension@@XZ; _com_ptr_t<_com_IIID<ISmartCardClassExtension,&__s_GUID const _GUID_8f878c32_8cc1_4984_b09a_dee6dbb9d5f8>>::operator->(void)
0x180053a83  mov     rdx, rax
0x180053a86  mov     rcx, [rax]
0x180053a89  mov     rax, [rcx+28h]
0x180053a8d  mov     rcx, rdx
0x180053a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a95  mov     edx, 0Bh
0x180053a9a  mov     [rsp+98h+var_70], eax
0x180053a9e  lea     rax, aReaderReader; "Reader::Reader"
0x180053aa5  mov     [rsp+98h+var_78], rax
0x180053aaa  lea     r9, [rsp+98h+var_58]
0x180053aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180053ab6  mov     rcx, [rcx+10h]
0x180053aba  call    WPP_SF_ssl
0x180053abf  nop
0x180053ac0  jmp     short $+2
0x180053ac2  mov     rcx, [rsp+98h+var_18]
0x180053aca  xor     rcx, rsp; StackCookie
0x180053acd  call    __security_check_cookie
0x180053ad2  add     rsp, 90h
0x180053ad9  pop     rbx
0x180053ada  retn
```
