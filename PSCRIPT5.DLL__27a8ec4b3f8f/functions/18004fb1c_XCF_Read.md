# XCF_Read

- ea: `0x18004fb1c`
- end: `0x18004fbbc`
- name: `XCF_Read`
- size: `160`
- prototype: `__int64 __fastcall(_JBTYPE *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180047c38`
- `0x180048608`
- `0x180049fe4`
- `0x18004f980`

## callees

- `0x18004f8e4`
- `0x18004fb1c`

## pseudocode

```c
__int64 __fastcall XCF_Read(_JBTYPE *a1, int a2)
{
  unsigned __int8 *v3; // rcx
  int v4; // r8d
  int v5; // edx
  int v6; // edx
  int v7; // edx
  __int64 result; // rax

  v3 = (unsigned __int8 *)a1[885].Part[0];
  if ( (unsigned __int64)&v3[a2] > a1[884].Part[1] )
    XCF_FatalErrorHandler(a1, 1);
  v4 = 0;
  v5 = a2 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 != 1 )
          XCF_FatalErrorHandler(a1, 20);
        v4 = *v3++ << 8;
        a1[885].Part[0] = (unsigned __int64)v3;
      }
      v4 = (*v3++ + v4) << 8;
      a1[885].Part[0] = (unsigned __int64)v3;
    }
    v4 = (*v3++ + v4) << 8;
    a1[885].Part[0] = (unsigned __int64)v3;
  }
  result = v4 + (unsigned int)*v3;
  a1[885].Part[0] = (unsigned __int64)(v3 + 1);
  return result;
}

```

## disassembly

```asm
0x18004fb1c  sub     rsp, 28h
0x18004fb20  mov     r9, rcx
0x18004fb23  movsxd  rax, edx
0x18004fb26  mov     rcx, [rcx+3750h]
0x18004fb2d  add     rax, rcx
0x18004fb30  cmp     rax, [r9+3748h]
0x18004fb37  ja      short loc_18004FBA0
0x18004fb39  xor     r8d, r8d
0x18004fb3c  sub     edx, 1
0x18004fb3f  jz      short loc_18004FB8A
0x18004fb41  sub     edx, 1
0x18004fb44  jz      short loc_18004FB76
0x18004fb46  sub     edx, 1
0x18004fb49  jz      short loc_18004FB62
0x18004fb4b  cmp     edx, 1
0x18004fb4e  jnz     short loc_18004FBAE
0x18004fb50  movzx   r8d, byte ptr [rcx]
0x18004fb54  shl     r8d, 8
0x18004fb58  inc     rcx
0x18004fb5b  mov     [r9+3750h], rcx
0x18004fb62  movzx   eax, byte ptr [rcx]
0x18004fb65  add     r8d, eax
0x18004fb68  shl     r8d, 8
0x18004fb6c  inc     rcx
0x18004fb6f  mov     [r9+3750h], rcx
0x18004fb76  movzx   eax, byte ptr [rcx]
0x18004fb79  add     r8d, eax
0x18004fb7c  shl     r8d, 8
0x18004fb80  inc     rcx
0x18004fb83  mov     [r9+3750h], rcx
0x18004fb8a  movzx   eax, byte ptr [rcx]
0x18004fb8d  add     eax, r8d
0x18004fb90  inc     rcx
0x18004fb93  mov     [r9+3750h], rcx
0x18004fb9a  add     rsp, 28h
0x18004fb9e  retn
0x18004fba0  mov     edx, 1
0x18004fba5  mov     rcx, r9
0x18004fba8  call    XCF_FatalErrorHandler
0x18004fbae  mov     edx, 14h
0x18004fbb3  mov     rcx, r9
0x18004fbb6  call    XCF_FatalErrorHandler
```
