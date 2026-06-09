# SSPI_CREDENTIAL::RemoveCredentialFromCache(SSPI_CREDENTIAL *)

- ea: `0x180005f10`
- end: `0x180005fbf`
- name: `?RemoveCredentialFromCache@SSPI_CREDENTIAL@@SAXPEAV1@@Z`
- size: `175`
- prototype: `void __fastcall(struct SSPI_CREDENTIAL *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001e00`

## callees

- `0x180001064`
- `0x180005f10`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x180005f88`
- `SspiCli!FreeCredentialsHandle` at `0x180005f88`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005f9f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005f9f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005f95`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005f95`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005f51`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005f51`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005f24`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005f24`

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
0x180005f10  mov     [rsp+arg_0], rbx
0x180005f15  push    rdi
0x180005f16  sub     rsp, 20h
0x180005f1a  mov     rbx, rcx
0x180005f1d  lea     rcx, ?sm_SSPICredentialLock@SSPI_CREDENTIAL@@0VCReaderWriterLock3@@A; CReaderWriterLock3 SSPI_CREDENTIAL::sm_SSPICredentialLock
0x180005f24  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180005f2a  lea     rdi, [rbx+80h]
0x180005f31  mov     rdx, [rdi]
0x180005f34  cmp     [rdx+8], rdi
0x180005f38  jnz     short loc_180005FB8
0x180005f3a  mov     rax, [rdi+8]
0x180005f3e  cmp     [rax], rdi
0x180005f41  jnz     short loc_180005FB8
0x180005f43  mov     [rax], rdx
0x180005f46  lea     rcx, ?sm_SSPICredentialLock@SSPI_CREDENTIAL@@0VCReaderWriterLock3@@A; CReaderWriterLock3 SSPI_CREDENTIAL::sm_SSPICredentialLock
0x180005f4d  mov     [rdx+8], rax
0x180005f51  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180005f57  or      eax, 0FFFFFFFFh
0x180005f5a  mov     qword ptr [rdi], 0
0x180005f61  lock xadd [rbx+4], eax
0x180005f66  cmp     eax, 1
0x180005f69  jnz     short loc_180005FAD
0x180005f6b  lea     rcx, [rbx+0C8h]; phCredential
0x180005f72  mov     dword ptr [rbx], 53434366h
0x180005f78  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180005f7c  jz      short loc_180005F8E
0x180005f7e  cmp     qword ptr [rbx+0D0h], 0FFFFFFFFFFFFFFFFh
0x180005f86  jz      short loc_180005F8E
0x180005f88  call    cs:__imp_FreeCredentialsHandle
0x180005f8e  lea     rcx, [rbx+90h]
0x180005f95  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180005f9b  lea     rcx, [rbx+8]
0x180005f9f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005fa5  mov     rcx, rbx; Block
0x180005fa8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005fad  mov     rbx, [rsp+28h+arg_0]
0x180005fb2  add     rsp, 20h
0x180005fb6  pop     rdi
0x180005fb7  retn
0x180005fb8  mov     ecx, 3
0x180005fbd  int     29h; Win8: RtlFailFast(ecx)
```
