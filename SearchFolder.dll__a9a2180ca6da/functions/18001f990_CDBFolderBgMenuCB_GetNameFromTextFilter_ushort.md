# CDBFolderBgMenuCB::_GetNameFromTextFilter(ushort * *)

- ea: `0x18001f990`
- end: `0x18001fa7c`
- name: `?_GetNameFromTextFilter@CDBFolderBgMenuCB@@AEAAJPEAPEAG@Z`
- size: `236`
- prototype: `__int64 __fastcall(CDBFolderBgMenuCB *this, unsigned __int16 **, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e834`

## callees

- `0x180019d30`
- `0x180019ecc`
- `0x18001f990`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_PathCleanupSpec` at `0x18001fa24`
- `SHELL32!__imp_PathCleanupSpec` at `0x18001fa24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fa47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fa47`

## pseudocode

```c
__int64 __fastcall CDBFolderBgMenuCB::_GetNameFromTextFilter(
        CDBFolderBgMenuCB *this,
        unsigned __int16 **a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
{
  struct IUnknown *v4; // rcx
  int v6; // edx
  int ServiceObject; // ebx
  int v8; // eax
  PWSTR v9; // rcx
  PWSTR pszSpec; // [rsp+50h] [rbp+20h] BYREF
  struct IItemFilter *v12; // [rsp+58h] [rbp+28h] BYREF
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF

  v4 = (struct IUnknown *)*((_QWORD *)this + 2);
  *a2 = 0;
  v12 = 0;
  ServiceObject = IUnknown_QueryServiceObject(v4, (const struct _GUID *)a2, a3, a4, (void **)&v12);
  if ( ServiceObject >= 0 )
  {
    ServiceObject = -2147467259;
    if ( (unsigned int)IItemFilter_HasFilter(v12, v6) )
    {
      v13 = 0;
      ServiceObject = (*(__int64 (__fastcall **)(struct IItemFilter *, __int64, __int64 *))(*(_QWORD *)v12 + 32LL))(
                        v12,
                        2,
                        &v13);
      if ( ServiceObject >= 0 )
      {
        pszSpec = 0;
        ServiceObject = (*(__int64 (__fastcall **)(__int64, _QWORD, PWSTR *))(*(_QWORD *)v13 + 64LL))(v13, 0, &pszSpec);
        if ( ServiceObject >= 0 )
        {
          v8 = PathCleanupSpec(0, pszSpec);
          v9 = pszSpec;
          if ( v8 >= 0 && *pszSpec )
          {
            *a2 = pszSpec;
            v9 = 0;
            pszSpec = 0;
          }
          else
          {
            ServiceObject = -2147467259;
          }
          CoTaskMemFree(v9);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    (*(void (__fastcall **)(struct IItemFilter *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)ServiceObject;
}

```

## disassembly

```asm
0x18001f990  mov     [rsp-18h+arg_18], rbx
0x18001f995  push    rbp
0x18001f996  push    rsi
0x18001f997  push    rdi
0x18001f998  mov     rbp, rsp
0x18001f99b  sub     rsp, 30h
0x18001f99f  mov     rcx, [rcx+10h]; struct IUnknown *
0x18001f9a3  lea     rax, [rbp+arg_8]
0x18001f9a7  xor     esi, esi
0x18001f9a9  mov     [rsp+30h+var_10], rax; void **
0x18001f9ae  mov     [rdx], rsi
0x18001f9b1  mov     rdi, rdx
0x18001f9b4  mov     [rbp+arg_8], rsi
0x18001f9b8  call    ?IUnknown_QueryServiceObject@@YAJPEAUIUnknown@@AEBU_GUID@@11PEAPEAX@Z; IUnknown_QueryServiceObject(IUnknown *,_GUID const &,_GUID const &,_GUID const &,void * *)
0x18001f9bd  mov     ebx, eax
0x18001f9bf  test    eax, eax
0x18001f9c1  js      loc_18001FA6D
0x18001f9c7  mov     rcx, [rbp+arg_8]; struct IItemFilter *
0x18001f9cb  mov     ebx, 80004005h
0x18001f9d0  call    ?IItemFilter_HasFilter@@YAHPEAUIItemFilter@@H@Z; IItemFilter_HasFilter(IItemFilter *,int)
0x18001f9d5  test    eax, eax
0x18001f9d7  jz      loc_18001FA5D
0x18001f9dd  mov     rcx, [rbp+arg_8]
0x18001f9e1  lea     r8, [rbp+arg_10]
0x18001f9e5  mov     [rbp+arg_10], rsi
0x18001f9e9  lea     edx, [rsi+2]
0x18001f9ec  mov     rax, [rcx]
0x18001f9ef  mov     rax, [rax+20h]
0x18001f9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9f8  mov     ebx, eax
0x18001f9fa  test    eax, eax
0x18001f9fc  js      short loc_18001FA5D
0x18001f9fe  mov     rcx, [rbp+arg_10]
0x18001fa02  lea     r8, [rbp+pszSpec]
0x18001fa06  mov     [rbp+pszSpec], rsi
0x18001fa0a  xor     edx, edx
0x18001fa0c  mov     rax, [rcx]
0x18001fa0f  mov     rax, [rax+40h]
0x18001fa13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa18  mov     ebx, eax
0x18001fa1a  test    eax, eax
0x18001fa1c  js      short loc_18001FA4D
0x18001fa1e  mov     rdx, [rbp+pszSpec]; pszSpec
0x18001fa22  xor     ecx, ecx; pszDir
0x18001fa24  call    cs:__imp_PathCleanupSpec
0x18001fa2a  mov     rcx, [rbp+pszSpec]; pv
0x18001fa2e  test    eax, eax
0x18001fa30  js      short loc_18001FA42
0x18001fa32  cmp     [rcx], si
0x18001fa35  jz      short loc_18001FA42
0x18001fa37  mov     [rdi], rcx
0x18001fa3a  mov     ecx, esi
0x18001fa3c  mov     [rbp+pszSpec], rcx
0x18001fa40  jmp     short loc_18001FA47
0x18001fa42  mov     ebx, 80004005h
0x18001fa47  call    cs:__imp_CoTaskMemFree
0x18001fa4d  mov     rcx, [rbp+arg_10]
0x18001fa51  mov     rax, [rcx]
0x18001fa54  mov     rax, [rax+10h]
0x18001fa58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa5d  mov     rcx, [rbp+arg_8]
0x18001fa61  mov     rax, [rcx]
0x18001fa64  mov     rax, [rax+10h]
0x18001fa68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa6d  mov     eax, ebx
0x18001fa6f  mov     rbx, [rsp+30h+arg_18]
0x18001fa74  add     rsp, 30h
0x18001fa78  pop     rdi
0x18001fa79  pop     rsi
0x18001fa7a  pop     rbp
0x18001fa7b  retn
```
