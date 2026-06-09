# AcpActivityCallback

- ea: `0x18001a910`
- end: `0x18001a95b`
- name: `AcpActivityCallback`
- size: `75`
- prototype: `void __fastcall(__int64, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001a910`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a931`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a931`

## pseudocode

```c
void __fastcall AcpActivityCallback(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // edi
  DWORD CurrentThreadId; // eax
  __int64 v7; // rdx

  if ( a3 )
  {
    if ( a3 != 1 )
      return;
    v5 = 1;
  }
  else
  {
    v5 = 0;
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = *(_QWORD *)(a5 + 24);
  *(_DWORD *)(a5 + 32) = CurrentThreadId;
  (*(void (__fastcall **)(_QWORD, __int64))(a5 + 16))(v5, v7);
  *(_DWORD *)(a5 + 32) = 0;
}

```

## disassembly

```asm
0x18001a910  mov     [rsp+arg_0], rbx
0x18001a915  push    rdi
0x18001a916  sub     rsp, 20h
0x18001a91a  test    r8d, r8d
0x18001a91d  jz      short loc_18001A92A
0x18001a91f  cmp     r8d, 1
0x18001a923  jnz     short loc_18001A950
0x18001a925  mov     edi, r8d
0x18001a928  jmp     short loc_18001A92C
0x18001a92a  xor     edi, edi
0x18001a92c  mov     rbx, [rsp+28h+arg_20]
0x18001a931  call    cs:__imp_GetCurrentThreadId
0x18001a937  mov     rdx, [rbx+18h]
0x18001a93b  mov     ecx, edi
0x18001a93d  mov     [rbx+20h], eax
0x18001a940  mov     rax, [rbx+10h]
0x18001a944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a949  mov     dword ptr [rbx+20h], 0
0x18001a950  mov     rbx, [rsp+28h+arg_0]
0x18001a955  add     rsp, 20h
0x18001a959  pop     rdi
0x18001a95a  retn
```
