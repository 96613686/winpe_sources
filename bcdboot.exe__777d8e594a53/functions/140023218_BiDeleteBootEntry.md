# BiDeleteBootEntry

- ea: `0x140023218`
- end: `0x1400232bb`
- name: `BiDeleteBootEntry`
- size: `163`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140021f58`
- `0x1400232c4`
- `0x140023714`

## callees

- `0x1400133e4`
- `0x140020678`
- `0x14002166c`
- `0x140021888`
- `0x140023218`
- `0x140027010`

## string_xrefs

- `0x14002324f`: `ZwDeleteBootEntry`
- `0x140023290`: `Failed to delete boot entry 0x%x. Status: %x`

## pseudocode

```c
__int64 __fastcall BiDeleteBootEntry(unsigned int a1)
{
  NTSTATUS v2; // ebx
  int v3; // eax
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  BiLogMessage(2, L"Deleting boot entry 0x%x", a1);
  if ( (int)BiLookupNtdllProcedureAddress("ZwDeleteBootEntry") >= 0 )
  {
    v2 = BiAcquirePrivilege(0x16u, (__int64)&v5);
    if ( v2 >= 0 )
    {
      v3 = MEMORY[0](a1);
      v2 = v3;
      if ( v3 < 0 )
        BiLogMessage(4, L"Failed to delete boot entry 0x%x. Status: %x", a1, (unsigned int)v3);
      BiReleasePrivilege(&v5);
    }
  }
  else
  {
    return (unsigned int)-1073741637;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140023218  mov     [rsp+arg_0], rbx
0x14002321d  push    rdi
0x14002321e  sub     rsp, 20h
0x140023222  mov     edi, ecx
0x140023224  mov     [rsp+28h+arg_8], 0
0x14002322d  mov     r8d, ecx
0x140023230  mov     [rsp+28h+arg_10], 0
0x140023239  mov     ecx, 2
0x14002323e  lea     rdx, aDeletingBootEn; "Deleting boot entry 0x%x"
0x140023245  call    BiLogMessage
0x14002324a  lea     rdx, [rsp+28h+arg_8]
0x14002324f  lea     rcx, aZwdeletebooten; "ZwDeleteBootEntry"
0x140023256  call    BiLookupNtdllProcedureAddress
0x14002325b  test    eax, eax
0x14002325d  jns     short loc_140023266
0x14002325f  mov     ebx, 0C00000BBh
0x140023264  jmp     short loc_1400232AE
0x140023266  lea     rdx, [rsp+28h+arg_10]
0x14002326b  mov     ecx, 16h
0x140023270  call    BiAcquirePrivilege
0x140023275  mov     ebx, eax
0x140023277  test    eax, eax
0x140023279  js      short loc_1400232AE
0x14002327b  mov     rax, [rsp+28h+arg_8]
0x140023280  mov     ecx, edi
0x140023282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023287  mov     ebx, eax
0x140023289  test    eax, eax
0x14002328b  jns     short loc_1400232A4
0x14002328d  mov     r9d, eax
0x140023290  lea     rdx, aFailedToDelete_0; "Failed to delete boot entry 0x%x. Statu"...
0x140023297  mov     r8d, edi
0x14002329a  mov     ecx, 4
0x14002329f  call    BiLogMessage
0x1400232a4  lea     rcx, [rsp+28h+arg_10]
0x1400232a9  call    BiReleasePrivilege
0x1400232ae  mov     eax, ebx
0x1400232b0  mov     rbx, [rsp+28h+arg_0]
0x1400232b5  add     rsp, 20h
0x1400232b9  pop     rdi
0x1400232ba  retn
```
