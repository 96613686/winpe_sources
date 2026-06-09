# StartAddress

- ea: `0x180156ba0`
- end: `0x180156c10`
- name: `StartAddress`
- size: `112`
- prototype: `void __fastcall __noreturn(_BYTE *Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180156ba0`
- `0x180156db4`
- `0x180158714`
- `0x1801599a4`
- `0x18015ebb4`
- `0x18016159c`
- `0x18018f7c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180156bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180156bae`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180156bb6`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180156bb6`

## pseudocode

```c
void __fastcall __noreturn StartAddress(_BYTE *Parameter)
{
  DWORD LastError; // eax
  unsigned int v3; // eax

  if ( !Parameter )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  *(_QWORD *)(sub_1801599A4() + 960) = Parameter;
  if ( (unsigned int)sub_18016159C() == 2 )
    Parameter[32] = (unsigned int)sub_18015EBB4(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))Parameter)(*((_QWORD *)Parameter + 1));
  sub_180156DB4(v3);
}

```

## disassembly

```asm
0x180156ba0  push    rbx
0x180156ba2  sub     rsp, 20h
0x180156ba6  mov     rbx, rcx
0x180156ba9  test    rcx, rcx
0x180156bac  jnz     short loc_180156BBD
0x180156bae  call    cs:__imp_GetLastError
0x180156bb4  mov     ecx, eax; dwExitCode
0x180156bb6  call    cs:ExitThread
0x180156bbd  call    sub_1801599A4
0x180156bc2  mov     [rax+3C0h], rbx
0x180156bc9  call    sub_18016159C
0x180156bce  cmp     eax, 2
0x180156bd1  jnz     short loc_180156BE3
0x180156bd3  lea     ecx, [rax-1]
0x180156bd6  call    sub_18015EBB4
0x180156bdb  test    eax, eax
0x180156bdd  setz    al
0x180156be0  mov     [rbx+20h], al
0x180156be3  mov     r10, 9E0C2E5B32D12870h
0x180156bed  mov     rcx, [rbx+8]
0x180156bf1  mov     rax, [rbx]
0x180156bf4  call    cs:__guard_xfg_dispatch_icall_fptr
0x180156bfa  mov     ecx, eax
0x180156bfc  call    sub_180156DB4
0x180156c02  mov     ecx, eax
0x180156c04  call    sub_180158714
0x180156c09  nop
0x180156c0a  add     rsp, 20h
0x180156c0e  pop     rbx
0x180156c0f  retn
```
