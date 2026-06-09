# SHWriteImplementingClassesOfCategory(_GUID const &)

- ea: `0x18002a31c`
- end: `0x18002a403`
- name: `?SHWriteImplementingClassesOfCategory@@YAJAEBU_GUID@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027ed0`
- `0x18002a090`

## callees

- `0x18002a31c`
- `0x18002a564`
- `0x18002a824`
- `0x18002d010`

## import_xrefs

- `iertutil!__imp_DSA_Destroy` at `0x18002a3ce`
- `iertutil!__imp_DSA_Destroy` at `0x18002a3ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a34f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a34f`

## pseudocode

```c
__int64 __fastcall SHWriteImplementingClassesOfCategory(const struct _GUID *a1)
{
  int v2; // ebx
  HDSA hdsa; // [rsp+58h] [rbp+10h] BYREF
  struct IEnumGUID *v5; // [rsp+60h] [rbp+18h]
  LPVOID v6; // [rsp+68h] [rbp+20h] BYREF

  v6 = 0;
  v2 = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatInformation, &v6);
  if ( v2 >= 0 )
  {
    v5 = 0;
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, const struct _GUID *))(*(_QWORD *)v6 + 40LL))(v6, 1, a1);
    if ( v2 >= 0 )
    {
      hdsa = 0;
      v2 = _EnumerateGuids(v5, &hdsa);
      if ( v2 >= 0 )
      {
        v2 = _WriteImplementingClassesOfCategory(a1, hdsa);
        DSA_Destroy(hdsa);
      }
      ((void (__fastcall *)(struct IEnumGUID *))v5->lpVtbl->Release)(v5);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002a31c  mov     r11, rsp
0x18002a31f  mov     [r11+8], rbx
0x18002a323  push    rdi
0x18002a324  sub     rsp, 40h
0x18002a328  xor     edx, edx; pUnkOuter
0x18002a32a  mov     qword ptr [r11+20h], 0
0x18002a332  mov     rdi, rcx
0x18002a335  lea     rax, [r11+20h]
0x18002a339  lea     r9, IID_ICatInformation; riid
0x18002a340  mov     [r11-28h], rax
0x18002a344  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18002a34b  lea     r8d, [rdx+1]; dwClsContext
0x18002a34f  call    cs:__imp_CoCreateInstance
0x18002a355  mov     ebx, eax
0x18002a357  test    eax, eax
0x18002a359  js      loc_18002A3F6
0x18002a35f  mov     rcx, [rsp+48h+arg_18]
0x18002a364  lea     r8, [rsp+48h+arg_10]
0x18002a369  mov     [rsp+48h+var_20], r8
0x18002a36e  xor     r9d, r9d
0x18002a371  mov     [rsp+48h+arg_10], 0
0x18002a37a  mov     r8, rdi
0x18002a37d  mov     [rsp+48h+var_28], 0
0x18002a386  mov     rax, [rcx]
0x18002a389  lea     edx, [r9+1]
0x18002a38d  mov     rax, [rax+28h]
0x18002a391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a396  mov     ebx, eax
0x18002a398  test    eax, eax
0x18002a39a  js      short loc_18002A3E5
0x18002a39c  mov     rcx, [rsp+48h+arg_10]; struct IEnumGUID *
0x18002a3a1  lea     rdx, [rsp+48h+hdsa]; struct _DSA **
0x18002a3a6  mov     [rsp+48h+hdsa], 0
0x18002a3af  call    ?_EnumerateGuids@@YAJPEAUIEnumGUID@@PEAPEAU_DSA@@@Z; _EnumerateGuids(IEnumGUID *,_DSA * *)
0x18002a3b4  mov     ebx, eax
0x18002a3b6  test    eax, eax
0x18002a3b8  js      short loc_18002A3D4
0x18002a3ba  mov     rdx, [rsp+48h+hdsa]; struct _DSA *
0x18002a3bf  mov     rcx, rdi; struct _GUID *
0x18002a3c2  call    ?_WriteImplementingClassesOfCategory@@YAJAEBU_GUID@@PEAU_DSA@@@Z; _WriteImplementingClassesOfCategory(_GUID const &,_DSA *)
0x18002a3c7  mov     rcx, [rsp+48h+hdsa]; hdsa
0x18002a3cc  mov     ebx, eax
0x18002a3ce  call    cs:__imp_DSA_Destroy
0x18002a3d4  mov     rcx, [rsp+48h+arg_10]
0x18002a3d9  mov     rax, [rcx]
0x18002a3dc  mov     rax, [rax+10h]
0x18002a3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3e5  mov     rcx, [rsp+48h+arg_18]
0x18002a3ea  mov     rax, [rcx]
0x18002a3ed  mov     rax, [rax+10h]
0x18002a3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3f6  mov     eax, ebx
0x18002a3f8  mov     rbx, [rsp+48h+arg_0]
0x18002a3fd  add     rsp, 40h
0x18002a401  pop     rdi
0x18002a402  retn
```
