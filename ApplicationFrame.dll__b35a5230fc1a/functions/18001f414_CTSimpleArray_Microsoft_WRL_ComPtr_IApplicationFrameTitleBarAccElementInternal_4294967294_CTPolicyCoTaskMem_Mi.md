# CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &,unsigned __int64 *)

- ea: `0x18001f414`
- end: `0x18001f547`
- name: `??$_Add@AEBV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@@?$CTSimpleArray@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@@@@@QEAAJAEBV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@PEA_K@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e930`

## callees

- `0x18001f414`
- `0x18001f550`
- `0x1800446fc`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001f4c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001f4c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rcx
  __int64 v6; // r8
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rsi
  __int64 v9; // r9
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rbx
  char *v14; // rax
  char *v15; // rbp
  unsigned __int64 v16; // rax
  __int64 *v17; // rdx
  __int64 v18; // rcx

  v4 = 0;
  v5 = *(_QWORD *)(a1 + 24);
  v6 = *(_QWORD *)(a1 + 8);
  if ( v6 != v5 )
  {
LABEL_19:
    v17 = (__int64 *)(*(_QWORD *)a1 + 8 * (*(_QWORD *)(a1 + 8))++);
    if ( v17 )
    {
      v18 = *a2;
      *v17 = *a2;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    }
    return (unsigned int)v4;
  }
  v7 = v6 + 1;
  v4 = -2147024774;
  v8 = 4294967294LL;
  if ( v7 > 0xFFFFFFFE || (v4 = 0, v7 <= v5) )
  {
    if ( v4 < 0 )
      return (unsigned int)v4;
    goto LABEL_19;
  }
  v9 = 2 * v5;
  if ( !is_mul_ok(v5, 2u) )
    return (unsigned int)-2147024362;
  v10 = v5;
  v11 = v5 + 4096;
  if ( v10 <= 0x1000 )
    v11 = v9;
  if ( v7 > v11 )
  {
    v8 = v7;
  }
  else if ( v11 <= 0xFFFFFFFE )
  {
    v8 = v11;
  }
  v12 = 8 * v8;
  if ( !is_mul_ok(v8, 8u) )
    return (unsigned int)-2147024362;
  v14 = (char *)CoTaskMemRealloc(*(LPVOID *)a1, 8 * v8);
  v15 = v14;
  if ( v14 )
  {
    v16 = CTCoAllocPolicy::_CoTaskMemSize(v14);
    if ( v16 > v12 )
      memset_0(&v15[v12], 0, v16 - v12);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
  if ( v4 >= 0 )
  {
    *(_QWORD *)(a1 + 24) = v8;
    *(_QWORD *)a1 = v15;
    goto LABEL_19;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f414  mov     [rsp+arg_0], rbx
0x18001f419  mov     [rsp+arg_8], rbp
0x18001f41e  push    rsi
0x18001f41f  push    rdi
0x18001f420  push    r14
0x18001f422  sub     rsp, 20h
0x18001f426  mov     r14, rdx
0x18001f429  mov     rdi, rcx
0x18001f42c  xor     ebx, ebx
0x18001f42e  mov     rcx, [rcx+18h]
0x18001f432  mov     r8, [rdi+8]
0x18001f436  cmp     r8, rcx
0x18001f439  jnz     loc_18001F4EB
0x18001f43f  inc     r8
0x18001f442  mov     ebx, 8007007Ah
0x18001f447  mov     esi, 0FFFFFFFEh
0x18001f44c  cmp     r8, rsi
0x18001f44f  ja      loc_18001F52B
0x18001f455  xor     ebx, ebx
0x18001f457  cmp     r8, rcx
0x18001f45a  jbe     loc_18001F52B
0x18001f460  lea     eax, [rbx+2]
0x18001f463  mul     rcx
0x18001f466  mov     r9, rax
0x18001f469  test    rdx, rdx
0x18001f46c  jnz     short loc_18001F4A3
0x18001f46e  sub     rax, rcx
0x18001f471  add     rcx, 1000h
0x18001f478  cmp     rax, 1000h
0x18001f47e  cmovbe  rcx, r9
0x18001f482  cmp     r8, rcx
0x18001f485  ja      loc_18001F51C
0x18001f48b  cmp     rcx, rsi
0x18001f48e  ja      short loc_18001F493
0x18001f490  mov     rsi, rcx
0x18001f493  mov     eax, 8
0x18001f498  mul     rsi
0x18001f49b  mov     rbx, rax
0x18001f49e  test    rdx, rdx
0x18001f4a1  jz      short loc_18001F4BD
0x18001f4a3  mov     ebx, 80070216h
0x18001f4a8  mov     eax, ebx
0x18001f4aa  mov     rbx, [rsp+38h+arg_0]
0x18001f4af  mov     rbp, [rsp+38h+arg_8]
0x18001f4b4  add     rsp, 20h
0x18001f4b8  pop     r14
0x18001f4ba  pop     rdi
0x18001f4bb  pop     rsi
0x18001f4bc  retn
0x18001f4bd  mov     rdx, rbx; cb
0x18001f4c0  mov     rcx, [rdi]; pv
0x18001f4c3  call    cs:__imp_CoTaskMemRealloc
0x18001f4c9  mov     rbp, rax
0x18001f4cc  test    rax, rax
0x18001f4cf  jz      short loc_18001F524
0x18001f4d1  mov     rcx, rax; void *
0x18001f4d4  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001f4d9  cmp     rax, rbx
0x18001f4dc  ja      short loc_18001F534
0x18001f4de  xor     ebx, ebx
0x18001f4e0  test    ebx, ebx
0x18001f4e2  js      short loc_18001F4A8
0x18001f4e4  mov     [rdi+18h], rsi
0x18001f4e8  mov     [rdi], rbp
0x18001f4eb  inc     qword ptr [rdi+8]
0x18001f4ef  mov     rdx, [rdi+8]
0x18001f4f3  mov     rax, [rdi]
0x18001f4f6  dec     rdx
0x18001f4f9  lea     rdx, [rax+rdx*8]
0x18001f4fd  test    rdx, rdx
0x18001f500  jz      short loc_18001F4A8
0x18001f502  mov     rcx, [r14]
0x18001f505  mov     [rdx], rcx
0x18001f508  test    rcx, rcx
0x18001f50b  jz      short loc_18001F51A
0x18001f50d  mov     rdx, [rcx]
0x18001f510  mov     rax, [rdx+8]
0x18001f514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f519  nop
0x18001f51a  jmp     short loc_18001F4A8
0x18001f51c  mov     rsi, r8
0x18001f51f  jmp     loc_18001F493
0x18001f524  mov     ebx, 8007000Eh
0x18001f529  jmp     short loc_18001F4E0
0x18001f52b  test    ebx, ebx
0x18001f52d  jns     short loc_18001F4EB
0x18001f52f  jmp     loc_18001F4A8
0x18001f534  sub     rax, rbx
0x18001f537  lea     rcx, [rbx+rbp]; void *
0x18001f53b  mov     r8, rax; Size
0x18001f53e  xor     edx, edx; Val
0x18001f540  call    memset_0
0x18001f545  jmp     short loc_18001F4DE
```
