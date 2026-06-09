# CAACDec::SetDecoderAsc(void)

- ea: `0x180041630`
- end: `0x180041835`
- name: `?SetDecoderAsc@CAACDec@@AEAAJXZ`
- size: `517`
- prototype: `__int64 __fastcall(CAACDec *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180048894`

## callees

- `0x180003af0`
- `0x180011b10`
- `0x180041630`
- `0x18004d320`
- `0x18004dc52`
- `0x18004dd14`
- `0x18009606c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800416aa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800416c2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800416aa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800416c2`

## string_xrefs

- `0x18004170d`: `CAACDec::OpenAACDec() ASC is not present for raw input. Opening core decoder with unknown channel config.`
- `0x1800416d9`: `CAACDec::OpenAACDec() ASC memory error`
- `0x18004180d`: `CAACDec::OpenAACDec() aacDecoder_ConfigRaw() failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall CAACDec::SetDecoderAsc(CAACDec *this)
{
  unsigned int v2; // ebx
  char *v3; // rsi
  __int64 v5; // rdx
  unsigned int v6; // ecx
  __int64 v7; // rsi
  __int64 v8; // rbx
  unsigned int v9; // ebp
  unsigned int v10; // r8d
  int v11; // ecx
  int v12; // eax
  _DWORD v13[2]; // [rsp+30h] [rbp-C8h]
  _BYTE *v14; // [rsp+38h] [rbp-C0h]
  _BYTE v15[128]; // [rsp+40h] [rbp-B8h] BYREF

  if ( !*((_DWORD *)this + 61517) || (v2 = *((_DWORD *)this + 61620)) == 0 )
  {
    TraceLoggingHelperBase::TraceVA(
      (CAACDec *)((char *)this + 246488),
      4u,
      "CAACDec::SetDecoderAsc",
      0xF2u,
      "CAACDec::OpenAACDec() ASC is not present for raw input. Opening core decoder with unknown channel config.");
    v2 = 2;
    v5 = 0;
    v6 = 14;
    while ( (unsigned int)v5 < 0x10 )
    {
      if ( *((_DWORD *)this + 61475) == dword_1800B5EC0[v5] )
      {
        v6 = v5;
        break;
      }
      v5 = (unsigned int)(v5 + 1);
    }
    v15[0] = (v6 >> 1) & 7 | 0x10;
    v15[1] = ((_BYTE)v6 << 7) | 0x78;
    goto LABEL_19;
  }
  v3 = (char *)this + 246352;
  if ( this == (CAACDec *)-246352LL || v2 > 0x80 )
  {
    memset_0(v15, 0, sizeof(v15));
    if ( v3 )
    {
      if ( v2 <= 0x80 )
      {
LABEL_11:
        TraceLoggingHelperBase::TraceVA(
          (CAACDec *)((char *)this + 246488),
          2u,
          "CAACDec::SetDecoderAsc",
          0xECu,
          "CAACDec::OpenAACDec() ASC memory error");
        return 2147500037LL;
      }
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
  memcpy_0(v15, v3, v2);
LABEL_19:
  v7 = *((_QWORD *)this + 30745);
  v13[0] = v2;
  v8 = 0;
  v14 = v15;
  v9 = *(_DWORD *)(v7 + 16);
  while ( 1 )
  {
    if ( (unsigned int)v8 >= v9 )
      return 0;
    v10 = v13[v8];
    if ( v10 )
    {
      v11 = transportDec_OutOfBandConfig(*(_QWORD *)(v7 + 24), *(const void **)&v15[8 * v8 - 8], v10, v8);
      if ( v11 )
        break;
    }
    v8 = (unsigned int)(v8 + 1);
  }
  if ( v11 == 515 )
  {
    v12 = 8203;
  }
  else
  {
    v12 = 8195;
    if ( v11 != 1026 )
      v12 = 5;
  }
  if ( (_DWORD)v8 )
  {
    *(_DWORD *)(v7 + 16) = v8;
    return 0;
  }
  TraceLoggingHelperBase::TraceVA(
    (CAACDec *)((char *)this + 246488),
    2u,
    "CAACDec::SetDecoderAsc",
    0x105u,
    "CAACDec::OpenAACDec() aacDecoder_ConfigRaw() failed with error 0x%x",
    v12);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180041630  push    rbx
0x180041632  push    rbp
0x180041633  push    rsi
0x180041634  push    rdi
0x180041635  sub     rsp, 0D8h
0x18004163c  mov     rax, cs:__security_cookie
0x180041643  xor     rax, rsp
0x180041646  mov     [rsp+0F8h+var_38], rax
0x18004164e  cmp     dword ptr [rcx+3C134h], 0
0x180041655  mov     rdi, rcx
0x180041658  jz      loc_18004170D
0x18004165e  mov     ebx, [rcx+3C2D0h]
0x180041664  test    ebx, ebx
0x180041666  jz      loc_18004170D
0x18004166c  lea     rsi, [rcx+3C250h]
0x180041673  mov     ebp, 80h
0x180041678  test    rsi, rsi
0x18004167b  jz      short loc_180041696
0x18004167d  cmp     ebx, ebp
0x18004167f  ja      short loc_180041696
0x180041681  mov     r8d, ebx; Size
0x180041684  lea     rcx, [rsp+0F8h+var_B8]; void *
0x180041689  mov     rdx, rsi; Src
0x18004168c  call    memcpy_0
0x180041691  jmp     loc_180041776
0x180041696  mov     r8, rbp; Size
0x180041699  lea     rcx, [rsp+0F8h+var_B8]; void *
0x18004169e  xor     edx, edx; Val
0x1800416a0  call    memset_0
0x1800416a5  test    rsi, rsi
0x1800416a8  jnz     short loc_1800416BE
0x1800416aa  call    cs:__imp__o__errno
0x1800416b1  nop     dword ptr [rax+rax+00h]
0x1800416b6  mov     dword ptr [rax], 16h
0x1800416bc  jmp     short loc_1800416D4
0x1800416be  cmp     ebx, ebp
0x1800416c0  jbe     short loc_1800416D9
0x1800416c2  call    cs:__imp__o__errno
0x1800416c9  nop     dword ptr [rax+rax+00h]
0x1800416ce  mov     dword ptr [rax], 22h ; '"'
0x1800416d4  call    _invalid_parameter_noinfo
0x1800416d9  lea     rax, aCaacdecOpenaac_5; "CAACDec::OpenAACDec() ASC memory error"
0x1800416e0  mov     r9d, 0ECh; unsigned int
0x1800416e6  lea     rcx, [rdi+3C2D8h]; this
0x1800416ed  mov     [rsp+0F8h+Format], rax; Format
0x1800416f2  lea     r8, aCaacdecSetdeco; "CAACDec::SetDecoderAsc"
0x1800416f9  mov     edx, 2; unsigned __int8
0x1800416fe  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180041703  mov     eax, 80004005h
0x180041708  jmp     loc_1800417E5
0x18004170d  lea     rax, aCaacdecOpenaac_3; "CAACDec::OpenAACDec() ASC is not presen"...
0x180041714  add     rcx, 3C2D8h; this
0x18004171b  mov     r9d, 0F2h; unsigned int
0x180041721  mov     [rsp+0F8h+Format], rax; Format
0x180041726  lea     r8, aCaacdecSetdeco; "CAACDec::SetDecoderAsc"
0x18004172d  mov     edx, 4; unsigned __int8
0x180041732  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180041737  mov     r8d, [rdi+3C08Ch]
0x18004173e  mov     ebx, 2
0x180041743  xor     edx, edx
0x180041745  lea     ecx, [rbx+0Ch]
0x180041748  cmp     edx, 10h
0x18004174b  jnb     short loc_180041760
0x18004174d  lea     r9, dword_1800B5EC0
0x180041754  cmp     r8d, [r9+rdx*4]
0x180041758  jz      short loc_18004175E
0x18004175a  inc     edx
0x18004175c  jmp     short loc_180041748
0x18004175e  mov     ecx, edx
0x180041760  mov     eax, ecx
0x180041762  shl     cl, 7
0x180041765  shr     eax, 1
0x180041767  and     al, 7
0x180041769  or      al, 10h
0x18004176b  or      cl, 78h
0x18004176e  mov     [rsp+0F8h+var_B8], al
0x180041772  mov     [rsp+0F8h+var_B7], cl
0x180041776  mov     rsi, [rdi+3C0C8h]
0x18004177d  lea     rax, [rsp+0F8h+var_B8]
0x180041782  mov     [rsp+0F8h+var_C8], ebx
0x180041786  xor     ebx, ebx
0x180041788  mov     [rsp+0F8h+var_C0], rax
0x18004178d  mov     ebp, [rsi+10h]
0x180041790  cmp     ebx, ebp
0x180041792  jnb     short loc_1800417E3
0x180041794  mov     r8d, [rsp+rbx*4+0F8h+var_C8]
0x180041799  test    r8d, r8d
0x18004179c  jz      short loc_1800417B5
0x18004179e  mov     rdx, [rsp+rbx*8+0F8h+var_C0]
0x1800417a3  mov     r9d, ebx
0x1800417a6  mov     rcx, [rsi+18h]
0x1800417aa  call    ?transportDec_OutOfBandConfig@@YA?AW4TRANSPORTDEC_ERROR@@QEAUTRANSPORTDEC@@PEAEII@Z; transportDec_OutOfBandConfig(TRANSPORTDEC * const,uchar *,uint,uint)
0x1800417af  mov     ecx, eax
0x1800417b1  test    eax, eax
0x1800417b3  jnz     short loc_1800417B9
0x1800417b5  inc     ebx
0x1800417b7  jmp     short loc_180041790
0x1800417b9  cmp     ecx, 203h
0x1800417bf  jz      short loc_1800417D6
0x1800417c1  cmp     ecx, 402h
0x1800417c7  mov     eax, 2003h
0x1800417cc  mov     edx, 5
0x1800417d1  cmovnz  eax, edx
0x1800417d4  jmp     short loc_1800417DB
0x1800417d6  mov     eax, 200Bh
0x1800417db  cmp     ebx, 1
0x1800417de  jb      short loc_180041802
0x1800417e0  mov     [rsi+10h], ebx
0x1800417e3  xor     eax, eax
0x1800417e5  mov     rcx, [rsp+0F8h+var_38]
0x1800417ed  xor     rcx, rsp; StackCookie
0x1800417f0  call    __security_check_cookie
0x1800417f5  add     rsp, 0D8h
0x1800417fc  pop     rdi
0x1800417fd  pop     rsi
0x1800417fe  pop     rbp
0x1800417ff  pop     rbx
0x180041800  retn
0x180041802  mov     [rsp+0F8h+var_D0], eax
0x180041806  lea     rcx, [rdi+3C2D8h]; this
0x18004180d  lea     rax, aCaacdecOpenaac_2; "CAACDec::OpenAACDec() aacDecoder_Config"...
0x180041814  mov     r9d, 105h; unsigned int
0x18004181a  lea     r8, aCaacdecSetdeco; "CAACDec::SetDecoderAsc"
0x180041821  mov     [rsp+0F8h+Format], rax; Format
0x180041826  mov     edx, 2; unsigned __int8
0x18004182b  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180041830  jmp     loc_180041703
```
