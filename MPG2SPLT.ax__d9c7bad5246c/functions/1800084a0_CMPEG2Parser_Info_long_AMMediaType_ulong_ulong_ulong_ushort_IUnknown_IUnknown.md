# CMPEG2Parser::Info(long,_AMMediaType * *,ulong *,ulong *,ulong *,ushort * *,IUnknown * *,IUnknown * *)

- ea: `0x1800084a0`
- end: `0x180008687`
- name: `?Info@CMPEG2Parser@@UEAAJJPEAPEAU_AMMediaType@@PEAK11PEAPEAGPEAPEAUIUnknown@@3@Z`
- size: `487`
- prototype: `__int64 __fastcall(CMPEG2Parser *__hidden this, int, struct _AMMediaType **, unsigned int *, unsigned int *, unsigned int *, unsigned __int16 **, struct IUnknown **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001460`
- `0x180001f04`
- `0x180006a9c`
- `0x180007214`
- `0x1800084a0`
- `0x180034010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008644`
- `ole32!CoTaskMemFree` at `0x180008644`

## pseudocode

```c
__int64 __fastcall CMPEG2Parser::Info(
        CMPEG2Parser *this,
        __int64 a2,
        struct _AMMediaType **a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int16 **a7,
        struct IUnknown **a8,
        struct IUnknown **a9)
{
  unsigned int v10; // edi
  __int64 i; // rcx
  __int64 v14; // rbp
  const wchar_t *v15; // r8
  __int64 v16; // r9
  int v17; // eax
  struct _AMMediaType *MediaType; // rax
  struct _AMMediaType **v19; // [rsp+20h] [rbp-88h]
  wchar_t Buffer[20]; // [rsp+30h] [rbp-78h] BYREF

  v10 = a2;
  v19 = a3;
  if ( (int)a2 >= *((_DWORD *)this + 307) )
    return 2147942487LL;
  if ( !*((_DWORD *)this + 11) )
    return 2147500037LL;
  LOBYTE(a2) = *((_BYTE *)this + 29);
  for ( i = *((_QWORD *)this + 2 * *((unsigned __int8 *)this + 28) - 369); ; i = *(_QWORD *)(i + 40) )
  {
    if ( !i )
      return 2147500037LL;
    if ( !*(_DWORD *)(i + 12) || *(_BYTE *)(i + 9) == (_BYTE)a2 )
      break;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(i + 32) + 48LL))(*(_QWORD *)(i + 32), a2);
  if ( !v14 )
    return 2147549183LL;
  if ( a7 )
  {
    if ( *((_BYTE *)this + 28) == 0xBD )
    {
      v15 = L"AC3(%d)";
      v16 = v10;
      if ( (*((_BYTE *)this + 29) & 0xF8) != 0x80 )
        v15 = L"LPCM(%d)";
    }
    else
    {
      v15 = L"Stream(%2.2X)";
      v16 = v10 + 192;
    }
    swprintf_s(Buffer, 0x14u, v15, v16, v19);
    if ( (unsigned int)AMGetWideString(Buffer) )
      return 2147942414LL;
  }
  if ( a4 )
  {
    *a4 = 0;
    v17 = *((unsigned __int8 *)this + 28);
    if ( (_BYTE)v17 != 0xBD )
    {
      if ( v17 != v10 + 192 )
        goto LABEL_25;
      goto LABEL_24;
    }
    if ( v10 == (*((_BYTE *)this + 29) & 7) )
LABEL_24:
      *a4 = 1;
  }
LABEL_25:
  if ( a9 )
    *a9 = 0;
  if ( a6 )
    *a6 = 0;
  if ( v19 )
  {
    MediaType = CreateMediaType((const struct _AMMediaType *)(v14 + 104));
    *v19 = MediaType;
    if ( !MediaType )
    {
      if ( a7 )
        CoTaskMemFree(*a7);
      return 2147942414LL;
    }
  }
  if ( a5 )
    *a5 = 0;
  if ( a8 )
    (**(void (__fastcall ***)(__int64, GUID *))(v14 + 24))(v14 + 24, &IID_IUnknown);
  return 0;
}

```

## disassembly

```asm
0x1800084a0  push    rbx
0x1800084a2  push    rbp
0x1800084a3  push    rsi
0x1800084a4  push    rdi
0x1800084a5  push    r12
0x1800084a7  push    r13
0x1800084a9  push    r14
0x1800084ab  push    r15
0x1800084ad  sub     rsp, 68h
0x1800084b1  mov     rax, cs:__security_cookie
0x1800084b8  xor     rax, rsp
0x1800084bb  mov     [rsp+0A8h+var_50], rax
0x1800084c0  mov     r14, r9
0x1800084c3  mov     rax, [rsp+0A8h+arg_38]
0x1800084cb  mov     edi, edx
0x1800084cd  mov     r15, [rsp+0A8h+arg_20]
0x1800084d5  mov     rbx, rcx
0x1800084d8  mov     r12, [rsp+0A8h+arg_28]
0x1800084e0  mov     rsi, [rsp+0A8h+arg_30]
0x1800084e8  mov     r13, [rsp+0A8h+arg_40]
0x1800084f0  mov     [rsp+0A8h+var_80], rax
0x1800084f5  mov     [rsp+0A8h+var_88], r8
0x1800084fa  cmp     edx, [rcx+4CCh]
0x180008500  jl      short loc_180008509
0x180008502  mov     eax, 80070057h
0x180008507  jmp     short loc_18000853C
0x180008509  cmp     dword ptr [rcx+2Ch], 0
0x18000850d  jz      short loc_180008537
0x18000850f  movzx   eax, byte ptr [rcx+1Ch]
0x180008513  mov     dl, [rcx+1Dh]
0x180008516  add     rax, rax
0x180008519  mov     rcx, [rcx+rax*8-0B88h]
0x180008521  jmp     short loc_180008532
0x180008523  cmp     dword ptr [rcx+0Ch], 0
0x180008527  jz      short loc_18000855A
0x180008529  cmp     [rcx+9], dl
0x18000852c  jz      short loc_18000855A
0x18000852e  mov     rcx, [rcx+28h]
0x180008532  test    rcx, rcx
0x180008535  jnz     short loc_180008523
0x180008537  mov     eax, 80004005h
0x18000853c  mov     rcx, [rsp+0A8h+var_50]
0x180008541  xor     rcx, rsp; StackCookie
0x180008544  call    __security_check_cookie
0x180008549  add     rsp, 68h
0x18000854d  pop     r15
0x18000854f  pop     r14
0x180008551  pop     r13
0x180008553  pop     r12
0x180008555  pop     rdi
0x180008556  pop     rsi
0x180008557  pop     rbp
0x180008558  pop     rbx
0x180008559  retn
0x18000855a  test    rcx, rcx
0x18000855d  jz      short loc_180008537
0x18000855f  mov     rcx, [rcx+20h]
0x180008563  mov     rax, [rcx]
0x180008566  mov     rax, [rax+30h]
0x18000856a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000856f  mov     rbp, rax
0x180008572  test    rax, rax
0x180008575  jnz     short loc_18000857E
0x180008577  mov     eax, 8000FFFFh
0x18000857c  jmp     short loc_18000853C
0x18000857e  test    rsi, rsi
0x180008581  jz      short loc_1800085D5
0x180008583  cmp     byte ptr [rbx+1Ch], 0BDh
0x180008587  jnz     short loc_1800085A7
0x180008589  mov     al, [rbx+1Dh]
0x18000858c  lea     rcx, aLpcmD; "LPCM(%d)"
0x180008593  and     al, 0F8h
0x180008595  lea     r8, aAc3D; "AC3(%d)"
0x18000859c  cmp     al, 80h
0x18000859e  mov     r9d, edi
0x1800085a1  cmovnz  r8, rcx
0x1800085a5  jmp     short loc_1800085B5
0x1800085a7  lea     r8, Format; "Stream(%2.2X)"
0x1800085ae  lea     r9d, [rdi+0C0h]
0x1800085b5  mov     edx, 14h; BufferCount
0x1800085ba  lea     rcx, [rsp+0A8h+Buffer]; Buffer
0x1800085bf  call    swprintf_s
0x1800085c4  mov     rdx, rsi
0x1800085c7  lea     rcx, [rsp+0A8h+Buffer]; Src
0x1800085cc  call    AMGetWideString
0x1800085d1  test    eax, eax
0x1800085d3  jnz     short loc_18000864A
0x1800085d5  test    r14, r14
0x1800085d8  jz      short loc_180008607
0x1800085da  mov     dword ptr [r14], 0
0x1800085e1  movzx   eax, byte ptr [rbx+1Ch]
0x1800085e5  cmp     al, 0BDh
0x1800085e7  jz      short loc_1800085F5
0x1800085e9  lea     ecx, [rdi+0C0h]
0x1800085ef  cmp     eax, ecx
0x1800085f1  jz      short loc_180008600
0x1800085f3  jmp     short loc_180008607
0x1800085f5  movzx   eax, byte ptr [rbx+1Dh]
0x1800085f9  and     eax, 7
0x1800085fc  cmp     edi, eax
0x1800085fe  jnz     short loc_180008607
0x180008600  mov     dword ptr [r14], 1
0x180008607  test    r13, r13
0x18000860a  jz      short loc_180008614
0x18000860c  mov     qword ptr [r13+0], 0
0x180008614  test    r12, r12
0x180008617  jz      short loc_180008621
0x180008619  mov     dword ptr [r12], 0
0x180008621  mov     rbx, [rsp+0A8h+var_88]
0x180008626  test    rbx, rbx
0x180008629  jz      short loc_180008654
0x18000862b  lea     rcx, [rbp+68h]; struct _AMMediaType *
0x18000862f  call    ?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z; CreateMediaType(_AMMediaType const *)
0x180008634  mov     [rbx], rax
0x180008637  test    rax, rax
0x18000863a  jnz     short loc_180008654
0x18000863c  test    rsi, rsi
0x18000863f  jz      short loc_18000864A
0x180008641  mov     rcx, [rsi]; pv
0x180008644  call    cs:__imp_CoTaskMemFree
0x18000864a  mov     eax, 8007000Eh
0x18000864f  jmp     loc_18000853C
0x180008654  test    r15, r15
0x180008657  jz      short loc_180008660
0x180008659  mov     dword ptr [r15], 0
0x180008660  mov     r8, [rsp+0A8h+var_80]
0x180008665  test    r8, r8
0x180008668  jz      short loc_180008680
0x18000866a  lea     rcx, [rbp+18h]
0x18000866e  mov     rax, [rcx]
0x180008671  lea     rdx, IID_IUnknown
0x180008678  mov     rax, [rax]
0x18000867b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008680  xor     eax, eax
0x180008682  jmp     loc_18000853C
```
