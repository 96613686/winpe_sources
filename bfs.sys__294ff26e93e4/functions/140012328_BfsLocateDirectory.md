# BfsLocateDirectory

- ea: `0x140012328`
- end: `0x1400123f5`
- name: `BfsLocateDirectory`
- size: `205`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001093c`

## callees

- `0x140012328`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140012378`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140012378`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400123bf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400123bf`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140012392`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140012392`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012367`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012367`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400123cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400123cb`

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
0x140012328  push    rbx
0x14001232a  push    rsi
0x14001232b  push    rdi
0x14001232c  sub     rsp, 0D0h
0x140012333  mov     rax, cs:__security_cookie
0x14001233a  xor     rax, rsp
0x14001233d  mov     [rsp+0E8h+var_28], rax
0x140012345  mov     rsi, r8
0x140012348  mov     rbx, rdx
0x14001234b  mov     rdi, rcx
0x14001234e  xor     edx, edx; Val
0x140012350  mov     r8d, 0A0h; Size
0x140012356  lea     rcx, [rsp+0E8h+Buffer]; void *
0x14001235b  call    memset
0x140012360  mov     qword ptr [rsi], 0
0x140012367  call    cs:__imp_KeEnterCriticalRegion
0x14001236e  nop     dword ptr [rax+rax+00h]
0x140012373  xor     edx, edx
0x140012375  mov     rcx, rdi
0x140012378  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001237f  nop     dword ptr [rax+rax+00h]
0x140012384  lea     rcx, [rdi+8]; Table
0x140012388  mov     [rsp+0E8h+Buffer], rbx
0x14001238d  lea     rdx, [rsp+0E8h+Buffer]; Buffer
0x140012392  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140012399  nop     dword ptr [rax+rax+00h]
0x14001239e  test    rax, rax
0x1400123a1  jz      short loc_1400123B5
0x1400123a3  lock inc dword ptr [rax+98h]
0x1400123aa  add     rax, 8
0x1400123ae  mov     [rsi], rax
0x1400123b1  xor     ebx, ebx
0x1400123b3  jmp     short loc_1400123BA
0x1400123b5  mov     ebx, 0C0000225h
0x1400123ba  xor     edx, edx
0x1400123bc  mov     rcx, rdi
0x1400123bf  call    cs:__imp_ExReleasePushLockSharedEx
0x1400123c6  nop     dword ptr [rax+rax+00h]
0x1400123cb  call    cs:__imp_KeLeaveCriticalRegion
0x1400123d2  nop     dword ptr [rax+rax+00h]
0x1400123d7  mov     eax, ebx
0x1400123d9  mov     rcx, [rsp+0E8h+var_28]
0x1400123e1  xor     rcx, rsp; StackCookie
0x1400123e4  call    __security_check_cookie
0x1400123e9  add     rsp, 0D0h
0x1400123f0  pop     rdi
0x1400123f1  pop     rsi
0x1400123f2  pop     rbx
0x1400123f3  retn
```
