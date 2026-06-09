# MpConfigUtils::CRefCachedConfigKey::`vector deleting destructor'(uint)

- ea: `0x1800060a0`
- end: `0x1800060f4`
- name: `??_ECRefCachedConfigKey@MpConfigUtils@@UEAAPEAXI@Z`
- size: `84`
- prototype: `void *__fastcall(MpConfigUtils::CRefCachedConfigKey *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800060a0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800060b8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800060b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800060e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800060e0`
- `mpclient!MpConfigClose` at `0x1800060c7`
- `mpclient!MpConfigClose` at `0x1800060c7`

## pseudocode

```c
MpConfigUtils::CRefCachedConfigKey *__fastcall MpConfigUtils::CRefCachedConfigKey::`vector deleting destructor'(
        MpConfigUtils::CRefCachedConfigKey *this,
        char a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    operator delete[](v4);
  if ( *((_QWORD *)this + 2) )
    MpConfigClose();
  *(_QWORD *)this = &CommonUtil::CRefObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800060a0  mov     [rsp+arg_0], rbx
0x1800060a5  push    rdi
0x1800060a6  sub     rsp, 20h
0x1800060aa  mov     rbx, rcx
0x1800060ad  mov     edi, edx
0x1800060af  mov     rcx, [rcx+18h]
0x1800060b3  test    rcx, rcx
0x1800060b6  jz      short loc_1800060BE
0x1800060b8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800060be  mov     rcx, [rbx+10h]
0x1800060c2  test    rcx, rcx
0x1800060c5  jz      short loc_1800060CD
0x1800060c7  call    cs:__imp_MpConfigClose
0x1800060cd  lea     rax, ??_7CRefObject@CommonUtil@@6B@; const CommonUtil::CRefObject::`vftable'
0x1800060d4  mov     [rbx], rax
0x1800060d7  test    dil, 1
0x1800060db  jz      short loc_1800060E6
0x1800060dd  mov     rcx, rbx
0x1800060e0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800060e6  mov     rax, rbx
0x1800060e9  mov     rbx, [rsp+28h+arg_0]
0x1800060ee  add     rsp, 20h
0x1800060f2  pop     rdi
0x1800060f3  retn
```
