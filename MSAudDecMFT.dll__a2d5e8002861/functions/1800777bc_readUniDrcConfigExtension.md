# _readUniDrcConfigExtension

- ea: `0x1800777bc`
- end: `0x1800778a5`
- name: `_readUniDrcConfigExtension`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800783f8`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012264`
- `0x180076548`
- `0x1800777bc`

## pseudocode

```c
__int64 __fastcall readUniDrcConfigExtension(int *a1, __int64 a2, __int64 a3)
{
  int v3; // esi
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r8
  int v10; // r14d
  __int64 result; // rax
  __int64 v12; // r8

  v3 = 0;
  *(_BYTE *)(a2 + 21044) = CDKreadBits(a1, 4, a3);
  while ( *(_BYTE *)(a2 + v3 + 21044) )
  {
    if ( v3 >= 7 )
      return 4294967199LL;
    v7 = CDKreadBits(a1, 4, v6);
    *(_DWORD *)(a2 + 4LL * v3 + 21052) = CDKreadBits(a1, (unsigned int)(v7 + 4), v8) + 1;
    CDKsyncCache_0(a1);
    if ( *(_BYTE *)(a2 + v3 + 21044) == 2 )
    {
      v10 = a1[2];
      result = readDrcExtensionV1(a1, a2, v9);
      if ( (_DWORD)result )
        return result;
      CDKsyncCache_0(a1);
      if ( v10 != a1[2] + *(_DWORD *)(a2 + 4LL * v3 + 21052) )
        return 4294967196LL;
    }
    else
    {
      CDKpushFor(a1, *(unsigned int *)(a2 + 4LL * v3 + 21052));
    }
    *(_BYTE *)(++v3 + a2 + 21044) = CDKreadBits(a1, 4, v12);
  }
  return 0;
}

```

## disassembly

```asm
0x1800777bc  push    rbx
0x1800777be  push    rbp
0x1800777bf  push    rsi
0x1800777c0  push    rdi
0x1800777c1  push    r14
0x1800777c3  sub     rsp, 20h
0x1800777c7  xor     esi, esi
0x1800777c9  mov     rdi, rdx
0x1800777cc  mov     rbx, rcx
0x1800777cf  lea     edx, [rsi+4]
0x1800777d2  call    CDKreadBits
0x1800777d7  mov     [rdi+5234h], al
0x1800777dd  movsxd  rbp, esi
0x1800777e0  cmp     byte ptr [rdi+rbp+5234h], 0
0x1800777e8  jz      loc_180077897
0x1800777ee  cmp     esi, 7
0x1800777f1  jge     loc_180077890
0x1800777f7  mov     edx, 4
0x1800777fc  mov     rcx, rbx
0x1800777ff  call    CDKreadBits
0x180077804  mov     rcx, rbx
0x180077807  lea     edx, [rax+4]
0x18007780a  call    CDKreadBits
0x18007780f  inc     eax
0x180077811  mov     rcx, rbx
0x180077814  mov     [rdi+rbp*4+523Ch], eax
0x18007781b  call    CDKsyncCache_0
0x180077820  movzx   ecx, byte ptr [rdi+rbp+5234h]
0x180077828  sub     ecx, 1
0x18007782b  jz      short loc_180077863
0x18007782d  cmp     ecx, 1
0x180077830  jnz     short loc_180077863
0x180077832  mov     r14d, [rbx+8]
0x180077836  mov     rdx, rdi
0x180077839  mov     rcx, rbx
0x18007783c  call    _readDrcExtensionV1
0x180077841  test    eax, eax
0x180077843  jnz     short loc_180077899
0x180077845  mov     rcx, rbx
0x180077848  call    CDKsyncCache_0
0x18007784d  mov     eax, [rdi+rbp*4+523Ch]
0x180077854  add     eax, [rbx+8]
0x180077857  cmp     r14d, eax
0x18007785a  jz      short loc_180077872
0x18007785c  mov     eax, 0FFFFFF9Ch
0x180077861  jmp     short loc_180077899
0x180077863  mov     edx, [rdi+rbp*4+523Ch]
0x18007786a  mov     rcx, rbx
0x18007786d  call    CDKpushFor
0x180077872  inc     esi
0x180077874  mov     edx, 4
0x180077879  mov     rcx, rbx
0x18007787c  call    CDKreadBits
0x180077881  movsxd  rcx, esi
0x180077884  mov     [rcx+rdi+5234h], al
0x18007788b  jmp     loc_1800777DD
0x180077890  mov     eax, 0FFFFFF9Fh
0x180077895  jmp     short loc_180077899
0x180077897  xor     eax, eax
0x180077899  add     rsp, 20h
0x18007789d  pop     r14
0x18007789f  pop     rdi
0x1800778a0  pop     rsi
0x1800778a1  pop     rbp
0x1800778a2  pop     rbx
0x1800778a3  retn
```
