# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::GetProviderDetails(EtwProviderConfig *)

- ea: `0x18001d8a0`
- end: `0x18001da22`
- name: `?GetProviderDetails@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEAUEtwProviderConfig@@@Z`
- size: `386`
- prototype: `int(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *__hidden this, struct EtwProviderConfig *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180010540`
- `0x18001d8a0`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x18001d8e8`
- `VCRUNTIME140!memcmp` at `0x18001d8e8`
- `ole32!CoTaskMemAlloc` at `0x18001d98a`
- `ole32!CoTaskMemAlloc` at `0x18001d98a`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::GetProviderDetails(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this,
        struct EtwProviderConfig *a2)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rsi
  volatile signed __int32 *v8; // rdi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  _DWORD *v14; // r8
  __int64 **v15; // r10
  __int64 v16; // r9
  __int64 *i; // rax
  _QWORD v18[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_BYTE *)this + 2552) )
    return 3775987731LL;
  if ( !a2 )
    return 2147500035LL;
  if ( !memcmp(a2, &GUID_NULL, 0x10u) )
    return 2147942487LL;
  v18[0] = 0;
  std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
    (char *)this + 1760,
    v18);
  v5 = v18[0];
  if ( v18[0] == *((_QWORD *)this + 221) )
    return 2147943568LL;
  v6 = *(_QWORD *)(v18[0] + 40LL);
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v7 = *(_QWORD *)(v5 + 32);
  v8 = *(volatile signed __int32 **)(v5 + 40);
  v9 = *((_DWORD *)a2 + 5);
  *((_DWORD *)a2 + 4) = *(_DWORD *)(v7 + 20) & 0xF;
  if ( !v9 )
    goto LABEL_23;
  v10 = v9 - 1;
  if ( !v10 )
    goto LABEL_16;
  v11 = v10 - 2;
  if ( !v11 )
  {
LABEL_23:
    *((_QWORD *)a2 + 3) = *(_QWORD *)(v7 + 24);
    *((_BYTE *)a2 + 32) = *(_BYTE *)(v7 + 40);
    goto LABEL_24;
  }
  if ( v11 != 1 )
  {
    v12 = -2147024809;
    goto LABEL_25;
  }
LABEL_16:
  v13 = *(_DWORD *)(v7 + 128);
  *((_DWORD *)a2 + 6) = v13;
  *((_QWORD *)a2 + 4) = 0;
  if ( v13 )
  {
    _mm_lfence();
    v14 = CoTaskMemAlloc(4LL * v13);
    if ( !v14 )
    {
      v12 = -2147024882;
      goto LABEL_25;
    }
    v15 = *(__int64 ***)(v7 + 120);
    v16 = 0;
    for ( i = *v15; i != (__int64 *)v15; i = (__int64 *)*i )
    {
      v14[v16] = *((_DWORD *)i + 4);
      v16 = (unsigned int)(v16 + 1);
    }
    *((_QWORD *)a2 + 4) = v14;
  }
LABEL_24:
  v12 = 0;
LABEL_25:
  if ( v8 && _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
    if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  return v12;
}

```

## disassembly

```asm
0x18001d8a0  mov     [rsp+arg_10], rbx
0x18001d8a5  mov     [rsp+arg_18], rsi
0x18001d8aa  push    rdi
0x18001d8ab  sub     rsp, 30h
0x18001d8af  mov     al, [rcx+9F8h]
0x18001d8b5  mov     rbx, rdx
0x18001d8b8  mov     rdi, rcx
0x18001d8bb  test    al, al
0x18001d8bd  jz      short loc_18001D8C9
0x18001d8bf  mov     eax, 0E1110013h
0x18001d8c4  jmp     loc_18001DA12
0x18001d8c9  test    rbx, rbx
0x18001d8cc  jnz     short loc_18001D8D8
0x18001d8ce  mov     eax, 80004003h
0x18001d8d3  jmp     loc_18001DA12
0x18001d8d8  mov     r8d, 10h; Size
0x18001d8de  lea     rdx, GUID_NULL; Buf2
0x18001d8e5  mov     rcx, rbx; Buf1
0x18001d8e8  call    cs:__imp_memcmp
0x18001d8ee  test    eax, eax
0x18001d8f0  jnz     short loc_18001D8FC
0x18001d8f2  mov     eax, 80070057h
0x18001d8f7  jmp     loc_18001DA12
0x18001d8fc  lea     rcx, [rdi+6E0h]
0x18001d903  mov     [rsp+38h+var_18], 0
0x18001d90c  mov     r8, rbx
0x18001d90f  lea     rdx, [rsp+38h+var_18]
0x18001d914  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18001d919  mov     rax, [rsp+38h+var_18]
0x18001d91e  cmp     rax, [rdi+6E8h]
0x18001d925  jnz     short loc_18001D931
0x18001d927  mov     eax, 80070490h
0x18001d92c  jmp     loc_18001DA12
0x18001d931  mov     rcx, [rax+28h]
0x18001d935  test    rcx, rcx
0x18001d938  jz      short loc_18001D93E
0x18001d93a  lock inc dword ptr [rcx+8]
0x18001d93e  mov     rsi, [rax+20h]
0x18001d942  mov     rdi, [rax+28h]
0x18001d946  mov     ecx, [rbx+14h]
0x18001d949  mov     eax, [rsi+14h]
0x18001d94c  and     eax, 0Fh
0x18001d94f  mov     [rbx+10h], eax
0x18001d952  test    ecx, ecx
0x18001d954  jz      short loc_18001D9C3
0x18001d956  sub     ecx, 1
0x18001d959  jz      short loc_18001D96C
0x18001d95b  sub     ecx, 2
0x18001d95e  jz      short loc_18001D9C3
0x18001d960  cmp     ecx, 1
0x18001d963  jz      short loc_18001D96C
0x18001d965  mov     ebx, 80070057h
0x18001d96a  jmp     short loc_18001D9D3
0x18001d96c  mov     eax, [rsi+80h]
0x18001d972  mov     [rbx+18h], eax
0x18001d975  mov     qword ptr [rbx+20h], 0
0x18001d97d  test    eax, eax
0x18001d97f  jz      short loc_18001D9D1
0x18001d981  lfence
0x18001d984  mov     ecx, eax
0x18001d986  shl     rcx, 2; cb
0x18001d98a  call    cs:__imp_CoTaskMemAlloc
0x18001d990  mov     r8, rax
0x18001d993  test    rax, rax
0x18001d996  jnz     short loc_18001D99F
0x18001d998  mov     ebx, 8007000Eh
0x18001d99d  jmp     short loc_18001D9D3
0x18001d99f  mov     r10, [rsi+78h]
0x18001d9a3  xor     r9d, r9d
0x18001d9a6  mov     rax, [r10]
0x18001d9a9  jmp     short loc_18001D9B8
0x18001d9ab  mov     ecx, [rax+10h]
0x18001d9ae  mov     [r8+r9*4], ecx
0x18001d9b2  inc     r9d
0x18001d9b5  mov     rax, [rax]
0x18001d9b8  cmp     rax, r10
0x18001d9bb  jnz     short loc_18001D9AB
0x18001d9bd  mov     [rbx+20h], r8
0x18001d9c1  jmp     short loc_18001D9D1
0x18001d9c3  mov     rax, [rsi+18h]
0x18001d9c7  mov     [rbx+18h], rax
0x18001d9cb  mov     al, [rsi+28h]
0x18001d9ce  mov     [rbx+20h], al
0x18001d9d1  xor     ebx, ebx
0x18001d9d3  test    rdi, rdi
0x18001d9d6  jz      short loc_18001DA10
0x18001d9d8  or      esi, 0FFFFFFFFh
0x18001d9db  mov     eax, esi
0x18001d9dd  lock xadd [rdi+8], eax
0x18001d9e2  add     eax, esi
0x18001d9e4  jnz     short loc_18001DA10
0x18001d9e6  mov     rax, [rdi]
0x18001d9e9  mov     rcx, rdi
0x18001d9ec  mov     rax, [rax]
0x18001d9ef  call    cs:__guard_dispatch_icall_fptr
0x18001d9f5  mov     edx, esi
0x18001d9f7  lock xadd [rdi+0Ch], edx
0x18001d9fc  add     edx, esi
0x18001d9fe  jnz     short loc_18001DA10
0x18001da00  mov     rdx, [rdi]
0x18001da03  mov     rcx, rdi
0x18001da06  mov     rax, [rdx+8]
0x18001da0a  call    cs:__guard_dispatch_icall_fptr
0x18001da10  mov     eax, ebx
0x18001da12  mov     rbx, [rsp+38h+arg_10]
0x18001da17  mov     rsi, [rsp+38h+arg_18]
0x18001da1c  add     rsp, 30h
0x18001da20  pop     rdi
0x18001da21  retn
```
