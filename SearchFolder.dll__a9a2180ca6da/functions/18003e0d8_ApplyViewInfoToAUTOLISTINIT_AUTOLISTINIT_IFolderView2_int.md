# ApplyViewInfoToAUTOLISTINIT(AUTOLISTINIT *,IFolderView2 *,int)

- ea: `0x18003e0d8`
- end: `0x18003e3aa`
- name: `?ApplyViewInfoToAUTOLISTINIT@@YAJPEAUAUTOLISTINIT@@PEAUIFolderView2@@H@Z`
- size: `722`
- prototype: `__int64 __fastcall(struct AUTOLISTINIT *, struct IFolderView2 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003e5d0`

## callees

- `0x180006924`
- `0x180009d00`
- `0x18000f718`
- `0x180013340`
- `0x18003dfac`
- `0x18003e020`
- `0x18003e0d8`
- `0x18003e4f0`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18003e352`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18003e352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e35c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e35c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e393`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e37a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e37a`

## pseudocode

```c
__int64 __fastcall ApplyViewInfoToAUTOLISTINIT(struct AUTOLISTINIT *a1, struct IFolderView2 *a2, int a3)
{
  struct IFolderView2Vtbl *lpVtbl; // r9
  int v7; // ebx
  int v8; // eax
  struct IFolderView2Vtbl *v9; // rax
  void *v10; // rcx
  void *v11; // r15
  struct IFolderView2Vtbl *v12; // rax
  unsigned int v13; // edx
  void *v14; // rcx
  char *v15; // r12
  CColumnList *v16; // rax
  IUnknown *v17; // rdi
  __int64 v18; // r14
  int appended; // eax
  unsigned int v20; // eax
  unsigned __int64 v22; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int64 v26; // [rsp+A0h] [rbp+50h] BYREF
  int v27; // [rsp+A8h] [rbp+58h] BYREF

  lpVtbl = a2->lpVtbl;
  v27 = 0;
  v7 = ((__int64 (__fastcall *)(struct IFolderView2 *, int *, char *))lpVtbl->GetViewModeAndIconSize)(
         a2,
         &v27,
         (char *)a1 + (a3 != 0 ? 8 : 0) + 48);
  if ( v7 >= 0 )
  {
    v8 = 3;
    switch ( v27 )
    {
      case 3:
        v8 = 4;
        break;
      case 4:
        v8 = 1;
        break;
      case 6:
        v8 = 2;
        break;
      case 8:
        v8 = 5;
        break;
    }
    if ( a3 )
      *((_DWORD *)a1 + 13) = v8;
    else
      *((_DWORD *)a1 + 11) = v8;
    v7 = ((__int64 (__fastcall *)(struct IFolderView2 *, char *, _QWORD))a2->lpVtbl->GetGroupBy)(a2, (char *)a1 + 60, 0);
    if ( v7 >= 0 )
    {
      v9 = a2->lpVtbl;
      v25 = 0;
      v7 = ((__int64 (__fastcall *)(struct IFolderView2 *, unsigned int *))v9->GetSortColumnCount)(a2, &v25);
      if ( v7 >= 0 )
      {
        if ( v25 )
        {
          pv = 0;
          v22 = 0;
          v7 = ULongLongMult((int)v25, 0x18u, &v22);
          if ( v7 >= 0 )
          {
            v7 = CTCoAllocPolicy::Alloc(v10, 1u, v22, &pv);
            if ( v7 >= 0 )
            {
              v11 = pv;
              v7 = ((__int64 (__fastcall *)(struct IFolderView2 *, LPVOID, _QWORD))a2->lpVtbl->GetSortColumns)(
                     a2,
                     pv,
                     v25);
              if ( v7 >= 0 )
              {
                v12 = a2->lpVtbl;
                v22 = 0;
                v7 = ((__int64 (__fastcall *)(struct IFolderView2 *, GUID *, unsigned __int64 *))v12->QueryInterface)(
                       a2,
                       &GUID_d8ec27bb_3f3b_4042_b10a_4acfd924d453,
                       &v22);
                if ( v7 >= 0 )
                {
                  LODWORD(v26) = 0;
                  v7 = (*(__int64 (__fastcall **)(unsigned __int64, __int64, unsigned __int64 *))(*(_QWORD *)v22 + 40LL))(
                         v22,
                         2,
                         &v26);
                  if ( v7 >= 0 )
                  {
                    hMem = 0;
                    pv = 0;
                    v7 = ULongLongMult((unsigned int)v26, 0x14u, (unsigned __int64 *)&pv);
                    if ( v7 >= 0 )
                    {
                      v7 = CTLocalAllocPolicy::Alloc(v14, v13, (unsigned __int64)pv, &hMem);
                      if ( v7 >= 0 )
                      {
                        v15 = (char *)hMem;
                        v7 = (*(__int64 (__fastcall **)(unsigned __int64, __int64, HLOCAL, _QWORD))(*(_QWORD *)v22 + 48LL))(
                               v22,
                               2,
                               hMem,
                               (unsigned int)v26);
                        if ( v7 >= 0 )
                        {
                          v7 = -2147024882;
                          v16 = (CColumnList *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
                          if ( v16 )
                          {
                            v17 = (IUnknown *)CColumnList::CColumnList(v16);
                            if ( v17 )
                            {
                              v7 = 0;
                              v18 = 0;
                              while ( (unsigned int)v18 < (unsigned int)v26 )
                              {
                                appended = CColumnList::AppendColumn(v17, &v15[20 * v18], 1);
                                v18 = (unsigned int)(v18 + 1);
                                v7 = appended;
                                if ( appended < 0 )
                                  goto LABEL_31;
                              }
                              IUnknown_Set((IUnknown **)a1 + 14, v17);
                              CoTaskMemFree(*((LPVOID *)a1 + 13));
                              v20 = v25;
                              *((_QWORD *)a1 + 13) = v11;
                              v11 = 0;
                              *((_DWORD *)a1 + 24) = v20;
LABEL_31:
                              CColumnList::Release((CColumnList *)v17);
                            }
                          }
                        }
                        LocalFree(v15);
                      }
                    }
                  }
                  (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v22 + 16LL))(v22);
                }
              }
              CoTaskMemFree(v11);
            }
          }
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e0d8  push    rbp
0x18003e0da  push    rbx
0x18003e0db  push    rsi
0x18003e0dc  push    rdi
0x18003e0dd  push    r12
0x18003e0df  push    r14
0x18003e0e1  push    r15
0x18003e0e3  mov     rbp, rsp
0x18003e0e6  sub     rsp, 50h
0x18003e0ea  mov     r9, [rdx]
0x18003e0ed  mov     eax, r8d
0x18003e0f0  mov     r14d, r8d
0x18003e0f3  mov     [rbp+arg_18], 0
0x18003e0fa  neg     eax
0x18003e0fc  mov     rsi, rcx
0x18003e0ff  mov     rdi, rdx
0x18003e102  lea     rdx, [rbp+arg_18]
0x18003e106  mov     rax, [r9+120h]
0x18003e10d  sbb     r8, r8
0x18003e110  add     rcx, 30h ; '0'
0x18003e114  and     r8d, 8
0x18003e118  add     r8, rcx
0x18003e11b  mov     rcx, rdi
0x18003e11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e123  mov     ebx, eax
0x18003e125  test    eax, eax
0x18003e127  js      loc_18003E399
0x18003e12d  mov     ecx, [rbp+arg_18]
0x18003e130  mov     eax, 3
0x18003e135  lea     r12d, [rax-1]
0x18003e139  lea     r15d, [rax-2]
0x18003e13d  sub     ecx, eax
0x18003e13f  jz      short loc_18003E161
0x18003e141  sub     ecx, r15d
0x18003e144  jz      short loc_18003E15C
0x18003e146  sub     ecx, r12d
0x18003e149  jz      short loc_18003E157
0x18003e14b  cmp     ecx, r12d
0x18003e14e  jnz     short loc_18003E166
0x18003e150  lea     eax, [r12+3]
0x18003e155  jmp     short loc_18003E166
0x18003e157  mov     eax, r12d
0x18003e15a  jmp     short loc_18003E166
0x18003e15c  mov     eax, r15d
0x18003e15f  jmp     short loc_18003E166
0x18003e161  mov     eax, 4
0x18003e166  test    r14d, r14d
0x18003e169  jz      short loc_18003E170
0x18003e16b  mov     [rsi+34h], eax
0x18003e16e  jmp     short loc_18003E173
0x18003e170  mov     [rsi+2Ch], eax
0x18003e173  mov     rax, [rdi]
0x18003e176  lea     rdx, [rsi+3Ch]
0x18003e17a  xor     r8d, r8d
0x18003e17d  mov     rcx, rdi
0x18003e180  mov     rax, [rax+90h]
0x18003e187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e18c  mov     ebx, eax
0x18003e18e  test    eax, eax
0x18003e190  js      loc_18003E399
0x18003e196  mov     rax, [rdi]
0x18003e199  lea     rdx, [rbp+arg_8]
0x18003e19d  mov     rcx, rdi
0x18003e1a0  mov     [rbp+arg_8], 0
0x18003e1a7  mov     rax, [rax+0D0h]
0x18003e1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1b3  mov     ebx, eax
0x18003e1b5  test    eax, eax
0x18003e1b7  js      loc_18003E399
0x18003e1bd  movsxd  rax, [rbp+arg_8]
0x18003e1c1  test    eax, eax
0x18003e1c3  jz      loc_18003E399
0x18003e1c9  mov     rcx, rax; unsigned __int64
0x18003e1cc  mov     [rbp+pv], 0
0x18003e1d4  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18003e1d8  mov     [rbp+var_20], 0
0x18003e1e0  mov     edx, 18h; unsigned __int64
0x18003e1e5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003e1ea  mov     ebx, eax
0x18003e1ec  test    eax, eax
0x18003e1ee  js      loc_18003E399
0x18003e1f4  mov     r8, [rbp+var_20]; unsigned __int64
0x18003e1f8  lea     r9, [rbp+pv]; void **
0x18003e1fc  mov     edx, r15d; unsigned int
0x18003e1ff  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003e204  mov     ebx, eax
0x18003e206  test    eax, eax
0x18003e208  js      loc_18003E399
0x18003e20e  mov     rax, [rdi]
0x18003e211  mov     rcx, rdi
0x18003e214  mov     r15, [rbp+pv]
0x18003e218  mov     r8d, [rbp+arg_8]
0x18003e21c  mov     rdx, r15
0x18003e21f  mov     rax, [rax+0E0h]
0x18003e226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e22b  mov     ebx, eax
0x18003e22d  test    eax, eax
0x18003e22f  js      loc_18003E390
0x18003e235  mov     rax, [rdi]
0x18003e238  lea     r8, [rbp+var_20]
0x18003e23c  lea     rdx, _GUID_d8ec27bb_3f3b_4042_b10a_4acfd924d453
0x18003e243  mov     [rbp+var_20], 0
0x18003e24b  mov     rcx, rdi
0x18003e24e  mov     rax, [rax]
0x18003e251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e256  mov     ebx, eax
0x18003e258  test    eax, eax
0x18003e25a  js      loc_18003E390
0x18003e260  mov     rcx, [rbp+var_20]
0x18003e264  lea     r8, [rbp+arg_10]
0x18003e268  mov     dword ptr [rbp+arg_10], 0
0x18003e26f  mov     edx, r12d
0x18003e272  mov     rax, [rcx]
0x18003e275  mov     rax, [rax+28h]
0x18003e279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e27e  mov     ebx, eax
0x18003e280  test    eax, eax
0x18003e282  js      loc_18003E380
0x18003e288  mov     ecx, dword ptr [rbp+arg_10]; unsigned __int64
0x18003e28b  lea     r8, [rbp+pv]; unsigned __int64 *
0x18003e28f  mov     edx, 14h; unsigned __int64
0x18003e294  mov     [rbp+hMem], 0
0x18003e29c  mov     [rbp+pv], 0
0x18003e2a4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003e2a9  mov     ebx, eax
0x18003e2ab  test    eax, eax
0x18003e2ad  js      loc_18003E380
0x18003e2b3  mov     r8, [rbp+pv]; unsigned __int64
0x18003e2b7  lea     r9, [rbp+hMem]; void **
0x18003e2bb  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003e2c0  mov     ebx, eax
0x18003e2c2  test    eax, eax
0x18003e2c4  js      loc_18003E380
0x18003e2ca  mov     rcx, [rbp+var_20]
0x18003e2ce  mov     edx, 2
0x18003e2d3  mov     r12, [rbp+hMem]
0x18003e2d7  mov     r9d, dword ptr [rbp+arg_10]
0x18003e2db  mov     r8, r12
0x18003e2de  mov     rax, [rcx]
0x18003e2e1  mov     rax, [rax+30h]
0x18003e2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2ea  mov     ebx, eax
0x18003e2ec  test    eax, eax
0x18003e2ee  js      loc_18003E377
0x18003e2f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e2fb  mov     ecx, 20h ; ' '; unsigned __int64
0x18003e300  mov     ebx, 8007000Eh
0x18003e305  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e30a  test    rax, rax
0x18003e30d  jz      short loc_18003E377
0x18003e30f  mov     rcx, rax; this
0x18003e312  call    ??0CColumnList@@QEAA@XZ; CColumnList::CColumnList(void)
0x18003e317  mov     rdi, rax
0x18003e31a  test    rax, rax
0x18003e31d  jz      short loc_18003E377
0x18003e31f  xor     ebx, ebx
0x18003e321  xor     r14d, r14d
0x18003e324  cmp     r14d, dword ptr [rbp+arg_10]
0x18003e328  jnb     short loc_18003E34B
0x18003e32a  lea     rdx, [r14+r14*4]
0x18003e32e  mov     r8d, 1
0x18003e334  lea     rdx, [r12+rdx*4]
0x18003e338  mov     rcx, rdi
0x18003e33b  call    ?AppendColumn@CColumnList@@UEAAJAEBU_tagpropertykey@@W4COLUMN_VISIBILITY@@@Z; CColumnList::AppendColumn(_tagpropertykey const &,COLUMN_VISIBILITY)
0x18003e340  inc     r14d
0x18003e343  mov     ebx, eax
0x18003e345  test    eax, eax
0x18003e347  jns     short loc_18003E324
0x18003e349  jmp     short loc_18003E36F
0x18003e34b  lea     rcx, [rsi+70h]; ppunk
0x18003e34f  mov     rdx, rdi; punk
0x18003e352  call    cs:__imp_IUnknown_Set
0x18003e358  mov     rcx, [rsi+68h]; pv
0x18003e35c  call    cs:__imp_CoTaskMemFree
0x18003e362  mov     eax, [rbp+arg_8]
0x18003e365  mov     [rsi+68h], r15
0x18003e369  xor     r15d, r15d
0x18003e36c  mov     [rsi+60h], eax
0x18003e36f  mov     rcx, rdi; this
0x18003e372  call    ?Release@CColumnList@@UEAAKXZ; CColumnList::Release(void)
0x18003e377  mov     rcx, r12; hMem
0x18003e37a  call    cs:__imp_LocalFree
0x18003e380  mov     rcx, [rbp+var_20]
0x18003e384  mov     rax, [rcx]
0x18003e387  mov     rax, [rax+10h]
0x18003e38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e390  mov     rcx, r15; pv
0x18003e393  call    cs:__imp_CoTaskMemFree
0x18003e399  mov     eax, ebx
0x18003e39b  add     rsp, 50h
0x18003e39f  pop     r15
0x18003e3a1  pop     r14
0x18003e3a3  pop     r12
0x18003e3a5  pop     rdi
0x18003e3a6  pop     rsi
0x18003e3a7  pop     rbx
0x18003e3a8  pop     rbp
0x18003e3a9  retn
```
