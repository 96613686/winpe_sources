# MpCommonConfigGetValue

- ea: `0x1400051d0`
- end: `0x140005264`
- name: `MpCommonConfigGetValue`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000513c`

## callees

- `0x1400024c0`
- `0x1400051d0`
- `0x140005c20`
- `0x140024c40`

## pseudocode

```c
__int64 __fastcall MpCommonConfigGetValue(
        __int64 a1,
        struct CommonUtil::IMpCommonConfigHook **a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v9; // ebx
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF

  v10 = 0;
  CommonUtil::MpCommonConfigGetHook((CommonUtil *)&v10, a2);
  if ( !v10 )
    return 2147943568LL;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, struct CommonUtil::IMpCommonConfigHook **, __int64, __int64))(*(_QWORD *)v10 + 24LL))(
         v10,
         a1,
         a2,
         a3,
         a4);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  return v9;
}

```

## disassembly

```asm
0x1400051d0  push    rbx
0x1400051d2  push    rbp
0x1400051d3  push    rsi
0x1400051d4  push    rdi
0x1400051d5  sub     rsp, 48h
0x1400051d9  mov     rax, cs:__security_cookie
0x1400051e0  xor     rax, rsp
0x1400051e3  mov     [rsp+68h+var_30], rax
0x1400051e8  mov     rbx, rcx
0x1400051eb  mov     [rsp+68h+var_38], 0
0x1400051f4  lea     rcx, [rsp+68h+var_38]; this
0x1400051f9  mov     rbp, r9
0x1400051fc  mov     rsi, r8
0x1400051ff  mov     rdi, rdx
0x140005202  call    ?MpCommonConfigGetHook@CommonUtil@@YAXPEAPEAUIMpCommonConfigHook@1@@Z; CommonUtil::MpCommonConfigGetHook(CommonUtil::IMpCommonConfigHook * *)
0x140005207  mov     rcx, [rsp+68h+var_38]
0x14000520c  test    rcx, rcx
0x14000520f  jnz     short loc_140005218
0x140005211  mov     eax, 80070490h
0x140005216  jmp     short loc_14000524E
0x140005218  mov     rax, [rcx]
0x14000521b  mov     r9, rsi
0x14000521e  mov     r8, rdi
0x140005221  mov     [rsp+68h+var_48], rbp
0x140005226  mov     rdx, rbx
0x140005229  mov     rax, [rax+18h]
0x14000522d  call    cs:__guard_dispatch_icall_fptr
0x140005233  mov     rcx, [rsp+68h+var_38]
0x140005238  mov     ebx, eax
0x14000523a  test    rcx, rcx
0x14000523d  jz      short loc_14000524C
0x14000523f  mov     rdx, [rcx]
0x140005242  mov     rax, [rdx+8]
0x140005246  call    cs:__guard_dispatch_icall_fptr
0x14000524c  mov     eax, ebx
0x14000524e  mov     rcx, [rsp+68h+var_30]
0x140005253  xor     rcx, rsp; StackCookie
0x140005256  call    __security_check_cookie
0x14000525b  add     rsp, 48h
0x14000525f  pop     rdi
0x140005260  pop     rsi
0x140005261  pop     rbp
0x140005262  pop     rbx
0x140005263  retn
```
