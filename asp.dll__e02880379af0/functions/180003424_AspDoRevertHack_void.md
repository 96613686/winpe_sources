# AspDoRevertHack(void * *)

- ea: `0x180003424`
- end: `0x180003465`
- name: `?AspDoRevertHack@@YAXPEAPEAX@Z`
- size: `65`
- prototype: `void __fastcall(PHANDLE TokenHandle)`
- caller_count: `12`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180001400`
- `0x180002ae8`
- `0x180003314`
- `0x180003e78`
- `0x1800041e8`
- `0x1800054e8`
- `0x180010630`
- `0x18001650c`
- `0x18004367c`
- `0x180043738`
- `0x180043974`
- `0x180060094`

## callees

- `0x180003424`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x18000345e`
- `ADVAPI32!OpenThreadToken` at `0x180003442`
- `ADVAPI32!OpenThreadToken` at `0x180003442`
- `KERNEL32!GetCurrentThread` at `0x18000342d`
- `KERNEL32!GetCurrentThread` at `0x18000342d`

## pseudocode

```c
void __fastcall AspDoRevertHack(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, TokenHandle) )
    RevertToSelf();
  else
    *TokenHandle = (HANDLE)-1LL;
}

```

## disassembly

```asm
0x180003424  push    rbx
0x180003426  sub     rsp, 20h
0x18000342a  mov     rbx, rcx
0x18000342d  call    cs:__imp_GetCurrentThread
0x180003433  mov     edx, 4; DesiredAccess
0x180003438  mov     r9, rbx; TokenHandle
0x18000343b  mov     rcx, rax; ThreadHandle
0x18000343e  lea     r8d, [rdx-3]; OpenAsSelf
0x180003442  call    cs:__imp_OpenThreadToken
0x180003448  test    eax, eax
0x18000344a  jnz     short loc_180003459
0x18000344c  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180003453  add     rsp, 20h
0x180003457  pop     rbx
0x180003458  retn
0x180003459  add     rsp, 20h
0x18000345d  pop     rbx
0x18000345e  jmp     cs:__imp_RevertToSelf
```
