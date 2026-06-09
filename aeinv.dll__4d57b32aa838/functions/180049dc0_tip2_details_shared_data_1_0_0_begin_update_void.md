# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180049dc0`
- end: `0x180049e8d`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180049d7c`
- `0x180106d90`

## callees

- `0x180049dc0`
- `0x1800561c4`
- `0x180059920`
- `0x180108f48`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180049ddf`
- `KERNEL32!EnterCriticalSection` at `0x180049ddf`
- `ole32!CoTaskMemFree` at `0x180049e3e`
- `ole32!CoTaskMemFree` at `0x180049e83`
- `ole32!CoTaskMemFree` at `0x180049e3e`
- `ole32!CoTaskMemFree` at `0x180049e83`

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
      tip2::details::shared_data<1,0,0>::deserialize_data((__int64 *)a1, (__int64)&v7);
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
0x180049dc0  push    rbx
0x180049dc2  sub     rsp, 60h
0x180049dc6  mov     rax, cs:__security_cookie
0x180049dcd  xor     rax, rsp
0x180049dd0  mov     [rsp+68h+var_18], rax
0x180049dd5  mov     rbx, rcx
0x180049dd8  add     rcx, 0C0h; lpCriticalSection
0x180049ddf  call    cs:__imp_EnterCriticalSection
0x180049de5  inc     dword ptr [rbx+0E8h]
0x180049deb  test    dword ptr [rbx+40h], 100h
0x180049df2  jnz     short loc_180049E44
0x180049df4  mov     rcx, [rbx+0F0h]
0x180049dfb  test    rcx, rcx
0x180049dfe  jz      loc_180049E89
0x180049e04  cmp     dword ptr [rbx+0E8h], 1
0x180049e0b  jnz     short loc_180049E89
0x180049e0d  mov     r8d, [rbx+0B8h]
0x180049e14  lea     r9, [rsp+68h+var_48]
0x180049e19  xorps   xmm0, xmm0
0x180049e1c  mov     edx, 1
0x180049e21  movups  [rsp+68h+var_48], xmm0
0x180049e26  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180049e2b  movups  [rsp+68h+var_28], xmm0
0x180049e30  call    TestQueryData
0x180049e35  mov     rcx, [rsp+68h+pv+8]; pv
0x180049e3a  test    eax, eax
0x180049e3c  jnz     short loc_180049E59
0x180049e3e  call    cs:__imp_CoTaskMemFree
0x180049e44  xor     al, al
0x180049e46  mov     rcx, [rsp+68h+var_18]
0x180049e4b  xor     rcx, rsp; StackCookie
0x180049e4e  call    __security_check_cookie
0x180049e53  add     rsp, 60h
0x180049e57  pop     rbx
0x180049e58  retn
0x180049e59  mov     eax, dword ptr [rsp+68h+pv+4]
0x180049e5d  or      [rbx+40h], eax
0x180049e60  test    rcx, rcx
0x180049e63  jz      short loc_180049E79
0x180049e65  lea     rdx, [rsp+68h+var_48]
0x180049e6a  mov     rcx, rbx
0x180049e6d  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180049e72  mov     rcx, [rsp+68h+pv+8]
0x180049e77  jmp     short loc_180049E83
0x180049e79  mov     edx, dword ptr [rsp+68h+pv]
0x180049e7d  mov     [rbx+0B8h], edx
0x180049e83  call    cs:__imp_CoTaskMemFree
0x180049e89  mov     al, 1
0x180049e8b  jmp     short loc_180049E46
```
