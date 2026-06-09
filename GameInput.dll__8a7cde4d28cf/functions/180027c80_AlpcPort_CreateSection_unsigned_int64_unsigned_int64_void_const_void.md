# AlpcPort::CreateSection(unsigned __int64,unsigned __int64,void const *,void * *)

- ea: `0x180027c80`
- end: `0x180027dda`
- name: `?CreateSection@AlpcPort@@UEAAJ_K0PEBXPEAPEAX@Z`
- size: `346`
- prototype: `__int64 __fastcall(AlpcPort *__hidden this, unsigned __int64, ULONG cbInput, PUCHAR pbInput, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180026448`
- `0x180027c80`
- `0x180028c10`
- `0x180029cf8`
- `0x18002bbd0`
- `0x18004c8e0`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180027d00`
- `bcrypt!BCryptGenRandom` at `0x180027d00`

## pseudocode

```c
__int64 __fastcall AlpcPort::CreateSection(
        AlpcPort *this,
        unsigned __int64 a2,
        ULONG cbInput,
        PUCHAR pbInput,
        void **a5)
{
  __int64 result; // rax
  NTSTATUS v8; // ecx
  __int64 v9; // rax
  void *v10; // r9
  struct AlpcSection *v11; // r9
  _QWORD *v12; // rdx
  __int64 v13; // rax
  _QWORD *v14; // r8
  int v15; // ecx
  struct AlpcSection *v16; // [rsp+30h] [rbp-38h] BYREF
  UCHAR pbBuffer[16]; // [rsp+38h] [rbp-30h] BYREF
  __int128 v18; // [rsp+48h] [rbp-20h]

  *(_OWORD *)pbBuffer = 0;
  *a5 = 0;
  v18 = 0;
  if ( pbInput )
  {
    result = SipcSectionId::InitializeFromData(pbBuffer, cbInput, pbInput);
    if ( (int)result >= 0 )
    {
      if ( SipcPort::FindSection(this, (const struct SipcSectionId *)pbBuffer) )
      {
        return 2147942487LL;
      }
      else
      {
LABEL_11:
        v10 = (void *)*((_QWORD *)this + 6);
        v16 = 0;
        result = AlpcSection::Create(this, a2, (const struct SipcSectionId *)pbBuffer, v10, &v16);
        if ( (int)result >= 0 )
        {
          v11 = v16;
          v12 = (_QWORD *)((char *)this + 8);
          v13 = *((_QWORD *)this + 1);
          v14 = (_QWORD *)(((unsigned __int64)v16 + 8) & -(__int64)(v16 != 0));
          if ( *(AlpcPort **)(v13 + 8) != (AlpcPort *)((char *)this + 8) )
            __fastfail(3u);
          *v14 = v13;
          v14[1] = v12;
          *(_QWORD *)(v13 + 8) = v14;
          ++*((_DWORD *)this + 6);
          *v12 = v14;
          *a5 = (void *)*((_QWORD *)v11 + 4);
          return 0;
        }
      }
    }
  }
  else
  {
    while ( 1 )
    {
      v8 = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
      if ( v8 < 0 )
        break;
      v9 = 0;
      while ( !pbBuffer[v9] )
      {
        if ( (unsigned __int64)++v9 >= 0x20 )
        {
          SipcFailFast(2147549183LL);
          JUMPOUT(0x180027DD9LL);
        }
      }
      if ( !SipcPort::FindSection(this, (const struct SipcSectionId *)pbBuffer) )
        goto LABEL_11;
    }
    v15 = v8 | 0x10000000;
    result = 2147549183LL;
    if ( v15 < 0 )
      return (unsigned int)v15;
  }
  return result;
}

```

## disassembly

```asm
0x180027c80  push    rbp
0x180027c82  push    rbx
0x180027c83  push    rsi
0x180027c84  push    rdi
0x180027c85  mov     rbp, rsp
0x180027c88  sub     rsp, 68h
0x180027c8c  mov     rax, cs:__security_cookie
0x180027c93  xor     rax, rsp
0x180027c96  mov     [rbp+var_10], rax
0x180027c9a  mov     rdi, [rbp+arg_20]
0x180027c9e  xorps   xmm0, xmm0
0x180027ca1  mov     rax, r8
0x180027ca4  mov     rsi, rdx
0x180027ca7  mov     rbx, rcx
0x180027caa  movups  xmmword ptr [rbp+pbBuffer], xmm0
0x180027cae  mov     qword ptr [rdi], 0
0x180027cb5  movups  [rbp+var_20], xmm0
0x180027cb9  test    r9, r9
0x180027cbc  jz      short loc_180027CF0
0x180027cbe  mov     r8, r9; pbInput
0x180027cc1  lea     rcx, [rbp+pbBuffer]; pbOutput
0x180027cc5  mov     rdx, rax; cbInput
0x180027cc8  call    ?InitializeFromData@SipcSectionId@@QEAAJ_KPEBX@Z; SipcSectionId::InitializeFromData(unsigned __int64,void const *)
0x180027ccd  test    eax, eax
0x180027ccf  js      loc_180027DB9
0x180027cd5  lea     rdx, [rbp+pbBuffer]; struct SipcSectionId *
0x180027cd9  mov     rcx, rbx; this
0x180027cdc  call    ?FindSection@SipcPort@@IEAAPEAVSipcSection@@AEBVSipcSectionId@@@Z; SipcPort::FindSection(SipcSectionId const &)
0x180027ce1  test    rax, rax
0x180027ce4  jz      short loc_180027D3F
0x180027ce6  mov     eax, 80070057h
0x180027ceb  jmp     loc_180027DB9
0x180027cf0  mov     r9d, 2; dwFlags
0x180027cf6  lea     rdx, [rbp+pbBuffer]; pbBuffer
0x180027cfa  xor     ecx, ecx; hAlgorithm
0x180027cfc  lea     r8d, [r9+1Eh]; cbBuffer
0x180027d00  call    cs:__imp_BCryptGenRandom
0x180027d07  nop     dword ptr [rax+rax+00h]
0x180027d0c  mov     ecx, eax
0x180027d0e  test    eax, eax
0x180027d10  js      loc_180027DAB
0x180027d16  xor     eax, eax
0x180027d18  cmp     [rbp+rax+pbBuffer], 0
0x180027d1d  jnz     short loc_180027D2E
0x180027d1f  inc     rax
0x180027d22  cmp     rax, 20h ; ' '
0x180027d26  jnb     loc_180027DCF
0x180027d2c  jmp     short loc_180027D18
0x180027d2e  lea     rdx, [rbp+pbBuffer]; struct SipcSectionId *
0x180027d32  mov     rcx, rbx; this
0x180027d35  call    ?FindSection@SipcPort@@IEAAPEAVSipcSection@@AEBVSipcSectionId@@@Z; SipcPort::FindSection(SipcSectionId const &)
0x180027d3a  test    rax, rax
0x180027d3d  jnz     short loc_180027CF0
0x180027d3f  mov     r9, [rbx+30h]; void *
0x180027d43  lea     rax, [rbp+var_38]
0x180027d47  lea     r8, [rbp+pbBuffer]; struct SipcSectionId *
0x180027d4b  mov     [rsp+68h+var_48], rax; struct AlpcSection **
0x180027d50  mov     rdx, rsi; unsigned __int64
0x180027d53  mov     [rbp+var_38], 0
0x180027d5b  mov     rcx, rbx; struct AlpcPort *
0x180027d5e  call    ?Create@AlpcSection@@SAJPEBVAlpcPort@@_KAEBVSipcSectionId@@PEAXPEAPEAV1@@Z; AlpcSection::Create(AlpcPort const *,unsigned __int64,SipcSectionId const &,void *,AlpcSection * *)
0x180027d63  test    eax, eax
0x180027d65  js      short loc_180027DB9
0x180027d67  mov     r9, [rbp+var_38]
0x180027d6b  lea     rdx, [rbx+8]
0x180027d6f  mov     rax, r9
0x180027d72  neg     rax
0x180027d75  mov     rax, [rdx]
0x180027d78  sbb     r8, r8
0x180027d7b  lea     rcx, [r9+8]
0x180027d7f  and     r8, rcx
0x180027d82  cmp     [rax+8], rdx
0x180027d86  jz      short loc_180027D8F
0x180027d88  mov     ecx, 3
0x180027d8d  int     29h; Win8: RtlFailFast(ecx)
0x180027d8f  mov     [r8], rax
0x180027d92  mov     [r8+8], rdx
0x180027d96  mov     [rax+8], r8
0x180027d9a  inc     dword ptr [rdx+10h]
0x180027d9d  mov     [rdx], r8
0x180027da0  mov     rax, [r9+20h]
0x180027da4  mov     [rdi], rax
0x180027da7  xor     eax, eax
0x180027da9  jmp     short loc_180027DB9
0x180027dab  or      ecx, 10000000h
0x180027db1  mov     eax, 8000FFFFh
0x180027db6  cmovl   eax, ecx
0x180027db9  mov     rcx, [rbp+var_10]
0x180027dbd  xor     rcx, rsp; StackCookie
0x180027dc0  call    __security_check_cookie
0x180027dc5  add     rsp, 68h
0x180027dc9  pop     rdi
0x180027dca  pop     rsi
0x180027dcb  pop     rbx
0x180027dcc  pop     rbp
0x180027dcd  retn
0x180027dcf  mov     ecx, 8000FFFFh
0x180027dd4  call    SipcFailFast
```
