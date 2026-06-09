# FwRule::SetRule(_tag_FW_RULE const *)

- ea: `0x180013e8c`
- end: `0x180013fbb`
- name: `?SetRule@FwRule@@AEAAJPEBU_tag_FW_RULE@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(FwRule *__hidden this, const struct _tag_FW_RULE *)`
- caller_count: `26`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180011a20`
- `0x180011cd0`
- `0x180011ed0`
- `0x180012120`
- `0x1800131a0`
- `0x1800133e0`
- `0x1800135e4`
- `0x180013840`
- `0x180013a80`
- `0x180013c90`
- `0x1800158f0`
- `0x180015b00`
- `0x180015db0`
- `0x18001ed70`
- `0x1800222c0`
- `0x180041b20`
- `0x180041d30`
- `0x180041f40`
- `0x180042190`
- `0x180042370`
- `0x180042550`
- `0x180042730`
- `0x180042980`
- `0x180042b60`
- `0x180042db0`
- `0x180042f90`

## callees

- `0x180013e8c`
- `0x180013fc4`
- `0x1800143d8`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180013f68`
- `fwbase!FwReportReturnError` at `0x180013f8e`
- `fwbase!FwReportReturnError` at `0x180013f68`
- `fwbase!FwReportReturnError` at `0x180013f8e`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180013efe`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180013f79`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180013efe`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180013f79`
- `FWPolicyIOMgr!FwCopyRule` at `0x180013ee2`
- `FWPolicyIOMgr!FwCopyRule` at `0x180013ee2`

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
0x180013e8c  mov     [rsp+arg_10], rbx
0x180013e91  push    rdi
0x180013e92  sub     rsp, 40h
0x180013e96  mov     rax, cs:__security_cookie
0x180013e9d  xor     rax, rsp
0x180013ea0  mov     [rsp+48h+var_18], rax
0x180013ea5  mov     rbx, rdx
0x180013ea8  mov     rdi, rcx
0x180013eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eb2  lea     rax, WPP_GLOBAL_Control
0x180013eb9  cmp     rcx, rax
0x180013ebc  jz      short loc_180013EC8
0x180013ebe  test    byte ptr [rcx+1Ch], 8
0x180013ec2  jnz     loc_180013FA1
0x180013ec8  lea     rdx, [rsp+48h+var_20]
0x180013ecd  mov     [rsp+48h+var_20], 0
0x180013ed6  mov     rcx, rbx
0x180013ed9  mov     [rsp+48h+var_28], 0
0x180013ee2  call    cs:__imp_FwCopyRule
0x180013ee9  nop     dword ptr [rax+rax+00h]
0x180013eee  mov     ebx, eax
0x180013ef0  test    eax, eax
0x180013ef2  js      short loc_180013F5F
0x180013ef4  cmp     dword ptr [rdi+58h], 0
0x180013ef8  jnz     short loc_180013F37
0x180013efa  mov     rcx, [rdi+50h]
0x180013efe  call    cs:__imp_FwFreeWFRule
0x180013f05  nop     dword ptr [rax+rax+00h]
0x180013f0a  mov     rax, [rsp+48h+var_20]
0x180013f0f  mov     [rdi+50h], rax
0x180013f13  mov     [rsp+48h+var_20], 0
0x180013f1c  mov     eax, ebx
0x180013f1e  mov     rcx, [rsp+48h+var_18]
0x180013f23  xor     rcx, rsp; StackCookie
0x180013f26  call    __security_check_cookie
0x180013f2b  mov     rbx, [rsp+48h+arg_10]
0x180013f30  add     rsp, 40h
0x180013f34  pop     rdi
0x180013f35  retn
0x180013f37  lea     rdx, [rsp+48h+var_28]; void **
0x180013f3c  mov     rcx, rdi; this
0x180013f3f  call    ?GetPolicyStoreHandle@FwRule@@AEAAJPEAPEAX@Z; FwRule::GetPolicyStoreHandle(void * *)
0x180013f44  mov     ebx, eax
0x180013f46  test    eax, eax
0x180013f48  js      short loc_180013F5F
0x180013f4a  mov     rdx, [rsp+48h+var_28]; void *
0x180013f4f  mov     rcx, [rsp+48h+var_20]; struct _tag_FW_RULE *
0x180013f54  call    ?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z; SaveRule(_tag_FW_RULE *,void *)
0x180013f59  mov     ebx, eax
0x180013f5b  test    eax, eax
0x180013f5d  jns     short loc_180013EFA
0x180013f5f  mov     edx, eax
0x180013f61  lea     rcx, aFwruleSetrule; "FwRule::SetRule"
0x180013f68  call    cs:__imp_FwReportReturnError
0x180013f6f  nop     dword ptr [rax+rax+00h]
0x180013f74  mov     rcx, [rsp+48h+var_20]
0x180013f79  call    cs:__imp_FwFreeWFRule
0x180013f80  nop     dword ptr [rax+rax+00h]
0x180013f85  mov     edx, ebx
0x180013f87  lea     rcx, aFwruleSetrule; "FwRule::SetRule"
0x180013f8e  call    cs:__imp_FwReportReturnError
0x180013f95  nop     dword ptr [rax+rax+00h]
0x180013f9a  mov     ebx, eax
0x180013f9c  jmp     loc_180013F1C
0x180013fa1  mov     rcx, [rcx+10h]
0x180013fa5  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180013fac  mov     edx, 5Ch ; '\'
0x180013fb1  call    WPP_SF_
0x180013fb6  jmp     loc_180013EC8
```
