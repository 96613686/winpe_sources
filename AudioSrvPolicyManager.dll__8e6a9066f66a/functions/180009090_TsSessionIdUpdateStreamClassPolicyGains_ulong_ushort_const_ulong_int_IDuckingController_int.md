# TsSessionIdUpdateStreamClassPolicyGains(ulong,ushort const *,ulong,int,IDuckingController *,int *)

- ea: `0x180009090`
- end: `0x18000965d`
- name: `?TsSessionIdUpdateStreamClassPolicyGains@@YAJKPEBGKHPEAUIDuckingController@@PEAH@Z`
- size: `1485`
- prototype: `__int64 __usercall@<rax>(DWORD SessionId@<ecx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, int@<r9d>, struct IDuckingController *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180022390`
- `0x180024bf0`

## callees

- `0x180006fdc`
- `0x180009090`
- `0x18000a384`
- `0x18000a580`
- `0x18000b1b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009204`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000929b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009204`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000929b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000918b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800092d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800093c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009503`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000950e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000918b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800092d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800093c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009503`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000950e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TsSessionIdUpdateStreamClassPolicyGains(
        DWORD SessionId,
        unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        struct IDuckingController *a5,
        int *a6)
{
  __int64 v6; // rbp
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  LPCRITICAL_SECTION v13; // r15
  int v14; // r14d
  unsigned int v15; // edi
  unsigned int v16; // ecx
  int v17; // r12d
  struct IDuckingController *v18; // r13
  _QWORD *i; // rbx
  _QWORD *v20; // rcx
  int *v21; // rsi
  __int64 v22; // rdi
  unsigned int j; // edx
  _QWORD *k; // rbx
  _QWORD *v25; // rcx
  _QWORD *v27; // rbx
  int v28; // edx
  int updated; // ebx
  __int64 v30; // rdx
  __int64 v31; // rdx
  _QWORD *v32; // rbx
  int v33; // edx
  __int64 v34; // rdx
  int v35; // eax
  int v36; // [rsp+20h] [rbp-78h]
  int v37; // [rsp+20h] [rbp-78h]
  int v38; // [rsp+20h] [rbp-78h]
  int v39; // [rsp+20h] [rbp-78h]
  int v40; // [rsp+20h] [rbp-78h]
  int v41; // [rsp+20h] [rbp-78h]
  int v42; // [rsp+20h] [rbp-78h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+40h] [rbp-58h]
  LPCRITICAL_SECTION v44[10]; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v46; // [rsp+A0h] [rbp+8h] BYREF
  unsigned __int16 *v47; // [rsp+A8h] [rbp+10h]
  int v48; // [rsp+B8h] [rbp+20h]

  v48 = a4;
  v47 = a2;
  v6 = a3;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)g_ApplicationManager + 32);
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)g_ApplicationManager + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_ApplicationManager + 32));
  v44[1] = v8;
  v44[0] = 0;
  EnterCriticalSection(&stru_180064458);
  v9 = HIBYTE(SessionId);
  _mm_lfence();
  v10 = *(_QWORD *)(qword_180064498
                  + 16
                  * (qword_1800644B0
                   & (0x100000001B3LL
                    * (v9
                     ^ (0x100000001B3LL
                      * (BYTE2(SessionId)
                       ^ (0x100000001B3LL
                        * (BYTE1(SessionId) ^ (0x100000001B3LL * ((unsigned __int8)SessionId ^ 0xCBF29CE484222325uLL)))))))))
                  + 8);
  if ( v10 == qword_180064488 )
  {
LABEL_6:
    v10 = 0;
  }
  else
  {
    v11 = *(_QWORD *)(qword_180064498
                    + 16
                    * (qword_1800644B0
                     & (0x100000001B3LL
                      * (v9
                       ^ (0x100000001B3LL
                        * (BYTE2(SessionId)
                         ^ (0x100000001B3LL
                          * (BYTE1(SessionId) ^ (0x100000001B3LL * ((unsigned __int8)SessionId ^ 0xCBF29CE484222325uLL))))))))));
    while ( SessionId != *(_DWORD *)(v10 + 16) )
    {
      if ( v10 == v11 )
        goto LABEL_6;
      v10 = *(_QWORD *)(v10 + 8);
    }
  }
  v12 = qword_180064488;
  if ( v10 )
    v12 = v10;
  if ( v12 == qword_180064488 )
  {
    LeaveCriticalSection(&stru_180064458);
    v35 = TsSessionCreate(SessionId, (struct TSSession **)v44);
    updated = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)(unsigned int)v35,
        v36);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A7,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)(unsigned int)updated,
        v42);
      if ( v8 )
        LeaveCriticalSection(v8);
      return (unsigned int)updated;
    }
    v13 = v44[0];
  }
  else
  {
    v13 = *(LPCRITICAL_SECTION *)(v12 + 24);
    LeaveCriticalSection(&stru_180064458);
  }
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 1;
  v18 = a5;
  while ( v16 < 0x18 )
  {
    LODWORD(v46) = 0;
    if ( qword_18004D530[24 * v6 + v16] )
    {
      for ( i = v13[26].LockSemaphore; ; i = (_QWORD *)*i )
      {
        if ( !i )
          goto LABEL_14;
        v20 = (_QWORD *)i[1];
        if ( v20[3] > 7u )
          v20 = (_QWORD *)*v20;
        if ( !(unsigned int)_o__wcsicmp(v20, qword_18004D530[24 * v6 + v15]) )
          break;
      }
      v27 = (_QWORD *)(i[1] + 32LL);
      v28 = *(_DWORD *)(*v27 + 24LL);
      if ( v28 )
      {
        if ( v28 == 1 )
        {
          updated = CStreamClassPolicyGains::UpdateStreamClassGainStage(
                      (LPCRITICAL_SECTION)((char *)v13 + 136),
                      v15,
                      1,
                      v27,
                      v48,
                      (__int64)v18,
                      (__int64)&v46);
          if ( updated < 0 )
          {
            v30 = 142;
            goto LABEL_44;
          }
        }
        else if ( v28 == 2 )
        {
          updated = CStreamClassPolicyGains::UpdateStreamClassGainStage(
                      v13 + 14,
                      v15,
                      1,
                      v27,
                      v48,
                      (__int64)v18,
                      (__int64)&v46);
          if ( updated < 0 )
          {
            v30 = 152;
            goto LABEL_44;
          }
        }
      }
      else
      {
        v44[0] = 0;
        CStreamClassPolicyGainsWrapper::GetStreamClassPolicyGainsForEndpoint(
          (CStreamClassPolicyGainsWrapper *)&v13[1].SpinCount,
          v47,
          (struct CStreamClassPolicyGains **)v44);
        updated = CStreamClassPolicyGains::UpdateStreamClassGainStage(
                    v44[0],
                    v15,
                    1,
                    v27,
                    v48,
                    (__int64)v18,
                    (__int64)&v46);
        if ( updated < 0 )
        {
          v30 = 132;
LABEL_44:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\streamclasspolicymanager.cpp",
            (const char *)(unsigned int)updated,
            v37);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x692,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
            (const char *)(unsigned int)updated,
            v38);
          v31 = 1708;
          goto LABEL_45;
        }
      }
      if ( v14 || (_DWORD)v46 )
        v14 = 1;
    }
LABEL_14:
    v16 = ++v15;
  }
  v21 = a6;
  if ( a6 )
    *a6 = v14;
  v22 = 0;
  for ( j = 0; ; j = v22 )
  {
    if ( j >= 0x18 )
    {
      if ( v21 )
      {
        if ( !*v21 && !v14 )
          v17 = 0;
        *v21 = v17;
      }
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return 0;
    }
    LODWORD(v46) = 0;
    if ( qword_18004E730[24 * v6 + j] )
      break;
LABEL_26:
    v22 = (unsigned int)(v22 + 1);
  }
  for ( k = v13[26].LockSemaphore; ; k = (_QWORD *)*k )
  {
    if ( !k )
      goto LABEL_26;
    v25 = (_QWORD *)k[1];
    if ( v25[3] > 7u )
      v25 = (_QWORD *)*v25;
    if ( !(unsigned int)_o__wcsicmp(v25, qword_18004E730[24 * v6 + v22]) )
      break;
  }
  v32 = (_QWORD *)(k[1] + 32LL);
  v33 = *(_DWORD *)(*v32 + 24LL);
  switch ( v33 )
  {
    case 0:
      v44[0] = 0;
      CStreamClassPolicyGainsWrapper::GetStreamClassPolicyGainsForEndpoint(
        (CStreamClassPolicyGainsWrapper *)&v13[1].SpinCount,
        v47,
        (struct CStreamClassPolicyGains **)v44);
      updated = CStreamClassPolicyGains::UpdateStreamClassGainStage(
                  v44[0],
                  v22,
                  0,
                  v32,
                  v48,
                  (__int64)v18,
                  (__int64)&v46);
      if ( updated < 0 )
      {
        v34 = 132;
        break;
      }
LABEL_55:
      if ( v14 || (_DWORD)v46 )
        v14 = 1;
      goto LABEL_26;
    case 1:
      updated = CStreamClassPolicyGains::UpdateStreamClassGainStage(
                  (LPCRITICAL_SECTION)((char *)v13 + 136),
                  v22,
                  0,
                  v32,
                  v48,
                  (__int64)v18,
                  (__int64)&v46);
      if ( updated >= 0 )
        goto LABEL_55;
      v34 = 142;
      break;
    case 2:
      updated = CStreamClassPolicyGains::UpdateStreamClassGainStage(
                  v13 + 14,
                  v22,
                  0,
                  v32,
                  v48,
                  (__int64)v18,
                  (__int64)&v46);
      if ( updated >= 0 )
        goto LABEL_55;
      v34 = 152;
      break;
    default:
      goto LABEL_55;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v34,
    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\streamclasspolicymanager.cpp",
    (const char *)(unsigned int)updated,
    v40);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x692,
    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
    (const char *)(unsigned int)updated,
    v41);
  v31 = 1715;
LABEL_45:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v31,
    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
    (const char *)(unsigned int)updated,
    v39);
  if ( lpCriticalSection )
  {
    LeaveCriticalSection(lpCriticalSection);
    return (unsigned int)updated;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180009090  mov     [rsp+arg_10], rbx
0x180009095  mov     [rsp+arg_18], r9d
0x18000909a  mov     [rsp+arg_8], rdx
0x18000909f  push    rbp
0x1800090a0  push    rsi
0x1800090a1  push    rdi
0x1800090a2  push    r12
0x1800090a4  push    r13
0x1800090a6  push    r14
0x1800090a8  push    r15
0x1800090aa  sub     rsp, 60h
0x1800090ae  mov     ebp, r8d
0x1800090b1  mov     ebx, ecx
0x1800090b3  mov     rdi, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x1800090ba  add     rdi, 20h ; ' '
0x1800090be  mov     [rsp+98h+lpCriticalSection], rdi
0x1800090c3  mov     rcx, rdi; lpCriticalSection
0x1800090c6  call    cs:__imp_EnterCriticalSection
0x1800090cc  mov     [rsp+98h+var_48], rdi
0x1800090d1  mov     [rsp+98h+var_50], 0
0x1800090da  lea     rcx, stru_180064458; lpCriticalSection
0x1800090e1  call    cs:__imp_EnterCriticalSection
0x1800090e7  mov     r8d, ebx
0x1800090ea  shr     r8d, 18h
0x1800090ee  mov     eax, ebx
0x1800090f0  shr     eax, 10h
0x1800090f3  movzx   edx, al
0x1800090f6  mov     eax, ebx
0x1800090f8  shr     eax, 8
0x1800090fb  movzx   ecx, al
0x1800090fe  movzx   r9d, bl
0x180009102  lfence
0x180009105  mov     rax, 0CBF29CE484222325h
0x18000910f  xor     r9, rax
0x180009112  mov     rax, 100000001B3h
0x18000911c  imul    r9, rax
0x180009120  xor     r9, rcx
0x180009123  imul    r9, rax
0x180009127  xor     r9, rdx
0x18000912a  imul    r9, rax
0x18000912e  xor     r9, r8
0x180009131  imul    r9, rax
0x180009135  and     r9, cs:qword_1800644B0
0x18000913c  add     r9, r9
0x18000913f  mov     rax, cs:qword_180064498
0x180009146  mov     rcx, [rax+r9*8+8]
0x18000914b  mov     rdx, cs:qword_180064488
0x180009152  cmp     rcx, rdx
0x180009155  jz      short loc_18000916B
0x180009157  mov     r8, [rax+r9*8]
0x18000915b  cmp     ebx, [rcx+10h]
0x18000915e  jz      short loc_18000916D
0x180009160  cmp     rcx, r8
0x180009163  jz      short loc_18000916B
0x180009165  mov     rcx, [rcx+8]
0x180009169  jmp     short loc_18000915B
0x18000916b  xor     ecx, ecx
0x18000916d  mov     rax, rdx
0x180009170  test    rcx, rcx
0x180009173  cmovnz  rax, rcx
0x180009177  lea     rcx, stru_180064458; lpCriticalSection
0x18000917e  cmp     rax, rdx
0x180009181  jz      loc_18000950E
0x180009187  mov     r15, [rax+18h]
0x18000918b  call    cs:__imp_LeaveCriticalSection
0x180009191  xor     r14d, r14d
0x180009194  lea     rdx, qword_18004D530
0x18000919b  xor     edi, edi
0x18000919d  xor     ecx, ecx
0x18000919f  mov     r12d, 1
0x1800091a5  mov     r13, [rsp+98h+arg_20]
0x1800091ad  nop     dword ptr [rax]
0x1800091b0  cmp     ecx, 18h
0x1800091b3  jnb     short loc_18000921E
0x1800091b5  mov     dword ptr [rsp+98h+arg_0], 0
0x1800091c0  lea     rsi, ds:0[rbp*2]
0x1800091c8  add     rsi, rbp
0x1800091cb  shl     rsi, 3
0x1800091cf  mov     eax, ecx
0x1800091d1  add     rax, rsi
0x1800091d4  cmp     qword ptr [rdx+rax*8], 0
0x1800091d9  jnz     short loc_1800091E1
0x1800091db  inc     edi
0x1800091dd  mov     ecx, edi
0x1800091df  jmp     short loc_1800091B0
0x1800091e1  mov     rbx, [r15+428h]
0x1800091e8  test    rbx, rbx
0x1800091eb  jz      short loc_1800091DB
0x1800091ed  mov     eax, edi
0x1800091ef  add     rax, rsi
0x1800091f2  mov     rcx, [rbx+8]
0x1800091f6  cmp     qword ptr [rcx+18h], 7
0x1800091fb  jbe     short loc_180009200
0x1800091fd  mov     rcx, [rcx]
0x180009200  mov     rdx, [rdx+rax*8]
0x180009204  call    cs:__imp__o__wcsicmp
0x18000920a  test    eax, eax
0x18000920c  jz      loc_1800092F4
0x180009212  mov     rbx, [rbx]
0x180009215  lea     rdx, qword_18004D530
0x18000921c  jmp     short loc_1800091E8
0x18000921e  mov     rsi, [rsp+98h+arg_28]
0x180009226  test    rsi, rsi
0x180009229  jz      short loc_18000922E
0x18000922b  mov     [rsi], r14d
0x18000922e  lea     r8, qword_18004E730
0x180009235  xor     edi, edi
0x180009237  xor     edx, edx
0x180009239  nop     dword ptr [rax+00000000h]
0x180009240  cmp     edx, 18h
0x180009243  jnb     short loc_1800092B5
0x180009245  mov     dword ptr [rsp+98h+arg_0], 0
0x180009250  lea     rcx, ds:0[rbp*2]
0x180009258  add     rcx, rbp
0x18000925b  mov     eax, edx
0x18000925d  lea     rcx, [rax+rcx*8]
0x180009261  cmp     qword ptr [r8+rcx*8], 0
0x180009266  jnz     short loc_18000926E
0x180009268  inc     edi
0x18000926a  mov     edx, edi
0x18000926c  jmp     short loc_180009240
0x18000926e  mov     rbx, [r15+428h]
0x180009275  test    rbx, rbx
0x180009278  jz      short loc_180009268
0x18000927a  lea     rcx, ds:0[rbp*2]
0x180009282  add     rcx, rbp
0x180009285  lea     rcx, [rdi+rcx*8]
0x180009289  mov     rdx, [r8+rcx*8]
0x18000928d  mov     rcx, [rbx+8]
0x180009291  cmp     qword ptr [rcx+18h], 7
0x180009296  jbe     short loc_18000929B
0x180009298  mov     rcx, [rcx]
0x18000929b  call    cs:__imp__o__wcsicmp
0x1800092a1  test    eax, eax
0x1800092a3  jz      loc_1800093F2
0x1800092a9  mov     rbx, [rbx]
0x1800092ac  lea     r8, qword_18004E730
0x1800092b3  jmp     short loc_180009275
0x1800092b5  test    rsi, rsi
0x1800092b8  jz      short loc_1800092CA
0x1800092ba  cmp     dword ptr [rsi], 0
0x1800092bd  jnz     short loc_1800092C7
0x1800092bf  test    r14d, r14d
0x1800092c2  jnz     short loc_1800092C7
0x1800092c4  xor     r12d, r12d
0x1800092c7  mov     [rsi], r12d
0x1800092ca  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x1800092cf  test    rcx, rcx
0x1800092d2  jz      short loc_1800092DA
0x1800092d4  call    cs:__imp_LeaveCriticalSection
0x1800092da  xor     eax, eax
0x1800092dc  mov     rbx, [rsp+98h+arg_10]
0x1800092e4  add     rsp, 60h
0x1800092e8  pop     r15
0x1800092ea  pop     r14
0x1800092ec  pop     r13
0x1800092ee  pop     r12
0x1800092f0  pop     rdi
0x1800092f1  pop     rsi
0x1800092f2  pop     rbp
0x1800092f3  retn
0x1800092f4  lea     rcx, [r15+48h]; this
0x1800092f8  mov     rbx, [rbx+8]
0x1800092fc  add     rbx, 20h ; ' '
0x180009300  mov     rax, [rbx]
0x180009303  mov     edx, [rax+18h]
0x180009306  test    edx, edx
0x180009308  jnz     loc_180009530
0x18000930e  mov     [rsp+98h+var_50], 0
0x180009317  lea     r8, [rsp+98h+var_50]; struct CStreamClassPolicyGains **
0x18000931c  mov     rdx, [rsp+98h+arg_8]; unsigned __int16 *
0x180009324  call    ?GetStreamClassPolicyGainsForEndpoint@CStreamClassPolicyGainsWrapper@@AEAAXPEBGPEAPEAVCStreamClassPolicyGains@@@Z; CStreamClassPolicyGainsWrapper::GetStreamClassPolicyGainsForEndpoint(ushort const *,CStreamClassPolicyGains * *)
0x180009329  lea     rax, [rsp+98h+arg_0]
0x180009331  mov     [rsp+98h+var_68], rax; __int64
0x180009336  mov     [rsp+98h+var_70], r13; __int64
0x18000933b  mov     eax, [rsp+98h+arg_18]
0x180009342  mov     [rsp+98h+var_78], eax; int
0x180009346  mov     r9, rbx
0x180009349  movzx   r8d, r12b
0x18000934d  mov     edx, edi
0x18000934f  mov     rcx, [rsp+98h+var_50]; lpCriticalSection
0x180009354  call    ?UpdateStreamClassGainStage@CStreamClassPolicyGains@@QEAAJK_NAEBV?$shared_ptr@VDuckingDescriptor@@@std@@HPEAUIDuckingController@@PEAH@Z; CStreamClassPolicyGains::UpdateStreamClassGainStage(ulong,bool,std::shared_ptr<DuckingDescriptor> const &,int,IDuckingController *,int *)
0x180009359  mov     ebx, eax
0x18000935b  test    eax, eax
0x18000935d  jns     short loc_1800093D2
0x18000935f  mov     edx, 84h; void *
0x180009364  lea     r8, aClientcoreMult_9; "clientcore\\multimedia\\audiocore\\serv"...
0x18000936b  mov     rcx, [rsp+98h]; this
0x180009373  mov     r9d, ebx; char *
0x180009376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000937b  mov     rcx, [rsp+98h]; this
0x180009383  mov     r9d, ebx; char *
0x180009386  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18000938d  mov     edx, 692h; void *
0x180009392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009397  mov     edx, 6ACh; void *
0x18000939c  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x1800093a3  mov     r9d, ebx; char *
0x1800093a6  mov     rcx, [rsp+98h]; this
0x1800093ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800093b3  nop
0x1800093b4  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x1800093b9  test    rcx, rcx
0x1800093bc  jnz     short loc_1800093C5
0x1800093be  mov     eax, ebx
0x1800093c0  jmp     loc_1800092DC
0x1800093c5  call    cs:__imp_LeaveCriticalSection
0x1800093cb  mov     eax, ebx
0x1800093cd  jmp     loc_1800092DC
0x1800093d2  test    r14d, r14d
0x1800093d5  jnz     short loc_1800093ED
0x1800093d7  cmp     dword ptr [rsp+98h+arg_0], r14d
0x1800093df  jnz     short loc_1800093ED
0x1800093e1  lea     rdx, qword_18004D530
0x1800093e8  jmp     loc_1800091DB
0x1800093ed  mov     r14d, r12d
0x1800093f0  jmp     short loc_1800093E1
0x1800093f2  lea     rcx, [r15+48h]; this
0x1800093f6  mov     rbx, [rbx+8]
0x1800093fa  add     rbx, 20h ; ' '
0x1800093fe  mov     rax, [rbx]
0x180009401  mov     edx, [rax+18h]
0x180009404  test    edx, edx
0x180009406  jnz     loc_1800095C7
0x18000940c  mov     [rsp+98h+var_50], 0
0x180009415  lea     r8, [rsp+98h+var_50]; struct CStreamClassPolicyGains **
0x18000941a  mov     rdx, [rsp+98h+arg_8]; unsigned __int16 *
0x180009422  call    ?GetStreamClassPolicyGainsForEndpoint@CStreamClassPolicyGainsWrapper@@AEAAXPEBGPEAPEAVCStreamClassPolicyGains@@@Z; CStreamClassPolicyGainsWrapper::GetStreamClassPolicyGainsForEndpoint(ushort const *,CStreamClassPolicyGains * *)
0x180009427  lea     rax, [rsp+98h+arg_0]
0x18000942f  mov     [rsp+98h+var_68], rax; __int64
0x180009434  mov     [rsp+98h+var_70], r13; __int64
0x180009439  mov     eax, [rsp+98h+arg_18]
0x180009440  mov     [rsp+98h+var_78], eax; int
0x180009444  mov     r9, rbx
0x180009447  xor     r8d, r8d
0x18000944a  mov     edx, edi
0x18000944c  mov     rcx, [rsp+98h+var_50]; lpCriticalSection
0x180009451  call    ?UpdateStreamClassGainStage@CStreamClassPolicyGains@@QEAAJK_NAEBV?$shared_ptr@VDuckingDescriptor@@@std@@HPEAUIDuckingController@@PEAH@Z; CStreamClassPolicyGains::UpdateStreamClassGainStage(ulong,bool,std::shared_ptr<DuckingDescriptor> const &,int,IDuckingController *,int *)
0x180009456  mov     ebx, eax
0x180009458  test    eax, eax
0x18000945a  jns     short loc_18000949E
0x18000945c  mov     edx, 84h; void *
0x180009461  lea     r8, aClientcoreMult_9; "clientcore\\multimedia\\audiocore\\serv"...
0x180009468  mov     rcx, [rsp+98h]; this
0x180009470  mov     r9d, ebx; char *
0x180009473  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009478  mov     rcx, [rsp+98h]; this
0x180009480  mov     r9d, ebx; char *
0x180009483  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18000948a  mov     edx, 692h; void *
0x18000948f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009494  mov     edx, 6B3h
0x180009499  jmp     loc_18000939C
0x18000949e  test    r14d, r14d
0x1800094a1  jnz     short loc_1800094B9
0x1800094a3  cmp     dword ptr [rsp+98h+arg_0], r14d
0x1800094ab  jnz     short loc_1800094B9
0x1800094ad  lea     r8, qword_18004E730
0x1800094b4  jmp     loc_180009268
0x1800094b9  mov     r14d, r12d
0x1800094bc  jmp     short loc_1800094AD
0x1800094be  mov     rcx, [rsp+98h]; this
0x1800094c6  mov     r9d, ebx; char *
0x1800094c9  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x1800094d0  mov     edx, 43Ch; void *
0x1800094d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094da  mov     rcx, [rsp+98h]; this
0x1800094e2  mov     r9d, ebx; char *
0x1800094e5  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x1800094ec  mov     edx, 6A7h; void *
0x1800094f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094f6  nop
0x1800094f7  test    rdi, rdi
0x1800094fa  jz      loc_1800093BE
0x180009500  mov     rcx, rdi; lpCriticalSection
0x180009503  call    cs:__imp_LeaveCriticalSection
0x180009509  jmp     loc_1800093BE
0x18000950e  call    cs:__imp_LeaveCriticalSection
0x180009514  lea     rdx, [rsp+98h+var_50]; struct TSSession **
0x180009519  mov     ecx, ebx; SessionId
0x18000951b  call    ?TsSessionCreate@@YAJKPEAPEAVTSSession@@@Z; TsSessionCreate(ulong,TSSession * *)
0x180009520  mov     ebx, eax
0x180009522  test    eax, eax
0x180009524  js      short loc_1800094BE
0x180009526  mov     r15, [rsp+98h+var_50]
0x18000952b  jmp     loc_180009191
0x180009530  cmp     edx, r12d
0x180009533  jnz     short loc_180009578
0x180009535  add     rcx, 40h ; '@'; lpCriticalSection
0x180009539  lea     rax, [rsp+98h+arg_0]
0x180009541  mov     [rsp+98h+var_68], rax; __int64
0x180009546  mov     [rsp+98h+var_70], r13; __int64
0x18000954b  mov     eax, [rsp+98h+arg_18]
0x180009552  mov     [rsp+98h+var_78], eax; int
0x180009556  mov     r9, rbx
0x180009559  movzx   r8d, r12b
0x18000955d  mov     edx, edi
0x18000955f  call    ?UpdateStreamClassGainStage@CStreamClassPolicyGains@@QEAAJK_NAEBV?$shared_ptr@VDuckingDescriptor@@@std@@HPEAUIDuckingController@@PEAH@Z; CStreamClassPolicyGains::UpdateStreamClassGainStage(ulong,bool,std::shared_ptr<DuckingDescriptor> const &,int,IDuckingController *,int *)
0x180009564  mov     ebx, eax
0x180009566  test    eax, eax
  ... truncated ...
```
