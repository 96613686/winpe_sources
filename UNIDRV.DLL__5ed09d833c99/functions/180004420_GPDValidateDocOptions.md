# GPDValidateDocOptions

- ea: `0x180004420`
- end: `0x1800046ac`
- name: `GPDValidateDocOptions`
- size: `652`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034678`

## callees

- `0x180004420`
- `0x180004810`
- `0x180005020`
- `0x180005b20`
- `0x180007150`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800045a8`
- `KERNEL32!LocalFree` at `0x1800045b7`
- `KERNEL32!LocalFree` at `0x18000469b`
- `KERNEL32!LocalFree` at `0x1800045a8`
- `KERNEL32!LocalFree` at `0x1800045b7`
- `KERNEL32!LocalFree` at `0x18000469b`
- `KERNEL32!LocalAlloc` at `0x180004481`
- `KERNEL32!LocalAlloc` at `0x180004497`
- `KERNEL32!LocalAlloc` at `0x180004481`
- `KERNEL32!LocalAlloc` at `0x180004497`

## string_xrefs

- `0x18000465a`: `ValidateDocOptions: Too many features: %d features defined (MAX_COMBINED_OPTIONS = %d)`

## pseudocode

```c
void __fastcall GPDValidateDocOptions(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebp
  unsigned int v5; // esi
  _BYTE *v6; // rbx
  unsigned __int8 *v7; // r15
  unsigned int v8; // r8d
  unsigned __int8 *v9; // rax
  unsigned int j; // ecx
  __int64 v11; // rdx
  unsigned int k; // ecx
  __int64 v13; // rdx
  __int64 m; // rax
  unsigned int n; // edx
  int v16; // r8d
  unsigned int v17; // r9d
  __int64 v18; // rax
  unsigned __int8 *v19; // rcx
  unsigned int i; // ecx
  __int64 v21; // rax

  if ( !a2 )
  {
    WriteDbgTraceErrorGpd((__int64)"GPDValidateDocOptions", "ValidateDocOptions: NULL  Option array not permitted.");
    return;
  }
  v4 = 256;
  v5 = *(_DWORD *)(a1 + 20);
  v6 = 0;
  v7 = 0;
  if ( v5 > 0x100 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"GPDValidateDocOptions",
      "ValidateDocOptions: Option array too small: %d < %d",
      256,
      v5);
    for ( i = 0; i < v4; ++i )
    {
LABEL_36:
      v21 = i;
      *(_WORD *)(a2 + 2 * v21) = 0;
    }
    goto LABEL_30;
  }
  v8 = *(_DWORD *)(a1 + 120);
  if ( v8 > 0x200 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"GPDValidateDocOptions",
      "ValidateDocOptions: Too many features: %d features defined (MAX_COMBINED_OPTIONS = %d)",
      v8,
      512);
  }
  else
  {
    v6 = LocalAlloc(0, 0x400u);
    v9 = (unsigned __int8 *)LocalAlloc(0, 0x400u);
    v7 = v9;
    if ( v6 && v9 )
    {
      for ( j = v5; j < 0x200; ++j )
      {
        v11 = j;
        v6[2 * v11] = 0;
      }
      for ( k = 0; k < v5; ++k )
      {
        v13 = a2 + 2LL * k;
        for ( m = *(unsigned __int8 *)(v13 + 1); (_DWORD)m; m = *(unsigned __int8 *)(a2 + 2 * m + 1) )
        {
          if ( (unsigned int)m < v5 || v6[2 * m] )
          {
            *(_BYTE *)(v13 + 1) = 0;
            break;
          }
          v6[2 * m] = 1;
        }
      }
      if ( (unsigned int)(*(_DWORD *)(a1 + 20) + *(_DWORD *)(a1 + 24)) <= 0x200
        && (unsigned int)BinitDefaultOptionArray((__int64)v7, a1)
        && (unsigned int)GPDCombineOptionArray(a1, (__int64)v6, 0x100u, a2, 0) )
      {
        for ( n = 0; n < *(_DWORD *)(a1 + 120); ++n )
        {
          v16 = 0;
          v17 = *(_DWORD *)(396LL * n + *(_QWORD *)(a1 + 112) + 392);
          v18 = n;
          while ( (unsigned int)v18 < 0x200 )
          {
            v19 = &v6[2 * v18];
            if ( *v19 >= v17 )
              break;
            if ( ++v16 > v17 )
              break;
            v18 = v19[1];
            if ( !v19[1] )
              goto LABEL_21;
          }
          *(_WORD *)&v6[2 * n] = v7[2 * n];
LABEL_21:
          ;
        }
        if ( (unsigned int)GPDSeparateOptionArray(a1, (__int64)v6, a2, 0x100u, 0) )
        {
          LocalFree(v6);
LABEL_24:
          LocalFree(v7);
          return;
        }
      }
    }
  }
  if ( v5 < 0x100 )
    v4 = v5;
  i = 0;
  if ( v4 )
    goto LABEL_36;
LABEL_30:
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    goto LABEL_24;
}

```

## disassembly

```asm
0x180004420  push    rdi
0x180004422  push    r14
0x180004424  sub     rsp, 38h
0x180004428  mov     r14, rdx
0x18000442b  mov     rdi, rcx
0x18000442e  test    rdx, rdx
0x180004431  jz      loc_180004614
0x180004437  mov     [rsp+48h+arg_0], rbx
0x18000443c  mov     [rsp+48h+arg_8], rbp
0x180004441  mov     ebp, 100h
0x180004446  mov     [rsp+48h+arg_10], rsi
0x18000444b  mov     esi, [rcx+14h]
0x18000444e  mov     [rsp+48h+arg_18], r12
0x180004453  xor     r12d, r12d
0x180004456  mov     [rsp+48h+var_18], r15
0x18000445b  mov     ebx, r12d
0x18000445e  mov     r15d, r12d
0x180004461  cmp     esi, ebp
0x180004463  ja      loc_180004629
0x180004469  mov     r8d, [rcx+78h]
0x18000446d  cmp     r8d, 200h
0x180004474  ja      loc_180004654
0x18000447a  mov     edx, 400h; uBytes
0x18000447f  xor     ecx, ecx; uFlags
0x180004481  call    cs:__imp_LocalAlloc
0x180004488  nop     dword ptr [rax+rax+00h]
0x18000448d  mov     edx, 400h; uBytes
0x180004492  xor     ecx, ecx; uFlags
0x180004494  mov     rbx, rax
0x180004497  call    cs:__imp_LocalAlloc
0x18000449e  nop     dword ptr [rax+rax+00h]
0x1800044a3  mov     r15, rax
0x1800044a6  test    rbx, rbx
0x1800044a9  jz      loc_1800045F5
0x1800044af  test    rax, rax
0x1800044b2  jz      loc_1800045F5
0x1800044b8  mov     ecx, esi
0x1800044ba  nop     word ptr [rax+rax+00h]
0x1800044c0  mov     edx, ecx
0x1800044c2  inc     ecx
0x1800044c4  mov     [rbx+rdx*2], r12b
0x1800044c8  cmp     ecx, 200h
0x1800044ce  jb      short loc_1800044C0
0x1800044d0  mov     ecx, r12d
0x1800044d3  test    esi, esi
0x1800044d5  jz      short loc_1800044FA
0x1800044d7  nop     word ptr [rax+rax+00000000h]
0x1800044e0  mov     eax, ecx
0x1800044e2  lea     rdx, [r14+rax*2]
0x1800044e6  movzx   eax, byte ptr [r14+rax*2+1]
0x1800044ec  test    eax, eax
0x1800044ee  jnz     loc_18000466F
0x1800044f4  inc     ecx
0x1800044f6  cmp     ecx, esi
0x1800044f8  jb      short loc_1800044E0
0x1800044fa  mov     eax, [rdi+18h]
0x1800044fd  add     eax, [rdi+14h]
0x180004500  cmp     eax, 200h
0x180004505  ja      loc_1800045F5
0x18000450b  mov     rdx, rdi
0x18000450e  mov     rcx, r15
0x180004511  call    BinitDefaultOptionArray
0x180004516  test    eax, eax
0x180004518  jz      loc_1800045F5
0x18000451e  mov     r9, r14
0x180004521  mov     [rsp+48h+var_28], r12
0x180004526  mov     r8d, ebp
0x180004529  mov     rdx, rbx
0x18000452c  mov     rcx, rdi
0x18000452f  call    GPDCombineOptionArray
0x180004534  test    eax, eax
0x180004536  jz      loc_1800045F5
0x18000453c  mov     edx, r12d
0x18000453f  cmp     [rdi+78h], r12d
0x180004543  jbe     short loc_18000458B
0x180004545  mov     rax, [rdi+70h]
0x180004549  mov     r8d, r12d
0x18000454c  mov     r10d, edx
0x18000454f  imul    rcx, r10, 18Ch
0x180004556  mov     r9d, [rcx+rax+188h]
0x18000455e  mov     eax, edx
0x180004560  cmp     eax, 200h
0x180004565  jnb     short loc_1800045E5
0x180004567  lea     rcx, [rbx+rax*2]
0x18000456b  movzx   eax, byte ptr [rbx+rax*2]
0x18000456f  cmp     eax, r9d
0x180004572  jnb     short loc_1800045E5
0x180004574  inc     r8d
0x180004577  cmp     r8d, r9d
0x18000457a  ja      short loc_1800045E5
0x18000457c  movzx   eax, byte ptr [rcx+1]
0x180004580  test    eax, eax
0x180004582  jnz     short loc_180004560
0x180004584  inc     edx
0x180004586  cmp     edx, [rdi+78h]
0x180004589  jb      short loc_180004545
0x18000458b  mov     r9d, ebp
0x18000458e  mov     dword ptr [rsp+48h+var_28], r12d
0x180004593  mov     r8, r14
0x180004596  mov     rdx, rbx
0x180004599  mov     rcx, rdi
0x18000459c  call    GPDSeparateOptionArray
0x1800045a1  test    eax, eax
0x1800045a3  jz      short loc_1800045F5
0x1800045a5  mov     rcx, rbx; hMem
0x1800045a8  call    cs:__imp_LocalFree
0x1800045af  nop     dword ptr [rax+rax+00h]
0x1800045b4  mov     rcx, r15; hMem
0x1800045b7  call    cs:__imp_LocalFree
0x1800045be  nop     dword ptr [rax+rax+00h]
0x1800045c3  mov     r12, [rsp+48h+arg_18]
0x1800045c8  mov     rsi, [rsp+48h+arg_10]
0x1800045cd  mov     rbp, [rsp+48h+arg_8]
0x1800045d2  mov     rbx, [rsp+48h+arg_0]
0x1800045d7  mov     r15, [rsp+48h+var_18]
0x1800045dc  add     rsp, 38h
0x1800045e0  pop     r14
0x1800045e2  pop     rdi
0x1800045e3  retn
0x1800045e5  movzx   eax, byte ptr [r15+r10*2]
0x1800045ea  mov     [rbx+r10*2], al
0x1800045ee  mov     [rbx+r10*2+1], r12b
0x1800045f3  jmp     short loc_180004584
0x1800045f5  cmp     esi, ebp
0x1800045f7  jb      loc_180004691
0x1800045fd  mov     ecx, r12d
0x180004600  test    ebp, ebp
0x180004602  jnz     short loc_180004645
0x180004604  test    rbx, rbx
0x180004607  jnz     loc_180004698
0x18000460d  test    r15, r15
0x180004610  jz      short loc_1800045C3
0x180004612  jmp     short loc_1800045B4
0x180004614  lea     rdx, aValidatedocopt_0; "ValidateDocOptions: NULL  Option array "...
0x18000461b  lea     rcx, aGpdvalidatedoc; "GPDValidateDocOptions"
0x180004622  call    WriteDbgTraceErrorGpd
0x180004627  jmp     short loc_1800045DC
0x180004629  mov     r9d, esi
0x18000462c  lea     rdx, aValidatedocopt_1; "ValidateDocOptions: Option array too sm"...
0x180004633  mov     r8d, ebp
0x180004636  lea     rcx, aGpdvalidatedoc; "GPDValidateDocOptions"
0x18000463d  call    WriteDbgTraceErrorGpd
0x180004642  mov     ecx, r12d
0x180004645  mov     eax, ecx
0x180004647  inc     ecx
0x180004649  mov     [r14+rax*2], r12w
0x18000464e  cmp     ecx, ebp
0x180004650  jb      short loc_180004645
0x180004652  jmp     short loc_180004604
0x180004654  mov     r9d, 200h
0x18000465a  lea     rdx, aValidatedocopt; "ValidateDocOptions: Too many features: "...
0x180004661  lea     rcx, aGpdvalidatedoc; "GPDValidateDocOptions"
0x180004668  call    WriteDbgTraceErrorGpd
0x18000466d  jmp     short loc_1800045F5
0x18000466f  cmp     eax, esi
0x180004671  jb      short loc_180004688
0x180004673  cmp     [rbx+rax*2], r12b
0x180004677  jnz     short loc_180004688
0x180004679  mov     byte ptr [rbx+rax*2], 1
0x18000467d  movzx   eax, byte ptr [r14+rax*2+1]
0x180004683  jmp     loc_1800044EC
0x180004688  mov     [rdx+1], r12b
0x18000468c  jmp     loc_1800044F4
0x180004691  mov     ebp, esi
0x180004693  jmp     loc_1800045FD
0x180004698  mov     rcx, rbx; hMem
0x18000469b  call    cs:__imp_LocalFree
0x1800046a2  nop     dword ptr [rax+rax+00h]
0x1800046a7  jmp     loc_18000460D
```
