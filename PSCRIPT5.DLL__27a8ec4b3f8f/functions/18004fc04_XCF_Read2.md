# XCF_Read2

- ea: `0x18004fc04`
- end: `0x18004fc52`
- name: `XCF_Read2`
- size: `78`
- prototype: `__int16 __fastcall(_JBTYPE *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180047c38`
- `0x180047e54`
- `0x180047ff4`
- `0x180048380`
- `0x180048544`
- `0x18004f980`

## callees

- `0x18004f8e4`
- `0x18004fc04`

## pseudocode

```c
__int16 __fastcall XCF_Read2(_JBTYPE *a1)
{
  unsigned __int8 *v1; // rdx
  unsigned __int64 v3; // r9
  __int16 v4; // ax
  unsigned __int8 *v5; // rdx
  __int16 v6; // cx

  v1 = (unsigned __int8 *)a1[885].Part[0];
  v3 = (unsigned __int64)(v1 + 2);
  if ( (unsigned __int64)(v1 + 2) > a1[884].Part[1] )
    XCF_FatalErrorHandler(a1, 1);
  v4 = *v1;
  v5 = v1 + 1;
  a1[885].Part[0] = (unsigned __int64)v5;
  v6 = *v5;
  a1[885].Part[0] = v3;
  return v6 + (v4 << 8);
}

```

## disassembly

```asm
0x18004fc04  sub     rsp, 28h
0x18004fc08  mov     rdx, [rcx+3750h]
0x18004fc0f  mov     r8, rcx
0x18004fc12  lea     r9, [rdx+2]
0x18004fc16  cmp     r9, [rcx+3748h]
0x18004fc1d  ja      short loc_18004FC47
0x18004fc1f  movzx   eax, byte ptr [rdx]
0x18004fc22  inc     rdx
0x18004fc25  mov     [rcx+3750h], rdx
0x18004fc2c  mov     ecx, 100h
0x18004fc31  imul    eax, ecx
0x18004fc34  movzx   ecx, byte ptr [rdx]
0x18004fc37  mov     [r8+3750h], r9
0x18004fc3e  add     ax, cx
0x18004fc41  add     rsp, 28h
0x18004fc45  retn
0x18004fc47  mov     edx, 1
0x18004fc4c  call    XCF_FatalErrorHandler
```
