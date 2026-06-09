# DllGetClassObject

- ea: `0x180025500`
- end: `0x1800255e9`
- name: `DllGetClassObject`
- size: `233`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001360`
- `0x180025500`
- `0x1800886f0`
- `0x180088750`

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
    if ( ++v7 >= 1 )
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
0x180025500  push    rbx
0x180025502  push    rbp
0x180025503  push    rsi
0x180025504  push    rdi
0x180025505  push    r15
0x180025507  sub     rsp, 20h
0x18002550b  mov     rbx, rdx
0x18002550e  mov     qword ptr [r8], 0
0x180025515  mov     rdi, r8
0x180025518  lea     rdx, IID_IUnknown; Buf2
0x18002551f  mov     rbp, rcx
0x180025522  mov     r15d, 10h
0x180025528  mov     r8d, r15d; Size
0x18002552b  mov     rcx, rbx; Buf1
0x18002552e  call    memcmp_0
0x180025533  test    eax, eax
0x180025535  jz      short loc_180025557
0x180025537  mov     r8d, r15d; Size
0x18002553a  lea     rdx, IID_IClassFactory; Buf2
0x180025541  mov     rcx, rbx; Buf1
0x180025544  call    memcmp_0
0x180025549  test    eax, eax
0x18002554b  jz      short loc_180025557
0x18002554d  mov     eax, 80004002h
0x180025552  jmp     loc_1800255DD
0x180025557  xor     ebx, ebx
0x180025559  movsxd  rax, ebx
0x18002555c  mov     r8, r15; Size
0x18002555f  mov     rdx, rbp; Buf2
0x180025562  lea     rcx, [rax+rax*4]
0x180025566  lea     rax, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x18002556d  lea     rsi, [rax+rcx*8]
0x180025571  mov     rcx, [rsi+8]; Buf1
0x180025575  call    memcmp_0
0x18002557a  test    eax, eax
0x18002557c  jz      short loc_18002558C
0x18002557e  inc     ebx
0x180025580  cmp     ebx, 1
0x180025583  jl      short loc_180025559
0x180025585  mov     eax, 80040111h
0x18002558a  jmp     short loc_1800255DD
0x18002558c  mov     ecx, 18h; Size
0x180025591  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025596  mov     rdx, rax
0x180025599  test    rax, rax
0x18002559c  jz      short loc_1800255D1
0x18002559e  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800255a5  mov     [rdx+8], rsi
0x1800255a9  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800255b0  mov     [rdx], rax
0x1800255b3  mov     dword ptr [rdx+10h], 0
0x1800255ba  mov     [rdi], rdx
0x1800255bd  mov     rcx, [rdx]
0x1800255c0  mov     rax, [rcx+8]
0x1800255c4  mov     rcx, rdx
0x1800255c7  call    cs:__guard_dispatch_icall_fptr
0x1800255cd  xor     eax, eax
0x1800255cf  jmp     short loc_1800255DD
0x1800255d1  mov     qword ptr [rdi], 0
0x1800255d8  mov     eax, 8007000Eh
0x1800255dd  add     rsp, 20h
0x1800255e1  pop     r15
0x1800255e3  pop     rdi
0x1800255e4  pop     rsi
0x1800255e5  pop     rbp
0x1800255e6  pop     rbx
0x1800255e7  retn
```
