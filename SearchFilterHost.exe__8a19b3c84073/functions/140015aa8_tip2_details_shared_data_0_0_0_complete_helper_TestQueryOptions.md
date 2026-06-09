# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x140015aa8`
- end: `0x140015b49`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140015a7c`
- `0x140016c80`

## callees

- `0x1400030a0`
- `0x140015aa8`
- `0x140015fa0`
- `0x1400185a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b30`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, __int64 a2)
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
    tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x140015aa8  push    rbx
0x140015aaa  sub     rsp, 60h
0x140015aae  mov     rax, cs:__security_cookie
0x140015ab5  xor     rax, rsp
0x140015ab8  mov     [rsp+68h+var_18], rax
0x140015abd  cmp     dword ptr [rcx+0E8h], 0
0x140015ac4  xorps   xmm0, xmm0
0x140015ac7  movups  [rsp+68h+var_48], xmm0
0x140015acc  mov     rbx, rcx
0x140015acf  movups  xmmword ptr [rsp+68h+pv], xmm0
0x140015ad4  movups  [rsp+68h+var_28], xmm0
0x140015ad9  jbe     short loc_140015ADE
0x140015adb  or      edx, 8
0x140015ade  mov     r8d, [rcx+0B8h]
0x140015ae5  lea     r9, [rsp+68h+var_48]
0x140015aea  mov     rcx, [rcx+0F0h]
0x140015af1  mov     qword ptr [rbx+0F0h], 0
0x140015afc  call    TestQueryData
0x140015b01  test    eax, eax
0x140015b03  jz      short loc_140015B2B
0x140015b05  mov     eax, dword ptr [rsp+68h+pv+4]
0x140015b09  or      [rbx+40h], eax
0x140015b0c  cmp     [rsp+68h+pv+8], 0
0x140015b12  jnz     short loc_140015B1E
0x140015b14  mov     eax, dword ptr [rsp+68h+pv]
0x140015b18  mov     [rbx+0B8h], eax
0x140015b1e  mov     rdx, qword ptr [rsp+68h+var_28]
0x140015b23  mov     rcx, rbx
0x140015b26  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x140015b2b  mov     rcx, [rsp+68h+pv+8]; pv
0x140015b30  call    cs:__imp_CoTaskMemFree
0x140015b36  mov     rcx, [rsp+68h+var_18]
0x140015b3b  xor     rcx, rsp; StackCookie
0x140015b3e  call    __security_check_cookie
0x140015b43  add     rsp, 60h
0x140015b47  pop     rbx
0x140015b48  retn
```
