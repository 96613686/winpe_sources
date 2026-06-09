# tip2::details::shared_data<1,0,1>::evaluate_and_report(__int64)

- ea: `0x1800284cc`
- end: `0x180028783`
- name: `?evaluate_and_report@?$shared_data@$00$0A@$00@details@tip2@@AEAAX_J@Z`
- size: `695`
- prototype: `void __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180027e30`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x1800284cc`
- `0x18002878c`
- `0x18002a4ec`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002871f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002871f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028708`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028708`
- `ole32!CoTaskMemFree` at `0x18002875a`
- `ole32!CoTaskMemFree` at `0x18002875a`

## string_xrefs

- `0x180028701`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,1>::evaluate_and_report(_DWORD *a1, __int64 a2)
{
  tip2::details *v4; // rcx
  char v5; // cl
  unsigned __int8 v6; // r8
  unsigned int v7; // edx
  bool v8; // zf
  char v9; // al
  __int64 v10; // r8
  __int64 v11; // rsi
  int v12; // edx
  _DWORD *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  const struct tip2::test_requirement *v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+30h] [rbp-D0h]
  __int128 v23; // [rsp+34h] [rbp-CCh]
  int v24; // [rsp+44h] [rbp-BCh]
  char v25; // [rsp+48h] [rbp-B8h]
  __int16 v26; // [rsp+4Ah] [rbp-B6h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int16 v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+8Ch] [rbp-74h]
  int v34; // [rsp+90h] [rbp-70h]
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  char v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+A9h] [rbp-57h] BYREF
  char v38; // [rsp+ADh] [rbp-53h]
  char v39; // [rsp+AEh] [rbp-52h] BYREF
  char v40; // [rsp+8A9h] [rbp+7A9h] BYREF
  int *v41; // [rsp+8B0h] [rbp+7B0h]
  char *v42; // [rsp+8B8h] [rbp+7B8h]
  char *v43; // [rsp+8C0h] [rbp+7C0h]

  v4 = (tip2::details *)(a1 + 2);
  if ( !*((_BYTE *)v4 + 152)
    && tip2::details::evaluate_flags(
         v4,
         *((const struct tip2::test_state **)a1 + 5),
         *((const struct tip2::test_requirement **)a1 + 7),
         *((const struct tip2::test_requirement **)a1 + 6),
         v21[0]) )
  {
    (***(void (__fastcall ****)(_QWORD))a1)(*(_QWORD *)a1);
  }
  v5 = *((_BYTE *)a1 + 160);
  if ( v5 != 5 )
  {
    if ( v5 )
    {
      if ( (unsigned __int8)(v5 - 2) > 1u && ((a1[5] & 0x1000) == 0 || v5 == 4) )
        goto LABEL_12;
    }
    else
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16394;
      *((_QWORD *)a1 + 21) = 0;
    }
    if ( (a1[16] & 0x800) != 0 )
    {
      v6 = 1;
LABEL_13:
      v7 = v6 | 2;
      v8 = (a1[5] & 0x200) == 0;
      if ( (a1[5] & 0x200) == 0 )
        v7 = v6;
      pv = 0;
      v36 = 0;
      v41 = &v37;
      v43 = &v40;
      v37 = -2143256512;
      v38 = 0;
      v42 = &v39;
      v9 = v6;
      if ( !v8 )
        v9 = 1;
      v10 = v7 | 4;
      if ( !v9 )
        v10 = v7;
      v11 = tip2::details::shared_data<1,0,1>::serialize_data(a1, &pv, v10, 1);
      memset_0(v21, 0, 0x78u);
      v12 = a1[45];
      v13 = a1 + 4;
      if ( v12 )
        LODWORD(v21[0]) = a1[45];
      else
        LODWORD(v21[0]) = *v13;
      v21[1] = *((const struct tip2::test_requirement **)a1 + 3);
      v22 = a1[5];
      v23 = *((_OWORD *)a1 + 9);
      v24 = a1[16] | 0x200000;
      v25 = *((_BYTE *)a1 + 160);
      v26 = *((_WORD *)a1 + 81);
      v27 = *((_QWORD *)a1 + 21);
      v28 = a2;
      v29 = v11;
      v33 = a1[44];
      if ( v12 )
        v34 = *v13;
      else
        v34 = 0;
      v14 = 0;
      v15 = 0;
      v16 = *((_QWORD *)a1 + 9);
      v17 = v16 + 168LL * *((_QWORD *)a1 + 11);
      if ( v16 != v17 )
      {
        do
        {
          v18 = *(_DWORD *)(v16 + 8);
          if ( (_DWORD)v14 != v18 )
            v15 = v16;
          v16 += 168;
          if ( (_DWORD)v14 == v18 )
            v18 = v14;
          v14 = v18;
        }
        while ( v16 != v17 );
        if ( v15 )
        {
          v30 = *(_DWORD *)(v15 + 8);
          v31 = *(_QWORD *)(v15 + 56);
          v32 = *(_WORD *)(v15 + 64);
        }
      }
      ProcAddress = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
      if ( `TestReport'::`2'::s_pfnTestReport )
        goto LABEL_37;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestReport");
      `TestReport'::`2'::s_pfnTestReport = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_37:
        ((void (__fastcall *)(const struct tip2::test_requirement **, __int64, __int64, __int64))ProcAddress)(
          v21,
          v16,
          v17,
          v14);
      (*(void (__fastcall **)(_QWORD, const struct tip2::test_requirement **))(**(_QWORD **)a1 + 24LL))(
        *(_QWORD *)a1,
        v21);
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_12:
    v6 = 0;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x1800284cc  mov     [rsp-8+arg_10], rbx
0x1800284d1  push    rbp
0x1800284d2  push    rsi
0x1800284d3  push    rdi
0x1800284d4  lea     rbp, [rsp-7E0h]
0x1800284dc  sub     rsp, 8E0h
0x1800284e3  mov     rax, cs:__security_cookie
0x1800284ea  xor     rax, rsp
0x1800284ed  mov     [rbp+7F0h+var_20], rax
0x1800284f4  mov     rdi, rdx
0x1800284f7  mov     rbx, rcx
0x1800284fa  add     rcx, 8; this
0x1800284fe  cmp     byte ptr [rcx+98h], 0
0x180028505  jnz     short loc_18002852B
0x180028507  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18002850b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18002850f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180028513  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180028518  test    al, al
0x18002851a  jz      short loc_18002852B
0x18002851c  mov     rcx, [rbx]
0x18002851f  mov     rax, [rcx]
0x180028522  mov     rax, [rax]
0x180028525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002852a  nop
0x18002852b  mov     cl, [rbx+0A0h]
0x180028531  cmp     cl, 5
0x180028534  jz      loc_180028761
0x18002853a  mov     r9d, 1
0x180028540  test    cl, cl
0x180028542  jnz     short loc_180028561
0x180028544  mov     byte ptr [rbx+0A0h], 3
0x18002854b  mov     word ptr [rbx+0A2h], 400Ah
0x180028554  mov     qword ptr [rbx+0A8h], 0
0x18002855f  jmp     short loc_180028577
0x180028561  lea     eax, [rcx-2]
0x180028564  cmp     al, r9b
0x180028567  jbe     short loc_180028577
0x180028569  test    dword ptr [rbx+14h], 1000h
0x180028570  jz      short loc_180028585
0x180028572  cmp     cl, 4
0x180028575  jz      short loc_180028585
0x180028577  test    dword ptr [rbx+40h], 800h
0x18002857e  jz      short loc_180028585
0x180028580  mov     r8b, r9b
0x180028583  jmp     short loc_180028588
0x180028585  xor     r8b, r8b
0x180028588  movzx   eax, r8b
0x18002858c  mov     edx, eax
0x18002858e  or      edx, 2
0x180028591  test    dword ptr [rbx+14h], 200h
0x180028598  cmovz   edx, eax
0x18002859b  mov     [rbp+7F0h+pv], 0
0x1800285a3  mov     [rbp+7F0h+var_848], 0
0x1800285a7  lea     rax, [rbp+7F0h+var_847]
0x1800285ab  mov     [rbp+7F0h+var_40], rax
0x1800285b2  lea     rax, [rbp+7F0h+var_47]
0x1800285b9  mov     [rbp+7F0h+var_30], rax
0x1800285c0  mov     [rbp+7F0h+var_847], 80408040h
0x1800285c7  mov     [rbp+7F0h+var_843], 0
0x1800285cb  lea     rax, [rbp+7F0h+var_842]
0x1800285cf  mov     [rbp+7F0h+var_38], rax
0x1800285d6  movzx   eax, r8b
0x1800285da  cmovnz  eax, r9d
0x1800285de  mov     r8d, edx
0x1800285e1  or      r8d, 4
0x1800285e5  test    al, al
0x1800285e7  cmovz   r8d, edx
0x1800285eb  lea     rdx, [rbp+7F0h+pv]
0x1800285ef  mov     rcx, rbx
0x1800285f2  call    ?serialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800285f7  mov     rsi, rax
0x1800285fa  xor     edx, edx; Val
0x1800285fc  lea     r8d, [rdx+78h]; Size
0x180028600  lea     rcx, [rsp+8F0h+var_8D0]; void *
0x180028605  call    memset_0
0x18002860a  mov     edx, [rbx+0B4h]
0x180028610  lea     rcx, [rbx+10h]
0x180028614  test    edx, edx
0x180028616  jz      short loc_18002861E
0x180028618  mov     [rsp+8F0h+var_8D0], edx
0x18002861c  jmp     short loc_180028624
0x18002861e  mov     eax, [rcx]
0x180028620  mov     [rsp+8F0h+var_8D0], eax
0x180028624  mov     rax, [rbx+18h]
0x180028628  mov     [rsp+8F0h+var_8C8], rax
0x18002862d  mov     eax, [rbx+14h]
0x180028630  mov     [rsp+8F0h+var_8C0], eax
0x180028634  movups  xmm0, xmmword ptr [rbx+90h]
0x18002863b  movdqu  [rsp+8F0h+var_8BC], xmm0
0x180028641  mov     eax, [rbx+40h]
0x180028644  bts     eax, 15h
0x180028648  mov     [rsp+8F0h+var_8AC], eax
0x18002864c  mov     al, [rbx+0A0h]
0x180028652  mov     [rsp+8F0h+var_8A8], al
0x180028656  movzx   eax, word ptr [rbx+0A2h]
0x18002865d  mov     [rsp+8F0h+var_8A6], ax
0x180028662  mov     rax, [rbx+0A8h]
0x180028669  mov     [rsp+8F0h+var_8A0], rax
0x18002866e  mov     [rsp+8F0h+var_898], rdi
0x180028673  mov     [rsp+8F0h+var_888], rsi
0x180028678  mov     eax, [rbx+0B0h]
0x18002867e  mov     [rbp+7F0h+var_864], eax
0x180028681  test    edx, edx
0x180028683  jz      short loc_18002868C
0x180028685  mov     eax, [rcx]
0x180028687  mov     [rbp+7F0h+var_860], eax
0x18002868a  jmp     short loc_180028693
0x18002868c  mov     [rbp+7F0h+var_860], 0
0x180028693  xor     r9d, r9d
0x180028696  xor     ecx, ecx
0x180028698  mov     rdx, [rbx+48h]
0x18002869c  imul    r8, [rbx+58h], 0A8h
0x1800286a4  add     r8, rdx
0x1800286a7  cmp     rdx, r8
0x1800286aa  jz      short loc_1800286E9
0x1800286ac  mov     eax, [rdx+8]
0x1800286af  cmp     r9d, eax
0x1800286b2  cmovnz  rcx, rdx
0x1800286b6  add     rdx, 0A8h
0x1800286bd  cmp     r9d, eax
0x1800286c0  cmovz   eax, r9d
0x1800286c4  mov     r9d, eax
0x1800286c7  cmp     rdx, r8
0x1800286ca  jnz     short loc_1800286AC
0x1800286cc  test    rcx, rcx
0x1800286cf  jz      short loc_1800286E9
0x1800286d1  mov     eax, [rcx+8]
0x1800286d4  mov     [rsp+8F0h+var_880], eax
0x1800286d8  mov     rax, [rcx+38h]
0x1800286dc  mov     [rsp+8F0h+var_878], rax
0x1800286e1  movzx   eax, word ptr [rcx+40h]
0x1800286e5  mov     [rbp+7F0h+var_870], ax
0x1800286e9  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800286f0  test    rax, rax
0x1800286f3  jnz     short loc_180028731
0x1800286f5  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800286fc  test    rax, rax
0x1800286ff  jnz     short loc_180028715
0x180028701  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180028708  call    cs:__imp_GetModuleHandleW
0x18002870e  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180028715  lea     rdx, aTestreport; "TestReport"
0x18002871c  mov     rcx, rax; hModule
0x18002871f  call    cs:__imp_GetProcAddress
0x180028725  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18002872c  test    rax, rax
0x18002872f  jz      short loc_18002873C
0x180028731  lea     rcx, [rsp+8F0h+var_8D0]
0x180028736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002873b  nop
0x18002873c  mov     rcx, [rbx]
0x18002873f  mov     rax, [rcx]
0x180028742  lea     rdx, [rsp+8F0h+var_8D0]
0x180028747  mov     rax, [rax+18h]
0x18002874b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028750  nop
0x180028751  mov     rcx, [rbp+7F0h+pv]; pv
0x180028755  test    rcx, rcx
0x180028758  jz      short loc_180028761
0x18002875a  call    cs:__imp_CoTaskMemFree
0x180028760  nop
0x180028761  mov     rcx, [rbp+7F0h+var_20]
0x180028768  xor     rcx, rsp; StackCookie
0x18002876b  call    __security_check_cookie
0x180028770  mov     rbx, [rsp+8F0h+arg_10]
0x180028778  add     rsp, 8E0h
0x18002877f  pop     rdi
0x180028780  pop     rsi
0x180028781  pop     rbp
0x180028782  retn
```
