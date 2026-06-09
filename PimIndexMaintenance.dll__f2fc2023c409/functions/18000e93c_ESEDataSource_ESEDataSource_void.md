# ESEDataSource::~ESEDataSource(void)

- ea: `0x18000e93c`
- end: `0x18000e976`
- name: `??1ESEDataSource@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ESEDataSource *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eaf0`
- `0x180021700`

## callees

- `0x18000e544`
- `0x18000e93c`
- `0x1800124a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e953`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e953`

## pseudocode

```c
void __fastcall ESEDataSource::~ESEDataSource(ESEDataSource *this)
{
  __int64 (__fastcall ***v2)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &ESEDataSource::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 24);
  v2 = (__int64 (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v2 )
    tlx::_delete<ESESession>(v2);
}

```

## disassembly

```asm
0x18000e93c  push    rbx
0x18000e93e  sub     rsp, 20h
0x18000e942  lea     rax, ??_7ESEDataSource@@6B@; const ESEDataSource::`vftable'
0x18000e949  mov     rbx, rcx
0x18000e94c  mov     [rcx], rax
0x18000e94f  add     rcx, 38h ; '8'; lpCriticalSection
0x18000e953  call    cs:__imp_DeleteCriticalSection
0x18000e959  lea     rcx, [rbx+18h]
0x18000e95d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000e962  mov     rcx, [rbx+10h]
0x18000e966  test    rcx, rcx
0x18000e969  jz      short loc_18000E970
0x18000e96b  call    ??$_delete@VESESession@@@tlx@@YAXPEAVESESession@@@Z; tlx::_delete<ESESession>(ESESession *)
0x18000e970  add     rsp, 20h
0x18000e974  pop     rbx
0x18000e975  retn
```
