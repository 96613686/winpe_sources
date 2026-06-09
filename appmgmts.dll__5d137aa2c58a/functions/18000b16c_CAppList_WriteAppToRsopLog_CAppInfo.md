# CAppList::WriteAppToRsopLog(CAppInfo *)

- ea: `0x18000b16c`
- end: `0x18000b3b5`
- name: `?WriteAppToRsopLog@CAppList@@QEAAJPEAVCAppInfo@@@Z`
- size: `585`
- prototype: `__int64 __fastcall(CAppList *__hidden this, struct CAppInfo *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x180002310`
- `0x18000239c`
- `0x18000b648`

## callees

- `0x1800016d0`
- `0x180002b14`
- `0x1800060fc`
- `0x1800061a0`
- `0x180007de4`
- `0x18000a6e4`
- `0x18000a7c0`
- `0x18000b16c`
- `0x18000b3bc`
- `0x18000c42c`
- `0x18000c790`
- `0x180012fbc`
- `0x18001b1a0`
- `0x18002a3d4`
- `0x18002a970`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2c6`

## pseudocode

```c
__int64 __fastcall CAppList::WriteAppToRsopLog(CAppList *this, struct CAppInfo *a2)
{
  int inited; // edi
  int v5; // eax
  int v6; // eax
  BOOL v7; // r8d
  _DWORD *v8; // rcx
  unsigned __int16 *RsopAppCriteria; // rbx
  HLOCAL v11[2]; // [rsp+20h] [rbp-79h] BYREF
  int v12; // [rsp+30h] [rbp-69h]
  __int64 v13; // [rsp+38h] [rbp-61h]
  __int64 v14; // [rsp+40h] [rbp-59h]
  struct CAppInfo *v15; // [rsp+48h] [rbp-51h]
  unsigned __int16 *v16; // [rsp+50h] [rbp-49h]
  __int64 v17; // [rsp+58h] [rbp-41h]
  __int64 v18; // [rsp+60h] [rbp-39h]
  unsigned __int16 v19[40]; // [rsp+70h] [rbp-29h] BYREF

  v13 = 0;
  v14 = 0;
  v11[1] = 0;
  v12 = 1;
  v11[0] = &CConflict::`vftable';
  v15 = a2;
  v16 = 0;
  v17 = 1;
  v18 = 0;
  if ( *((_DWORD *)a2 + 75) || *((_DWORD *)a2 + 58) == 1274 && (unsigned int)(*((_DWORD *)a2 + 57) - 1) > 2 )
    goto LABEL_34;
  inited = CAppList::InitRsopLog(this);
  if ( inited < 0 )
    goto LABEL_35;
  if ( *((struct CAppInfo **)a2 + 52) == (struct CAppInfo *)((char *)a2 + 400) || !*((_QWORD *)a2 + 52) )
  {
    if ( !*(_DWORD *)(*((_QWORD *)this + 11) + 128LL) )
      goto LABEL_10;
LABEL_34:
    inited = 0;
    goto LABEL_35;
  }
  if ( !*((_DWORD *)a2 + 57) )
    CAppInfo::SetAction((__int64)a2, 1, *((_DWORD *)a2 + 95), 0);
LABEL_10:
  v5 = CAppInfo::GetRsopEntryType(a2) - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( !v6 )
    {
      v7 = 1;
      v8 = (_DWORD *)*((_QWORD *)a2 + 52);
      if ( v8 != (_DWORD *)((char *)a2 + 400) && v8 )
        v7 = v8[4] != 3;
      inited = CAppList::MarkRSOPEntryAsRemoved((IWbemServices **)this, a2, v7);
      if ( inited >= 0 )
        *((_DWORD *)a2 + 76) = 1;
      goto LABEL_35;
    }
    if ( v6 != 1 )
      goto LABEL_35;
  }
  else
  {
    RsopAppCriteria = CAppInfo::GetRsopAppCriteria(a2);
    inited = CGroupPolicyLog::ClearLog(this, RsopAppCriteria, 1);
    LocalFree(RsopAppCriteria);
    if ( inited < 0
      || *(_DWORD *)(*((_QWORD *)this + 11) + 36LL) == 1 && (*((_BYTE *)a2 + 212) & 8) != 0 && !*((_DWORD *)a2 + 108) )
    {
      goto LABEL_35;
    }
  }
  if ( (!*(_DWORD *)(*((_QWORD *)this + 10) + 308LL) || *((_DWORD *)a2 + 57) == 2) && !*((_DWORD *)a2 + 74) )
  {
    GuidToString((struct _GUID *)((char *)a2 + 24), v19);
    v16 = StringDuplicate(v19);
    if ( v16 )
    {
      inited = CGroupPolicyLog::WriteNewRecord(this, (struct CGroupPolicyRecord *)v11);
      if ( inited >= 0 )
      {
LABEL_33:
        CConflict::LogFailure((CConflict *)v11);
        CAppList::WriteConflicts(this, a2);
        goto LABEL_35;
      }
    }
    else
    {
      inited = -2147024882;
    }
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC24u, (unsigned int)inited);
    inited = 0;
    goto LABEL_33;
  }
LABEL_35:
  CConflict::~CConflict(v11);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000b16c  mov     [rsp-8+arg_10], rbx
0x18000b171  mov     [rsp-8+arg_18], rsi
0x18000b176  push    rbp
0x18000b177  push    rdi
0x18000b178  push    r12
0x18000b17a  push    r14
0x18000b17c  push    r15
0x18000b17e  lea     rbp, [rsp-37h]
0x18000b183  sub     rsp, 0D0h
0x18000b18a  mov     rax, cs:__security_cookie
0x18000b191  xor     rax, rsp
0x18000b194  mov     [rbp+57h+var_30], rax
0x18000b198  mov     rsi, rdx
0x18000b19b  mov     r14, rcx
0x18000b19e  xor     r15d, r15d
0x18000b1a1  mov     [rbp+57h+var_B8], r15
0x18000b1a5  mov     [rbp+57h+var_B0], r15
0x18000b1a9  mov     [rbp+57h+var_C8], r15
0x18000b1ad  lea     r12d, [r15+1]
0x18000b1b1  mov     [rbp+57h+var_C0], r12d
0x18000b1b5  lea     rax, ??_7CConflict@@6B@; const CConflict::`vftable'
0x18000b1bc  mov     [rbp+57h+var_D0], rax
0x18000b1c0  mov     [rbp+57h+var_A8], rdx
0x18000b1c4  mov     [rbp+57h+var_A0], r15
0x18000b1c8  mov     [rbp+57h+var_98], r12
0x18000b1cc  mov     [rbp+57h+var_90], r15
0x18000b1d0  cmp     [rdx+12Ch], r15d
0x18000b1d7  jnz     loc_18000B37F
0x18000b1dd  cmp     dword ptr [rdx+0E8h], 4FAh
0x18000b1e7  jnz     short loc_18000B1FB
0x18000b1e9  mov     eax, [rdx+0E4h]
0x18000b1ef  sub     eax, r12d
0x18000b1f2  cmp     eax, 2
0x18000b1f5  ja      loc_18000B37F
0x18000b1fb  call    ?InitRsopLog@CAppList@@AEAAJXZ; CAppList::InitRsopLog(void)
0x18000b200  mov     edi, eax
0x18000b202  test    eax, eax
0x18000b204  js      loc_18000B382
0x18000b20a  lea     rbx, [rsi+190h]
0x18000b211  cmp     [rbx+10h], rbx
0x18000b215  jz      short loc_18000B23D
0x18000b217  cmp     [rbx+10h], r15
0x18000b21b  jz      short loc_18000B23D
0x18000b21d  cmp     [rsi+0E4h], r15d
0x18000b224  jnz     short loc_18000B24E
0x18000b226  xor     r9d, r9d
0x18000b229  mov     r8d, [rsi+17Ch]
0x18000b230  mov     edx, r12d
0x18000b233  mov     rcx, rsi
0x18000b236  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x18000b23b  jmp     short loc_18000B24E
0x18000b23d  mov     rax, [r14+58h]
0x18000b241  cmp     [rax+80h], r15d
0x18000b248  jnz     loc_18000B37F
0x18000b24e  mov     rcx, rsi; this
0x18000b251  call    ?GetRsopEntryType@CAppInfo@@QEAAJXZ; CAppInfo::GetRsopEntryType(void)
0x18000b256  sub     eax, 1
0x18000b259  jz      short loc_18000B2A8
0x18000b25b  sub     eax, 1
0x18000b25e  jz      short loc_18000B26E
0x18000b260  cmp     eax, 1
0x18000b263  jz      loc_18000B2F4
0x18000b269  jmp     loc_18000B382
0x18000b26e  mov     r8d, r12d
0x18000b271  mov     rcx, [rbx+10h]
0x18000b275  cmp     rcx, rbx
0x18000b278  jz      short loc_18000B287
0x18000b27a  test    rcx, rcx
0x18000b27d  jz      short loc_18000B287
0x18000b27f  cmp     dword ptr [rcx+10h], 3
0x18000b283  cmovz   r8d, r15d; int
0x18000b287  mov     rdx, rsi; struct CAppInfo *
0x18000b28a  mov     rcx, r14; this
0x18000b28d  call    ?MarkRSOPEntryAsRemoved@CAppList@@QEAAJPEAVCAppInfo@@H@Z; CAppList::MarkRSOPEntryAsRemoved(CAppInfo *,int)
0x18000b292  mov     edi, eax
0x18000b294  test    eax, eax
0x18000b296  js      loc_18000B382
0x18000b29c  mov     [rsi+130h], r12d
0x18000b2a3  jmp     loc_18000B382
0x18000b2a8  mov     rcx, rsi; this
0x18000b2ab  call    ?GetRsopAppCriteria@CAppInfo@@AEAAPEAGXZ; CAppInfo::GetRsopAppCriteria(void)
0x18000b2b0  mov     rbx, rax
0x18000b2b3  mov     r8d, r12d; int
0x18000b2b6  mov     rdx, rax; unsigned __int16 *
0x18000b2b9  mov     rcx, r14; this
0x18000b2bc  call    ?ClearLog@CGroupPolicyLog@@QEAAJPEBGH@Z; CGroupPolicyLog::ClearLog(ushort const *,int)
0x18000b2c1  mov     edi, eax
0x18000b2c3  mov     rcx, rbx; hMem
0x18000b2c6  call    cs:__imp_LocalFree
0x18000b2cc  test    edi, edi
0x18000b2ce  js      loc_18000B382
0x18000b2d4  mov     rax, [r14+58h]
0x18000b2d8  cmp     [rax+24h], r12d
0x18000b2dc  jnz     short loc_18000B2F4
0x18000b2de  test    byte ptr [rsi+0D4h], 8
0x18000b2e5  jz      short loc_18000B2F4
0x18000b2e7  cmp     [rsi+1B0h], r15d
0x18000b2ee  jz      loc_18000B382
0x18000b2f4  mov     rax, [r14+50h]
0x18000b2f8  cmp     [rax+134h], r15d
0x18000b2ff  jz      short loc_18000B30A
0x18000b301  cmp     dword ptr [rsi+0E4h], 2
0x18000b308  jnz     short loc_18000B382
0x18000b30a  cmp     [rsi+128h], r15d
0x18000b311  jnz     short loc_18000B382
0x18000b313  lea     rcx, [rsi+18h]; struct _GUID *
0x18000b317  lea     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x18000b31b  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x18000b320  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x18000b324  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x18000b329  mov     [rbp+57h+var_A0], rax
0x18000b32d  test    rax, rax
0x18000b330  jz      short loc_18000B346
0x18000b332  lea     rdx, [rbp+57h+var_D0]; struct CGroupPolicyRecord *
0x18000b336  mov     rcx, r14; this
0x18000b339  call    ?WriteNewRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@@Z; CGroupPolicyLog::WriteNewRecord(CGroupPolicyRecord *)
0x18000b33e  mov     edi, eax
0x18000b340  test    eax, eax
0x18000b342  jns     short loc_18000B369
0x18000b344  jmp     short loc_18000B34B
0x18000b346  mov     edi, 8007000Eh
0x18000b34b  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000b352  jz      short loc_18000B366
0x18000b354  mov     r8d, edi
0x18000b357  mov     edx, 0C24h; unsigned int
0x18000b35c  mov     ecx, 4; unsigned int
0x18000b361  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000b366  mov     edi, r15d
0x18000b369  lea     rcx, [rbp+57h+var_D0]; this
0x18000b36d  call    ?LogFailure@CConflict@@QEAAJXZ; CConflict::LogFailure(void)
0x18000b372  mov     rdx, rsi; struct CAppInfo *
0x18000b375  mov     rcx, r14; this
0x18000b378  call    ?WriteConflicts@CAppList@@AEAAJPEAVCAppInfo@@@Z; CAppList::WriteConflicts(CAppInfo *)
0x18000b37d  jmp     short loc_18000B382
0x18000b37f  mov     edi, r15d
0x18000b382  lea     rcx, [rbp+57h+var_D0]; this
0x18000b386  call    ??1CConflict@@UEAA@XZ; CConflict::~CConflict(void)
0x18000b38b  mov     eax, edi
0x18000b38d  mov     rcx, [rbp+57h+var_30]
0x18000b391  xor     rcx, rsp; StackCookie
0x18000b394  call    __security_check_cookie
0x18000b399  lea     r11, [rsp+0F0h+var_20]
0x18000b3a1  mov     rbx, [r11+40h]
0x18000b3a5  mov     rsi, [r11+48h]
0x18000b3a9  mov     rsp, r11
0x18000b3ac  pop     r15
0x18000b3ae  pop     r14
0x18000b3b0  pop     r12
0x18000b3b2  pop     rdi
0x18000b3b3  pop     rbp
0x18000b3b4  retn
```
