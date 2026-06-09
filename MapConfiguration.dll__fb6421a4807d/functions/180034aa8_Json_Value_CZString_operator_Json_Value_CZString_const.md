# Json::Value::CZString::operator<(Json::Value::CZString const &)

- ea: `0x180034aa8`
- end: `0x180034b38`
- name: `??MCZString@Value@Json@@QEBA_NAEBV012@@Z`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180033bb0`
- `0x180033d58`
- `0x180033e08`

## callees

- `0x1800094a0`
- `0x18000b209`
- `0x18002ccd0`
- `0x180034aa8`
- `0x1800360f0`

## string_xrefs

- `0x180034b1b`: `assert json failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Json::Value::CZString::operator<(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  unsigned int v3; // ebx
  unsigned int v5; // eax
  const void *v6; // rdx
  int v7; // eax
  _BYTE v8[32]; // [rsp+20h] [rbp-38h] BYREF

  v2 = *(_DWORD *)(a1 + 8);
  v3 = *(_DWORD *)(a2 + 8);
  if ( !*(_QWORD *)a1 )
    return v2 < v3;
  v2 >>= 2;
  v3 >>= 2;
  v5 = v3;
  if ( v3 >= v2 )
    v5 = v2;
  v6 = *(const void **)a2;
  if ( !v6 )
  {
    std::string::string((__int64)v8, (__int64)"assert json failed");
    Json::throwLogicError(v8);
  }
  v7 = memcmp_0(*(const void **)a1, v6, 2LL * v5);
  if ( v7 < 0 )
    return 1;
  if ( v7 <= 0 )
    return v2 < v3;
  return 0;
}

```

## disassembly

```asm
0x180034aa8  mov     [rsp+arg_0], rbx
0x180034aad  push    rdi
0x180034aae  sub     rsp, 50h
0x180034ab2  mov     rax, cs:__security_cookie
0x180034ab9  xor     rax, rsp
0x180034abc  mov     [rsp+58h+var_18], rax
0x180034ac1  mov     edi, [rcx+8]
0x180034ac4  mov     ebx, [rdx+8]
0x180034ac7  cmp     qword ptr [rcx], 0
0x180034acb  jnz     short loc_180034AEA
0x180034acd  cmp     edi, ebx
0x180034acf  setb    al
0x180034ad2  mov     rcx, [rsp+58h+var_18]
0x180034ad7  xor     rcx, rsp; StackCookie
0x180034ada  call    __security_check_cookie
0x180034adf  mov     rbx, [rsp+58h+arg_0]
0x180034ae4  add     rsp, 50h
0x180034ae8  pop     rdi
0x180034ae9  retn
0x180034aea  shr     edi, 2
0x180034aed  shr     ebx, 2
0x180034af0  mov     eax, ebx
0x180034af2  cmp     ebx, edi
0x180034af4  cmovnb  eax, edi
0x180034af7  mov     rdx, [rdx]; Buf2
0x180034afa  test    rdx, rdx
0x180034afd  jz      short loc_180034B1B
0x180034aff  mov     r8d, eax
0x180034b02  add     r8, r8; Size
0x180034b05  mov     rcx, [rcx]; Buf1
0x180034b08  call    memcmp_0
0x180034b0d  test    eax, eax
0x180034b0f  jns     short loc_180034B15
0x180034b11  mov     al, 1
0x180034b13  jmp     short loc_180034AD2
0x180034b15  jle     short loc_180034ACD
0x180034b17  xor     al, al
0x180034b19  jmp     short loc_180034AD2
0x180034b1b  lea     rdx, aAssertJsonFail; "assert json failed"
0x180034b22  lea     rcx, [rsp+58h+var_38]
0x180034b27  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180034b2c  nop
0x180034b2d  lea     rcx, [rsp+58h+var_38]
0x180034b32  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
```
