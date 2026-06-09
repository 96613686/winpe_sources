# wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1400022a8`
- end: `0x14000235e`
- name: `??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400063c4`
- `0x1400080c8`

## callees

- `0x140002004`
- `0x1400022a8`
- `0x1400023c0`
- `0x1400057fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400022c2`
- `KERNEL32!GetLastError` at `0x1400022c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::ReportFailure_GetLastErrorHr<1>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  DWORD LastError; // ebx
  wil::details *v12; // [rsp+30h] [rbp-68h]
  _DWORD v13[18]; // [rsp+50h] [rbp-48h] BYREF

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v12) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v12);
    LastError = 668;
  }
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v13[0] = LastError;
  v13[1] = wil::details::HrToNtStatus((wil::details *)LastError);
  v13[2] = 0;
  wil::details::ReportFailure_Base<1,0>(a1, a2, a3, a4, a5, a6, v13);
  return LastError;
}

```

## disassembly

```asm
0x1400022a8  push    rbx
0x1400022aa  push    rbp
0x1400022ab  push    rsi
0x1400022ac  push    rdi
0x1400022ad  push    r12
0x1400022af  push    r14
0x1400022b1  push    r15
0x1400022b3  sub     rsp, 60h
0x1400022b7  mov     rdi, r9
0x1400022ba  mov     rsi, r8
0x1400022bd  mov     ebp, edx
0x1400022bf  mov     r14, rcx
0x1400022c2  call    cs:__imp_GetLastError
0x1400022c8  mov     ebx, eax
0x1400022ca  mov     r15, [rsp+98h+arg_28]
0x1400022d2  mov     r12, [rsp+98h+arg_20]
0x1400022da  test    eax, eax
0x1400022dc  jnz     short loc_140002305
0x1400022de  mov     dword ptr [rsp+98h+var_68], 8007029Ch; wil::details *
0x1400022e6  mov     [rsp+98h+var_70], r15; __int64
0x1400022eb  mov     [rsp+98h+var_78], r12; __int64
0x1400022f0  mov     r9, rdi; int
0x1400022f3  mov     r8, rsi; int
0x1400022f6  mov     edx, ebp; int
0x1400022f8  mov     rcx, r14; int
0x1400022fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140002300  mov     ebx, 29Ch
0x140002305  test    ebx, ebx
0x140002307  jle     short loc_140002312
0x140002309  movzx   ebx, bx
0x14000230c  or      ebx, 80070000h
0x140002312  mov     [rsp+98h+var_48], ebx
0x140002316  mov     ecx, ebx; this
0x140002318  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000231d  mov     [rsp+98h+var_44], eax
0x140002321  mov     [rsp+98h+var_40], 0
0x140002329  lea     rax, [rsp+98h+var_48]
0x14000232e  mov     [rsp+98h+var_68], rax
0x140002333  mov     [rsp+98h+var_70], r15
0x140002338  mov     [rsp+98h+var_78], r12
0x14000233d  mov     r9, rdi
0x140002340  mov     r8, rsi
0x140002343  mov     edx, ebp
0x140002345  mov     rcx, r14
0x140002348  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000234d  mov     eax, ebx
0x14000234f  add     rsp, 60h
0x140002353  pop     r15
0x140002355  pop     r14
0x140002357  pop     r12
0x140002359  pop     rdi
0x14000235a  pop     rsi
0x14000235b  pop     rbp
0x14000235c  pop     rbx
0x14000235d  retn
```
