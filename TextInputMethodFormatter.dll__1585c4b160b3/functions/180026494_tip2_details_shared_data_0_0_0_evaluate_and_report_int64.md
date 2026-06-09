# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x180026494`
- end: `0x180026819`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180026128`

## callees

- `0x180002240`
- `0x180002db8`
- `0x180026494`
- `0x180026820`
- `0x180027e30`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026730`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800267bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026730`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800267bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026719`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800267a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026719`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800267a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800267f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800267f0`

## string_xrefs

- `0x180026712`: `kernelbase.dll`
- `0x18002679e`: `kernelbase.dll`

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
0x180026494  mov     [rsp-8+arg_10], rbx
0x180026499  push    rbp
0x18002649a  push    rsi
0x18002649b  push    rdi
0x18002649c  lea     rbp, [rsp-7F0h]
0x1800264a4  sub     rsp, 8F0h
0x1800264ab  mov     rax, cs:__security_cookie
0x1800264b2  xor     rax, rsp
0x1800264b5  mov     [rbp+800h+var_20], rax
0x1800264bc  mov     rdi, rdx
0x1800264bf  mov     rbx, rcx
0x1800264c2  add     rcx, 8; this
0x1800264c6  cmp     byte ptr [rcx+98h], 0
0x1800264cd  jnz     short loc_18002653E
0x1800264cf  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x1800264d3  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x1800264d7  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x1800264db  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1800264e0  test    al, al
0x1800264e2  jz      short loc_18002653E
0x1800264e4  mov     rcx, [rbx]
0x1800264e7  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800264ee  test    rax, rax
0x1800264f1  jz      short loc_180026532
0x1800264f3  mov     [rsp+900h+var_8E0], 0
0x1800264fc  xor     r9d, r9d
0x1800264ff  xor     r8d, r8d
0x180026502  xor     edx, edx
0x180026504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026509  test    al, al
0x18002650b  jnz     short loc_18002653E
0x18002650d  cmp     [rbx+0A0h], al
0x180026513  jnz     short loc_18002653E
0x180026515  mov     byte ptr [rbx+0A0h], 3
0x18002651c  mov     word ptr [rbx+0A2h], 400Bh
0x180026525  mov     qword ptr [rbx+0A8h], 0
0x180026530  jmp     short loc_18002653E
0x180026532  mov     rax, [rcx]
0x180026535  mov     rax, [rax]
0x180026538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002653d  nop
0x18002653e  mov     cl, [rbx+0A0h]
0x180026544  cmp     cl, 5
0x180026547  jz      loc_1800267F7
0x18002654d  mov     r9d, 1
0x180026553  test    cl, cl
0x180026555  jnz     short loc_180026574
0x180026557  mov     byte ptr [rbx+0A0h], 3
0x18002655e  mov     word ptr [rbx+0A2h], 400Ah
0x180026567  mov     qword ptr [rbx+0A8h], 0
0x180026572  jmp     short loc_18002658A
0x180026574  lea     eax, [rcx-2]
0x180026577  cmp     al, r9b
0x18002657a  jbe     short loc_18002658A
0x18002657c  test    dword ptr [rbx+14h], 1000h
0x180026583  jz      short loc_180026598
0x180026585  cmp     cl, 4
0x180026588  jz      short loc_180026598
0x18002658a  test    dword ptr [rbx+40h], 800h
0x180026591  jz      short loc_180026598
0x180026593  mov     r8b, r9b
0x180026596  jmp     short loc_18002659B
0x180026598  xor     r8b, r8b
0x18002659b  movzx   eax, r8b
0x18002659f  mov     edx, eax
0x1800265a1  or      edx, 2
0x1800265a4  test    dword ptr [rbx+14h], 200h
0x1800265ab  cmovz   edx, eax
0x1800265ae  mov     [rbp+800h+pv], 0
0x1800265b6  mov     [rbp+800h+var_848], 0
0x1800265ba  lea     rax, [rbp+800h+var_847]
0x1800265be  mov     [rbp+800h+var_40], rax
0x1800265c5  lea     rax, [rbp+800h+var_47]
0x1800265cc  mov     [rbp+800h+var_30], rax
0x1800265d3  mov     [rbp+800h+var_847], 80408040h
0x1800265da  mov     [rbp+800h+var_843], 0
0x1800265de  lea     rax, [rbp+800h+var_842]
0x1800265e2  mov     [rbp+800h+var_38], rax
0x1800265e9  movzx   eax, r8b
0x1800265ed  cmovnz  eax, r9d
0x1800265f1  mov     r8d, edx
0x1800265f4  or      r8d, 4
0x1800265f8  test    al, al
0x1800265fa  cmovz   r8d, edx
0x1800265fe  lea     rdx, [rbp+800h+pv]
0x180026602  mov     rcx, rbx
0x180026605  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002660a  mov     rsi, rax
0x18002660d  xor     edx, edx; Val
0x18002660f  lea     r8d, [rdx+78h]; Size
0x180026613  lea     rcx, [rsp+900h+var_8D0]; void *
0x180026618  call    memset_0
0x18002661d  mov     edx, [rbx+0B4h]
0x180026623  lea     rcx, [rbx+10h]
0x180026627  test    edx, edx
0x180026629  jz      short loc_180026631
0x18002662b  mov     [rsp+900h+var_8D0], edx
0x18002662f  jmp     short loc_180026637
0x180026631  mov     eax, [rcx]
0x180026633  mov     [rsp+900h+var_8D0], eax
0x180026637  mov     rax, [rbx+18h]
0x18002663b  mov     [rsp+900h+var_8C8], rax
0x180026640  mov     eax, [rbx+14h]
0x180026643  mov     [rsp+900h+var_8C0], eax
0x180026647  movups  xmm0, xmmword ptr [rbx+90h]
0x18002664e  movdqu  [rsp+900h+var_8BC], xmm0
0x180026654  mov     eax, [rbx+40h]
0x180026657  bts     eax, 15h
0x18002665b  mov     [rsp+900h+var_8AC], eax
0x18002665f  mov     al, [rbx+0A0h]
0x180026665  mov     [rsp+900h+var_8A8], al
0x180026669  movzx   eax, word ptr [rbx+0A2h]
0x180026670  mov     [rsp+900h+var_8A6], ax
0x180026675  mov     rax, [rbx+0A8h]
0x18002667c  mov     [rsp+900h+var_8A0], rax
0x180026681  mov     [rsp+900h+var_898], rdi
0x180026686  mov     [rsp+900h+var_888], rsi
0x18002668b  mov     eax, [rbx+0B0h]
0x180026691  mov     [rbp+800h+var_864], eax
0x180026694  test    edx, edx
0x180026696  jz      short loc_18002669F
0x180026698  mov     eax, [rcx]
0x18002669a  mov     [rbp+800h+var_860], eax
0x18002669d  jmp     short loc_1800266A6
0x18002669f  mov     [rbp+800h+var_860], 0
0x1800266a6  xor     r9d, r9d
0x1800266a9  xor     ecx, ecx
0x1800266ab  mov     rdx, [rbx+48h]
0x1800266af  imul    r8, [rbx+58h], 0A8h
0x1800266b7  add     r8, rdx
0x1800266ba  cmp     rdx, r8
0x1800266bd  jz      short loc_1800266FA
0x1800266bf  mov     eax, [rdx+8]
0x1800266c2  cmp     r9d, eax
0x1800266c5  cmovnz  rcx, rdx
0x1800266c9  add     rdx, 0A8h
0x1800266d0  cmp     r9d, eax
0x1800266d3  cmovz   eax, r9d
0x1800266d7  mov     r9d, eax
0x1800266da  cmp     rdx, r8
0x1800266dd  jnz     short loc_1800266BF
0x1800266df  test    rcx, rcx
0x1800266e2  jz      short loc_1800266FA
0x1800266e4  mov     eax, [rcx+8]
0x1800266e7  mov     [rbp+800h+var_880], eax
0x1800266ea  mov     rax, [rcx+38h]
0x1800266ee  mov     [rbp+800h+var_878], rax
0x1800266f2  movzx   eax, word ptr [rcx+40h]
0x1800266f6  mov     [rbp+800h+var_870], ax
0x1800266fa  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180026701  test    rax, rax
0x180026704  jnz     short loc_180026742
0x180026706  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18002670d  test    rax, rax
0x180026710  jnz     short loc_180026726
0x180026712  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026719  call    cs:__imp_GetModuleHandleW
0x18002671f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180026726  lea     rdx, aTestreport; "TestReport"
0x18002672d  mov     rcx, rax; hModule
0x180026730  call    cs:__imp_GetProcAddress
0x180026736  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18002673d  test    rax, rax
0x180026740  jz      short loc_18002674D
0x180026742  lea     rcx, [rsp+900h+var_8D0]
0x180026747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002674c  nop
0x18002674d  mov     rcx, [rbx]
0x180026750  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180026757  lea     rdx, [rsp+900h+var_8D0]
0x18002675c  test    rax, rax
0x18002675f  jz      short loc_1800267DA
0x180026761  mov     [rsp+900h+var_8E0], rdx
0x180026766  xor     r9d, r9d
0x180026769  xor     r8d, r8d
0x18002676c  xor     edx, edx
0x18002676e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026773  test    al, al
0x180026775  jnz     short loc_1800267E7
0x180026777  mov     eax, 400Eh
0x18002677c  mov     [rsp+900h+var_8A6], ax
0x180026781  mov     [rsp+900h+var_8A8], 3
0x180026786  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18002678d  test    rax, rax
0x180026790  jnz     short loc_1800267CE
0x180026792  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180026799  test    rax, rax
0x18002679c  jnz     short loc_1800267B2
0x18002679e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800267a5  call    cs:__imp_GetModuleHandleW
0x1800267ab  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800267b2  lea     rdx, aTestreport; "TestReport"
0x1800267b9  mov     rcx, rax; hModule
0x1800267bc  call    cs:__imp_GetProcAddress
0x1800267c2  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800267c9  test    rax, rax
0x1800267cc  jz      short loc_1800267E7
0x1800267ce  lea     rcx, [rsp+900h+var_8D0]
0x1800267d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267d8  jmp     short loc_1800267E7
0x1800267da  mov     rax, [rcx]
0x1800267dd  mov     rax, [rax+18h]
0x1800267e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267e6  nop
0x1800267e7  mov     rcx, [rbp+800h+pv]; pv
0x1800267eb  test    rcx, rcx
0x1800267ee  jz      short loc_1800267F7
0x1800267f0  call    cs:__imp_CoTaskMemFree
0x1800267f6  nop
0x1800267f7  mov     rcx, [rbp+800h+var_20]
0x1800267fe  xor     rcx, rsp; StackCookie
0x180026801  call    __security_check_cookie
0x180026806  mov     rbx, [rsp+900h+arg_10]
0x18002680e  add     rsp, 8F0h
0x180026815  pop     rdi
0x180026816  pop     rsi
0x180026817  pop     rbp
0x180026818  retn
```
