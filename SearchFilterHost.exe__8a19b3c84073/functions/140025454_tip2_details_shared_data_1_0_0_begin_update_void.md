# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x140025454`
- end: `0x140025521`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `char __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001dd20`
- `0x14001df20`
- `0x14001ffa0`
- `0x140022180`

## callees

- `0x1400030a0`
- `0x1400185a0`
- `0x140025454`
- `0x1400256e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140025473`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140025473`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400254d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025517`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400254d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025517`

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
0x140025454  push    rbx
0x140025456  sub     rsp, 60h
0x14002545a  mov     rax, cs:__security_cookie
0x140025461  xor     rax, rsp
0x140025464  mov     [rsp+68h+var_18], rax
0x140025469  mov     rbx, rcx
0x14002546c  add     rcx, 0C0h; lpCriticalSection
0x140025473  call    cs:__imp_EnterCriticalSection
0x140025479  inc     dword ptr [rbx+0E8h]
0x14002547f  test    dword ptr [rbx+40h], 100h
0x140025486  jnz     short loc_1400254D8
0x140025488  mov     rcx, [rbx+0F0h]
0x14002548f  test    rcx, rcx
0x140025492  jz      loc_14002551D
0x140025498  cmp     dword ptr [rbx+0E8h], 1
0x14002549f  jnz     short loc_14002551D
0x1400254a1  mov     r8d, [rbx+0B8h]
0x1400254a8  lea     r9, [rsp+68h+var_48]
0x1400254ad  xorps   xmm0, xmm0
0x1400254b0  mov     edx, 1
0x1400254b5  movups  [rsp+68h+var_48], xmm0
0x1400254ba  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1400254bf  movups  [rsp+68h+var_28], xmm0
0x1400254c4  call    TestQueryData
0x1400254c9  mov     rcx, [rsp+68h+pv+8]; pv
0x1400254ce  test    eax, eax
0x1400254d0  jnz     short loc_1400254ED
0x1400254d2  call    cs:__imp_CoTaskMemFree
0x1400254d8  xor     al, al
0x1400254da  mov     rcx, [rsp+68h+var_18]
0x1400254df  xor     rcx, rsp; StackCookie
0x1400254e2  call    __security_check_cookie
0x1400254e7  add     rsp, 60h
0x1400254eb  pop     rbx
0x1400254ec  retn
0x1400254ed  mov     eax, dword ptr [rsp+68h+pv+4]
0x1400254f1  or      [rbx+40h], eax
0x1400254f4  test    rcx, rcx
0x1400254f7  jz      short loc_14002550D
0x1400254f9  lea     rdx, [rsp+68h+var_48]
0x1400254fe  mov     rcx, rbx
0x140025501  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x140025506  mov     rcx, [rsp+68h+pv+8]
0x14002550b  jmp     short loc_140025517
0x14002550d  mov     edx, dword ptr [rsp+68h+pv]
0x140025511  mov     [rbx+0B8h], edx
0x140025517  call    cs:__imp_CoTaskMemFree
0x14002551d  mov     al, 1
0x14002551f  jmp     short loc_1400254DA
```
