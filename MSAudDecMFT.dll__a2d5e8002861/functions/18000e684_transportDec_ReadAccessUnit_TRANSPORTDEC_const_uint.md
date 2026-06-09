# transportDec_ReadAccessUnit(TRANSPORTDEC * const,uint)

- ea: `0x18000e684`
- end: `0x18000e9a9`
- name: `?transportDec_ReadAccessUnit@@YA?AW4TRANSPORTDEC_ERROR@@QEAUTRANSPORTDEC@@I@Z`
- size: `805`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000a810`
- `0x1800710ac`

## callees

- `0x18000e684`
- `0x18000e9b0`
- `0x1800103a0`
- `0x18001115c`
- `0x180011234`
- `0x18004dd14`
- `0x1800710ac`
- `0x18007a4ac`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall transportDec_ReadAccessUnit(__int64 a1, unsigned int a2)
{
  __int64 v2; // r15
  unsigned int DecodeHeader; // ebx
  int *v5; // rsi
  int v6; // eax
  int v8; // r12d
  int v9; // ebp
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // [rsp+90h] [rbp+8h] BYREF
  char v14; // [rsp+A0h] [rbp+18h] BYREF
  int v15; // [rsp+A8h] [rbp+20h]

  v2 = a2;
  if ( !a1 )
    return 514;
  DecodeHeader = 0;
  v5 = (int *)(a1 + 48LL * a2 + 136);
  CDKsyncCache_0(v5);
  if ( v5[2] <= 0 )
  {
    DecodeHeader = 257;
    *(_DWORD *)(a1 + 3844) = 0;
  }
  switch ( *(_DWORD *)a1 )
  {
    case 0:
      CDKsyncCache_0(v5);
      *(_DWORD *)(a1 + 4 * v2 + 3840) = v5[2];
      *(_DWORD *)(a1 + 3872) |= 1u;
      break;
    case 1:
      if ( (*(_BYTE *)(a1 + 3872) & 0x20) == 0 )
      {
        CDKsyncCache_0(v5);
        v8 = v5[2];
        v9 = 0;
        v15 = v8;
        v14 = 0;
        LOBYTE(v13) = 1;
        while ( v9 < 2 )
        {
          if ( v9 > 0 )
          {
            CDKsyncCache_0(v5);
            CDKpushBack(v5, (unsigned int)(v8 - v5[2]));
            LOBYTE(v13) = 2;
          }
          memset_0((void *)(a1 + 312), 0, 0x6DCu);
          *(_DWORD *)(a1 + 1512) = -1;
          *(_BYTE *)(a1 + 1543) = 15;
          *(_BYTE *)(a1 + 1537) = -1;
          memset_0((void *)(a1 + 1044), 0, 0x1D1u);
          *(_BYTE *)(a1 + 1046) = 15;
          DecodeHeader = adifRead_DecodeHeader(a1 + 192, a1 + 1044, v5);
          if ( DecodeHeader )
            return DecodeHeader;
          LOBYTE(v10) = v13;
          *(_DWORD *)(a1 + 1512) = *(unsigned __int8 *)(a1 + 1045) + 1;
          *(_BYTE *)(a1 + 1543) = *(_BYTE *)(a1 + 1046);
          v11 = *(unsigned __int8 *)(a1 + 1046);
          *(_BYTE *)(a1 + 1536) = 0;
          *(_DWORD *)(a1 + 1520) = 1024;
          v12 = *(_QWORD *)(a1 + 16);
          *(_DWORD *)(a1 + 1516) = dword_18009C260[v11];
          *(_DWORD *)(a1 + 3848) = *(_DWORD *)(a1 + 196);
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64, char *))(a1 + 8))(v12, a1 + 312, v10, &v14) )
            return 1025;
          *(_DWORD *)(a1 + 3872) |= 0x20u;
          if ( !v9 && v14 && (*(unsigned int (__fastcall **)(_QWORD, __int64))(a1 + 40))(*(_QWORD *)(a1 + 48), a1 + 312) )
            DecodeHeader = 1025;
          v8 = v15;
          ++v9;
        }
      }
      *(_DWORD *)(a1 + 4 * v2 + 3840) = -1;
      break;
    case 2:
LABEL_19:
      DecodeHeader = transportDec_readStream((struct TRANSPORTDEC *)a1);
      break;
    case 6:
    case 7:
      if ( DecodeHeader )
        goto LABEL_10;
      v13 = *(_DWORD *)(a1 + 3872) & 0x20;
      DecodeHeader = transportDec_readHeader((unsigned int *)a1, v5, 0, 1, (int *)(a1 + 3840 + 4 * v2), 0, 0, &v13, 0);
      if ( v13 )
        *(_DWORD *)(a1 + 3872) |= 0x20u;
      break;
    case 0xA:
      goto LABEL_19;
    default:
      DecodeHeader = 1026;
      break;
  }
  if ( DecodeHeader )
  {
LABEL_10:
    v6 = 0;
    goto LABEL_8;
  }
  CDKsyncCache_0(v5);
  v6 = v5[2];
LABEL_8:
  *(_DWORD *)(a1 + 4 * v2 + 3836) = v6;
  if ( *(_DWORD *)a1 == 2 )
  {
    if ( *(_BYTE *)(a1 + 211) )
    {
      *(_BYTE *)(a1 + 211) = 0;
      return (unsigned int)transportDec_DetermineImplicitChannelConfig(a1, (unsigned int)v2);
    }
  }
  return DecodeHeader;
}

```

## disassembly

```asm
0x18000e684  mov     [rsp+arg_8], rbx
0x18000e689  push    rbp
0x18000e68a  push    rsi
0x18000e68b  push    rdi
0x18000e68c  push    r12
0x18000e68e  push    r13
0x18000e690  push    r14
0x18000e692  push    r15
0x18000e694  sub     rsp, 50h
0x18000e698  xor     r13d, r13d
0x18000e69b  mov     r15d, edx
0x18000e69e  mov     rdi, rcx
0x18000e6a1  test    rcx, rcx
0x18000e6a4  jz      loc_18000E73B
0x18000e6aa  lea     rsi, [r15+r15*2]
0x18000e6ae  mov     ebx, r13d
0x18000e6b1  shl     rsi, 4
0x18000e6b5  add     rsi, 88h
0x18000e6bc  add     rsi, rcx
0x18000e6bf  mov     rcx, rsi
0x18000e6c2  call    CDKsyncCache_0
0x18000e6c7  cmp     [rsi+8], r13d
0x18000e6cb  jle     short loc_18000E728
0x18000e6cd  mov     ecx, [rdi]
0x18000e6cf  test    ecx, ecx
0x18000e6d1  jnz     loc_18000E761
0x18000e6d7  mov     rcx, rsi
0x18000e6da  call    CDKsyncCache_0
0x18000e6df  mov     eax, [rsi+8]
0x18000e6e2  mov     [rdi+r15*4+0F00h], eax
0x18000e6ea  or      dword ptr [rdi+0F20h], 1
0x18000e6f1  test    ebx, ebx
0x18000e6f3  jnz     short loc_18000E736
0x18000e6f5  mov     rcx, rsi
0x18000e6f8  call    CDKsyncCache_0
0x18000e6fd  mov     eax, [rsi+8]
0x18000e700  mov     [rdi+r15*4+0EFCh], eax
0x18000e708  cmp     dword ptr [rdi], 2
0x18000e70b  jz      short loc_18000E742
0x18000e70d  mov     eax, ebx
0x18000e70f  mov     rbx, [rsp+88h+arg_8]
0x18000e717  add     rsp, 50h
0x18000e71b  pop     r15
0x18000e71d  pop     r14
0x18000e71f  pop     r13
0x18000e721  pop     r12
0x18000e723  pop     rdi
0x18000e724  pop     rsi
0x18000e725  pop     rbp
0x18000e726  retn
0x18000e728  mov     ebx, 101h
0x18000e72d  mov     [rdi+0F04h], r13d
0x18000e734  jmp     short loc_18000E6CD
0x18000e736  mov     eax, r13d
0x18000e739  jmp     short loc_18000E700
0x18000e73b  mov     eax, 202h
0x18000e740  jmp     short loc_18000E70F
0x18000e742  cmp     [rdi+0D3h], r13b
0x18000e749  jz      short loc_18000E70D
0x18000e74b  mov     edx, r15d
0x18000e74e  mov     [rdi+0D3h], r13b
0x18000e755  mov     rcx, rdi
0x18000e758  call    transportDec_DetermineImplicitChannelConfig
0x18000e75d  mov     ebx, eax
0x18000e75f  jmp     short loc_18000E70D
0x18000e761  sub     ecx, 1
0x18000e764  jz      loc_18000E808
0x18000e76a  sub     ecx, 1
0x18000e76d  jz      short loc_18000E77E
0x18000e76f  sub     ecx, 4
0x18000e772  jz      short loc_18000E79A
0x18000e774  sub     ecx, 1
0x18000e777  jz      short loc_18000E79A
0x18000e779  cmp     ecx, 3
0x18000e77c  jnz     short loc_18000E790
0x18000e77e  mov     edx, r15d
0x18000e781  mov     rcx, rdi; struct TRANSPORTDEC *
0x18000e784  call    transportDec_readStream
0x18000e789  mov     ebx, eax
0x18000e78b  jmp     loc_18000E6F1
0x18000e790  mov     ebx, 402h
0x18000e795  jmp     loc_18000E6F1
0x18000e79a  test    ebx, ebx
0x18000e79c  jnz     short loc_18000E736
0x18000e79e  mov     eax, [rdi+0F20h]
0x18000e7a4  lea     rcx, [rsp+88h+arg_0]
0x18000e7ac  and     eax, 20h
0x18000e7af  mov     [rsp+88h+var_48], r13
0x18000e7b4  mov     [rsp+88h+var_50], rcx
0x18000e7b9  lea     r9d, [rbx+1]
0x18000e7bd  mov     [rsp+88h+arg_0], eax
0x18000e7c4  xor     r8d, r8d
0x18000e7c7  mov     [rsp+88h+var_58], r13
0x18000e7cc  lea     rax, [rdi+0F00h]
0x18000e7d3  lea     rax, [rax+r15*4]
0x18000e7d7  mov     [rsp+88h+var_60], r13
0x18000e7dc  mov     rdx, rsi
0x18000e7df  mov     [rsp+88h+var_68], rax
0x18000e7e4  mov     rcx, rdi
0x18000e7e7  call    transportDec_readHeader
0x18000e7ec  mov     ebx, eax
0x18000e7ee  cmp     [rsp+88h+arg_0], r13d
0x18000e7f6  jz      loc_18000E6F1
0x18000e7fc  or      dword ptr [rdi+0F20h], 20h
0x18000e803  jmp     loc_18000E6F1
0x18000e808  test    byte ptr [rdi+0F20h], 20h
0x18000e80f  jnz     loc_18000E998
0x18000e815  mov     rcx, rsi
0x18000e818  call    CDKsyncCache_0
0x18000e81d  mov     r12d, [rsi+8]
0x18000e821  mov     ebp, r13d
0x18000e824  mov     [rsp+88h+arg_18], r12d
0x18000e82c  mov     [rsp+88h+arg_10], r13b
0x18000e834  mov     byte ptr [rsp+88h+arg_0], 1
0x18000e83c  cmp     ebp, 2
0x18000e83f  jge     loc_18000E998
0x18000e845  test    ebp, ebp
0x18000e847  jle     short loc_18000E867
0x18000e849  mov     rcx, rsi
0x18000e84c  call    CDKsyncCache_0
0x18000e851  mov     edx, r12d
0x18000e854  mov     rcx, rsi
0x18000e857  sub     edx, [rsi+8]
0x18000e85a  call    CDKpushBack
0x18000e85f  mov     byte ptr [rsp+88h+arg_0], 2
0x18000e867  lea     r13, [rdi+138h]
0x18000e86e  xor     edx, edx; Val
0x18000e870  mov     rcx, r13; void *
0x18000e873  mov     r8d, 6DCh; Size
0x18000e879  call    memset_0
0x18000e87e  lea     rbx, [r13+2DCh]
0x18000e885  mov     dword ptr [r13+4B0h], 0FFFFFFFFh
0x18000e890  mov     rcx, rbx; void *
0x18000e893  mov     byte ptr [r13+4CFh], 0Fh
0x18000e89b  xor     edx, edx; Val
0x18000e89d  mov     byte ptr [r13+4C9h], 0FFh
0x18000e8a5  mov     r8d, 1D1h; Size
0x18000e8ab  call    memset_0
0x18000e8b0  lea     r12, [rdi+414h]
0x18000e8b7  mov     byte ptr [rbx+2], 0Fh
0x18000e8bb  mov     rdx, r12
0x18000e8be  lea     rcx, [rdi+0C0h]
0x18000e8c5  mov     r8, rsi
0x18000e8c8  call    ?adifRead_DecodeHeader@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCAdifHeader@@PEAUCProgramConfig@@PEAUCDK_BITSTREAM@@@Z; adifRead_DecodeHeader(CAdifHeader *,CProgramConfig *,CDK_BITSTREAM *)
0x18000e8cd  mov     ebx, eax
0x18000e8cf  test    eax, eax
0x18000e8d1  jnz     loc_18000E70D
0x18000e8d7  movzx   eax, byte ptr [r12+1]
0x18000e8dd  lea     rcx, dword_18009C260
0x18000e8e4  mov     r8b, byte ptr [rsp+88h+arg_0]
0x18000e8ec  lea     r9, [rsp+88h+arg_10]
0x18000e8f4  inc     eax
0x18000e8f6  mov     rdx, r13
0x18000e8f9  mov     [rdi+5E8h], eax
0x18000e8ff  mov     al, [r12+2]
0x18000e904  mov     [rdi+607h], al
0x18000e90a  movzx   eax, byte ptr [r12+2]
0x18000e910  mov     [rdi+600h], bl
0x18000e916  mov     dword ptr [rdi+5F0h], 400h
0x18000e920  mov     eax, [rcx+rax*4]
0x18000e923  mov     rcx, [rdi+10h]
0x18000e927  mov     [rdi+5ECh], eax
0x18000e92d  mov     eax, [rdi+0C4h]
0x18000e933  mov     [rdi+0F08h], eax
0x18000e939  mov     rax, [rdi+8]
0x18000e93d  call    cs:__guard_dispatch_icall_fptr
0x18000e943  test    eax, eax
0x18000e945  jnz     short loc_18000E98E
0x18000e947  or      dword ptr [rdi+0F20h], 20h
0x18000e94e  test    ebp, ebp
0x18000e950  jnz     short loc_18000E97C
0x18000e952  cmp     [rsp+88h+arg_10], bpl
0x18000e95a  jz      short loc_18000E97C
0x18000e95c  mov     rcx, [rdi+30h]
0x18000e960  mov     rdx, r13
0x18000e963  mov     rax, [rdi+28h]
0x18000e967  call    cs:__guard_dispatch_icall_fptr
0x18000e96d  xor     r13d, r13d
0x18000e970  test    eax, eax
0x18000e972  mov     eax, 401h
0x18000e977  cmovnz  ebx, eax
0x18000e97a  jmp     short loc_18000E97F
0x18000e97c  xor     r13d, r13d
0x18000e97f  mov     r12d, [rsp+88h+arg_18]
0x18000e987  inc     ebp
0x18000e989  jmp     loc_18000E83C
0x18000e98e  mov     ebx, 401h
0x18000e993  jmp     loc_18000E70D
0x18000e998  mov     dword ptr [rdi+r15*4+0F00h], 0FFFFFFFFh
0x18000e9a4  jmp     loc_18000E6F1
```
