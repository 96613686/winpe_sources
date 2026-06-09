# Dossier::GetFeatureBuildEOSDate(ushort const *,ushort * *)

- ea: `0x18000d9e0`
- end: `0x18000db62`
- name: `?GetFeatureBuildEOSDate@Dossier@@UEAAJPEBGPEAPEAG@Z`
- size: `386`
- prototype: `int(Dossier *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006e28`
- `0x18000b2d8`
- `0x18000d9e0`
- `0x18000efec`
- `0x180018a50`
- `0x18001972e`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000dac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000dac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da17`

## pseudocode

```c
__int64 __fastcall Dossier::GetFeatureBuildEOSDate(Dossier *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx
  int v8; // esi
  int v9; // eax
  __int64 v10; // rax
  unsigned __int16 **v11; // r8
  void *v12; // rdi
  int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-20h]
  unsigned int v16; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-Ch] BYREF
  LPVOID pv; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v20; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+48h] BYREF

  v16 = 0;
  v21 = 0;
  v20 = 0;
  v17 = 0;
  *a3 = 0;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
  v7 = v6;
  if ( v6 )
    memset_0(v6, 0, 0x208u);
  if ( (unsigned int)GetVersionElements(a2, &v16, &v21, &v20, &v17) == 4 )
  {
    v15 = v21;
    v9 = StringCchPrintfW(v7, 0x104u, L"%d.%d.%d.EOS", v16);
    v8 = v9;
    if ( v9 >= 0 )
    {
      if ( v7 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v7[v10] );
        v7 = (unsigned __int16 *)CoTaskMemRealloc(v7, 2LL * (unsigned int)(v10 + 1));
      }
      v8 = (*(__int64 (__fastcall **)(Dossier *, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)this + 48LL))(
             this,
             v7,
             a3);
      if ( v8 < 0 )
      {
        pv = 0;
        CSpDynamicString::operator=(&pv, L"10.0.0.EOS");
        *a3 = 0;
        v11 = a3;
        v12 = pv;
        v13 = (*(__int64 (__fastcall **)(Dossier *, LPVOID, unsigned __int16 **))(*(_QWORD *)this + 48LL))(
                this,
                pv,
                v11);
        v8 = v13;
        if ( v13 >= 0 )
          v8 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CF,
            (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
            (const char *)(unsigned int)v13,
            v15);
        CoTaskMemFree(v12);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
        (const char *)(unsigned int)v9,
        v15);
    }
  }
  else
  {
    v8 = -2147024119;
  }
  CoTaskMemFree(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d9e0  mov     [rsp-28h+arg_0], rbx
0x18000d9e5  push    rbp
0x18000d9e6  push    rsi
0x18000d9e7  push    rdi
0x18000d9e8  push    r14
0x18000d9ea  push    r15
0x18000d9ec  mov     rbp, rsp
0x18000d9ef  sub     rsp, 40h
0x18000d9f3  xor     r15d, r15d
0x18000d9f6  mov     r14, rcx
0x18000d9f9  mov     ecx, 208h; cb
0x18000d9fe  mov     [rbp+var_10], r15d
0x18000da02  mov     [rbp+arg_18], r15d
0x18000da06  mov     rdi, r8
0x18000da09  mov     [rbp+arg_10], r15d
0x18000da0d  mov     rsi, rdx
0x18000da10  mov     [rbp+var_C], r15d
0x18000da14  mov     [r8], r15
0x18000da17  call    cs:__imp_CoTaskMemAlloc
0x18000da1d  mov     rbx, rax
0x18000da20  test    rax, rax
0x18000da23  jz      short loc_18000DA35
0x18000da25  xor     edx, edx; Val
0x18000da27  mov     r8d, 208h; Size
0x18000da2d  mov     rcx, rax; void *
0x18000da30  call    memset_0
0x18000da35  lea     rax, [rbp+var_C]
0x18000da39  mov     rcx, rsi; unsigned __int16 *
0x18000da3c  lea     r9, [rbp+arg_10]; unsigned int *
0x18000da40  mov     [rsp+40h+var_20], rax; unsigned int *
0x18000da45  lea     r8, [rbp+arg_18]; unsigned int *
0x18000da49  lea     rdx, [rbp+var_10]; unsigned int *
0x18000da4d  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x18000da52  cmp     eax, 4
0x18000da55  jz      short loc_18000DA61
0x18000da57  mov     esi, 80070309h
0x18000da5c  jmp     loc_18000DB46
0x18000da61  mov     ecx, [rbp+arg_18]
0x18000da64  lea     r8, aDDDEos; "%d.%d.%d.EOS"
0x18000da6b  mov     eax, [rbp+arg_10]
0x18000da6e  mov     edx, 104h; unsigned __int64
0x18000da73  mov     r9d, [rbp+var_10]
0x18000da77  mov     [rsp+40h+var_18], eax
0x18000da7b  mov     dword ptr [rsp+40h+var_20], ecx; int
0x18000da7f  mov     rcx, rbx; unsigned __int16 *
0x18000da82  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000da87  mov     esi, eax
0x18000da89  test    eax, eax
0x18000da8b  jns     short loc_18000DAAA
0x18000da8d  mov     rcx, [rbp+28h]; this
0x18000da91  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000da98  mov     r9d, eax; char *
0x18000da9b  mov     edx, 1C3h; void *
0x18000daa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000daa5  jmp     loc_18000DB46
0x18000daaa  test    rbx, rbx
0x18000daad  jz      short loc_18000DACF
0x18000daaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dab3  inc     rax
0x18000dab6  cmp     [rbx+rax*2], r15w
0x18000dabb  jnz     short loc_18000DAB3
0x18000dabd  lea     edx, [rax+1]
0x18000dac0  mov     rcx, rbx; pv
0x18000dac3  add     rdx, rdx; cb
0x18000dac6  call    cs:__imp_CoTaskMemRealloc
0x18000dacc  mov     rbx, rax
0x18000dacf  mov     rax, [r14]
0x18000dad2  mov     r8, rdi
0x18000dad5  mov     rdx, rbx
0x18000dad8  mov     rcx, r14
0x18000dadb  mov     rax, [rax+30h]
0x18000dadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dae4  mov     esi, eax
0x18000dae6  test    eax, eax
0x18000dae8  jns     short loc_18000DB46
0x18000daea  lea     rdx, a1000Eos; "10.0.0.EOS"
0x18000daf1  mov     [rbp+pv], r15
0x18000daf5  lea     rcx, [rbp+pv]
0x18000daf9  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x18000dafe  mov     [rdi], r15
0x18000db01  mov     r8, rdi
0x18000db04  mov     rax, [r14]
0x18000db07  mov     rcx, r14
0x18000db0a  mov     rdi, [rbp+pv]
0x18000db0e  mov     rdx, rdi
0x18000db11  mov     rax, [rax+30h]
0x18000db15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db1a  mov     esi, eax
0x18000db1c  test    eax, eax
0x18000db1e  jns     short loc_18000DB3A
0x18000db20  mov     rcx, [rbp+28h]; this
0x18000db24  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000db2b  mov     r9d, eax; char *
0x18000db2e  mov     edx, 1CFh; void *
0x18000db33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db38  jmp     short loc_18000DB3D
0x18000db3a  mov     esi, r15d
0x18000db3d  mov     rcx, rdi; pv
0x18000db40  call    cs:__imp_CoTaskMemFree
0x18000db46  mov     rcx, rbx; pv
0x18000db49  call    cs:__imp_CoTaskMemFree
0x18000db4f  mov     rbx, [rsp+40h+arg_0]
0x18000db54  mov     eax, esi
0x18000db56  add     rsp, 40h
0x18000db5a  pop     r15
0x18000db5c  pop     r14
0x18000db5e  pop     rdi
0x18000db5f  pop     rsi
0x18000db60  pop     rbp
0x18000db61  retn
```
