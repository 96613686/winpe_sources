# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18004dabc`
- end: `0x18004db89`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ae0c`
- `0x180062080`
- `0x1800631d8`

## callees

- `0x180003ed0`
- `0x18004dabc`
- `0x18004df78`
- `0x180051b68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dadb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dadb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004db3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004db7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004db3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004db7f`

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
0x18004dabc  push    rbx
0x18004dabe  sub     rsp, 60h
0x18004dac2  mov     rax, cs:__security_cookie
0x18004dac9  xor     rax, rsp
0x18004dacc  mov     [rsp+68h+var_18], rax
0x18004dad1  mov     rbx, rcx
0x18004dad4  add     rcx, 0C0h; lpCriticalSection
0x18004dadb  call    cs:__imp_EnterCriticalSection
0x18004dae1  inc     dword ptr [rbx+0E8h]
0x18004dae7  test    dword ptr [rbx+40h], 100h
0x18004daee  jnz     short loc_18004DB40
0x18004daf0  mov     rcx, [rbx+0F0h]
0x18004daf7  test    rcx, rcx
0x18004dafa  jz      loc_18004DB85
0x18004db00  cmp     dword ptr [rbx+0E8h], 1
0x18004db07  jnz     short loc_18004DB85
0x18004db09  mov     r8d, [rbx+0B8h]
0x18004db10  lea     r9, [rsp+68h+var_48]
0x18004db15  xorps   xmm0, xmm0
0x18004db18  mov     edx, 1
0x18004db1d  movups  [rsp+68h+var_48], xmm0
0x18004db22  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18004db27  movups  [rsp+68h+var_28], xmm0
0x18004db2c  call    TestQueryData
0x18004db31  mov     rcx, [rsp+68h+pv+8]; pv
0x18004db36  test    eax, eax
0x18004db38  jnz     short loc_18004DB55
0x18004db3a  call    cs:__imp_CoTaskMemFree
0x18004db40  xor     al, al
0x18004db42  mov     rcx, [rsp+68h+var_18]
0x18004db47  xor     rcx, rsp; StackCookie
0x18004db4a  call    __security_check_cookie
0x18004db4f  add     rsp, 60h
0x18004db53  pop     rbx
0x18004db54  retn
0x18004db55  mov     eax, dword ptr [rsp+68h+pv+4]
0x18004db59  or      [rbx+40h], eax
0x18004db5c  test    rcx, rcx
0x18004db5f  jz      short loc_18004DB75
0x18004db61  lea     rdx, [rsp+68h+var_48]
0x18004db66  mov     rcx, rbx
0x18004db69  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004db6e  mov     rcx, [rsp+68h+pv+8]
0x18004db73  jmp     short loc_18004DB7F
0x18004db75  mov     edx, dword ptr [rsp+68h+pv]
0x18004db79  mov     [rbx+0B8h], edx
0x18004db7f  call    cs:__imp_CoTaskMemFree
0x18004db85  mov     al, 1
0x18004db87  jmp     short loc_18004DB42
```
