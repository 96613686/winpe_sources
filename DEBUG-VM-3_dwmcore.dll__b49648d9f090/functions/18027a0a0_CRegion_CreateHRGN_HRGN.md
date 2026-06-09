# CRegion::CreateHRGN(HRGN__ * *)

- ea: `0x18027a0a0`
- end: `0x18027a2d9`
- name: `?CreateHRGN@CRegion@@QEBAJPEAPEAUHRGN__@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(CRegion *__hidden this, HRGN *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18028b7e0`
- `0x18028b960`

## callees

- `0x18000caf0`
- `0x18000d5a0`
- `0x18000d5d8`
- `0x180042de0`
- `0x180044220`
- `0x180048e48`
- `0x180168d00`
- `0x180228490`
- `0x18022943c`
- `0x18027a0a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027a0fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027a233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027a0fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027a233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027a119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027a261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027a119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027a261`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x18027a241`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x18027a241`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x18027a107`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x18027a107`

## pseudocode

```c
__int64 __fastcall CRegion::CreateHRGN(CRegion *this, HRGN *a2)
{
  unsigned int RectangleCount; // eax
  unsigned int v5; // esi
  HRGN Region; // rsi
  signed int v7; // eax
  signed int v8; // ebx
  int v9; // r14d
  DWORD v10; // r12d
  RGNDATA *p_Data; // rbx
  char *Buffer; // rsi
  _DWORD *v13; // rcx
  int v14; // eax
  FastRegion::Internal::CRgnData *v15; // rcx
  __int64 v16; // rdx
  signed int LastError; // eax
  _BYTE v19[8]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h]
  _DWORD *v21; // [rsp+40h] [rbp-C0h]
  FastRegion::Internal::CRgnData *v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+50h] [rbp-B0h]
  RECT rect; // [rsp+60h] [rbp-A0h] BYREF
  RGNDATA Data; // [rsp+70h] [rbp-90h] BYREF

  RectangleCount = FastRegion::CRegion::GetRectangleCount(this);
  v5 = RectangleCount;
  if ( RectangleCount > 1 )
  {
    *(_QWORD *)&rect.left = 0;
    v9 = 16 * RectangleCount;
    v10 = 16 * RectangleCount + 32;
    memset_0(&Data, 0, 0x120u);
    if ( v5 > 0x10 )
    {
      *(_QWORD *)&rect.left = MIDL_user_allocate(v10);
      p_Data = *(RGNDATA **)&rect.left;
      if ( !*(_QWORD *)&rect.left )
      {
        v8 = -2147024882;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x61u, 0);
        goto LABEL_23;
      }
    }
    else
    {
      p_Data = &Data;
    }
    *(_QWORD *)&p_Data->rdh.rcBound.left = 0;
    *(_QWORD *)&p_Data->rdh.rcBound.right = 0;
    p_Data->rdh.nCount = v5;
    Buffer = p_Data->Buffer;
    p_Data->rdh.dwSize = 32;
    p_Data->rdh.iType = 1;
    p_Data->rdh.nRgnSize = v9;
    FastRegion::CRegion::BeginIterator(this, v19);
    while ( 1 )
    {
      v13 = v21;
      if ( (unsigned __int64)v21 >= v20 )
        break;
      *((_DWORD *)Buffer + 1) = *v21;
      v14 = v13[2];
      v15 = v22;
      *((_DWORD *)Buffer + 3) = v14;
      v16 = 2 * v23;
      *(_DWORD *)Buffer = *((_DWORD *)v15 + v16);
      *((_DWORD *)Buffer + 2) = *((_DWORD *)v15 + v16 + 1);
      Buffer += 16;
      FastRegion::Internal::CRgnData::StepIterator(v15, (struct FastRegion::CRegion::Iterator *)v19);
    }
    SetLastError(0);
    Region = ExtCreateRegion(0, v10, p_Data);
    if ( Region )
    {
      std::unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>::~unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>(&rect);
      goto LABEL_17;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2003304445;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x7Du, 0);
LABEL_23:
    std::unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>::~unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>(&rect);
    return (unsigned int)v8;
  }
  rect = 0;
  FastRegion::CRegion::GetBoundingRect(this, &rect);
  SetLastError(0);
  Region = CreateRectRgnIndirect(&rect);
  if ( Region )
  {
LABEL_17:
    v8 = 0;
    *a2 = Region;
    return (unsigned int)v8;
  }
  v7 = GetLastError();
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
    v8 = -2003304445;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x4Cu, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18027a0a0  mov     [rsp-8+arg_10], rbx
0x18027a0a5  mov     [rsp-8+arg_18], rsi
0x18027a0aa  push    rbp
0x18027a0ab  push    r12
0x18027a0ad  push    r13
0x18027a0af  push    r14
0x18027a0b1  push    r15
0x18027a0b3  lea     rbp, [rsp-0A0h]
0x18027a0bb  sub     rsp, 1A0h
0x18027a0c2  mov     rax, cs:__security_cookie
0x18027a0c9  xor     rax, rsp
0x18027a0cc  mov     [rbp+0C0h+var_30], rax
0x18027a0d3  mov     r13, rdx
0x18027a0d6  mov     r15, rcx
0x18027a0d9  call    ?GetRectangleCount@CRegion@FastRegion@@QEBAIXZ; FastRegion::CRegion::GetRectangleCount(void)
0x18027a0de  mov     esi, eax
0x18027a0e0  cmp     eax, 1
0x18027a0e3  ja      short loc_18027A15E
0x18027a0e5  xorps   xmm0, xmm0
0x18027a0e8  lea     rdx, [rsp+1C0h+rect]; struct tagRECT *
0x18027a0ed  mov     rcx, r15; this
0x18027a0f0  movups  xmmword ptr [rsp+1C0h+rect.left], xmm0
0x18027a0f5  call    ?GetBoundingRect@CRegion@FastRegion@@QEBA_NAEAUtagRECT@@@Z; FastRegion::CRegion::GetBoundingRect(tagRECT &)
0x18027a0fa  xor     ecx, ecx; dwErrCode
0x18027a0fc  call    cs:__imp_SetLastError
0x18027a102  lea     rcx, [rsp+1C0h+rect]; lprect
0x18027a107  call    cs:__imp_CreateRectRgnIndirect
0x18027a10d  mov     rsi, rax
0x18027a110  test    rax, rax
0x18027a113  jnz     loc_18027A259
0x18027a119  call    cs:__imp_GetLastError
0x18027a11f  mov     ebx, eax
0x18027a121  test    eax, eax
0x18027a123  jle     short loc_18027A12E
0x18027a125  movzx   ebx, ax
0x18027a128  or      ebx, 80070000h
0x18027a12e  test    ebx, ebx
0x18027a130  mov     [rsp+1C0h+var_198], 0; void *
0x18027a139  mov     eax, 88980003h
0x18027a13e  mov     [rsp+1C0h+var_1A0], 4Ch ; 'L'; unsigned int
0x18027a146  cmovns  ebx, eax
0x18027a149  xor     edx, edx; int *
0x18027a14b  mov     r9d, ebx; int
0x18027a14e  xor     r8d, r8d; unsigned int
0x18027a151  lea     ecx, [rdx+14h]; unsigned int
0x18027a154  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18027a159  jmp     loc_18027A2AB
0x18027a15e  mov     r14d, esi
0x18027a161  mov     qword ptr [rsp+1C0h+rect.left], 0
0x18027a16a  shl     r14d, 4
0x18027a16e  lea     rcx, [rsp+1C0h+Data]; void *
0x18027a173  xor     edx, edx; Val
0x18027a175  mov     r8d, 120h; Size
0x18027a17b  lea     r12d, [r14+20h]
0x18027a17f  call    memset_0
0x18027a184  cmp     esi, 10h
0x18027a187  ja      short loc_18027A204
0x18027a189  lea     rbx, [rsp+1C0h+Data]
0x18027a18e  mov     qword ptr [rbx+10h], 0
0x18027a196  lea     rdx, [rsp+1C0h+var_190]
0x18027a19b  mov     qword ptr [rbx+18h], 0
0x18027a1a3  mov     rcx, r15
0x18027a1a6  mov     [rbx+8], esi
0x18027a1a9  lea     rsi, [rbx+20h]
0x18027a1ad  mov     dword ptr [rbx], 20h ; ' '
0x18027a1b3  mov     dword ptr [rbx+4], 1
0x18027a1ba  mov     [rbx+0Ch], r14d
0x18027a1be  call    ?BeginIterator@CRegion@FastRegion@@QEBA?AVIterator@12@XZ; FastRegion::CRegion::BeginIterator(void)
0x18027a1c3  mov     rcx, [rsp+1C0h+var_180]
0x18027a1c8  cmp     rcx, [rsp+1C0h+var_188]
0x18027a1cd  jnb     short loc_18027A231
0x18027a1cf  mov     eax, [rcx]
0x18027a1d1  mov     [rsi+4], eax
0x18027a1d4  mov     eax, [rcx+8]
0x18027a1d7  mov     rcx, [rsp+1C0h+var_178]; this
0x18027a1dc  mov     [rsi+0Ch], eax
0x18027a1df  mov     eax, [rsp+1C0h+var_170]
0x18027a1e3  add     eax, eax
0x18027a1e5  movsxd  rdx, eax
0x18027a1e8  mov     eax, [rcx+rdx*4]
0x18027a1eb  mov     [rsi], eax
0x18027a1ed  mov     eax, [rcx+rdx*4+4]
0x18027a1f1  lea     rdx, [rsp+1C0h+var_190]; struct FastRegion::CRegion::Iterator *
0x18027a1f6  mov     [rsi+8], eax
0x18027a1f9  add     rsi, 10h
0x18027a1fd  call    ?StepIterator@CRgnData@Internal@FastRegion@@QEBAXPEAVIterator@CRegion@3@@Z; FastRegion::Internal::CRgnData::StepIterator(FastRegion::CRegion::Iterator *)
0x18027a202  jmp     short loc_18027A1C3
0x18027a204  mov     ecx, r12d; size
0x18027a207  call    MIDL_user_allocate
0x18027a20c  mov     qword ptr [rsp+1C0h+rect.left], rax
0x18027a211  mov     rbx, rax
0x18027a214  test    rax, rax
0x18027a217  jnz     loc_18027A18E
0x18027a21d  mov     [rsp+1C0h+var_198], rax
0x18027a222  mov     ebx, 8007000Eh
0x18027a227  mov     [rsp+1C0h+var_1A0], 61h ; 'a'
0x18027a22f  jmp     short loc_18027A291
0x18027a231  xor     ecx, ecx; dwErrCode
0x18027a233  call    cs:__imp_SetLastError
0x18027a239  mov     r8, rbx; lpData
0x18027a23c  mov     edx, r12d; nCount
0x18027a23f  xor     ecx, ecx; lpx
0x18027a241  call    cs:__imp_ExtCreateRegion
0x18027a247  mov     rsi, rax
0x18027a24a  test    rax, rax
0x18027a24d  jz      short loc_18027A261
0x18027a24f  lea     rcx, [rsp+1C0h+rect]
0x18027a254  call    ??1?$unique_ptr@$$BY0A@U?$aligned_storage_for@UEffectInput@@@detail@@U?$default_delete@$$BY0A@U?$aligned_storage_for@UEffectInput@@@detail@@@std@@@std@@QEAA@XZ; std::unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>::~unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>(void)
0x18027a259  xor     ebx, ebx
0x18027a25b  mov     [r13+0], rsi
0x18027a25f  jmp     short loc_18027A2AB
0x18027a261  call    cs:__imp_GetLastError
0x18027a267  mov     ebx, eax
0x18027a269  test    eax, eax
0x18027a26b  jle     short loc_18027A276
0x18027a26d  movzx   ebx, ax
0x18027a270  or      ebx, 80070000h
0x18027a276  test    ebx, ebx
0x18027a278  mov     [rsp+1C0h+var_198], 0; void *
0x18027a281  mov     eax, 88980003h
0x18027a286  mov     [rsp+1C0h+var_1A0], 7Dh ; '}'; unsigned int
0x18027a28e  cmovns  ebx, eax
0x18027a291  xor     edx, edx; int *
0x18027a293  mov     r9d, ebx; int
0x18027a296  xor     r8d, r8d; unsigned int
0x18027a299  lea     ecx, [rdx+14h]; unsigned int
0x18027a29c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18027a2a1  lea     rcx, [rsp+1C0h+rect]
0x18027a2a6  call    ??1?$unique_ptr@$$BY0A@U?$aligned_storage_for@UEffectInput@@@detail@@U?$default_delete@$$BY0A@U?$aligned_storage_for@UEffectInput@@@detail@@@std@@@std@@QEAA@XZ; std::unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>::~unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>(void)
0x18027a2ab  mov     eax, ebx
0x18027a2ad  mov     rcx, [rbp+0C0h+var_30]
0x18027a2b4  xor     rcx, rsp; StackCookie
0x18027a2b7  call    __security_check_cookie
0x18027a2bc  lea     r11, [rsp+1C0h+var_20]
0x18027a2c4  mov     rbx, [r11+40h]
0x18027a2c8  mov     rsi, [r11+48h]
0x18027a2cc  mov     rsp, r11
0x18027a2cf  pop     r15
0x18027a2d1  pop     r14
0x18027a2d3  pop     r13
0x18027a2d5  pop     r12
0x18027a2d7  pop     rbp
0x18027a2d8  retn
```
