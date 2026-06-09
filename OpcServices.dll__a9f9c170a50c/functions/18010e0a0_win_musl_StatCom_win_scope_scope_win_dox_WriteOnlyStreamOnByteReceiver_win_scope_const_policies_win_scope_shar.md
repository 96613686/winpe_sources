# win_musl::StatCom<win_scope::scope<win_dox::WriteOnlyStreamOnByteReceiver *,win_scope::const_policies<win_scope::shared_policies>>,IStream,2,win_musl::InnerCom<win_scope::scope<win_dox::WriteOnlyStreamOnByteReceiver *,win_scope::const_policies<win_scope::shared_policies>>,IStream,win_scope::report_policy_throw>>::Stat(tagSTATSTG *,ulong)

- ea: `0x18010e0a0`
- end: `0x18010e0ee`
- name: `?Stat@?$StatCom@V?$scope@PEAVWriteOnlyStreamOnByteReceiver@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIStream@@$01V?$InnerCom@V?$scope@PEAVWriteOnlyStreamOnByteReceiver@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIStream@@Ureport_policy_throw@2@@win_musl@@@win_musl@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18010d9d4`
- `0x18010e0a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010e0d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010e0d6`

## pseudocode

```c
__int64 __fastcall win_musl::StatCom<win_scope::scope<win_dox::WriteOnlyStreamOnByteReceiver *,win_scope::const_policies<win_scope::shared_policies>>,IStream,2,win_musl::InnerCom<win_scope::scope<win_dox::WriteOnlyStreamOnByteReceiver *,win_scope::const_policies<win_scope::shared_policies>>,IStream,win_scope::report_policy_throw>>::Stat(
        int a1,
        LPVOID *a2,
        int a3)
{
  __int64 result; // rax
  char v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = 1;
  result = win_musl::ModuleEntryCall_win_musl::StatCom_win_scope::scope_win_dox::WriteOnlyStreamOnByteReceiver___win_scope::const_policies_win_scope::shared_policies____IStream_2_win_musl::InnerCom_win_scope::scope_win_dox::WriteOnlyStreamOnByteReceiver___win_scope::const_policies_win_scope::shared_policies____IStream_win_scope::report_policy_throw____tagSTATSTG___unsigned_long_bool___(
             a1,
             (_DWORD)a2,
             (_DWORD)a2,
             a3,
             (__int64)&v5);
  if ( (int)result >= 0 && !v5 )
  {
    if ( *a2 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
    return 2147483658LL;
  }
  return result;
}

```

## disassembly

```asm
0x18010e0a0  push    rbx
0x18010e0a2  sub     rsp, 30h
0x18010e0a6  lea     rax, [rsp+38h+arg_18]
0x18010e0ab  mov     [rsp+38h+arg_18], 1
0x18010e0b0  mov     r9d, r8d
0x18010e0b3  mov     [rsp+38h+var_18], rax
0x18010e0b8  mov     r8, rdx
0x18010e0bb  mov     rbx, rdx
0x18010e0be  call    win_musl__ModuleEntryCall_win_musl__StatCom_win_scope__scope_win_dox__WriteOnlyStreamOnByteReceiver___win_scope__const_policies_win_scope__shared_policies____IStream_2_win_musl__InnerCom_win_scope__scope_win_dox__WriteOnlyStreamOnByteReceiver___win_scope__const_policies_win_scope__shared_policies____IStream_win_scope__report_policy_throw____tagSTATSTG___unsigned_long_bool___
0x18010e0c3  test    eax, eax
0x18010e0c5  js      short loc_18010E0E8
0x18010e0c7  cmp     [rsp+38h+arg_18], 0
0x18010e0cc  jnz     short loc_18010E0E8
0x18010e0ce  mov     rcx, [rbx]; pv
0x18010e0d1  test    rcx, rcx
0x18010e0d4  jz      short loc_18010E0E3
0x18010e0d6  call    cs:__imp_CoTaskMemFree
0x18010e0dc  mov     qword ptr [rbx], 0
0x18010e0e3  mov     eax, 8000000Ah
0x18010e0e8  add     rsp, 30h
0x18010e0ec  pop     rbx
0x18010e0ed  retn
```
