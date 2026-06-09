# MsCleanupThunk(void)

- ea: `0x1400ab0c0`
- end: `0x1400ab14f`
- name: `?MsCleanupThunk@@YAXXZ`
- size: `143`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140088170`

## callees

- `0x1400ab0c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1400ab102`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1400ab102`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1400ab0f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1400ab0f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1400ab120`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1400ab120`

## pseudocode

```c
void MsCleanupThunk(void)
{
  __int64 v0; // rdi
  __int64 v1; // rbx
  struct _TP_POOL *v2; // rcx

  v0 = 3;
  v1 = 264;
  do
  {
    if ( *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1) )
    {
      CloseThreadpoolCleanupGroupMembers(*(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 8), 0, 0);
      CloseThreadpoolCleanupGroup(*(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 8));
      *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 8) = 0;
    }
    v2 = *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1);
    if ( v2 )
    {
      CloseThreadpool(v2);
      *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1) = 0;
    }
    v1 -= 88;
    --v0;
  }
  while ( v0 );
}

```

## disassembly

```asm
0x1400ab0c0  mov     [rsp+arg_0], rbx
0x1400ab0c5  mov     [rsp+arg_8], rbp
0x1400ab0ca  push    rdi
0x1400ab0cb  sub     rsp, 20h
0x1400ab0cf  mov     edi, 3
0x1400ab0d4  lea     rbp, ?MspThunkThreadpool@@3PAUMS_THREADPOOL@@A; MS_THREADPOOL near * MspThunkThreadpool
0x1400ab0db  mov     ebx, 108h
0x1400ab0e0  cmp     qword ptr [rbx+rbp], 0
0x1400ab0e5  jz      short loc_1400AB117
0x1400ab0e7  mov     rcx, [rbx+rbp+8]; ptpcg
0x1400ab0ec  xor     r8d, r8d; pvCleanupContext
0x1400ab0ef  xor     edx, edx; fCancelPendingCallbacks
0x1400ab0f1  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1400ab0f8  nop     dword ptr [rax+rax+00h]
0x1400ab0fd  mov     rcx, [rbx+rbp+8]; ptpcg
0x1400ab102  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1400ab109  nop     dword ptr [rax+rax+00h]
0x1400ab10e  mov     qword ptr [rbx+rbp+8], 0
0x1400ab117  mov     rcx, [rbx+rbp]; ptpp
0x1400ab11b  test    rcx, rcx
0x1400ab11e  jz      short loc_1400AB134
0x1400ab120  call    cs:__imp_CloseThreadpool
0x1400ab127  nop     dword ptr [rax+rax+00h]
0x1400ab12c  mov     qword ptr [rbx+rbp], 0
0x1400ab134  sub     rbx, 58h ; 'X'
0x1400ab138  sub     rdi, 1
0x1400ab13c  jnz     short loc_1400AB0E0
0x1400ab13e  mov     rbx, [rsp+28h+arg_0]
0x1400ab143  mov     rbp, [rsp+28h+arg_8]
0x1400ab148  add     rsp, 20h
0x1400ab14c  pop     rdi
0x1400ab14d  retn
```
