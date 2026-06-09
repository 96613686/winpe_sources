# RedirectionContextSetupAsynchIO(_REDIRECTION_CONTEXT *,void (*)(_REDIRECTION_CONTEXT *))

- ea: `0x180020d68`
- end: `0x180020db0`
- name: `?RedirectionContextSetupAsynchIO@@YAJPEAU_REDIRECTION_CONTEXT@@P6AX0@Z@Z`
- size: `72`
- prototype: `__int64 __fastcall(struct _REDIRECTION_CONTEXT *, void (*)(struct _REDIRECTION_CONTEXT *))`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800114e0`

## callees

- `0x1800150c0`
- `0x180020d68`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180020d9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180020d9b`

## pseudocode

```c
__int64 __fastcall RedirectionContextSetupAsynchIO(
        struct _REDIRECTION_CONTEXT *a1,
        void (*a2)(struct _REDIRECTION_CONTEXT *))
{
  unsigned int v3; // edi

  *((_QWORD *)a1 + 23) = a2;
  v3 = -1073741536;
  if ( RedirectionContextThreadpoolIsSafeForUse(a1) )
  {
    SetThreadpoolWait(*((PTP_WAIT *)a1 + 22), *((HANDLE *)a1 + 21), 0);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180020d68  mov     [rsp+arg_0], rbx
0x180020d6d  push    rdi
0x180020d6e  sub     rsp, 20h
0x180020d72  mov     rbx, rcx
0x180020d75  mov     [rcx+0B8h], rdx
0x180020d7c  mov     edi, 0C0000120h
0x180020d81  call    ?RedirectionContextThreadpoolIsSafeForUse@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextThreadpoolIsSafeForUse(_REDIRECTION_CONTEXT *)
0x180020d86  test    al, al
0x180020d88  jz      short loc_180020DA3
0x180020d8a  mov     rdx, [rbx+0A8h]; h
0x180020d91  xor     r8d, r8d; pftTimeout
0x180020d94  mov     rcx, [rbx+0B0h]; pwa
0x180020d9b  call    cs:__imp_SetThreadpoolWait
0x180020da1  xor     edi, edi
0x180020da3  mov     rbx, [rsp+28h+arg_0]
0x180020da8  mov     eax, edi
0x180020daa  add     rsp, 20h
0x180020dae  pop     rdi
0x180020daf  retn
```
