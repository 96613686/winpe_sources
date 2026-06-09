# tip2::details::shared_data<1,0,1>::begin_update(void)

- ea: `0x180121504`
- end: `0x1801215d1`
- name: `?begin_update@?$shared_data@$00$0A@$00@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18011c5d0`
- `0x18013c654`
- `0x18013d048`

## callees

- `0x1800a98c0`
- `0x180121504`
- `0x180121958`
- `0x180123fc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121523`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180121582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801215c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180121582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801215c7`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,1>::begin_update(__int64 a1)
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
      tip2::details::shared_data<1,0,1>::deserialize_data(a1, &v7);
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
0x180121504  push    rbx
0x180121506  sub     rsp, 60h
0x18012150a  mov     rax, cs:__security_cookie
0x180121511  xor     rax, rsp
0x180121514  mov     [rsp+68h+var_18], rax
0x180121519  mov     rbx, rcx
0x18012151c  add     rcx, 0C0h; lpCriticalSection
0x180121523  call    cs:__imp_EnterCriticalSection
0x180121529  inc     dword ptr [rbx+0E8h]
0x18012152f  test    dword ptr [rbx+40h], 100h
0x180121536  jnz     short loc_180121588
0x180121538  mov     rcx, [rbx+0F0h]
0x18012153f  test    rcx, rcx
0x180121542  jz      loc_1801215CD
0x180121548  cmp     dword ptr [rbx+0E8h], 1
0x18012154f  jnz     short loc_1801215CD
0x180121551  mov     r8d, [rbx+0B8h]
0x180121558  lea     r9, [rsp+68h+var_48]
0x18012155d  xorps   xmm0, xmm0
0x180121560  mov     edx, 1
0x180121565  movups  [rsp+68h+var_48], xmm0
0x18012156a  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18012156f  movups  [rsp+68h+var_28], xmm0
0x180121574  call    TestQueryData
0x180121579  mov     rcx, [rsp+68h+pv+8]; pv
0x18012157e  test    eax, eax
0x180121580  jnz     short loc_18012159D
0x180121582  call    cs:__imp_CoTaskMemFree
0x180121588  xor     al, al
0x18012158a  mov     rcx, [rsp+68h+var_18]
0x18012158f  xor     rcx, rsp; StackCookie
0x180121592  call    __security_check_cookie
0x180121597  add     rsp, 60h
0x18012159b  pop     rbx
0x18012159c  retn
0x18012159d  mov     eax, dword ptr [rsp+68h+pv+4]
0x1801215a1  or      [rbx+40h], eax
0x1801215a4  test    rcx, rcx
0x1801215a7  jz      short loc_1801215BD
0x1801215a9  lea     rdx, [rsp+68h+var_48]
0x1801215ae  mov     rcx, rbx
0x1801215b1  call    ?deserialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1801215b6  mov     rcx, [rsp+68h+pv+8]
0x1801215bb  jmp     short loc_1801215C7
0x1801215bd  mov     edx, dword ptr [rsp+68h+pv]
0x1801215c1  mov     [rbx+0B8h], edx
0x1801215c7  call    cs:__imp_CoTaskMemFree
0x1801215cd  mov     al, 1
0x1801215cf  jmp     short loc_18012158A
```
