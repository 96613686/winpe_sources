# CIISGenObject::ResolveExtendedChildPath(ushort *,ushort * *,ushort * *)

- ea: `0x1800079c4`
- end: `0x180007c41`
- name: `?ResolveExtendedChildPath@CIISGenObject@@IEAAJPEAGPEAPEAG1@Z`
- size: `637`
- prototype: `int(CIISGenObject *__hidden this, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007e04`

## callees

- `0x1800079c4`
- `0x180013f94`
- `0x180013fd0`
- `0x18001beb8`
- `0x18001d66a`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180007ae6`
- `msvcrt!wcscat_s` at `0x180007bd8`
- `msvcrt!wcscat_s` at `0x180007be7`
- `msvcrt!wcscat_s` at `0x180007ae6`
- `msvcrt!wcscat_s` at `0x180007bd8`
- `msvcrt!wcscat_s` at `0x180007be7`
- `msvcrt!wcsrchr` at `0x180007af1`
- `msvcrt!wcsrchr` at `0x180007bf5`
- `msvcrt!wcsrchr` at `0x180007af1`
- `msvcrt!wcsrchr` at `0x180007bf5`
- `msvcrt!wcscpy_s` at `0x180007ab6`
- `msvcrt!wcscpy_s` at `0x180007b7d`
- `msvcrt!wcscpy_s` at `0x180007bc5`
- `msvcrt!wcscpy_s` at `0x180007ab6`
- `msvcrt!wcscpy_s` at `0x180007b7d`
- `msvcrt!wcscpy_s` at `0x180007bc5`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180007a57`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180007a57`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180007c15`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180007c15`

## pseudocode

```c
__int64 __fastcall CIISGenObject::ResolveExtendedChildPath(
        CIISGenObject *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int v4; // r14d
  unsigned __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  rsize_t v12; // r15
  size_t v13; // rbx
  int ADsClass; // ebx
  wchar_t *v15; // rax
  wchar_t *v16; // rdi
  const wchar_t *v17; // r8
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rax
  wchar_t *v22; // rax
  int v23; // ecx
  int v24; // edx
  int v25; // eax
  const wchar_t *v26; // r8
  wchar_t *v27; // rax
  unsigned int v29; // [rsp+20h] [rbp-288h]
  wchar_t Destination[264]; // [rsp+40h] [rbp-268h] BYREF

  v4 = 0;
  *a3 = 0;
  *a4 = 0;
  memset_0(Destination, 0, 0x208u);
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(*((_QWORD *)this + 3) + 2 * v10) );
  v11 = (unsigned int)(v10 + 2 + v9);
  v12 = (unsigned int)v11;
  v13 = 2 * v11;
  if ( (unsigned __int64)(2 * v11) <= 0xFFFFFFFF )
  {
    v15 = (wchar_t *)AllocADsMem(2 * (int)v11);
    v16 = v15;
    if ( v15 )
    {
      memset_0(v15, 0, v13);
      v17 = (const wchar_t *)*((_QWORD *)this + 18);
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(*((_QWORD *)this + 3) + 2 * v18) );
      v19 = -1;
      do
        ++v19;
      while ( v17[v19] );
      if ( v19 <= v18 )
      {
        wcscpy_s(v16, v12, v17);
        v20 = -1;
        do
          ++v20;
        while ( v16[v20] );
        if ( v16[(unsigned int)(v20 - 1)] != 47 )
          v16[(unsigned int)v20] = 47;
        wcscat_s(v16, v12, a2);
LABEL_20:
        v21 = wcsrchr(v16, 0x2Fu);
        if ( v21 )
          *v21 = 0;
        while ( 1 )
        {
          if ( v4 )
          {
            ADsClass = MetaBaseGetADsClass(
                         *((struct IMSAdminBaseW **)this + 25),
                         v16,
                         *((struct IIsSchema **)this + 26),
                         Destination,
                         v29);
            if ( ADsClass < 0 )
              goto LABEL_40;
            goto LABEL_36;
          }
          v22 = v16;
          do
          {
            v23 = *(wchar_t *)((char *)v22 + *((_QWORD *)this + 18) - (_QWORD)v16);
            v24 = *v22 - v23;
            if ( v24 )
              break;
            ++v22;
          }
          while ( v23 );
          if ( !v24 )
            break;
          v25 = MetaBaseDetectKey(*((struct IMSAdminBaseW **)this + 25), v16);
          ADsClass = v25;
          if ( v25 < 0 )
          {
            if ( (_WORD)v25 != 3 )
              goto LABEL_40;
            goto LABEL_20;
          }
          v4 = 1;
        }
        v26 = (const wchar_t *)*((_QWORD *)this + 5);
        do
          ++v8;
        while ( v26[v8] );
        if ( v8 >= 0x104 )
          goto LABEL_14;
        wcscpy_s(Destination, 0x104u, v26);
LABEL_36:
        ADsClass = ADsAllocString(Destination, a4);
        if ( ADsClass >= 0 )
        {
          wcscpy_s(v16, v12, *((const wchar_t **)this + 3));
          wcscat_s(v16, v12, L"/");
          wcscat_s(v16, v12, a2);
          v27 = wcsrchr(v16, 0x2Fu);
          if ( v27 )
            *v27 = 0;
          ADsClass = ADsAllocString(v16, a3);
        }
      }
      else
      {
LABEL_14:
        ADsClass = -2147463160;
      }
LABEL_40:
      FreeADsMem(v16);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024362;
  }
  return (unsigned int)ADsClass;
}

```

## disassembly

```asm
0x1800079c4  push    rbx
0x1800079c6  push    rbp
0x1800079c7  push    rsi
0x1800079c8  push    rdi
0x1800079c9  push    r12
0x1800079cb  push    r13
0x1800079cd  push    r14
0x1800079cf  push    r15
0x1800079d1  sub     rsp, 268h
0x1800079d8  mov     rax, cs:__security_cookie
0x1800079df  xor     rax, rsp
0x1800079e2  mov     [rsp+2A8h+var_58], rax
0x1800079ea  xor     r14d, r14d
0x1800079ed  mov     [rsp+2A8h+var_278], r9
0x1800079f2  mov     [r8], r14
0x1800079f5  mov     r13, r8
0x1800079f8  mov     r12, rdx
0x1800079fb  mov     [r9], r14
0x1800079fe  mov     rbp, rcx
0x180007a01  mov     r8d, 208h; Size
0x180007a07  xor     edx, edx; Val
0x180007a09  lea     rcx, [rsp+2A8h+Destination]; void *
0x180007a0e  call    memset_0
0x180007a13  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007a17  mov     rcx, rsi
0x180007a1a  inc     rcx
0x180007a1d  cmp     [r12+rcx*2], r14w
0x180007a22  jnz     short loc_180007A1A
0x180007a24  mov     rdx, [rbp+18h]
0x180007a28  mov     rax, rsi
0x180007a2b  inc     rax
0x180007a2e  cmp     [rdx+rax*2], r14w
0x180007a33  jnz     short loc_180007A2B
0x180007a35  add     eax, 2
0x180007a38  add     ecx, eax
0x180007a3a  mov     eax, 0FFFFFFFFh
0x180007a3f  mov     r15d, ecx
0x180007a42  lea     rbx, [rcx+rcx]
0x180007a46  cmp     rbx, rax
0x180007a49  jbe     short loc_180007A55
0x180007a4b  mov     ebx, 80070216h
0x180007a50  jmp     loc_180007C1B
0x180007a55  add     ecx, ecx; cb
0x180007a57  call    cs:__imp_AllocADsMem
0x180007a5d  mov     rdi, rax
0x180007a60  test    rax, rax
0x180007a63  jnz     short loc_180007A6F
0x180007a65  mov     ebx, 8007000Eh
0x180007a6a  jmp     loc_180007C1B
0x180007a6f  mov     r8, rbx; Size
0x180007a72  xor     edx, edx; Val
0x180007a74  mov     rcx, rdi; void *
0x180007a77  call    memset_0
0x180007a7c  mov     r8, [rbp+90h]; Source
0x180007a83  mov     rcx, rsi
0x180007a86  mov     rax, [rbp+18h]
0x180007a8a  inc     rcx
0x180007a8d  cmp     [rax+rcx*2], r14w
0x180007a92  jnz     short loc_180007A8A
0x180007a94  mov     rax, rsi
0x180007a97  inc     rax
0x180007a9a  cmp     [r8+rax*2], r14w
0x180007a9f  jnz     short loc_180007A97
0x180007aa1  cmp     rax, rcx
0x180007aa4  jbe     short loc_180007AB0
0x180007aa6  mov     ebx, 80005008h
0x180007aab  jmp     loc_180007C12
0x180007ab0  mov     rdx, r15; SizeInWords
0x180007ab3  mov     rcx, rdi; Destination
0x180007ab6  call    cs:__imp_wcscpy_s
0x180007abc  mov     rdx, rsi
0x180007abf  inc     rdx
0x180007ac2  cmp     [rdi+rdx*2], r14w
0x180007ac7  jnz     short loc_180007ABF
0x180007ac9  lea     eax, [rdx-1]
0x180007acc  mov     ebx, 2Fh ; '/'
0x180007ad1  cmp     [rdi+rax*2], bx
0x180007ad5  jz      short loc_180007ADD
0x180007ad7  mov     eax, edx
0x180007ad9  mov     [rdi+rax*2], bx
0x180007add  mov     r8, r12; Source
0x180007ae0  mov     rdx, r15; SizeInWords
0x180007ae3  mov     rcx, rdi; Destination
0x180007ae6  call    cs:__imp_wcscat_s
0x180007aec  mov     edx, ebx; Ch
0x180007aee  mov     rcx, rdi; Str
0x180007af1  call    cs:__imp_wcsrchr
0x180007af7  xor     r9d, r9d
0x180007afa  test    rax, rax
0x180007afd  jz      short loc_180007B03
0x180007aff  mov     [rax], r9w
0x180007b03  test    r14d, r14d
0x180007b06  jnz     short loc_180007B85
0x180007b08  mov     r8, [rbp+90h]
0x180007b0f  mov     rax, rdi
0x180007b12  sub     r8, rdi
0x180007b15  movzx   edx, word ptr [rax]
0x180007b18  movzx   ecx, word ptr [rax+r8]
0x180007b1d  sub     edx, ecx
0x180007b1f  jnz     short loc_180007B29
0x180007b21  add     rax, 2
0x180007b25  test    ecx, ecx
0x180007b27  jnz     short loc_180007B15
0x180007b29  test    edx, edx
0x180007b2b  jz      short loc_180007B5C
0x180007b2d  mov     rcx, [rbp+0C8h]; struct IMSAdminBaseW *
0x180007b34  mov     rdx, rdi; unsigned __int16 *
0x180007b37  call    ?MetaBaseDetectKey@@YAJPEAUIMSAdminBaseW@@PEBG@Z; MetaBaseDetectKey(IMSAdminBaseW *,ushort const *)
0x180007b3c  xor     r9d, r9d
0x180007b3f  mov     ebx, eax
0x180007b41  test    eax, eax
0x180007b43  js      short loc_180007B4B
0x180007b45  lea     r14d, [r9+1]
0x180007b49  jmp     short loc_180007B03
0x180007b4b  cmp     ax, 3
0x180007b4f  jnz     loc_180007C12
0x180007b55  mov     edx, 2Fh ; '/'
0x180007b5a  jmp     short loc_180007AEE
0x180007b5c  mov     r8, [rbp+28h]; Source
0x180007b60  inc     rsi
0x180007b63  cmp     [r8+rsi*2], r9w
0x180007b68  jnz     short loc_180007B60
0x180007b6a  mov     edx, 104h; SizeInWords
0x180007b6f  cmp     rsi, rdx
0x180007b72  jnb     loc_180007AA6
0x180007b78  lea     rcx, [rsp+2A8h+Destination]; Destination
0x180007b7d  call    cs:__imp_wcscpy_s
0x180007b83  jmp     short loc_180007BA6
0x180007b85  mov     r8, [rbp+0D0h]; this
0x180007b8c  lea     r9, [rsp+2A8h+Destination]; unsigned __int16 *
0x180007b91  mov     rcx, [rbp+0C8h]; struct IMSAdminBaseW *
0x180007b98  mov     rdx, rdi; Str
0x180007b9b  call    ?MetaBaseGetADsClass@@YAJPEAUIMSAdminBaseW@@PEAGPEAVIIsSchema@@1K@Z; MetaBaseGetADsClass(IMSAdminBaseW *,ushort *,IIsSchema *,ushort *,ulong)
0x180007ba0  mov     ebx, eax
0x180007ba2  test    eax, eax
0x180007ba4  js      short loc_180007C12
0x180007ba6  mov     rdx, [rsp+2A8h+var_278]
0x180007bab  lea     rcx, [rsp+2A8h+Destination]
0x180007bb0  call    ADsAllocString
0x180007bb5  mov     ebx, eax
0x180007bb7  test    eax, eax
0x180007bb9  js      short loc_180007C12
0x180007bbb  mov     r8, [rbp+18h]; Source
0x180007bbf  mov     rdx, r15; SizeInWords
0x180007bc2  mov     rcx, rdi; Destination
0x180007bc5  call    cs:__imp_wcscpy_s
0x180007bcb  lea     r8, Source; "/"
0x180007bd2  mov     rdx, r15; SizeInWords
0x180007bd5  mov     rcx, rdi; Destination
0x180007bd8  call    cs:__imp_wcscat_s
0x180007bde  mov     r8, r12; Source
0x180007be1  mov     rdx, r15; SizeInWords
0x180007be4  mov     rcx, rdi; Destination
0x180007be7  call    cs:__imp_wcscat_s
0x180007bed  mov     edx, 2Fh ; '/'; Ch
0x180007bf2  mov     rcx, rdi; Str
0x180007bf5  call    cs:__imp_wcsrchr
0x180007bfb  test    rax, rax
0x180007bfe  jz      short loc_180007C05
0x180007c00  xor     ecx, ecx
0x180007c02  mov     [rax], cx
0x180007c05  mov     rdx, r13
0x180007c08  mov     rcx, rdi
0x180007c0b  call    ADsAllocString
0x180007c10  mov     ebx, eax
0x180007c12  mov     rcx, rdi; pMem
0x180007c15  call    cs:__imp_FreeADsMem
0x180007c1b  mov     eax, ebx
0x180007c1d  mov     rcx, [rsp+2A8h+var_58]
0x180007c25  xor     rcx, rsp; StackCookie
0x180007c28  call    __security_check_cookie
0x180007c2d  add     rsp, 268h
0x180007c34  pop     r15
0x180007c36  pop     r14
0x180007c38  pop     r13
0x180007c3a  pop     r12
0x180007c3c  pop     rdi
0x180007c3d  pop     rsi
0x180007c3e  pop     rbp
0x180007c3f  pop     rbx
0x180007c40  retn
```
