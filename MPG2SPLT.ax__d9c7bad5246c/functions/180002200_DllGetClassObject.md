# DllGetClassObject

- ea: `0x180002200`
- end: `0x1800022e7`
- name: `DllGetClassObject`
- size: `231`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180002200`
- `0x180033df1`
- `0x180034010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v7; // ebx
  struct CFactoryTemplate near **v8; // rsi
  _QWORD *v9; // rax

  *ppv = 0;
  if ( memcmp_0(riid, &IID_IUnknown, 0x10u) && memcmp_0(riid, &IID_IClassFactory, 0x10u) )
    return -2147467262;
  v7 = 0;
  while ( 1 )
  {
    v8 = &g_Templates + 5 * v7;
    if ( !memcmp_0(v8[1], rclsid, 0x10u) )
      break;
    if ( ++v7 >= 5 )
      return -2147221231;
  }
  v9 = operator new(0x18u);
  if ( v9 )
  {
    _InterlockedIncrement(&CBaseObject::m_cObjects);
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
0x180002200  push    rbx
0x180002202  push    rbp
0x180002203  push    rsi
0x180002204  push    rdi
0x180002205  push    r15
0x180002207  sub     rsp, 20h
0x18000220b  mov     rbx, rdx
0x18000220e  mov     qword ptr [r8], 0
0x180002215  mov     rdi, r8
0x180002218  lea     rdx, IID_IUnknown; Buf2
0x18000221f  mov     rbp, rcx
0x180002222  mov     r15d, 10h
0x180002228  mov     r8d, r15d; Size
0x18000222b  mov     rcx, rbx; Buf1
0x18000222e  call    memcmp_0
0x180002233  test    eax, eax
0x180002235  jz      short loc_180002257
0x180002237  mov     r8d, r15d; Size
0x18000223a  lea     rdx, IID_IClassFactory; Buf2
0x180002241  mov     rcx, rbx; Buf1
0x180002244  call    memcmp_0
0x180002249  test    eax, eax
0x18000224b  jz      short loc_180002257
0x18000224d  mov     eax, 80004002h
0x180002252  jmp     loc_1800022DC
0x180002257  xor     ebx, ebx
0x180002259  movsxd  rax, ebx
0x18000225c  mov     r8, r15; Size
0x18000225f  mov     rdx, rbp; Buf2
0x180002262  lea     rcx, [rax+rax*4]
0x180002266  lea     rax, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x18000226d  lea     rsi, [rax+rcx*8]
0x180002271  mov     rcx, [rsi+8]; Buf1
0x180002275  call    memcmp_0
0x18000227a  test    eax, eax
0x18000227c  jz      short loc_18000228C
0x18000227e  inc     ebx
0x180002280  cmp     ebx, 5
0x180002283  jl      short loc_180002259
0x180002285  mov     eax, 80040111h
0x18000228a  jmp     short loc_1800022DC
0x18000228c  mov     ecx, 18h; Size
0x180002291  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002296  mov     rdx, rax
0x180002299  test    rax, rax
0x18000229c  jz      short loc_1800022D0
0x18000229e  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800022a5  mov     [rdx+8], rsi
0x1800022a9  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800022b0  mov     [rdx], rax
0x1800022b3  mov     dword ptr [rdx+10h], 0
0x1800022ba  mov     [rdi], rdx
0x1800022bd  mov     rcx, [rdx]
0x1800022c0  mov     rax, [rcx+8]
0x1800022c4  mov     rcx, rdx
0x1800022c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022cc  xor     eax, eax
0x1800022ce  jmp     short loc_1800022DC
0x1800022d0  mov     qword ptr [rdi], 0
0x1800022d7  mov     eax, 8007000Eh
0x1800022dc  add     rsp, 20h
0x1800022e0  pop     r15
0x1800022e2  pop     rdi
0x1800022e3  pop     rsi
0x1800022e4  pop     rbp
0x1800022e5  pop     rbx
0x1800022e6  retn
```
