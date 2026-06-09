# Windows::Service::Task::Save(bool)

- ea: `0x18005d944`
- end: `0x18005dd23`
- name: `?Save@Task@Service@Windows@@QEAAX_N@Z`
- size: `991`
- prototype: `void __fastcall(Windows::Service::Task *this)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18005b500`
- `0x18005c140`
- `0x18005c2b0`
- `0x18005de30`

## callees

- `0x1800209fc`
- `0x180023a34`
- `0x180023ac4`
- `0x18005c718`
- `0x18005cef8`
- `0x18005d79c`
- `0x18005d944`
- `0x18005e98c`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005d9bc`
- `OLEAUT32!__imp_SysAllocString` at `0x18005dac8`
- `OLEAUT32!__imp_SysAllocString` at `0x18005db56`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d9bc`
- `OLEAUT32!__imp_SysAllocString` at `0x18005dac8`
- `OLEAUT32!__imp_SysAllocString` at `0x18005db56`
- `OLEAUT32!__imp_SysFreeString` at `0x18005dbf6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005dc64`
- `OLEAUT32!__imp_SysFreeString` at `0x18005dbf6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005dc64`
- `OLEAUT32!__imp_VariantInit` at `0x18005d99e`
- `OLEAUT32!__imp_VariantInit` at `0x18005daaa`
- `OLEAUT32!__imp_VariantInit` at `0x18005db26`
- `OLEAUT32!__imp_VariantInit` at `0x18005d99e`
- `OLEAUT32!__imp_VariantInit` at `0x18005daaa`
- `OLEAUT32!__imp_VariantInit` at `0x18005db26`
- `OLEAUT32!__imp_VariantClear` at `0x18005dc01`
- `OLEAUT32!__imp_VariantClear` at `0x18005dc3a`
- `OLEAUT32!__imp_VariantClear` at `0x18005dc89`
- `OLEAUT32!__imp_VariantClear` at `0x18005dc01`
- `OLEAUT32!__imp_VariantClear` at `0x18005dc3a`
- `OLEAUT32!__imp_VariantClear` at `0x18005dc89`

## string_xrefs

- `0x18005dcd8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005dcff`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005dd11`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005dcc6`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005dced`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
void __fastcall Windows::Service::Task::Save(Windows::Service::Task *this)
{
  const OLECHAR *v2; // rcx
  BSTR v3; // rax
  const char *v4; // r9
  OLECHAR *v5; // rbx
  PCNZWCH *v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  const OLECHAR *v9; // rcx
  BSTR v10; // rax
  const char *v11; // r9
  __int64 *v12; // rsi
  __int64 v13; // r14
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  __int128 v18; // xmm10
  IRecordInfo *v19; // xmm11_8
  __int64 v20; // r15
  const OLECHAR *v21; // rcx
  BSTR v22; // rax
  const char *v23; // r9
  OLECHAR *v24; // rbx
  int v25; // eax
  Windows::Service::Task *v26; // rcx
  int v27; // [rsp+20h] [rbp-E0h]
  BSTR v28; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v30; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v32; // [rsp+90h] [rbp-70h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-50h]
  IRecordInfo *v34; // [rsp+C0h] [rbp-40h]
  __int128 v35; // [rsp+D0h] [rbp-30h]
  IRecordInfo *v36; // [rsp+E0h] [rbp-20h]
  int v37[4]; // [rsp+F0h] [rbp-10h] BYREF
  IRecordInfo *v38; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  __int64 *v40; // [rsp+1C0h] [rbp+C0h] BYREF
  OLECHAR *v41; // [rsp+1C8h] [rbp+C8h] BYREF

  if ( *((_BYTE *)this + 40) )
  {
    VariantInit(&pvarg);
    v2 = (const OLECHAR *)&Windows::Service::Task::c_securityDescriptor;
    if ( (unsigned __int64)qword_1800976C8 > 7 )
      v2 = Windows::Service::Task::c_securityDescriptor;
    v3 = SysAllocString(v2);
    v28 = v3;
    if ( !v3 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    pvarg.llVal = (LONGLONG)v3;
    pvarg.vt = 8;
    Windows::Service::Task::TaskService((int)&v41);
    v5 = v41;
    v28 = v41;
    if ( v41 )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v41 + 8LL))(v41);
    Windows::Service::Task::EnsureTaskFolderExists(&v28);
    if ( v5 )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v5 + 16LL))(v5);
    v6 = &Windows::Service::Task::c_taskFolder;
    if ( (unsigned __int64)qword_180097688 > 7 )
      v6 = (PCNZWCH *)Windows::Service::Task::c_taskFolder;
    wil::make_bstr(&bstrString, v6);
    v40 = 0;
    v7 = *(_QWORD *)v41;
    v40 = 0;
    v8 = (*(__int64 (__fastcall **)(OLECHAR *, BSTR, __int64 **))(v7 + 56))(v41, bstrString, &v40);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v8,
        v27);
    VariantInit(&v30);
    v9 = (const OLECHAR *)&Windows::Service::Task::c_systemId;
    if ( (unsigned __int64)qword_1800976E8 > 7 )
      v9 = Windows::Service::Task::c_systemId;
    v10 = SysAllocString(v9);
    v28 = v10;
    if ( !v10 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
    v30.llVal = (LONGLONG)v10;
    v30.vt = 8;
    v12 = v40;
    v13 = *v40;
    v14 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v32);
    v16 = *(_OWORD *)&v32.vt;
    v17 = v32.pRecInfo;
    v18 = *(_OWORD *)&v30.vt;
    v19 = v30.pRecInfo;
    v20 = *(_QWORD *)this;
    v21 = (const OLECHAR *)((char *)this + 8);
    if ( *((_QWORD *)this + 4) > 7u )
      v21 = *(const OLECHAR **)v21;
    v22 = SysAllocString(v21);
    v24 = v22;
    v28 = v22;
    if ( !v22 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    v33 = v14;
    v34 = pRecInfo;
    v35 = v16;
    v36 = v17;
    *(_OWORD *)v37 = v18;
    v38 = v19;
    v25 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64))(v13 + 136))(v12, v22, v20, 6);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v25,
        (int)v37);
    SysFreeString(v24);
    VariantClear(&v32);
    Windows::Service::Task::Protect((__int64 **)this);
    Windows::Service::Task::LogTaskModified(v26, 0);
    VariantClear(&v30);
    if ( v40 )
      (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v41 )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v41 + 16LL))(v41);
    VariantClear(&pvarg);
  }
}

```

## disassembly

```asm
0x18005d944  mov     rax, rsp
0x18005d947  mov     [rax+10h], dl
0x18005d94a  push    rbp
0x18005d94b  push    rbx
0x18005d94c  push    rsi
0x18005d94d  push    rdi
0x18005d94e  push    r13
0x18005d950  push    r14
0x18005d952  push    r15
0x18005d954  lea     rbp, [rsp-70h]
0x18005d959  sub     rsp, 170h
0x18005d960  movaps  xmmword ptr [rax-48h], xmm6
0x18005d964  movaps  xmmword ptr [rax-58h], xmm7
0x18005d968  movaps  xmmword ptr [rax-68h], xmm8
0x18005d96d  movaps  xmmword ptr [rax-78h], xmm9
0x18005d972  movaps  xmmword ptr [rax-88h], xmm10
0x18005d97a  movaps  xmmword ptr [rax-98h], xmm11
0x18005d982  mov     rdi, rcx
0x18005d985  mov     [rbp+0A0h+arg_8], 0
0x18005d98f  cmp     byte ptr [rcx+28h], 0
0x18005d993  jz      loc_18005DC8F
0x18005d999  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x18005d99e  call    cs:__imp_VariantInit
0x18005d9a4  nop
0x18005d9a5  lea     rcx, ?c_securityDescriptor@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_securityDescriptor
0x18005d9ac  cmp     cs:qword_1800976C8, 7
0x18005d9b4  cmova   rcx, cs:?c_securityDescriptor@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; psz
0x18005d9bc  call    cs:__imp_SysAllocString
0x18005d9c2  mov     [rsp+1A0h+var_150], rax
0x18005d9c7  mov     [rbp+0A0h+arg_8], 1
0x18005d9d1  mov     rcx, [rbp+0A8h]; this
0x18005d9d8  test    rax, rax
0x18005d9db  jz      loc_18005DCD8
0x18005d9e1  mov     qword ptr [rbp+0A0h+pvarg+8], rax
0x18005d9e5  mov     r13d, 8
0x18005d9eb  mov     word ptr [rsp+1A0h+pvarg], r13w
0x18005d9f1  lea     rcx, [rbp+0A0h+arg_18]; int
0x18005d9f8  call    ?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::TaskService(void)
0x18005d9fd  nop
0x18005d9fe  mov     rbx, [rbp+0A0h+arg_18]
0x18005da05  mov     [rsp+1A0h+var_150], rbx
0x18005da0a  test    rbx, rbx
0x18005da0d  jz      short loc_18005DA1F
0x18005da0f  mov     rax, [rbx]
0x18005da12  mov     rcx, rbx
0x18005da15  mov     rax, [rax+8]
0x18005da19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da1e  nop
0x18005da1f  lea     rcx, [rsp+1A0h+var_150]
0x18005da24  call    ?EnsureTaskFolderExists@Task@Service@Windows@@CAXAEBV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@@Z; Windows::Service::Task::EnsureTaskFolderExists(wil::com_ptr_t<ITaskService,wil::err_exception_policy> const &)
0x18005da29  nop
0x18005da2a  test    rbx, rbx
0x18005da2d  jz      short loc_18005DA3F
0x18005da2f  mov     rax, [rbx]
0x18005da32  mov     rcx, rbx
0x18005da35  mov     rax, [rax+10h]
0x18005da39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da3e  nop
0x18005da3f  lea     rdx, ?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005da46  cmp     cs:qword_180097688, 7
0x18005da4e  cmova   rdx, cs:?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005da56  lea     rcx, [rsp+1A0h+bstrString]
0x18005da5b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005da60  nop
0x18005da61  mov     [rbp+0A0h+arg_10], 0
0x18005da6c  mov     rcx, [rbp+0A0h+arg_18]
0x18005da73  mov     rax, [rcx]
0x18005da76  mov     [rbp+0A0h+arg_10], 0
0x18005da81  lea     r8, [rbp+0A0h+arg_10]
0x18005da88  mov     rdx, [rsp+1A0h+bstrString]
0x18005da8d  mov     rax, [rax+38h]
0x18005da91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da96  mov     rcx, [rbp+0A8h]; this
0x18005da9d  test    eax, eax
0x18005da9f  js      loc_18005DCEA
0x18005daa5  lea     rcx, [rsp+1A0h+var_140]; pvarg
0x18005daaa  call    cs:__imp_VariantInit
0x18005dab0  nop
0x18005dab1  lea     rcx, ?c_systemId@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_systemId
0x18005dab8  cmp     cs:qword_1800976E8, 7
0x18005dac0  cmova   rcx, cs:?c_systemId@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; psz
0x18005dac8  call    cs:__imp_SysAllocString
0x18005dace  mov     [rsp+1A0h+var_150], rax
0x18005dad3  mov     [rbp+0A0h+arg_8], 4
0x18005dadd  mov     rcx, [rbp+0A8h]; this
0x18005dae4  test    rax, rax
0x18005dae7  jz      loc_18005DCFF
0x18005daed  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x18005daf2  mov     word ptr [rsp+1A0h+var_140], r13w
0x18005daf8  mov     [rbp+0A0h+arg_0], 0
0x18005db03  mov     rsi, [rbp+0A0h+arg_10]
0x18005db0a  mov     r14, [rsi]
0x18005db0d  mov     [rbp+0A0h+arg_0], 0
0x18005db18  movups  xmm6, xmmword ptr [rsp+1A0h+pvarg]
0x18005db1d  movsd   xmm7, qword ptr [rbp+0A0h+pvarg+10h]
0x18005db22  lea     rcx, [rbp+0A0h+var_110]; pvarg
0x18005db26  call    cs:__imp_VariantInit
0x18005db2c  nop
0x18005db2d  movups  xmm8, xmmword ptr [rbp+0A0h+var_110]
0x18005db32  movsd   xmm9, qword ptr [rbp+0A0h+var_110+10h]
0x18005db38  movups  xmm10, xmmword ptr [rsp+1A0h+var_140]
0x18005db3e  movsd   xmm11, qword ptr [rsp+1A0h+var_140+10h]
0x18005db45  mov     r15, [rdi]
0x18005db48  lea     rcx, [rdi+8]
0x18005db4c  cmp     qword ptr [rcx+18h], 7
0x18005db51  jbe     short loc_18005DB56
0x18005db53  mov     rcx, [rcx]; psz
0x18005db56  call    cs:__imp_SysAllocString
0x18005db5c  mov     rbx, rax
0x18005db5f  mov     [rsp+1A0h+var_150], rax
0x18005db64  mov     [rbp+0A0h+arg_8], r13d
0x18005db6b  mov     rcx, [rbp+0A8h]; this
0x18005db72  test    rax, rax
0x18005db75  jz      loc_18005DD11
0x18005db7b  movaps  [rbp+0A0h+var_F0], xmm6
0x18005db7f  movsd   [rbp+0A0h+var_E0], xmm7
0x18005db84  movaps  [rbp+0A0h+var_D0], xmm8
0x18005db89  movsd   [rbp+0A0h+var_C0], xmm9
0x18005db8f  movaps  xmmword ptr [rbp+0A0h+var_B0], xmm10
0x18005db94  movsd   [rbp+0A0h+var_A0], xmm11
0x18005db9a  lea     rax, [rbp+0A0h+arg_0]
0x18005dba1  mov     [rsp+1A0h+var_160], rax
0x18005dba6  lea     rax, [rbp+0A0h+var_F0]
0x18005dbaa  mov     [rsp+1A0h+var_168], rax
0x18005dbaf  mov     [rsp+1A0h+var_170], 5
0x18005dbb7  lea     rax, [rbp+0A0h+var_D0]
0x18005dbbb  mov     [rsp+1A0h+var_178], rax
0x18005dbc0  lea     rax, [rbp+0A0h+var_B0]
0x18005dbc4  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18005dbc9  mov     r9d, 6
0x18005dbcf  mov     r8, r15
0x18005dbd2  mov     rdx, rbx
0x18005dbd5  mov     rcx, rsi
0x18005dbd8  mov     rax, [r14+88h]
0x18005dbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dbe4  mov     rcx, [rbp+0A8h]; this
0x18005dbeb  test    eax, eax
0x18005dbed  js      loc_18005DCC3
0x18005dbf3  mov     rcx, rbx; bstrString
0x18005dbf6  call    cs:__imp_SysFreeString
0x18005dbfc  nop
0x18005dbfd  lea     rcx, [rbp+0A0h+var_110]; pvarg
0x18005dc01  call    cs:__imp_VariantClear
0x18005dc07  mov     rcx, rdi; this
0x18005dc0a  call    ?Protect@Task@Service@Windows@@AEAAXXZ; Windows::Service::Task::Protect(void)
0x18005dc0f  mov     rdx, [rbp+0A0h+arg_0]; struct IRegisteredTask *
0x18005dc16  call    ?LogTaskModified@Task@Service@Windows@@AEAAXPEAUIRegisteredTask@@@Z; Windows::Service::Task::LogTaskModified(IRegisteredTask *)
0x18005dc1b  nop
0x18005dc1c  mov     rcx, [rbp+0A0h+arg_0]
0x18005dc23  test    rcx, rcx
0x18005dc26  jz      short loc_18005DC35
0x18005dc28  mov     rax, [rcx]
0x18005dc2b  mov     rax, [rax+10h]
0x18005dc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc34  nop
0x18005dc35  lea     rcx, [rsp+1A0h+var_140]; pvarg
0x18005dc3a  call    cs:__imp_VariantClear
0x18005dc40  nop
0x18005dc41  mov     rcx, [rbp+0A0h+arg_10]
0x18005dc48  test    rcx, rcx
0x18005dc4b  jz      short loc_18005DC5A
0x18005dc4d  mov     rax, [rcx]
0x18005dc50  mov     rax, [rax+10h]
0x18005dc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc59  nop
0x18005dc5a  mov     rcx, [rsp+1A0h+bstrString]; bstrString
0x18005dc5f  test    rcx, rcx
0x18005dc62  jz      short loc_18005DC6B
0x18005dc64  call    cs:__imp_SysFreeString
0x18005dc6a  nop
0x18005dc6b  mov     rcx, [rbp+0A0h+arg_18]
0x18005dc72  test    rcx, rcx
0x18005dc75  jz      short loc_18005DC84
0x18005dc77  mov     rax, [rcx]
0x18005dc7a  mov     rax, [rax+10h]
0x18005dc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc83  nop
0x18005dc84  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x18005dc89  call    cs:__imp_VariantClear
0x18005dc8f  lea     r11, [rsp+1A0h+var_30]
0x18005dc97  movaps  xmm6, xmmword ptr [r11-10h]
0x18005dc9c  movaps  xmm7, xmmword ptr [r11-20h]
0x18005dca1  movaps  xmm8, xmmword ptr [r11-30h]
0x18005dca6  movaps  xmm9, xmmword ptr [r11-40h]
0x18005dcab  movaps  xmm10, xmmword ptr [r11-50h]
0x18005dcb0  movaps  xmm11, xmmword ptr [r11-60h]
0x18005dcb5  mov     rsp, r11
0x18005dcb8  pop     r15
0x18005dcba  pop     r14
0x18005dcbc  pop     r13
0x18005dcbe  pop     rdi
0x18005dcbf  pop     rsi
0x18005dcc0  pop     rbx
0x18005dcc1  pop     rbp
0x18005dcc2  retn
0x18005dcc3  mov     r9d, eax; char *
0x18005dcc6  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005dccd  mov     edx, 0E7h; void *
0x18005dcd2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005dcd8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005dcdf  mov     edx, 15F3h; void *
0x18005dce4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005dcea  mov     r9d, eax; char *
0x18005dced  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005dcf4  mov     edx, 0D8h; void *
0x18005dcf9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005dcff  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005dd06  mov     edx, 15F3h; void *
0x18005dd0b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005dd11  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005dd18  mov     edx, 15F3h; void *
0x18005dd1d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
