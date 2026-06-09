# CopyAcceleratorRpc::Cleanup(void)

- ea: `0x14001e350`
- end: `0x14001e3c3`
- name: `?Cleanup@CopyAcceleratorRpc@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(CopyAcceleratorRpc *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001d330`

## callees

- `0x14001da70`
- `0x14001e350`
- `0x14001e3c4`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14001e364`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001e364`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001e3b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001e3b0`

## pseudocode

```c
__int64 __fastcall CopyAcceleratorRpc::Cleanup(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  int v3; // ebx

  v1 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  v3 = CopyAcceleratorRpc::CleanupUnsafe((CopyAcceleratorRpc *)this);
  if ( v3 >= 0 )
  {
    v3 = 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
      (unsigned int)v3);
  }
  ReleaseSRWLockExclusive(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001e350  mov     [rsp+arg_0], rbx
0x14001e355  push    rdi
0x14001e356  sub     rsp, 20h
0x14001e35a  lea     rdi, [rcx+28h]
0x14001e35e  mov     rbx, rcx
0x14001e361  mov     rcx, rdi; SRWLock
0x14001e364  call    cs:__imp_AcquireSRWLockExclusive
0x14001e36a  mov     rcx, rbx; this
0x14001e36d  call    ?CleanupUnsafe@CopyAcceleratorRpc@@AEAAJXZ; CopyAcceleratorRpc::CleanupUnsafe(void)
0x14001e372  mov     ebx, eax
0x14001e374  test    eax, eax
0x14001e376  jns     short loc_14001E3AB
0x14001e378  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e37f  lea     rax, WPP_GLOBAL_Control
0x14001e386  cmp     rcx, rax
0x14001e389  jz      short loc_14001E3AD
0x14001e38b  test    byte ptr [rcx+1Ch], 1
0x14001e38f  jz      short loc_14001E3AD
0x14001e391  mov     rcx, [rcx+10h]
0x14001e395  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e39c  mov     edx, 10h
0x14001e3a1  mov     r9d, ebx
0x14001e3a4  call    WPP_SF_d
0x14001e3a9  jmp     short loc_14001E3AD
0x14001e3ab  xor     ebx, ebx
0x14001e3ad  mov     rcx, rdi; SRWLock
0x14001e3b0  call    cs:__imp_ReleaseSRWLockExclusive
0x14001e3b6  mov     eax, ebx
0x14001e3b8  mov     rbx, [rsp+28h+arg_0]
0x14001e3bd  add     rsp, 20h
0x14001e3c1  pop     rdi
0x14001e3c2  retn
```
