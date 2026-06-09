# CEncodingStream::CommitToStream(ulong)

- ea: `0x180012840`
- end: `0x180012a92`
- name: `?CommitToStream@CEncodingStream@@UEAAJK@Z`
- size: `594`
- prototype: `__int64 __fastcall(CEncodingStream *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180012840`
- `0x180012a98`
- `0x180012afc`
- `0x180014e68`
- `0x1800171c4`
- `0x180021a30`
- `0x180022348`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800128eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800128eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180012955`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180012967`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180012955`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180012967`

## pseudocode

```c
__int64 __fastcall CEncodingStream::CommitToStream(CEncodingStream *this, unsigned int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  HRESULT v6; // eax
  int v7; // ecx
  HGLOBAL *v8; // rsi
  char *v9; // r14
  unsigned int EncodingHeaderSize; // eax
  ULONG v11; // r15d
  char *v12; // r14
  int v13; // eax
  const wchar_t *v14; // r15
  unsigned int v15; // esi
  unsigned int v16; // r14d
  unsigned int v17; // r8d
  const wchar_t *v18; // rdx
  ULONG pulResult; // [rsp+30h] [rbp-98h] BYREF
  int v21[3]; // [rsp+34h] [rbp-94h] BYREF
  _BYTE v22[16]; // [rsp+40h] [rbp-88h] BYREF
  ULONGLONG ullOperand; // [rsp+50h] [rbp-78h]

  v4 = 0;
  memset_0(v22, 0, 0x50u);
  v5 = *((_QWORD *)this + 6);
  pulResult = 0;
  v21[0] = 0;
  if ( *((_QWORD *)this + 5) == v5 )
    goto LABEL_16;
  v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v5 + 96LL))(v5, v22, 1);
  v4 = v6;
  if ( v6 >= 0 )
  {
    v6 = ULongLongToULong(ullOperand, &pulResult);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v8 = (HGLOBAL *)((char *)this + 32);
      v9 = (char *)GlobalLock(*((HGLOBAL *)this + 4));
      if ( !v9 )
      {
        v4 = -2147024882;
        goto LABEL_40;
      }
      EncodingHeaderSize = CEncodingStream::GetEncodingHeaderSize(this);
      v11 = pulResult - EncodingHeaderSize;
      v12 = &v9[EncodingHeaderSize];
      v13 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, int *))(**((_QWORD **)this + 5) + 32LL))(
              *((_QWORD *)this + 5),
              v12,
              pulResult - EncodingHeaderSize,
              v21);
      v4 = v13;
      if ( v13 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v13);
        if ( v12 )
          GlobalUnlock(*v8);
        return v4;
      }
      GlobalUnlock(*v8);
      if ( v21[0] != v11 )
      {
        v4 = -2003292303;
        goto LABEL_40;
      }
LABEL_16:
      if ( a2 )
      {
        if ( (*((_BYTE *)this + 24) & 1) != 0 )
        {
          v14 = (const wchar_t *)"                                                                                                    \n";
          v15 = 101;
          goto LABEL_23;
        }
        if ( (*((_BYTE *)this + 24) & 2) != 0 )
        {
          v14 = L"                                                                                                    \n";
          v15 = 202;
          goto LABEL_23;
        }
        if ( (*((_BYTE *)this + 24) & 4) == 0 )
          goto LABEL_39;
        v14 = L" ";
        v15 = 404;
LABEL_23:
        while ( a2 )
        {
          v16 = v15;
          if ( v15 >= a2 )
            v16 = a2;
          v6 = WriteFullBufferToStream(*((struct IStream **)this + 5), v14, v16);
          v4 = v6;
          if ( v6 < 0 )
          {
            if ( g_doStackCaptures )
              goto LABEL_4;
            return v4;
          }
          a2 -= v16;
        }
      }
      if ( !*((_DWORD *)this + 7) )
        return v4;
      if ( (*((_BYTE *)this + 24) & 1) != 0 )
      {
        v17 = 19;
        v18 = (const wchar_t *)"<?xpacket end='w'?>";
        goto LABEL_33;
      }
      if ( (*((_BYTE *)this + 24) & 2) != 0 )
      {
        v17 = 38;
        v18 = L"<?xpacket end='w'?>";
        goto LABEL_33;
      }
      if ( (*((_BYTE *)this + 24) & 4) != 0 )
      {
        v17 = 76;
        v18 = L"<";
LABEL_33:
        v6 = WriteFullBufferToStream(*((struct IStream **)this + 5), v18, v17);
        v4 = v6;
        if ( v6 >= 0 )
          return v4;
        goto LABEL_3;
      }
LABEL_39:
      v4 = -2003292317;
LABEL_40:
      if ( g_doStackCaptures )
      {
        v7 = v4;
        goto LABEL_42;
      }
      return v4;
    }
  }
LABEL_3:
  if ( g_doStackCaptures )
  {
LABEL_4:
    v7 = v6;
LABEL_42:
    DoStackCapture(v7);
  }
  return v4;
}

```

## disassembly

```asm
0x180012840  mov     [rsp+arg_10], rbx
0x180012845  mov     [rsp+arg_18], rbp
0x18001284a  push    rsi
0x18001284b  push    rdi
0x18001284c  push    r12
0x18001284e  push    r14
0x180012850  push    r15
0x180012852  sub     rsp, 0A0h
0x180012859  mov     rax, cs:__security_cookie
0x180012860  xor     rax, rsp
0x180012863  mov     [rsp+0C8h+var_38], rax
0x18001286b  xor     r12d, r12d
0x18001286e  mov     ebp, edx
0x180012870  mov     rdi, rcx
0x180012873  xor     edx, edx; Val
0x180012875  lea     rcx, [rsp+0C8h+var_88]; void *
0x18001287a  mov     ebx, r12d
0x18001287d  lea     r8d, [r12+50h]; Size
0x180012882  call    memset_0
0x180012887  mov     rcx, [rdi+30h]
0x18001288b  mov     [rsp+0C8h+pulResult], r12d
0x180012890  mov     [rsp+0C8h+var_94], r12d
0x180012895  cmp     [rdi+28h], rcx
0x180012899  jz      loc_18001297E
0x18001289f  mov     rax, [rcx]
0x1800128a2  lea     r8d, [r12+1]
0x1800128a7  lea     rdx, [rsp+0C8h+var_88]
0x1800128ac  mov     rax, [rax+60h]
0x1800128b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b5  mov     ebx, eax
0x1800128b7  test    eax, eax
0x1800128b9  jns     short loc_1800128CF
0x1800128bb  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800128c2  jz      loc_180012A64
0x1800128c8  mov     ecx, eax
0x1800128ca  jmp     loc_180012A5F
0x1800128cf  mov     rcx, [rsp+0C8h+ullOperand]; ullOperand
0x1800128d4  lea     rdx, [rsp+0C8h+pulResult]; pulResult
0x1800128d9  call    ULongLongToULong
0x1800128de  mov     ebx, eax
0x1800128e0  test    eax, eax
0x1800128e2  js      short loc_1800128BB
0x1800128e4  lea     rsi, [rdi+20h]
0x1800128e8  mov     rcx, [rsi]; hMem
0x1800128eb  call    cs:__imp_GlobalLock
0x1800128f1  mov     r14, rax
0x1800128f4  test    rax, rax
0x1800128f7  jnz     short loc_180012903
0x1800128f9  mov     ebx, 8007000Eh
0x1800128fe  jmp     loc_180012A54
0x180012903  mov     rcx, rdi; this
0x180012906  call    ?GetEncodingHeaderSize@CEncodingStream@@AEAAKXZ; CEncodingStream::GetEncodingHeaderSize(void)
0x18001290b  mov     r15d, [rsp+0C8h+pulResult]
0x180012910  lea     r9, [rsp+0C8h+var_94]
0x180012915  mov     ecx, eax
0x180012917  sub     r15d, eax
0x18001291a  add     r14, rcx
0x18001291d  mov     r8d, r15d
0x180012920  mov     rcx, [rdi+28h]
0x180012924  mov     rdx, r14
0x180012927  mov     rax, [rcx]
0x18001292a  mov     rax, [rax+20h]
0x18001292e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012933  mov     ebx, eax
0x180012935  test    eax, eax
0x180012937  jns     short loc_180012964
0x180012939  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012940  jz      short loc_180012960
0x180012942  mov     ecx, eax; int
0x180012944  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012949  test    r14, r14
0x18001294c  jz      loc_180012A64
0x180012952  mov     rcx, [rsi]; hMem
0x180012955  call    cs:__imp_GlobalUnlock
0x18001295b  jmp     loc_180012A64
0x180012960  test    eax, eax
0x180012962  js      short loc_180012949
0x180012964  mov     rcx, [rsi]; hMem
0x180012967  call    cs:__imp_GlobalUnlock
0x18001296d  cmp     [rsp+0C8h+var_94], r15d
0x180012972  jz      short loc_18001297E
0x180012974  mov     ebx, 88982F71h
0x180012979  jmp     loc_180012A54
0x18001297e  test    ebp, ebp
0x180012980  jz      short loc_1800129F8
0x180012982  test    byte ptr [rdi+18h], 1
0x180012986  jz      short loc_180012996
0x180012988  lea     r15, asc_1800384B0; "                                       "...
0x18001298f  mov     esi, 65h ; 'e'
0x180012994  jmp     short loc_1800129C0
0x180012996  test    byte ptr [rdi+18h], 2
0x18001299a  jz      short loc_1800129AA
0x18001299c  lea     r15, asc_1800395D0; "                                       "...
0x1800129a3  mov     esi, 0CAh
0x1800129a8  jmp     short loc_1800129C0
0x1800129aa  test    byte ptr [rdi+18h], 4
0x1800129ae  jz      loc_180012A4F
0x1800129b4  lea     r15, asc_1800396A0; " "
0x1800129bb  mov     esi, 194h
0x1800129c0  test    ebp, ebp
0x1800129c2  jz      short loc_1800129F8
0x1800129c4  mov     rcx, [rdi+28h]; struct IStream *
0x1800129c8  cmp     esi, ebp
0x1800129ca  mov     r14d, esi
0x1800129cd  mov     rdx, r15; void *
0x1800129d0  cmovnb  r14d, ebp
0x1800129d4  mov     r8d, r14d; unsigned int
0x1800129d7  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800129dc  mov     ebx, eax
0x1800129de  test    eax, eax
0x1800129e0  jns     short loc_1800129F3
0x1800129e2  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800129e9  jnz     loc_1800128C8
0x1800129ef  test    eax, eax
0x1800129f1  js      short loc_180012A64
0x1800129f3  sub     ebp, r14d
0x1800129f6  jmp     short loc_1800129C0
0x1800129f8  cmp     [rdi+1Ch], r12d
0x1800129fc  jz      short loc_180012A64
0x1800129fe  test    byte ptr [rdi+18h], 1
0x180012a02  jz      short loc_180012A25
0x180012a04  mov     r8d, 13h; unsigned int
0x180012a0a  lea     rdx, aXpacketEndW; "<?xpacket end='w'?>"
0x180012a11  mov     rcx, [rdi+28h]; struct IStream *
0x180012a15  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x180012a1a  mov     ebx, eax
0x180012a1c  test    eax, eax
0x180012a1e  jns     short loc_180012A64
0x180012a20  jmp     loc_1800128BB
0x180012a25  test    byte ptr [rdi+18h], 2
0x180012a29  jz      short loc_180012A3A
0x180012a2b  mov     r8d, 26h ; '&'
0x180012a31  lea     rdx, aXpacketEndW_0; "<?xpacket end='w'?>"
0x180012a38  jmp     short loc_180012A11
0x180012a3a  test    byte ptr [rdi+18h], 4
0x180012a3e  jz      short loc_180012A4F
0x180012a40  mov     r8d, 4Ch ; 'L'
0x180012a46  lea     rdx, asc_180038460; "<"
0x180012a4d  jmp     short loc_180012A11
0x180012a4f  mov     ebx, 88982F63h
0x180012a54  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012a5b  jz      short loc_180012A64
0x180012a5d  mov     ecx, ebx; int
0x180012a5f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012a64  mov     eax, ebx
0x180012a66  mov     rcx, [rsp+0C8h+var_38]
0x180012a6e  xor     rcx, rsp; StackCookie
0x180012a71  call    __security_check_cookie
0x180012a76  lea     r11, [rsp+0C8h+var_28]
0x180012a7e  mov     rbx, [r11+40h]
0x180012a82  mov     rbp, [r11+48h]
0x180012a86  mov     rsp, r11
0x180012a89  pop     r15
0x180012a8b  pop     r14
0x180012a8d  pop     r12
0x180012a8f  pop     rdi
0x180012a90  pop     rsi
0x180012a91  retn
```
