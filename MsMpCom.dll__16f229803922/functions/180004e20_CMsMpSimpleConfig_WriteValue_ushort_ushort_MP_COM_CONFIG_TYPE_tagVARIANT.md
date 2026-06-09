# CMsMpSimpleConfig::WriteValue(ushort *,ushort *,_MP_COM_CONFIG_TYPE,tagVARIANT)

- ea: `0x180004e20`
- end: `0x180004f5a`
- name: `?WriteValue@CMsMpSimpleConfig@@UEAAJPEAG0W4_MP_COM_CONFIG_TYPE@@UtagVARIANT@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004e20`
- `0x18000a010`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CMsMpSimpleConfig::WriteValue(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ecx

  if ( !a2 || !a3 )
    return 2147500035LL;
  switch ( *(_WORD *)a5 )
  {
    case 8:
      if ( a4 != 2 )
        return 2147942487LL;
      v8 = *(_QWORD *)(a5 + 8);
      if ( !v8 )
        return 2147942487LL;
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      v6 = 2 * v9 + 2;
      break;
    case 0x13:
      if ( a4 != 1 )
        return 2147942487LL;
      v6 = 4;
      break;
    case 0x2011:
      if ( (unsigned int)(a4 - 3) > 1 )
        return 2147942487LL;
      v7 = *(_QWORD *)(a5 + 8);
      if ( !v7 )
        return 2147942487LL;
      v6 = *(unsigned int *)(v7 + 24);
      break;
    case 0x2012:
      if ( a4 != 3 )
        return 2147942487LL;
      v5 = *(_QWORD *)(a5 + 8);
      if ( !v5 )
        return 2147942487LL;
      v6 = 2LL * *(unsigned int *)(v5 + 24);
      break;
    default:
      return 2147942487LL;
  }
  if ( (unsigned int)v6 != v6 )
    return 2147942487LL;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16), a2);
  v11 = 0;
  if ( v10 < 0 )
    return (unsigned int)v10;
  return v11;
}

```

## disassembly

```asm
0x180004e20  mov     [rsp+arg_0], rbx
0x180004e25  mov     [rsp+arg_8], rsi
0x180004e2a  push    rdi
0x180004e2b  sub     rsp, 40h
0x180004e2f  xor     esi, esi
0x180004e31  mov     r11d, r9d
0x180004e34  mov     rdi, rdx
0x180004e37  test    rdx, rdx
0x180004e3a  jz      loc_180004F45
0x180004e40  test    r8, r8
0x180004e43  jz      loc_180004F45
0x180004e49  mov     rbx, [rsp+48h+arg_20]
0x180004e4e  movzx   r10d, word ptr [rbx]
0x180004e52  sub     r10d, 8
0x180004e56  jz      loc_180004EE7
0x180004e5c  sub     r10d, 0Bh
0x180004e60  jz      short loc_180004ED2
0x180004e62  sub     r10d, 1FFEh
0x180004e69  jz      short loc_180004E9B
0x180004e6b  cmp     r10d, 1
0x180004e6f  jnz     loc_180004F3E
0x180004e75  lea     r9d, [rsi+3]
0x180004e79  cmp     r11d, r9d
0x180004e7c  jnz     loc_180004F3E
0x180004e82  mov     rbx, [rbx+8]
0x180004e86  test    rbx, rbx
0x180004e89  jz      loc_180004F3E
0x180004e8f  mov     eax, [rbx+18h]
0x180004e92  mov     rbx, [rbx+10h]
0x180004e96  add     rax, rax
0x180004e99  jmp     short loc_180004F10
0x180004e9b  lea     eax, [r9-3]
0x180004e9f  mov     r9d, 1
0x180004ea5  cmp     eax, r9d
0x180004ea8  ja      loc_180004F3E
0x180004eae  mov     rbx, [rbx+8]
0x180004eb2  test    rbx, rbx
0x180004eb5  jz      loc_180004F3E
0x180004ebb  mov     eax, [rbx+18h]
0x180004ebe  sub     r11d, 4
0x180004ec2  mov     rbx, [rbx+10h]
0x180004ec6  neg     r11d
0x180004ec9  sbb     r9d, r9d
0x180004ecc  add     r9d, 4
0x180004ed0  jmp     short loc_180004F10
0x180004ed2  mov     r9d, 1
0x180004ed8  cmp     r11d, r9d
0x180004edb  jnz     short loc_180004F3E
0x180004edd  lea     eax, [r9+3]
0x180004ee1  add     rbx, 8
0x180004ee5  jmp     short loc_180004F10
0x180004ee7  mov     r9d, 2
0x180004eed  cmp     r11d, r9d
0x180004ef0  jnz     short loc_180004F3E
0x180004ef2  mov     rbx, [rbx+8]
0x180004ef6  test    rbx, rbx
0x180004ef9  jz      short loc_180004F3E
0x180004efb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004eff  inc     rax
0x180004f02  cmp     [rbx+rax*2], si
0x180004f06  jnz     short loc_180004EFF
0x180004f08  lea     rax, ds:2[rax*2]
0x180004f10  mov     edx, eax
0x180004f12  cmp     rdx, rax
0x180004f15  jnz     short loc_180004F3E
0x180004f17  mov     rcx, [rcx+10h]
0x180004f1b  mov     [rsp+48h+var_20], rbx
0x180004f20  mov     [rsp+48h+var_28], edx
0x180004f24  mov     rdx, rdi
0x180004f27  mov     rax, [rcx]
0x180004f2a  mov     rax, [rax+10h]
0x180004f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f33  test    eax, eax
0x180004f35  mov     ecx, esi
0x180004f37  cmovs   ecx, eax
0x180004f3a  mov     eax, ecx
0x180004f3c  jmp     short loc_180004F4A
0x180004f3e  mov     eax, 80070057h
0x180004f43  jmp     short loc_180004F4A
0x180004f45  mov     eax, 80004003h
0x180004f4a  mov     rbx, [rsp+48h+arg_0]
0x180004f4f  mov     rsi, [rsp+48h+arg_8]
0x180004f54  add     rsp, 40h
0x180004f58  pop     rdi
0x180004f59  retn
```
