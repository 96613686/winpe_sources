# CDeployUpdate::~CDeployUpdate(void)

- ea: `0x180015b94`
- end: `0x180015d1e`
- name: `??1CDeployUpdate@@UEAA@XZ`
- size: `394`
- prototype: `void __fastcall(CDeployUpdate *this, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180015e10`

## callees

- `0x18000c14c`
- `0x18000dce4`
- `0x180015b94`
- `0x180015d24`
- `0x180015f78`
- `0x180061d54`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015cea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015cea`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall CDeployUpdate::~CDeployUpdate(CDeployUpdate *this, const struct std::nothrow_t *a2)
{
  __int64 i; // rdi
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  *(_QWORD *)this = &CDeployUpdate::`vftable';
  if ( *((_QWORD *)this + 69) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 137); i = (unsigned int)(i + 1) )
    {
      v4 = *(_QWORD *)(*((_QWORD *)this + 69) + 8 * i);
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *(_QWORD *)(*((_QWORD *)this + 69) + 8 * i) = 0;
    }
  }
  operator delete(*((void **)this + 69), a2);
  *((_QWORD *)this + 69) = 0;
  FreeObject((CDeployUpdate *)((char *)this + 200), 1);
  CDeployUpdate::CleanupProps(this);
  v5 = (void *)*((_QWORD *)this + 74);
  if ( v5 )
  {
    operator delete(v5, (const struct std::nothrow_t *)0x90);
    *((_QWORD *)this + 74) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 73);
  if ( v6 )
  {
    operator delete(v6, (const struct std::nothrow_t *)0x90);
    *((_QWORD *)this + 73) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 71);
  if ( v7 )
  {
    SusFree(v7);
    *((_QWORD *)this + 71) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 58);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)this + 58) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 57);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 57) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 56);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)this + 56) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 55);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *((_QWORD *)this + 55) = 0;
  }
  UpdateDeploymentStatusData::~UpdateDeploymentStatusData((CDeployUpdate *)((char *)this + 16));
  *(_QWORD *)this = &CUnknownImpl<IDeploymentUpdate>::`vftable';
}

```

## disassembly

```asm
0x180015b94  mov     [rsp+arg_0], rbx
0x180015b99  mov     [rsp+arg_8], rsi
0x180015b9e  push    rdi
0x180015b9f  sub     rsp, 20h
0x180015ba3  mov     rbx, rcx
0x180015ba6  lea     rax, ??_7CDeployUpdate@@6B@; const CDeployUpdate::`vftable'
0x180015bad  mov     [rcx], rax
0x180015bb0  cmp     qword ptr [rcx+228h], 0
0x180015bb8  jz      short loc_180015BF9
0x180015bba  xor     edi, edi
0x180015bbc  cmp     [rcx+224h], edi
0x180015bc2  jbe     short loc_180015BF9
0x180015bc4  mov     rax, [rbx+228h]
0x180015bcb  mov     rcx, [rax+rdi*8]
0x180015bcf  test    rcx, rcx
0x180015bd2  jz      short loc_180015BE0
0x180015bd4  mov     rax, [rcx]
0x180015bd7  mov     rax, [rax+10h]
0x180015bdb  call    _guard_dispatch_icall
0x180015be0  mov     rax, [rbx+228h]
0x180015be7  mov     qword ptr [rax+rdi*8], 0
0x180015bef  inc     edi
0x180015bf1  cmp     edi, [rbx+224h]
0x180015bf7  jb      short loc_180015BC4
0x180015bf9  mov     rcx, [rbx+228h]; void *
0x180015c00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c05  mov     qword ptr [rbx+228h], 0
0x180015c10  lea     rcx, [rbx+0C8h]; struct tagMatchingUpdate *
0x180015c17  mov     edx, 1; int
0x180015c1c  call    ?FreeObject@@YAXAEAUtagMatchingUpdate@@H@Z; FreeObject(tagMatchingUpdate &,int)
0x180015c21  mov     rcx, rbx; this
0x180015c24  call    ?CleanupProps@CDeployUpdate@@QEAAXXZ; CDeployUpdate::CleanupProps(void)
0x180015c29  mov     rcx, [rbx+250h]; void *
0x180015c30  mov     edi, 90h
0x180015c35  test    rcx, rcx
0x180015c38  jz      short loc_180015C4C
0x180015c3a  mov     edx, edi; struct std::nothrow_t *
0x180015c3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c41  mov     qword ptr [rbx+250h], 0
0x180015c4c  mov     rcx, [rbx+248h]; void *
0x180015c53  test    rcx, rcx
0x180015c56  jz      short loc_180015C6B
0x180015c58  mov     rdx, rdi; struct std::nothrow_t *
0x180015c5b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c60  mov     qword ptr [rbx+248h], 0
0x180015c6b  mov     rcx, [rbx+238h]; lpMem
0x180015c72  test    rcx, rcx
0x180015c75  jz      short loc_180015C87
0x180015c77  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180015c7c  mov     qword ptr [rbx+238h], 0
0x180015c87  mov     rcx, [rbx+1D0h]; pv
0x180015c8e  test    rcx, rcx
0x180015c91  jz      short loc_180015CA4
0x180015c93  call    cs:__imp_CoTaskMemFree
0x180015c99  mov     qword ptr [rbx+1D0h], 0
0x180015ca4  mov     rcx, [rbx+1C8h]; pv
0x180015cab  test    rcx, rcx
0x180015cae  jz      short loc_180015CC1
0x180015cb0  call    cs:__imp_CoTaskMemFree
0x180015cb6  mov     qword ptr [rbx+1C8h], 0
0x180015cc1  mov     rcx, [rbx+1C0h]; pv
0x180015cc8  test    rcx, rcx
0x180015ccb  jz      short loc_180015CDE
0x180015ccd  call    cs:__imp_CoTaskMemFree
0x180015cd3  mov     qword ptr [rbx+1C0h], 0
0x180015cde  mov     rcx, [rbx+1B8h]; pv
0x180015ce5  test    rcx, rcx
0x180015ce8  jz      short loc_180015CFB
0x180015cea  call    cs:__imp_CoTaskMemFree
0x180015cf0  mov     qword ptr [rbx+1B8h], 0
0x180015cfb  lea     rcx, [rbx+10h]; this
0x180015cff  call    ??1UpdateDeploymentStatusData@@QEAA@XZ; UpdateDeploymentStatusData::~UpdateDeploymentStatusData(void)
0x180015d04  lea     rax, ??_7?$CUnknownImpl@UIDeploymentUpdate@@@@6B@; const CUnknownImpl<IDeploymentUpdate>::`vftable'
0x180015d0b  mov     [rbx], rax
0x180015d0e  mov     rbx, [rsp+28h+arg_0]
0x180015d13  mov     rsi, [rsp+28h+arg_8]
0x180015d18  add     rsp, 20h
0x180015d1c  pop     rdi
0x180015d1d  retn
```
