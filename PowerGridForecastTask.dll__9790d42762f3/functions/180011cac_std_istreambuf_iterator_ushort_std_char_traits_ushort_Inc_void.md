# std::istreambuf_iterator<ushort,std::char_traits<ushort>>::_Inc(void)

- ea: `0x180011cac`
- end: `0x180011d11`
- name: `?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ`
- size: `101`
- prototype: `char __fastcall(__int64 *)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x180008c34`
- `0x180008e00`
- `0x18000d948`
- `0x18000e050`
- `0x18000e758`
- `0x18000eee8`
- `0x18000f678`
- `0x18000f850`
- `0x18000fa28`
- `0x18000fe64`
- `0x1800102a0`
- `0x18001046c`
- `0x18001108c`
- `0x180018d90`
- `0x180019340`
- `0x180019950`
- `0x180019b00`

## callees

- `0x180011cac`
- `0x180037010`

## pseudocode

```c
char __fastcall std::istreambuf_iterator<unsigned short>::_Inc(__int64 *a1)
{
  __int64 v2; // rcx
  int *v3; // rax
  __int16 **v4; // rcx
  __int16 *v5; // rdx
  __int16 v6; // ax
  char result; // al

  v2 = *a1;
  if ( !v2
    || (!**(_QWORD **)(v2 + 56) || (v3 = *(int **)(v2 + 80), *v3 <= 0)
      ? (v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2))
      : (--*v3, v4 = *(__int16 ***)(v2 + 56), v5 = *v4, ++*v4, v6 = *v5),
        v6 == -1) )
  {
    *a1 = 0;
    result = 1;
  }
  else
  {
    result = 0;
  }
  *((_BYTE *)a1 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x180011cac  push    rbx
0x180011cae  sub     rsp, 20h
0x180011cb2  mov     rbx, rcx
0x180011cb5  mov     rcx, [rcx]
0x180011cb8  test    rcx, rcx
0x180011cbb  jz      short loc_180011CFF
0x180011cbd  mov     rax, [rcx+38h]
0x180011cc1  cmp     qword ptr [rax], 0
0x180011cc5  jz      short loc_180011CE5
0x180011cc7  mov     rax, [rcx+50h]
0x180011ccb  cmp     dword ptr [rax], 0
0x180011cce  jle     short loc_180011CE5
0x180011cd0  dec     dword ptr [rax]
0x180011cd2  mov     rcx, [rcx+38h]
0x180011cd6  mov     rdx, [rcx]
0x180011cd9  lea     rax, [rdx+2]
0x180011cdd  mov     [rcx], rax
0x180011ce0  movzx   eax, word ptr [rdx]
0x180011ce3  jmp     short loc_180011CF1
0x180011ce5  mov     rax, [rcx]
0x180011ce8  mov     rax, [rax+38h]
0x180011cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cf1  mov     ecx, 0FFFFh
0x180011cf6  cmp     ax, cx
0x180011cf9  jz      short loc_180011CFF
0x180011cfb  xor     al, al
0x180011cfd  jmp     short loc_180011D08
0x180011cff  mov     qword ptr [rbx], 0
0x180011d06  mov     al, 1
0x180011d08  mov     [rbx+8], al
0x180011d0b  add     rsp, 20h
0x180011d0f  pop     rbx
0x180011d10  retn
```
