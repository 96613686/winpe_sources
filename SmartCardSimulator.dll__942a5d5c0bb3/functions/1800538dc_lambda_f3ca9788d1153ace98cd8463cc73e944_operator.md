# _lambda_f3ca9788d1153ace98cd8463cc73e944_::operator()

- ea: `0x1800538dc`
- end: `0x1800539d7`
- name: `_lambda_f3ca9788d1153ace98cd8463cc73e944_::operator()`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053bc0`
- `0x180053cac`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x1800533d4`
- `0x1800538dc`
- `0x180054200`
- `0x1800586c6`
- `0x180058700`
- `0x18005e010`

## string_xrefs

- `0x18005399a`: `Reader::CardPowerOn`

## pseudocode

```c
PVOID __fastcall lambda_f3ca9788d1153ace98cd8463cc73e944_::operator()(__int64 a1)
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
                    12,
                    v8,
                    (unsigned int)v10,
                    (__int64)"Reader::CardPowerOn",
                    v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800538dc  push    rbx
0x1800538de  sub     rsp, 90h
0x1800538e5  mov     rax, cs:__security_cookie
0x1800538ec  xor     rax, rsp
0x1800538ef  mov     [rsp+98h+var_18], rax
0x1800538f7  mov     rbx, rcx
0x1800538fa  xor     edx, edx; Val
0x1800538fc  lea     r8d, [rdx+40h]; Size
0x180053900  lea     rcx, [rsp+98h+var_58]; void *
0x180053905  call    memset_0
0x18005390a  mov     rax, [rbx]
0x18005390d  cmp     byte ptr [rax], 0
0x180053910  jz      short loc_180053919
0x180053912  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x180053917  jmp     short loc_18005391E
0x180053919  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x18005391e  mov     edx, eax
0x180053920  lea     rax, [rsp+98h+var_58]
0x180053925  mov     [rsp+98h+var_68], rax
0x18005392a  lea     rax, [rsp+98h+var_18]
0x180053932  mov     [rsp+98h+var_60], rax
0x180053937  mov     rax, [rbx]
0x18005393a  mov     cl, [rax]
0x18005393c  neg     cl
0x18005393e  sbb     r9b, r9b
0x180053941  and     r9b, 2
0x180053945  add     r9b, 3Ch ; '<'
0x180053949  lea     rcx, [rsp+98h+var_68]
0x18005394e  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180053953  lea     rcx, WPP_GLOBAL_Control
0x18005395a  mov     rax, cs:WPP_GLOBAL_Control
0x180053961  cmp     rax, rcx
0x180053964  jz      short loc_1800539BC
0x180053966  test    byte ptr [rax+1Ch], 2
0x18005396a  jz      short loc_1800539BC
0x18005396c  cmp     byte ptr [rax+19h], 5
0x180053970  jb      short loc_1800539BC
0x180053972  mov     rcx, [rbx+8]
0x180053976  add     rcx, 28h ; '('
0x18005397a  call    ??C?$_com_ptr_t@V?$_com_IIID@UISmartCardClassExtension@@$1?_GUID_8f878c32_8cc1_4984_b09a_dee6dbb9d5f8@@3U__s_GUID@@B@@@@QEBAPEAUISmartCardClassExtension@@XZ; _com_ptr_t<_com_IIID<ISmartCardClassExtension,&__s_GUID const _GUID_8f878c32_8cc1_4984_b09a_dee6dbb9d5f8>>::operator->(void)
0x18005397f  mov     rdx, rax
0x180053982  mov     rcx, [rax]
0x180053985  mov     rax, [rcx+28h]
0x180053989  mov     rcx, rdx
0x18005398c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053991  mov     edx, 0Ch
0x180053996  mov     [rsp+98h+var_70], eax
0x18005399a  lea     rax, aReaderCardpowe; "Reader::CardPowerOn"
0x1800539a1  mov     [rsp+98h+var_78], rax
0x1800539a6  lea     r9, [rsp+98h+var_58]
0x1800539ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539b2  mov     rcx, [rcx+10h]
0x1800539b6  call    WPP_SF_ssl
0x1800539bb  nop
0x1800539bc  jmp     short $+2
0x1800539be  mov     rcx, [rsp+98h+var_18]
0x1800539c6  xor     rcx, rsp; StackCookie
0x1800539c9  call    __security_check_cookie
0x1800539ce  add     rsp, 90h
0x1800539d5  pop     rbx
0x1800539d6  retn
```
