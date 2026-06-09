# BeginAcquireStoreLicenseForPackageActivation

- ea: `0x18000efe0`
- end: `0x18000f057`
- name: `BeginAcquireStoreLicenseForPackageActivation`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001960`
- `0x18000efe0`
- `0x18000f060`

## import_xrefs

- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18000f01d`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18000f01d`

## pseudocode

```c
__int64 __fastcall BeginAcquireStoreLicenseForPackageActivation(__int64 a1, int a2, __int64 a3)
{
  __int64 result; // rax
  int v6[4]; // [rsp+20h] [rbp-1F8h] BYREF
  _BYTE v7[464]; // [rsp+30h] [rbp-1E8h] BYREF

  v6[0] = 232;
  result = PsmCreateKey(a1, L"LMV1xF00Dx7238", v7, v6);
  if ( (int)result >= 0 )
    return BeginAcquireStoreLicenseForPackageActivation2((__int64)v7, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000efe0  mov     [rsp+arg_18], rbx
0x18000efe5  push    rdi
0x18000efe6  sub     rsp, 210h
0x18000efed  mov     rax, cs:__security_cookie
0x18000eff4  xor     rax, rsp
0x18000eff7  mov     [rsp+218h+var_18], rax
0x18000efff  mov     rdi, r8
0x18000f002  mov     [rsp+218h+var_1F8], 0E8h
0x18000f00a  mov     ebx, edx
0x18000f00c  lea     r8, [rsp+218h+var_1E8]
0x18000f011  lea     rdx, aLmv1xf00dx7238; "LMV1xF00Dx7238"
0x18000f018  lea     r9, [rsp+218h+var_1F8]
0x18000f01d  call    cs:__imp_PsmCreateKey
0x18000f023  test    eax, eax
0x18000f025  js      short loc_18000F036
0x18000f027  mov     r8, rdi
0x18000f02a  lea     rcx, [rsp+218h+var_1E8]
0x18000f02f  mov     edx, ebx
0x18000f031  call    BeginAcquireStoreLicenseForPackageActivation2
0x18000f036  mov     rcx, [rsp+218h+var_18]
0x18000f03e  xor     rcx, rsp; StackCookie
0x18000f041  call    __security_check_cookie
0x18000f046  mov     rbx, [rsp+218h+arg_18]
0x18000f04e  add     rsp, 210h
0x18000f055  pop     rdi
0x18000f056  retn
```
