# _anonymous_namespace_::ServiceLifetimeManager::DoesSessionExist

- ea: `0x140005620`
- end: `0x1400056d5`
- name: `_anonymous_namespace_::ServiceLifetimeManager::DoesSessionExist`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005620`
- `0x140006c80`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x140005641`
- `KERNEL32!AcquireSRWLockShared` at `0x140005641`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400056b8`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400056b8`

## pseudocode

```c
bool __fastcall anonymous_namespace_::ServiceLifetimeManager::DoesSessionExist(RTL_SRWLOCK *a1, unsigned __int8 *a2)
{
  RTL_SRWLOCK *v2; // rbp
  __int64 v5; // r9
  unsigned __int64 v6; // r8
  __int64 v7; // r10
  __int64 v8; // rax
  unsigned __int64 i; // rcx
  __int64 v10; // rax
  PVOID Ptr; // rcx
  bool v12; // bl
  _QWORD v14[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = a1 + 5;
  AcquireSRWLockShared(a1 + 5);
  v5 = 0xCBF29CE484222325uLL;
  v6 = 0;
  v7 = 0xCBF29CE484222325uLL;
  do
  {
    v8 = a2[v6++];
    v7 = 0x100000001B3LL * (v8 ^ v7);
  }
  while ( v6 < 8 );
  for ( i = 0; i < 8; ++i )
  {
    v10 = a2[i + 8];
    v5 = 0x100000001B3LL * (v10 ^ v5);
  }
  Ptr = (PVOID)std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
                 &a1[6].Ptr,
                 v14,
                 a2,
                 v7 ^ v5)[1];
  if ( !Ptr )
    Ptr = a1[7].Ptr;
  v12 = Ptr != a1[7].Ptr;
  ReleaseSRWLockShared(v2);
  return v12;
}

```

## disassembly

```asm
0x140005620  mov     [rsp+arg_0], rbx
0x140005625  mov     [rsp+arg_8], rbp
0x14000562a  mov     [rsp+arg_10], rsi
0x14000562f  push    rdi
0x140005630  sub     rsp, 30h
0x140005634  lea     rbp, [rcx+28h]
0x140005638  mov     rbx, rcx
0x14000563b  mov     rcx, rbp; SRWLock
0x14000563e  mov     rsi, rdx
0x140005641  call    cs:__imp_AcquireSRWLockShared
0x140005647  mov     r9, 0CBF29CE484222325h
0x140005651  xor     r8d, r8d
0x140005654  mov     r10, r9
0x140005657  mov     rdx, 100000001B3h
0x140005661  movzx   eax, byte ptr [rsi+r8]
0x140005666  inc     r8
0x140005669  xor     r10, rax
0x14000566c  imul    r10, rdx
0x140005670  cmp     r8, 8
0x140005674  jb      short loc_140005661
0x140005676  xor     ecx, ecx
0x140005678  movzx   eax, byte ptr [rsi+rcx+8]
0x14000567d  inc     rcx
0x140005680  xor     r9, rax
0x140005683  imul    r9, rdx
0x140005687  cmp     rcx, 8
0x14000568b  jb      short loc_140005678
0x14000568d  xor     r9, r10
0x140005690  lea     rdx, [rsp+38h+var_18]
0x140005695  mov     r8, rsi
0x140005698  lea     rcx, [rbx+30h]
0x14000569c  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x1400056a1  mov     rcx, [rax+8]
0x1400056a5  test    rcx, rcx
0x1400056a8  jnz     short loc_1400056AE
0x1400056aa  mov     rcx, [rbx+38h]
0x1400056ae  cmp     rcx, [rbx+38h]
0x1400056b2  mov     rcx, rbp; SRWLock
0x1400056b5  setnz   bl
0x1400056b8  call    cs:__imp_ReleaseSRWLockShared
0x1400056be  mov     rbp, [rsp+38h+arg_8]
0x1400056c3  mov     al, bl
0x1400056c5  mov     rbx, [rsp+38h+arg_0]
0x1400056ca  mov     rsi, [rsp+38h+arg_10]
0x1400056cf  add     rsp, 30h
0x1400056d3  pop     rdi
0x1400056d4  retn
```
