# RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)

- ea: `0x140025e90`
- end: `0x140025ee5`
- name: `??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(RtlSystemUtil::PrivilegeAcquisition *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001344c`

## callees

- `0x140002310`
- `0x14000e66c`
- `0x140025e7c`
- `0x140025eec`

## pseudocode

```c
void __fastcall RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(RtlSystemUtil::PrivilegeAcquisition *this)
{
  __int64 v2; // rax
  _BYTE v3[16]; // [rsp+20h] [rbp-28h] BYREF
  int v4; // [rsp+30h] [rbp-18h] BYREF

  v4 = 0;
  v2 = RtlSystemUtil::PrivilegeAcquisition::_PrivilegeAcquisition_::_2_::_lambda_1_::_lambda_1_(v3, this, &v4);
  RtlSystemUtil::PrivilegeAcquisition::_PrivilegeAcquisition_::_2_::_lambda_1_::operator()(v2);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(this);
}

```

## disassembly

```asm
0x140025e90  push    rbx
0x140025e92  sub     rsp, 40h
0x140025e96  mov     rax, cs:__security_cookie
0x140025e9d  xor     rax, rsp
0x140025ea0  mov     [rsp+48h+var_10], rax
0x140025ea5  mov     rdx, rcx
0x140025ea8  mov     [rsp+48h+var_18], 0
0x140025eb0  mov     rbx, rcx
0x140025eb3  lea     r8, [rsp+48h+var_18]
0x140025eb8  lea     rcx, [rsp+48h+var_28]
0x140025ebd  call    _RtlSystemUtil__PrivilegeAcquisition___PrivilegeAcquisition____2____lambda_1____lambda_1_
0x140025ec2  mov     rcx, rax
0x140025ec5  call    _RtlSystemUtil__PrivilegeAcquisition___PrivilegeAcquisition____2____lambda_1___operator__
0x140025eca  mov     rcx, rbx
0x140025ecd  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140025ed2  mov     rcx, [rsp+48h+var_10]
0x140025ed7  xor     rcx, rsp; StackCookie
0x140025eda  call    __security_check_cookie
0x140025edf  add     rsp, 40h
0x140025ee3  pop     rbx
0x140025ee4  retn
```
