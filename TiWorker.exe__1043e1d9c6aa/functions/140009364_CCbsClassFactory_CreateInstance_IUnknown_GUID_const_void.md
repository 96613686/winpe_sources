# CCbsClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140009364`
- end: `0x140009499`
- name: `?CreateInstance@CCbsClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `309`
- prototype: `__int64 __fastcall(CCbsClassFactory *this, struct IUnknown *, const struct _GUID *, struct ICbsWorker **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140006780`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008ef4`
- `0x140009084`
- `0x140009364`
- `0x1400094f4`

## string_xrefs

- `0x140009435`: `Failed to create session.`

## pseudocode

```c
__int64 __fastcall CCbsClassFactory::CreateInstance(
        CCbsClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct ICbsWorker **a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-38h]
  struct ICbsWorker **v14; // [rsp+30h] [rbp-28h] BYREF
  struct ICbsWorker *v15; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a4 )
  {
    v5 = -2147024809;
    v6 = 15;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\tiworker\\tiworkerclassfactory.cpp",
      (const char *)v5,
      v13);
    return v5;
  }
  *a4 = 0;
  if ( a2 )
  {
    v5 = -2147221232;
    v6 = 18;
    goto LABEL_3;
  }
  v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v8 )
  {
    v9 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICbsWorker.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICbsWorker.Data1 )
      v9 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICbsWorker.Data4;
    if ( v9 )
    {
      v5 = -2147467262;
      v6 = 19;
      goto LABEL_3;
    }
  }
  v15 = 0;
  v10 = CCbsClassFactory::CreateWorker((CCbsClassFactory *)((char *)this - 80), &v15);
  v5 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v15) = v10;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogPartial<>(v11, 3, "Failed to create session.");
      v14 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)&v14);
    }
    v6 = 22;
    goto LABEL_3;
  }
  *a4 = v15;
  return 0;
}

```

## disassembly

```asm
0x140009364  mov     [rsp+arg_8], rbx
0x140009369  push    rdi
0x14000936a  sub     rsp, 50h
0x14000936e  mov     rax, cs:__security_cookie
0x140009375  xor     rax, rsp
0x140009378  mov     [rsp+58h+var_18], rax
0x14000937d  mov     rdi, r9
0x140009380  test    r9, r9
0x140009383  jnz     short loc_1400093A9
0x140009385  mov     ebx, 80070057h
0x14000938a  lea     edx, [r9+0Fh]; void *
0x14000938e  mov     rcx, [rsp+58h]; this
0x140009393  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\tiworker\\tiworkerc"...
0x14000939a  mov     r9d, ebx; char *
0x14000939d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400093a2  mov     eax, ebx
0x1400093a4  jmp     loc_140009481
0x1400093a9  mov     qword ptr [r9], 0
0x1400093b0  test    rdx, rdx
0x1400093b3  jz      short loc_1400093C1
0x1400093b5  mov     ebx, 80040110h
0x1400093ba  mov     edx, 12h
0x1400093bf  jmp     short loc_14000938E
0x1400093c1  mov     rax, [r8]
0x1400093c4  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1400093cb  jnz     short loc_1400093D8
0x1400093cd  mov     rax, [r8+8]
0x1400093d1  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1400093d8  test    rax, rax
0x1400093db  jz      short loc_140009405
0x1400093dd  mov     rax, [r8]
0x1400093e0  sub     rax, qword ptr cs:IID_ICbsWorker.Data1
0x1400093e7  jnz     short loc_1400093F4
0x1400093e9  mov     rax, [r8+8]
0x1400093ed  sub     rax, qword ptr cs:IID_ICbsWorker.Data4
0x1400093f4  test    rax, rax
0x1400093f7  jz      short loc_140009405
0x1400093f9  mov     ebx, 80004002h
0x1400093fe  mov     edx, 13h
0x140009403  jmp     short loc_14000938E
0x140009405  add     rcx, 0FFFFFFFFFFFFFFB0h; this
0x140009409  mov     [rsp+58h+var_20], 0
0x140009412  lea     rdx, [rsp+58h+var_20]; struct ICbsWorker **
0x140009417  call    ?CreateWorker@CCbsClassFactory@@QEAAJPEAPEAUICbsWorker@@@Z; CCbsClassFactory::CreateWorker(ICbsWorker * *)
0x14000941c  mov     ebx, eax
0x14000941e  test    eax, eax
0x140009420  jns     short loc_140009477
0x140009422  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x14000942a  mov     dword ptr [rsp+58h+var_20], eax
0x14000942e  jz      short loc_14000946D
0x140009430  mov     edi, 3
0x140009435  lea     r8, aFailedToCreate; "Failed to create session."
0x14000943c  mov     edx, edi
0x14000943e  call    ??$LogPartial@$$V@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogPartial<>(LogAdapter::LogLevel,char const * const)
0x140009443  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000944a  lea     rax, [rsp+58h+var_20]
0x14000944f  mov     [rsp+58h+var_28], rax
0x140009454  lea     r9, asc_140030534; ": {}"
0x14000945b  lea     rax, [rsp+58h+var_28]
0x140009460  mov     r8d, edi
0x140009463  mov     qword ptr [rsp+58h+var_38], rax
0x140009468  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000946d  mov     edx, 16h
0x140009472  jmp     loc_14000938E
0x140009477  mov     rax, [rsp+58h+var_20]
0x14000947c  mov     [rdi], rax
0x14000947f  xor     eax, eax
0x140009481  mov     rcx, [rsp+58h+var_18]
0x140009486  xor     rcx, rsp; StackCookie
0x140009489  call    __security_check_cookie
0x14000948e  mov     rbx, [rsp+58h+arg_8]
0x140009493  add     rsp, 50h
0x140009497  pop     rdi
0x140009498  retn
```
