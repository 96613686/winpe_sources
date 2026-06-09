# BiCacheGuidValues

- ea: `0x14002090c`
- end: `0x1400209ca`
- name: `BiCacheGuidValues`
- size: `190`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int16, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400209d0`

## callees

- `0x14001e5e4`
- `0x14001f980`
- `0x14001fc5c`
- `0x14002090c`
- `0x140026650`

## string_xrefs

- `0x14002096b`: `GuidCache`

## pseudocode

```c
__int64 __fastcall BiCacheGuidValues(__int64 a1, unsigned int a2, __int64 a3, __int16 a4, __int64 a5)
{
  __int64 v6; // rdi
  __int64 result; // rax
  unsigned int v9; // ebx
  HANDLE Handle; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v11[24]; // [rsp+38h] [rbp-28h] BYREF

  v6 = a2;
  Handle = 0;
  memset(v11, 0, sizeof(v11));
  result = BiOpenKey(a1, L"Description", 131103, &Handle);
  if ( (int)result >= 0 )
  {
    *(_QWORD *)v11 = a3 + v6;
    *(_DWORD *)&v11[14] = *(_DWORD *)a5;
    *(_WORD *)&v11[18] = *(_WORD *)(a5 + 4);
    *(_DWORD *)&v11[8] = v6;
    *(_WORD *)&v11[12] = a4;
    v9 = BiSetRegistryValue(Handle, L"GuidCache", 0, 3, v11, 24);
    BiCloseKey(Handle);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x14002090c  push    rbp
0x14002090e  push    rbx
0x14002090f  push    rsi
0x140020910  push    rdi
0x140020911  push    r14
0x140020913  mov     rbp, rsp
0x140020916  sub     rsp, 60h
0x14002091a  mov     rax, cs:__security_cookie
0x140020921  xor     rax, rsp
0x140020924  mov     [rbp+var_10], rax
0x140020928  mov     rsi, [rbp+arg_20]
0x14002092c  xor     eax, eax
0x14002092e  mov     r14d, r9d
0x140020931  mov     edi, edx
0x140020933  mov     rbx, r8
0x140020936  mov     [rbp+var_18], rax
0x14002093a  xorps   xmm0, xmm0
0x14002093d  mov     [rbp+Handle], rax
0x140020941  lea     r9, [rbp+Handle]
0x140020945  mov     r8d, 2001Fh
0x14002094b  lea     rdx, aDescription; "Description"
0x140020952  movups  [rbp+var_28], xmm0
0x140020956  call    BiOpenKey
0x14002095b  test    eax, eax
0x14002095d  js      short loc_1400209B3
0x14002095f  mov     rcx, [rbp+Handle]
0x140020963  lea     rax, [rbx+rdi]
0x140020967  mov     qword ptr [rbp+var_28], rax
0x14002096b  lea     rdx, aGuidcache; "GuidCache"
0x140020972  mov     eax, [rsi]
0x140020974  mov     r9d, 3
0x14002097a  mov     dword ptr [rbp+var_28+0Eh], eax
0x14002097d  xor     r8d, r8d
0x140020980  movzx   eax, word ptr [rsi+4]
0x140020984  mov     word ptr [rbp+var_18+2], ax
0x140020988  lea     rax, [rbp+var_28]
0x14002098c  mov     [rsp+60h+var_38], 18h
0x140020994  mov     [rsp+60h+var_40], rax
0x140020999  mov     dword ptr [rbp+var_28+8], edi
0x14002099c  mov     word ptr [rbp+var_28+0Ch], r14w
0x1400209a1  call    BiSetRegistryValue
0x1400209a6  mov     rcx, [rbp+Handle]; Handle
0x1400209aa  mov     ebx, eax
0x1400209ac  call    BiCloseKey
0x1400209b1  mov     eax, ebx
0x1400209b3  mov     rcx, [rbp+var_10]
0x1400209b7  xor     rcx, rsp; StackCookie
0x1400209ba  call    __security_check_cookie
0x1400209bf  add     rsp, 60h
0x1400209c3  pop     r14
0x1400209c5  pop     rdi
0x1400209c6  pop     rsi
0x1400209c7  pop     rbx
0x1400209c8  pop     rbp
0x1400209c9  retn
```
