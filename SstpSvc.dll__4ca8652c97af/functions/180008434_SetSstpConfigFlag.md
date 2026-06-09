# SetSstpConfigFlag

- ea: `0x180008434`
- end: `0x180008489`
- name: `SetSstpConfigFlag`
- size: `85`
- prototype: `void __fastcall(int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b2e0`
- `0x18000c8d0`
- `0x180014840`

## callees

- `0x180008434`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008450`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008450`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008482`

## pseudocode

```c
void __fastcall SetSstpConfigFlag(int a1, int a2)
{
  RTL_SRWLOCK *v4; // rcx

  AcquireSRWLockExclusive((PSRWLOCK)SstpSvcGlobals + 96);
  v4 = (RTL_SRWLOCK *)SstpSvcGlobals;
  if ( a2 )
    *((_DWORD *)SstpSvcGlobals + 194) |= a1;
  else
    *((_DWORD *)SstpSvcGlobals + 194) &= ~a1;
  ReleaseSRWLockExclusive(v4 + 96);
}

```

## disassembly

```asm
0x180008434  mov     [rsp+arg_0], rbx
0x180008439  push    rdi
0x18000843a  sub     rsp, 20h
0x18000843e  mov     edi, ecx
0x180008440  mov     ebx, edx
0x180008442  mov     rcx, cs:SstpSvcGlobals
0x180008449  add     rcx, 300h; SRWLock
0x180008450  call    cs:__imp_AcquireSRWLockExclusive
0x180008456  mov     rcx, cs:SstpSvcGlobals
0x18000845d  test    ebx, ebx
0x18000845f  jz      short loc_180008469
0x180008461  or      [rcx+308h], edi
0x180008467  jmp     short loc_180008471
0x180008469  not     edi
0x18000846b  and     [rcx+308h], edi
0x180008471  add     rcx, 300h
0x180008478  mov     rbx, [rsp+28h+arg_0]
0x18000847d  add     rsp, 20h
0x180008481  pop     rdi
0x180008482  jmp     cs:__imp_ReleaseSRWLockExclusive
```
