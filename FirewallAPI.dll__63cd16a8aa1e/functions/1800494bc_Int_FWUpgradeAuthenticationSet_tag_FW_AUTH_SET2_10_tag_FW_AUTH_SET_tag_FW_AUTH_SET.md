# Int_FWUpgradeAuthenticationSet(_tag_FW_AUTH_SET2_10 *,_tag_FW_AUTH_SET * *,_tag_FW_AUTH_SET * *)

- ea: `0x1800494bc`
- end: `0x18004957f`
- name: `?Int_FWUpgradeAuthenticationSet@@YAKPEAU_tag_FW_AUTH_SET2_10@@PEAPEAU_tag_FW_AUTH_SET@@1@Z`
- size: `195`
- prototype: `unsigned int __fastcall(struct _tag_FW_AUTH_SET2_10 *, struct _tag_FW_AUTH_SET **, struct _tag_FW_AUTH_SET **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004979c`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x1800494bc`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800494ff`
- `fwbase!FwHResultToWindowsError` at `0x1800494ff`
- `FWPolicyIOMgr!FwCopyAuthsetToHigherVersion` at `0x1800494f7`
- `FWPolicyIOMgr!FwCopyAuthsetToHigherVersion` at `0x1800494f7`
- `FWPolicyIOMgr!FwDownlevelAuthSetFree` at `0x180049551`
- `FWPolicyIOMgr!FwDownlevelAuthSetFree` at `0x180049551`

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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v7);
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
0x1800494bc  mov     [rsp+arg_18], rbx
0x1800494c1  push    rsi
0x1800494c2  push    rdi
0x1800494c3  push    r14
0x1800494c5  sub     rsp, 30h
0x1800494c9  mov     rax, cs:__security_cookie
0x1800494d0  xor     rax, rsp
0x1800494d3  mov     [rsp+48h+var_20], rax
0x1800494d8  mov     rdi, rcx
0x1800494db  mov     [rsp+48h+var_28], 0
0x1800494e4  mov     r14, r8
0x1800494e7  mov     rsi, rdx
0x1800494ea  mov     rdx, rdi
0x1800494ed  lea     r8, [rsp+48h+var_28]
0x1800494f2  mov     ecx, 20Ah
0x1800494f7  call    cs:__imp_FwCopyAuthsetToHigherVersion
0x1800494fd  mov     ecx, eax
0x1800494ff  call    cs:__imp_FwHResultToWindowsError
0x180049505  mov     ebx, eax
0x180049507  test    eax, eax
0x180049509  jz      short loc_18004953E
0x18004950b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049512  lea     rax, WPP_GLOBAL_Control
0x180049519  cmp     rcx, rax
0x18004951c  jz      short loc_180049562
0x18004951e  test    byte ptr [rcx+1Ch], 1
0x180049522  jz      short loc_180049562
0x180049524  mov     rcx, [rcx+10h]
0x180049528  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18004952f  mov     edx, 0C3h
0x180049534  mov     r9d, ebx
0x180049537  call    WPP_SF_d
0x18004953c  jmp     short loc_180049562
0x18004953e  mov     rax, [rsp+48h+var_28]
0x180049543  mov     ecx, 20Ah
0x180049548  mov     r8, [rdi]
0x18004954b  mov     rdx, rdi
0x18004954e  mov     [rax], r8
0x180049551  call    cs:__imp_FwDownlevelAuthSetFree
0x180049557  mov     rax, [rsp+48h+var_28]
0x18004955c  mov     [r14], rax
0x18004955f  mov     [rsi], rax
0x180049562  mov     eax, ebx
0x180049564  mov     rcx, [rsp+48h+var_20]
0x180049569  xor     rcx, rsp; StackCookie
0x18004956c  call    __security_check_cookie
0x180049571  mov     rbx, [rsp+48h+arg_18]
0x180049576  add     rsp, 30h
0x18004957a  pop     r14
0x18004957c  pop     rdi
0x18004957d  pop     rsi
0x18004957e  retn
```
