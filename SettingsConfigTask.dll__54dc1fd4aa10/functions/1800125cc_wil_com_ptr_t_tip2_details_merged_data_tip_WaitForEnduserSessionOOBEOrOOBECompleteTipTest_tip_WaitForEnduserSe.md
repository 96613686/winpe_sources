# wil::com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>(void)

- ea: `0x1800125cc`
- end: `0x1800125e2`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012820`
- `0x1800128c0`
- `0x18001c150`
- `0x18001e1ac`

## callees

- `0x1800125cc`
- `0x18001a5cc`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x1800125cc  sub     rsp, 28h
0x1800125d0  mov     rcx, [rcx]; pv
0x1800125d3  test    rcx, rcx
0x1800125d6  jz      short loc_1800125DD
0x1800125d8  call    ?Release@?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::Release(void)
0x1800125dd  add     rsp, 28h
0x1800125e1  retn
```
