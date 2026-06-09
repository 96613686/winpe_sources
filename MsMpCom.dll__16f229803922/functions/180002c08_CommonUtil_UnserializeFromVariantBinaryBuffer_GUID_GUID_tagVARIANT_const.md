# CommonUtil::UnserializeFromVariantBinaryBuffer<_GUID>(_GUID *,tagVARIANT const &)

- ea: `0x180002c08`
- end: `0x180002c63`
- name: `??$UnserializeFromVariantBinaryBuffer@U_GUID@@@CommonUtil@@YAJPEAU_GUID@@AEBUtagVARIANT@@@Z`
- size: `91`
- prototype: `__int64 __fastcall(void *, CommonUtil *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003200`

## callees

- `0x180001cf2`
- `0x180002c08`
- `0x180008de0`

## pseudocode

```c
__int64 __fastcall CommonUtil::UnserializeFromVariantBinaryBuffer<_GUID>(
        void *a1,
        CommonUtil *this,
        __int64 a3,
        unsigned __int64 *a4)
{
  __int64 result; // rax
  const void *v6; // [rsp+40h] [rbp+18h] BYREF
  void *Src; // [rsp+48h] [rbp+20h] BYREF

  Src = 0;
  v6 = 0;
  result = CommonUtil::VariantExtractBinaryBuffer(this, (const struct tagVARIANT *)&Src, &v6, a4);
  if ( (int)result >= 0 )
  {
    if ( v6 == (const void *)16 )
    {
      memmove_0(a1, Src, 0x10u);
      return 0;
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002c08  mov     r11, rsp
0x180002c0b  push    rbx
0x180002c0c  sub     rsp, 20h
0x180002c10  mov     rax, rdx
0x180002c13  mov     qword ptr [r11+20h], 0
0x180002c1b  mov     rbx, rcx
0x180002c1e  mov     qword ptr [r11+18h], 0
0x180002c26  mov     rcx, rax; this
0x180002c29  lea     r8, [r11+18h]; void **
0x180002c2d  lea     rdx, [r11+20h]; struct tagVARIANT *
0x180002c31  call    ?VariantExtractBinaryBuffer@CommonUtil@@YAJAEBUtagVARIANT@@PEAPEBXPEA_K@Z; CommonUtil::VariantExtractBinaryBuffer(tagVARIANT const &,void const * *,unsigned __int64 *)
0x180002c36  test    eax, eax
0x180002c38  js      short loc_180002C5D
0x180002c3a  mov     r8d, 10h; Size
0x180002c40  cmp     [rsp+28h+arg_10], r8
0x180002c45  jz      short loc_180002C4E
0x180002c47  mov     eax, 80070057h
0x180002c4c  jmp     short loc_180002C5D
0x180002c4e  mov     rdx, [rsp+28h+Src]; Src
0x180002c53  mov     rcx, rbx; void *
0x180002c56  call    memmove_0
0x180002c5b  xor     eax, eax
0x180002c5d  add     rsp, 20h
0x180002c61  pop     rbx
0x180002c62  retn
```
