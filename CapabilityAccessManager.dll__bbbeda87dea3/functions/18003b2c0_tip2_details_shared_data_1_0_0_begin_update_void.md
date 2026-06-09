# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18003b2c0`
- end: `0x18003b38d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fb74`
- `0x18002fe74`
- `0x18003c6f4`
- `0x180049948`
- `0x18006874c`
- `0x18006a080`

## callees

- `0x1800094c0`
- `0x18003b2c0`
- `0x18003b828`
- `0x18003e0e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b2df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b2df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b383`

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
0x18003b2c0  push    rbx
0x18003b2c2  sub     rsp, 60h
0x18003b2c6  mov     rax, cs:__security_cookie
0x18003b2cd  xor     rax, rsp
0x18003b2d0  mov     [rsp+68h+var_18], rax
0x18003b2d5  mov     rbx, rcx
0x18003b2d8  add     rcx, 0C0h; lpCriticalSection
0x18003b2df  call    cs:__imp_EnterCriticalSection
0x18003b2e5  inc     dword ptr [rbx+0E8h]
0x18003b2eb  test    dword ptr [rbx+40h], 100h
0x18003b2f2  jnz     short loc_18003B344
0x18003b2f4  mov     rcx, [rbx+0F0h]
0x18003b2fb  test    rcx, rcx
0x18003b2fe  jz      loc_18003B389
0x18003b304  cmp     dword ptr [rbx+0E8h], 1
0x18003b30b  jnz     short loc_18003B389
0x18003b30d  mov     r8d, [rbx+0B8h]
0x18003b314  lea     r9, [rsp+68h+var_48]
0x18003b319  xorps   xmm0, xmm0
0x18003b31c  mov     edx, 1
0x18003b321  movups  [rsp+68h+var_48], xmm0
0x18003b326  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18003b32b  movups  [rsp+68h+var_28], xmm0
0x18003b330  call    TestQueryData
0x18003b335  mov     rcx, [rsp+68h+pv+8]; pv
0x18003b33a  test    eax, eax
0x18003b33c  jnz     short loc_18003B359
0x18003b33e  call    cs:__imp_CoTaskMemFree
0x18003b344  xor     al, al
0x18003b346  mov     rcx, [rsp+68h+var_18]
0x18003b34b  xor     rcx, rsp; StackCookie
0x18003b34e  call    __security_check_cookie
0x18003b353  add     rsp, 60h
0x18003b357  pop     rbx
0x18003b358  retn
0x18003b359  mov     eax, dword ptr [rsp+68h+pv+4]
0x18003b35d  or      [rbx+40h], eax
0x18003b360  test    rcx, rcx
0x18003b363  jz      short loc_18003B379
0x18003b365  lea     rdx, [rsp+68h+var_48]
0x18003b36a  mov     rcx, rbx
0x18003b36d  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18003b372  mov     rcx, [rsp+68h+pv+8]
0x18003b377  jmp     short loc_18003B383
0x18003b379  mov     edx, dword ptr [rsp+68h+pv]
0x18003b37d  mov     [rbx+0B8h], edx
0x18003b383  call    cs:__imp_CoTaskMemFree
0x18003b389  mov     al, 1
0x18003b38b  jmp     short loc_18003B346
```
