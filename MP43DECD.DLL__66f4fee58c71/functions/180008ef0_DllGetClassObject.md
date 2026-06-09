# DllGetClassObject

- ea: `0x180008ef0`
- end: `0x180008fe4`
- name: `DllGetClassObject`
- size: `244`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000142c`
- `0x180008ef0`
- `0x180020f39`
- `0x180022010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v7; // ebx
  const void **v8; // rsi
  _QWORD *v9; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  if ( memcmp_0(riid, &IID_IUnknown, 0x10u) && memcmp_0(riid, &IID_IClassFactory, 0x10u) )
    return -2147467262;
  v7 = 0;
  while ( 1 )
  {
    v8 = (const void **)(&g_ComClassTemplates + 2 * v7);
    if ( !memcmp_0(*v8, rclsid, 0x10u) )
      break;
    if ( ++v7 >= 1 )
      return -2147221231;
  }
  v9 = operator new(0x18u);
  if ( v9 )
  {
    _InterlockedIncrement(&g_cActiveObjects);
    v9[1] = v8;
    *v9 = &CClassFactory::`vftable';
    *((_DWORD *)v9 + 4) = 0;
    *ppv = v9;
    (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
    return 0;
  }
  else
  {
    *ppv = 0;
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180008ef0  push    rbx
0x180008ef2  push    rbp
0x180008ef3  push    rsi
0x180008ef4  push    rdi
0x180008ef5  push    r15
0x180008ef7  sub     rsp, 20h
0x180008efb  mov     rdi, r8
0x180008efe  mov     rbx, rdx
0x180008f01  mov     rbp, rcx
0x180008f04  test    r8, r8
0x180008f07  jnz     short loc_180008F13
0x180008f09  mov     eax, 80004003h
0x180008f0e  jmp     loc_180008FD9
0x180008f13  mov     qword ptr [r8], 0
0x180008f1a  lea     rdx, IID_IUnknown; Buf2
0x180008f21  mov     r15d, 10h
0x180008f27  mov     rcx, rbx; Buf1
0x180008f2a  mov     r8d, r15d; Size
0x180008f2d  call    memcmp_0
0x180008f32  test    eax, eax
0x180008f34  jz      short loc_180008F56
0x180008f36  mov     r8d, r15d; Size
0x180008f39  lea     rdx, IID_IClassFactory; Buf2
0x180008f40  mov     rcx, rbx; Buf1
0x180008f43  call    memcmp_0
0x180008f48  test    eax, eax
0x180008f4a  jz      short loc_180008F56
0x180008f4c  mov     eax, 80004002h
0x180008f51  jmp     loc_180008FD9
0x180008f56  xor     ebx, ebx
0x180008f58  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x180008f5f  movsxd  rsi, ebx
0x180008f62  shl     rsi, 4
0x180008f66  mov     r8, r15; Size
0x180008f69  add     rsi, rcx
0x180008f6c  mov     rdx, rbp; Buf2
0x180008f6f  mov     rcx, [rsi]; Buf1
0x180008f72  call    memcmp_0
0x180008f77  test    eax, eax
0x180008f79  jz      short loc_180008F89
0x180008f7b  inc     ebx
0x180008f7d  cmp     ebx, 1
0x180008f80  jl      short loc_180008F58
0x180008f82  mov     eax, 80040111h
0x180008f87  jmp     short loc_180008FD9
0x180008f89  mov     ecx, 18h; Size
0x180008f8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008f93  mov     rdx, rax
0x180008f96  test    rax, rax
0x180008f99  jz      short loc_180008FCD
0x180008f9b  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180008fa2  mov     [rdx+8], rsi
0x180008fa6  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180008fad  mov     [rdx], rax
0x180008fb0  mov     dword ptr [rdx+10h], 0
0x180008fb7  mov     [rdi], rdx
0x180008fba  mov     rcx, [rdx]
0x180008fbd  mov     rax, [rcx+8]
0x180008fc1  mov     rcx, rdx
0x180008fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc9  xor     eax, eax
0x180008fcb  jmp     short loc_180008FD9
0x180008fcd  mov     qword ptr [rdi], 0
0x180008fd4  mov     eax, 8007000Eh
0x180008fd9  add     rsp, 20h
0x180008fdd  pop     r15
0x180008fdf  pop     rdi
0x180008fe0  pop     rsi
0x180008fe1  pop     rbp
0x180008fe2  pop     rbx
0x180008fe3  retn
```
