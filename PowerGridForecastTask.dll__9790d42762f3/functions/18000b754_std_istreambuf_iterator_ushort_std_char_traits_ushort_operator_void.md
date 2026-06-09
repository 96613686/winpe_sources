# std::istreambuf_iterator<ushort,std::char_traits<ushort>>::operator*(void)

- ea: `0x18000b754`
- end: `0x18000b7b6`
- name: `??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ`
- size: `98`
- prototype: `__int64 __fastcall(__int64 *)`
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

- `0x18000b754`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall std::istreambuf_iterator<unsigned short>::operator*(__int64 *a1)
{
  __int64 v2; // rcx
  __int16 *v3; // rdx
  __int16 v4; // ax

  if ( !*((_BYTE *)a1 + 8) )
  {
    v2 = *a1;
    if ( !v2
      || ((v3 = **(__int16 ***)(v2 + 56)) == 0 || **(int **)(v2 + 80) <= 0
        ? (v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2))
        : (v4 = *v3),
          v4 == -1) )
    {
      *a1 = 0;
    }
    else
    {
      *((_WORD *)a1 + 5) = v4;
    }
    *((_BYTE *)a1 + 8) = 1;
  }
  return (__int64)a1 + 10;
}

```

## disassembly

```asm
0x18000b754  push    rbx
0x18000b756  sub     rsp, 20h
0x18000b75a  cmp     byte ptr [rcx+8], 0
0x18000b75e  mov     rbx, rcx
0x18000b761  jnz     short loc_18000B7AC
0x18000b763  mov     rcx, [rcx]
0x18000b766  test    rcx, rcx
0x18000b769  jz      short loc_18000B7A1
0x18000b76b  mov     rax, [rcx+38h]
0x18000b76f  mov     rdx, [rax]
0x18000b772  test    rdx, rdx
0x18000b775  jz      short loc_18000B785
0x18000b777  mov     rax, [rcx+50h]
0x18000b77b  cmp     dword ptr [rax], 0
0x18000b77e  jle     short loc_18000B785
0x18000b780  movzx   eax, word ptr [rdx]
0x18000b783  jmp     short loc_18000B791
0x18000b785  mov     rax, [rcx]
0x18000b788  mov     rax, [rax+30h]
0x18000b78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b791  mov     ecx, 0FFFFh
0x18000b796  cmp     ax, cx
0x18000b799  jz      short loc_18000B7A1
0x18000b79b  mov     [rbx+0Ah], ax
0x18000b79f  jmp     short loc_18000B7A8
0x18000b7a1  mov     qword ptr [rbx], 0
0x18000b7a8  mov     byte ptr [rbx+8], 1
0x18000b7ac  lea     rax, [rbx+0Ah]
0x18000b7b0  add     rsp, 20h
0x18000b7b4  pop     rbx
0x18000b7b5  retn
```
