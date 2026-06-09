# CInitiateWinSAT::WinSATCompletionRoutine(void *,void *)

- ea: `0x18001ef50`
- end: `0x18001f25c`
- name: `?WinSATCompletionRoutine@CInitiateWinSAT@@CAXPEAX0@Z`
- size: `780`
- prototype: `void __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180012bd0`
- `0x180012c06`
- `0x18001cb6c`
- `0x18001d8c0`
- `0x18001ef50`
- `0x18001f264`
- `0x18002dd40`
- `0x180033010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001f1bd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001f1bd`

## pseudocode

```c
void __fastcall CInitiateWinSAT::WinSATCompletionRoutine(_QWORD *a1, char *a2)
{
  __int64 v3; // rcx
  const char *v4; // rdx
  mlib *v5; // rcx
  signed int v6; // ebx
  unsigned __int16 v7; // r9
  OLECHAR *v8; // rdi
  int v9; // r8d
  const unsigned __int16 *v10; // r12
  __int64 v11; // r15
  unsigned __int64 v12; // rax
  OLECHAR *v13; // rax
  OLECHAR *v14; // rsi
  int v15; // esi
  const OLECHAR *v16; // r8
  unsigned __int64 *v17; // [rsp+28h] [rbp-30h]
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  v3 = a1[9];
  if ( !v3 )
    return;
  if ( a2 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, char *))(*(_QWORD *)v3 + 32LL))(
      v3,
      *(unsigned int *)a2,
      *((unsigned int *)a2 + 1),
      a2 + 8);
    return;
  }
  v6 = WinSATGetCompletionStatus();
  v8 = 0;
  if ( v6 > -2147221452 )
  {
    switch ( v6 )
    {
      case -2147221451:
        v9 = 11023;
        break;
      case -2147221450:
        v9 = 11024;
        break;
      case -2147221449:
        v9 = 11025;
        break;
      case -2147221448:
        v9 = 11026;
        break;
      case -2147221447:
        v9 = 11027;
        break;
      case 262194:
        v9 = 11020;
        break;
      case 262195:
        v9 = 11021;
        break;
      default:
LABEL_31:
        v8 = (OLECHAR *)&String2;
LABEL_44:
        v15 = 0;
        goto LABEL_45;
    }
  }
  else
  {
    if ( v6 != -2147221452 )
    {
      v5 = (mlib *)(v6 + 2147221503);
      v4 = (const char *)0x180000000LL;
      switch ( v6 )
      {
        case -2147221503:
          v9 = 11001;
          goto LABEL_39;
        case -2147221502:
          v9 = 11002;
          goto LABEL_39;
        case -2147221501:
          v9 = 11003;
          goto LABEL_39;
        case -2147221498:
          v9 = 11006;
          goto LABEL_39;
        case -2147221497:
          v9 = 11007;
          goto LABEL_39;
        case -2147221496:
          v9 = 11008;
          goto LABEL_39;
        case -2147221495:
          v9 = 11009;
          goto LABEL_39;
        case -2147221494:
          v9 = 11010;
          goto LABEL_39;
        case -2147221493:
          v9 = 11011;
          goto LABEL_39;
        case -2147221492:
          v9 = 11012;
          goto LABEL_39;
        case -2147221491:
          v9 = 11013;
          goto LABEL_39;
        case -2147221490:
          v9 = 11014;
          goto LABEL_39;
        case -2147221489:
          v9 = 11015;
          goto LABEL_39;
        case -2147221488:
          v9 = 11016;
          goto LABEL_39;
        case -2147221487:
          v9 = 11017;
          goto LABEL_39;
        case -2147221486:
          v9 = 11018;
          goto LABEL_39;
        case -2147221485:
          v9 = 11019;
          goto LABEL_39;
        default:
          goto LABEL_31;
      }
    }
    v9 = 11022;
  }
LABEL_39:
  v18 = 0;
  v10 = mlib::MUIStrAndLen_(v5, v4, v9, v7, (HINSTANCE)&v18, v17);
  v11 = v18 + 1;
  v12 = 2 * (v18 + 1);
  if ( !is_mul_ok(v18 + 1, 2u) )
    v12 = -1;
  v13 = (OLECHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  if ( v13 )
  {
    memcpy_0(v13, v10, 2 * v11);
    v8 = v14;
    goto LABEL_44;
  }
  v15 = -2147024882;
LABEL_45:
  WriteToRegistrySuccessOfLastRunOfWinsat(v6);
  v16 = &String2;
  if ( v15 >= 0 )
    v16 = v8;
  (*(void (__fastcall **)(_QWORD, _QWORD, const OLECHAR *))(*(_QWORD *)a1[9] + 24LL))(a1[9], (unsigned int)v6, v16);
  operator delete[](v8);
}

```

## disassembly

```asm
0x18001ef50  mov     [rsp+arg_8], rbx
0x18001ef55  mov     [rsp+arg_0], rcx
0x18001ef5a  push    rsi
0x18001ef5b  push    rdi
0x18001ef5c  push    r12
0x18001ef5e  push    r14
0x18001ef60  push    r15
0x18001ef62  sub     rsp, 30h
0x18001ef66  mov     r14, rcx
0x18001ef69  mov     rcx, [rcx+48h]
0x18001ef6d  test    rcx, rcx
0x18001ef70  jz      loc_18001F1FB
0x18001ef76  test    rdx, rdx
0x18001ef79  jnz     loc_18001F1CB
0x18001ef7f  call    WinSATGetCompletionStatus
0x18001ef84  mov     ebx, eax
0x18001ef86  xor     edi, edi
0x18001ef88  mov     [rsp+58h+arg_10], rdi
0x18001ef8d  mov     eax, 80040034h
0x18001ef92  cmp     ebx, eax
0x18001ef94  jg      loc_18001F08C
0x18001ef9a  jz      loc_18001F084
0x18001efa0  lea     eax, [rbx+7FFBFFFFh]; switch 19 cases
0x18001efa6  cmp     eax, 12h
0x18001efa9  ja      def_18001EFC3; jumptable 000000018001EFC3 default case, cases -2147221500,-2147221499
0x18001efaf  movsxd  rcx, eax
0x18001efb2  lea     rdx, cs:180000000h
0x18001efb9  mov     eax, ds:(jpt_18001EFC3 - 180000000h)[rdx+rcx*4]
0x18001efc0  add     rax, rdx
0x18001efc3  jmp     rax; switch jump
0x18001efc9  mov     r8d, 2AF9h; jumptable 000000018001EFC3 case -2147221503
0x18001efcf  jmp     loc_18001F10B
0x18001efd4  mov     r8d, 2AFAh; jumptable 000000018001EFC3 case -2147221502
0x18001efda  jmp     loc_18001F10B
0x18001efdf  mov     r8d, 2AFBh; jumptable 000000018001EFC3 case -2147221501
0x18001efe5  jmp     loc_18001F10B
0x18001efea  mov     r8d, 2AFEh; jumptable 000000018001EFC3 case -2147221498
0x18001eff0  jmp     loc_18001F10B
0x18001eff5  mov     r8d, 2AFFh; jumptable 000000018001EFC3 case -2147221497
0x18001effb  jmp     loc_18001F10B
0x18001f000  mov     r8d, 2B00h; jumptable 000000018001EFC3 case -2147221496
0x18001f006  jmp     loc_18001F10B
0x18001f00b  mov     r8d, 2B01h; jumptable 000000018001EFC3 case -2147221495
0x18001f011  jmp     loc_18001F10B
0x18001f016  mov     r8d, 2B02h; jumptable 000000018001EFC3 case -2147221494
0x18001f01c  jmp     loc_18001F10B
0x18001f021  mov     r8d, 2B03h; jumptable 000000018001EFC3 case -2147221493
0x18001f027  jmp     loc_18001F10B
0x18001f02c  mov     r8d, 2B04h; jumptable 000000018001EFC3 case -2147221492
0x18001f032  jmp     loc_18001F10B
0x18001f037  mov     r8d, 2B05h; jumptable 000000018001EFC3 case -2147221491
0x18001f03d  jmp     loc_18001F10B
0x18001f042  mov     r8d, 2B06h; jumptable 000000018001EFC3 case -2147221490
0x18001f048  jmp     loc_18001F10B
0x18001f04d  mov     r8d, 2B07h; jumptable 000000018001EFC3 case -2147221489
0x18001f053  jmp     loc_18001F10B
0x18001f058  mov     r8d, 2B08h; jumptable 000000018001EFC3 case -2147221488
0x18001f05e  jmp     loc_18001F10B
0x18001f063  mov     r8d, 2B09h; jumptable 000000018001EFC3 case -2147221487
0x18001f069  jmp     loc_18001F10B
0x18001f06e  mov     r8d, 2B0Ah; jumptable 000000018001EFC3 case -2147221486
0x18001f074  jmp     loc_18001F10B
0x18001f079  mov     r8d, 2B0Bh; jumptable 000000018001EFC3 case -2147221485
0x18001f07f  jmp     loc_18001F10B
0x18001f084  mov     r8d, 2B0Eh
0x18001f08a  jmp     short loc_18001F10B
0x18001f08c  cmp     ebx, 80040035h
0x18001f092  jz      short loc_18001F105
0x18001f094  cmp     ebx, 80040036h
0x18001f09a  jz      short loc_18001F0FD
0x18001f09c  cmp     ebx, 80040037h
0x18001f0a2  jz      short loc_18001F0F5
0x18001f0a4  cmp     ebx, 80040038h
0x18001f0aa  jz      short loc_18001F0ED
0x18001f0ac  cmp     ebx, 80040039h
0x18001f0b2  jz      short loc_18001F0E5
0x18001f0b4  cmp     ebx, 40032h
0x18001f0ba  jz      short loc_18001F0DD
0x18001f0bc  cmp     ebx, 40033h
0x18001f0c2  jz      short loc_18001F0D5
0x18001f0c4  lea     rdi, String2; jumptable 000000018001EFC3 default case, cases -2147221500,-2147221499
0x18001f0cb  mov     [rsp+58h+arg_10], rdi
0x18001f0d0  jmp     loc_18001F172
0x18001f0d5  mov     r8d, 2B0Dh
0x18001f0db  jmp     short loc_18001F10B
0x18001f0dd  mov     r8d, 2B0Ch
0x18001f0e3  jmp     short loc_18001F10B
0x18001f0e5  mov     r8d, 2B13h
0x18001f0eb  jmp     short loc_18001F10B
0x18001f0ed  mov     r8d, 2B12h
0x18001f0f3  jmp     short loc_18001F10B
0x18001f0f5  mov     r8d, 2B11h
0x18001f0fb  jmp     short loc_18001F10B
0x18001f0fd  mov     r8d, 2B10h
0x18001f103  jmp     short loc_18001F10B
0x18001f105  mov     r8d, 2B0Fh; int
0x18001f10b  and     [rsp+58h+arg_18], rdi
0x18001f110  lea     rax, [rsp+58h+arg_18]
0x18001f115  mov     [rsp+58h+var_38], rax; HINSTANCE
0x18001f11a  call    ?MUIStrAndLen_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@AEA_K@Z; mlib::MUIStrAndLen_(char const *,int,ushort,HINSTANCE__ *,unsigned __int64 &)
0x18001f11f  mov     r12, rax
0x18001f122  mov     r15, [rsp+58h+arg_18]
0x18001f127  inc     r15
0x18001f12a  mov     eax, 2
0x18001f12f  mul     r15
0x18001f132  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f139  cmovo   rax, rcx
0x18001f13d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f144  mov     rcx, rax; unsigned __int64
0x18001f147  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f14c  mov     rsi, rax
0x18001f14f  test    rax, rax
0x18001f152  jnz     short loc_18001F15B
0x18001f154  mov     esi, 8007000Eh
0x18001f159  jmp     short loc_18001F174
0x18001f15b  lea     r8, [r15+r15]; Size
0x18001f15f  mov     rdx, r12; Src
0x18001f162  mov     rcx, rsi; void *
0x18001f165  call    memcpy_0
0x18001f16a  mov     rdi, rsi
0x18001f16d  mov     [rsp+58h+arg_10], rsi
0x18001f172  xor     esi, esi
0x18001f174  mov     ecx, ebx; unsigned int
0x18001f176  call    ?WriteToRegistrySuccessOfLastRunOfWinsat@@YA_NJ@Z; WriteToRegistrySuccessOfLastRunOfWinsat(long)
0x18001f17b  nop
0x18001f17c  mov     rcx, [r14+48h]
0x18001f180  mov     rax, [rcx]
0x18001f183  mov     edx, ebx
0x18001f185  mov     rax, [rax+18h]
0x18001f189  test    esi, esi
0x18001f18b  lea     r8, String2
0x18001f192  js      short loc_18001F197
0x18001f194  mov     r8, rdi
0x18001f197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f19c  jmp     short loc_18001F1BA
0x18001f19e  mov     rcx, [rsp+58h+arg_0]
0x18001f1a3  add     rcx, 48h ; 'H'; struct IUnknown **
0x18001f1a7  xor     eax, eax
0x18001f1a9  cmp     [rcx], rax
0x18001f1ac  jz      short loc_18001F1B5
0x18001f1ae  xor     edx, edx; struct IUnknown *
0x18001f1b0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001f1b5  mov     rdi, [rsp+58h+arg_10]
0x18001f1ba  mov     rcx, rdi
0x18001f1bd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001f1c4  nop     dword ptr [rax+rax+00h]
0x18001f1c9  jmp     short loc_18001F1FB
0x18001f1cb  mov     rax, [rcx]
0x18001f1ce  lea     r9, [rdx+8]
0x18001f1d2  mov     r8d, [rdx+4]
0x18001f1d6  mov     edx, [rdx]
0x18001f1d8  mov     rax, [rax+20h]
0x18001f1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1e1  jmp     short loc_18001F1FB
0x18001f1e3  mov     rcx, [rsp+58h+arg_0]
0x18001f1e8  add     rcx, 48h ; 'H'; struct IUnknown **
0x18001f1ec  xor     eax, eax
0x18001f1ee  cmp     [rcx], rax
0x18001f1f1  jz      short loc_18001F1FB
0x18001f1f3  xor     edx, edx; struct IUnknown *
0x18001f1f5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001f1fa  nop
0x18001f1fb  mov     rbx, [rsp+58h+arg_8]
0x18001f200  add     rsp, 30h
0x18001f204  pop     r15
0x18001f206  pop     r14
0x18001f208  pop     r12
0x18001f20a  pop     rdi
0x18001f20b  pop     rsi
0x18001f20c  retn
0x180031bec  push    rbp
0x180031bee  sub     rsp, 30h
0x180031bf2  mov     rbp, rdx
0x180031bf5  mov     rax, [rcx]
0x180031bf8  xor     ecx, ecx
0x180031bfa  cmp     dword ptr [rax], 0C0000005h
0x180031c00  setz    cl
0x180031c03  mov     eax, ecx
0x180031c05  add     rsp, 30h
0x180031c09  pop     rbp
0x180031c0a  retn
0x180031c0c  push    rbp
0x180031c0e  sub     rsp, 30h
0x180031c12  mov     rbp, rdx
0x180031c15  mov     rax, [rcx]
0x180031c18  xor     ecx, ecx
0x180031c1a  cmp     dword ptr [rax], 0C0000005h
0x180031c20  setz    cl
0x180031c23  mov     eax, ecx
0x180031c25  add     rsp, 30h
0x180031c29  pop     rbp
0x180031c2a  retn
```
