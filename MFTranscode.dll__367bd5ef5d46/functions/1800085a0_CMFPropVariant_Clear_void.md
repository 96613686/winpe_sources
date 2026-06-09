# CMFPropVariant::Clear(void)

- ea: `0x1800085a0`
- end: `0x18000877d`
- name: `?Clear@CMFPropVariant@@QEAAJXZ`
- size: `477`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `21`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008050`
- `0x18000f07c`
- `0x18000f4a0`
- `0x180014e14`
- `0x180015fe8`
- `0x1800467d4`
- `0x180046fb0`
- `0x180047880`
- `0x180047a10`
- `0x180048310`
- `0x180048490`
- `0x1800488b0`
- `0x180048db8`
- `0x1800497a4`
- `0x180049a9c`
- `0x18004a398`
- `0x18004b900`
- `0x18004d62c`
- `0x18004dafc`
- `0x180055d04`
- `0x180057fe4`

## callees

- `0x1800085a0`
- `0x18000f07c`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180058338`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000863d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000874c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000863d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000874c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800085ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800085ec`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Clear(PROPVARIANT *pvar)
{
  unsigned int v2; // ebx
  int vt; // ecx
  __int64 result; // rax
  __int64 v5; // rdx
  unsigned int k; // ebp
  BYTE *v7; // rdi
  __int64 j; // rdi
  __int64 v9; // rcx
  unsigned int i; // edi
  struct tagPROPVARIANT v11; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  vt = pvar->vt;
  result = 0;
  if ( (_WORD)vt )
  {
    switch ( vt )
    {
      case 4108:
        if ( !pvar->bstrblobVal.pData )
        {
          v2 = -2147467261;
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_25;
          v5 = 11;
          goto LABEL_24;
        }
        for ( i = 0; pvar->lVal > i; ++i )
        {
          memset(&v11, 0, sizeof(v11));
          CMFPropVariant::GetElementDataAsVariant((CMFPropVariant *)pvar, i, &v11);
          CMFPropVariant::~CMFPropVariant((CMFPropVariant *)&v11);
        }
        break;
      case 4109:
        if ( !pvar->bstrblobVal.pData )
        {
          v2 = -2147467261;
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_25;
          v5 = 12;
          goto LABEL_24;
        }
        for ( j = 0; pvar->lVal > (unsigned int)j; j = (unsigned int)(j + 1) )
        {
          v9 = *(_QWORD *)&pvar->bstrblobVal.pData[8 * j];
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        break;
      case 4161:
        if ( !pvar->bstrblobVal.pData )
        {
          v2 = -2147467261;
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_25;
          v5 = 10;
LABEL_24:
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v5,
            WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
            pvar,
            -2147467261);
          goto LABEL_25;
        }
        for ( k = 0; pvar->lVal > k; *((_QWORD *)v7 + 1) = 0 )
        {
          v7 = &pvar->bstrblobVal.pData[16 * k];
          CoTaskMemFree(*((LPVOID *)v7 + 1));
          ++k;
        }
        CoTaskMemFree(pvar->bstrblobVal.pData);
LABEL_30:
        *(_OWORD *)&pvar->vt = 0;
        pvar->bstrblobVal.pData = 0;
        return v2;
      default:
        v2 = PropVariantClear(pvar);
        if ( (v2 & 0x80000000) == 0 )
          return v2;
LABEL_25:
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvar, v2);
        return v2;
    }
    CoTaskMemFree(pvar->bstrblobVal.pData);
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x1800085a0  mov     [rsp+arg_18], rbx
0x1800085a5  push    rsi
0x1800085a6  sub     rsp, 50h
0x1800085aa  mov     rax, cs:__security_cookie
0x1800085b1  xor     rax, rsp
0x1800085b4  mov     [rsp+58h+var_10], rax
0x1800085b9  mov     rsi, rcx
0x1800085bc  xor     ebx, ebx
0x1800085be  movzx   ecx, word ptr [rcx]
0x1800085c1  xor     eax, eax
0x1800085c3  cmp     ax, cx
0x1800085c6  jz      loc_180008765
0x1800085cc  mov     edx, ecx
0x1800085ce  mov     [rsp+58h+arg_10], rdi
0x1800085d3  sub     edx, 100Ch
0x1800085d9  jz      loc_1800086AD
0x1800085df  sub     edx, 1
0x1800085e2  jz      short loc_180008662
0x1800085e4  cmp     edx, 34h ; '4'
0x1800085e7  jz      short loc_180008601
0x1800085e9  mov     rcx, rsi; pvar
0x1800085ec  call    cs:__imp_PropVariantClear
0x1800085f2  mov     ebx, eax
0x1800085f4  test    eax, eax
0x1800085f6  js      loc_1800086E4
0x1800085fc  jmp     loc_18000875E
0x180008601  cmp     [rsi+10h], rax
0x180008605  jnz     short loc_180008623
0x180008607  mov     ebx, 80004003h
0x18000860c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180008611  cmp     al, 1
0x180008613  jb      loc_1800086E4
0x180008619  mov     edx, 0Ah
0x18000861e  jmp     loc_1800086C6
0x180008623  mov     [rsp+58h+arg_8], rbp
0x180008628  xor     ebp, ebp
0x18000862a  cmp     [rsi+8], eax
0x18000862d  jbe     short loc_18000864E
0x18000862f  mov     edi, ebp
0x180008631  shl     rdi, 4
0x180008635  add     rdi, [rsi+10h]
0x180008639  mov     rcx, [rdi+8]; pv
0x18000863d  call    cs:__imp_CoTaskMemFree
0x180008643  inc     ebp
0x180008645  mov     [rdi+8], rbx
0x180008649  cmp     [rsi+8], ebp
0x18000864c  ja      short loc_18000862F
0x18000864e  mov     rcx, [rsi+10h]; pv
0x180008652  call    cs:__imp_CoTaskMemFree
0x180008658  mov     rbp, [rsp+58h+arg_8]
0x18000865d  jmp     loc_180008752
0x180008662  cmp     [rsi+10h], rax
0x180008666  jnz     short loc_18000867D
0x180008668  mov     ebx, 80004003h
0x18000866d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180008672  cmp     al, 1
0x180008674  jb      short loc_1800086E4
0x180008676  mov     edx, 0Ch
0x18000867b  jmp     short loc_1800086C6
0x18000867d  xor     edi, edi
0x18000867f  cmp     [rsi+8], eax
0x180008682  jbe     loc_180008748
0x180008688  mov     rax, [rsi+10h]
0x18000868c  mov     rcx, [rax+rdi*8]
0x180008690  test    rcx, rcx
0x180008693  jz      short loc_1800086A1
0x180008695  mov     rax, [rcx]
0x180008698  mov     rax, [rax+10h]
0x18000869c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a1  inc     edi
0x1800086a3  cmp     [rsi+8], edi
0x1800086a6  ja      short loc_180008688
0x1800086a8  jmp     loc_180008748
0x1800086ad  cmp     [rsi+10h], rax
0x1800086b1  jnz     short loc_180008712
0x1800086b3  mov     ebx, 80004003h
0x1800086b8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800086bd  cmp     al, 1
0x1800086bf  jb      short loc_1800086E4
0x1800086c1  mov     edx, 0Bh
0x1800086c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086cd  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800086d4  mov     r9, rsi
0x1800086d7  mov     [rsp+58h+var_38], ebx
0x1800086db  mov     rcx, [rcx+10h]
0x1800086df  call    WPP_SF_qd
0x1800086e4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800086e9  cmp     al, 1
0x1800086eb  jb      short loc_18000875E
0x1800086ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086f4  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800086fb  mov     edx, 0Dh
0x180008700  mov     [rsp+58h+var_38], ebx
0x180008704  mov     r9, rsi
0x180008707  mov     rcx, [rcx+10h]
0x18000870b  call    WPP_SF_qd
0x180008710  jmp     short loc_18000875E
0x180008712  xor     edi, edi
0x180008714  cmp     [rsi+8], eax
0x180008717  jbe     short loc_180008748
0x180008719  xorps   xmm0, xmm0
0x18000871c  lea     r8, [rsp+58h+var_28]; struct tagPROPVARIANT *
0x180008721  xor     eax, eax
0x180008723  mov     edx, edi; unsigned int
0x180008725  mov     rcx, rsi; this
0x180008728  mov     qword ptr [rsp+58h+var_28+10h], rax
0x18000872d  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x180008732  call    ?GetElementDataAsVariant@CMFPropVariant@@IEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElementDataAsVariant(ulong,tagPROPVARIANT *)
0x180008737  lea     rcx, [rsp+58h+var_28]; this
0x18000873c  call    ??1CMFPropVariant@@QEAA@XZ; CMFPropVariant::~CMFPropVariant(void)
0x180008741  inc     edi
0x180008743  cmp     [rsi+8], edi
0x180008746  ja      short loc_180008719
0x180008748  mov     rcx, [rsi+10h]; pv
0x18000874c  call    cs:__imp_CoTaskMemFree
0x180008752  xorps   xmm0, xmm0
0x180008755  xor     eax, eax
0x180008757  movups  xmmword ptr [rsi], xmm0
0x18000875a  mov     [rsi+10h], rax
0x18000875e  mov     rdi, [rsp+58h+arg_10]
0x180008763  mov     eax, ebx
0x180008765  mov     rcx, [rsp+58h+var_10]
0x18000876a  xor     rcx, rsp; StackCookie
0x18000876d  call    __security_check_cookie
0x180008772  mov     rbx, [rsp+58h+arg_18]
0x180008777  add     rsp, 50h
0x18000877b  pop     rsi
0x18000877c  retn
```
