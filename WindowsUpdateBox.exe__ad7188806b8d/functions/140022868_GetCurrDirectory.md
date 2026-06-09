# GetCurrDirectory

- ea: `0x140022868`
- end: `0x140022959`
- name: `GetCurrDirectory`
- size: `241`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140025f90`

## callees

- `0x140022868`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140022904`
- `KERNEL32!HeapFree` at `0x140022904`
- `KERNEL32!HeapAlloc` at `0x1400228af`
- `KERNEL32!HeapAlloc` at `0x1400228af`
- `KERNEL32!GetProcessHeap` at `0x14002289a`
- `KERNEL32!GetProcessHeap` at `0x1400228f0`
- `KERNEL32!GetProcessHeap` at `0x14002289a`
- `KERNEL32!GetProcessHeap` at `0x1400228f0`
- `KERNEL32!GetCurrentDirectoryW` at `0x14002287f`
- `KERNEL32!GetCurrentDirectoryW` at `0x1400228c8`
- `KERNEL32!GetCurrentDirectoryW` at `0x14002287f`
- `KERNEL32!GetCurrentDirectoryW` at `0x1400228c8`
- `KERNEL32!GetLastError` at `0x1400228d8`
- `KERNEL32!GetLastError` at `0x14002291f`
- `KERNEL32!GetLastError` at `0x1400228d8`
- `KERNEL32!GetLastError` at `0x14002291f`
- `KERNEL32!SetLastError` at `0x140022939`
- `KERNEL32!SetLastError` at `0x140022939`

## pseudocode

```c
WCHAR *GetCurrDirectory()
{
  WCHAR *v0; // rbx
  DWORD LastError; // edi
  DWORD CurrentDirectoryW; // esi
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  HANDLE v5; // rax

  v0 = 0;
  LastError = 0;
  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  if ( CurrentDirectoryW )
  {
    ProcessHeap = GetProcessHeap();
    v4 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * CurrentDirectoryW);
    v0 = v4;
    if ( v4 )
    {
      if ( !GetCurrentDirectoryW(CurrentDirectoryW, v4) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 31;
        v5 = GetProcessHeap();
        if ( HeapFree(v5, 0, v0) )
          v0 = 0;
      }
    }
    else
    {
      LastError = 14;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 31;
  }
  SetLastError(LastError);
  return v0;
}

```

## disassembly

```asm
0x140022868  mov     [rsp+arg_0], rbx
0x14002286d  mov     [rsp+arg_8], rsi
0x140022872  push    rdi
0x140022873  sub     rsp, 20h
0x140022877  xor     edx, edx; lpBuffer
0x140022879  xor     ecx, ecx; nBufferLength
0x14002287b  xor     ebx, ebx
0x14002287d  xor     edi, edi
0x14002287f  call    cs:__imp_GetCurrentDirectoryW
0x140022886  nop     dword ptr [rax+rax+00h]
0x14002288b  mov     esi, eax
0x14002288d  test    eax, eax
0x14002288f  jz      loc_14002291F
0x140022895  mov     ebx, esi
0x140022897  add     rbx, rbx
0x14002289a  call    cs:__imp_GetProcessHeap
0x1400228a1  nop     dword ptr [rax+rax+00h]
0x1400228a6  mov     r8, rbx; dwBytes
0x1400228a9  lea     edx, [rdi+8]; dwFlags
0x1400228ac  mov     rcx, rax; hHeap
0x1400228af  call    cs:__imp_HeapAlloc
0x1400228b6  nop     dword ptr [rax+rax+00h]
0x1400228bb  mov     rbx, rax
0x1400228be  test    rax, rax
0x1400228c1  jz      short loc_140022918
0x1400228c3  mov     rdx, rax; lpBuffer
0x1400228c6  mov     ecx, esi; nBufferLength
0x1400228c8  call    cs:__imp_GetCurrentDirectoryW
0x1400228cf  nop     dword ptr [rax+rax+00h]
0x1400228d4  test    eax, eax
0x1400228d6  jnz     short loc_140022937
0x1400228d8  call    cs:__imp_GetLastError
0x1400228df  nop     dword ptr [rax+rax+00h]
0x1400228e4  mov     edi, eax
0x1400228e6  mov     eax, 1Fh
0x1400228eb  test    edi, edi
0x1400228ed  cmovz   edi, eax
0x1400228f0  call    cs:__imp_GetProcessHeap
0x1400228f7  nop     dword ptr [rax+rax+00h]
0x1400228fc  mov     r8, rbx; lpMem
0x1400228ff  xor     edx, edx; dwFlags
0x140022901  mov     rcx, rax; hHeap
0x140022904  call    cs:__imp_HeapFree
0x14002290b  nop     dword ptr [rax+rax+00h]
0x140022910  test    eax, eax
0x140022912  jz      short loc_140022937
0x140022914  xor     ebx, ebx
0x140022916  jmp     short loc_140022937
0x140022918  mov     edi, 0Eh
0x14002291d  jmp     short loc_140022937
0x14002291f  call    cs:__imp_GetLastError
0x140022926  nop     dword ptr [rax+rax+00h]
0x14002292b  mov     edi, eax
0x14002292d  mov     eax, 1Fh
0x140022932  test    edi, edi
0x140022934  cmovz   edi, eax
0x140022937  mov     ecx, edi; dwErrCode
0x140022939  call    cs:__imp_SetLastError
0x140022940  nop     dword ptr [rax+rax+00h]
0x140022945  mov     rsi, [rsp+28h+arg_8]
0x14002294a  mov     rax, rbx
0x14002294d  mov     rbx, [rsp+28h+arg_0]
0x140022952  add     rsp, 20h
0x140022956  pop     rdi
0x140022957  retn
```
