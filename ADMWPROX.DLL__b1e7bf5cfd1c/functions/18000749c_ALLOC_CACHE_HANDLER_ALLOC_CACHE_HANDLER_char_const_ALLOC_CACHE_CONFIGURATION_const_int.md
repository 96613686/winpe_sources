# ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)

- ea: `0x18000749c`
- end: `0x1800075fc`
- name: `??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z`
- size: `352`
- prototype: `ALLOC_CACHE_HANDLER *__fastcall(ALLOC_CACHE_HANDLER *__hidden this, const char *, const struct ALLOC_CACHE_CONFIGURATION *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180007c70`
- `0x180007f1c`

## callees

- `0x18000749c`
- `0x180007810`
- `0x180007b14`
- `0x1800083de`

## import_xrefs

- `msvcrt!_aligned_malloc` at `0x180007561`
- `msvcrt!_aligned_malloc` at `0x180007561`
- `KERNEL32!InitializeSListHead` at `0x1800075a6`
- `KERNEL32!InitializeSListHead` at `0x1800075a6`

## pseudocode

```c
ALLOC_CACHE_HANDLER *__fastcall ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
        ALLOC_CACHE_HANDLER *this,
        const char *a2,
        const struct ALLOC_CACHE_CONFIGURATION *a3,
        int a4)
{
  int v5; // eax
  unsigned int v6; // ecx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // r15
  size_t v10; // rbp
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  unsigned int v13; // ebp
  size_t Alignment; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

  *(_DWORD *)this = 0;
  *((_DWORD *)this + 1) = a4;
  *((_DWORD *)this + 2) = 0;
  v5 = *((_DWORD *)a3 + 1);
  *((_DWORD *)this + 3) = v5;
  v6 = *((_DWORD *)a3 + 2);
  *((_QWORD *)this + 25) = a2;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_DWORD *)this + 48) = 0;
  if ( v5 > 0xFFFF )
    *((_DWORD *)this + 3) = 0xFFFF;
  v7 = 16;
  LODWORD(Alignment) = 0;
  v16 = 0;
  if ( v6 > 0x10 )
    v7 = v6;
  *((_DWORD *)this + 4) = v7;
  if ( (int)PER_CPU<_SLIST_HEADER>::GetProcessorInformation(&Alignment, &v16) >= 0 )
  {
    v8 = (unsigned int)Alignment >= 0x10 ? Alignment : (Alignment + 15) & ~(Alignment - 1);
    v9 = (unsigned int)Alignment;
    v10 = (unsigned int)Alignment + v8 * v16;
    v11 = _aligned_malloc(v10, (unsigned int)Alignment);
    v12 = v11;
    if ( v11 )
    {
      memset_0(v11, 0, (unsigned int)v10);
      v13 = 0;
      v12[2] = v16;
      v12[1] = v8;
      *v12 = (char *)v12 + v9;
      while ( (unsigned __int64)v13 < v12[2] )
        InitializeSListHead((PSLIST_HEADER)(*v12 + v12[1] * v13++));
      *((_QWORD *)this + 3) = v12;
      *((_DWORD *)this + 49) = _InterlockedIncrement(&ALLOC_CACHE_HANDLER::sm_nFillPattern);
      if ( ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled )
        *((_DWORD *)this + 3) = 0;
      *(_DWORD *)this = 1;
      ALLOC_CACHE_HANDLER::InsertNewItem(this);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18000749c  mov     [rsp+arg_8], rbx
0x1800074a1  mov     [rsp+arg_10], rbp
0x1800074a6  push    rsi
0x1800074a7  push    rdi
0x1800074a8  push    r15
0x1800074aa  sub     rsp, 20h
0x1800074ae  mov     rbx, rcx
0x1800074b1  mov     dword ptr [rcx], 0
0x1800074b7  mov     [rcx+4], r9d
0x1800074bb  mov     dword ptr [rcx+8], 0
0x1800074c2  mov     eax, [r8+4]
0x1800074c6  mov     [rcx+0Ch], eax
0x1800074c9  mov     ecx, [r8+8]
0x1800074cd  mov     [rbx+0C8h], rdx
0x1800074d4  mov     edx, 0FFFFh
0x1800074d9  mov     qword ptr [rbx+18h], 0
0x1800074e1  mov     dword ptr [rbx+40h], 0
0x1800074e8  mov     dword ptr [rbx+80h], 0
0x1800074f2  mov     dword ptr [rbx+0C0h], 0
0x1800074fc  cmp     eax, edx
0x1800074fe  jle     short loc_180007503
0x180007500  mov     [rbx+0Ch], edx
0x180007503  mov     eax, 10h
0x180007508  mov     dword ptr [rsp+38h+Alignment], 0
0x180007510  cmp     ecx, eax
0x180007512  mov     [rsp+38h+arg_18], 0
0x18000751a  lea     rdx, [rsp+38h+arg_18]
0x18000751f  cmova   eax, ecx
0x180007522  lea     rcx, [rsp+38h+Alignment]
0x180007527  mov     [rbx+10h], eax
0x18000752a  call    ?GetProcessorInformation@?$PER_CPU@T_SLIST_HEADER@@@@CAJPEAK0@Z; PER_CPU<_SLIST_HEADER>::GetProcessorInformation(ulong *,ulong *)
0x18000752f  test    eax, eax
0x180007531  js      loc_1800075E6
0x180007537  mov     ecx, dword ptr [rsp+38h+Alignment]
0x18000753b  cmp     ecx, 10h
0x18000753e  jnb     short loc_18000754C
0x180007540  lea     edi, [rcx-1]
0x180007543  not     edi
0x180007545  lea     eax, [rcx+0Fh]
0x180007548  and     edi, eax
0x18000754a  jmp     short loc_18000754E
0x18000754c  mov     edi, ecx
0x18000754e  mov     eax, [rsp+38h+arg_18]
0x180007552  mov     r15, rcx
0x180007555  imul    eax, edi
0x180007558  mov     rdx, rcx; Alignment
0x18000755b  add     eax, ecx
0x18000755d  mov     ecx, eax; Size
0x18000755f  mov     ebp, eax
0x180007561  call    cs:__imp__aligned_malloc
0x180007567  mov     rsi, rax
0x18000756a  test    rax, rax
0x18000756d  jz      short loc_1800075E6
0x18000756f  mov     r8d, ebp; Size
0x180007572  xor     edx, edx; Val
0x180007574  mov     rcx, rax; void *
0x180007577  call    memset_0
0x18000757c  mov     eax, [rsp+38h+arg_18]
0x180007580  lea     rcx, [r15+rsi]
0x180007584  xor     ebp, ebp
0x180007586  mov     [rsi+10h], rax
0x18000758a  mov     eax, edi
0x18000758c  mov     [rsi+8], rax
0x180007590  mov     [rsi], rcx
0x180007593  lea     edi, [rbp+1]
0x180007596  cmp     [rsp+38h+arg_18], ebp
0x18000759a  jbe     short loc_1800075B6
0x18000759c  mov     ecx, ebp
0x18000759e  imul    rcx, [rsi+8]
0x1800075a3  add     rcx, [rsi]; ListHead
0x1800075a6  call    cs:__imp_InitializeSListHead
0x1800075ac  add     ebp, edi
0x1800075ae  mov     eax, ebp
0x1800075b0  cmp     rax, [rsi+10h]
0x1800075b4  jb      short loc_18000759C
0x1800075b6  mov     [rbx+18h], rsi
0x1800075ba  mov     eax, edi
0x1800075bc  lock xadd cs:?sm_nFillPattern@ALLOC_CACHE_HANDLER@@0JA, eax; long ALLOC_CACHE_HANDLER::sm_nFillPattern
0x1800075c4  add     eax, edi
0x1800075c6  mov     [rbx+0C4h], eax
0x1800075cc  cmp     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x1800075d3  jz      short loc_1800075DC
0x1800075d5  mov     dword ptr [rbx+0Ch], 0
0x1800075dc  mov     rcx, rbx; struct ALLOC_CACHE_HANDLER *
0x1800075df  mov     [rbx], edi
0x1800075e1  call    ?InsertNewItem@ALLOC_CACHE_HANDLER@@SAXPEAV1@@Z; ALLOC_CACHE_HANDLER::InsertNewItem(ALLOC_CACHE_HANDLER *)
0x1800075e6  mov     rbp, [rsp+38h+arg_10]
0x1800075eb  mov     rax, rbx
0x1800075ee  mov     rbx, [rsp+38h+arg_8]
0x1800075f3  add     rsp, 20h
0x1800075f7  pop     r15
0x1800075f9  pop     rdi
0x1800075fa  pop     rsi
0x1800075fb  retn
```
