# _lambda_4b219dab6383df0d1036cf0d043e8b2c_::operator()

- ea: `0x1800535ec`
- end: `0x1800536e7`
- name: `_lambda_4b219dab6383df0d1036cf0d043e8b2c_::operator()`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053328`
- `0x180053b3c`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x1800533d4`
- `0x1800535ec`
- `0x180054200`
- `0x1800586c6`
- `0x180058700`
- `0x18005e010`

## string_xrefs

- `0x1800536aa`: `Reader::~Reader`

## pseudocode

```c
PVOID __fastcall lambda_4b219dab6383df0d1036cf0d043e8b2c_::operator()(__int64 a1)
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
                    10,
                    v8,
                    (unsigned int)v10,
                    (__int64)"Reader::~Reader",
                    v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800535ec  push    rbx
0x1800535ee  sub     rsp, 90h
0x1800535f5  mov     rax, cs:__security_cookie
0x1800535fc  xor     rax, rsp
0x1800535ff  mov     [rsp+98h+var_18], rax
0x180053607  mov     rbx, rcx
0x18005360a  xor     edx, edx; Val
0x18005360c  lea     r8d, [rdx+40h]; Size
0x180053610  lea     rcx, [rsp+98h+var_58]; void *
0x180053615  call    memset_0
0x18005361a  mov     rax, [rbx]
0x18005361d  cmp     byte ptr [rax], 0
0x180053620  jz      short loc_180053629
0x180053622  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x180053627  jmp     short loc_18005362E
0x180053629  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x18005362e  mov     edx, eax
0x180053630  lea     rax, [rsp+98h+var_58]
0x180053635  mov     [rsp+98h+var_68], rax
0x18005363a  lea     rax, [rsp+98h+var_18]
0x180053642  mov     [rsp+98h+var_60], rax
0x180053647  mov     rax, [rbx]
0x18005364a  mov     cl, [rax]
0x18005364c  neg     cl
0x18005364e  sbb     r9b, r9b
0x180053651  and     r9b, 2
0x180053655  add     r9b, 3Ch ; '<'
0x180053659  lea     rcx, [rsp+98h+var_68]
0x18005365e  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180053663  lea     rcx, WPP_GLOBAL_Control
0x18005366a  mov     rax, cs:WPP_GLOBAL_Control
0x180053671  cmp     rax, rcx
0x180053674  jz      short loc_1800536CC
0x180053676  test    byte ptr [rax+1Ch], 2
0x18005367a  jz      short loc_1800536CC
0x18005367c  cmp     byte ptr [rax+19h], 5
0x180053680  jb      short loc_1800536CC
0x180053682  mov     rcx, [rbx+8]
0x180053686  add     rcx, 28h ; '('
0x18005368a  call    ??C?$_com_ptr_t@V?$_com_IIID@UISmartCardClassExtension@@$1?_GUID_8f878c32_8cc1_4984_b09a_dee6dbb9d5f8@@3U__s_GUID@@B@@@@QEBAPEAUISmartCardClassExtension@@XZ; _com_ptr_t<_com_IIID<ISmartCardClassExtension,&__s_GUID const _GUID_8f878c32_8cc1_4984_b09a_dee6dbb9d5f8>>::operator->(void)
0x18005368f  mov     rdx, rax
0x180053692  mov     rcx, [rax]
0x180053695  mov     rax, [rcx+28h]
0x180053699  mov     rcx, rdx
0x18005369c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536a1  mov     edx, 0Ah
0x1800536a6  mov     [rsp+98h+var_70], eax
0x1800536aa  lea     rax, aReaderReader_0; "Reader::~Reader"
0x1800536b1  mov     [rsp+98h+var_78], rax
0x1800536b6  lea     r9, [rsp+98h+var_58]
0x1800536bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800536c2  mov     rcx, [rcx+10h]
0x1800536c6  call    WPP_SF_ssl
0x1800536cb  nop
0x1800536cc  jmp     short $+2
0x1800536ce  mov     rcx, [rsp+98h+var_18]
0x1800536d6  xor     rcx, rsp; StackCookie
0x1800536d9  call    __security_check_cookie
0x1800536de  add     rsp, 90h
0x1800536e5  pop     rbx
0x1800536e6  retn
```
