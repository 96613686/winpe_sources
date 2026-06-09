# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180018cc4`
- end: `0x180018d91`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015f00`
- `0x180019048`

## callees

- `0x180009f30`
- `0x180018cc4`
- `0x180019158`
- `0x18001bae8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ce3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ce3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d87`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,0>::begin_update(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // eax
  void *v5; // rcx
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v9; // [rsp+40h] [rbp-28h]

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
    return 0;
  v2 = *(_QWORD *)(a1 + 240);
  if ( v2 && *(_DWORD *)(a1 + 232) == 1 )
  {
    v3 = *(unsigned int *)(a1 + 184);
    v7 = 0;
    *(_OWORD *)pv = 0;
    v9 = 0;
    v4 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))TestQueryData)(v2, 1, v3, &v7);
    v5 = pv[1];
    if ( !v4 )
    {
      CoTaskMemFree(pv[1]);
      return 0;
    }
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( v5 )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v7);
      v5 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x180018cc4  push    rbx
0x180018cc6  sub     rsp, 60h
0x180018cca  mov     rax, cs:__security_cookie
0x180018cd1  xor     rax, rsp
0x180018cd4  mov     [rsp+68h+var_18], rax
0x180018cd9  mov     rbx, rcx
0x180018cdc  add     rcx, 0C0h; lpCriticalSection
0x180018ce3  call    cs:__imp_EnterCriticalSection
0x180018ce9  inc     dword ptr [rbx+0E8h]
0x180018cef  test    dword ptr [rbx+40h], 100h
0x180018cf6  jnz     short loc_180018D48
0x180018cf8  mov     rcx, [rbx+0F0h]
0x180018cff  test    rcx, rcx
0x180018d02  jz      loc_180018D8D
0x180018d08  cmp     dword ptr [rbx+0E8h], 1
0x180018d0f  jnz     short loc_180018D8D
0x180018d11  mov     r8d, [rbx+0B8h]
0x180018d18  lea     r9, [rsp+68h+var_48]
0x180018d1d  xorps   xmm0, xmm0
0x180018d20  mov     edx, 1
0x180018d25  movups  [rsp+68h+var_48], xmm0
0x180018d2a  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180018d2f  movups  [rsp+68h+var_28], xmm0
0x180018d34  call    TestQueryData
0x180018d39  mov     rcx, [rsp+68h+pv+8]; pv
0x180018d3e  test    eax, eax
0x180018d40  jnz     short loc_180018D5D
0x180018d42  call    cs:__imp_CoTaskMemFree
0x180018d48  xor     al, al
0x180018d4a  mov     rcx, [rsp+68h+var_18]
0x180018d4f  xor     rcx, rsp; StackCookie
0x180018d52  call    __security_check_cookie
0x180018d57  add     rsp, 60h
0x180018d5b  pop     rbx
0x180018d5c  retn
0x180018d5d  mov     eax, dword ptr [rsp+68h+pv+4]
0x180018d61  or      [rbx+40h], eax
0x180018d64  test    rcx, rcx
0x180018d67  jz      short loc_180018D7D
0x180018d69  lea     rdx, [rsp+68h+var_48]
0x180018d6e  mov     rcx, rbx
0x180018d71  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180018d76  mov     rcx, [rsp+68h+pv+8]
0x180018d7b  jmp     short loc_180018D87
0x180018d7d  mov     edx, dword ptr [rsp+68h+pv]
0x180018d81  mov     [rbx+0B8h], edx
0x180018d87  call    cs:__imp_CoTaskMemFree
0x180018d8d  mov     al, 1
0x180018d8f  jmp     short loc_180018D4A
```
