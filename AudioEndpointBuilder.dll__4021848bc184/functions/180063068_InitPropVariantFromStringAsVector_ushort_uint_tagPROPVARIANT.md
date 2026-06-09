# InitPropVariantFromStringAsVector(ushort *,uint,tagPROPVARIANT *)

- ea: `0x180063068`
- end: `0x180063226`
- name: `?InitPropVariantFromStringAsVector@@YAJPEAGIPEAUtagPROPVARIANT@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800322a0`

## callees

- `0x18000ceb0`
- `0x180010da8`
- `0x180024208`
- `0x18003f7a4`
- `0x180063068`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800630aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800630aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006318e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800631d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800631f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006318e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800631d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800631f4`

## string_xrefs

- `0x1800630c5`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180063163`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x1800631ae`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall InitPropVariantFromStringAsVector(unsigned __int16 *a1, int a2, struct tagPROPVARIANT *a3)
{
  int v5; // ecx
  unsigned __int16 *v6; // r8
  __int64 v8; // rcx
  _QWORD *v9; // rax
  unsigned int i; // ebx
  int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // esi
  int v15; // eax
  unsigned int v16; // ebx
  unsigned int k; // edx
  void *v18; // rcx
  unsigned int v19; // ebx
  unsigned int j; // edx
  void *v21; // rcx
  int v22; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  _QWORD *pv; // [rsp+70h] [rbp+30h]
  unsigned int v25; // [rsp+78h] [rbp+38h] BYREF
  unsigned __int64 v26; // [rsp+88h] [rbp+48h] BYREF

  v5 = 0;
  v6 = a1;
  while ( a2 )
  {
    --a2;
    if ( !*v6++ )
      ++v5;
  }
  v8 = (unsigned int)(v5 + 1);
  v25 = v8;
  v9 = CoTaskMemAlloc(8 * v8);
  pv = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 8LL * v25);
    for ( i = 0; i < v25; ++i )
    {
      v26 = 0;
      if ( !*a1 )
        break;
      v12 = StringCchLengthW(a1, 0x7FFFFFFFu, &v26);
      v14 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D6,
          (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
          (const char *)(unsigned int)v12,
          (int)&v25);
        v19 = 0;
        for ( j = v25; v19 < j; ++v19 )
        {
          v21 = (void *)pv[v19];
          if ( v21 )
          {
            CoTaskMemFree(v21);
            pv[v19] = 0;
            j = v25;
          }
        }
        goto LABEL_22;
      }
      v15 = _AllocString<CTCoAllocPolicy>(i, v13, a1, &pv[i]);
      v14 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D8,
          (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
          (const char *)(unsigned int)v15,
          (int)&v25);
        v16 = 0;
        for ( k = v25; v16 < k; ++v16 )
        {
          v18 = (void *)pv[v16];
          if ( v18 )
          {
            CoTaskMemFree(v18);
            pv[v16] = 0;
            k = v25;
          }
        }
LABEL_22:
        CoTaskMemFree(pv);
        return v14;
      }
      a1 += v26 + 1;
    }
    a3->vt = 4127;
    a3->lVal = i;
    a3->bstrblobVal.pData = (BYTE *)pv;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C4,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)0x8007000ELL,
      v22);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180063068  mov     [rsp-28h+arg_10], rbx
0x18006306d  push    rbp
0x18006306e  push    rsi
0x18006306f  push    rdi
0x180063070  push    r14
0x180063072  push    r15
0x180063074  mov     rbp, rsp
0x180063077  sub     rsp, 40h
0x18006307b  mov     r14, r8
0x18006307e  mov     rdi, rcx
0x180063081  xor     r15d, r15d
0x180063084  mov     ecx, r15d
0x180063087  mov     r8, rdi
0x18006308a  jmp     short loc_18006309D
0x18006308c  dec     edx
0x18006308e  movzx   eax, word ptr [r8]
0x180063092  lea     r8, [r8+2]
0x180063096  test    ax, ax
0x180063099  jnz     short loc_18006309D
0x18006309b  inc     ecx
0x18006309d  test    edx, edx
0x18006309f  jnz     short loc_18006308C
0x1800630a1  inc     ecx
0x1800630a3  mov     [rbp+arg_8], ecx
0x1800630a6  shl     rcx, 3; cb
0x1800630aa  call    cs:__imp_CoTaskMemAlloc
0x1800630b0  mov     [rbp+pv], rax
0x1800630b4  test    rax, rax
0x1800630b7  jnz     short loc_1800630DD
0x1800630b9  mov     rcx, [rbp+28h]; this
0x1800630bd  mov     ebx, 8007000Eh
0x1800630c2  mov     r9d, ebx; char *
0x1800630c5  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x1800630cc  mov     edx, 3C4h; void *
0x1800630d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800630d6  mov     eax, ebx
0x1800630d8  jmp     loc_180063212
0x1800630dd  mov     r8d, [rbp+arg_8]
0x1800630e1  shl     r8, 3; Size
0x1800630e5  xor     edx, edx; Val
0x1800630e7  mov     rcx, rax; void *
0x1800630ea  call    memset_0
0x1800630ef  lea     rax, [rbp+arg_8]
0x1800630f3  mov     [rbp+var_20], rax
0x1800630f7  lea     rax, [rbp+pv]
0x1800630fb  mov     [rbp+var_18], rax
0x1800630ff  mov     [rbp+var_10], 1
0x180063103  mov     ebx, r15d
0x180063106  cmp     ebx, [rbp+arg_8]
0x180063109  jnb     loc_1800631FE
0x18006310f  mov     [rbp+arg_18], r15
0x180063113  cmp     [rdi], r15w
0x180063117  jz      loc_1800631FE
0x18006311d  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x180063121  mov     edx, 7FFFFFFFh; unsigned __int64
0x180063126  mov     rcx, rdi; unsigned __int16 *
0x180063129  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006312e  mov     esi, eax
0x180063130  test    eax, eax
0x180063132  js      short loc_1800631A7
0x180063134  mov     ecx, ebx
0x180063136  mov     rax, [rbp+pv]
0x18006313a  lea     r9, [rax+rcx*8]
0x18006313e  mov     r8, rdi
0x180063141  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180063146  mov     esi, eax
0x180063148  test    eax, eax
0x18006314a  js      short loc_18006315C
0x18006314c  mov     rax, [rbp+arg_18]
0x180063150  lea     rdi, [rdi+rax*2]
0x180063154  add     rdi, 2
0x180063158  inc     ebx
0x18006315a  jmp     short loc_180063106
0x18006315c  mov     rcx, [rbp+28h]; this
0x180063160  mov     r9d, eax; char *
0x180063163  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x18006316a  mov     edx, 3D8h; void *
0x18006316f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063174  nop
0x180063175  mov     ebx, r15d
0x180063178  mov     edx, [rbp+arg_8]
0x18006317b  test    edx, edx
0x18006317d  jz      short loc_1800631F0
0x18006317f  mov     edi, ebx
0x180063181  mov     rax, [rbp+pv]
0x180063185  mov     rcx, [rax+rdi*8]; pv
0x180063189  test    rcx, rcx
0x18006318c  jz      short loc_18006319F
0x18006318e  call    cs:__imp_CoTaskMemFree
0x180063194  mov     rax, [rbp+pv]
0x180063198  mov     [rax+rdi*8], r15
0x18006319c  mov     edx, [rbp+arg_8]
0x18006319f  inc     ebx
0x1800631a1  cmp     ebx, edx
0x1800631a3  jb      short loc_18006317F
0x1800631a5  jmp     short loc_1800631F0
0x1800631a7  mov     rcx, [rbp+28h]; this
0x1800631ab  mov     r9d, eax; char *
0x1800631ae  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x1800631b5  mov     edx, 3D6h; void *
0x1800631ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800631bf  nop
0x1800631c0  mov     ebx, r15d
0x1800631c3  mov     edx, [rbp+arg_8]
0x1800631c6  test    edx, edx
0x1800631c8  jz      short loc_1800631F0
0x1800631ca  mov     edi, ebx
0x1800631cc  mov     rax, [rbp+pv]
0x1800631d0  mov     rcx, [rax+rdi*8]; pv
0x1800631d4  test    rcx, rcx
0x1800631d7  jz      short loc_1800631EA
0x1800631d9  call    cs:__imp_CoTaskMemFree
0x1800631df  mov     rax, [rbp+pv]
0x1800631e3  mov     [rax+rdi*8], r15
0x1800631e7  mov     edx, [rbp+arg_8]
0x1800631ea  inc     ebx
0x1800631ec  cmp     ebx, edx
0x1800631ee  jb      short loc_1800631CA
0x1800631f0  mov     rcx, [rbp+pv]; pv
0x1800631f4  call    cs:__imp_CoTaskMemFree
0x1800631fa  mov     eax, esi
0x1800631fc  jmp     short loc_180063212
0x1800631fe  mov     word ptr [r14], 101Fh
0x180063204  mov     [r14+8], ebx
0x180063208  mov     rax, [rbp+pv]
0x18006320c  mov     [r14+10h], rax
0x180063210  xor     eax, eax
0x180063212  mov     rbx, [rsp+40h+arg_10]
0x18006321a  add     rsp, 40h
0x18006321e  pop     r15
0x180063220  pop     r14
0x180063222  pop     rdi
0x180063223  pop     rsi
0x180063224  pop     rbp
0x180063225  retn
```
