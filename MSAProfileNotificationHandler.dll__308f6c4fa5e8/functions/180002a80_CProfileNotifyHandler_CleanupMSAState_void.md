# CProfileNotifyHandler::CleanupMSAState(void *)

- ea: `0x180002a80`
- end: `0x180002abc`
- name: `?CleanupMSAState@CProfileNotifyHandler@@CAKPEAX@Z`
- size: `60`
- prototype: `__int64 __fastcall(unsigned __int16 *lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180001cd4`
- `0x180002a80`
- `0x1800066d4`

## pseudocode

```c
__int64 __fastcall CProfileNotifyHandler::CleanupMSAState(unsigned __int16 *lpThreadParameter)
{
  unsigned int v2; // edi

  ++g_cRefDll;
  v2 = WLIDCCleanupIdentity(lpThreadParameter);
  if ( lpThreadParameter )
    operator delete(lpThreadParameter, 0);
  --g_cRefDll;
  return v2;
}

```

## disassembly

```asm
0x180002a80  mov     [rsp+arg_0], rbx
0x180002a85  push    rdi
0x180002a86  sub     rsp, 20h
0x180002a8a  inc     cs:?g_cRefDll@@3JA; long g_cRefDll
0x180002a90  mov     rbx, rcx
0x180002a93  call    ?WLIDCCleanupIdentity@@YAJPEBG@Z; WLIDCCleanupIdentity(ushort const *)
0x180002a98  mov     edi, eax
0x180002a9a  test    rbx, rbx
0x180002a9d  jz      short loc_180002AA9
0x180002a9f  xor     edx, edx; unsigned __int64
0x180002aa1  mov     rcx, rbx; void *
0x180002aa4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002aa9  dec     cs:?g_cRefDll@@3JA; long g_cRefDll
0x180002aaf  mov     eax, edi
0x180002ab1  mov     rbx, [rsp+28h+arg_0]
0x180002ab6  add     rsp, 20h
0x180002aba  pop     rdi
0x180002abb  retn
```
