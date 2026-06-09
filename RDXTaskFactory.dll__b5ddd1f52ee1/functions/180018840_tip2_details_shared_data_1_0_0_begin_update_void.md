# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180018840`
- end: `0x18001890d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001717c`
- `0x180019e98`
- `0x18003ad30`
- `0x18003eebc`
- `0x180040500`

## callees

- `0x180003390`
- `0x180018840`
- `0x180018de0`
- `0x18001b56c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001885f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001885f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800188be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800188be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018903`

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
0x180018840  push    rbx
0x180018842  sub     rsp, 60h
0x180018846  mov     rax, cs:__security_cookie
0x18001884d  xor     rax, rsp
0x180018850  mov     [rsp+68h+var_18], rax
0x180018855  mov     rbx, rcx
0x180018858  add     rcx, 0C0h; lpCriticalSection
0x18001885f  call    cs:__imp_EnterCriticalSection
0x180018865  inc     dword ptr [rbx+0E8h]
0x18001886b  test    dword ptr [rbx+40h], 100h
0x180018872  jnz     short loc_1800188C4
0x180018874  mov     rcx, [rbx+0F0h]
0x18001887b  test    rcx, rcx
0x18001887e  jz      loc_180018909
0x180018884  cmp     dword ptr [rbx+0E8h], 1
0x18001888b  jnz     short loc_180018909
0x18001888d  mov     r8d, [rbx+0B8h]
0x180018894  lea     r9, [rsp+68h+var_48]
0x180018899  xorps   xmm0, xmm0
0x18001889c  mov     edx, 1
0x1800188a1  movups  [rsp+68h+var_48], xmm0
0x1800188a6  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800188ab  movups  [rsp+68h+var_28], xmm0
0x1800188b0  call    TestQueryData
0x1800188b5  mov     rcx, [rsp+68h+pv+8]; pv
0x1800188ba  test    eax, eax
0x1800188bc  jnz     short loc_1800188D9
0x1800188be  call    cs:__imp_CoTaskMemFree
0x1800188c4  xor     al, al
0x1800188c6  mov     rcx, [rsp+68h+var_18]
0x1800188cb  xor     rcx, rsp; StackCookie
0x1800188ce  call    __security_check_cookie
0x1800188d3  add     rsp, 60h
0x1800188d7  pop     rbx
0x1800188d8  retn
0x1800188d9  mov     eax, dword ptr [rsp+68h+pv+4]
0x1800188dd  or      [rbx+40h], eax
0x1800188e0  test    rcx, rcx
0x1800188e3  jz      short loc_1800188F9
0x1800188e5  lea     rdx, [rsp+68h+var_48]
0x1800188ea  mov     rcx, rbx
0x1800188ed  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800188f2  mov     rcx, [rsp+68h+pv+8]
0x1800188f7  jmp     short loc_180018903
0x1800188f9  mov     edx, dword ptr [rsp+68h+pv]
0x1800188fd  mov     [rbx+0B8h], edx
0x180018903  call    cs:__imp_CoTaskMemFree
0x180018909  mov     al, 1
0x18001890b  jmp     short loc_1800188C6
```
