# DllGetClassObject

- ea: `0x180008fb0`
- end: `0x1800090a4`
- name: `DllGetClassObject`
- size: `244`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000145c`
- `0x180008fb0`
- `0x180020ff9`
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
0x180008fb0  push    rbx
0x180008fb2  push    rbp
0x180008fb3  push    rsi
0x180008fb4  push    rdi
0x180008fb5  push    r15
0x180008fb7  sub     rsp, 20h
0x180008fbb  mov     rdi, r8
0x180008fbe  mov     rbx, rdx
0x180008fc1  mov     rbp, rcx
0x180008fc4  test    r8, r8
0x180008fc7  jnz     short loc_180008FD3
0x180008fc9  mov     eax, 80004003h
0x180008fce  jmp     loc_180009099
0x180008fd3  mov     qword ptr [r8], 0
0x180008fda  lea     rdx, IID_IUnknown; Buf2
0x180008fe1  mov     r15d, 10h
0x180008fe7  mov     rcx, rbx; Buf1
0x180008fea  mov     r8d, r15d; Size
0x180008fed  call    memcmp_0
0x180008ff2  test    eax, eax
0x180008ff4  jz      short loc_180009016
0x180008ff6  mov     r8d, r15d; Size
0x180008ff9  lea     rdx, IID_IClassFactory; Buf2
0x180009000  mov     rcx, rbx; Buf1
0x180009003  call    memcmp_0
0x180009008  test    eax, eax
0x18000900a  jz      short loc_180009016
0x18000900c  mov     eax, 80004002h
0x180009011  jmp     loc_180009099
0x180009016  xor     ebx, ebx
0x180009018  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18000901f  movsxd  rsi, ebx
0x180009022  shl     rsi, 4
0x180009026  mov     r8, r15; Size
0x180009029  add     rsi, rcx
0x18000902c  mov     rdx, rbp; Buf2
0x18000902f  mov     rcx, [rsi]; Buf1
0x180009032  call    memcmp_0
0x180009037  test    eax, eax
0x180009039  jz      short loc_180009049
0x18000903b  inc     ebx
0x18000903d  cmp     ebx, 1
0x180009040  jl      short loc_180009018
0x180009042  mov     eax, 80040111h
0x180009047  jmp     short loc_180009099
0x180009049  mov     ecx, 18h; Size
0x18000904e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009053  mov     rdx, rax
0x180009056  test    rax, rax
0x180009059  jz      short loc_18000908D
0x18000905b  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180009062  mov     [rdx+8], rsi
0x180009066  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x18000906d  mov     [rdx], rax
0x180009070  mov     dword ptr [rdx+10h], 0
0x180009077  mov     [rdi], rdx
0x18000907a  mov     rcx, [rdx]
0x18000907d  mov     rax, [rcx+8]
0x180009081  mov     rcx, rdx
0x180009084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009089  xor     eax, eax
0x18000908b  jmp     short loc_180009099
0x18000908d  mov     qword ptr [rdi], 0
0x180009094  mov     eax, 8007000Eh
0x180009099  add     rsp, 20h
0x18000909d  pop     r15
0x18000909f  pop     rdi
0x1800090a0  pop     rsi
0x1800090a1  pop     rbp
0x1800090a2  pop     rbx
0x1800090a3  retn
```
