# AllocateMemory

- ea: `0x180004390`
- end: `0x180004492`
- name: `AllocateMemory`
- size: `258`
- prototype: `__int64 __fastcall(SIZE_T dwBytes, _QWORD *, int, char)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180002f80`
- `0x180003710`
- `0x180003800`
- `0x180004260`
- `0x180004db0`
- `0x18000b894`
- `0x18000c6f0`
- `0x18000cca0`
- `0x18000cd80`
- `0x18000cf08`
- `0x18000d3d0`

## callees

- `0x180004390`
- `0x180004cb0`
- `0x18000b774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004400`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800043c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800043c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043aa`

## pseudocode

```c
__int64 __fastcall AllocateMemory(SIZE_T dwBytes, _QWORD *a2, int a3, char a4)
{
  SIZE_T v5; // rbp
  unsigned int v8; // edi
  HANDLE ProcessHeap; // rbx
  LPVOID v10; // rax
  int v11; // r8d
  LPVOID v12; // rbx
  DWORD LastError; // eax
  int v15; // r8d

  v5 = (unsigned int)dwBytes;
  v8 = 0;
  ProcessHeap = GetProcessHeap();
  if ( ProcessHeap || (LastError = GetLastError(), (v8 = LastError) == 0) )
  {
    v10 = HeapAlloc(ProcessHeap, 8u, v5);
    v12 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v11, a3, a4, (char)v10, v5);
    }
    else
    {
      v8 = 14;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v11, a3, a4, v5);
    }
  }
  else
  {
    v12 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v15, a3, a4, LastError);
  }
  *a2 = v12;
  return v8;
}

```

## disassembly

```asm
0x180004390  push    rbx
0x180004392  push    rbp
0x180004393  push    rsi
0x180004394  push    rdi
0x180004395  push    r14
0x180004397  push    r15
0x180004399  sub     rsp, 48h
0x18000439d  mov     r14d, r9d
0x1800043a0  mov     ebp, ecx
0x1800043a2  mov     r15, r8
0x1800043a5  mov     rsi, rdx
0x1800043a8  xor     edi, edi
0x1800043aa  call    cs:__imp_GetProcessHeap
0x1800043b0  mov     rbx, rax
0x1800043b3  test    rax, rax
0x1800043b6  jz      short loc_180004400
0x1800043b8  mov     r8, rbp; dwBytes
0x1800043bb  mov     edx, 8; dwFlags
0x1800043c0  mov     rcx, rbx; hHeap
0x1800043c3  call    cs:__imp_HeapAlloc
0x1800043c9  mov     rbx, rax
0x1800043cc  test    rax, rax
0x1800043cf  jz      short loc_18000444E
0x1800043d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043d8  lea     rdx, WPP_GLOBAL_Control
0x1800043df  cmp     rcx, rdx
0x1800043e2  jz      short loc_1800043EE
0x1800043e4  test    byte ptr [rcx+1Ch], 2
0x1800043e8  jnz     loc_18000446E
0x1800043ee  mov     [rsi], rbx
0x1800043f1  mov     eax, edi
0x1800043f3  add     rsp, 48h
0x1800043f7  pop     r15
0x1800043f9  pop     r14
0x1800043fb  pop     rdi
0x1800043fc  pop     rsi
0x1800043fd  pop     rbp
0x1800043fe  pop     rbx
0x1800043ff  retn
0x180004400  call    cs:__imp_GetLastError
0x180004406  mov     edi, eax
0x180004408  test    eax, eax
0x18000440a  jz      short loc_1800043B8
0x18000440c  xor     ebx, ebx
0x18000440e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004415  lea     rdx, WPP_GLOBAL_Control
0x18000441c  cmp     rcx, rdx
0x18000441f  jz      short loc_1800043EE
0x180004421  test    byte ptr [rcx+1Ch], 4
0x180004425  jz      short loc_1800043EE
0x180004427  mov     edx, 0Ah
0x18000442c  mov     dword ptr [rsp+78h+var_50], eax
0x180004430  jmp     short loc_18000443B
0x180004432  mov     edx, 0Bh
0x180004437  mov     dword ptr [rsp+78h+var_50], ebp
0x18000443b  mov     rcx, [rcx+10h]
0x18000443f  mov     r9, r15
0x180004442  mov     [rsp+78h+var_58], r14d
0x180004447  call    WPP_SF_sdd
0x18000444c  jmp     short loc_1800043EE
0x18000444e  mov     edi, 0Eh
0x180004453  mov     rcx, cs:WPP_GLOBAL_Control
0x18000445a  lea     rdx, WPP_GLOBAL_Control
0x180004461  cmp     rcx, rdx
0x180004464  jz      short loc_1800043EE
0x180004466  test    byte ptr [rcx+1Ch], 4
0x18000446a  jz      short loc_1800043EE
0x18000446c  jmp     short loc_180004432
0x18000446e  mov     rcx, [rcx+10h]
0x180004472  mov     edx, 0Ch
0x180004477  mov     [rsp+78h+var_48], ebp
0x18000447b  mov     r9, r15
0x18000447e  mov     [rsp+78h+var_50], rax
0x180004483  mov     [rsp+78h+var_58], r14d
0x180004488  call    WPP_SF_sdqd
0x18000448d  jmp     loc_1800043EE
```
