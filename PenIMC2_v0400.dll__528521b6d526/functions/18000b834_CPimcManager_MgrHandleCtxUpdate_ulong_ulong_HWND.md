# CPimcManager::MgrHandleCtxUpdate(ulong,ulong,HWND__ *)

- ea: `0x18000b834`
- end: `0x18000b8b9`
- name: `?MgrHandleCtxUpdate@CPimcManager@@SAXKKPEAUHWND__@@@Z`
- size: `133`
- prototype: `static void(unsigned int, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000b5d0`

## callees

- `0x18000b834`
- `0x18000b8bc`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000b863`
- `KERNEL32!WaitForSingleObject` at `0x18000b863`
- `KERNEL32!ReleaseMutex` at `0x18000b89e`
- `KERNEL32!ReleaseMutex` at `0x18000b89e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPimcManager::MgrHandleCtxUpdate(int a1, unsigned int a2, HWND a3)
{
  DWORD v6; // ebx
  struct CHookThreadItem *i; // r8

  v6 = 0;
  if ( g_hMutexHook )
    v6 = WaitForSingleObject(g_hMutexHook, 0xFFFFFFFF);
  for ( i = (struct CHookThreadItem *)g_HookThreadMap; i; i = (struct CHookThreadItem *)*((_QWORD *)i + 14) )
  {
    if ( *(_DWORD *)i == a1 )
    {
      CPimcManager::PostCtxUpdateForSubtree(a2, a3, i);
      break;
    }
  }
  if ( !v6 )
    ReleaseMutex(g_hMutexHook);
}

```

## disassembly

```asm
0x18000b834  mov     rax, rsp
0x18000b837  mov     [rax+8], rbx
0x18000b83b  mov     [rax+10h], rbp
0x18000b83f  mov     [rax+18h], rsi
0x18000b843  push    rdi
0x18000b844  sub     rsp, 20h
0x18000b848  mov     rsi, r8
0x18000b84b  mov     ebp, edx
0x18000b84d  mov     edi, ecx
0x18000b84f  xor     ebx, ebx
0x18000b851  mov     [rax+20h], ebx
0x18000b854  mov     rcx, cs:?g_hMutexHook@@3PEAXEA; hHandle
0x18000b85b  test    rcx, rcx
0x18000b85e  jz      short loc_18000B86F
0x18000b860  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b863  call    cs:__imp_WaitForSingleObject
0x18000b869  mov     ebx, eax
0x18000b86b  mov     [rsp+28h+arg_18], eax
0x18000b86f  mov     r8, cs:?g_HookThreadMap@@3V?$CPbList@UCHookThreadItem@@@@A; CPbList<CHookThreadItem> g_HookThreadMap
0x18000b876  jmp     short loc_18000B881
0x18000b878  cmp     [r8], edi
0x18000b87b  jz      short loc_18000B888
0x18000b87d  mov     r8, [r8+70h]; struct CHookThreadItem *
0x18000b881  test    r8, r8
0x18000b884  jnz     short loc_18000B878
0x18000b886  jmp     short loc_18000B893
0x18000b888  mov     rdx, rsi; HWND
0x18000b88b  mov     ecx, ebp; unsigned int
0x18000b88d  call    ?PostCtxUpdateForSubtree@CPimcManager@@SAXKPEAUHWND__@@PEAUCHookThreadItem@@@Z; CPimcManager::PostCtxUpdateForSubtree(ulong,HWND__ *,CHookThreadItem *)
0x18000b892  nop
0x18000b893  test    ebx, ebx
0x18000b895  jnz     short loc_18000B8A4
0x18000b897  mov     rcx, cs:?g_hMutexHook@@3PEAXEA; hMutex
0x18000b89e  call    cs:__imp_ReleaseMutex
0x18000b8a4  mov     rbx, [rsp+28h+arg_0]
0x18000b8a9  mov     rbp, [rsp+28h+arg_8]
0x18000b8ae  mov     rsi, [rsp+28h+arg_10]
0x18000b8b3  add     rsp, 20h
0x18000b8b7  pop     rdi
0x18000b8b8  retn
```
