# _anonymous_namespace_::ActionLaunch::Set

- ea: `0x18001a7d8`
- end: `0x18001ab9a`
- name: `_anonymous_namespace_::ActionLaunch::Set`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003c10`

## callees

- `0x180003840`
- `0x18000aa80`
- `0x18000ae10`
- `0x18000b240`
- `0x18000b4f0`
- `0x18000c9e0`
- `0x18000cd60`
- `0x18000d1f0`
- `0x18000e2c0`
- `0x18000e454`
- `0x18000ec88`
- `0x18000f4cc`
- `0x18001a7d8`
- `0x18001b484`
- `0x180020c02`
- `0x180020c30`

## import_xrefs

- `UBPM!UbpmTriggerConsumerRegister` at `0x18001aaa9`
- `UBPM!UbpmTriggerConsumerRegister` at `0x18001aaa9`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18001aaef`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18001aaef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a8f3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a8f3`

## string_xrefs

- `0x18001aa3a`: `NT TASK\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall anonymous_namespace_::ActionLaunch::Set(__int64 a1, __int64 a2, unsigned __int16 **a3)
{
  __int64 v4; // rsi
  int SecurityInfo; // ebx
  __int64 v7; // rax
  __int64 last_of; // rax
  __int64 v9; // r11
  SecurityContext *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  void *v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rax
  int v16; // ecx
  BOOL v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  struct _DAB_SID_INFO *v28[3]; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+80h] [rbp-80h]
  int v30; // [rsp+84h] [rbp-7Ch]
  int v31; // [rsp+ACh] [rbp-54h]
  void *v32; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v33; // [rsp+C0h] [rbp-40h] BYREF
  struct _SID_AND_ATTRIBUTES *v34; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v35[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v36; // [rsp+E0h] [rbp-20h]
  int v37; // [rsp+F0h] [rbp-10h]
  __int128 *v38; // [rsp+F8h] [rbp-8h]
  _QWORD v39[3]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v40; // [rsp+158h] [rbp+58h]
  _QWORD v41[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v42; // [rsp+178h] [rbp+78h]
  _QWORD v43[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v44; // [rsp+198h] [rbp+98h]
  _BYTE v45[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Dst[264]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = a2;
  v40 = 7;
  v39[2] = 0;
  LOWORD(v39[0]) = 0;
  v42 = 7;
  v41[2] = 0;
  LOWORD(v41[0]) = 0;
  v44 = 7;
  v43[2] = 0;
  LOWORD(v43[0]) = 0;
  if ( !a3 )
    goto LABEL_24;
  if ( !*a3 )
    goto LABEL_24;
  if ( !a2 )
    goto LABEL_24;
  memset_0(&v27, 0, 0x70u);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  memset_0(v35, 0, 0x68u);
  *(_OWORD *)(a1 + 104) = 0;
  *(_OWORD *)(a1 + 120) = 0;
  *(_OWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 8) = v4;
  Action::CreateUniqueId(a1, v41);
  *(_QWORD *)(a1 + 160) = StrDup(*a3);
  *(_QWORD *)(a1 + 168) = StrDup(a3[1]);
  if ( ExpandEnvironmentStringsW(*(LPCWSTR *)(a1 + 160), Dst, 0x104u) - 1 > 0x103 )
    goto LABEL_24;
  SecurityInfo = 0;
  *(_DWORD *)(a1 + 176) = *(_DWORD *)(v4 + 44) & 0x20;
  v7 = std::char_traits<unsigned short>::length(Dst);
  std::wstring::assign(v39, Dst, v7);
  last_of = std::wstring::find_last_of(v39);
  if ( last_of != -1 )
    std::wstring::erase(v39, 0, last_of + 1);
  *(_DWORD *)(a1 + 104) = 1;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 112) = Dst;
  *(_QWORD *)(a1 + 120) = *(_QWORD *)(a1 + 168);
  if ( !CSchedule::IsScheduleOwner(*(CSchedule **)(a1 + 8), L"S-1-5-18", 0) )
  {
    v10 = *(SecurityContext **)(v9 + 272);
    if ( !v10 )
    {
LABEL_18:
      SecurityInfo = -2147467259;
      goto LABEL_22;
    }
    SecurityInfo = SecurityContext::GetSecurityInfo(v10, v28, &v32, &v33, &v34);
    if ( SecurityInfo < 0 )
      goto LABEL_22;
    v29 = 2;
    v27 = 1;
    v28[1] = 0;
    v30 = 2;
    v31 = 0;
    *(_QWORD *)(a1 + 136) = &v27;
  }
  LODWORD(v25) = 1;
  v11 = v41;
  if ( v42 >= 8 )
    v11 = (_QWORD *)v41[0];
  *(_QWORD *)&v24 = v11;
  v12 = v39;
  if ( v40 >= 8 )
    v12 = (_QWORD *)v39[0];
  *((_QWORD *)&v24 + 1) = v12;
  *((_QWORD *)&v25 + 1) = a1 + 104;
  v37 = 1;
  v38 = &v24;
  v13 = (void *)std::operator+<unsigned short>(v45, L"NT TASK\\", v41);
  std::wstring::operator=(v43, v13);
  LOBYTE(v14) = 1;
  std::wstring::_Tidy(v45, v14, 0);
  v15 = v43;
  if ( v44 >= 8 )
    v15 = (_QWORD *)v43[0];
  v35[1] = v15;
  v35[0] = a1 + 88;
  v36 = 4;
  v23 = 0;
  if ( (unsigned int)UbpmTriggerConsumerRegister(v35, &v23) )
    goto LABEL_18;
  if ( (byte_180030D03 & 4) != 0 )
    McTemplateU0jzz_EventWriteTransfer(
      v16,
      (unsigned int)LaunchSet,
      *(_QWORD *)(a1 + 8) + 16,
      *(_QWORD *)(a1 + 160),
      *(_QWORD *)(a1 + 168));
  UbpmCloseTriggerConsumer(v23);
LABEL_22:
  TsiFreeActionAccountInfoSecurityParameters((struct _UBPM_ACTION_ACCOUNT_INFO *)&v27);
  if ( SecurityInfo >= 0 )
  {
    v17 = *(_QWORD *)(a1 + 160) != 0;
    LOBYTE(a2) = 1;
    std::wstring::_Tidy(v43, a2, 0);
    LOBYTE(v18) = 1;
    std::wstring::_Tidy(v41, v18, 0);
    LOBYTE(v19) = 1;
    std::wstring::_Tidy(v39, v19, 0);
    return v17;
  }
LABEL_24:
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v43, a2, 0);
  LOBYTE(v21) = 1;
  std::wstring::_Tidy(v41, v21, 0);
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(v39, v22, 0);
  return 0;
}

```

## disassembly

```asm
0x18001a7d8  mov     [rsp-8+arg_8], rbx
0x18001a7dd  mov     [rsp-8+arg_18], rsi
0x18001a7e2  push    rbp
0x18001a7e3  push    rdi
0x18001a7e4  push    r14
0x18001a7e6  lea     rbp, [rsp-2E0h]
0x18001a7ee  sub     rsp, 3E0h
0x18001a7f5  mov     rax, cs:__security_cookie
0x18001a7fc  xor     rax, rsp
0x18001a7ff  mov     [rbp+2F0h+var_20], rax
0x18001a806  mov     rbx, r8
0x18001a809  mov     rsi, rdx
0x18001a80c  mov     rdi, rcx
0x18001a80f  mov     ecx, 7
0x18001a814  mov     [rbp+2F0h+var_298], rcx
0x18001a818  mov     [rbp+2F0h+var_2A0], 0
0x18001a820  xor     eax, eax
0x18001a822  mov     word ptr [rbp+2F0h+var_2B0], ax
0x18001a826  mov     [rbp+2F0h+var_278], rcx
0x18001a82a  mov     [rbp+2F0h+var_280], rax
0x18001a82e  mov     word ptr [rbp+2F0h+var_290], ax
0x18001a832  mov     [rbp+2F0h+var_258], rcx
0x18001a839  mov     [rbp+2F0h+var_260], rax
0x18001a840  mov     word ptr [rbp+2F0h+var_270], ax
0x18001a847  test    r8, r8
0x18001a84a  jz      loc_18001AB42
0x18001a850  cmp     [r8], rax
0x18001a853  jz      loc_18001AB42
0x18001a859  test    rdx, rdx
0x18001a85c  jz      loc_18001AB42
0x18001a862  xor     edx, edx; Val
0x18001a864  lea     r8d, [rcx+69h]; Size
0x18001a868  lea     rcx, [rsp+3F0h+var_390]; void *
0x18001a86d  call    memset_0
0x18001a872  xorps   xmm0, xmm0
0x18001a875  xor     eax, eax
0x18001a877  movups  [rsp+3F0h+var_3B8], xmm0
0x18001a87c  movups  [rsp+3F0h+var_3A8], xmm0
0x18001a881  mov     [rsp+3F0h+var_398], rax
0x18001a886  xor     edx, edx; Val
0x18001a888  lea     r8d, [rax+68h]; Size
0x18001a88c  lea     rcx, [rbp+2F0h+var_320]; void *
0x18001a890  call    memset_0
0x18001a895  lea     r14, [rdi+68h]
0x18001a899  xorps   xmm0, xmm0
0x18001a89c  xor     eax, eax
0x18001a89e  movups  xmmword ptr [r14], xmm0
0x18001a8a2  movups  xmmword ptr [r14+10h], xmm0
0x18001a8a7  movups  xmmword ptr [r14+20h], xmm0
0x18001a8ac  mov     [r14+30h], rax
0x18001a8b0  mov     [rdi+8], rsi
0x18001a8b4  lea     rdx, [rbp+2F0h+var_290]
0x18001a8b8  mov     rcx, rdi
0x18001a8bb  call    ?CreateUniqueId@Action@@IEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Action::CreateUniqueId(std::wstring *)
0x18001a8c0  mov     rcx, [rbx]; Src
0x18001a8c3  call    ?StrDup@@YAPEAGPEAG@Z; StrDup(ushort *)
0x18001a8c8  mov     [rdi+0A0h], rax
0x18001a8cf  mov     rcx, [rbx+8]; Src
0x18001a8d3  call    ?StrDup@@YAPEAGPEAG@Z; StrDup(ushort *)
0x18001a8d8  mov     [rdi+0A8h], rax
0x18001a8df  mov     r8d, 104h; nSize
0x18001a8e5  lea     rdx, [rbp+2F0h+Dst]; lpDst
0x18001a8ec  mov     rcx, [rdi+0A0h]; lpSrc
0x18001a8f3  call    cs:__imp_ExpandEnvironmentStringsW
0x18001a8f9  dec     eax
0x18001a8fb  cmp     eax, 103h
0x18001a900  ja      loc_18001AB42
0x18001a906  xor     ebx, ebx
0x18001a908  mov     eax, [rsi+2Ch]
0x18001a90b  and     eax, 20h
0x18001a90e  mov     [rdi+0B0h], eax
0x18001a914  lea     rcx, [rbp+2F0h+Dst]
0x18001a91b  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001a920  mov     r8, rax
0x18001a923  lea     rdx, [rbp+2F0h+Dst]
0x18001a92a  lea     rcx, [rbp+2F0h+var_2B0]
0x18001a92e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001a933  lea     rcx, [rbp+2F0h+var_2B0]
0x18001a937  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find_last_of(ushort const *,unsigned __int64)
0x18001a93c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a940  jz      short loc_18001A951
0x18001a942  lea     r8, [rax+1]
0x18001a946  xor     edx, edx
0x18001a948  lea     rcx, [rbp+2F0h+var_2B0]
0x18001a94c  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18001a951  mov     dword ptr [r14], 1
0x18001a958  mov     [rdi+88h], rbx
0x18001a95f  lea     rax, [rbp+2F0h+Dst]
0x18001a966  mov     [rdi+70h], rax
0x18001a96a  mov     rax, [rdi+0A8h]
0x18001a971  mov     [rdi+78h], rax
0x18001a975  mov     r11, [rdi+8]
0x18001a979  xor     r8d, r8d; unsigned __int16 *
0x18001a97c  lea     rdx, aS1518; "S-1-5-18"
0x18001a983  mov     rcx, r11; this
0x18001a986  call    ?IsScheduleOwner@CSchedule@@QEAAHQEAG0@Z; CSchedule::IsScheduleOwner(ushort * const,ushort * const)
0x18001a98b  test    eax, eax
0x18001a98d  jnz     short loc_18001A9F3
0x18001a98f  mov     rcx, [r11+110h]; this
0x18001a996  test    rcx, rcx
0x18001a999  jz      loc_18001AAB3
0x18001a99f  lea     rax, [rbp+2F0h+var_328]
0x18001a9a3  mov     [rsp+3F0h+var_3D0], rax; struct _SID_AND_ATTRIBUTES **
0x18001a9a8  lea     r9, [rbp+2F0h+var_330]; unsigned int *
0x18001a9ac  lea     r8, [rbp+2F0h+var_340]; void **
0x18001a9b0  lea     rdx, [rsp+3F0h+var_388]; struct _DAB_SID_INFO **
0x18001a9b5  call    ?GetSecurityInfo@SecurityContext@@QEAAJPEAPEAU_DAB_SID_INFO@@PEAPEAXPEAKPEAPEAU_SID_AND_ATTRIBUTES@@@Z; SecurityContext::GetSecurityInfo(_DAB_SID_INFO * *,void * *,ulong *,_SID_AND_ATTRIBUTES * *)
0x18001a9ba  mov     ebx, eax
0x18001a9bc  test    eax, eax
0x18001a9be  js      loc_18001AAF5
0x18001a9c4  mov     eax, 2
0x18001a9c9  mov     [rbp+2F0h+var_370], eax
0x18001a9cc  mov     [rsp+3F0h+var_390], 1
0x18001a9d4  mov     [rsp+3F0h+var_380], 0
0x18001a9dd  mov     [rbp+2F0h+var_36C], eax
0x18001a9e0  mov     [rbp+2F0h+var_344], 0
0x18001a9e7  lea     rax, [rsp+3F0h+var_390]
0x18001a9ec  mov     [rdi+88h], rax
0x18001a9f3  mov     dword ptr [rsp+3F0h+var_3A8], 1
0x18001a9fb  lea     rax, [rbp+2F0h+var_290]
0x18001a9ff  cmp     [rbp+2F0h+var_278], 8
0x18001aa04  cmovnb  rax, [rbp+2F0h+var_290]
0x18001aa09  mov     qword ptr [rsp+3F0h+var_3B8], rax
0x18001aa0e  lea     rax, [rbp+2F0h+var_2B0]
0x18001aa12  cmp     [rbp+2F0h+var_298], 8
0x18001aa17  cmovnb  rax, [rbp+2F0h+var_2B0]
0x18001aa1c  mov     qword ptr [rsp+3F0h+var_3B8+8], rax
0x18001aa21  mov     qword ptr [rsp+3F0h+var_3A8+8], r14
0x18001aa26  mov     [rbp+2F0h+var_300], 1
0x18001aa2d  lea     rax, [rsp+3F0h+var_3B8]
0x18001aa32  mov     [rbp+2F0h+var_2F8], rax
0x18001aa36  lea     r8, [rbp+2F0h+var_290]
0x18001aa3a  lea     rdx, aNtTask; "NT TASK\\"
0x18001aa41  lea     rcx, [rbp+2F0h+var_250]
0x18001aa48  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x18001aa4d  mov     rdx, rax; Src
0x18001aa50  lea     rcx, [rbp+2F0h+var_270]; void *
0x18001aa57  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001aa5c  xor     r8d, r8d
0x18001aa5f  mov     dl, 1
0x18001aa61  lea     rcx, [rbp+2F0h+var_250]
0x18001aa68  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001aa6d  lea     rax, [rbp+2F0h+var_270]
0x18001aa74  cmp     [rbp+2F0h+var_258], 8
0x18001aa7c  cmovnb  rax, [rbp+2F0h+var_270]
0x18001aa84  mov     [rbp+2F0h+var_318], rax
0x18001aa88  lea     rax, [rdi+58h]
0x18001aa8c  mov     [rbp+2F0h+var_320], rax
0x18001aa90  mov     [rbp+2F0h+var_310], 4
0x18001aa97  mov     [rsp+3F0h+var_3C0], 0
0x18001aaa0  lea     rdx, [rsp+3F0h+var_3C0]
0x18001aaa5  lea     rcx, [rbp+2F0h+var_320]
0x18001aaa9  call    cs:__imp_UbpmTriggerConsumerRegister
0x18001aaaf  test    eax, eax
0x18001aab1  jz      short loc_18001AABA
0x18001aab3  mov     ebx, 80004005h
0x18001aab8  jmp     short loc_18001AAF5
0x18001aaba  test    cs:byte_180030D03, 4
0x18001aac1  jz      short loc_18001AAEA
0x18001aac3  mov     r8, [rdi+8]
0x18001aac7  add     r8, 10h
0x18001aacb  mov     rax, [rdi+0A8h]
0x18001aad2  mov     [rsp+3F0h+var_3D0], rax
0x18001aad7  mov     r9, [rdi+0A0h]
0x18001aade  lea     rdx, LaunchSet
0x18001aae5  call    McTemplateU0jzz_EventWriteTransfer
0x18001aaea  mov     rcx, [rsp+3F0h+var_3C0]
0x18001aaef  call    cs:__imp_UbpmCloseTriggerConsumer
0x18001aaf5  lea     rcx, [rsp+3F0h+var_390]; struct _UBPM_ACTION_ACCOUNT_INFO *
0x18001aafa  call    ?TsiFreeActionAccountInfoSecurityParameters@@YAXPEAU_UBPM_ACTION_ACCOUNT_INFO@@@Z; TsiFreeActionAccountInfoSecurityParameters(_UBPM_ACTION_ACCOUNT_INFO *)
0x18001aaff  test    ebx, ebx
0x18001ab01  js      short loc_18001AB42
0x18001ab03  xor     ebx, ebx
0x18001ab05  cmp     [rdi+0A0h], rbx
0x18001ab0c  setnz   bl
0x18001ab0f  xor     r8d, r8d
0x18001ab12  mov     dl, 1
0x18001ab14  lea     rcx, [rbp+2F0h+var_270]
0x18001ab1b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab20  nop
0x18001ab21  xor     r8d, r8d
0x18001ab24  mov     dl, 1
0x18001ab26  lea     rcx, [rbp+2F0h+var_290]
0x18001ab2a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab2f  nop
0x18001ab30  xor     r8d, r8d
0x18001ab33  mov     dl, 1
0x18001ab35  lea     rcx, [rbp+2F0h+var_2B0]
0x18001ab39  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab3e  mov     eax, ebx
0x18001ab40  jmp     short loc_18001AB73
0x18001ab42  xor     r8d, r8d
0x18001ab45  mov     dl, 1
0x18001ab47  lea     rcx, [rbp+2F0h+var_270]
0x18001ab4e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab53  nop
0x18001ab54  xor     r8d, r8d
0x18001ab57  mov     dl, 1
0x18001ab59  lea     rcx, [rbp+2F0h+var_290]
0x18001ab5d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab62  nop
0x18001ab63  xor     r8d, r8d
0x18001ab66  mov     dl, 1
0x18001ab68  lea     rcx, [rbp+2F0h+var_2B0]
0x18001ab6c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab71  xor     eax, eax
0x18001ab73  mov     rcx, [rbp+2F0h+var_20]
0x18001ab7a  xor     rcx, rsp; StackCookie
0x18001ab7d  call    __security_check_cookie
0x18001ab82  lea     r11, [rsp+3F0h+var_10]
0x18001ab8a  mov     rbx, [r11+28h]
0x18001ab8e  mov     rsi, [r11+38h]
0x18001ab92  mov     rsp, r11
0x18001ab95  pop     r14
0x18001ab97  pop     rdi
0x18001ab98  pop     rbp
0x18001ab99  retn
```
