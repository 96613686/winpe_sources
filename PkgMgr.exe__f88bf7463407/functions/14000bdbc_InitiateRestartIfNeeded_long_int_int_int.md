# InitiateRestartIfNeeded(long,int,int,int *)

- ea: `0x14000bdbc`
- end: `0x14000bf2b`
- name: `?InitiateRestartIfNeeded@@YAJJHHPEAH@Z`
- size: `367`
- prototype: `__int64 __fastcall(int, int, int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000d734`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000bdbc`
- `0x14000ca60`
- `0x14000dc0c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000be9b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000be9b`

## string_xrefs

- `0x14000be1d`: `Failed asking user if it was ok to restart the computer`
- `0x14000bec6`: `Failed restarting the computer`

## pseudocode

```c
__int64 __fastcall InitiateRestartIfNeeded(const wchar_t *a1, int a2, int a3, int *a4)
{
  int v5; // eax
  int v6; // ebx
  int v7; // edx
  __int64 v8; // rdx
  int restarted; // eax
  int v11; // edx
  int v12; // [rsp+20h] [rbp-38h]
  int v13[2]; // [rsp+30h] [rbp-28h] BYREF
  int v14; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v14 = 1;
  *a4 = 0;
  if ( !a2 )
  {
    if ( a3 )
      goto LABEL_10;
    v5 = UIAskUserAboutRestart((int)a1, &v14);
    v6 = v5;
    if ( v5 < 0 )
    {
      v14 = v5;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed asking user if it was ok to restart the computer");
        *(_QWORD *)v13 = &v14;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v7,
          3,
          (unsigned int)": {}",
          (__int64)v13);
      }
      v8 = 167;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
        (const char *)(unsigned int)v6,
        v12);
      return (unsigned int)v6;
    }
    if ( v14 )
    {
LABEL_10:
      while ( 1 )
      {
        restarted = RestartComputer(a1);
        if ( restarted != -2147023625 && restarted != -2147024875 )
          break;
        Sleep(0xBB8u);
      }
      v6 = 0;
      if ( restarted != -2147023781 )
        v6 = restarted;
      if ( v6 < 0 )
      {
        v14 = v6;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed restarting the computer");
          *(_QWORD *)v13 = &v14;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v11,
            3,
            (unsigned int)": {}",
            (__int64)v13);
        }
        v8 = 193;
        goto LABEL_7;
      }
      *a4 = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000bdbc  mov     [rsp+arg_8], rbx
0x14000bdc1  push    rdi
0x14000bdc2  sub     rsp, 50h
0x14000bdc6  mov     rax, cs:__security_cookie
0x14000bdcd  xor     rax, rsp
0x14000bdd0  mov     [rsp+58h+var_18], rax
0x14000bdd5  mov     [rsp+58h+var_20], 1
0x14000bddd  mov     rdi, r9
0x14000bde0  mov     dword ptr [r9], 0
0x14000bde7  test    edx, edx
0x14000bde9  jnz     loc_14000BF11
0x14000bdef  test    r8d, r8d
0x14000bdf2  jnz     loc_14000BE83
0x14000bdf8  lea     rdx, [rsp+58h+var_20]; int *
0x14000bdfd  call    ?UIAskUserAboutRestart@@YAJJPEAH@Z; UIAskUserAboutRestart(long,int *)
0x14000be02  mov     ebx, eax
0x14000be04  test    eax, eax
0x14000be06  jns     short loc_14000BE78
0x14000be08  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000be0f  mov     [rsp+58h+var_20], eax
0x14000be13  test    rcx, rcx
0x14000be16  jz      short loc_14000BE58
0x14000be18  mov     edi, 3
0x14000be1d  lea     r9, aFailedAskingUs; "Failed asking user if it was ok to rest"...
0x14000be24  mov     r8d, edi
0x14000be27  xor     edx, edx
0x14000be29  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000be2e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000be35  lea     rax, [rsp+58h+var_20]
0x14000be3a  mov     qword ptr [rsp+58h+var_28], rax
0x14000be3f  lea     r9, asc_14002D4FC; ": {}"
0x14000be46  lea     rax, [rsp+58h+var_28]
0x14000be4b  mov     r8d, edi
0x14000be4e  mov     qword ptr [rsp+58h+var_38], rax; int
0x14000be53  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000be58  mov     edx, 0A7h; void *
0x14000be5d  mov     rcx, [rsp+58h]; this
0x14000be62  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000be69  mov     r9d, ebx; char *
0x14000be6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000be71  mov     eax, ebx
0x14000be73  jmp     loc_14000BF13
0x14000be78  cmp     [rsp+58h+var_20], 0
0x14000be7d  jz      loc_14000BF11
0x14000be83  call    ?RestartComputer@@YAJXZ; RestartComputer(void)
0x14000be88  cmp     eax, 800704F7h
0x14000be8d  jz      short loc_14000BE96
0x14000be8f  cmp     eax, 80070015h
0x14000be94  jnz     short loc_14000BEA3
0x14000be96  mov     ecx, 0BB8h; dwMilliseconds
0x14000be9b  call    cs:__imp_Sleep
0x14000bea1  jmp     short loc_14000BE83
0x14000bea3  xor     ebx, ebx
0x14000bea5  cmp     eax, 8007045Bh
0x14000beaa  cmovnz  ebx, eax
0x14000bead  test    ebx, ebx
0x14000beaf  jns     short loc_14000BF0B
0x14000beb1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000beb8  mov     [rsp+58h+var_20], ebx
0x14000bebc  test    rcx, rcx
0x14000bebf  jz      short loc_14000BF01
0x14000bec1  mov     edi, 3
0x14000bec6  lea     r9, aFailedRestarti; "Failed restarting the computer"
0x14000becd  mov     r8d, edi
0x14000bed0  xor     edx, edx
0x14000bed2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000bed7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000bede  lea     rax, [rsp+58h+var_20]
0x14000bee3  mov     qword ptr [rsp+58h+var_28], rax
0x14000bee8  lea     r9, asc_14002D4FC; ": {}"
0x14000beef  lea     rax, [rsp+58h+var_28]
0x14000bef4  mov     r8d, edi
0x14000bef7  mov     qword ptr [rsp+58h+var_38], rax
0x14000befc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000bf01  mov     edx, 0C1h
0x14000bf06  jmp     loc_14000BE5D
0x14000bf0b  mov     dword ptr [rdi], 1
0x14000bf11  xor     eax, eax
0x14000bf13  mov     rcx, [rsp+58h+var_18]
0x14000bf18  xor     rcx, rsp; StackCookie
0x14000bf1b  call    __security_check_cookie
0x14000bf20  mov     rbx, [rsp+58h+arg_8]
0x14000bf25  add     rsp, 50h
0x14000bf29  pop     rdi
0x14000bf2a  retn
```
