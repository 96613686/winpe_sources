# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18013bb8c`
- end: `0x18013bc59`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180139f6c`
- `0x18013b1f0`

## callees

- `0x1800474ec`
- `0x18007b498`
- `0x1801201a0`
- `0x18013bb8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013bbab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013bbab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bc0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bc4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bc0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bc4f`

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
0x18013bb8c  push    rbx
0x18013bb8e  sub     rsp, 60h
0x18013bb92  mov     rax, cs:__security_cookie
0x18013bb99  xor     rax, rsp
0x18013bb9c  mov     [rsp+68h+var_18], rax
0x18013bba1  mov     rbx, rcx
0x18013bba4  add     rcx, 0C0h; lpCriticalSection
0x18013bbab  call    cs:__imp_EnterCriticalSection
0x18013bbb1  inc     dword ptr [rbx+0E8h]
0x18013bbb7  test    dword ptr [rbx+40h], 100h
0x18013bbbe  jnz     short loc_18013BC10
0x18013bbc0  mov     rcx, [rbx+0F0h]
0x18013bbc7  test    rcx, rcx
0x18013bbca  jz      loc_18013BC55
0x18013bbd0  cmp     dword ptr [rbx+0E8h], 1
0x18013bbd7  jnz     short loc_18013BC55
0x18013bbd9  mov     r8d, [rbx+0B8h]
0x18013bbe0  lea     r9, [rsp+68h+var_48]
0x18013bbe5  xorps   xmm0, xmm0
0x18013bbe8  mov     edx, 1
0x18013bbed  movups  [rsp+68h+var_48], xmm0
0x18013bbf2  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18013bbf7  movups  [rsp+68h+var_28], xmm0
0x18013bbfc  call    TestQueryData
0x18013bc01  mov     rcx, [rsp+68h+pv+8]; pv
0x18013bc06  test    eax, eax
0x18013bc08  jnz     short loc_18013BC25
0x18013bc0a  call    cs:__imp_CoTaskMemFree
0x18013bc10  xor     al, al
0x18013bc12  mov     rcx, [rsp+68h+var_18]
0x18013bc17  xor     rcx, rsp; StackCookie
0x18013bc1a  call    __security_check_cookie
0x18013bc1f  add     rsp, 60h
0x18013bc23  pop     rbx
0x18013bc24  retn
0x18013bc25  mov     eax, dword ptr [rsp+68h+pv+4]
0x18013bc29  or      [rbx+40h], eax
0x18013bc2c  test    rcx, rcx
0x18013bc2f  jz      short loc_18013BC45
0x18013bc31  lea     rdx, [rsp+68h+var_48]
0x18013bc36  mov     rcx, rbx
0x18013bc39  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18013bc3e  mov     rcx, [rsp+68h+pv+8]
0x18013bc43  jmp     short loc_18013BC4F
0x18013bc45  mov     edx, dword ptr [rsp+68h+pv]
0x18013bc49  mov     [rbx+0B8h], edx
0x18013bc4f  call    cs:__imp_CoTaskMemFree
0x18013bc55  mov     al, 1
0x18013bc57  jmp     short loc_18013BC12
```
