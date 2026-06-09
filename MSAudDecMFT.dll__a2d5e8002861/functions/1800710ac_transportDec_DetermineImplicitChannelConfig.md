# transportDec_DetermineImplicitChannelConfig

- ea: `0x1800710ac`
- end: `0x1800711ec`
- name: `transportDec_DetermineImplicitChannelConfig`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000e684`

## callees

- `0x18000e684`
- `0x18000e9b0`
- `0x18001115c`
- `0x180046ebc`
- `0x1800710ac`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall transportDec_DetermineImplicitChannelConfig(__int64 a1, unsigned int a2)
{
  __int64 v2; // r15
  int *v4; // rsi
  unsigned __int8 v5; // di
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned int (__fastcall *v8)(__int64, __int64); // rax
  __int64 v9; // r8
  unsigned int v10; // edi
  __int64 v11; // rdx
  _DWORD v13[2]; // [rsp+30h] [rbp-18h]
  __int16 v14; // [rsp+38h] [rbp-10h]
  char v15; // [rsp+88h] [rbp+40h] BYREF

  v2 = a2;
  v13[0] = 18748688;
  v13[1] = 84148994;
  v14 = 1798;
  v4 = (int *)(48LL * a2 + a1 + 136);
  v5 = 0;
LABEL_2:
  if ( !*(_BYTE *)(a1 + 1505) || (*(unsigned int (__fastcall **)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 32)) )
  {
    while ( v5 < 0xAu )
    {
      v6 = v5++;
      CProgramConfig_GetDefault((struct CProgramConfig *)(a1 + 1044), *((unsigned __int8 *)v13 + v6));
      if ( *(_BYTE *)(a1 + 1505) )
      {
        *(_BYTE *)(a1 + 1505) = 2;
        CDKsyncCache_0(v4);
        CDKpushBack(v4, (unsigned int)(*(_DWORD *)(a1 + 3832) - v4[2] + 12));
        transportDec_ReadAccessUnit(a1, v2);
        goto LABEL_2;
      }
    }
    v10 = 258;
    goto LABEL_12;
  }
  v7 = *(_QWORD *)(a1 + 48);
  v8 = *(unsigned int (__fastcall **)(__int64, __int64))(a1 + 40);
  v15 = 1;
  if ( v8(v7, a1 + 312)
    || (LOBYTE(v9) = 2,
        (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, char *))(a1 + 8))(
          *(_QWORD *)(a1 + 16),
          a1 + 312,
          v9,
          &v15)) )
  {
    v10 = 515;
LABEL_12:
    CDKsyncCache_0(v4);
    v11 = (unsigned int)(*(_DWORD *)(a1 + 3832) - v4[2] + 4);
    goto LABEL_13;
  }
  CDKsyncCache_0(v4);
  v11 = (unsigned int)(*(_DWORD *)(a1 + 4 * v2 + 3836) - v4[2]);
  v10 = 0;
LABEL_13:
  CDKpushBack(v4, v11);
  return v10;
}

```

## disassembly

```asm
0x1800710ac  push    rbp
0x1800710ae  push    rbx
0x1800710af  push    rsi
0x1800710b0  push    rdi
0x1800710b1  push    r14
0x1800710b3  push    r15
0x1800710b5  mov     rbp, rsp
0x1800710b8  sub     rsp, 48h
0x1800710bc  mov     r15d, edx
0x1800710bf  lea     rsi, [rcx+88h]
0x1800710c6  mov     rbx, rcx
0x1800710c9  mov     [rbp+var_18], 11E1510h
0x1800710d0  mov     [rbp+var_14], 5040302h
0x1800710d7  mov     [rbp+var_10], 706h
0x1800710dd  lea     rax, [r15+r15*2]
0x1800710e1  shl     rax, 4
0x1800710e5  add     rsi, rax
0x1800710e8  xor     dil, dil
0x1800710eb  cmp     byte ptr [rbx+5E1h], 0
0x1800710f2  jz      short loc_180071106
0x1800710f4  mov     rcx, [rbx+20h]
0x1800710f8  mov     rax, [rbx+18h]
0x1800710fc  call    cs:__guard_dispatch_icall_fptr
0x180071102  test    eax, eax
0x180071104  jz      short loc_180071161
0x180071106  cmp     dil, 0Ah
0x18007110a  jnb     loc_1800711BB
0x180071110  movzx   eax, dil
0x180071114  lea     rcx, [rbx+414h]; struct CProgramConfig *
0x18007111b  inc     dil
0x18007111e  movzx   edx, byte ptr [rbp+rax+var_18]; unsigned int
0x180071123  call    ?CProgramConfig_GetDefault@@YAXPEAUCProgramConfig@@I@Z; CProgramConfig_GetDefault(CProgramConfig *,uint)
0x180071128  cmp     byte ptr [rbx+5E1h], 0
0x18007112f  jz      short loc_180071106
0x180071131  mov     rcx, rsi
0x180071134  mov     byte ptr [rbx+5E1h], 2
0x18007113b  call    CDKsyncCache_0
0x180071140  mov     edx, [rbx+0EF8h]
0x180071146  mov     rcx, rsi
0x180071149  sub     edx, [rsi+8]
0x18007114c  add     edx, 0Ch
0x18007114f  call    CDKpushBack
0x180071154  mov     edx, r15d
0x180071157  mov     rcx, rbx
0x18007115a  call    ?transportDec_ReadAccessUnit@@YA?AW4TRANSPORTDEC_ERROR@@QEAUTRANSPORTDEC@@I@Z; transportDec_ReadAccessUnit(TRANSPORTDEC * const,uint)
0x18007115f  jmp     short loc_1800710EB
0x180071161  mov     rcx, [rbx+30h]
0x180071165  lea     rdi, [rbx+138h]
0x18007116c  mov     rax, [rbx+28h]
0x180071170  mov     rdx, rdi
0x180071173  mov     [rbp+arg_8], 1
0x180071177  call    cs:__guard_dispatch_icall_fptr
0x18007117d  test    eax, eax
0x18007117f  jz      short loc_180071188
0x180071181  mov     edi, 203h
0x180071186  jmp     short loc_1800711C0
0x180071188  mov     rcx, [rbx+10h]
0x18007118c  lea     r9, [rbp+arg_8]
0x180071190  mov     rax, [rbx+8]
0x180071194  mov     r8b, 2
0x180071197  mov     rdx, rdi
0x18007119a  call    cs:__guard_dispatch_icall_fptr
0x1800711a0  test    eax, eax
0x1800711a2  jnz     short loc_180071181
0x1800711a4  mov     rcx, rsi
0x1800711a7  call    CDKsyncCache_0
0x1800711ac  mov     edx, [rbx+r15*4+0EFCh]
0x1800711b4  sub     edx, [rsi+8]
0x1800711b7  xor     edi, edi
0x1800711b9  jmp     short loc_1800711D4
0x1800711bb  mov     edi, 102h
0x1800711c0  mov     rcx, rsi
0x1800711c3  call    CDKsyncCache_0
0x1800711c8  mov     edx, [rbx+0EF8h]
0x1800711ce  sub     edx, [rsi+8]
0x1800711d1  add     edx, 4
0x1800711d4  mov     rcx, rsi
0x1800711d7  call    CDKpushBack
0x1800711dc  mov     eax, edi
0x1800711de  add     rsp, 48h
0x1800711e2  pop     r15
0x1800711e4  pop     r14
0x1800711e6  pop     rdi
0x1800711e7  pop     rsi
0x1800711e8  pop     rbx
0x1800711e9  pop     rbp
0x1800711ea  retn
```
