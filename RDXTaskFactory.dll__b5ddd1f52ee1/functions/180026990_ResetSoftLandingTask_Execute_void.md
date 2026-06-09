# ResetSoftLandingTask::Execute(void)

- ea: `0x180026990`
- end: `0x180026a6c`
- name: `?Execute@ResetSoftLandingTask@@MEAAXXZ`
- size: `220`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x18001094c`
- `0x180024a48`
- `0x1800266e8`
- `0x180026990`
- `0x18002fc68`
- `0x180050010`

## import_xrefs

- `SHCORE!SHDeleteKeyW` at `0x1800269c1`
- `SHCORE!SHDeleteKeyW` at `0x1800269c1`

## string_xrefs

- `0x1800269d2`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetsoftlandingtask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ResetSoftLandingTask::Execute(HSTRING *this)
{
  LSTATUS v2; // eax
  __int64 (__fastcall ***v3)(); // rdx
  HSTRING v4; // [rsp+20h] [rbp-19h] BYREF
  _BYTE v5[24]; // [rsp+28h] [rbp-11h] BYREF
  __int64 (__fastcall **v6)(); // [rsp+40h] [rbp+7h] BYREF
  __int128 v7; // [rsp+48h] [rbp+Fh]
  __int64 (__fastcall ***v8)(); // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v2 = SHDeleteKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SoftLanding");
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetsoftlandingtask.cpp",
      (const char *)(unsigned int)v2,
      (int)v4);
  LODWORD(v4) = 0;
  v8 = 0;
  v6 = off_180052BA0;
  v7 = *(_OWORD *)_lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(
                    (_lambda_6d98a26ab645bb601d6c6842c9556ef9_ *)v5,
                    this,
                    &v4);
  v8 = &v6;
  RetailDemoUtil::ExecuteAsDemoUser(&v6);
  if ( v8 )
  {
    v3 = &v6;
    LOBYTE(v3) = v8 != &v6;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v8)[4])(v8, v3);
  }
  RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<24,long>((unsigned int)v4);
}

```

## disassembly

```asm
0x180026990  mov     [rsp-8+arg_0], rbx
0x180026995  push    rbp
0x180026996  lea     rbp, [rsp-57h]
0x18002699b  sub     rsp, 90h
0x1800269a2  mov     rax, cs:__security_cookie
0x1800269a9  xor     rax, rsp
0x1800269ac  mov     [rbp+57h+var_10], rax
0x1800269b0  mov     rbx, rcx
0x1800269b3  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800269ba  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800269c1  call    cs:__imp_SHDeleteKeyW
0x1800269c7  mov     rcx, [rbp+5Fh]; this
0x1800269cb  test    eax, eax
0x1800269cd  jns     short loc_1800269E4
0x1800269cf  mov     r9d, eax; char *
0x1800269d2  lea     r8, aPcshellShellRe_23; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800269d9  mov     edx, 25h ; '%'; void *
0x1800269de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800269e4  mov     dword ptr [rbp+57h+var_70], 0
0x1800269eb  mov     [rbp+57h+var_18], 0
0x1800269f3  lea     rax, off_180052BA0
0x1800269fa  mov     [rbp+57h+var_50], rax
0x1800269fe  lea     r8, [rbp+57h+var_70]; HSTRING *
0x180026a02  mov     rdx, rbx; HSTRING *
0x180026a05  lea     rcx, [rbp+57h+var_68]; this
0x180026a09  call    ??0_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@QEAA@AEAPEAUHSTRING__@@0@Z; _lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(HSTRING__ * &,HSTRING__ * &)
0x180026a0e  movups  xmm0, xmmword ptr [rax]
0x180026a11  movdqu  [rbp+57h+var_48], xmm0
0x180026a16  lea     rax, [rbp+57h+var_50]
0x180026a1a  mov     [rbp+57h+var_18], rax
0x180026a1e  lea     rcx, [rbp+57h+var_50]
0x180026a22  call    ?ExecuteAsDemoUser@RetailDemoUtil@@YAXAEBV?$function@$$A6AXXZ@std@@@Z; RetailDemoUtil::ExecuteAsDemoUser(std::function<void (void)> const &)
0x180026a27  nop
0x180026a28  mov     rcx, [rbp+57h+var_18]
0x180026a2c  test    rcx, rcx
0x180026a2f  jz      short loc_180026A47
0x180026a31  mov     rax, [rcx]
0x180026a34  lea     rdx, [rbp+57h+var_50]
0x180026a38  cmp     rcx, rdx
0x180026a3b  setnz   dl
0x180026a3e  mov     rax, [rax+20h]
0x180026a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a47  mov     ecx, dword ptr [rbp+57h+var_70]
0x180026a4a  call    ??$HandleEvent@$0BI@J@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@SAXJ@Z; RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<24,long>(long)
0x180026a4f  mov     rcx, [rbp+57h+var_10]
0x180026a53  xor     rcx, rsp; StackCookie
0x180026a56  call    __security_check_cookie
0x180026a5b  mov     rbx, [rsp+90h+arg_0]
0x180026a63  add     rsp, 90h
0x180026a6a  pop     rbp
0x180026a6b  retn
```
