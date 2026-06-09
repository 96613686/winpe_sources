# FileProvBuildChunkTable

- ea: `0x140038b10`
- end: `0x140038e8f`
- name: `FileProvBuildChunkTable`
- size: `895`
- prototype: `__int64 __fastcall(__int64, __int64, volatile signed __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400382b0`

## callees

- `0x140007a30`
- `0x14000a140`
- `0x14000d3b8`
- `0x14000d440`
- `0x14000fb60`
- `0x1400119c0`
- `0x140038760`
- `0x140038b10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140038d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038dd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038dd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e57`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038bda`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038c17`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038bda`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038c17`

## string_xrefs

- `0x140038dc0`: `Wof compressed file's resource table is corrupt`

## pseudocode

```c
__int64 __fastcall FileProvBuildChunkTable(__int64 a1, __int64 a2, volatile signed __int64 *a3)
{
  unsigned int *v5; // r12
  __int64 v6; // r8
  __int64 v7; // rdi
  unsigned int v8; // esi
  int v9; // r15d
  unsigned int v10; // ebx
  _QWORD *PoolWithTag; // r13
  unsigned int v12; // ebp
  __int64 v13; // rdx
  char *v14; // r14
  unsigned int v15; // esi
  __int64 v16; // r11
  unsigned __int64 v17; // r9
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r10
  unsigned int v22; // edx
  __int16 v23; // r8
  _BYTE v25[224]; // [rsp+20h] [rbp-118h] BYREF
  char *P; // [rsp+158h] [rbp+20h]
  int Pa; // [rsp+158h] [rbp+20h]

  v5 = (unsigned int *)FileProvCompressionScheme(a2);
  memset(v25, 0, sizeof(v25));
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  v6 = *(_QWORD *)(a2 + 8);
  v7 = (*v5 + v6 - 1) / *v5;
  v8 = v7 - 1;
  if ( (_DWORD)v7 == 1 )
  {
    v15 = 0;
    goto LABEL_24;
  }
  if ( v8 > 0x1FFFFFFD )
  {
    v15 = -1073741670;
    goto LABEL_24;
  }
  v9 = 8;
  v10 = 1;
  if ( !HIDWORD(v6) )
    v9 = 4;
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, 32LL * ((v8 + 14) / 0xD), 0x74637066u);
  if ( !PoolWithTag )
  {
    v15 = -1073741670;
    goto LABEL_24;
  }
  v12 = v8 * v9;
  P = (char *)ExAllocatePoolWithTag(PagedPool, (v8 * v9 + 4095) & 0xFFFFF000, 0x74637066u);
  if ( !P )
  {
    ExFreePoolWithTag(PoolWithTag, 0);
    v15 = -1073741670;
    goto LABEL_24;
  }
  FileProvInitializeCompletionContextOnStack(a1, v13, v25);
  v14 = P;
  Pa = FileProvReadCompressed(0, P, (v12 + 4095) & 0xFFFFF000, v25);
  v15 = Pa;
  if ( Pa < 0 )
  {
    ExFreePoolWithTag(PoolWithTag, 0);
    ExFreePoolWithTag(v14, 0);
    goto LABEL_24;
  }
  v16 = 0;
  v17 = v12;
  *PoolWithTag = v12;
  while ( 1 )
  {
    if ( v10 == (_DWORD)v7 )
    {
      v18 = *(_QWORD *)(a2 + 16) - v12;
      goto LABEL_14;
    }
    if ( v10 > (unsigned int)v7 )
      break;
    if ( *(_DWORD *)(a2 + 12) )
      v18 = *(_QWORD *)&v14[v16];
    else
      v18 = *(unsigned int *)&v14[v16];
LABEL_14:
    v19 = v12 + v18;
    if ( v19 < v17 || (v20 = *v5, v19 + v20 < v17) || v19 > v20 + v17 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Wof compressed file's resource table is corrupt");
      ExFreePoolWithTag(PoolWithTag, 0);
      ExFreePoolWithTag(v14, 0);
      v15 = -1073700185;
      goto LABEL_24;
    }
    v21 = v10 / 0xD;
    v22 = v10 % 0xD;
    if ( v10 % 0xD )
    {
      v23 = v19 - v17;
      v16 = (unsigned int)(v9 + v16);
      v17 = v12 + v18;
      ++v10;
      *((_WORD *)&PoolWithTag[4 * v21] + v22 + 3) = v23;
    }
    else
    {
      v16 = (unsigned int)(v9 + v16);
      v17 = v12 + v18;
      ++v10;
      PoolWithTag[4 * v21] = v19;
    }
  }
  ExFreePoolWithTag(v14, 0);
  if ( _InterlockedCompareExchange64(a3, (signed __int64)PoolWithTag, 0) )
    ExFreePoolWithTag(PoolWithTag, 0);
  v15 = Pa;
LABEL_24:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_3b099794e4b93327e327da255c047df6_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x140038b10  mov     rax, rsp
0x140038b13  mov     [rax+18h], r8
0x140038b17  mov     [rax+10h], rdx
0x140038b1b  push    rsi
0x140038b1c  sub     rsp, 130h
0x140038b23  mov     [rax+8], rbx
0x140038b27  mov     rbx, rdx
0x140038b2a  mov     [rax-18h], rdi
0x140038b2e  mov     [rax-20h], r12
0x140038b32  mov     [rax-30h], r14
0x140038b36  mov     r14, rcx
0x140038b39  mov     rcx, rdx
0x140038b3c  call    FileProvCompressionScheme
0x140038b41  lea     rcx, [rsp+138h+var_118]; void *
0x140038b46  xor     edx, edx; Val
0x140038b48  mov     r8d, 0E0h; Size
0x140038b4e  mov     r12, rax
0x140038b51  call    memset
0x140038b56  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b5d  mov     eax, [rcx+2Ch]
0x140038b60  test    al, 20h
0x140038b62  jnz     loc_140038E1D
0x140038b68  mov     ecx, [r12]
0x140038b6c  mov     r8, [rbx+8]
0x140038b70  lea     rax, [r8-1]
0x140038b74  add     rax, rcx
0x140038b77  cqo
0x140038b79  idiv    rcx
0x140038b7c  mov     rdi, rax
0x140038b7f  lea     esi, [rax-1]
0x140038b82  test    esi, esi
0x140038b84  jz      loc_140038DB1
0x140038b8a  cmp     esi, 1FFFFFFDh
0x140038b90  ja      loc_140038DB9
0x140038b96  shr     r8, 20h
0x140038b9a  lea     ecx, [rsi+0Eh]
0x140038b9d  test    r8d, r8d
0x140038ba0  mov     [rsp+138h+var_28], r13
0x140038ba8  mov     eax, 4
0x140038bad  mov     [rsp+138h+var_38], r15
0x140038bb5  mov     r15d, 8
0x140038bbb  mov     ebx, 1
0x140038bc0  cmovz   r15d, eax
0x140038bc4  mov     r8d, 74637066h; Tag
0x140038bca  mov     eax, 4EC4EC4Fh
0x140038bcf  mul     ecx
0x140038bd1  mov     ecx, ebx; PoolType
0x140038bd3  shr     edx, 2
0x140038bd6  shl     rdx, 5; NumberOfBytes
0x140038bda  call    cs:__imp_ExAllocatePoolWithTag
0x140038be1  nop     dword ptr [rax+rax+00h]
0x140038be6  mov     r13, rax
0x140038be9  test    rax, rax
0x140038bec  jz      loc_140038DF8
0x140038bf2  mov     [rsp+138h+var_10], rbp
0x140038bfa  mov     r8d, 74637066h; Tag
0x140038c00  mov     ebp, r15d
0x140038c03  mov     ecx, ebx; PoolType
0x140038c05  imul    ebp, esi
0x140038c08  lea     eax, [rbp+0FFFh]
0x140038c0e  and     eax, 0FFFFF000h
0x140038c13  mov     edx, eax; NumberOfBytes
0x140038c15  mov     esi, eax
0x140038c17  call    cs:__imp_ExAllocatePoolWithTag
0x140038c1e  nop     dword ptr [rax+rax+00h]
0x140038c23  mov     [rsp+138h+P], rax
0x140038c2b  test    rax, rax
0x140038c2e  jz      loc_140038E02
0x140038c34  lea     r8, [rsp+138h+var_118]
0x140038c39  mov     rcx, r14
0x140038c3c  call    FileProvInitializeCompletionContextOnStack
0x140038c41  mov     r14, [rsp+138h+P]
0x140038c49  lea     r9, [rsp+138h+var_118]
0x140038c4e  mov     rdx, r14
0x140038c51  mov     r8d, esi
0x140038c54  xor     ecx, ecx
0x140038c56  call    FileProvReadCompressed
0x140038c5b  mov     dword ptr [rsp+138h+P], eax
0x140038c62  mov     esi, eax
0x140038c64  test    eax, eax
0x140038c66  js      loc_140038E41
0x140038c6c  mov     esi, ebp
0x140038c6e  xor     r11d, r11d
0x140038c71  mov     r9d, ebp
0x140038c74  mov     rbp, [rsp+138h+arg_8]
0x140038c7c  mov     [r13+0], rsi
0x140038c80  cmp     ebx, edi
0x140038c82  jz      short loc_140038CFA
0x140038c84  ja      loc_140038D18
0x140038c8a  cmp     dword ptr [rbp+0Ch], 0
0x140038c8e  jnz     loc_140038DA8
0x140038c94  mov     eax, [r11+r14]
0x140038c98  lea     rcx, [rsi+rax]
0x140038c9c  cmp     rcx, r9
0x140038c9f  jb      loc_140038DC0
0x140038ca5  mov     edx, [r12]
0x140038ca9  lea     rax, [rcx+rdx]
0x140038cad  cmp     rax, r9
0x140038cb0  jb      loc_140038DC0
0x140038cb6  lea     rax, [rdx+r9]
0x140038cba  cmp     rcx, rax
0x140038cbd  ja      loc_140038DC0
0x140038cc3  mov     eax, 4EC4EC4Fh
0x140038cc8  mul     ebx
0x140038cca  shr     edx, 2
0x140038ccd  imul    eax, edx, 0Dh
0x140038cd0  mov     r10d, edx
0x140038cd3  mov     edx, ebx
0x140038cd5  sub     edx, eax
0x140038cd7  jz      short loc_140038D03
0x140038cd9  dec     edx
0x140038cdb  shl     r10, 4
0x140038cdf  add     rdx, r10
0x140038ce2  movzx   r8d, cx
0x140038ce6  sub     r8w, r9w
0x140038cea  add     r11d, r15d
0x140038ced  mov     r9, rcx
0x140038cf0  inc     ebx
0x140038cf2  mov     [r13+rdx*2+8], r8w
0x140038cf8  jmp     short loc_140038C80
0x140038cfa  mov     rax, [rbp+10h]
0x140038cfe  sub     rax, rsi
0x140038d01  jmp     short loc_140038C98
0x140038d03  shl     r10, 5
0x140038d07  add     r11d, r15d
0x140038d0a  mov     r9, rcx
0x140038d0d  inc     ebx
0x140038d0f  mov     [r10+r13], rcx
0x140038d13  jmp     loc_140038C80
0x140038d18  xor     edx, edx; Tag
0x140038d1a  mov     rcx, r14; P
0x140038d1d  call    cs:__imp_ExFreePoolWithTag
0x140038d24  nop     dword ptr [rax+rax+00h]
0x140038d29  mov     rcx, [rsp+138h+arg_10]
0x140038d31  xor     eax, eax
0x140038d33  lock cmpxchg [rcx], r13
0x140038d38  jz      short loc_140038D4B
0x140038d3a  xor     edx, edx; Tag
0x140038d3c  mov     rcx, r13; P
0x140038d3f  call    cs:__imp_ExFreePoolWithTag
0x140038d46  nop     dword ptr [rax+rax+00h]
0x140038d4b  mov     esi, dword ptr [rsp+138h+P]
0x140038d52  mov     rbp, [rsp+138h+var_10]
0x140038d5a  mov     r13, [rsp+138h+var_28]
0x140038d62  mov     r15, [rsp+138h+var_38]
0x140038d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140038d71  mov     r14, [rsp+138h+var_30]
0x140038d79  mov     r12, [rsp+138h+var_20]
0x140038d81  mov     rdi, [rsp+138h+var_18]
0x140038d89  mov     eax, [rcx+2Ch]
0x140038d8c  mov     rbx, [rsp+138h+arg_0]
0x140038d94  test    al, 20h
0x140038d96  jnz     loc_140038E68
0x140038d9c  mov     eax, esi
0x140038d9e  add     rsp, 130h
0x140038da5  pop     rsi
0x140038da6  retn
0x140038da8  mov     rax, [r11+r14]
0x140038dac  jmp     loc_140038C98
0x140038db1  xor     r11d, r11d
0x140038db4  mov     esi, r11d
0x140038db7  jmp     short loc_140038D6A
0x140038db9  mov     esi, 0C000009Ah
0x140038dbe  jmp     short loc_140038D6A
0x140038dc0  lea     rcx, aWofCompressedF; "Wof compressed file's resource table is"...
0x140038dc7  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140038dcc  xor     edx, edx; Tag
0x140038dce  mov     rcx, r13; P
0x140038dd1  call    cs:__imp_ExFreePoolWithTag
0x140038dd8  nop     dword ptr [rax+rax+00h]
0x140038ddd  xor     edx, edx; Tag
0x140038ddf  mov     rcx, r14; P
0x140038de2  call    cs:__imp_ExFreePoolWithTag
0x140038de9  nop     dword ptr [rax+rax+00h]
0x140038dee  mov     esi, 0C000A2A7h
0x140038df3  jmp     loc_140038D52
0x140038df8  mov     esi, 0C000009Ah
0x140038dfd  jmp     loc_140038D5A
0x140038e02  xor     edx, edx; Tag
0x140038e04  mov     rcx, r13; P
0x140038e07  call    cs:__imp_ExFreePoolWithTag
0x140038e0e  nop     dword ptr [rax+rax+00h]
0x140038e13  mov     esi, 0C000009Ah
0x140038e18  jmp     loc_140038D52
0x140038e1d  cmp     byte ptr [rcx+29h], 4
0x140038e21  jb      loc_140038B68
0x140038e27  mov     rcx, [rcx+18h]
0x140038e2b  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038e32  mov     edx, 0Ah
0x140038e37  call    WPP_SF_
0x140038e3c  jmp     loc_140038B68
0x140038e41  xor     edx, edx; Tag
0x140038e43  mov     rcx, r13; P
0x140038e46  call    cs:__imp_ExFreePoolWithTag
0x140038e4d  nop     dword ptr [rax+rax+00h]
0x140038e52  xor     edx, edx; Tag
0x140038e54  mov     rcx, r14; P
0x140038e57  call    cs:__imp_ExFreePoolWithTag
0x140038e5e  nop     dword ptr [rax+rax+00h]
0x140038e63  jmp     loc_140038D52
0x140038e68  cmp     byte ptr [rcx+29h], 4
0x140038e6c  jb      loc_140038D9C
0x140038e72  mov     rcx, [rcx+18h]
0x140038e76  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038e7d  mov     edx, 0Bh
0x140038e82  mov     r9d, esi
0x140038e85  call    WPP_SF_d
0x140038e8a  jmp     loc_140038D9C
```
