# CSW::CSW(CReadWriteLock &)

- ea: `0x180002df0`
- end: `0x180002ead`
- name: `??0CSW@@QEAA@AEAVCReadWriteLock@@@Z`
- size: `189`
- prototype: `CSW *__fastcall(CSW *__hidden this, struct CReadWriteLock *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006834`
- `0x18000a840`
- `0x18000d930`

## callees

- `0x180002df0`
- `0x18000f170`
- `0x18000f2e0`

## import_xrefs

- `KERNEL32!Sleep` at `0x180002e62`
- `KERNEL32!Sleep` at `0x180002e62`
- `KERNEL32!WaitForSingleObject` at `0x180002e9b`
- `KERNEL32!WaitForSingleObject` at `0x180002e9b`

## pseudocode

```c
CSW *__fastcall CSW::CSW(CSW *this, struct CReadWriteLock *a2, __int64 a3)
{
  unsigned int v4; // edi
  signed __int32 v5; // ebx
  unsigned int v6; // eax
  void *v7; // r8

  *(_QWORD *)this = &s_rwlockRpcTable;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, a3, &s_rwlockRpcTable);
  v4 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v5 = dword_180017C9C;
        if ( dword_180017C9C )
          break;
        if ( !_InterlockedCompareExchange(&dword_180017C9C, 1024, 0) )
          return this;
      }
      if ( (dword_180017C9C & 0xFFC00000) != 0xFFC00000 )
        break;
      Sleep(0x3E8u);
    }
    v6 = v4++;
    if ( v6 >= s_rwlockRpcTable )
    {
      v7 = CReadWriteLock::GetWriteWaiterEvent((CReadWriteLock *)&s_rwlockRpcTable);
      if ( v5 == _InterlockedCompareExchange(&dword_180017C9C, v5 + 0x400000, v5) )
        break;
    }
  }
  WaitForSingleObject(v7, 0xFFFFFFFF);
  return this;
}

```

## disassembly

```asm
0x180002df0  push    rbx
0x180002df2  push    rbp
0x180002df3  push    rsi
0x180002df4  push    rdi
0x180002df5  sub     rsp, 28h
0x180002df9  lea     rbp, ?s_rwlockRpcTable@@3VCReadWriteLock@@A; CReadWriteLock s_rwlockRpcTable
0x180002e00  mov     rsi, rcx
0x180002e03  mov     [rcx], rbp
0x180002e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e0d  lea     rax, WPP_GLOBAL_Control
0x180002e14  cmp     rcx, rax
0x180002e17  jz      short loc_180002E30
0x180002e19  test    byte ptr [rcx+1Ch], 4
0x180002e1d  jz      short loc_180002E30
0x180002e1f  mov     rcx, [rcx+10h]
0x180002e23  mov     edx, 0Bh
0x180002e28  mov     r9, rbp
0x180002e2b  call    WPP_SF_q
0x180002e30  xor     edi, edi
0x180002e32  mov     ebx, cs:dword_180017C9C
0x180002e38  test    ebx, ebx
0x180002e3a  jnz     short loc_180002E4F
0x180002e3c  mov     ecx, 400h
0x180002e41  xor     eax, eax
0x180002e43  lock cmpxchg cs:dword_180017C9C, ecx
0x180002e4b  jnz     short loc_180002E32
0x180002e4d  jmp     short loc_180002EA1
0x180002e4f  mov     eax, ebx
0x180002e51  and     eax, 0FFC00000h
0x180002e56  cmp     eax, 0FFC00000h
0x180002e5b  jnz     short loc_180002E6A
0x180002e5d  mov     ecx, 3E8h; dwMilliseconds
0x180002e62  call    cs:__imp_Sleep
0x180002e68  jmp     short loc_180002E32
0x180002e6a  mov     eax, edi
0x180002e6c  inc     edi
0x180002e6e  cmp     eax, cs:?s_rwlockRpcTable@@3VCReadWriteLock@@A; CReadWriteLock s_rwlockRpcTable
0x180002e74  jb      short loc_180002E32
0x180002e76  mov     rcx, rbp; this
0x180002e79  call    ?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetWriteWaiterEvent(void)
0x180002e7e  mov     r8, rax
0x180002e81  lea     ecx, [rbx+400000h]
0x180002e87  mov     eax, ebx
0x180002e89  lock cmpxchg cs:dword_180017C9C, ecx
0x180002e91  cmp     ebx, eax
0x180002e93  jnz     short loc_180002E32
0x180002e95  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002e98  mov     rcx, r8; hHandle
0x180002e9b  call    cs:__imp_WaitForSingleObject
0x180002ea1  mov     rax, rsi
0x180002ea4  add     rsp, 28h
0x180002ea8  pop     rdi
0x180002ea9  pop     rsi
0x180002eaa  pop     rbp
0x180002eab  pop     rbx
0x180002eac  retn
```
