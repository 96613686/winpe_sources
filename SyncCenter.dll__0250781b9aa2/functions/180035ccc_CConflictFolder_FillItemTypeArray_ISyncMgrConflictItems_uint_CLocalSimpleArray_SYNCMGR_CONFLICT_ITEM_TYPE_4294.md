# CConflictFolder::_FillItemTypeArray(ISyncMgrConflictItems *,uint,CLocalSimpleArray<SYNCMGR_CONFLICT_ITEM_TYPE,4294967294> *)

- ea: `0x180035ccc`
- end: `0x180035e0f`
- name: `?_FillItemTypeArray@CConflictFolder@@AEAAJPEAUISyncMgrConflictItems@@IPEAV?$CLocalSimpleArray@W4SYNCMGR_CONFLICT_ITEM_TYPE@@$0PPPPPPPO@@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(__int64, __int64 *, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003625c`

## callees

- `0x1800153ac`
- `0x18003468c`
- `0x180035ccc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035dd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035dd2`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_FillItemTypeArray(__int64 a1, __int64 *a2, unsigned int a3, _QWORD *a4)
{
  int v4; // edi
  int v5; // esi
  unsigned int v6; // r14d
  __int64 *v8; // r9
  __int64 v9; // rax
  __int64 (__fastcall *v10)(__int64 *, _QWORD, LPVOID *); // rax
  unsigned __int64 v11; // r8
  __int64 v12; // rdx
  _DWORD *v13; // rdx
  LPVOID v14; // rcx
  void *v15; // r15
  void *v16; // r12
  void *v17; // r13
  LPVOID pv[2]; // [rsp+20h] [rbp-30h] BYREF
  LPVOID v20[2]; // [rsp+30h] [rbp-20h]
  __int128 v21; // [rsp+40h] [rbp-10h]
  void *v22; // [rsp+90h] [rbp+40h]

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v8 = a2;
  if ( a3 )
  {
    do
    {
      if ( v4 < 0 )
        break;
      if ( v5 < 0 )
        goto LABEL_13;
      v9 = *v8;
      *(_OWORD *)pv = 0;
      v10 = *(__int64 (__fastcall **)(__int64 *, _QWORD, LPVOID *))(v9 + 32);
      *(_OWORD *)v20 = 0;
      v21 = 0;
      v5 = v10(v8, v6, pv);
      if ( v5 >= 0 )
      {
        v12 = a4[1];
        v4 = 0;
        if ( v12 != a4[3]
          || (v4 = CTSimpleArray<enum SYNCMGR_CONFLICT_ITEM_TYPE,4294967294,CTPolicyLocalMem<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardCompareHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardMergeHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>>::_EnsureCapacity(
                     a4,
                     v12 + 1,
                     v11),
              v4 >= 0) )
        {
          v13 = (_DWORD *)(*a4 + 4 * a4[1]++);
          if ( v13 )
            *v13 = DWORD2(v21);
        }
      }
      v14 = pv[0];
      v15 = pv[1];
      v16 = v20[0];
      v17 = v20[1];
      v22 = (void *)v21;
      *(_OWORD *)pv = 0;
      *(_OWORD *)v20 = 0;
      v21 = 0;
      if ( v14 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
      CoTaskMemFree(v15);
      CoTaskMemFree(v16);
      CoTaskMemFree(v17);
      CoTaskMemFree(v22);
      v8 = a2;
      ++v6;
    }
    while ( v6 < a3 );
    if ( v5 >= 0 )
      return (unsigned int)v4;
LABEL_13:
    CTSimpleArray<enum SYNCMGR_CONFLICT_ITEM_TYPE,4294967294,CTPolicyLocalMem<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardCompareHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardMergeHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>>::RemoveAll(a4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180035ccc  mov     rax, rsp
0x180035ccf  mov     [rax+20h], rbx
0x180035cd3  mov     [rax+18h], r8d
0x180035cd7  mov     [rax+10h], rdx
0x180035cdb  mov     [rax+8], rcx
0x180035cdf  push    rbp
0x180035ce0  push    rsi
0x180035ce1  push    rdi
0x180035ce2  push    r12
0x180035ce4  push    r13
0x180035ce6  push    r14
0x180035ce8  push    r15
0x180035cea  mov     rbp, rsp
0x180035ced  sub     rsp, 50h
0x180035cf1  xor     edi, edi
0x180035cf3  xor     esi, esi
0x180035cf5  xor     r14d, r14d
0x180035cf8  mov     rbx, r9
0x180035cfb  mov     r9, rdx
0x180035cfe  test    r8d, r8d
0x180035d01  jz      loc_180035DF5
0x180035d07  test    edi, edi
0x180035d09  js      loc_180035DE9
0x180035d0f  test    esi, esi
0x180035d11  js      loc_180035DED
0x180035d17  mov     rax, [r9]
0x180035d1a  lea     r8, [rbp+pv]
0x180035d1e  xorps   xmm0, xmm0
0x180035d21  mov     edx, r14d
0x180035d24  mov     rcx, r9
0x180035d27  movups  xmmword ptr [rbp+pv], xmm0
0x180035d2b  mov     rax, [rax+20h]
0x180035d2f  movups  xmmword ptr [rbp+var_20], xmm0
0x180035d33  movups  [rbp+var_10], xmm0
0x180035d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d3c  mov     esi, eax
0x180035d3e  test    eax, eax
0x180035d40  js      short loc_180035D7B
0x180035d42  mov     rdx, [rbx+8]
0x180035d46  xor     edi, edi
0x180035d48  cmp     rdx, [rbx+18h]
0x180035d4c  jnz     short loc_180035D5F
0x180035d4e  inc     rdx
0x180035d51  mov     rcx, rbx
0x180035d54  call    ?_EnsureCapacity@?$CTSimpleArray@W4SYNCMGR_CONFLICT_ITEM_TYPE@@$0PPPPPPPO@V?$CTPolicyLocalMem@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@V?$CSimpleArrayStandardCompareHelper@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@V?$CSimpleArrayStandardMergeHelper@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@@@QEAAJ_K0@Z; CTSimpleArray<SYNCMGR_CONFLICT_ITEM_TYPE,4294967294,CTPolicyLocalMem<SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardCompareHelper<SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardMergeHelper<SYNCMGR_CONFLICT_ITEM_TYPE>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180035d59  mov     edi, eax
0x180035d5b  test    eax, eax
0x180035d5d  js      short loc_180035D7B
0x180035d5f  inc     qword ptr [rbx+8]
0x180035d63  mov     rdx, [rbx+8]
0x180035d67  mov     rax, [rbx]
0x180035d6a  dec     rdx
0x180035d6d  lea     rdx, [rax+rdx*4]
0x180035d71  test    rdx, rdx
0x180035d74  jz      short loc_180035D7B
0x180035d76  mov     eax, dword ptr [rbp+var_10+8]
0x180035d79  mov     [rdx], eax
0x180035d7b  mov     rcx, [rbp+pv]
0x180035d7f  xorps   xmm0, xmm0
0x180035d82  mov     rax, qword ptr [rbp+var_10]
0x180035d86  mov     r15, [rbp+pv+8]
0x180035d8a  mov     r12, [rbp+var_20]
0x180035d8e  mov     r13, [rbp+var_20+8]
0x180035d92  mov     [rbp+arg_0], rax
0x180035d96  movups  xmmword ptr [rbp+pv], xmm0
0x180035d9a  movups  xmmword ptr [rbp+var_20], xmm0
0x180035d9e  movups  [rbp+var_10], xmm0
0x180035da2  test    rcx, rcx
0x180035da5  jz      short loc_180035DB3
0x180035da7  mov     rax, [rcx]
0x180035daa  mov     rax, [rax+10h]
0x180035dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035db3  mov     rcx, r15; pv
0x180035db6  call    cs:__imp_CoTaskMemFree
0x180035dbc  mov     rcx, r12; pv
0x180035dbf  call    cs:__imp_CoTaskMemFree
0x180035dc5  mov     rcx, r13; pv
0x180035dc8  call    cs:__imp_CoTaskMemFree
0x180035dce  mov     rcx, [rbp+arg_0]; pv
0x180035dd2  call    cs:__imp_CoTaskMemFree
0x180035dd8  mov     r9, [rbp+arg_8]
0x180035ddc  inc     r14d
0x180035ddf  cmp     r14d, [rbp+arg_10]
0x180035de3  jb      loc_180035D07
0x180035de9  test    esi, esi
0x180035deb  jns     short loc_180035DF5
0x180035ded  mov     rcx, rbx
0x180035df0  call    ?RemoveAll@?$CTSimpleArray@W4SYNCMGR_CONFLICT_ITEM_TYPE@@$0PPPPPPPO@V?$CTPolicyLocalMem@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@V?$CSimpleArrayStandardCompareHelper@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@V?$CSimpleArrayStandardMergeHelper@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@@@QEAAXXZ; CTSimpleArray<SYNCMGR_CONFLICT_ITEM_TYPE,4294967294,CTPolicyLocalMem<SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardCompareHelper<SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardMergeHelper<SYNCMGR_CONFLICT_ITEM_TYPE>>::RemoveAll(void)
0x180035df5  mov     rbx, [rsp+50h+arg_18]
0x180035dfd  mov     eax, edi
0x180035dff  add     rsp, 50h
0x180035e03  pop     r15
0x180035e05  pop     r14
0x180035e07  pop     r13
0x180035e09  pop     r12
0x180035e0b  pop     rdi
0x180035e0c  pop     rsi
0x180035e0d  pop     rbp
0x180035e0e  retn
```
