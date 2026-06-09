# XCF_Read1

- ea: `0x18004fbc4`
- end: `0x18004fbfb`
- name: `XCF_Read1`
- size: `55`
- prototype: `char __fastcall(_JBTYPE *)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180047c38`
- `0x180047e54`
- `0x180047ff4`
- `0x180048380`
- `0x180048438`
- `0x180048544`
- `0x180048608`
- `0x18004f980`

## callees

- `0x18004f8e4`
- `0x18004fbc4`

## pseudocode

```c
char __fastcall XCF_Read1(_JBTYPE *a1)
{
  char *v2; // rcx
  char result; // al

  v2 = (char *)a1[885].Part[0];
  if ( (unsigned __int64)v2 >= a1[884].Part[1] )
    XCF_FatalErrorHandler(a1, 1);
  result = *v2;
  a1[885].Part[0] = (unsigned __int64)(v2 + 1);
  return result;
}

```

## disassembly

```asm
0x18004fbc4  sub     rsp, 28h
0x18004fbc8  mov     r8, rcx
0x18004fbcb  mov     rcx, [rcx+3750h]
0x18004fbd2  cmp     rcx, [r8+3748h]
0x18004fbd9  jnb     short loc_18004FBED
0x18004fbdb  mov     al, [rcx]
0x18004fbdd  inc     rcx
0x18004fbe0  mov     [r8+3750h], rcx
0x18004fbe7  add     rsp, 28h
0x18004fbeb  retn
0x18004fbed  mov     edx, 1
0x18004fbf2  mov     rcx, r8
0x18004fbf5  call    XCF_FatalErrorHandler
```
