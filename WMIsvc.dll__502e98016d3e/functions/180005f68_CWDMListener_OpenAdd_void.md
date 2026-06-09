# CWDMListener::OpenAdd(void)

- ea: `0x180005f68`
- end: `0x180005fd6`
- name: `?OpenAdd@CWDMListener@@QEAAKXZ`
- size: `110`
- prototype: `unsigned int __fastcall(CWDMListener *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004b60`
- `0x180016aec`

## callees

- `0x180005f68`
- `0x18000c65c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fb5`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180005fa6`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180005fa6`
- `WMICLNT!WmiOpenBlock` at `0x180005f82`
- `WMICLNT!WmiOpenBlock` at `0x180005f82`

## pseudocode

```c
__int64 __fastcall CWDMListener::OpenAdd(CWDMListener *this)
{
  __int64 v2; // rax
  DWORD LastError; // ebx

  if ( !(unsigned int)WmiOpenBlock((char *)this + 96, 1048580, (char *)this + 8) )
  {
    v2 = RegisterWaitForSingleObjectEx(*((_QWORD *)this + 1), CWDMListener::EvtCallBackAdd, this, 0xFFFFFFFFLL, 8);
    *((_QWORD *)this + 3) = v2;
    if ( v2 )
      return 0;
  }
  LastError = GetLastError();
  CWDMListener::CloseAdd(this);
  return LastError;
}

```

## disassembly

```asm
0x180005f68  mov     [rsp+arg_0], rbx
0x180005f6d  push    rdi
0x180005f6e  sub     rsp, 30h
0x180005f72  mov     rdi, rcx
0x180005f75  mov     edx, 100004h
0x180005f7a  add     rcx, 60h ; '`'
0x180005f7e  lea     r8, [rdi+8]
0x180005f82  call    cs:__imp_WmiOpenBlock
0x180005f88  test    eax, eax
0x180005f8a  jnz     short loc_180005FB5
0x180005f8c  mov     rcx, [rdi+8]
0x180005f90  lea     rdx, ?EvtCallBackAdd@CWDMListener@@SAXPEAXE@Z; CWDMListener::EvtCallBackAdd(void *,uchar)
0x180005f97  or      r9d, 0FFFFFFFFh
0x180005f9b  mov     [rsp+38h+var_18], 8
0x180005fa3  mov     r8, rdi
0x180005fa6  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180005fac  mov     [rdi+18h], rax
0x180005fb0  test    rax, rax
0x180005fb3  jnz     short loc_180005FD2
0x180005fb5  call    cs:__imp_GetLastError
0x180005fbb  mov     rcx, rdi; this
0x180005fbe  mov     ebx, eax
0x180005fc0  call    ?CloseAdd@CWDMListener@@QEAAKXZ; CWDMListener::CloseAdd(void)
0x180005fc5  mov     eax, ebx
0x180005fc7  mov     rbx, [rsp+38h+arg_0]
0x180005fcc  add     rsp, 30h
0x180005fd0  pop     rdi
0x180005fd1  retn
0x180005fd2  xor     eax, eax
0x180005fd4  jmp     short loc_180005FC7
```
