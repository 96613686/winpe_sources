# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18007611c`
- end: `0x1800761e9`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180073a9c`
- `0x18007ded0`

## callees

- `0x180057ac4`
- `0x180061320`
- `0x18007611c`
- `0x1800785e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007613b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007613b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007619a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800761df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007619a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800761df`

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
0x18007611c  push    rbx
0x18007611e  sub     rsp, 60h
0x180076122  mov     rax, cs:__security_cookie
0x180076129  xor     rax, rsp
0x18007612c  mov     [rsp+68h+var_18], rax
0x180076131  mov     rbx, rcx
0x180076134  add     rcx, 0C0h; lpCriticalSection
0x18007613b  call    cs:__imp_EnterCriticalSection
0x180076141  inc     dword ptr [rbx+0E8h]
0x180076147  test    dword ptr [rbx+40h], 100h
0x18007614e  jnz     short loc_1800761A0
0x180076150  mov     rcx, [rbx+0F0h]
0x180076157  test    rcx, rcx
0x18007615a  jz      loc_1800761E5
0x180076160  cmp     dword ptr [rbx+0E8h], 1
0x180076167  jnz     short loc_1800761E5
0x180076169  mov     r8d, [rbx+0B8h]
0x180076170  lea     r9, [rsp+68h+var_48]
0x180076175  xorps   xmm0, xmm0
0x180076178  mov     edx, 1
0x18007617d  movups  [rsp+68h+var_48], xmm0
0x180076182  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180076187  movups  [rsp+68h+var_28], xmm0
0x18007618c  call    TestQueryData
0x180076191  mov     rcx, [rsp+68h+pv+8]; pv
0x180076196  test    eax, eax
0x180076198  jnz     short loc_1800761B5
0x18007619a  call    cs:__imp_CoTaskMemFree
0x1800761a0  xor     al, al
0x1800761a2  mov     rcx, [rsp+68h+var_18]
0x1800761a7  xor     rcx, rsp; StackCookie
0x1800761aa  call    __security_check_cookie
0x1800761af  add     rsp, 60h
0x1800761b3  pop     rbx
0x1800761b4  retn
0x1800761b5  mov     eax, dword ptr [rsp+68h+pv+4]
0x1800761b9  or      [rbx+40h], eax
0x1800761bc  test    rcx, rcx
0x1800761bf  jz      short loc_1800761D5
0x1800761c1  lea     rdx, [rsp+68h+var_48]
0x1800761c6  mov     rcx, rbx
0x1800761c9  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800761ce  mov     rcx, [rsp+68h+pv+8]
0x1800761d3  jmp     short loc_1800761DF
0x1800761d5  mov     edx, dword ptr [rsp+68h+pv]
0x1800761d9  mov     [rbx+0B8h], edx
0x1800761df  call    cs:__imp_CoTaskMemFree
0x1800761e5  mov     al, 1
0x1800761e7  jmp     short loc_1800761A2
```
