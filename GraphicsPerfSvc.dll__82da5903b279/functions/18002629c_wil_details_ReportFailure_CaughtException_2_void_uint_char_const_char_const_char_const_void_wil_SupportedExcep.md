# wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x18002629c`
- end: `0x18002632a`
- name: `??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `142`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800264b0`

## callees

- `0x180003ab0`
- `0x1800047f0`
- `0x18000dab4`
- `0x18002f0d0`

## string_xrefs

- `0x1800262ee`: `onecoreuap\windows\directx\dxg\common\servicehelpers\parameters.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<2>(int a1)
{
  char v3; // [rsp+50h] [rbp-1028h] BYREF
  _BYTE v4[4096]; // [rsp+60h] [rbp-1018h] BYREF

  memset_0(v4, 0, sizeof(v4));
  return *(unsigned int *)wil::details::ReportFailure_CaughtExceptionCommon<2>(
                            (unsigned int)&v3,
                            a1,
                            39,
                            (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\parameters.cpp");
}

```

## disassembly

```asm
0x18002629c  mov     [rsp+arg_8], rbx
0x1800262a1  push    rdi
0x1800262a2  mov     eax, 1070h
0x1800262a7  call    _alloca_probe
0x1800262ac  sub     rsp, rax
0x1800262af  mov     rax, cs:__security_cookie
0x1800262b6  xor     rax, rsp
0x1800262b9  mov     [rsp+1078h+var_18], rax
0x1800262c1  mov     rbx, [rsp+1078h+arg_28]
0x1800262c9  mov     rdi, rcx
0x1800262cc  lea     rcx, [rsp+1078h+var_1018]; void *
0x1800262d1  xor     edx, edx; Val
0x1800262d3  mov     r8d, 1000h; Size
0x1800262d9  call    memset_0
0x1800262de  lea     rax, [rsp+1078h+var_1018]
0x1800262e3  mov     r8d, 27h ; '''
0x1800262e9  mov     [rsp+1078h+var_1040], rax
0x1800262ee  lea     r9, aOnecoreuapWind_2; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800262f5  mov     rdx, rdi
0x1800262f8  mov     [rsp+1078h+var_1048], rbx
0x1800262fd  lea     rcx, [rsp+1078h+var_1028]
0x180026302  call    ??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)
0x180026307  mov     eax, [rax]
0x180026309  mov     rcx, [rsp+1078h+var_18]
0x180026311  xor     rcx, rsp; StackCookie
0x180026314  call    __security_check_cookie
0x180026319  mov     rbx, [rsp+1078h+arg_8]
0x180026321  add     rsp, 1070h
0x180026328  pop     rdi
0x180026329  retn
```
