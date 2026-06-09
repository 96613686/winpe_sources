# CommonUtil::CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<ushort *>>::~CUniqueHandle<CommonUtil::CAutoUniqueArrayPtrDelete2<ushort *>>(void)

- ea: `0x1400029a0`
- end: `0x1400029b6`
- name: `??1?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEAG@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140012331`
- `0x140012378`

## callees

- `0x1400015f4`
- `0x1400029a0`

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
0x1400029a0  sub     rsp, 28h
0x1400029a4  mov     rcx, [rcx]; void *
0x1400029a7  test    rcx, rcx
0x1400029aa  jz      short loc_1400029B1
0x1400029ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400029b1  add     rsp, 28h
0x1400029b5  retn
```
