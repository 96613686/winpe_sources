# CRpcIOManagerServer::Poke(_SessionRank,ushort *,ushort *,ulong,uchar *)

- ea: `0x180058304`
- end: `0x1800587c3`
- name: `?Poke@CRpcIOManagerServer@@QEAAJW4_SessionRank@@PEAG1KPEAE@Z`
- size: `1215`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800557d0`

## callees

- `0x180003cf0`
- `0x18000cd08`
- `0x18000cddc`
- `0x18000fb60`
- `0x18001d178`
- `0x1800562b4`
- `0x180057db4`
- `0x180058304`
- `0x1800592a8`
- `0x1800594e0`
- `0x1800678d0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800586e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800586e4`

## string_xrefs

- `0x180058360`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x1800583ec`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180058461`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x1800584aa`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x1800586ae`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180058705`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18005875f`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x1800583be`: `VerifyRpcSecurity Call Failed`
- `0x180058642`: `CConnectionManager::CreateANewSessionObject failed. This indicates a low memory situation.`
- `0x18005868c`: `Session Object created, but CM was asked to stop listening. This is an informational message.`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::Poke(
        __int64 a1,
        int a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  struct INameObject *v9; // rdi
  __int64 v10; // rax
  int v11; // eax
  unsigned __int16 *v12; // r12
  int started; // ebx
  const wchar_t *v14; // rax
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int8 *v18; // rsi
  unsigned int v19; // ebx
  int v21; // eax
  __int64 v22; // rax
  bool v23; // zf
  __int64 v24; // rax
  CSessionObject *v25; // rsi
  __int64 v26; // rax
  CSessionObject *v27; // rcx
  unsigned __int16 *v28; // [rsp+28h] [rbp-38h]
  unsigned __int16 *v29; // [rsp+28h] [rbp-38h]
  const wchar_t *v30; // [rsp+30h] [rbp-30h]
  __int64 v31; // [rsp+38h] [rbp-28h]
  int v32; // [rsp+40h] [rbp-20h] BYREF
  CSessionObject *v33; // [rsp+48h] [rbp-18h] BYREF
  void *Block; // [rsp+50h] [rbp-10h] BYREF
  struct INameObject *v35; // [rsp+58h] [rbp-8h] BYREF
  int v36; // [rsp+A0h] [rbp+40h] BYREF
  int v37; // [rsp+A8h] [rbp+48h]

  v37 = a2;
  v35 = 0;
  v33 = 0;
  Block = 0;
  v36 = 0;
  v32 = 0;
  v9 = 0;
  TraceStringInline(
    1,
    6,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    1888,
    L"CRpcIOManagerServer::Poke",
    0,
    L"In");
  v10 = *(_QWORD *)(a1 + 88);
  if ( *(_DWORD *)(v10 + 40) || !*(_DWORD *)(v10 + 60) )
    v11 = CRpcIOManagerServer::VerifyRpcSecurity((CRpcIOManagerServer *)a1, (unsigned __int16 **)&Block, &v32, &v36, a3);
  else
    v11 = CRpcIOManagerServer::VerifyRpcSecuritySchannel(
            (CRpcIOManagerServer *)a1,
            (unsigned __int16 **)&Block,
            &v32,
            &v36,
            a3);
  v12 = (unsigned __int16 *)Block;
  started = v11;
  if ( v11 < 0 )
  {
    v14 = L"VerifyRpcSecurity Call Failed";
    v15 = 1908;
    goto LABEL_7;
  }
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( a3[v17] );
  if ( (unsigned __int64)(v17 - 1) > 0xFF )
    goto LABEL_42;
  do
    ++v16;
  while ( a4[v16] );
  if ( v16 != 36 || (v18 = a6, v19 = a5, !a6) && a5 || v37 != 2 )
  {
LABEL_42:
    started = -2147024809;
    goto LABEL_43;
  }
  TraceStringInline(
    1,
    4,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    1922,
    L"CRpcIOManagerServer::Poke",
    0,
    L"Client host = %s",
    a3);
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 60LL) != 2 )
  {
    LODWORD(v31) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 60LL);
    LODWORD(v29) = -2147483357;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      1931,
      L"CRpcIOManagerServer::Poke",
      v29,
      L"CM not yet in postinit state. (The current state is %d)",
      v31);
    return 2147483939LL;
  }
  v21 = CRpcIOManagerServer::FindOrCreateNameObject((CRpcIOManagerServer *)a1, a3, a4, v19, v18, v12, &v35);
  v9 = v35;
  started = v21;
  if ( !v21 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 88) + 60LL)
      || (started = (*(__int64 (__fastcall **)(struct INameObject *, unsigned __int16 *, unsigned __int16 *, _QWORD))(*(_QWORD *)v35 + 160LL))(
                      v35,
                      a3,
                      v12,
                      (unsigned int)v32),
          started >= 0) )
    {
      v22 = *(_QWORD *)(a1 + 88);
      if ( !*(_DWORD *)(v22 + 40) && !*(_DWORD *)(v22 + 60) )
      {
        v23 = (*(unsigned int (__fastcall **)(struct INameObject *))(*(_QWORD *)v9 + 128LL))(v9) == 0;
        v24 = *(_QWORD *)v9;
        if ( v23 )
        {
          if ( (*(unsigned int (__fastcall **)(struct INameObject *))(v24 + 144))(v9)
            && !(*(unsigned int (__fastcall **)(struct INameObject *))(*(_QWORD *)v9 + 176LL))(v9) )
          {
            v30 = L"Received a Poke call from a contact we expected to be KtmRm, but they could not be verified as KtmRm.";
            started = -2147024891;
            LODWORD(v28) = -2147024891;
            v15 = 1995;
            goto LABEL_8;
          }
        }
        else if ( !(*(unsigned int (__fastcall **)(struct INameObject *))(v24 + 168))(v9) )
        {
          v30 = L"Received a Poke call from a contact we expected to be MSDTC, but they could not be verified as MSDTC.";
          started = -2147024891;
          LODWORD(v28) = -2147024891;
          v15 = 1979;
          goto LABEL_8;
        }
      }
      CRWLock::AcquireWriterLock((CRWLock *)(*(_QWORD *)(a1 + 8) + 344LL));
      CConnectionManager::LookForExistingSession(*(CConnectionManager **)(a1 + 8), v9, &v33);
      v25 = v33;
      if ( v33 )
      {
        if ( *((_DWORD *)v33 + 1) )
        {
          *((_DWORD *)v33 + 4) = 1;
          *((_DWORD *)v25 + 355) = v36;
          SetEvent(*((HANDLE *)v25 + 16));
          if ( (unsigned int)(*((_DWORD *)v25 + 26) - 1) > 2 )
          {
            LODWORD(v31) = *((_DWORD *)v25 + 26);
            LODWORD(v28) = -2147483357;
            started = -2147483357;
            TraceStringInline(
              1,
              1,
              L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
              2076,
              L"CRpcIOManagerServer::Poke",
              v28,
              L"Recived Poke for a new session, but old session still active. This is an informational message. (The state is %d)",
              v31);
          }
        }
      }
      else
      {
        started = CConnectionManager::CreateANewSessionObject(*(CConnectionManager **)(a1 + 8), v9, &v33);
        if ( started )
        {
          LODWORD(v28) = started;
          TraceStringInline(
            1,
            1,
            L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
            2018,
            L"CRpcIOManagerServer::Poke",
            v28,
            L"CConnectionManager::CreateANewSessionObject failed. This indicates a low memory situation.");
        }
        else
        {
          v26 = *(_QWORD *)(a1 + 8);
          if ( *(_DWORD *)(v26 + 68) == 1 && *(_DWORD *)(v26 + 60) == 2 )
          {
            v27 = v33;
            *((_DWORD *)v33 + 4) = 1;
            *((_DWORD *)v27 + 355) = v36;
            started = CSessionObject::StartMaintenance(v27);
          }
          else
          {
            started = -2147483357;
            LODWORD(v28) = -2147483357;
            TraceStringInline(
              1,
              1,
              L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
              2042,
              L"CRpcIOManagerServer::Poke",
              v28,
              L"Session Object created, but CM was asked to stop listening. This is an informational message.");
          }
        }
      }
      CRWLock::ReleaseWriterLock((CRWLock *)(*(_QWORD *)(a1 + 8) + 344LL));
      goto LABEL_43;
    }
    v14 = L"Call to INameObject::VerifyAndSetPartnerAsDTCorKtmRm failed";
    v15 = 1959;
LABEL_7:
    v30 = v14;
    LODWORD(v28) = started;
LABEL_8:
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      v15,
      L"CRpcIOManagerServer::Poke",
      v28,
      v30);
  }
LABEL_43:
  TraceStringInline(
    1,
    6,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    2092,
    L"CRpcIOManagerServer::Poke",
    0,
    L"Out");
  if ( v9 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v12 )
    operator delete(v12);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180058304  mov     r11, rsp
0x180058307  mov     [r11+18h], rbx
0x18005830b  mov     [rsp-38h+arg_8], edx
0x18005830f  push    rbp
0x180058310  push    rsi
0x180058311  push    rdi
0x180058312  push    r12
0x180058314  push    r13
0x180058316  push    r14
0x180058318  push    r15
0x18005831a  mov     rbp, rsp
0x18005831d  sub     rsp, 60h
0x180058321  xor     esi, esi
0x180058323  lea     rax, aIn_0; "In"
0x18005832a  mov     [r11-68h], rax
0x18005832e  mov     r13, r9
0x180058331  mov     r15, r8
0x180058334  mov     [r11-70h], rsi
0x180058338  mov     r14, rcx
0x18005833b  mov     [rbp+var_8], rsi
0x18005833f  lea     rax, aCrpciomanagers_14; "CRpcIOManagerServer::Poke"
0x180058346  mov     [rbp+var_18], rsi
0x18005834a  lea     edx, [rsi+6]
0x18005834d  mov     [rbp+Block], rsi
0x180058351  lea     ecx, [rsi+1]
0x180058354  mov     [rbp+arg_0], esi
0x180058357  mov     r9d, 760h
0x18005835d  mov     [rbp+var_20], esi
0x180058360  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180058367  mov     [r11-78h], rax
0x18005836b  mov     edi, esi
0x18005836d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058372  mov     rax, [r14+58h]
0x180058376  cmp     [rax+28h], esi
0x180058379  jnz     short loc_18005839B
0x18005837b  cmp     [rax+3Ch], esi
0x18005837e  jz      short loc_18005839B
0x180058380  lea     r9, [rbp+arg_0]; int *
0x180058384  mov     [rsp+60h+var_40], r15; unsigned __int16 *
0x180058389  lea     r8, [rbp+var_20]; int *
0x18005838d  mov     rcx, r14; this
0x180058390  lea     rdx, [rbp+Block]; unsigned __int16 **
0x180058394  call    ?VerifyRpcSecuritySchannel@CRpcIOManagerServer@@AEAAJPEAPEAGPEAH1PEAG@Z; CRpcIOManagerServer::VerifyRpcSecuritySchannel(ushort * *,int *,int *,ushort *)
0x180058399  jmp     short loc_1800583B4
0x18005839b  lea     r9, [rbp+arg_0]; int *
0x18005839f  mov     [rsp+60h+var_40], r15; unsigned __int16 *
0x1800583a4  lea     r8, [rbp+var_20]; int *
0x1800583a8  mov     rcx, r14; this
0x1800583ab  lea     rdx, [rbp+Block]; unsigned __int16 **
0x1800583af  call    ?VerifyRpcSecurity@CRpcIOManagerServer@@AEAAJPEAPEAGPEAH1PEAG@Z; CRpcIOManagerServer::VerifyRpcSecurity(ushort * *,int *,int *,ushort *)
0x1800583b4  mov     r12, [rbp+Block]
0x1800583b8  mov     ebx, eax
0x1800583ba  test    eax, eax
0x1800583bc  jns     short loc_1800583FD
0x1800583be  lea     rax, aVerifyrpcsecur; "VerifyRpcSecurity Call Failed"
0x1800583c5  mov     r9d, 774h
0x1800583cb  mov     [rsp+60h+var_30], rax
0x1800583d0  mov     dword ptr [rsp+60h+var_38], ebx
0x1800583d4  mov     r15d, 1
0x1800583da  lea     rax, aCrpciomanagers_14; "CRpcIOManagerServer::Poke"
0x1800583e1  mov     edx, r15d
0x1800583e4  mov     [rsp+60h+var_40], rax
0x1800583e9  mov     ecx, r15d
0x1800583ec  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x1800583f3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800583f8  jmp     loc_18005874D
0x1800583fd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180058401  mov     rax, rcx
0x180058404  inc     rax
0x180058407  cmp     [r15+rax*2], si
0x18005840c  jnz     short loc_180058404
0x18005840e  dec     rax
0x180058411  cmp     rax, 0FFh
0x180058417  ja      loc_180058742
0x18005841d  inc     rcx
0x180058420  cmp     [r13+rcx*2+0], si
0x180058426  jnz     short loc_18005841D
0x180058428  cmp     rcx, 24h ; '$'
0x18005842c  jnz     loc_180058742
0x180058432  mov     rsi, [rbp+arg_28]
0x180058436  mov     ebx, [rbp+arg_20]
0x180058439  test    rsi, rsi
0x18005843c  jnz     short loc_180058446
0x18005843e  test    ebx, ebx
0x180058440  jnz     loc_180058742
0x180058446  cmp     [rbp+arg_8], 2
0x18005844a  jnz     loc_180058742
0x180058450  mov     [rsp+60h+var_28], r15
0x180058455  lea     rax, aClientHostS; "Client host = %s"
0x18005845c  mov     [rsp+60h+var_30], rax
0x180058461  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180058468  mov     edx, 4
0x18005846d  mov     [rsp+60h+var_38], rdi
0x180058472  lea     rax, aCrpciomanagers_14; "CRpcIOManagerServer::Poke"
0x180058479  mov     r9d, 782h
0x18005847f  mov     [rsp+60h+var_40], rax
0x180058484  lea     edi, [rdx-3]
0x180058487  mov     ecx, edi
0x180058489  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18005848e  mov     rax, [r14+8]
0x180058492  mov     edx, [rax+3Ch]
0x180058495  cmp     edx, 2
0x180058498  jz      short loc_1800584DC
0x18005849a  mov     dword ptr [rsp+60h+var_28], edx
0x18005849e  lea     rax, aCmNotYetInPost_0; "CM not yet in postinit state. (The curr"...
0x1800584a5  mov     [rsp+60h+var_30], rax
0x1800584aa  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x1800584b1  lea     rax, aCrpciomanagers_14; "CRpcIOManagerServer::Poke"
0x1800584b8  mov     esi, 80000123h
0x1800584bd  mov     dword ptr [rsp+60h+var_38], esi
0x1800584c1  mov     r9d, 78Bh
0x1800584c7  mov     edx, edi
0x1800584c9  mov     [rsp+60h+var_40], rax
0x1800584ce  mov     ecx, edi
0x1800584d0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800584d5  mov     eax, esi
0x1800584d7  jmp     loc_1800587AB
0x1800584dc  lea     rax, [rbp+var_8]
0x1800584e0  mov     r9d, ebx; unsigned int
0x1800584e3  mov     [rsp+60h+var_30], rax; struct INameObject **
0x1800584e8  mov     r8, r13; unsigned __int16 *
0x1800584eb  mov     [rsp+60h+var_38], r12; unsigned __int16 *
0x1800584f0  mov     rdx, r15; unsigned __int16 *
0x1800584f3  mov     rcx, r14; this
0x1800584f6  mov     [rsp+60h+var_40], rsi; unsigned __int8 *
0x1800584fb  call    ?FindOrCreateNameObject@CRpcIOManagerServer@@AEAAJPEBG0KPEAE0PEAPEAUINameObject@@@Z; CRpcIOManagerServer::FindOrCreateNameObject(ushort const *,ushort const *,ulong,uchar *,ushort const *,INameObject * *)
0x180058500  mov     rdi, [rbp+var_8]
0x180058504  mov     ebx, eax
0x180058506  test    eax, eax
0x180058508  jnz     loc_180058747
0x18005850e  mov     rax, [r14+58h]
0x180058512  cmp     [rax+3Ch], ebx
0x180058515  jnz     short loc_18005854B
0x180058517  mov     rax, [rdi]
0x18005851a  mov     r8, r12
0x18005851d  mov     r9d, [rbp+var_20]
0x180058521  mov     rdx, r15
0x180058524  mov     rcx, rdi
0x180058527  mov     rax, [rax+0A0h]
0x18005852e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058533  mov     ebx, eax
0x180058535  test    eax, eax
0x180058537  jns     short loc_18005854B
0x180058539  lea     rax, aCallToInameobj_0; "Call to INameObject::VerifyAndSetPartne"...
0x180058540  mov     r9d, 7A7h
0x180058546  jmp     loc_1800583CB
0x18005854b  mov     rax, [r14+58h]
0x18005854f  cmp     dword ptr [rax+28h], 0
0x180058553  jnz     loc_1800585F9
0x180058559  cmp     dword ptr [rax+3Ch], 0
0x18005855d  jnz     loc_1800585F9
0x180058563  mov     rax, [rdi]
0x180058566  mov     rcx, rdi
0x180058569  mov     rax, [rax+80h]
0x180058570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058575  test    eax, eax
0x180058577  mov     rcx, rdi
0x18005857a  mov     rax, [rdi]
0x18005857d  jz      short loc_1800585B1
0x18005857f  mov     rax, [rax+0A8h]
0x180058586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005858b  test    eax, eax
0x18005858d  jnz     short loc_1800585F9
0x18005858f  mov     eax, 80070005h
0x180058594  lea     rcx, aReceivedAPokeC; "Received a Poke call from a contact we "...
0x18005859b  mov     [rsp+60h+var_30], rcx
0x1800585a0  mov     ebx, eax
0x1800585a2  mov     dword ptr [rsp+60h+var_38], eax
0x1800585a6  mov     r9d, 7BBh
0x1800585ac  jmp     loc_1800583D4
0x1800585b1  mov     rax, [rax+90h]
0x1800585b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585bd  test    eax, eax
0x1800585bf  jz      short loc_1800585F9
0x1800585c1  mov     rax, [rdi]
0x1800585c4  mov     rcx, rdi
0x1800585c7  mov     rax, [rax+0B0h]
0x1800585ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585d3  test    eax, eax
0x1800585d5  jnz     short loc_1800585F9
0x1800585d7  mov     eax, 80070005h
0x1800585dc  lea     rcx, aReceivedAPokeC_0; "Received a Poke call from a contact we "...
0x1800585e3  mov     [rsp+60h+var_30], rcx
0x1800585e8  mov     ebx, eax
0x1800585ea  mov     dword ptr [rsp+60h+var_38], eax
0x1800585ee  mov     r9d, 7CBh
0x1800585f4  jmp     loc_1800583D4
0x1800585f9  mov     rcx, [r14+8]
0x1800585fd  mov     r13d, 158h
0x180058603  add     rcx, r13; this
0x180058606  call    ?AcquireWriterLock@CRWLock@@QEAAJXZ; CRWLock::AcquireWriterLock(void)
0x18005860b  mov     rcx, [r14+8]; this
0x18005860f  lea     r8, [rbp+var_18]; struct CSessionObject **
0x180058613  mov     rdx, rdi; struct INameObject *
0x180058616  call    ?LookForExistingSession@CConnectionManager@@AEAAXPEAUINameObject@@PEAPEAVCSessionObject@@@Z; CConnectionManager::LookForExistingSession(INameObject *,CSessionObject * *)
0x18005861b  mov     rsi, [rbp+var_18]
0x18005861f  test    rsi, rsi
0x180058622  jnz     loc_1800586C4
0x180058628  mov     rcx, [r14+8]; this
0x18005862c  lea     r8, [rbp+var_18]; struct CSessionObject **
0x180058630  mov     rdx, rdi; struct INameObject *
0x180058633  call    ?CreateANewSessionObject@CConnectionManager@@AEAAJPEAUINameObject@@PEAPEAVCSessionObject@@@Z; CConnectionManager::CreateANewSessionObject(INameObject *,CSessionObject * *)
0x180058638  lea     r15d, [rsi+1]
0x18005863c  mov     ebx, eax
0x18005863e  test    eax, eax
0x180058640  jz      short loc_18005865A
0x180058642  lea     rax, aCconnectionman; "CConnectionManager::CreateANewSessionOb"...
0x180058649  mov     r9d, 7E2h
0x18005864f  mov     [rsp+60h+var_30], rax
0x180058654  mov     dword ptr [rsp+60h+var_38], ebx
0x180058658  jmp     short loc_1800586A4
0x18005865a  mov     rax, [r14+8]
0x18005865e  cmp     [rax+44h], r15d
0x180058662  jnz     short loc_180058687
0x180058664  cmp     dword ptr [rax+3Ch], 2
0x180058668  jnz     short loc_180058687
0x18005866a  mov     rcx, [rbp+var_18]; this
0x18005866e  mov     [rcx+10h], r15d
0x180058672  mov     eax, [rbp+arg_0]
0x180058675  mov     [rcx+58Ch], eax
0x18005867b  call    ?StartMaintenance@CSessionObject@@QEAAJXZ; CSessionObject::StartMaintenance(void)
0x180058680  mov     ebx, eax
0x180058682  jmp     loc_180058734
0x180058687  mov     esi, 80000123h
0x18005868c  lea     rax, aSessionObjectC; "Session Object created, but CM was aske"...
0x180058693  mov     [rsp+60h+var_30], rax
0x180058698  mov     ebx, esi
0x18005869a  mov     dword ptr [rsp+60h+var_38], esi
0x18005869e  mov     r9d, 7FAh
0x1800586a4  lea     rax, aCrpciomanagers_14; "CRpcIOManagerServer::Poke"
0x1800586ab  mov     edx, r15d
0x1800586ae  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x1800586b5  mov     [rsp+60h+var_40], rax
0x1800586ba  mov     ecx, r15d
0x1800586bd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800586c2  jmp     short loc_180058734
0x1800586c4  cmp     dword ptr [rsi+4], 0
0x1800586c8  mov     r15d, 1
0x1800586ce  jz      short loc_180058734
0x1800586d0  mov     [rsi+10h], r15d
0x1800586d4  mov     eax, [rbp+arg_0]
0x1800586d7  mov     [rsi+58Ch], eax
0x1800586dd  mov     rcx, [rsi+80h]; hEvent
0x1800586e4  call    cs:__imp_SetEvent
0x1800586ea  mov     ecx, [rsi+68h]
0x1800586ed  lea     eax, [rcx-1]
0x1800586f0  cmp     eax, 2
0x1800586f3  jbe     short loc_180058734
0x1800586f5  mov     dword ptr [rsp+60h+var_28], ecx
0x1800586f9  lea     rax, aRecivedPokeFor; "Recived Poke for a new session, but old"...
0x180058700  mov     [rsp+60h+var_30], rax
0x180058705  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18005870c  mov     esi, 80000123h
0x180058711  lea     rax, aCrpciomanagers_14; "CRpcIOManagerServer::Poke"
0x180058718  mov     dword ptr [rsp+60h+var_38], esi
0x18005871c  mov     r9d, 81Ch
0x180058722  mov     edx, r15d
0x180058725  mov     [rsp+60h+var_40], rax
0x18005872a  mov     ecx, r15d
0x18005872d  mov     ebx, esi
0x18005872f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058734  mov     rcx, [r14+8]
0x180058738  add     rcx, r13; this
0x18005873b  call    ?ReleaseWriterLock@CRWLock@@QEAAJXZ; CRWLock::ReleaseWriterLock(void)
0x180058740  jmp     short loc_18005874D
0x180058742  mov     ebx, 80070057h
0x180058747  mov     r15d, 1
0x18005874d  lea     rax, aOut; "Out"
0x180058754  mov     r9d, 82Ch
0x18005875a  mov     [rsp+60h+var_30], rax
0x18005875f  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180058766  lea     rax, aCrpciomanagers_14; "CRpcIOManagerServer::Poke"
0x18005876d  mov     [rsp+60h+var_38], 0
0x180058776  mov     edx, 6
0x18005877b  mov     [rsp+60h+var_40], rax
0x180058780  mov     ecx, r15d
0x180058783  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058788  test    rdi, rdi
0x18005878b  jz      short loc_18005879C
0x18005878d  mov     rax, [rdi]
0x180058790  mov     rcx, rdi
0x180058793  mov     rax, [rax+10h]
0x180058797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005879c  test    r12, r12
0x18005879f  jz      short loc_1800587A9
0x1800587a1  mov     rcx, r12; Block
0x1800587a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800587a9  mov     eax, ebx
0x1800587ab  mov     rbx, [rsp+60h+arg_10]
0x1800587b3  add     rsp, 60h
0x1800587b7  pop     r15
0x1800587b9  pop     r14
0x1800587bb  pop     r13
0x1800587bd  pop     r12
0x1800587bf  pop     rdi
0x1800587c0  pop     rsi
0x1800587c1  pop     rbp
0x1800587c2  retn
```
