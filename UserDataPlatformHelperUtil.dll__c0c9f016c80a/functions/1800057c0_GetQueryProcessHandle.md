# GetQueryProcessHandle

- ea: `0x1800057c0`
- end: `0x180005827`
- name: `GetQueryProcessHandle`
- size: `103`
- prototype: `__int64 __fastcall(DWORD dwProcessId, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800057c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005808`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800057d9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800057d9`
- `api-ms-win-coreui-secruntime-l1-1-0!OpenProcessForQuery` at `0x1800057f2`
- `api-ms-win-coreui-secruntime-l1-1-0!OpenProcessForQuery` at `0x1800057f2`

## pseudocode

```c
__int64 __fastcall GetQueryProcessHandle(DWORD dwProcessId, _QWORD *a2)
{
  HANDLE v4; // rax
  int v5; // ebx
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF

  v4 = OpenProcess(0x101000u, 0, dwProcessId);
  if ( v4 )
    goto LABEL_7;
  hObject = 0;
  v5 = OpenProcessForQuery(0, dwProcessId, &hObject);
  if ( v5 >= 0 )
  {
    v4 = hObject;
LABEL_7:
    *a2 = v4;
    return 0;
  }
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800057c0  mov     [rsp+arg_0], rbx
0x1800057c5  push    rdi
0x1800057c6  sub     rsp, 20h
0x1800057ca  mov     rdi, rdx
0x1800057cd  mov     ebx, ecx
0x1800057cf  mov     r8d, ecx; dwProcessId
0x1800057d2  xor     edx, edx; bInheritHandle
0x1800057d4  mov     ecx, 101000h; dwDesiredAccess
0x1800057d9  call    cs:__imp_OpenProcess
0x1800057df  test    rax, rax
0x1800057e2  jnz     short loc_180005817
0x1800057e4  lea     r8, [rsp+28h+hObject]
0x1800057e9  mov     [rsp+28h+hObject], rax
0x1800057ee  mov     edx, ebx
0x1800057f0  xor     ecx, ecx
0x1800057f2  call    cs:__imp_OpenProcessForQuery
0x1800057f8  mov     ebx, eax
0x1800057fa  test    eax, eax
0x1800057fc  jns     short loc_180005812
0x1800057fe  mov     rcx, [rsp+28h+hObject]; hObject
0x180005803  test    rcx, rcx
0x180005806  jz      short loc_18000580E
0x180005808  call    cs:__imp_CloseHandle
0x18000580e  mov     eax, ebx
0x180005810  jmp     short loc_18000581C
0x180005812  mov     rax, [rsp+28h+hObject]
0x180005817  mov     [rdi], rax
0x18000581a  xor     eax, eax
0x18000581c  mov     rbx, [rsp+28h+arg_0]
0x180005821  add     rsp, 20h
0x180005825  pop     rdi
0x180005826  retn
```
