# CUpdateDeploymentJob::AddDeploymentUpdate(IDeploymentUpdate *)

- ea: `0x180031f20`
- end: `0x180032331`
- name: `?AddDeploymentUpdate@CUpdateDeploymentJob@@UEAAJPEAUIDeploymentUpdate@@@Z`
- size: `1041`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this, struct IDeploymentUpdate *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callees

- `0x180003180`
- `0x18000dce4`
- `0x180015614`
- `0x180023220`
- `0x1800233f4`
- `0x180023fdc`
- `0x18002ca68`
- `0x180031f20`
- `0x180061960`
- `0x180061d54`
- `0x180062534`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800321a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800321a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032295`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800322a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032295`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800322a6`

## string_xrefs

- `0x180031f5e`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032183`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032279`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUpdateDeploymentJob::AddDeploymentUpdate(CUpdateDeploymentJob *this, struct IDeploymentUpdate *a2)
{
  int Instance; // esi
  __int64 v6; // rdx
  __int64 (__fastcall *v7)(struct IDeploymentUpdate *, void **); // rsi
  __int64 (__fastcall *v8)(struct IDeploymentUpdate *, void **); // rsi
  __int64 (__fastcall *v9)(struct IDeploymentUpdate *, void **); // rsi
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  const struct std::nothrow_t *v13; // rdx
  _QWORD *v14; // rsi
  unsigned int v15; // r8d
  __int64 v16; // rax
  void *v17; // rcx
  const struct std::nothrow_t *v18; // rdx
  void *v19; // rcx
  int v20; // [rsp+20h] [rbp-60h]
  int v21; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v22; // [rsp+4Ch] [rbp-34h] BYREF
  void *v23; // [rsp+50h] [rbp-30h] BYREF
  void *v24; // [rsp+58h] [rbp-28h] BYREF
  void *lpMem; // [rsp+60h] [rbp-20h] BYREF
  void *v26; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1038,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80004003LL,
      v20);
    return 2147500035LL;
  }
  v26 = 0;
  v22 = 0;
  v21 = 0;
  lpMem = 0;
  v24 = 0;
  v23 = 0;
  Instance = (*(__int64 (__fastcall **)(struct IDeploymentUpdate *, void **))(*(_QWORD *)a2 + 24LL))(a2, &v26);
  if ( Instance < 0 )
  {
    v6 = 4162;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)Instance,
      v20);
    goto LABEL_55;
  }
  Instance = (*(__int64 (__fastcall **)(struct IDeploymentUpdate *, unsigned int *))(*(_QWORD *)a2 + 32LL))(a2, &v22);
  if ( Instance < 0 )
  {
    v6 = 4163;
    goto LABEL_37;
  }
  Instance = (*(__int64 (__fastcall **)(struct IDeploymentUpdate *, int *))(*(_QWORD *)a2 + 40LL))(a2, &v21);
  if ( Instance < 0 )
  {
    v6 = 4164;
    goto LABEL_37;
  }
  v7 = *(__int64 (__fastcall **)(struct IDeploymentUpdate *, void **))(*(_QWORD *)a2 + 48LL);
  if ( lpMem )
    SusFree(lpMem);
  Instance = v7(a2, &lpMem);
  if ( Instance < 0 )
  {
    v6 = 4165;
    goto LABEL_37;
  }
  v8 = *(__int64 (__fastcall **)(struct IDeploymentUpdate *, void **))(*(_QWORD *)a2 + 56LL);
  if ( v24 )
    SusFree(v24);
  Instance = v8(a2, &v24);
  if ( Instance < 0 )
  {
    v6 = 4166;
    goto LABEL_37;
  }
  v9 = *(__int64 (__fastcall **)(struct IDeploymentUpdate *, void **))(*(_QWORD *)a2 + 64LL);
  if ( v23 )
    SusFree(v23);
  Instance = v9(a2, &v23);
  if ( Instance < 0 )
  {
    v6 = 4167;
    goto LABEL_37;
  }
  if ( v21 == 1 )
  {
    v10 = 1;
  }
  else if ( v21 == 2 )
  {
    v10 = 2;
  }
  else
  {
    v10 = 4;
    if ( v21 != 4 )
    {
      if ( v21 == 8 )
        v10 = 8;
      else
        v10 = 0;
    }
  }
  v20 = (int)v24;
  Instance = CDeployUpdate::CreateInstance(v26, v22, v10, lpMem);
  if ( Instance < 0 )
  {
    v6 = 4175;
    goto LABEL_37;
  }
  Instance = DPCopyMatchingUpdateToDeployUpdate(
               *((_DWORD *)this + 200),
               *((struct IUpdateDeploymentDataProvider **)this + 89),
               0);
  if ( Instance < 0 )
  {
    v6 = 4178;
    goto LABEL_37;
  }
  Instance = DPGetMetadataAndDeploymentForBundledUpdate(
               *((_DWORD *)this + 200),
               *((struct IUpdateDeploymentDataProvider **)this + 89),
               0);
  if ( Instance < 0 )
  {
    v6 = 4181;
    goto LABEL_37;
  }
  Instance = DPGetPropForUpdate(
               *((_DWORD *)this + 200),
               *((struct IUpdateDeploymentDataProvider **)this + 89),
               *((struct IUpdateDeploymentCallerIdentity **)this + 88),
               0);
  if ( Instance < 0 )
  {
    v6 = 4185;
    goto LABEL_37;
  }
  if ( this != (CUpdateDeploymentJob *)-880LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  if ( *((_DWORD *)this + 218) )
  {
    Instance = -2145124298;
    v11 = 4190;
  }
  else
  {
    v12 = 8LL * (unsigned int)(*((_DWORD *)this + 172) + 1);
    if ( !is_mul_ok((unsigned int)(*((_DWORD *)this + 172) + 1), 8u) )
      v12 = -1;
    v14 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    v15 = 0;
    v16 = *((unsigned int *)this + 172);
    if ( (_DWORD)v16 )
    {
      do
      {
        v13 = (const struct std::nothrow_t *)v15;
        v14[v15] = *(_QWORD *)(*((_QWORD *)this + 87) + 8LL * v15);
        *(_QWORD *)(*((_QWORD *)this + 87) + 8LL * v15++) = 0;
        v16 = *((unsigned int *)this + 172);
      }
      while ( v15 < (unsigned int)v16 );
    }
    v14[v16] = 0;
    v17 = (void *)*((_QWORD *)this + 87);
    *((_QWORD *)this + 87) = 0;
    operator delete(v17, v13);
    v19 = (void *)*((_QWORD *)this + 87);
    if ( v19 )
      operator delete(v19, v18);
    *((_QWORD *)this + 87) = v14;
    ++*((_DWORD *)this + 172);
    Instance = CUpdateDeploymentJob::SortDeployUpdates(this);
    if ( Instance >= 0 )
    {
      if ( this != (CUpdateDeploymentJob *)-880LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
      Instance = 0;
      goto LABEL_55;
    }
    v11 = 4207;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
    (const char *)(unsigned int)Instance,
    v20);
  if ( this != (CUpdateDeploymentJob *)-880LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
LABEL_55:
  if ( v23 )
  {
    SusFree(v23);
    v23 = 0;
  }
  if ( v24 )
  {
    SusFree(v24);
    v24 = 0;
  }
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  if ( v26 )
  {
    SusFree(v26);
    v26 = 0;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180031f20  mov     [rsp-28h+arg_10], rbx
0x180031f25  push    rbp
0x180031f26  push    rsi
0x180031f27  push    rdi
0x180031f28  push    r14
0x180031f2a  push    r15
0x180031f2c  mov     rbp, rsp
0x180031f2f  sub     rsp, 80h
0x180031f36  mov     rax, cs:__security_cookie
0x180031f3d  xor     rax, rsp
0x180031f40  mov     [rbp+var_10], rax
0x180031f44  mov     rdi, rdx
0x180031f47  mov     r14, rcx
0x180031f4a  xor     r15d, r15d
0x180031f4d  test    rdx, rdx
0x180031f50  jnz     short loc_180031F76
0x180031f52  mov     rcx, [rbp+28h]; this
0x180031f56  mov     ebx, 80004003h
0x180031f5b  mov     r9d, ebx; char *
0x180031f5e  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180031f65  mov     edx, 1038h; void *
0x180031f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031f6f  mov     eax, ebx
0x180031f71  jmp     loc_18003230E
0x180031f76  mov     rbx, r15
0x180031f79  mov     [rbp+var_40], rbx
0x180031f7d  mov     [rbp+var_18], r15
0x180031f81  mov     [rbp+var_34], r15d
0x180031f85  mov     [rbp+var_38], r15d
0x180031f89  mov     [rbp+lpMem], r15
0x180031f8d  mov     [rbp+var_28], r15
0x180031f91  mov     [rbp+var_30], r15
0x180031f95  mov     rax, [rdx]
0x180031f98  lea     rdx, [rbp+var_18]
0x180031f9c  mov     rcx, rdi
0x180031f9f  mov     rax, [rax+18h]
0x180031fa3  call    _guard_dispatch_icall
0x180031fa8  mov     esi, eax
0x180031faa  test    eax, eax
0x180031fac  jns     short loc_180031FB8
0x180031fae  mov     edx, 1042h
0x180031fb3  jmp     loc_18003217C
0x180031fb8  mov     rax, [rdi]
0x180031fbb  lea     rdx, [rbp+var_34]
0x180031fbf  mov     rcx, rdi
0x180031fc2  mov     rax, [rax+20h]
0x180031fc6  call    _guard_dispatch_icall
0x180031fcb  mov     esi, eax
0x180031fcd  test    eax, eax
0x180031fcf  jns     short loc_180031FDB
0x180031fd1  mov     edx, 1043h
0x180031fd6  jmp     loc_18003217C
0x180031fdb  mov     rax, [rdi]
0x180031fde  lea     rdx, [rbp+var_38]
0x180031fe2  mov     rcx, rdi
0x180031fe5  mov     rax, [rax+28h]
0x180031fe9  call    _guard_dispatch_icall
0x180031fee  mov     esi, eax
0x180031ff0  test    eax, eax
0x180031ff2  jns     short loc_180031FFE
0x180031ff4  mov     edx, 1044h
0x180031ff9  jmp     loc_18003217C
0x180031ffe  mov     rax, [rdi]
0x180032001  mov     rsi, [rax+30h]
0x180032005  mov     rcx, [rbp+lpMem]; lpMem
0x180032009  test    rcx, rcx
0x18003200c  jz      short loc_180032013
0x18003200e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180032013  lea     rdx, [rbp+lpMem]
0x180032017  mov     rcx, rdi
0x18003201a  mov     rax, rsi
0x18003201d  call    _guard_dispatch_icall
0x180032022  mov     esi, eax
0x180032024  test    eax, eax
0x180032026  jns     short loc_180032032
0x180032028  mov     edx, 1045h
0x18003202d  jmp     loc_18003217C
0x180032032  mov     rax, [rdi]
0x180032035  mov     rsi, [rax+38h]
0x180032039  mov     rcx, [rbp+var_28]; lpMem
0x18003203d  test    rcx, rcx
0x180032040  jz      short loc_180032047
0x180032042  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180032047  lea     rdx, [rbp+var_28]
0x18003204b  mov     rcx, rdi
0x18003204e  mov     rax, rsi
0x180032051  call    _guard_dispatch_icall
0x180032056  mov     esi, eax
0x180032058  test    eax, eax
0x18003205a  jns     short loc_180032066
0x18003205c  mov     edx, 1046h
0x180032061  jmp     loc_18003217C
0x180032066  mov     rax, [rdi]
0x180032069  mov     rsi, [rax+40h]
0x18003206d  mov     rcx, [rbp+var_30]; lpMem
0x180032071  test    rcx, rcx
0x180032074  jz      short loc_18003207B
0x180032076  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003207b  lea     rdx, [rbp+var_30]
0x18003207f  mov     rcx, rdi
0x180032082  mov     rax, rsi
0x180032085  call    _guard_dispatch_icall
0x18003208a  mov     esi, eax
0x18003208c  test    eax, eax
0x18003208e  jns     short loc_18003209A
0x180032090  mov     edx, 1047h
0x180032095  jmp     loc_18003217C
0x18003209a  mov     rdx, [rbp+var_30]
0x18003209e  mov     r9, [rbp+var_28]
0x1800320a2  mov     ecx, [rbp+var_38]
0x1800320a5  sub     ecx, 1
0x1800320a8  jz      short loc_1800320D4
0x1800320aa  sub     ecx, 1
0x1800320ad  jz      short loc_1800320CC
0x1800320af  sub     ecx, 2
0x1800320b2  mov     r8d, 4
0x1800320b8  jz      short loc_1800320DA
0x1800320ba  cmp     ecx, r8d
0x1800320bd  jz      short loc_1800320C4
0x1800320bf  mov     r8d, r15d
0x1800320c2  jmp     short loc_1800320DA
0x1800320c4  mov     r8d, 8
0x1800320ca  jmp     short loc_1800320DA
0x1800320cc  mov     r8d, 2
0x1800320d2  jmp     short loc_1800320DA
0x1800320d4  mov     r8d, 1
0x1800320da  lea     rax, [rbp+var_40]
0x1800320de  mov     [rsp+80h+var_50], rax
0x1800320e3  mov     [rsp+80h+var_58], rdx
0x1800320e8  mov     qword ptr [rsp+80h+var_60], r9; int
0x1800320ed  mov     r9, [rbp+lpMem]
0x1800320f1  mov     edx, [rbp+var_34]
0x1800320f4  mov     rcx, [rbp+var_18]
0x1800320f8  call    ?CreateInstance@CDeployUpdate@@SAJPEB_WKW4tagDeploymentOperation@@000PEAPEAV1@@Z; CDeployUpdate::CreateInstance(wchar_t const *,ulong,tagDeploymentOperation,wchar_t const *,wchar_t const *,wchar_t const *,CDeployUpdate * *)
0x1800320fd  mov     esi, eax
0x1800320ff  mov     rbx, [rbp+var_40]
0x180032103  test    eax, eax
0x180032105  jns     short loc_18003210E
0x180032107  mov     edx, 104Fh
0x18003210c  jmp     short loc_18003217C
0x18003210e  mov     r8, rbx; struct CDeployUpdate *
0x180032111  mov     rdx, [r14+2C8h]; struct IUpdateDeploymentDataProvider *
0x180032118  mov     ecx, [r14+320h]; unsigned int
0x18003211f  call    ?DPCopyMatchingUpdateToDeployUpdate@@YAJKPEAUIUpdateDeploymentDataProvider@@PEAVCDeployUpdate@@@Z; DPCopyMatchingUpdateToDeployUpdate(ulong,IUpdateDeploymentDataProvider *,CDeployUpdate *)
0x180032124  mov     esi, eax
0x180032126  test    eax, eax
0x180032128  jns     short loc_180032131
0x18003212a  mov     edx, 1052h
0x18003212f  jmp     short loc_18003217C
0x180032131  mov     r8, rbx; struct CDeployUpdate *
0x180032134  mov     rdx, [r14+2C8h]; struct IUpdateDeploymentDataProvider *
0x18003213b  mov     ecx, [r14+320h]; unsigned int
0x180032142  call    ?DPGetMetadataAndDeploymentForBundledUpdate@@YAJKPEAUIUpdateDeploymentDataProvider@@PEAVCDeployUpdate@@@Z; DPGetMetadataAndDeploymentForBundledUpdate(ulong,IUpdateDeploymentDataProvider *,CDeployUpdate *)
0x180032147  mov     esi, eax
0x180032149  test    eax, eax
0x18003214b  jns     short loc_180032154
0x18003214d  mov     edx, 1055h
0x180032152  jmp     short loc_18003217C
0x180032154  mov     r9, rbx; struct CDeployUpdate *
0x180032157  mov     r8, [r14+2C0h]; struct IUpdateDeploymentCallerIdentity *
0x18003215e  mov     rdx, [r14+2C8h]; struct IUpdateDeploymentDataProvider *
0x180032165  mov     ecx, [r14+320h]; unsigned int
0x18003216c  call    ?DPGetPropForUpdate@@YAJKPEAUIUpdateDeploymentDataProvider@@PEAUIUpdateDeploymentCallerIdentity@@PEAVCDeployUpdate@@@Z; DPGetPropForUpdate(ulong,IUpdateDeploymentDataProvider *,IUpdateDeploymentCallerIdentity *,CDeployUpdate *)
0x180032171  mov     esi, eax
0x180032173  test    eax, eax
0x180032175  jns     short loc_180032194
0x180032177  mov     edx, 1059h; void *
0x18003217c  mov     rcx, [rbp+28h]; this
0x180032180  mov     r9d, esi; char *
0x180032183  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18003218a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003218f  jmp     loc_1800322AF
0x180032194  lea     rdi, [r14+370h]
0x18003219b  test    rdi, rdi
0x18003219e  jz      short loc_1800321AA
0x1800321a0  lea     rcx, [rdi+8]; lpCriticalSection
0x1800321a4  call    cs:__imp_EnterCriticalSection
0x1800321aa  cmp     [r14+368h], r15d
0x1800321b1  jz      short loc_1800321C2
0x1800321b3  mov     esi, 80240036h
0x1800321b8  mov     edx, 105Eh
0x1800321bd  jmp     loc_180032279
0x1800321c2  mov     edx, [r14+2B0h]
0x1800321c9  inc     edx
0x1800321cb  mov     eax, 8
0x1800321d0  mul     rdx
0x1800321d3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800321da  cmovb   rax, rcx
0x1800321de  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800321e5  mov     rcx, rax; unsigned __int64
0x1800321e8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800321ed  mov     rsi, rax
0x1800321f0  mov     r8d, r15d
0x1800321f3  mov     eax, [r14+2B0h]
0x1800321fa  test    eax, eax
0x1800321fc  jz      short loc_18003222A
0x1800321fe  mov     edx, r8d; struct std::nothrow_t *
0x180032201  mov     rax, [r14+2B8h]
0x180032208  mov     rcx, [rax+rdx*8]
0x18003220c  mov     [rsi+rdx*8], rcx
0x180032210  mov     rax, [r14+2B8h]
0x180032217  mov     [rax+rdx*8], r15
0x18003221b  inc     r8d
0x18003221e  mov     eax, [r14+2B0h]
0x180032225  cmp     r8d, eax
0x180032228  jb      short loc_1800321FE
0x18003222a  mov     rcx, rbx
0x18003222d  mov     rbx, r15
0x180032230  mov     [rsi+rax*8], rcx
0x180032234  mov     rcx, [r14+2B8h]; void *
0x18003223b  mov     [r14+2B8h], r15
0x180032242  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032247  mov     rcx, [r14+2B8h]; void *
0x18003224e  test    rcx, rcx
0x180032251  jz      short loc_180032258
0x180032253  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032258  mov     [r14+2B8h], rsi
0x18003225f  inc     dword ptr [r14+2B0h]
0x180032266  mov     rcx, r14; this
0x180032269  call    ?SortDeployUpdates@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::SortDeployUpdates(void)
0x18003226e  mov     esi, eax
0x180032270  test    eax, eax
0x180032272  jns     short loc_18003229D
0x180032274  mov     edx, 106Fh; void *
0x180032279  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180032280  mov     rcx, [rbp+28h]; this
0x180032284  mov     r9d, esi; char *
0x180032287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003228c  test    rdi, rdi
0x18003228f  jz      short loc_1800322AF
0x180032291  lea     rcx, [rdi+8]; lpCriticalSection
0x180032295  call    cs:__imp_LeaveCriticalSection
0x18003229b  jmp     short loc_1800322AF
0x18003229d  test    rdi, rdi
0x1800322a0  jz      short loc_1800322AC
0x1800322a2  lea     rcx, [rdi+8]; lpCriticalSection
0x1800322a6  call    cs:__imp_LeaveCriticalSection
0x1800322ac  mov     esi, r15d
0x1800322af  mov     rcx, [rbp+var_30]; lpMem
0x1800322b3  test    rcx, rcx
0x1800322b6  jz      short loc_1800322C1
0x1800322b8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800322bd  mov     [rbp+var_30], r15
0x1800322c1  mov     rcx, [rbp+var_28]; lpMem
0x1800322c5  test    rcx, rcx
0x1800322c8  jz      short loc_1800322D3
0x1800322ca  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800322cf  mov     [rbp+var_28], r15
0x1800322d3  mov     rcx, [rbp+lpMem]; lpMem
0x1800322d7  test    rcx, rcx
0x1800322da  jz      short loc_1800322E5
0x1800322dc  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800322e1  mov     [rbp+lpMem], r15
0x1800322e5  mov     rcx, [rbp+var_18]; lpMem
0x1800322e9  test    rcx, rcx
0x1800322ec  jz      short loc_1800322F7
0x1800322ee  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800322f3  mov     [rbp+var_18], r15
0x1800322f7  test    rbx, rbx
0x1800322fa  jz      short loc_18003230C
0x1800322fc  mov     rcx, [rbx]
0x1800322ff  mov     rax, [rcx+10h]
0x180032303  mov     rcx, rbx
0x180032306  call    _guard_dispatch_icall
0x18003230b  nop
0x18003230c  mov     eax, esi
0x18003230e  mov     rcx, [rbp+var_10]
0x180032312  xor     rcx, rsp; StackCookie
0x180032315  call    __security_check_cookie
0x18003231a  mov     rbx, [rsp+80h+arg_10]
0x180032322  add     rsp, 80h
0x180032329  pop     r15
0x18003232b  pop     r14
0x18003232d  pop     rdi
0x18003232e  pop     rsi
0x18003232f  pop     rbp
0x180032330  retn
```
