# CDataSourceControl::~CDataSourceControl(void)

- ea: `0x1800a82f0`
- end: `0x1800a85b8`
- name: `??1CDataSourceControl@@QEAA@XZ`
- size: `712`
- prototype: `void __fastcall(CDataSourceControl *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800a85f0`

## callees

- `0x180019840`
- `0x180019870`
- `0x180020220`
- `0x1800a82f0`
- `0x1800a87e4`
- `0x1800a9780`
- `0x1800acfb4`
- `0x1800d7010`

## import_xrefs

- `msvcrt!free` at `0x1800a8400`
- `msvcrt!free` at `0x1800a840d`
- `msvcrt!free` at `0x1800a851a`
- `msvcrt!free` at `0x1800a8537`
- `msvcrt!free` at `0x1800a8400`
- `msvcrt!free` at `0x1800a840d`
- `msvcrt!free` at `0x1800a851a`
- `msvcrt!free` at `0x1800a8537`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a84c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a84d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a84c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a84d6`
- `OLEAUT32!__imp_VariantClear` at `0x1800a83e9`
- `OLEAUT32!__imp_VariantClear` at `0x1800a83e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDataSourceControl::~CDataSourceControl(CDataSourceControl *this)
{
  CDataSourceControl *v1; // rbx
  _QWORD *v2; // rcx
  int v3; // edi
  int v4; // eax
  bool v5; // zf
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  int i; // esi
  __int64 v10; // rdi
  struct __POSITION *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  void *v14; // rcx
  ATL::CAccessorBase *v15; // rcx
  void *v16; // rdi
  void *v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned int *v20; // rdi
  CException *v21; // [rsp+20h] [rbp-28h] BYREF
  struct __POSITION *j; // [rsp+58h] [rbp+10h] BYREF
  __int64 v25; // [rsp+60h] [rbp+18h] BYREF

  try
  {
    v1 = this;
    *(_QWORD *)this = &CDataSourceControl::`vftable';
    if ( *((_DWORD *)this + 44) )
    {
      v2 = (_QWORD *)*((_QWORD *)this + 20);
      if ( v2 )
      {
        v25 = 0;
        if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v2)(*v2, &IID_IConnectionPointContainer, &v25) >= 0 )
        {
          j = 0;
          if ( (*(int (__fastcall **)(__int64, GUID *, struct __POSITION **))(*(_QWORD *)v25 + 32LL))(
                 v25,
                 &IID_IRowsetNotify,
                 &j) >= 0 )
          {
            (*(void (__fastcall **)(struct __POSITION *, _QWORD))(*(_QWORD *)j + 48LL))(j, *((unsigned int *)v1 + 44));
            (*(void (__fastcall **)(struct __POSITION *))(*(_QWORD *)j + 16LL))(j);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
      }
    }
    while ( *((_QWORD *)v1 + 9) )
    {
      v20 = *(unsigned int **)(*((_QWORD *)v1 + 7) + 16LL);
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v20 + 384LL))(*(_QWORD *)v20, v20[3], 0);
      *(_QWORD *)(*(_QWORD *)v20 + 240LL) = 0;
    }
    CObList::RemoveAll((CDataSourceControl *)((char *)v1 + 48));
    if ( *((_QWORD *)v1 + 16) )
    {
      v3 = 0;
      v4 = *((_DWORD *)v1 + 28);
      v5 = v4 == 0;
      if ( v4 > 0 )
      {
        do
        {
          VariantClear((VARIANTARG *)(*((_QWORD *)v1 + 16) + 24LL * v3++));
          v6 = *((_DWORD *)v1 + 28);
        }
        while ( v3 < v6 );
        v5 = v6 == 0;
      }
      if ( !v5 )
      {
        free(*((void **)v1 + 15));
        free(*((void **)v1 + 16));
      }
    }
    v7 = *((_QWORD *)v1 + 2);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = *((_QWORD *)v1 + 3);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( *((_QWORD *)v1 + 5) )
    {
      for ( i = 0; i < *((_QWORD *)v1 + 4); ++i )
      {
        v10 = (__int64)i << 6;
        v11 = *(struct __POSITION **)(*(_QWORD *)(*((_QWORD *)v1 + 5) + v10 + 56) + 8LL);
        for ( j = v11; ; v11 = j )
        {
          v12 = *((_QWORD *)v1 + 5);
          if ( !v11 )
            break;
          *((_QWORD *)*CObList::GetNext(*(CObList **)(v12 + v10 + 56), &j) + 30) = 0;
        }
        CObList::RemoveAll(*(CObList **)(v10 + v12 + 56));
        v13 = *(_QWORD *)(v10 + *((_QWORD *)v1 + 5) + 56);
        if ( v13 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, 1);
      }
      CoTaskMemFree(*((LPVOID *)v1 + 5));
    }
    v14 = (void *)*((_QWORD *)v1 + 13);
    if ( v14 )
      CoTaskMemFree(v14);
    v15 = (ATL::CAccessorBase *)*((_QWORD *)v1 + 21);
    if ( v15 )
    {
      ATL::CAccessorBase::ReleaseAccessors(v15, **((struct IUnknown ***)v1 + 20));
      ATL::CDynamicAccessor::Close(*((ATL::CDynamicAccessor **)v1 + 21));
    }
    v16 = (void *)*((_QWORD *)v1 + 21);
    if ( v16 )
    {
      ATL::CDynamicAccessor::Close(*((ATL::CDynamicAccessor **)v1 + 21));
      free(v16);
    }
    v17 = (void *)*((_QWORD *)v1 + 20);
    if ( v17 )
    {
      ATL::CRowset::~CRowset(*((ATL::CRowset **)v1 + 20));
      free(v17);
    }
    v18 = *((_QWORD *)v1 + 19);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v19 = *((_QWORD *)v1 + 18);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  catch ( CException *v21 )
  {
    if ( v21 )
      CException::Delete(v21);
    v1 = this;
  }
  CPtrList::~CPtrList((CDataSourceControl *)((char *)v1 + 48));
}

```

## disassembly

```asm
0x1800a82f0  mov     [rsp+arg_0], rcx
0x1800a82f5  push    rbx
0x1800a82f6  push    rsi
0x1800a82f7  push    rdi
0x1800a82f8  sub     rsp, 30h
0x1800a82fc  mov     rbx, rcx
0x1800a82ff  lea     rax, ??_7CDataSourceControl@@6B@; const CDataSourceControl::`vftable'
0x1800a8306  mov     [rcx], rax
0x1800a8309  cmp     dword ptr [rcx+0B0h], 0
0x1800a8310  jz      loc_1800A83B0
0x1800a8316  mov     rcx, [rcx+0A0h]
0x1800a831d  test    rcx, rcx
0x1800a8320  jz      loc_1800A83B0
0x1800a8326  mov     [rsp+48h+arg_10], 0
0x1800a832f  mov     rcx, [rcx]
0x1800a8332  mov     rax, [rcx]
0x1800a8335  lea     r8, [rsp+48h+arg_10]
0x1800a833a  lea     rdx, IID_IConnectionPointContainer
0x1800a8341  mov     rax, [rax]
0x1800a8344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8349  test    eax, eax
0x1800a834b  js      short loc_1800A83B0
0x1800a834d  mov     [rsp+48h+arg_8], 0
0x1800a8356  mov     rcx, [rsp+48h+arg_10]
0x1800a835b  mov     rax, [rcx]
0x1800a835e  lea     r8, [rsp+48h+arg_8]
0x1800a8363  lea     rdx, IID_IRowsetNotify
0x1800a836a  mov     rax, [rax+20h]
0x1800a836e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8373  test    eax, eax
0x1800a8375  js      short loc_1800A839F
0x1800a8377  mov     rcx, [rsp+48h+arg_8]
0x1800a837c  mov     rax, [rcx]
0x1800a837f  mov     edx, [rbx+0B0h]
0x1800a8385  mov     rax, [rax+30h]
0x1800a8389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a838e  mov     rcx, [rsp+48h+arg_8]
0x1800a8393  mov     rax, [rcx]
0x1800a8396  mov     rax, [rax+10h]
0x1800a839a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a839f  mov     rcx, [rsp+48h+arg_10]
0x1800a83a4  mov     rax, [rcx]
0x1800a83a7  mov     rax, [rax+10h]
0x1800a83ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a83b0  cmp     qword ptr [rbx+48h], 0
0x1800a83b5  jnz     loc_1800A8570
0x1800a83bb  lea     rcx, [rbx+30h]; this
0x1800a83bf  call    ?RemoveAll@CObList@@QEAAXXZ; CObList::RemoveAll(void)
0x1800a83c4  cmp     qword ptr [rbx+80h], 0
0x1800a83cc  jz      short loc_1800A8413
0x1800a83ce  xor     edi, edi
0x1800a83d0  mov     eax, [rbx+70h]
0x1800a83d3  test    eax, eax
0x1800a83d5  jle     short loc_1800A83FA
0x1800a83d7  movsxd  rax, edi
0x1800a83da  lea     rcx, [rax+rax*2]
0x1800a83de  mov     rax, [rbx+80h]
0x1800a83e5  lea     rcx, [rax+rcx*8]; pvarg
0x1800a83e9  call    cs:__imp_VariantClear
0x1800a83ef  inc     edi
0x1800a83f1  mov     eax, [rbx+70h]
0x1800a83f4  cmp     edi, eax
0x1800a83f6  jl      short loc_1800A83D7
0x1800a83f8  test    eax, eax
0x1800a83fa  jz      short loc_1800A8413
0x1800a83fc  mov     rcx, [rbx+78h]; Block
0x1800a8400  call    cs:__imp_free
0x1800a8406  mov     rcx, [rbx+80h]; Block
0x1800a840d  call    cs:__imp_free
0x1800a8413  mov     rcx, [rbx+10h]
0x1800a8417  test    rcx, rcx
0x1800a841a  jz      short loc_1800A8428
0x1800a841c  mov     rax, [rcx]
0x1800a841f  mov     rax, [rax+10h]
0x1800a8423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8428  mov     rcx, [rbx+18h]
0x1800a842c  test    rcx, rcx
0x1800a842f  jz      short loc_1800A843D
0x1800a8431  mov     rax, [rcx]
0x1800a8434  mov     rax, [rax+10h]
0x1800a8438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a843d  cmp     qword ptr [rbx+28h], 0
0x1800a8442  jz      loc_1800A84CD
0x1800a8448  xor     esi, esi
0x1800a844a  movsxd  rdi, esi
0x1800a844d  cmp     rdi, [rbx+20h]
0x1800a8451  jge     short loc_1800A84C3
0x1800a8453  shl     rdi, 6
0x1800a8457  mov     rax, [rbx+28h]
0x1800a845b  mov     rcx, [rax+rdi+38h]
0x1800a8460  mov     rax, [rcx+8]
0x1800a8464  mov     [rsp+48h+arg_8], rax
0x1800a8469  mov     rcx, [rbx+28h]
0x1800a846d  test    rax, rax
0x1800a8470  jz      short loc_1800A8496
0x1800a8472  lea     rdx, [rsp+48h+arg_8]; struct __POSITION **
0x1800a8477  mov     rcx, [rcx+rdi+38h]; this
0x1800a847c  call    ?GetNext@CObList@@QEAAAEAPEAVCObject@@AEAPEAU__POSITION@@@Z; CObList::GetNext(__POSITION * &)
0x1800a8481  mov     rax, [rax]
0x1800a8484  mov     qword ptr [rax+0F0h], 0
0x1800a848f  mov     rax, [rsp+48h+arg_8]
0x1800a8494  jmp     short loc_1800A8469
0x1800a8496  mov     rcx, [rdi+rcx+38h]; this
0x1800a849b  call    ?RemoveAll@CObList@@QEAAXXZ; CObList::RemoveAll(void)
0x1800a84a0  mov     rax, [rbx+28h]
0x1800a84a4  mov     rcx, [rdi+rax+38h]
0x1800a84a9  test    rcx, rcx
0x1800a84ac  jz      short loc_1800A84BF
0x1800a84ae  mov     rax, [rcx]
0x1800a84b1  mov     edx, 1
0x1800a84b6  mov     rax, [rax+8]
0x1800a84ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a84bf  inc     esi
0x1800a84c1  jmp     short loc_1800A844A
0x1800a84c3  mov     rcx, [rbx+28h]; pv
0x1800a84c7  call    cs:__imp_CoTaskMemFree
0x1800a84cd  mov     rcx, [rbx+68h]; pv
0x1800a84d1  test    rcx, rcx
0x1800a84d4  jz      short loc_1800A84DC
0x1800a84d6  call    cs:__imp_CoTaskMemFree
0x1800a84dc  mov     rcx, [rbx+0A8h]; this
0x1800a84e3  test    rcx, rcx
0x1800a84e6  jz      short loc_1800A8503
0x1800a84e8  mov     rdx, [rbx+0A0h]
0x1800a84ef  mov     rdx, [rdx]; struct IUnknown *
0x1800a84f2  call    ?ReleaseAccessors@CAccessorBase@ATL@@QEAAJPEAUIUnknown@@@Z; ATL::CAccessorBase::ReleaseAccessors(IUnknown *)
0x1800a84f7  mov     rcx, [rbx+0A8h]; this
0x1800a84fe  call    ?Close@CDynamicAccessor@ATL@@QEAAXXZ; ATL::CDynamicAccessor::Close(void)
0x1800a8503  mov     rdi, [rbx+0A8h]
0x1800a850a  test    rdi, rdi
0x1800a850d  jz      short loc_1800A8520
0x1800a850f  mov     rcx, rdi; this
0x1800a8512  call    ?Close@CDynamicAccessor@ATL@@QEAAXXZ; ATL::CDynamicAccessor::Close(void)
0x1800a8517  mov     rcx, rdi; Block
0x1800a851a  call    cs:__imp_free
0x1800a8520  mov     rdi, [rbx+0A0h]
0x1800a8527  test    rdi, rdi
0x1800a852a  jz      short loc_1800A853D
0x1800a852c  mov     rcx, rdi; this
0x1800a852f  call    ??1CRowset@ATL@@QEAA@XZ; ATL::CRowset::~CRowset(void)
0x1800a8534  mov     rcx, rdi; Block
0x1800a8537  call    cs:__imp_free
0x1800a853d  mov     rcx, [rbx+98h]
0x1800a8544  test    rcx, rcx
0x1800a8547  jz      short loc_1800A8555
0x1800a8549  mov     rax, [rcx]
0x1800a854c  mov     rax, [rax+10h]
0x1800a8550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8555  mov     rcx, [rbx+90h]
0x1800a855c  test    rcx, rcx
0x1800a855f  jz      short loc_1800A856E
0x1800a8561  mov     rax, [rcx]
0x1800a8564  mov     rax, [rax+10h]
0x1800a8568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a856d  nop
0x1800a856e  jmp     short loc_1800A85A8
0x1800a8570  mov     rax, [rbx+38h]
0x1800a8574  mov     rdi, [rax+10h]
0x1800a8578  mov     rcx, [rdi]
0x1800a857b  mov     rax, [rcx]
0x1800a857e  xor     r8d, r8d
0x1800a8581  mov     edx, [rdi+0Ch]
0x1800a8584  mov     rax, [rax+180h]
0x1800a858b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8590  mov     rax, [rdi]
0x1800a8593  mov     qword ptr [rax+0F0h], 0
0x1800a859e  jmp     loc_1800A83B0
0x1800a85a3  mov     rbx, [rsp+48h+arg_0]
0x1800a85a8  lea     rcx, [rbx+30h]; this
0x1800a85ac  add     rsp, 30h
0x1800a85b0  pop     rdi
0x1800a85b1  pop     rsi
0x1800a85b2  pop     rbx
0x1800a85b3  jmp     ??1CPtrList@@UEAA@XZ; CPtrList::~CPtrList(void)
```
