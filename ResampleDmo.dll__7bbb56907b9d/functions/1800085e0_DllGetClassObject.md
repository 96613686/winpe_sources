# DllGetClassObject

- ea: `0x1800085e0`
- end: `0x1800086c5`
- name: `DllGetClassObject`
- size: `229`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800085e0`
- `0x1800086cc`
- `0x18000abfc`
- `0x180085010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  int i; // ecx
  const struct CComClassTemplate *v7; // rdi
  __int64 v8; // rax
  CClassFactory *v10; // rax
  CClassFactory *v11; // rax
  __int64 v12; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v5 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v5 )
    goto LABEL_5;
  v12 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v12 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IClassFactory.Data4;
  if ( v12 )
    return -2147467262;
LABEL_5:
  for ( i = 0; ; ++i )
  {
    if ( i >= 1 )
      return -2147221231;
    v7 = (const struct CComClassTemplate *)(&g_ComClassTemplates + 2 * i);
    v8 = **(_QWORD **)v7 - *(_QWORD *)&rclsid->Data1;
    if ( !v8 )
      v8 = *(_QWORD *)(*(_QWORD *)v7 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v8 )
      break;
  }
  v10 = (CClassFactory *)operator new(0x18u);
  v11 = CClassFactory::CClassFactory(v10, v7);
  *ppv = v11;
  if ( !v11 )
    return -2147024882;
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v11 + 8LL))(v11);
  return 0;
}

```

## disassembly

```asm
0x1800085e0  mov     [rsp+arg_0], rbx
0x1800085e5  push    rdi
0x1800085e6  sub     rsp, 20h
0x1800085ea  mov     rbx, r8
0x1800085ed  mov     r8, rcx
0x1800085f0  test    rbx, rbx
0x1800085f3  jz      short loc_180008650
0x1800085f5  mov     qword ptr [rbx], 0
0x1800085fc  mov     rax, [rdx]
0x1800085ff  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180008606  jnz     short loc_180008613
0x180008608  mov     rax, [rdx+8]
0x18000860c  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180008613  test    rax, rax
0x180008616  jnz     short loc_180008690
0x180008618  xor     ecx, ecx
0x18000861a  cmp     ecx, 1
0x18000861d  jge     loc_1800086BE
0x180008623  lea     rdx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18000862a  movsxd  rdi, ecx
0x18000862d  shl     rdi, 4
0x180008631  add     rdi, rdx
0x180008634  mov     rdx, [rdi]
0x180008637  mov     rax, [rdx]
0x18000863a  sub     rax, [r8]
0x18000863d  jnz     short loc_180008647
0x18000863f  mov     rax, [rdx+8]
0x180008643  sub     rax, [r8+8]
0x180008647  test    rax, rax
0x18000864a  jz      short loc_180008660
0x18000864c  inc     ecx
0x18000864e  jmp     short loc_18000861A
0x180008650  mov     eax, 80004003h
0x180008655  mov     rbx, [rsp+28h+arg_0]
0x18000865a  add     rsp, 20h
0x18000865e  pop     rdi
0x18000865f  retn
0x180008660  mov     ecx, 18h; Size
0x180008665  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000866a  mov     rdx, rdi; struct CComClassTemplate *
0x18000866d  mov     rcx, rax; this
0x180008670  call    ??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z; CClassFactory::CClassFactory(CComClassTemplate const *)
0x180008675  mov     [rbx], rax
0x180008678  mov     rcx, rax
0x18000867b  test    rax, rax
0x18000867e  jz      short loc_1800086B7
0x180008680  mov     rax, [rax]
0x180008683  mov     rax, [rax+8]
0x180008687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000868c  xor     eax, eax
0x18000868e  jmp     short loc_180008655
0x180008690  mov     rax, [rdx]
0x180008693  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000869a  jnz     short loc_1800086A7
0x18000869c  mov     rax, [rdx+8]
0x1800086a0  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x1800086a7  test    rax, rax
0x1800086aa  jz      loc_180008618
0x1800086b0  mov     eax, 80004002h
0x1800086b5  jmp     short loc_180008655
0x1800086b7  mov     eax, 8007000Eh
0x1800086bc  jmp     short loc_180008655
0x1800086be  mov     eax, 80040111h
0x1800086c3  jmp     short loc_180008655
```
