# CProfileCache::~CProfileCache(void)

- ea: `0x180006190`
- end: `0x180006215`
- name: `??1CProfileCache@@AEAA@XZ`
- size: `133`
- prototype: `void __fastcall(CProfileCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180006980`

## callees

- `0x18000599c`
- `0x180006190`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800061e9`
- `KERNEL32!CloseHandle` at `0x1800061f8`
- `KERNEL32!CloseHandle` at `0x1800061e9`
- `KERNEL32!CloseHandle` at `0x1800061f8`
- `ole32!CoTaskMemFree` at `0x1800061a7`
- `ole32!CoTaskMemFree` at `0x1800061b1`
- `ole32!CoTaskMemFree` at `0x1800061a7`
- `ole32!CoTaskMemFree` at `0x1800061b1`
- `SHELL32!__imp_ILFree` at `0x180006202`
- `SHELL32!__imp_ILFree` at `0x180006202`

## pseudocode

```c
void __fastcall CProfileCache::~CProfileCache(CProfileCache *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CProfileCache::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 4));
  CoTaskMemFree(*((LPVOID *)this + 5));
  FreeStringArray(*((unsigned __int16 ***)this + 3), *((_DWORD *)this + 4));
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
    CloseHandle(v4);
  ILFree(*((LPITEMIDLIST *)this + 12));
  _InterlockedDecrement(&g_cRefThisDll);
}

```

## disassembly

```asm
0x180006190  push    rbx
0x180006192  sub     rsp, 20h
0x180006196  mov     rbx, rcx
0x180006199  lea     rax, ??_7CProfileCache@@6B@; const CProfileCache::`vftable'
0x1800061a0  mov     [rcx], rax
0x1800061a3  mov     rcx, [rcx+20h]; pv
0x1800061a7  call    cs:__imp_CoTaskMemFree
0x1800061ad  mov     rcx, [rbx+28h]; pv
0x1800061b1  call    cs:__imp_CoTaskMemFree
0x1800061b7  mov     edx, [rbx+10h]; unsigned int
0x1800061ba  mov     rcx, [rbx+18h]; unsigned __int16 **
0x1800061be  call    ?FreeStringArray@@YAXPEAPEAGI@Z; FreeStringArray(ushort * *,uint)
0x1800061c3  mov     rcx, [rbx+8]
0x1800061c7  test    rcx, rcx
0x1800061ca  jz      short loc_1800061E0
0x1800061cc  mov     rax, [rcx]
0x1800061cf  mov     rax, [rax+10h]
0x1800061d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d8  mov     qword ptr [rbx+8], 0
0x1800061e0  mov     rcx, [rbx+40h]; hObject
0x1800061e4  test    rcx, rcx
0x1800061e7  jz      short loc_1800061EF
0x1800061e9  call    cs:__imp_CloseHandle
0x1800061ef  mov     rcx, [rbx+38h]; hObject
0x1800061f3  test    rcx, rcx
0x1800061f6  jz      short loc_1800061FE
0x1800061f8  call    cs:__imp_CloseHandle
0x1800061fe  mov     rcx, [rbx+60h]; pidl
0x180006202  call    cs:__imp_ILFree
0x180006208  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000620f  add     rsp, 20h
0x180006213  pop     rbx
0x180006214  retn
```
