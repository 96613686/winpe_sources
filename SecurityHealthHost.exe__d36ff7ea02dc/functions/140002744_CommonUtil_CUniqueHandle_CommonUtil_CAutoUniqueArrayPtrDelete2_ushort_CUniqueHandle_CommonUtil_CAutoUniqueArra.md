# CommonUtil::CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<ushort *>>::~CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<ushort *>>(void)

- ea: `0x140002744`
- end: `0x14000275a`
- name: `??1?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEAG@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000fc54`
- `0x14000fc9b`

## callees

- `0x140001614`
- `0x140002744`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<unsigned short *>>::~CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<unsigned short *>>(
        void **a1,
        unsigned __int64 a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x140002744  sub     rsp, 28h
0x140002748  mov     rcx, [rcx]; void *
0x14000274b  test    rcx, rcx
0x14000274e  jz      short loc_140002755
0x140002750  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002755  add     rsp, 28h
0x140002759  retn
```
