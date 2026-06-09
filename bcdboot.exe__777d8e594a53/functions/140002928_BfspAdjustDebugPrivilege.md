# BfspAdjustDebugPrivilege

- ea: `0x140002928`
- end: `0x14000299f`
- name: `BfspAdjustDebugPrivilege`
- size: `119`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140003368`

## callees

- `0x140002928`
- `0x14000e79c`
- `0x14000e950`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000298c`
- `KERNEL32!HeapFree` at `0x14000298c`
- `KERNEL32!GetProcessHeap` at `0x14000297c`
- `KERNEL32!GetProcessHeap` at `0x14000297c`

## string_xrefs

- `0x14000293f`: `SeDebugPrivilege`

## pseudocode

```c
__int64 __fastcall BfspAdjustDebugPrivilege(unsigned int a1)
{
  unsigned int v1; // edi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+18h] BYREF
  const wchar_t *v5; // [rsp+48h] [rbp+20h] BYREF

  lpMem = 0;
  v5 = L"SeDebugPrivilege";
  v1 = BfspCreateTokenPrivilegesInformation(&v5, 1, a1, &lpMem);
  if ( v1 )
    v1 = BfspAdjustTokenPrivileges((PTOKEN_PRIVILEGES)lpMem);
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return v1;
}

```

## disassembly

```asm
0x140002928  mov     r11, rsp
0x14000292b  mov     [r11+8], rsi
0x14000292f  push    rdi
0x140002930  sub     rsp, 20h
0x140002934  mov     rsi, rdx
0x140002937  mov     qword ptr [r11+18h], 0
0x14000293f  lea     rax, aSedebugprivile; "SeDebugPrivilege"
0x140002946  mov     r8d, ecx
0x140002949  mov     edx, 1
0x14000294e  mov     [r11+20h], rax
0x140002952  lea     rcx, [r11+20h]
0x140002956  lea     r9, [r11+18h]
0x14000295a  call    BfspCreateTokenPrivilegesInformation
0x14000295f  mov     edi, eax
0x140002961  test    eax, eax
0x140002963  jz      short loc_140002974
0x140002965  mov     rcx, [rsp+28h+lpMem]; NewState
0x14000296a  mov     rdx, rsi
0x14000296d  call    BfspAdjustTokenPrivileges
0x140002972  mov     edi, eax
0x140002974  cmp     [rsp+28h+lpMem], 0
0x14000297a  jz      short loc_140002992
0x14000297c  call    cs:__imp_GetProcessHeap
0x140002982  mov     r8, [rsp+28h+lpMem]; lpMem
0x140002987  xor     edx, edx; dwFlags
0x140002989  mov     rcx, rax; hHeap
0x14000298c  call    cs:__imp_HeapFree
0x140002992  mov     rsi, [rsp+28h+arg_0]
0x140002997  mov     eax, edi
0x140002999  add     rsp, 20h
0x14000299d  pop     rdi
0x14000299e  retn
```
