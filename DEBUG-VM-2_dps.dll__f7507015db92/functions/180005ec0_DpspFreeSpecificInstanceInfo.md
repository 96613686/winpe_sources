# DpspFreeSpecificInstanceInfo

- ea: `0x180005ec0`
- end: `0x180006095`
- name: `DpspFreeSpecificInstanceInfo`
- size: `469`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001830`
- `0x180002090`
- `0x180003830`
- `0x18000f774`
- `0x180012670`
- `0x180013214`
- `0x1800137a8`

## callees

- `0x180005ec0`
- `0x1800060a0`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fa1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000605c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fa1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000605c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000608e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000604e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006077`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000604e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006077`

## string_xrefs

- `0x180005ef6`: `WdipDeleteInstanceParameters`
- `0x180005efd`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`

## pseudocode

```c
BOOL __fastcall DpspFreeSpecificInstanceInfo(__int64 a1)
{
  _QWORD *v1; // r15
  __int64 v2; // rsi
  unsigned int i; // ebx
  __int64 v4; // rax
  __int64 v5; // rbp
  void **v6; // r14
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  void *v9; // rdi
  HANDLE v10; // rax
  void *v11; // rdi
  HANDLE v12; // rax
  void *v13; // rbx
  HANDLE v14; // rax
  char *v15; // rcx
  char *v16; // rcx
  void *v17; // rbx
  HANDLE v18; // rax
  void *v19; // rbx
  HANDLE v20; // rax
  HANDLE v21; // rax

  v1 = *(_QWORD **)a1;
  v2 = *(_QWORD *)(*(_QWORD *)a1 + 1224LL);
  if ( v2 )
  {
    if ( *(_QWORD *)(v2 + 8) )
    {
      for ( i = 0; i < *(_DWORD *)(v2 + 4); ++i )
      {
        v4 = *(_QWORD *)(v2 + 8);
        v5 = *(_QWORD *)(v4 + 8LL * i);
        v6 = (void **)(v4 + 8LL * i);
        if ( v5 && v6 )
        {
          v7 = *(void **)(v5 + 48);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
          v9 = *(void **)(v5 + 56);
          *(_QWORD *)(v5 + 48) = 0;
          v10 = GetProcessHeap();
          HeapFree(v10, 0, v9);
          *(_QWORD *)(v5 + 56) = 0;
          v11 = *v6;
          v12 = GetProcessHeap();
          HeapFree(v12, 0, v11);
          *v6 = 0;
        }
      }
      v13 = *(void **)(v2 + 8);
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v13);
      *(_QWORD *)(v2 + 8) = 0;
    }
  }
  else
  {
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipDeleteInstanceParameters",
      124,
      (const wchar_t *)L"Error = %d",
      87);
  }
  v15 = (char *)v1[99];
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v15);
    v1[99] = 0;
  }
  v16 = (char *)v1[100];
  if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v16);
    v1[100] = 0;
  }
  v17 = (void *)v1[98];
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v17);
  v1[98] = 0;
  DpspFreeSpecificInstanceSID(v1);
  v19 = (void *)v1[94];
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v19);
  v1[94] = 0;
  v1[152] = 0;
  v1[101] = 0;
  v21 = GetProcessHeap();
  return HeapFree(v21, 0, v1);
}

```

## disassembly

```asm
0x180005ec0  push    rbx
0x180005ec2  push    r12
0x180005ec4  push    r15
0x180005ec6  sub     rsp, 30h
0x180005eca  mov     r15, [rcx]
0x180005ecd  xor     r12d, r12d
0x180005ed0  mov     [rsp+48h+arg_8], rsi
0x180005ed5  mov     rsi, [r15+4C8h]
0x180005edc  test    rsi, rsi
0x180005edf  jnz     short loc_180005F0E
0x180005ee1  lea     r9, aErrorD; "Error = %d"
0x180005ee8  mov     dword ptr [rsp+48h+Args], 57h ; 'W'; Args
0x180005ef0  mov     r8d, 7Ch ; '|'; int
0x180005ef6  lea     rdx, aWdipdeleteinst; "WdipDeleteInstanceParameters"
0x180005efd  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005f04  call    WdipTraceError
0x180005f09  jmp     loc_180005FDC
0x180005f0e  cmp     [rsi+8], r12
0x180005f12  jz      loc_180005FDC
0x180005f18  mov     ebx, r12d
0x180005f1b  cmp     [rsi+4], ebx
0x180005f1e  jbe     loc_180005FC0
0x180005f24  mov     [rsp+48h+arg_0], rbp
0x180005f29  mov     [rsp+48h+arg_18], r14
0x180005f2e  mov     [rsp+48h+arg_10], rdi
0x180005f33  nop     dword ptr [rax+00h]
0x180005f37  nop     word ptr [rax+rax+00000000h]
0x180005f40  mov     rax, [rsi+8]
0x180005f44  mov     ecx, ebx
0x180005f46  mov     rbp, [rax+rcx*8]
0x180005f4a  lea     r14, [rax+rcx*8]
0x180005f4e  test    rbp, rbp
0x180005f51  jz      short loc_180005FAA
0x180005f53  test    r14, r14
0x180005f56  jz      short loc_180005FAA
0x180005f58  mov     rdi, [rbp+30h]
0x180005f5c  call    cs:__imp_GetProcessHeap
0x180005f62  mov     r8, rdi; lpMem
0x180005f65  xor     edx, edx; dwFlags
0x180005f67  mov     rcx, rax; hHeap
0x180005f6a  call    cs:__imp_HeapFree
0x180005f70  mov     rdi, [rbp+38h]
0x180005f74  mov     [rbp+30h], r12
0x180005f78  call    cs:__imp_GetProcessHeap
0x180005f7e  mov     r8, rdi; lpMem
0x180005f81  xor     edx, edx; dwFlags
0x180005f83  mov     rcx, rax; hHeap
0x180005f86  call    cs:__imp_HeapFree
0x180005f8c  mov     [rbp+38h], r12
0x180005f90  mov     rdi, [r14]
0x180005f93  call    cs:__imp_GetProcessHeap
0x180005f99  mov     r8, rdi; lpMem
0x180005f9c  xor     edx, edx; dwFlags
0x180005f9e  mov     rcx, rax; hHeap
0x180005fa1  call    cs:__imp_HeapFree
0x180005fa7  mov     [r14], r12
0x180005faa  inc     ebx
0x180005fac  cmp     ebx, [rsi+4]
0x180005faf  jb      short loc_180005F40
0x180005fb1  mov     r14, [rsp+48h+arg_18]
0x180005fb6  mov     rdi, [rsp+48h+arg_10]
0x180005fbb  mov     rbp, [rsp+48h+arg_0]
0x180005fc0  mov     rbx, [rsi+8]
0x180005fc4  call    cs:__imp_GetProcessHeap
0x180005fca  mov     r8, rbx; lpMem
0x180005fcd  xor     edx, edx; dwFlags
0x180005fcf  mov     rcx, rax; hHeap
0x180005fd2  call    cs:__imp_HeapFree
0x180005fd8  mov     [rsi+8], r12
0x180005fdc  mov     rcx, [r15+318h]; hObject
0x180005fe3  mov     rsi, [rsp+48h+arg_8]
0x180005fe8  lea     rax, [rcx-1]
0x180005fec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005ff0  ja      short loc_180005FFF
0x180005ff2  call    cs:__imp_CloseHandle
0x180005ff8  mov     [r15+318h], r12
0x180005fff  mov     rcx, [r15+320h]; hObject
0x180006006  lea     rax, [rcx-1]
0x18000600a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000600e  ja      short loc_18000601D
0x180006010  call    cs:__imp_CloseHandle
0x180006016  mov     [r15+320h], r12
0x18000601d  mov     rbx, [r15+310h]
0x180006024  call    cs:__imp_GetProcessHeap
0x18000602a  mov     r8, rbx; lpMem
0x18000602d  xor     edx, edx; dwFlags
0x18000602f  mov     rcx, rax; hHeap
0x180006032  call    cs:__imp_HeapFree
0x180006038  mov     rcx, r15
0x18000603b  mov     [r15+310h], r12
0x180006042  call    DpspFreeSpecificInstanceSID
0x180006047  mov     rbx, [r15+2F0h]
0x18000604e  call    cs:__imp_GetProcessHeap
0x180006054  mov     r8, rbx; lpMem
0x180006057  xor     edx, edx; dwFlags
0x180006059  mov     rcx, rax; hHeap
0x18000605c  call    cs:__imp_HeapFree
0x180006062  mov     [r15+2F0h], r12
0x180006069  mov     [r15+4C0h], r12
0x180006070  mov     [r15+328h], r12
0x180006077  call    cs:__imp_GetProcessHeap
0x18000607d  mov     r8, r15
0x180006080  xor     edx, edx
0x180006082  mov     rcx, rax
0x180006085  add     rsp, 30h
0x180006089  pop     r15
0x18000608b  pop     r12
0x18000608d  pop     rbx
0x18000608e  jmp     cs:__imp_HeapFree
```
