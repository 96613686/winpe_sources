# CommonUtil::NewRefInstance<ShieldProvider::Tracer,ulong,ulong>(ShieldProvider::Tracer * *,ulong const &,ulong const &)

- ea: `0x1400028b8`
- end: `0x140002999`
- name: `??$NewRefInstance@VTracer@ShieldProvider@@KK@CommonUtil@@YAJPEAPEAVTracer@ShieldProvider@@AEBK1@Z`
- size: `225`
- prototype: `__int64 __fastcall(ShieldProvider::Tracer **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400031e0`

## callees

- `0x140002810`
- `0x1400028b8`
- `0x140002f00`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::NewRefInstance<ShieldProvider::Tracer,unsigned long,unsigned long>(
        ShieldProvider::Tracer **a1,
        unsigned int *a2,
        unsigned int *a3)
{
  int v6; // ebx
  ShieldProvider::Tracer *v7; // r8
  ShieldProvider::Tracer *v9; // rbx
  int v10; // esi
  ShieldProvider::Tracer *v11; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v11 = 0;
  v6 = CommonUtil::CreateNewRefObject<ShieldProvider::Tracer>(&v11);
  if ( v6 < 0 )
  {
    v7 = v11;
    if ( v11 )
    {
      if ( *((_DWORD *)v11 + 2) == 1 )
      {
        *((_DWORD *)v11 + 2) = 0;
        goto LABEL_6;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) <= 1 )
      {
LABEL_6:
        if ( v7 )
          (**(void (__fastcall ***)(ShieldProvider::Tracer *, __int64))v7)(v7, 1);
      }
    }
    return (unsigned int)v6;
  }
  v9 = v11;
  v10 = ShieldProvider::Tracer::Initialize(v11, (unsigned __int16 **)*a2, (const unsigned __int16 *)*a3);
  if ( v10 < 0 )
  {
    if ( v9 )
    {
      if ( *((_DWORD *)v9 + 2) == 1 )
      {
        *((_DWORD *)v9 + 2) = 0;
LABEL_14:
        (**(void (__fastcall ***)(ShieldProvider::Tracer *, __int64))v9)(v9, 1);
        return (unsigned int)v10;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) <= 1 )
        goto LABEL_14;
    }
    return (unsigned int)v10;
  }
  *a1 = v9;
  return 0;
}

```

## disassembly

```asm
0x1400028b8  push    rbx
0x1400028ba  push    rsi
0x1400028bb  push    rdi
0x1400028bc  push    r14
0x1400028be  sub     rsp, 28h
0x1400028c2  mov     rdi, rcx
0x1400028c5  mov     qword ptr [rcx], 0
0x1400028cc  lea     rcx, [rsp+48h+arg_0]
0x1400028d1  mov     [rsp+48h+arg_0], 0
0x1400028da  mov     rsi, r8
0x1400028dd  mov     r14, rdx
0x1400028e0  call    ??$CreateNewRefObject@VTracer@ShieldProvider@@@CommonUtil@@YAJPEAPEAVTracer@ShieldProvider@@@Z; CommonUtil::CreateNewRefObject<ShieldProvider::Tracer>(ShieldProvider::Tracer * *)
0x1400028e5  mov     ebx, eax
0x1400028e7  test    eax, eax
0x1400028e9  jns     short loc_140002932
0x1400028eb  mov     r8, [rsp+48h+arg_0]
0x1400028f0  test    r8, r8
0x1400028f3  jz      short loc_14000292E
0x1400028f5  mov     ecx, [r8+8]
0x1400028f9  cmp     ecx, 1
0x1400028fc  jnz     short loc_140002908
0x1400028fe  mov     dword ptr [r8+8], 0
0x140002906  jmp     short loc_140002916
0x140002908  or      eax, 0FFFFFFFFh
0x14000290b  lock xadd [r8+8], eax
0x140002911  sub     eax, 1
0x140002914  jg      short loc_14000292E
0x140002916  test    r8, r8
0x140002919  jz      short loc_14000292E
0x14000291b  mov     rax, [r8]
0x14000291e  mov     edx, 1
0x140002923  mov     rcx, r8
0x140002926  mov     rax, [rax]
0x140002929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000292e  mov     eax, ebx
0x140002930  jmp     short loc_14000298F
0x140002932  mov     rbx, [rsp+48h+arg_0]
0x140002937  mov     r8d, [rsi]; unsigned int
0x14000293a  mov     rcx, rbx; this
0x14000293d  mov     edx, [r14]; unsigned int
0x140002940  call    ?Initialize@Tracer@ShieldProvider@@QEAAJKK@Z; ShieldProvider::Tracer::Initialize(ulong,ulong)
0x140002945  mov     esi, eax
0x140002947  test    eax, eax
0x140002949  jns     short loc_14000298A
0x14000294b  test    rbx, rbx
0x14000294e  jz      short loc_140002986
0x140002950  mov     ecx, [rbx+8]
0x140002953  cmp     ecx, 1
0x140002956  jnz     short loc_140002961
0x140002958  mov     dword ptr [rbx+8], 0
0x14000295f  jmp     short loc_14000296E
0x140002961  or      eax, 0FFFFFFFFh
0x140002964  lock xadd [rbx+8], eax
0x140002969  sub     eax, 1
0x14000296c  jg      short loc_140002986
0x14000296e  test    rbx, rbx
0x140002971  jz      short loc_140002986
0x140002973  mov     rax, [rbx]
0x140002976  mov     edx, 1
0x14000297b  mov     rcx, rbx
0x14000297e  mov     rax, [rax]
0x140002981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002986  mov     eax, esi
0x140002988  jmp     short loc_14000298F
0x14000298a  mov     [rdi], rbx
0x14000298d  xor     eax, eax
0x14000298f  add     rsp, 28h
0x140002993  pop     r14
0x140002995  pop     rdi
0x140002996  pop     rsi
0x140002997  pop     rbx
0x140002998  retn
```
