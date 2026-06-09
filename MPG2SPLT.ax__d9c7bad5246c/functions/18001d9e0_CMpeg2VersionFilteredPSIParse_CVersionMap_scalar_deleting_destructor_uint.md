# CMpeg2VersionFilteredPSIParse::CVersionMap::`scalar deleting destructor'(uint)

- ea: `0x18001d9e0`
- end: `0x18001da57`
- name: `??_GCVersionMap@CMpeg2VersionFilteredPSIParse@@UEAAPEAXI@Z`
- size: `119`
- prototype: `void *__fastcall(CMpeg2VersionFilteredPSIParse::CVersionMap *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x18001d9e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001da05`
- `KERNEL32!DeleteCriticalSection` at `0x18001da05`

## pseudocode

```c
CMpeg2VersionFilteredPSIParse::CVersionMap *__fastcall CMpeg2VersionFilteredPSIParse::CVersionMap::`scalar deleting destructor'(
        CMpeg2VersionFilteredPSIParse::CVersionMap *this,
        char a2)
{
  __int64 **v4; // rdi
  __int64 *v5; // rcx
  __int64 v6; // rdx
  __int64 *v7; // rax

  *(_QWORD *)this = &TGenericMap<unsigned long,unsigned long,0,5,19>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  v4 = (__int64 **)((char *)this + 8);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == (__int64 *)v4 )
      break;
    v6 = *v5;
    v7 = (__int64 *)v5[1];
    *v7 = *v5;
    *(_QWORD *)(v6 + 8) = v7;
    operator delete(v5, 0x180u);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x1A8u);
  return this;
}

```

## disassembly

```asm
0x18001d9e0  mov     [rsp+arg_0], rbx
0x18001d9e5  mov     [rsp+arg_8], rsi
0x18001d9ea  push    rdi
0x18001d9eb  sub     rsp, 20h
0x18001d9ef  lea     rax, ??_7?$TGenericMap@KK$0A@$04$0BD@@@6B@; const TGenericMap<ulong,ulong,0,5,19>::`vftable'
0x18001d9f6  mov     rbx, rcx
0x18001d9f9  mov     [rcx], rax
0x18001d9fc  mov     esi, edx
0x18001d9fe  add     rcx, 180h; lpCriticalSection
0x18001da05  call    cs:__imp_DeleteCriticalSection
0x18001da0b  lea     rdi, [rbx+8]
0x18001da0f  mov     rcx, [rdi]; void *
0x18001da12  cmp     rcx, rdi
0x18001da15  jz      short loc_18001DA31
0x18001da17  mov     rdx, [rcx]
0x18001da1a  mov     rax, [rcx+8]
0x18001da1e  mov     [rax], rdx
0x18001da21  mov     [rdx+8], rax
0x18001da25  mov     edx, 180h; unsigned __int64
0x18001da2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001da2f  jmp     short loc_18001DA0F
0x18001da31  test    sil, 1
0x18001da35  jz      short loc_18001DA44
0x18001da37  mov     edx, 1A8h; unsigned __int64
0x18001da3c  mov     rcx, rbx; void *
0x18001da3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001da44  mov     rsi, [rsp+28h+arg_8]
0x18001da49  mov     rax, rbx
0x18001da4c  mov     rbx, [rsp+28h+arg_0]
0x18001da51  add     rsp, 20h
0x18001da55  pop     rdi
0x18001da56  retn
```
