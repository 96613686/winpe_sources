# CAggregateTelemetry<CPhotographyBaseData,ulong,double,0,0>::~CAggregateTelemetry<CPhotographyBaseData,ulong,double,0,0>(void)

- ea: `0x18000e6cc`
- end: `0x18000e749`
- name: `??1?$CAggregateTelemetry@VCPhotographyBaseData@@KN$0A@$0A@@@UEAA@XZ`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f5d0`
- `0x18000f610`

## callees

- `0x1800028cc`
- `0x18000e6cc`
- `0x1800158e0`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e6fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e6fc`

## pseudocode

```c
void __fastcall CAggregateTelemetry<CPhotographyBaseData,unsigned long,double,0,0>::~CAggregateTelemetry<CPhotographyBaseData,unsigned long,double,0,0>(
        __int64 a1,
        __int64 a2)
{
  void *v3; // rdi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *(_QWORD *)a1 = &CAggregateTelemetry<CPhotographyBaseData,unsigned long,double,0,0>::`vftable';
  if ( *(_BYTE *)(a1 + 16) )
  {
    LOBYTE(a2) = 1;
    CAggregateTelemetry<CPhotographyBaseData,unsigned long,double,0,0>::Log(a1, a2);
  }
  v3 = *(void **)(a1 + 24);
  if ( v3 )
  {
    DeleteCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 24));
    operator delete(v3, (const struct std::nothrow_t *)0x28);
    *(_QWORD *)(a1 + 24) = 0;
  }
  if ( *(_BYTE *)(a1 + 17) )
  {
    v4 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 8);
    if ( v4 )
    {
      (**v4)(v4, 1);
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
}

```

## disassembly

```asm
0x18000e6cc  mov     [rsp+arg_0], rbx
0x18000e6d1  push    rdi
0x18000e6d2  sub     rsp, 20h
0x18000e6d6  mov     rbx, rcx
0x18000e6d9  lea     rax, ??_7?$CAggregateTelemetry@VCPhotographyBaseData@@KN$0A@$0A@@@6B@; const CAggregateTelemetry<CPhotographyBaseData,ulong,double,0,0>::`vftable'
0x18000e6e0  mov     [rcx], rax
0x18000e6e3  cmp     byte ptr [rcx+10h], 0
0x18000e6e7  jz      short loc_18000E6F0
0x18000e6e9  mov     dl, 1
0x18000e6eb  call    ?Log@?$CAggregateTelemetry@VCPhotographyBaseData@@KN$0A@$0A@@@UEAAX_N@Z; CAggregateTelemetry<CPhotographyBaseData,ulong,double,0,0>::Log(bool)
0x18000e6f0  mov     rdi, [rbx+18h]
0x18000e6f4  test    rdi, rdi
0x18000e6f7  jz      short loc_18000E717
0x18000e6f9  mov     rcx, rdi; lpCriticalSection
0x18000e6fc  call    cs:__imp_DeleteCriticalSection
0x18000e702  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18000e707  mov     rcx, rdi; void *
0x18000e70a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e70f  mov     qword ptr [rbx+18h], 0
0x18000e717  cmp     byte ptr [rbx+11h], 0
0x18000e71b  jz      short loc_18000E73E
0x18000e71d  mov     rcx, [rbx+8]
0x18000e721  test    rcx, rcx
0x18000e724  jz      short loc_18000E73E
0x18000e726  mov     rax, [rcx]
0x18000e729  mov     edx, 1
0x18000e72e  mov     rax, [rax]
0x18000e731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e736  mov     qword ptr [rbx+8], 0
0x18000e73e  mov     rbx, [rsp+28h+arg_0]
0x18000e743  add     rsp, 20h
0x18000e747  pop     rdi
0x18000e748  retn
```
