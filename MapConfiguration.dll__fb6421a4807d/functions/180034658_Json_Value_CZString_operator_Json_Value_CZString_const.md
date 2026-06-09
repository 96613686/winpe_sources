# Json::Value::CZString::operator==(Json::Value::CZString const &)

- ea: `0x180034658`
- end: `0x1800346d5`
- name: `??8CZString@Value@Json@@QEBA_NAEBV012@@Z`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180034794`
- `0x180035d2c`

## callees

- `0x1800094a0`
- `0x18000b209`
- `0x18002ccd0`
- `0x180034658`
- `0x1800360f0`

## string_xrefs

- `0x1800346b8`: `assert json failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Json::Value::CZString::operator==(__int64 a1, __int64 a2)
{
  const void *v2; // r9
  unsigned int v3; // eax
  unsigned int v4; // ecx
  unsigned int v7; // eax
  const void *v8; // rdx
  _BYTE v9[32]; // [rsp+20h] [rbp-38h] BYREF

  v2 = *(const void **)a1;
  v3 = *(_DWORD *)(a1 + 8);
  v4 = *(_DWORD *)(a2 + 8);
  if ( !v2 )
    return v3 == v4;
  v7 = v3 >> 2;
  if ( v7 == v4 >> 2 )
  {
    v8 = *(const void **)a2;
    if ( !v8 )
    {
      std::string::string((__int64)v9, (__int64)"assert json failed");
      Json::throwLogicError(v9);
    }
    return memcmp_0(v2, v8, 2LL * v7) == 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180034658  sub     rsp, 58h
0x18003465c  mov     rax, cs:__security_cookie
0x180034663  xor     rax, rsp
0x180034666  mov     [rsp+58h+var_18], rax
0x18003466b  mov     r9, [rcx]
0x18003466e  mov     eax, [rcx+8]
0x180034671  mov     ecx, [rdx+8]
0x180034674  test    r9, r9
0x180034677  jnz     short loc_180034690
0x180034679  cmp     eax, ecx
0x18003467b  setz    al
0x18003467e  mov     rcx, [rsp+58h+var_18]
0x180034683  xor     rcx, rsp; StackCookie
0x180034686  call    __security_check_cookie
0x18003468b  add     rsp, 58h
0x18003468f  retn
0x180034690  shr     eax, 2
0x180034693  shr     ecx, 2
0x180034696  cmp     eax, ecx
0x180034698  jz      short loc_18003469E
0x18003469a  xor     al, al
0x18003469c  jmp     short loc_18003467E
0x18003469e  mov     rdx, [rdx]; Buf2
0x1800346a1  test    rdx, rdx
0x1800346a4  jz      short loc_1800346B8
0x1800346a6  mov     r8d, eax
0x1800346a9  add     r8, r8; Size
0x1800346ac  mov     rcx, r9; Buf1
0x1800346af  call    memcmp_0
0x1800346b4  test    eax, eax
0x1800346b6  jmp     short loc_18003467B
0x1800346b8  lea     rdx, aAssertJsonFail; "assert json failed"
0x1800346bf  lea     rcx, [rsp+58h+var_38]
0x1800346c4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800346c9  nop
0x1800346ca  lea     rcx, [rsp+58h+var_38]
0x1800346cf  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
```
