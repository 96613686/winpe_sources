# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x14002f084`
- end: `0x14002f125`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002d5f8`
- `0x14002dbb4`

## callees

- `0x1400030a0`
- `0x1400185a0`
- `0x14002f084`
- `0x14002f70c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002f10c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002f10c`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::complete_helper(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v4; // r8
  __int64 v5; // rcx
  __int128 v6; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v8; // [rsp+40h] [rbp-28h]

  v2 = *(_DWORD *)(a1 + 232) == 0;
  v6 = 0;
  *(_OWORD *)pv = 0;
  v8 = 0;
  if ( !v2 )
    a2 = (unsigned int)a2 | 8;
  v4 = *(unsigned int *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))TestQueryData)(v5, a2, v4, &v6) )
  {
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( !pv[1] )
      *(_DWORD *)(a1 + 184) = pv[0];
    tip2::details::shared_data<0,0,1>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x14002f084  push    rbx
0x14002f086  sub     rsp, 60h
0x14002f08a  mov     rax, cs:__security_cookie
0x14002f091  xor     rax, rsp
0x14002f094  mov     [rsp+68h+var_18], rax
0x14002f099  cmp     dword ptr [rcx+0E8h], 0
0x14002f0a0  xorps   xmm0, xmm0
0x14002f0a3  movups  [rsp+68h+var_48], xmm0
0x14002f0a8  mov     rbx, rcx
0x14002f0ab  movups  xmmword ptr [rsp+68h+pv], xmm0
0x14002f0b0  movups  [rsp+68h+var_28], xmm0
0x14002f0b5  jbe     short loc_14002F0BA
0x14002f0b7  or      edx, 8
0x14002f0ba  mov     r8d, [rcx+0B8h]
0x14002f0c1  lea     r9, [rsp+68h+var_48]
0x14002f0c6  mov     rcx, [rcx+0F0h]
0x14002f0cd  mov     qword ptr [rbx+0F0h], 0
0x14002f0d8  call    TestQueryData
0x14002f0dd  test    eax, eax
0x14002f0df  jz      short loc_14002F107
0x14002f0e1  mov     eax, dword ptr [rsp+68h+pv+4]
0x14002f0e5  or      [rbx+40h], eax
0x14002f0e8  cmp     [rsp+68h+pv+8], 0
0x14002f0ee  jnz     short loc_14002F0FA
0x14002f0f0  mov     eax, dword ptr [rsp+68h+pv]
0x14002f0f4  mov     [rbx+0B8h], eax
0x14002f0fa  mov     rdx, qword ptr [rsp+68h+var_28]
0x14002f0ff  mov     rcx, rbx
0x14002f102  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x14002f107  mov     rcx, [rsp+68h+pv+8]; pv
0x14002f10c  call    cs:__imp_CoTaskMemFree
0x14002f112  mov     rcx, [rsp+68h+var_18]
0x14002f117  xor     rcx, rsp; StackCookie
0x14002f11a  call    __security_check_cookie
0x14002f11f  add     rsp, 60h
0x14002f123  pop     rbx
0x14002f124  retn
```
