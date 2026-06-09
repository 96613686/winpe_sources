# TieringJetSession::Initialize(TieringJetDatabase *)

- ea: `0x14001a1d4`
- end: `0x14001a267`
- name: `?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(TieringJetSession *this, RTL_SRWLOCK **)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c444`
- `0x14000c648`
- `0x14000d5f0`
- `0x14000ef74`
- `0x14000f108`
- `0x1400108e0`
- `0x140010d1c`
- `0x1400122fc`
- `0x140017120`
- `0x1400211a4`
- `0x14002eef0`
- `0x14003cfb4`
- `0x14003d800`
- `0x14003db78`
- `0x14003ddd4`
- `0x14003e49c`
- `0x14003eba8`
- `0x14003f4d8`

## callees

- `0x140009c08`
- `0x14001a1d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a254`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a254`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001a1ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001a1ef`

## pseudocode

```c
__int64 __fastcall TieringJetSession::Initialize(TieringJetSession *this, RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v3; // rdi
  __int64 v4; // rax
  unsigned int v5; // ebx

  *((_QWORD *)this + 5) = a2;
  v3 = *a2 + 3;
  AcquireSRWLockExclusive(v3);
  v4 = *((_QWORD *)this + 5);
  if ( *(_BYTE *)(v4 + 77) )
  {
    v5 = -2147220993;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
        *(_QWORD *)(v4 + 112),
        255);
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 72));
    *((_BYTE *)this + 34) = 1;
    v5 = 0;
  }
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
  return v5;
}

```

## disassembly

```asm
0x14001a1d4  mov     [rsp+arg_0], rbx
0x14001a1d9  push    rdi
0x14001a1da  sub     rsp, 30h
0x14001a1de  mov     [rcx+28h], rdx
0x14001a1e2  mov     rbx, rcx
0x14001a1e5  mov     rdi, [rdx]
0x14001a1e8  add     rdi, 18h
0x14001a1ec  mov     rcx, rdi; SRWLock
0x14001a1ef  call    cs:__imp_AcquireSRWLockExclusive
0x14001a1f5  mov     rax, [rbx+28h]
0x14001a1f9  cmp     byte ptr [rax+4Dh], 0
0x14001a1fd  jz      short loc_14001A242
0x14001a1ff  mov     ebx, 800401FFh
0x14001a204  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a20b  lea     rdx, WPP_GLOBAL_Control
0x14001a212  cmp     rcx, rdx
0x14001a215  jz      short loc_14001A24C
0x14001a217  test    byte ptr [rcx+1Ch], 1
0x14001a21b  jz      short loc_14001A24C
0x14001a21d  cmp     byte ptr [rcx+19h], 2
0x14001a221  jb      short loc_14001A24C
0x14001a223  mov     r9, [rax+70h]
0x14001a227  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001a22e  mov     rcx, [rcx+10h]
0x14001a232  mov     edx, 4Fh ; 'O'
0x14001a237  mov     [rsp+38h+var_18], ebx
0x14001a23b  call    WPP_SF_Sd
0x14001a240  jmp     short loc_14001A24C
0x14001a242  lock inc dword ptr [rax+48h]
0x14001a246  mov     byte ptr [rbx+22h], 1
0x14001a24a  xor     ebx, ebx
0x14001a24c  test    rdi, rdi
0x14001a24f  jz      short loc_14001A25A
0x14001a251  mov     rcx, rdi; SRWLock
0x14001a254  call    cs:__imp_ReleaseSRWLockExclusive
0x14001a25a  mov     eax, ebx
0x14001a25c  mov     rbx, [rsp+38h+arg_0]
0x14001a261  add     rsp, 30h
0x14001a265  pop     rdi
0x14001a266  retn
```
