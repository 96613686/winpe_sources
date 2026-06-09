# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x1400569b0`
- end: `0x140056d35`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140056498`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400569b0`
- `0x140056d3c`
- `0x140057c30`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140056c4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140056cd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140056c4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140056cd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140056c35`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140056cc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140056c35`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140056cc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140056d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140056d0c`

## string_xrefs

- `0x140056c2e`: `kernelbase.dll`
- `0x140056cba`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1400569b0  mov     [rsp-8+arg_10], rbx
0x1400569b5  push    rbp
0x1400569b6  push    rsi
0x1400569b7  push    rdi
0x1400569b8  lea     rbp, [rsp-7F0h]
0x1400569c0  sub     rsp, 8F0h
0x1400569c7  mov     rax, cs:__security_cookie
0x1400569ce  xor     rax, rsp
0x1400569d1  mov     [rbp+800h+var_20], rax
0x1400569d8  mov     rdi, rdx
0x1400569db  mov     rbx, rcx
0x1400569de  add     rcx, 8; this
0x1400569e2  cmp     byte ptr [rcx+98h], 0
0x1400569e9  jnz     short loc_140056A5A
0x1400569eb  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x1400569ef  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x1400569f3  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x1400569f7  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1400569fc  test    al, al
0x1400569fe  jz      short loc_140056A5A
0x140056a00  mov     rcx, [rbx]
0x140056a03  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x140056a0a  test    rax, rax
0x140056a0d  jz      short loc_140056A4E
0x140056a0f  mov     [rsp+900h+var_8E0], 0
0x140056a18  xor     r9d, r9d
0x140056a1b  xor     r8d, r8d
0x140056a1e  xor     edx, edx
0x140056a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056a25  test    al, al
0x140056a27  jnz     short loc_140056A5A
0x140056a29  cmp     [rbx+0A0h], al
0x140056a2f  jnz     short loc_140056A5A
0x140056a31  mov     byte ptr [rbx+0A0h], 3
0x140056a38  mov     word ptr [rbx+0A2h], 400Bh
0x140056a41  mov     qword ptr [rbx+0A8h], 0
0x140056a4c  jmp     short loc_140056A5A
0x140056a4e  mov     rax, [rcx]
0x140056a51  mov     rax, [rax]
0x140056a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056a59  nop
0x140056a5a  mov     cl, [rbx+0A0h]
0x140056a60  cmp     cl, 5
0x140056a63  jz      loc_140056D13
0x140056a69  mov     r9d, 1
0x140056a6f  test    cl, cl
0x140056a71  jnz     short loc_140056A90
0x140056a73  mov     byte ptr [rbx+0A0h], 3
0x140056a7a  mov     word ptr [rbx+0A2h], 400Ah
0x140056a83  mov     qword ptr [rbx+0A8h], 0
0x140056a8e  jmp     short loc_140056AA6
0x140056a90  lea     eax, [rcx-2]
0x140056a93  cmp     al, r9b
0x140056a96  jbe     short loc_140056AA6
0x140056a98  test    dword ptr [rbx+14h], 1000h
0x140056a9f  jz      short loc_140056AB4
0x140056aa1  cmp     cl, 4
0x140056aa4  jz      short loc_140056AB4
0x140056aa6  test    dword ptr [rbx+40h], 800h
0x140056aad  jz      short loc_140056AB4
0x140056aaf  mov     r8b, r9b
0x140056ab2  jmp     short loc_140056AB7
0x140056ab4  xor     r8b, r8b
0x140056ab7  movzx   eax, r8b
0x140056abb  mov     edx, eax
0x140056abd  or      edx, 2
0x140056ac0  test    dword ptr [rbx+14h], 200h
0x140056ac7  cmovz   edx, eax
0x140056aca  mov     [rbp+800h+pv], 0
0x140056ad2  mov     [rbp+800h+var_848], 0
0x140056ad6  lea     rax, [rbp+800h+var_847]
0x140056ada  mov     [rbp+800h+var_40], rax
0x140056ae1  lea     rax, [rbp+800h+var_47]
0x140056ae8  mov     [rbp+800h+var_30], rax
0x140056aef  mov     [rbp+800h+var_847], 80408040h
0x140056af6  mov     [rbp+800h+var_843], 0
0x140056afa  lea     rax, [rbp+800h+var_842]
0x140056afe  mov     [rbp+800h+var_38], rax
0x140056b05  movzx   eax, r8b
0x140056b09  cmovnz  eax, r9d
0x140056b0d  mov     r8d, edx
0x140056b10  or      r8d, 4
0x140056b14  test    al, al
0x140056b16  cmovz   r8d, edx
0x140056b1a  lea     rdx, [rbp+800h+pv]
0x140056b1e  mov     rcx, rbx
0x140056b21  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x140056b26  mov     rsi, rax
0x140056b29  xor     edx, edx; Val
0x140056b2b  lea     r8d, [rdx+78h]; Size
0x140056b2f  lea     rcx, [rsp+900h+var_8D0]; void *
0x140056b34  call    memset_0
0x140056b39  mov     edx, [rbx+0B4h]
0x140056b3f  lea     rcx, [rbx+10h]
0x140056b43  test    edx, edx
0x140056b45  jz      short loc_140056B4D
0x140056b47  mov     [rsp+900h+var_8D0], edx
0x140056b4b  jmp     short loc_140056B53
0x140056b4d  mov     eax, [rcx]
0x140056b4f  mov     [rsp+900h+var_8D0], eax
0x140056b53  mov     rax, [rbx+18h]
0x140056b57  mov     [rsp+900h+var_8C8], rax
0x140056b5c  mov     eax, [rbx+14h]
0x140056b5f  mov     [rsp+900h+var_8C0], eax
0x140056b63  movups  xmm0, xmmword ptr [rbx+90h]
0x140056b6a  movdqu  [rsp+900h+var_8BC], xmm0
0x140056b70  mov     eax, [rbx+40h]
0x140056b73  bts     eax, 15h
0x140056b77  mov     [rsp+900h+var_8AC], eax
0x140056b7b  mov     al, [rbx+0A0h]
0x140056b81  mov     [rsp+900h+var_8A8], al
0x140056b85  movzx   eax, word ptr [rbx+0A2h]
0x140056b8c  mov     [rsp+900h+var_8A6], ax
0x140056b91  mov     rax, [rbx+0A8h]
0x140056b98  mov     [rsp+900h+var_8A0], rax
0x140056b9d  mov     [rsp+900h+var_898], rdi
0x140056ba2  mov     [rsp+900h+var_888], rsi
0x140056ba7  mov     eax, [rbx+0B0h]
0x140056bad  mov     [rbp+800h+var_864], eax
0x140056bb0  test    edx, edx
0x140056bb2  jz      short loc_140056BBB
0x140056bb4  mov     eax, [rcx]
0x140056bb6  mov     [rbp+800h+var_860], eax
0x140056bb9  jmp     short loc_140056BC2
0x140056bbb  mov     [rbp+800h+var_860], 0
0x140056bc2  xor     r9d, r9d
0x140056bc5  xor     ecx, ecx
0x140056bc7  mov     rdx, [rbx+48h]
0x140056bcb  imul    r8, [rbx+58h], 0A8h
0x140056bd3  add     r8, rdx
0x140056bd6  cmp     rdx, r8
0x140056bd9  jz      short loc_140056C16
0x140056bdb  mov     eax, [rdx+8]
0x140056bde  cmp     r9d, eax
0x140056be1  cmovnz  rcx, rdx
0x140056be5  add     rdx, 0A8h
0x140056bec  cmp     r9d, eax
0x140056bef  cmovz   eax, r9d
0x140056bf3  mov     r9d, eax
0x140056bf6  cmp     rdx, r8
0x140056bf9  jnz     short loc_140056BDB
0x140056bfb  test    rcx, rcx
0x140056bfe  jz      short loc_140056C16
0x140056c00  mov     eax, [rcx+8]
0x140056c03  mov     [rbp+800h+var_880], eax
0x140056c06  mov     rax, [rcx+38h]
0x140056c0a  mov     [rbp+800h+var_878], rax
0x140056c0e  movzx   eax, word ptr [rcx+40h]
0x140056c12  mov     [rbp+800h+var_870], ax
0x140056c16  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x140056c1d  test    rax, rax
0x140056c20  jnz     short loc_140056C5E
0x140056c22  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140056c29  test    rax, rax
0x140056c2c  jnz     short loc_140056C42
0x140056c2e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140056c35  call    cs:__imp_GetModuleHandleW
0x140056c3b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x140056c42  lea     rdx, aTestreport; "TestReport"
0x140056c49  mov     rcx, rax; hModule
0x140056c4c  call    cs:__imp_GetProcAddress
0x140056c52  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x140056c59  test    rax, rax
0x140056c5c  jz      short loc_140056C69
0x140056c5e  lea     rcx, [rsp+900h+var_8D0]
0x140056c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056c68  nop
0x140056c69  mov     rcx, [rbx]
0x140056c6c  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x140056c73  lea     rdx, [rsp+900h+var_8D0]
0x140056c78  test    rax, rax
0x140056c7b  jz      short loc_140056CF6
0x140056c7d  mov     [rsp+900h+var_8E0], rdx
0x140056c82  xor     r9d, r9d
0x140056c85  xor     r8d, r8d
0x140056c88  xor     edx, edx
0x140056c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056c8f  test    al, al
0x140056c91  jnz     short loc_140056D03
0x140056c93  mov     eax, 400Eh
0x140056c98  mov     [rsp+900h+var_8A6], ax
0x140056c9d  mov     [rsp+900h+var_8A8], 3
0x140056ca2  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x140056ca9  test    rax, rax
0x140056cac  jnz     short loc_140056CEA
0x140056cae  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140056cb5  test    rax, rax
0x140056cb8  jnz     short loc_140056CCE
0x140056cba  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140056cc1  call    cs:__imp_GetModuleHandleW
0x140056cc7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x140056cce  lea     rdx, aTestreport; "TestReport"
0x140056cd5  mov     rcx, rax; hModule
0x140056cd8  call    cs:__imp_GetProcAddress
0x140056cde  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x140056ce5  test    rax, rax
0x140056ce8  jz      short loc_140056D03
0x140056cea  lea     rcx, [rsp+900h+var_8D0]
0x140056cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056cf4  jmp     short loc_140056D03
0x140056cf6  mov     rax, [rcx]
0x140056cf9  mov     rax, [rax+18h]
0x140056cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056d02  nop
0x140056d03  mov     rcx, [rbp+800h+pv]; pv
0x140056d07  test    rcx, rcx
0x140056d0a  jz      short loc_140056D13
0x140056d0c  call    cs:__imp_CoTaskMemFree
0x140056d12  nop
0x140056d13  mov     rcx, [rbp+800h+var_20]
0x140056d1a  xor     rcx, rsp; StackCookie
0x140056d1d  call    __security_check_cookie
0x140056d22  mov     rbx, [rsp+900h+arg_10]
0x140056d2a  add     rsp, 8F0h
0x140056d31  pop     rdi
0x140056d32  pop     rsi
0x140056d33  pop     rbp
0x140056d34  retn
```
