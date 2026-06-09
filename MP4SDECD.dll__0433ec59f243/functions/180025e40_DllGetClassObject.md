# DllGetClassObject

- ea: `0x180025e40`
- end: `0x180025f2f`
- name: `DllGetClassObject`
- size: `239`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180025e40`
- `0x180025f38`
- `0x18002a670`
- `0x180046010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v6; // rax
  __int64 v7; // rax
  int i; // ecx
  const struct CComClassTemplate *v9; // rdi
  __int64 v10; // rax
  CClassFactory *v11; // rax
  CClassFactory *v12; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v6 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v6 )
    goto LABEL_10;
  v7 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v7 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IClassFactory.Data4;
  if ( v7 )
    return -2147467262;
LABEL_10:
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
      return -2147221231;
    v9 = (const struct CComClassTemplate *)(&g_ComClassTemplates + 2 * i);
    v10 = **(_QWORD **)v9 - *(_QWORD *)&rclsid->Data1;
    if ( !v10 )
      v10 = *(_QWORD *)(*(_QWORD *)v9 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v10 )
      break;
  }
  v11 = (CClassFactory *)operator new(0x18u);
  if ( v11 )
  {
    v12 = CClassFactory::CClassFactory(v11, v9);
    *ppv = v12;
    if ( v12 )
    {
      (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v12 + 8LL))(v12);
      return 0;
    }
  }
  else
  {
    *ppv = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x180025e40  mov     [rsp+arg_0], rbx
0x180025e45  push    rdi
0x180025e46  sub     rsp, 20h
0x180025e4a  mov     rbx, r8
0x180025e4d  mov     r8, rcx
0x180025e50  test    rbx, rbx
0x180025e53  jnz     short loc_180025E5F
0x180025e55  mov     eax, 80004003h
0x180025e5a  jmp     loc_180025F24
0x180025e5f  mov     qword ptr [rbx], 0
0x180025e66  mov     rax, [rdx]
0x180025e69  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180025e70  jnz     short loc_180025E7D
0x180025e72  mov     rax, [rdx+8]
0x180025e76  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180025e7d  test    rax, rax
0x180025e80  jz      short loc_180025EA5
0x180025e82  mov     rax, [rdx]
0x180025e85  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x180025e8c  jnz     short loc_180025E99
0x180025e8e  mov     rax, [rdx+8]
0x180025e92  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x180025e99  test    rax, rax
0x180025e9c  jz      short loc_180025EA5
0x180025e9e  mov     eax, 80004002h
0x180025ea3  jmp     short loc_180025F24
0x180025ea5  xor     ecx, ecx
0x180025ea7  cmp     ecx, 2
0x180025eaa  jge     short loc_180025F1F
0x180025eac  lea     rdx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x180025eb3  movsxd  rdi, ecx
0x180025eb6  shl     rdi, 4
0x180025eba  add     rdi, rdx
0x180025ebd  mov     rdx, [rdi]
0x180025ec0  mov     rax, [rdx]
0x180025ec3  sub     rax, [r8]
0x180025ec6  jnz     short loc_180025ED0
0x180025ec8  mov     rax, [rdx+8]
0x180025ecc  sub     rax, [r8+8]
0x180025ed0  test    rax, rax
0x180025ed3  jz      short loc_180025ED9
0x180025ed5  inc     ecx
0x180025ed7  jmp     short loc_180025EA7
0x180025ed9  mov     ecx, 18h; Size
0x180025ede  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025ee3  test    rax, rax
0x180025ee6  jz      short loc_180025F11
0x180025ee8  mov     rdx, rdi; struct CComClassTemplate *
0x180025eeb  mov     rcx, rax; this
0x180025eee  call    ??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z; CClassFactory::CClassFactory(CComClassTemplate const *)
0x180025ef3  mov     [rbx], rax
0x180025ef6  mov     rdx, rax
0x180025ef9  test    rax, rax
0x180025efc  jz      short loc_180025F18
0x180025efe  mov     rcx, [rax]
0x180025f01  mov     rax, [rcx+8]
0x180025f05  mov     rcx, rdx
0x180025f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f0d  xor     eax, eax
0x180025f0f  jmp     short loc_180025F24
0x180025f11  mov     qword ptr [rbx], 0
0x180025f18  mov     eax, 8007000Eh
0x180025f1d  jmp     short loc_180025F24
0x180025f1f  mov     eax, 80040111h
0x180025f24  mov     rbx, [rsp+28h+arg_0]
0x180025f29  add     rsp, 20h
0x180025f2d  pop     rdi
0x180025f2e  retn
```
