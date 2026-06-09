# ReadTaskPipe(void *,void *,void *,TASK_PAYLOAD * *)

- ea: `0x1400178d0`
- end: `0x140017a41`
- name: `?ReadTaskPipe@@YAHPEAX00PEAPEAUTASK_PAYLOAD@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE hFile, HANDLE hEvent, struct TASK_PAYLOAD **)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x140017c58`

## callees

- `0x1400178d0`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x140017946`
- `KERNEL32!ResetEvent` at `0x140017946`
- `KERNEL32!ReadFile` at `0x1400179a0`
- `KERNEL32!ReadFile` at `0x1400179a0`
- `KERNEL32!PeekNamedPipe` at `0x140017913`
- `KERNEL32!PeekNamedPipe` at `0x140017913`
- `KERNEL32!HeapAlloc` at `0x140017961`
- `KERNEL32!HeapAlloc` at `0x140017961`
- `KERNEL32!HeapFree` at `0x1400179bf`
- `KERNEL32!HeapFree` at `0x140017a1f`
- `KERNEL32!HeapFree` at `0x1400179bf`
- `KERNEL32!HeapFree` at `0x140017a1f`
- `KERNEL32!SetLastError` at `0x140017974`
- `KERNEL32!SetLastError` at `0x1400179f6`
- `KERNEL32!SetLastError` at `0x140017a2c`
- `KERNEL32!SetLastError` at `0x140017974`
- `KERNEL32!SetLastError` at `0x1400179f6`
- `KERNEL32!SetLastError` at `0x140017a2c`
- `KERNEL32!GetLastError` at `0x14001791f`
- `KERNEL32!GetLastError` at `0x14001797a`
- `KERNEL32!GetLastError` at `0x1400179ac`
- `KERNEL32!GetLastError` at `0x1400179cd`
- `KERNEL32!GetLastError` at `0x1400179fc`
- `KERNEL32!GetLastError` at `0x140017a06`
- `KERNEL32!GetLastError` at `0x14001791f`
- `KERNEL32!GetLastError` at `0x14001797a`
- `KERNEL32!GetLastError` at `0x1400179ac`
- `KERNEL32!GetLastError` at `0x1400179cd`
- `KERNEL32!GetLastError` at `0x1400179fc`
- `KERNEL32!GetLastError` at `0x140017a06`

## pseudocode

```c
__int64 __fastcall ReadTaskPipe(HANDLE hHeap, HANDLE hFile, HANDLE hEvent, struct TASK_PAYLOAD **a4)
{
  _QWORD *v4; // rsi
  unsigned int v9; // ebx
  BOOL v10; // eax
  _QWORD *v11; // rax
  DWORD LastError; // edi
  DWORD v13; // ecx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T dwBytes[8]; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  dwBytes[0] = 0;
  NumberOfBytesRead = 0;
  v9 = PeekNamedPipe(hFile, dwBytes, 8u, &NumberOfBytesRead, 0, 0);
  if ( v9 )
  {
    if ( !NumberOfBytesRead )
    {
      if ( !hEvent )
        goto LABEL_15;
      v10 = ResetEvent(hEvent);
      goto LABEL_14;
    }
    if ( NumberOfBytesRead < 8 )
      goto LABEL_22;
    v11 = HeapAlloc(hHeap, 0, dwBytes[0]);
    v4 = v11;
    if ( !v11 )
    {
      v9 = 0;
      SetLastError(8u);
      goto LABEL_10;
    }
    v9 = ReadFile(hFile, v11, dwBytes[0], &NumberOfBytesRead, 0);
    if ( v9 )
    {
      if ( NumberOfBytesRead >= 8 )
      {
        if ( *v4 == dwBytes[0] )
          goto LABEL_22;
        v13 = 1359;
      }
      else
      {
        v13 = 24;
      }
      v9 = 0;
      SetLastError(v13);
    }
    else if ( GetLastError() == 109 )
    {
      v10 = HeapFree(hHeap, 0, v4);
      v4 = 0;
LABEL_14:
      v9 = v10;
      if ( v10 )
        goto LABEL_15;
LABEL_22:
      LastError = GetLastError();
      if ( v9 )
        goto LABEL_26;
      if ( !v4 )
      {
LABEL_25:
        v4 = 0;
        goto LABEL_26;
      }
LABEL_24:
      HeapFree(hHeap, 0, v4);
      goto LABEL_25;
    }
    LastError = GetLastError();
    goto LABEL_24;
  }
  if ( GetLastError() != 109 )
  {
LABEL_10:
    LastError = GetLastError();
    goto LABEL_25;
  }
  v9 = 1;
LABEL_15:
  LastError = GetLastError();
LABEL_26:
  *a4 = (struct TASK_PAYLOAD *)v4;
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x1400178d0  mov     rax, rsp
0x1400178d3  push    rbx
0x1400178d4  push    rbp
0x1400178d5  push    rsi
0x1400178d6  push    rdi
0x1400178d7  push    r14
0x1400178d9  push    r15
0x1400178db  sub     rsp, 48h
0x1400178df  xor     esi, esi
0x1400178e1  mov     qword ptr [rax-40h], 0
0x1400178e9  mov     r14, rdx
0x1400178ec  mov     [rax-50h], rsi
0x1400178f0  mov     r15, r9
0x1400178f3  mov     dword ptr [rax-48h], 0
0x1400178fa  mov     rdi, r8
0x1400178fd  mov     [rax-58h], rsi
0x140017901  mov     rbp, rcx
0x140017904  lea     r8d, [rsi+8]; nBufferSize
0x140017908  lea     r9, [rax-48h]; lpBytesRead
0x14001790c  mov     rcx, r14; hNamedPipe
0x14001790f  lea     rdx, [rax-40h]; lpBuffer
0x140017913  call    cs:__imp_PeekNamedPipe
0x140017919  mov     ebx, eax
0x14001791b  test    eax, eax
0x14001791d  jnz     short loc_140017932
0x14001791f  call    cs:__imp_GetLastError
0x140017925  cmp     eax, 6Dh ; 'm'
0x140017928  jnz     short loc_14001797A
0x14001792a  lea     ebx, [rsi+1]
0x14001792d  jmp     loc_1400179CD
0x140017932  mov     eax, [rsp+78h+NumberOfBytesRead]
0x140017936  test    eax, eax
0x140017938  jnz     short loc_14001794E
0x14001793a  test    rdi, rdi
0x14001793d  jz      loc_1400179CD
0x140017943  mov     rcx, rdi; hEvent
0x140017946  call    cs:__imp_ResetEvent
0x14001794c  jmp     short loc_1400179C7
0x14001794e  cmp     eax, 8
0x140017951  jb      loc_140017A06
0x140017957  mov     r8, [rsp+78h+dwBytes]; dwBytes
0x14001795c  xor     edx, edx; dwFlags
0x14001795e  mov     rcx, rbp; hHeap
0x140017961  call    cs:__imp_HeapAlloc
0x140017967  mov     rsi, rax
0x14001796a  test    rax, rax
0x14001796d  jnz     short loc_140017987
0x14001796f  xor     ebx, ebx
0x140017971  lea     ecx, [rax+8]; dwErrCode
0x140017974  call    cs:__imp_SetLastError
0x14001797a  call    cs:__imp_GetLastError
0x140017980  mov     edi, eax
0x140017982  jmp     loc_140017A25
0x140017987  mov     r8d, dword ptr [rsp+78h+dwBytes]; nNumberOfBytesToRead
0x14001798c  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140017991  mov     rdx, rsi; lpBuffer
0x140017994  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14001799d  mov     rcx, r14; hFile
0x1400179a0  call    cs:__imp_ReadFile
0x1400179a6  mov     ebx, eax
0x1400179a8  test    eax, eax
0x1400179aa  jnz     short loc_1400179D7
0x1400179ac  call    cs:__imp_GetLastError
0x1400179b2  cmp     eax, 6Dh ; 'm'
0x1400179b5  jnz     short loc_1400179FC
0x1400179b7  mov     r8, rsi; lpMem
0x1400179ba  xor     edx, edx; dwFlags
0x1400179bc  mov     rcx, rbp; hHeap
0x1400179bf  call    cs:__imp_HeapFree
0x1400179c5  xor     esi, esi
0x1400179c7  mov     ebx, eax
0x1400179c9  test    eax, eax
0x1400179cb  jz      short loc_140017A06
0x1400179cd  call    cs:__imp_GetLastError
0x1400179d3  mov     edi, eax
0x1400179d5  jmp     short loc_140017A27
0x1400179d7  cmp     [rsp+78h+NumberOfBytesRead], 8
0x1400179dc  jnb     short loc_1400179E5
0x1400179de  mov     ecx, 18h
0x1400179e3  jmp     short loc_1400179F4
0x1400179e5  mov     rax, [rsp+78h+dwBytes]
0x1400179ea  cmp     [rsi], rax
0x1400179ed  jz      short loc_140017A06
0x1400179ef  mov     ecx, 54Fh; dwErrCode
0x1400179f4  xor     ebx, ebx
0x1400179f6  call    cs:__imp_SetLastError
0x1400179fc  call    cs:__imp_GetLastError
0x140017a02  mov     edi, eax
0x140017a04  jmp     short loc_140017A17
0x140017a06  call    cs:__imp_GetLastError
0x140017a0c  mov     edi, eax
0x140017a0e  test    ebx, ebx
0x140017a10  jnz     short loc_140017A27
0x140017a12  test    rsi, rsi
0x140017a15  jz      short loc_140017A25
0x140017a17  mov     r8, rsi; lpMem
0x140017a1a  xor     edx, edx; dwFlags
0x140017a1c  mov     rcx, rbp; hHeap
0x140017a1f  call    cs:__imp_HeapFree
0x140017a25  xor     esi, esi
0x140017a27  mov     ecx, edi; dwErrCode
0x140017a29  mov     [r15], rsi
0x140017a2c  call    cs:__imp_SetLastError
0x140017a32  mov     eax, ebx
0x140017a34  add     rsp, 48h
0x140017a38  pop     r15
0x140017a3a  pop     r14
0x140017a3c  pop     rdi
0x140017a3d  pop     rsi
0x140017a3e  pop     rbp
0x140017a3f  pop     rbx
0x140017a40  retn
```
