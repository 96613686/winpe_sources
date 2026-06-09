# DeviceCollectionFormatDeviceText(DEVICE_COLLECTION *,ulong,ushort *,ulong,ushort *)

- ea: `0x180002de8`
- end: `0x180002e52`
- name: `?DeviceCollectionFormatDeviceText@@YAHPEAUDEVICE_COLLECTION@@KPEAGK1@Z`
- size: `106`
- prototype: `int(struct DEVICE_COLLECTION *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006bd0`
- `0x180007c20`
- `0x180007f1c`

## callees

- `0x180002de8`
- `0x180003048`

## pseudocode

```c
__int64 __fastcall DeviceCollectionFormatDeviceText(
        struct DEVICE_COLLECTION **a1,
        int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  struct DEVICE_COLLECTION *v5; // rax
  int v6; // r10d
  unsigned __int64 v7; // rdi
  __int64 v9; // r9

  v5 = *a1;
  v6 = 0;
  v7 = a4;
  while ( 1 )
  {
    if ( v5 == (struct DEVICE_COLLECTION *)a1 )
    {
      *a5 = 0;
      return 0;
    }
    if ( v6 == a2 )
      break;
    v5 = *(struct DEVICE_COLLECTION **)v5;
    ++v6;
  }
  v9 = *((_QWORD *)v5 + 53);
  if ( !v9 )
    v9 = (__int64)v5 + 16;
  StringCchPrintfW(a5, v7, a3, v9);
  a5[(unsigned int)(v7 - 1)] = 0;
  return 1;
}

```

## disassembly

```asm
0x180002de8  mov     [rsp+arg_0], rbx
0x180002ded  push    rdi
0x180002dee  sub     rsp, 20h
0x180002df2  mov     rax, [rcx]
0x180002df5  xor     r10d, r10d
0x180002df8  mov     edi, r9d
0x180002dfb  jmp     short loc_180002E08
0x180002dfd  cmp     r10d, edx
0x180002e00  jz      short loc_180002E24
0x180002e02  mov     rax, [rax]
0x180002e05  inc     r10d
0x180002e08  cmp     rax, rcx
0x180002e0b  jnz     short loc_180002DFD
0x180002e0d  mov     rax, [rsp+28h+arg_20]
0x180002e12  xor     ecx, ecx
0x180002e14  mov     [rax], cx
0x180002e17  xor     eax, eax
0x180002e19  mov     rbx, [rsp+28h+arg_0]
0x180002e1e  add     rsp, 20h
0x180002e22  pop     rdi
0x180002e23  retn
0x180002e24  mov     r9, [rax+1A8h]
0x180002e2b  test    r9, r9
0x180002e2e  jnz     short loc_180002E34
0x180002e30  lea     r9, [rax+10h]
0x180002e34  mov     rbx, [rsp+28h+arg_20]
0x180002e39  mov     rdx, rdi; unsigned __int64
0x180002e3c  mov     rcx, rbx; unsigned __int16 *
0x180002e3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002e44  xor     ecx, ecx
0x180002e46  lea     edx, [rdi-1]
0x180002e49  mov     [rbx+rdx*2], cx
0x180002e4d  lea     eax, [rcx+1]
0x180002e50  jmp     short loc_180002E19
```
