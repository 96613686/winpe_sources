# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x180026754`
- end: `0x180026ad9`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025cb0`

## callees

- `0x1800060a0`
- `0x180006ed4`
- `0x180026754`
- `0x180026ae0`
- `0x180027c5c`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800269f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026a7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800269f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026a7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800269d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026a65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800269d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ab0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ab0`

## string_xrefs

- `0x1800269d2`: `kernelbase.dll`
- `0x180026a5e`: `kernelbase.dll`

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
0x180026754  mov     [rsp-8+arg_10], rbx
0x180026759  push    rbp
0x18002675a  push    rsi
0x18002675b  push    rdi
0x18002675c  lea     rbp, [rsp-7F0h]
0x180026764  sub     rsp, 8F0h
0x18002676b  mov     rax, cs:__security_cookie
0x180026772  xor     rax, rsp
0x180026775  mov     [rbp+800h+var_20], rax
0x18002677c  mov     rdi, rdx
0x18002677f  mov     rbx, rcx
0x180026782  add     rcx, 8; this
0x180026786  cmp     byte ptr [rcx+98h], 0
0x18002678d  jnz     short loc_1800267FE
0x18002678f  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x180026793  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x180026797  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x18002679b  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1800267a0  test    al, al
0x1800267a2  jz      short loc_1800267FE
0x1800267a4  mov     rcx, [rbx]
0x1800267a7  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800267ae  test    rax, rax
0x1800267b1  jz      short loc_1800267F2
0x1800267b3  mov     [rsp+900h+var_8E0], 0
0x1800267bc  xor     r9d, r9d
0x1800267bf  xor     r8d, r8d
0x1800267c2  xor     edx, edx
0x1800267c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267c9  test    al, al
0x1800267cb  jnz     short loc_1800267FE
0x1800267cd  cmp     [rbx+0A0h], al
0x1800267d3  jnz     short loc_1800267FE
0x1800267d5  mov     byte ptr [rbx+0A0h], 3
0x1800267dc  mov     word ptr [rbx+0A2h], 400Bh
0x1800267e5  mov     qword ptr [rbx+0A8h], 0
0x1800267f0  jmp     short loc_1800267FE
0x1800267f2  mov     rax, [rcx]
0x1800267f5  mov     rax, [rax]
0x1800267f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267fd  nop
0x1800267fe  mov     cl, [rbx+0A0h]
0x180026804  cmp     cl, 5
0x180026807  jz      loc_180026AB7
0x18002680d  mov     r9d, 1
0x180026813  test    cl, cl
0x180026815  jnz     short loc_180026834
0x180026817  mov     byte ptr [rbx+0A0h], 3
0x18002681e  mov     word ptr [rbx+0A2h], 400Ah
0x180026827  mov     qword ptr [rbx+0A8h], 0
0x180026832  jmp     short loc_18002684A
0x180026834  lea     eax, [rcx-2]
0x180026837  cmp     al, r9b
0x18002683a  jbe     short loc_18002684A
0x18002683c  test    dword ptr [rbx+14h], 1000h
0x180026843  jz      short loc_180026858
0x180026845  cmp     cl, 4
0x180026848  jz      short loc_180026858
0x18002684a  test    dword ptr [rbx+40h], 800h
0x180026851  jz      short loc_180026858
0x180026853  mov     r8b, r9b
0x180026856  jmp     short loc_18002685B
0x180026858  xor     r8b, r8b
0x18002685b  movzx   eax, r8b
0x18002685f  mov     edx, eax
0x180026861  or      edx, 2
0x180026864  test    dword ptr [rbx+14h], 200h
0x18002686b  cmovz   edx, eax
0x18002686e  mov     [rbp+800h+pv], 0
0x180026876  mov     [rbp+800h+var_848], 0
0x18002687a  lea     rax, [rbp+800h+var_847]
0x18002687e  mov     [rbp+800h+var_40], rax
0x180026885  lea     rax, [rbp+800h+var_47]
0x18002688c  mov     [rbp+800h+var_30], rax
0x180026893  mov     [rbp+800h+var_847], 80408040h
0x18002689a  mov     [rbp+800h+var_843], 0
0x18002689e  lea     rax, [rbp+800h+var_842]
0x1800268a2  mov     [rbp+800h+var_38], rax
0x1800268a9  movzx   eax, r8b
0x1800268ad  cmovnz  eax, r9d
0x1800268b1  mov     r8d, edx
0x1800268b4  or      r8d, 4
0x1800268b8  test    al, al
0x1800268ba  cmovz   r8d, edx
0x1800268be  lea     rdx, [rbp+800h+pv]
0x1800268c2  mov     rcx, rbx
0x1800268c5  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800268ca  mov     rsi, rax
0x1800268cd  xor     edx, edx; Val
0x1800268cf  lea     r8d, [rdx+78h]; Size
0x1800268d3  lea     rcx, [rsp+900h+var_8D0]; void *
0x1800268d8  call    memset_0
0x1800268dd  mov     edx, [rbx+0B4h]
0x1800268e3  lea     rcx, [rbx+10h]
0x1800268e7  test    edx, edx
0x1800268e9  jz      short loc_1800268F1
0x1800268eb  mov     [rsp+900h+var_8D0], edx
0x1800268ef  jmp     short loc_1800268F7
0x1800268f1  mov     eax, [rcx]
0x1800268f3  mov     [rsp+900h+var_8D0], eax
0x1800268f7  mov     rax, [rbx+18h]
0x1800268fb  mov     [rsp+900h+var_8C8], rax
0x180026900  mov     eax, [rbx+14h]
0x180026903  mov     [rsp+900h+var_8C0], eax
0x180026907  movups  xmm0, xmmword ptr [rbx+90h]
0x18002690e  movdqu  [rsp+900h+var_8BC], xmm0
0x180026914  mov     eax, [rbx+40h]
0x180026917  bts     eax, 15h
0x18002691b  mov     [rsp+900h+var_8AC], eax
0x18002691f  mov     al, [rbx+0A0h]
0x180026925  mov     [rsp+900h+var_8A8], al
0x180026929  movzx   eax, word ptr [rbx+0A2h]
0x180026930  mov     [rsp+900h+var_8A6], ax
0x180026935  mov     rax, [rbx+0A8h]
0x18002693c  mov     [rsp+900h+var_8A0], rax
0x180026941  mov     [rsp+900h+var_898], rdi
0x180026946  mov     [rsp+900h+var_888], rsi
0x18002694b  mov     eax, [rbx+0B0h]
0x180026951  mov     [rbp+800h+var_864], eax
0x180026954  test    edx, edx
0x180026956  jz      short loc_18002695F
0x180026958  mov     eax, [rcx]
0x18002695a  mov     [rbp+800h+var_860], eax
0x18002695d  jmp     short loc_180026966
0x18002695f  mov     [rbp+800h+var_860], 0
0x180026966  xor     r9d, r9d
0x180026969  xor     ecx, ecx
0x18002696b  mov     rdx, [rbx+48h]
0x18002696f  imul    r8, [rbx+58h], 0A8h
0x180026977  add     r8, rdx
0x18002697a  cmp     rdx, r8
0x18002697d  jz      short loc_1800269BA
0x18002697f  mov     eax, [rdx+8]
0x180026982  cmp     r9d, eax
0x180026985  cmovnz  rcx, rdx
0x180026989  add     rdx, 0A8h
0x180026990  cmp     r9d, eax
0x180026993  cmovz   eax, r9d
0x180026997  mov     r9d, eax
0x18002699a  cmp     rdx, r8
0x18002699d  jnz     short loc_18002697F
0x18002699f  test    rcx, rcx
0x1800269a2  jz      short loc_1800269BA
0x1800269a4  mov     eax, [rcx+8]
0x1800269a7  mov     [rbp+800h+var_880], eax
0x1800269aa  mov     rax, [rcx+38h]
0x1800269ae  mov     [rbp+800h+var_878], rax
0x1800269b2  movzx   eax, word ptr [rcx+40h]
0x1800269b6  mov     [rbp+800h+var_870], ax
0x1800269ba  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800269c1  test    rax, rax
0x1800269c4  jnz     short loc_180026A02
0x1800269c6  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800269cd  test    rax, rax
0x1800269d0  jnz     short loc_1800269E6
0x1800269d2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800269d9  call    cs:__imp_GetModuleHandleW
0x1800269df  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800269e6  lea     rdx, aTestreport; "TestReport"
0x1800269ed  mov     rcx, rax; hModule
0x1800269f0  call    cs:__imp_GetProcAddress
0x1800269f6  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800269fd  test    rax, rax
0x180026a00  jz      short loc_180026A0D
0x180026a02  lea     rcx, [rsp+900h+var_8D0]
0x180026a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a0c  nop
0x180026a0d  mov     rcx, [rbx]
0x180026a10  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180026a17  lea     rdx, [rsp+900h+var_8D0]
0x180026a1c  test    rax, rax
0x180026a1f  jz      short loc_180026A9A
0x180026a21  mov     [rsp+900h+var_8E0], rdx
0x180026a26  xor     r9d, r9d
0x180026a29  xor     r8d, r8d
0x180026a2c  xor     edx, edx
0x180026a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a33  test    al, al
0x180026a35  jnz     short loc_180026AA7
0x180026a37  mov     eax, 400Eh
0x180026a3c  mov     [rsp+900h+var_8A6], ax
0x180026a41  mov     [rsp+900h+var_8A8], 3
0x180026a46  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180026a4d  test    rax, rax
0x180026a50  jnz     short loc_180026A8E
0x180026a52  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180026a59  test    rax, rax
0x180026a5c  jnz     short loc_180026A72
0x180026a5e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026a65  call    cs:__imp_GetModuleHandleW
0x180026a6b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180026a72  lea     rdx, aTestreport; "TestReport"
0x180026a79  mov     rcx, rax; hModule
0x180026a7c  call    cs:__imp_GetProcAddress
0x180026a82  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180026a89  test    rax, rax
0x180026a8c  jz      short loc_180026AA7
0x180026a8e  lea     rcx, [rsp+900h+var_8D0]
0x180026a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a98  jmp     short loc_180026AA7
0x180026a9a  mov     rax, [rcx]
0x180026a9d  mov     rax, [rax+18h]
0x180026aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aa6  nop
0x180026aa7  mov     rcx, [rbp+800h+pv]; pv
0x180026aab  test    rcx, rcx
0x180026aae  jz      short loc_180026AB7
0x180026ab0  call    cs:__imp_CoTaskMemFree
0x180026ab6  nop
0x180026ab7  mov     rcx, [rbp+800h+var_20]
0x180026abe  xor     rcx, rsp; StackCookie
0x180026ac1  call    __security_check_cookie
0x180026ac6  mov     rbx, [rsp+900h+arg_10]
0x180026ace  add     rsp, 8F0h
0x180026ad5  pop     rdi
0x180026ad6  pop     rsi
0x180026ad7  pop     rbp
0x180026ad8  retn
```
