# tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)

- ea: `0x1800ca58c`
- end: `0x1800ca843`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ca33c`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x1800ca58c`
- `0x1800ca84c`
- `0x1800cc2e0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca7df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca7df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ca7c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ca7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca81a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca81a`

## string_xrefs

- `0x1800ca7c1`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<0,0,1>::evaluate_and_report(_DWORD *a1, __int64 a2)
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
      v11 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, v10);
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
0x1800ca58c  mov     [rsp-8+arg_10], rbx
0x1800ca591  push    rbp
0x1800ca592  push    rsi
0x1800ca593  push    rdi
0x1800ca594  lea     rbp, [rsp-7E0h]
0x1800ca59c  sub     rsp, 8E0h
0x1800ca5a3  mov     rax, cs:__security_cookie
0x1800ca5aa  xor     rax, rsp
0x1800ca5ad  mov     [rbp+7F0h+var_20], rax
0x1800ca5b4  mov     rdi, rdx
0x1800ca5b7  mov     rbx, rcx
0x1800ca5ba  add     rcx, 8; this
0x1800ca5be  cmp     byte ptr [rcx+98h], 0
0x1800ca5c5  jnz     short loc_1800CA5EB
0x1800ca5c7  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x1800ca5cb  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x1800ca5cf  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x1800ca5d3  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1800ca5d8  test    al, al
0x1800ca5da  jz      short loc_1800CA5EB
0x1800ca5dc  mov     rcx, [rbx]
0x1800ca5df  mov     rax, [rcx]
0x1800ca5e2  mov     rax, [rax]
0x1800ca5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca5ea  nop
0x1800ca5eb  mov     cl, [rbx+0A0h]
0x1800ca5f1  cmp     cl, 5
0x1800ca5f4  jz      loc_1800CA821
0x1800ca5fa  mov     r9d, 1
0x1800ca600  test    cl, cl
0x1800ca602  jnz     short loc_1800CA621
0x1800ca604  mov     byte ptr [rbx+0A0h], 3
0x1800ca60b  mov     word ptr [rbx+0A2h], 400Ah
0x1800ca614  mov     qword ptr [rbx+0A8h], 0
0x1800ca61f  jmp     short loc_1800CA637
0x1800ca621  lea     eax, [rcx-2]
0x1800ca624  cmp     al, r9b
0x1800ca627  jbe     short loc_1800CA637
0x1800ca629  test    dword ptr [rbx+14h], 1000h
0x1800ca630  jz      short loc_1800CA645
0x1800ca632  cmp     cl, 4
0x1800ca635  jz      short loc_1800CA645
0x1800ca637  test    dword ptr [rbx+40h], 800h
0x1800ca63e  jz      short loc_1800CA645
0x1800ca640  mov     r8b, r9b
0x1800ca643  jmp     short loc_1800CA648
0x1800ca645  xor     r8b, r8b
0x1800ca648  movzx   eax, r8b
0x1800ca64c  mov     edx, eax
0x1800ca64e  or      edx, 2
0x1800ca651  test    dword ptr [rbx+14h], 200h
0x1800ca658  cmovz   edx, eax
0x1800ca65b  mov     [rbp+7F0h+pv], 0
0x1800ca663  mov     [rbp+7F0h+var_848], 0
0x1800ca667  lea     rax, [rbp+7F0h+var_847]
0x1800ca66b  mov     [rbp+7F0h+var_40], rax
0x1800ca672  lea     rax, [rbp+7F0h+var_47]
0x1800ca679  mov     [rbp+7F0h+var_30], rax
0x1800ca680  mov     [rbp+7F0h+var_847], 80408040h
0x1800ca687  mov     [rbp+7F0h+var_843], 0
0x1800ca68b  lea     rax, [rbp+7F0h+var_842]
0x1800ca68f  mov     [rbp+7F0h+var_38], rax
0x1800ca696  movzx   eax, r8b
0x1800ca69a  cmovnz  eax, r9d
0x1800ca69e  mov     r8d, edx
0x1800ca6a1  or      r8d, 4
0x1800ca6a5  test    al, al
0x1800ca6a7  cmovz   r8d, edx
0x1800ca6ab  lea     rdx, [rbp+7F0h+pv]
0x1800ca6af  mov     rcx, rbx
0x1800ca6b2  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800ca6b7  mov     rsi, rax
0x1800ca6ba  xor     edx, edx; Val
0x1800ca6bc  lea     r8d, [rdx+78h]; Size
0x1800ca6c0  lea     rcx, [rsp+8F0h+var_8D0]; void *
0x1800ca6c5  call    memset_0
0x1800ca6ca  mov     edx, [rbx+0B4h]
0x1800ca6d0  lea     rcx, [rbx+10h]
0x1800ca6d4  test    edx, edx
0x1800ca6d6  jz      short loc_1800CA6DE
0x1800ca6d8  mov     [rsp+8F0h+var_8D0], edx
0x1800ca6dc  jmp     short loc_1800CA6E4
0x1800ca6de  mov     eax, [rcx]
0x1800ca6e0  mov     [rsp+8F0h+var_8D0], eax
0x1800ca6e4  mov     rax, [rbx+18h]
0x1800ca6e8  mov     [rsp+8F0h+var_8C8], rax
0x1800ca6ed  mov     eax, [rbx+14h]
0x1800ca6f0  mov     [rsp+8F0h+var_8C0], eax
0x1800ca6f4  movups  xmm0, xmmword ptr [rbx+90h]
0x1800ca6fb  movdqu  [rsp+8F0h+var_8BC], xmm0
0x1800ca701  mov     eax, [rbx+40h]
0x1800ca704  bts     eax, 15h
0x1800ca708  mov     [rsp+8F0h+var_8AC], eax
0x1800ca70c  mov     al, [rbx+0A0h]
0x1800ca712  mov     [rsp+8F0h+var_8A8], al
0x1800ca716  movzx   eax, word ptr [rbx+0A2h]
0x1800ca71d  mov     [rsp+8F0h+var_8A6], ax
0x1800ca722  mov     rax, [rbx+0A8h]
0x1800ca729  mov     [rsp+8F0h+var_8A0], rax
0x1800ca72e  mov     [rsp+8F0h+var_898], rdi
0x1800ca733  mov     [rsp+8F0h+var_888], rsi
0x1800ca738  mov     eax, [rbx+0B0h]
0x1800ca73e  mov     [rbp+7F0h+var_864], eax
0x1800ca741  test    edx, edx
0x1800ca743  jz      short loc_1800CA74C
0x1800ca745  mov     eax, [rcx]
0x1800ca747  mov     [rbp+7F0h+var_860], eax
0x1800ca74a  jmp     short loc_1800CA753
0x1800ca74c  mov     [rbp+7F0h+var_860], 0
0x1800ca753  xor     r9d, r9d
0x1800ca756  xor     ecx, ecx
0x1800ca758  mov     rdx, [rbx+48h]
0x1800ca75c  imul    r8, [rbx+58h], 0A8h
0x1800ca764  add     r8, rdx
0x1800ca767  cmp     rdx, r8
0x1800ca76a  jz      short loc_1800CA7A9
0x1800ca76c  mov     eax, [rdx+8]
0x1800ca76f  cmp     r9d, eax
0x1800ca772  cmovnz  rcx, rdx
0x1800ca776  add     rdx, 0A8h
0x1800ca77d  cmp     r9d, eax
0x1800ca780  cmovz   eax, r9d
0x1800ca784  mov     r9d, eax
0x1800ca787  cmp     rdx, r8
0x1800ca78a  jnz     short loc_1800CA76C
0x1800ca78c  test    rcx, rcx
0x1800ca78f  jz      short loc_1800CA7A9
0x1800ca791  mov     eax, [rcx+8]
0x1800ca794  mov     [rsp+8F0h+var_880], eax
0x1800ca798  mov     rax, [rcx+38h]
0x1800ca79c  mov     [rsp+8F0h+var_878], rax
0x1800ca7a1  movzx   eax, word ptr [rcx+40h]
0x1800ca7a5  mov     [rbp+7F0h+var_870], ax
0x1800ca7a9  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800ca7b0  test    rax, rax
0x1800ca7b3  jnz     short loc_1800CA7F1
0x1800ca7b5  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800ca7bc  test    rax, rax
0x1800ca7bf  jnz     short loc_1800CA7D5
0x1800ca7c1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800ca7c8  call    cs:__imp_GetModuleHandleW
0x1800ca7ce  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800ca7d5  lea     rdx, aTestreport; "TestReport"
0x1800ca7dc  mov     rcx, rax; hModule
0x1800ca7df  call    cs:__imp_GetProcAddress
0x1800ca7e5  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800ca7ec  test    rax, rax
0x1800ca7ef  jz      short loc_1800CA7FC
0x1800ca7f1  lea     rcx, [rsp+8F0h+var_8D0]
0x1800ca7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca7fb  nop
0x1800ca7fc  mov     rcx, [rbx]
0x1800ca7ff  mov     rax, [rcx]
0x1800ca802  lea     rdx, [rsp+8F0h+var_8D0]
0x1800ca807  mov     rax, [rax+18h]
0x1800ca80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca810  nop
0x1800ca811  mov     rcx, [rbp+7F0h+pv]; pv
0x1800ca815  test    rcx, rcx
0x1800ca818  jz      short loc_1800CA821
0x1800ca81a  call    cs:__imp_CoTaskMemFree
0x1800ca820  nop
0x1800ca821  mov     rcx, [rbp+7F0h+var_20]
0x1800ca828  xor     rcx, rsp; StackCookie
0x1800ca82b  call    __security_check_cookie
0x1800ca830  mov     rbx, [rsp+8F0h+arg_10]
0x1800ca838  add     rsp, 8E0h
0x1800ca83f  pop     rdi
0x1800ca840  pop     rsi
0x1800ca841  pop     rbp
0x1800ca842  retn
```
