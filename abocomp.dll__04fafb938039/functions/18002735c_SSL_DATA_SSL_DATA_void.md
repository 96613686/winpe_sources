# SSL_DATA::SSL_DATA(void)

- ea: `0x18002735c`
- end: `0x1800273bc`
- name: `??0SSL_DATA@@QEAA@XZ`
- size: `96`
- prototype: `SSL_DATA *__fastcall(SSL_DATA *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180013ec0`
- `0x180016200`
- `0x1800165d0`
- `0x18002742c`
- `0x1800293b0`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800273ad`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800273ad`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027365`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027379`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027386`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027365`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027379`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027386`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18002736f`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18002736f`

## pseudocode

```c
SSL_DATA *__fastcall SSL_DATA::SSL_DATA(SSL_DATA *this)
{
  STRU::STRU(this);
  BUFFER::BUFFER((SSL_DATA *)((char *)this + 56));
  STRU::STRU((SSL_DATA *)((char *)this + 104));
  STRU::STRU((SSL_DATA *)((char *)this + 160));
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  STRU::Copy(this, (const unsigned __int16 *)&g_SSLCertStoreName);
  return this;
}

```

## disassembly

```asm
0x18002735c  push    rbx
0x18002735e  sub     rsp, 20h
0x180027362  mov     rbx, rcx
0x180027365  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002736b  lea     rcx, [rbx+38h]
0x18002736f  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180027375  lea     rcx, [rbx+68h]
0x180027379  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002737f  lea     rcx, [rbx+0A0h]
0x180027386  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002738c  xor     eax, eax
0x18002738e  lea     rdx, ?g_SSLCertStoreName@@3PAGA; "MY"
0x180027395  mov     rcx, rbx
0x180027398  mov     [rbx+0D8h], rax
0x18002739f  mov     [rbx+0E0h], rax
0x1800273a6  mov     [rbx+0E8h], rax
0x1800273ad  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800273b3  mov     rax, rbx
0x1800273b6  add     rsp, 20h
0x1800273ba  pop     rbx
0x1800273bb  retn
```
