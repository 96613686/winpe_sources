# CfpBuildAckRenameMessage

- ea: `0x180008a54`
- end: `0x180008c5d`
- name: `CfpBuildAckRenameMessage`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a4c8`

## callees

- `0x180008a54`
- `0x180008c64`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180008b24`
- `ntdll!RtlNtStatusToDosError` at `0x180008ba0`
- `ntdll!RtlNtStatusToDosError` at `0x180008c1f`
- `ntdll!RtlNtStatusToDosError` at `0x180008b24`
- `ntdll!RtlNtStatusToDosError` at `0x180008ba0`
- `ntdll!RtlNtStatusToDosError` at `0x180008c1f`

## pseudocode

```c
__int64 __fastcall CfpBuildAckRenameMessage(__int64 a1, unsigned int a2, __int64 a3, int a4, int a5)
{
  unsigned __int64 v6; // rsi
  signed int v8; // r10d
  _WORD *v9; // rbp
  NTSTATUS v10; // edi
  NTSTATUS v11; // ecx
  __int64 v12; // rdx
  unsigned int v13; // eax
  signed int v14; // eax
  NTSTATUS v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rax
  signed int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rax
  signed int v21; // eax

  v6 = a2;
  v8 = a2 < 0xC8 ? 0x57 : 0;
  if ( a2 < 0xC8 )
    v8 = (a2 < 0xC8 ? 0x57 : 0) | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  v8 = CfpBuildMessageHeader(a1, a2, a3, 513);
  if ( v8 < 0 )
    return (unsigned int)v8;
  v9 = (_WORD *)(a1 + 14);
  v10 = -1073741789;
  if ( (unsigned int)v6 < 0x18 )
    goto LABEL_9;
  if ( *v9 <= 0xAu )
  {
    v11 = -1073741811;
    goto LABEL_14;
  }
  if ( (unsigned int)v6 < 0x68 || (v12 = *(unsigned int *)(a1 + 8), ((v12 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v6) )
  {
LABEL_9:
    v11 = -1073741789;
  }
  else
  {
    v13 = (v12 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v13;
    if ( *(_WORD *)(a1 + 96) )
      *(_WORD *)(a1 + 12) |= 1u;
    *(_DWORD *)(a1 + 100) = v13;
    *(_DWORD *)(a1 + 96) = 262154;
    *(_DWORD *)(v13 + a1) = a5;
    v11 = 0;
    *(_DWORD *)(a1 + 8) += 4;
  }
LABEL_14:
  v14 = RtlNtStatusToDosError(v11);
  v8 = v14;
  if ( v14 > 0 )
    v8 = (unsigned __int16)v14 | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( (unsigned int)v6 >= 0x18 )
    {
      if ( *v9 <= 5u )
      {
        v15 = -1073741811;
        goto LABEL_26;
      }
      if ( (unsigned int)v6 >= 0x40 )
      {
        v16 = *(unsigned int *)(a1 + 8);
        if ( ((v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v6 )
        {
          v17 = ((_DWORD)v16 + 3) & 0xFFFFFFFC;
          *(_DWORD *)(a1 + 8) = v17;
          if ( *(_WORD *)(a1 + 56) )
            *(_WORD *)(a1 + 12) |= 1u;
          *(_DWORD *)(a1 + 56) = 262154;
          v15 = 0;
          *(_DWORD *)(a1 + 60) = v17;
          *(_DWORD *)(v17 + a1) = a4;
          *(_DWORD *)(a1 + 8) += 4;
          goto LABEL_26;
        }
      }
    }
    v15 = -1073741789;
LABEL_26:
    v18 = RtlNtStatusToDosError(v15);
    v8 = v18;
    if ( v18 > 0 )
      v8 = (unsigned __int16)v18 | 0x80070000;
    if ( v8 >= 0 )
    {
      if ( (unsigned int)v6 >= 0x18 )
      {
        if ( *v9 > 0xDu )
        {
          if ( (unsigned int)v6 >= 0x80 )
          {
            v19 = *(unsigned int *)(a1 + 8);
            if ( ((v19 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v6 )
            {
              v20 = ((_DWORD)v19 + 3) & 0xFFFFFFFC;
              *(_DWORD *)(a1 + 8) = v20;
              if ( *(_WORD *)(a1 + 120) )
                *(_WORD *)(a1 + 12) |= 1u;
              *(_DWORD *)(a1 + 120) = 262154;
              v10 = 0;
              *(_DWORD *)(a1 + 124) = v20;
              *(_DWORD *)(v20 + a1) = 5;
              *(_DWORD *)(a1 + 8) += 4;
            }
          }
        }
        else
        {
          v10 = -1073741811;
        }
      }
      v21 = RtlNtStatusToDosError(v10);
      v8 = v21;
      if ( v21 > 0 )
        v8 = (unsigned __int16)v21 | 0x80070000;
      if ( v8 >= 0 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        *(_WORD *)(a1 + 12) &= ~2u;
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008a54  push    rbx
0x180008a56  push    rbp
0x180008a57  push    rsi
0x180008a58  push    rdi
0x180008a59  push    r12
0x180008a5b  push    r13
0x180008a5d  push    r14
0x180008a5f  push    r15
0x180008a61  sub     rsp, 28h
0x180008a65  mov     rbx, rcx
0x180008a68  mov     esi, edx
0x180008a6a  mov     ecx, 0C8h
0x180008a6f  mov     r13d, 80070000h
0x180008a75  cmp     edx, ecx
0x180008a77  mov     r14d, r9d
0x180008a7a  sbb     r10d, r10d
0x180008a7d  and     r10d, 57h
0x180008a81  mov     eax, r10d
0x180008a84  or      eax, r13d
0x180008a87  cmp     edx, ecx
0x180008a89  cmovb   r10d, eax
0x180008a8d  xor     r15d, r15d
0x180008a90  test    r10d, r10d
0x180008a93  js      loc_180008C49
0x180008a99  mov     r9d, 201h
0x180008a9f  mov     edx, esi
0x180008aa1  mov     rcx, rbx
0x180008aa4  call    CfpBuildMessageHeader
0x180008aa9  mov     r10d, eax
0x180008aac  test    eax, eax
0x180008aae  js      loc_180008C49
0x180008ab4  lea     rbp, [rbx+0Eh]
0x180008ab8  mov     edi, 0C0000023h
0x180008abd  lea     r8d, [r15+0Ah]
0x180008ac1  lea     r12d, [r15+4]
0x180008ac5  cmp     esi, 18h
0x180008ac8  jb      short loc_180008ADB
0x180008aca  cmp     r8w, [rbp+0]
0x180008acf  jb      short loc_180008AD6
0x180008ad1  lea     ecx, [rdi-16h]
0x180008ad4  jmp     short loc_180008B24
0x180008ad6  cmp     esi, 68h ; 'h'
0x180008ad9  jnb     short loc_180008ADF
0x180008adb  mov     ecx, edi
0x180008add  jmp     short loc_180008B24
0x180008adf  mov     edx, [rbx+8]
0x180008ae2  lea     rcx, [rdx+3]
0x180008ae6  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008aea  add     rcx, r12
0x180008aed  cmp     rcx, rsi
0x180008af0  ja      short loc_180008ADB
0x180008af2  lea     eax, [rdx+3]
0x180008af5  and     eax, 0FFFFFFFCh
0x180008af8  mov     [rbx+8], eax
0x180008afb  cmp     [rbx+60h], r15w
0x180008b00  jz      short loc_180008B07
0x180008b02  or      word ptr [rbx+0Ch], 1
0x180008b07  mov     ecx, eax
0x180008b09  mov     [rbx+64h], eax
0x180008b0c  mov     eax, [rsp+68h+arg_20]
0x180008b13  mov     dword ptr [rbx+60h], 4000Ah
0x180008b1a  mov     [rcx+rbx], eax
0x180008b1d  mov     ecx, r15d; Status
0x180008b20  add     [rbx+8], r12d
0x180008b24  call    cs:__imp_RtlNtStatusToDosError
0x180008b2a  mov     r10d, eax
0x180008b2d  test    eax, eax
0x180008b2f  jle     short loc_180008B38
0x180008b31  movzx   r10d, ax
0x180008b35  or      r10d, r13d
0x180008b38  test    r10d, r10d
0x180008b3b  js      loc_180008C49
0x180008b41  mov     r13d, 5
0x180008b47  cmp     esi, 18h
0x180008b4a  jnb     short loc_180008B50
0x180008b4c  mov     ecx, edi
0x180008b4e  jmp     short loc_180008BA0
0x180008b50  cmp     r13w, [rbp+0]
0x180008b55  jb      short loc_180008B5E
0x180008b57  mov     ecx, 0C000000Dh
0x180008b5c  jmp     short loc_180008BA0
0x180008b5e  cmp     esi, 40h ; '@'
0x180008b61  jb      short loc_180008B4C
0x180008b63  mov     edx, [rbx+8]
0x180008b66  lea     rcx, [rdx+3]
0x180008b6a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008b6e  add     rcx, r12
0x180008b71  cmp     rcx, rsi
0x180008b74  ja      short loc_180008B4C
0x180008b76  lea     eax, [rdx+3]
0x180008b79  and     eax, 0FFFFFFFCh
0x180008b7c  mov     [rbx+8], eax
0x180008b7f  cmp     [rbx+38h], r15w
0x180008b84  jz      short loc_180008B8B
0x180008b86  or      word ptr [rbx+0Ch], 1
0x180008b8b  mov     dword ptr [rbx+38h], 4000Ah
0x180008b92  mov     ecx, r15d; Status
0x180008b95  mov     [rbx+3Ch], eax
0x180008b98  mov     [rax+rbx], r14d
0x180008b9c  add     [rbx+8], r12d
0x180008ba0  call    cs:__imp_RtlNtStatusToDosError
0x180008ba6  mov     r10d, eax
0x180008ba9  test    eax, eax
0x180008bab  jle     short loc_180008BB8
0x180008bad  movzx   r10d, ax
0x180008bb1  or      r10d, 80070000h
0x180008bb8  test    r10d, r10d
0x180008bbb  js      loc_180008C49
0x180008bc1  cmp     esi, 18h
0x180008bc4  jb      short loc_180008C1D
0x180008bc6  mov     eax, 0Dh
0x180008bcb  cmp     ax, [rbp+0]
0x180008bcf  jb      short loc_180008BD8
0x180008bd1  mov     edi, 0C000000Dh
0x180008bd6  jmp     short loc_180008C1D
0x180008bd8  cmp     esi, 80h
0x180008bde  jb      short loc_180008C1D
0x180008be0  mov     edx, [rbx+8]
0x180008be3  lea     rcx, [rdx+3]
0x180008be7  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008beb  add     rcx, r12
0x180008bee  cmp     rcx, rsi
0x180008bf1  ja      short loc_180008C1D
0x180008bf3  lea     eax, [rdx+3]
0x180008bf6  and     eax, 0FFFFFFFCh
0x180008bf9  mov     [rbx+8], eax
0x180008bfc  cmp     [rbx+78h], r15w
0x180008c01  jz      short loc_180008C08
0x180008c03  or      word ptr [rbx+0Ch], 1
0x180008c08  mov     dword ptr [rbx+78h], 4000Ah
0x180008c0f  mov     edi, r15d
0x180008c12  mov     [rbx+7Ch], eax
0x180008c15  mov     [rax+rbx], r13d
0x180008c19  add     [rbx+8], r12d
0x180008c1d  mov     ecx, edi; Status
0x180008c1f  call    cs:__imp_RtlNtStatusToDosError
0x180008c25  mov     r10d, eax
0x180008c28  test    eax, eax
0x180008c2a  jle     short loc_180008C37
0x180008c2c  movzx   r10d, ax
0x180008c30  or      r10d, 80070000h
0x180008c37  test    r10d, r10d
0x180008c3a  js      short loc_180008C49
0x180008c3c  mov     eax, 0FFFDh
0x180008c41  mov     [rbx+4], r15d
0x180008c45  and     [rbx+0Ch], ax
0x180008c49  mov     eax, r10d
0x180008c4c  add     rsp, 28h
0x180008c50  pop     r15
0x180008c52  pop     r14
0x180008c54  pop     r13
0x180008c56  pop     r12
0x180008c58  pop     rdi
0x180008c59  pop     rsi
0x180008c5a  pop     rbp
0x180008c5b  pop     rbx
0x180008c5c  retn
```
