# CProfileCache::_UpdateMapping(void)

- ea: `0x180006ef4`
- end: `0x180007078`
- name: `?_UpdateMapping@CProfileCache@@AEAAJXZ`
- size: `388`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006240`
- `0x180006760`
- `0x1800067b0`
- `0x180006890`

## callees

- `0x180003ca0`
- `0x1800069c0`
- `0x180006bd4`
- `0x180006c28`
- `0x180006ef4`
- `0x18000a7a7`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180006f62`
- `ole32!CoTaskMemAlloc` at `0x180006f8e`
- `ole32!CoTaskMemAlloc` at `0x180006fba`
- `ole32!CoTaskMemAlloc` at `0x180006f62`
- `ole32!CoTaskMemAlloc` at `0x180006f8e`
- `ole32!CoTaskMemAlloc` at `0x180006fba`

## pseudocode

```c
__int64 __fastcall CProfileCache::_UpdateMapping(CProfileCache *this)
{
  signed __int32 *v1; // rdi
  int v3; // esi
  __int64 v4; // rcx
  void *v5; // rax
  void *v6; // rax
  void *v7; // rax
  __int64 v8; // rcx
  int v9; // edx
  bool v10; // zf
  signed __int32 v11; // edx
  struct IEnumNetworkPrivate *v13; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+38h] [rbp+10h] BYREF

  v1 = (signed __int32 *)((char *)this + 48);
  CReaderWriterLock3::WriteLock((CProfileCache *)((char *)this + 48));
  CProfileCache::_ClearMapping(this);
  if ( !*((_QWORD *)this + 1) )
  {
    v3 = -2147467259;
    goto LABEL_12;
  }
  LODWORD(v13) = 0;
  v14 = 0;
  v3 = CProfileCache::_CountConnectedInterfaces(this, (unsigned int *)&v13, &v14);
  if ( v3 < 0 )
    goto LABEL_11;
  v4 = (unsigned int)v13;
  *((_DWORD *)this + 4) = (_DWORD)v13;
  v5 = CoTaskMemAlloc(16 * v4);
  *((_QWORD *)this + 4) = v5;
  if ( !v5
    || (memset_0(v5, 0, 16LL * *((unsigned int *)this + 4)),
        v6 = CoTaskMemAlloc(16LL * *((unsigned int *)this + 4)),
        (*((_QWORD *)this + 5) = v6) == 0)
    || (memset_0(v6, 0, 16LL * *((unsigned int *)this + 4)),
        v7 = CoTaskMemAlloc(8LL * *((unsigned int *)this + 4)),
        (*((_QWORD *)this + 3) = v7) == 0) )
  {
    v3 = -2147024882;
LABEL_11:
    CProfileCache::_ClearMapping(this);
    goto LABEL_12;
  }
  memset_0(v7, 0, 8LL * *((unsigned int *)this + 4));
  v8 = *((_QWORD *)this + 1);
  v13 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, struct IEnumNetworkPrivate **))(*(_QWORD *)v8 + 32LL))(v8, 1, &v13);
  if ( v3 < 0 )
    goto LABEL_11;
  v3 = CProfileCache::_AddMappings(this, v13);
  (*(void (__fastcall **)(struct IEnumNetworkPrivate *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v3 < 0 )
    goto LABEL_11;
LABEL_12:
  v9 = v1[1] - 1;
  v10 = (((*((_BYTE *)v1 + 4) - 1) & 3) != 0 ? v9 : 0) == 0;
  _InterlockedExchange(v1 + 1, ((*((_BYTE *)v1 + 4) - 1) & 3) != 0 ? v9 : 0);
  if ( v10 )
  {
    _m_prefetchw(v1);
    do
      v11 = *v1;
    while ( v11 != _InterlockedCompareExchange(v1, (v11 - 0x10000) & 0xFFFF0000, v11) );
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006ef4  mov     [rsp+arg_10], rbx
0x180006ef9  mov     [rsp+arg_18], rsi
0x180006efe  push    rdi
0x180006eff  sub     rsp, 20h
0x180006f03  lea     rdi, [rcx+30h]
0x180006f07  mov     rbx, rcx
0x180006f0a  mov     rcx, rdi; this
0x180006f0d  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180006f12  mov     rcx, rbx; this
0x180006f15  call    ?_ClearMapping@CProfileCache@@AEAAXXZ; CProfileCache::_ClearMapping(void)
0x180006f1a  cmp     qword ptr [rbx+8], 0
0x180006f1f  jnz     short loc_180006F2B
0x180006f21  mov     esi, 80004005h
0x180006f26  jmp     loc_180007037
0x180006f2b  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x180006f30  mov     dword ptr [rsp+28h+arg_0], 0
0x180006f38  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x180006f3d  mov     [rsp+28h+arg_8], 0
0x180006f45  mov     rcx, rbx; this
0x180006f48  call    ?_CountConnectedInterfaces@CProfileCache@@AEAAJPEAI0@Z; CProfileCache::_CountConnectedInterfaces(uint *,uint *)
0x180006f4d  mov     esi, eax
0x180006f4f  test    eax, eax
0x180006f51  js      loc_18000702F
0x180006f57  mov     ecx, dword ptr [rsp+28h+arg_0]
0x180006f5b  mov     [rbx+10h], ecx
0x180006f5e  shl     rcx, 4; cb
0x180006f62  call    cs:__imp_CoTaskMemAlloc
0x180006f68  mov     [rbx+20h], rax
0x180006f6c  test    rax, rax
0x180006f6f  jz      loc_18000702A
0x180006f75  mov     r8d, [rbx+10h]
0x180006f79  xor     edx, edx; Val
0x180006f7b  shl     r8, 4; Size
0x180006f7f  mov     rcx, rax; void *
0x180006f82  call    memset_0
0x180006f87  mov     ecx, [rbx+10h]
0x180006f8a  shl     rcx, 4; cb
0x180006f8e  call    cs:__imp_CoTaskMemAlloc
0x180006f94  mov     [rbx+28h], rax
0x180006f98  test    rax, rax
0x180006f9b  jz      loc_18000702A
0x180006fa1  mov     r8d, [rbx+10h]
0x180006fa5  xor     edx, edx; Val
0x180006fa7  shl     r8, 4; Size
0x180006fab  mov     rcx, rax; void *
0x180006fae  call    memset_0
0x180006fb3  mov     ecx, [rbx+10h]
0x180006fb6  shl     rcx, 3; cb
0x180006fba  call    cs:__imp_CoTaskMemAlloc
0x180006fc0  mov     [rbx+18h], rax
0x180006fc4  test    rax, rax
0x180006fc7  jz      short loc_18000702A
0x180006fc9  mov     r8d, [rbx+10h]
0x180006fcd  xor     edx, edx; Val
0x180006fcf  shl     r8, 3; Size
0x180006fd3  mov     rcx, rax; void *
0x180006fd6  call    memset_0
0x180006fdb  mov     rcx, [rbx+8]
0x180006fdf  lea     r8, [rsp+28h+arg_0]
0x180006fe4  mov     [rsp+28h+arg_0], 0
0x180006fed  mov     edx, 1
0x180006ff2  mov     rax, [rcx]
0x180006ff5  mov     rax, [rax+20h]
0x180006ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffe  mov     esi, eax
0x180007000  test    eax, eax
0x180007002  js      short loc_18000702F
0x180007004  mov     rdx, [rsp+28h+arg_0]; struct IEnumNetworkPrivate *
0x180007009  mov     rcx, rbx; this
0x18000700c  call    ?_AddMappings@CProfileCache@@AEAAJPEAUIEnumNetworkPrivate@@@Z; CProfileCache::_AddMappings(IEnumNetworkPrivate *)
0x180007011  mov     rcx, [rsp+28h+arg_0]
0x180007016  mov     esi, eax
0x180007018  mov     rax, [rcx]
0x18000701b  mov     rax, [rax+10h]
0x18000701f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007024  test    esi, esi
0x180007026  jns     short loc_180007037
0x180007028  jmp     short loc_18000702F
0x18000702a  mov     esi, 8007000Eh
0x18000702f  mov     rcx, rbx; this
0x180007032  call    ?_ClearMapping@CProfileCache@@AEAAXXZ; CProfileCache::_ClearMapping(void)
0x180007037  mov     edx, [rdi+4]
0x18000703a  dec     edx
0x18000703c  mov     eax, edx
0x18000703e  and     al, 3
0x180007040  neg     al
0x180007042  sbb     ecx, ecx
0x180007044  and     ecx, edx
0x180007046  xchg    ecx, [rdi+4]
0x180007049  jnz     short loc_180007066
0x18000704b  prefetchw byte ptr [rdi]
0x18000704e  mov     edx, [rdi]
0x180007050  mov     eax, edx
0x180007052  lea     ecx, [rdx-10000h]
0x180007058  and     ecx, 0FFFF0000h
0x18000705e  lock cmpxchg [rdi], ecx
0x180007062  cmp     edx, eax
0x180007064  jnz     short loc_18000704E
0x180007066  mov     rbx, [rsp+28h+arg_10]
0x18000706b  mov     eax, esi
0x18000706d  mov     rsi, [rsp+28h+arg_18]
0x180007072  add     rsp, 20h
0x180007076  pop     rdi
0x180007077  retn
```
