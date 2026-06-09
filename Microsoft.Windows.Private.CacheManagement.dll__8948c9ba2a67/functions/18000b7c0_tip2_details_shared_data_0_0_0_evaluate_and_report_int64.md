# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x18000b7c0`
- end: `0x18000bb2d`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `877`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000adb0`

## callees

- `0x18000aec0`
- `0x18000b7c0`
- `0x18000c430`
- `0x18000c4a0`
- `0x1800181b0`
- `0x18001cdf0`
- `0x18001d600`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ba81`
- `KERNEL32!GetProcAddress` at `0x18000ba81`
- `KERNEL32!GetModuleHandleW` at `0x18000ba6a`
- `KERNEL32!GetModuleHandleW` at `0x18000ba6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bafc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bafc`

## string_xrefs

- `0x18000ba63`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000b7c0  mov     [rsp-8+arg_10], rbx
0x18000b7c5  push    rbp
0x18000b7c6  push    rsi
0x18000b7c7  push    rdi
0x18000b7c8  push    r12
0x18000b7ca  push    r13
0x18000b7cc  push    r14
0x18000b7ce  push    r15
0x18000b7d0  lea     rbp, [rsp-7F0h]
0x18000b7d8  sub     rsp, 8F0h
0x18000b7df  mov     rax, cs:__security_cookie
0x18000b7e6  xor     rax, rsp
0x18000b7e9  mov     [rbp+820h+var_40], rax
0x18000b7f0  mov     r13, rdx
0x18000b7f3  mov     rbx, rcx
0x18000b7f6  add     rcx, 8; this
0x18000b7fa  xor     r14d, r14d
0x18000b7fd  cmp     [rcx+98h], r14b
0x18000b804  jnz     short loc_18000B86F
0x18000b806  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18000b80a  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18000b80e  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x18000b812  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x18000b817  test    al, al
0x18000b819  jz      short loc_18000B86F
0x18000b81b  mov     rcx, [rbx]
0x18000b81e  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18000b825  test    rax, rax
0x18000b828  jz      short loc_18000B862
0x18000b82a  mov     [rsp+920h+var_900], r14
0x18000b82f  xor     r9d, r9d
0x18000b832  xor     r8d, r8d
0x18000b835  xor     edx, edx
0x18000b837  call    cs:__guard_dispatch_icall_fptr
0x18000b83d  test    al, al
0x18000b83f  jnz     short loc_18000B86F
0x18000b841  cmp     [rbx+0A0h], al
0x18000b847  jnz     short loc_18000B86F
0x18000b849  mov     byte ptr [rbx+0A0h], 3
0x18000b850  mov     word ptr [rbx+0A2h], 400Bh
0x18000b859  mov     [rbx+0A8h], r14
0x18000b860  jmp     short loc_18000B86F
0x18000b862  mov     rax, [rcx]
0x18000b865  mov     rax, [rax]
0x18000b868  call    cs:__guard_dispatch_icall_fptr
0x18000b86e  nop
0x18000b86f  movzx   eax, byte ptr [rbx+0A0h]
0x18000b876  test    al, al
0x18000b878  jnz     short loc_18000B893
0x18000b87a  mov     byte ptr [rbx+0A0h], 3
0x18000b881  mov     word ptr [rbx+0A2h], 400Ah
0x18000b88a  mov     [rbx+0A8h], r14
0x18000b891  jmp     short loc_18000B8A8
0x18000b893  cmp     al, 2
0x18000b895  jz      short loc_18000B8A8
0x18000b897  cmp     al, 3
0x18000b899  jz      short loc_18000B8A8
0x18000b89b  test    dword ptr [rbx+14h], 1000h
0x18000b8a2  jz      short loc_18000B8BA
0x18000b8a4  cmp     al, 4
0x18000b8a6  jz      short loc_18000B8BA
0x18000b8a8  lea     r15, [rbx+40h]
0x18000b8ac  test    dword ptr [r15], 800h
0x18000b8b3  jz      short loc_18000B8BA
0x18000b8b5  mov     r12b, 1
0x18000b8b8  jmp     short loc_18000B8C1
0x18000b8ba  xor     r12b, r12b
0x18000b8bd  lea     r15, [rbx+40h]
0x18000b8c1  movzx   eax, r12b
0x18000b8c5  mov     esi, eax
0x18000b8c7  or      esi, 2
0x18000b8ca  test    dword ptr [rbx+14h], 200h
0x18000b8d1  cmovz   esi, eax
0x18000b8d4  xor     edx, edx; Val
0x18000b8d6  mov     r8d, 802h; Size
0x18000b8dc  lea     rcx, [rbp+820h+var_862]; void *
0x18000b8e0  call    memset
0x18000b8e5  mov     [rbp+820h+pv], r14
0x18000b8e9  mov     [rbp+820h+var_868], 0
0x18000b8ed  lea     rax, [rbp+820h+var_867]
0x18000b8f1  mov     [rbp+820h+var_60], rax
0x18000b8f8  lea     rax, [rbp+820h+var_67]
0x18000b8ff  mov     [rbp+820h+var_50], rax
0x18000b906  mov     [rbp+820h+var_867], 80408040h
0x18000b90d  mov     [rbp+820h+var_863], 0
0x18000b911  lea     rax, [rbp+820h+var_862]
0x18000b915  mov     [rbp+820h+var_58], rax
0x18000b91c  movzx   eax, r12b
0x18000b920  mov     ecx, 1
0x18000b925  test    dword ptr [rbx+14h], 200h
0x18000b92c  cmovnz  eax, ecx
0x18000b92f  mov     r8d, esi
0x18000b932  or      r8d, 4
0x18000b936  test    al, al
0x18000b938  cmovz   r8d, esi
0x18000b93c  lea     rdx, [rbp+820h+pv]
0x18000b940  mov     rcx, rbx
0x18000b943  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000b948  mov     rdx, rax
0x18000b94b  xorps   xmm0, xmm0
0x18000b94e  xor     eax, eax
0x18000b950  movups  [rsp+920h+var_8F0], xmm0
0x18000b955  movups  [rsp+920h+var_8E0], xmm0
0x18000b95a  movups  [rsp+920h+var_8D0], xmm0
0x18000b95f  movups  [rsp+920h+var_8C0], xmm0
0x18000b964  movups  [rsp+920h+var_8B0], xmm0
0x18000b969  movups  [rbp+820h+var_8A0], xmm0
0x18000b96d  movups  [rbp+820h+var_890], xmm0
0x18000b971  mov     [rbp+820h+var_880], rax
0x18000b975  mov     ecx, [rbx+0B4h]
0x18000b97b  test    ecx, ecx
0x18000b97d  jz      short loc_18000B985
0x18000b97f  mov     dword ptr [rsp+920h+var_8F0], ecx
0x18000b983  jmp     short loc_18000B98C
0x18000b985  mov     eax, [rbx+10h]
0x18000b988  mov     dword ptr [rsp+920h+var_8F0], eax
0x18000b98c  mov     rax, [rbx+18h]
0x18000b990  mov     qword ptr [rsp+920h+var_8F0+8], rax
0x18000b995  mov     eax, [rbx+14h]
0x18000b998  mov     dword ptr [rsp+920h+var_8E0], eax
0x18000b99c  movups  xmm0, xmmword ptr [rbx+90h]
0x18000b9a3  movups  [rsp+920h+var_8E0+4], xmm0
0x18000b9a8  mov     eax, [r15]
0x18000b9ab  bts     eax, 15h
0x18000b9af  mov     dword ptr [rsp+920h+var_8D0+4], eax
0x18000b9b3  movzx   eax, byte ptr [rbx+0A0h]
0x18000b9ba  mov     byte ptr [rsp+920h+var_8D0+8], al
0x18000b9be  movzx   eax, word ptr [rbx+0A2h]
0x18000b9c5  mov     word ptr [rsp+920h+var_8D0+0Ah], ax
0x18000b9ca  mov     rax, [rbx+0A8h]
0x18000b9d1  mov     qword ptr [rsp+920h+var_8C0], rax
0x18000b9d6  mov     qword ptr [rsp+920h+var_8C0+8], r13
0x18000b9db  mov     qword ptr [rsp+920h+var_8B0+8], rdx
0x18000b9e0  mov     eax, [rbx+0B0h]
0x18000b9e6  mov     dword ptr [rbp+820h+var_890+0Ch], eax
0x18000b9e9  test    ecx, ecx
0x18000b9eb  jz      short loc_18000B9F5
0x18000b9ed  mov     eax, [rbx+10h]
0x18000b9f0  mov     dword ptr [rbp+820h+var_880], eax
0x18000b9f3  jmp     short loc_18000B9F9
0x18000b9f5  mov     dword ptr [rbp+820h+var_880], r14d
0x18000b9f9  mov     rdx, r14
0x18000b9fc  mov     rcx, [rbx+48h]
0x18000ba00  imul    r8, [rbx+58h], 0A8h
0x18000ba08  add     r8, rcx
0x18000ba0b  cmp     rcx, r8
0x18000ba0e  jz      short loc_18000BA4B
0x18000ba10  mov     eax, [rcx+8]
0x18000ba13  cmp     r14d, eax
0x18000ba16  cmovnz  rdx, rcx
0x18000ba1a  add     rcx, 0A8h
0x18000ba21  cmp     r14d, eax
0x18000ba24  cmovz   eax, r14d
0x18000ba28  mov     r14d, eax
0x18000ba2b  cmp     rcx, r8
0x18000ba2e  jnz     short loc_18000BA10
0x18000ba30  test    rdx, rdx
0x18000ba33  jz      short loc_18000BA4B
0x18000ba35  mov     eax, [rdx+8]
0x18000ba38  mov     dword ptr [rbp+820h+var_8A0], eax
0x18000ba3b  mov     rax, [rdx+38h]
0x18000ba3f  mov     qword ptr [rbp+820h+var_8A0+8], rax
0x18000ba43  movzx   eax, word ptr [rdx+40h]
0x18000ba47  mov     word ptr [rbp+820h+var_890], ax
0x18000ba4b  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18000ba52  test    rax, rax
0x18000ba55  jnz     short loc_18000BA93
0x18000ba57  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000ba5e  test    rax, rax
0x18000ba61  jnz     short loc_18000BA77
0x18000ba63  lea     rcx, ModuleName; "kernelbase.dll"
0x18000ba6a  call    cs:__imp_GetModuleHandleW
0x18000ba70  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000ba77  lea     rdx, aTestreport; "TestReport"
0x18000ba7e  mov     rcx, rax; hModule
0x18000ba81  call    cs:__imp_GetProcAddress
0x18000ba87  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18000ba8e  test    rax, rax
0x18000ba91  jz      short loc_18000BA9F
0x18000ba93  lea     rcx, [rsp+920h+var_8F0]
0x18000ba98  call    cs:__guard_dispatch_icall_fptr
0x18000ba9e  nop
0x18000ba9f  mov     rcx, [rbx]
0x18000baa2  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18000baa9  lea     rdx, [rsp+920h+var_8F0]
0x18000baae  test    rax, rax
0x18000bab1  jz      short loc_18000BAE5
0x18000bab3  mov     [rsp+920h+var_900], rdx
0x18000bab8  xor     r9d, r9d
0x18000babb  xor     r8d, r8d
0x18000babe  xor     edx, edx
0x18000bac0  call    cs:__guard_dispatch_icall_fptr
0x18000bac6  test    al, al
0x18000bac8  jnz     short loc_18000BAF3
0x18000baca  mov     eax, 400Eh
0x18000bacf  mov     word ptr [rsp+920h+var_8D0+0Ah], ax
0x18000bad4  mov     byte ptr [rsp+920h+var_8D0+8], 3
0x18000bad9  lea     rcx, [rsp+920h+var_8F0]
0x18000bade  call    TestReport
0x18000bae3  jmp     short loc_18000BAF3
0x18000bae5  mov     rax, [rcx]
0x18000bae8  mov     rax, [rax+18h]
0x18000baec  call    cs:__guard_dispatch_icall_fptr
0x18000baf2  nop
0x18000baf3  mov     rcx, [rbp+820h+pv]; pv
0x18000baf7  test    rcx, rcx
0x18000bafa  jz      short loc_18000BB03
0x18000bafc  call    cs:__imp_CoTaskMemFree
0x18000bb02  nop
0x18000bb03  mov     rcx, [rbp+820h+var_40]
0x18000bb0a  xor     rcx, rsp; StackCookie
0x18000bb0d  call    __security_check_cookie
0x18000bb12  mov     rbx, [rsp+920h+arg_10]
0x18000bb1a  add     rsp, 8F0h
0x18000bb21  pop     r15
0x18000bb23  pop     r14
0x18000bb25  pop     r13
0x18000bb27  pop     r12
0x18000bb29  pop     rdi
0x18000bb2a  pop     rsi
0x18000bb2b  pop     rbp
0x18000bb2c  retn
```
