# CAppList::ProcessPolicy(void)

- ea: `0x18000ac90`
- end: `0x18000aeae`
- name: `?ProcessPolicy@CAppList@@QEAAKXZ`
- size: `542`
- prototype: `__int64 __fastcall(CAppList *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b7e8`
- `0x180011ac0`

## callees

- `0x180007410`
- `0x180007918`
- `0x1800079b0`
- `0x18000ac90`
- `0x18000b0a8`
- `0x180012690`
- `0x18001b1a0`
- `0x18001b4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000accd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ace5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000accd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ace5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae5b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000ad37`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000adfe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000ae9b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000ad37`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000adfe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000ae9b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000acbb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000ae31`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000acbb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000ae31`

## pseudocode

```c
__int64 __fastcall CAppList::ProcessPolicy(CAppList *this)
{
  __int64 v2; // rcx
  DWORD LastError; // eax
  DWORD v4; // edi
  __int64 v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  DWORD v10; // esi
  unsigned int i; // ebp
  CAppList *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // eax
  _DWORD *v15; // rax
  __int64 v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx

  v2 = *((_QWORD *)this + 10);
  if ( *(_DWORD *)(v2 + 396) != 1 && *(_DWORD *)(v2 + 296) && !ImpersonateLoggedOnUser(*(HANDLE *)(v2 + 264)) )
  {
    if ( *(_DWORD *)&gDebugLevel )
    {
      LastError = GetLastError();
      _DebugMsg(2, 0xBC4u, LastError);
    }
    v4 = GetLastError();
    if ( v4 )
    {
      v5 = *((_QWORD *)this + 10);
      goto LABEL_9;
    }
  }
  v6 = CAppList::SetAppActions(this);
  v5 = *((_QWORD *)this + 10);
  v4 = v6;
  if ( v6 )
  {
LABEL_9:
    CEventsBase::Report((CEventsBase *)(v5 + 344), 0x6Eu, 0, 0);
    v7 = *((_QWORD *)this + 10);
    if ( *(_DWORD *)(v7 + 396) != 1 && *(_DWORD *)(v7 + 296) )
      RevertToSelf();
    v8 = *((_QWORD *)this + 10);
    if ( !*(_DWORD *)(v8 + 488) )
      *(_DWORD *)(v8 + 488) = v4;
    return v4;
  }
  if ( *(_DWORD *)(v5 + 396) == 1 )
    return 0;
  v10 = 0;
  for ( i = 0; i <= 2; ++i )
  {
    v12 = (CAppList *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 9) = *((_QWORD *)this + 8);
    for ( *((_QWORD *)this + 8) = v12; ; *((_QWORD *)this + 8) = v12 )
    {
      if ( v12 == (CAppList *)((char *)this + 48) )
        v12 = 0;
      if ( !v12 )
        break;
      if ( !i )
      {
        v14 = CAppInfo::ProcessUnapplyActions(v12);
        goto LABEL_29;
      }
      if ( i == 1 )
      {
        v14 = CAppInfo::ProcessApplyActions(v12);
        goto LABEL_29;
      }
      v13 = *((_QWORD *)this + 11);
      if ( *(_DWORD *)(v13 + 32) && *(_DWORD *)(v13 + 36) == 2 )
      {
        v14 = CAppInfo::ProcessTransformConflicts(v12);
LABEL_29:
        v4 = v14;
      }
      if ( !v10 && v4 )
        v10 = v4;
      v15 = (_DWORD *)*((_QWORD *)this + 10);
      if ( !v15[75] && v10 && v10 != 1274 )
      {
        if ( v15[99] != 1 && v15[74] )
          RevertToSelf();
        ForceSynchronousRefresh(*(void **)(*((_QWORD *)this + 10) + 264LL));
        v16 = *((_QWORD *)this + 10);
        if ( *(_DWORD *)(v16 + 396) != 1 && *(_DWORD *)(v16 + 296) && !ImpersonateLoggedOnUser(*(HANDLE *)(v16 + 264)) )
        {
          if ( *(_DWORD *)&gDebugLevel )
          {
            v17 = GetLastError();
            _DebugMsg(2, 0xBC4u, v17);
          }
          GetLastError();
        }
      }
      v12 = *(CAppList **)(*((_QWORD *)this + 8) + 8LL);
    }
    *((_QWORD *)this + 8) = *((_QWORD *)this + 9);
  }
  v18 = *((_QWORD *)this + 10);
  if ( *(_DWORD *)(v18 + 396) != 1 && *(_DWORD *)(v18 + 296) )
    RevertToSelf();
  return v10;
}

```

## disassembly

```asm
0x18000ac90  push    rbx
0x18000ac92  push    rbp
0x18000ac93  push    rsi
0x18000ac94  push    rdi
0x18000ac95  push    r14
0x18000ac97  sub     rsp, 20h
0x18000ac9b  mov     rbx, rcx
0x18000ac9e  mov     rcx, [rcx+50h]
0x18000aca2  cmp     dword ptr [rcx+18Ch], 1
0x18000aca9  jz      short loc_18000ACF7
0x18000acab  cmp     dword ptr [rcx+128h], 0
0x18000acb2  jz      short loc_18000ACF7
0x18000acb4  mov     rcx, [rcx+108h]; hToken
0x18000acbb  call    cs:__imp_ImpersonateLoggedOnUser
0x18000acc1  test    eax, eax
0x18000acc3  jnz     short loc_18000ACF7
0x18000acc5  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x18000accb  jz      short loc_18000ACE5
0x18000accd  call    cs:__imp_GetLastError
0x18000acd3  mov     edx, 0BC4h; unsigned int
0x18000acd8  mov     ecx, 2; unsigned int
0x18000acdd  mov     r8d, eax
0x18000ace0  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000ace5  call    cs:__imp_GetLastError
0x18000aceb  mov     edi, eax
0x18000aced  test    eax, eax
0x18000acef  jz      short loc_18000ACF7
0x18000acf1  mov     rcx, [rbx+50h]
0x18000acf5  jmp     short loc_18000AD09
0x18000acf7  mov     rcx, rbx; this
0x18000acfa  call    ?SetAppActions@CAppList@@QEAAKXZ; CAppList::SetAppActions(void)
0x18000acff  mov     rcx, [rbx+50h]
0x18000ad03  mov     edi, eax
0x18000ad05  test    eax, eax
0x18000ad07  jz      short loc_18000AD57
0x18000ad09  xor     eax, eax
0x18000ad0b  add     rcx, 158h; this
0x18000ad12  movzx   r9d, ax; unsigned __int16
0x18000ad16  xor     r8d, r8d; int
0x18000ad19  lea     edx, [rax+6Eh]; unsigned int
0x18000ad1c  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18000ad21  mov     rax, [rbx+50h]
0x18000ad25  cmp     dword ptr [rax+18Ch], 1
0x18000ad2c  jz      short loc_18000AD3D
0x18000ad2e  cmp     dword ptr [rax+128h], 0
0x18000ad35  jz      short loc_18000AD3D
0x18000ad37  call    cs:__imp_RevertToSelf
0x18000ad3d  mov     rax, [rbx+50h]
0x18000ad41  cmp     dword ptr [rax+1E8h], 0
0x18000ad48  jnz     short loc_18000AD50
0x18000ad4a  mov     [rax+1E8h], edi
0x18000ad50  mov     eax, edi
0x18000ad52  jmp     loc_18000AEA3
0x18000ad57  cmp     dword ptr [rcx+18Ch], 1
0x18000ad5e  jnz     short loc_18000AD67
0x18000ad60  xor     eax, eax
0x18000ad62  jmp     loc_18000AEA3
0x18000ad67  xor     esi, esi
0x18000ad69  lea     r14, [rbx+30h]
0x18000ad6d  xor     ebp, ebp
0x18000ad6f  mov     rax, [rbx+40h]
0x18000ad73  mov     rcx, [rbx+38h]
0x18000ad77  mov     [rbx+48h], rax
0x18000ad7b  mov     [rbx+40h], rcx
0x18000ad7f  xor     eax, eax
0x18000ad81  cmp     rcx, r14
0x18000ad84  cmovz   rcx, rax; this
0x18000ad88  test    rcx, rcx
0x18000ad8b  jz      loc_18000AE72
0x18000ad91  mov     eax, ebp
0x18000ad93  test    ebp, ebp
0x18000ad95  jz      short loc_18000ADBF
0x18000ad97  sub     eax, 1
0x18000ad9a  jz      short loc_18000ADB8
0x18000ad9c  cmp     eax, 1
0x18000ad9f  jnz     short loc_18000ADC6
0x18000ada1  mov     rax, [rbx+58h]
0x18000ada5  cmp     dword ptr [rax+20h], 0
0x18000ada9  jz      short loc_18000ADC6
0x18000adab  cmp     dword ptr [rax+24h], 2
0x18000adaf  jnz     short loc_18000ADC6
0x18000adb1  call    ?ProcessTransformConflicts@CAppInfo@@QEAAKXZ; CAppInfo::ProcessTransformConflicts(void)
0x18000adb6  jmp     short loc_18000ADC4
0x18000adb8  call    ?ProcessApplyActions@CAppInfo@@QEAAKXZ; CAppInfo::ProcessApplyActions(void)
0x18000adbd  jmp     short loc_18000ADC4
0x18000adbf  call    ?ProcessUnapplyActions@CAppInfo@@QEAAKXZ; CAppInfo::ProcessUnapplyActions(void)
0x18000adc4  mov     edi, eax
0x18000adc6  test    esi, esi
0x18000adc8  jnz     short loc_18000ADCF
0x18000adca  test    edi, edi
0x18000adcc  cmovnz  esi, edi
0x18000adcf  mov     rax, [rbx+50h]
0x18000add3  cmp     dword ptr [rax+12Ch], 0
0x18000adda  jnz     loc_18000AE61
0x18000ade0  test    esi, esi
0x18000ade2  jz      short loc_18000AE61
0x18000ade4  cmp     esi, 4FAh
0x18000adea  jz      short loc_18000AE61
0x18000adec  cmp     dword ptr [rax+18Ch], 1
0x18000adf3  jz      short loc_18000AE04
0x18000adf5  cmp     dword ptr [rax+128h], 0
0x18000adfc  jz      short loc_18000AE04
0x18000adfe  call    cs:__imp_RevertToSelf
0x18000ae04  mov     rcx, [rbx+50h]
0x18000ae08  mov     rcx, [rcx+108h]; void *
0x18000ae0f  call    ?ForceSynchronousRefresh@@YAKPEAX@Z; ForceSynchronousRefresh(void *)
0x18000ae14  mov     rcx, [rbx+50h]
0x18000ae18  cmp     dword ptr [rcx+18Ch], 1
0x18000ae1f  jz      short loc_18000AE61
0x18000ae21  cmp     dword ptr [rcx+128h], 0
0x18000ae28  jz      short loc_18000AE61
0x18000ae2a  mov     rcx, [rcx+108h]; hToken
0x18000ae31  call    cs:__imp_ImpersonateLoggedOnUser
0x18000ae37  test    eax, eax
0x18000ae39  jnz     short loc_18000AE61
0x18000ae3b  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x18000ae41  jz      short loc_18000AE5B
0x18000ae43  call    cs:__imp_GetLastError
0x18000ae49  mov     edx, 0BC4h; unsigned int
0x18000ae4e  mov     ecx, 2; unsigned int
0x18000ae53  mov     r8d, eax
0x18000ae56  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000ae5b  call    cs:__imp_GetLastError
0x18000ae61  mov     rax, [r14+10h]
0x18000ae65  mov     rcx, [rax+8]
0x18000ae69  mov     [r14+10h], rcx
0x18000ae6d  jmp     loc_18000AD7F
0x18000ae72  mov     rax, [rbx+48h]
0x18000ae76  inc     ebp
0x18000ae78  mov     [rbx+40h], rax
0x18000ae7c  cmp     ebp, 2
0x18000ae7f  jbe     loc_18000AD6F
0x18000ae85  mov     rcx, [rbx+50h]
0x18000ae89  cmp     dword ptr [rcx+18Ch], 1
0x18000ae90  jz      short loc_18000AEA1
0x18000ae92  cmp     dword ptr [rcx+128h], 0
0x18000ae99  jz      short loc_18000AEA1
0x18000ae9b  call    cs:__imp_RevertToSelf
0x18000aea1  mov     eax, esi
0x18000aea3  add     rsp, 20h
0x18000aea7  pop     r14
0x18000aea9  pop     rdi
0x18000aeaa  pop     rsi
0x18000aeab  pop     rbp
0x18000aeac  pop     rbx
0x18000aead  retn
```
