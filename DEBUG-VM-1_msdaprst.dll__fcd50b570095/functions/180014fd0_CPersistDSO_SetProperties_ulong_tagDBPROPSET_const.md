# CPersistDSO::SetProperties(ulong,tagDBPROPSET * const)

- ea: `0x180014fd0`
- end: `0x18001513f`
- name: `?SetProperties@CPersistDSO@@UEAAJKQEAUtagDBPROPSET@@@Z`
- size: `367`
- prototype: `int(CPersistDSO *__hidden this, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180014fd0`
- `0x180015fb4`
- `0x18002ca58`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180015012`
- `KERNEL32!GetCurrentThreadId` at `0x180015012`
- `KERNEL32!LeaveCriticalSection` at `0x1800150cc`
- `KERNEL32!LeaveCriticalSection` at `0x180015122`
- `KERNEL32!LeaveCriticalSection` at `0x1800150cc`
- `KERNEL32!LeaveCriticalSection` at `0x180015122`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015032`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015032`
- `MSDART!UMSEnterCSWraper` at `0x180014ffe`
- `MSDART!UMSEnterCSWraper` at `0x180014ffe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::SetProperties(GUID *this, unsigned int a2, struct tagDBPROPSET *const a3)
{
  GUID *v6; // rbx
  unsigned __int8 *v7; // rdi
  unsigned int v8; // edx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // esi
  bool v12; // zf
  __int64 v13; // rcx
  unsigned int v15; // ebx
  __int64 v16; // rcx
  int v17; // [rsp+30h] [rbp-48h] BYREF
  GUID *v18; // [rsp+38h] [rbp-40h]
  unsigned __int8 *v19; // [rsp+40h] [rbp-38h]
  GUID *v20; // [rsp+48h] [rbp-30h]
  int v22; // [rsp+88h] [rbp+10h]
  GUID *v23; // [rsp+98h] [rbp+20h]

  v6 = this + 3;
  v23 = this + 3;
  UMSEnterCSWraper(&this[3]);
  v7 = &v6->Data4[4];
  v19 = &v6->Data4[4];
  if ( !*(_DWORD *)&v6->Data4[4] )
    *(_DWORD *)v6->Data4 = GetCurrentThreadId();
  ++*(_DWORD *)v7;
  v18 = v6 + 1;
  ++v6[1].Data1;
  v20 = v6;
  SetErrorInfo(0, 0);
  this[6] = IID_IDBProperties;
  *(_DWORD *)&this[263].Data2 = 0;
  if ( a2 == 1 )
  {
    v9 = *(_QWORD *)&a3->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
    if ( !v9 )
      v9 = *(_QWORD *)a3->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DBINIT.Data4;
    if ( !v9 )
      this[292].Data1 = 0;
  }
  try
  {
    v10 = CUtlProps::utlSetProperties(
            (CUtlProps *)this[287].Data4,
            v8,
            a2,
            a3,
            (const struct CBidGenericBase *)this[286].Data4,
            0);
    this[292].Data1 = 1;
    v11 = Exit(v10, 0xBB8u);
  }
  catch ( long v17 )
  {
    v22 = v17;
    goto LABEL_12;
  }
  catch ( ... )
  {
    v22 = -2147467259;
LABEL_12:
    this[292].Data1 = 1;
    v15 = Exit(v22, 0);
    --v18->Data1;
    v12 = (*(_DWORD *)v19)-- == 1;
    if ( v12 )
      *(_DWORD *)v23->Data4 = -1;
    v16 = *(_QWORD *)&v23->Data1;
    --*(_DWORD *)(v16 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 8));
    return v15;
  }
  --v6[1].Data1;
  v12 = (*(_DWORD *)v7)-- == 1;
  if ( v12 )
    *(_DWORD *)v6->Data4 = -1;
  v13 = *(_QWORD *)&v6->Data1;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v11;
}

```

## disassembly

```asm
0x180014fd0  mov     [rsp+arg_10], rbx
0x180014fd5  mov     [rsp+arg_0], rcx
0x180014fda  push    rsi
0x180014fdb  push    rdi
0x180014fdc  push    r12
0x180014fde  push    r14
0x180014fe0  push    r15
0x180014fe2  sub     rsp, 50h
0x180014fe6  mov     r15, r8
0x180014fe9  mov     r12d, edx
0x180014fec  mov     rsi, rcx
0x180014fef  lea     rbx, [rcx+30h]
0x180014ff3  mov     [rsp+78h+arg_18], rbx
0x180014ffb  mov     rcx, rbx
0x180014ffe  call    cs:__imp_UMSEnterCSWraper
0x180015004  lea     rdi, [rbx+0Ch]
0x180015008  mov     [rsp+78h+var_38], rdi
0x18001500d  cmp     dword ptr [rdi], 0
0x180015010  jnz     short loc_18001501B
0x180015012  call    cs:__imp_GetCurrentThreadId
0x180015018  mov     [rbx+8], eax
0x18001501b  inc     dword ptr [rdi]
0x18001501d  lea     r14, [rbx+10h]
0x180015021  mov     [rsp+78h+var_40], r14
0x180015026  inc     dword ptr [r14]
0x180015029  mov     [rsp+78h+var_30], rbx
0x18001502e  xor     edx, edx; perrinfo
0x180015030  xor     ecx, ecx; dwReserved
0x180015032  call    cs:__imp_SetErrorInfo
0x180015038  movups  xmm0, xmmword ptr cs:IID_IDBProperties.Data1
0x18001503f  movdqu  xmmword ptr [rsi+60h], xmm0
0x180015044  mov     dword ptr [rsi+1074h], 0
0x18001504e  cmp     r12d, 1
0x180015052  jnz     short loc_180015077
0x180015054  mov     rax, [r15+0Ch]
0x180015058  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x18001505f  jnz     short loc_18001506C
0x180015061  mov     rax, [r15+14h]
0x180015065  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x18001506c  test    rax, rax
0x18001506f  jnz     short loc_180015077
0x180015071  mov     [rsi+1240h], eax
0x180015077  lea     rax, [rsi+11E8h]
0x18001507e  lea     rcx, [rsi+11F8h]; this
0x180015085  mov     [rsp+78h+var_50], 0; int
0x18001508d  mov     [rsp+78h+var_58], rax; struct CBidGenericBase *
0x180015092  mov     r9, r15; struct tagDBPROPSET *
0x180015095  mov     r8d, r12d; unsigned int
0x180015098  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x18001509d  mov     dword ptr [rsi+1240h], 1
0x1800150a7  mov     edx, 0BB8h; unsigned int
0x1800150ac  mov     ecx, eax; int
0x1800150ae  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800150b3  mov     esi, eax
0x1800150b5  or      edx, 0FFFFFFFFh
0x1800150b8  add     [r14], edx
0x1800150bb  add     [rdi], edx
0x1800150bd  jnz     short loc_1800150C2
0x1800150bf  mov     [rbx+8], edx
0x1800150c2  mov     rcx, [rbx]
0x1800150c5  dec     dword ptr [rcx+30h]
0x1800150c8  add     rcx, 8; lpCriticalSection
0x1800150cc  call    cs:__imp_LeaveCriticalSection
0x1800150d2  mov     eax, esi
0x1800150d4  jmp     short loc_18001512A
0x1800150d6  jmp     short $+2
0x1800150d8  mov     rax, [rsp+78h+arg_0]
0x1800150e0  mov     dword ptr [rax+1240h], 1
0x1800150ea  xor     edx, edx; unsigned int
0x1800150ec  mov     ecx, [rsp+78h+arg_8]; int
0x1800150f3  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800150f8  mov     ebx, eax
0x1800150fa  or      edx, 0FFFFFFFFh
0x1800150fd  mov     rcx, [rsp+78h+var_40]
0x180015102  add     [rcx], edx
0x180015104  mov     rcx, [rsp+78h+var_38]
0x180015109  add     [rcx], edx
0x18001510b  mov     rcx, [rsp+78h+arg_18]
0x180015113  jnz     short loc_180015118
0x180015115  mov     [rcx+8], edx
0x180015118  mov     rcx, [rcx]
0x18001511b  dec     dword ptr [rcx+30h]
0x18001511e  add     rcx, 8; lpCriticalSection
0x180015122  call    cs:__imp_LeaveCriticalSection
0x180015128  mov     eax, ebx
0x18001512a  mov     rbx, [rsp+78h+arg_10]
0x180015132  add     rsp, 50h
0x180015136  pop     r15
0x180015138  pop     r14
0x18001513a  pop     r12
0x18001513c  pop     rdi
0x18001513d  pop     rsi
0x18001513e  retn
```
