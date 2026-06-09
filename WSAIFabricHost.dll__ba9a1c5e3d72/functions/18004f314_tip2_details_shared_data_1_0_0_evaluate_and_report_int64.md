# tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)

- ea: `0x18004f314`
- end: `0x18004f699`
- name: `?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ddf0`
- `0x18004dea8`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x18004f314`
- `0x18004f6a0`
- `0x180053bb4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f5b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f63c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f5b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f63c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004f599`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004f625`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004f599`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004f625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f670`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f670`

## string_xrefs

- `0x18004f592`: `kernelbase.dll`
- `0x18004f61e`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
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
0x18004f314  mov     [rsp-8+arg_10], rbx
0x18004f319  push    rbp
0x18004f31a  push    rsi
0x18004f31b  push    rdi
0x18004f31c  lea     rbp, [rsp-7F0h]
0x18004f324  sub     rsp, 8F0h
0x18004f32b  mov     rax, cs:__security_cookie
0x18004f332  xor     rax, rsp
0x18004f335  mov     [rbp+800h+var_20], rax
0x18004f33c  mov     rdi, rdx
0x18004f33f  mov     rbx, rcx
0x18004f342  add     rcx, 8; this
0x18004f346  cmp     byte ptr [rcx+98h], 0
0x18004f34d  jnz     short loc_18004F3BE
0x18004f34f  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18004f353  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18004f357  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x18004f35b  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x18004f360  test    al, al
0x18004f362  jz      short loc_18004F3BE
0x18004f364  mov     rcx, [rbx]
0x18004f367  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18004f36e  test    rax, rax
0x18004f371  jz      short loc_18004F3B2
0x18004f373  mov     [rsp+900h+var_8E0], 0
0x18004f37c  xor     r9d, r9d
0x18004f37f  xor     r8d, r8d
0x18004f382  xor     edx, edx
0x18004f384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f389  test    al, al
0x18004f38b  jnz     short loc_18004F3BE
0x18004f38d  cmp     [rbx+0A0h], al
0x18004f393  jnz     short loc_18004F3BE
0x18004f395  mov     byte ptr [rbx+0A0h], 3
0x18004f39c  mov     word ptr [rbx+0A2h], 400Bh
0x18004f3a5  mov     qword ptr [rbx+0A8h], 0
0x18004f3b0  jmp     short loc_18004F3BE
0x18004f3b2  mov     rax, [rcx]
0x18004f3b5  mov     rax, [rax]
0x18004f3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3bd  nop
0x18004f3be  mov     cl, [rbx+0A0h]
0x18004f3c4  cmp     cl, 5
0x18004f3c7  jz      loc_18004F677
0x18004f3cd  mov     r9d, 1
0x18004f3d3  test    cl, cl
0x18004f3d5  jnz     short loc_18004F3F4
0x18004f3d7  mov     byte ptr [rbx+0A0h], 3
0x18004f3de  mov     word ptr [rbx+0A2h], 400Ah
0x18004f3e7  mov     qword ptr [rbx+0A8h], 0
0x18004f3f2  jmp     short loc_18004F40A
0x18004f3f4  lea     eax, [rcx-2]
0x18004f3f7  cmp     al, r9b
0x18004f3fa  jbe     short loc_18004F40A
0x18004f3fc  test    dword ptr [rbx+14h], 1000h
0x18004f403  jz      short loc_18004F418
0x18004f405  cmp     cl, 4
0x18004f408  jz      short loc_18004F418
0x18004f40a  test    dword ptr [rbx+40h], 800h
0x18004f411  jz      short loc_18004F418
0x18004f413  mov     r8b, r9b
0x18004f416  jmp     short loc_18004F41B
0x18004f418  xor     r8b, r8b
0x18004f41b  movzx   eax, r8b
0x18004f41f  mov     edx, eax
0x18004f421  or      edx, 2
0x18004f424  test    dword ptr [rbx+14h], 200h
0x18004f42b  cmovz   edx, eax
0x18004f42e  mov     [rbp+800h+pv], 0
0x18004f436  mov     [rbp+800h+var_848], 0
0x18004f43a  lea     rax, [rbp+800h+var_847]
0x18004f43e  mov     [rbp+800h+var_40], rax
0x18004f445  lea     rax, [rbp+800h+var_47]
0x18004f44c  mov     [rbp+800h+var_30], rax
0x18004f453  mov     [rbp+800h+var_847], 80408040h
0x18004f45a  mov     [rbp+800h+var_843], 0
0x18004f45e  lea     rax, [rbp+800h+var_842]
0x18004f462  mov     [rbp+800h+var_38], rax
0x18004f469  movzx   eax, r8b
0x18004f46d  cmovnz  eax, r9d
0x18004f471  mov     r8d, edx
0x18004f474  or      r8d, 4
0x18004f478  test    al, al
0x18004f47a  cmovz   r8d, edx
0x18004f47e  lea     rdx, [rbp+800h+pv]
0x18004f482  mov     rcx, rbx
0x18004f485  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18004f48a  mov     rsi, rax
0x18004f48d  xor     edx, edx; Val
0x18004f48f  lea     r8d, [rdx+78h]; Size
0x18004f493  lea     rcx, [rsp+900h+var_8D0]; void *
0x18004f498  call    memset_0
0x18004f49d  mov     edx, [rbx+0B4h]
0x18004f4a3  lea     rcx, [rbx+10h]
0x18004f4a7  test    edx, edx
0x18004f4a9  jz      short loc_18004F4B1
0x18004f4ab  mov     [rsp+900h+var_8D0], edx
0x18004f4af  jmp     short loc_18004F4B7
0x18004f4b1  mov     eax, [rcx]
0x18004f4b3  mov     [rsp+900h+var_8D0], eax
0x18004f4b7  mov     rax, [rbx+18h]
0x18004f4bb  mov     [rsp+900h+var_8C8], rax
0x18004f4c0  mov     eax, [rbx+14h]
0x18004f4c3  mov     [rsp+900h+var_8C0], eax
0x18004f4c7  movups  xmm0, xmmword ptr [rbx+90h]
0x18004f4ce  movdqu  [rsp+900h+var_8BC], xmm0
0x18004f4d4  mov     eax, [rbx+40h]
0x18004f4d7  bts     eax, 15h
0x18004f4db  mov     [rsp+900h+var_8AC], eax
0x18004f4df  mov     al, [rbx+0A0h]
0x18004f4e5  mov     [rsp+900h+var_8A8], al
0x18004f4e9  movzx   eax, word ptr [rbx+0A2h]
0x18004f4f0  mov     [rsp+900h+var_8A6], ax
0x18004f4f5  mov     rax, [rbx+0A8h]
0x18004f4fc  mov     [rsp+900h+var_8A0], rax
0x18004f501  mov     [rsp+900h+var_898], rdi
0x18004f506  mov     [rsp+900h+var_888], rsi
0x18004f50b  mov     eax, [rbx+0B0h]
0x18004f511  mov     [rbp+800h+var_864], eax
0x18004f514  test    edx, edx
0x18004f516  jz      short loc_18004F51F
0x18004f518  mov     eax, [rcx]
0x18004f51a  mov     [rbp+800h+var_860], eax
0x18004f51d  jmp     short loc_18004F526
0x18004f51f  mov     [rbp+800h+var_860], 0
0x18004f526  xor     r9d, r9d
0x18004f529  xor     ecx, ecx
0x18004f52b  mov     rdx, [rbx+48h]
0x18004f52f  imul    r8, [rbx+58h], 0A8h
0x18004f537  add     r8, rdx
0x18004f53a  cmp     rdx, r8
0x18004f53d  jz      short loc_18004F57A
0x18004f53f  mov     eax, [rdx+8]
0x18004f542  cmp     r9d, eax
0x18004f545  cmovnz  rcx, rdx
0x18004f549  add     rdx, 0A8h
0x18004f550  cmp     r9d, eax
0x18004f553  cmovz   eax, r9d
0x18004f557  mov     r9d, eax
0x18004f55a  cmp     rdx, r8
0x18004f55d  jnz     short loc_18004F53F
0x18004f55f  test    rcx, rcx
0x18004f562  jz      short loc_18004F57A
0x18004f564  mov     eax, [rcx+8]
0x18004f567  mov     [rbp+800h+var_880], eax
0x18004f56a  mov     rax, [rcx+38h]
0x18004f56e  mov     [rbp+800h+var_878], rax
0x18004f572  movzx   eax, word ptr [rcx+40h]
0x18004f576  mov     [rbp+800h+var_870], ax
0x18004f57a  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18004f581  test    rax, rax
0x18004f584  jnz     short loc_18004F5C2
0x18004f586  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18004f58d  test    rax, rax
0x18004f590  jnz     short loc_18004F5A6
0x18004f592  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18004f599  call    cs:__imp_GetModuleHandleW
0x18004f59f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18004f5a6  lea     rdx, aTestreport; "TestReport"
0x18004f5ad  mov     rcx, rax; hModule
0x18004f5b0  call    cs:__imp_GetProcAddress
0x18004f5b6  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18004f5bd  test    rax, rax
0x18004f5c0  jz      short loc_18004F5CD
0x18004f5c2  lea     rcx, [rsp+900h+var_8D0]
0x18004f5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5cc  nop
0x18004f5cd  mov     rcx, [rbx]
0x18004f5d0  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18004f5d7  lea     rdx, [rsp+900h+var_8D0]
0x18004f5dc  test    rax, rax
0x18004f5df  jz      short loc_18004F65A
0x18004f5e1  mov     [rsp+900h+var_8E0], rdx
0x18004f5e6  xor     r9d, r9d
0x18004f5e9  xor     r8d, r8d
0x18004f5ec  xor     edx, edx
0x18004f5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5f3  test    al, al
0x18004f5f5  jnz     short loc_18004F667
0x18004f5f7  mov     eax, 400Eh
0x18004f5fc  mov     [rsp+900h+var_8A6], ax
0x18004f601  mov     [rsp+900h+var_8A8], 3
0x18004f606  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18004f60d  test    rax, rax
0x18004f610  jnz     short loc_18004F64E
0x18004f612  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18004f619  test    rax, rax
0x18004f61c  jnz     short loc_18004F632
0x18004f61e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18004f625  call    cs:__imp_GetModuleHandleW
0x18004f62b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18004f632  lea     rdx, aTestreport; "TestReport"
0x18004f639  mov     rcx, rax; hModule
0x18004f63c  call    cs:__imp_GetProcAddress
0x18004f642  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18004f649  test    rax, rax
0x18004f64c  jz      short loc_18004F667
0x18004f64e  lea     rcx, [rsp+900h+var_8D0]
0x18004f653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f658  jmp     short loc_18004F667
0x18004f65a  mov     rax, [rcx]
0x18004f65d  mov     rax, [rax+18h]
0x18004f661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f666  nop
0x18004f667  mov     rcx, [rbp+800h+pv]; pv
0x18004f66b  test    rcx, rcx
0x18004f66e  jz      short loc_18004F677
0x18004f670  call    cs:__imp_CoTaskMemFree
0x18004f676  nop
0x18004f677  mov     rcx, [rbp+800h+var_20]
0x18004f67e  xor     rcx, rsp; StackCookie
0x18004f681  call    __security_check_cookie
0x18004f686  mov     rbx, [rsp+900h+arg_10]
0x18004f68e  add     rsp, 8F0h
0x18004f695  pop     rdi
0x18004f696  pop     rsi
0x18004f697  pop     rbp
0x18004f698  retn
```
