# SensorTransform::CreatePresentationDescriptor(IMFPresentationDescriptor * *)

- ea: `0x1800bdce0`
- end: `0x1800bdf21`
- name: `?CreatePresentationDescriptor@SensorTransform@@UEAAJPEAPEAUIMFPresentationDescriptor@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(SensorTransform *__hidden this, struct IMFPresentationDescriptor **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800041f0`
- `0x18000478c`
- `0x180004f20`
- `0x180008cf0`
- `0x180009608`
- `0x1800bdce0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bdf02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bdf02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bdd06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bdd06`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1800bde96`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1800bde96`
- `MFPlat!MFTraceError` at `0x1800bdd45`
- `MFPlat!MFTraceError` at `0x1800bdd45`

## string_xrefs

- `0x1800bdd32`: `SensorTransform::CreatePresentationDescriptor`

## pseudocode

```c
__int64 __fastcall SensorTransform::CreatePresentationDescriptor(
        SensorTransform *this,
        struct IMFPresentationDescriptor **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  bool v5; // zf
  unsigned int v6; // edi
  __int64 v7; // rdx
  unsigned __int64 v8; // rbp
  IMFStreamDescriptor **v9; // rax
  IMFStreamDescriptor **v10; // r14
  __int64 i; // r15
  __int64 v12; // rcx
  HRESULT v13; // eax
  const struct std::nothrow_t *v14; // rdx
  __int64 v15; // rdx
  __int64 j; // rsi
  IMFStreamDescriptor *v17; // rcx
  IMFPresentationDescriptor *ppPresentationDescriptor; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 608);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  v5 = *((_BYTE *)this + 588) == 0;
  ppPresentationDescriptor = 0;
  if ( !v5 )
  {
    v6 = -1072873851;
    MFTraceError(
      "avcore\\mf\\frameserver\\sensortransform\\manager\\sensortransform.cpp",
      650,
      "SensorTransform::CreatePresentationDescriptor",
      this,
      -1072873851,
      1);
    goto LABEL_32;
  }
  if ( !*((_QWORD *)this + 99) )
  {
    v6 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_32;
    v7 = 93;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, this, v6);
    goto LABEL_32;
  }
  v8 = *((unsigned int *)this + 204);
  if ( (_DWORD)v8 != *((_DWORD *)this + 176) )
  {
    v6 = -2147418113;
    if ( !g_wppLevels )
      goto LABEL_32;
    v7 = 94;
    goto LABEL_6;
  }
  if ( !a2 )
  {
    v6 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_32;
    v7 = 95;
    goto LABEL_6;
  }
  *a2 = 0;
  v9 = (IMFStreamDescriptor **)operator new[](saturated_mul(v8, 8u));
  v10 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_32;
    v7 = 96;
    goto LABEL_6;
  }
  memset_0(v9, 0, 8 * v8);
  for ( i = 0; (unsigned int)i < (unsigned int)v8; i = (unsigned int)(i + 1) )
  {
    v12 = *(_QWORD *)(*((_QWORD *)this + 101) + 8 * i);
    v13 = (*(__int64 (__fastcall **)(__int64, IMFStreamDescriptor **))(*(_QWORD *)v12 + 64LL))(v12, &v10[i]);
    v6 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_27;
      v15 = 97;
      goto LABEL_22;
    }
  }
  v13 = MFCreatePresentationDescriptor(v8, v10, &ppPresentationDescriptor);
  v6 = v13;
  if ( v13 >= 0 )
  {
    *a2 = ppPresentationDescriptor;
    ppPresentationDescriptor = 0;
  }
  else if ( g_wppLevels )
  {
    v15 = 98;
LABEL_22:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, this, v13);
  }
LABEL_27:
  for ( j = 0; (unsigned int)j < (unsigned int)v8; j = (unsigned int)(j + 1) )
  {
    v17 = v10[j];
    if ( v17 )
    {
      ((void (__fastcall *)(IMFStreamDescriptor *))v17->lpVtbl->Release)(v17);
      v10[j] = 0;
    }
  }
  operator delete(v10, v14);
LABEL_32:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppPresentationDescriptor);
  LeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x1800bdce0  mov     [rsp+arg_8], rbx
0x1800bdce5  mov     [rsp+arg_10], rbp
0x1800bdcea  push    rsi
0x1800bdceb  push    rdi
0x1800bdcec  push    r12
0x1800bdcee  push    r14
0x1800bdcf0  push    r15
0x1800bdcf2  sub     rsp, 30h
0x1800bdcf6  lea     rbx, [rcx+260h]
0x1800bdcfd  mov     rsi, rcx
0x1800bdd00  mov     rcx, rbx; lpCriticalSection
0x1800bdd03  mov     r12, rdx
0x1800bdd06  call    cs:__imp_EnterCriticalSection
0x1800bdd0c  cmp     byte ptr [rsi+24Ch], 0
0x1800bdd13  mov     [rsp+58h+ppPresentationDescriptor], 0
0x1800bdd1c  jz      short loc_1800BDD50
0x1800bdd1e  mov     edi, 0C00D3E85h
0x1800bdd23  mov     [rsp+58h+var_30], 1
0x1800bdd2b  mov     r9, rsi
0x1800bdd2e  mov     [rsp+58h+var_38], edi
0x1800bdd32  lea     r8, aSensortransfor_23; "SensorTransform::CreatePresentationDesc"...
0x1800bdd39  mov     edx, 28Ah
0x1800bdd3e  lea     rcx, aAvcoreMfFrames; "avcore\\mf\\frameserver\\sensortransfor"...
0x1800bdd45  call    cs:__imp_MFTraceError
0x1800bdd4b  jmp     loc_1800BDEF5
0x1800bdd50  cmp     qword ptr [rsi+318h], 0
0x1800bdd58  jnz     short loc_1800BDD94
0x1800bdd5a  mov     edi, 0C00D36B6h
0x1800bdd5f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bdd66  jb      loc_1800BDEF5
0x1800bdd6c  mov     edx, 5Dh ; ']'
0x1800bdd71  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdd78  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x1800bdd7f  mov     r9, rsi
0x1800bdd82  mov     [rsp+58h+var_38], edi
0x1800bdd86  mov     rcx, [rcx+10h]
0x1800bdd8a  call    WPP_SF_qD
0x1800bdd8f  jmp     loc_1800BDEF5
0x1800bdd94  mov     ebp, [rsi+330h]
0x1800bdd9a  cmp     ebp, [rsi+2C0h]
0x1800bdda0  jz      short loc_1800BDDBB
0x1800bdda2  mov     edi, 8000FFFFh
0x1800bdda7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bddae  jb      loc_1800BDEF5
0x1800bddb4  mov     edx, 5Eh ; '^'
0x1800bddb9  jmp     short loc_1800BDD71
0x1800bddbb  test    r12, r12
0x1800bddbe  jnz     short loc_1800BDDD9
0x1800bddc0  mov     edi, 80004003h
0x1800bddc5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bddcc  jb      loc_1800BDEF5
0x1800bddd2  lea     edx, [r12+5Fh]
0x1800bddd7  jmp     short loc_1800BDD71
0x1800bddd9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800bdde0  mov     qword ptr [r12], 0
0x1800bdde8  mov     eax, 8
0x1800bdded  mul     rbp
0x1800bddf0  cmovb   rax, rcx
0x1800bddf4  mov     rcx, rax; unsigned __int64
0x1800bddf7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bddfc  mov     r14, rax
0x1800bddff  test    rax, rax
0x1800bde02  jnz     short loc_1800BDE1E
0x1800bde04  mov     edi, 8007000Eh
0x1800bde09  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bde10  jb      loc_1800BDEF5
0x1800bde16  lea     edx, [rax+60h]
0x1800bde19  jmp     loc_1800BDD71
0x1800bde1e  lea     r8, ds:0[rbp*8]; Size
0x1800bde26  xor     edx, edx; Val
0x1800bde28  mov     rcx, r14; void *
0x1800bde2b  call    memset_0
0x1800bde30  xor     r15d, r15d
0x1800bde33  cmp     r15d, ebp
0x1800bde36  jnb     short loc_1800BDE8C
0x1800bde38  mov     rax, [rsi+328h]
0x1800bde3f  lea     rdx, [r14+r15*8]
0x1800bde43  mov     rcx, [rax+r15*8]
0x1800bde47  mov     rax, [rcx]
0x1800bde4a  mov     rax, [rax+40h]
0x1800bde4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bde53  mov     edi, eax
0x1800bde55  test    eax, eax
0x1800bde57  js      short loc_1800BDE5E
0x1800bde59  inc     r15d
0x1800bde5c  jmp     short loc_1800BDE33
0x1800bde5e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bde65  jb      short loc_1800BDEC4
0x1800bde67  mov     edx, 61h ; 'a'
0x1800bde6c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bde73  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x1800bde7a  mov     r9, rsi
0x1800bde7d  mov     [rsp+58h+var_38], eax
0x1800bde81  mov     rcx, [rcx+10h]
0x1800bde85  call    WPP_SF_qD
0x1800bde8a  jmp     short loc_1800BDEC4
0x1800bde8c  lea     r8, [rsp+58h+ppPresentationDescriptor]; ppPresentationDescriptor
0x1800bde91  mov     rdx, r14; apStreamDescriptors
0x1800bde94  mov     ecx, ebp; cStreamDescriptors
0x1800bde96  call    cs:__imp_MFCreatePresentationDescriptor
0x1800bde9c  mov     edi, eax
0x1800bde9e  test    eax, eax
0x1800bdea0  jns     short loc_1800BDEB2
0x1800bdea2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bdea9  jb      short loc_1800BDEC4
0x1800bdeab  mov     edx, 62h ; 'b'
0x1800bdeb0  jmp     short loc_1800BDE6C
0x1800bdeb2  mov     rax, [rsp+58h+ppPresentationDescriptor]
0x1800bdeb7  mov     [r12], rax
0x1800bdebb  mov     [rsp+58h+ppPresentationDescriptor], 0
0x1800bdec4  xor     esi, esi
0x1800bdec6  test    ebp, ebp
0x1800bdec8  jz      short loc_1800BDEED
0x1800bdeca  mov     rcx, [r14+rsi*8]
0x1800bdece  test    rcx, rcx
0x1800bded1  jz      short loc_1800BDEE7
0x1800bded3  mov     rax, [rcx]
0x1800bded6  mov     rax, [rax+10h]
0x1800bdeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdedf  mov     qword ptr [r14+rsi*8], 0
0x1800bdee7  inc     esi
0x1800bdee9  cmp     esi, ebp
0x1800bdeeb  jb      short loc_1800BDECA
0x1800bdeed  mov     rcx, r14; void *
0x1800bdef0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bdef5  lea     rcx, [rsp+58h+ppPresentationDescriptor]; void *
0x1800bdefa  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bdeff  mov     rcx, rbx; lpCriticalSection
0x1800bdf02  call    cs:__imp_LeaveCriticalSection
0x1800bdf08  mov     rbx, [rsp+58h+arg_8]
0x1800bdf0d  mov     eax, edi
0x1800bdf0f  mov     rbp, [rsp+58h+arg_10]
0x1800bdf14  add     rsp, 30h
0x1800bdf18  pop     r15
0x1800bdf1a  pop     r14
0x1800bdf1c  pop     r12
0x1800bdf1e  pop     rdi
0x1800bdf1f  pop     rsi
0x1800bdf20  retn
```
