# CAppList::WriteConflicts(CAppInfo *)

- ea: `0x18000b3bc`
- end: `0x18000b641`
- name: `?WriteConflicts@CAppList@@AEAAJPEAVCAppInfo@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(IWbemServices **this, struct CAppInfo *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18000b16c`

## callees

- `0x1800016d0`
- `0x180002b14`
- `0x18000b3bc`
- `0x18000c480`
- `0x18000c53c`
- `0x18000c5d8`
- `0x180012fbc`
- `0x18001b1a0`
- `0x180029cc0`
- `0x18002a818`
- `0x18002a970`
- `0x18002c010`

## import_xrefs

- `USERENV!RsopResetPolicySettingStatus` at `0x18000b5de`
- `USERENV!RsopResetPolicySettingStatus` at `0x18000b5de`

## pseudocode

```c
__int64 __fastcall CAppList::WriteConflicts(IWbemServices **this, struct CAppInfo *a2)
{
  CConflictTable *v4; // rdi
  int v5; // esi
  struct CConflict *NextConflict; // rax
  struct CConflict *v7; // rbx
  __int64 *i; // rax
  __int64 *v9; // rcx
  __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  int v12; // ebx
  int v13; // eax
  const unsigned __int16 *v14; // r8
  int v15; // eax
  int v17[2]; // [rsp+20h] [rbp-69h]
  int v18; // [rsp+30h] [rbp-59h] BYREF
  __int64 v19; // [rsp+38h] [rbp-51h] BYREF
  __int64 *v20; // [rsp+40h] [rbp-49h]
  __int128 v21; // [rsp+48h] [rbp-41h]
  unsigned __int16 v22[40]; // [rsp+60h] [rbp-29h] BYREF

  v21 = 0;
  v20 = &v19;
  v19 = (__int64)&v19;
  v4 = (struct CAppInfo *)((char *)a2 + 256);
  v18 = 2;
  v5 = 0;
  *((_QWORD *)a2 + 36) = 0;
  *((_QWORD *)a2 + 35) = *((_QWORD *)a2 + 34);
  *((_QWORD *)a2 + 34) = *((_QWORD *)a2 + 33);
  while ( 1 )
  {
    NextConflict = CConflictTable::GetNextConflict(v4, &v18);
    v7 = NextConflict;
    if ( !NextConflict )
      break;
    v5 = CConflictList::AddConflict(
           (CConflictList *)&v19,
           *((struct CAppInfo **)NextConflict + 5),
           *((struct CAppInfo **)NextConflict + 8),
           *((_DWORD *)NextConflict + 15),
           *((_DWORD *)NextConflict + 14));
    if ( v5 )
      break;
    v18 = *((_DWORD *)v7 + 14);
  }
  if ( v5 >= 0 )
  {
    *((_QWORD *)&v21 + 1) = v21;
    for ( i = v20; ; i = *(__int64 **)(v21 + 8) )
    {
      *(_QWORD *)&v21 = i;
      v9 = 0;
      if ( i != &v19 )
        v9 = i;
      v10 = (unsigned __int64)(v9 - 3) & -(__int64)(v9 != 0);
      if ( !v10 )
        goto LABEL_35;
      GuidToString((struct _GUID *)((char *)a2 + 24), v22);
      v11 = StringDuplicate(v22);
      *(_QWORD *)(v10 + 48) = v11;
      if ( !v11 )
      {
        v5 = -2147024882;
        goto LABEL_33;
      }
      v5 = 0;
      if ( *(_QWORD *)(*(_QWORD *)(v10 + 40) + 64LL) )
        break;
      v12 = CGroupPolicyLog::OpenExistingRecord((CGroupPolicyLog *)this, (struct CGroupPolicyRecord *)v10);
      if ( v12 < 0 )
        goto LABEL_21;
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v12 < 0 )
        goto LABEL_21;
      v13 = CGroupPolicyRecord::ClearValue((CGroupPolicyRecord *)v10, L"RemovalCause");
      v12 = v13;
      if ( v13 < 0 )
      {
        if ( !*(_DWORD *)&gDebugLevel )
          continue;
        v14 = L"RemovalCause";
        goto LABEL_20;
      }
      v13 = CGroupPolicyRecord::ClearValue((CGroupPolicyRecord *)v10, L"RemovalType");
      v12 = v13;
      if ( v13 < 0 )
      {
        if ( !*(_DWORD *)&gDebugLevel )
          continue;
        v14 = L"RemovalType";
        goto LABEL_20;
      }
      v13 = CGroupPolicyRecord::ClearValue((CGroupPolicyRecord *)v10, L"RemovingApplication");
      v12 = v13;
      if ( v13 >= 0 )
      {
        v15 = ((__int64 (__fastcall *)(IWbemServices *, _QWORD, _QWORD, _QWORD, _QWORD))this[4]->lpVtbl->PutInstance)(
                this[4],
                *(_QWORD *)(v10 + 8),
                0,
                0,
                0);
        goto LABEL_30;
      }
      if ( *(_DWORD *)&gDebugLevel )
      {
        v14 = L"RemovingApplication";
LABEL_20:
        _DebugMsg(4, 0xC29u, v14, (unsigned int)v13);
      }
LABEL_21:
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC24u, (unsigned int)v12);
LABEL_23:
      ;
    }
    v15 = CGroupPolicyLog::WriteNewRecord((CGroupPolicyLog *)this, (struct CGroupPolicyRecord *)v10);
LABEL_30:
    v12 = v15;
    if ( v15 >= 0 )
    {
      RsopResetPolicySettingStatus(0, this[4], *(IWbemClassObject **)(v10 + 8));
      goto LABEL_23;
    }
    goto LABEL_21;
  }
LABEL_33:
  if ( *(_DWORD *)&gDebugLevel )
  {
    v17[0] = v5;
    _DebugMsg(4, 0xC2Au, *((_QWORD *)a2 + 5), *((_QWORD *)a2 + 9), *(_QWORD *)v17);
  }
LABEL_35:
  CConflictList::~CConflictList((CConflictList *)&v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b3bc  mov     [rsp-8+arg_10], rbx
0x18000b3c1  mov     [rsp-8+arg_18], rsi
0x18000b3c6  push    rbp
0x18000b3c7  push    rdi
0x18000b3c8  push    r13
0x18000b3ca  push    r14
0x18000b3cc  push    r15
0x18000b3ce  lea     rbp, [rsp-37h]
0x18000b3d3  sub     rsp, 0C0h
0x18000b3da  mov     rax, cs:__security_cookie
0x18000b3e1  xor     rax, rsp
0x18000b3e4  mov     [rbp+57h+var_30], rax
0x18000b3e8  mov     r14, rdx
0x18000b3eb  mov     r15, rcx
0x18000b3ee  xorps   xmm0, xmm0
0x18000b3f1  movdqu  [rbp+57h+var_98], xmm0
0x18000b3f6  lea     rax, [rbp+57h+var_A8]
0x18000b3fa  mov     [rbp+57h+var_A0], rax
0x18000b3fe  lea     rax, [rbp+57h+var_A8]
0x18000b402  mov     [rbp+57h+var_A8], rax
0x18000b406  lea     rdi, [rdx+100h]
0x18000b40d  mov     [rbp+57h+var_B0], 2
0x18000b414  xor     esi, esi
0x18000b416  mov     [rdi+20h], rsi
0x18000b41a  mov     rax, [rdi+10h]
0x18000b41e  mov     [rdi+18h], rax
0x18000b422  mov     rax, [rdi+8]
0x18000b426  mov     [rdi+10h], rax
0x18000b42a  jmp     short loc_18000B454
0x18000b42c  mov     ecx, [rbx+38h]
0x18000b42f  mov     [rsp+0E0h+var_C0], ecx; int
0x18000b433  mov     r9d, [rbx+3Ch]; unsigned int
0x18000b437  mov     r8, [rbx+40h]; struct CAppInfo *
0x18000b43b  mov     rdx, [rbx+28h]; struct CAppInfo *
0x18000b43f  lea     rcx, [rbp+57h+var_A8]; this
0x18000b443  call    ?AddConflict@CConflictList@@QEAAJPEAVCAppInfo@@0KJ@Z; CConflictList::AddConflict(CAppInfo *,CAppInfo *,ulong,long)
0x18000b448  mov     esi, eax
0x18000b44a  test    eax, eax
0x18000b44c  jnz     short loc_18000B468
0x18000b44e  mov     eax, [rbx+38h]
0x18000b451  mov     [rbp+57h+var_B0], eax
0x18000b454  lea     rdx, [rbp+57h+var_B0]; int *
0x18000b458  mov     rcx, rdi; this
0x18000b45b  call    ?GetNextConflict@CConflictTable@@QEAAPEAVCConflict@@PEAJ@Z; CConflictTable::GetNextConflict(long *)
0x18000b460  test    rax, rax
0x18000b463  mov     rbx, rax
0x18000b466  jnz     short loc_18000B42C
0x18000b468  mov     r13d, 4
0x18000b46e  test    esi, esi
0x18000b470  js      loc_18000B5EB
0x18000b476  mov     rax, qword ptr [rbp+57h+var_98]
0x18000b47a  mov     qword ptr [rbp+57h+var_98+8], rax
0x18000b47e  mov     rax, [rbp+57h+var_A0]
0x18000b482  mov     qword ptr [rbp+57h+var_98], rax
0x18000b486  xor     ecx, ecx
0x18000b488  lea     rdx, [rbp+57h+var_A8]
0x18000b48c  cmp     rax, rdx
0x18000b48f  cmovnz  rcx, rax
0x18000b493  lea     rax, [rcx-18h]
0x18000b497  neg     rcx
0x18000b49a  sbb     rdi, rdi
0x18000b49d  and     rdi, rax
0x18000b4a0  jz      loc_18000B60E
0x18000b4a6  lea     rcx, [r14+18h]; struct _GUID *
0x18000b4aa  lea     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x18000b4ae  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x18000b4b3  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x18000b4b7  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x18000b4bc  mov     [rdi+30h], rax
0x18000b4c0  test    rax, rax
0x18000b4c3  jz      loc_18000B5E6
0x18000b4c9  xor     esi, esi
0x18000b4cb  mov     rax, [rdi+28h]
0x18000b4cf  mov     rdx, rdi; struct CGroupPolicyRecord *
0x18000b4d2  mov     rcx, r15; this
0x18000b4d5  cmp     [rax+40h], rsi
0x18000b4d9  jnz     loc_18000B5C9
0x18000b4df  call    ?OpenExistingRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@@Z; CGroupPolicyLog::OpenExistingRecord(CGroupPolicyRecord *)
0x18000b4e4  mov     ebx, eax
0x18000b4e6  test    eax, eax
0x18000b4e8  js      short loc_18000B559
0x18000b4ea  mov     rax, [rdi]
0x18000b4ed  mov     rcx, rdi
0x18000b4f0  mov     rax, [rax+10h]
0x18000b4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f9  mov     ebx, eax
0x18000b4fb  test    eax, eax
0x18000b4fd  js      short loc_18000B559
0x18000b4ff  lea     rdx, aRemovalcause; "RemovalCause"
0x18000b506  mov     rcx, rdi; this
0x18000b509  call    ?ClearValue@CGroupPolicyRecord@@QEAAJPEBG@Z; CGroupPolicyRecord::ClearValue(ushort const *)
0x18000b50e  mov     ebx, eax
0x18000b510  test    eax, eax
0x18000b512  jns     short loc_18000B525
0x18000b514  cmp     cs:?gDebugLevel@@3KA, esi; ulong gDebugLevel
0x18000b51a  jz      short loc_18000B571
0x18000b51c  lea     r8, aRemovalcause; "RemovalCause"
0x18000b523  jmp     short loc_18000B549
0x18000b525  lea     rdx, aRemovaltype; "RemovalType"
0x18000b52c  mov     rcx, rdi; this
0x18000b52f  call    ?ClearValue@CGroupPolicyRecord@@QEAAJPEBG@Z; CGroupPolicyRecord::ClearValue(ushort const *)
0x18000b534  mov     ebx, eax
0x18000b536  test    eax, eax
0x18000b538  jns     short loc_18000B57E
0x18000b53a  cmp     cs:?gDebugLevel@@3KA, esi; ulong gDebugLevel
0x18000b540  jz      short loc_18000B571
0x18000b542  lea     r8, aRemovaltype; "RemovalType"
0x18000b549  mov     r9d, eax
0x18000b54c  mov     edx, 0C29h; unsigned int
0x18000b551  mov     ecx, r13d; unsigned int
0x18000b554  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000b559  cmp     cs:?gDebugLevel@@3KA, esi; ulong gDebugLevel
0x18000b55f  jz      short loc_18000B571
0x18000b561  mov     r8d, ebx
0x18000b564  mov     edx, 0C24h; unsigned int
0x18000b569  mov     ecx, r13d; unsigned int
0x18000b56c  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000b571  mov     rax, qword ptr [rbp+57h+var_98]
0x18000b575  mov     rax, [rax+8]
0x18000b579  jmp     loc_18000B482
0x18000b57e  lea     rdx, aRemovingapplic; "RemovingApplication"
0x18000b585  mov     rcx, rdi; this
0x18000b588  call    ?ClearValue@CGroupPolicyRecord@@QEAAJPEBG@Z; CGroupPolicyRecord::ClearValue(ushort const *)
0x18000b58d  mov     ebx, eax
0x18000b58f  test    eax, eax
0x18000b591  jns     short loc_18000B5A8
0x18000b593  cmp     cs:?gDebugLevel@@3KA, esi; ulong gDebugLevel
0x18000b599  jz      short loc_18000B5A4
0x18000b59b  lea     r8, aRemovingapplic; "RemovingApplication"
0x18000b5a2  jmp     short loc_18000B549
0x18000b5a4  test    eax, eax
0x18000b5a6  js      short loc_18000B559
0x18000b5a8  mov     rcx, [r15+20h]
0x18000b5ac  mov     rax, [rcx]
0x18000b5af  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x18000b5b4  xor     r9d, r9d
0x18000b5b7  xor     r8d, r8d
0x18000b5ba  mov     rdx, [rdi+8]
0x18000b5be  mov     rax, [rax+70h]
0x18000b5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c7  jmp     short loc_18000B5CE
0x18000b5c9  call    ?WriteNewRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@@Z; CGroupPolicyLog::WriteNewRecord(CGroupPolicyRecord *)
0x18000b5ce  mov     ebx, eax
0x18000b5d0  test    eax, eax
0x18000b5d2  js      short loc_18000B559
0x18000b5d4  mov     r8, [rdi+8]; pSettingInstance
0x18000b5d8  mov     rdx, [r15+20h]; pServices
0x18000b5dc  xor     ecx, ecx; dwFlags
0x18000b5de  call    cs:__imp_RsopResetPolicySettingStatus
0x18000b5e4  jmp     short loc_18000B571
0x18000b5e6  mov     esi, 8007000Eh
0x18000b5eb  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000b5f2  jz      short loc_18000B60E
0x18000b5f4  mov     [rsp+0E0h+var_C0], esi
0x18000b5f8  mov     r9, [r14+48h]
0x18000b5fc  mov     r8, [r14+28h]
0x18000b600  mov     edx, 0C2Ah; unsigned int
0x18000b605  mov     ecx, r13d; unsigned int
0x18000b608  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000b60d  nop
0x18000b60e  lea     rcx, [rbp+57h+var_A8]; this
0x18000b612  call    ??1CConflictList@@QEAA@XZ; CConflictList::~CConflictList(void)
0x18000b617  mov     eax, esi
0x18000b619  mov     rcx, [rbp+57h+var_30]
0x18000b61d  xor     rcx, rsp; StackCookie
0x18000b620  call    __security_check_cookie
0x18000b625  lea     r11, [rsp+0E0h+var_20]
0x18000b62d  mov     rbx, [r11+40h]
0x18000b631  mov     rsi, [r11+48h]
0x18000b635  mov     rsp, r11
0x18000b638  pop     r15
0x18000b63a  pop     r14
0x18000b63c  pop     r13
0x18000b63e  pop     rdi
0x18000b63f  pop     rbp
0x18000b640  retn
```
