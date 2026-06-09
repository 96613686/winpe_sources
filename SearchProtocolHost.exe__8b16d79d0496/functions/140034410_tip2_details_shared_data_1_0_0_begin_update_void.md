# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x140034410`
- end: `0x1400344dd`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140020ed0`
- `0x14002d100`

## callees

- `0x140005240`
- `0x140034410`
- `0x140034cb0`
- `0x140039f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003442f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003442f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003448e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400344d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003448e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400344d3`

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
0x140034410  push    rbx
0x140034412  sub     rsp, 60h
0x140034416  mov     rax, cs:__security_cookie
0x14003441d  xor     rax, rsp
0x140034420  mov     [rsp+68h+var_18], rax
0x140034425  mov     rbx, rcx
0x140034428  add     rcx, 0C0h; lpCriticalSection
0x14003442f  call    cs:__imp_EnterCriticalSection
0x140034435  inc     dword ptr [rbx+0E8h]
0x14003443b  test    dword ptr [rbx+40h], 100h
0x140034442  jnz     short loc_140034494
0x140034444  mov     rcx, [rbx+0F0h]
0x14003444b  test    rcx, rcx
0x14003444e  jz      loc_1400344D9
0x140034454  cmp     dword ptr [rbx+0E8h], 1
0x14003445b  jnz     short loc_1400344D9
0x14003445d  mov     r8d, [rbx+0B8h]
0x140034464  lea     r9, [rsp+68h+var_48]
0x140034469  xorps   xmm0, xmm0
0x14003446c  mov     edx, 1
0x140034471  movups  [rsp+68h+var_48], xmm0
0x140034476  movups  xmmword ptr [rsp+68h+pv], xmm0
0x14003447b  movups  [rsp+68h+var_28], xmm0
0x140034480  call    TestQueryData
0x140034485  mov     rcx, [rsp+68h+pv+8]; pv
0x14003448a  test    eax, eax
0x14003448c  jnz     short loc_1400344A9
0x14003448e  call    cs:__imp_CoTaskMemFree
0x140034494  xor     al, al
0x140034496  mov     rcx, [rsp+68h+var_18]
0x14003449b  xor     rcx, rsp; StackCookie
0x14003449e  call    __security_check_cookie
0x1400344a3  add     rsp, 60h
0x1400344a7  pop     rbx
0x1400344a8  retn
0x1400344a9  mov     eax, dword ptr [rsp+68h+pv+4]
0x1400344ad  or      [rbx+40h], eax
0x1400344b0  test    rcx, rcx
0x1400344b3  jz      short loc_1400344C9
0x1400344b5  lea     rdx, [rsp+68h+var_48]
0x1400344ba  mov     rcx, rbx
0x1400344bd  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1400344c2  mov     rcx, [rsp+68h+pv+8]
0x1400344c7  jmp     short loc_1400344D3
0x1400344c9  mov     edx, dword ptr [rsp+68h+pv]
0x1400344cd  mov     [rbx+0B8h], edx
0x1400344d3  call    cs:__imp_CoTaskMemFree
0x1400344d9  mov     al, 1
0x1400344db  jmp     short loc_140034496
```
