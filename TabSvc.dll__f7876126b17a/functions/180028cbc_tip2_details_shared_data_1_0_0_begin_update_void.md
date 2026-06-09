# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180028cbc`
- end: `0x180028d89`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `char __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800194b0`
- `0x180023ac0`
- `0x18002fefe`

## callees

- `0x18001af84`
- `0x18001bbe0`
- `0x180028cbc`
- `0x18002b308`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028d3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028d3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028d7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028cdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028cdb`

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
0x180028cbc  push    rbx
0x180028cbe  sub     rsp, 60h
0x180028cc2  mov     rax, cs:__security_cookie
0x180028cc9  xor     rax, rsp
0x180028ccc  mov     [rsp+68h+var_18], rax
0x180028cd1  mov     rbx, rcx
0x180028cd4  add     rcx, 0C0h; lpCriticalSection
0x180028cdb  call    cs:__imp_EnterCriticalSection
0x180028ce1  inc     dword ptr [rbx+0E8h]
0x180028ce7  test    dword ptr [rbx+40h], 100h
0x180028cee  jnz     short loc_180028D40
0x180028cf0  mov     rcx, [rbx+0F0h]
0x180028cf7  test    rcx, rcx
0x180028cfa  jz      loc_180028D85
0x180028d00  cmp     dword ptr [rbx+0E8h], 1
0x180028d07  jnz     short loc_180028D85
0x180028d09  mov     r8d, [rbx+0B8h]
0x180028d10  lea     r9, [rsp+68h+var_48]
0x180028d15  xorps   xmm0, xmm0
0x180028d18  mov     edx, 1
0x180028d1d  movups  [rsp+68h+var_48], xmm0
0x180028d22  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180028d27  movups  [rsp+68h+var_28], xmm0
0x180028d2c  call    TestQueryData
0x180028d31  mov     rcx, [rsp+68h+pv+8]; pv
0x180028d36  test    eax, eax
0x180028d38  jnz     short loc_180028D55
0x180028d3a  call    cs:__imp_CoTaskMemFree
0x180028d40  xor     al, al
0x180028d42  mov     rcx, [rsp+68h+var_18]
0x180028d47  xor     rcx, rsp; StackCookie
0x180028d4a  call    __security_check_cookie
0x180028d4f  add     rsp, 60h
0x180028d53  pop     rbx
0x180028d54  retn
0x180028d55  mov     eax, dword ptr [rsp+68h+pv+4]
0x180028d59  or      [rbx+40h], eax
0x180028d5c  test    rcx, rcx
0x180028d5f  jz      short loc_180028D75
0x180028d61  lea     rdx, [rsp+68h+var_48]
0x180028d66  mov     rcx, rbx
0x180028d69  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180028d6e  mov     rcx, [rsp+68h+pv+8]
0x180028d73  jmp     short loc_180028D7F
0x180028d75  mov     edx, dword ptr [rsp+68h+pv]
0x180028d79  mov     [rbx+0B8h], edx
0x180028d7f  call    cs:__imp_CoTaskMemFree
0x180028d85  mov     al, 1
0x180028d87  jmp     short loc_180028D42
```
