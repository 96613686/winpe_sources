# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(_GUID const &,ushort const *)

- ea: `0x180007850`
- end: `0x180007bca`
- name: `?SetString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `890`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180007850`
- `0x1800170b4`
- `0x1800170c0`
- `0x180017e20`
- `0x1800594bc`
- `0x1800594c8`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007980`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007980`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007877`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007908`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007877`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007908`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007b85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007b85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007a46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007a46`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(
        __int64 a1,
        unsigned int *a2,
        _WORD *a3)
{
  int v6; // r15d
  __int64 v7; // rbx
  int v8; // r8d
  unsigned int v9; // r9d
  __int64 v10; // rdi
  int v11; // r11d
  int v12; // eax
  int v13; // r10d
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdi
  int v17; // edi
  unsigned int v18; // edi
  char *v19; // r15
  __int64 v20; // rcx
  unsigned int v21; // edx
  __int64 k; // r10
  __int64 v23; // rdi
  unsigned __int64 v25; // rbx
  void *v26; // rax
  unsigned int v27; // ebp
  int i; // r13d
  __int64 v30; // rax
  int v31; // r10d
  __int64 v32; // rax
  int j; // r10d
  __int64 v34; // rax
  __int64 v35; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v6 = *(_DWORD *)(a1 + 60);
  v7 = -1;
  v8 = v6;
  if ( v6 )
  {
    v9 = *a2;
    if ( v6 < 4 )
    {
      v31 = 0;
      while ( v31 < v6 )
      {
        v32 = *(_QWORD *)(a1 + 48);
        v14 = v32 + 40LL * v31;
        if ( *(_DWORD *)v14 == v9 )
        {
          v35 = *(_QWORD *)a2 - *(_QWORD *)v14;
          if ( *(_QWORD *)a2 == *(_QWORD *)v14 )
            v35 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + 8);
          if ( !v35 )
            goto LABEL_9;
          ++v31;
        }
        else
        {
          if ( *(_DWORD *)(v32 + 40LL * v31) > v9 )
            break;
          ++v31;
        }
      }
    }
    else
    {
      v10 = *(_QWORD *)(a1 + 48);
      v11 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v12 = (v11 + v8) / 2;
          v13 = v12;
          v14 = v10 + 40LL * v12;
          if ( v9 >= *(_DWORD *)v14 )
            break;
          if ( v12 == v11 )
            goto LABEL_10;
          v8 = (v11 + v8) / 2;
        }
        if ( v9 <= *(_DWORD *)(v10 + 40LL * v12) )
          break;
        v11 = v12 + 1;
        if ( v12 + 1 == v8 )
          goto LABEL_10;
      }
      v15 = *(_QWORD *)a2 - *(_QWORD *)v14;
      if ( *(_QWORD *)a2 == *(_QWORD *)v14 )
        v15 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + 8);
      if ( v15 )
      {
        if ( v13 > v11 )
        {
          for ( i = v13 - 1; i >= v11; --i )
          {
            v14 = v10 + 40LL * i;
            if ( v9 != *(_DWORD *)v14 )
              break;
            v30 = *(_QWORD *)a2 - *(_QWORD *)v14;
            if ( *(_QWORD *)a2 == *(_QWORD *)v14 )
              v30 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + 8);
            if ( !v30 )
              goto LABEL_9;
          }
        }
        for ( j = v13 + 1; j < v8; ++j )
        {
          v14 = v10 + 40LL * j;
          if ( v9 != *(_DWORD *)v14 )
            break;
          v34 = *(_QWORD *)a2 - *(_QWORD *)v14;
          if ( *(_QWORD *)a2 == *(_QWORD *)v14 )
            v34 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + 8);
          if ( !v34 )
            goto LABEL_9;
        }
      }
      else
      {
LABEL_9:
        v16 = v14 + 16;
        if ( v14 != -16 )
        {
          PropVariantClear((PROPVARIANT *)(v14 + 16));
          goto LABEL_19;
        }
      }
    }
  }
LABEL_10:
  v17 = *(_DWORD *)(a1 + 56);
  if ( v6 != v17 )
  {
LABEL_15:
    v21 = *(_DWORD *)(a1 + 60);
    for ( k = 0; (unsigned int)k < v21; k = (unsigned int)(k + 1) )
    {
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 48) + 40 * k) >= *a2 )
        break;
    }
    v23 = 40 * k;
    memmove_0(
      (void *)(*(_QWORD *)(a1 + 48) + 40LL * (unsigned int)(k + 1)),
      (const void *)(40 * k + *(_QWORD *)(a1 + 48)),
      40LL * (v21 - (unsigned int)k));
    *(_OWORD *)(*(_QWORD *)(a1 + 48) + v23) = *(_OWORD *)a2;
    v16 = *(_QWORD *)(a1 + 48) + 16LL + v23;
    *(_OWORD *)v16 = 0;
    *(_QWORD *)(v16 + 16) = 0;
    ++*(_DWORD *)(a1 + 60);
    goto LABEL_19;
  }
  v18 = 2 * v17 + 4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( v18 <= *(_DWORD *)(a1 + 56) )
  {
LABEL_14:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    goto LABEL_15;
  }
  v19 = (char *)operator new[](saturated_mul(v18, 0x28u));
  if ( v19 )
  {
    memcpy_0(v19, *(const void **)(a1 + 48), 40LL * *(unsigned int *)(a1 + 60));
    operator delete(*(void **)(a1 + 48));
    v20 = *(unsigned int *)(a1 + 60);
    *(_DWORD *)(a1 + 56) = v18;
    *(_QWORD *)(a1 + 48) = v19;
    memset_0(&v19[40 * v20], 0, 40LL * (v18 - (unsigned int)v20));
    goto LABEL_14;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v16 = 0;
LABEL_19:
  if ( !a3 )
    goto LABEL_56;
  if ( !v16 )
  {
LABEL_58:
    v27 = -2147024882;
    goto LABEL_25;
  }
  while ( a3[++v7] != 0 )
    ;
  v25 = 2 * v7 + 2;
  if ( v25 >= 0xFFFFFFFF )
  {
LABEL_56:
    v27 = -2147024809;
    goto LABEL_25;
  }
  v26 = CoTaskMemAlloc((unsigned int)v25);
  *(_QWORD *)(v16 + 8) = v26;
  if ( !v26 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 152LL))(a1, a2);
    goto LABEL_58;
  }
  v27 = 0;
  memcpy_0(v26, a3, (unsigned int)v25);
  *(_WORD *)v16 = 31;
  *(_DWORD *)(a1 + 64) = 1;
LABEL_25:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v27;
}

```

## disassembly

```asm
0x180007850  mov     [rsp+arg_10], rbx
0x180007855  push    rbp
0x180007856  push    rsi
0x180007857  push    rdi
0x180007858  push    r12
0x18000785a  push    r14
0x18000785c  sub     rsp, 20h
0x180007860  mov     r14, rcx
0x180007863  mov     [rsp+48h+arg_0], r13
0x180007868  add     rcx, 8; lpCriticalSection
0x18000786c  mov     [rsp+48h+arg_8], r15
0x180007871  mov     rsi, r8
0x180007874  mov     rbp, rdx
0x180007877  call    cs:__imp_EnterCriticalSection
0x18000787d  mov     r15d, [r14+3Ch]
0x180007881  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007888  mov     r8d, r15d
0x18000788b  test    r15d, r15d
0x18000788e  jz      short loc_1800078F0
0x180007890  mov     r9d, [rbp+0]
0x180007894  cmp     r15d, 4
0x180007898  jl      loc_180007AD1
0x18000789e  mov     rdi, [r14+30h]
0x1800078a2  xor     r11d, r11d
0x1800078a5  lea     eax, [r11+r8]
0x1800078a9  cdq
0x1800078aa  sub     eax, edx
0x1800078ac  sar     eax, 1
0x1800078ae  movsxd  r10, eax
0x1800078b1  lea     rdx, [r10+r10*4]
0x1800078b5  cmp     r9d, [rdi+rdx*8]
0x1800078b9  lea     rdx, [rdi+rdx*8]
0x1800078bd  jb      loc_180007B3D
0x1800078c3  ja      loc_180007B4E
0x1800078c9  mov     rax, [rbp+0]
0x1800078cd  sub     rax, [rdx]
0x1800078d0  jnz     short loc_1800078DA
0x1800078d2  mov     rax, [rbp+8]
0x1800078d6  sub     rax, [rdx+8]
0x1800078da  test    rax, rax
0x1800078dd  jnz     loc_180007A93
0x1800078e3  lea     rdi, [rdx+10h]
0x1800078e7  test    rdi, rdi
0x1800078ea  jnz     loc_180007B82
0x1800078f0  mov     edi, [r14+38h]
0x1800078f4  cmp     r15d, edi
0x1800078f7  jnz     loc_180007986
0x1800078fd  lea     rcx, [r14+8]; lpCriticalSection
0x180007901  lea     edi, ds:4[rdi*2]
0x180007908  call    cs:__imp_EnterCriticalSection
0x18000790e  cmp     edi, [r14+38h]
0x180007912  jbe     short loc_18000797C
0x180007914  mov     ecx, edi
0x180007916  mov     eax, 28h ; '('
0x18000791b  mul     rcx
0x18000791e  cmovb   rax, rbx
0x180007922  mov     rcx, rax; unsigned __int64
0x180007925  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000792a  mov     r15, rax
0x18000792d  test    rax, rax
0x180007930  jz      loc_180007B90
0x180007936  mov     eax, [r14+3Ch]
0x18000793a  mov     rcx, r15; void *
0x18000793d  mov     rdx, [r14+30h]; Src
0x180007941  lea     r8, [rax+rax*4]
0x180007945  shl     r8, 3; Size
0x180007949  call    memcpy_0
0x18000794e  mov     rcx, [r14+30h]; Block
0x180007952  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007957  mov     ecx, [r14+3Ch]
0x18000795b  xor     edx, edx; Val
0x18000795d  mov     [r14+38h], edi
0x180007961  sub     edi, ecx
0x180007963  mov     [r14+30h], r15
0x180007967  lea     rax, [rcx+rcx*4]
0x18000796b  lea     r8, [rdi+rdi*4]
0x18000796f  shl     r8, 3; Size
0x180007973  lea     rcx, [r15+rax*8]; void *
0x180007977  call    memset_0
0x18000797c  lea     rcx, [r14+8]; lpCriticalSection
0x180007980  call    cs:__imp_LeaveCriticalSection
0x180007986  mov     edx, [r14+3Ch]
0x18000798a  xor     r10d, r10d
0x18000798d  test    edx, edx
0x18000798f  jz      short loc_1800079AB
0x180007991  mov     r8d, [rbp+0]
0x180007995  mov     r9, [r14+30h]
0x180007999  lea     rcx, [r10+r10*4]
0x18000799d  cmp     [r9+rcx*8], r8d
0x1800079a1  jnb     short loc_1800079AB
0x1800079a3  inc     r10d
0x1800079a6  cmp     r10d, edx
0x1800079a9  jb      short loc_180007999
0x1800079ab  mov     r9, [r14+30h]
0x1800079af  lea     rcx, [r10+r10*4]
0x1800079b3  sub     edx, r10d
0x1800079b6  lea     rdi, ds:0[rcx*8]
0x1800079be  lea     eax, [r10+1]
0x1800079c2  lea     rax, [rax+rax*4]
0x1800079c6  lea     rcx, [r9+rax*8]; void *
0x1800079ca  lea     r8, [rdx+rdx*4]
0x1800079ce  shl     r8, 3; Size
0x1800079d2  lea     rdx, [rdi+r9]; Src
0x1800079d6  call    memmove_0
0x1800079db  movups  xmm0, xmmword ptr [rbp+0]
0x1800079df  mov     rax, [r14+30h]
0x1800079e3  movups  xmmword ptr [rax+rdi], xmm0
0x1800079e7  mov     rax, [r14+30h]
0x1800079eb  add     rax, 10h
0x1800079ef  xorps   xmm0, xmm0
0x1800079f2  add     rdi, rax
0x1800079f5  xor     eax, eax
0x1800079f7  movups  xmmword ptr [rdi], xmm0
0x1800079fa  mov     [rdi+10h], rax
0x1800079fe  inc     dword ptr [r14+3Ch]
0x180007a02  mov     r15, [rsp+48h+arg_8]
0x180007a07  mov     r13, [rsp+48h+arg_0]
0x180007a0c  test    rsi, rsi
0x180007a0f  jz      loc_180007BA1
0x180007a15  test    rdi, rdi
0x180007a18  jz      loc_180007BC0
0x180007a1e  xchg    ax, ax
0x180007a20  cmp     word ptr [rsi+rbx*2+2], 0
0x180007a26  lea     rbx, [rbx+1]
0x180007a2a  jnz     short loc_180007A20
0x180007a2c  lea     rbx, ds:2[rbx*2]
0x180007a34  mov     eax, 0FFFFFFFFh
0x180007a39  cmp     rbx, rax
0x180007a3c  jnb     loc_180007BA1
0x180007a42  mov     ebx, ebx
0x180007a44  mov     ecx, ebx; cb
0x180007a46  call    cs:__imp_CoTaskMemAlloc
0x180007a4c  mov     [rdi+8], rax
0x180007a50  test    rax, rax
0x180007a53  jz      loc_180007BAB
0x180007a59  xor     ebp, ebp
0x180007a5b  mov     r8d, ebx; Size
0x180007a5e  mov     rdx, rsi; Src
0x180007a61  mov     rcx, rax; void *
0x180007a64  call    memcpy_0
0x180007a69  mov     word ptr [rdi], 1Fh
0x180007a6e  mov     dword ptr [r14+40h], 1
0x180007a76  lea     rcx, [r14+8]; lpCriticalSection
0x180007a7a  call    cs:__imp_LeaveCriticalSection
0x180007a80  mov     rbx, [rsp+48h+arg_10]
0x180007a85  mov     eax, ebp
0x180007a87  add     rsp, 20h
0x180007a8b  pop     r14
0x180007a8d  pop     r12
0x180007a8f  pop     rdi
0x180007a90  pop     rsi
0x180007a91  pop     rbp
0x180007a92  retn
0x180007a93  cmp     r10d, r11d
0x180007a96  jle     short loc_180007AFD
0x180007a98  lea     r13d, [r10-1]
0x180007a9c  cmp     r13d, r11d
0x180007a9f  jl      short loc_180007AFD
0x180007aa1  movsxd  rax, r13d
0x180007aa4  lea     rcx, [rax+rax*4]
0x180007aa8  cmp     r9d, [rdi+rcx*8]
0x180007aac  lea     rdx, [rdi+rcx*8]
0x180007ab0  jnz     short loc_180007AFD
0x180007ab2  mov     rax, [rbp+0]
0x180007ab6  sub     rax, [rdx]
0x180007ab9  jnz     short loc_180007AC3
0x180007abb  mov     rax, [rbp+8]
0x180007abf  sub     rax, [rdx+8]
0x180007ac3  test    rax, rax
0x180007ac6  jz      loc_1800078E3
0x180007acc  dec     r13d
0x180007acf  jmp     short loc_180007A9C
0x180007ad1  xor     r10d, r10d
0x180007ad4  cmp     r10d, r15d
0x180007ad7  jge     loc_1800078F0
0x180007add  movsxd  rax, r10d
0x180007ae0  lea     rcx, [rax+rax*4]
0x180007ae4  mov     rax, [r14+30h]
0x180007ae8  cmp     [rax+rcx*8], r9d
0x180007aec  lea     rdx, [rax+rcx*8]
0x180007af0  jz      short loc_180007B60
0x180007af2  ja      loc_1800078F0
0x180007af8  inc     r10d
0x180007afb  jmp     short loc_180007AD4
0x180007afd  inc     r10d
0x180007b00  cmp     r10d, r8d
0x180007b03  jge     loc_1800078F0
0x180007b09  movsxd  rax, r10d
0x180007b0c  lea     rcx, [rax+rax*4]
0x180007b10  cmp     r9d, [rdi+rcx*8]
0x180007b14  lea     rdx, [rdi+rcx*8]
0x180007b18  jnz     loc_1800078F0
0x180007b1e  mov     rax, [rbp+0]
0x180007b22  sub     rax, [rdx]
0x180007b25  jnz     short loc_180007B2F
0x180007b27  mov     rax, [rbp+8]
0x180007b2b  sub     rax, [rdx+8]
0x180007b2f  test    rax, rax
0x180007b32  jz      loc_1800078E3
0x180007b38  inc     r10d
0x180007b3b  jmp     short loc_180007B00
0x180007b3d  cmp     r10d, r11d
0x180007b40  jz      loc_1800078F0
0x180007b46  mov     r8d, r10d
0x180007b49  jmp     loc_1800078A5
0x180007b4e  lea     r11d, [r10+1]
0x180007b52  cmp     r11d, r8d
0x180007b55  jnz     loc_1800078A5
0x180007b5b  jmp     loc_1800078F0
0x180007b60  mov     rax, [rbp+0]
0x180007b64  sub     rax, [rdx]
0x180007b67  jnz     short loc_180007B71
0x180007b69  mov     rax, [rbp+8]
0x180007b6d  sub     rax, [rdx+8]
0x180007b71  test    rax, rax
0x180007b74  jz      loc_1800078E3
0x180007b7a  inc     r10d
0x180007b7d  jmp     loc_180007AD4
0x180007b82  mov     rcx, rdi; pvar
0x180007b85  call    cs:__imp_PropVariantClear
0x180007b8b  jmp     loc_180007A02
0x180007b90  lea     rcx, [r14+8]; lpCriticalSection
0x180007b94  call    cs:__imp_LeaveCriticalSection
0x180007b9a  xor     edi, edi
0x180007b9c  jmp     loc_180007A02
0x180007ba1  mov     ebp, 80070057h
0x180007ba6  jmp     loc_180007A76
0x180007bab  mov     rax, [r14]
0x180007bae  mov     rdx, rbp
0x180007bb1  mov     rcx, r14
0x180007bb4  mov     rax, [rax+98h]
0x180007bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc0  mov     ebp, 8007000Eh
0x180007bc5  jmp     loc_180007A76
```
