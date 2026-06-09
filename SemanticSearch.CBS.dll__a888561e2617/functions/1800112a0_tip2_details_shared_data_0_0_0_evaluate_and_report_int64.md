# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x1800112a0`
- end: `0x18001160d`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `877`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010910`

## callees

- `0x180010a20`
- `0x1800112a0`
- `0x180011f20`
- `0x180011f90`
- `0x18004c070`
- `0x18005e260`
- `0x18005e2c0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180011561`
- `KERNEL32!GetProcAddress` at `0x180011561`
- `KERNEL32!GetModuleHandleW` at `0x18001154a`
- `KERNEL32!GetModuleHandleW` at `0x18001154a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800115dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800115dc`

## string_xrefs

- `0x180011543`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
{
  tip2::details *v4; // rcx
  int v5; // r14d
  void (__fastcall ***v6)(_QWORD); // rcx
  char v7; // al
  _DWORD *v8; // r15
  unsigned __int8 v9; // r12
  unsigned int v10; // esi
  char v11; // al
  __int64 v12; // r8
  __int64 v13; // rdx
  int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void (__fastcall ***v21)(_QWORD); // rcx
  const struct tip2::test_requirement *v22; // [rsp+20h] [rbp-E0h]
  _OWORD v23[3]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h]
  __int128 v25; // [rsp+70h] [rbp-90h]
  __int128 v26; // [rsp+80h] [rbp-80h]
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  char v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+B9h] [rbp-47h] BYREF
  char v32; // [rsp+BDh] [rbp-43h]
  _BYTE v33[2050]; // [rsp+BEh] [rbp-42h] BYREF
  int *v34; // [rsp+8C0h] [rbp+7C0h]
  _BYTE *v35; // [rsp+8C8h] [rbp+7C8h]
  _BYTE *v36; // [rsp+8D0h] [rbp+7D0h]

  v4 = (tip2::details *)(a1 + 8);
  v5 = 0;
  if ( !*((_BYTE *)v4 + 152)
    && tip2::details::evaluate_flags(
         v4,
         *(const struct tip2::test_state **)(a1 + 40),
         *(const struct tip2::test_requirement **)(a1 + 56),
         *(const struct tip2::test_requirement **)(a1 + 48),
         v22) )
  {
    v6 = *(void (__fastcall ****)(_QWORD))a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v6, 0, 0, 0, 0) && !*(_BYTE *)(a1 + 160) )
      {
        *(_BYTE *)(a1 + 160) = 3;
        *(_WORD *)(a1 + 162) = 16395;
        *(_QWORD *)(a1 + 168) = 0;
      }
    }
    else
    {
      (**v6)(v6);
    }
  }
  v7 = *(_BYTE *)(a1 + 160);
  if ( v7 )
  {
    if ( v7 != 2 && v7 != 3 && ((*(_DWORD *)(a1 + 20) & 0x1000) == 0 || v7 == 4) )
      goto LABEL_16;
  }
  else
  {
    *(_BYTE *)(a1 + 160) = 3;
    *(_WORD *)(a1 + 162) = 16394;
    *(_QWORD *)(a1 + 168) = 0;
  }
  v8 = (_DWORD *)(a1 + 64);
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
  {
    v9 = 1;
    goto LABEL_17;
  }
LABEL_16:
  v9 = 0;
  v8 = (_DWORD *)(a1 + 64);
LABEL_17:
  v10 = v9 | 2;
  if ( (*(_DWORD *)(a1 + 20) & 0x200) == 0 )
    v10 = v9;
  memset(v33, 0, sizeof(v33));
  pv = 0;
  v30 = 0;
  v34 = &v31;
  v36 = &v33[2043];
  v31 = -2143256512;
  v32 = 0;
  v35 = v33;
  v11 = v9;
  if ( (*(_DWORD *)(a1 + 20) & 0x200) != 0 )
    v11 = 1;
  v12 = v10 | 4;
  if ( !v11 )
    v12 = v10;
  v13 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, v12);
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v14 = *(_DWORD *)(a1 + 180);
  if ( v14 )
    LODWORD(v23[0]) = *(_DWORD *)(a1 + 180);
  else
    LODWORD(v23[0]) = *(_DWORD *)(a1 + 16);
  *((_QWORD *)&v23[0] + 1) = *(_QWORD *)(a1 + 24);
  LODWORD(v23[1]) = *(_DWORD *)(a1 + 20);
  *(_OWORD *)((char *)&v23[1] + 4) = *(_OWORD *)(a1 + 144);
  DWORD1(v23[2]) = *v8 | 0x200000;
  BYTE8(v23[2]) = *(_BYTE *)(a1 + 160);
  WORD5(v23[2]) = *(_WORD *)(a1 + 162);
  *(_QWORD *)&v24 = *(_QWORD *)(a1 + 168);
  *((_QWORD *)&v24 + 1) = a2;
  *((_QWORD *)&v25 + 1) = v13;
  HIDWORD(v27) = *(_DWORD *)(a1 + 176);
  if ( v14 )
    LODWORD(v28) = *(_DWORD *)(a1 + 16);
  else
    LODWORD(v28) = 0;
  v15 = 0;
  v16 = *(_QWORD *)(a1 + 72);
  v17 = v16 + 168LL * *(_QWORD *)(a1 + 88);
  if ( v16 != v17 )
  {
    do
    {
      v18 = *(_DWORD *)(v16 + 8);
      if ( v5 != v18 )
        v15 = v16;
      v16 += 168;
      if ( v5 == v18 )
        v18 = v5;
      v5 = v18;
    }
    while ( v16 != v17 );
    if ( v15 )
    {
      LODWORD(v26) = *(_DWORD *)(v15 + 8);
      *((_QWORD *)&v26 + 1) = *(_QWORD *)(v15 + 56);
      LOWORD(v27) = *(_WORD *)(v15 + 64);
    }
  }
  ProcAddress = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
  if ( `TestReport'::`2'::s_pfnTestReport )
    goto LABEL_41;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestReport");
  `TestReport'::`2'::s_pfnTestReport = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_41:
    ((void (__fastcall *)(_OWORD *, __int64))ProcAddress)(v23, v15);
  v21 = *(void (__fastcall ****)(_QWORD))a1;
  if ( tip2::details::g_test_interface_exception_guard )
  {
    if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v21, 0, 0, 0, v23) )
    {
      WORD5(v23[2]) = 16398;
      BYTE8(v23[2]) = 3;
      TestReport(v23);
    }
  }
  else
  {
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD), _OWORD *))(*v21)[3])(v21, v23);
  }
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x1800112a0  mov     [rsp-8+arg_10], rbx
0x1800112a5  push    rbp
0x1800112a6  push    rsi
0x1800112a7  push    rdi
0x1800112a8  push    r12
0x1800112aa  push    r13
0x1800112ac  push    r14
0x1800112ae  push    r15
0x1800112b0  lea     rbp, [rsp-7F0h]
0x1800112b8  sub     rsp, 8F0h
0x1800112bf  mov     rax, cs:__security_cookie
0x1800112c6  xor     rax, rsp
0x1800112c9  mov     [rbp+820h+var_40], rax
0x1800112d0  mov     r13, rdx
0x1800112d3  mov     rbx, rcx
0x1800112d6  add     rcx, 8; this
0x1800112da  xor     r14d, r14d
0x1800112dd  cmp     [rcx+98h], r14b
0x1800112e4  jnz     short loc_18001134F
0x1800112e6  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x1800112ea  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x1800112ee  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x1800112f2  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1800112f7  test    al, al
0x1800112f9  jz      short loc_18001134F
0x1800112fb  mov     rcx, [rbx]
0x1800112fe  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180011305  test    rax, rax
0x180011308  jz      short loc_180011342
0x18001130a  mov     [rsp+920h+var_900], r14
0x18001130f  xor     r9d, r9d
0x180011312  xor     r8d, r8d
0x180011315  xor     edx, edx
0x180011317  call    cs:__guard_dispatch_icall_fptr
0x18001131d  test    al, al
0x18001131f  jnz     short loc_18001134F
0x180011321  cmp     [rbx+0A0h], al
0x180011327  jnz     short loc_18001134F
0x180011329  mov     byte ptr [rbx+0A0h], 3
0x180011330  mov     word ptr [rbx+0A2h], 400Bh
0x180011339  mov     [rbx+0A8h], r14
0x180011340  jmp     short loc_18001134F
0x180011342  mov     rax, [rcx]
0x180011345  mov     rax, [rax]
0x180011348  call    cs:__guard_dispatch_icall_fptr
0x18001134e  nop
0x18001134f  movzx   eax, byte ptr [rbx+0A0h]
0x180011356  test    al, al
0x180011358  jnz     short loc_180011373
0x18001135a  mov     byte ptr [rbx+0A0h], 3
0x180011361  mov     word ptr [rbx+0A2h], 400Ah
0x18001136a  mov     [rbx+0A8h], r14
0x180011371  jmp     short loc_180011388
0x180011373  cmp     al, 2
0x180011375  jz      short loc_180011388
0x180011377  cmp     al, 3
0x180011379  jz      short loc_180011388
0x18001137b  test    dword ptr [rbx+14h], 1000h
0x180011382  jz      short loc_18001139A
0x180011384  cmp     al, 4
0x180011386  jz      short loc_18001139A
0x180011388  lea     r15, [rbx+40h]
0x18001138c  test    dword ptr [r15], 800h
0x180011393  jz      short loc_18001139A
0x180011395  mov     r12b, 1
0x180011398  jmp     short loc_1800113A1
0x18001139a  xor     r12b, r12b
0x18001139d  lea     r15, [rbx+40h]
0x1800113a1  movzx   eax, r12b
0x1800113a5  mov     esi, eax
0x1800113a7  or      esi, 2
0x1800113aa  test    dword ptr [rbx+14h], 200h
0x1800113b1  cmovz   esi, eax
0x1800113b4  xor     edx, edx; Val
0x1800113b6  mov     r8d, 802h; Size
0x1800113bc  lea     rcx, [rbp+820h+var_862]; void *
0x1800113c0  call    memset
0x1800113c5  mov     [rbp+820h+pv], r14
0x1800113c9  mov     [rbp+820h+var_868], 0
0x1800113cd  lea     rax, [rbp+820h+var_867]
0x1800113d1  mov     [rbp+820h+var_60], rax
0x1800113d8  lea     rax, [rbp+820h+var_67]
0x1800113df  mov     [rbp+820h+var_50], rax
0x1800113e6  mov     [rbp+820h+var_867], 80408040h
0x1800113ed  mov     [rbp+820h+var_863], 0
0x1800113f1  lea     rax, [rbp+820h+var_862]
0x1800113f5  mov     [rbp+820h+var_58], rax
0x1800113fc  movzx   eax, r12b
0x180011400  mov     ecx, 1
0x180011405  test    dword ptr [rbx+14h], 200h
0x18001140c  cmovnz  eax, ecx
0x18001140f  mov     r8d, esi
0x180011412  or      r8d, 4
0x180011416  test    al, al
0x180011418  cmovz   r8d, esi
0x18001141c  lea     rdx, [rbp+820h+pv]
0x180011420  mov     rcx, rbx
0x180011423  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180011428  mov     rdx, rax
0x18001142b  xorps   xmm0, xmm0
0x18001142e  xor     eax, eax
0x180011430  movups  [rsp+920h+var_8F0], xmm0
0x180011435  movups  [rsp+920h+var_8E0], xmm0
0x18001143a  movups  [rsp+920h+var_8D0], xmm0
0x18001143f  movups  [rsp+920h+var_8C0], xmm0
0x180011444  movups  [rsp+920h+var_8B0], xmm0
0x180011449  movups  [rbp+820h+var_8A0], xmm0
0x18001144d  movups  [rbp+820h+var_890], xmm0
0x180011451  mov     [rbp+820h+var_880], rax
0x180011455  mov     ecx, [rbx+0B4h]
0x18001145b  test    ecx, ecx
0x18001145d  jz      short loc_180011465
0x18001145f  mov     dword ptr [rsp+920h+var_8F0], ecx
0x180011463  jmp     short loc_18001146C
0x180011465  mov     eax, [rbx+10h]
0x180011468  mov     dword ptr [rsp+920h+var_8F0], eax
0x18001146c  mov     rax, [rbx+18h]
0x180011470  mov     qword ptr [rsp+920h+var_8F0+8], rax
0x180011475  mov     eax, [rbx+14h]
0x180011478  mov     dword ptr [rsp+920h+var_8E0], eax
0x18001147c  movups  xmm0, xmmword ptr [rbx+90h]
0x180011483  movups  [rsp+920h+var_8E0+4], xmm0
0x180011488  mov     eax, [r15]
0x18001148b  bts     eax, 15h
0x18001148f  mov     dword ptr [rsp+920h+var_8D0+4], eax
0x180011493  movzx   eax, byte ptr [rbx+0A0h]
0x18001149a  mov     byte ptr [rsp+920h+var_8D0+8], al
0x18001149e  movzx   eax, word ptr [rbx+0A2h]
0x1800114a5  mov     word ptr [rsp+920h+var_8D0+0Ah], ax
0x1800114aa  mov     rax, [rbx+0A8h]
0x1800114b1  mov     qword ptr [rsp+920h+var_8C0], rax
0x1800114b6  mov     qword ptr [rsp+920h+var_8C0+8], r13
0x1800114bb  mov     qword ptr [rsp+920h+var_8B0+8], rdx
0x1800114c0  mov     eax, [rbx+0B0h]
0x1800114c6  mov     dword ptr [rbp+820h+var_890+0Ch], eax
0x1800114c9  test    ecx, ecx
0x1800114cb  jz      short loc_1800114D5
0x1800114cd  mov     eax, [rbx+10h]
0x1800114d0  mov     dword ptr [rbp+820h+var_880], eax
0x1800114d3  jmp     short loc_1800114D9
0x1800114d5  mov     dword ptr [rbp+820h+var_880], r14d
0x1800114d9  mov     rdx, r14
0x1800114dc  mov     rcx, [rbx+48h]
0x1800114e0  imul    r8, [rbx+58h], 0A8h
0x1800114e8  add     r8, rcx
0x1800114eb  cmp     rcx, r8
0x1800114ee  jz      short loc_18001152B
0x1800114f0  mov     eax, [rcx+8]
0x1800114f3  cmp     r14d, eax
0x1800114f6  cmovnz  rdx, rcx
0x1800114fa  add     rcx, 0A8h
0x180011501  cmp     r14d, eax
0x180011504  cmovz   eax, r14d
0x180011508  mov     r14d, eax
0x18001150b  cmp     rcx, r8
0x18001150e  jnz     short loc_1800114F0
0x180011510  test    rdx, rdx
0x180011513  jz      short loc_18001152B
0x180011515  mov     eax, [rdx+8]
0x180011518  mov     dword ptr [rbp+820h+var_8A0], eax
0x18001151b  mov     rax, [rdx+38h]
0x18001151f  mov     qword ptr [rbp+820h+var_8A0+8], rax
0x180011523  movzx   eax, word ptr [rdx+40h]
0x180011527  mov     word ptr [rbp+820h+var_890], ax
0x18001152b  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180011532  test    rax, rax
0x180011535  jnz     short loc_180011573
0x180011537  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001153e  test    rax, rax
0x180011541  jnz     short loc_180011557
0x180011543  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001154a  call    cs:__imp_GetModuleHandleW
0x180011550  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180011557  lea     rdx, aTestreport; "TestReport"
0x18001155e  mov     rcx, rax; hModule
0x180011561  call    cs:__imp_GetProcAddress
0x180011567  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18001156e  test    rax, rax
0x180011571  jz      short loc_18001157F
0x180011573  lea     rcx, [rsp+920h+var_8F0]
0x180011578  call    cs:__guard_dispatch_icall_fptr
0x18001157e  nop
0x18001157f  mov     rcx, [rbx]
0x180011582  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180011589  lea     rdx, [rsp+920h+var_8F0]
0x18001158e  test    rax, rax
0x180011591  jz      short loc_1800115C5
0x180011593  mov     [rsp+920h+var_900], rdx
0x180011598  xor     r9d, r9d
0x18001159b  xor     r8d, r8d
0x18001159e  xor     edx, edx
0x1800115a0  call    cs:__guard_dispatch_icall_fptr
0x1800115a6  test    al, al
0x1800115a8  jnz     short loc_1800115D3
0x1800115aa  mov     eax, 400Eh
0x1800115af  mov     word ptr [rsp+920h+var_8D0+0Ah], ax
0x1800115b4  mov     byte ptr [rsp+920h+var_8D0+8], 3
0x1800115b9  lea     rcx, [rsp+920h+var_8F0]
0x1800115be  call    TestReport
0x1800115c3  jmp     short loc_1800115D3
0x1800115c5  mov     rax, [rcx]
0x1800115c8  mov     rax, [rax+18h]
0x1800115cc  call    cs:__guard_dispatch_icall_fptr
0x1800115d2  nop
0x1800115d3  mov     rcx, [rbp+820h+pv]; pv
0x1800115d7  test    rcx, rcx
0x1800115da  jz      short loc_1800115E3
0x1800115dc  call    cs:__imp_CoTaskMemFree
0x1800115e2  nop
0x1800115e3  mov     rcx, [rbp+820h+var_40]
0x1800115ea  xor     rcx, rsp; StackCookie
0x1800115ed  call    __security_check_cookie
0x1800115f2  mov     rbx, [rsp+920h+arg_10]
0x1800115fa  add     rsp, 8F0h
0x180011601  pop     r15
0x180011603  pop     r14
0x180011605  pop     r13
0x180011607  pop     r12
0x180011609  pop     rdi
0x18001160a  pop     rsi
0x18001160b  pop     rbp
0x18001160c  retn
```
