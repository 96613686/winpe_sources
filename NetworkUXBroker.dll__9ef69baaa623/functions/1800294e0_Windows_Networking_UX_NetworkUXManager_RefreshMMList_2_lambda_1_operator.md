# _Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()

- ea: `0x1800294e0`
- end: `0x18002956b`
- name: `_Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029930`

## callees

- `0x18002901c`
- `0x1800294e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029528`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002950d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002950d`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()(
        __int64 a1,
        const WCHAR *a2)
{
  const WCHAR *v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rsi
  const WCHAR *StringRawBuffer; // rax
  _QWORD v8[7]; // [rsp+30h] [rbp-38h] BYREF
  const WCHAR *v9; // [rsp+78h] [rbp+10h] BYREF

  v9 = a2;
  v2 = a2;
  v4 = *(_QWORD *)(*(_QWORD *)a1 + 72LL);
  v5 = *(_QWORD *)(*(_QWORD *)a1 + 80LL);
  if ( v4 == v5 )
  {
LABEL_5:
    v8[0] = *(_QWORD *)a1;
    v8[1] = &v9;
    _Windows::Networking::UX::NetworkUXManager::_RefreshMMList_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::operator()(v8);
  }
  else
  {
    while ( 1 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v4 + 96LL), 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, v2, -1, 1) == 2 )
        break;
      v4 += 8;
      if ( v4 == v5 )
        goto LABEL_5;
      v2 = v9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800294e0  mov     [rsp+arg_8], rdx
0x1800294e5  push    rbx
0x1800294e6  push    rsi
0x1800294e7  push    rdi
0x1800294e8  push    r14
0x1800294ea  sub     rsp, 48h
0x1800294ee  mov     rdi, rdx
0x1800294f1  mov     r14, rcx
0x1800294f4  mov     rax, [rcx]
0x1800294f7  mov     rbx, [rax+48h]
0x1800294fb  mov     rsi, [rax+50h]
0x1800294ff  cmp     rbx, rsi
0x180029502  jz      short loc_180029543
0x180029504  mov     rcx, [rbx]
0x180029507  xor     edx, edx; length
0x180029509  mov     rcx, [rcx+60h]; string
0x18002950d  call    cs:__imp_WindowsGetStringRawBuffer
0x180029513  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18002951b  or      r9d, 0FFFFFFFFh; cchCount2
0x18002951f  mov     r8, rdi; lpString2
0x180029522  or      edx, r9d; cchCount1
0x180029525  mov     rcx, rax; lpString1
0x180029528  call    cs:__imp_CompareStringOrdinal
0x18002952e  cmp     eax, 2
0x180029531  jz      short loc_18002955F
0x180029533  add     rbx, 8
0x180029537  cmp     rbx, rsi
0x18002953a  jz      short loc_180029543
0x18002953c  mov     rdi, [rsp+68h+arg_8]
0x180029541  jmp     short loc_180029504
0x180029543  mov     rax, [r14]
0x180029546  mov     [rsp+68h+var_38], rax
0x18002954b  lea     rax, [rsp+68h+arg_8]
0x180029550  mov     [rsp+68h+var_30], rax
0x180029555  lea     rcx, [rsp+68h+var_38]
0x18002955a  call    __Windows__Networking__UX__NetworkUXManager___RefreshMMList____2____lambda_1___operator______2____lambda_1___operator__
0x18002955f  xor     eax, eax
0x180029561  add     rsp, 48h
0x180029565  pop     r14
0x180029567  pop     rdi
0x180029568  pop     rsi
0x180029569  pop     rbx
0x18002956a  retn
```
