# CDbOperationManager::SetEseParametersHelper(unsigned __int64 *,CStringHashTable<int,CStringHashPolicy,CStringCompare> &,ushort const *,unsigned __int64)

- ea: `0x1800eb41c`
- end: `0x1800eb6c6`
- name: `?SetEseParametersHelper@CDbOperationManager@@CAJPEA_KAEAV?$CStringHashTable@HVCStringHashPolicy@@VCStringCompare@@@@PEBG_K@Z`
- size: `682`
- prototype: `__int64 __fastcall(JET_INSTANCE *pinstance)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800eb16c`

## callees

- `0x18001133c`
- `0x18001137c`
- `0x18007fbac`
- `0x1800d6154`
- `0x1800eb41c`
- `0x1800eb840`
- `0x1800eb9e8`
- `0x1800ebaf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800eb588`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800eb588`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eb569`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eb590`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eb569`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eb590`
- `KERNEL32!CompareStringOrdinal` at `0x1800eb533`
- `KERNEL32!CompareStringOrdinal` at `0x1800eb533`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eb4a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eb4a7`
- `SHLWAPI!SHStrDupW` at `0x1800eb47b`
- `SHLWAPI!SHStrDupW` at `0x1800eb47b`
- `ESENT!JetSetSystemParameterW` at `0x1800eb5cc`
- `ESENT!JetSetSystemParameterW` at `0x1800eb5cc`

## pseudocode

```c
__int64 __fastcall CDbOperationManager::SetEseParametersHelper(
        JET_INSTANCE *pinstance,
        __int64 a2,
        const WCHAR *a3,
        JET_API_PTR a4)
{
  __int64 v5; // rcx
  __int64 v10; // rdx
  HRESULT updated; // edi
  __int64 v12; // rdx
  int v13; // esi
  int v14; // edi
  wchar_t **v15; // rcx
  int v16; // ebp
  int v17; // eax
  int v18; // ecx
  unsigned int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  JET_ERR v23; // eax
  int v24; // edx
  int v25; // r8d
  const wchar_t *v26; // r9
  const wchar_t *v27; // r9
  LPWSTR ppwsz[9]; // [rsp+40h] [rbp-48h] BYREF
  wchar_t *EndPtr; // [rsp+98h] [rbp+10h] BYREF
  const WCHAR *v30; // [rsp+A0h] [rbp+18h] BYREF

  v30 = a3;
  v5 = *(_QWORD *)(a2 + 16);
  if ( v5
    && *(_DWORD *)CSimpleHashTable<unsigned short const *,int,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(
                    v5,
                    *(unsigned int *)(a2 + 4),
                    &v30) == 1 )
  {
    return 0;
  }
  LODWORD(EndPtr) = 1;
  ppwsz[0] = 0;
  updated = SHStrDupW(a3, ppwsz);
  if ( updated >= 0 )
  {
    updated = CSimpleHashTable<unsigned short const *,int,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                a2,
                v10,
                ppwsz,
                &EndPtr);
    if ( updated >= 0 )
    {
      v13 = 94;
      v14 = 0;
      while ( 1 )
      {
        v15 = &off_180147620;
        if ( v14 > v13 )
          goto LABEL_21;
        v16 = (v13 - v14) / 2 + v14;
        v17 = CompareStringOrdinal(a3, -1, (&off_180147620)[2 * v16], -1, 0);
        if ( v17 == 2 )
          break;
        if ( v17 != 1 )
          v14 = v16 + 1;
        v18 = v16 - 1;
        if ( v17 != 1 )
          v18 = v13;
        v13 = v18;
      }
      if ( v16 < 0 )
      {
LABEL_21:
        *(_DWORD *)_o__errno(v15, v12, 2) = 0;
        EndPtr = 0;
        v19 = wcstoul(a3, &EndPtr, 0);
        if ( *(_DWORD *)_o__errno(v21, v20, v22) || *EndPtr || EndPtr == a3 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids, a3);
          return (unsigned int)-2147024809;
        }
      }
      else
      {
        v19 = *((_DWORD *)&off_180147620 + 4 * v16 + 2);
      }
      v23 = JetSetSystemParameterW(pinstance, 0xFFFFFFFFFFFFFFFFuLL, v19, a4, 0);
      updated = ResultFromJetError(v23);
      if ( updated < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v27 = L"global";
          if ( pinstance )
            v27 = L"instance";
          WPP_SF_SSID(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, (_DWORD)v27, (__int64)a3, a4, updated);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v26 = L"global";
        if ( pinstance )
          v26 = L"instance";
        WPP_SF_SSI(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          (_DWORD)v26,
          (__int64)a3,
          a4);
      }
      return (unsigned int)updated;
    }
    CoTaskMemFree(ppwsz[0]);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      101,
      &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
      (unsigned int)updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800eb41c  mov     rax, rsp
0x1800eb41f  mov     [rax+8], rbx
0x1800eb423  mov     [rax+18h], r8
0x1800eb427  push    rbp
0x1800eb428  push    rsi
0x1800eb429  push    rdi
0x1800eb42a  push    r12
0x1800eb42c  push    r13
0x1800eb42e  push    r14
0x1800eb430  push    r15
0x1800eb432  sub     rsp, 50h
0x1800eb436  mov     r15, rcx
0x1800eb439  xor     r13d, r13d
0x1800eb43c  mov     rcx, [rdx+10h]
0x1800eb440  mov     r14, r9
0x1800eb443  mov     rbx, r8
0x1800eb446  mov     rsi, rdx
0x1800eb449  test    rcx, rcx
0x1800eb44c  jz      short loc_1800EB463
0x1800eb44e  mov     edx, [rdx+4]
0x1800eb451  lea     r8, [rax+18h]
0x1800eb455  call    ?s_LookupEntry@?$CSimpleHashTable@PEBGHVCStringHashPolicy@@VCStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@CAAEAVHashBucket@1@PEAV21@IAEBQEBG@Z; CSimpleHashTable<ushort const *,int,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(CSimpleHashTable<ushort const *,int,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::HashBucket *,uint,ushort const * const &)
0x1800eb45a  cmp     dword ptr [rax], 1
0x1800eb45d  jnz     short loc_1800EB463
0x1800eb45f  xor     eax, eax
0x1800eb461  jmp     short loc_1800EB4E0
0x1800eb463  lea     rdx, [rsp+88h+ppwsz]; ppwsz
0x1800eb468  mov     dword ptr [rsp+88h+EndPtr], 1
0x1800eb473  mov     rcx, rbx; psz
0x1800eb476  mov     [rsp+88h+ppwsz], r13
0x1800eb47b  call    cs:__imp_SHStrDupW
0x1800eb481  mov     edi, eax
0x1800eb483  test    eax, eax
0x1800eb485  js      short loc_1800EB4AD
0x1800eb487  lea     r9, [rsp+88h+EndPtr]
0x1800eb48f  mov     rcx, rsi
0x1800eb492  lea     r8, [rsp+88h+ppwsz]
0x1800eb497  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGHVCStringHashPolicy@@VCStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBHPEAH@Z; CSimpleHashTable<ushort const *,int,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,int const &,int *)
0x1800eb49c  mov     edi, eax
0x1800eb49e  test    eax, eax
0x1800eb4a0  jns     short loc_1800EB4F8
0x1800eb4a2  mov     rcx, [rsp+88h+ppwsz]; pv
0x1800eb4a7  call    cs:__imp_CoTaskMemFree
0x1800eb4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb4b4  lea     rax, WPP_GLOBAL_Control
0x1800eb4bb  cmp     rcx, rax
0x1800eb4be  jz      short loc_1800EB4DE
0x1800eb4c0  test    byte ptr [rcx+1Ch], 1
0x1800eb4c4  jz      short loc_1800EB4DE
0x1800eb4c6  mov     rcx, [rcx+10h]
0x1800eb4ca  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800eb4d1  mov     edx, 65h ; 'e'
0x1800eb4d6  mov     r9d, edi
0x1800eb4d9  call    WPP_SF_d
0x1800eb4de  mov     eax, edi
0x1800eb4e0  mov     rbx, [rsp+88h+arg_0]
0x1800eb4e8  add     rsp, 50h
0x1800eb4ec  pop     r15
0x1800eb4ee  pop     r14
0x1800eb4f0  pop     r13
0x1800eb4f2  pop     r12
0x1800eb4f4  pop     rdi
0x1800eb4f5  pop     rsi
0x1800eb4f6  pop     rbp
0x1800eb4f7  retn
0x1800eb4f8  mov     esi, 5Eh ; '^'
0x1800eb4fd  mov     edi, r13d
0x1800eb500  lea     r8d, [rsi-5Ch]
0x1800eb504  lea     rcx, off_180147620; "JET_paramAccessDeniedRetryPeriod"
0x1800eb50b  cmp     edi, esi
0x1800eb50d  jg      short loc_1800EB569
0x1800eb50f  mov     eax, esi
0x1800eb511  mov     [rsp+88h+bIgnoreCase], r13d; bIgnoreCase
0x1800eb516  sub     eax, edi
0x1800eb518  or      r9d, 0FFFFFFFFh; cchCount2
0x1800eb51c  cdq
0x1800eb51d  idiv    r8d
0x1800eb520  or      edx, r9d; cchCount1
0x1800eb523  lea     ebp, [rax+rdi]
0x1800eb526  movsxd  r12, ebp
0x1800eb529  add     r12, r12
0x1800eb52c  mov     r8, [rcx+r12*8]; lpString2
0x1800eb530  mov     rcx, rbx; lpString1
0x1800eb533  call    cs:__imp_CompareStringOrdinal
0x1800eb539  mov     r8d, 2
0x1800eb53f  cmp     eax, r8d
0x1800eb542  jz      short loc_1800EB557
0x1800eb544  cmp     eax, 1
0x1800eb547  lea     ecx, [rbp+1]
0x1800eb54a  cmovnz  edi, ecx
0x1800eb54d  lea     ecx, [rbp-1]
0x1800eb550  cmovnz  ecx, esi
0x1800eb553  mov     esi, ecx
0x1800eb555  jmp     short loc_1800EB504
0x1800eb557  test    ebp, ebp
0x1800eb559  js      short loc_1800EB569
0x1800eb55b  lea     rdi, off_180147620; "JET_paramAccessDeniedRetryPeriod"
0x1800eb562  mov     edi, [rdi+r12*8+8]
0x1800eb567  jmp     short loc_1800EB5BA
0x1800eb569  call    cs:__imp__o__errno
0x1800eb56f  xor     r8d, r8d; Radix
0x1800eb572  lea     rdx, [rsp+88h+EndPtr]; EndPtr
0x1800eb57a  mov     rcx, rbx; String
0x1800eb57d  mov     [rax], r13d
0x1800eb580  mov     [rsp+88h+EndPtr], r13
0x1800eb588  call    cs:__imp_wcstoul
0x1800eb58e  mov     edi, eax
0x1800eb590  call    cs:__imp__o__errno
0x1800eb596  cmp     [rax], r13d
0x1800eb599  jnz     loc_1800EB68B
0x1800eb59f  mov     rax, [rsp+88h+EndPtr]
0x1800eb5a7  cmp     [rax], r13w
0x1800eb5ab  jnz     loc_1800EB68B
0x1800eb5b1  cmp     rax, rbx
0x1800eb5b4  jz      loc_1800EB68B
0x1800eb5ba  mov     r9, r14; lParam
0x1800eb5bd  mov     qword ptr [rsp+88h+bIgnoreCase], r13; szParam
0x1800eb5c2  mov     r8d, edi; paramid
0x1800eb5c5  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x1800eb5c9  mov     rcx, r15; pinstance
0x1800eb5cc  call    cs:__imp_JetSetSystemParameterW
0x1800eb5d2  mov     ecx, eax; int
0x1800eb5d4  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800eb5d9  mov     edi, eax
0x1800eb5db  test    eax, eax
0x1800eb5dd  js      short loc_1800EB639
0x1800eb5df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb5e6  lea     rax, WPP_GLOBAL_Control
0x1800eb5ed  cmp     rcx, rax
0x1800eb5f0  jz      loc_1800EB4DE
0x1800eb5f6  test    byte ptr [rcx+1Ch], 4
0x1800eb5fa  jz      loc_1800EB4DE
0x1800eb600  mov     rcx, [rcx+10h]
0x1800eb604  lea     rax, aInstance_3; "instance"
0x1800eb60b  test    r15, r15
0x1800eb60e  mov     [rsp+88h+var_60], r14
0x1800eb613  lea     r9, aGlobal_4; "global"
0x1800eb61a  mov     qword ptr [rsp+88h+bIgnoreCase], rbx
0x1800eb61f  cmovnz  r9, rax
0x1800eb623  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800eb62a  mov     edx, 67h ; 'g'
0x1800eb62f  call    WPP_SF_SSI
0x1800eb634  jmp     loc_1800EB4DE
0x1800eb639  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb640  lea     rax, WPP_GLOBAL_Control
0x1800eb647  cmp     rcx, rax
0x1800eb64a  jz      loc_1800EB4DE
0x1800eb650  test    byte ptr [rcx+1Ch], 1
0x1800eb654  jz      loc_1800EB4DE
0x1800eb65a  mov     rcx, [rcx+10h]
0x1800eb65e  lea     rax, aInstance_3; "instance"
0x1800eb665  test    r15, r15
0x1800eb668  mov     [rsp+88h+var_58], edi
0x1800eb66c  lea     r9, aGlobal_4; "global"
0x1800eb673  mov     [rsp+88h+var_60], r14
0x1800eb678  cmovnz  r9, rax
0x1800eb67c  mov     qword ptr [rsp+88h+bIgnoreCase], rbx
0x1800eb681  call    WPP_SF_SSID
0x1800eb686  jmp     loc_1800EB4DE
0x1800eb68b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb692  lea     rax, WPP_GLOBAL_Control
0x1800eb699  cmp     rcx, rax
0x1800eb69c  jz      short loc_1800EB6BC
0x1800eb69e  test    byte ptr [rcx+1Ch], 1
0x1800eb6a2  jz      short loc_1800EB6BC
0x1800eb6a4  mov     rcx, [rcx+10h]
0x1800eb6a8  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800eb6af  mov     edx, 66h ; 'f'
0x1800eb6b4  mov     r9, rbx
0x1800eb6b7  call    WPP_SF_S
0x1800eb6bc  mov     edi, 80070057h
0x1800eb6c1  jmp     loc_1800EB4DE
```
