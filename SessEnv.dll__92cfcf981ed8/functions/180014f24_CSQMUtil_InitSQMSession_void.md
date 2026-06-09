# CSQMUtil::InitSQMSession(void)

- ea: `0x180014f24`
- end: `0x180015238`
- name: `?InitSQMSession@CSQMUtil@@SAJXZ`
- size: `788`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800407a8`
- `0x1800417cc`

## callees

- `0x180003f30`
- `0x180014f24`
- `0x18001a280`
- `0x180041b04`
- `0x180041f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001508d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001511d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001514f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001508d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001511d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001514f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151c0`
- `SQMAPI!SqmGetSession` at `0x1800150c3`
- `SQMAPI!SqmGetSession` at `0x1800150c3`
- `SQMAPI!SqmReadSharedMachineId` at `0x180014f91`
- `SQMAPI!SqmReadSharedMachineId` at `0x180014f91`
- `SQMAPI!SqmSetUserId` at `0x180015145`
- `SQMAPI!SqmSetUserId` at `0x180015145`
- `SQMAPI!SqmSetAppId` at `0x1800150e1`
- `SQMAPI!SqmSetAppId` at `0x1800150e1`
- `SQMAPI!SqmReadSharedUserId` at `0x18001504a`
- `SQMAPI!SqmReadSharedUserId` at `0x18001504a`
- `SQMAPI!SqmCreateNewId` at `0x180014fb1`
- `SQMAPI!SqmCreateNewId` at `0x180015058`
- `SQMAPI!SqmCreateNewId` at `0x180014fb1`
- `SQMAPI!SqmCreateNewId` at `0x180015058`
- `SQMAPI!SqmIsWindowsOptedIn` at `0x180014f4e`
- `SQMAPI!SqmIsWindowsOptedIn` at `0x180014f4e`
- `SQMAPI!SqmWriteSharedMachineId` at `0x180014fdf`
- `SQMAPI!SqmWriteSharedMachineId` at `0x180014fdf`
- `SQMAPI!SqmEndSession` at `0x1800151ec`
- `SQMAPI!SqmEndSession` at `0x1800151ec`
- `SQMAPI!SqmWriteSharedUserId` at `0x180015083`
- `SQMAPI!SqmWriteSharedUserId` at `0x180015083`
- `SQMAPI!SqmSetMachineId` at `0x180015113`
- `SQMAPI!SqmSetMachineId` at `0x180015113`
- `RPCRT4!RpcStringFreeW` at `0x18001520e`
- `RPCRT4!RpcStringFreeW` at `0x18001520e`
- `RPCRT4!UuidToStringW` at `0x180015018`
- `RPCRT4!UuidToStringW` at `0x180015018`

## string_xrefs

- `0x180014ffb`: `SqmWriteSharedMachineId() failed: 0x%x in %s`
- `0x180014fcc`: `SqmCreateNewId(machine ID) failed: 0x%x in %s`
- `0x180015073`: `SqmCreateNewId() failed failed: 0x%x in %s`
- `0x18001509f`: `SqmWriteSharedUserId() failed: 0x%x in %s`
- `0x180015196`: `sqmCommonPointMrg.AddCommonDatapoints() failed: 0x%x in %s`

## pseudocode

```c
__int64 CSQMUtil::InitSQMSession(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  const char *v2; // rdx
  signed int v3; // eax
  signed int v4; // eax
  RPC_STATUS v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  struct HSQMSESSION__ *Session; // rax
  signed int v9; // eax
  signed int v10; // eax
  struct HSQMSESSION__ *v11; // rdx
  signed int v12; // eax
  int v13; // eax
  signed int v14; // eax
  unsigned int *v16[2]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v17; // [rsp+30h] [rbp-40h]
  UUID Uuid; // [rsp+40h] [rbp-30h] BYREF
  __int128 v19; // [rsp+50h] [rbp-20h] BYREF

  Uuid = 0;
  v19 = 0;
  if ( !(unsigned int)SqmIsWindowsOptedIn() )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v2 = "SqmIsWindowsOptedIn() returned FALSE( not allowed to collect user data) failed: 0x%x in %s";
LABEL_5:
    _DbgPrintMessage(4, v2, v1, "CSQMUtil::InitSQMSession");
    goto LABEL_47;
  }
  if ( !(unsigned int)SqmReadSharedMachineId(&Uuid) )
  {
    if ( !(unsigned int)SqmCreateNewId(&Uuid) )
    {
      v3 = GetLastError();
      v1 = v3;
      if ( v3 > 0 )
        v1 = (unsigned __int16)v3 | 0x80070000;
      v2 = "SqmCreateNewId(machine ID) failed: 0x%x in %s";
      goto LABEL_5;
    }
    if ( !(unsigned int)SqmWriteSharedMachineId(&Uuid) )
    {
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      _DbgPrintMessage(4, "SqmWriteSharedMachineId() failed: 0x%x in %s", v4, "CSQMUtil::InitSQMSession");
    }
  }
  v5 = UuidToStringW(&Uuid, &CSQMUtil::m_pMachineIdStr);
  if ( v5 )
  {
    if ( v5 > 0 )
      v1 = (unsigned __int16)v5 | 0x80070000;
    else
      v1 = v5;
    _DbgPrintMessage(8, "MachineId: UuidToString FAILED with error 0x%x", v5);
    goto LABEL_47;
  }
  if ( !(unsigned int)SqmReadSharedUserId(&v19) )
  {
    if ( !(unsigned int)SqmCreateNewId(&v19) )
    {
      v6 = GetLastError();
      v1 = v6;
      if ( v6 > 0 )
        v1 = (unsigned __int16)v6 | 0x80070000;
      v2 = "SqmCreateNewId() failed failed: 0x%x in %s";
      goto LABEL_5;
    }
    if ( !(unsigned int)SqmWriteSharedUserId(&v19) )
    {
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      _DbgPrintMessage(4, "SqmWriteSharedUserId() failed: 0x%x in %s", v7, "CSQMUtil::InitSQMSession");
    }
  }
  Session = (struct HSQMSESSION__ *)SqmGetSession(L"TSSQM_session", 64000, 1);
  CSQMUtil::m_hSQMSession = Session;
  if ( !Session )
  {
    v14 = GetLastError();
    v1 = v14;
    if ( v14 > 0 )
      v1 = (unsigned __int16)v14 | 0x80070000;
LABEL_47:
    if ( (v1 & 0x80000000) == 0 )
      return v1;
    goto LABEL_48;
  }
  if ( !(unsigned int)SqmSetAppId(Session, 101457929) )
  {
    v9 = GetLastError();
    v1 = v9;
    if ( v9 > 0 )
      v1 = (unsigned __int16)v9 | 0x80070000;
    v2 = "SqmSetAppId() failed: 0x%x in %s";
    goto LABEL_5;
  }
  if ( !(unsigned int)SqmSetMachineId(CSQMUtil::m_hSQMSession, &Uuid) )
  {
    v10 = GetLastError();
    v1 = v10;
    if ( v10 > 0 )
      v1 = (unsigned __int16)v10 | 0x80070000;
    v2 = "SqmSetMachineId() failed: 0x%x in %s";
    goto LABEL_5;
  }
  if ( !(unsigned int)SqmSetUserId(CSQMUtil::m_hSQMSession, &v19) )
  {
    v12 = GetLastError();
    v1 = v12;
    if ( v12 > 0 )
      v1 = (unsigned __int16)v12 | 0x80070000;
    v2 = "SqmSetUserId() failed: 0x%x in %s";
    goto LABEL_5;
  }
  v16[1] = 0;
  v16[0] = 0;
  v17 = 0;
  v13 = CSqmCommonDataPointManager::AddCommonDatapoints(v16, v11);
  v1 = v13;
  if ( v13 >= 0 )
  {
    CSqmCommonDataPointManager::CleanAllDataPointsInMemory((CSqmCommonDataPointManager *)v16);
    return v1;
  }
  _DbgPrintMessage(8, "sqmCommonPointMrg.AddCommonDatapoints() failed: 0x%x in %s", v13, "CSQMUtil::InitSQMSession");
  CSqmCommonDataPointManager::CleanAllDataPointsInMemory((CSqmCommonDataPointManager *)v16);
LABEL_48:
  if ( CSQMUtil::m_hSQMSession )
  {
    SqmEndSession(CSQMUtil::m_hSQMSession, 0, 0);
    CSQMUtil::m_hSQMSession = 0;
  }
  if ( CSQMUtil::m_pMachineIdStr )
  {
    RpcStringFreeW(&CSQMUtil::m_pMachineIdStr);
    CSQMUtil::m_pMachineIdStr = 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180014f24  push    rbp
0x180014f26  push    rbx
0x180014f27  push    rsi
0x180014f28  push    rdi
0x180014f29  push    r14
0x180014f2b  mov     rbp, rsp
0x180014f2e  sub     rsp, 70h
0x180014f32  mov     rax, cs:__security_cookie
0x180014f39  xor     rax, rsp
0x180014f3c  mov     [rbp+var_10], rax
0x180014f40  xorps   xmm0, xmm0
0x180014f43  xorps   xmm1, xmm1
0x180014f46  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180014f4a  movups  [rbp+var_20], xmm1
0x180014f4e  call    cs:__imp_SqmIsWindowsOptedIn
0x180014f54  test    eax, eax
0x180014f56  jnz     short loc_180014F8D
0x180014f58  call    cs:__imp_GetLastError
0x180014f5e  mov     ebx, eax
0x180014f60  test    eax, eax
0x180014f62  jle     short loc_180014F6D
0x180014f64  movzx   ebx, ax
0x180014f67  or      ebx, 80070000h
0x180014f6d  lea     r9, aCsqmutilInitsq; "CSQMUtil::InitSQMSession"
0x180014f74  mov     ecx, 4; int
0x180014f79  lea     rdx, aSqmiswindowsop_0; "SqmIsWindowsOptedIn() returned FALSE( n"...
0x180014f80  mov     r8d, ebx
0x180014f83  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014f88  jmp     loc_1800151D1
0x180014f8d  lea     rcx, [rbp+Uuid]
0x180014f91  call    cs:__imp_SqmReadSharedMachineId
0x180014f97  mov     edi, 80070000h
0x180014f9c  lea     rsi, aCsqmutilInitsq; "CSQMUtil::InitSQMSession"
0x180014fa3  mov     r14d, 4
0x180014fa9  test    eax, eax
0x180014fab  jnz     short loc_18001500D
0x180014fad  lea     rcx, [rbp+Uuid]
0x180014fb1  call    cs:__imp_SqmCreateNewId
0x180014fb7  test    eax, eax
0x180014fb9  jnz     short loc_180014FDB
0x180014fbb  call    cs:__imp_GetLastError
0x180014fc1  mov     ebx, eax
0x180014fc3  test    eax, eax
0x180014fc5  jle     short loc_180014FCC
0x180014fc7  movzx   ebx, ax
0x180014fca  or      ebx, edi
0x180014fcc  lea     rdx, aSqmcreatenewid_1; "SqmCreateNewId(machine ID) failed: 0x%x"...
0x180014fd3  mov     r9, rsi
0x180014fd6  mov     ecx, r14d
0x180014fd9  jmp     short loc_180014F80
0x180014fdb  lea     rcx, [rbp+Uuid]
0x180014fdf  call    cs:__imp_SqmWriteSharedMachineId
0x180014fe5  test    eax, eax
0x180014fe7  jnz     short loc_18001500D
0x180014fe9  call    cs:__imp_GetLastError
0x180014fef  test    eax, eax
0x180014ff1  jle     short loc_180014FF8
0x180014ff3  movzx   eax, ax
0x180014ff6  or      eax, edi
0x180014ff8  mov     r9, rsi
0x180014ffb  lea     rdx, aSqmwriteshared_2; "SqmWriteSharedMachineId() failed: 0x%x "...
0x180015002  mov     r8d, eax
0x180015005  mov     ecx, r14d; int
0x180015008  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001500d  lea     rdx, ?m_pMachineIdStr@CSQMUtil@@0PEAGEA; StringUuid
0x180015014  lea     rcx, [rbp+Uuid]; Uuid
0x180015018  call    cs:__imp_UuidToStringW
0x18001501e  test    eax, eax
0x180015020  jz      short loc_180015046
0x180015022  jg      short loc_180015028
0x180015024  mov     ebx, eax
0x180015026  jmp     short loc_18001502D
0x180015028  movzx   ebx, ax
0x18001502b  or      ebx, edi
0x18001502d  mov     r8d, eax
0x180015030  lea     rdx, aMachineidUuidt; "MachineId: UuidToString FAILED with err"...
0x180015037  mov     ecx, 8; int
0x18001503c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015041  jmp     loc_1800151D1
0x180015046  lea     rcx, [rbp+var_20]
0x18001504a  call    cs:__imp_SqmReadSharedUserId
0x180015050  test    eax, eax
0x180015052  jnz     short loc_1800150B1
0x180015054  lea     rcx, [rbp+var_20]
0x180015058  call    cs:__imp_SqmCreateNewId
0x18001505e  test    eax, eax
0x180015060  jnz     short loc_18001507F
0x180015062  call    cs:__imp_GetLastError
0x180015068  mov     ebx, eax
0x18001506a  test    eax, eax
0x18001506c  jle     short loc_180015073
0x18001506e  movzx   ebx, ax
0x180015071  or      ebx, edi
0x180015073  lea     rdx, aSqmcreatenewid_0; "SqmCreateNewId() failed failed: 0x%x in"...
0x18001507a  jmp     loc_180014FD3
0x18001507f  lea     rcx, [rbp+var_20]
0x180015083  call    cs:__imp_SqmWriteSharedUserId
0x180015089  test    eax, eax
0x18001508b  jnz     short loc_1800150B1
0x18001508d  call    cs:__imp_GetLastError
0x180015093  test    eax, eax
0x180015095  jle     short loc_18001509C
0x180015097  movzx   eax, ax
0x18001509a  or      eax, edi
0x18001509c  mov     r9, rsi
0x18001509f  lea     rdx, aSqmwriteshared_1; "SqmWriteSharedUserId() failed: 0x%x in "...
0x1800150a6  mov     r8d, eax
0x1800150a9  mov     ecx, r14d; int
0x1800150ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800150b1  mov     edx, 0FA00h
0x1800150b6  lea     rcx, aTssqmSession; "TSSQM_session"
0x1800150bd  mov     r8d, 1
0x1800150c3  call    cs:__imp_SqmGetSession
0x1800150c9  mov     cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA, rax; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x1800150d0  test    rax, rax
0x1800150d3  jz      loc_1800151C0
0x1800150d9  mov     edx, 60C2009h
0x1800150de  mov     rcx, rax
0x1800150e1  call    cs:__imp_SqmSetAppId
0x1800150e7  test    eax, eax
0x1800150e9  jnz     short loc_180015108
0x1800150eb  call    cs:__imp_GetLastError
0x1800150f1  mov     ebx, eax
0x1800150f3  test    eax, eax
0x1800150f5  jle     short loc_1800150FC
0x1800150f7  movzx   ebx, ax
0x1800150fa  or      ebx, edi
0x1800150fc  lea     rdx, aSqmsetappidFai; "SqmSetAppId() failed: 0x%x in %s"
0x180015103  jmp     loc_180014FD3
0x180015108  mov     rcx, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x18001510f  lea     rdx, [rbp+Uuid]
0x180015113  call    cs:__imp_SqmSetMachineId
0x180015119  test    eax, eax
0x18001511b  jnz     short loc_18001513A
0x18001511d  call    cs:__imp_GetLastError
0x180015123  mov     ebx, eax
0x180015125  test    eax, eax
0x180015127  jle     short loc_18001512E
0x180015129  movzx   ebx, ax
0x18001512c  or      ebx, edi
0x18001512e  lea     rdx, aSqmsetmachinei_0; "SqmSetMachineId() failed: 0x%x in %s"
0x180015135  jmp     loc_180014FD3
0x18001513a  mov     rcx, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x180015141  lea     rdx, [rbp+var_20]
0x180015145  call    cs:__imp_SqmSetUserId
0x18001514b  test    eax, eax
0x18001514d  jnz     short loc_18001516C
0x18001514f  call    cs:__imp_GetLastError
0x180015155  mov     ebx, eax
0x180015157  test    eax, eax
0x180015159  jle     short loc_180015160
0x18001515b  movzx   ebx, ax
0x18001515e  or      ebx, edi
0x180015160  lea     rdx, aSqmsetuseridFa; "SqmSetUserId() failed: 0x%x in %s"
0x180015167  jmp     loc_180014FD3
0x18001516c  xorps   xmm0, xmm0
0x18001516f  mov     [rbp+var_48], 0
0x180015177  lea     rcx, [rbp+var_50]; this
0x18001517b  mov     [rbp+var_50], 0
0x180015183  movdqu  [rbp+var_40], xmm0
0x180015188  call    ?AddCommonDatapoints@CSqmCommonDataPointManager@@QEAAJPEAUHSQMSESSION__@@@Z; CSqmCommonDataPointManager::AddCommonDatapoints(HSQMSESSION__ *)
0x18001518d  mov     ebx, eax
0x18001518f  test    eax, eax
0x180015191  jns     short loc_1800151B5
0x180015193  mov     r9, rsi
0x180015196  lea     rdx, aSqmcommonpoint; "sqmCommonPointMrg.AddCommonDatapoints()"...
0x18001519d  mov     r8d, eax
0x1800151a0  mov     ecx, 8; int
0x1800151a5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800151aa  lea     rcx, [rbp+var_50]; this
0x1800151ae  call    ?CleanAllDataPointsInMemory@CSqmCommonDataPointManager@@AEAAXXZ; CSqmCommonDataPointManager::CleanAllDataPointsInMemory(void)
0x1800151b3  jmp     short loc_1800151D5
0x1800151b5  lea     rcx, [rbp+var_50]; this
0x1800151b9  call    ?CleanAllDataPointsInMemory@CSqmCommonDataPointManager@@AEAAXXZ; CSqmCommonDataPointManager::CleanAllDataPointsInMemory(void)
0x1800151be  jmp     short loc_18001521F
0x1800151c0  call    cs:__imp_GetLastError
0x1800151c6  mov     ebx, eax
0x1800151c8  test    eax, eax
0x1800151ca  jle     short loc_1800151D1
0x1800151cc  movzx   ebx, ax
0x1800151cf  or      ebx, edi
0x1800151d1  test    ebx, ebx
0x1800151d3  jns     short loc_18001521F
0x1800151d5  mov     rcx, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x1800151dc  test    rcx, rcx
0x1800151df  jz      short loc_1800151FD
0x1800151e1  mov     r9d, 8
0x1800151e7  xor     r8d, r8d
0x1800151ea  xor     edx, edx
0x1800151ec  call    cs:__imp_SqmEndSession
0x1800151f2  mov     cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA, 0; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x1800151fd  cmp     cs:?m_pMachineIdStr@CSQMUtil@@0PEAGEA, 0; ushort * CSQMUtil::m_pMachineIdStr
0x180015205  jz      short loc_18001521F
0x180015207  lea     rcx, ?m_pMachineIdStr@CSQMUtil@@0PEAGEA; String
0x18001520e  call    cs:__imp_RpcStringFreeW
0x180015214  mov     cs:?m_pMachineIdStr@CSQMUtil@@0PEAGEA, 0; ushort * CSQMUtil::m_pMachineIdStr
0x18001521f  mov     eax, ebx
0x180015221  mov     rcx, [rbp+var_10]
0x180015225  xor     rcx, rsp; StackCookie
0x180015228  call    __security_check_cookie
0x18001522d  add     rsp, 70h
0x180015231  pop     r14
0x180015233  pop     rdi
0x180015234  pop     rsi
0x180015235  pop     rbx
0x180015236  pop     rbp
0x180015237  retn
```
