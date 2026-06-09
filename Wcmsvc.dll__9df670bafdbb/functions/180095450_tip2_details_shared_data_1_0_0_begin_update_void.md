# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180095450`
- end: `0x18009551d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180095294`

## callees

- `0x180084f50`
- `0x180095450`
- `0x180095938`
- `0x180097ffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009546f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009546f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800954ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800954ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095513`

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
0x180095450  push    rbx
0x180095452  sub     rsp, 60h
0x180095456  mov     rax, cs:__security_cookie
0x18009545d  xor     rax, rsp
0x180095460  mov     [rsp+68h+var_18], rax
0x180095465  mov     rbx, rcx
0x180095468  add     rcx, 0C0h; lpCriticalSection
0x18009546f  call    cs:__imp_EnterCriticalSection
0x180095475  inc     dword ptr [rbx+0E8h]
0x18009547b  test    dword ptr [rbx+40h], 100h
0x180095482  jnz     short loc_1800954D4
0x180095484  mov     rcx, [rbx+0F0h]
0x18009548b  test    rcx, rcx
0x18009548e  jz      loc_180095519
0x180095494  cmp     dword ptr [rbx+0E8h], 1
0x18009549b  jnz     short loc_180095519
0x18009549d  mov     r8d, [rbx+0B8h]
0x1800954a4  lea     r9, [rsp+68h+var_48]
0x1800954a9  xorps   xmm0, xmm0
0x1800954ac  mov     edx, 1
0x1800954b1  movups  [rsp+68h+var_48], xmm0
0x1800954b6  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800954bb  movups  [rsp+68h+var_28], xmm0
0x1800954c0  call    TestQueryData
0x1800954c5  mov     rcx, [rsp+68h+pv+8]; pv
0x1800954ca  test    eax, eax
0x1800954cc  jnz     short loc_1800954E9
0x1800954ce  call    cs:__imp_CoTaskMemFree
0x1800954d4  xor     al, al
0x1800954d6  mov     rcx, [rsp+68h+var_18]
0x1800954db  xor     rcx, rsp; StackCookie
0x1800954de  call    __security_check_cookie
0x1800954e3  add     rsp, 60h
0x1800954e7  pop     rbx
0x1800954e8  retn
0x1800954e9  mov     eax, dword ptr [rsp+68h+pv+4]
0x1800954ed  or      [rbx+40h], eax
0x1800954f0  test    rcx, rcx
0x1800954f3  jz      short loc_180095509
0x1800954f5  lea     rdx, [rsp+68h+var_48]
0x1800954fa  mov     rcx, rbx
0x1800954fd  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180095502  mov     rcx, [rsp+68h+pv+8]
0x180095507  jmp     short loc_180095513
0x180095509  mov     edx, dword ptr [rsp+68h+pv]
0x18009550d  mov     [rbx+0B8h], edx
0x180095513  call    cs:__imp_CoTaskMemFree
0x180095519  mov     al, 1
0x18009551b  jmp     short loc_1800954D6
```
