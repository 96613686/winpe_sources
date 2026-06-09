# _RpcSmsRouter_AcknowledgeMessage

- ea: `0x180009b60`
- end: `0x180009d33`
- name: `_RpcSmsRouter_AcknowledgeMessage`
- size: `467`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x180009b60`
- `0x18000f38c`
- `0x1800152ac`
- `0x18002643c`
- `0x180026f00`
- `0x1800270b0`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## string_xrefs

- `0x180009bf8`: `Failed security check.`
- `0x180009c49`: `Failed to get service manager instance.`
- `0x180009cbf`: `AcknowledgeMessage for RegId: %S, AppName: %S, UserSid: %S, MsgId: %llu failed`
- `0x180009ccb`: `CSmsServiceManager::AcknowledgeMessage`

## pseudocode

```c
__int64 __fastcall RpcSmsRouter_AcknowledgeMessage(__int64 a1, const wchar_t *a2, unsigned __int64 a3, int a4)
{
  unsigned int v7; // ebx
  unsigned int v8; // edx
  int v9; // r8d
  signed int UserSid; // eax
  int Instance; // eax
  const unsigned __int16 *v12; // rsi
  struct CSmsServiceManager *v13; // rdi
  const unsigned __int16 *v14; // r14
  int v15; // eax
  struct CSmsServiceManager *v17; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v18[2]; // [rsp+50h] [rbp-29h] BYREF
  __m128i v19; // [rsp+60h] [rbp-19h]
  unsigned __int16 *v20[2]; // [rsp+70h] [rbp-9h] BYREF
  __m128i si128; // [rsp+80h] [rbp+7h]

  v17 = 0;
  *(_OWORD *)v20 = 0;
  LOWORD(v20[0]) = 0;
  *(_OWORD *)v18 = 0;
  LOWORD(v18[0]) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v19 = si128;
  if ( !(unsigned int)HasCapability(L"cellularMessaging") )
  {
    v7 = -2147024891;
    v8 = 380;
    v9 = -2147024891;
LABEL_6:
    LogSmsRouterError("_RpcSmsRouter_AcknowledgeMessage", v8, v9, "Failed security check.");
    goto LABEL_19;
  }
  UserSid = CSmsRpcUtils::GetUserSid((__int64)v18);
  v7 = UserSid;
  if ( UserSid < 0 )
  {
    v8 = 386;
LABEL_5:
    v9 = UserSid;
    goto LABEL_6;
  }
  UserSid = CSmsRpcUtils::CalculateAppName(0);
  v7 = UserSid;
  if ( UserSid < 0 )
  {
    v8 = 392;
    goto LABEL_5;
  }
  Instance = CSmsServiceManager::GetInstance(&v17);
  v7 = Instance;
  if ( Instance >= 0 )
  {
    LogSmsRouterInfo("_RpcSmsRouter_AcknowledgeMessage", 0x192u, "Ack RegId: %S MsgId: %llu, Accepted: %lu", a2, a3, a4);
    v12 = (const unsigned __int16 *)v18;
    v13 = v17;
    v14 = (const unsigned __int16 *)v20;
    if ( v19.m128i_i64[1] > 7uLL )
      v12 = v18[0];
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = v20[0];
    v15 = CSmsInterceptor::AcknowledgeMessage((struct CSmsServiceManager *)((char *)v17 + 96), a2, v14, v12, a3, a4);
    v7 = v15;
    if ( v15 < 0 )
      LogSmsRouterError(
        "CSmsServiceManager::AcknowledgeMessage",
        0x144u,
        v15,
        "AcknowledgeMessage for RegId: %S, AppName: %S, UserSid: %S, MsgId: %llu failed",
        a2,
        v14,
        v12,
        a3);
    (*(void (__fastcall **)(struct CSmsServiceManager *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  else
  {
    LogSmsRouterError("_RpcSmsRouter_AcknowledgeMessage", 0x18Eu, Instance, "Failed to get service manager instance.");
  }
LABEL_19:
  std::wstring::~wstring((char **)v18);
  std::wstring::~wstring((char **)v20);
  return v7;
}

```

## disassembly

```asm
0x180009b60  mov     [rsp-8+arg_0], rbx
0x180009b65  push    rbp
0x180009b66  push    rsi
0x180009b67  push    rdi
0x180009b68  push    r12
0x180009b6a  push    r13
0x180009b6c  push    r14
0x180009b6e  push    r15
0x180009b70  lea     rbp, [rsp-27h]
0x180009b75  sub     rsp, 0A0h
0x180009b7c  mov     rax, cs:__security_cookie
0x180009b83  xor     rax, rsp
0x180009b86  mov     [rbp+57h+var_40], rax
0x180009b8a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180009b92  lea     rcx, SourceString; "cellularMessaging"
0x180009b99  xorps   xmm0, xmm0
0x180009b9c  mov     [rbp+57h+var_88], 0
0x180009ba4  xor     eax, eax
0x180009ba6  mov     r13d, r9d
0x180009ba9  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180009bad  mov     word ptr [rbp+57h+var_60], ax
0x180009bb1  mov     r12, r8
0x180009bb4  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180009bb8  mov     word ptr [rbp+57h+var_80], ax
0x180009bbc  mov     r15, rdx
0x180009bbf  movdqu  [rbp+57h+var_50], xmm1
0x180009bc4  movdqu  [rbp+57h+var_70], xmm1
0x180009bc9  call    ?HasCapability@@YAHPEBG@Z; HasCapability(ushort const *)
0x180009bce  test    eax, eax
0x180009bd0  jnz     short loc_180009BE1
0x180009bd2  mov     ebx, 80070005h
0x180009bd7  mov     edx, 17Ch
0x180009bdc  mov     r8d, ebx
0x180009bdf  jmp     short loc_180009BF8
0x180009be1  lea     rcx, [rbp+57h+var_80]
0x180009be5  call    ?GetUserSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSmsRpcUtils::GetUserSid(std::wstring &)
0x180009bea  mov     ebx, eax
0x180009bec  test    eax, eax
0x180009bee  jns     short loc_180009C10
0x180009bf0  mov     edx, 182h; unsigned int
0x180009bf5  mov     r8d, eax; int
0x180009bf8  lea     r9, aFailedSecurity; "Failed security check."
0x180009bff  lea     rcx, aRpcsmsrouterAc; "_RpcSmsRouter_AcknowledgeMessage"
0x180009c06  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180009c0b  jmp     loc_180009CF8
0x180009c10  lea     r8, [rbp+57h+var_90]
0x180009c14  mov     [rbp+57h+var_90], 0
0x180009c1b  lea     rdx, [rbp+57h+var_60]
0x180009c1f  xor     ecx, ecx; Src
0x180009c21  call    ?CalculateAppName@CSmsRpcUtils@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAH@Z; CSmsRpcUtils::CalculateAppName(ushort const *,std::wstring &,int &)
0x180009c26  mov     ebx, eax
0x180009c28  test    eax, eax
0x180009c2a  jns     short loc_180009C33
0x180009c2c  mov     edx, 188h
0x180009c31  jmp     short loc_180009BF5
0x180009c33  lea     rcx, [rbp+57h+var_88]; struct CSmsServiceManager **
0x180009c37  call    ?GetInstance@CSmsServiceManager@@SAJPEAPEAV1@@Z; CSmsServiceManager::GetInstance(CSmsServiceManager * *)
0x180009c3c  lea     rcx, aRpcsmsrouterAc; "_RpcSmsRouter_AcknowledgeMessage"
0x180009c43  mov     ebx, eax
0x180009c45  test    eax, eax
0x180009c47  jns     short loc_180009C5A
0x180009c49  lea     r9, aFailedToGetSer; "Failed to get service manager instance."
0x180009c50  mov     r8d, eax
0x180009c53  mov     edx, 18Eh
0x180009c58  jmp     short loc_180009C06
0x180009c5a  mov     [rsp+0D0h+var_A8], r13d
0x180009c5f  lea     r8, aAckRegidSMsgid; "Ack RegId: %S MsgId: %llu, Accepted: %l"...
0x180009c66  mov     r9, r15
0x180009c69  mov     [rsp+0D0h+var_B0], r12
0x180009c6e  mov     edx, 192h; unsigned int
0x180009c73  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180009c78  cmp     qword ptr [rbp+57h+var_70+8], 7
0x180009c7d  lea     rsi, [rbp+57h+var_80]
0x180009c81  mov     rdi, [rbp+57h+var_88]
0x180009c85  lea     r14, [rbp+57h+var_60]
0x180009c89  cmova   rsi, [rbp+57h+var_80]
0x180009c8e  mov     rdx, r15; unsigned __int16 *
0x180009c91  cmp     qword ptr [rbp+57h+var_50+8], 7
0x180009c96  mov     r9, rsi; unsigned __int16 *
0x180009c99  mov     [rsp+0D0h+var_A8], r13d; int
0x180009c9e  cmova   r14, [rbp+57h+var_60]
0x180009ca3  lea     rcx, [rdi+60h]; this
0x180009ca7  mov     r8, r14; unsigned __int16 *
0x180009caa  mov     [rsp+0D0h+var_B0], r12; unsigned __int64
0x180009caf  call    ?AcknowledgeMessage@CSmsInterceptor@@QEAAJPEBG00_KH@Z; CSmsInterceptor::AcknowledgeMessage(ushort const *,ushort const *,ushort const *,unsigned __int64,int)
0x180009cb4  mov     ebx, eax
0x180009cb6  test    eax, eax
0x180009cb8  jns     short loc_180009CE9
0x180009cba  mov     [rsp+0D0h+var_98], r12
0x180009cbf  lea     r9, aAcknowledgemes_0; "AcknowledgeMessage for RegId: %S, AppNa"...
0x180009cc6  mov     [rsp+0D0h+var_A0], rsi
0x180009ccb  lea     rcx, aCsmsserviceman_0; "CSmsServiceManager::AcknowledgeMessage"
0x180009cd2  mov     qword ptr [rsp+0D0h+var_A8], r14
0x180009cd7  mov     r8d, eax; int
0x180009cda  mov     edx, 144h; unsigned int
0x180009cdf  mov     [rsp+0D0h+var_B0], r15
0x180009ce4  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180009ce9  mov     rax, [rdi]
0x180009cec  mov     rcx, rdi
0x180009cef  mov     rax, [rax+10h]
0x180009cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cf8  lea     rcx, [rbp+57h+var_80]; void *
0x180009cfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009d01  lea     rcx, [rbp+57h+var_60]; void *
0x180009d05  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009d0a  mov     eax, ebx
0x180009d0c  mov     rcx, [rbp+57h+var_40]
0x180009d10  xor     rcx, rsp; StackCookie
0x180009d13  call    __security_check_cookie
0x180009d18  mov     rbx, [rsp+0D0h+arg_0]
0x180009d20  add     rsp, 0A0h
0x180009d27  pop     r15
0x180009d29  pop     r14
0x180009d2b  pop     r13
0x180009d2d  pop     r12
0x180009d2f  pop     rdi
0x180009d30  pop     rsi
0x180009d31  pop     rbp
0x180009d32  retn
```
