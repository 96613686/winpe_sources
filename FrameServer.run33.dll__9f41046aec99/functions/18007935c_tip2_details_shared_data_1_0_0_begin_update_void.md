# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18007935c`
- end: `0x180079429`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180076584`
- `0x1800780e0`

## callees

- `0x180003e20`
- `0x18007935c`
- `0x1800797ac`
- `0x18007bcb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007937b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007937b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800793da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007941f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800793da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007941f`

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
0x18007935c  push    rbx
0x18007935e  sub     rsp, 60h
0x180079362  mov     rax, cs:__security_cookie
0x180079369  xor     rax, rsp
0x18007936c  mov     [rsp+68h+var_18], rax
0x180079371  mov     rbx, rcx
0x180079374  add     rcx, 0C0h; lpCriticalSection
0x18007937b  call    cs:__imp_EnterCriticalSection
0x180079381  inc     dword ptr [rbx+0E8h]
0x180079387  test    dword ptr [rbx+40h], 100h
0x18007938e  jnz     short loc_1800793E0
0x180079390  mov     rcx, [rbx+0F0h]
0x180079397  test    rcx, rcx
0x18007939a  jz      loc_180079425
0x1800793a0  cmp     dword ptr [rbx+0E8h], 1
0x1800793a7  jnz     short loc_180079425
0x1800793a9  mov     r8d, [rbx+0B8h]
0x1800793b0  lea     r9, [rsp+68h+var_48]
0x1800793b5  xorps   xmm0, xmm0
0x1800793b8  mov     edx, 1
0x1800793bd  movups  [rsp+68h+var_48], xmm0
0x1800793c2  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800793c7  movups  [rsp+68h+var_28], xmm0
0x1800793cc  call    TestQueryData
0x1800793d1  mov     rcx, [rsp+68h+pv+8]; pv
0x1800793d6  test    eax, eax
0x1800793d8  jnz     short loc_1800793F5
0x1800793da  call    cs:__imp_CoTaskMemFree
0x1800793e0  xor     al, al
0x1800793e2  mov     rcx, [rsp+68h+var_18]
0x1800793e7  xor     rcx, rsp; StackCookie
0x1800793ea  call    __security_check_cookie
0x1800793ef  add     rsp, 60h
0x1800793f3  pop     rbx
0x1800793f4  retn
0x1800793f5  mov     eax, dword ptr [rsp+68h+pv+4]
0x1800793f9  or      [rbx+40h], eax
0x1800793fc  test    rcx, rcx
0x1800793ff  jz      short loc_180079415
0x180079401  lea     rdx, [rsp+68h+var_48]
0x180079406  mov     rcx, rbx
0x180079409  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18007940e  mov     rcx, [rsp+68h+pv+8]
0x180079413  jmp     short loc_18007941F
0x180079415  mov     edx, dword ptr [rsp+68h+pv]
0x180079419  mov     [rbx+0B8h], edx
0x18007941f  call    cs:__imp_CoTaskMemFree
0x180079425  mov     al, 1
0x180079427  jmp     short loc_1800793E2
```
