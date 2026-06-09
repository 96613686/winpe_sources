# Dossier::GetRTMBuild(ushort const *,ushort * *)

- ea: `0x18000df40`
- end: `0x18000e0e7`
- name: `?GetRTMBuild@Dossier@@UEAAJPEBGPEAPEAG@Z`
- size: `423`
- prototype: `int(Dossier *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b2d8`
- `0x18000df40`
- `0x18000efec`
- `0x180018a50`
- `0x18001972e`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e0be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e0c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e0be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e0c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e02b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e02b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000df7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000df7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e052`

## pseudocode

```c
__int64 __fastcall Dossier::GetRTMBuild(Dossier *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx
  int v8; // esi
  int v9; // eax
  __int64 v10; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  int v13; // eax
  unsigned __int16 *v14; // rcx
  unsigned int *v16; // [rsp+20h] [rbp-20h]
  unsigned int v17; // [rsp+20h] [rbp-20h]
  int v18; // [rsp+20h] [rbp-20h]
  unsigned int v19; // [rsp+28h] [rbp-18h]
  unsigned int v20; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v21[3]; // [rsp+34h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  unsigned int v23; // [rsp+90h] [rbp+50h] BYREF
  unsigned int v24; // [rsp+98h] [rbp+58h] BYREF

  v20 = 0;
  v24 = 0;
  v23 = 0;
  v21[0] = 0;
  *a3 = 0;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
  v7 = v6;
  if ( v6 )
    memset_0(v6, 0, 0x208u);
  if ( (unsigned int)GetVersionElements(a2, &v20, &v24, &v23, v21) == 4 )
  {
    v17 = v24;
    v9 = StringCchPrintfW(v7, 0x104u, L"%d.%d.%d.RTM", v20);
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
        v11 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
        v12 = v11;
        if ( v11 )
          memset_0(v11, 0, 0x208u);
        v19 = v23;
        LODWORD(v16) = v24;
        v13 = StringCchPrintfW(v12, 0x104u, L"%d.%d.%d.0", v20, v16, v19);
        v8 = v13;
        if ( v13 >= 0 )
        {
          *a3 = v12;
          v8 = 0;
          v14 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
            (const char *)(unsigned int)v13,
            v18);
          v14 = v12;
        }
        CoTaskMemFree(v14);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x177,
        (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
        (const char *)(unsigned int)v9,
        v17);
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
0x18000df40  mov     [rsp-38h+arg_0], rbx
0x18000df45  push    rbp
0x18000df46  push    rsi
0x18000df47  push    rdi
0x18000df48  push    r12
0x18000df4a  push    r13
0x18000df4c  push    r14
0x18000df4e  push    r15
0x18000df50  mov     rbp, rsp
0x18000df53  sub     rsp, 40h
0x18000df57  xor     r12d, r12d
0x18000df5a  mov     r15, rcx
0x18000df5d  mov     r13d, 208h
0x18000df63  mov     [rbp+var_10], r12d
0x18000df67  mov     ecx, r13d; cb
0x18000df6a  mov     [rbp+arg_18], r12d
0x18000df6e  mov     r14, r8
0x18000df71  mov     [rbp+arg_10], r12d
0x18000df75  mov     rdi, rdx
0x18000df78  mov     [rbp+var_C], r12d
0x18000df7c  mov     [r8], r12
0x18000df7f  call    cs:__imp_CoTaskMemAlloc
0x18000df85  mov     rbx, rax
0x18000df88  test    rax, rax
0x18000df8b  jz      short loc_18000DF9A
0x18000df8d  mov     r8d, r13d; Size
0x18000df90  xor     edx, edx; Val
0x18000df92  mov     rcx, rax; void *
0x18000df95  call    memset_0
0x18000df9a  lea     rax, [rbp+var_C]
0x18000df9e  mov     rcx, rdi; unsigned __int16 *
0x18000dfa1  lea     r9, [rbp+arg_10]; unsigned int *
0x18000dfa5  mov     [rsp+40h+var_20], rax; unsigned int *
0x18000dfaa  lea     r8, [rbp+arg_18]; unsigned int *
0x18000dfae  lea     rdx, [rbp+var_10]; unsigned int *
0x18000dfb2  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x18000dfb7  cmp     eax, 4
0x18000dfba  jz      short loc_18000DFC6
0x18000dfbc  mov     esi, 80070309h
0x18000dfc1  jmp     loc_18000E0C4
0x18000dfc6  mov     ecx, [rbp+arg_18]
0x18000dfc9  lea     r8, aDDDRtm; "%d.%d.%d.RTM"
0x18000dfd0  mov     eax, [rbp+arg_10]
0x18000dfd3  mov     edx, 104h; unsigned __int64
0x18000dfd8  mov     r9d, [rbp+var_10]
0x18000dfdc  mov     [rsp+40h+var_18], eax
0x18000dfe0  mov     dword ptr [rsp+40h+var_20], ecx; int
0x18000dfe4  mov     rcx, rbx; unsigned __int16 *
0x18000dfe7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dfec  mov     esi, eax
0x18000dfee  test    eax, eax
0x18000dff0  jns     short loc_18000E00F
0x18000dff2  mov     rcx, [rbp+38h]; this
0x18000dff6  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000dffd  mov     r9d, eax; char *
0x18000e000  mov     edx, 177h; void *
0x18000e005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e00a  jmp     loc_18000E0C4
0x18000e00f  test    rbx, rbx
0x18000e012  jz      short loc_18000E034
0x18000e014  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e018  inc     rax
0x18000e01b  cmp     [rbx+rax*2], r12w
0x18000e020  jnz     short loc_18000E018
0x18000e022  lea     edx, [rax+1]
0x18000e025  mov     rcx, rbx; pv
0x18000e028  add     rdx, rdx; cb
0x18000e02b  call    cs:__imp_CoTaskMemRealloc
0x18000e031  mov     rbx, rax
0x18000e034  mov     rax, [r15]
0x18000e037  mov     r8, r14
0x18000e03a  mov     rdx, rbx
0x18000e03d  mov     rcx, r15
0x18000e040  mov     rax, [rax+30h]
0x18000e044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e049  mov     esi, eax
0x18000e04b  test    eax, eax
0x18000e04d  jns     short loc_18000E0C4
0x18000e04f  mov     rcx, r13; cb
0x18000e052  call    cs:__imp_CoTaskMemAlloc
0x18000e058  mov     rdi, rax
0x18000e05b  test    rax, rax
0x18000e05e  jz      short loc_18000E06D
0x18000e060  mov     r8, r13; Size
0x18000e063  xor     edx, edx; Val
0x18000e065  mov     rcx, rax; void *
0x18000e068  call    memset_0
0x18000e06d  mov     ecx, [rbp+arg_18]
0x18000e070  lea     r8, aDDD0; "%d.%d.%d.0"
0x18000e077  mov     eax, [rbp+arg_10]
0x18000e07a  mov     edx, 104h; unsigned __int64
0x18000e07f  mov     r9d, [rbp+var_10]
0x18000e083  mov     [rsp+40h+var_18], eax
0x18000e087  mov     dword ptr [rsp+40h+var_20], ecx; int
0x18000e08b  mov     rcx, rdi; unsigned __int16 *
0x18000e08e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e093  mov     esi, eax
0x18000e095  test    eax, eax
0x18000e097  jns     short loc_18000E0B6
0x18000e099  mov     rcx, [rbp+38h]; this
0x18000e09d  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000e0a4  mov     r9d, eax; char *
0x18000e0a7  mov     edx, 182h; void *
0x18000e0ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e0b1  mov     rcx, rdi
0x18000e0b4  jmp     short loc_18000E0BE
0x18000e0b6  mov     [r14], rdi
0x18000e0b9  mov     esi, r12d
0x18000e0bc  xor     ecx, ecx; pv
0x18000e0be  call    cs:__imp_CoTaskMemFree
0x18000e0c4  mov     rcx, rbx; pv
0x18000e0c7  call    cs:__imp_CoTaskMemFree
0x18000e0cd  mov     rbx, [rsp+40h+arg_0]
0x18000e0d5  mov     eax, esi
0x18000e0d7  add     rsp, 40h
0x18000e0db  pop     r15
0x18000e0dd  pop     r14
0x18000e0df  pop     r13
0x18000e0e1  pop     r12
0x18000e0e3  pop     rdi
0x18000e0e4  pop     rsi
0x18000e0e5  pop     rbp
0x18000e0e6  retn
```
