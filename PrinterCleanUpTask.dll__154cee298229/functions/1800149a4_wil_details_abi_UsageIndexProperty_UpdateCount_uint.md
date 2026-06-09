# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1800149a4`
- end: `0x1800149ed`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180012604`
- `0x180013bb0`
- `0x180014224`

## callees

- `0x180005920`
- `0x1800149a4`

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
0x1800149a4  sub     rsp, 28h
0x1800149a8  lea     r8, [rcx+4]; Source
0x1800149ac  cmp     [r8], edx
0x1800149af  jz      short loc_1800149E8
0x1800149b1  mov     al, [rcx+2]
0x1800149b4  mov     [r8], edx
0x1800149b7  cmp     al, 1
0x1800149b9  jnz     short loc_1800149D3
0x1800149bb  mov     r9d, 2
0x1800149c1  mov     [rsp+28h+arg_8], dx
0x1800149c6  movzx   eax, dx
0x1800149c9  lea     r8, [rsp+28h+arg_8]
0x1800149ce  mov     edx, r9d
0x1800149d1  jmp     short loc_1800149DF
0x1800149d3  cmp     al, 2
0x1800149d5  jnz     short loc_1800149E8
0x1800149d7  mov     edx, 4; DestinationSize
0x1800149dc  mov     r9d, edx; SourceSize
0x1800149df  mov     rcx, [rcx+10h]; Destination
0x1800149e3  call    memcpy_s
0x1800149e8  add     rsp, 28h
0x1800149ec  retn
```
