# tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>(void)

- ea: `0x18001eb2c`
- end: `0x18001ebda`
- name: `??0?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `174`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ab14`

## callees

- `0x18001ebe0`

## string_xrefs

- `0x18001eb57`: `CreateBacklightServerTipTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>(
        __int64 a1)
{
  __int64 result; // rax
  _DWORD v3[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v4; // [rsp+28h] [rbp-30h]
  __int16 v5; // [rsp+30h] [rbp-28h]
  int v6; // [rsp+32h] [rbp-26h]
  __int16 v7; // [rsp+36h] [rbp-22h]
  __int128 v8; // [rsp+38h] [rbp-20h]
  __int64 v9; // [rsp+48h] [rbp-10h]

  v3[0] = 56258760;
  v6 = 0;
  v7 = 0;
  *(_QWORD *)a1 = &tip2::details::test_data_interface::`vftable';
  v9 = 0;
  v4 = "CreateBacklightServerTipTest";
  v3[1] = 16640;
  v5 = 1;
  v8 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(a1 + 8, a1, v3);
  *(_DWORD *)(a1 + 272) = 0;
  *(_BYTE *)(a1 + 276) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_DWORD *)(a1 + 288) = 0;
  *(_QWORD *)a1 = &tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::`vftable';
  *(_QWORD *)(a1 + 264) = a1 + 16;
  result = a1;
  *(_DWORD *)(a1 + 296) = 1;
  return result;
}

```

## disassembly

```asm
0x18001eb2c  push    rbx
0x18001eb2e  sub     rsp, 50h
0x18001eb32  xor     edx, edx
0x18001eb34  mov     [rsp+58h+var_38], 35A70C8h
0x18001eb3c  mov     rbx, rcx
0x18001eb3f  mov     [rsp+58h+var_26], edx
0x18001eb43  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18001eb4a  mov     [rsp+58h+var_22], dx
0x18001eb4f  mov     [rcx], rax
0x18001eb52  lea     r8, [rsp+58h+var_38]
0x18001eb57  lea     rcx, aCreatebackligh; "CreateBacklightServerTipTest"
0x18001eb5e  mov     [rsp+58h+var_10], rdx
0x18001eb63  mov     [rsp+58h+var_30], rcx
0x18001eb68  xorps   xmm0, xmm0
0x18001eb6b  lea     rcx, [rbx+8]
0x18001eb6f  mov     [rsp+58h+var_34], 4100h
0x18001eb77  mov     rdx, rbx
0x18001eb7a  mov     [rsp+58h+var_28], 1
0x18001eb81  movdqu  [rsp+58h+var_20], xmm0
0x18001eb87  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18001eb8c  mov     dword ptr [rbx+110h], 0
0x18001eb96  lea     rax, ??_7?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::`vftable'
0x18001eb9d  mov     byte ptr [rbx+114h], 0
0x18001eba4  mov     qword ptr [rbx+118h], 0
0x18001ebaf  mov     dword ptr [rbx+120h], 0
0x18001ebb9  mov     [rbx], rax
0x18001ebbc  lea     rax, [rbx+10h]
0x18001ebc0  mov     [rbx+108h], rax
0x18001ebc7  mov     rax, rbx
0x18001ebca  mov     dword ptr [rbx+128h], 1
0x18001ebd4  add     rsp, 50h
0x18001ebd8  pop     rbx
0x18001ebd9  retn
```
