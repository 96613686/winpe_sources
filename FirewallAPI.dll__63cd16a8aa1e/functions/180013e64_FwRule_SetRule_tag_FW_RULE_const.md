# FwRule::SetRule(_tag_FW_RULE const *)

- ea: `0x180013e64`
- end: `0x180013f71`
- name: `?SetRule@FwRule@@AEAAJPEBU_tag_FW_RULE@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(FwRule *__hidden this, const struct _tag_FW_RULE *)`
- caller_count: `26`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180011c20`
- `0x180011e50`
- `0x180012030`
- `0x180012260`
- `0x180013230`
- `0x180013450`
- `0x180013638`
- `0x180013860`
- `0x180013a90`
- `0x180013c80`
- `0x180015850`
- `0x180015a40`
- `0x180015cd0`
- `0x18001d8b0`
- `0x180020b00`
- `0x18003eaa0`
- `0x18003ec90`
- `0x18003ee80`
- `0x18003f0b0`
- `0x18003f280`
- `0x18003f450`
- `0x18003f620`
- `0x18003f850`
- `0x18003fa20`
- `0x18003fc60`
- `0x18003fe30`

## callees

- `0x180013e64`
- `0x180013f78`
- `0x180014368`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180013f33`
- `fwbase!FwReportReturnError` at `0x180013f4d`
- `fwbase!FwReportReturnError` at `0x180013f33`
- `fwbase!FwReportReturnError` at `0x180013f4d`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180013ed0`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180013f3e`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180013ed0`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180013f3e`
- `FWPolicyIOMgr!FwCopyRule` at `0x180013eba`
- `FWPolicyIOMgr!FwCopyRule` at `0x180013eba`

## pseudocode

```c
__int64 __fastcall FwRule::SetRule(FwRule *this, const struct _tag_FW_RULE *a2)
{
  int PolicyStoreHandle; // eax
  unsigned int v5; // ebx
  void *v7; // [rsp+20h] [rbp-28h] BYREF
  struct _tag_FW_RULE *v8; // [rsp+28h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  v8 = 0;
  v7 = 0;
  PolicyStoreHandle = FwCopyRule(a2, &v8);
  v5 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0
    || *((_DWORD *)this + 22)
    && ((PolicyStoreHandle = FwRule::GetPolicyStoreHandle(this, &v7), v5 = PolicyStoreHandle, PolicyStoreHandle < 0)
     || (PolicyStoreHandle = SaveRule(v8, v7), v5 = PolicyStoreHandle, PolicyStoreHandle < 0)) )
  {
    FwReportReturnError("FwRule::SetRule", (unsigned int)PolicyStoreHandle);
    FwFreeWFRule(v8);
    return (unsigned int)FwReportReturnError("FwRule::SetRule", v5);
  }
  else
  {
    FwFreeWFRule(*((_QWORD *)this + 10));
    *((_QWORD *)this + 10) = v8;
    v8 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180013e64  mov     [rsp+arg_10], rbx
0x180013e69  push    rdi
0x180013e6a  sub     rsp, 40h
0x180013e6e  mov     rax, cs:__security_cookie
0x180013e75  xor     rax, rsp
0x180013e78  mov     [rsp+48h+var_18], rax
0x180013e7d  mov     rbx, rdx
0x180013e80  mov     rdi, rcx
0x180013e83  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e8a  lea     rax, WPP_GLOBAL_Control
0x180013e91  cmp     rcx, rax
0x180013e94  jz      short loc_180013EA0
0x180013e96  test    byte ptr [rcx+1Ch], 8
0x180013e9a  jnz     loc_180013F57
0x180013ea0  lea     rdx, [rsp+48h+var_20]
0x180013ea5  mov     [rsp+48h+var_20], 0
0x180013eae  mov     rcx, rbx
0x180013eb1  mov     [rsp+48h+var_28], 0
0x180013eba  call    cs:__imp_FwCopyRule
0x180013ec0  mov     ebx, eax
0x180013ec2  test    eax, eax
0x180013ec4  js      short loc_180013F2A
0x180013ec6  cmp     dword ptr [rdi+58h], 0
0x180013eca  jnz     short loc_180013F02
0x180013ecc  mov     rcx, [rdi+50h]
0x180013ed0  call    cs:__imp_FwFreeWFRule
0x180013ed6  mov     rax, [rsp+48h+var_20]
0x180013edb  mov     [rdi+50h], rax
0x180013edf  mov     [rsp+48h+var_20], 0
0x180013ee8  mov     eax, ebx
0x180013eea  mov     rcx, [rsp+48h+var_18]
0x180013eef  xor     rcx, rsp; StackCookie
0x180013ef2  call    __security_check_cookie
0x180013ef7  mov     rbx, [rsp+48h+arg_10]
0x180013efc  add     rsp, 40h
0x180013f00  pop     rdi
0x180013f01  retn
0x180013f02  lea     rdx, [rsp+48h+var_28]; void **
0x180013f07  mov     rcx, rdi; this
0x180013f0a  call    ?GetPolicyStoreHandle@FwRule@@AEAAJPEAPEAX@Z; FwRule::GetPolicyStoreHandle(void * *)
0x180013f0f  mov     ebx, eax
0x180013f11  test    eax, eax
0x180013f13  js      short loc_180013F2A
0x180013f15  mov     rdx, [rsp+48h+var_28]; void *
0x180013f1a  mov     rcx, [rsp+48h+var_20]; struct _tag_FW_RULE *
0x180013f1f  call    ?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z; SaveRule(_tag_FW_RULE *,void *)
0x180013f24  mov     ebx, eax
0x180013f26  test    eax, eax
0x180013f28  jns     short loc_180013ECC
0x180013f2a  mov     edx, eax
0x180013f2c  lea     rcx, aFwruleSetrule; "FwRule::SetRule"
0x180013f33  call    cs:__imp_FwReportReturnError
0x180013f39  mov     rcx, [rsp+48h+var_20]
0x180013f3e  call    cs:__imp_FwFreeWFRule
0x180013f44  mov     edx, ebx
0x180013f46  lea     rcx, aFwruleSetrule; "FwRule::SetRule"
0x180013f4d  call    cs:__imp_FwReportReturnError
0x180013f53  mov     ebx, eax
0x180013f55  jmp     short loc_180013EE8
0x180013f57  mov     rcx, [rcx+10h]
0x180013f5b  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180013f62  mov     edx, 5Ch ; '\'
0x180013f67  call    WPP_SF_
0x180013f6c  jmp     loc_180013EA0
```
