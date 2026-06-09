# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18004a0c0`
- end: `0x18004a18d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c34c`
- `0x180042950`
- `0x180042eb0`
- `0x180045510`
- `0x18004c1d0`
- `0x1800bdd18`
- `0x1800bdeec`

## callees

- `0x180006e50`
- `0x18004a0c0`
- `0x18004a900`
- `0x18004d980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a0df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a0df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a13e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a183`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a13e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a183`

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
0x18004a0c0  push    rbx
0x18004a0c2  sub     rsp, 60h
0x18004a0c6  mov     rax, cs:__security_cookie
0x18004a0cd  xor     rax, rsp
0x18004a0d0  mov     [rsp+68h+var_18], rax
0x18004a0d5  mov     rbx, rcx
0x18004a0d8  add     rcx, 0C0h; lpCriticalSection
0x18004a0df  call    cs:__imp_EnterCriticalSection
0x18004a0e5  inc     dword ptr [rbx+0E8h]
0x18004a0eb  test    dword ptr [rbx+40h], 100h
0x18004a0f2  jnz     short loc_18004A144
0x18004a0f4  mov     rcx, [rbx+0F0h]
0x18004a0fb  test    rcx, rcx
0x18004a0fe  jz      loc_18004A189
0x18004a104  cmp     dword ptr [rbx+0E8h], 1
0x18004a10b  jnz     short loc_18004A189
0x18004a10d  mov     r8d, [rbx+0B8h]
0x18004a114  lea     r9, [rsp+68h+var_48]
0x18004a119  xorps   xmm0, xmm0
0x18004a11c  mov     edx, 1
0x18004a121  movups  [rsp+68h+var_48], xmm0
0x18004a126  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18004a12b  movups  [rsp+68h+var_28], xmm0
0x18004a130  call    TestQueryData
0x18004a135  mov     rcx, [rsp+68h+pv+8]; pv
0x18004a13a  test    eax, eax
0x18004a13c  jnz     short loc_18004A159
0x18004a13e  call    cs:__imp_CoTaskMemFree
0x18004a144  xor     al, al
0x18004a146  mov     rcx, [rsp+68h+var_18]
0x18004a14b  xor     rcx, rsp; StackCookie
0x18004a14e  call    __security_check_cookie
0x18004a153  add     rsp, 60h
0x18004a157  pop     rbx
0x18004a158  retn
0x18004a159  mov     eax, dword ptr [rsp+68h+pv+4]
0x18004a15d  or      [rbx+40h], eax
0x18004a160  test    rcx, rcx
0x18004a163  jz      short loc_18004A179
0x18004a165  lea     rdx, [rsp+68h+var_48]
0x18004a16a  mov     rcx, rbx
0x18004a16d  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004a172  mov     rcx, [rsp+68h+pv+8]
0x18004a177  jmp     short loc_18004A183
0x18004a179  mov     edx, dword ptr [rsp+68h+pv]
0x18004a17d  mov     [rbx+0B8h], edx
0x18004a183  call    cs:__imp_CoTaskMemFree
0x18004a189  mov     al, 1
0x18004a18b  jmp     short loc_18004A146
```
