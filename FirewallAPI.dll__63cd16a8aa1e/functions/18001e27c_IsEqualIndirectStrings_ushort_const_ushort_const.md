# IsEqualIndirectStrings(ushort const *,ushort const *)

- ea: `0x18001e27c`
- end: `0x18001e371`
- name: `?IsEqualIndirectStrings@@YAHPEBG0@Z`
- size: `245`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e160`
- `0x180030b90`

## callees

- `0x18001e27c`
- `0x1800277b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e326`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e326`
- `fwbase!FwBaseFree` at `0x18001e344`
- `fwbase!FwBaseFree` at `0x18001e34f`
- `fwbase!FwBaseFree` at `0x18001e344`
- `fwbase!FwBaseFree` at `0x18001e34f`
- `fwbase!FwResolveIndirectString` at `0x18001e2df`
- `fwbase!FwResolveIndirectString` at `0x18001e2fe`
- `fwbase!FwResolveIndirectString` at `0x18001e2df`
- `fwbase!FwResolveIndirectString` at `0x18001e2fe`
- `fwbase!FwReportReturnError` at `0x18001e2d2`
- `fwbase!FwReportReturnError` at `0x18001e2d2`
- `fwbase!FwStringCopy` at `0x18001e2bf`
- `fwbase!FwStringCopy` at `0x18001e2ef`
- `fwbase!FwStringCopy` at `0x18001e2bf`
- `fwbase!FwStringCopy` at `0x18001e2ef`

## pseudocode

```c
_BOOL8 __fastcall IsEqualIndirectStrings(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  BOOL v2; // edi
  const unsigned __int16 *v3; // rbx
  const unsigned __int16 *v4; // rsi
  int v5; // eax
  int v6; // ebp
  int v7; // eax
  const unsigned __int16 *v9; // [rsp+20h] [rbp-38h] BYREF
  const unsigned __int16 *v10; // [rsp+28h] [rbp-30h] BYREF

  v2 = 0;
  v3 = a2;
  v9 = 0;
  v4 = a1;
  v10 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v5 = FwStringCopy(a1, &v9);
      if ( v5 < 0 || (v6 = FwResolveIndirectString(&v9), v5 = FwStringCopy(v3, &v10), v5 < 0) )
      {
        FwReportReturnError("IsEqualIndirectStrings", (unsigned int)v5);
      }
      else
      {
        v7 = FwResolveIndirectString(&v10);
        if ( v6 >= 0 && v7 >= 0 )
        {
          v3 = v10;
          v4 = v9;
        }
        LOBYTE(v2) = (unsigned int)_o__wcsicmp(v4, v3) == 0;
      }
    }
  }
  else
  {
    v2 = a2 == 0;
  }
  FwBaseFree(v9);
  FwBaseFree(v10);
  return v2;
}

```

## disassembly

```asm
0x18001e27c  mov     r11, rsp
0x18001e27f  mov     [r11+18h], rbx
0x18001e283  push    rbp
0x18001e284  push    rsi
0x18001e285  push    rdi
0x18001e286  sub     rsp, 40h
0x18001e28a  mov     rax, cs:__security_cookie
0x18001e291  xor     rax, rsp
0x18001e294  mov     [rsp+58h+var_28], rax
0x18001e299  xor     edi, edi
0x18001e29b  mov     rbx, rdx
0x18001e29e  mov     [r11-38h], rdi
0x18001e2a2  mov     rsi, rcx
0x18001e2a5  mov     [r11-30h], rdi
0x18001e2a9  test    rcx, rcx
0x18001e2ac  jz      loc_18001E334
0x18001e2b2  test    rdx, rdx
0x18001e2b5  jz      loc_18001E33F
0x18001e2bb  lea     rdx, [r11-38h]
0x18001e2bf  call    cs:__imp_FwStringCopy
0x18001e2c5  test    eax, eax
0x18001e2c7  jns     short loc_18001E2DA
0x18001e2c9  mov     edx, eax
0x18001e2cb  lea     rcx, aIsequalindirec; "IsEqualIndirectStrings"
0x18001e2d2  call    cs:__imp_FwReportReturnError
0x18001e2d8  jmp     short loc_18001E33F
0x18001e2da  lea     rcx, [rsp+58h+var_38]
0x18001e2df  call    cs:__imp_FwResolveIndirectString
0x18001e2e5  lea     rdx, [rsp+58h+var_30]
0x18001e2ea  mov     rcx, rbx
0x18001e2ed  mov     ebp, eax
0x18001e2ef  call    cs:__imp_FwStringCopy
0x18001e2f5  test    eax, eax
0x18001e2f7  js      short loc_18001E2C9
0x18001e2f9  lea     rcx, [rsp+58h+var_30]
0x18001e2fe  call    cs:__imp_FwResolveIndirectString
0x18001e304  test    ebp, ebp
0x18001e306  js      short loc_18001E320
0x18001e308  test    eax, eax
0x18001e30a  js      short loc_18001E313
0x18001e30c  mov     rbx, [rsp+58h+var_30]
0x18001e311  jmp     short loc_18001E31B
0x18001e313  test    ebp, ebp
0x18001e315  js      short loc_18001E320
0x18001e317  test    eax, eax
0x18001e319  js      short loc_18001E320
0x18001e31b  mov     rsi, [rsp+58h+var_38]
0x18001e320  mov     rdx, rbx
0x18001e323  mov     rcx, rsi
0x18001e326  call    cs:__imp__o__wcsicmp
0x18001e32c  test    eax, eax
0x18001e32e  setz    dil
0x18001e332  jmp     short loc_18001E33F
0x18001e334  test    rbx, rbx
0x18001e337  mov     eax, 1
0x18001e33c  cmovz   edi, eax
0x18001e33f  mov     rcx, [rsp+58h+var_38]
0x18001e344  call    cs:__imp_FwBaseFree
0x18001e34a  mov     rcx, [rsp+58h+var_30]
0x18001e34f  call    cs:__imp_FwBaseFree
0x18001e355  mov     eax, edi
0x18001e357  mov     rcx, [rsp+58h+var_28]
0x18001e35c  xor     rcx, rsp; StackCookie
0x18001e35f  call    __security_check_cookie
0x18001e364  mov     rbx, [rsp+58h+arg_10]
0x18001e369  add     rsp, 40h
0x18001e36d  pop     rdi
0x18001e36e  pop     rsi
0x18001e36f  pop     rbp
0x18001e370  retn
```
