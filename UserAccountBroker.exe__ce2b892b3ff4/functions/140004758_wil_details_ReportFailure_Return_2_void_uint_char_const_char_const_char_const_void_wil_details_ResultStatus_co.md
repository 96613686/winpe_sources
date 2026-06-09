# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004758`
- end: `0x140004877`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `287`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64, __int64, __int64, __int64, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140003fb0`

## callees

- `0x14000195f`
- `0x140004758`
- `0x140005cd4`
- `0x1400069e0`
- `0x140006b90`
- `0x140006c20`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  __int64 result; // rax
  const struct wil::FailureInfo *v15; // rdx
  char v16; // [rsp+48h] [rbp-1530h]
  _BYTE v17[160]; // [rsp+80h] [rbp-14F8h] BYREF
  _BYTE v18[1024]; // [rsp+120h] [rbp-1458h] BYREF
  _BYTE v19[4096]; // [rsp+520h] [rbp-1058h] BYREF

  memset_0(v17, 0, 0x98u);
  v16 = 0;
  result = wil::details::LogFailure(a1, a2, a3, a4, a5, a6, 2, a7, a8, v16, v19, 2048, v18, 1024, a10, v17);
  if ( (v17[4] & 1) != 0 )
    wil::details::WilFailFast((wil::details *)v17, v15);
  return result;
}

```

## disassembly

```asm
0x140004758  push    rbx
0x14000475a  push    rbp
0x14000475b  push    rsi
0x14000475c  push    rdi
0x14000475d  push    r12
0x14000475f  push    r13
0x140004761  push    r14
0x140004763  push    r15
0x140004765  mov     eax, 1538h
0x14000476a  call    _alloca_probe
0x14000476f  sub     rsp, rax
0x140004772  mov     rax, cs:__security_cookie
0x140004779  xor     rax, rsp
0x14000477c  mov     [rsp+1578h+var_58], rax
0x140004784  mov     rbp, [rsp+1578h+arg_20]
0x14000478c  mov     r12, r8
0x14000478f  mov     rsi, [rsp+1578h+arg_28]
0x140004797  mov     r15d, edx
0x14000479a  mov     rdi, [rsp+1578h+arg_30]
0x1400047a2  mov     r14, rcx
0x1400047a5  mov     rbx, [rsp+1578h+arg_38]
0x1400047ad  lea     rcx, [rsp+1578h+var_14F8]; void *
0x1400047b5  xor     edx, edx; Val
0x1400047b7  mov     r8d, 98h; Size
0x1400047bd  mov     r13, r9
0x1400047c0  call    memset_0
0x1400047c5  lea     rax, [rsp+1578h+var_14F8]
0x1400047cd  mov     r9, r13
0x1400047d0  mov     [rsp+1578h+var_1500], rax
0x1400047d5  mov     r8, r12
0x1400047d8  mov     eax, [rsp+1578h+arg_48]
0x1400047df  mov     edx, r15d
0x1400047e2  mov     [rsp+1578h+var_1508], eax
0x1400047e6  mov     rcx, r14
0x1400047e9  mov     [rsp+1578h+var_1510], 400h
0x1400047f2  lea     rax, [rsp+1578h+var_1458]
0x1400047fa  mov     [rsp+1578h+var_1518], rax
0x1400047ff  lea     rax, [rsp+1578h+var_1058]
0x140004807  mov     [rsp+1578h+var_1520], 800h
0x140004810  mov     [rsp+1578h+var_1528], rax
0x140004815  mov     [rsp+1578h+var_1530], 0
0x14000481a  mov     [rsp+1578h+var_1538], rbx
0x14000481f  mov     [rsp+1578h+var_1540], rdi
0x140004824  mov     [rsp+1578h+var_1548], 2
0x14000482c  mov     [rsp+1578h+var_1550], rsi
0x140004831  mov     [rsp+1578h+var_1558], rbp
0x140004836  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x14000483b  test    [rsp+1578h+var_14F4], 1
0x140004843  jnz     short loc_140004869
0x140004845  mov     rcx, [rsp+1578h+var_58]
0x14000484d  xor     rcx, rsp; StackCookie
0x140004850  call    __security_check_cookie
0x140004855  add     rsp, 1538h
0x14000485c  pop     r15
0x14000485e  pop     r14
0x140004860  pop     r13
0x140004862  pop     r12
0x140004864  pop     rdi
0x140004865  pop     rsi
0x140004866  pop     rbp
0x140004867  pop     rbx
0x140004868  retn
0x140004869  lea     rcx, [rsp+1578h+var_14F8]; this
0x140004871  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
