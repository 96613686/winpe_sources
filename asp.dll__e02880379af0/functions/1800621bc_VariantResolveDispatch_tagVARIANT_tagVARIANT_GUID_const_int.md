# VariantResolveDispatch(tagVARIANT *,tagVARIANT *,_GUID const &,int)

- ea: `0x1800621bc`
- end: `0x18006233c`
- name: `?VariantResolveDispatch@@YAJPEAUtagVARIANT@@0AEBU_GUID@@H@Z`
- size: `384`
- prototype: `__int64 __fastcall(VARIANTARG *pvarg, VARIANTARG *pvargSrc, const struct _GUID *, unsigned int)`
- caller_count: `23`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180018de0`
- `0x180032154`
- `0x1800332c0`
- `0x180033430`
- `0x180036b40`
- `0x18003ab50`
- `0x18003af10`
- `0x18003b590`
- `0x18004d9b0`
- `0x18004dec0`
- `0x18004e430`
- `0x18004e890`
- `0x18004f030`
- `0x18004f610`
- `0x18004f950`
- `0x18004fca0`
- `0x180050000`
- `0x180050360`
- `0x180051460`
- `0x180053850`
- `0x180058c08`
- `0x180059ba0`
- `0x180059d70`

## callees

- `0x180023d86`
- `0x1800405bc`
- `0x1800406b0`
- `0x1800621bc`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006230d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006230d`
- `OLEAUT32!__imp_VariantInit` at `0x180062206`
- `OLEAUT32!__imp_VariantInit` at `0x180062268`
- `OLEAUT32!__imp_VariantInit` at `0x180062206`
- `OLEAUT32!__imp_VariantInit` at `0x180062268`
- `OLEAUT32!__imp_VariantClear` at `0x1800622c1`
- `OLEAUT32!__imp_VariantClear` at `0x180062331`
- `OLEAUT32!__imp_VariantClear` at `0x1800622c1`
- `OLEAUT32!__imp_VariantClear` at `0x180062331`
- `OLEAUT32!__imp_VariantCopy` at `0x180062224`
- `OLEAUT32!__imp_VariantCopy` at `0x180062224`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18006221c`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18006221c`

## pseudocode

```c
__int64 __fastcall VariantResolveDispatch(
        VARIANTARG *pvarg,
        VARIANTARG *pvargSrc,
        const struct _GUID *a3,
        unsigned int a4)
{
  HRESULT v8; // eax
  unsigned int v9; // edi
  int v11; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  int v13; // [rsp+20h] [rbp-69h]
  VARIANTARG pvarga; // [rsp+50h] [rbp-39h] BYREF
  __int128 v15; // [rsp+68h] [rbp-21h] BYREF
  __int64 v16; // [rsp+78h] [rbp-11h]
  _BYTE v17[8]; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int16 *v18; // [rsp+88h] [rbp-1h]
  unsigned __int16 *v19; // [rsp+90h] [rbp+7h]
  BSTR bstrString; // [rsp+98h] [rbp+Fh]

  v16 = 0;
  memset(&pvarga, 0, sizeof(pvarga));
  v15 = 0;
  memset_0(v17, 0, 0x40u);
  VariantInit(pvarg);
  if ( (pvargSrc->vt & 0x4000) != 0 )
    v8 = VariantCopyInd(pvarg, pvargSrc);
  else
    v8 = VariantCopy(pvarg, pvargSrc);
  v9 = v8;
  if ( v8 >= 0 )
  {
    while ( 1 )
    {
      if ( pvarg->vt != 9 )
        return 0;
      if ( !pvarg->llVal )
      {
        v9 = -2147352573;
        goto LABEL_15;
      }
      VariantInit(&pvarga);
      LOWORD(v13) = 3;
      v11 = (*(__int64 (__fastcall **)(LONGLONG, _QWORD, GUID *, __int64, int, __int128 *, VARIANTARG *, _BYTE *, _QWORD))(*pvarg->pllVal + 48))(
              pvarg->llVal,
              0,
              &GUID_NULL,
              2048,
              v13,
              &v15,
              &pvarga,
              v17,
              0);
      v9 = v11;
      if ( v11 < 0 )
        break;
      VariantClear(pvarg);
      pRecInfo = pvarga.pRecInfo;
      *(_OWORD *)&pvarg->vt = *(_OWORD *)&pvarga.vt;
      pvarg->pRecInfo = pRecInfo;
    }
    if ( v11 == -2147352567 )
    {
      Exception(a3, v18, v19);
      SysFreeString(bstrString);
      goto LABEL_16;
    }
LABEL_15:
    ExceptionId(a3, a4, 0x2328u, 0);
LABEL_16:
    VariantClear(pvarg);
  }
  else
  {
    ExceptionId(a3, a4, (v8 != -2147024882) + 100, 0);
  }
  return v9;
}

```

## disassembly

```asm
0x1800621bc  push    rbp
0x1800621be  push    rbx
0x1800621bf  push    rsi
0x1800621c0  push    rdi
0x1800621c1  push    r14
0x1800621c3  lea     rbp, [rsp-37h]
0x1800621c8  sub     rsp, 0C0h
0x1800621cf  xor     eax, eax
0x1800621d1  mov     rsi, r8
0x1800621d4  mov     rdi, rdx
0x1800621d7  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800621db  mov     rbx, rcx
0x1800621de  mov     [rbp+57h+var_68], rax
0x1800621e2  xorps   xmm0, xmm0
0x1800621e5  lea     rcx, [rbp+57h+var_60]; void *
0x1800621e9  xorps   xmm1, xmm1
0x1800621ec  lea     r8d, [rax+40h]; Size
0x1800621f0  xor     edx, edx; Val
0x1800621f2  mov     r14d, r9d
0x1800621f5  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800621f9  movdqu  [rbp+57h+var_78], xmm1
0x1800621fe  call    memset_0
0x180062203  mov     rcx, rbx; pvarg
0x180062206  call    cs:__imp_VariantInit
0x18006220c  mov     eax, 4000h
0x180062211  mov     rdx, rdi; pvargSrc
0x180062214  mov     rcx, rbx; pvargDest
0x180062217  test    [rdi], ax
0x18006221a  jz      short loc_180062224
0x18006221c  call    cs:__imp_VariantCopyInd
0x180062222  jmp     short loc_18006222A
0x180062224  call    cs:__imp_VariantCopy
0x18006222a  mov     edi, eax
0x18006222c  test    eax, eax
0x18006222e  jns     loc_1800622D8
0x180062234  xor     r8d, r8d
0x180062237  mov     edx, r14d; unsigned int
0x18006223a  cmp     eax, 8007000Eh
0x18006223f  mov     rcx, rsi; struct _GUID *
0x180062242  setnz   r8b
0x180062246  xor     r9d, r9d; int
0x180062249  add     r8d, 64h ; 'd'; unsigned int
0x18006224d  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180062252  mov     eax, edi
0x180062254  jmp     loc_1800622E4
0x180062259  cmp     qword ptr [rbx+8], 0
0x18006225e  jz      loc_180062315
0x180062264  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180062268  call    cs:__imp_VariantInit
0x18006226e  mov     rcx, [rbx+8]
0x180062272  lea     rdx, [rbp+57h+var_60]
0x180062276  mov     [rsp+0E0h+var_A0], 0
0x18006227f  lea     r8, GUID_NULL
0x180062286  mov     [rsp+0E0h+var_A8], rdx
0x18006228b  mov     r9d, 800h
0x180062291  lea     rdx, [rbp+57h+pvarg]
0x180062295  mov     rax, [rcx]
0x180062298  mov     [rsp+0E0h+var_B0], rdx
0x18006229d  lea     rdx, [rbp+57h+var_78]
0x1800622a1  mov     [rsp+0E0h+var_B8], rdx
0x1800622a6  xor     edx, edx
0x1800622a8  mov     [rsp+0E0h+var_C0], 3
0x1800622af  mov     rax, [rax+30h]
0x1800622b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622b8  mov     edi, eax
0x1800622ba  test    eax, eax
0x1800622bc  js      short loc_1800622F2
0x1800622be  mov     rcx, rbx; pvarg
0x1800622c1  call    cs:__imp_VariantClear
0x1800622c7  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800622cb  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800622d0  movups  xmmword ptr [rbx], xmm0
0x1800622d3  movsd   qword ptr [rbx+10h], xmm1
0x1800622d8  cmp     word ptr [rbx], 9
0x1800622dc  jz      loc_180062259
0x1800622e2  xor     eax, eax
0x1800622e4  add     rsp, 0C0h
0x1800622eb  pop     r14
0x1800622ed  pop     rdi
0x1800622ee  pop     rsi
0x1800622ef  pop     rbx
0x1800622f0  pop     rbp
0x1800622f1  retn
0x1800622f2  cmp     eax, 80020009h
0x1800622f7  jnz     short loc_18006231A
0x1800622f9  mov     r8, [rbp+57h+var_50]; unsigned __int16 *
0x1800622fd  mov     rcx, rsi; struct _GUID *
0x180062300  mov     rdx, [rbp+57h+var_58]; unsigned __int16 *
0x180062304  call    ?Exception@@YAXAEBU_GUID@@PEAG1@Z; Exception(_GUID const &,ushort *,ushort *)
0x180062309  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18006230d  call    cs:__imp_SysFreeString
0x180062313  jmp     short loc_18006232E
0x180062315  mov     edi, 80020003h
0x18006231a  xor     r9d, r9d; int
0x18006231d  mov     r8d, 2328h; unsigned int
0x180062323  mov     edx, r14d; unsigned int
0x180062326  mov     rcx, rsi; struct _GUID *
0x180062329  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18006232e  mov     rcx, rbx; pvarg
0x180062331  call    cs:__imp_VariantClear
0x180062337  jmp     loc_180062252
```
