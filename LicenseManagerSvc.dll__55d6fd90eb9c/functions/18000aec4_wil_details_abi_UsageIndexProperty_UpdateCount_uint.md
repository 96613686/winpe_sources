# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000aec4`
- end: `0x18000af0d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008774`
- `0x180009f68`
- `0x18000aa44`

## callees

- `0x180007b30`
- `0x18000aec4`

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
0x18000aec4  sub     rsp, 28h
0x18000aec8  lea     r8, [rcx+4]; Source
0x18000aecc  cmp     [r8], edx
0x18000aecf  jz      short loc_18000AF08
0x18000aed1  mov     al, [rcx+2]
0x18000aed4  mov     [r8], edx
0x18000aed7  cmp     al, 1
0x18000aed9  jnz     short loc_18000AEF3
0x18000aedb  mov     r9d, 2
0x18000aee1  mov     [rsp+28h+arg_8], dx
0x18000aee6  movzx   eax, dx
0x18000aee9  lea     r8, [rsp+28h+arg_8]
0x18000aeee  mov     edx, r9d
0x18000aef1  jmp     short loc_18000AEFF
0x18000aef3  cmp     al, 2
0x18000aef5  jnz     short loc_18000AF08
0x18000aef7  mov     edx, 4; DestinationSize
0x18000aefc  mov     r9d, edx; SourceSize
0x18000aeff  mov     rcx, [rcx+10h]; Destination
0x18000af03  call    memcpy_s
0x18000af08  add     rsp, 28h
0x18000af0c  retn
```
