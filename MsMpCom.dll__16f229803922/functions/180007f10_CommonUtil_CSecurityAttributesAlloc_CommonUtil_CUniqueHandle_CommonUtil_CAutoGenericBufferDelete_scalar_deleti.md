# CommonUtil::CSecurityAttributesAlloc<CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>>::`scalar deleting destructor'(uint)

- ea: `0x180007f10`
- end: `0x180007f67`
- name: `??_G?$CSecurityAttributesAlloc@V?$CUniqueHandle@UCAutoGenericBufferDelete@CommonUtil@@@CommonUtil@@@CommonUtil@@UEAAPEAXI@Z`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007f10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007f3a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f53`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f3a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f53`

## pseudocode

```c
_QWORD *__fastcall CommonUtil::CSecurityAttributesAlloc<CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  void *v4; // rcx

  *a1 = &CommonUtil::CSecurityAttributesAlloc<CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>>::`vftable';
  v4 = (void *)a1[2];
  a1[2] = 0;
  if ( v4 )
    operator delete(v4);
  *a1 = &CommonUtil::CRefObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180007f10  mov     [rsp+arg_0], rbx
0x180007f15  push    rdi
0x180007f16  sub     rsp, 20h
0x180007f1a  mov     rbx, rcx
0x180007f1d  lea     rax, ??_7?$CSecurityAttributesAlloc@V?$CUniqueHandle@UCAutoGenericBufferDelete@CommonUtil@@@CommonUtil@@@CommonUtil@@6B@; const CommonUtil::CSecurityAttributesAlloc<CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>>::`vftable'
0x180007f24  mov     [rcx], rax
0x180007f27  mov     edi, edx
0x180007f29  mov     rcx, [rcx+10h]
0x180007f2d  mov     qword ptr [rbx+10h], 0
0x180007f35  test    rcx, rcx
0x180007f38  jz      short loc_180007F40
0x180007f3a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007f40  lea     rax, ??_7CRefObject@CommonUtil@@6B@; const CommonUtil::CRefObject::`vftable'
0x180007f47  mov     [rbx], rax
0x180007f4a  test    dil, 1
0x180007f4e  jz      short loc_180007F59
0x180007f50  mov     rcx, rbx
0x180007f53  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007f59  mov     rax, rbx
0x180007f5c  mov     rbx, [rsp+28h+arg_0]
0x180007f61  add     rsp, 20h
0x180007f65  pop     rdi
0x180007f66  retn
```
