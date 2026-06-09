# std::shared_ptr<PCLmWriter::MemoryByteStream>::_Set_ptr_rep_and_enable_shared<PCLmWriter::MemoryByteStream>(PCLmWriter::MemoryByteStream * const,std::_Ref_count_base * const)

- ea: `0x180011008`
- end: `0x180011076`
- name: `??$_Set_ptr_rep_and_enable_shared@VMemoryByteStream@PCLmWriter@@@?$shared_ptr@VMemoryByteStream@PCLmWriter@@@std@@AEAAXQEAVMemoryByteStream@PCLmWriter@@QEAV_Ref_count_base@1@@Z`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800127d0`
- `0x180012880`

## callees

- `0x1800101cc`
- `0x180010204`
- `0x180011008`

## pseudocode

```c
void __fastcall std::shared_ptr<PCLmWriter::MemoryByteStream>::_Set_ptr_rep_and_enable_shared<PCLmWriter::MemoryByteStream>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rax
  volatile signed __int32 *v4; // rbx
  _QWORD *v5; // rax
  volatile signed __int32 *v6; // r8
  std::_Ref_count_base *v7; // rcx

  *a1 = a2;
  a1[1] = a3;
  if ( a2 )
  {
    v3 = *(_QWORD *)(a2 + 24);
    if ( !v3 || !*(_DWORD *)(v3 + 8) )
    {
      if ( a3 )
        _InterlockedIncrement((volatile signed __int32 *)(a3 + 8));
      v4 = (volatile signed __int32 *)a1[1];
      v5 = (_QWORD *)(a2 + 16);
      if ( v4 )
      {
        _InterlockedIncrement(v4 + 3);
        v6 = v4;
      }
      else
      {
        v6 = 0;
        a2 = 0;
      }
      *v5 = a2;
      v7 = (std::_Ref_count_base *)v5[1];
      v5[1] = v6;
      if ( v7 )
        std::_Ref_count_base::_Decwref(v7);
      if ( v4 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v4);
    }
  }
}

```

## disassembly

```asm
0x180011008  push    rbx
0x18001100a  sub     rsp, 20h
0x18001100e  mov     [rcx], rdx
0x180011011  mov     [rcx+8], r8
0x180011015  test    rdx, rdx
0x180011018  jz      short loc_180011070
0x18001101a  mov     rax, [rdx+18h]
0x18001101e  test    rax, rax
0x180011021  jz      short loc_180011029
0x180011023  cmp     dword ptr [rax+8], 0
0x180011027  jnz     short loc_180011070
0x180011029  test    r8, r8
0x18001102c  jz      short loc_180011033
0x18001102e  lock inc dword ptr [r8+8]
0x180011033  mov     rbx, [rcx+8]
0x180011037  lea     rax, [rdx+10h]
0x18001103b  test    rbx, rbx
0x18001103e  jz      short loc_180011049
0x180011040  lock inc dword ptr [rbx+0Ch]
0x180011044  mov     r8, rbx
0x180011047  jmp     short loc_18001104E
0x180011049  xor     r8d, r8d
0x18001104c  xor     edx, edx
0x18001104e  mov     [rax], rdx
0x180011051  mov     rcx, [rax+8]; this
0x180011055  mov     [rax+8], r8
0x180011059  test    rcx, rcx
0x18001105c  jz      short loc_180011063
0x18001105e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180011063  test    rbx, rbx
0x180011066  jz      short loc_180011070
0x180011068  mov     rcx, rbx; this
0x18001106b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011070  add     rsp, 20h
0x180011074  pop     rbx
0x180011075  retn
```
