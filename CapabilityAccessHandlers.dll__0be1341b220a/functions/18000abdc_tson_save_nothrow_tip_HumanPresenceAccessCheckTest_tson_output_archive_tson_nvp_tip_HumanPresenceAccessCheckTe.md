# tson::save_nothrow<_tip_HumanPresenceAccessCheckTest &>(tson::output_archive &,tson::nvp<_tip_HumanPresenceAccessCheckTest &> &)

- ea: `0x18000abdc`
- end: `0x18000ac71`
- name: `??$save_nothrow@AEAU_tip_HumanPresenceAccessCheckTest@@@tson@@YAXAEAVoutput_archive@0@AEAV?$nvp@AEAU_tip_HumanPresenceAccessCheckTest@@@0@@Z`
- size: `149`
- prototype: `void __fastcall(tson::output_archive *this, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000ea70`

## callees

- `0x18000ab58`
- `0x18000df0c`
- `0x18000e324`
- `0x18000ef58`

## string_xrefs

- `0x18000ac36`: `accessCheckStatus`

## pseudocode

```c
void __fastcall tson::save_nothrow<_tip_HumanPresenceAccessCheckTest &>(tson::output_archive *this, __int64 a2)
{
  char v2; // r8
  __int64 v4; // rbx
  unsigned int v5; // edx
  const char *v6; // [rsp+20h] [rbp-38h] BYREF
  char v7; // [rsp+28h] [rbp-30h]
  __int64 v8; // [rsp+30h] [rbp-28h]
  const char *v9; // [rsp+38h] [rbp-20h] BYREF
  char v10; // [rsp+40h] [rbp-18h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v2 = *(_BYTE *)(a2 + 8);
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_BYTE *)this + 8) = v2;
  v4 = *(_QWORD *)(a2 + 16);
  tson::output_archive::startNode(this);
  *((_BYTE *)this + 8) = 17;
  v6 = "endTime";
  v7 = 7;
  v8 = v4 + 32;
  v9 = "startTime";
  v11 = v4 + 24;
  *(_QWORD *)this = "accessCheckStatus";
  v5 = *(_DWORD *)(v4 + 16);
  v10 = 9;
  tson::output_archive::saveValue(this, v5);
  tson::output_archive::process<tson::nvp<unsigned __int64 &>,tson::nvp<unsigned __int64 &>>(this, &v9, &v6);
  tson::output_archive::finishNode(this);
}

```

## disassembly

```asm
0x18000abdc  mov     [rsp+arg_0], rbx
0x18000abe1  push    rdi
0x18000abe2  sub     rsp, 50h
0x18000abe6  mov     r8b, [rdx+8]
0x18000abea  mov     rdi, rcx
0x18000abed  mov     rax, [rdx]
0x18000abf0  mov     [rcx], rax
0x18000abf3  mov     [rcx+8], r8b
0x18000abf7  mov     rbx, [rdx+10h]
0x18000abfb  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18000ac00  lea     rax, aEndtime; "endTime"
0x18000ac07  mov     byte ptr [rdi+8], 11h
0x18000ac0b  mov     [rsp+58h+var_38], rax
0x18000ac10  mov     rcx, rdi; this
0x18000ac13  lea     rax, [rbx+20h]
0x18000ac17  mov     [rsp+58h+var_30], 7
0x18000ac1c  mov     [rsp+58h+var_28], rax
0x18000ac21  lea     rax, aStarttime; "startTime"
0x18000ac28  mov     [rsp+58h+var_20], rax
0x18000ac2d  lea     rax, [rbx+18h]
0x18000ac31  mov     [rsp+58h+var_10], rax
0x18000ac36  lea     rax, aAccesschecksta; "accessCheckStatus"
0x18000ac3d  mov     [rdi], rax
0x18000ac40  mov     edx, [rbx+10h]; unsigned int
0x18000ac43  mov     [rsp+58h+var_18], 9
0x18000ac48  call    ?saveValue@output_archive@tson@@QEAAXK@Z; tson::output_archive::saveValue(ulong)
0x18000ac4d  lea     r8, [rsp+58h+var_38]
0x18000ac52  mov     rcx, rdi
0x18000ac55  lea     rdx, [rsp+58h+var_20]
0x18000ac5a  call    ??$process@V?$nvp@AEA_K@tson@@V12@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEA_K@1@0@Z; tson::output_archive::process<tson::nvp<unsigned __int64 &>,tson::nvp<unsigned __int64 &>>(tson::nvp<unsigned __int64 &> &&,tson::nvp<unsigned __int64 &> &&)
0x18000ac5f  mov     rcx, rdi; this
0x18000ac62  mov     rbx, [rsp+58h+arg_0]
0x18000ac67  add     rsp, 50h
0x18000ac6b  pop     rdi
0x18000ac6c  jmp     ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
```
