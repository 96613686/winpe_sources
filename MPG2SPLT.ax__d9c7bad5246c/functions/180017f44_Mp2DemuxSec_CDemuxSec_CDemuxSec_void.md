# Mp2DemuxSec::CDemuxSec::~CDemuxSec(void)

- ea: `0x180017f44`
- end: `0x180017fc3`
- name: `??1CDemuxSec@Mp2DemuxSec@@UEAA@XZ`
- size: `127`
- prototype: `void __fastcall(Mp2DemuxSec::CDemuxSec *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180010f0c`
- `0x180010ff8`
- `0x180011510`
- `0x180013a58`
- `0x180018110`

## callees

- `0x180001048`
- `0x180017f44`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180017fa3`
- `KERNEL32!LocalFree` at `0x180017fb2`
- `KERNEL32!LocalFree` at `0x180017fa3`
- `KERNEL32!LocalFree` at `0x180017fb2`
- `ADVAPI32!FreeSid` at `0x180017f72`
- `ADVAPI32!FreeSid` at `0x180017f94`
- `ADVAPI32!FreeSid` at `0x180017f72`
- `ADVAPI32!FreeSid` at `0x180017f94`

## pseudocode

```c
void __fastcall Mp2DemuxSec::CDemuxSec::~CDemuxSec(Mp2DemuxSec::CDemuxSec *this, unsigned __int64 a2)
{
  bool v2; // zf
  __int64 i; // rdi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v2 = *((_QWORD *)this + 6) == 0;
  *(_QWORD *)this = &Mp2DemuxSec::CDemuxSec::`vftable';
  if ( !v2 )
  {
    for ( i = 0; (unsigned int)i < *((unsigned __int8 *)this + 56); i = (unsigned int)(i + 1) )
      FreeSid(*(PSID *)(*((_QWORD *)this + 6) + 8 * i));
    operator delete(*((void **)this + 6), a2);
  }
  v5 = (void *)*((_QWORD *)this + 8);
  if ( v5 )
    FreeSid(v5);
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
    LocalFree(v6);
  v7 = (void *)*((_QWORD *)this + 9);
  if ( v7 )
    LocalFree(v7);
}

```

## disassembly

```asm
0x180017f44  mov     [rsp+arg_0], rbx
0x180017f49  push    rdi
0x180017f4a  sub     rsp, 20h
0x180017f4e  cmp     qword ptr [rcx+30h], 0
0x180017f53  lea     rax, ??_7CDemuxSec@Mp2DemuxSec@@6B@; const Mp2DemuxSec::CDemuxSec::`vftable'
0x180017f5a  mov     [rcx], rax
0x180017f5d  mov     rbx, rcx
0x180017f60  jz      short loc_180017F8B
0x180017f62  xor     edi, edi
0x180017f64  cmp     [rcx+38h], dil
0x180017f68  jbe     short loc_180017F82
0x180017f6a  mov     rcx, [rbx+30h]
0x180017f6e  mov     rcx, [rcx+rdi*8]; pSid
0x180017f72  call    cs:__imp_FreeSid
0x180017f78  movzx   eax, byte ptr [rbx+38h]
0x180017f7c  inc     edi
0x180017f7e  cmp     edi, eax
0x180017f80  jb      short loc_180017F6A
0x180017f82  mov     rcx, [rbx+30h]; void *
0x180017f86  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017f8b  mov     rcx, [rbx+40h]; pSid
0x180017f8f  test    rcx, rcx
0x180017f92  jz      short loc_180017F9A
0x180017f94  call    cs:__imp_FreeSid
0x180017f9a  mov     rcx, [rbx+8]; hMem
0x180017f9e  test    rcx, rcx
0x180017fa1  jz      short loc_180017FA9
0x180017fa3  call    cs:__imp_LocalFree
0x180017fa9  mov     rcx, [rbx+48h]; hMem
0x180017fad  test    rcx, rcx
0x180017fb0  jz      short loc_180017FB8
0x180017fb2  call    cs:__imp_LocalFree
0x180017fb8  mov     rbx, [rsp+28h+arg_0]
0x180017fbd  add     rsp, 20h
0x180017fc1  pop     rdi
0x180017fc2  retn
```
