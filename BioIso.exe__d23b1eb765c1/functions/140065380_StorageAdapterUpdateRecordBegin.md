# StorageAdapterUpdateRecordBegin

- ea: `0x140065380`
- end: `0x140065643`
- name: `StorageAdapterUpdateRecordBegin`
- size: `707`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x14000a420`
- `0x14000f9e0`
- `0x1400115c0`
- `0x14005c8b0`
- `0x14005c8c8`
- `0x140063374`
- `0x140063760`
- `0x140065380`
- `0x14007dcc8`
- `0x14007dd44`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400653ef`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400653ef`

## string_xrefs

- `0x1400653d3`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14006540c`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14006543b`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140065469`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140065494`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400654ca`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140065524`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14006555c`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140065596`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400655d1`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140065615`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageAdapterUpdateRecordBegin(__int64 a1, _DWORD *a2, char a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v8; // rsi
  int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // edi
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  __int64 v15; // rax
  int Count; // eax
  unsigned int v17; // ebx
  int v18; // eax
  unsigned int v19; // ebx
  int CurrentRecord; // eax
  unsigned int v21; // ebx
  unsigned __int64 v22; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v23[8]; // [rsp+28h] [rbp-30h] BYREF
  _BYTE v24[40]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v26; // [rsp+60h] [rbp+8h] BYREF

  v26 = a1;
  if ( a1 && a2 && a4 )
  {
    if ( *a2 != 2 )
    {
      if ( *a2 != 3 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6AD,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)0x80070057LL,
          v22);
        return 2147942487LL;
      }
      if ( !IsValidSid(a2 + 2) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6B2,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)0x80070057LL,
          v22);
        return 2147942487LL;
      }
      a1 = v26;
    }
    if ( a3 )
    {
      v8 = *(_QWORD *)(a1 + 64);
      if ( v8 )
      {
        v9 = StorageAdapterClearContext();
        v11 = v9;
        if ( v9 >= 0 )
        {
          try
          {
            LOBYTE(v10) = a3;
            v12 = StorageAdapterQueryBySubject(v26, a2, v10);
            v13 = v12;
            if ( v12 >= 0 )
            {
              v15 = lambda_bf25de864d02f14d70572f3f2647544a_::_lambda_bf25de864d02f14d70572f3f2647544a_(v23, &v26);
              wil::ScopeExit__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___(v24, v15);
              v22 = 0;
              Count = ResGetCount((struct _RESULT_SET *)(v8 + 48), &v22);
              v17 = Count;
              if ( Count >= 0 )
              {
                if ( v22 <= 1 )
                {
                  v18 = ResMoveToFirst((struct _RESULT_SET *)(v8 + 48));
                  v19 = v18;
                  if ( v18 >= 0 )
                  {
                    CurrentRecord = StorageAdapterGetCurrentRecord(v26, a4);
                    v21 = CurrentRecord;
                    if ( CurrentRecord >= 0 )
                    {
                      v24[8] = 0;
                      *(_BYTE *)(v8 + 80) = 1;
                      wil::details::ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___::_ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___(v24);
                      result = 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x6E0,
                        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                        (const char *)(unsigned int)CurrentRecord,
                        v22);
                      wil::details::ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___::_ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___(v24);
                      result = v21;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x6DB,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                      (const char *)(unsigned int)v18,
                      v22);
                    wil::details::ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___::_ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___(v24);
                    result = v19;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x6D5,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                    (const char *)0x8009801CLL,
                    v22);
                  wil::details::ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___::_ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___(v24);
                  result = 2148106268LL;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x6D1,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                  (const char *)(unsigned int)Count,
                  v22);
                wil::details::ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___::_ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___(v24);
                result = v17;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6C5,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                (const char *)(unsigned int)v12,
                v22);
              result = v13;
            }
          }
          catch ( ... )
          {
            LODWORD(v26) = wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x6E8,
                             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                             v14);
            return (unsigned int)v26;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6BF,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
            (const char *)(unsigned int)v9,
            v22);
          return v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6BB,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)0x8009800FLL,
          v22);
        return 2148106255LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B6,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)0x80070057LL,
        v22);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A8,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v22);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x140065380  mov     [rsp+arg_8], rbx
0x140065385  mov     [rsp+arg_10], rsi
0x14006538a  mov     [rsp+arg_0], rcx
0x14006538f  push    rdi
0x140065390  push    r14
0x140065392  push    r15
0x140065394  sub     rsp, 40h
0x140065398  mov     r15, r9
0x14006539b  mov     r14b, r8b
0x14006539e  mov     rbx, rdx
0x1400653a1  test    rcx, rcx
0x1400653a4  jz      loc_140065608
0x1400653aa  test    rdx, rdx
0x1400653ad  jz      loc_140065608
0x1400653b3  test    r9, r9
0x1400653b6  jz      loc_140065608
0x1400653bc  cmp     dword ptr [rdx], 2
0x1400653bf  jz      short loc_140065429
0x1400653c1  cmp     dword ptr [rdx], 3
0x1400653c4  jz      short loc_1400653EB
0x1400653c6  mov     rcx, [rsp+58h]; this
0x1400653cb  mov     ebx, 80070057h
0x1400653d0  mov     r9d, ebx; char *
0x1400653d3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400653da  mov     edx, 6ADh; void *
0x1400653df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400653e4  mov     eax, ebx
0x1400653e6  jmp     loc_14006562E
0x1400653eb  lea     rcx, [rdx+8]; pSid
0x1400653ef  call    cs:__imp_IsValidSid
0x1400653f6  nop     dword ptr [rax+rax+00h]
0x1400653fb  test    eax, eax
0x1400653fd  jnz     short loc_140065424
0x1400653ff  mov     rcx, [rsp+58h]; this
0x140065404  mov     ebx, 80070057h
0x140065409  mov     r9d, ebx; char *
0x14006540c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140065413  mov     edx, 6B2h; void *
0x140065418  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006541d  mov     eax, ebx
0x14006541f  jmp     loc_14006562E
0x140065424  mov     rcx, [rsp+58h+arg_0]
0x140065429  test    r14b, r14b
0x14006542c  jnz     short loc_140065453
0x14006542e  mov     rcx, [rsp+58h]; this
0x140065433  mov     ebx, 80070057h
0x140065438  mov     r9d, ebx; char *
0x14006543b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140065442  mov     edx, 6B6h; void *
0x140065447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006544c  mov     eax, ebx
0x14006544e  jmp     loc_14006562E
0x140065453  mov     rsi, [rcx+40h]
0x140065457  test    rsi, rsi
0x14006545a  jnz     short loc_140065481
0x14006545c  mov     rcx, [rsp+58h]; this
0x140065461  mov     ebx, 8009800Fh
0x140065466  mov     r9d, ebx; char *
0x140065469  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140065470  mov     edx, 6BBh; void *
0x140065475  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006547a  mov     eax, ebx
0x14006547c  jmp     loc_14006562E
0x140065481  call    StorageAdapterClearContext
0x140065486  mov     edi, eax
0x140065488  test    eax, eax
0x14006548a  jns     short loc_1400654AC
0x14006548c  mov     rcx, [rsp+58h]; this
0x140065491  mov     r9d, eax; char *
0x140065494  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14006549b  mov     edx, 6BFh; void *
0x1400654a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400654a5  mov     eax, edi
0x1400654a7  jmp     loc_14006562E
0x1400654ac  mov     r8b, r14b
0x1400654af  mov     rdx, rbx
0x1400654b2  mov     rcx, [rsp+58h+arg_0]
0x1400654b7  call    StorageAdapterQueryBySubject
0x1400654bc  mov     ebx, eax
0x1400654be  test    eax, eax
0x1400654c0  jns     short loc_1400654E2
0x1400654c2  mov     rcx, [rsp+58h]; this
0x1400654c7  mov     r9d, eax; char *
0x1400654ca  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400654d1  mov     edx, 6C5h; void *
0x1400654d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400654db  mov     eax, ebx
0x1400654dd  jmp     loc_14006562E
0x1400654e2  lea     rdx, [rsp+58h+arg_0]
0x1400654e7  lea     rcx, [rsp+58h+var_30]
0x1400654ec  call    _lambda_bf25de864d02f14d70572f3f2647544a____lambda_bf25de864d02f14d70572f3f2647544a_
0x1400654f1  mov     rdx, rax
0x1400654f4  lea     rcx, [rsp+58h+var_28]
0x1400654f9  call    wil__ScopeExit__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___
0x1400654fe  nop
0x1400654ff  mov     [rsp+58h+var_38], 0; int
0x140065508  lea     rdx, [rsp+58h+var_38]; unsigned __int64 *
0x14006550d  lea     rcx, [rsi+30h]; struct _RESULT_SET *
0x140065511  call    ?ResGetCount@@YAJPEAU_RESULT_SET@@PEA_K@Z; ResGetCount(_RESULT_SET *,unsigned __int64 *)
0x140065516  mov     ebx, eax
0x140065518  test    eax, eax
0x14006551a  jns     short loc_140065547
0x14006551c  mov     rcx, [rsp+58h]; this
0x140065521  mov     r9d, eax; char *
0x140065524  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14006552b  mov     edx, 6D1h; void *
0x140065530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140065535  nop
0x140065536  lea     rcx, [rsp+58h+var_28]
0x14006553b  call    wil__details__ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f______ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___
0x140065540  mov     eax, ebx
0x140065542  jmp     loc_14006562E
0x140065547  cmp     [rsp+58h+var_38], 1
0x14006554d  jbe     short loc_14006557F
0x14006554f  mov     rcx, [rsp+58h]; this
0x140065554  mov     ebx, 8009801Ch
0x140065559  mov     r9d, ebx; char *
0x14006555c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140065563  mov     edx, 6D5h; void *
0x140065568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006556d  nop
0x14006556e  lea     rcx, [rsp+58h+var_28]
0x140065573  call    wil__details__ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f______ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___
0x140065578  mov     eax, ebx
0x14006557a  jmp     loc_14006562E
0x14006557f  lea     rcx, [rsi+30h]; struct _RESULT_SET *
0x140065583  call    ?ResMoveToFirst@@YAJPEAU_RESULT_SET@@@Z; ResMoveToFirst(_RESULT_SET *)
0x140065588  mov     ebx, eax
0x14006558a  test    eax, eax
0x14006558c  jns     short loc_1400655B6
0x14006558e  mov     rcx, [rsp+58h]; this
0x140065593  mov     r9d, eax; char *
0x140065596  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14006559d  mov     edx, 6DBh; void *
0x1400655a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400655a7  nop
0x1400655a8  lea     rcx, [rsp+58h+var_28]
0x1400655ad  call    wil__details__ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f______ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___
0x1400655b2  mov     eax, ebx
0x1400655b4  jmp     short loc_14006562E
0x1400655b6  mov     rdx, r15
0x1400655b9  mov     rcx, [rsp+58h+arg_0]
0x1400655be  call    StorageAdapterGetCurrentRecord
0x1400655c3  mov     ebx, eax
0x1400655c5  test    eax, eax
0x1400655c7  jns     short loc_1400655F1
0x1400655c9  mov     rcx, [rsp+58h]; this
0x1400655ce  mov     r9d, eax; char *
0x1400655d1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400655d8  mov     edx, 6E0h; void *
0x1400655dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400655e2  nop
0x1400655e3  lea     rcx, [rsp+58h+var_28]
0x1400655e8  call    wil__details__ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f______ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___
0x1400655ed  mov     eax, ebx
0x1400655ef  jmp     short loc_14006562E
0x1400655f1  mov     [rsp+58h+var_20], 0
0x1400655f6  mov     byte ptr [rsi+50h], 1
0x1400655fa  lea     rcx, [rsp+58h+var_28]
0x1400655ff  call    wil__details__ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f______ScopeExitFn__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___
0x140065604  xor     eax, eax
0x140065606  jmp     short loc_14006562E
0x140065608  mov     rcx, [rsp+58h]; this
0x14006560d  mov     ebx, 80004003h
0x140065612  mov     r9d, ebx; char *
0x140065615  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14006561c  mov     edx, 6A8h; void *
0x140065621  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140065626  mov     eax, ebx
0x140065628  jmp     short loc_14006562E
0x14006562a  mov     eax, dword ptr [rsp+58h+arg_0]
0x14006562e  mov     rbx, [rsp+58h+arg_8]
0x140065633  mov     rsi, [rsp+58h+arg_10]
0x140065638  add     rsp, 40h
0x14006563c  pop     r15
0x14006563e  pop     r14
0x140065640  pop     rdi
0x140065641  retn
```
