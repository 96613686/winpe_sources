# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18001d134`
- end: `0x18001d201`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012e28`
- `0x180019660`

## callees

- `0x1800021d0`
- `0x18001d134`
- `0x18001dcf4`
- `0x1800219a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d153`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1f7`

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
0x18001d134  push    rbx
0x18001d136  sub     rsp, 60h
0x18001d13a  mov     rax, cs:__security_cookie
0x18001d141  xor     rax, rsp
0x18001d144  mov     [rsp+68h+var_18], rax
0x18001d149  mov     rbx, rcx
0x18001d14c  add     rcx, 0C0h; lpCriticalSection
0x18001d153  call    cs:__imp_EnterCriticalSection
0x18001d159  inc     dword ptr [rbx+0E8h]
0x18001d15f  test    dword ptr [rbx+40h], 100h
0x18001d166  jnz     short loc_18001D1B8
0x18001d168  mov     rcx, [rbx+0F0h]
0x18001d16f  test    rcx, rcx
0x18001d172  jz      loc_18001D1FD
0x18001d178  cmp     dword ptr [rbx+0E8h], 1
0x18001d17f  jnz     short loc_18001D1FD
0x18001d181  mov     r8d, [rbx+0B8h]
0x18001d188  lea     r9, [rsp+68h+var_48]
0x18001d18d  xorps   xmm0, xmm0
0x18001d190  mov     edx, 1
0x18001d195  movups  [rsp+68h+var_48], xmm0
0x18001d19a  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18001d19f  movups  [rsp+68h+var_28], xmm0
0x18001d1a4  call    TestQueryData
0x18001d1a9  mov     rcx, [rsp+68h+pv+8]; pv
0x18001d1ae  test    eax, eax
0x18001d1b0  jnz     short loc_18001D1CD
0x18001d1b2  call    cs:__imp_CoTaskMemFree
0x18001d1b8  xor     al, al
0x18001d1ba  mov     rcx, [rsp+68h+var_18]
0x18001d1bf  xor     rcx, rsp; StackCookie
0x18001d1c2  call    __security_check_cookie
0x18001d1c7  add     rsp, 60h
0x18001d1cb  pop     rbx
0x18001d1cc  retn
0x18001d1cd  mov     eax, dword ptr [rsp+68h+pv+4]
0x18001d1d1  or      [rbx+40h], eax
0x18001d1d4  test    rcx, rcx
0x18001d1d7  jz      short loc_18001D1ED
0x18001d1d9  lea     rdx, [rsp+68h+var_48]
0x18001d1de  mov     rcx, rbx
0x18001d1e1  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18001d1e6  mov     rcx, [rsp+68h+pv+8]
0x18001d1eb  jmp     short loc_18001D1F7
0x18001d1ed  mov     edx, dword ptr [rsp+68h+pv]
0x18001d1f1  mov     [rbx+0B8h], edx
0x18001d1f7  call    cs:__imp_CoTaskMemFree
0x18001d1fd  mov     al, 1
0x18001d1ff  jmp     short loc_18001D1BA
```
