# CabInit(void)

- ea: `0x18000c284`
- end: `0x18000c390`
- name: `?CabInit@@YAPEAU_CAB_STRUCT@@XZ`
- size: `268`
- prototype: `struct _CAB_STRUCT *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c398`

## callees

- `0x18000c284`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000c29d`
- `KERNEL32!HeapAlloc` at `0x18000c29d`
- `KERNEL32!GetProcessHeap` at `0x18000c28e`
- `KERNEL32!GetProcessHeap` at `0x18000c369`
- `KERNEL32!GetProcessHeap` at `0x18000c28e`
- `KERNEL32!GetProcessHeap` at `0x18000c369`
- `KERNEL32!SetLastError` at `0x18000c2ae`
- `KERNEL32!SetLastError` at `0x18000c2ae`
- `KERNEL32!HeapFree` at `0x18000c377`
- `KERNEL32!HeapFree` at `0x18000c377`
- `Cabinet!__imp_FDICreate` at `0x18000c320`
- `Cabinet!__imp_FDICreate` at `0x18000c320`
- `Cabinet!__imp_FDIDestroy` at `0x18000c357`
- `Cabinet!__imp_FDIDestroy` at `0x18000c357`

## pseudocode

```c
struct _CAB_STRUCT *CabInit(void)
{
  HANDLE ProcessHeap; // rax
  char *v1; // rax
  char *v2; // rbx
  char *v4; // rdi
  HFDI v5; // rax
  HANDLE v6; // rax

  ProcessHeap = GetProcessHeap();
  v1 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
  v2 = v1;
  if ( v1 )
  {
    v4 = v1;
    *(_OWORD *)v1 = 0;
    *((_QWORD *)v1 + 2) = 0;
    v5 = FDICreate(
           FdiAlloc,
           FdiFree,
           (PFNOPEN)FdiOpen,
           (PFNREAD)FdiRead,
           (PFNWRITE)FdiWrite,
           FdiClose,
           FdiSeek,
           -1,
           (PERF)(v1 + 8));
    *(_QWORD *)v2 = v5;
    if ( !v5 )
    {
      if ( *(_QWORD *)v2 )
        FDIDestroy(*(HFDI *)v2);
      *(_OWORD *)v2 = 0;
      *((_QWORD *)v2 + 2) = 0;
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v2);
      return 0;
    }
    return (struct _CAB_STRUCT *)v4;
  }
  else
  {
    SetLastError(8u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000c284  mov     [rsp+arg_10], rbx
0x18000c289  push    rdi
0x18000c28a  sub     rsp, 60h
0x18000c28e  call    cs:__imp_GetProcessHeap
0x18000c294  mov     rcx, rax; hHeap
0x18000c297  xor     edx, edx; dwFlags
0x18000c299  lea     r8d, [rdx+18h]; dwBytes
0x18000c29d  call    cs:__imp_HeapAlloc
0x18000c2a3  mov     rbx, rax
0x18000c2a6  test    rax, rax
0x18000c2a9  jnz     short loc_18000C2BB
0x18000c2ab  lea     ecx, [rax+8]; dwErrCode
0x18000c2ae  call    cs:__imp_SetLastError
0x18000c2b4  xor     eax, eax
0x18000c2b6  jmp     loc_18000C382
0x18000c2bb  mov     rdi, rbx
0x18000c2be  mov     [rsp+68h+arg_0], rbx
0x18000c2c3  xorps   xmm0, xmm0
0x18000c2c6  xor     eax, eax
0x18000c2c8  movups  xmmword ptr [rbx], xmm0
0x18000c2cb  mov     [rbx+10h], rax
0x18000c2cf  lea     rax, [rbx+8]
0x18000c2d3  mov     [rsp+68h+perf], rax; perf
0x18000c2d8  mov     [rsp+68h+cpuType], 0FFFFFFFFh; cpuType
0x18000c2e0  lea     rax, FdiSeek
0x18000c2e7  mov     [rsp+68h+pfnseek], rax; pfnseek
0x18000c2ec  lea     rax, FdiClose
0x18000c2f3  mov     [rsp+68h+pfnclose], rax; pfnclose
0x18000c2f8  lea     rax, FdiWrite
0x18000c2ff  mov     [rsp+68h+pfnwrite], rax; pfnwrite
0x18000c304  lea     r9, FdiRead; pfnread
0x18000c30b  lea     r8, FdiOpen; pfnopen
0x18000c312  lea     rdx, FdiFree; pfnfree
0x18000c319  lea     rcx, FdiAlloc; pfnalloc
0x18000c320  call    cs:__imp_FDICreate
0x18000c326  mov     [rbx], rax
0x18000c329  xor     ecx, ecx
0x18000c32b  lea     edx, [rcx+1]
0x18000c32e  test    rax, rax
0x18000c331  cmovz   ecx, edx
0x18000c334  mov     [rsp+68h+var_18], ecx
0x18000c338  jmp     short loc_18000C34B
0x18000c33a  mov     ecx, 1
0x18000c33f  mov     [rsp+68h+var_18], ecx
0x18000c343  mov     rdi, [rsp+68h+arg_0]
0x18000c348  mov     rbx, rdi
0x18000c34b  test    ecx, ecx
0x18000c34d  jz      short loc_18000C37F
0x18000c34f  mov     rcx, [rbx]; hfdi
0x18000c352  test    rcx, rcx
0x18000c355  jz      short loc_18000C35D
0x18000c357  call    cs:__imp_FDIDestroy
0x18000c35d  xorps   xmm0, xmm0
0x18000c360  xor     eax, eax
0x18000c362  movups  xmmword ptr [rbx], xmm0
0x18000c365  mov     [rbx+10h], rax
0x18000c369  call    cs:__imp_GetProcessHeap
0x18000c36f  mov     rcx, rax; hHeap
0x18000c372  mov     r8, rbx; lpMem
0x18000c375  xor     edx, edx; dwFlags
0x18000c377  call    cs:__imp_HeapFree
0x18000c37d  xor     edi, edi
0x18000c37f  mov     rax, rdi
0x18000c382  mov     rbx, [rsp+68h+arg_10]
0x18000c38a  add     rsp, 60h
0x18000c38e  pop     rdi
0x18000c38f  retn
```
