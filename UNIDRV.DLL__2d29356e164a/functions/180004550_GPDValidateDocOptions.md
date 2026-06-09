# GPDValidateDocOptions

- ea: `0x180004550`
- end: `0x1800047b9`
- name: `GPDValidateDocOptions`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180033ce0`

## callees

- `0x180004550`
- `0x18000490c`
- `0x180005100`
- `0x180005bf0`
- `0x180007220`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800046c8`
- `KERNEL32!LocalFree` at `0x1800046d1`
- `KERNEL32!LocalFree` at `0x1800047ae`
- `KERNEL32!LocalFree` at `0x1800046c8`
- `KERNEL32!LocalFree` at `0x1800046d1`
- `KERNEL32!LocalFree` at `0x1800047ae`
- `KERNEL32!LocalAlloc` at `0x1800045b1`
- `KERNEL32!LocalAlloc` at `0x1800045c1`
- `KERNEL32!LocalAlloc` at `0x1800045b1`
- `KERNEL32!LocalAlloc` at `0x1800045c1`

## string_xrefs

- `0x18000476d`: `ValidateDocOptions: Too many features: %d features defined (MAX_COMBINED_OPTIONS = %d)`

## pseudocode

```c
__int64 __fastcall GPDValidateDocOptions(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebp
  unsigned int v5; // esi
  _BYTE *v6; // rbx
  unsigned __int8 *v7; // r15
  unsigned int v8; // r8d
  __int64 result; // rax
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

  if ( !a2 )
    return WriteDbgTraceErrorGpd(
             (__int64)"GPDValidateDocOptions",
             "ValidateDocOptions: NULL  Option array not permitted.");
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
      result = i;
      *(_WORD *)(a2 + 2 * result) = 0;
    }
    goto LABEL_30;
  }
  v8 = *(_DWORD *)(a1 + 120);
  if ( v8 > 0x200 )
  {
    result = WriteDbgTraceErrorGpd(
               (__int64)"GPDValidateDocOptions",
               "ValidateDocOptions: Too many features: %d features defined (MAX_COMBINED_OPTIONS = %d)",
               v8,
               512);
  }
  else
  {
    v6 = LocalAlloc(0, 0x400u);
    result = (__int64)LocalAlloc(0, 0x400u);
    v7 = (unsigned __int8 *)result;
    if ( v6 && result )
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
      result = (unsigned int)(*(_DWORD *)(a1 + 20) + *(_DWORD *)(a1 + 24));
      if ( (unsigned int)result <= 0x200 )
      {
        result = BinitDefaultOptionArray(v7, a1);
        if ( (_DWORD)result )
        {
          result = GPDCombineOptionArray(a1, (__int64)v6, 256, a2, 0);
          if ( (_DWORD)result )
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
            result = GPDSeparateOptionArray(a1, (_DWORD)v6, a2, 256, 0);
            if ( (_DWORD)result )
            {
              LocalFree(v6);
              return (__int64)LocalFree(v7);
            }
          }
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
    result = (__int64)LocalFree(v6);
  if ( v7 )
    return (__int64)LocalFree(v7);
  return result;
}

```

## disassembly

```asm
0x180004550  push    rdi
0x180004552  push    r14
0x180004554  sub     rsp, 38h
0x180004558  mov     r14, rdx
0x18000455b  mov     rdi, rcx
0x18000455e  test    rdx, rdx
0x180004561  jz      loc_180004727
0x180004567  mov     [rsp+48h+arg_0], rbx
0x18000456c  mov     [rsp+48h+arg_8], rbp
0x180004571  mov     ebp, 100h
0x180004576  mov     [rsp+48h+arg_10], rsi
0x18000457b  mov     esi, [rcx+14h]
0x18000457e  mov     [rsp+48h+arg_18], r12
0x180004583  xor     r12d, r12d
0x180004586  mov     [rsp+48h+var_18], r15
0x18000458b  mov     ebx, r12d
0x18000458e  mov     r15d, r12d
0x180004591  cmp     esi, ebp
0x180004593  ja      loc_18000473C
0x180004599  mov     r8d, [rcx+78h]
0x18000459d  cmp     r8d, 200h
0x1800045a4  ja      loc_180004767
0x1800045aa  mov     edx, 400h; uBytes
0x1800045af  xor     ecx, ecx; uFlags
0x1800045b1  call    cs:__imp_LocalAlloc
0x1800045b7  mov     edx, 400h; uBytes
0x1800045bc  xor     ecx, ecx; uFlags
0x1800045be  mov     rbx, rax
0x1800045c1  call    cs:__imp_LocalAlloc
0x1800045c7  mov     r15, rax
0x1800045ca  test    rbx, rbx
0x1800045cd  jz      loc_180004708
0x1800045d3  test    rax, rax
0x1800045d6  jz      loc_180004708
0x1800045dc  mov     ecx, esi
0x1800045de  xchg    ax, ax
0x1800045e0  mov     edx, ecx
0x1800045e2  inc     ecx
0x1800045e4  mov     [rbx+rdx*2], r12b
0x1800045e8  cmp     ecx, 200h
0x1800045ee  jb      short loc_1800045E0
0x1800045f0  mov     ecx, r12d
0x1800045f3  test    esi, esi
0x1800045f5  jz      short loc_18000461A
0x1800045f7  nop     word ptr [rax+rax+00000000h]
0x180004600  mov     eax, ecx
0x180004602  lea     rdx, [r14+rax*2]
0x180004606  movzx   eax, byte ptr [r14+rax*2+1]
0x18000460c  test    eax, eax
0x18000460e  jnz     loc_180004782
0x180004614  inc     ecx
0x180004616  cmp     ecx, esi
0x180004618  jb      short loc_180004600
0x18000461a  mov     eax, [rdi+18h]
0x18000461d  add     eax, [rdi+14h]
0x180004620  cmp     eax, 200h
0x180004625  ja      loc_180004708
0x18000462b  mov     rdx, rdi
0x18000462e  mov     rcx, r15
0x180004631  call    BinitDefaultOptionArray
0x180004636  test    eax, eax
0x180004638  jz      loc_180004708
0x18000463e  mov     r9, r14
0x180004641  mov     [rsp+48h+var_28], r12
0x180004646  mov     r8d, ebp
0x180004649  mov     rdx, rbx
0x18000464c  mov     rcx, rdi
0x18000464f  call    GPDCombineOptionArray
0x180004654  test    eax, eax
0x180004656  jz      loc_180004708
0x18000465c  mov     edx, r12d
0x18000465f  cmp     [rdi+78h], r12d
0x180004663  jbe     short loc_1800046AB
0x180004665  mov     rax, [rdi+70h]
0x180004669  mov     r8d, r12d
0x18000466c  mov     r10d, edx
0x18000466f  imul    rcx, r10, 18Ch
0x180004676  mov     r9d, [rcx+rax+188h]
0x18000467e  mov     eax, edx
0x180004680  cmp     eax, 200h
0x180004685  jnb     short loc_1800046F8
0x180004687  lea     rcx, [rbx+rax*2]
0x18000468b  movzx   eax, byte ptr [rbx+rax*2]
0x18000468f  cmp     eax, r9d
0x180004692  jnb     short loc_1800046F8
0x180004694  inc     r8d
0x180004697  cmp     r8d, r9d
0x18000469a  ja      short loc_1800046F8
0x18000469c  movzx   eax, byte ptr [rcx+1]
0x1800046a0  test    eax, eax
0x1800046a2  jnz     short loc_180004680
0x1800046a4  inc     edx
0x1800046a6  cmp     edx, [rdi+78h]
0x1800046a9  jb      short loc_180004665
0x1800046ab  mov     r9d, ebp
0x1800046ae  mov     dword ptr [rsp+48h+var_28], r12d
0x1800046b3  mov     r8, r14
0x1800046b6  mov     rdx, rbx
0x1800046b9  mov     rcx, rdi
0x1800046bc  call    GPDSeparateOptionArray
0x1800046c1  test    eax, eax
0x1800046c3  jz      short loc_180004708
0x1800046c5  mov     rcx, rbx; hMem
0x1800046c8  call    cs:__imp_LocalFree
0x1800046ce  mov     rcx, r15; hMem
0x1800046d1  call    cs:__imp_LocalFree
0x1800046d7  mov     r12, [rsp+48h+arg_18]
0x1800046dc  mov     rsi, [rsp+48h+arg_10]
0x1800046e1  mov     rbp, [rsp+48h+arg_8]
0x1800046e6  mov     rbx, [rsp+48h+arg_0]
0x1800046eb  mov     r15, [rsp+48h+var_18]
0x1800046f0  add     rsp, 38h
0x1800046f4  pop     r14
0x1800046f6  pop     rdi
0x1800046f7  retn
0x1800046f8  movzx   eax, byte ptr [r15+r10*2]
0x1800046fd  mov     [rbx+r10*2], al
0x180004701  mov     [rbx+r10*2+1], r12b
0x180004706  jmp     short loc_1800046A4
0x180004708  cmp     esi, ebp
0x18000470a  jb      loc_1800047A4
0x180004710  mov     ecx, r12d
0x180004713  test    ebp, ebp
0x180004715  jnz     short loc_180004758
0x180004717  test    rbx, rbx
0x18000471a  jnz     loc_1800047AB
0x180004720  test    r15, r15
0x180004723  jz      short loc_1800046D7
0x180004725  jmp     short loc_1800046CE
0x180004727  lea     rdx, aValidatedocopt_0; "ValidateDocOptions: NULL  Option array "...
0x18000472e  lea     rcx, aGpdvalidatedoc; "GPDValidateDocOptions"
0x180004735  call    WriteDbgTraceErrorGpd
0x18000473a  jmp     short loc_1800046F0
0x18000473c  mov     r9d, esi
0x18000473f  lea     rdx, aValidatedocopt_1; "ValidateDocOptions: Option array too sm"...
0x180004746  mov     r8d, ebp
0x180004749  lea     rcx, aGpdvalidatedoc; "GPDValidateDocOptions"
0x180004750  call    WriteDbgTraceErrorGpd
0x180004755  mov     ecx, r12d
0x180004758  mov     eax, ecx
0x18000475a  inc     ecx
0x18000475c  mov     [r14+rax*2], r12w
0x180004761  cmp     ecx, ebp
0x180004763  jb      short loc_180004758
0x180004765  jmp     short loc_180004717
0x180004767  mov     r9d, 200h
0x18000476d  lea     rdx, aValidatedocopt; "ValidateDocOptions: Too many features: "...
0x180004774  lea     rcx, aGpdvalidatedoc; "GPDValidateDocOptions"
0x18000477b  call    WriteDbgTraceErrorGpd
0x180004780  jmp     short loc_180004708
0x180004782  cmp     eax, esi
0x180004784  jb      short loc_18000479B
0x180004786  cmp     [rbx+rax*2], r12b
0x18000478a  jnz     short loc_18000479B
0x18000478c  mov     byte ptr [rbx+rax*2], 1
0x180004790  movzx   eax, byte ptr [r14+rax*2+1]
0x180004796  jmp     loc_18000460C
0x18000479b  mov     [rdx+1], r12b
0x18000479f  jmp     loc_180004614
0x1800047a4  mov     ebp, esi
0x1800047a6  jmp     loc_180004710
0x1800047ab  mov     rcx, rbx; hMem
0x1800047ae  call    cs:__imp_LocalFree
0x1800047b4  jmp     loc_180004720
```
