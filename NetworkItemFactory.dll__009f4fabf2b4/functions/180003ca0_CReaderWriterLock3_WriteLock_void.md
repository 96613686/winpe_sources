# CReaderWriterLock3::WriteLock(void)

- ea: `0x180003ca0`
- end: `0x180003d20`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `128`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003bb4`
- `0x18000488c`
- `0x180005058`
- `0x180006240`
- `0x1800066e8`
- `0x180006ef4`
- `0x180007e18`
- `0x180008250`
- `0x180008bf4`
- `0x1800091b0`
- `0x180009574`
- `0x1800098d4`
- `0x18000a018`

## callees

- `0x180003ca0`
- `0x1800076c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180003ccd`
- `KERNEL32!GetCurrentThreadId` at `0x180003ce2`
- `KERNEL32!GetCurrentThreadId` at `0x180003ccd`
- `KERNEL32!GetCurrentThreadId` at `0x180003ce2`

## pseudocode

```c
void __fastcall CReaderWriterLock3::WriteLock(CReaderWriterLock3 *this)
{
  signed __int32 v2; // ecx
  DWORD v3; // eax
  signed __int32 v4; // edx

  if ( !*((_DWORD *)this + 1) )
  {
    v2 = *(_DWORD *)this;
    if ( !(_WORD)v2 && v2 == _InterlockedCompareExchange((volatile signed __int32 *)this, (v2 + 0x10000) | 0xFFFF, v2) )
    {
      v3 = GetCurrentThreadId() & 0xFFFFFFFC | 1;
LABEL_5:
      _InterlockedExchange((volatile __int32 *)this + 1, v3);
      return;
    }
  }
  if ( (*((_DWORD *)this + 1) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
  {
    v3 = *((_DWORD *)this + 1) + 1;
    goto LABEL_5;
  }
  do
    v4 = *(_DWORD *)this;
  while ( v4 != _InterlockedCompareExchange((volatile signed __int32 *)this, v4 + 0x10000, v4) );
  CReaderWriterLock3::_LockSpin(this, 1);
}

```

## disassembly

```asm
0x180003ca0  push    rbx
0x180003ca2  sub     rsp, 20h
0x180003ca6  mov     eax, [rcx+4]
0x180003ca9  mov     rbx, rcx
0x180003cac  test    eax, eax
0x180003cae  jnz     short loc_180003CE2
0x180003cb0  mov     ecx, [rcx]
0x180003cb2  test    cx, cx
0x180003cb5  jnz     short loc_180003CE2
0x180003cb7  lea     edx, [rcx+10000h]
0x180003cbd  mov     eax, ecx
0x180003cbf  or      edx, 0FFFFh
0x180003cc5  lock cmpxchg [rbx], edx
0x180003cc9  cmp     ecx, eax
0x180003ccb  jnz     short loc_180003CE2
0x180003ccd  call    cs:__imp_GetCurrentThreadId
0x180003cd3  and     eax, 0FFFFFFFCh
0x180003cd6  or      eax, 1
0x180003cd9  xchg    eax, [rbx+4]
0x180003cdc  add     rsp, 20h
0x180003ce0  pop     rbx
0x180003ce1  retn
0x180003ce2  call    cs:__imp_GetCurrentThreadId
0x180003ce8  mov     ecx, [rbx+4]
0x180003ceb  and     eax, 0FFFFFFFCh
0x180003cee  and     ecx, 0FFFFFFFCh
0x180003cf1  cmp     ecx, eax
0x180003cf3  jnz     short loc_180003CFC
0x180003cf5  mov     eax, [rbx+4]
0x180003cf8  inc     eax
0x180003cfa  jmp     short loc_180003CD9
0x180003cfc  mov     edx, [rbx]
0x180003cfe  mov     eax, edx
0x180003d00  lea     ecx, [rdx+10000h]
0x180003d06  lock cmpxchg [rbx], ecx
0x180003d0a  cmp     edx, eax
0x180003d0c  jnz     short loc_180003CFC
0x180003d0e  mov     edx, 1
0x180003d13  mov     rcx, rbx
0x180003d16  add     rsp, 20h
0x180003d1a  pop     rbx
0x180003d1b  jmp     ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
```
