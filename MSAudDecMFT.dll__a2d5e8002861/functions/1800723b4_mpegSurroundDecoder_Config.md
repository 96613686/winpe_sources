# mpegSurroundDecoder_Config

- ea: `0x1800723b4`
- end: `0x1800725e8`
- name: `mpegSurroundDecoder_Config`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180070860`

## callees

- `0x1800056a8`
- `0x18004d320`
- `0x18004dd14`
- `0x180071ccc`
- `0x1800723b4`
- `0x18007d2f8`
- `0x18007d4f4`
- `0x1800803ec`
- `0x180096060`

## pseudocode

```c
__int64 __fastcall mpegSurroundDecoder_Config(
        __int64 a1,
        int *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        int a8,
        int a9,
        char a10,
        _BYTE *a11)
{
  __int64 v13; // rdi
  _DWORD *v15; // r15
  unsigned int v16; // ebx
  char v17; // si
  int v18; // eax
  bool v19; // zf
  unsigned int v20; // eax
  int v21; // ecx
  __int64 result; // rax
  __int64 v23; // rsi
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v25[11]; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+6Ch] [rbp-94h]

  v24 = a1;
  v13 = a1;
  memset_0(v25, 0, 0xC0u);
  v15 = (_DWORD *)(v13 + 2264);
  if ( a3 != 23 && a3 != 39 )
  {
    if ( a3 != 42 && a3 != 147 )
      return (unsigned int)-983;
    v17 = a10;
    if ( a10 == 1 )
    {
      v16 = SpatialDecParseMps212Config(a2, v25, a4, a3, a7, a8);
      v15 = v25;
      v18 = v26;
    }
    else
    {
      v16 = SpatialDecParseMps212Config(a2, v13 + 2264, a4, a3, a7, a8);
      v18 = *(_DWORD *)(v13 + 2308);
    }
    if ( v16 )
      return v16;
    v19 = a6 == v18;
    goto LABEL_17;
  }
  v17 = a10;
  if ( a10 == 1 )
  {
    v20 = SpatialDecParseSpecificConfig(a2, v25, a9, a3);
    v21 = v26;
    v15 = v25;
  }
  else
  {
    v20 = SpatialDecParseSpecificConfig(a2, (_DWORD *)(v13 + 2264), a9, a3);
    v21 = *(_DWORD *)(v13 + 2308);
  }
  v16 = v20;
  if ( v20 )
    return v16;
  if ( a6 > 0 )
  {
    v19 = a6 == v21;
LABEL_17:
    if ( !v19 )
      return (unsigned int)-982;
  }
  result = sscCheckOutOfBand(v15, a3, a4, a5);
  v16 = result;
  if ( !(_DWORD)result )
  {
    if ( (v17 & 1) != 0 )
      return result;
    if ( (v17 & 2) != 0 && *a11 )
    {
      result = mpegSurroundDecoder_Create(&v24, a7, 0);
      v16 = result;
      if ( (_DWORD)result )
        return result;
      v13 = v24;
    }
    v23 = *(unsigned __int8 *)(v13 + 5588);
    if ( memcmp_0((const void *)(v13 + 2264), (const void *)(v13 + 192 * v23 + 2060), 0xC0u) )
    {
      *(_DWORD *)(v13 + 4 * v23 + 5616) |= 0x80u;
      if ( !*(_QWORD *)(v13 + 2256) )
        return (unsigned int)-1000;
      SpatialDecInitParserContext();
      *(_QWORD *)(*(_QWORD *)(v13 + 2256) + 360LL) = v13 + 192LL * *(unsigned __int8 *)(v13 + 5589) + 2060;
    }
    *(_BYTE *)(v13 + 2457) = 1;
  }
  return v16;
}

```

## disassembly

```asm
0x1800723b4  mov     [rsp-8+arg_10], rbx
0x1800723b9  push    rbp
0x1800723ba  push    rsi
0x1800723bb  push    rdi
0x1800723bc  push    r12
0x1800723be  push    r13
0x1800723c0  push    r14
0x1800723c2  push    r15
0x1800723c4  lea     rbp, [rsp-10h]
0x1800723c9  sub     rsp, 110h
0x1800723d0  mov     rax, cs:__security_cookie
0x1800723d7  xor     rax, rsp
0x1800723da  mov     [rbp+40h+var_40], rax
0x1800723de  mov     r14d, r8d
0x1800723e1  mov     [rsp+140h+var_110], rcx
0x1800723e6  mov     rbx, rdx
0x1800723e9  mov     rdi, rcx
0x1800723ec  xor     edx, edx; Val
0x1800723ee  lea     rcx, [rsp+140h+var_100]; void *
0x1800723f3  mov     r8d, 0C0h; Size
0x1800723f9  mov     r13d, r9d
0x1800723fc  call    memset_0
0x180072401  mov     r12d, [rbp+40h+arg_30]
0x180072408  lea     r15, [rdi+8D8h]
0x18007240f  mov     ecx, r14d
0x180072412  sub     ecx, 17h
0x180072415  jz      short loc_180072489
0x180072417  sub     ecx, 10h
0x18007241a  jz      short loc_180072489
0x18007241c  sub     ecx, 3
0x18007241f  jz      short loc_180072430
0x180072421  cmp     ecx, 69h ; 'i'
0x180072424  jz      short loc_180072430
0x180072426  mov     ebx, 0FFFFFC29h
0x18007242b  jmp     loc_1800725BE
0x180072430  mov     sil, [rbp+40h+arg_48]
0x180072437  mov     r9d, r14d
0x18007243a  mov     eax, [rbp+40h+arg_38]
0x180072440  mov     r8d, r13d
0x180072443  mov     [rsp+140h+var_118], eax
0x180072447  mov     rcx, rbx
0x18007244a  mov     [rsp+140h+var_120], r12d
0x18007244f  cmp     sil, 1
0x180072453  jnz     short loc_18007246C
0x180072455  lea     rdx, [rsp+140h+var_100]
0x18007245a  call    ?SpatialDecParseMps212Config@@YA?AW4SACDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@HW4AUDIO_OBJECT_TYPE@@HH@Z; SpatialDecParseMps212Config(CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG *,int,AUDIO_OBJECT_TYPE,int,int)
0x18007245f  mov     ebx, eax
0x180072461  lea     r15, [rsp+140h+var_100]
0x180072466  mov     eax, [rsp+140h+var_D4]
0x18007246a  jmp     short loc_18007247C
0x18007246c  mov     rdx, r15
0x18007246f  call    ?SpatialDecParseMps212Config@@YA?AW4SACDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@HW4AUDIO_OBJECT_TYPE@@HH@Z; SpatialDecParseMps212Config(CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG *,int,AUDIO_OBJECT_TYPE,int,int)
0x180072474  mov     ebx, eax
0x180072476  mov     eax, [rdi+904h]
0x18007247c  test    ebx, ebx
0x18007247e  jnz     loc_1800725BE
0x180072484  cmp     [rbp+40h+arg_28], eax
0x180072487  jmp     short loc_1800724D9
0x180072489  mov     sil, [rbp+40h+arg_48]
0x180072490  mov     r9d, r14d
0x180072493  mov     r8d, [rbp+40h+arg_40]
0x18007249a  mov     rcx, rbx
0x18007249d  cmp     sil, 1
0x1800724a1  jnz     short loc_1800724B8
0x1800724a3  lea     rdx, [rsp+140h+var_100]
0x1800724a8  call    ?SpatialDecParseSpecificConfig@@YA?AW4SACDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@HW4AUDIO_OBJECT_TYPE@@@Z; SpatialDecParseSpecificConfig(CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG *,int,AUDIO_OBJECT_TYPE)
0x1800724ad  mov     ecx, [rsp+140h+var_D4]
0x1800724b1  lea     r15, [rsp+140h+var_100]
0x1800724b6  jmp     short loc_1800724C6
0x1800724b8  mov     rdx, r15
0x1800724bb  call    ?SpatialDecParseSpecificConfig@@YA?AW4SACDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@HW4AUDIO_OBJECT_TYPE@@@Z; SpatialDecParseSpecificConfig(CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG *,int,AUDIO_OBJECT_TYPE)
0x1800724c0  mov     ecx, [rdi+904h]
0x1800724c6  mov     ebx, eax
0x1800724c8  test    eax, eax
0x1800724ca  jnz     loc_1800725BE
0x1800724d0  mov     eax, [rbp+40h+arg_28]
0x1800724d3  test    eax, eax
0x1800724d5  jle     short loc_1800724E5
0x1800724d7  cmp     eax, ecx
0x1800724d9  jz      short loc_1800724E5
0x1800724db  mov     ebx, 0FFFFFC2Ah
0x1800724e0  jmp     loc_1800725BE
0x1800724e5  mov     r9d, [rbp+40h+arg_20]
0x1800724e9  mov     r8d, r13d
0x1800724ec  mov     edx, r14d
0x1800724ef  mov     rcx, r15
0x1800724f2  call    sscCheckOutOfBand
0x1800724f7  mov     ebx, eax
0x1800724f9  test    eax, eax
0x1800724fb  jnz     loc_1800725BE
0x180072501  test    sil, 1
0x180072505  jnz     loc_1800725C0
0x18007250b  test    sil, 2
0x18007250f  jz      short loc_18007253C
0x180072511  mov     rax, [rbp+40h+arg_50]
0x180072518  cmp     byte ptr [rax], 0
0x18007251b  jz      short loc_18007253C
0x18007251d  xor     r8d, r8d
0x180072520  lea     rcx, [rsp+140h+var_110]
0x180072525  mov     edx, r12d
0x180072528  call    mpegSurroundDecoder_Create
0x18007252d  mov     ebx, eax
0x18007252f  test    eax, eax
0x180072531  jnz     loc_1800725C0
0x180072537  mov     rdi, [rsp+140h+var_110]
0x18007253c  movzx   esi, byte ptr [rdi+15D4h]
0x180072543  lea     rcx, [rdi+8D8h]; Buf1
0x18007254a  mov     r8d, 0C0h; Size
0x180072550  lea     rdx, [rsi+rsi*2]
0x180072554  shl     rdx, 6
0x180072558  add     rdx, 80Ch
0x18007255f  add     rdx, rdi; Buf2
0x180072562  call    memcmp_0
0x180072567  test    eax, eax
0x180072569  jz      short loc_1800725B3
0x18007256b  bts     dword ptr [rdi+rsi*4+15F0h], 7
0x180072574  mov     rcx, [rdi+8D0h]
0x18007257b  test    rcx, rcx
0x18007257e  jnz     short loc_180072587
0x180072580  mov     ebx, 0FFFFFC18h
0x180072585  jmp     short loc_1800725BE
0x180072587  call    SpatialDecInitParserContext
0x18007258c  movzx   eax, byte ptr [rdi+15D5h]
0x180072593  lea     rdx, [rax+rax*2]
0x180072597  mov     rax, [rdi+8D0h]
0x18007259e  shl     rdx, 6
0x1800725a2  add     rdx, 80Ch
0x1800725a9  add     rdx, rdi
0x1800725ac  mov     [rax+168h], rdx
0x1800725b3  test    ebx, ebx
0x1800725b5  jnz     short loc_1800725BE
0x1800725b7  mov     byte ptr [rdi+999h], 1
0x1800725be  mov     eax, ebx
0x1800725c0  mov     rcx, [rbp+40h+var_40]
0x1800725c4  xor     rcx, rsp; StackCookie
0x1800725c7  call    __security_check_cookie
0x1800725cc  mov     rbx, [rsp+140h+arg_10]
0x1800725d4  add     rsp, 110h
0x1800725db  pop     r15
0x1800725dd  pop     r14
0x1800725df  pop     r13
0x1800725e1  pop     r12
0x1800725e3  pop     rdi
0x1800725e4  pop     rsi
0x1800725e5  pop     rbp
0x1800725e6  retn
```
