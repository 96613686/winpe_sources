# CInSequence::Load(void *,ushort)

- ea: `0x18006719c`
- end: `0x180067535`
- name: `?Load@CInSequence@@QEAAHPEAXG@Z`
- size: `921`
- prototype: `int(CInSequence *__hidden this, void *, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180066dbc`

## callees

- `0x18000f430`
- `0x18000faec`
- `0x18004b990`
- `0x18006719c`
- `0x18009bd1c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x1800674a8`
- `msvcrt!free` at `0x180067507`
- `msvcrt!free` at `0x1800674a8`
- `msvcrt!free` at `0x180067507`
- `KERNEL32!ReadFile` at `0x1800671f0`
- `KERNEL32!ReadFile` at `0x18006722e`
- `KERNEL32!ReadFile` at `0x180067269`
- `KERNEL32!ReadFile` at `0x18006729a`
- `KERNEL32!ReadFile` at `0x1800672e5`
- `KERNEL32!ReadFile` at `0x18006732e`
- `KERNEL32!ReadFile` at `0x180067377`
- `KERNEL32!ReadFile` at `0x1800673b4`
- `KERNEL32!ReadFile` at `0x1800673f7`
- `KERNEL32!ReadFile` at `0x18006743f`
- `KERNEL32!ReadFile` at `0x1800671f0`
- `KERNEL32!ReadFile` at `0x18006722e`
- `KERNEL32!ReadFile` at `0x180067269`
- `KERNEL32!ReadFile` at `0x18006729a`
- `KERNEL32!ReadFile` at `0x1800672e5`
- `KERNEL32!ReadFile` at `0x18006732e`
- `KERNEL32!ReadFile` at `0x180067377`
- `KERNEL32!ReadFile` at `0x1800673b4`
- `KERNEL32!ReadFile` at `0x1800673f7`
- `KERNEL32!ReadFile` at `0x18006743f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInSequence::Load(CInSequence *this, void *a2, unsigned __int16 a3)
{
  __int64 v6; // rax
  int v7; // eax
  _DWORD *v8; // rbx
  CReference *v9; // rbx
  CReference *v10; // rax
  CReference *v11; // rsi
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-30h] BYREF
  int v14; // [rsp+34h] [rbp-2Ch] BYREF
  __int64 Buffer; // [rsp+38h] [rbp-28h] BYREF
  DWORD nNumberOfBytesToRead[2]; // [rsp+40h] [rbp-20h] BYREF
  CReference *v17; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+50h] [rbp-10h]

  NumberOfBytesRead = 0;
  Buffer = 0;
  v14 = 0;
  if ( !ReadFile(a2, &Buffer, 8u, &NumberOfBytesRead, 0) )
    return 0;
  if ( NumberOfBytesRead != 8 )
    return 0;
  v6 = Buffer;
  *((_QWORD *)this + 14) = Buffer;
  *((_QWORD *)this + 16) = v6;
  if ( !ReadFile(a2, &v14, 4u, &NumberOfBytesRead, 0) )
    return 0;
  if ( NumberOfBytesRead != 4 )
    return 0;
  v7 = v14;
  *((_DWORD *)this + 30) = v14;
  *((_DWORD *)this + 34) = v7;
  if ( !ReadFile(a2, (char *)this + 200, 8u, &NumberOfBytesRead, 0) )
    return 0;
  if ( NumberOfBytesRead != 8 )
    return 0;
  v8 = (_DWORD *)((char *)this + 216);
  if ( !ReadFile(a2, (char *)this + 216, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
    return 0;
  if ( a3 < 2u && *v8 == 1 )
  {
    nNumberOfBytesToRead[0] = 0;
    LOWORD(nNumberOfBytesToRead[1]) = 0;
    if ( !ReadFile(a2, nNumberOfBytesToRead, 4u, &NumberOfBytesRead, 0) )
      return 0;
    if ( NumberOfBytesRead != 4 )
      return 0;
    *((_DWORD *)this + 55) = nNumberOfBytesToRead[0];
    *((_DWORD *)this + 56) = 0;
    if ( !ReadFile(a2, &v17, 0xCu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 12 )
      return 0;
    *(_QWORD *)((char *)this + 228) = v17;
    *((_DWORD *)this + 59) = v18;
  }
  else
  {
    if ( !ReadFile(a2, (char *)this + 220, 0x10u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 16 )
      return 0;
    if ( *v8 == 1 && *((_WORD *)this + 111) == 6 )
    {
      if ( !ReadFile(a2, nNumberOfBytesToRead, 8u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 8 )
        return 0;
      *(_QWORD *)((char *)this + 236) = *(_QWORD *)nNumberOfBytesToRead;
    }
  }
  if ( *v8 != 2 )
    goto LABEL_33;
  nNumberOfBytesToRead[0] = 0;
  if ( !ReadFile(a2, nNumberOfBytesToRead, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
    return 0;
  if ( !nNumberOfBytesToRead[0] )
    goto LABEL_33;
  v17 = 0;
  v9 = (CReference *)MmAllocate(nNumberOfBytesToRead[0]);
  v17 = v9;
  if ( !ReadFile(a2, v9, nNumberOfBytesToRead[0], &NumberOfBytesRead, 0) || nNumberOfBytesToRead[0] != NumberOfBytesRead )
  {
    free(v9);
    return 0;
  }
  v10 = (CReference *)MmAllocate(0x18u);
  v11 = v10;
  v17 = v10;
  if ( v10 )
  {
    *((_DWORD *)v10 + 2) = 1;
    *(_QWORD *)v10 = &CQueueSecurityDescriptor::`vftable';
    *((_QWORD *)v10 + 2) = v9;
  }
  else
  {
    v11 = 0;
  }
  v17 = v11;
  R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=((CReference **)this + 31, (__int64 *)&v17);
  SafeRelease<CSockTransport>(v11);
  free(0);
LABEL_33:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 428) & 4) != 0 )
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 52),
      33,
      &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids,
      *((__int64 *)this + 14) >> 32,
      *((_DWORD *)this + 28),
      *((_DWORD *)this + 30));
  return 1;
}

```

## disassembly

```asm
0x18006719c  mov     [rsp-28h+arg_10], rbx
0x1800671a1  mov     [rsp-28h+arg_18], rsi
0x1800671a6  push    rbp
0x1800671a7  push    rdi
0x1800671a8  push    r12
0x1800671aa  push    r14
0x1800671ac  push    r15
0x1800671ae  mov     rbp, rsp
0x1800671b1  sub     rsp, 60h
0x1800671b5  mov     rax, cs:__security_cookie
0x1800671bc  xor     rax, rsp
0x1800671bf  mov     [rbp+var_8], rax
0x1800671c3  movzx   r14d, r8w
0x1800671c7  mov     rsi, rdx
0x1800671ca  mov     rdi, rcx
0x1800671cd  xor     r15d, r15d
0x1800671d0  mov     [rbp+NumberOfBytesRead], r15d
0x1800671d4  mov     [rbp+Buffer], r15
0x1800671d8  mov     [rbp+var_2C], r15d
0x1800671dc  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x1800671e1  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800671e5  lea     r8d, [r15+8]; nNumberOfBytesToRead
0x1800671e9  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800671ed  mov     rcx, rsi; hFile
0x1800671f0  call    cs:__imp_ReadFile
0x1800671f6  test    eax, eax
0x1800671f8  jz      loc_18006750E
0x1800671fe  cmp     [rbp+NumberOfBytesRead], 8
0x180067202  jnz     loc_18006750E
0x180067208  mov     rax, [rbp+Buffer]
0x18006720c  mov     [rdi+70h], rax
0x180067210  mov     [rdi+80h], rax
0x180067217  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x18006721c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180067220  lea     r12d, [r15+4]
0x180067224  mov     r8d, r12d; nNumberOfBytesToRead
0x180067227  lea     rdx, [rbp+var_2C]; lpBuffer
0x18006722b  mov     rcx, rsi; hFile
0x18006722e  call    cs:__imp_ReadFile
0x180067234  test    eax, eax
0x180067236  jz      loc_18006750E
0x18006723c  cmp     [rbp+NumberOfBytesRead], r12d
0x180067240  jnz     loc_18006750E
0x180067246  mov     eax, [rbp+var_2C]
0x180067249  mov     [rdi+78h], eax
0x18006724c  mov     [rdi+88h], eax
0x180067252  lea     rdx, [rdi+0C8h]; lpBuffer
0x180067259  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x18006725e  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180067262  lea     r8d, [r15+8]; nNumberOfBytesToRead
0x180067266  mov     rcx, rsi; hFile
0x180067269  call    cs:__imp_ReadFile
0x18006726f  test    eax, eax
0x180067271  jz      loc_18006750E
0x180067277  cmp     [rbp+NumberOfBytesRead], 8
0x18006727b  jnz     loc_18006750E
0x180067281  lea     rbx, [rdi+0D8h]
0x180067288  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x18006728d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180067291  mov     r8d, r12d; nNumberOfBytesToRead
0x180067294  mov     rdx, rbx; lpBuffer
0x180067297  mov     rcx, rsi; hFile
0x18006729a  call    cs:__imp_ReadFile
0x1800672a0  test    eax, eax
0x1800672a2  jz      loc_18006750E
0x1800672a8  cmp     [rbp+NumberOfBytesRead], r12d
0x1800672ac  jnz     loc_18006750E
0x1800672b2  lea     eax, [r15+2]
0x1800672b6  cmp     r14w, ax
0x1800672ba  jnb     loc_18006735E
0x1800672c0  cmp     dword ptr [rbx], 1
0x1800672c3  jnz     loc_18006735E
0x1800672c9  xor     eax, eax
0x1800672cb  mov     [rbp+nNumberOfBytesToRead], eax
0x1800672ce  mov     word ptr [rbp+nNumberOfBytesToRead+4], ax
0x1800672d2  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x1800672d7  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800672db  mov     r8d, r12d; nNumberOfBytesToRead
0x1800672de  lea     rdx, [rbp+nNumberOfBytesToRead]; lpBuffer
0x1800672e2  mov     rcx, rsi; hFile
0x1800672e5  call    cs:__imp_ReadFile
0x1800672eb  test    eax, eax
0x1800672ed  jz      loc_18006750E
0x1800672f3  cmp     [rbp+NumberOfBytesRead], r12d
0x1800672f7  jnz     loc_18006750E
0x1800672fd  movzx   eax, word ptr [rbp+nNumberOfBytesToRead]
0x180067301  mov     [rdi+0DCh], ax
0x180067308  movzx   eax, word ptr [rbp+nNumberOfBytesToRead+2]
0x18006730c  mov     [rdi+0DEh], ax
0x180067313  mov     [rdi+0E0h], r15d
0x18006731a  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x18006731f  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180067323  lea     r8d, [r15+0Ch]; nNumberOfBytesToRead
0x180067327  lea     rdx, [rbp+var_18]; lpBuffer
0x18006732b  mov     rcx, rsi; hFile
0x18006732e  call    cs:__imp_ReadFile
0x180067334  test    eax, eax
0x180067336  jz      loc_18006750E
0x18006733c  cmp     [rbp+NumberOfBytesRead], 0Ch
0x180067340  jnz     loc_18006750E
0x180067346  movsd   xmm0, [rbp+var_18]
0x18006734b  movsd   qword ptr [rdi+0E4h], xmm0
0x180067353  mov     eax, [rbp+var_10]
0x180067356  mov     [rdi+0ECh], eax
0x18006735c  jmp     short loc_1800673D7
0x18006735e  lea     rdx, [rdi+0DCh]; lpBuffer
0x180067365  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x18006736a  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006736e  mov     r8d, 10h; nNumberOfBytesToRead
0x180067374  mov     rcx, rsi; hFile
0x180067377  call    cs:__imp_ReadFile
0x18006737d  test    eax, eax
0x18006737f  jz      loc_18006750E
0x180067385  cmp     [rbp+NumberOfBytesRead], 10h
0x180067389  jnz     loc_18006750E
0x18006738f  cmp     dword ptr [rbx], 1
0x180067392  jnz     short loc_1800673D7
0x180067394  cmp     word ptr [rdi+0DEh], 6
0x18006739c  jnz     short loc_1800673D7
0x18006739e  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x1800673a3  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800673a7  mov     r8d, 8; nNumberOfBytesToRead
0x1800673ad  lea     rdx, [rbp+nNumberOfBytesToRead]; lpBuffer
0x1800673b1  mov     rcx, rsi; hFile
0x1800673b4  call    cs:__imp_ReadFile
0x1800673ba  test    eax, eax
0x1800673bc  jz      loc_18006750E
0x1800673c2  cmp     [rbp+NumberOfBytesRead], 8
0x1800673c6  jnz     loc_18006750E
0x1800673cc  mov     rax, qword ptr [rbp+nNumberOfBytesToRead]
0x1800673d0  mov     [rdi+0ECh], rax
0x1800673d7  cmp     dword ptr [rbx], 2
0x1800673da  jnz     loc_1800674AF
0x1800673e0  mov     [rbp+nNumberOfBytesToRead], r15d
0x1800673e4  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x1800673e9  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800673ed  mov     r8d, r12d; nNumberOfBytesToRead
0x1800673f0  lea     rdx, [rbp+nNumberOfBytesToRead]; lpBuffer
0x1800673f4  mov     rcx, rsi; hFile
0x1800673f7  call    cs:__imp_ReadFile
0x1800673fd  test    eax, eax
0x1800673ff  jz      loc_18006750E
0x180067405  cmp     [rbp+NumberOfBytesRead], r12d
0x180067409  jnz     loc_18006750E
0x18006740f  mov     eax, [rbp+nNumberOfBytesToRead]
0x180067412  test    eax, eax
0x180067414  jz      loc_1800674AF
0x18006741a  mov     [rbp+var_18], r15
0x18006741e  mov     ecx, eax; unsigned __int64
0x180067420  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180067425  mov     rbx, rax
0x180067428  mov     [rbp+var_18], rax
0x18006742c  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x180067431  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180067435  mov     r8d, [rbp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180067439  mov     rdx, rax; lpBuffer
0x18006743c  mov     rcx, rsi; hFile
0x18006743f  call    cs:__imp_ReadFile
0x180067445  test    eax, eax
0x180067447  jz      loc_180067504
0x18006744d  mov     eax, [rbp+NumberOfBytesRead]
0x180067450  cmp     [rbp+nNumberOfBytesToRead], eax
0x180067453  jnz     loc_180067504
0x180067459  mov     ecx, 18h; unsigned __int64
0x18006745e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180067463  mov     rsi, rax
0x180067466  mov     [rbp+var_18], rax
0x18006746a  test    rax, rax
0x18006746d  jz      short loc_180067486
0x18006746f  mov     dword ptr [rax+8], 1
0x180067476  lea     rax, ??_7CQueueSecurityDescriptor@@6B@; const CQueueSecurityDescriptor::`vftable'
0x18006747d  mov     [rsi], rax
0x180067480  mov     [rsi+10h], rbx
0x180067484  jmp     short loc_180067489
0x180067486  mov     rsi, r15
0x180067489  mov     [rbp+var_18], rsi
0x18006748d  lea     rcx, [rdi+0F8h]
0x180067494  lea     rdx, [rbp+var_18]
0x180067498  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x18006749d  mov     rcx, rsi
0x1800674a0  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x1800674a5  nop
0x1800674a6  xor     ecx, ecx; Block
0x1800674a8  call    cs:__imp_free
0x1800674ae  nop
0x1800674af  lea     rax, WPP_GLOBAL_Control
0x1800674b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800674bd  cmp     rcx, rax
0x1800674c0  jz      short loc_1800674FD
0x1800674c2  test    [rcx+1ACh], r12b
0x1800674c9  jz      short loc_1800674FD
0x1800674cb  mov     r9, [rdi+70h]
0x1800674cf  sar     r9, 20h
0x1800674d3  mov     edx, 21h ; '!'
0x1800674d8  mov     r8d, [rdi+78h]
0x1800674dc  mov     [rsp+60h+var_38], r8d
0x1800674e1  mov     r8d, [rdi+70h]
0x1800674e5  mov     dword ptr [rsp+60h+lpOverlapped], r8d
0x1800674ea  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x1800674f1  mov     rcx, [rcx+1A0h]
0x1800674f8  call    WPP_SF_DDd
0x1800674fd  mov     eax, 1
0x180067502  jmp     short loc_180067510
0x180067504  mov     rcx, rbx; Block
0x180067507  call    cs:__imp_free
0x18006750d  nop
0x18006750e  xor     eax, eax
0x180067510  mov     rcx, [rbp+var_8]
0x180067514  xor     rcx, rsp; StackCookie
0x180067517  call    __security_check_cookie
0x18006751c  lea     r11, [rsp+60h+var_s0]
0x180067521  mov     rbx, [r11+40h]
0x180067525  mov     rsi, [r11+48h]
0x180067529  mov     rsp, r11
0x18006752c  pop     r15
0x18006752e  pop     r14
0x180067530  pop     r12
0x180067532  pop     rdi
0x180067533  pop     rbp
0x180067534  retn
```
