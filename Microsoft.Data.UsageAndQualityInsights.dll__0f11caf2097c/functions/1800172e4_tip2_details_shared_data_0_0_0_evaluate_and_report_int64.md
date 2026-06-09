# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x1800172e4`
- end: `0x180017669`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180016dcc`

## callees

- `0x1800033d0`
- `0x180003fb8`
- `0x1800172e4`
- `0x180017670`
- `0x180018ba0`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017569`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800175f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017569`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800175f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001760c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001760c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017640`

## string_xrefs

- `0x180017562`: `kernelbase.dll`
- `0x1800175ee`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
{
  tip2::details *v4; // rcx
  void (__fastcall ***v5)(_QWORD); // rcx
  char v6; // cl
  unsigned __int8 v7; // r8
  unsigned int v8; // edx
  bool v9; // zf
  char v10; // al
  __int64 v11; // r8
  __int64 v12; // rsi
  int v13; // edx
  int *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void (__fastcall ***v22)(_QWORD); // rcx
  FARPROC v23; // rax
  HMODULE v24; // rax
  const struct tip2::test_requirement *v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+40h] [rbp-C0h]
  __int128 v29; // [rsp+44h] [rbp-BCh]
  int v30; // [rsp+54h] [rbp-ACh]
  char v31; // [rsp+58h] [rbp-A8h]
  __int16 v32; // [rsp+5Ah] [rbp-A6h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int16 v38; // [rsp+90h] [rbp-70h]
  int v39; // [rsp+9Ch] [rbp-64h]
  int v40; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+B9h] [rbp-47h] BYREF
  char v44; // [rsp+BDh] [rbp-43h]
  char v45; // [rsp+BEh] [rbp-42h] BYREF
  char v46; // [rsp+8B9h] [rbp+7B9h] BYREF
  int *v47; // [rsp+8C0h] [rbp+7C0h]
  char *v48; // [rsp+8C8h] [rbp+7C8h]
  char *v49; // [rsp+8D0h] [rbp+7D0h]

  v4 = (tip2::details *)(a1 + 8);
  if ( !*((_BYTE *)v4 + 152)
    && tip2::details::evaluate_flags(
         v4,
         *(const struct tip2::test_state **)(a1 + 40),
         *(const struct tip2::test_requirement **)(a1 + 56),
         *(const struct tip2::test_requirement **)(a1 + 48),
         v25) )
  {
    v5 = *(void (__fastcall ****)(_QWORD))a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v5, 0, 0, 0, 0) && !*(_BYTE *)(a1 + 160) )
      {
        *(_BYTE *)(a1 + 160) = 3;
        *(_WORD *)(a1 + 162) = 16395;
        *(_QWORD *)(a1 + 168) = 0;
      }
    }
    else
    {
      (**v5)(v5);
    }
  }
  v6 = *(_BYTE *)(a1 + 160);
  if ( v6 != 5 )
  {
    if ( v6 )
    {
      if ( (unsigned __int8)(v6 - 2) > 1u && ((*(_DWORD *)(a1 + 20) & 0x1000) == 0 || v6 == 4) )
        goto LABEL_16;
    }
    else
    {
      *(_BYTE *)(a1 + 160) = 3;
      *(_WORD *)(a1 + 162) = 16394;
      *(_QWORD *)(a1 + 168) = 0;
    }
    if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    {
      v7 = 1;
LABEL_17:
      v8 = v7 | 2;
      v9 = (*(_DWORD *)(a1 + 20) & 0x200) == 0;
      if ( (*(_DWORD *)(a1 + 20) & 0x200) == 0 )
        v8 = v7;
      pv = 0;
      v42 = 0;
      v47 = &v43;
      v49 = &v46;
      v43 = -2143256512;
      v44 = 0;
      v48 = &v45;
      v10 = v7;
      if ( !v9 )
        v10 = 1;
      v11 = v8 | 4;
      if ( !v10 )
        v11 = v8;
      v12 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, v11);
      memset_0(&v26, 0, 0x78u);
      v13 = *(_DWORD *)(a1 + 180);
      v14 = (int *)(a1 + 16);
      if ( v13 )
        v26 = *(_DWORD *)(a1 + 180);
      else
        v26 = *v14;
      v27 = *(_QWORD *)(a1 + 24);
      v28 = *(_DWORD *)(a1 + 20);
      v29 = *(_OWORD *)(a1 + 144);
      v30 = *(_DWORD *)(a1 + 64) | 0x200000;
      v31 = *(_BYTE *)(a1 + 160);
      v32 = *(_WORD *)(a1 + 162);
      v33 = *(_QWORD *)(a1 + 168);
      v34 = a2;
      v35 = v12;
      v39 = *(_DWORD *)(a1 + 176);
      if ( v13 )
        v40 = *v14;
      else
        v40 = 0;
      v15 = 0;
      v16 = 0;
      v17 = *(_QWORD *)(a1 + 72);
      v18 = v17 + 168LL * *(_QWORD *)(a1 + 88);
      if ( v17 != v18 )
      {
        do
        {
          v19 = *(_DWORD *)(v17 + 8);
          if ( (_DWORD)v15 != v19 )
            v16 = v17;
          v17 += 168;
          if ( (_DWORD)v15 == v19 )
            v19 = v15;
          v15 = v19;
        }
        while ( v17 != v18 );
        if ( v16 )
        {
          v36 = *(_DWORD *)(v16 + 8);
          v37 = *(_QWORD *)(v16 + 56);
          v38 = *(_WORD *)(v16 + 64);
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
        ((void (__fastcall *)(int *, __int64, __int64, __int64))ProcAddress)(&v26, v17, v18, v15);
      v22 = *(void (__fastcall ****)(_QWORD))a1;
      if ( tip2::details::g_test_interface_exception_guard )
      {
        if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v22, 0, 0, 0, &v26) )
        {
          v32 = 16398;
          v31 = 3;
          v23 = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
          if ( `TestReport'::`2'::s_pfnTestReport )
            goto LABEL_48;
          v24 = g_tip_details_kernelbaseModuleHandle;
          if ( !g_tip_details_kernelbaseModuleHandle )
          {
            v24 = GetModuleHandleW(L"kernelbase.dll");
            g_tip_details_kernelbaseModuleHandle = v24;
          }
          v23 = GetProcAddress(v24, "TestReport");
          `TestReport'::`2'::s_pfnTestReport = (__int64)v23;
          if ( v23 )
LABEL_48:
            ((void (__fastcall *)(int *))v23)(&v26);
        }
      }
      else
      {
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD), int *))(*v22)[3])(v22, &v26);
      }
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_16:
    v7 = 0;
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800172e4  mov     [rsp-8+arg_10], rbx
0x1800172e9  push    rbp
0x1800172ea  push    rsi
0x1800172eb  push    rdi
0x1800172ec  lea     rbp, [rsp-7F0h]
0x1800172f4  sub     rsp, 8F0h
0x1800172fb  mov     rax, cs:__security_cookie
0x180017302  xor     rax, rsp
0x180017305  mov     [rbp+800h+var_20], rax
0x18001730c  mov     rdi, rdx
0x18001730f  mov     rbx, rcx
0x180017312  add     rcx, 8; this
0x180017316  cmp     byte ptr [rcx+98h], 0
0x18001731d  jnz     short loc_18001738E
0x18001731f  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x180017323  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x180017327  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x18001732b  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180017330  test    al, al
0x180017332  jz      short loc_18001738E
0x180017334  mov     rcx, [rbx]
0x180017337  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18001733e  test    rax, rax
0x180017341  jz      short loc_180017382
0x180017343  mov     [rsp+900h+var_8E0], 0
0x18001734c  xor     r9d, r9d
0x18001734f  xor     r8d, r8d
0x180017352  xor     edx, edx
0x180017354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017359  test    al, al
0x18001735b  jnz     short loc_18001738E
0x18001735d  cmp     [rbx+0A0h], al
0x180017363  jnz     short loc_18001738E
0x180017365  mov     byte ptr [rbx+0A0h], 3
0x18001736c  mov     word ptr [rbx+0A2h], 400Bh
0x180017375  mov     qword ptr [rbx+0A8h], 0
0x180017380  jmp     short loc_18001738E
0x180017382  mov     rax, [rcx]
0x180017385  mov     rax, [rax]
0x180017388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001738d  nop
0x18001738e  mov     cl, [rbx+0A0h]
0x180017394  cmp     cl, 5
0x180017397  jz      loc_180017647
0x18001739d  mov     r9d, 1
0x1800173a3  test    cl, cl
0x1800173a5  jnz     short loc_1800173C4
0x1800173a7  mov     byte ptr [rbx+0A0h], 3
0x1800173ae  mov     word ptr [rbx+0A2h], 400Ah
0x1800173b7  mov     qword ptr [rbx+0A8h], 0
0x1800173c2  jmp     short loc_1800173DA
0x1800173c4  lea     eax, [rcx-2]
0x1800173c7  cmp     al, r9b
0x1800173ca  jbe     short loc_1800173DA
0x1800173cc  test    dword ptr [rbx+14h], 1000h
0x1800173d3  jz      short loc_1800173E8
0x1800173d5  cmp     cl, 4
0x1800173d8  jz      short loc_1800173E8
0x1800173da  test    dword ptr [rbx+40h], 800h
0x1800173e1  jz      short loc_1800173E8
0x1800173e3  mov     r8b, r9b
0x1800173e6  jmp     short loc_1800173EB
0x1800173e8  xor     r8b, r8b
0x1800173eb  movzx   eax, r8b
0x1800173ef  mov     edx, eax
0x1800173f1  or      edx, 2
0x1800173f4  test    dword ptr [rbx+14h], 200h
0x1800173fb  cmovz   edx, eax
0x1800173fe  mov     [rbp+800h+pv], 0
0x180017406  mov     [rbp+800h+var_848], 0
0x18001740a  lea     rax, [rbp+800h+var_847]
0x18001740e  mov     [rbp+800h+var_40], rax
0x180017415  lea     rax, [rbp+800h+var_47]
0x18001741c  mov     [rbp+800h+var_30], rax
0x180017423  mov     [rbp+800h+var_847], 80408040h
0x18001742a  mov     [rbp+800h+var_843], 0
0x18001742e  lea     rax, [rbp+800h+var_842]
0x180017432  mov     [rbp+800h+var_38], rax
0x180017439  movzx   eax, r8b
0x18001743d  cmovnz  eax, r9d
0x180017441  mov     r8d, edx
0x180017444  or      r8d, 4
0x180017448  test    al, al
0x18001744a  cmovz   r8d, edx
0x18001744e  lea     rdx, [rbp+800h+pv]
0x180017452  mov     rcx, rbx
0x180017455  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18001745a  mov     rsi, rax
0x18001745d  xor     edx, edx; Val
0x18001745f  lea     r8d, [rdx+78h]; Size
0x180017463  lea     rcx, [rsp+900h+var_8D0]; void *
0x180017468  call    memset_0
0x18001746d  mov     edx, [rbx+0B4h]
0x180017473  lea     rcx, [rbx+10h]
0x180017477  test    edx, edx
0x180017479  jz      short loc_180017481
0x18001747b  mov     [rsp+900h+var_8D0], edx
0x18001747f  jmp     short loc_180017487
0x180017481  mov     eax, [rcx]
0x180017483  mov     [rsp+900h+var_8D0], eax
0x180017487  mov     rax, [rbx+18h]
0x18001748b  mov     [rsp+900h+var_8C8], rax
0x180017490  mov     eax, [rbx+14h]
0x180017493  mov     [rsp+900h+var_8C0], eax
0x180017497  movups  xmm0, xmmword ptr [rbx+90h]
0x18001749e  movdqu  [rsp+900h+var_8BC], xmm0
0x1800174a4  mov     eax, [rbx+40h]
0x1800174a7  bts     eax, 15h
0x1800174ab  mov     [rsp+900h+var_8AC], eax
0x1800174af  mov     al, [rbx+0A0h]
0x1800174b5  mov     [rsp+900h+var_8A8], al
0x1800174b9  movzx   eax, word ptr [rbx+0A2h]
0x1800174c0  mov     [rsp+900h+var_8A6], ax
0x1800174c5  mov     rax, [rbx+0A8h]
0x1800174cc  mov     [rsp+900h+var_8A0], rax
0x1800174d1  mov     [rsp+900h+var_898], rdi
0x1800174d6  mov     [rsp+900h+var_888], rsi
0x1800174db  mov     eax, [rbx+0B0h]
0x1800174e1  mov     [rbp+800h+var_864], eax
0x1800174e4  test    edx, edx
0x1800174e6  jz      short loc_1800174EF
0x1800174e8  mov     eax, [rcx]
0x1800174ea  mov     [rbp+800h+var_860], eax
0x1800174ed  jmp     short loc_1800174F6
0x1800174ef  mov     [rbp+800h+var_860], 0
0x1800174f6  xor     r9d, r9d
0x1800174f9  xor     ecx, ecx
0x1800174fb  mov     rdx, [rbx+48h]
0x1800174ff  imul    r8, [rbx+58h], 0A8h
0x180017507  add     r8, rdx
0x18001750a  cmp     rdx, r8
0x18001750d  jz      short loc_18001754A
0x18001750f  mov     eax, [rdx+8]
0x180017512  cmp     r9d, eax
0x180017515  cmovnz  rcx, rdx
0x180017519  add     rdx, 0A8h
0x180017520  cmp     r9d, eax
0x180017523  cmovz   eax, r9d
0x180017527  mov     r9d, eax
0x18001752a  cmp     rdx, r8
0x18001752d  jnz     short loc_18001750F
0x18001752f  test    rcx, rcx
0x180017532  jz      short loc_18001754A
0x180017534  mov     eax, [rcx+8]
0x180017537  mov     [rbp+800h+var_880], eax
0x18001753a  mov     rax, [rcx+38h]
0x18001753e  mov     [rbp+800h+var_878], rax
0x180017542  movzx   eax, word ptr [rcx+40h]
0x180017546  mov     [rbp+800h+var_870], ax
0x18001754a  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180017551  test    rax, rax
0x180017554  jnz     short loc_180017592
0x180017556  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001755d  test    rax, rax
0x180017560  jnz     short loc_180017576
0x180017562  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180017569  call    cs:__imp_GetModuleHandleW
0x18001756f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180017576  lea     rdx, aTestreport; "TestReport"
0x18001757d  mov     rcx, rax; hModule
0x180017580  call    cs:__imp_GetProcAddress
0x180017586  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18001758d  test    rax, rax
0x180017590  jz      short loc_18001759D
0x180017592  lea     rcx, [rsp+900h+var_8D0]
0x180017597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001759c  nop
0x18001759d  mov     rcx, [rbx]
0x1800175a0  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800175a7  lea     rdx, [rsp+900h+var_8D0]
0x1800175ac  test    rax, rax
0x1800175af  jz      short loc_18001762A
0x1800175b1  mov     [rsp+900h+var_8E0], rdx
0x1800175b6  xor     r9d, r9d
0x1800175b9  xor     r8d, r8d
0x1800175bc  xor     edx, edx
0x1800175be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175c3  test    al, al
0x1800175c5  jnz     short loc_180017637
0x1800175c7  mov     eax, 400Eh
0x1800175cc  mov     [rsp+900h+var_8A6], ax
0x1800175d1  mov     [rsp+900h+var_8A8], 3
0x1800175d6  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800175dd  test    rax, rax
0x1800175e0  jnz     short loc_18001761E
0x1800175e2  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800175e9  test    rax, rax
0x1800175ec  jnz     short loc_180017602
0x1800175ee  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800175f5  call    cs:__imp_GetModuleHandleW
0x1800175fb  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180017602  lea     rdx, aTestreport; "TestReport"
0x180017609  mov     rcx, rax; hModule
0x18001760c  call    cs:__imp_GetProcAddress
0x180017612  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180017619  test    rax, rax
0x18001761c  jz      short loc_180017637
0x18001761e  lea     rcx, [rsp+900h+var_8D0]
0x180017623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017628  jmp     short loc_180017637
0x18001762a  mov     rax, [rcx]
0x18001762d  mov     rax, [rax+18h]
0x180017631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017636  nop
0x180017637  mov     rcx, [rbp+800h+pv]; pv
0x18001763b  test    rcx, rcx
0x18001763e  jz      short loc_180017647
0x180017640  call    cs:__imp_CoTaskMemFree
0x180017646  nop
0x180017647  mov     rcx, [rbp+800h+var_20]
0x18001764e  xor     rcx, rsp; StackCookie
0x180017651  call    __security_check_cookie
0x180017656  mov     rbx, [rsp+900h+arg_10]
0x18001765e  add     rsp, 8F0h
0x180017665  pop     rdi
0x180017666  pop     rsi
0x180017667  pop     rbp
0x180017668  retn
```
