# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x1800342c0`
- end: `0x18003438d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800273f0`

## callees

- `0x180002520`
- `0x18001b7f0`
- `0x1800342c0`
- `0x180034b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003433e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003433e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034383`

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
0x1800342c0  push    rbx
0x1800342c2  sub     rsp, 60h
0x1800342c6  mov     rax, cs:__security_cookie
0x1800342cd  xor     rax, rsp
0x1800342d0  mov     [rsp+68h+var_18], rax
0x1800342d5  mov     rbx, rcx
0x1800342d8  add     rcx, 0C0h; lpCriticalSection
0x1800342df  call    cs:__imp_EnterCriticalSection
0x1800342e5  inc     dword ptr [rbx+0E8h]
0x1800342eb  test    dword ptr [rbx+40h], 100h
0x1800342f2  jnz     short loc_180034344
0x1800342f4  mov     rcx, [rbx+0F0h]
0x1800342fb  test    rcx, rcx
0x1800342fe  jz      loc_180034389
0x180034304  cmp     dword ptr [rbx+0E8h], 1
0x18003430b  jnz     short loc_180034389
0x18003430d  mov     r8d, [rbx+0B8h]
0x180034314  lea     r9, [rsp+68h+var_48]
0x180034319  xorps   xmm0, xmm0
0x18003431c  mov     edx, 1
0x180034321  movups  [rsp+68h+var_48], xmm0
0x180034326  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18003432b  movups  [rsp+68h+var_28], xmm0
0x180034330  call    TestQueryData
0x180034335  mov     rcx, [rsp+68h+pv+8]; pv
0x18003433a  test    eax, eax
0x18003433c  jnz     short loc_180034359
0x18003433e  call    cs:__imp_CoTaskMemFree
0x180034344  xor     al, al
0x180034346  mov     rcx, [rsp+68h+var_18]
0x18003434b  xor     rcx, rsp; StackCookie
0x18003434e  call    __security_check_cookie
0x180034353  add     rsp, 60h
0x180034357  pop     rbx
0x180034358  retn
0x180034359  mov     eax, dword ptr [rsp+68h+pv+4]
0x18003435d  or      [rbx+40h], eax
0x180034360  test    rcx, rcx
0x180034363  jz      short loc_180034379
0x180034365  lea     rdx, [rsp+68h+var_48]
0x18003436a  mov     rcx, rbx
0x18003436d  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180034372  mov     rcx, [rsp+68h+pv+8]
0x180034377  jmp     short loc_180034383
0x180034379  mov     edx, dword ptr [rsp+68h+pv]
0x18003437d  mov     [rbx+0B8h], edx
0x180034383  call    cs:__imp_CoTaskMemFree
0x180034389  mov     al, 1
0x18003438b  jmp     short loc_180034346
```
