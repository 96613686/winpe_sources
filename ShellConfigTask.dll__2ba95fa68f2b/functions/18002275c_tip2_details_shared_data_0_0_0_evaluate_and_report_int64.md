# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x18002275c`
- end: `0x180022ae1`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002189c`

## callees

- `0x180002590`
- `0x180002f98`
- `0x18002275c`
- `0x180022ae8`
- `0x1800245dc`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800229e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022a6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800229e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022a6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800229f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022a84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800229f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022a84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ab8`

## string_xrefs

- `0x1800229da`: `kernelbase.dll`
- `0x180022a66`: `kernelbase.dll`

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
0x18002275c  mov     [rsp-8+arg_10], rbx
0x180022761  push    rbp
0x180022762  push    rsi
0x180022763  push    rdi
0x180022764  lea     rbp, [rsp-7F0h]
0x18002276c  sub     rsp, 8F0h
0x180022773  mov     rax, cs:__security_cookie
0x18002277a  xor     rax, rsp
0x18002277d  mov     [rbp+800h+var_20], rax
0x180022784  mov     rdi, rdx
0x180022787  mov     rbx, rcx
0x18002278a  add     rcx, 8; this
0x18002278e  cmp     byte ptr [rcx+98h], 0
0x180022795  jnz     short loc_180022806
0x180022797  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18002279b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18002279f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x1800227a3  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1800227a8  test    al, al
0x1800227aa  jz      short loc_180022806
0x1800227ac  mov     rcx, [rbx]
0x1800227af  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800227b6  test    rax, rax
0x1800227b9  jz      short loc_1800227FA
0x1800227bb  mov     [rsp+900h+var_8E0], 0
0x1800227c4  xor     r9d, r9d
0x1800227c7  xor     r8d, r8d
0x1800227ca  xor     edx, edx
0x1800227cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227d1  test    al, al
0x1800227d3  jnz     short loc_180022806
0x1800227d5  cmp     [rbx+0A0h], al
0x1800227db  jnz     short loc_180022806
0x1800227dd  mov     byte ptr [rbx+0A0h], 3
0x1800227e4  mov     word ptr [rbx+0A2h], 400Bh
0x1800227ed  mov     qword ptr [rbx+0A8h], 0
0x1800227f8  jmp     short loc_180022806
0x1800227fa  mov     rax, [rcx]
0x1800227fd  mov     rax, [rax]
0x180022800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022805  nop
0x180022806  mov     cl, [rbx+0A0h]
0x18002280c  cmp     cl, 5
0x18002280f  jz      loc_180022ABF
0x180022815  mov     r9d, 1
0x18002281b  test    cl, cl
0x18002281d  jnz     short loc_18002283C
0x18002281f  mov     byte ptr [rbx+0A0h], 3
0x180022826  mov     word ptr [rbx+0A2h], 400Ah
0x18002282f  mov     qword ptr [rbx+0A8h], 0
0x18002283a  jmp     short loc_180022852
0x18002283c  lea     eax, [rcx-2]
0x18002283f  cmp     al, r9b
0x180022842  jbe     short loc_180022852
0x180022844  test    dword ptr [rbx+14h], 1000h
0x18002284b  jz      short loc_180022860
0x18002284d  cmp     cl, 4
0x180022850  jz      short loc_180022860
0x180022852  test    dword ptr [rbx+40h], 800h
0x180022859  jz      short loc_180022860
0x18002285b  mov     r8b, r9b
0x18002285e  jmp     short loc_180022863
0x180022860  xor     r8b, r8b
0x180022863  movzx   eax, r8b
0x180022867  mov     edx, eax
0x180022869  or      edx, 2
0x18002286c  test    dword ptr [rbx+14h], 200h
0x180022873  cmovz   edx, eax
0x180022876  mov     [rbp+800h+pv], 0
0x18002287e  mov     [rbp+800h+var_848], 0
0x180022882  lea     rax, [rbp+800h+var_847]
0x180022886  mov     [rbp+800h+var_40], rax
0x18002288d  lea     rax, [rbp+800h+var_47]
0x180022894  mov     [rbp+800h+var_30], rax
0x18002289b  mov     [rbp+800h+var_847], 80408040h
0x1800228a2  mov     [rbp+800h+var_843], 0
0x1800228a6  lea     rax, [rbp+800h+var_842]
0x1800228aa  mov     [rbp+800h+var_38], rax
0x1800228b1  movzx   eax, r8b
0x1800228b5  cmovnz  eax, r9d
0x1800228b9  mov     r8d, edx
0x1800228bc  or      r8d, 4
0x1800228c0  test    al, al
0x1800228c2  cmovz   r8d, edx
0x1800228c6  lea     rdx, [rbp+800h+pv]
0x1800228ca  mov     rcx, rbx
0x1800228cd  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800228d2  mov     rsi, rax
0x1800228d5  xor     edx, edx; Val
0x1800228d7  lea     r8d, [rdx+78h]; Size
0x1800228db  lea     rcx, [rsp+900h+var_8D0]; void *
0x1800228e0  call    memset_0
0x1800228e5  mov     edx, [rbx+0B4h]
0x1800228eb  lea     rcx, [rbx+10h]
0x1800228ef  test    edx, edx
0x1800228f1  jz      short loc_1800228F9
0x1800228f3  mov     [rsp+900h+var_8D0], edx
0x1800228f7  jmp     short loc_1800228FF
0x1800228f9  mov     eax, [rcx]
0x1800228fb  mov     [rsp+900h+var_8D0], eax
0x1800228ff  mov     rax, [rbx+18h]
0x180022903  mov     [rsp+900h+var_8C8], rax
0x180022908  mov     eax, [rbx+14h]
0x18002290b  mov     [rsp+900h+var_8C0], eax
0x18002290f  movups  xmm0, xmmword ptr [rbx+90h]
0x180022916  movdqu  [rsp+900h+var_8BC], xmm0
0x18002291c  mov     eax, [rbx+40h]
0x18002291f  bts     eax, 15h
0x180022923  mov     [rsp+900h+var_8AC], eax
0x180022927  mov     al, [rbx+0A0h]
0x18002292d  mov     [rsp+900h+var_8A8], al
0x180022931  movzx   eax, word ptr [rbx+0A2h]
0x180022938  mov     [rsp+900h+var_8A6], ax
0x18002293d  mov     rax, [rbx+0A8h]
0x180022944  mov     [rsp+900h+var_8A0], rax
0x180022949  mov     [rsp+900h+var_898], rdi
0x18002294e  mov     [rsp+900h+var_888], rsi
0x180022953  mov     eax, [rbx+0B0h]
0x180022959  mov     [rbp+800h+var_864], eax
0x18002295c  test    edx, edx
0x18002295e  jz      short loc_180022967
0x180022960  mov     eax, [rcx]
0x180022962  mov     [rbp+800h+var_860], eax
0x180022965  jmp     short loc_18002296E
0x180022967  mov     [rbp+800h+var_860], 0
0x18002296e  xor     r9d, r9d
0x180022971  xor     ecx, ecx
0x180022973  mov     rdx, [rbx+48h]
0x180022977  imul    r8, [rbx+58h], 0A8h
0x18002297f  add     r8, rdx
0x180022982  cmp     rdx, r8
0x180022985  jz      short loc_1800229C2
0x180022987  mov     eax, [rdx+8]
0x18002298a  cmp     r9d, eax
0x18002298d  cmovnz  rcx, rdx
0x180022991  add     rdx, 0A8h
0x180022998  cmp     r9d, eax
0x18002299b  cmovz   eax, r9d
0x18002299f  mov     r9d, eax
0x1800229a2  cmp     rdx, r8
0x1800229a5  jnz     short loc_180022987
0x1800229a7  test    rcx, rcx
0x1800229aa  jz      short loc_1800229C2
0x1800229ac  mov     eax, [rcx+8]
0x1800229af  mov     [rbp+800h+var_880], eax
0x1800229b2  mov     rax, [rcx+38h]
0x1800229b6  mov     [rbp+800h+var_878], rax
0x1800229ba  movzx   eax, word ptr [rcx+40h]
0x1800229be  mov     [rbp+800h+var_870], ax
0x1800229c2  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800229c9  test    rax, rax
0x1800229cc  jnz     short loc_180022A0A
0x1800229ce  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800229d5  test    rax, rax
0x1800229d8  jnz     short loc_1800229EE
0x1800229da  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800229e1  call    cs:__imp_GetModuleHandleW
0x1800229e7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800229ee  lea     rdx, aTestreport; "TestReport"
0x1800229f5  mov     rcx, rax; hModule
0x1800229f8  call    cs:__imp_GetProcAddress
0x1800229fe  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180022a05  test    rax, rax
0x180022a08  jz      short loc_180022A15
0x180022a0a  lea     rcx, [rsp+900h+var_8D0]
0x180022a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a14  nop
0x180022a15  mov     rcx, [rbx]
0x180022a18  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180022a1f  lea     rdx, [rsp+900h+var_8D0]
0x180022a24  test    rax, rax
0x180022a27  jz      short loc_180022AA2
0x180022a29  mov     [rsp+900h+var_8E0], rdx
0x180022a2e  xor     r9d, r9d
0x180022a31  xor     r8d, r8d
0x180022a34  xor     edx, edx
0x180022a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a3b  test    al, al
0x180022a3d  jnz     short loc_180022AAF
0x180022a3f  mov     eax, 400Eh
0x180022a44  mov     [rsp+900h+var_8A6], ax
0x180022a49  mov     [rsp+900h+var_8A8], 3
0x180022a4e  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180022a55  test    rax, rax
0x180022a58  jnz     short loc_180022A96
0x180022a5a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180022a61  test    rax, rax
0x180022a64  jnz     short loc_180022A7A
0x180022a66  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180022a6d  call    cs:__imp_GetModuleHandleW
0x180022a73  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180022a7a  lea     rdx, aTestreport; "TestReport"
0x180022a81  mov     rcx, rax; hModule
0x180022a84  call    cs:__imp_GetProcAddress
0x180022a8a  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180022a91  test    rax, rax
0x180022a94  jz      short loc_180022AAF
0x180022a96  lea     rcx, [rsp+900h+var_8D0]
0x180022a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aa0  jmp     short loc_180022AAF
0x180022aa2  mov     rax, [rcx]
0x180022aa5  mov     rax, [rax+18h]
0x180022aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aae  nop
0x180022aaf  mov     rcx, [rbp+800h+pv]; pv
0x180022ab3  test    rcx, rcx
0x180022ab6  jz      short loc_180022ABF
0x180022ab8  call    cs:__imp_CoTaskMemFree
0x180022abe  nop
0x180022abf  mov     rcx, [rbp+800h+var_20]
0x180022ac6  xor     rcx, rsp; StackCookie
0x180022ac9  call    __security_check_cookie
0x180022ace  mov     rbx, [rsp+900h+arg_10]
0x180022ad6  add     rsp, 8F0h
0x180022add  pop     rdi
0x180022ade  pop     rsi
0x180022adf  pop     rbp
0x180022ae0  retn
```
