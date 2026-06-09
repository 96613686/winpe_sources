# CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::~CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>(void)

- ea: `0x180014fd0`
- end: `0x180015051`
- name: `??1?$CTSparseBlock@KPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@$0BE@$00@@QEAA@XZ`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015058`
- `0x1800153f0`

## callees

- `0x180001ee8`
- `0x180014fd0`
- `0x180040010`

## pseudocode

```c
void **__fastcall CTSparseBlock<unsigned long,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::~CTSparseBlock<unsigned long,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>(
        __int64 a1)
{
  bool v1; // zf
  void **result; // rax
  __int64 v4; // rdi
  __int64 v5; // rdx

  v1 = *(_DWORD *)(a1 + 8) == 0;
  result = &CTPtrArray<CASFStreamPropertiesObjectExv1::_STREAM_NAME,20>::`vftable';
  *(_QWORD *)a1 = &CTPtrArray<CASFStreamPropertiesObjectExv1::_STREAM_NAME,20>::`vftable';
  if ( v1 )
  {
    *(_DWORD *)(a1 + 12) &= ~1u;
    *(_DWORD *)(a1 + 8) = 0;
    *(_WORD *)(a1 + 24) = 0;
    *(_BYTE *)(a1 + 26) = 0;
    result = (void **)memset_0((void *)(a1 + 32), 0, 0xA0u);
    v4 = *(_QWORD *)(a1 + 192);
    *(_QWORD *)(a1 + 192) = 0;
    do
    {
      if ( !v4 )
        break;
      v5 = v4;
      v4 = *(_QWORD *)(v4 + 192);
      result = (void **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, v5);
    }
    while ( (int)result >= 0 );
  }
  return result;
}

```

## disassembly

```asm
0x180014fd0  mov     [rsp+arg_0], rbx
0x180014fd5  push    rdi
0x180014fd6  sub     rsp, 20h
0x180014fda  cmp     dword ptr [rcx+8], 0
0x180014fde  lea     rax, ??_7?$CTPtrArray@U_STREAM_NAME@CASFStreamPropertiesObjectExv1@@$0BE@@@6B@; const CTPtrArray<CASFStreamPropertiesObjectExv1::_STREAM_NAME,20>::`vftable'
0x180014fe5  mov     [rcx], rax
0x180014fe8  mov     rbx, rcx
0x180014feb  jnz     short loc_180015046
0x180014fed  and     dword ptr [rcx+0Ch], 0FFFFFFFEh
0x180014ff1  xor     eax, eax
0x180014ff3  mov     dword ptr [rcx+8], 0
0x180014ffa  xor     edx, edx; Val
0x180014ffc  mov     [rcx+18h], ax
0x180015000  mov     r8d, 0A0h; Size
0x180015006  mov     [rcx+1Ah], al
0x180015009  add     rcx, 20h ; ' '; void *
0x18001500d  call    memset_0
0x180015012  mov     rdi, [rbx+0C0h]
0x180015019  mov     qword ptr [rbx+0C0h], 0
0x180015024  test    rdi, rdi
0x180015027  jz      short loc_180015046
0x180015029  mov     rax, [rbx]
0x18001502c  mov     rdx, rdi
0x18001502f  mov     rdi, [rdi+0C0h]
0x180015036  mov     rcx, rbx
0x180015039  mov     rax, [rax+8]
0x18001503d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015042  test    eax, eax
0x180015044  jns     short loc_180015024
0x180015046  mov     rbx, [rsp+28h+arg_0]
0x18001504b  add     rsp, 20h
0x18001504f  pop     rdi
0x180015050  retn
```
