# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180037bc8`
- end: `0x180037c95`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `char __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180034ca0`
- `0x1800390ac`
- `0x1800428ac`

## callees

- `0x180009190`
- `0x18002c8f8`
- `0x180037bc8`
- `0x180038098`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037be7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037be7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c8b`

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
0x180037bc8  push    rbx
0x180037bca  sub     rsp, 60h
0x180037bce  mov     rax, cs:__security_cookie
0x180037bd5  xor     rax, rsp
0x180037bd8  mov     [rsp+68h+var_18], rax
0x180037bdd  mov     rbx, rcx
0x180037be0  add     rcx, 0C0h; lpCriticalSection
0x180037be7  call    cs:__imp_EnterCriticalSection
0x180037bed  inc     dword ptr [rbx+0E8h]
0x180037bf3  test    dword ptr [rbx+40h], 100h
0x180037bfa  jnz     short loc_180037C4C
0x180037bfc  mov     rcx, [rbx+0F0h]
0x180037c03  test    rcx, rcx
0x180037c06  jz      loc_180037C91
0x180037c0c  cmp     dword ptr [rbx+0E8h], 1
0x180037c13  jnz     short loc_180037C91
0x180037c15  mov     r8d, [rbx+0B8h]
0x180037c1c  lea     r9, [rsp+68h+var_48]
0x180037c21  xorps   xmm0, xmm0
0x180037c24  mov     edx, 1
0x180037c29  movups  [rsp+68h+var_48], xmm0
0x180037c2e  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180037c33  movups  [rsp+68h+var_28], xmm0
0x180037c38  call    TestQueryData
0x180037c3d  mov     rcx, [rsp+68h+pv+8]; pv
0x180037c42  test    eax, eax
0x180037c44  jnz     short loc_180037C61
0x180037c46  call    cs:__imp_CoTaskMemFree
0x180037c4c  xor     al, al
0x180037c4e  mov     rcx, [rsp+68h+var_18]
0x180037c53  xor     rcx, rsp; StackCookie
0x180037c56  call    __security_check_cookie
0x180037c5b  add     rsp, 60h
0x180037c5f  pop     rbx
0x180037c60  retn
0x180037c61  mov     eax, dword ptr [rsp+68h+pv+4]
0x180037c65  or      [rbx+40h], eax
0x180037c68  test    rcx, rcx
0x180037c6b  jz      short loc_180037C81
0x180037c6d  lea     rdx, [rsp+68h+var_48]
0x180037c72  mov     rcx, rbx
0x180037c75  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180037c7a  mov     rcx, [rsp+68h+pv+8]
0x180037c7f  jmp     short loc_180037C8B
0x180037c81  mov     edx, dword ptr [rsp+68h+pv]
0x180037c85  mov     [rbx+0B8h], edx
0x180037c8b  call    cs:__imp_CoTaskMemFree
0x180037c91  mov     al, 1
0x180037c93  jmp     short loc_180037C4E
```
