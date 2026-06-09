# BfsLocateDirectory

- ea: `0x140012198`
- end: `0x140012265`
- name: `BfsLocateDirectory`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001079c`

## callees

- `0x140012198`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400121e8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400121e8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14001222f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14001222f`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140012202`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140012202`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400121d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400121d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001223b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001223b`

## pseudocode

```c
__int64 __fastcall BfsLocateDirectory(__int64 a1, __int64 a2, _QWORD *a3)
{
  volatile signed __int32 *v6; // rax
  unsigned int v7; // ebx
  _QWORD Buffer[20]; // [rsp+20h] [rbp-C8h] BYREF

  memset(Buffer, 0, sizeof(Buffer));
  *a3 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  Buffer[0] = a2;
  v6 = (volatile signed __int32 *)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 8), Buffer);
  if ( v6 )
  {
    _InterlockedIncrement(v6 + 38);
    *a3 = v6 + 2;
    v7 = 0;
  }
  else
  {
    v7 = -1073741275;
  }
  ExReleasePushLockSharedEx(a1, 0);
  KeLeaveCriticalRegion();
  return v7;
}

```

## disassembly

```asm
0x140012198  push    rbx
0x14001219a  push    rsi
0x14001219b  push    rdi
0x14001219c  sub     rsp, 0D0h
0x1400121a3  mov     rax, cs:__security_cookie
0x1400121aa  xor     rax, rsp
0x1400121ad  mov     [rsp+0E8h+var_28], rax
0x1400121b5  mov     rsi, r8
0x1400121b8  mov     rbx, rdx
0x1400121bb  mov     rdi, rcx
0x1400121be  xor     edx, edx; Val
0x1400121c0  mov     r8d, 0A0h; Size
0x1400121c6  lea     rcx, [rsp+0E8h+Buffer]; void *
0x1400121cb  call    memset
0x1400121d0  mov     qword ptr [rsi], 0
0x1400121d7  call    cs:__imp_KeEnterCriticalRegion
0x1400121de  nop     dword ptr [rax+rax+00h]
0x1400121e3  xor     edx, edx
0x1400121e5  mov     rcx, rdi
0x1400121e8  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400121ef  nop     dword ptr [rax+rax+00h]
0x1400121f4  lea     rcx, [rdi+8]; Table
0x1400121f8  mov     [rsp+0E8h+Buffer], rbx
0x1400121fd  lea     rdx, [rsp+0E8h+Buffer]; Buffer
0x140012202  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140012209  nop     dword ptr [rax+rax+00h]
0x14001220e  test    rax, rax
0x140012211  jz      short loc_140012225
0x140012213  lock inc dword ptr [rax+98h]
0x14001221a  add     rax, 8
0x14001221e  mov     [rsi], rax
0x140012221  xor     ebx, ebx
0x140012223  jmp     short loc_14001222A
0x140012225  mov     ebx, 0C0000225h
0x14001222a  xor     edx, edx
0x14001222c  mov     rcx, rdi
0x14001222f  call    cs:__imp_ExReleasePushLockSharedEx
0x140012236  nop     dword ptr [rax+rax+00h]
0x14001223b  call    cs:__imp_KeLeaveCriticalRegion
0x140012242  nop     dword ptr [rax+rax+00h]
0x140012247  mov     eax, ebx
0x140012249  mov     rcx, [rsp+0E8h+var_28]
0x140012251  xor     rcx, rsp; StackCookie
0x140012254  call    __security_check_cookie
0x140012259  add     rsp, 0D0h
0x140012260  pop     rdi
0x140012261  pop     rsi
0x140012262  pop     rbx
0x140012263  retn
```
