# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18003c1a0`
- end: `0x18003c26d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180036028`
- `0x180039ed0`
- `0x18003eed4`

## callees

- `0x1800032b0`
- `0x18003c1a0`
- `0x18003c738`
- `0x18003fab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c1bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c1bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c21e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c263`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c21e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c263`

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
0x18003c1a0  push    rbx
0x18003c1a2  sub     rsp, 60h
0x18003c1a6  mov     rax, cs:__security_cookie
0x18003c1ad  xor     rax, rsp
0x18003c1b0  mov     [rsp+68h+var_18], rax
0x18003c1b5  mov     rbx, rcx
0x18003c1b8  add     rcx, 0C0h; lpCriticalSection
0x18003c1bf  call    cs:__imp_EnterCriticalSection
0x18003c1c5  inc     dword ptr [rbx+0E8h]
0x18003c1cb  test    dword ptr [rbx+40h], 100h
0x18003c1d2  jnz     short loc_18003C224
0x18003c1d4  mov     rcx, [rbx+0F0h]
0x18003c1db  test    rcx, rcx
0x18003c1de  jz      loc_18003C269
0x18003c1e4  cmp     dword ptr [rbx+0E8h], 1
0x18003c1eb  jnz     short loc_18003C269
0x18003c1ed  mov     r8d, [rbx+0B8h]
0x18003c1f4  lea     r9, [rsp+68h+var_48]
0x18003c1f9  xorps   xmm0, xmm0
0x18003c1fc  mov     edx, 1
0x18003c201  movups  [rsp+68h+var_48], xmm0
0x18003c206  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18003c20b  movups  [rsp+68h+var_28], xmm0
0x18003c210  call    TestQueryData
0x18003c215  mov     rcx, [rsp+68h+pv+8]; pv
0x18003c21a  test    eax, eax
0x18003c21c  jnz     short loc_18003C239
0x18003c21e  call    cs:__imp_CoTaskMemFree
0x18003c224  xor     al, al
0x18003c226  mov     rcx, [rsp+68h+var_18]
0x18003c22b  xor     rcx, rsp; StackCookie
0x18003c22e  call    __security_check_cookie
0x18003c233  add     rsp, 60h
0x18003c237  pop     rbx
0x18003c238  retn
0x18003c239  mov     eax, dword ptr [rsp+68h+pv+4]
0x18003c23d  or      [rbx+40h], eax
0x18003c240  test    rcx, rcx
0x18003c243  jz      short loc_18003C259
0x18003c245  lea     rdx, [rsp+68h+var_48]
0x18003c24a  mov     rcx, rbx
0x18003c24d  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18003c252  mov     rcx, [rsp+68h+pv+8]
0x18003c257  jmp     short loc_18003C263
0x18003c259  mov     edx, dword ptr [rsp+68h+pv]
0x18003c25d  mov     [rbx+0B8h], edx
0x18003c263  call    cs:__imp_CoTaskMemFree
0x18003c269  mov     al, 1
0x18003c26b  jmp     short loc_18003C226
```
