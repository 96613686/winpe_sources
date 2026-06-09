# _RtlSystemUtil::PrivilegeAcquisition::_PrivilegeAcquisition_::_2_::_lambda_1_::operator()

- ea: `0x140025eec`
- end: `0x140025f1d`
- name: `_RtlSystemUtil::PrivilegeAcquisition::_PrivilegeAcquisition_::_2_::_lambda_1_::operator()`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140025e90`

## callees

- `0x1400068e8`
- `0x140025eec`
- `0x140026bb8`

## pseudocode

```c
void __fastcall RtlSystemUtil::PrivilegeAcquisition::_PrivilegeAcquisition_::_2_::_lambda_1_::operator()(
        RtlSystemUtil::PrivilegeAcquisition **a1,
        void *a2)
{
  RtlSystemUtil::PrivilegeAcquisition *v3; // rcx
  int v4; // eax
  Windows::ErrorHandling::Rtl::CVoidRaiseFrame *v5; // rcx

  v3 = *a1;
  if ( *((_BYTE *)v3 + 8) && (v4 = RtlSystemUtil::PrivilegeAcquisition::Restore(v3, a2), v4 < 0) )
  {
    v5 = a1[1];
    *(_DWORD *)v5 = v4;
    Windows::ErrorHandling::Rtl::CVoidRaiseFrame::ExitReturn(v5);
  }
  else
  {
    Windows::ErrorHandling::Rtl::CVoidRaiseFrame::ExitReturn(a1[1]);
  }
}

```

## disassembly

```asm
0x140025eec  push    rbx
0x140025eee  sub     rsp, 20h
0x140025ef2  mov     rbx, rcx
0x140025ef5  mov     rcx, [rcx]; this
0x140025ef8  cmp     byte ptr [rcx+8], 0
0x140025efc  jz      short loc_140025F0F
0x140025efe  call    ?Restore@PrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::PrivilegeAcquisition::Restore(void)
0x140025f03  test    eax, eax
0x140025f05  jns     short loc_140025F0F
0x140025f07  mov     rcx, [rbx+8]
0x140025f0b  mov     [rcx], eax
0x140025f0d  jmp     short loc_140025F13
0x140025f0f  mov     rcx, [rbx+8]; this
0x140025f13  add     rsp, 20h
0x140025f17  pop     rbx
0x140025f18  jmp     ?ExitReturn@CVoidRaiseFrame@Rtl@ErrorHandling@Windows@@QEBAXXZ; Windows::ErrorHandling::Rtl::CVoidRaiseFrame::ExitReturn(void)
```
