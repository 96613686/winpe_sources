# _anonymous_namespace_::GetAccessibilitySettings

- ea: `0x180045b18`
- end: `0x180045c6f`
- name: `_anonymous_namespace_::GetAccessibilitySettings`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180047104`

## callees

- `0x180043964`
- `0x180043e78`
- `0x180045b18`
- `0x180045c78`
- `0x18004c8e0`

## import_xrefs

- `ntdll!swprintf_s` at `0x180045b85`
- `ntdll!swprintf_s` at `0x180045ba4`
- `ntdll!swprintf_s` at `0x180045b85`
- `ntdll!swprintf_s` at `0x180045ba4`

## string_xrefs

- `0x180045bbb`: `GamepadAccessibilityButtonSettings`
- `0x180045bd1`: `GamepadAccessibilityAnalogSettings`

## pseudocode

```c
bool __fastcall anonymous_namespace_::GetAccessibilitySettings(
        const char *a1,
        __int64 *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4,
        _BYTE *a5,
        bool *a6)
{
  bool v10; // bl
  int v11; // r9d
  int v12; // r9d
  __int64 v13; // rdx
  int v14; // r9d
  int v15; // r9d
  int v16; // r9d
  bool result; // al
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-69h] BYREF
  unsigned __int64 v20; // [rsp+28h] [rbp-61h] BYREF
  __int64 v21; // [rsp+30h] [rbp-59h] BYREF
  wchar_t Buffer[20]; // [rsp+38h] [rbp-51h] BYREF
  wchar_t v23[20]; // [rsp+60h] [rbp-29h] BYREF

  v21 = 0;
  v19 = 0;
  v20 = 0xFEDCBA9876543210uLL;
  v10 = 0;
  swprintf_s(Buffer, 0x11u, L"%llx", a1);
  swprintf_s(v23, 0x11u, L"%llX", a1);
  *a3 = 0;
  anonymous_namespace_::GetPropertyValue_unsigned___int64_(
    a2,
    L"GamepadAccessibilityButtonSettings",
    (__int64)&v20,
    v11);
  anonymous_namespace_::GetPropertyValue_unsigned___int64_(
    a2,
    L"GamepadAccessibilityAnalogSettings",
    (__int64)&v21,
    v12);
  anonymous_namespace_::GetPropertyValue_unsigned_long_(a2, v13, (__int64)&v19, v14);
  if ( (int)anonymous_namespace_::GetPropertyValue_unsigned___int64_(a2, Buffer, (__int64)a3, v15) < 0
    && (int)anonymous_namespace_::GetPropertyValue_unsigned___int64_(a2, v23, (__int64)a3, v16) < 0
    || !*a3 )
  {
    v10 = (int)anonymous_namespace_::GetUInt64KeyFromUInt64Value(a2, a1, a3, v16) >= 0;
  }
  result = v10;
  *a4 = v20;
  v18 = v19 == 0;
  *a5 = v21 & 0xF;
  *a6 = !v18;
  return result;
}

```

## disassembly

```asm
0x180045b18  push    rbp
0x180045b1a  push    rbx
0x180045b1b  push    rsi
0x180045b1c  push    rdi
0x180045b1d  push    r12
0x180045b1f  push    r13
0x180045b21  push    r14
0x180045b23  push    r15
0x180045b25  lea     rbp, [rsp-0Fh]
0x180045b2a  sub     rsp, 98h
0x180045b31  mov     rax, cs:__security_cookie
0x180045b38  xor     rax, rsp
0x180045b3b  mov     [rbp+47h+var_48], rax
0x180045b3f  mov     r12, [rbp+47h+arg_20]
0x180045b43  mov     r15, r9
0x180045b46  mov     r13, [rbp+47h+arg_28]
0x180045b4a  mov     r9, rcx
0x180045b4d  mov     rdi, r8
0x180045b50  mov     [rbp+47h+var_A0], 0
0x180045b58  mov     rsi, rdx
0x180045b5b  mov     [rbp+47h+var_B0], 0
0x180045b62  mov     r14, rcx
0x180045b65  lea     r8, aLlx; "%llx"
0x180045b6c  mov     rax, 0FEDCBA9876543210h
0x180045b76  lea     rcx, [rbp+47h+Buffer]; Buffer
0x180045b7a  mov     edx, 11h; BufferCount
0x180045b7f  mov     [rbp+47h+var_A8], rax
0x180045b83  xor     bl, bl
0x180045b85  call    cs:__imp_swprintf_s
0x180045b8c  nop     dword ptr [rax+rax+00h]
0x180045b91  mov     r9, r14
0x180045b94  lea     r8, aLlx_0; "%llX"
0x180045b9b  mov     edx, 11h; BufferCount
0x180045ba0  lea     rcx, [rbp+47h+var_70]; Buffer
0x180045ba4  call    cs:__imp_swprintf_s
0x180045bab  nop     dword ptr [rax+rax+00h]
0x180045bb0  lea     r8, [rbp+47h+var_A8]
0x180045bb4  mov     qword ptr [rdi], 0
0x180045bbb  lea     rdx, aGamepadaccessi_0; "GamepadAccessibilityButtonSettings"
0x180045bc2  mov     rcx, rsi
0x180045bc5  call    _anonymous_namespace___GetPropertyValue_unsigned___int64_
0x180045bca  lea     r8, [rbp+47h+var_A0]
0x180045bce  mov     rcx, rsi
0x180045bd1  lea     rdx, aGamepadaccessi_1; "GamepadAccessibilityAnalogSettings"
0x180045bd8  call    _anonymous_namespace___GetPropertyValue_unsigned___int64_
0x180045bdd  lea     r8, [rbp+47h+var_B0]
0x180045be1  mov     rcx, rsi
0x180045be4  call    _anonymous_namespace___GetPropertyValue_unsigned_long_
0x180045be9  mov     r8, rdi
0x180045bec  lea     rdx, [rbp+47h+Buffer]
0x180045bf0  mov     rcx, rsi
0x180045bf3  call    _anonymous_namespace___GetPropertyValue_unsigned___int64_
0x180045bf8  test    eax, eax
0x180045bfa  jns     short loc_180045C0F
0x180045bfc  mov     r8, rdi
0x180045bff  lea     rdx, [rbp+47h+var_70]
0x180045c03  mov     rcx, rsi
0x180045c06  call    _anonymous_namespace___GetPropertyValue_unsigned___int64_
0x180045c0b  test    eax, eax
0x180045c0d  js      short loc_180045C15
0x180045c0f  cmp     qword ptr [rdi], 0
0x180045c13  jnz     short loc_180045C30
0x180045c15  mov     r8, rdi
0x180045c18  mov     rdx, r14
0x180045c1b  mov     rcx, rsi
0x180045c1e  call    _anonymous_namespace___GetUInt64KeyFromUInt64Value
0x180045c23  test    eax, eax
0x180045c25  movzx   ebx, bl
0x180045c28  mov     ecx, 1
0x180045c2d  cmovns  ebx, ecx
0x180045c30  mov     rcx, [rbp+47h+var_A8]
0x180045c34  mov     al, bl
0x180045c36  mov     [r15], rcx
0x180045c39  mov     cl, byte ptr [rbp+47h+var_A0]
0x180045c3c  and     cl, 0Fh
0x180045c3f  cmp     [rbp+47h+var_B0], 0
0x180045c43  mov     [r12], cl
0x180045c47  setnz   cl
0x180045c4a  mov     [r13+0], cl
0x180045c4e  mov     rcx, [rbp+47h+var_48]
0x180045c52  xor     rcx, rsp; StackCookie
0x180045c55  call    __security_check_cookie
0x180045c5a  add     rsp, 98h
0x180045c61  pop     r15
0x180045c63  pop     r14
0x180045c65  pop     r13
0x180045c67  pop     r12
0x180045c69  pop     rdi
0x180045c6a  pop     rsi
0x180045c6b  pop     rbx
0x180045c6c  pop     rbp
0x180045c6d  retn
```
