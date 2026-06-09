# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180018aa0`
- end: `0x180018b50`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018b58`
- `0x180019f7c`

## callees

- `0x180003390`
- `0x180018aa0`
- `0x180018de0`
- `0x1800192bc`
- `0x18001b56c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b37`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::complete_helper(__int64 a1, __int64 a2)
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
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v6);
    else
      *(_DWORD *)(a1 + 184) = pv[0];
    tip2::details::shared_data<1,0,0>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x180018aa0  push    rbx
0x180018aa2  sub     rsp, 60h
0x180018aa6  mov     rax, cs:__security_cookie
0x180018aad  xor     rax, rsp
0x180018ab0  mov     [rsp+68h+var_18], rax
0x180018ab5  cmp     dword ptr [rcx+0E8h], 0
0x180018abc  xorps   xmm0, xmm0
0x180018abf  movups  [rsp+68h+var_48], xmm0
0x180018ac4  mov     rbx, rcx
0x180018ac7  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180018acc  movups  [rsp+68h+var_28], xmm0
0x180018ad1  jbe     short loc_180018AD6
0x180018ad3  or      edx, 8
0x180018ad6  mov     r8d, [rcx+0B8h]
0x180018add  lea     r9, [rsp+68h+var_48]
0x180018ae2  mov     rcx, [rcx+0F0h]
0x180018ae9  mov     qword ptr [rbx+0F0h], 0
0x180018af4  call    TestQueryData
0x180018af9  test    eax, eax
0x180018afb  jz      short loc_180018B32
0x180018afd  mov     eax, dword ptr [rsp+68h+pv+4]
0x180018b01  or      [rbx+40h], eax
0x180018b04  cmp     [rsp+68h+pv+8], 0
0x180018b0a  jz      short loc_180018B1B
0x180018b0c  lea     rdx, [rsp+68h+var_48]
0x180018b11  mov     rcx, rbx
0x180018b14  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180018b19  jmp     short loc_180018B25
0x180018b1b  mov     eax, dword ptr [rsp+68h+pv]
0x180018b1f  mov     [rbx+0B8h], eax
0x180018b25  mov     rdx, qword ptr [rsp+68h+var_28]
0x180018b2a  mov     rcx, rbx
0x180018b2d  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x180018b32  mov     rcx, [rsp+68h+pv+8]; pv
0x180018b37  call    cs:__imp_CoTaskMemFree
0x180018b3d  mov     rcx, [rsp+68h+var_18]
0x180018b42  xor     rcx, rsp; StackCookie
0x180018b45  call    __security_check_cookie
0x180018b4a  add     rsp, 60h
0x180018b4e  pop     rbx
0x180018b4f  retn
```
