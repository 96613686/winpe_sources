# CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)

- ea: `0x140017658`
- end: `0x1400177d8`
- name: `?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ`
- size: `384`
- prototype: `void(unsigned int, size_t, size_t *, const char *, ...)`
- caller_count: `97`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140007010`
- `0x140007110`
- `0x140007b40`
- `0x1400091f0`
- `0x140009334`
- `0x140009438`
- `0x140009650`
- `0x140009b2c`
- `0x14000a3f8`
- `0x14000a730`
- `0x14000b79c`
- `0x14000bb74`
- `0x14000bc20`
- `0x14000bd04`
- `0x14000bdd0`
- `0x14000bec4`
- `0x14000c204`
- `0x14000c2b4`
- `0x14000c320`
- `0x14000c3e0`
- `0x14000c6e4`
- `0x14000c830`
- `0x14000c92c`
- `0x14000ca08`
- `0x14000ca98`
- `0x14000cd7c`
- `0x14000ce08`
- `0x14000ceb4`
- `0x14000cf8c`
- `0x14000d020`
- `0x14000d12c`
- `0x14000d23c`
- `0x14000d420`
- `0x14000d4d0`
- `0x14000d5c8`
- `0x14000dca8`
- `0x14000eb34`
- `0x14000ec74`
- `0x14000ede4`
- `0x14000eee4`
- `0x14000ef94`
- `0x14000f020`
- `0x14000f238`
- `0x14000f484`
- `0x14000f634`
- `0x14000f7b4`
- `0x14000f8a4`
- `0x14000f990`
- `0x14000fbc4`
- `0x14000fd94`

## callees

- `0x1400023e0`
- `0x140017658`
- `0x140017e6c`
- `0x140018520`
- `0x14002b010`

## pseudocode

```c
void CBSWdsLogLight(unsigned int a1, size_t a2, size_t *a3, const char *a4, ...)
{
  int v5; // edi
  __int64 v6; // rax
  enum tagLOGRESULT (__high *v7)(struct tagLOG_PARTIAL_MSG *, unsigned int, const char *, const char *, unsigned int, const char *, const char *, void *, unsigned int, void *, unsigned int); // rdi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  enum tagLOGRESULT (__high *v10)(struct tagLOG_PARTIAL_MSG *, unsigned int, const char *, const char *, unsigned int, const char *, const char *, void *, unsigned int, void *, unsigned int); // rdi
  struct tagLOG_PARTIAL_MSG *v11; // rbx
  void *v12; // [rsp+38h] [rbp-460h]
  void *v13; // [rsp+38h] [rbp-460h]
  char pszDest[1024]; // [rsp+70h] [rbp-428h] BYREF
  va_list va; // [rsp+4C0h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a2;
  if ( vpfnWdsSetupLogMessageA && vpfnConstructPartialMsgVA && vpfnCurrentIP )
  {
    if ( (_BYTE)a3 )
    {
      if ( StringVPrintfWorkerA(pszDest, a2, a3, a4, va) >= 0 )
      {
        v6 = HresultMsg(a1, "%hs [HRESULT = 0x%08x]", pszDest, v5);
        v7 = vpfnWdsSetupLogMessageA;
        v8 = v6;
        v12 = vpfnCurrentIP();
        ((void (__fastcall *)(__int64, __int64, const char *, _QWORD, int, const char *, const char *, void *, _DWORD, _QWORD, _DWORD))v7)(
          v8,
          0x20000,
          "D",
          0,
          1361,
          "onecore\\base\\cbs\\util\\cbsutil.cpp",
          "CBSWdsLogLight",
          v12,
          0,
          0,
          0);
      }
    }
    else
    {
      v9 = vpfnConstructPartialMsgVA(a1, a4, va);
      v10 = vpfnWdsSetupLogMessageA;
      v11 = v9;
      v13 = vpfnCurrentIP();
      ((void (__fastcall *)(struct tagLOG_PARTIAL_MSG *, __int64, const char *, _QWORD, int, const char *, const char *, void *, _DWORD, _QWORD, _DWORD))v10)(
        v11,
        0x20000,
        "D",
        0,
        1369,
        "onecore\\base\\cbs\\util\\cbsutil.cpp",
        "CBSWdsLogLight",
        v13,
        0,
        0,
        0);
    }
  }
}

```

## disassembly

```asm
0x140017658  mov     r11, rsp
0x14001765b  mov     [r11+20h], r9
0x14001765f  push    rbx
0x140017660  push    rdi
0x140017661  sub     rsp, 488h
0x140017668  mov     rax, cs:__security_cookie
0x14001766f  xor     rax, rsp
0x140017672  mov     [rsp+498h+var_28], rax
0x14001767a  cmp     cs:?vpfnWdsSetupLogMessageA@@3P6A?AW4tagLOGRESULT@@PEAUtagLOG_PARTIAL_MSG@@KPEBD1K11PEAXK2I@ZEA, 0; tagLOGRESULT (*vpfnWdsSetupLogMessageA)(tagLOG_PARTIAL_MSG *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint)
0x140017682  mov     ebx, ecx
0x140017684  lea     rcx, [r11+28h]
0x140017688  mov     [rsp+498h+var_438], 0
0x140017691  mov     edi, edx
0x140017693  jz      loc_1400177BE
0x140017699  mov     rax, cs:?vpfnConstructPartialMsgVA@@3P6APEAUtagLOG_PARTIAL_MSG@@KPEBDPEAD@ZEA; tagLOG_PARTIAL_MSG * (*vpfnConstructPartialMsgVA)(ulong,char const *,char *)
0x1400176a0  test    rax, rax
0x1400176a3  jz      loc_1400177BE
0x1400176a9  cmp     cs:?vpfnCurrentIP@@3P6APEAXXZEA, 0; void * (*vpfnCurrentIP)(void)
0x1400176b1  jz      loc_1400177BE
0x1400176b7  test    r8b, r8b
0x1400176ba  jz      loc_140017743
0x1400176c0  mov     [rsp+498h+argList], rcx; argList
0x1400176c5  lea     rcx, [rsp+498h+pszDest]; pszDest
0x1400176ca  call    StringVPrintfWorkerA
0x1400176cf  test    eax, eax
0x1400176d1  js      loc_1400177BE
0x1400176d7  mov     r9d, edi
0x1400176da  lea     r8, [rsp+498h+pszDest]
0x1400176df  lea     rdx, aHsHresult0x08x; "%hs [HRESULT = 0x%08x]"
0x1400176e6  mov     ecx, ebx
0x1400176e8  call    ?HresultMsg@@YAPEAUtagLOG_PARTIAL_MSG@@W4tagLOG_SETUPLOG_SEVERITY@@PEBDZZ; HresultMsg(tagLOG_SETUPLOG_SEVERITY,char const *,...)
0x1400176ed  mov     rdi, cs:?vpfnWdsSetupLogMessageA@@3P6A?AW4tagLOGRESULT@@PEAUtagLOG_PARTIAL_MSG@@KPEBD1K11PEAXK2I@ZEA; tagLOGRESULT (*vpfnWdsSetupLogMessageA)(tagLOG_PARTIAL_MSG *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint)
0x1400176f4  mov     rbx, rax
0x1400176f7  mov     rax, cs:?vpfnCurrentIP@@3P6APEAXXZEA; void * (*vpfnCurrentIP)(void)
0x1400176fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017703  mov     [rsp+498h+var_448], 0
0x14001770b  mov     [rsp+498h+var_450], 0
0x140017714  mov     [rsp+498h+var_458], 0
0x14001771c  mov     [rsp+498h+var_460], rax
0x140017721  lea     rax, aCbswdsloglight; "CBSWdsLogLight"
0x140017728  mov     [rsp+498h+var_468], rax
0x14001772d  lea     rax, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140017734  mov     [rsp+498h+var_470], rax
0x140017739  mov     dword ptr [rsp+498h+argList], 551h
0x140017741  jmp     short loc_1400177A4
0x140017743  mov     r8, rcx
0x140017746  mov     rdx, r9
0x140017749  mov     ecx, ebx
0x14001774b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017750  mov     rdi, cs:?vpfnWdsSetupLogMessageA@@3P6A?AW4tagLOGRESULT@@PEAUtagLOG_PARTIAL_MSG@@KPEBD1K11PEAXK2I@ZEA; tagLOGRESULT (*vpfnWdsSetupLogMessageA)(tagLOG_PARTIAL_MSG *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint)
0x140017757  mov     rbx, rax
0x14001775a  mov     rax, cs:?vpfnCurrentIP@@3P6APEAXXZEA; void * (*vpfnCurrentIP)(void)
0x140017761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017766  mov     [rsp+498h+var_448], 0
0x14001776e  mov     [rsp+498h+var_450], 0
0x140017777  mov     [rsp+498h+var_458], 0
0x14001777f  mov     [rsp+498h+var_460], rax
0x140017784  lea     rax, aCbswdsloglight; "CBSWdsLogLight"
0x14001778b  mov     [rsp+498h+var_468], rax
0x140017790  lea     rax, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140017797  mov     [rsp+498h+var_470], rax
0x14001779c  mov     dword ptr [rsp+498h+argList], 559h
0x1400177a4  xor     r9d, r9d
0x1400177a7  lea     r8, aD_0; "D"
0x1400177ae  mov     edx, 20000h
0x1400177b3  mov     rcx, rbx
0x1400177b6  mov     rax, rdi
0x1400177b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400177be  mov     rcx, [rsp+498h+var_28]
0x1400177c6  xor     rcx, rsp; StackCookie
0x1400177c9  call    __security_check_cookie
0x1400177ce  add     rsp, 488h
0x1400177d5  pop     rdi
0x1400177d6  pop     rbx
0x1400177d7  retn
```
