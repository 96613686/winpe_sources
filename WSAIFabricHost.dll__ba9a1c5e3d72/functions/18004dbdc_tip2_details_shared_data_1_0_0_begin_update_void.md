# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18004dbdc`
- end: `0x18004dca9`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044700`
- `0x180045790`
- `0x1800844c4`
- `0x1800845ce`

## callees

- `0x180004ca0`
- `0x18004dbdc`
- `0x18004e4d0`
- `0x180054d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dbfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dbfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dc5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dc9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dc5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dc9f`

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
0x18004dbdc  push    rbx
0x18004dbde  sub     rsp, 60h
0x18004dbe2  mov     rax, cs:__security_cookie
0x18004dbe9  xor     rax, rsp
0x18004dbec  mov     [rsp+68h+var_18], rax
0x18004dbf1  mov     rbx, rcx
0x18004dbf4  add     rcx, 0C0h; lpCriticalSection
0x18004dbfb  call    cs:__imp_EnterCriticalSection
0x18004dc01  inc     dword ptr [rbx+0E8h]
0x18004dc07  test    dword ptr [rbx+40h], 100h
0x18004dc0e  jnz     short loc_18004DC60
0x18004dc10  mov     rcx, [rbx+0F0h]
0x18004dc17  test    rcx, rcx
0x18004dc1a  jz      loc_18004DCA5
0x18004dc20  cmp     dword ptr [rbx+0E8h], 1
0x18004dc27  jnz     short loc_18004DCA5
0x18004dc29  mov     r8d, [rbx+0B8h]
0x18004dc30  lea     r9, [rsp+68h+var_48]
0x18004dc35  xorps   xmm0, xmm0
0x18004dc38  mov     edx, 1
0x18004dc3d  movups  [rsp+68h+var_48], xmm0
0x18004dc42  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18004dc47  movups  [rsp+68h+var_28], xmm0
0x18004dc4c  call    TestQueryData
0x18004dc51  mov     rcx, [rsp+68h+pv+8]; pv
0x18004dc56  test    eax, eax
0x18004dc58  jnz     short loc_18004DC75
0x18004dc5a  call    cs:__imp_CoTaskMemFree
0x18004dc60  xor     al, al
0x18004dc62  mov     rcx, [rsp+68h+var_18]
0x18004dc67  xor     rcx, rsp; StackCookie
0x18004dc6a  call    __security_check_cookie
0x18004dc6f  add     rsp, 60h
0x18004dc73  pop     rbx
0x18004dc74  retn
0x18004dc75  mov     eax, dword ptr [rsp+68h+pv+4]
0x18004dc79  or      [rbx+40h], eax
0x18004dc7c  test    rcx, rcx
0x18004dc7f  jz      short loc_18004DC95
0x18004dc81  lea     rdx, [rsp+68h+var_48]
0x18004dc86  mov     rcx, rbx
0x18004dc89  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004dc8e  mov     rcx, [rsp+68h+pv+8]
0x18004dc93  jmp     short loc_18004DC9F
0x18004dc95  mov     edx, dword ptr [rsp+68h+pv]
0x18004dc99  mov     [rbx+0B8h], edx
0x18004dc9f  call    cs:__imp_CoTaskMemFree
0x18004dca5  mov     al, 1
0x18004dca7  jmp     short loc_18004DC62
```
