# BlockMem::Init(void)

- ea: `0x1400011ac`
- end: `0x14000138c`
- name: `?Init@BlockMem@@SAJXZ`
- size: `480`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x14000248c`

## callees

- `0x140001138`
- `0x1400011ac`
- `0x140004f00`
- `0x140004f2c`
- `0x140006590`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x1400011fe`
- `KERNEL32!HeapCreate` at `0x1400012a2`
- `KERNEL32!HeapCreate` at `0x140001338`
- `KERNEL32!HeapCreate` at `0x1400011fe`
- `KERNEL32!HeapCreate` at `0x1400012a2`
- `KERNEL32!HeapCreate` at `0x140001338`
- `KERNEL32!HeapDestroy` at `0x140001250`
- `KERNEL32!HeapDestroy` at `0x140001250`
- `KERNEL32!FreeLibrary` at `0x140001236`
- `KERNEL32!FreeLibrary` at `0x140001236`
- `KERNEL32!GetProcAddress` at `0x1400011e9`
- `KERNEL32!GetProcAddress` at `0x1400011e9`

## string_xrefs

- `0x1400011c7`: `kernel32.dll`

## pseudocode

```c
__int64 BlockMem::Init(void)
{
  int v0; // ebx
  unsigned int v1; // r15d
  FARPROC ProcAddress; // rdi
  HANDLE v3; // rax
  unsigned int v4; // r13d
  unsigned int v5; // edi
  signed int v6; // ebx
  __int64 v7; // r14
  __int64 v8; // rax
  int v9; // ebp
  __int64 *v10; // rsi
  unsigned int v11; // r12d
  HANDLE v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  HANDLE v15; // rcx
  __int64 *v16; // rax
  int v18; // [rsp+70h] [rbp+8h] BYREF
  HMODULE hModule; // [rsp+78h] [rbp+10h] BYREF
  __int64 v20; // [rsp+80h] [rbp+18h]

  v0 = 0;
  v1 = LoadLibraryUsingFullPath(L"kernel32.dll", 0, &hModule);
  if ( !hModule )
    goto LABEL_6;
  ProcAddress = GetProcAddress(hModule, "HeapSetInformation");
  if ( ProcAddress )
  {
    v3 = HeapCreate(0, 0, 0);
    BlockMem::s_lfh = v3;
    if ( v3 )
    {
      v18 = 2;
      v0 = ((__int64 (__fastcall *)(HANDLE, _QWORD, int *, __int64))ProcAddress)(v3, 0, &v18, 4);
    }
  }
  FreeLibrary(hModule);
  if ( !v0 )
  {
LABEL_6:
    if ( BlockMem::s_lfh )
    {
      HeapDestroy(BlockMem::s_lfh);
      BlockMem::s_lfh = 0;
    }
    v4 = 0;
    v5 = 64;
    v6 = BlockMem::IndexFromSize(0x40u);
    v7 = v6;
    v20 = v6;
    v8 = v6;
    while ( 2 )
    {
      v9 = 0;
      v10 = &qword_14000A158[2 * v8];
      do
      {
        v11 = v5;
        if ( v5 <= 0x80000 )
        {
          v12 = HeapCreate(0, 0, 0);
          if ( !v12 )
            return (unsigned int)GetLastWin32Error();
          *(v10 - 1) = (__int64)v12;
          *(_DWORD *)v10 = v5;
          if ( v9 )
            v5 = 2 * v4;
          else
            v5 |= v5 >> 1;
          ++v6;
          v8 = v20 + 1;
          v10 += 2;
          ++v20;
          if ( v9 )
            v11 = v4;
          v4 = v11;
        }
        ++v9;
      }
      while ( v9 < 2 );
      if ( v5 <= 0x80000 )
        continue;
      break;
    }
    if ( v7 > 0 )
    {
      v13 = 2 * v7;
      v14 = qword_14000A158;
      do
      {
        *(v14 - 1) = (__int64)*(&BlockMem::s_heaps + v13);
        *(_DWORD *)v14 = *((_DWORD *)&BlockMem::s_heaps + 2 * v13 + 2);
        v14 += 2;
        --v7;
      }
      while ( v7 );
    }
    v15 = HeapCreate(0, 0, 0);
    if ( !v15 )
      return (unsigned int)GetLastWin32Error();
    if ( (unsigned int)v6 < 0x43 )
    {
      v16 = &qword_14000A158[2 * v6];
      do
      {
        *(_DWORD *)v16 = -1;
        ++v6;
        *(v16 - 1) = (__int64)v15;
        v16 += 2;
      }
      while ( (unsigned int)v6 < 0x43 );
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400011ac  mov     [rsp+arg_18], rbx
0x1400011b1  push    rbp
0x1400011b2  push    rsi
0x1400011b3  push    rdi
0x1400011b4  push    r12
0x1400011b6  push    r13
0x1400011b8  push    r14
0x1400011ba  push    r15
0x1400011bc  sub     rsp, 30h
0x1400011c0  lea     r8, [rsp+68h+hModule]; HINSTANCE *
0x1400011c5  xor     edx, edx; int
0x1400011c7  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1400011ce  xor     ebx, ebx
0x1400011d0  call    ?LoadLibraryUsingFullPath@@YAJPEBGHPEAPEAUHINSTANCE__@@@Z; LoadLibraryUsingFullPath(ushort const *,int,HINSTANCE__ * *)
0x1400011d5  mov     rcx, [rsp+68h+hModule]; hModule
0x1400011da  mov     r15d, eax
0x1400011dd  test    rcx, rcx
0x1400011e0  jz      short loc_140001244
0x1400011e2  lea     rdx, ProcName; "HeapSetInformation"
0x1400011e9  call    cs:__imp_GetProcAddress
0x1400011ef  mov     rdi, rax
0x1400011f2  test    rax, rax
0x1400011f5  jz      short loc_140001231
0x1400011f7  xor     r8d, r8d; dwMaximumSize
0x1400011fa  xor     edx, edx; dwInitialSize
0x1400011fc  xor     ecx, ecx; flOptions
0x1400011fe  call    cs:__imp_HeapCreate
0x140001204  mov     cs:?s_lfh@BlockMem@@0PEAXEA, rax; void * BlockMem::s_lfh
0x14000120b  test    rax, rax
0x14000120e  jz      short loc_140001231
0x140001210  mov     rcx, rax
0x140001213  mov     [rsp+68h+arg_0], 2
0x14000121b  mov     rax, rdi
0x14000121e  lea     r9d, [rbx+4]
0x140001222  lea     r8, [rsp+68h+arg_0]
0x140001227  xor     edx, edx
0x140001229  call    cs:__guard_dispatch_icall_fptr
0x14000122f  mov     ebx, eax
0x140001231  mov     rcx, [rsp+68h+hModule]; hLibModule
0x140001236  call    cs:__imp_FreeLibrary
0x14000123c  test    ebx, ebx
0x14000123e  jnz     loc_140001367
0x140001244  mov     rcx, cs:?s_lfh@BlockMem@@0PEAXEA; hHeap
0x14000124b  test    rcx, rcx
0x14000124e  jz      short loc_14000125E
0x140001250  call    cs:__imp_HeapDestroy
0x140001256  and     cs:?s_lfh@BlockMem@@0PEAXEA, 0; void * BlockMem::s_lfh
0x14000125e  xor     r13d, r13d
0x140001261  lea     edi, [r13+40h]
0x140001265  mov     ecx, edi; unsigned int
0x140001267  call    ?IndexFromSize@BlockMem@@CAHI@Z; BlockMem::IndexFromSize(uint)
0x14000126c  movsxd  rbx, eax
0x14000126f  mov     r14, rbx
0x140001272  mov     [rsp+68h+arg_10], rbx
0x14000127a  mov     rax, rbx
0x14000127d  mov     rsi, rax
0x140001280  lea     rcx, qword_14000A158
0x140001287  shl     rsi, 4
0x14000128b  xor     ebp, ebp
0x14000128d  add     rsi, rcx
0x140001290  mov     r12d, edi
0x140001293  cmp     edi, 80000h
0x140001299  ja      short loc_1400012ED
0x14000129b  xor     r8d, r8d; dwMaximumSize
0x14000129e  xor     edx, edx; dwInitialSize
0x1400012a0  xor     ecx, ecx; flOptions
0x1400012a2  call    cs:__imp_HeapCreate
0x1400012a8  test    rax, rax
0x1400012ab  jz      loc_140001382
0x1400012b1  mov     [rsi-8], rax
0x1400012b5  mov     [rsi], edi
0x1400012b7  test    ebp, ebp
0x1400012b9  jnz     short loc_1400012C3
0x1400012bb  mov     eax, edi
0x1400012bd  shr     eax, 1
0x1400012bf  or      edi, eax
0x1400012c1  jmp     short loc_1400012CB
0x1400012c3  lea     edi, ds:0[r13*2]
0x1400012cb  mov     rax, [rsp+68h+arg_10]
0x1400012d3  inc     ebx
0x1400012d5  inc     rax
0x1400012d8  add     rsi, 10h
0x1400012dc  test    ebp, ebp
0x1400012de  mov     [rsp+68h+arg_10], rax
0x1400012e6  cmovnz  r12d, r13d
0x1400012ea  mov     r13d, r12d
0x1400012ed  inc     ebp
0x1400012ef  cmp     ebp, 2
0x1400012f2  jl      short loc_140001290
0x1400012f4  cmp     edi, 80000h
0x1400012fa  jbe     short loc_14000127D
0x1400012fc  lea     rdi, qword_14000A158
0x140001303  test    r14, r14
0x140001306  jle     short loc_140001331
0x140001308  mov     rdx, r14
0x14000130b  lea     r8, ?s_heaps@BlockMem@@0PAUBlockMemHeapInfo@@A; BlockMemHeapInfo near * BlockMem::s_heaps
0x140001312  add     rdx, rdx
0x140001315  mov     rcx, rdi
0x140001318  mov     rax, [r8+rdx*8]
0x14000131c  mov     [rcx-8], rax
0x140001320  mov     eax, [r8+rdx*8+8]
0x140001325  mov     [rcx], eax
0x140001327  lea     rcx, [rcx+10h]
0x14000132b  sub     r14, 1
0x14000132f  jnz     short loc_140001318
0x140001331  xor     r8d, r8d; dwMaximumSize
0x140001334  xor     edx, edx; dwInitialSize
0x140001336  xor     ecx, ecx; flOptions
0x140001338  call    cs:__imp_HeapCreate
0x14000133e  mov     rcx, rax
0x140001341  test    rax, rax
0x140001344  jz      short loc_140001382
0x140001346  cmp     ebx, 43h ; 'C'
0x140001349  jnb     short loc_140001367
0x14000134b  movsxd  rax, ebx
0x14000134e  shl     rax, 4
0x140001352  add     rax, rdi
0x140001355  or      dword ptr [rax], 0FFFFFFFFh
0x140001358  inc     ebx
0x14000135a  mov     [rax-8], rcx
0x14000135e  lea     rax, [rax+10h]
0x140001362  cmp     ebx, 43h ; 'C'
0x140001365  jb      short loc_140001355
0x140001367  mov     rbx, [rsp+68h+arg_18]
0x14000136f  mov     eax, r15d
0x140001372  add     rsp, 30h
0x140001376  pop     r15
0x140001378  pop     r14
0x14000137a  pop     r13
0x14000137c  pop     r12
0x14000137e  pop     rdi
0x14000137f  pop     rsi
0x140001380  pop     rbp
0x140001381  retn
0x140001382  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x140001387  mov     r15d, eax
0x14000138a  jmp     short loc_140001367
```
