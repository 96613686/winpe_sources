# Apx::ApfDataFormat::_CreateAndInitialize(_APX_DATAFORMAT_CONFIG *,Apx::ApfDataFormat * *)

- ea: `0x18001d4fc`
- end: `0x18001d67a`
- name: `?_CreateAndInitialize@ApfDataFormat@Apx@@SAJPEAU_APX_DATAFORMAT_CONFIG@@PEAPEAV12@@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct _APX_DATAFORMAT_CONFIG *, struct Apx::ApfDataFormat **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001d680`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000a1b4`
- `0x18001cb40`
- `0x18001d4fc`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfDataFormat::_CreateAndInitialize(
        struct _APX_DATAFORMAT_CONFIG *a1,
        struct Apx::ApfDataFormat **a2)
{
  Apx::ApfDataFormat *v4; // rax
  Apx::ApfDataFormat *v5; // rbx
  _QWORD *v6; // rcx
  int v7; // edi
  _QWORD *v8; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
  }
  v4 = (Apx::ApfDataFormat *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 2) = 1;
    *(_QWORD *)v4 = &Apx::ApfDataFormat::`vftable';
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
        WPP_SF_(v6[2], 17, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
    }
    v7 = Apx::ApfDataFormat::Initialize(v5, a1);
    if ( v7 < 0 )
    {
      (**(void (__fastcall ***)(Apx::ApfDataFormat *, __int64))v5)(v5, 1);
    }
    else
    {
      *a2 = v5;
      v7 = 0;
    }
    goto LABEL_21;
  }
  v7 = -2147024882;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
LABEL_21:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_(v8[2], 15, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001d4fc  push    rbx
0x18001d4fe  push    rsi
0x18001d4ff  push    rdi
0x18001d500  push    r13
0x18001d502  push    r15
0x18001d504  sub     rsp, 20h
0x18001d508  mov     rsi, rdx
0x18001d50b  mov     rdi, rcx
0x18001d50e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d515  lea     r15, WPP_GLOBAL_Control
0x18001d51c  lea     r13, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids
0x18001d523  cmp     rcx, r15
0x18001d526  jz      short loc_18001D545
0x18001d528  test    byte ptr [rcx+1Ch], 1
0x18001d52c  jz      short loc_18001D545
0x18001d52e  cmp     byte ptr [rcx+19h], 5
0x18001d532  jb      short loc_18001D545
0x18001d534  mov     rcx, [rcx+10h]
0x18001d538  mov     edx, 0Dh
0x18001d53d  mov     r8, r13
0x18001d540  call    WPP_SF_
0x18001d545  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d54c  mov     ecx, 30h ; '0'; unsigned __int64
0x18001d551  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d556  mov     rbx, rax
0x18001d559  test    rax, rax
0x18001d55c  jz      loc_18001D612
0x18001d562  mov     dword ptr [rax+8], 1
0x18001d569  lea     rax, ??_7ApfDataFormat@Apx@@6B@; const Apx::ApfDataFormat::`vftable'
0x18001d570  mov     [rbx], rax
0x18001d573  mov     qword ptr [rbx+10h], 0
0x18001d57b  mov     qword ptr [rbx+18h], 0
0x18001d583  mov     qword ptr [rbx+20h], 0
0x18001d58b  mov     qword ptr [rbx+28h], 0
0x18001d593  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d59a  cmp     rcx, r15
0x18001d59d  jz      short loc_18001D5E5
0x18001d59f  test    byte ptr [rcx+1Ch], 1
0x18001d5a3  jz      short loc_18001D5C3
0x18001d5a5  cmp     byte ptr [rcx+19h], 5
0x18001d5a9  jb      short loc_18001D5C3
0x18001d5ab  mov     rcx, [rcx+10h]
0x18001d5af  mov     edx, 10h
0x18001d5b4  mov     r8, r13
0x18001d5b7  call    WPP_SF_
0x18001d5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5c3  cmp     rcx, r15
0x18001d5c6  jz      short loc_18001D5E5
0x18001d5c8  test    byte ptr [rcx+1Ch], 1
0x18001d5cc  jz      short loc_18001D5E5
0x18001d5ce  cmp     byte ptr [rcx+19h], 5
0x18001d5d2  jb      short loc_18001D5E5
0x18001d5d4  mov     rcx, [rcx+10h]
0x18001d5d8  mov     edx, 11h
0x18001d5dd  mov     r8, r13
0x18001d5e0  call    WPP_SF_
0x18001d5e5  mov     rdx, rdi; struct _APX_DATAFORMAT_CONFIG *
0x18001d5e8  mov     rcx, rbx; this
0x18001d5eb  call    ?Initialize@ApfDataFormat@Apx@@AEAAJPEAU_APX_DATAFORMAT_CONFIG@@@Z; Apx::ApfDataFormat::Initialize(_APX_DATAFORMAT_CONFIG *)
0x18001d5f0  mov     edi, eax
0x18001d5f2  test    eax, eax
0x18001d5f4  js      short loc_18001D5FD
0x18001d5f6  mov     [rsi], rbx
0x18001d5f9  xor     edi, edi
0x18001d5fb  jmp     short loc_18001D643
0x18001d5fd  mov     rax, [rbx]
0x18001d600  mov     edx, 1
0x18001d605  mov     rcx, rbx
0x18001d608  mov     rax, [rax]
0x18001d60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d610  jmp     short loc_18001D643
0x18001d612  mov     edi, 8007000Eh
0x18001d617  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d61e  cmp     rcx, r15
0x18001d621  jz      short loc_18001D66C
0x18001d623  test    byte ptr [rcx+1Ch], 20h
0x18001d627  jz      short loc_18001D64A
0x18001d629  cmp     byte ptr [rcx+19h], 2
0x18001d62d  jb      short loc_18001D64A
0x18001d62f  mov     rcx, [rcx+10h]
0x18001d633  mov     edx, 0Eh
0x18001d638  mov     r9d, edi
0x18001d63b  mov     r8, r13
0x18001d63e  call    WPP_SF_d
0x18001d643  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d64a  cmp     rcx, r15
0x18001d64d  jz      short loc_18001D66C
0x18001d64f  test    byte ptr [rcx+1Ch], 1
0x18001d653  jz      short loc_18001D66C
0x18001d655  cmp     byte ptr [rcx+19h], 5
0x18001d659  jb      short loc_18001D66C
0x18001d65b  mov     rcx, [rcx+10h]
0x18001d65f  mov     edx, 0Fh
0x18001d664  mov     r8, r13
0x18001d667  call    WPP_SF_
0x18001d66c  mov     eax, edi
0x18001d66e  add     rsp, 20h
0x18001d672  pop     r15
0x18001d674  pop     r13
0x18001d676  pop     rdi
0x18001d677  pop     rsi
0x18001d678  pop     rbx
0x18001d679  retn
```
