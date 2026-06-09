# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x140034974`
- end: `0x140034a15`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000f014`
- `0x14001d04c`

## callees

- `0x140005240`
- `0x140034974`
- `0x1400356d0`
- `0x140039f70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400349fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400349fc`

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
0x140034974  push    rbx
0x140034976  sub     rsp, 60h
0x14003497a  mov     rax, cs:__security_cookie
0x140034981  xor     rax, rsp
0x140034984  mov     [rsp+68h+var_18], rax
0x140034989  cmp     dword ptr [rcx+0E8h], 0
0x140034990  xorps   xmm0, xmm0
0x140034993  movups  [rsp+68h+var_48], xmm0
0x140034998  mov     rbx, rcx
0x14003499b  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1400349a0  movups  [rsp+68h+var_28], xmm0
0x1400349a5  jbe     short loc_1400349AA
0x1400349a7  or      edx, 8
0x1400349aa  mov     r8d, [rcx+0B8h]
0x1400349b1  lea     r9, [rsp+68h+var_48]
0x1400349b6  mov     rcx, [rcx+0F0h]
0x1400349bd  mov     qword ptr [rbx+0F0h], 0
0x1400349c8  call    TestQueryData
0x1400349cd  test    eax, eax
0x1400349cf  jz      short loc_1400349F7
0x1400349d1  mov     eax, dword ptr [rsp+68h+pv+4]
0x1400349d5  or      [rbx+40h], eax
0x1400349d8  cmp     [rsp+68h+pv+8], 0
0x1400349de  jnz     short loc_1400349EA
0x1400349e0  mov     eax, dword ptr [rsp+68h+pv]
0x1400349e4  mov     [rbx+0B8h], eax
0x1400349ea  mov     rdx, qword ptr [rsp+68h+var_28]
0x1400349ef  mov     rcx, rbx
0x1400349f2  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x1400349f7  mov     rcx, [rsp+68h+pv+8]; pv
0x1400349fc  call    cs:__imp_CoTaskMemFree
0x140034a02  mov     rcx, [rsp+68h+var_18]
0x140034a07  xor     rcx, rsp; StackCookie
0x140034a0a  call    __security_check_cookie
0x140034a0f  add     rsp, 60h
0x140034a13  pop     rbx
0x140034a14  retn
```
