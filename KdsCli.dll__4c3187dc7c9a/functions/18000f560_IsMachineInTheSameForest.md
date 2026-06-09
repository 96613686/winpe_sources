# IsMachineInTheSameForest

- ea: `0x18000f560`
- end: `0x18000f62e`
- name: `IsMachineInTheSameForest`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ecb0`

## callees

- `0x18000f560`
- `0x18000fe30`
- `0x18001a450`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18000f58f`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18000f58f`
- `ntdll!RtlNtStatusToDosError` at `0x18000f59b`
- `ntdll!RtlNtStatusToDosError` at `0x18000f59b`

## string_xrefs

- `0x18000f5bf`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall IsMachineInTheSameForest(char *a1, int *a2)
{
  int v4; // edi
  NTSTATUS v5; // eax
  signed int v6; // eax
  unsigned int v7; // ebx
  char v8; // r9
  char v9; // cl
  int CachedMachineDomainInfo; // eax
  char *v11; // rcx
  int v12; // eax
  int v13; // edx
  __int64 result; // rax
  int v15; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int16 *v16; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int16 *v17; // [rsp+58h] [rbp+20h] BYREF

  v16 = 0;
  v15 = 0;
  v4 = 1;
  v5 = LsaLookupUserAccountType(0, &v15);
  if ( v5 < 0 )
  {
    v6 = RtlNtStatusToDosError(v5);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v8 = 119;
    v9 = v7;
    goto LABEL_5;
  }
  if ( v15 == 5 )
  {
    v7 = 0;
    v4 = 0;
    goto LABEL_15;
  }
  CachedMachineDomainInfo = GetCachedMachineDomainInfo(&v17, &v16);
  v7 = CachedMachineDomainInfo;
  if ( CachedMachineDomainInfo < 0 )
  {
    v8 = -121;
    v9 = CachedMachineDomainInfo;
LABEL_5:
    SidKeyDebugTraceError(v9, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", v8);
    goto LABEL_15;
  }
  v11 = (char *)((char *)v16 - a1);
  do
  {
    v12 = *(unsigned __int16 *)&v11[(_QWORD)a1];
    v13 = *(unsigned __int16 *)a1 - v12;
    if ( v13 )
      break;
    a1 += 2;
  }
  while ( v12 );
  if ( v13 )
    v4 = 0;
LABEL_15:
  result = v7;
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x18000f560  mov     rax, rsp
0x18000f563  mov     [rax+8], rbx
0x18000f567  push    rsi
0x18000f568  push    rdi
0x18000f569  push    r14
0x18000f56b  sub     rsp, 20h
0x18000f56f  mov     r14, rdx
0x18000f572  mov     qword ptr [rax+18h], 0
0x18000f57a  mov     rsi, rcx
0x18000f57d  mov     dword ptr [rax+10h], 0
0x18000f584  lea     rdx, [rax+10h]
0x18000f588  xor     ecx, ecx
0x18000f58a  mov     edi, 1
0x18000f58f  call    cs:__imp_LsaLookupUserAccountType
0x18000f595  test    eax, eax
0x18000f597  jns     short loc_18000F5CD
0x18000f599  mov     ecx, eax; Status
0x18000f59b  call    cs:__imp_RtlNtStatusToDosError
0x18000f5a1  mov     ebx, eax
0x18000f5a3  test    eax, eax
0x18000f5a5  jle     short loc_18000F5B0
0x18000f5a7  movzx   ebx, ax
0x18000f5aa  or      ebx, 80070000h
0x18000f5b0  mov     r9d, 477h; unsigned int
0x18000f5b6  mov     ecx, ebx; unsigned int
0x18000f5b8  lea     rdx, aHr; "hr"
0x18000f5bf  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f5c6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f5cb  jmp     short loc_18000F61B
0x18000f5cd  cmp     [rsp+38h+arg_8], 5
0x18000f5d2  jnz     short loc_18000F5DA
0x18000f5d4  xor     ebx, ebx
0x18000f5d6  xor     edi, edi
0x18000f5d8  jmp     short loc_18000F61B
0x18000f5da  lea     rdx, [rsp+38h+arg_10]; unsigned __int16 **
0x18000f5df  lea     rcx, [rsp+38h+arg_18]; unsigned __int16 **
0x18000f5e4  call    ?GetCachedMachineDomainInfo@@YAJPEAPEAG0@Z; GetCachedMachineDomainInfo(ushort * *,ushort * *)
0x18000f5e9  mov     ebx, eax
0x18000f5eb  test    eax, eax
0x18000f5ed  jns     short loc_18000F5F9
0x18000f5ef  mov     r9d, 487h
0x18000f5f5  mov     ecx, eax
0x18000f5f7  jmp     short loc_18000F5B8
0x18000f5f9  mov     rcx, [rsp+38h+arg_10]
0x18000f5fe  sub     rcx, rsi
0x18000f601  movzx   edx, word ptr [rsi]
0x18000f604  movzx   eax, word ptr [rsi+rcx]
0x18000f608  sub     edx, eax
0x18000f60a  jnz     short loc_18000F614
0x18000f60c  add     rsi, 2
0x18000f610  test    eax, eax
0x18000f612  jnz     short loc_18000F601
0x18000f614  xor     eax, eax
0x18000f616  test    edx, edx
0x18000f618  cmovnz  edi, eax
0x18000f61b  mov     eax, ebx
0x18000f61d  mov     [r14], edi
0x18000f620  mov     rbx, [rsp+38h+arg_0]
0x18000f625  add     rsp, 20h
0x18000f629  pop     r14
0x18000f62b  pop     rdi
0x18000f62c  pop     rsi
0x18000f62d  retn
```
