# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18004a290`
- end: `0x18004a35d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180047c2c`
- `0x1800493e0`

## callees

- `0x180027bc8`
- `0x18002cd20`
- `0x1800384a4`
- `0x18004a290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a2af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a2af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a30e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a353`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a30e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a353`

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
0x18004a290  push    rbx
0x18004a292  sub     rsp, 60h
0x18004a296  mov     rax, cs:__security_cookie
0x18004a29d  xor     rax, rsp
0x18004a2a0  mov     [rsp+68h+var_18], rax
0x18004a2a5  mov     rbx, rcx
0x18004a2a8  add     rcx, 0C0h; lpCriticalSection
0x18004a2af  call    cs:__imp_EnterCriticalSection
0x18004a2b5  inc     dword ptr [rbx+0E8h]
0x18004a2bb  test    dword ptr [rbx+40h], 100h
0x18004a2c2  jnz     short loc_18004A314
0x18004a2c4  mov     rcx, [rbx+0F0h]
0x18004a2cb  test    rcx, rcx
0x18004a2ce  jz      loc_18004A359
0x18004a2d4  cmp     dword ptr [rbx+0E8h], 1
0x18004a2db  jnz     short loc_18004A359
0x18004a2dd  mov     r8d, [rbx+0B8h]
0x18004a2e4  lea     r9, [rsp+68h+var_48]
0x18004a2e9  xorps   xmm0, xmm0
0x18004a2ec  mov     edx, 1
0x18004a2f1  movups  [rsp+68h+var_48], xmm0
0x18004a2f6  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18004a2fb  movups  [rsp+68h+var_28], xmm0
0x18004a300  call    TestQueryData
0x18004a305  mov     rcx, [rsp+68h+pv+8]; pv
0x18004a30a  test    eax, eax
0x18004a30c  jnz     short loc_18004A329
0x18004a30e  call    cs:__imp_CoTaskMemFree
0x18004a314  xor     al, al
0x18004a316  mov     rcx, [rsp+68h+var_18]
0x18004a31b  xor     rcx, rsp; StackCookie
0x18004a31e  call    __security_check_cookie
0x18004a323  add     rsp, 60h
0x18004a327  pop     rbx
0x18004a328  retn
0x18004a329  mov     eax, dword ptr [rsp+68h+pv+4]
0x18004a32d  or      [rbx+40h], eax
0x18004a330  test    rcx, rcx
0x18004a333  jz      short loc_18004A349
0x18004a335  lea     rdx, [rsp+68h+var_48]
0x18004a33a  mov     rcx, rbx
0x18004a33d  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004a342  mov     rcx, [rsp+68h+pv+8]
0x18004a347  jmp     short loc_18004A353
0x18004a349  mov     edx, dword ptr [rsp+68h+pv]
0x18004a34d  mov     [rbx+0B8h], edx
0x18004a353  call    cs:__imp_CoTaskMemFree
0x18004a359  mov     al, 1
0x18004a35b  jmp     short loc_18004A316
```
