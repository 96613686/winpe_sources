# FormLongPathName

- ea: `0x140022594`
- end: `0x1400226f2`
- name: `FormLongPathName`
- size: `350`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140023dcc`
- `0x140026104`
- `0x14002840c`

## callees

- `0x140022594`
- `0x140022c14`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14002269c`
- `KERNEL32!HeapFree` at `0x14002269c`
- `KERNEL32!HeapAlloc` at `0x14002260a`
- `KERNEL32!HeapAlloc` at `0x14002260a`
- `KERNEL32!GetProcessHeap` at `0x1400225f4`
- `KERNEL32!GetProcessHeap` at `0x140022688`
- `KERNEL32!GetProcessHeap` at `0x1400225f4`
- `KERNEL32!GetProcessHeap` at `0x140022688`
- `KERNEL32!GetLongPathNameW` at `0x1400225dd`
- `KERNEL32!GetLongPathNameW` at `0x140022627`
- `KERNEL32!GetLongPathNameW` at `0x1400225dd`
- `KERNEL32!GetLongPathNameW` at `0x140022627`
- `KERNEL32!GetLastError` at `0x140022637`
- `KERNEL32!GetLastError` at `0x140022659`
- `KERNEL32!GetLastError` at `0x1400226aa`
- `KERNEL32!GetLastError` at `0x140022637`
- `KERNEL32!GetLastError` at `0x140022659`
- `KERNEL32!GetLastError` at `0x1400226aa`
- `KERNEL32!SetLastError` at `0x1400226ba`
- `KERNEL32!SetLastError` at `0x1400226d0`
- `KERNEL32!SetLastError` at `0x1400226ba`
- `KERNEL32!SetLastError` at `0x1400226d0`

## pseudocode

```c
void *__fastcall FormLongPathName(unsigned __int16 *a1)
{
  void *v1; // rbx
  DWORD v2; // esi
  const WCHAR *v3; // rax
  const WCHAR *v4; // rdi
  DWORD LongPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v7; // rax
  void *v8; // rax
  void *v9; // rcx
  WCHAR *v10; // rbp
  DWORD LastError; // edi
  HANDLE v12; // rax

  v1 = 0;
  v2 = 0;
  if ( a1 && *a1 )
  {
    v3 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v4 = v3;
    if ( !v3 )
    {
      LastError = GetLastError();
LABEL_20:
      SetLastError(LastError);
      return v1;
    }
    LongPathNameW = GetLongPathNameW(v3, 0, 0);
    if ( LongPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v7 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * LongPathNameW);
      v1 = v7;
      if ( v7 )
      {
        if ( !GetLongPathNameW(v4, v7, LongPathNameW) )
          v2 = GetLastError();
      }
      else
      {
        v2 = 14;
      }
      v8 = v1;
      v9 = v1;
      if ( v1 )
        goto LABEL_13;
    }
    else
    {
      v2 = GetLastError();
      v9 = 0;
      v8 = 0;
    }
    v1 = (void *)v4;
LABEL_13:
    v10 = 0;
    if ( v9 )
      v10 = (WCHAR *)v4;
    LastError = 0;
    if ( v8 )
      LastError = v2;
    if ( v10 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v10);
    }
    goto LABEL_20;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x140022594  mov     [rsp+arg_8], rbx
0x140022599  mov     [rsp+arg_10], rbp
0x14002259e  push    rsi
0x14002259f  push    rdi
0x1400225a0  push    r14
0x1400225a2  sub     rsp, 20h
0x1400225a6  xor     r14d, r14d
0x1400225a9  mov     ebx, r14d
0x1400225ac  mov     esi, r14d
0x1400225af  test    rcx, rcx
0x1400225b2  jz      loc_1400226CB
0x1400225b8  cmp     r14w, [rcx]
0x1400225bc  jz      loc_1400226CB
0x1400225c2  xor     edx, edx
0x1400225c4  call    PrepareUnicodePathEx
0x1400225c9  mov     rdi, rax
0x1400225cc  test    rax, rax
0x1400225cf  jz      loc_1400226AA
0x1400225d5  xor     r8d, r8d; cchBuffer
0x1400225d8  xor     edx, edx; lpszLongPath
0x1400225da  mov     rcx, rax; lpszShortPath
0x1400225dd  call    cs:__imp_GetLongPathNameW
0x1400225e4  nop     dword ptr [rax+rax+00h]
0x1400225e9  mov     ebp, eax
0x1400225eb  test    eax, eax
0x1400225ed  jz      short loc_140022659
0x1400225ef  mov     ebx, ebp
0x1400225f1  add     rbx, rbx
0x1400225f4  call    cs:__imp_GetProcessHeap
0x1400225fb  nop     dword ptr [rax+rax+00h]
0x140022600  mov     r8, rbx; dwBytes
0x140022603  lea     edx, [r14+8]; dwFlags
0x140022607  mov     rcx, rax; hHeap
0x14002260a  call    cs:__imp_HeapAlloc
0x140022611  nop     dword ptr [rax+rax+00h]
0x140022616  mov     rbx, rax
0x140022619  test    rax, rax
0x14002261c  jz      short loc_140022647
0x14002261e  mov     r8d, ebp; cchBuffer
0x140022621  mov     rdx, rax; lpszLongPath
0x140022624  mov     rcx, rdi; lpszShortPath
0x140022627  call    cs:__imp_GetLongPathNameW
0x14002262e  nop     dword ptr [rax+rax+00h]
0x140022633  test    eax, eax
0x140022635  jnz     short loc_14002264C
0x140022637  call    cs:__imp_GetLastError
0x14002263e  nop     dword ptr [rax+rax+00h]
0x140022643  mov     esi, eax
0x140022645  jmp     short loc_14002264C
0x140022647  mov     esi, 0Eh
0x14002264c  mov     rax, rbx
0x14002264f  mov     rcx, rbx
0x140022652  test    rbx, rbx
0x140022655  jnz     short loc_140022670
0x140022657  jmp     short loc_14002266D
0x140022659  call    cs:__imp_GetLastError
0x140022660  nop     dword ptr [rax+rax+00h]
0x140022665  mov     esi, eax
0x140022667  mov     rcx, r14
0x14002266a  mov     rax, r14
0x14002266d  mov     rbx, rdi
0x140022670  test    rcx, rcx
0x140022673  mov     rbp, r14
0x140022676  cmovnz  rbp, rdi
0x14002267a  test    rax, rax
0x14002267d  mov     edi, r14d
0x140022680  cmovnz  edi, esi
0x140022683  test    rbp, rbp
0x140022686  jz      short loc_1400226B8
0x140022688  call    cs:__imp_GetProcessHeap
0x14002268f  nop     dword ptr [rax+rax+00h]
0x140022694  mov     r8, rbp; lpMem
0x140022697  xor     edx, edx; dwFlags
0x140022699  mov     rcx, rax; hHeap
0x14002269c  call    cs:__imp_HeapFree
0x1400226a3  nop     dword ptr [rax+rax+00h]
0x1400226a8  jmp     short loc_1400226B8
0x1400226aa  call    cs:__imp_GetLastError
0x1400226b1  nop     dword ptr [rax+rax+00h]
0x1400226b6  mov     edi, eax
0x1400226b8  mov     ecx, edi; dwErrCode
0x1400226ba  call    cs:__imp_SetLastError
0x1400226c1  nop     dword ptr [rax+rax+00h]
0x1400226c6  mov     rax, rbx
0x1400226c9  jmp     short loc_1400226DE
0x1400226cb  mov     ecx, 57h ; 'W'; dwErrCode
0x1400226d0  call    cs:__imp_SetLastError
0x1400226d7  nop     dword ptr [rax+rax+00h]
0x1400226dc  xor     eax, eax
0x1400226de  mov     rbx, [rsp+38h+arg_8]
0x1400226e3  mov     rbp, [rsp+38h+arg_10]
0x1400226e8  add     rsp, 20h
0x1400226ec  pop     r14
0x1400226ee  pop     rdi
0x1400226ef  pop     rsi
0x1400226f0  retn
```
