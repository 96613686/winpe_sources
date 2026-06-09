# CXMLRowset::GetData(ulong,unsigned __int64,ushort,bool,ulong *,unsigned __int64 *,void *)

- ea: `0x1800282d0`
- end: `0x18002854e`
- name: `?GetData@CXMLRowset@@UEAAJK_KG_NPEAKPEA_KPEAX@Z`
- size: `638`
- prototype: `__int64 __fastcall(CXMLRowset *__hidden this, unsigned int, unsigned __int64, unsigned __int16, bool, unsigned int *, unsigned __int64 *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x180003abc`
- `0x1800040a8`
- `0x18000416c`
- `0x1800041f8`
- `0x18001a6c8`
- `0x1800282d0`
- `0x180028724`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CXMLRowset::GetData(
        CXMLRowset *this,
        unsigned int a2,
        __int64 a3,
        unsigned __int16 a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned __int64 *a7,
        _QWORD *a8)
{
  unsigned __int16 v8; // r10
  int v9; // edi
  __int64 v12; // rdx
  int *v13; // rbx
  CMetaData *v14; // rsi
  unsigned __int16 v15; // dx
  unsigned __int16 Type; // bp
  unsigned __int16 v17; // dx
  unsigned __int8 Precision; // r15
  unsigned __int16 v19; // dx
  unsigned __int8 Scale; // al
  unsigned int v21; // edx
  unsigned __int8 v22; // r12
  int v23; // r11d
  unsigned __int16 *v24; // rdi
  unsigned __int8 *v25; // rax
  unsigned __int8 *v26; // rsi
  int v27; // edx
  __int64 v28; // rax
  unsigned __int16 *i; // rcx
  int v31; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v32; // [rsp+C0h] [rbp+18h]

  v32 = a3;
  v8 = a2 - 1;
  v9 = 0;
  v12 = 8LL * a2;
  if ( (_BYTE)a5 || (v13 = *(int **)(v12 + *((_QWORD *)this + 35)), (v13[1] & 0x10000000) != 0) )
    v13 = *(int **)(v12 + *((_QWORD *)this + 36));
  v14 = (CXMLRowset *)((char *)this + 304);
  a5 = v13[1] & 0xFEFFFFFF;
  if ( (CMetaData::mdGetFlags((CXMLRowset *)((char *)this + 304), v8) & 0x2000) != 0 )
  {
    if ( a7 )
      *a7 = *v13;
    *a8 = *((_QWORD *)v13 + 1);
    goto LABEL_33;
  }
  Type = CMetaData::mdGetType(v14, v15);
  Precision = CMetaData::mdGetPrecision(v14, v17);
  Scale = CMetaData::mdGetScale(v14, v19);
  v31 = 0;
  v22 = Scale;
  if ( v23 )
    goto LABEL_33;
  a5 = 8;
  v24 = (unsigned __int16 *)*((_QWORD *)v13 + 1);
  if ( Type == 128 )
  {
    v25 = MMMAlloc(*v13, v21);
    v26 = v25;
    if ( !v25 )
    {
      v9 = -2147024882;
      goto LABEL_33;
    }
    v9 = DecodeBin(v24, v25, *v13, &v31);
    if ( v9 < 0 )
      goto LABEL_32;
    v27 = v31;
    v24 = (unsigned __int16 *)v26;
  }
  else
  {
    v26 = 0;
    if ( Type == 135 || Type == 7 || Type == 64 )
    {
      v28 = *v13;
      if ( (int)v28 >= 19 )
        v24[10] = 32;
      if ( Type == 64 && (int)v28 > 19 )
      {
        for ( i = &v24[v28 - 1]; i >= v24 && *i == 48; --i )
          ;
        i[1] = 0;
      }
    }
    Type = 130;
    v27 = 2 * *v13;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned __int64 *, unsigned __int16 *, _QWORD *, __int64, _DWORD, unsigned int *, unsigned __int8, unsigned __int8, _DWORD))(**((_QWORD **)this + 66) + 24LL))(
         *((_QWORD *)this + 66),
         Type,
         a4,
         v27,
         a7,
         v24,
         a8,
         v32,
         0,
         &a5,
         Precision,
         v22,
         0);
  if ( v9 < 0 && (bidGblFlags & 2) != 0 && off_180048DE0[0] )
    bidTraceW(off_180048210[0], 219136, off_180048DE0[0], (unsigned int)v9, 214);
  if ( v26 )
LABEL_32:
    MMMFree(v26);
LABEL_33:
  if ( a6 )
    *a6 = a5;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800282d0  mov     [rsp+arg_0], rbx
0x1800282d5  mov     [rsp+arg_10], r8
0x1800282da  push    rbp
0x1800282db  push    rsi
0x1800282dc  push    rdi
0x1800282dd  push    r12
0x1800282df  push    r13
0x1800282e1  push    r14
0x1800282e3  push    r15
0x1800282e5  sub     rsp, 70h
0x1800282e9  mov     eax, edx
0x1800282eb  lea     r10d, [rdx-1]
0x1800282ef  xor     edi, edi
0x1800282f1  movzx   r13d, r9w
0x1800282f5  mov     r14, rcx
0x1800282f8  lea     rdx, ds:0[rax*8]
0x180028300  cmp     byte ptr [rsp+0A8h+arg_20], dil
0x180028308  jnz     short loc_18002831E
0x18002830a  mov     rax, [rcx+118h]
0x180028311  mov     rbx, [rdx+rax]
0x180028315  test    dword ptr [rbx+4], 10000000h
0x18002831c  jz      short loc_180028329
0x18002831e  mov     rax, [rcx+120h]
0x180028325  mov     rbx, [rdx+rax]
0x180028329  mov     r11d, [rbx+4]
0x18002832d  lea     rsi, [rcx+130h]
0x180028334  btr     r11d, 18h
0x180028339  movzx   edx, r10w; unsigned __int16
0x18002833d  mov     rcx, rsi; this
0x180028340  mov     [rsp+0A8h+arg_20], r11d
0x180028348  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18002834d  bt      eax, 0Dh
0x180028351  jnb     short loc_18002837A
0x180028353  mov     rcx, [rsp+0A8h+arg_30]
0x18002835b  test    rcx, rcx
0x18002835e  jz      short loc_180028366
0x180028360  movsxd  rax, dword ptr [rbx]
0x180028363  mov     [rcx], rax
0x180028366  mov     rax, [rsp+0A8h+arg_38]
0x18002836e  mov     rcx, [rbx+8]
0x180028372  mov     [rax], rcx
0x180028375  jmp     loc_18002851E
0x18002837a  mov     rcx, rsi; this
0x18002837d  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180028382  mov     rcx, rsi; this
0x180028385  movzx   ebp, ax
0x180028388  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x18002838d  mov     rcx, rsi; this
0x180028390  mov     r15b, al
0x180028393  call    ?mdGetScale@CMetaData@@QEAAEG@Z; CMetaData::mdGetScale(ushort)
0x180028398  mov     [rsp+0A8h+arg_8], edi
0x18002839f  mov     r12b, al
0x1800283a2  test    r11d, r11d
0x1800283a5  jnz     loc_18002851E
0x1800283ab  mov     eax, 80h
0x1800283b0  mov     [rsp+0A8h+arg_20], 8
0x1800283bb  mov     rdi, [rbx+8]
0x1800283bf  cmp     bp, ax
0x1800283c2  jnz     short loc_180028409
0x1800283c4  mov     ecx, [rbx]; unsigned int
0x1800283c6  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800283cb  mov     rsi, rax
0x1800283ce  test    rax, rax
0x1800283d1  jnz     short loc_1800283DD
0x1800283d3  mov     edi, 8007000Eh
0x1800283d8  jmp     loc_18002851E
0x1800283dd  mov     r8d, [rbx]; unsigned int
0x1800283e0  lea     r9, [rsp+0A8h+arg_8]; int *
0x1800283e8  mov     rdx, rsi; unsigned __int8 *
0x1800283eb  mov     rcx, rdi; unsigned __int16 *
0x1800283ee  call    ?DecodeBin@@YAJPEAGPEAEKPEAJ@Z; DecodeBin(ushort *,uchar *,ulong,long *)
0x1800283f3  mov     edi, eax
0x1800283f5  test    eax, eax
0x1800283f7  js      loc_180028516
0x1800283fd  mov     edx, [rsp+0A8h+arg_8]
0x180028404  mov     rdi, rsi
0x180028407  jmp     short loc_180028463
0x180028409  xor     esi, esi
0x18002840b  mov     eax, 87h
0x180028410  lea     edx, [rsi+40h]
0x180028413  cmp     bp, ax
0x180028416  jz      short loc_180028423
0x180028418  cmp     bp, 7
0x18002841c  jz      short loc_180028423
0x18002841e  cmp     bp, dx
0x180028421  jnz     short loc_18002845A
0x180028423  movsxd  rax, dword ptr [rbx]
0x180028426  cmp     eax, 13h
0x180028429  jl      short loc_180028431
0x18002842b  mov     word ptr [rdi+14h], 20h ; ' '
0x180028431  cmp     dx, bp
0x180028434  jnz     short loc_18002845A
0x180028436  cmp     eax, 13h
0x180028439  jle     short loc_18002845A
0x18002843b  lea     rcx, [rax-1]
0x18002843f  lea     rcx, [rdi+rcx*2]
0x180028443  jmp     short loc_18002844F
0x180028445  cmp     word ptr [rcx], 30h ; '0'
0x180028449  jnz     short loc_180028454
0x18002844b  sub     rcx, 2
0x18002844f  cmp     rcx, rdi
0x180028452  jnb     short loc_180028445
0x180028454  xor     eax, eax
0x180028456  mov     [rcx+2], ax
0x18002845a  mov     edx, [rbx]
0x18002845c  mov     ebp, 82h
0x180028461  add     edx, edx
0x180028463  mov     rcx, [r14+210h]
0x18002846a  mov     r8, [rsp+0A8h+arg_38]
0x180028472  mov     [rsp+0A8h+var_48], 0
0x18002847a  mov     [rsp+0A8h+var_50], r12b
0x18002847f  mov     rax, [rcx]
0x180028482  mov     [rsp+0A8h+var_58], r15b
0x180028487  movsxd  r9, edx
0x18002848a  lea     rdx, [rsp+0A8h+arg_20]
0x180028492  mov     [rsp+0A8h+var_60], rdx
0x180028497  mov     rdx, [rsp+0A8h+arg_10]
0x18002849f  mov     rax, [rax+18h]
0x1800284a3  mov     [rsp+0A8h+var_68], 0
0x1800284ab  mov     [rsp+0A8h+var_70], rdx
0x1800284b0  movzx   edx, bp
0x1800284b3  mov     [rsp+0A8h+var_78], r8
0x1800284b8  mov     r8, [rsp+0A8h+arg_30]
0x1800284c0  mov     [rsp+0A8h+var_80], rdi
0x1800284c5  mov     [rsp+0A8h+var_88], r8
0x1800284ca  movzx   r8d, r13w
0x1800284ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284d3  mov     edi, eax
0x1800284d5  test    eax, eax
0x1800284d7  jns     short loc_180028511
0x1800284d9  test    byte ptr cs:_bidGblFlags, 2
0x1800284e0  jz      short loc_180028511
0x1800284e2  mov     rax, cs:off_180048DE0; "<CXMLRowset::GetData|ADO|ERR>  HRESULT:"...
0x1800284e9  test    rax, rax
0x1800284ec  jz      short loc_180028511
0x1800284ee  mov     r8, cs:off_180048DE0; "<CXMLRowset::GetData|ADO|ERR>  HRESULT:"...
0x1800284f5  mov     r9d, edi
0x1800284f8  mov     rcx, cs:off_180048210; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800284ff  mov     edx, 35800h
0x180028504  mov     dword ptr [rsp+0A8h+var_88], 0D6h
0x18002850c  call    _bidTraceW
0x180028511  test    rsi, rsi
0x180028514  jz      short loc_18002851E
0x180028516  mov     rcx, rsi; unsigned __int8 *
0x180028519  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18002851e  mov     rcx, [rsp+0A8h+arg_28]
0x180028526  test    rcx, rcx
0x180028529  jz      short loc_180028534
0x18002852b  mov     eax, [rsp+0A8h+arg_20]
0x180028532  mov     [rcx], eax
0x180028534  mov     rbx, [rsp+0A8h+arg_0]
0x18002853c  mov     eax, edi
0x18002853e  add     rsp, 70h
0x180028542  pop     r15
0x180028544  pop     r14
0x180028546  pop     r13
0x180028548  pop     r12
0x18002854a  pop     rdi
0x18002854b  pop     rsi
0x18002854c  pop     rbp
0x18002854d  retn
```
