# CServiceModule::_DelayStartTabtip(ulong)

- ea: `0x1800282a0`
- end: `0x180028519`
- name: `?_DelayStartTabtip@CServiceModule@@AEAA_NK@Z`
- size: `633`
- prototype: `char __fastcall(CServiceModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024260`

## callees

- `0x180002940`
- `0x180011400`
- `0x1800117c0`
- `0x180012dc0`
- `0x180013080`
- `0x1800137e0`
- `0x180013950`
- `0x18001a674`
- `0x18001a6c0`
- `0x18001bc04`
- `0x18001bc20`
- `0x18001c04c`
- `0x18001fe10`
- `0x1800282a0`
- `0x180028578`
- `0x180028a24`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800284b2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800284b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800284ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800284ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028402`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028402`
- `WTSAPI32!WTSQueryUserToken` at `0x18002836b`
- `WTSAPI32!WTSQueryUserToken` at `0x18002836b`

## string_xrefs

- `0x1800282d3`: `drivers\tablet\platform\pen\penservice\penservice.cpp`

## pseudocode

```c
char __fastcall CServiceModule::_DelayStartTabtip(CServiceModule *this, unsigned int a2)
{
  const unsigned __int16 *v4; // rdx
  const char *v5; // r9
  char v6; // r15
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // r8d
  void *EventInSession; // rsi
  unsigned __int16 *v10; // rax
  const struct std::nothrow_t *v11; // rdx
  unsigned __int16 *v12; // rdi
  unsigned int v13; // r8d
  unsigned __int16 *v14; // rax
  const struct std::nothrow_t *v15; // rdx
  unsigned __int16 *v16; // rbx
  unsigned int v17; // r8d
  _QWORD *v18; // rax
  void *v19; // rbx
  unsigned int v20; // ecx
  unsigned int v21; // r14d
  unsigned int v22; // r14d
  __int64 v23; // rcx
  ULONG dwMilliseconds; // [rsp+20h] [rbp-40h]
  HLOCAL v26[2]; // [rsp+30h] [rbp-30h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-20h] BYREF
  __int16 v28; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HLOCAL hMem; // [rsp+A0h] [rbp+40h] BYREF
  void *phToken; // [rsp+A8h] [rbp+48h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x7ED,
      (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
      v5);
  v6 = 0;
  Block[0] = 0;
  Block[1] = 0;
  v28 = 0;
  if ( (int)StringSd::SetOwner((StringSd *)Block, v4) >= 0 && (int)StringSd::SetGroup((StringSd *)Block, v7) >= 0 )
  {
    EventInSession = 0;
    v10 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)0x1F0003, v8);
    v12 = v10;
    hMem = v10;
    if ( v10 && StringSd::AddDaclAce((StringSd *)Block, v10) >= 0 )
    {
      phToken = 0;
      v26[0] = 0;
      if ( WTSQueryUserToken(a2, &phToken) && (int)GetLogonSessionSid(phToken, (LPWSTR *)v26) >= 0 )
      {
        v14 = StringAce::Allow((StringAce *)v26[0], (const unsigned __int16 *)0x1F0003, v13);
        v16 = v14;
        v26[1] = v14;
        if ( v14 && StringSd::AddDaclAce((StringSd *)Block, v14) >= 0 )
        {
          hMem = 0;
          if ( StringSd::GetSecurityDescriptor((StringSd *)Block, &hMem) >= 0 )
            EventInSession = CreateEventInSession(a2, L"ShellDesktopSwitchEvent", v17, 1, dwMilliseconds, hMem);
          LocalFree(hMem);
        }
        operator delete(v16, v15);
      }
      SH<void *,SH_HANDLE>::Reset(&phToken);
      LocalFree(v26[0]);
    }
    operator delete(v12, v11);
    if ( EventInSession )
    {
      v18 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v18;
      if ( v18 )
      {
        *v18 = EventInSession;
        *((_DWORD *)v18 + 2) = a2;
        v18[2] = this;
        v20 = *((_DWORD *)this + 139);
        v21 = v20 + 1;
        if ( v20 + 1 < v20
          || (int)CPbPreallocArray<CServiceModule::SessionDelayHandles,10>::EnsureSize((char *)this + 384) < 0 )
        {
          operator delete(v19, (const struct std::nothrow_t *)0x18);
        }
        else
        {
          *((_DWORD *)this + 139) = v21;
          v22 = v21 - 1;
          v23 = 16LL * v22;
          *(_QWORD *)(v23 + *((_QWORD *)this + 68)) = EventInSession;
          if ( RegisterWaitForSingleObject(
                 (PHANDLE)(*((_QWORD *)this + 68) + 8LL + v23),
                 EventInSession,
                 CServiceModule::s_LogonCallback,
                 v19,
                 0xEA60u,
                 8u) )
          {
            EventInSession = 0;
            v6 = 1;
          }
          else
          {
            operator delete(v19, (const struct std::nothrow_t *)0x18);
            CPbPreallocArray<CServiceModule::SessionDelayHandles,10>::Remove((char *)this + 384, v22);
          }
        }
      }
      CloseHandle(EventInSession);
    }
  }
  operator delete(Block[0]);
  return v6;
}

```

## disassembly

```asm
0x1800282a0  mov     [rsp-28h+arg_0], rbx
0x1800282a5  mov     [rsp-28h+arg_8], rsi
0x1800282aa  push    rbp
0x1800282ab  push    rdi
0x1800282ac  push    r13
0x1800282ae  push    r14
0x1800282b0  push    r15
0x1800282b2  mov     rbp, rsp
0x1800282b5  sub     rsp, 60h
0x1800282b9  mov     r14d, edx
0x1800282bc  mov     r13, rcx
0x1800282bf  mov     rbx, [rbp+28h]
0x1800282c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_59994706@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl(void)'::`2'::impl
0x1800282ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(void)
0x1800282cf  test    al, al
0x1800282d1  jz      short loc_1800282E8
0x1800282d3  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x1800282da  mov     edx, 7EDh; void *
0x1800282df  mov     rcx, rbx; this
0x1800282e2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800282e8  xor     r15b, r15b
0x1800282eb  mov     [rbp+Block], 0
0x1800282f3  mov     [rbp+var_18], 0
0x1800282fb  mov     [rbp+var_10], 0
0x180028301  lea     rcx, [rbp+Block]; this
0x180028305  call    ?SetOwner@StringSd@@QEAAJPEBG@Z; StringSd::SetOwner(ushort const *)
0x18002830a  test    eax, eax
0x18002830c  js      loc_1800284F4
0x180028312  lea     rcx, [rbp+Block]; this
0x180028316  call    ?SetGroup@StringSd@@QEAAJPEBG@Z; StringSd::SetGroup(ushort const *)
0x18002831b  test    eax, eax
0x18002831d  js      loc_1800284F4
0x180028323  xor     esi, esi
0x180028325  mov     ebx, 1F0003h
0x18002832a  mov     edx, ebx; unsigned __int16 *
0x18002832c  lea     rcx, aSy; "SY"
0x180028333  call    ?Allow@StringAce@@YAPEAGPEBGK@Z; StringAce::Allow(ushort const *,ulong)
0x180028338  mov     rdi, rax
0x18002833b  mov     [rbp+hMem], rax
0x18002833f  test    rax, rax
0x180028342  jz      loc_180028409
0x180028348  mov     rdx, rax; unsigned __int16 *
0x18002834b  lea     rcx, [rbp+Block]; this
0x18002834f  call    ?AddDaclAce@StringSd@@QEAAJPEBG@Z; StringSd::AddDaclAce(ushort const *)
0x180028354  test    eax, eax
0x180028356  js      loc_180028409
0x18002835c  mov     [rbp+phToken], rsi
0x180028360  mov     [rbp+var_30], rsi
0x180028364  lea     rdx, [rbp+phToken]; phToken
0x180028368  mov     ecx, r14d; SessionId
0x18002836b  call    cs:__imp_WTSQueryUserToken
0x180028371  test    eax, eax
0x180028373  jz      short loc_1800283F4
0x180028375  lea     rdx, [rbp+var_30]; StringSid
0x180028379  mov     rcx, [rbp+phToken]; TokenHandle
0x18002837d  call    ?GetLogonSessionSid@@YAJPEAXPEAPEAG@Z; GetLogonSessionSid(void *,ushort * *)
0x180028382  test    eax, eax
0x180028384  js      short loc_1800283F4
0x180028386  mov     edx, ebx; unsigned __int16 *
0x180028388  mov     rcx, [rbp+var_30]; this
0x18002838c  call    ?Allow@StringAce@@YAPEAGPEBGK@Z; StringAce::Allow(ushort const *,ulong)
0x180028391  mov     rbx, rax
0x180028394  mov     [rbp+var_28], rax
0x180028398  test    rax, rax
0x18002839b  jz      short loc_1800283EC
0x18002839d  mov     rdx, rax; unsigned __int16 *
0x1800283a0  lea     rcx, [rbp+Block]; this
0x1800283a4  call    ?AddDaclAce@StringSd@@QEAAJPEBG@Z; StringSd::AddDaclAce(ushort const *)
0x1800283a9  test    eax, eax
0x1800283ab  js      short loc_1800283EC
0x1800283ad  mov     [rbp+hMem], rsi
0x1800283b1  lea     rdx, [rbp+hMem]; void **
0x1800283b5  lea     rcx, [rbp+Block]; this
0x1800283b9  call    ?GetSecurityDescriptor@StringSd@@QEAAJPEAPEAX@Z; StringSd::GetSecurityDescriptor(void * *)
0x1800283be  test    eax, eax
0x1800283c0  js      short loc_1800283E1
0x1800283c2  mov     rax, [rbp+hMem]
0x1800283c6  mov     qword ptr [rsp+60h+dwFlags], rax; void *
0x1800283cb  lea     r9d, [rsi+1]; int
0x1800283cf  lea     rdx, aShelldesktopsw; "ShellDesktopSwitchEvent"
0x1800283d6  mov     ecx, r14d; unsigned int
0x1800283d9  call    ?CreateEventInSession@@YAPEAXKPEAGKHHPEAX@Z; CreateEventInSession(ulong,ushort *,ulong,int,int,void *)
0x1800283de  mov     rsi, rax
0x1800283e1  mov     rcx, [rbp+hMem]; hMem
0x1800283e5  call    cs:__imp_LocalFree
0x1800283eb  nop
0x1800283ec  mov     rcx, rbx; void *
0x1800283ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800283f4  lea     rcx, [rbp+phToken]
0x1800283f8  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800283fd  nop
0x1800283fe  mov     rcx, [rbp+var_30]; hMem
0x180028402  call    cs:__imp_LocalFree
0x180028408  nop
0x180028409  mov     rcx, rdi; void *
0x18002840c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028411  test    rsi, rsi
0x180028414  jz      loc_1800284F4
0x18002841a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028421  mov     ecx, 18h; unsigned __int64
0x180028426  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002842b  mov     rbx, rax
0x18002842e  test    rax, rax
0x180028431  jz      loc_1800284EA
0x180028437  mov     [rax], rsi
0x18002843a  mov     [rax+8], r14d
0x18002843e  mov     [rax+10h], r13
0x180028442  lea     rdi, [r13+180h]
0x180028449  mov     ecx, [rdi+0ACh]
0x18002844f  lea     r14d, [rcx+1]
0x180028453  cmp     r14d, ecx
0x180028456  jb      loc_1800284DD
0x18002845c  mov     edx, r14d
0x18002845f  mov     rcx, rdi; Src
0x180028462  call    ?EnsureSize@?$CPbPreallocArray@USessionDelayHandles@CServiceModule@@$09@@IEAAJIH@Z; CPbPreallocArray<CServiceModule::SessionDelayHandles,10>::EnsureSize(uint,int)
0x180028467  test    eax, eax
0x180028469  js      short loc_1800284DD
0x18002846b  mov     [rdi+0ACh], r14d
0x180028472  dec     r14d
0x180028475  mov     ecx, r14d
0x180028478  shl     rcx, 4
0x18002847c  mov     rax, [r13+220h]
0x180028483  mov     [rcx+rax], rsi
0x180028487  mov     rax, [r13+220h]
0x18002848e  add     rax, 8
0x180028492  add     rcx, rax; phNewWaitObject
0x180028495  mov     [rsp+60h+dwFlags], 8; dwFlags
0x18002849d  mov     [rsp+60h+dwMilliseconds], 0EA60h; dwMilliseconds
0x1800284a5  mov     r9, rbx; Context
0x1800284a8  lea     r8, ?s_LogonCallback@CServiceModule@@SAXPEAXE@Z; Callback
0x1800284af  mov     rdx, rsi; hObject
0x1800284b2  call    cs:__imp_RegisterWaitForSingleObject
0x1800284b8  test    eax, eax
0x1800284ba  jz      short loc_1800284C3
0x1800284bc  xor     esi, esi
0x1800284be  mov     r15b, 1
0x1800284c1  jmp     short loc_1800284EA
0x1800284c3  mov     edx, 18h; struct std::nothrow_t *
0x1800284c8  mov     rcx, rbx; void *
0x1800284cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800284d0  mov     edx, r14d
0x1800284d3  mov     rcx, rdi
0x1800284d6  call    ?Remove@?$CPbPreallocArray@USessionDelayHandles@CServiceModule@@$09@@QEAAJI@Z; CPbPreallocArray<CServiceModule::SessionDelayHandles,10>::Remove(uint)
0x1800284db  jmp     short loc_1800284EA
0x1800284dd  mov     edx, 18h; struct std::nothrow_t *
0x1800284e2  mov     rcx, rbx; void *
0x1800284e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800284ea  mov     rcx, rsi; hObject
0x1800284ed  call    cs:__imp_CloseHandle
0x1800284f3  nop
0x1800284f4  mov     rcx, [rbp+Block]; Block
0x1800284f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800284fd  mov     al, r15b
0x180028500  lea     r11, [rsp+60h+var_s0]
0x180028505  mov     rbx, [r11+30h]
0x180028509  mov     rsi, [r11+38h]
0x18002850d  mov     rsp, r11
0x180028510  pop     r15
0x180028512  pop     r14
0x180028514  pop     r13
0x180028516  pop     rdi
0x180028517  pop     rbp
0x180028518  retn
```
