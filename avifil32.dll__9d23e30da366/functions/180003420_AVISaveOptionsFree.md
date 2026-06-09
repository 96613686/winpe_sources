# AVISaveOptionsFree

- ea: `0x180003420`
- end: `0x1800034de`
- name: `AVISaveOptionsFree`
- size: `190`
- prototype: `HRESULT __stdcall(int nStreams, LPAVICOMPRESSOPTIONS *plpOptions)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003420`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003455`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003497`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003455`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003497`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000344c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003464`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000348e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800034a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000344c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003464`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000348e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800034a6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000346d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800034af`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000346d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800034af`

## pseudocode

```c
HRESULT __stdcall AVISaveOptionsFree(int nStreams, LPAVICOMPRESSOPTIONS *plpOptions)
{
  unsigned int i; // ebx
  const void *lpParms; // rcx
  HGLOBAL v5; // rax
  HGLOBAL v6; // rax
  const void *lpFormat; // rcx
  HGLOBAL v8; // rax
  HGLOBAL v9; // rax
  LPAVICOMPRESSOPTIONS v10; // rax

  for ( i = nStreams; (int)i > 0; v10->lpFormat = 0 )
  {
    lpParms = plpOptions[i - 1]->lpParms;
    if ( lpParms )
    {
      v5 = GlobalHandle(lpParms);
      GlobalUnlock(v5);
      v6 = GlobalHandle(plpOptions[i - 1]->lpParms);
      GlobalFree(v6);
    }
    plpOptions[i - 1]->lpParms = 0;
    lpFormat = plpOptions[i - 1]->lpFormat;
    if ( lpFormat )
    {
      v8 = GlobalHandle(lpFormat);
      GlobalUnlock(v8);
      v9 = GlobalHandle(plpOptions[i - 1]->lpFormat);
      GlobalFree(v9);
    }
    v10 = plpOptions[--i];
  }
  return 0;
}

```

## disassembly

```asm
0x180003420  mov     [rsp+arg_0], rbx
0x180003425  mov     [rsp+arg_8], rsi
0x18000342a  push    rdi
0x18000342b  sub     rsp, 20h
0x18000342f  mov     rdi, rdx
0x180003432  mov     ebx, ecx
0x180003434  test    ecx, ecx
0x180003436  jle     loc_1800034CC
0x18000343c  mov     esi, ebx
0x18000343e  mov     rax, [rdi+rsi*8-8]
0x180003443  mov     rcx, [rax+28h]; pMem
0x180003447  test    rcx, rcx
0x18000344a  jz      short loc_180003473
0x18000344c  call    cs:__imp_GlobalHandle
0x180003452  mov     rcx, rax; hMem
0x180003455  call    cs:__imp_GlobalUnlock
0x18000345b  mov     rcx, [rdi+rsi*8-8]
0x180003460  mov     rcx, [rcx+28h]; pMem
0x180003464  call    cs:__imp_GlobalHandle
0x18000346a  mov     rcx, rax; hMem
0x18000346d  call    cs:__imp_GlobalFree
0x180003473  mov     rax, [rdi+rsi*8-8]
0x180003478  mov     qword ptr [rax+28h], 0
0x180003480  mov     rax, [rdi+rsi*8-8]
0x180003485  mov     rcx, [rax+18h]; pMem
0x180003489  test    rcx, rcx
0x18000348c  jz      short loc_1800034B5
0x18000348e  call    cs:__imp_GlobalHandle
0x180003494  mov     rcx, rax; hMem
0x180003497  call    cs:__imp_GlobalUnlock
0x18000349d  mov     rcx, [rdi+rsi*8-8]
0x1800034a2  mov     rcx, [rcx+18h]; pMem
0x1800034a6  call    cs:__imp_GlobalHandle
0x1800034ac  mov     rcx, rax; hMem
0x1800034af  call    cs:__imp_GlobalFree
0x1800034b5  mov     rax, [rdi+rsi*8-8]
0x1800034ba  dec     ebx
0x1800034bc  mov     qword ptr [rax+18h], 0
0x1800034c4  test    ebx, ebx
0x1800034c6  jg      loc_18000343C
0x1800034cc  mov     rbx, [rsp+28h+arg_0]
0x1800034d1  xor     eax, eax
0x1800034d3  mov     rsi, [rsp+28h+arg_8]
0x1800034d8  add     rsp, 20h
0x1800034dc  pop     rdi
0x1800034dd  retn
```
