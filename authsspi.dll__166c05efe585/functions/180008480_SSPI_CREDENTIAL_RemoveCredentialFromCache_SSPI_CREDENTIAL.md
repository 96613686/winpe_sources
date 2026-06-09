# SSPI_CREDENTIAL::RemoveCredentialFromCache(SSPI_CREDENTIAL *)

- ea: `0x180008480`
- end: `0x18000852f`
- name: `?RemoveCredentialFromCache@SSPI_CREDENTIAL@@SAXPEAV1@@Z`
- size: `175`
- prototype: `void __fastcall(struct SSPI_CREDENTIAL *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800021f0`
- `0x1800048f0`

## callees

- `0x180001064`
- `0x180008480`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x1800084f8`
- `SspiCli!FreeCredentialsHandle` at `0x1800084f8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800084c1`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800084c1`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008494`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008494`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000850f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000850f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180008505`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180008505`

## pseudocode

```c
void __fastcall SSPI_CREDENTIAL::RemoveCredentialFromCache(struct SSPI_CREDENTIAL *Block)
{
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  _QWORD *v4; // rax

  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
  v2 = (_QWORD *)((char *)Block + 128);
  v3 = *((_QWORD *)Block + 16);
  if ( *(struct SSPI_CREDENTIAL **)(v3 + 8) != (struct SSPI_CREDENTIAL *)((char *)Block + 128)
    || (v4 = (_QWORD *)*((_QWORD *)Block + 17), (_QWORD *)*v4 != v2) )
  {
    __fastfail(3u);
  }
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
  *v2 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 1, 0xFFFFFFFF) == 1 )
  {
    *(_DWORD *)Block = 1396917094;
    if ( *((_QWORD *)Block + 25) != -1 && *((_QWORD *)Block + 26) != -1 )
      FreeCredentialsHandle((PCredHandle)((char *)Block + 200));
    MULTISZ::~MULTISZ((struct SSPI_CREDENTIAL *)((char *)Block + 144));
    STRA::~STRA((struct SSPI_CREDENTIAL *)((char *)Block + 8));
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x180008480  mov     [rsp+arg_0], rbx
0x180008485  push    rdi
0x180008486  sub     rsp, 20h
0x18000848a  mov     rbx, rcx
0x18000848d  lea     rcx, ?sm_SSPICredentialLock@SSPI_CREDENTIAL@@0VCReaderWriterLock3@@A; CReaderWriterLock3 SSPI_CREDENTIAL::sm_SSPICredentialLock
0x180008494  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000849a  lea     rdi, [rbx+80h]
0x1800084a1  mov     rdx, [rdi]
0x1800084a4  cmp     [rdx+8], rdi
0x1800084a8  jnz     short loc_180008528
0x1800084aa  mov     rax, [rdi+8]
0x1800084ae  cmp     [rax], rdi
0x1800084b1  jnz     short loc_180008528
0x1800084b3  mov     [rax], rdx
0x1800084b6  lea     rcx, ?sm_SSPICredentialLock@SSPI_CREDENTIAL@@0VCReaderWriterLock3@@A; CReaderWriterLock3 SSPI_CREDENTIAL::sm_SSPICredentialLock
0x1800084bd  mov     [rdx+8], rax
0x1800084c1  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800084c7  or      eax, 0FFFFFFFFh
0x1800084ca  mov     qword ptr [rdi], 0
0x1800084d1  lock xadd [rbx+4], eax
0x1800084d6  cmp     eax, 1
0x1800084d9  jnz     short loc_18000851D
0x1800084db  lea     rcx, [rbx+0C8h]; phCredential
0x1800084e2  mov     dword ptr [rbx], 53434366h
0x1800084e8  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800084ec  jz      short loc_1800084FE
0x1800084ee  cmp     qword ptr [rbx+0D0h], 0FFFFFFFFFFFFFFFFh
0x1800084f6  jz      short loc_1800084FE
0x1800084f8  call    cs:__imp_FreeCredentialsHandle
0x1800084fe  lea     rcx, [rbx+90h]
0x180008505  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000850b  lea     rcx, [rbx+8]
0x18000850f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008515  mov     rcx, rbx; Block
0x180008518  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000851d  mov     rbx, [rsp+28h+arg_0]
0x180008522  add     rsp, 20h
0x180008526  pop     rdi
0x180008527  retn
0x180008528  mov     ecx, 3
0x18000852d  int     29h; Win8: RtlFailFast(ecx)
```
