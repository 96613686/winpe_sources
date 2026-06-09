# Int_FWUpgradeAuthenticationSet(_tag_FW_AUTH_SET2_10 *,_tag_FW_AUTH_SET * *,_tag_FW_AUTH_SET * *)

- ea: `0x18004cb14`
- end: `0x18004cbea`
- name: `?Int_FWUpgradeAuthenticationSet@@YAKPEAU_tag_FW_AUTH_SET2_10@@PEAPEAU_tag_FW_AUTH_SET@@1@Z`
- size: `214`
- prototype: `unsigned int __fastcall(struct _tag_FW_AUTH_SET2_10 *, struct _tag_FW_AUTH_SET **, struct _tag_FW_AUTH_SET **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004ce20`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x18004cb14`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18004cb5d`
- `fwbase!FwHResultToWindowsError` at `0x18004cb5d`
- `FWPolicyIOMgr!FwCopyAuthsetToHigherVersion` at `0x18004cb4f`
- `FWPolicyIOMgr!FwCopyAuthsetToHigherVersion` at `0x18004cb4f`
- `FWPolicyIOMgr!FwDownlevelAuthSetFree` at `0x18004cbb5`
- `FWPolicyIOMgr!FwDownlevelAuthSetFree` at `0x18004cbb5`

## pseudocode

```c
__int64 __fastcall Int_FWUpgradeAuthenticationSet(
        struct _tag_FW_AUTH_SET2_10 *a1,
        struct _tag_FW_AUTH_SET **a2,
        struct _tag_FW_AUTH_SET **a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  struct _tag_FW_AUTH_SET *v8; // rax
  struct _tag_FW_AUTH_SET *v10; // [rsp+20h] [rbp-28h] BYREF

  v10 = 0;
  v6 = FwCopyAuthsetToHigherVersion(522, a1, &v10);
  v7 = FwHResultToWindowsError(v6);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v7);
  }
  else
  {
    *(_QWORD *)v10 = *(_QWORD *)a1;
    FwDownlevelAuthSetFree(522, a1);
    v8 = v10;
    *a3 = v10;
    *a2 = v8;
  }
  return v7;
}

```

## disassembly

```asm
0x18004cb14  mov     [rsp+arg_18], rbx
0x18004cb19  push    rsi
0x18004cb1a  push    rdi
0x18004cb1b  push    r14
0x18004cb1d  sub     rsp, 30h
0x18004cb21  mov     rax, cs:__security_cookie
0x18004cb28  xor     rax, rsp
0x18004cb2b  mov     [rsp+48h+var_20], rax
0x18004cb30  mov     rdi, rcx
0x18004cb33  mov     [rsp+48h+var_28], 0
0x18004cb3c  mov     r14, r8
0x18004cb3f  mov     rsi, rdx
0x18004cb42  mov     rdx, rdi
0x18004cb45  lea     r8, [rsp+48h+var_28]
0x18004cb4a  mov     ecx, 20Ah
0x18004cb4f  call    cs:__imp_FwCopyAuthsetToHigherVersion
0x18004cb56  nop     dword ptr [rax+rax+00h]
0x18004cb5b  mov     ecx, eax
0x18004cb5d  call    cs:__imp_FwHResultToWindowsError
0x18004cb64  nop     dword ptr [rax+rax+00h]
0x18004cb69  mov     ebx, eax
0x18004cb6b  test    eax, eax
0x18004cb6d  jz      short loc_18004CBA2
0x18004cb6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb76  lea     rax, WPP_GLOBAL_Control
0x18004cb7d  cmp     rcx, rax
0x18004cb80  jz      short loc_18004CBCC
0x18004cb82  test    byte ptr [rcx+1Ch], 1
0x18004cb86  jz      short loc_18004CBCC
0x18004cb88  mov     rcx, [rcx+10h]
0x18004cb8c  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004cb93  mov     edx, 0C2h
0x18004cb98  mov     r9d, ebx
0x18004cb9b  call    WPP_SF_d
0x18004cba0  jmp     short loc_18004CBCC
0x18004cba2  mov     rax, [rsp+48h+var_28]
0x18004cba7  mov     ecx, 20Ah
0x18004cbac  mov     r8, [rdi]
0x18004cbaf  mov     rdx, rdi
0x18004cbb2  mov     [rax], r8
0x18004cbb5  call    cs:__imp_FwDownlevelAuthSetFree
0x18004cbbc  nop     dword ptr [rax+rax+00h]
0x18004cbc1  mov     rax, [rsp+48h+var_28]
0x18004cbc6  mov     [r14], rax
0x18004cbc9  mov     [rsi], rax
0x18004cbcc  mov     eax, ebx
0x18004cbce  mov     rcx, [rsp+48h+var_20]
0x18004cbd3  xor     rcx, rsp; StackCookie
0x18004cbd6  call    __security_check_cookie
0x18004cbdb  mov     rbx, [rsp+48h+arg_18]
0x18004cbe0  add     rsp, 30h
0x18004cbe4  pop     r14
0x18004cbe6  pop     rdi
0x18004cbe7  pop     rsi
0x18004cbe8  retn
```
