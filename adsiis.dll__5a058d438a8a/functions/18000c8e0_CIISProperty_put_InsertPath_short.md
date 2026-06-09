# CIISProperty::put_InsertPath(short)

- ea: `0x18000c8e0`
- end: `0x18000c943`
- name: `?put_InsertPath@CIISProperty@@UEAAJF@Z`
- size: `99`
- prototype: `__int64 __fastcall(CIISProperty *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c8e0`
- `0x18001b5ac`

## pseudocode

```c
__int64 __fastcall CIISProperty::put_InsertPath(CIISProperty *this, __int16 a2)
{
  __int64 result; // rax
  unsigned int v5; // ecx
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  if ( (int)IIsSchema::PropNameWToId(*((IIsSchema **)this + 25), *((const unsigned __int16 **)this + 28), &v6) >= 0 )
    return 2147500037LL;
  v5 = *((_DWORD *)this + 33) | 0x40;
  if ( a2 != -1 )
    v5 = *((_DWORD *)this + 33) & 0xFFFFFFBF;
  result = 0;
  *((_DWORD *)this + 33) = v5;
  return result;
}

```

## disassembly

```asm
0x18000c8e0  mov     [rsp+arg_8], rbx
0x18000c8e5  push    rdi
0x18000c8e6  sub     rsp, 20h
0x18000c8ea  movzx   edi, dx
0x18000c8ed  mov     [rsp+28h+arg_0], 0
0x18000c8f5  mov     rdx, [rcx+0E0h]; unsigned __int16 *
0x18000c8fc  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x18000c901  mov     rbx, rcx
0x18000c904  mov     rcx, [rcx+0C8h]; this
0x18000c90b  call    ?PropNameWToId@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::PropNameWToId(ushort const *,ulong *)
0x18000c910  test    eax, eax
0x18000c912  js      short loc_18000C91B
0x18000c914  mov     eax, 80004005h
0x18000c919  jmp     short loc_18000C938
0x18000c91b  mov     ecx, [rbx+84h]
0x18000c921  mov     eax, ecx
0x18000c923  and     eax, 0FFFFFFBFh
0x18000c926  or      ecx, 40h
0x18000c929  cmp     di, 0FFFFh
0x18000c92d  cmovnz  ecx, eax
0x18000c930  xor     eax, eax
0x18000c932  mov     [rbx+84h], ecx
0x18000c938  mov     rbx, [rsp+28h+arg_8]
0x18000c93d  add     rsp, 20h
0x18000c941  pop     rdi
0x18000c942  retn
```
