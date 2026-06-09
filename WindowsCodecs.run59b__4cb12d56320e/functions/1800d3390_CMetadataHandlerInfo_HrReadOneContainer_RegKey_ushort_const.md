# CMetadataHandlerInfo::HrReadOneContainer(RegKey *,ushort const *)

- ea: `0x1800d3390`
- end: `0x1800d36bd`
- name: `?HrReadOneContainer@CMetadataHandlerInfo@@IEAAJPEAVRegKey@@PEBG@Z`
- size: `813`
- prototype: `int(CMetadataHandlerInfo *__hidden this, struct RegKey *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180061bf4`

## callees

- `0x180025cd8`
- `0x180064368`
- `0x180064458`
- `0x1800bd9d4`
- `0x1800c7d9c`
- `0x1800d3390`
- `0x1800d36c4`
- `0x1800e5e60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3681`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3690`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3681`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3690`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800d33e8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800d33e8`

## string_xrefs

- `0x1800d3485`: `WriteHeader`
- `0x1800d3463`: `WritePosition`
- `0x1800d34b0`: `WriteOffset`

## pseudocode

```c
__int64 __fastcall CMetadataHandlerInfo::HrReadOneContainer(
        CMetadataHandlerInfo *this,
        struct RegKey *a2,
        const unsigned __int16 *a3)
{
  void *v5; // r14
  HRESULT IntValue; // eax
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 *v10; // rsi
  _QWORD *v11; // r8
  __int64 v12; // rax
  CRegistryInfo *v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // edx
  int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  __int64 v24; // [rsp+30h] [rbp-39h] BYREF
  void *v25; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v26[4]; // [rsp+40h] [rbp-29h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v28[4]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+70h] [rbp+7h]
  GUID iid; // [rsp+78h] [rbp+Fh] BYREF

  v25 = 0;
  v29 = 0;
  v5 = 0;
  iid = 0;
  *(_OWORD *)v26 = 0;
  *(_OWORD *)Block = 0;
  *(_OWORD *)v28 = 0;
  IntValue = IIDFromString(a3, &iid);
  v8 = IntValue;
  if ( IntValue < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_48;
LABEL_3:
    DoStackCapture(IntValue);
LABEL_48:
    free(Block[1]);
    free(v5);
    return (unsigned int)v8;
  }
  v9 = 0;
  v10 = (__int64 *)((char *)this + 304);
  while ( (unsigned int)v9 < *((_DWORD *)this + 73) )
  {
    v7 = 56LL * (unsigned int)v9;
    v11 = *(_QWORD **)(v7 + *v10);
    v12 = *(_QWORD *)&iid.Data1 - *v11;
    if ( *(_QWORD *)&iid.Data1 == *v11 )
      v12 = *(_QWORD *)iid.Data4 - v11[1];
    if ( !v12 )
      return (unsigned int)v8;
    v9 = (unsigned int)(v9 + 1);
  }
  if ( (*((_BYTE *)this + 76) & 0x10) != 0 )
  {
    IntValue = CRegistryInfo::SafeReadIntValue(a2, L"WritePosition", &v26[2]);
    v8 = IntValue;
    if ( IntValue < 0
      || (IntValue = CRegistryInfo::SafeReadBinaryValue(
                       v13,
                       a2,
                       L"WriteHeader",
                       (unsigned __int8 **)&Block[1],
                       (unsigned int *)Block),
          v8 = IntValue,
          IntValue < 0) )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_48;
      goto LABEL_3;
    }
    if ( (int)CRegistryInfo::SafeReadIntValue(a2, L"WriteOffset", v28) < 0 )
      *(_QWORD *)v28 = -1;
  }
  else if ( (*((_BYTE *)this + 76) & 8) != 0 )
  {
    v24 = 0;
    v14 = CComponentInfo::ReadPatterns<WICMetadataPattern>(v7, v9, a2, &v25, &v24, (char *)&v24 + 4);
    v8 = v14;
    if ( v14 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v14);
      v5 = v25;
      goto LABEL_48;
    }
    v5 = v25;
    v29 = v24;
    *(_QWORD *)&v28[2] = v25;
  }
  v15 = *((_DWORD *)this + 118);
  v16 = v15 + 1;
  if ( v15 + 1 < v15 )
  {
    v8 = -2147024362;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_48;
    DoStackCapture(-2147024362);
    goto LABEL_46;
  }
  if ( v16 <= *((_DWORD *)this + 117) )
  {
    *(GUID *)(*((_QWORD *)this + 56) + 16LL * v15) = iid;
    *((_DWORD *)this + 118) = v16;
    goto LABEL_31;
  }
  v17 = DynArrayImpl<0>::AddMultipleAndSet((__int64)this + 448, 0x10u, 1, &iid);
  v8 = v17;
  if ( v17 < 0 && (_DWORD)g_doStackCaptures )
    DoStackCapture(v17);
  if ( v8 < 0 )
  {
LABEL_46:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_48;
  }
LABEL_31:
  v18 = *((unsigned int *)this + 82);
  *(_QWORD *)v26 = *((_QWORD *)this + 56) + 16LL * (unsigned int)(*((_DWORD *)this + 118) - 1);
  v19 = v18 + 1;
  if ( (int)v18 + 1 < (unsigned int)v18 )
  {
    v8 = -2147024362;
    if ( !(_DWORD)g_doStackCaptures )
    {
LABEL_43:
      DynArray<_GUID,0>::RemoveAt((char *)this + 448, (unsigned int)(*((_DWORD *)this + 118) - 1));
      goto LABEL_48;
    }
    DoStackCapture(-2147024362);
LABEL_41:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_43;
  }
  if ( v19 <= *((_DWORD *)this + 81) )
  {
    v8 = 0;
    v20 = 56 * v18;
    v21 = *v10;
    *(_OWORD *)(v20 + v21) = *(_OWORD *)v26;
    *(_OWORD *)(v20 + v21 + 16) = *(_OWORD *)Block;
    *(_OWORD *)(v20 + v21 + 32) = *(_OWORD *)v28;
    *(_QWORD *)(v20 + v21 + 48) = v29;
    *((_DWORD *)this + 82) = v19;
    return (unsigned int)v8;
  }
  v22 = DynArrayImpl<0>::AddMultipleAndSet((__int64)this + 304, 0x38u, 1, v26);
  v8 = v22;
  if ( v22 < 0 && (_DWORD)g_doStackCaptures )
    DoStackCapture(v22);
  if ( v8 < 0 )
    goto LABEL_41;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800d3390  push    rbp
0x1800d3392  push    rbx
0x1800d3393  push    rsi
0x1800d3394  push    rdi
0x1800d3395  push    r12
0x1800d3397  push    r14
0x1800d3399  push    r15
0x1800d339b  lea     rbp, [rsp-27h]
0x1800d33a0  sub     rsp, 90h
0x1800d33a7  mov     rax, cs:__security_cookie
0x1800d33ae  xor     rax, rsp
0x1800d33b1  mov     [rbp+57h+var_38], rax
0x1800d33b5  xorps   xmm1, xmm1
0x1800d33b8  mov     rdi, rdx
0x1800d33bb  mov     r15, rcx
0x1800d33be  lea     rdx, [rbp+57h+iid]; lpiid
0x1800d33c2  xor     r12d, r12d
0x1800d33c5  xorps   xmm0, xmm0
0x1800d33c8  xor     eax, eax
0x1800d33ca  mov     [rbp+57h+var_88], r12
0x1800d33ce  mov     rcx, r8; lpsz
0x1800d33d1  mov     [rbp+57h+var_50], rax
0x1800d33d5  mov     r14d, r12d
0x1800d33d8  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x1800d33dc  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x1800d33e0  movups  xmmword ptr [rbp+57h+Block], xmm1
0x1800d33e4  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x1800d33e8  call    cs:__imp_IIDFromString
0x1800d33ef  nop     dword ptr [rax+rax+00h]
0x1800d33f4  mov     ebx, eax
0x1800d33f6  test    eax, eax
0x1800d33f8  jns     short loc_1800D3417
0x1800d33fa  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d3401  jz      short loc_1800D340F
0x1800d3403  mov     ecx, eax; int
0x1800d3405  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d340a  jmp     loc_1800D367D
0x1800d340f  test    eax, eax
0x1800d3411  js      loc_1800D367D
0x1800d3417  mov     edx, r12d
0x1800d341a  lea     rsi, [r15+130h]
0x1800d3421  cmp     edx, [r15+124h]
0x1800d3428  jnb     short loc_1800D3455
0x1800d342a  mov     eax, edx
0x1800d342c  imul    rcx, rax, 38h ; '8'
0x1800d3430  mov     rax, [rsi]
0x1800d3433  mov     r8, [rcx+rax]
0x1800d3437  mov     rax, qword ptr [rbp+57h+iid.Data1]
0x1800d343b  sub     rax, [r8]
0x1800d343e  jnz     short loc_1800D3448
0x1800d3440  mov     rax, qword ptr [rbp+57h+iid.Data4]
0x1800d3444  sub     rax, [r8+8]
0x1800d3448  test    rax, rax
0x1800d344b  jz      loc_1800D369C
0x1800d3451  inc     edx
0x1800d3453  jmp     short loc_1800D3421
0x1800d3455  test    byte ptr [r15+4Ch], 10h
0x1800d345a  jz      short loc_1800D34CA
0x1800d345c  lea     r8, [rbp+57h+var_80+8]; unsigned int *
0x1800d3460  mov     rcx, rdi; struct RegKey *
0x1800d3463  lea     rdx, aWriteposition; "WritePosition"
0x1800d346a  call    ?SafeReadIntValue@CRegistryInfo@@KAJPEAVRegKey@@PEBGPEAK@Z; CRegistryInfo::SafeReadIntValue(RegKey *,ushort const *,ulong *)
0x1800d346f  mov     ebx, eax
0x1800d3471  test    eax, eax
0x1800d3473  js      short loc_1800D3497
0x1800d3475  lea     rax, [rbp+57h+Block]
0x1800d3479  mov     rdx, rdi; struct RegKey *
0x1800d347c  lea     r9, [rbp+57h+Block+8]; unsigned __int8 **
0x1800d3480  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x1800d3485  lea     r8, aWriteheader; "WriteHeader"
0x1800d348c  call    ?SafeReadBinaryValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAEPEAI@Z; CRegistryInfo::SafeReadBinaryValue(RegKey *,ushort const *,uchar * *,uint *)
0x1800d3491  mov     ebx, eax
0x1800d3493  test    eax, eax
0x1800d3495  jns     short loc_1800D34A9
0x1800d3497  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d349e  jz      loc_1800D367D
0x1800d34a4  jmp     loc_1800D3403
0x1800d34a9  lea     r8, [rbp+57h+var_60]; unsigned int *
0x1800d34ad  mov     rcx, rdi; struct RegKey *
0x1800d34b0  lea     rdx, aWriteoffset; "WriteOffset"
0x1800d34b7  call    ?SafeReadIntValue@CRegistryInfo@@KAJPEAVRegKey@@PEBGPEAK@Z; CRegistryInfo::SafeReadIntValue(RegKey *,ushort const *,ulong *)
0x1800d34bc  test    eax, eax
0x1800d34be  jns     short loc_1800D352A
0x1800d34c0  mov     qword ptr [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x1800d34c8  jmp     short loc_1800D352A
0x1800d34ca  test    byte ptr [r15+4Ch], 8
0x1800d34cf  jz      short loc_1800D352A
0x1800d34d1  lea     rax, [rbp+57h+var_90+4]
0x1800d34d5  mov     dword ptr [rbp+57h+var_90+4], r12d
0x1800d34d9  mov     [rsp+0C0h+var_98], rax
0x1800d34de  lea     r9, [rbp+57h+var_88]
0x1800d34e2  lea     rax, [rbp+57h+var_90]
0x1800d34e6  mov     dword ptr [rbp+57h+var_90], r12d
0x1800d34ea  mov     r8, rdi
0x1800d34ed  mov     [rsp+0C0h+var_A0], rax
0x1800d34f2  call    ??$ReadPatterns@UWICMetadataPattern@@@CComponentInfo@@IEAAJP6AJPEAVRegKey@@PEAUWICMetadataPattern@@@Z0PEAPEAU2@PEAI4@Z; CComponentInfo::ReadPatterns<WICMetadataPattern>(long (*)(RegKey *,WICMetadataPattern *),RegKey *,WICMetadataPattern * *,uint *,uint *)
0x1800d34f7  mov     ebx, eax
0x1800d34f9  test    eax, eax
0x1800d34fb  jns     short loc_1800D3516
0x1800d34fd  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d3504  jz      short loc_1800D350D
0x1800d3506  mov     ecx, eax; int
0x1800d3508  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d350d  mov     r14, [rbp+57h+var_88]
0x1800d3511  jmp     loc_1800D367D
0x1800d3516  mov     eax, dword ptr [rbp+57h+var_90]
0x1800d3519  mov     r14, [rbp+57h+var_88]
0x1800d351d  mov     dword ptr [rbp+57h+var_50], eax
0x1800d3520  mov     eax, dword ptr [rbp+57h+var_90+4]
0x1800d3523  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800d3526  mov     qword ptr [rbp+57h+var_60+8], r14
0x1800d352a  lea     rdi, [r15+1C0h]
0x1800d3531  mov     eax, [rdi+18h]
0x1800d3534  lea     edx, [rax+1]
0x1800d3537  cmp     edx, eax
0x1800d3539  jb      loc_1800D3654
0x1800d353f  cmp     edx, [rdi+14h]
0x1800d3542  ja      short loc_1800D355A
0x1800d3544  movups  xmm0, xmmword ptr [rbp+57h+iid.Data1]
0x1800d3548  mov     ecx, eax
0x1800d354a  mov     rax, [rdi]
0x1800d354d  add     rcx, rcx
0x1800d3550  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x1800d3555  mov     [rdi+18h], edx
0x1800d3558  jmp     short loc_1800D358D
0x1800d355a  mov     edx, 10h
0x1800d355f  lea     r9, [rbp+57h+iid]
0x1800d3563  mov     rcx, rdi
0x1800d3566  lea     r8d, [rdx-0Fh]
0x1800d356a  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800d356f  mov     ebx, eax
0x1800d3571  test    eax, eax
0x1800d3573  jns     short loc_1800D3585
0x1800d3575  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d357c  jz      short loc_1800D3585
0x1800d357e  mov     ecx, eax; int
0x1800d3580  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3585  test    ebx, ebx
0x1800d3587  js      loc_1800D3669
0x1800d358d  mov     ecx, [rdi+18h]
0x1800d3590  mov     eax, [rsi+18h]
0x1800d3593  dec     ecx
0x1800d3595  shl     rcx, 4
0x1800d3599  add     rcx, [rdi]
0x1800d359c  mov     qword ptr [rbp+57h+var_80], rcx
0x1800d35a0  lea     edx, [rax+1]
0x1800d35a3  cmp     edx, eax
0x1800d35a5  jb      short loc_1800D3618
0x1800d35a7  cmp     edx, [rsi+14h]
0x1800d35aa  ja      short loc_1800D35E3
0x1800d35ac  movups  xmm0, xmmword ptr [rbp+57h+var_80]
0x1800d35b0  mov     ebx, r12d
0x1800d35b3  imul    rcx, rax, 38h ; '8'
0x1800d35b7  mov     rax, [rsi]
0x1800d35ba  movups  xmmword ptr [rcx+rax], xmm0
0x1800d35be  movups  xmm1, xmmword ptr [rbp+57h+Block]
0x1800d35c2  movups  xmmword ptr [rcx+rax+10h], xmm1
0x1800d35c7  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x1800d35cb  movups  xmmword ptr [rcx+rax+20h], xmm0
0x1800d35d0  movsd   xmm1, [rbp+57h+var_50]
0x1800d35d5  movsd   qword ptr [rcx+rax+30h], xmm1
0x1800d35db  mov     [rsi+18h], edx
0x1800d35de  jmp     loc_1800D369C
0x1800d35e3  mov     edx, 38h ; '8'
0x1800d35e8  lea     r9, [rbp+57h+var_80]
0x1800d35ec  mov     rcx, rsi
0x1800d35ef  lea     r8d, [rdx-37h]
0x1800d35f3  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800d35f8  mov     ebx, eax
0x1800d35fa  test    eax, eax
0x1800d35fc  jns     short loc_1800D360E
0x1800d35fe  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d3605  jz      short loc_1800D360E
0x1800d3607  mov     ecx, eax; int
0x1800d3609  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d360e  test    ebx, ebx
0x1800d3610  jns     loc_1800D369C
0x1800d3616  jmp     short loc_1800D362D
0x1800d3618  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d361f  mov     ebx, 80070216h
0x1800d3624  jz      short loc_1800D363D
0x1800d3626  mov     ecx, ebx; int
0x1800d3628  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d362d  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d3634  jz      short loc_1800D363D
0x1800d3636  mov     ecx, ebx; int
0x1800d3638  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d363d  test    ebx, ebx
0x1800d363f  jns     short loc_1800D369C
0x1800d3641  lea     rcx, [r15+1C0h]
0x1800d3648  mov     edx, [rcx+18h]
0x1800d364b  dec     edx
0x1800d364d  call    ?RemoveAt@?$DynArray@U_GUID@@$0A@@@QEAAJI@Z; DynArray<_GUID,0>::RemoveAt(uint)
0x1800d3652  jmp     short loc_1800D367D
0x1800d3654  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d365b  mov     ebx, 80070216h
0x1800d3660  jz      short loc_1800D3679
0x1800d3662  mov     ecx, ebx; int
0x1800d3664  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3669  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d3670  jz      short loc_1800D3679
0x1800d3672  mov     ecx, ebx; int
0x1800d3674  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3679  test    ebx, ebx
0x1800d367b  jns     short loc_1800D369C
0x1800d367d  mov     rcx, [rbp+57h+Block+8]; Block
0x1800d3681  call    cs:__imp_free
0x1800d3688  nop     dword ptr [rax+rax+00h]
0x1800d368d  mov     rcx, r14; Block
0x1800d3690  call    cs:__imp_free
0x1800d3697  nop     dword ptr [rax+rax+00h]
0x1800d369c  mov     eax, ebx
0x1800d369e  mov     rcx, [rbp+57h+var_38]
0x1800d36a2  xor     rcx, rsp; StackCookie
0x1800d36a5  call    __security_check_cookie
0x1800d36aa  add     rsp, 90h
0x1800d36b1  pop     r15
0x1800d36b3  pop     r14
0x1800d36b5  pop     r12
0x1800d36b7  pop     rdi
0x1800d36b8  pop     rsi
0x1800d36b9  pop     rbx
0x1800d36ba  pop     rbp
0x1800d36bb  retn
```
