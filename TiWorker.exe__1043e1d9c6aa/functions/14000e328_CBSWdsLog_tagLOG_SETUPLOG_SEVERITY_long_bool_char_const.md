# CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)

- ea: `0x14000e328`
- end: `0x14000e548`
- name: `?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ`
- size: `544`
- prototype: `void(unsigned int, int, size_t *, const char *, ...)`
- caller_count: `40`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140006644`
- `0x140006700`
- `0x1400067a0`
- `0x140006d68`
- `0x140006e70`
- `0x140007004`
- `0x140007228`
- `0x14000766c`
- `0x1400076d4`
- `0x140007758`
- `0x1400079e8`
- `0x140007d40`
- `0x140007da0`
- `0x140007eb8`
- `0x140008730`
- `0x1400087d0`
- `0x1400088b0`
- `0x140008910`
- `0x140008970`
- `0x140008a10`
- `0x140008a70`
- `0x140008ad0`
- `0x140008b30`
- `0x140008c10`
- `0x140009f04`
- `0x14000a5b4`
- `0x14000a884`
- `0x14000a900`
- `0x14000a974`
- `0x14000ab58`
- `0x14000ade4`
- `0x14000af9c`
- `0x14000b174`
- `0x14000b258`
- `0x14000b2f8`
- `0x14000b9b0`
- `0x14000c648`
- `0x14000c6bc`
- `0x14000caa0`
- `0x14000cd48`

## callees

- `0x140002310`
- `0x14000e27c`
- `0x14000e328`
- `0x14000ed0c`
- `0x14000f428`
- `0x14000f49c`
- `0x14002b010`

## pseudocode

```c
void CBSWdsLog(unsigned int a1, int a2, size_t *a3, const char *a4, ...)
{
  char v4; // bl
  const char *v7; // rax
  char *v8; // rdx
  const char *v9; // rax
  __int64 v10; // rax
  enum tagLOGRESULT (__high *v11)(struct tagLOG_PARTIAL_MSG *, unsigned int, const char *, const char *, unsigned int, const char *, const char *, void *, unsigned int, void *, unsigned int); // rdi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  enum tagLOGRESULT (__high *v14)(struct tagLOG_PARTIAL_MSG *, unsigned int, const char *, const char *, unsigned int, const char *, const char *, void *, unsigned int, void *, unsigned int); // rdi
  struct tagLOG_PARTIAL_MSG *v15; // rbx
  void *v16; // [rsp+38h] [rbp-C8h]
  void *v17; // [rsp+38h] [rbp-C8h]
  char pszDest[1024]; // [rsp+70h] [rbp-90h] BYREF
  char v19[1024]; // [rsp+470h] [rbp+370h] BYREF
  const char *pszFormat; // [rsp+8D8h] [rbp+7D8h]
  va_list va; // [rsp+8E0h] [rbp+7E0h] BYREF

  va_start(va, a4);
  pszFormat = a4;
  v4 = (char)a3;
  if ( vpfnCustomLogging )
  {
    if ( StringVPrintfWorkerA(pszDest, 0x400u, a3, a4, va) >= 0 )
    {
      if ( !v4 )
      {
        v8 = pszDest;
        goto LABEL_7;
      }
      v7 = CBSTextizeHresult(a2);
      if ( StringCchPrintfA(v19, 0x400u, "%hs [HRESULT = 0x%08x - %hs]", pszDest, a2, v7) >= 0 )
      {
        v8 = v19;
LABEL_7:
        ((void (__fastcall *)(_QWORD, char *))vpfnCustomLogging)(a1, v8);
      }
    }
    a4 = pszFormat;
  }
  if ( vpfnWdsSetupLogMessageA && vpfnConstructPartialMsgVA && vpfnCurrentIP )
  {
    if ( v4 )
    {
      if ( StringVPrintfWorkerA(pszDest, 0x400u, a3, a4, va) >= 0 )
      {
        v9 = CBSTextizeHresult(a2);
        v10 = HresultMsg(a1, "%hs [HRESULT = 0x%08x - %hs]", pszDest, a2, v9);
        v11 = vpfnWdsSetupLogMessageA;
        v12 = v10;
        v16 = vpfnCurrentIP();
        ((void (__fastcall *)(__int64, __int64, const char *, _QWORD, int, const char *, const char *, void *, _DWORD, _QWORD, _DWORD))v11)(
          v12,
          0x20000,
          "D",
          0,
          1308,
          "onecore\\base\\cbs\\util\\cbsutil.cpp",
          "CBSWdsLog",
          v16,
          0,
          0,
          0);
      }
    }
    else
    {
      v13 = vpfnConstructPartialMsgVA(a1, a4, va);
      v14 = vpfnWdsSetupLogMessageA;
      v15 = v13;
      v17 = vpfnCurrentIP();
      ((void (__fastcall *)(struct tagLOG_PARTIAL_MSG *, __int64, const char *, _QWORD, int, const char *, const char *, void *, _DWORD, _QWORD, _DWORD))v14)(
        v15,
        0x20000,
        "D",
        0,
        1317,
        "onecore\\base\\cbs\\util\\cbsutil.cpp",
        "CBSWdsLog",
        v17,
        0,
        0,
        0);
    }
  }
}

```

## disassembly

```asm
0x14000e328  mov     [rsp-8+pszFormat], r9
0x14000e32d  push    rbp
0x14000e32e  push    rbx
0x14000e32f  push    rsi
0x14000e330  push    rdi
0x14000e331  push    r12
0x14000e333  push    r15
0x14000e335  lea     rbp, [rsp-788h]
0x14000e33d  sub     rsp, 888h
0x14000e344  mov     rax, cs:__security_cookie
0x14000e34b  xor     rax, rsp
0x14000e34e  mov     [rbp+7B0h+var_40], rax
0x14000e355  cmp     cs:?vpfnCustomLogging@@3P6AXIPEBD@ZEA, 0; void (*vpfnCustomLogging)(uint,char const *)
0x14000e35d  lea     r12, [rbp+7B0h+arg_20]
0x14000e364  mov     bl, r8b
0x14000e367  mov     [rsp+8B0h+var_850], 0
0x14000e370  mov     esi, edx
0x14000e372  mov     edi, ecx
0x14000e374  mov     r15d, 400h
0x14000e37a  jz      short loc_14000E3E8
0x14000e37c  mov     edx, r15d; cchDest
0x14000e37f  mov     [rsp+8B0h+argList], r12; argList
0x14000e384  lea     rcx, [rsp+8B0h+pszDest]; pszDest
0x14000e389  call    StringVPrintfWorkerA
0x14000e38e  test    eax, eax
0x14000e390  js      short loc_14000E3E1
0x14000e392  test    bl, bl
0x14000e394  jz      short loc_14000E3CE
0x14000e396  mov     ecx, esi; int
0x14000e398  call    ?CBSTextizeHresult@@YAPEBDJ@Z; CBSTextizeHresult(long)
0x14000e39d  mov     [rsp+8B0h+var_888], rax
0x14000e3a2  lea     r9, [rsp+8B0h+pszDest]
0x14000e3a7  lea     r8, aHsHresult0x08x; "%hs [HRESULT = 0x%08x - %hs]"
0x14000e3ae  mov     dword ptr [rsp+8B0h+argList], esi
0x14000e3b2  mov     edx, r15d; unsigned __int64
0x14000e3b5  lea     rcx, [rbp+7B0h+var_440]; char *
0x14000e3bc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000e3c1  test    eax, eax
0x14000e3c3  js      short loc_14000E3E1
0x14000e3c5  lea     rdx, [rbp+7B0h+var_440]
0x14000e3cc  jmp     short loc_14000E3D3
0x14000e3ce  lea     rdx, [rsp+8B0h+pszDest]
0x14000e3d3  mov     rax, cs:?vpfnCustomLogging@@3P6AXIPEBD@ZEA; void (*vpfnCustomLogging)(uint,char const *)
0x14000e3da  mov     ecx, edi
0x14000e3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3e1  mov     r9, [rbp+7B0h+pszFormat]; pszFormat
0x14000e3e8  cmp     cs:?vpfnWdsSetupLogMessageA@@3P6A?AW4tagLOGRESULT@@PEAUtagLOG_PARTIAL_MSG@@KPEBD1K11PEAXK2I@ZEA, 0; tagLOGRESULT (*vpfnWdsSetupLogMessageA)(tagLOG_PARTIAL_MSG *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint)
0x14000e3f0  jz      loc_14000E529
0x14000e3f6  mov     rax, cs:?vpfnConstructPartialMsgVA@@3P6APEAUtagLOG_PARTIAL_MSG@@KPEBDPEAD@ZEA; tagLOG_PARTIAL_MSG * (*vpfnConstructPartialMsgVA)(ulong,char const *,char *)
0x14000e3fd  test    rax, rax
0x14000e400  jz      loc_14000E529
0x14000e406  cmp     cs:?vpfnCurrentIP@@3P6APEAXXZEA, 0; void * (*vpfnCurrentIP)(void)
0x14000e40e  jz      loc_14000E529
0x14000e414  test    bl, bl
0x14000e416  jz      loc_14000E4AE
0x14000e41c  mov     rdx, r15; cchDest
0x14000e41f  mov     [rsp+8B0h+argList], r12; argList
0x14000e424  lea     rcx, [rsp+8B0h+pszDest]; pszDest
0x14000e429  call    StringVPrintfWorkerA
0x14000e42e  test    eax, eax
0x14000e430  js      loc_14000E529
0x14000e436  mov     ecx, esi; int
0x14000e438  call    ?CBSTextizeHresult@@YAPEBDJ@Z; CBSTextizeHresult(long)
0x14000e43d  mov     r9d, esi
0x14000e440  mov     [rsp+8B0h+argList], rax
0x14000e445  lea     r8, [rsp+8B0h+pszDest]
0x14000e44a  mov     ecx, edi
0x14000e44c  lea     rdx, aHsHresult0x08x; "%hs [HRESULT = 0x%08x - %hs]"
0x14000e453  call    ?HresultMsg@@YAPEAUtagLOG_PARTIAL_MSG@@W4tagLOG_SETUPLOG_SEVERITY@@PEBDZZ; HresultMsg(tagLOG_SETUPLOG_SEVERITY,char const *,...)
0x14000e458  mov     rdi, cs:?vpfnWdsSetupLogMessageA@@3P6A?AW4tagLOGRESULT@@PEAUtagLOG_PARTIAL_MSG@@KPEBD1K11PEAXK2I@ZEA; tagLOGRESULT (*vpfnWdsSetupLogMessageA)(tagLOG_PARTIAL_MSG *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint)
0x14000e45f  mov     rbx, rax
0x14000e462  mov     rax, cs:?vpfnCurrentIP@@3P6APEAXXZEA; void * (*vpfnCurrentIP)(void)
0x14000e469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e46e  mov     [rsp+8B0h+var_860], 0
0x14000e476  mov     [rsp+8B0h+var_868], 0
0x14000e47f  mov     [rsp+8B0h+var_870], 0
0x14000e487  mov     [rsp+8B0h+var_878], rax
0x14000e48c  lea     rax, aCbswdslog; "CBSWdsLog"
0x14000e493  mov     [rsp+8B0h+var_880], rax
0x14000e498  lea     rax, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000e49f  mov     [rsp+8B0h+var_888], rax
0x14000e4a4  mov     dword ptr [rsp+8B0h+argList], 51Ch
0x14000e4ac  jmp     short loc_14000E50F
0x14000e4ae  mov     r8, r12
0x14000e4b1  mov     rdx, r9
0x14000e4b4  mov     ecx, edi
0x14000e4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4bb  mov     rdi, cs:?vpfnWdsSetupLogMessageA@@3P6A?AW4tagLOGRESULT@@PEAUtagLOG_PARTIAL_MSG@@KPEBD1K11PEAXK2I@ZEA; tagLOGRESULT (*vpfnWdsSetupLogMessageA)(tagLOG_PARTIAL_MSG *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint)
0x14000e4c2  mov     rbx, rax
0x14000e4c5  mov     rax, cs:?vpfnCurrentIP@@3P6APEAXXZEA; void * (*vpfnCurrentIP)(void)
0x14000e4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4d1  mov     [rsp+8B0h+var_860], 0
0x14000e4d9  mov     [rsp+8B0h+var_868], 0
0x14000e4e2  mov     [rsp+8B0h+var_870], 0
0x14000e4ea  mov     [rsp+8B0h+var_878], rax
0x14000e4ef  lea     rax, aCbswdslog; "CBSWdsLog"
0x14000e4f6  mov     [rsp+8B0h+var_880], rax
0x14000e4fb  lea     rax, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000e502  mov     [rsp+8B0h+var_888], rax
0x14000e507  mov     dword ptr [rsp+8B0h+argList], 525h
0x14000e50f  xor     r9d, r9d
0x14000e512  lea     r8, aD_0; "D"
0x14000e519  mov     edx, 20000h
0x14000e51e  mov     rcx, rbx
0x14000e521  mov     rax, rdi
0x14000e524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e529  mov     rcx, [rbp+7B0h+var_40]
0x14000e530  xor     rcx, rsp; StackCookie
0x14000e533  call    __security_check_cookie
0x14000e538  add     rsp, 888h
0x14000e53f  pop     r15
0x14000e541  pop     r12
0x14000e543  pop     rdi
0x14000e544  pop     rsi
0x14000e545  pop     rbx
0x14000e546  pop     rbp
0x14000e547  retn
```
