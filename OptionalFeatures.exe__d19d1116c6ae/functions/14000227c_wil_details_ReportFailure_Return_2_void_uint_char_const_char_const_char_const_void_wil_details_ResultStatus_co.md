# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000227c`
- end: `0x14000239b`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001ad4`

## callees

- `0x14000187f`
- `0x14000227c`
- `0x140003740`
- `0x140004850`
- `0x140004ba0`
- `0x140004c30`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // [rsp+48h] [rbp-1530h]
  _BYTE v16[160]; // [rsp+80h] [rbp-14F8h] BYREF
  _BYTE v17[1024]; // [rsp+120h] [rbp-1458h] BYREF
  _BYTE v18[4096]; // [rsp+520h] [rbp-1058h] BYREF

  memset_0(v16, 0, 0x98u);
  LOBYTE(v15) = 0;
  wil::details::LogFailure(
    a1,
    a2,
    a3,
    a4,
    a5,
    a6,
    2,
    a7,
    a8,
    v15,
    (wil *)v18,
    2048,
    v17,
    1024,
    a10,
    (unsigned __int64)v16);
  if ( (v16[4] & 1) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v14);
}

```

## disassembly

```asm
0x14000227c  push    rbx
0x14000227e  push    rbp
0x14000227f  push    rsi
0x140002280  push    rdi
0x140002281  push    r12
0x140002283  push    r13
0x140002285  push    r14
0x140002287  push    r15
0x140002289  mov     eax, 1538h
0x14000228e  call    _alloca_probe
0x140002293  sub     rsp, rax
0x140002296  mov     rax, cs:__security_cookie
0x14000229d  xor     rax, rsp
0x1400022a0  mov     [rsp+1578h+var_58], rax
0x1400022a8  mov     rbp, [rsp+1578h+arg_20]
0x1400022b0  mov     r12, r8
0x1400022b3  mov     rsi, [rsp+1578h+arg_28]
0x1400022bb  mov     r15d, edx
0x1400022be  mov     rdi, [rsp+1578h+arg_30]
0x1400022c6  mov     r14, rcx
0x1400022c9  mov     rbx, [rsp+1578h+arg_38]
0x1400022d1  lea     rcx, [rsp+1578h+var_14F8]; void *
0x1400022d9  xor     edx, edx; Val
0x1400022db  mov     r8d, 98h; Size
0x1400022e1  mov     r13, r9
0x1400022e4  call    memset_0
0x1400022e9  lea     rax, [rsp+1578h+var_14F8]
0x1400022f1  mov     r9, r13
0x1400022f4  mov     [rsp+1578h+var_1500], rax
0x1400022f9  mov     r8, r12
0x1400022fc  mov     eax, [rsp+1578h+arg_48]
0x140002303  mov     edx, r15d
0x140002306  mov     [rsp+1578h+var_1508], eax
0x14000230a  mov     rcx, r14
0x14000230d  mov     [rsp+1578h+var_1510], 400h
0x140002316  lea     rax, [rsp+1578h+var_1458]
0x14000231e  mov     [rsp+1578h+var_1518], rax
0x140002323  lea     rax, [rsp+1578h+var_1058]
0x14000232b  mov     [rsp+1578h+var_1520], 800h
0x140002334  mov     [rsp+1578h+var_1528], rax
0x140002339  mov     byte ptr [rsp+1578h+var_1530], 0
0x14000233e  mov     [rsp+1578h+var_1538], rbx
0x140002343  mov     [rsp+1578h+var_1540], rdi
0x140002348  mov     [rsp+1578h+var_1548], 2
0x140002350  mov     [rsp+1578h+var_1550], rsi
0x140002355  mov     [rsp+1578h+var_1558], rbp
0x14000235a  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x14000235f  test    [rsp+1578h+var_14F4], 1
0x140002367  jnz     short loc_14000238D
0x140002369  mov     rcx, [rsp+1578h+var_58]
0x140002371  xor     rcx, rsp; StackCookie
0x140002374  call    __security_check_cookie
0x140002379  add     rsp, 1538h
0x140002380  pop     r15
0x140002382  pop     r14
0x140002384  pop     r13
0x140002386  pop     r12
0x140002388  pop     rdi
0x140002389  pop     rsi
0x14000238a  pop     rbp
0x14000238b  pop     rbx
0x14000238c  retn
0x14000238d  lea     rcx, [rsp+1578h+var_14F8]; this
0x140002395  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
