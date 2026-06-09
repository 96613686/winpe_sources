# CResultSetFactory::_CreateSession(_GUID const &,IDBProperties *,IServiceProvider *,PROVIDER_CAPABILITIES *,_GUID const &,IUnknown * *)

- ea: `0x18001d7f8`
- end: `0x18001db35`
- name: `?_CreateSession@CResultSetFactory@@AEAAJAEBU_GUID@@PEAUIDBProperties@@PEAUIServiceProvider@@PEAW4PROVIDER_CAPABILITIES@@0PEAPEAUIUnknown@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(CResultSetFactory *this, const struct _GUID *, struct IDBProperties *, struct IUnknown *, enum PROVIDER_CAPABILITIES *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062e9c`

## callees

- `0x18001d7f8`
- `0x18001db40`
- `0x18001e4c4`
- `0x18004d56c`
- `0x180063a68`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d9e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d9e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da00`
- `PROPSYS!VariantToInt32WithDefault` at `0x18001d984`
- `PROPSYS!VariantToInt32WithDefault` at `0x18001d984`
- `OLEAUT32!__imp_VariantClear` at `0x18001d9d1`
- `OLEAUT32!__imp_VariantClear` at `0x18001d9d1`

## pseudocode

```c
__int64 __fastcall CResultSetFactory::_CreateSession(
        CResultSetFactory *this,
        const struct _GUID *a2,
        struct IDBProperties *a3,
        struct IUnknown *a4,
        enum PROVIDER_CAPABILITIES *a5,
        const struct _GUID *a6,
        struct IUnknown **a7)
{
  struct IUnknown **v7; // r15
  struct IUnknown *v8; // r14
  struct IDBPropertiesVtbl *lpVtbl; // rax
  __int64 v12; // rcx
  int ContinueOnSite; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx
  _DWORD *v16; // rbx
  unsigned int v17; // edi
  LONG v18; // eax
  unsigned int v19; // r12d
  unsigned int v20; // esi
  __int64 v21; // r14
  __int64 v22; // r15
  __int64 i; // rdi
  LPVOID *p_pv; // [rsp+20h] [rbp-61h]
  LPVOID pv; // [rsp+30h] [rbp-51h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-49h] BYREF
  __int64 v28; // [rsp+40h] [rbp-41h] BYREF
  int v29; // [rsp+48h] [rbp-39h] BYREF
  struct IServiceProvider *v30; // [rsp+50h] [rbp-31h]
  struct IUnknown **v31; // [rsp+58h] [rbp-29h]
  int *v32; // [rsp+60h] [rbp-21h] BYREF
  int v33; // [rsp+68h] [rbp-19h]
  _BYTE v34[20]; // [rsp+6Ch] [rbp-15h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v7 = a7;
  v8 = a4;
  v30 = (struct IServiceProvider *)a4;
  v31 = a7;
  *a7 = 0;
  *(_DWORD *)a5 = 0;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    *(_QWORD *)&v34[4] = a2;
    *(_QWORD *)&v34[12] = 16;
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)DataLayer_CreateSession_Start,
      (_DWORD)a3,
      2,
      (__int64)&v32);
  }
  lpVtbl = a3->lpVtbl;
  v28 = 0;
  ContinueOnSite = ((__int64 (__fastcall *)(struct IDBProperties *, GUID *, __int64 *))lpVtbl->QueryInterface)(
                     a3,
                     &GUID_0c733a8b_2a1c_11ce_ade5_00aa0044773d,
                     &v28);
  if ( ContinueOnSite >= 0 )
  {
    ContinueOnSite = QueryContinueOnSite(v8);
    if ( ContinueOnSite >= 0 )
    {
      ContinueOnSite = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 24LL))(v28);
      if ( ContinueOnSite >= 0 )
      {
        ContinueOnSite = QueryContinueOnSite(v8);
        if ( ContinueOnSite >= 0 )
        {
          *(_DWORD *)a5 = 0;
          v32 = &v29;
          v29 = 0x40000;
          v33 = 1;
          *(GUID *)v34 = DBPROPSET_DATASOURCEINFO;
          *(_DWORD *)&v34[16] = 0;
          v27 = 0;
          pv = 0;
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 4) != 0 )
            McTemplateU0j_EtwEventWriteTransfer(v14, DataLayer_GetDataSourceProperties_Start, a2);
          p_pv = &pv;
          ContinueOnSite = ((__int64 (__fastcall *)(struct IDBProperties *, __int64, int **, unsigned int *))a3->lpVtbl->GetProperties)(
                             a3,
                             1,
                             &v32,
                             &v27);
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 4) != 0 )
            McTemplateU0j_EtwEventWriteTransfer(v15, DataLayer_GetDataSourceProperties_Stop, a2);
          if ( (int)(ContinueOnSite + 0x80000000) < 0 || ContinueOnSite == -2147217887 )
          {
            v16 = pv;
            v17 = 0;
            if ( *((_DWORD *)pv + 2) )
            {
              do
              {
                if ( *(_DWORD *)(*(_QWORD *)v16 + 72LL * v17) == 0x40000 )
                {
                  v18 = VariantToInt32WithDefault((const VARIANT *const)(*(_QWORD *)v16 + 48LL + 72LL * v17), 17);
                  v16 = pv;
                  *(_DWORD *)a5 = v18;
                }
                ++v17;
              }
              while ( v17 < v16[2] );
            }
            v19 = v27;
            v20 = 0;
            pv = 0;
            if ( v27 )
            {
              v21 = 0;
              do
              {
                v22 = 0;
                for ( i = 8 * v21; (unsigned int)v22 < v16[i + 2]; v22 = (unsigned int)(v22 + 1) )
                  VariantClear((VARIANTARG *)(*(_QWORD *)&v16[i] + 8 * (v22 + 8 * v22 + 6)));
                CoTaskMemFree(*(LPVOID *)&v16[i]);
                ++v20;
                ++v21;
              }
              while ( v20 < v19 );
              v8 = (struct IUnknown *)v30;
              v7 = v31;
            }
            CoTaskMemFree(v16);
            pv = 0;
            ContinueOnSite = (**(__int64 (__fastcall ***)(__int64, GUID *, LPVOID *))v28)(
                               v28,
                               &GUID_0c733a5d_2a1c_11ce_ade5_00aa0044773d,
                               &pv);
            if ( ContinueOnSite >= 0 )
            {
              ContinueOnSite = QueryContinueOnSite(v8);
              if ( ContinueOnSite >= 0 )
                ContinueOnSite = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IUnknown **))(*(_QWORD *)pv + 24LL))(
                                   pv,
                                   0,
                                   &GUID_0c733a1d_2a1c_11ce_ade5_00aa0044773d,
                                   v7);
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x238A,
              (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
              (const char *)(unsigned int)ContinueOnSite,
              (int)&pv);
          }
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McTemplateU0j_EtwEventWriteTransfer(v12, DataLayer_CreateSession_Stop, a2);
  if ( ContinueOnSite < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23B6,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)ContinueOnSite,
      (int)p_pv);
  return (unsigned int)ContinueOnSite;
}

```

## disassembly

```asm
0x18001d7f8  mov     [rsp-8+arg_0], rbx
0x18001d7fd  push    rbp
0x18001d7fe  push    rsi
0x18001d7ff  push    rdi
0x18001d800  push    r12
0x18001d802  push    r13
0x18001d804  push    r14
0x18001d806  push    r15
0x18001d808  lea     rbp, [rsp-0Fh]
0x18001d80d  sub     rsp, 90h
0x18001d814  mov     rax, cs:__security_cookie
0x18001d81b  xor     rax, rsp
0x18001d81e  mov     [rbp+3Fh+var_40], rax
0x18001d822  mov     r15, [rbp+3Fh+arg_30]
0x18001d826  xor     r12d, r12d
0x18001d829  mov     rsi, [rbp+3Fh+arg_20]
0x18001d82d  mov     r14, r9
0x18001d830  mov     [rbp+3Fh+var_70], r9
0x18001d834  mov     rdi, r8
0x18001d837  mov     r13, rdx
0x18001d83a  mov     [rbp+3Fh+var_68], r15
0x18001d83e  mov     [r15], r12
0x18001d841  mov     [rsi], r12d
0x18001d844  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18001d84b  jnz     loc_18001DAB3
0x18001d851  mov     rax, [rdi]
0x18001d854  lea     r8, [rbp+3Fh+var_80]
0x18001d858  lea     rdx, _GUID_0c733a8b_2a1c_11ce_ade5_00aa0044773d
0x18001d85f  mov     [rbp+3Fh+var_80], r12
0x18001d863  mov     rcx, rdi
0x18001d866  mov     rax, [rax]
0x18001d869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d86e  mov     ebx, eax
0x18001d870  test    eax, eax
0x18001d872  js      loc_18001DA79
0x18001d878  mov     rcx, r14; struct IUnknown *
0x18001d87b  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x18001d880  mov     ebx, eax
0x18001d882  test    eax, eax
0x18001d884  js      loc_18001DA69
0x18001d88a  mov     rcx, [rbp+3Fh+var_80]
0x18001d88e  mov     rax, [rcx]
0x18001d891  mov     rax, [rax+18h]
0x18001d895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d89a  mov     ebx, eax
0x18001d89c  test    eax, eax
0x18001d89e  js      loc_18001DA69
0x18001d8a4  mov     rcx, r14; struct IUnknown *
0x18001d8a7  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x18001d8ac  mov     ebx, eax
0x18001d8ae  test    eax, eax
0x18001d8b0  js      loc_18001DA69
0x18001d8b6  movups  xmm0, xmmword ptr cs:DBPROPSET_DATASOURCEINFO.Data1
0x18001d8bd  lea     rax, [rbp+3Fh+var_78]
0x18001d8c1  mov     [rsi], r12d
0x18001d8c4  mov     [rbp+3Fh+var_60], rax
0x18001d8c8  mov     ebx, 1
0x18001d8cd  xor     eax, eax
0x18001d8cf  mov     [rbp+3Fh+var_78], 40000h
0x18001d8d6  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 4
0x18001d8dd  mov     [rbp+3Fh+var_58], ebx
0x18001d8e0  movdqu  [rbp+3Fh+var_54], xmm0
0x18001d8e5  mov     [rbp+3Fh+var_44], eax
0x18001d8e8  mov     [rbp+3Fh+var_88], r12d
0x18001d8ec  mov     [rbp+3Fh+pv], r12
0x18001d8f0  jnz     loc_18001DAF0
0x18001d8f6  mov     rax, [rdi]
0x18001d8f9  lea     rcx, [rbp+3Fh+pv]
0x18001d8fd  mov     qword ptr [rsp+0C0h+var_A0], rcx; int
0x18001d902  lea     r9, [rbp+3Fh+var_88]
0x18001d906  lea     r8, [rbp+3Fh+var_60]
0x18001d90a  mov     edx, ebx
0x18001d90c  mov     rcx, rdi
0x18001d90f  mov     rax, [rax+18h]
0x18001d913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d918  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 4
0x18001d91f  mov     ebx, eax
0x18001d921  jnz     loc_18001DB04
0x18001d927  mov     ecx, 80000000h
0x18001d92c  lea     eax, [rbx+rcx]
0x18001d92f  test    ecx, eax
0x18001d931  jnz     short loc_18001D958
0x18001d933  cmp     ebx, 80040E21h
0x18001d939  jz      short loc_18001D958
0x18001d93b  mov     rcx, [rbp+47h]; this
0x18001d93f  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18001d946  mov     r9d, ebx; char *
0x18001d949  mov     edx, 238Ah; void *
0x18001d94e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d953  jmp     loc_18001DA69
0x18001d958  mov     rbx, [rbp+3Fh+pv]
0x18001d95c  mov     edi, r12d
0x18001d95f  cmp     [rbx+8], r12d
0x18001d963  jbe     short loc_18001D997
0x18001d965  mov     eax, edi
0x18001d967  lea     rcx, [rax+rax*8]
0x18001d96b  mov     rax, [rbx]
0x18001d96e  cmp     dword ptr [rax+rcx*8], 40000h
0x18001d975  jnz     short loc_18001D990
0x18001d977  add     rax, 30h ; '0'
0x18001d97b  mov     edx, 11h; lDefault
0x18001d980  lea     rcx, [rax+rcx*8]; varIn
0x18001d984  call    cs:__imp_VariantToInt32WithDefault
0x18001d98a  mov     rbx, [rbp+3Fh+pv]
0x18001d98e  mov     [rsi], eax
0x18001d990  inc     edi
0x18001d992  cmp     edi, [rbx+8]
0x18001d995  jb      short loc_18001D965
0x18001d997  mov     r12d, [rbp+3Fh+var_88]
0x18001d99b  xor     esi, esi
0x18001d99d  mov     [rbp+3Fh+pv], 0
0x18001d9a5  test    r12d, r12d
0x18001d9a8  jz      short loc_18001D9FD
0x18001d9aa  xor     r14d, r14d
0x18001d9ad  mov     rdi, r14
0x18001d9b0  xor     r15d, r15d
0x18001d9b3  shl     rdi, 5
0x18001d9b7  cmp     [rdi+rbx+8], r15d
0x18001d9bc  jbe     short loc_18001D9E1
0x18001d9be  mov     rax, [rdi+rbx]
0x18001d9c2  lea     rcx, ds:6[r15*8]
0x18001d9ca  add     rcx, r15
0x18001d9cd  lea     rcx, [rax+rcx*8]; pvarg
0x18001d9d1  call    cs:__imp_VariantClear
0x18001d9d7  inc     r15d
0x18001d9da  cmp     r15d, [rdi+rbx+8]
0x18001d9df  jb      short loc_18001D9BE
0x18001d9e1  mov     rcx, [rdi+rbx]; pv
0x18001d9e5  call    cs:__imp_CoTaskMemFree
0x18001d9eb  inc     esi
0x18001d9ed  inc     r14
0x18001d9f0  cmp     esi, r12d
0x18001d9f3  jb      short loc_18001D9AD
0x18001d9f5  mov     r14, [rbp+3Fh+var_70]
0x18001d9f9  mov     r15, [rbp+3Fh+var_68]
0x18001d9fd  mov     rcx, rbx; pv
0x18001da00  call    cs:__imp_CoTaskMemFree
0x18001da06  mov     rcx, [rbp+3Fh+var_80]
0x18001da0a  lea     r8, [rbp+3Fh+pv]
0x18001da0e  xor     r12d, r12d
0x18001da11  lea     rdx, _GUID_0c733a5d_2a1c_11ce_ade5_00aa0044773d
0x18001da18  mov     [rbp+3Fh+pv], r12
0x18001da1c  mov     rax, [rcx]
0x18001da1f  mov     rax, [rax]
0x18001da22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da27  mov     ebx, eax
0x18001da29  test    eax, eax
0x18001da2b  js      short loc_18001DA69
0x18001da2d  mov     rcx, r14; struct IUnknown *
0x18001da30  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x18001da35  mov     ebx, eax
0x18001da37  test    eax, eax
0x18001da39  js      short loc_18001DA59
0x18001da3b  mov     rcx, [rbp+3Fh+pv]
0x18001da3f  lea     r8, _GUID_0c733a1d_2a1c_11ce_ade5_00aa0044773d
0x18001da46  mov     r9, r15
0x18001da49  xor     edx, edx
0x18001da4b  mov     rax, [rcx]
0x18001da4e  mov     rax, [rax+18h]
0x18001da52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da57  mov     ebx, eax
0x18001da59  mov     rcx, [rbp+3Fh+pv]
0x18001da5d  mov     rax, [rcx]
0x18001da60  mov     rax, [rax+10h]
0x18001da64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da69  mov     rcx, [rbp+3Fh+var_80]
0x18001da6d  mov     rax, [rcx]
0x18001da70  mov     rax, [rax+10h]
0x18001da74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da79  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18001da80  jnz     short loc_18001DADF
0x18001da82  test    ebx, ebx
0x18001da84  js      loc_18001DB18
0x18001da8a  mov     eax, ebx
0x18001da8c  mov     rcx, [rbp+3Fh+var_40]
0x18001da90  xor     rcx, rsp; StackCookie
0x18001da93  call    __security_check_cookie
0x18001da98  mov     rbx, [rsp+0C0h+arg_0]
0x18001daa0  add     rsp, 90h
0x18001daa7  pop     r15
0x18001daa9  pop     r14
0x18001daab  pop     r13
0x18001daad  pop     r12
0x18001daaf  pop     rdi
0x18001dab0  pop     rsi
0x18001dab1  pop     rbp
0x18001dab2  retn
0x18001dab3  lea     rax, [rbp+3Fh+var_60]
0x18001dab7  mov     qword ptr [rbp+3Fh+var_54+4], r13
0x18001dabb  mov     r9d, 2
0x18001dac1  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001dac6  lea     rdx, DataLayer_CreateSession_Start
0x18001dacd  mov     qword ptr [rbp+3Fh+var_54+0Ch], 10h
0x18001dad5  call    McGenEventWrite_EtwEventWriteTransfer
0x18001dada  jmp     loc_18001D851
0x18001dadf  mov     r8, r13
0x18001dae2  lea     rdx, DataLayer_CreateSession_Stop
0x18001dae9  call    McTemplateU0j_EtwEventWriteTransfer
0x18001daee  jmp     short loc_18001DA82
0x18001daf0  mov     r8, r13
0x18001daf3  lea     rdx, DataLayer_GetDataSourceProperties_Start
0x18001dafa  call    McTemplateU0j_EtwEventWriteTransfer
0x18001daff  jmp     loc_18001D8F6
0x18001db04  mov     r8, r13
0x18001db07  lea     rdx, DataLayer_GetDataSourceProperties_Stop
0x18001db0e  call    McTemplateU0j_EtwEventWriteTransfer
0x18001db13  jmp     loc_18001D927
0x18001db18  mov     rcx, [rbp+47h]; this
0x18001db1c  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18001db23  mov     r9d, ebx; char *
0x18001db26  mov     edx, 23B6h; void *
0x18001db2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db30  jmp     loc_18001DA8A
```
