# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x1800ccc50`
- end: `0x1800ccd1d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c936c`
- `0x1800d8920`

## callees

- `0x180005860`
- `0x1800742c0`
- `0x1800ccc50`
- `0x1800ccf38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ccc6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ccc6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cccce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ccd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cccce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ccd13`

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
0x1800ccc50  push    rbx
0x1800ccc52  sub     rsp, 60h
0x1800ccc56  mov     rax, cs:__security_cookie
0x1800ccc5d  xor     rax, rsp
0x1800ccc60  mov     [rsp+68h+var_18], rax
0x1800ccc65  mov     rbx, rcx
0x1800ccc68  add     rcx, 0C0h; lpCriticalSection
0x1800ccc6f  call    cs:__imp_EnterCriticalSection
0x1800ccc75  inc     dword ptr [rbx+0E8h]
0x1800ccc7b  test    dword ptr [rbx+40h], 100h
0x1800ccc82  jnz     short loc_1800CCCD4
0x1800ccc84  mov     rcx, [rbx+0F0h]
0x1800ccc8b  test    rcx, rcx
0x1800ccc8e  jz      loc_1800CCD19
0x1800ccc94  cmp     dword ptr [rbx+0E8h], 1
0x1800ccc9b  jnz     short loc_1800CCD19
0x1800ccc9d  mov     r8d, [rbx+0B8h]
0x1800ccca4  lea     r9, [rsp+68h+var_48]
0x1800ccca9  xorps   xmm0, xmm0
0x1800cccac  mov     edx, 1
0x1800cccb1  movups  [rsp+68h+var_48], xmm0
0x1800cccb6  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800cccbb  movups  [rsp+68h+var_28], xmm0
0x1800cccc0  call    TestQueryData
0x1800cccc5  mov     rcx, [rsp+68h+pv+8]; pv
0x1800cccca  test    eax, eax
0x1800ccccc  jnz     short loc_1800CCCE9
0x1800cccce  call    cs:__imp_CoTaskMemFree
0x1800cccd4  xor     al, al
0x1800cccd6  mov     rcx, [rsp+68h+var_18]
0x1800cccdb  xor     rcx, rsp; StackCookie
0x1800cccde  call    __security_check_cookie
0x1800ccce3  add     rsp, 60h
0x1800ccce7  pop     rbx
0x1800ccce8  retn
0x1800ccce9  mov     eax, dword ptr [rsp+68h+pv+4]
0x1800ccced  or      [rbx+40h], eax
0x1800cccf0  test    rcx, rcx
0x1800cccf3  jz      short loc_1800CCD09
0x1800cccf5  lea     rdx, [rsp+68h+var_48]
0x1800cccfa  mov     rcx, rbx
0x1800cccfd  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800ccd02  mov     rcx, [rsp+68h+pv+8]
0x1800ccd07  jmp     short loc_1800CCD13
0x1800ccd09  mov     edx, dword ptr [rsp+68h+pv]
0x1800ccd0d  mov     [rbx+0B8h], edx
0x1800ccd13  call    cs:__imp_CoTaskMemFree
0x1800ccd19  mov     al, 1
0x1800ccd1b  jmp     short loc_1800CCCD6
```
