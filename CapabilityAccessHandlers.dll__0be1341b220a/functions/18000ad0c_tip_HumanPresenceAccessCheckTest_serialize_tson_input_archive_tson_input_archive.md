# _tip_HumanPresenceAccessCheckTest::serialize<tson::input_archive>(tson::input_archive &)

- ea: `0x18000ad0c`
- end: `0x18000adbd`
- name: `??$serialize@Vinput_archive@tson@@@_tip_HumanPresenceAccessCheckTest@@QEAAXAEAVinput_archive@tson@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000d380`

## callees

- `0x18000ab28`
- `0x18000ad0c`
- `0x18000d2d0`
- `0x18000d308`
- `0x18000e8e8`

## string_xrefs

- `0x18000ad5f`: `accessCheckStatus`

## pseudocode

```c
__int64 __fastcall _tip_HumanPresenceAccessCheckTest::serialize<tson::input_archive>(__int64 a1, __int64 a2)
{
  int v3; // edi
  __int64 v5; // rdx
  const char *v7; // [rsp+20h] [rbp-38h] BYREF
  char v8; // [rsp+28h] [rbp-30h]
  __int64 v9; // [rsp+30h] [rbp-28h]
  const char *v10; // [rsp+38h] [rbp-20h] BYREF
  char v11; // [rsp+40h] [rbp-18h]
  __int64 v12; // [rsp+48h] [rbp-10h]
  int v13; // [rsp+60h] [rbp+8h] BYREF

  *(_BYTE *)(a2 + 24) = 17;
  v7 = "endTime";
  v8 = 7;
  v9 = a1 + 32;
  v3 = 0;
  v13 = 0;
  v10 = "startTime";
  v11 = 9;
  v12 = a1 + 24;
  *(_QWORD *)(a2 + 16) = "accessCheckStatus";
  if ( tson::input_archive::search((tson::input_archive *)a2) )
  {
    LOBYTE(v5) = 18;
    tson::input_archive::consume_expected_marker(a2, v5, 2147944029LL);
    tson::read_buffer::consume_n(*(tson::read_buffer **)a2, &v13, 4u);
    v3 = v13;
  }
  *(_DWORD *)(a1 + 16) = v3;
  return tson::input_archive::process<tson::nvp<unsigned __int64 &>,tson::nvp<unsigned __int64 &>>(a2, &v10, &v7);
}

```

## disassembly

```asm
0x18000ad0c  mov     r11, rsp
0x18000ad0f  mov     [r11+10h], rbx
0x18000ad13  mov     [r11+18h], rsi
0x18000ad17  push    rdi
0x18000ad18  sub     rsp, 50h
0x18000ad1c  lea     rax, aEndtime; "endTime"
0x18000ad23  mov     byte ptr [rdx+18h], 11h
0x18000ad27  mov     [r11-38h], rax
0x18000ad2b  mov     rsi, rcx
0x18000ad2e  lea     rax, [rcx+20h]
0x18000ad32  mov     [rsp+58h+var_30], 7
0x18000ad37  mov     [r11-28h], rax
0x18000ad3b  xor     edi, edi
0x18000ad3d  lea     rax, aStarttime; "startTime"
0x18000ad44  mov     [rsp+58h+arg_0], edi
0x18000ad48  mov     [r11-20h], rax
0x18000ad4c  mov     rbx, rdx
0x18000ad4f  lea     rax, [rcx+18h]
0x18000ad53  mov     [rsp+58h+var_18], 9
0x18000ad58  mov     [r11-10h], rax
0x18000ad5c  mov     rcx, rdx; this
0x18000ad5f  lea     rax, aAccesschecksta; "accessCheckStatus"
0x18000ad66  mov     [rdx+10h], rax
0x18000ad6a  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x18000ad6f  test    al, al
0x18000ad71  jz      short loc_18000AD98
0x18000ad73  mov     r8d, 8007065Dh
0x18000ad79  mov     dl, 12h
0x18000ad7b  mov     rcx, rbx
0x18000ad7e  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18000ad83  mov     rcx, [rbx]; this
0x18000ad86  lea     rdx, [rsp+58h+arg_0]; void *
0x18000ad8b  lea     r8d, [rdi+4]; unsigned __int64
0x18000ad8f  call    ?consume_n@read_buffer@tson@@QEAA_NPEAX_K@Z; tson::read_buffer::consume_n(void *,unsigned __int64)
0x18000ad94  mov     edi, [rsp+58h+arg_0]
0x18000ad98  lea     r8, [rsp+58h+var_38]
0x18000ad9d  mov     [rsi+10h], edi
0x18000ada0  lea     rdx, [rsp+58h+var_20]
0x18000ada5  mov     rcx, rbx
0x18000ada8  call    ??$process@V?$nvp@AEA_K@tson@@V12@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_K@1@0@Z; tson::input_archive::process<tson::nvp<unsigned __int64 &>,tson::nvp<unsigned __int64 &>>(tson::nvp<unsigned __int64 &> &&,tson::nvp<unsigned __int64 &> &&)
0x18000adad  mov     rbx, [rsp+58h+arg_8]
0x18000adb2  mov     rsi, [rsp+58h+arg_10]
0x18000adb7  add     rsp, 50h
0x18000adbb  pop     rdi
0x18000adbc  retn
```
