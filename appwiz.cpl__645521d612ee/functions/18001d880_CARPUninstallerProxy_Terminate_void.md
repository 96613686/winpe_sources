# CARPUninstallerProxy::Terminate(void)

- ea: `0x18001d880`
- end: `0x18001d96f`
- name: `?Terminate@CARPUninstallerProxy@@UEAAJXZ`
- size: `239`
- prototype: `__int64 __fastcall(CARPUninstallerProxy *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180011da0`
- `0x18001d880`
- `0x180059010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18001d91a`
- `SHCORE!SHCreateThread` at `0x18001d91a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d95d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d95d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001d8ee`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001d8ee`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18001d945`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18001d945`

## pseudocode

```c
__int64 __fastcall CARPUninstallerProxy::Terminate(CARPUninstallerProxy *this)
{
  int v3; // eax
  HRESULT v4; // esi
  LPSTREAM *v5; // rdi
  IStream **v6; // r14
  IStream *v7; // rbx
  void *pData; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 143) )
  {
    *((_DWORD *)this + 11) = -2147023673;
    return 0;
  }
  v3 = *((_DWORD *)this + 10);
  if ( v3 )
    *((_DWORD *)this + 9) = v3;
  pData = 0;
  v4 = CTLocalAllocPolicy::Alloc(this, 0x40u, 0x10u, &pData);
  if ( v4 >= 0 )
  {
    v5 = (LPSTREAM *)pData;
    *(_QWORD *)pData = this;
    v6 = v5 + 1;
    v4 = CoMarshalInterThreadInterfaceInStream(
           &GUID_dc95a094_ee0e_4974_9600_027d2321c2d4,
           *((LPUNKNOWN *)this + 2),
           v5 + 1);
    if ( v4 < 0 )
    {
LABEL_10:
      LocalFree(v5);
      return (unsigned int)v4;
    }
    (*(void (__fastcall **)(CARPUninstallerProxy *))(*(_QWORD *)this + 8LL))(this);
    if ( !SHCreateThread(_CbsFinalizeThreadProc, v5, 8u, 0) )
    {
      (*(void (__fastcall **)(CARPUninstallerProxy *))(*(_QWORD *)this + 16LL))(this);
      v7 = *v6;
      *v6 = 0;
      if ( v7 )
      {
        CoReleaseMarshalData(v7);
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      goto LABEL_10;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d880  push    rbx
0x18001d882  push    rsi
0x18001d883  push    rdi
0x18001d884  push    r14
0x18001d886  sub     rsp, 28h
0x18001d88a  cmp     dword ptr [rcx+23Ch], 0
0x18001d891  mov     rbx, rcx
0x18001d894  jz      short loc_18001D8A4
0x18001d896  mov     dword ptr [rcx+2Ch], 800704C7h
0x18001d89d  xor     eax, eax
0x18001d89f  jmp     loc_18001D965
0x18001d8a4  mov     eax, [rcx+28h]
0x18001d8a7  test    eax, eax
0x18001d8a9  jz      short loc_18001D8AE
0x18001d8ab  mov     [rcx+24h], eax
0x18001d8ae  mov     edx, 40h ; '@'; unsigned int
0x18001d8b3  mov     [rsp+48h+pData], 0
0x18001d8bc  lea     r9, [rsp+48h+pData]; void **
0x18001d8c1  lea     r8d, [rdx-30h]; unsigned __int64
0x18001d8c5  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001d8ca  mov     esi, eax
0x18001d8cc  test    eax, eax
0x18001d8ce  js      loc_18001D963
0x18001d8d4  mov     rdi, [rsp+48h+pData]
0x18001d8d9  lea     rcx, _GUID_dc95a094_ee0e_4974_9600_027d2321c2d4; riid
0x18001d8e0  mov     [rdi], rbx
0x18001d8e3  lea     r14, [rdi+8]
0x18001d8e7  mov     rdx, [rbx+10h]; pUnk
0x18001d8eb  mov     r8, r14; ppStm
0x18001d8ee  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18001d8f4  mov     esi, eax
0x18001d8f6  test    eax, eax
0x18001d8f8  js      short loc_18001D95A
0x18001d8fa  mov     rax, [rbx]
0x18001d8fd  mov     rcx, rbx
0x18001d900  mov     rax, [rax+8]
0x18001d904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d909  xor     r9d, r9d; pfnCallback
0x18001d90c  lea     rcx, ?_CbsFinalizeThreadProc@@YAKPEAX@Z; pfnThreadProc
0x18001d913  mov     rdx, rdi; pData
0x18001d916  lea     r8d, [r9+8]; flags
0x18001d91a  call    cs:__imp_SHCreateThread
0x18001d920  test    eax, eax
0x18001d922  jnz     short loc_18001D963
0x18001d924  mov     rax, [rbx]
0x18001d927  mov     rcx, rbx
0x18001d92a  mov     rax, [rax+10h]
0x18001d92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d933  mov     rbx, [r14]
0x18001d936  mov     qword ptr [r14], 0
0x18001d93d  test    rbx, rbx
0x18001d940  jz      short loc_18001D95A
0x18001d942  mov     rcx, rbx; pStm
0x18001d945  call    cs:__imp_CoReleaseMarshalData
0x18001d94b  mov     rax, [rbx]
0x18001d94e  mov     rcx, rbx
0x18001d951  mov     rax, [rax+10h]
0x18001d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d95a  mov     rcx, rdi; hMem
0x18001d95d  call    cs:__imp_LocalFree
0x18001d963  mov     eax, esi
0x18001d965  add     rsp, 28h
0x18001d969  pop     r14
0x18001d96b  pop     rdi
0x18001d96c  pop     rsi
0x18001d96d  pop     rbx
0x18001d96e  retn
```
