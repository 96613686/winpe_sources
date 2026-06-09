# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180022d44`
- end: `0x180022e11`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d208`
- `0x18002468c`
- `0x18002f4fb`
- `0x18002f7d2`
- `0x18002f844`

## callees

- `0x180003560`
- `0x180022d44`
- `0x1800234b8`
- `0x180026470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022d63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022d63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e07`

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
0x180022d44  push    rbx
0x180022d46  sub     rsp, 60h
0x180022d4a  mov     rax, cs:__security_cookie
0x180022d51  xor     rax, rsp
0x180022d54  mov     [rsp+68h+var_18], rax
0x180022d59  mov     rbx, rcx
0x180022d5c  add     rcx, 0C0h; lpCriticalSection
0x180022d63  call    cs:__imp_EnterCriticalSection
0x180022d69  inc     dword ptr [rbx+0E8h]
0x180022d6f  test    dword ptr [rbx+40h], 100h
0x180022d76  jnz     short loc_180022DC8
0x180022d78  mov     rcx, [rbx+0F0h]
0x180022d7f  test    rcx, rcx
0x180022d82  jz      loc_180022E0D
0x180022d88  cmp     dword ptr [rbx+0E8h], 1
0x180022d8f  jnz     short loc_180022E0D
0x180022d91  mov     r8d, [rbx+0B8h]
0x180022d98  lea     r9, [rsp+68h+var_48]
0x180022d9d  xorps   xmm0, xmm0
0x180022da0  mov     edx, 1
0x180022da5  movups  [rsp+68h+var_48], xmm0
0x180022daa  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180022daf  movups  [rsp+68h+var_28], xmm0
0x180022db4  call    TestQueryData
0x180022db9  mov     rcx, [rsp+68h+pv+8]; pv
0x180022dbe  test    eax, eax
0x180022dc0  jnz     short loc_180022DDD
0x180022dc2  call    cs:__imp_CoTaskMemFree
0x180022dc8  xor     al, al
0x180022dca  mov     rcx, [rsp+68h+var_18]
0x180022dcf  xor     rcx, rsp; StackCookie
0x180022dd2  call    __security_check_cookie
0x180022dd7  add     rsp, 60h
0x180022ddb  pop     rbx
0x180022ddc  retn
0x180022ddd  mov     eax, dword ptr [rsp+68h+pv+4]
0x180022de1  or      [rbx+40h], eax
0x180022de4  test    rcx, rcx
0x180022de7  jz      short loc_180022DFD
0x180022de9  lea     rdx, [rsp+68h+var_48]
0x180022dee  mov     rcx, rbx
0x180022df1  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180022df6  mov     rcx, [rsp+68h+pv+8]
0x180022dfb  jmp     short loc_180022E07
0x180022dfd  mov     edx, dword ptr [rsp+68h+pv]
0x180022e01  mov     [rbx+0B8h], edx
0x180022e07  call    cs:__imp_CoTaskMemFree
0x180022e0d  mov     al, 1
0x180022e0f  jmp     short loc_180022DCA
```
