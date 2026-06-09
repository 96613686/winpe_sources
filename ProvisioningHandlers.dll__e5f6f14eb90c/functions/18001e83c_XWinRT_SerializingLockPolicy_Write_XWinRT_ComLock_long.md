# XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)

- ea: `0x18001e83c`
- end: `0x18001e886`
- name: `?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z`
- size: `74`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012740`
- `0x180019680`
- `0x1800198cc`
- `0x18001bd20`
- `0x18001bfb0`
- `0x18001c1d0`
- `0x18001cc40`
- `0x18001ce70`

## callees

- `0x18001e83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e865`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e865`

## pseudocode

```c
RTL_SRWLOCK **__fastcall XWinRT::SerializingLockPolicy::Write(RTL_SRWLOCK **a1, RTL_SRWLOCK *a2, _DWORD *a3)
{
  RTL_SRWLOCK *v4; // rcx
  RTL_SRWLOCK **result; // rax

  *a1 = a2;
  v4 = a2 + 1;
  if ( LODWORD(a2->Ptr) == 1 )
  {
    if ( !LODWORD(v4->Ptr) )
      LODWORD(v4->Ptr) = -268435456;
  }
  else
  {
    AcquireSRWLockExclusive(v4);
  }
  result = a1;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18001e83c  mov     [rsp+arg_0], rbx
0x18001e841  push    rdi
0x18001e842  sub     rsp, 20h
0x18001e846  mov     [rcx], rdx
0x18001e849  mov     rbx, rcx
0x18001e84c  cmp     dword ptr [rdx], 1
0x18001e84f  lea     rcx, [rdx+8]; SRWLock
0x18001e853  mov     rdi, r8
0x18001e856  jnz     short loc_18001E865
0x18001e858  cmp     dword ptr [rcx], 0
0x18001e85b  jnz     short loc_18001E871
0x18001e85d  mov     dword ptr [rcx], 0F0000000h
0x18001e863  jmp     short loc_18001E871
0x18001e865  call    cs:__imp_AcquireSRWLockExclusive
0x18001e86c  nop     dword ptr [rax+rax+00h]
0x18001e871  mov     rax, rbx
0x18001e874  mov     dword ptr [rdi], 0
0x18001e87a  mov     rbx, [rsp+28h+arg_0]
0x18001e87f  add     rsp, 20h
0x18001e883  pop     rdi
0x18001e884  retn
```
