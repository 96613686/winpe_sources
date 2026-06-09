# CspWriteOutputCharacterA

- ea: `0x1400219e4`
- end: `0x140021b86`
- name: `CspWriteOutputCharacterA`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400206a0`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x14001f6b8`
- `0x140020a78`
- `0x140020b2c`
- `0x140020ba8`
- `0x1400219e4`

## import_xrefs

- `ntdll!RtlUTF8ToUnicodeN` at `0x140021ad4`
- `ntdll!RtlUTF8ToUnicodeN` at `0x140021ad4`

## pseudocode

```c
NTSTATUS __fastcall CspWriteOutputCharacterA(__int64 a1, __int64 a2)
{
  __int64 v4; // r9
  __int64 v5; // r8
  int v6; // edi
  int v7; // r15d
  unsigned int v8; // r12d
  int v9; // ebx
  NTSTATUS result; // eax
  unsigned int v11; // ecx
  __int64 v12; // r9
  __int16 v13; // r8
  int v14; // r9d
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h]
  _BYTE v18[512]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[1024]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v18, 0, sizeof(v18));
  v4 = *(unsigned __int16 *)(a1 + 362);
  v5 = *(unsigned __int16 *)(a1 + 360);
  v17 = 0;
  v15 = 0;
  v16 = 0;
  v6 = 0;
  CspInitializeScreenIterator(&v16, a2, v5, v4);
  v7 = 0;
  v8 = *(_DWORD *)(a1 + 340) - *(_DWORD *)(a1 + 260);
  if ( v8 )
  {
    while ( 1 )
    {
      v9 = v8;
      if ( v8 > 0x200 )
        v9 = 512;
      result = ReadMessageInput((void **)a1, a1 + 216, v7, (__int64)v18, v9);
      if ( result < 0 )
        break;
      if ( v9 == 512 )
        v9 = 512 - CspCountUtf8IncompleteBytes(v18);
      result = RtlUTF8ToUnicodeN(v19, 1024, &v15, v18, v9);
      if ( result < 0 )
        break;
      v11 = v15;
      v12 = 0;
      if ( (v15 & 0xFFFFFFFE) != 0 )
      {
        while ( 1 )
        {
          v13 = WORD1(v17);
          if ( WORD1(v17) >= *(_WORD *)(v16 + 34) )
            break;
          *(_WORD *)(*((_QWORD *)&v16 + 1) + 4LL * (unsigned __int16)v17) = (char)v18[v12];
          if ( v13 < *(__int16 *)(a2 + 24) )
            *(_WORD *)(a2 + 24) = v13;
          if ( v13 > *(__int16 *)(a2 + 26) )
            *(_WORD *)(a2 + 26) = v13;
          CspAdvanceScreenIterator(&v16);
          v11 = v15;
          v12 = (unsigned int)(v14 + 1);
          if ( (unsigned int)v12 >= v15 >> 1 )
            goto LABEL_15;
        }
        v6 += v12;
        goto LABEL_17;
      }
LABEL_15:
      v6 += v11 >> 1;
      v7 += v9;
    }
  }
  else
  {
LABEL_17:
    *(_DWORD *)(a1 + 368) = v6;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400219e4  mov     [rsp-8+arg_10], rbx
0x1400219e9  push    rbp
0x1400219ea  push    rsi
0x1400219eb  push    rdi
0x1400219ec  push    r12
0x1400219ee  push    r13
0x1400219f0  push    r14
0x1400219f2  push    r15
0x1400219f4  lea     rbp, [rsp-560h]
0x1400219fc  sub     rsp, 660h
0x140021a03  mov     rax, cs:__security_cookie
0x140021a0a  xor     rax, rsp
0x140021a0d  mov     [rbp+590h+var_40], rax
0x140021a14  mov     r14, rdx
0x140021a17  mov     rsi, rcx
0x140021a1a  xor     edx, edx; Val
0x140021a1c  lea     rcx, [rsp+690h+var_640]; void *
0x140021a21  mov     r8d, 200h; Size
0x140021a27  call    memset_0
0x140021a2c  movzx   r9d, word ptr [rsi+16Ah]
0x140021a34  lea     rcx, [rsp+690h+var_658]
0x140021a39  movzx   r8d, word ptr [rsi+168h]
0x140021a41  xor     eax, eax
0x140021a43  xorps   xmm0, xmm0
0x140021a46  mov     [rsp+690h+var_648], rax
0x140021a4b  mov     rdx, r14
0x140021a4e  mov     [rsp+690h+var_660], eax
0x140021a52  movups  [rsp+690h+var_658], xmm0
0x140021a57  xor     edi, edi
0x140021a59  call    CspInitializeScreenIterator
0x140021a5e  mov     r12d, [rsi+154h]
0x140021a65  mov     r15d, edi
0x140021a68  sub     r12d, [rsi+104h]
0x140021a6f  jz      loc_140021B54
0x140021a75  mov     eax, 200h
0x140021a7a  lea     r9, [rsp+690h+var_640]
0x140021a7f  cmp     r12d, eax
0x140021a82  lea     rdx, [rsi+0D8h]
0x140021a89  mov     ebx, r12d
0x140021a8c  mov     r8d, r15d
0x140021a8f  cmova   ebx, eax
0x140021a92  mov     rcx, rsi
0x140021a95  mov     [rsp+690h+var_670], ebx
0x140021a99  call    ReadMessageInput
0x140021a9e  test    eax, eax
0x140021aa0  js      loc_140021B5C
0x140021aa6  cmp     ebx, 200h
0x140021aac  jnz     short loc_140021ABA
0x140021aae  lea     rcx, [rsp+690h+var_640]
0x140021ab3  call    CspCountUtf8IncompleteBytes
0x140021ab8  sub     ebx, eax
0x140021aba  lea     r9, [rsp+690h+var_640]
0x140021abf  mov     [rsp+690h+var_670], ebx
0x140021ac3  lea     r8, [rsp+690h+var_660]
0x140021ac8  mov     edx, 400h
0x140021acd  lea     rcx, [rbp+590h+var_440]
0x140021ad4  call    cs:__imp_RtlUTF8ToUnicodeN
0x140021ada  test    eax, eax
0x140021adc  js      short loc_140021B5C
0x140021ade  mov     ecx, [rsp+690h+var_660]
0x140021ae2  xor     r9d, r9d
0x140021ae5  test    ecx, 0FFFFFFFEh
0x140021aeb  jbe     short loc_140021B45
0x140021aed  mov     rax, qword ptr [rsp+690h+var_658]
0x140021af2  movzx   r8d, word ptr [rsp+690h+var_648+2]
0x140021af8  cmp     r8w, [rax+22h]
0x140021afd  jnb     short loc_140021B51
0x140021aff  movzx   ecx, word ptr [rsp+690h+var_648]
0x140021b04  mov     rax, qword ptr [rsp+690h+var_658+8]
0x140021b09  movsx   edx, [rsp+r9+690h+var_640]
0x140021b0f  mov     [rax+rcx*4], dx
0x140021b13  cmp     r8w, [r14+18h]
0x140021b18  jge     short loc_140021B1F
0x140021b1a  mov     [r14+18h], r8w
0x140021b1f  cmp     r8w, [r14+1Ah]
0x140021b24  jle     short loc_140021B2B
0x140021b26  mov     [r14+1Ah], r8w
0x140021b2b  lea     rcx, [rsp+690h+var_658]
0x140021b30  call    CspAdvanceScreenIterator
0x140021b35  mov     ecx, [rsp+690h+var_660]
0x140021b39  inc     r9d
0x140021b3c  mov     eax, ecx
0x140021b3e  shr     eax, 1
0x140021b40  cmp     r9d, eax
0x140021b43  jb      short loc_140021AED
0x140021b45  shr     ecx, 1
0x140021b47  add     edi, ecx
0x140021b49  add     r15d, ebx
0x140021b4c  jmp     loc_140021A75
0x140021b51  add     edi, r9d
0x140021b54  mov     [rsi+170h], edi
0x140021b5a  xor     eax, eax
0x140021b5c  mov     rcx, [rbp+590h+var_40]
0x140021b63  xor     rcx, rsp; StackCookie
0x140021b66  call    __security_check_cookie
0x140021b6b  mov     rbx, [rsp+690h+arg_10]
0x140021b73  add     rsp, 660h
0x140021b7a  pop     r15
0x140021b7c  pop     r14
0x140021b7e  pop     r13
0x140021b80  pop     r12
0x140021b82  pop     rdi
0x140021b83  pop     rsi
0x140021b84  pop     rbp
0x140021b85  retn
```
