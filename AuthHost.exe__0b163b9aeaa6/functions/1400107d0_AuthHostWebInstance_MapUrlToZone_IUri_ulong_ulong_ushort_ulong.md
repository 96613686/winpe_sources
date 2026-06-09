# AuthHostWebInstance::MapUrlToZone(IUri *,ulong *,ulong,ushort * *,ulong *)

- ea: `0x1400107d0`
- end: `0x14001080b`
- name: `?MapUrlToZone@AuthHostWebInstance@@UEAAJPEAUIUri@@PEAKKPEAPEAG1@Z`
- size: `59`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, struct IUri *, unsigned int *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400055c0`

## callees

- `0x1400107d0`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::MapUrlToZone(
        AuthHostWebInstance *this,
        struct IUri *a2,
        unsigned int *a3,
        __int64 a4,
        unsigned __int16 **a5,
        unsigned int *a6)
{
  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  *a3 = 3;
  return 0;
}

```

## disassembly

```asm
0x1400107d0  test    rdx, rdx
0x1400107d3  jz      short loc_140010805
0x1400107d5  test    r8, r8
0x1400107d8  jz      short loc_140010805
0x1400107da  mov     rax, [rsp+arg_20]
0x1400107df  test    rax, rax
0x1400107e2  jz      short loc_1400107EB
0x1400107e4  mov     qword ptr [rax], 0
0x1400107eb  mov     rax, [rsp+arg_28]
0x1400107f0  test    rax, rax
0x1400107f3  jz      short loc_1400107FB
0x1400107f5  mov     dword ptr [rax], 0
0x1400107fb  mov     dword ptr [r8], 3
0x140010802  xor     eax, eax
0x140010804  retn
0x140010805  mov     eax, 80070057h
0x14001080a  retn
```
