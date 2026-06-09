# tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::serialize(tson::output_archive &,tip2::details::serialize_options)

- ea: `0x18000ea70`
- end: `0x18000eaff`
- name: `?serialize@?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@EEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z`
- size: `143`
- prototype: `void __fastcall(__int64, tson::output_archive *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000abdc`
- `0x18000df0c`
- `0x18000ea70`
- `0x18000ef58`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::serialize(
        __int64 a1,
        tson::output_archive *a2,
        char a3)
{
  const char *v6; // [rsp+20h] [rbp-28h] BYREF
  char v7; // [rsp+28h] [rbp-20h]
  __int64 v8; // [rsp+30h] [rbp-18h]

  if ( (a3 & 2) != 0 )
  {
    *((_BYTE *)a2 + 8) = 7;
    *(_QWORD *)a2 = "metrics";
    tson::output_archive::startNode(a2);
    *(_DWORD *)(a1 + 184) = 0;
    tson::output_archive::finishNode(a2);
  }
  if ( (a3 & 1) != 0 )
  {
    v7 = 4;
    v6 = "test";
    v8 = (a1 + 256) & -(__int64)(a1 != 0);
    tson::save_nothrow<_tip_HumanPresenceAccessCheckTest &>(a2, (__int64)&v6);
  }
}

```

## disassembly

```asm
0x18000ea70  mov     [rsp+arg_0], rbx
0x18000ea75  mov     [rsp+arg_8], rsi
0x18000ea7a  push    rdi
0x18000ea7b  sub     rsp, 40h
0x18000ea7f  mov     esi, r8d
0x18000ea82  mov     rbx, rdx
0x18000ea85  mov     rdi, rcx
0x18000ea88  test    r8b, 2
0x18000ea8c  jz      short loc_18000EAB6
0x18000ea8e  lea     rax, aMetrics; "metrics"
0x18000ea95  mov     byte ptr [rdx+8], 7
0x18000ea99  mov     rcx, rdx; this
0x18000ea9c  mov     [rdx], rax
0x18000ea9f  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18000eaa4  mov     rcx, rbx; this
0x18000eaa7  mov     dword ptr [rdi+0B8h], 0
0x18000eab1  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000eab6  test    sil, 1
0x18000eaba  jz      short loc_18000EAEF
0x18000eabc  lea     rcx, [rdi+100h]
0x18000eac3  mov     [rsp+48h+var_20], 4
0x18000eac8  neg     rdi
0x18000eacb  lea     rax, aTest; "test"
0x18000ead2  mov     [rsp+48h+var_28], rax
0x18000ead7  lea     rdx, [rsp+48h+var_28]
0x18000eadc  sbb     rax, rax
0x18000eadf  and     rax, rcx
0x18000eae2  mov     rcx, rbx; this
0x18000eae5  mov     [rsp+48h+var_18], rax
0x18000eaea  call    ??$save_nothrow@AEAU_tip_HumanPresenceAccessCheckTest@@@tson@@YAXAEAVoutput_archive@0@AEAV?$nvp@AEAU_tip_HumanPresenceAccessCheckTest@@@0@@Z; tson::save_nothrow<_tip_HumanPresenceAccessCheckTest &>(tson::output_archive &,tson::nvp<_tip_HumanPresenceAccessCheckTest &> &)
0x18000eaef  mov     rbx, [rsp+48h+arg_0]
0x18000eaf4  mov     rsi, [rsp+48h+arg_8]
0x18000eaf9  add     rsp, 40h
0x18000eafd  pop     rdi
0x18000eafe  retn
```
