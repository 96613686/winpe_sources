# HandleDiskRequest_GetDiskPath(ulong,void *,ushort * *)

- ea: `0x140018110`
- end: `0x1400181da`
- name: `?HandleDiskRequest_GetDiskPath@@YAHKPEAXPEAPEAG@Z`
- size: `202`
- prototype: `__int64 __fastcall(int, HANDLE hHeap, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400181e0`
- `0x140018288`

## callees

- `0x140018110`
- `0x14001a900`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x140018187`
- `KERNEL32!HeapReAlloc` at `0x140018187`
- `KERNEL32!HeapAlloc` at `0x140018139`
- `KERNEL32!HeapAlloc` at `0x140018139`
- `KERNEL32!HeapFree` at `0x1400181a7`
- `KERNEL32!HeapFree` at `0x1400181a7`
- `KERNEL32!SetLastError` at `0x14001814c`
- `KERNEL32!SetLastError` at `0x1400181b4`
- `KERNEL32!SetLastError` at `0x14001814c`
- `KERNEL32!SetLastError` at `0x1400181b4`
- `KERNEL32!GetLastError` at `0x140018152`
- `KERNEL32!GetLastError` at `0x140018197`
- `KERNEL32!GetLastError` at `0x1400181d0`
- `KERNEL32!GetLastError` at `0x140018152`
- `KERNEL32!GetLastError` at `0x140018197`
- `KERNEL32!GetLastError` at `0x1400181d0`

## pseudocode

```c
__int64 __fastcall HandleDiskRequest_GetDiskPath(int a1, HANDLE hHeap, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbp
  unsigned int DiskPath; // ebx
  DWORD LastError; // edi
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // rsi
  unsigned __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0x8000;
  v6 = (unsigned __int16 *)HeapAlloc(hHeap, 0, 0x10000u);
  v7 = v6;
  if ( v6 )
  {
    DiskPath = GetDiskPath(a1, 0, &v13, v6);
    if ( DiskPath )
    {
      v10 = v13;
      v11 = (unsigned __int16 *)HeapReAlloc(hHeap, 0, v7, 2 * v13);
      if ( v11 )
      {
        v11[v10 - 1] = 0;
        LastError = GetLastError();
        goto LABEL_8;
      }
      DiskPath = 0;
    }
    LastError = GetLastError();
    HeapFree(hHeap, 0, v7);
  }
  else
  {
    DiskPath = 0;
    SetLastError(8u);
    LastError = GetLastError();
  }
  v11 = 0;
LABEL_8:
  *a3 = v11;
  SetLastError(LastError);
  return DiskPath;
}

```

## disassembly

```asm
0x140018110  push    rbx
0x140018112  push    rbp
0x140018113  push    rsi
0x140018114  push    rdi
0x140018115  push    r14
0x140018117  push    r15
0x140018119  sub     rsp, 28h
0x14001811d  mov     r14, rdx
0x140018120  mov     [rsp+58h+arg_18], 8000h
0x140018129  mov     r15, r8
0x14001812c  mov     ebx, ecx
0x14001812e  mov     rcx, r14; hHeap
0x140018131  xor     edx, edx; dwFlags
0x140018133  mov     r8d, 10000h; dwBytes
0x140018139  call    cs:__imp_HeapAlloc
0x14001813f  mov     rbp, rax
0x140018142  test    rax, rax
0x140018145  jnz     short loc_14001815C
0x140018147  lea     ecx, [rax+8]; dwErrCode
0x14001814a  xor     ebx, ebx
0x14001814c  call    cs:__imp_SetLastError
0x140018152  call    cs:__imp_GetLastError
0x140018158  mov     edi, eax
0x14001815a  jmp     short loc_1400181AD
0x14001815c  mov     r9, rbp; unsigned __int16 *
0x14001815f  lea     r8, [rsp+58h+arg_18]; unsigned __int64 *
0x140018164  xor     edx, edx; int
0x140018166  mov     ecx, ebx; unsigned int
0x140018168  call    ?GetDiskPath@@YAHKHPEA_KPEAG@Z; GetDiskPath(ulong,int,unsigned __int64 *,ushort *)
0x14001816d  mov     ebx, eax
0x14001816f  test    eax, eax
0x140018171  jz      short loc_140018197
0x140018173  mov     rax, [rsp+58h+arg_18]
0x140018178  mov     r8, rbp; lpMem
0x14001817b  xor     edx, edx; dwFlags
0x14001817d  mov     rcx, r14; hHeap
0x140018180  lea     rdi, [rax+rax]
0x140018184  mov     r9, rdi; dwBytes
0x140018187  call    cs:__imp_HeapReAlloc
0x14001818d  mov     rsi, rax
0x140018190  test    rax, rax
0x140018193  jnz     short loc_1400181C9
0x140018195  xor     ebx, ebx
0x140018197  call    cs:__imp_GetLastError
0x14001819d  mov     r8, rbp; lpMem
0x1400181a0  xor     edx, edx; dwFlags
0x1400181a2  mov     rcx, r14; hHeap
0x1400181a5  mov     edi, eax
0x1400181a7  call    cs:__imp_HeapFree
0x1400181ad  xor     esi, esi
0x1400181af  mov     ecx, edi; dwErrCode
0x1400181b1  mov     [r15], rsi
0x1400181b4  call    cs:__imp_SetLastError
0x1400181ba  mov     eax, ebx
0x1400181bc  add     rsp, 28h
0x1400181c0  pop     r15
0x1400181c2  pop     r14
0x1400181c4  pop     rdi
0x1400181c5  pop     rsi
0x1400181c6  pop     rbp
0x1400181c7  pop     rbx
0x1400181c8  retn
0x1400181c9  xor     eax, eax
0x1400181cb  mov     [rdi+rsi-2], ax
0x1400181d0  call    cs:__imp_GetLastError
0x1400181d6  mov     edi, eax
0x1400181d8  jmp     short loc_1400181AF
```
