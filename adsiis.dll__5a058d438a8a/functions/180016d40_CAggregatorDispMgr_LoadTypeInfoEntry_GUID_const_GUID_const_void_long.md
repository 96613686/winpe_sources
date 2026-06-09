# CAggregatorDispMgr::LoadTypeInfoEntry(_GUID const &,_GUID const &,void *,long)

- ea: `0x180016d40`
- end: `0x180016e9a`
- name: `?LoadTypeInfoEntry@CAggregatorDispMgr@@QEAAJAEBU_GUID@@0PEAXJ@Z`
- size: `346`
- prototype: `__int64 __usercall@<rax>(CAggregatorDispMgr *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct _GUID *@<r8>, void *@<r9>, int)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ed0`
- `0x180002b00`
- `0x180004360`
- `0x18000816c`
- `0x1800094f8`
- `0x180009624`
- `0x18000978c`
- `0x18000dc6c`
- `0x18000e2e0`
- `0x18000f7ac`

## callees

- `0x180016b44`
- `0x180016d40`
- `0x18001e010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180016df3`
- `KERNEL32!LocalAlloc` at `0x180016df3`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180016d96`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180016d96`

## pseudocode

```c
__int64 __fastcall CAggregatorDispMgr::LoadTypeInfoEntry(
        CAggregatorDispMgr *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void *a4,
        int a5)
{
  __int128 v5; // xmm0
  GUID v7; // xmm1
  HRESULT v9; // esi
  void *v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  int v14; // ecx
  int v15; // eax
  struct _typeinfoentry *TypeInfo; // rax
  struct _typeinfoentry *v17; // rax
  GUID rguid; // [rsp+30h] [rbp-20h] BYREF
  __int128 v19; // [rsp+40h] [rbp-10h] BYREF
  void *v20; // [rsp+78h] [rbp+28h] BYREF
  ITypeLib *pptlib; // [rsp+80h] [rbp+30h] BYREF

  v5 = (__int128)*a3;
  v7 = *a2;
  pptlib = 0;
  v20 = 0;
  v19 = v5;
  rguid = v7;
  v9 = LoadRegTypeLib(&rguid, 1u, 0, 0x800u, &pptlib);
  if ( v9 < 0 )
    goto LABEL_7;
  v9 = ((__int64 (__fastcall *)(ITypeLib *, __int128 *, void **))pptlib->lpVtbl->GetTypeInfoOfGuid)(pptlib, &v19, &v20);
  ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  if ( v9 < 0 )
    goto LABEL_7;
  v10 = v20;
  if ( CAggregatorDispMgr::FindTypeInfo(this, v20) )
  {
    v9 = -2147467259;
LABEL_8:
    if ( v10 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v9;
  }
  v11 = LocalAlloc(0x40u, 0x20u);
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
LABEL_7:
    v10 = v20;
    goto LABEL_8;
  }
  v11[1] = v10;
  v14 = *((_DWORD *)this + 2);
  *((_DWORD *)this + 2) = v14 + 1;
  *(_DWORD *)v11 = v14;
  v11[2] = a4;
  v11[3] = *((_QWORD *)this + 2);
  v15 = a5;
  *((_QWORD *)this + 2) = v12;
  if ( v15 == -4 )
  {
    if ( v20 )
    {
      TypeInfo = CAggregatorDispMgr::FindTypeInfo(this, v20);
      if ( TypeInfo )
        *((_QWORD *)this + 3) = TypeInfo;
    }
  }
  else if ( !v15 )
  {
    if ( v20 )
    {
      v17 = CAggregatorDispMgr::FindTypeInfo(this, v20);
      if ( v17 )
        *((_QWORD *)this + 4) = v17;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016d40  mov     [rsp-18h+arg_0], rbx
0x180016d45  mov     [rsp-18h+arg_18], rsi
0x180016d4a  push    rbp
0x180016d4b  push    rdi
0x180016d4c  push    r14
0x180016d4e  mov     rbp, rsp
0x180016d51  sub     rsp, 50h
0x180016d55  movups  xmm0, xmmword ptr [r8]
0x180016d59  xor     r8d, r8d; wVerMinor
0x180016d5c  mov     r14, r9
0x180016d5f  movups  xmm1, xmmword ptr [rdx]
0x180016d62  mov     rbx, rcx
0x180016d65  mov     [rbp+arg_10], 0
0x180016d6d  lea     rax, [rbp+arg_10]
0x180016d71  mov     [rbp+arg_8], 0
0x180016d79  lea     edx, [r8+1]; wVerMajor
0x180016d7d  mov     [rsp+50h+pptlib], rax; pptlib
0x180016d82  mov     r9d, 800h; lcid
0x180016d88  lea     rcx, [rbp+rguid]; rguid
0x180016d8c  movdqu  [rbp+var_10], xmm0
0x180016d91  movdqu  xmmword ptr [rbp+rguid.Data1], xmm1
0x180016d96  call    cs:__imp_LoadRegTypeLib
0x180016d9c  mov     esi, eax
0x180016d9e  test    eax, eax
0x180016da0  js      short loc_180016E06
0x180016da2  mov     rcx, [rbp+arg_10]
0x180016da6  lea     r8, [rbp+arg_8]
0x180016daa  lea     rdx, [rbp+var_10]
0x180016dae  mov     rax, [rcx]
0x180016db1  mov     rax, [rax+30h]
0x180016db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dba  mov     rcx, [rbp+arg_10]
0x180016dbe  mov     esi, eax
0x180016dc0  mov     rax, [rcx]
0x180016dc3  mov     rax, [rax+10h]
0x180016dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dcc  test    esi, esi
0x180016dce  js      short loc_180016E06
0x180016dd0  mov     rdi, [rbp+arg_8]
0x180016dd4  mov     rcx, rbx; this
0x180016dd7  mov     rdx, rdi; void *
0x180016dda  call    ?FindTypeInfo@CAggregatorDispMgr@@AEAAPEAU_typeinfoentry@@PEAX@Z; CAggregatorDispMgr::FindTypeInfo(void *)
0x180016ddf  test    rax, rax
0x180016de2  jz      short loc_180016DEB
0x180016de4  mov     esi, 80004005h
0x180016de9  jmp     short loc_180016E0A
0x180016deb  mov     edx, 20h ; ' '; uBytes
0x180016df0  lea     ecx, [rdx+20h]; uFlags
0x180016df3  call    cs:__imp_LocalAlloc
0x180016df9  mov     rdx, rax
0x180016dfc  test    rax, rax
0x180016dff  jnz     short loc_180016E35
0x180016e01  mov     esi, 8007000Eh
0x180016e06  mov     rdi, [rbp+arg_8]
0x180016e0a  test    rdi, rdi
0x180016e0d  jz      short loc_180016E1E
0x180016e0f  mov     rdx, [rdi]
0x180016e12  mov     rcx, rdi
0x180016e15  mov     rax, [rdx+10h]
0x180016e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e1e  mov     eax, esi
0x180016e20  lea     r11, [rsp+50h+var_s0]
0x180016e25  mov     rbx, [r11+20h]
0x180016e29  mov     rsi, [r11+38h]
0x180016e2d  mov     rsp, r11
0x180016e30  pop     r14
0x180016e32  pop     rdi
0x180016e33  pop     rbp
0x180016e34  retn
0x180016e35  mov     [rax+8], rdi
0x180016e39  mov     ecx, [rbx+8]
0x180016e3c  lea     eax, [rcx+1]
0x180016e3f  mov     [rbx+8], eax
0x180016e42  mov     [rdx], ecx
0x180016e44  mov     [rdx+10h], r14
0x180016e48  mov     rax, [rbx+10h]
0x180016e4c  mov     [rdx+18h], rax
0x180016e50  mov     eax, [rbp+arg_20]
0x180016e53  mov     [rbx+10h], rdx
0x180016e57  cmp     eax, 0FFFFFFFCh
0x180016e5a  jnz     short loc_180016E78
0x180016e5c  mov     rdx, [rbp+arg_8]; void *
0x180016e60  test    rdx, rdx
0x180016e63  jz      short loc_180016E96
0x180016e65  mov     rcx, rbx; this
0x180016e68  call    ?FindTypeInfo@CAggregatorDispMgr@@AEAAPEAU_typeinfoentry@@PEAX@Z; CAggregatorDispMgr::FindTypeInfo(void *)
0x180016e6d  test    rax, rax
0x180016e70  jz      short loc_180016E96
0x180016e72  mov     [rbx+18h], rax
0x180016e76  jmp     short loc_180016E96
0x180016e78  test    eax, eax
0x180016e7a  jnz     short loc_180016E96
0x180016e7c  mov     rdx, [rbp+arg_8]; void *
0x180016e80  test    rdx, rdx
0x180016e83  jz      short loc_180016E96
0x180016e85  mov     rcx, rbx; this
0x180016e88  call    ?FindTypeInfo@CAggregatorDispMgr@@AEAAPEAU_typeinfoentry@@PEAX@Z; CAggregatorDispMgr::FindTypeInfo(void *)
0x180016e8d  test    rax, rax
0x180016e90  jz      short loc_180016E96
0x180016e92  mov     [rbx+20h], rax
0x180016e96  xor     eax, eax
0x180016e98  jmp     short loc_180016E20
```
