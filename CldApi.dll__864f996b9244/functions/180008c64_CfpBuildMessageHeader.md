# CfpBuildMessageHeader

- ea: `0x180008c64`
- end: `0x18000910c`
- name: `CfpBuildMessageHeader`
- size: `1192`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008570`
- `0x1800087f8`
- `0x180008a54`
- `0x180009114`
- `0x180009630`
- `0x180009904`
- `0x180009c20`
- `0x18000a234`

## callees

- `0x1800022ee`
- `0x180008c64`
- `0x18001be5c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180008d1e`
- `ntdll!RtlNtStatusToDosError` at `0x180008da2`
- `ntdll!RtlNtStatusToDosError` at `0x180008e20`
- `ntdll!RtlNtStatusToDosError` at `0x180008e9e`
- `ntdll!RtlNtStatusToDosError` at `0x180008fa0`
- `ntdll!RtlNtStatusToDosError` at `0x18000904a`
- `ntdll!RtlNtStatusToDosError` at `0x1800090e4`
- `ntdll!RtlNtStatusToDosError` at `0x180008d1e`
- `ntdll!RtlNtStatusToDosError` at `0x180008da2`
- `ntdll!RtlNtStatusToDosError` at `0x180008e20`
- `ntdll!RtlNtStatusToDosError` at `0x180008e9e`
- `ntdll!RtlNtStatusToDosError` at `0x180008fa0`
- `ntdll!RtlNtStatusToDosError` at `0x18000904a`
- `ntdll!RtlNtStatusToDosError` at `0x1800090e4`

## pseudocode

```c
__int64 __fastcall CfpBuildMessageHeader(__int64 a1, unsigned int a2, __int64 a3, __int16 a4)
{
  unsigned __int64 v4; // rsi
  signed int v8; // ecx
  NTSTATUS v9; // edi
  NTSTATUS v10; // ecx
  __int64 v11; // rdx
  int v12; // ecx
  signed int v13; // eax
  NTSTATUS v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax
  signed int v17; // eax
  NTSTATUS v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  signed int v22; // eax
  NTSTATUS v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  signed int v27; // eax
  __int64 v28; // rdx
  NTSTATUS v29; // ecx
  __int64 v30; // r8
  unsigned int v31; // ecx
  __int64 v32; // r8
  signed int v33; // eax
  unsigned __int16 *v34; // rdx
  NTSTATUS v35; // ecx
  __int64 v36; // r9
  size_t v37; // r8
  __int64 v38; // rcx
  unsigned __int16 *v39; // rcx
  signed int v40; // eax
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rax
  signed int v44; // eax

  v4 = a2;
  v8 = a2 < 0xC8 ? 0x57 : 0;
  if ( a2 < 0xC8 )
    v8 = (a2 < 0xC8 ? 0x57 : 0) | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  *(_DWORD *)(a1 + 8) = 200;
  *(_QWORD *)a1 = 1886219331;
  *(_DWORD *)(a1 + 12) = 1507328;
  memset_0((void *)(a1 + 16), 0, 0xB8u);
  v9 = -1073741789;
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_5;
  if ( *(_WORD *)(a1 + 14) )
  {
    v11 = *(unsigned int *)(a1 + 8);
    if ( ((v11 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > v4 )
    {
LABEL_5:
      v10 = -1073741789;
      goto LABEL_10;
    }
    v12 = (v11 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v12;
    *(_DWORD *)(a1 + 20) = v12;
    v10 = 0;
    *(_DWORD *)(a1 + 16) = 65543;
    *(_BYTE *)((((_DWORD)v11 + 3) & 0xFFFFFFFC) + a1) = 1;
    ++*(_DWORD *)(a1 + 8);
  }
  else
  {
    v10 = -1073741811;
  }
LABEL_10:
  v13 = RtlNtStatusToDosError(v10);
  v8 = v13;
  if ( v13 > 0 )
    v8 = (unsigned __int16)v13 | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_14;
  if ( *(_WORD *)(a1 + 14) > 1u )
  {
    if ( (unsigned int)v4 < 0x20 || (v15 = *(unsigned int *)(a1 + 8), ((v15 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 > v4) )
    {
LABEL_14:
      v14 = -1073741789;
      goto LABEL_22;
    }
    v16 = ((_DWORD)v15 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v16;
    if ( *(_WORD *)(a1 + 24) )
      *(_WORD *)(a1 + 12) |= 1u;
    *(_DWORD *)(a1 + 24) = 131080;
    v14 = 0;
    *(_DWORD *)(a1 + 28) = v16;
    *(_WORD *)(v16 + a1) = a4;
    *(_DWORD *)(a1 + 8) += 2;
  }
  else
  {
    v14 = -1073741811;
  }
LABEL_22:
  v17 = RtlNtStatusToDosError(v14);
  v8 = v17;
  if ( v17 > 0 )
    v8 = (unsigned __int16)v17 | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_26;
  if ( *(_WORD *)(a1 + 14) > 4u )
  {
    if ( (unsigned int)v4 < 0x38 || (v19 = *(unsigned int *)(a1 + 8), ((v19 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > v4) )
    {
LABEL_26:
      v18 = -1073741789;
      goto LABEL_34;
    }
    v20 = *(_QWORD *)(a3 + 8);
    v21 = ((_DWORD)v19 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v21;
    if ( *(_WORD *)(a1 + 48) )
      *(_WORD *)(a1 + 12) |= 1u;
    *(_DWORD *)(a1 + 48) = 524294;
    *(_DWORD *)(a1 + 52) = v21;
    *(_QWORD *)(v21 + a1) = v20;
    v18 = 0;
    *(_DWORD *)(a1 + 8) += 8;
  }
  else
  {
    v18 = -1073741811;
  }
LABEL_34:
  v22 = RtlNtStatusToDosError(v18);
  v8 = v22;
  if ( v22 > 0 )
    v8 = (unsigned __int16)v22 | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_38;
  if ( *(_WORD *)(a1 + 14) > 7u )
  {
    if ( (unsigned int)v4 < 0x50 || (v24 = *(unsigned int *)(a1 + 8), ((v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > v4) )
    {
LABEL_38:
      v23 = -1073741789;
      goto LABEL_46;
    }
    v25 = *(_QWORD *)(a3 + 16);
    v26 = ((_DWORD)v24 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v26;
    if ( *(_WORD *)(a1 + 72) )
      *(_WORD *)(a1 + 12) |= 1u;
    *(_DWORD *)(a1 + 72) = 524294;
    *(_DWORD *)(a1 + 76) = v26;
    *(_QWORD *)(v26 + a1) = v25;
    v23 = 0;
    *(_DWORD *)(a1 + 8) += 8;
  }
  else
  {
    v23 = -1073741811;
  }
LABEL_46:
  v27 = RtlNtStatusToDosError(v23);
  v8 = v27;
  if ( v27 > 0 )
    v8 = (unsigned __int16)v27 | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( *(_DWORD *)a3 >= 0x20u )
  {
    v28 = *(_QWORD *)(a3 + 24);
    if ( v28 )
    {
      if ( (unsigned int)v4 < 0x18 )
      {
LABEL_52:
        v29 = -1073741789;
        goto LABEL_62;
      }
      if ( *(_WORD *)(a1 + 14) > 8u )
      {
        if ( (unsigned int)v4 < 0x58 )
          goto LABEL_52;
        v30 = *(unsigned int *)(a1 + 8);
        if ( ((v30 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 130 > v4 )
          goto LABEL_52;
        if ( *(_WORD *)(a1 + 80) )
          *(_WORD *)(a1 + 12) |= 1u;
        v31 = (v30 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(a1 + 8) = v31;
        *(_DWORD *)(a1 + 80) = 8519697;
        v32 = v31 + a1;
        *(_DWORD *)(a1 + 84) = v31;
        if ( v32 != v28 )
        {
          *(_OWORD *)v32 = *(_OWORD *)v28;
          *(_OWORD *)(v32 + 16) = *(_OWORD *)(v28 + 16);
          *(_OWORD *)(v32 + 32) = *(_OWORD *)(v28 + 32);
          *(_OWORD *)(v32 + 48) = *(_OWORD *)(v28 + 48);
          *(_OWORD *)(v32 + 64) = *(_OWORD *)(v28 + 64);
          *(_OWORD *)(v32 + 80) = *(_OWORD *)(v28 + 80);
          *(_OWORD *)(v32 + 96) = *(_OWORD *)(v28 + 96);
          *(_OWORD *)(v32 + 112) = *(_OWORD *)(v28 + 112);
          *(_WORD *)(v32 + 128) = *(_WORD *)(v28 + 128);
        }
        v29 = 0;
        *(_DWORD *)(a1 + 8) += *(unsigned __int16 *)(a1 + 82);
      }
      else
      {
        v29 = -1073741811;
      }
LABEL_62:
      v33 = RtlNtStatusToDosError(v29);
      v8 = v33;
      if ( v33 > 0 )
        v8 = (unsigned __int16)v33 | 0x80070000;
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
  }
  if ( *(_DWORD *)a3 < 0x28u || (v34 = *(unsigned __int16 **)(a3 + 32)) == 0 )
  {
LABEL_81:
    if ( a4 == 513 )
    {
      if ( *(_DWORD *)a3 < 0x30u )
        v41 = 0;
      else
        v41 = *(_QWORD *)(a3 + 40);
      if ( (unsigned int)v4 >= 0x18 )
      {
        if ( *(_WORD *)(a1 + 14) > 0xCu )
        {
          if ( (unsigned int)v4 >= 0x78 )
          {
            v42 = *(unsigned int *)(a1 + 8);
            if ( ((v42 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= v4 )
            {
              v43 = ((_DWORD)v42 + 3) & 0xFFFFFFFC;
              *(_DWORD *)(a1 + 8) = v43;
              if ( *(_WORD *)(a1 + 112) )
                *(_WORD *)(a1 + 12) |= 1u;
              *(_DWORD *)(a1 + 112) = 524294;
              v9 = 0;
              *(_DWORD *)(a1 + 116) = v43;
              *(_QWORD *)(v43 + a1) = v41;
              *(_DWORD *)(a1 + 8) += 8;
            }
          }
        }
        else
        {
          v9 = -1073741811;
        }
      }
      v44 = RtlNtStatusToDosError(v9);
      v8 = v44;
      if ( v44 > 0 )
        return (unsigned __int16)v44 | 0x80070000;
    }
    return (unsigned int)v8;
  }
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_68;
  if ( *(_WORD *)(a1 + 14) > 9u )
  {
    if ( (unsigned int)v4 < 0x60
      || (v36 = *(unsigned int *)(a1 + 8), v37 = *v34, v37 + ((v36 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v4) )
    {
LABEL_68:
      v35 = -1073741789;
      goto LABEL_78;
    }
    if ( *(_WORD *)(a1 + 88) )
      *(_WORD *)(a1 + 12) |= 1u;
    v38 = ((_DWORD)v36 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v38;
    *(_DWORD *)(a1 + 92) = v38;
    v39 = (unsigned __int16 *)(a1 + v38);
    *(_WORD *)(a1 + 88) = 17;
    *(_WORD *)(a1 + 90) = v37;
    if ( v39 != v34 )
      memcpy_0(v39, v34, v37);
    v35 = 0;
    *(_DWORD *)(a1 + 8) += *(unsigned __int16 *)(a1 + 90);
  }
  else
  {
    v35 = -1073741811;
  }
LABEL_78:
  v40 = RtlNtStatusToDosError(v35);
  v8 = v40;
  if ( v40 > 0 )
    v8 = (unsigned __int16)v40 | 0x80070000;
  if ( v8 >= 0 )
    goto LABEL_81;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008c64  push    rbx
0x180008c66  push    rbp
0x180008c67  push    rsi
0x180008c68  push    rdi
0x180008c69  push    r12
0x180008c6b  push    r13
0x180008c6d  push    r14
0x180008c6f  push    r15
0x180008c71  sub     rsp, 28h
0x180008c75  mov     esi, edx
0x180008c77  mov     rbx, rcx
0x180008c7a  mov     edx, 0C8h
0x180008c7f  mov     r13d, 80070000h
0x180008c85  cmp     esi, edx
0x180008c87  movzx   r15d, r9w
0x180008c8b  mov     rbp, r8
0x180008c8e  sbb     ecx, ecx
0x180008c90  and     ecx, 57h
0x180008c93  mov     eax, ecx
0x180008c95  or      eax, r13d
0x180008c98  cmp     esi, edx
0x180008c9a  cmovb   ecx, eax
0x180008c9d  xor     r12d, r12d
0x180008ca0  test    ecx, ecx
0x180008ca2  js      loc_1800090F9
0x180008ca8  mov     [rbx+8], edx
0x180008cab  lea     rcx, [rbx+10h]; void *
0x180008caf  xor     edx, edx; Val
0x180008cb1  mov     qword ptr [rbx], 706D6C43h
0x180008cb8  mov     r8d, 0B8h; Size
0x180008cbe  mov     dword ptr [rbx+0Ch], 170000h
0x180008cc5  call    memset_0
0x180008cca  lea     r9d, [r12+1]
0x180008ccf  mov     edi, 0C0000023h
0x180008cd4  cmp     esi, 18h
0x180008cd7  jnb     short loc_180008CDD
0x180008cd9  mov     ecx, edi
0x180008cdb  jmp     short loc_180008D1E
0x180008cdd  cmp     r12w, [rbx+0Eh]
0x180008ce2  jb      short loc_180008CEB
0x180008ce4  mov     ecx, 0C000000Dh
0x180008ce9  jmp     short loc_180008D1E
0x180008ceb  mov     edx, [rbx+8]
0x180008cee  lea     rcx, [rdx+3]
0x180008cf2  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008cf6  add     rcx, r9
0x180008cf9  cmp     rcx, rsi
0x180008cfc  ja      short loc_180008CD9
0x180008cfe  lea     eax, [rdx+3]
0x180008d01  and     eax, 0FFFFFFFCh
0x180008d04  mov     ecx, eax
0x180008d06  mov     [rbx+8], ecx
0x180008d09  mov     [rbx+14h], ecx
0x180008d0c  mov     ecx, r12d; Status
0x180008d0f  mov     dword ptr [rbx+10h], 10007h
0x180008d16  mov     [rax+rbx], r9b
0x180008d1a  add     [rbx+8], r9d
0x180008d1e  call    cs:__imp_RtlNtStatusToDosError
0x180008d24  mov     ecx, eax
0x180008d26  test    eax, eax
0x180008d28  jle     short loc_180008D30
0x180008d2a  movzx   ecx, ax
0x180008d2d  or      ecx, r13d
0x180008d30  test    ecx, ecx
0x180008d32  js      loc_1800090F9
0x180008d38  mov     r13d, 8
0x180008d3e  lea     r14d, [r13-7]
0x180008d42  cmp     esi, 18h
0x180008d45  jnb     short loc_180008D4B
0x180008d47  mov     ecx, edi
0x180008d49  jmp     short loc_180008DA2
0x180008d4b  cmp     r14w, [rbx+0Eh]
0x180008d50  jb      short loc_180008D59
0x180008d52  mov     ecx, 0C000000Dh
0x180008d57  jmp     short loc_180008DA2
0x180008d59  cmp     esi, 20h ; ' '
0x180008d5c  jb      short loc_180008D47
0x180008d5e  mov     edx, [rbx+8]
0x180008d61  mov     r8d, 2
0x180008d67  lea     rcx, [rdx+3]
0x180008d6b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008d6f  add     rcx, r8
0x180008d72  cmp     rcx, rsi
0x180008d75  ja      short loc_180008D47
0x180008d77  lea     eax, [rdx+3]
0x180008d7a  and     eax, 0FFFFFFFCh
0x180008d7d  mov     [rbx+8], eax
0x180008d80  cmp     [rbx+18h], r12w
0x180008d85  jz      short loc_180008D8C
0x180008d87  or      [rbx+0Ch], r14w
0x180008d8c  mov     dword ptr [rbx+18h], 20008h
0x180008d93  mov     ecx, r12d; Status
0x180008d96  mov     [rbx+1Ch], eax
0x180008d99  mov     [rax+rbx], r15w
0x180008d9e  add     [rbx+8], r8d
0x180008da2  call    cs:__imp_RtlNtStatusToDosError
0x180008da8  mov     ecx, eax
0x180008daa  test    eax, eax
0x180008dac  jle     short loc_180008DB7
0x180008dae  movzx   ecx, ax
0x180008db1  or      ecx, 80070000h
0x180008db7  test    ecx, ecx
0x180008db9  js      loc_1800090F9
0x180008dbf  cmp     esi, 18h
0x180008dc2  jnb     short loc_180008DC8
0x180008dc4  mov     ecx, edi
0x180008dc6  jmp     short loc_180008E20
0x180008dc8  mov     eax, 4
0x180008dcd  cmp     ax, [rbx+0Eh]
0x180008dd1  jb      short loc_180008DDA
0x180008dd3  mov     ecx, 0C000000Dh
0x180008dd8  jmp     short loc_180008E20
0x180008dda  cmp     esi, 38h ; '8'
0x180008ddd  jb      short loc_180008DC4
0x180008ddf  mov     edx, [rbx+8]
0x180008de2  lea     rcx, [rdx+3]
0x180008de6  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008dea  add     rcx, r13
0x180008ded  cmp     rcx, rsi
0x180008df0  ja      short loc_180008DC4
0x180008df2  mov     rcx, [rbp+8]
0x180008df6  lea     eax, [rdx+3]
0x180008df9  and     eax, 0FFFFFFFCh
0x180008dfc  mov     [rbx+8], eax
0x180008dff  cmp     [rbx+30h], r12w
0x180008e04  jz      short loc_180008E0B
0x180008e06  or      [rbx+0Ch], r14w
0x180008e0b  mov     dword ptr [rbx+30h], 80006h
0x180008e12  mov     [rbx+34h], eax
0x180008e15  mov     [rax+rbx], rcx
0x180008e19  mov     ecx, r12d; Status
0x180008e1c  add     [rbx+8], r13d
0x180008e20  call    cs:__imp_RtlNtStatusToDosError
0x180008e26  mov     ecx, eax
0x180008e28  test    eax, eax
0x180008e2a  jle     short loc_180008E35
0x180008e2c  movzx   ecx, ax
0x180008e2f  or      ecx, 80070000h
0x180008e35  test    ecx, ecx
0x180008e37  js      loc_1800090F9
0x180008e3d  cmp     esi, 18h
0x180008e40  jnb     short loc_180008E46
0x180008e42  mov     ecx, edi
0x180008e44  jmp     short loc_180008E9E
0x180008e46  mov     eax, 7
0x180008e4b  cmp     ax, [rbx+0Eh]
0x180008e4f  jb      short loc_180008E58
0x180008e51  mov     ecx, 0C000000Dh
0x180008e56  jmp     short loc_180008E9E
0x180008e58  cmp     esi, 50h ; 'P'
0x180008e5b  jb      short loc_180008E42
0x180008e5d  mov     edx, [rbx+8]
0x180008e60  lea     rcx, [rdx+3]
0x180008e64  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008e68  add     rcx, r13
0x180008e6b  cmp     rcx, rsi
0x180008e6e  ja      short loc_180008E42
0x180008e70  mov     rcx, [rbp+10h]
0x180008e74  lea     eax, [rdx+3]
0x180008e77  and     eax, 0FFFFFFFCh
0x180008e7a  mov     [rbx+8], eax
0x180008e7d  cmp     [rbx+48h], r12w
0x180008e82  jz      short loc_180008E89
0x180008e84  or      [rbx+0Ch], r14w
0x180008e89  mov     dword ptr [rbx+48h], 80006h
0x180008e90  mov     [rbx+4Ch], eax
0x180008e93  mov     [rax+rbx], rcx
0x180008e97  mov     ecx, r12d; Status
0x180008e9a  add     [rbx+8], r13d
0x180008e9e  call    cs:__imp_RtlNtStatusToDosError
0x180008ea4  mov     ecx, eax
0x180008ea6  test    eax, eax
0x180008ea8  jle     short loc_180008EB3
0x180008eaa  movzx   ecx, ax
0x180008ead  or      ecx, 80070000h
0x180008eb3  test    ecx, ecx
0x180008eb5  js      loc_1800090F9
0x180008ebb  cmp     dword ptr [rbp+0], 20h ; ' '
0x180008ebf  mov     r14d, 11h
0x180008ec5  jb      loc_180008FBD
0x180008ecb  mov     rdx, [rbp+18h]
0x180008ecf  test    rdx, rdx
0x180008ed2  jz      loc_180008FBD
0x180008ed8  cmp     esi, 18h
0x180008edb  jnb     short loc_180008EE4
0x180008edd  mov     ecx, edi
0x180008edf  jmp     loc_180008FA0
0x180008ee4  cmp     r13w, [rbx+0Eh]
0x180008ee9  jb      short loc_180008EF5
0x180008eeb  mov     ecx, 0C000000Dh
0x180008ef0  jmp     loc_180008FA0
0x180008ef5  cmp     esi, 58h ; 'X'
0x180008ef8  jb      short loc_180008EDD
0x180008efa  mov     r8d, [rbx+8]
0x180008efe  lea     rcx, [r8+3]
0x180008f02  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008f06  add     rcx, 82h
0x180008f0d  cmp     rcx, rsi
0x180008f10  ja      short loc_180008EDD
0x180008f12  cmp     [rbx+50h], r12w
0x180008f17  jz      short loc_180008F22
0x180008f19  mov     eax, 1
0x180008f1e  or      [rbx+0Ch], ax
0x180008f22  lea     eax, [r8+3]
0x180008f26  and     eax, 0FFFFFFFCh
0x180008f29  mov     ecx, eax
0x180008f2b  mov     [rbx+8], ecx
0x180008f2e  mov     dword ptr [rbx+50h], 820011h
0x180008f35  lea     r8, [rax+rbx]
0x180008f39  mov     [rbx+54h], ecx
0x180008f3c  cmp     r8, rdx
0x180008f3f  jz      short loc_180008F96
0x180008f41  movups  xmm0, xmmword ptr [rdx]
0x180008f44  movups  xmmword ptr [r8], xmm0
0x180008f48  movups  xmm1, xmmword ptr [rdx+10h]
0x180008f4c  movups  xmmword ptr [r8+10h], xmm1
0x180008f51  movups  xmm0, xmmword ptr [rdx+20h]
0x180008f55  movups  xmmword ptr [r8+20h], xmm0
0x180008f5a  movups  xmm1, xmmword ptr [rdx+30h]
0x180008f5e  movups  xmmword ptr [r8+30h], xmm1
0x180008f63  movups  xmm0, xmmword ptr [rdx+40h]
0x180008f67  movups  xmmword ptr [r8+40h], xmm0
0x180008f6c  movups  xmm1, xmmword ptr [rdx+50h]
0x180008f70  movups  xmmword ptr [r8+50h], xmm1
0x180008f75  movups  xmm0, xmmword ptr [rdx+60h]
0x180008f79  movups  xmmword ptr [r8+60h], xmm0
0x180008f7e  movups  xmm1, xmmword ptr [rdx+70h]
0x180008f82  movups  xmmword ptr [r8+70h], xmm1
0x180008f87  movzx   eax, word ptr [rdx+80h]
0x180008f8e  mov     [r8+80h], ax
0x180008f96  movzx   eax, word ptr [rbx+52h]
0x180008f9a  mov     ecx, r12d; Status
0x180008f9d  add     [rbx+8], eax
0x180008fa0  call    cs:__imp_RtlNtStatusToDosError
0x180008fa6  mov     ecx, eax
0x180008fa8  test    eax, eax
0x180008faa  jle     short loc_180008FB5
0x180008fac  movzx   ecx, ax
0x180008faf  or      ecx, 80070000h
0x180008fb5  test    ecx, ecx
0x180008fb7  js      loc_1800090F9
0x180008fbd  cmp     dword ptr [rbp+0], 28h ; '('
0x180008fc1  jb      loc_180009067
0x180008fc7  mov     rdx, [rbp+20h]; Src
0x180008fcb  test    rdx, rdx
0x180008fce  jz      loc_180009067
0x180008fd4  cmp     esi, 18h
0x180008fd7  jnb     short loc_180008FDD
0x180008fd9  mov     ecx, edi
0x180008fdb  jmp     short loc_18000904A
0x180008fdd  mov     eax, 9
0x180008fe2  cmp     ax, [rbx+0Eh]
0x180008fe6  jb      short loc_180008FEF
0x180008fe8  mov     ecx, 0C000000Dh
0x180008fed  jmp     short loc_18000904A
0x180008fef  cmp     esi, 60h ; '`'
0x180008ff2  jb      short loc_180008FD9
0x180008ff4  mov     r9d, [rbx+8]
0x180008ff8  movzx   r8d, word ptr [rdx]; Size
0x180008ffc  lea     rcx, [r9+3]
0x180009000  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180009004  add     rcx, r8
0x180009007  cmp     rcx, rsi
0x18000900a  ja      short loc_180008FD9
0x18000900c  cmp     [rbx+58h], r12w
0x180009011  jz      short loc_18000901C
0x180009013  mov     eax, 1
0x180009018  or      [rbx+0Ch], ax
0x18000901c  lea     ecx, [r9+3]
0x180009020  and     ecx, 0FFFFFFFCh
0x180009023  mov     [rbx+8], ecx
0x180009026  mov     [rbx+5Ch], ecx
0x180009029  add     rcx, rbx; void *
0x18000902c  mov     [rbx+58h], r14w
0x180009031  mov     [rbx+5Ah], r8w
0x180009036  cmp     rcx, rdx
0x180009039  jz      short loc_180009040
0x18000903b  call    memcpy_0
0x180009040  movzx   eax, word ptr [rbx+5Ah]
0x180009044  mov     ecx, r12d; Status
0x180009047  add     [rbx+8], eax
0x18000904a  call    cs:__imp_RtlNtStatusToDosError
0x180009050  mov     ecx, eax
0x180009052  test    eax, eax
0x180009054  jle     short loc_18000905F
0x180009056  movzx   ecx, ax
0x180009059  or      ecx, 80070000h
0x18000905f  test    ecx, ecx
0x180009061  js      loc_1800090F9
0x180009067  mov     eax, 201h
0x18000906c  cmp     r15w, ax
0x180009070  jnz     loc_1800090F9
0x180009076  cmp     dword ptr [rbp+0], 30h ; '0'
0x18000907a  jb      short loc_180009082
0x18000907c  mov     r8, [rbp+28h]
0x180009080  jmp     short loc_180009085
0x180009082  mov     r8, r12
0x180009085  cmp     esi, 18h
0x180009088  jb      short loc_1800090E2
0x18000908a  mov     eax, 0Ch
  ... truncated ...
```
