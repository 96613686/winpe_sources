# AbortUninstallVolume_FreeMountPoints

- ea: `0x14001d738`
- end: `0x14001d7b8`
- name: `AbortUninstallVolume_FreeMountPoints`
- size: `128`
- prototype: `__int64 __fastcall(int, LPVOID *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, installer_update`

## callers

- `0x14001d640`
- `0x14001e464`

## callees

- `0x14001d738`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001d769`
- `KERNEL32!HeapFree` at `0x14001d790`
- `KERNEL32!HeapFree` at `0x14001d769`
- `KERNEL32!HeapFree` at `0x14001d790`
- `KERNEL32!GetProcessHeap` at `0x14001d751`
- `KERNEL32!GetProcessHeap` at `0x14001d751`
- `KERNEL32!SetLastError` at `0x14001d7a3`
- `KERNEL32!SetLastError` at `0x14001d7a3`

## pseudocode

```c
__int64 __fastcall AbortUninstallVolume_FreeMountPoints(int a1, LPVOID *a2)
{
  unsigned int v4; // ebx
  DWORD v5; // esi
  LPVOID *v6; // r14
  HANDLE i; // r15
  BOOL v8; // eax
  BOOL v9; // eax

  v4 = 1;
  v5 = 0;
  v6 = a2;
  for ( i = GetProcessHeap(); a1; --a1 )
  {
    v8 = HeapFree(i, 0, *v6);
    if ( v4 )
    {
      v4 = v8;
      v5 = 6;
    }
    ++v6;
  }
  if ( a2 )
  {
    v9 = HeapFree(i, 0, a2);
    if ( v4 )
    {
      v4 = v9;
      v5 = 6;
    }
  }
  SetLastError(v5);
  return v4;
}

```

## disassembly

```asm
0x14001d738  push    rbx
0x14001d73a  push    rbp
0x14001d73b  push    rsi
0x14001d73c  push    rdi
0x14001d73d  push    r14
0x14001d73f  push    r15
0x14001d741  sub     rsp, 28h
0x14001d745  mov     rbp, rdx
0x14001d748  mov     edi, ecx
0x14001d74a  mov     ebx, 1
0x14001d74f  xor     esi, esi
0x14001d751  call    cs:__imp_GetProcessHeap
0x14001d757  mov     r14, rbp
0x14001d75a  mov     r15, rax
0x14001d75d  test    edi, edi
0x14001d75f  jz      short loc_14001D783
0x14001d761  mov     r8, [r14]; lpMem
0x14001d764  xor     edx, edx; dwFlags
0x14001d766  mov     rcx, r15; hHeap
0x14001d769  call    cs:__imp_HeapFree
0x14001d76f  test    ebx, ebx
0x14001d771  jz      short loc_14001D77A
0x14001d773  mov     ebx, eax
0x14001d775  mov     esi, 6
0x14001d77a  add     r14, 8
0x14001d77e  add     edi, 0FFFFFFFFh
0x14001d781  jnz     short loc_14001D761
0x14001d783  test    rbp, rbp
0x14001d786  jz      short loc_14001D7A1
0x14001d788  mov     r8, rbp; lpMem
0x14001d78b  xor     edx, edx; dwFlags
0x14001d78d  mov     rcx, r15; hHeap
0x14001d790  call    cs:__imp_HeapFree
0x14001d796  test    ebx, ebx
0x14001d798  jz      short loc_14001D7A1
0x14001d79a  mov     ebx, eax
0x14001d79c  mov     esi, 6
0x14001d7a1  mov     ecx, esi; dwErrCode
0x14001d7a3  call    cs:__imp_SetLastError
0x14001d7a9  mov     eax, ebx
0x14001d7ab  add     rsp, 28h
0x14001d7af  pop     r15
0x14001d7b1  pop     r14
0x14001d7b3  pop     rdi
0x14001d7b4  pop     rsi
0x14001d7b5  pop     rbp
0x14001d7b6  pop     rbx
0x14001d7b7  retn
```
