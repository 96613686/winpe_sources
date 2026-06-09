# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000a2f0`
- end: `0x18000a339`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180004aac`
- `0x180008428`
- `0x180009a18`

## callees

- `0x18000a2f0`
- `0x18000b43c`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexProperty::UpdateCount(wil::details_abi::UsageIndexProperty *this, int a2)
{
  __int16 *v2; // r8
  char v3; // al
  rsize_t v4; // r9
  rsize_t v5; // rdx
  __int16 v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (__int16 *)((char *)this + 4);
  if ( *((_DWORD *)this + 1) != a2 )
  {
    v3 = *((_BYTE *)this + 2);
    *(_DWORD *)v2 = a2;
    if ( v3 == 1 )
    {
      v4 = 2;
      v6 = a2;
      v2 = &v6;
      v5 = 2;
    }
    else
    {
      if ( v3 != 2 )
        return;
      v5 = 4;
      v4 = 4;
    }
    memcpy_s(*((void *const *)this + 2), v5, v2, v4);
  }
}

```

## disassembly

```asm
0x18000a2f0  sub     rsp, 28h
0x18000a2f4  lea     r8, [rcx+4]; Source
0x18000a2f8  cmp     [r8], edx
0x18000a2fb  jz      short loc_18000A334
0x18000a2fd  mov     al, [rcx+2]
0x18000a300  mov     [r8], edx
0x18000a303  cmp     al, 1
0x18000a305  jnz     short loc_18000A31F
0x18000a307  mov     r9d, 2
0x18000a30d  mov     [rsp+28h+arg_8], dx
0x18000a312  movzx   eax, dx
0x18000a315  lea     r8, [rsp+28h+arg_8]
0x18000a31a  mov     edx, r9d
0x18000a31d  jmp     short loc_18000A32B
0x18000a31f  cmp     al, 2
0x18000a321  jnz     short loc_18000A334
0x18000a323  mov     edx, 4; DestinationSize
0x18000a328  mov     r9d, edx; SourceSize
0x18000a32b  mov     rcx, [rcx+10h]; Destination
0x18000a32f  call    memcpy_s
0x18000a334  add     rsp, 28h
0x18000a338  retn
```
