# IsDllInProcess(ulong,char *,int *)

- ea: `0x18002e194`
- end: `0x18002e232`
- name: `?IsDllInProcess@@YAJKPEADPEAH@Z`
- size: `158`
- prototype: `__int64 __fastcall(DWORD dwProcessId, char *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002e2d4`

## callees

- `0x18002dee0`
- `0x18002e194`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e21a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e21a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002e1bb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002e1bb`

## pseudocode

```c
signed int __fastcall IsDllInProcess(DWORD dwProcessId, char *a2, int *a3)
{
  HANDLE v5; // rax
  int (*v6)(void *, struct _MODULE_INFO *); // rdx
  void *v7; // rdi
  signed int result; // eax
  unsigned int v9; // ebx
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF

  v10 = 0;
  v5 = OpenProcess(0x410u, 0, dwProcessId);
  v7 = v5;
  if ( v5 )
  {
    *(_QWORD *)&v10 = a2;
    *((_QWORD *)&v10 + 1) = a3;
    *a3 = 0;
    v9 = (unsigned int)EnumModules(v5, v6, &v10) == 0 ? 0x80004005 : 0;
    CloseHandle(v7);
    return v9;
  }
  else if ( GetLastError() == 87 )
  {
    *a3 = 0;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002e194  mov     [rsp+arg_0], rbx
0x18002e199  mov     [rsp+arg_8], rsi
0x18002e19e  push    rdi
0x18002e19f  sub     rsp, 30h
0x18002e1a3  mov     rbx, r8
0x18002e1a6  mov     rsi, rdx
0x18002e1a9  mov     r8d, ecx; dwProcessId
0x18002e1ac  xorps   xmm0, xmm0
0x18002e1af  mov     ecx, 410h; dwDesiredAccess
0x18002e1b4  xor     edx, edx; bInheritHandle
0x18002e1b6  movups  [rsp+38h+var_18], xmm0
0x18002e1bb  call    cs:__imp_OpenProcess
0x18002e1c1  mov     rdi, rax
0x18002e1c4  test    rax, rax
0x18002e1c7  jnz     short loc_18002E1EE
0x18002e1c9  call    cs:__imp_GetLastError
0x18002e1cf  cmp     eax, 57h ; 'W'
0x18002e1d2  jnz     short loc_18002E1DA
0x18002e1d4  mov     [rbx], edi
0x18002e1d6  xor     eax, eax
0x18002e1d8  jmp     short loc_18002E222
0x18002e1da  call    cs:__imp_GetLastError
0x18002e1e0  test    eax, eax
0x18002e1e2  jle     short loc_18002E222
0x18002e1e4  movzx   eax, ax
0x18002e1e7  or      eax, 80070000h
0x18002e1ec  jmp     short loc_18002E222
0x18002e1ee  lea     r8, [rsp+38h+var_18]; void *
0x18002e1f3  mov     qword ptr [rsp+38h+var_18], rsi
0x18002e1f8  mov     rcx, rdi; hProcess
0x18002e1fb  mov     qword ptr [rsp+38h+var_18+8], rbx
0x18002e200  mov     dword ptr [rbx], 0
0x18002e206  call    ?EnumModules@@YAHPEAXP6AH0PEAU_MODULE_INFO@@@Z0@Z; EnumModules(void *,int (*)(void *,_MODULE_INFO *),void *)
0x18002e20b  neg     eax
0x18002e20d  mov     rcx, rdi; hObject
0x18002e210  sbb     ebx, ebx
0x18002e212  not     ebx
0x18002e214  and     ebx, 80004005h
0x18002e21a  call    cs:__imp_CloseHandle
0x18002e220  mov     eax, ebx
0x18002e222  mov     rbx, [rsp+38h+arg_0]
0x18002e227  mov     rsi, [rsp+38h+arg_8]
0x18002e22c  add     rsp, 30h
0x18002e230  pop     rdi
0x18002e231  retn
```
