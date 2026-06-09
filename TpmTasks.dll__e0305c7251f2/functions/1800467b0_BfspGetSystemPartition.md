# BfspGetSystemPartition

- ea: `0x1800467b0`
- end: `0x180046954`
- name: `BfspGetSystemPartition`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180046a3c`
- `0x180046ec0`
- `0x180048f2c`
- `0x18004aec4`
- `0x18004f970`

## callees

- `0x1800085bc`
- `0x1800467b0`
- `0x18004cdd4`
- `0x180052938`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180046867`
- `ntdll!RtlNtStatusToDosError` at `0x180046867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046846`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004685f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046946`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046846`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004685f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046946`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800467fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046838`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046851`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800468d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046938`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800467fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046838`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046851`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800468d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046938`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004680c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800468e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004680c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800468e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004686f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004686f`
- `bcd!SyspartGetSystemPartition` at `0x1800468ad`
- `bcd!SyspartGetSystemPartition` at `0x180046904`
- `bcd!SyspartGetSystemPartition` at `0x1800468ad`
- `bcd!SyspartGetSystemPartition` at `0x180046904`

## pseudocode

```c
wchar_t *__fastcall BfspGetSystemPartition(char a1)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  HANDLE v4; // rax
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  NTSTATUS v7; // edi
  HANDLE v8; // rax
  ULONG v9; // eax
  int SystemPartition; // eax
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v14; // rax
  __int64 v15; // rsi
  HANDLE v16; // rax
  size_t Size; // [rsp+48h] [rbp+10h] BYREF

  LODWORD(Size) = 0;
  if ( !BfspSystemPartitionName )
  {
    SystemPartition = SyspartGetSystemPartition(0, 0, &Size);
    v7 = SystemPartition;
    if ( SystemPartition != -1073741789 )
    {
      v6 = 0;
      if ( SystemPartition >= 0 )
        v7 = -1073741823;
      goto LABEL_6;
    }
    v12 = Size;
    ProcessHeap = GetProcessHeap();
    v14 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v12);
    v6 = v14;
    if ( !v14 )
      goto LABEL_5;
    v7 = SyspartGetSystemPartition(v14, (unsigned int)Size, &Size);
    if ( v7 < 0 )
      goto LABEL_6;
    goto LABEL_16;
  }
  v2 = -1;
  do
    ++v2;
  while ( *((_WORD *)BfspSystemPartitionName + v2) );
  LODWORD(Size) = 2 * v2 + 2;
  v3 = Size;
  v4 = GetProcessHeap();
  v5 = (wchar_t *)HeapAlloc(v4, 8u, v3);
  v6 = v5;
  if ( v5 )
  {
    memcpy_0(v5, BfspSystemPartitionName, (unsigned int)Size);
LABEL_16:
    if ( !a1 )
      return v6;
    v15 = BuildPath(L"\\\\?\\GLOBALROOT", v6);
    if ( v15 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v6);
      return (wchar_t *)v15;
    }
  }
LABEL_5:
  v7 = -1073741670;
LABEL_6:
  BfspLogMessage(4, L"Failed to get partition name. Status = %#x", (unsigned int)v7);
  if ( v6 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v6);
  }
  v9 = RtlNtStatusToDosError(v7);
  SetLastError(v9);
  return 0;
}

```

## disassembly

```asm
0x1800467b0  mov     [rsp+arg_0], rbx
0x1800467b5  mov     [rsp+arg_10], rbp
0x1800467ba  push    rsi
0x1800467bb  push    rdi
0x1800467bc  push    r14
0x1800467be  sub     rsp, 20h
0x1800467c2  mov     rdx, cs:BfspSystemPartitionName
0x1800467c9  xor     r14d, r14d
0x1800467cc  mov     dword ptr [rsp+38h+Size], r14d
0x1800467d1  mov     bpl, cl
0x1800467d4  mov     esi, r14d
0x1800467d7  test    rdx, rdx
0x1800467da  jz      loc_1800468A4
0x1800467e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800467e4  inc     rax
0x1800467e7  cmp     [rdx+rax*2], r14w
0x1800467ec  jnz     short loc_1800467E4
0x1800467ee  lea     eax, ds:2[rax*2]
0x1800467f5  mov     dword ptr [rsp+38h+Size], eax
0x1800467f9  mov     ebx, eax
0x1800467fb  call    cs:__imp_GetProcessHeap
0x180046801  mov     r8d, ebx; dwBytes
0x180046804  mov     edx, 8; dwFlags
0x180046809  mov     rcx, rax; hHeap
0x18004680c  call    cs:__imp_HeapAlloc
0x180046812  mov     rbx, rax
0x180046815  test    rax, rax
0x180046818  jnz     short loc_18004688E
0x18004681a  mov     edi, 0C000009Ah
0x18004681f  mov     r8d, edi
0x180046822  lea     rdx, aFailedToGetPar; "Failed to get partition name. Status = "...
0x180046829  mov     ecx, 4
0x18004682e  call    BfspLogMessage
0x180046833  test    rsi, rsi
0x180046836  jz      short loc_18004684C
0x180046838  call    cs:__imp_GetProcessHeap
0x18004683e  mov     r8, rsi; lpMem
0x180046841  xor     edx, edx; dwFlags
0x180046843  mov     rcx, rax; hHeap
0x180046846  call    cs:__imp_HeapFree
0x18004684c  test    rbx, rbx
0x18004684f  jz      short loc_180046865
0x180046851  call    cs:__imp_GetProcessHeap
0x180046857  mov     r8, rbx; lpMem
0x18004685a  xor     edx, edx; dwFlags
0x18004685c  mov     rcx, rax; hHeap
0x18004685f  call    cs:__imp_HeapFree
0x180046865  mov     ecx, edi; Status
0x180046867  call    cs:__imp_RtlNtStatusToDosError
0x18004686d  mov     ecx, eax; dwErrCode
0x18004686f  call    cs:__imp_SetLastError
0x180046875  mov     rbx, r14
0x180046878  mov     rbp, [rsp+38h+arg_10]
0x18004687d  mov     rax, rbx
0x180046880  mov     rbx, [rsp+38h+arg_0]
0x180046885  add     rsp, 20h
0x180046889  pop     r14
0x18004688b  pop     rdi
0x18004688c  pop     rsi
0x18004688d  retn
0x18004688e  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x180046893  mov     rcx, rax; void *
0x180046896  mov     rdx, cs:BfspSystemPartitionName; Src
0x18004689d  call    memcpy_0
0x1800468a2  jmp     short loc_180046914
0x1800468a4  lea     r8, [rsp+38h+Size]
0x1800468a9  xor     edx, edx
0x1800468ab  xor     ecx, ecx
0x1800468ad  call    cs:__imp_SyspartGetSystemPartition
0x1800468b3  mov     edi, eax
0x1800468b5  cmp     eax, 0C0000023h
0x1800468ba  jz      short loc_1800468D1
0x1800468bc  mov     rbx, r14
0x1800468bf  test    eax, eax
0x1800468c1  js      loc_18004681F
0x1800468c7  mov     edi, 0C0000001h
0x1800468cc  jmp     loc_18004681F
0x1800468d1  mov     ebx, dword ptr [rsp+38h+Size]
0x1800468d5  call    cs:__imp_GetProcessHeap
0x1800468db  mov     r8d, ebx; dwBytes
0x1800468de  mov     edx, 8; dwFlags
0x1800468e3  mov     rcx, rax; hHeap
0x1800468e6  call    cs:__imp_HeapAlloc
0x1800468ec  mov     rbx, rax
0x1800468ef  test    rax, rax
0x1800468f2  jz      loc_18004681A
0x1800468f8  mov     edx, dword ptr [rsp+38h+Size]
0x1800468fc  lea     r8, [rsp+38h+Size]
0x180046901  mov     rcx, rax
0x180046904  call    cs:__imp_SyspartGetSystemPartition
0x18004690a  mov     edi, eax
0x18004690c  test    eax, eax
0x18004690e  js      loc_18004681F
0x180046914  test    bpl, bpl
0x180046917  jz      loc_180046878
0x18004691d  mov     rdx, rbx; STRSAFE_PCNZWCH
0x180046920  lea     rcx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180046927  call    BuildPath
0x18004692c  mov     rsi, rax
0x18004692f  test    rax, rax
0x180046932  jz      loc_18004681A
0x180046938  call    cs:__imp_GetProcessHeap
0x18004693e  mov     r8, rbx; lpMem
0x180046941  xor     edx, edx; dwFlags
0x180046943  mov     rcx, rax; hHeap
0x180046946  call    cs:__imp_HeapFree
0x18004694c  mov     rbx, rsi
0x18004694f  jmp     loc_180046878
```
