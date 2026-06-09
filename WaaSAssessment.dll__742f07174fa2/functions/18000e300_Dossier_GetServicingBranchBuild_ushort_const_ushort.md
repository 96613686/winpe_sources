# Dossier::GetServicingBranchBuild(ushort const *,ushort * *)

- ea: `0x18000e300`
- end: `0x18000e430`
- name: `?GetServicingBranchBuild@Dossier@@UEAAJPEBGPEAPEAG@Z`
- size: `304`
- prototype: `int(Dossier *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b2d8`
- `0x18000e300`
- `0x18000efec`
- `0x180018a50`
- `0x18001972e`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e3e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e3e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e332`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e332`

## pseudocode

```c
__int64 __fastcall Dossier::GetServicingBranchBuild(Dossier *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx
  unsigned int v8; // edi
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned int v13; // [rsp+20h] [rbp-38h]
  unsigned int v14; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v15[9]; // [rsp+34h] [rbp-24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v17; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v18; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  v18 = 0;
  v17 = 0;
  v15[0] = 0;
  *a3 = 0;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
  v7 = v6;
  if ( v6 )
    memset_0(v6, 0, 0x208u);
  if ( (unsigned int)GetVersionElements(a2, &v14, &v18, &v17, v15) == 4 )
  {
    v13 = v18;
    v9 = StringCchPrintfW(v7, 0x104u, L"%d.%d.%d.SB", v14);
    v8 = v9;
    if ( v9 >= 0 )
    {
      if ( v7 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v7[v11] );
        v7 = (unsigned __int16 *)CoTaskMemRealloc(v7, 2LL * (unsigned int)(v11 + 1));
      }
      v9 = (*(__int64 (__fastcall **)(Dossier *, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)this + 48LL))(
             this,
             v7,
             a3);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v8 = 0;
        goto LABEL_15;
      }
      v10 = 545;
    }
    else
    {
      v10 = 541;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)v9,
      v13);
  }
  else
  {
    v8 = -2147024119;
  }
LABEL_15:
  CoTaskMemFree(v7);
  return v8;
}

```

## disassembly

```asm
0x18000e300  mov     rax, rsp
0x18000e303  mov     [rax+8], rbx
0x18000e307  mov     [rax+10h], rbp
0x18000e30b  push    rsi
0x18000e30c  push    rdi
0x18000e30d  push    r14
0x18000e30f  sub     rsp, 40h
0x18000e313  xor     ebp, ebp
0x18000e315  mov     r14, rcx
0x18000e318  mov     ecx, 208h; cb
0x18000e31d  mov     [rax-28h], ebp
0x18000e320  mov     [rax+20h], ebp
0x18000e323  mov     rsi, r8
0x18000e326  mov     [rax+18h], ebp
0x18000e329  mov     rdi, rdx
0x18000e32c  mov     [rax-24h], ebp
0x18000e32f  mov     [r8], rbp
0x18000e332  call    cs:__imp_CoTaskMemAlloc
0x18000e338  mov     rbx, rax
0x18000e33b  test    rax, rax
0x18000e33e  jz      short loc_18000E350
0x18000e340  xor     edx, edx; Val
0x18000e342  mov     r8d, 208h; Size
0x18000e348  mov     rcx, rax; void *
0x18000e34b  call    memset_0
0x18000e350  lea     rax, [rsp+58h+var_24]
0x18000e355  mov     rcx, rdi; unsigned __int16 *
0x18000e358  lea     r9, [rsp+58h+arg_10]; unsigned int *
0x18000e35d  mov     [rsp+58h+var_38], rax; unsigned int *
0x18000e362  lea     r8, [rsp+58h+arg_18]; unsigned int *
0x18000e367  lea     rdx, [rsp+58h+var_28]; unsigned int *
0x18000e36c  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x18000e371  cmp     eax, 4
0x18000e374  jz      short loc_18000E380
0x18000e376  mov     edi, 80070309h
0x18000e37b  jmp     loc_18000E412
0x18000e380  mov     ecx, [rsp+58h+arg_18]
0x18000e384  lea     r8, aDDDSb; "%d.%d.%d.SB"
0x18000e38b  mov     eax, [rsp+58h+arg_10]
0x18000e38f  mov     edx, 104h; unsigned __int64
0x18000e394  mov     r9d, [rsp+58h+var_28]
0x18000e399  mov     [rsp+58h+var_30], eax
0x18000e39d  mov     dword ptr [rsp+58h+var_38], ecx; int
0x18000e3a1  mov     rcx, rbx; unsigned __int16 *
0x18000e3a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e3a9  mov     edi, eax
0x18000e3ab  test    eax, eax
0x18000e3ad  jns     short loc_18000E3CA
0x18000e3af  mov     edx, 21Dh; void *
0x18000e3b4  mov     rcx, [rsp+58h]; this
0x18000e3b9  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000e3c0  mov     r9d, eax; char *
0x18000e3c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3c8  jmp     short loc_18000E412
0x18000e3ca  test    rbx, rbx
0x18000e3cd  jz      short loc_18000E3EE
0x18000e3cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e3d3  inc     rax
0x18000e3d6  cmp     [rbx+rax*2], bp
0x18000e3da  jnz     short loc_18000E3D3
0x18000e3dc  lea     edx, [rax+1]
0x18000e3df  mov     rcx, rbx; pv
0x18000e3e2  add     rdx, rdx; cb
0x18000e3e5  call    cs:__imp_CoTaskMemRealloc
0x18000e3eb  mov     rbx, rax
0x18000e3ee  mov     rax, [r14]
0x18000e3f1  mov     r8, rsi
0x18000e3f4  mov     rdx, rbx
0x18000e3f7  mov     rcx, r14
0x18000e3fa  mov     rax, [rax+30h]
0x18000e3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e403  mov     edi, eax
0x18000e405  test    eax, eax
0x18000e407  jns     short loc_18000E410
0x18000e409  mov     edx, 221h
0x18000e40e  jmp     short loc_18000E3B4
0x18000e410  mov     edi, ebp
0x18000e412  mov     rcx, rbx; pv
0x18000e415  call    cs:__imp_CoTaskMemFree
0x18000e41b  mov     rbx, [rsp+58h+arg_0]
0x18000e420  mov     eax, edi
0x18000e422  mov     rbp, [rsp+58h+arg_8]
0x18000e427  add     rsp, 40h
0x18000e42b  pop     r14
0x18000e42d  pop     rdi
0x18000e42e  pop     rsi
0x18000e42f  retn
```
