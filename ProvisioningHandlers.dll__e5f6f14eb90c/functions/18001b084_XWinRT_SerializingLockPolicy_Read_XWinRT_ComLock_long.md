# XWinRT::SerializingLockPolicy::Read(XWinRT::ComLock &,long *)

- ea: `0x18001b084`
- end: `0x18001b0cd`
- name: `?Read@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireRead@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z`
- size: `73`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015010`
- `0x180015130`
- `0x180015f50`
- `0x180016280`
- `0x180018ee0`
- `0x1800190a0`
- `0x180021b50`

## callees

- `0x18001b084`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b0ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b0ac`

## pseudocode

```c
RTL_SRWLOCK **__fastcall XWinRT::SerializingLockPolicy::Read(RTL_SRWLOCK **a1, RTL_SRWLOCK *a2, _DWORD *a3)
{
  RTL_SRWLOCK *v4; // rcx
  RTL_SRWLOCK **result; // rax

  *a1 = a2;
  v4 = a2 + 1;
  if ( LODWORD(a2->Ptr) == 1 )
  {
    if ( SLODWORD(v4->Ptr) >= 0 )
      ++LODWORD(v4->Ptr);
  }
  else
  {
    AcquireSRWLockShared(v4);
  }
  result = a1;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18001b084  mov     [rsp+arg_0], rbx
0x18001b089  push    rdi
0x18001b08a  sub     rsp, 20h
0x18001b08e  mov     [rcx], rdx
0x18001b091  mov     rbx, rcx
0x18001b094  cmp     dword ptr [rdx], 1
0x18001b097  lea     rcx, [rdx+8]; SRWLock
0x18001b09b  mov     rdi, r8
0x18001b09e  jnz     short loc_18001B0AC
0x18001b0a0  mov     eax, [rcx]
0x18001b0a2  test    eax, eax
0x18001b0a4  js      short loc_18001B0B8
0x18001b0a6  inc     eax
0x18001b0a8  mov     [rcx], eax
0x18001b0aa  jmp     short loc_18001B0B8
0x18001b0ac  call    cs:__imp_AcquireSRWLockShared
0x18001b0b3  nop     dword ptr [rax+rax+00h]
0x18001b0b8  mov     rax, rbx
0x18001b0bb  mov     dword ptr [rdi], 0
0x18001b0c1  mov     rbx, [rsp+28h+arg_0]
0x18001b0c6  add     rsp, 20h
0x18001b0ca  pop     rdi
0x18001b0cb  retn
```
