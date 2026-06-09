# CProfileCache::NotifyBackgroundThread(void)

- ea: `0x1800066e8`
- end: `0x180006751`
- name: `?NotifyBackgroundThread@CProfileCache@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CProfileCache *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002f90`
- `0x1800065ac`

## callees

- `0x180003ca0`
- `0x1800066e8`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000674a`

## pseudocode

```c
void __fastcall CProfileCache::NotifyBackgroundThread(CProfileCache *this)
{
  signed __int32 *v1; // rbx
  int v3; // r8d
  bool v4; // zf
  signed __int32 v5; // edx

  v1 = (signed __int32 *)((char *)this + 48);
  CReaderWriterLock3::WriteLock((CProfileCache *)((char *)this + 48));
  *((_QWORD *)this + 13) = 0;
  v3 = v1[1] - 1;
  v4 = (((*((_BYTE *)v1 + 4) - 1) & 3) != 0 ? v3 : 0) == 0;
  _InterlockedExchange(v1 + 1, ((*((_BYTE *)v1 + 4) - 1) & 3) != 0 ? v3 : 0);
  if ( v4 )
  {
    _m_prefetchw(v1);
    do
      v5 = *v1;
    while ( v5 != _InterlockedCompareExchange(v1, (v5 - 0x10000) & 0xFFFF0000, v5) );
  }
  SetEvent(*((HANDLE *)this + 8));
}

```

## disassembly

```asm
0x1800066e8  mov     [rsp+arg_0], rbx
0x1800066ed  push    rdi
0x1800066ee  sub     rsp, 20h
0x1800066f2  lea     rbx, [rcx+30h]
0x1800066f6  mov     rdi, rcx
0x1800066f9  mov     rcx, rbx; this
0x1800066fc  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180006701  mov     qword ptr [rdi+68h], 0
0x180006709  mov     r8d, [rbx+4]
0x18000670d  dec     r8d
0x180006710  mov     eax, r8d
0x180006713  and     al, 3
0x180006715  neg     al
0x180006717  sbb     edx, edx
0x180006719  and     edx, r8d
0x18000671c  xchg    edx, [rbx+4]
0x18000671f  jnz     short loc_18000673C
0x180006721  prefetchw byte ptr [rbx]
0x180006724  mov     edx, [rbx]
0x180006726  mov     eax, edx
0x180006728  lea     ecx, [rdx-10000h]
0x18000672e  and     ecx, 0FFFF0000h
0x180006734  lock cmpxchg [rbx], ecx
0x180006738  cmp     edx, eax
0x18000673a  jnz     short loc_180006724
0x18000673c  mov     rcx, [rdi+40h]
0x180006740  mov     rbx, [rsp+28h+arg_0]
0x180006745  add     rsp, 20h
0x180006749  pop     rdi
0x18000674a  jmp     cs:__imp_SetEvent
```
