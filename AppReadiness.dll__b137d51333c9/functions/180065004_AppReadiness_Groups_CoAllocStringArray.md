# AppReadiness::Groups::_CoAllocStringArray

- ea: `0x180065004`
- end: `0x1800650c1`
- name: `AppReadiness::Groups::_CoAllocStringArray`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025e34`

## callees

- `0x180008420`
- `0x18001ffd0`
- `0x180020458`
- `0x180065004`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800650a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800650a3`

## pseudocode

```c
__int64 __fastcall AppReadiness::Groups::_CoAllocStringArray(__int64 a1, unsigned __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v7; // rdx
  void *v8; // rcx
  int v9; // ebx
  int v10; // eax
  unsigned __int64 v11; // rbp
  int v12; // eax
  unsigned __int64 v13; // rdi
  unsigned __int64 v15; // [rsp+60h] [rbp+18h] BYREF
  void *v16; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  *a3 = 0;
  v16 = 0;
  v15 = 0;
  v9 = ULongLongMult(a2, 8u, &v15);
  if ( v9 >= 0 )
  {
    v10 = CTCoAllocPolicy::Alloc(v8, 1u, v15, &v16);
    v3 = v16;
    v9 = v10;
  }
  if ( v9 >= 0 )
  {
    v11 = 0;
    do
    {
      if ( v11 >= a2 )
      {
        *a3 = v3;
        return (unsigned int)v9;
      }
      v12 = _AllocString<CTCoAllocPolicy>((__int64)v8, v7, *(__int64 **)(a1 + 8 * v11), &v3[v11]);
      v8 = (void *)(v11 + 1);
      v9 = v12;
      if ( v12 < 0 )
        v8 = (void *)v11;
      v11 = (unsigned __int64)v8;
    }
    while ( v12 >= 0 );
    v13 = 0;
    if ( v8 )
    {
      do
        CoTaskMemFree((LPVOID)v3[v13++]);
      while ( v13 < v11 );
    }
    CoTaskMemFree(v3);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180065004  mov     rax, rsp
0x180065007  mov     [rax+8], rbx
0x18006500b  push    rbp
0x18006500c  push    rsi
0x18006500d  push    rdi
0x18006500e  push    r14
0x180065010  push    r15
0x180065012  sub     rsp, 20h
0x180065016  xor     esi, esi
0x180065018  mov     qword ptr [r8], 0
0x18006501f  mov     r14, rdx
0x180065022  mov     [rax+20h], rsi
0x180065026  mov     r15, rcx
0x180065029  mov     [rax+18h], rsi
0x18006502d  mov     rdi, r8
0x180065030  mov     rcx, r14; unsigned __int64
0x180065033  lea     edx, [rsi+8]; unsigned __int64
0x180065036  lea     r8, [rax+18h]; unsigned __int64 *
0x18006503a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006503f  mov     ebx, eax
0x180065041  test    eax, eax
0x180065043  js      short loc_18006505E
0x180065045  mov     r8, [rsp+48h+arg_10]; unsigned __int64
0x18006504a  lea     r9, [rsp+48h+arg_18]; void **
0x18006504f  lea     edx, [rsi+1]; unsigned int
0x180065052  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180065057  mov     rsi, [rsp+48h+arg_18]
0x18006505c  mov     ebx, eax
0x18006505e  test    ebx, ebx
0x180065060  js      short loc_1800650AE
0x180065062  xor     ebp, ebp
0x180065064  cmp     rbp, r14
0x180065067  jnb     short loc_1800650AB
0x180065069  mov     r8, [r15+rbp*8]
0x18006506d  lea     r9, [rsi+rbp*8]
0x180065071  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180065076  lea     rcx, [rbp+1]
0x18006507a  test    eax, eax
0x18006507c  mov     ebx, eax
0x18006507e  cmovs   rcx, rbp
0x180065082  mov     rbp, rcx
0x180065085  jns     short loc_180065064
0x180065087  xor     edi, edi
0x180065089  test    rcx, rcx
0x18006508c  jz      short loc_1800650A0
0x18006508e  mov     rcx, [rsi+rdi*8]; pv
0x180065092  call    cs:__imp_CoTaskMemFree
0x180065098  inc     rdi
0x18006509b  cmp     rdi, rbp
0x18006509e  jb      short loc_18006508E
0x1800650a0  mov     rcx, rsi; pv
0x1800650a3  call    cs:__imp_CoTaskMemFree
0x1800650a9  jmp     short loc_1800650AE
0x1800650ab  mov     [rdi], rsi
0x1800650ae  mov     eax, ebx
0x1800650b0  mov     rbx, [rsp+48h+arg_0]
0x1800650b5  add     rsp, 20h
0x1800650b9  pop     r15
0x1800650bb  pop     r14
0x1800650bd  pop     rdi
0x1800650be  pop     rsi
0x1800650bf  pop     rbp
0x1800650c0  retn
```
