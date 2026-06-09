# GenADTG::GetHRowsToStream(unsigned __int64 *,unsigned __int64 * *,ulong * *,unsigned __int64)

- ea: `0x1800066ac`
- end: `0x180006a21`
- name: `?GetHRowsToStream@GenADTG@@AEAAXPEA_KPEAPEA_KPEAPEAK_K@Z`
- size: `885`
- prototype: `void __fastcall(GenADTG *__hidden this, unsigned __int64 *, unsigned __int64 **, unsigned int **, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180005edc`
- `0x180008c10`

## callees

- `0x1800066ac`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000697e`
- `ole32!CoTaskMemFree` at `0x18000698f`
- `ole32!CoTaskMemFree` at `0x18000697e`
- `ole32!CoTaskMemFree` at `0x18000698f`
- `ole32!CoTaskMemAlloc` at `0x180006894`
- `ole32!CoTaskMemAlloc` at `0x180006894`

## pseudocode

```c
void __fastcall GenADTG::GetHRowsToStream(
        GenADTG *this,
        unsigned __int64 *a2,
        LPVOID *a3,
        LPVOID *a4,
        unsigned __int64 a5)
{
  __int64 v6; // r15
  bool v10; // cf
  unsigned int v11; // eax
  int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  LPVOID v15; // rcx
  unsigned int *v16; // rax
  int v17; // eax
  int v18; // ebx
  unsigned int v19; // ebx

  v6 = *((_QWORD *)this + 5);
  if ( !*((_DWORD *)this + 69) && v6 )
  {
    v10 = *((_DWORD *)this + 48) != 0;
    *((_DWORD *)this + 69) = 1;
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v6 + 56LL))(
            v6,
            a5,
            v10 ? 7 : 4,
            a2,
            a3,
            a4);
    v12 = v11;
    if ( v11 == -2147024809 )
    {
      if ( *((_DWORD *)this + 71) != 1 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800484D0[0] )
            bidTraceW(off_1800481C0[0], 2400256, off_1800484D0[0], 2147500037LL, 2344);
        }
        ThrowHR(-2147467259);
      }
LABEL_11:
      if ( (bidGblFlags & 2) != 0 && off_1800484C8[0] )
        bidTraceW(off_1800481C0[0], 2406400, off_1800484C8[0], v11, 2350);
      ThrowHR(v12);
    }
    if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147467263 )
      goto LABEL_11;
  }
  if ( !*((_DWORD *)this + 48) && !*a2 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, __int64, unsigned __int64 *, LPVOID *))(**((_QWORD **)this + 4) + 16LL))(
            *((_QWORD *)this + 4),
            a5,
            0,
            1,
            a2,
            a3);
    v14 = v13;
    if ( v13 == -2147024809 )
    {
      if ( *((_DWORD *)this + 71) != 1 )
        v14 = -2147467259;
LABEL_21:
      if ( (bidGblFlags & 2) != 0 && off_1800484C0[0] )
        bidTraceW(off_1800481C0[0], 2426880, off_1800484C0[0], v14, 2370);
      ThrowHR(v14);
    }
    if ( v13 < 0 )
      goto LABEL_21;
    if ( v6 )
    {
      if ( *a3 && *a2 )
      {
        v15 = *a4;
        if ( !*a4 )
        {
          v16 = (unsigned int *)CoTaskMemAlloc((unsigned int)(4 * *(_DWORD *)a2));
          *a4 = v16;
          v15 = v16;
          if ( !v16 )
          {
            if ( (bidGblFlags & 2) != 0 && off_1800484B8[0] )
              bidTraceW(off_1800481C0[0], 2438144, off_1800484B8[0], 2147942414LL, 2381);
            ThrowHR(-2147024882);
          }
        }
        v17 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, LPVOID, LPVOID))(*(_QWORD *)v6 + 64LL))(
                v6,
                a5,
                *a2,
                *a3,
                v15);
        v18 = v17;
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800484B0[0] )
            bidTraceW(off_1800481C0[0], 2444288, off_1800484B0[0], (unsigned int)v17, 2387);
          ThrowHR(v18);
        }
        if ( *(_DWORD *)*a4 == 1 )
LABEL_40:
          *((_DWORD *)this + 70) = 1;
      }
      else if ( !*((_DWORD *)this + 70) )
      {
        CoTaskMemFree(*a4);
        *a4 = 0;
        CoTaskMemFree(*a3);
        *a3 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v6 + 56LL))(
                v6,
                a5,
                1,
                a2,
                a3,
                a4);
        if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147467263 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800484A8[0] )
            bidTraceW(off_1800481C0[0], 2467840, off_1800484A8[0], v19, 2410);
          ThrowHR(v19);
        }
        goto LABEL_40;
      }
    }
  }
}

```

## disassembly

```asm
0x1800066ac  push    rbx
0x1800066ae  push    rbp
0x1800066af  push    rsi
0x1800066b0  push    rdi
0x1800066b1  push    r14
0x1800066b3  push    r15
0x1800066b5  sub     rsp, 48h
0x1800066b9  cmp     dword ptr [rcx+114h], 0
0x1800066c0  mov     r14, r9
0x1800066c3  mov     r15, [rcx+28h]
0x1800066c7  mov     rbp, r8
0x1800066ca  mov     rsi, rdx
0x1800066cd  mov     rdi, rcx
0x1800066d0  jnz     loc_1800067CA
0x1800066d6  test    r15, r15
0x1800066d9  jz      loc_1800067CA
0x1800066df  mov     eax, [rdi+0C0h]
0x1800066e5  neg     eax
0x1800066e7  mov     dword ptr [rcx+114h], 1
0x1800066f1  mov     rcx, [r15]
0x1800066f4  sbb     r8d, r8d
0x1800066f7  mov     [rsp+78h+var_50], r9
0x1800066fc  and     r8d, 3
0x180006700  mov     [rsp+78h+var_58], rbp
0x180006705  mov     r9, rdx
0x180006708  add     r8d, 4
0x18000670c  mov     rax, [rcx+38h]
0x180006710  mov     rcx, r15
0x180006713  mov     rdx, [rsp+78h+arg_20]
0x18000671b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006720  mov     ebx, eax
0x180006722  cmp     eax, 80070057h
0x180006727  jnz     short loc_180006777
0x180006729  cmp     dword ptr [rdi+11Ch], 1
0x180006730  jz      short loc_18000678A
0x180006732  test    byte ptr cs:_bidGblFlags, 2
0x180006739  mov     ebx, 80004005h
0x18000673e  jz      short loc_18000676F
0x180006740  mov     rax, cs:off_1800484D0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006747  test    rax, rax
0x18000674a  jz      short loc_18000676F
0x18000674c  mov     r8, cs:off_1800484D0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006753  mov     r9d, ebx
0x180006756  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000675d  mov     edx, 24A000h
0x180006762  mov     dword ptr [rsp+78h+var_58], 928h
0x18000676a  call    _bidTraceW
0x18000676f  mov     ecx, ebx; int
0x180006771  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006777  mov     ecx, 80000000h
0x18000677c  add     eax, ecx
0x18000677e  test    ecx, eax
0x180006780  jnz     short loc_1800067CA
0x180006782  cmp     ebx, 80004001h
0x180006788  jz      short loc_1800067CA
0x18000678a  test    byte ptr cs:_bidGblFlags, 2
0x180006791  jz      short loc_1800067C2
0x180006793  mov     rax, cs:off_1800484C8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x18000679a  test    rax, rax
0x18000679d  jz      short loc_1800067C2
0x18000679f  mov     r8, cs:off_1800484C8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x1800067a6  mov     r9d, ebx
0x1800067a9  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800067b0  mov     edx, 24B800h
0x1800067b5  mov     dword ptr [rsp+78h+var_58], 92Eh
0x1800067bd  call    _bidTraceW
0x1800067c2  mov     ecx, ebx; int
0x1800067c4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800067ca  cmp     dword ptr [rdi+0C0h], 0
0x1800067d1  jnz     loc_180006965
0x1800067d7  cmp     qword ptr [rsi], 0
0x1800067db  jnz     loc_180006965
0x1800067e1  mov     rcx, [rdi+20h]
0x1800067e5  mov     r9d, 1
0x1800067eb  mov     rdx, [rsp+78h+arg_20]
0x1800067f3  xor     r8d, r8d
0x1800067f6  mov     [rsp+78h+var_50], rbp
0x1800067fb  mov     [rsp+78h+var_58], rsi
0x180006800  mov     rax, [rcx]
0x180006803  mov     rax, [rax+10h]
0x180006807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000680c  mov     ebx, eax
0x18000680e  cmp     eax, 80070057h
0x180006813  jnz     short loc_180006825
0x180006815  cmp     dword ptr [rdi+11Ch], 1
0x18000681c  jz      short loc_180006829
0x18000681e  mov     ebx, 80004005h
0x180006823  jmp     short loc_180006829
0x180006825  test    eax, eax
0x180006827  jns     short loc_180006869
0x180006829  test    byte ptr cs:_bidGblFlags, 2
0x180006830  jz      short loc_180006861
0x180006832  mov     rax, cs:off_1800484C0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006839  test    rax, rax
0x18000683c  jz      short loc_180006861
0x18000683e  mov     r8, cs:off_1800484C0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006845  mov     r9d, ebx
0x180006848  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000684f  mov     edx, 250800h
0x180006854  mov     dword ptr [rsp+78h+var_58], 942h
0x18000685c  call    _bidTraceW
0x180006861  mov     ecx, ebx; int
0x180006863  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006869  test    r15, r15
0x18000686c  jz      loc_180006965
0x180006872  cmp     qword ptr [rbp+0], 0
0x180006877  jz      loc_180006972
0x18000687d  cmp     qword ptr [rsi], 0
0x180006881  jz      loc_180006972
0x180006887  mov     rcx, [r14]
0x18000688a  test    rcx, rcx
0x18000688d  jnz     short loc_1800068EA
0x18000688f  mov     ecx, [rsi]
0x180006891  shl     ecx, 2; cb
0x180006894  call    cs:__imp_CoTaskMemAlloc
0x18000689a  mov     [r14], rax
0x18000689d  mov     rcx, rax
0x1800068a0  test    rax, rax
0x1800068a3  jnz     short loc_1800068EA
0x1800068a5  test    byte ptr cs:_bidGblFlags, 2
0x1800068ac  mov     ebx, 8007000Eh
0x1800068b1  jz      short loc_1800068E2
0x1800068b3  mov     rax, cs:off_1800484B8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x1800068ba  test    rax, rax
0x1800068bd  jz      short loc_1800068E2
0x1800068bf  mov     r8, cs:off_1800484B8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x1800068c6  mov     r9d, ebx
0x1800068c9  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800068d0  mov     edx, 253400h
0x1800068d5  mov     dword ptr [rsp+78h+var_58], 94Dh
0x1800068dd  call    _bidTraceW
0x1800068e2  mov     ecx, ebx; int
0x1800068e4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800068ea  mov     rax, [r15]
0x1800068ed  mov     r9, [rbp+0]
0x1800068f1  mov     r8, [rsi]
0x1800068f4  mov     rdx, [rsp+78h+arg_20]
0x1800068fc  mov     rax, [rax+40h]
0x180006900  mov     [rsp+78h+var_58], rcx
0x180006905  mov     rcx, r15
0x180006908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000690d  mov     ebx, eax
0x18000690f  test    eax, eax
0x180006911  jns     short loc_180006953
0x180006913  test    byte ptr cs:_bidGblFlags, 2
0x18000691a  jz      short loc_18000694B
0x18000691c  mov     rcx, cs:off_1800484B0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006923  test    rcx, rcx
0x180006926  jz      short loc_18000694B
0x180006928  mov     r8, cs:off_1800484B0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x18000692f  mov     r9d, eax
0x180006932  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006939  mov     edx, 254C00h
0x18000693e  mov     dword ptr [rsp+78h+var_58], 953h
0x180006946  call    _bidTraceW
0x18000694b  mov     ecx, ebx; int
0x18000694d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006953  mov     rax, [r14]
0x180006956  cmp     dword ptr [rax], 1
0x180006959  jnz     short loc_180006965
0x18000695b  mov     dword ptr [rdi+118h], 1
0x180006965  add     rsp, 48h
0x180006969  pop     r15
0x18000696b  pop     r14
0x18000696d  pop     rdi
0x18000696e  pop     rsi
0x18000696f  pop     rbp
0x180006970  pop     rbx
0x180006971  retn
0x180006972  cmp     dword ptr [rdi+118h], 0
0x180006979  jnz     short loc_180006965
0x18000697b  mov     rcx, [r14]; pv
0x18000697e  call    cs:__imp_CoTaskMemFree
0x180006984  mov     qword ptr [r14], 0
0x18000698b  mov     rcx, [rbp+0]; pv
0x18000698f  call    cs:__imp_CoTaskMemFree
0x180006995  mov     rdx, [rsp+78h+arg_20]
0x18000699d  mov     r9, rsi
0x1800069a0  mov     qword ptr [rbp+0], 0
0x1800069a8  mov     r8d, 1
0x1800069ae  mov     rax, [r15]
0x1800069b1  mov     rcx, r15
0x1800069b4  mov     [rsp+78h+var_50], r14
0x1800069b9  mov     [rsp+78h+var_58], rbp
0x1800069be  mov     rax, [rax+38h]
0x1800069c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c7  mov     ebx, eax
0x1800069c9  mov     eax, 80000000h
0x1800069ce  lea     ecx, [rbx+rax]
0x1800069d1  test    eax, ecx
0x1800069d3  jnz     short loc_18000695B
0x1800069d5  cmp     ebx, 80004001h
0x1800069db  jz      loc_18000695B
0x1800069e1  test    byte ptr cs:_bidGblFlags, 2
0x1800069e8  jz      short loc_180006A19
0x1800069ea  mov     rcx, cs:off_1800484A8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x1800069f1  test    rcx, rcx
0x1800069f4  jz      short loc_180006A19
0x1800069f6  mov     r8, cs:off_1800484A8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x1800069fd  mov     r9d, ebx
0x180006a00  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006a07  mov     edx, 25A800h
0x180006a0c  mov     dword ptr [rsp+78h+var_58], 96Ah
0x180006a14  call    _bidTraceW
0x180006a19  mov     ecx, ebx; int
0x180006a1b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
