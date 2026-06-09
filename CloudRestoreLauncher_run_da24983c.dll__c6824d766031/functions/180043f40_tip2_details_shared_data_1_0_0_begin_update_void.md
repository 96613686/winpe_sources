# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180043f40`
- end: `0x18004400d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180038170`
- `0x1800455f4`
- `0x180069324`
- `0x180077da8`
- `0x18008cb00`

## callees

- `0x18000c6e0`
- `0x1800134d4`
- `0x180043f40`
- `0x1800444e8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180043f5f`
- `KERNEL32!EnterCriticalSection` at `0x180043f5f`
- `OLE32!CoTaskMemFree` at `0x180043fbe`
- `OLE32!CoTaskMemFree` at `0x180044003`
- `OLE32!CoTaskMemFree` at `0x180043fbe`
- `OLE32!CoTaskMemFree` at `0x180044003`

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
0x180043f40  push    rbx
0x180043f42  sub     rsp, 60h
0x180043f46  mov     rax, cs:__security_cookie
0x180043f4d  xor     rax, rsp
0x180043f50  mov     [rsp+68h+var_18], rax
0x180043f55  mov     rbx, rcx
0x180043f58  add     rcx, 0C0h; lpCriticalSection
0x180043f5f  call    cs:__imp_EnterCriticalSection
0x180043f65  inc     dword ptr [rbx+0E8h]
0x180043f6b  test    dword ptr [rbx+40h], 100h
0x180043f72  jnz     short loc_180043FC4
0x180043f74  mov     rcx, [rbx+0F0h]
0x180043f7b  test    rcx, rcx
0x180043f7e  jz      loc_180044009
0x180043f84  cmp     dword ptr [rbx+0E8h], 1
0x180043f8b  jnz     short loc_180044009
0x180043f8d  mov     r8d, [rbx+0B8h]
0x180043f94  lea     r9, [rsp+68h+var_48]
0x180043f99  xorps   xmm0, xmm0
0x180043f9c  mov     edx, 1
0x180043fa1  movups  [rsp+68h+var_48], xmm0
0x180043fa6  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180043fab  movups  [rsp+68h+var_28], xmm0
0x180043fb0  call    TestQueryData
0x180043fb5  mov     rcx, [rsp+68h+pv+8]; pv
0x180043fba  test    eax, eax
0x180043fbc  jnz     short loc_180043FD9
0x180043fbe  call    cs:__imp_CoTaskMemFree
0x180043fc4  xor     al, al
0x180043fc6  mov     rcx, [rsp+68h+var_18]
0x180043fcb  xor     rcx, rsp; StackCookie
0x180043fce  call    __security_check_cookie
0x180043fd3  add     rsp, 60h
0x180043fd7  pop     rbx
0x180043fd8  retn
0x180043fd9  mov     eax, dword ptr [rsp+68h+pv+4]
0x180043fdd  or      [rbx+40h], eax
0x180043fe0  test    rcx, rcx
0x180043fe3  jz      short loc_180043FF9
0x180043fe5  lea     rdx, [rsp+68h+var_48]
0x180043fea  mov     rcx, rbx
0x180043fed  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180043ff2  mov     rcx, [rsp+68h+pv+8]
0x180043ff7  jmp     short loc_180044003
0x180043ff9  mov     edx, dword ptr [rsp+68h+pv]
0x180043ffd  mov     [rbx+0B8h], edx
0x180044003  call    cs:__imp_CoTaskMemFree
0x180044009  mov     al, 1
0x18004400b  jmp     short loc_180043FC6
```
