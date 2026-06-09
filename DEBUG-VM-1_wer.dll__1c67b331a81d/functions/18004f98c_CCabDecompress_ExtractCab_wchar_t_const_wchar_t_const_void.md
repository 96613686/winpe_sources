# CCabDecompress::ExtractCab(wchar_t const *,wchar_t const *,void *)

- ea: `0x18004f98c`
- end: `0x18004fd57`
- name: `?ExtractCab@CCabDecompress@@QEAAJPEB_W0PEAX@Z`
- size: `971`
- prototype: `__int64 __fastcall(CCabDecompress *__hidden this, LPCWCH lpWideCharStr, const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007158c`

## callees

- `0x180004bb4`
- `0x18000c390`
- `0x180013730`
- `0x18001fe24`
- `0x18002b61c`
- `0x18004f98c`
- `0x18004fd60`
- `0x180050db0`
- `0x1800654ec`
- `0x180093538`
- `0x18009be30`
- `0x18009c55c`

## import_xrefs

- `ntdll!strrchr` at `0x18004fa92`
- `ntdll!strrchr` at `0x18004fa92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fc77`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fc77`
- `Cabinet!__imp_FDICreate` at `0x18004fbc0`
- `Cabinet!__imp_FDICreate` at `0x18004fbc0`
- `Cabinet!__imp_FDICopy` at `0x18004fc68`
- `Cabinet!__imp_FDICopy` at `0x18004fc68`
- `Cabinet!__imp_FDIDestroy` at `0x18004fcc5`
- `Cabinet!__imp_FDIDestroy` at `0x18004fcc5`

## pseudocode

```c
__int64 __fastcall CCabDecompress::ExtractCab(HANDLE *this, LPCWCH lpWideCharStr, const wchar_t *a3, void *a4)
{
  unsigned int v8; // r8d
  unsigned int v9; // edi
  int v10; // eax
  wchar_t *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  char *v14; // rax
  _BYTE *v15; // r10
  HFDI v16; // rsi
  ERF perf; // [rsp+50h] [rbp-B0h] BYREF
  char Str[272]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR pszCabinet[272]; // [rsp+170h] [rbp+70h] BYREF

  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  if ( lpWideCharStr && a3 )
  {
    Str[0] = 0;
    pszCabinet[0] = 0;
    if ( !UtilPathIsDirectory(a3) )
    {
      v9 = -2147024809;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, a3);
      return v9;
    }
    v10 = WideToAnsi(lpWideCharStr, Str, v8);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return v9;
      v12 = 76;
      goto LABEL_11;
    }
    v14 = strrchr(Str, 92);
    if ( v14 )
    {
      v10 = StringCchCopyA(pszCabinet, 0x104u, v14 + 1);
      v9 = v10;
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v12 = 78;
        goto LABEL_11;
      }
      *v15 = 0;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               this + 1,
                               a3) )
      {
        v9 = -2147024882;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v12 = 79;
        v13 = 2147942414LL;
LABEL_12:
        WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v13);
        return v9;
      }
      *this = a4;
      v16 = FDICreate(
              CCabDecompress::static_FDIAlloc,
              CCabDecompress::static_FDIFree,
              CCabDecompress::static_FDIOpen,
              CCabDecompress::static_FDIRead,
              CCabDecompress::static_FDIWrite,
              CCabDecompress::static_FDIClose,
              CCabDecompress::static_FDISeek,
              1,
              &perf);
      if ( !v16 )
      {
        v10 = FDIGetHRESULTFromERF(&perf);
        v9 = v10;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v12 = 80;
        goto LABEL_11;
      }
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          (unsigned int)Str,
          (__int64)pszCabinet);
      if ( FDICopy(v16, pszCabinet, Str, 0, CCabDecompress::static_FDINotify, 0, this) )
      {
        v9 = 0;
      }
      else
      {
        if ( WaitForSingleObject(*this, 0) )
          v9 = FDIGetHRESULTFromERF(&perf);
        else
          v9 = -2147467260;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v9);
      }
      if ( !FDIDestroy(v16) && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = FDIGetHRESULTFromERF(&perf);
        v11 = WPP_GLOBAL_Control;
        v12 = 83;
LABEL_11:
        v13 = (unsigned int)v10;
        goto LABEL_12;
      }
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, Str);
    }
  }
  else
  {
    v9 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x18004f98c  mov     [rsp-8+arg_18], rbx
0x18004f991  push    rbp
0x18004f992  push    rsi
0x18004f993  push    rdi
0x18004f994  push    r14
0x18004f996  push    r15
0x18004f998  lea     rbp, [rsp-190h]
0x18004f9a0  sub     rsp, 290h
0x18004f9a7  mov     rax, cs:__security_cookie
0x18004f9ae  xor     rax, rsp
0x18004f9b1  mov     [rbp+1B0h+var_30], rax
0x18004f9b8  xor     eax, eax
0x18004f9ba  mov     r15, r9
0x18004f9bd  mov     qword ptr [rsp+2B0h+var_260.erfOper], rax
0x18004f9c2  mov     rsi, r8
0x18004f9c5  mov     [rsp+2B0h+var_260.fError], eax
0x18004f9c9  mov     rbx, rdx
0x18004f9cc  mov     r14, rcx
0x18004f9cf  test    rdx, rdx
0x18004f9d2  jz      loc_18004FCFC
0x18004f9d8  test    r8, r8
0x18004f9db  jz      loc_18004FCFC
0x18004f9e1  mov     rcx, r8; wchar_t *
0x18004f9e4  mov     [rsp+2B0h+Str], al
0x18004f9e8  mov     [rbp+1B0h+pszCabinet], al
0x18004f9eb  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x18004f9f0  test    al, al
0x18004f9f2  jnz     short loc_18004FA37
0x18004f9f4  mov     edi, 80070057h
0x18004f9f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa00  lea     rbx, WPP_GLOBAL_Control
0x18004fa07  cmp     rcx, rbx
0x18004fa0a  jz      loc_18004FD2F
0x18004fa10  test    byte ptr [rcx+1Ch], 1
0x18004fa14  jz      loc_18004FD2F
0x18004fa1a  mov     rcx, [rcx+10h]
0x18004fa1e  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18004fa25  mov     edx, 4Bh ; 'K'
0x18004fa2a  mov     r9, rsi
0x18004fa2d  call    WPP_SF_S
0x18004fa32  jmp     loc_18004FD2F
0x18004fa37  lea     rdx, [rsp+2B0h+Str]; lpMultiByteStr
0x18004fa3c  mov     rcx, rbx; lpWideCharStr
0x18004fa3f  call    ?WideToAnsi@@YAJPEB_WPEADK@Z; WideToAnsi(wchar_t const *,char *,ulong)
0x18004fa44  mov     edi, eax
0x18004fa46  test    eax, eax
0x18004fa48  jns     short loc_18004FA88
0x18004fa4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa51  lea     rbx, WPP_GLOBAL_Control
0x18004fa58  cmp     rcx, rbx
0x18004fa5b  jz      loc_18004FD2F
0x18004fa61  test    byte ptr [rcx+1Ch], 1
0x18004fa65  jz      loc_18004FD2F
0x18004fa6b  mov     edx, 4Ch ; 'L'
0x18004fa70  mov     r9d, eax
0x18004fa73  mov     rcx, [rcx+10h]
0x18004fa77  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18004fa7e  call    WPP_SF_d
0x18004fa83  jmp     loc_18004FD2F
0x18004fa88  mov     edx, 5Ch ; '\'; Ch
0x18004fa8d  lea     rcx, [rsp+2B0h+Str]; Str
0x18004fa92  call    cs:__imp_strrchr
0x18004fa98  test    rax, rax
0x18004fa9b  jnz     short loc_18004FADB
0x18004fa9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004faa4  lea     rbx, WPP_GLOBAL_Control
0x18004faab  cmp     rcx, rbx
0x18004faae  jz      loc_18004FD2F
0x18004fab4  test    byte ptr [rcx+1Ch], 1
0x18004fab8  jz      loc_18004FD2F
0x18004fabe  mov     rcx, [rcx+10h]
0x18004fac2  lea     edx, [rax+4Dh]
0x18004fac5  lea     r9, [rsp+2B0h+Str]
0x18004faca  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18004fad1  call    WPP_SF_s
0x18004fad6  jmp     loc_18004FD2F
0x18004fadb  lea     r10, [rax+1]
0x18004fadf  mov     edx, 104h; unsigned __int64
0x18004fae4  mov     r8, r10; char *
0x18004fae7  lea     rcx, [rbp+1B0h+pszCabinet]; char *
0x18004faeb  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18004faf0  mov     edi, eax
0x18004faf2  test    eax, eax
0x18004faf4  jns     short loc_18004FB21
0x18004faf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fafd  lea     rbx, WPP_GLOBAL_Control
0x18004fb04  cmp     rcx, rbx
0x18004fb07  jz      loc_18004FD2F
0x18004fb0d  test    byte ptr [rcx+1Ch], 1
0x18004fb11  jz      loc_18004FD2F
0x18004fb17  mov     edx, 4Eh ; 'N'
0x18004fb1c  jmp     loc_18004FA70
0x18004fb21  lea     rcx, [r14+8]
0x18004fb25  mov     byte ptr [r10], 0
0x18004fb29  mov     rdx, rsi
0x18004fb2c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18004fb31  test    al, al
0x18004fb33  jnz     short loc_18004FB6B
0x18004fb35  mov     edi, 8007000Eh
0x18004fb3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fb41  lea     rbx, WPP_GLOBAL_Control
0x18004fb48  cmp     rcx, rbx
0x18004fb4b  jz      loc_18004FD2F
0x18004fb51  test    byte ptr [rcx+1Ch], 1
0x18004fb55  jz      loc_18004FD2F
0x18004fb5b  mov     edx, 4Fh ; 'O'
0x18004fb60  mov     r9d, 8007000Eh
0x18004fb66  jmp     loc_18004FA73
0x18004fb6b  lea     rax, [rsp+2B0h+var_260]
0x18004fb70  mov     [r14], r15
0x18004fb73  mov     [rsp+2B0h+perf], rax; perf
0x18004fb78  lea     r9, ?static_FDIRead@CCabDecompress@@KAI_JPEAXI@Z; pfnread
0x18004fb7f  mov     [rsp+2B0h+cpuType], 1; cpuType
0x18004fb87  lea     rax, ?static_FDISeek@CCabDecompress@@KAJ_JJH@Z; CCabDecompress::static_FDISeek(__int64,long,int)
0x18004fb8e  mov     [rsp+2B0h+pfnseek], rax; pfnseek
0x18004fb93  lea     r8, ?static_FDIOpen@CCabDecompress@@KA_JPEADHH@Z; pfnopen
0x18004fb9a  lea     rax, ?static_FDIClose@CCabDecompress@@KAH_J@Z; CCabDecompress::static_FDIClose(__int64)
0x18004fba1  mov     [rsp+2B0h+pfnclose], rax; pfnclose
0x18004fba6  lea     rdx, ?static_FDIFree@CCabDecompress@@KAXPEAX@Z; pfnfree
0x18004fbad  lea     rax, ?static_FDIWrite@CCabDecompress@@KAI_JPEAXI@Z; CCabDecompress::static_FDIWrite(__int64,void *,uint)
0x18004fbb4  lea     rcx, ?static_FDIAlloc@CCabDecompress@@KAPEAXK@Z; pfnalloc
0x18004fbbb  mov     [rsp+2B0h+pfnwrite], rax; pfnwrite
0x18004fbc0  call    cs:__imp_FDICreate
0x18004fbc6  mov     rsi, rax
0x18004fbc9  test    rax, rax
0x18004fbcc  jnz     short loc_18004FC03
0x18004fbce  lea     rcx, [rsp+2B0h+var_260]; struct ERF *
0x18004fbd3  call    ?FDIGetHRESULTFromERF@@YAJAEAUERF@@@Z; FDIGetHRESULTFromERF(ERF &)
0x18004fbd8  mov     edi, eax
0x18004fbda  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fbe1  lea     rbx, WPP_GLOBAL_Control
0x18004fbe8  cmp     rcx, rbx
0x18004fbeb  jz      loc_18004FD2F
0x18004fbf1  test    byte ptr [rcx+1Ch], 1
0x18004fbf5  jz      loc_18004FD2F
0x18004fbfb  lea     edx, [rsi+50h]
0x18004fbfe  jmp     loc_18004FA70
0x18004fc03  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fc0a  lea     rbx, WPP_GLOBAL_Control
0x18004fc11  cmp     rcx, rbx
0x18004fc14  jz      short loc_18004FC3F
0x18004fc16  test    byte ptr [rcx+1Ch], 4
0x18004fc1a  jz      short loc_18004FC3F
0x18004fc1c  mov     rcx, [rcx+10h]
0x18004fc20  lea     rax, [rbp+1B0h+pszCabinet]
0x18004fc24  mov     edx, 51h ; 'Q'
0x18004fc29  mov     [rsp+2B0h+pfnwrite], rax
0x18004fc2e  lea     r9, [rsp+2B0h+Str]
0x18004fc33  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18004fc3a  call    WPP_SF_ss
0x18004fc3f  mov     [rsp+2B0h+pfnseek], r14; pvUser
0x18004fc44  lea     rax, ?static_FDINotify@CCabDecompress@@KA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; CCabDecompress::static_FDINotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x18004fc4b  mov     [rsp+2B0h+pfnclose], 0; pfnfdid
0x18004fc54  lea     r8, [rsp+2B0h+Str]; pszCabPath
0x18004fc59  xor     r9d, r9d; flags
0x18004fc5c  mov     [rsp+2B0h+pfnwrite], rax; pfnfdin
0x18004fc61  lea     rdx, [rbp+1B0h+pszCabinet]; pszCabinet
0x18004fc65  mov     rcx, rsi; hfdi
0x18004fc68  call    cs:__imp_FDICopy
0x18004fc6e  test    eax, eax
0x18004fc70  jnz     short loc_18004FCC0
0x18004fc72  mov     rcx, [r14]; hHandle
0x18004fc75  xor     edx, edx; dwMilliseconds
0x18004fc77  call    cs:__imp_WaitForSingleObject
0x18004fc7d  test    eax, eax
0x18004fc7f  jnz     short loc_18004FC88
0x18004fc81  mov     edi, 80004004h
0x18004fc86  jmp     short loc_18004FC94
0x18004fc88  lea     rcx, [rsp+2B0h+var_260]; struct ERF *
0x18004fc8d  call    ?FDIGetHRESULTFromERF@@YAJAEAUERF@@@Z; FDIGetHRESULTFromERF(ERF &)
0x18004fc92  mov     edi, eax
0x18004fc94  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fc9b  cmp     rcx, rbx
0x18004fc9e  jz      short loc_18004FCC2
0x18004fca0  test    byte ptr [rcx+1Ch], 1
0x18004fca4  jz      short loc_18004FCC2
0x18004fca6  mov     rcx, [rcx+10h]
0x18004fcaa  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18004fcb1  mov     edx, 52h ; 'R'
0x18004fcb6  mov     r9d, edi
0x18004fcb9  call    WPP_SF_d
0x18004fcbe  jmp     short loc_18004FCC2
0x18004fcc0  xor     edi, edi
0x18004fcc2  mov     rcx, rsi; hfdi
0x18004fcc5  call    cs:__imp_FDIDestroy
0x18004fccb  test    eax, eax
0x18004fccd  jnz     short loc_18004FD2F
0x18004fccf  mov     rax, cs:WPP_GLOBAL_Control
0x18004fcd6  cmp     rax, rbx
0x18004fcd9  jz      short loc_18004FD2F
0x18004fcdb  test    byte ptr [rax+1Ch], 1
0x18004fcdf  jz      short loc_18004FD2F
0x18004fce1  lea     rcx, [rsp+2B0h+var_260]; struct ERF *
0x18004fce6  call    ?FDIGetHRESULTFromERF@@YAJAEAUERF@@@Z; FDIGetHRESULTFromERF(ERF &)
0x18004fceb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fcf2  mov     edx, 53h ; 'S'
0x18004fcf7  jmp     loc_18004FA70
0x18004fcfc  mov     edi, 80070057h
0x18004fd01  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fd08  lea     rbx, WPP_GLOBAL_Control
0x18004fd0f  cmp     rcx, rbx
0x18004fd12  jz      short loc_18004FD2F
0x18004fd14  test    byte ptr [rcx+1Ch], 1
0x18004fd18  jz      short loc_18004FD2F
0x18004fd1a  mov     rcx, [rcx+10h]
0x18004fd1e  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18004fd25  mov     edx, 4Ah ; 'J'
0x18004fd2a  call    WPP_SF_
0x18004fd2f  mov     eax, edi
0x18004fd31  mov     rcx, [rbp+1B0h+var_30]
0x18004fd38  xor     rcx, rsp; StackCookie
0x18004fd3b  call    __security_check_cookie
0x18004fd40  mov     rbx, [rsp+2B0h+arg_18]
0x18004fd48  add     rsp, 290h
0x18004fd4f  pop     r15
0x18004fd51  pop     r14
0x18004fd53  pop     rdi
0x18004fd54  pop     rsi
0x18004fd55  pop     rbp
0x18004fd56  retn
```
