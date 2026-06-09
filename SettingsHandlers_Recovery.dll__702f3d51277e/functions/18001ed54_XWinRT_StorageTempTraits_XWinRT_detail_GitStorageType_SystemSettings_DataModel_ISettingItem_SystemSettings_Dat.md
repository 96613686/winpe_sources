# XWinRT::StorageTempTraits<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,SystemSettings::DataModel::ISettingItem *,XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>::ResolveDemand(XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem> *,SystemSettings::DataModel::ISettingItem * *)

- ea: `0x18001ed54`
- end: `0x18001ee00`
- name: `?ResolveDemand@?$StorageTempTraits@V?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@PEAUISettingItem@DataModel@SystemSettings@@V123@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@@XWinRT@@SAJPEAV?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@2@PEAPEAUISettingItem@DataModel@SystemSettings@@@Z`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180015830`
- `0x1800167c0`

## callees

- `0x18000282c`
- `0x18001ed54`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall XWinRT::StorageTempTraits<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,SystemSettings::DataModel::ISettingItem *,XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>::ResolveDemand(
        __int64 a1,
        volatile signed __int32 **a2)
{
  volatile signed __int32 *v3; // r10
  int v4; // esi
  volatile signed __int32 *v5; // rdi

  *a2 = 0;
  v3 = *(volatile signed __int32 **)a1;
  if ( *(_BYTE *)(a1 + 8) )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, volatile signed __int32 **))(*(_QWORD *)qword_18005A068
                                                                                        + 40LL))(
           qword_18005A068,
           *((unsigned int *)v3 + 1),
           &GUID_40c037cc_d8bf_489e_8697_d66baa3221bf,
           a2);
    if ( v4 >= 0 )
    {
      v5 = *(volatile signed __int32 **)a1;
      if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)a1, 0xFFFFFFFF) == 1 && v5 )
      {
        if ( *((_DWORD *)v5 + 1) )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18005A068 + 32LL))(qword_18005A068);
        operator delete((void *)v5);
      }
      *(_BYTE *)(a1 + 8) = 0;
      *(_QWORD *)a1 = 0;
    }
  }
  else
  {
    v4 = 0;
    *a2 = v3;
    *(_QWORD *)a1 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ed54  mov     [rsp+arg_8], rbx
0x18001ed59  mov     [rsp+arg_10], rsi
0x18001ed5e  push    rdi
0x18001ed5f  sub     rsp, 30h
0x18001ed63  mov     rbx, rcx
0x18001ed66  mov     qword ptr [rdx], 0
0x18001ed6d  mov     r10, [rcx]
0x18001ed70  cmp     byte ptr [rcx+8], 0
0x18001ed74  jz      short loc_18001EDE6
0x18001ed76  mov     rcx, cs:qword_18005A068
0x18001ed7d  mov     rax, [rcx]
0x18001ed80  mov     r9, rdx
0x18001ed83  lea     r8, _GUID_40c037cc_d8bf_489e_8697_d66baa3221bf
0x18001ed8a  mov     edx, [r10+4]
0x18001ed8e  mov     rax, [rax+28h]
0x18001ed92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed97  mov     esi, eax
0x18001ed99  test    eax, eax
0x18001ed9b  js      short loc_18001EDEE
0x18001ed9d  mov     rdi, [rbx]
0x18001eda0  or      eax, 0FFFFFFFFh
0x18001eda3  lock xadd [rdi], eax
0x18001eda7  cmp     eax, 1
0x18001edaa  jnz     short loc_18001EDD9
0x18001edac  test    rdi, rdi
0x18001edaf  jz      short loc_18001EDD9
0x18001edb1  mov     edx, [rdi+4]
0x18001edb4  test    edx, edx
0x18001edb6  jz      short loc_18001EDCC
0x18001edb8  mov     rcx, cs:qword_18005A068
0x18001edbf  mov     rax, [rcx]
0x18001edc2  mov     rax, [rax+20h]
0x18001edc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edcb  nop
0x18001edcc  mov     edx, 8
0x18001edd1  mov     rcx, rdi; Block
0x18001edd4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001edd9  mov     byte ptr [rbx+8], 0
0x18001eddd  mov     qword ptr [rbx], 0
0x18001ede4  jmp     short loc_18001EDEE
0x18001ede6  xor     esi, esi
0x18001ede8  mov     [rdx], r10
0x18001edeb  mov     [rcx], rsi
0x18001edee  mov     eax, esi
0x18001edf0  mov     rbx, [rsp+38h+arg_8]
0x18001edf5  mov     rsi, [rsp+38h+arg_10]
0x18001edfa  add     rsp, 30h
0x18001edfe  pop     rdi
0x18001edff  retn
```
