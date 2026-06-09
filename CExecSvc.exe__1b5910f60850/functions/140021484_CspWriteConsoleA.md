# CspWriteConsoleA

- ea: `0x140021484`
- end: `0x1400215a8`
- name: `CspWriteConsoleA`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400204b0`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x14001f6b8`
- `0x140020b2c`
- `0x140021484`
- `0x140021b8c`

## import_xrefs

- `ntdll!RtlUTF8ToUnicodeN` at `0x140021559`
- `ntdll!RtlUTF8ToUnicodeN` at `0x140021559`

## pseudocode

```c
__int64 __fastcall CspWriteConsoleA(void **a1, __int64 a2, __int64 a3, int *a4)
{
  int v8; // edi
  int v9; // esi
  unsigned int i; // edi
  int v11; // ebx
  __int64 result; // rax
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+3Ch] [rbp-C4h]
  _BYTE *v16; // [rsp+40h] [rbp-C0h]
  _BYTE v17[512]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[1024]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v17, 0, sizeof(v17));
  v8 = *(_DWORD *)(a2 + 124);
  v9 = 0;
  v16 = v18;
  v15 = 0;
  v14[1] = 1024;
  v13 = 0;
  for ( i = v8 - *(_DWORD *)(a2 + 44); i; i -= v11 )
  {
    v11 = i;
    if ( i > 0x200 )
      v11 = 512;
    if ( ReadMessageInput(a1, a2, v9, (__int64)v17, v11) < 0 )
      break;
    if ( v11 == 512 )
      v11 = 512 - CspCountUtf8IncompleteBytes(v17);
    result = RtlUTF8ToUnicodeN(v18, 1024, &v13, v17, v11);
    if ( (int)result < 0 )
      return result;
    v14[0] = v13;
    CspWriteString(a3, v14);
    v9 += v11;
  }
  *a4 = v9;
  return 0;
}

```

## disassembly

```asm
0x140021484  push    rbp
0x140021486  push    rbx
0x140021487  push    rsi
0x140021488  push    rdi
0x140021489  push    r12
0x14002148b  push    r13
0x14002148d  push    r14
0x14002148f  push    r15
0x140021491  lea     rbp, [rsp-568h]
0x140021499  sub     rsp, 668h
0x1400214a0  mov     rax, cs:__security_cookie
0x1400214a7  xor     rax, rsp
0x1400214aa  mov     [rbp+5A0h+var_50], rax
0x1400214b1  mov     r12, r8
0x1400214b4  mov     r15, rdx
0x1400214b7  mov     r13, rcx
0x1400214ba  xor     edx, edx; Val
0x1400214bc  mov     r8d, 200h; Size
0x1400214c2  lea     rcx, [rsp+6A0h+var_650]; void *
0x1400214c7  mov     r14, r9
0x1400214ca  call    memset_0
0x1400214cf  mov     edi, [r15+7Ch]
0x1400214d3  lea     rax, [rbp+5A0h+var_450]
0x1400214da  mov     esi, 0
0x1400214df  mov     [rsp+6A0h+var_660], rax
0x1400214e4  mov     eax, 400h
0x1400214e9  mov     [rsp+6A0h+var_664], 0
0x1400214f1  mov     [rsp+6A0h+var_666], ax
0x1400214f6  mov     [rsp+6A0h+var_670], 0
0x1400214fe  sub     edi, [r15+2Ch]
0x140021502  jz      short loc_140021580
0x140021504  mov     eax, 200h
0x140021509  lea     r9, [rsp+6A0h+var_650]
0x14002150e  cmp     edi, eax
0x140021510  mov     ebx, edi
0x140021512  mov     r8d, esi
0x140021515  mov     rdx, r15
0x140021518  cmova   ebx, eax
0x14002151b  mov     rcx, r13
0x14002151e  mov     [rsp+6A0h+var_680], ebx
0x140021522  call    ReadMessageInput
0x140021527  test    eax, eax
0x140021529  js      short loc_140021580
0x14002152b  cmp     ebx, 200h
0x140021531  jnz     short loc_14002153F
0x140021533  lea     rcx, [rsp+6A0h+var_650]
0x140021538  call    CspCountUtf8IncompleteBytes
0x14002153d  sub     ebx, eax
0x14002153f  lea     r9, [rsp+6A0h+var_650]
0x140021544  mov     [rsp+6A0h+var_680], ebx
0x140021548  lea     r8, [rsp+6A0h+var_670]
0x14002154d  mov     edx, 400h
0x140021552  lea     rcx, [rbp+5A0h+var_450]
0x140021559  call    cs:__imp_RtlUTF8ToUnicodeN
0x14002155f  test    eax, eax
0x140021561  js      short loc_140021585
0x140021563  movzx   eax, word ptr [rsp+6A0h+var_670]
0x140021568  lea     rdx, [rsp+6A0h+var_668]
0x14002156d  mov     rcx, r12
0x140021570  mov     [rsp+6A0h+var_668], ax
0x140021575  call    CspWriteString
0x14002157a  add     esi, ebx
0x14002157c  sub     edi, ebx
0x14002157e  jnz     short loc_140021504
0x140021580  mov     [r14], esi
0x140021583  xor     eax, eax
0x140021585  mov     rcx, [rbp+5A0h+var_50]
0x14002158c  xor     rcx, rsp; StackCookie
0x14002158f  call    __security_check_cookie
0x140021594  add     rsp, 668h
0x14002159b  pop     r15
0x14002159d  pop     r14
0x14002159f  pop     r13
0x1400215a1  pop     r12
0x1400215a3  pop     rdi
0x1400215a4  pop     rsi
0x1400215a5  pop     rbx
0x1400215a6  pop     rbp
0x1400215a7  retn
```
