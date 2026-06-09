# _RpcSmsRouter_GetMessage

- ea: `0x180009d50`
- end: `0x180009f57`
- name: `_RpcSmsRouter_GetMessage`
- size: `519`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x180009d50`
- `0x1800152ac`
- `0x1800153cc`
- `0x18002643c`
- `0x180026f00`
- `0x1800270b0`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009ed6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009ed6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f1f`

## string_xrefs

- `0x180009dea`: `Failed security check.`
- `0x180009e31`: `Failed to get service manager instance.`

## pseudocode

```c
__int64 __fastcall RpcSmsRouter_GetMessage(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned __int64 *a3,
        _QWORD *a4,
        unsigned int *a5)
{
  int NextMessage; // edi
  unsigned int v9; // edx
  int v10; // r8d
  signed int UserSid; // eax
  int Instance; // eax
  const unsigned __int16 *v13; // r9
  const unsigned __int16 *v14; // r8
  struct CSmsServiceManager *v15; // rbx
  _WORD *v16; // rbx
  __int64 v17; // rcx
  _WORD *v18; // rax
  __int64 v19; // rdx
  _WORD *v20; // r9
  __int64 v21; // r8
  _WORD *v22; // rdx
  struct CSmsServiceManager *v24; // [rsp+48h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-31h] BYREF
  unsigned __int16 *v26[2]; // [rsp+58h] [rbp-29h] BYREF
  __m128i v27; // [rsp+68h] [rbp-19h]
  unsigned __int16 *v28[2]; // [rsp+78h] [rbp-9h] BYREF
  __m128i si128; // [rsp+88h] [rbp+7h]

  v24 = 0;
  *(_OWORD *)v28 = 0;
  LOWORD(v28[0]) = 0;
  *(_OWORD *)v26 = 0;
  LOWORD(v26[0]) = 0;
  hMem = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v27 = si128;
  if ( !(unsigned int)HasCapability(L"cellularMessaging") )
  {
    NextMessage = -2147024891;
    v9 = 326;
    v10 = -2147024891;
LABEL_6:
    LogSmsRouterError("_RpcSmsRouter_GetMessage", v9, v10, "Failed security check.");
    goto LABEL_26;
  }
  UserSid = CSmsRpcUtils::GetUserSid((__int64)v26);
  NextMessage = UserSid;
  if ( UserSid < 0 )
  {
    v9 = 332;
LABEL_5:
    v10 = UserSid;
    goto LABEL_6;
  }
  UserSid = CSmsRpcUtils::CalculateAppName(0);
  NextMessage = UserSid;
  if ( UserSid < 0 )
  {
    v9 = 338;
    goto LABEL_5;
  }
  Instance = CSmsServiceManager::GetInstance(&v24);
  NextMessage = Instance;
  if ( Instance >= 0 )
  {
    v13 = (const unsigned __int16 *)v26;
    if ( v27.m128i_i64[1] > 7uLL )
      v13 = v26[0];
    v14 = (const unsigned __int16 *)v28;
    v15 = v24;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = v28[0];
    NextMessage = CSmsServiceManager::GetNextMessage(v24, a2, v14, v13, a3, (unsigned __int16 **)&hMem, a5);
    (*(void (__fastcall **)(struct CSmsServiceManager *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( NextMessage >= 0 )
    {
      LogSmsRouterInfo("_RpcSmsRouter_GetMessage", 0x165u, "GetMessage RegId: %S MsgId: %llu", a2, *a3);
      v16 = hMem;
      v17 = -1;
      do
        ++v17;
      while ( *((_WORD *)hMem + v17) );
      v18 = malloc(2 * v17 + 2);
      v19 = 2147483646;
      *a4 = v18;
      v20 = v16;
      v21 = 0x7FFFFFFF;
      do
      {
        if ( !v19 )
          break;
        if ( !*v20 )
          break;
        *v18++ = *v20++;
        --v19;
        --v21;
      }
      while ( v21 );
      v22 = v18 - 1;
      if ( v21 )
        v22 = v18;
      *v22 = 0;
      LocalFree(v16);
    }
  }
  else
  {
    LogSmsRouterError("_RpcSmsRouter_GetMessage", 0x158u, Instance, "Failed to get service manager instance.");
  }
LABEL_26:
  std::wstring::~wstring((char **)v26);
  std::wstring::~wstring((char **)v28);
  return (unsigned int)NextMessage;
}

```

## disassembly

```asm
0x180009d50  push    rbp
0x180009d52  push    rbx
0x180009d53  push    rsi
0x180009d54  push    rdi
0x180009d55  push    r12
0x180009d57  push    r14
0x180009d59  push    r15
0x180009d5b  lea     rbp, [rsp-1Fh]
0x180009d60  sub     rsp, 0A0h
0x180009d67  mov     rax, cs:__security_cookie
0x180009d6e  xor     rax, rsp
0x180009d71  mov     [rbp+4Fh+var_38], rax
0x180009d75  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180009d7d  lea     rcx, SourceString; "cellularMessaging"
0x180009d84  mov     rbx, [rbp+4Fh+arg_20]
0x180009d88  xor     r12d, r12d
0x180009d8b  xorps   xmm0, xmm0
0x180009d8e  mov     [rbp+4Fh+var_88], r12
0x180009d92  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x180009d96  mov     word ptr [rbp+4Fh+var_58], r12w
0x180009d9b  mov     r15, r9
0x180009d9e  movups  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180009da2  mov     word ptr [rbp+4Fh+var_78], r12w
0x180009da7  mov     r14, r8
0x180009daa  mov     rsi, rdx
0x180009dad  mov     [rbp+4Fh+hMem], r12
0x180009db1  movdqu  [rbp+4Fh+var_48], xmm1
0x180009db6  movdqu  [rbp+4Fh+var_68], xmm1
0x180009dbb  call    ?HasCapability@@YAHPEBG@Z; HasCapability(ushort const *)
0x180009dc0  test    eax, eax
0x180009dc2  jnz     short loc_180009DD3
0x180009dc4  mov     edi, 80070005h
0x180009dc9  mov     edx, 146h
0x180009dce  mov     r8d, edi
0x180009dd1  jmp     short loc_180009DEA
0x180009dd3  lea     rcx, [rbp+4Fh+var_78]
0x180009dd7  call    ?GetUserSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSmsRpcUtils::GetUserSid(std::wstring &)
0x180009ddc  mov     edi, eax
0x180009dde  test    eax, eax
0x180009de0  jns     short loc_180009E02
0x180009de2  mov     edx, 14Ch; unsigned int
0x180009de7  mov     r8d, eax; int
0x180009dea  lea     r9, aFailedSecurity; "Failed security check."
0x180009df1  lea     rcx, aRpcsmsrouterGe_2; "_RpcSmsRouter_GetMessage"
0x180009df8  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180009dfd  jmp     loc_180009F25
0x180009e02  lea     r8, [rbp+4Fh+var_90]
0x180009e06  mov     [rbp+4Fh+var_90], r12d
0x180009e0a  lea     rdx, [rbp+4Fh+var_58]
0x180009e0e  xor     ecx, ecx; Src
0x180009e10  call    ?CalculateAppName@CSmsRpcUtils@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAH@Z; CSmsRpcUtils::CalculateAppName(ushort const *,std::wstring &,int &)
0x180009e15  mov     edi, eax
0x180009e17  test    eax, eax
0x180009e19  jns     short loc_180009E22
0x180009e1b  mov     edx, 152h
0x180009e20  jmp     short loc_180009DE7
0x180009e22  lea     rcx, [rbp+4Fh+var_88]; struct CSmsServiceManager **
0x180009e26  call    ?GetInstance@CSmsServiceManager@@SAJPEAPEAV1@@Z; CSmsServiceManager::GetInstance(CSmsServiceManager * *)
0x180009e2b  mov     edi, eax
0x180009e2d  test    eax, eax
0x180009e2f  jns     short loc_180009E42
0x180009e31  lea     r9, aFailedToGetSer; "Failed to get service manager instance."
0x180009e38  mov     r8d, eax
0x180009e3b  mov     edx, 158h
0x180009e40  jmp     short loc_180009DF1
0x180009e42  cmp     qword ptr [rbp+4Fh+var_68+8], 7
0x180009e47  lea     rax, [rbp+4Fh+hMem]
0x180009e4b  mov     [rsp+0D0h+var_A0], rbx; unsigned int *
0x180009e50  lea     r9, [rbp+4Fh+var_78]
0x180009e54  cmova   r9, [rbp+4Fh+var_78]; unsigned __int16 *
0x180009e59  lea     r8, [rbp+4Fh+var_58]
0x180009e5d  cmp     qword ptr [rbp+4Fh+var_48+8], 7
0x180009e62  mov     rdx, rsi; unsigned __int16 *
0x180009e65  mov     rbx, [rbp+4Fh+var_88]
0x180009e69  cmova   r8, [rbp+4Fh+var_58]; unsigned __int16 *
0x180009e6e  mov     rcx, rbx; this
0x180009e71  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x180009e76  mov     [rsp+0D0h+var_B0], r14; unsigned __int64 *
0x180009e7b  call    ?GetNextMessage@CSmsServiceManager@@QEAAJPEBG00PEA_KPEAPEAGPEAK@Z; CSmsServiceManager::GetNextMessage(ushort const *,ushort const *,ushort const *,unsigned __int64 *,ushort * *,ulong *)
0x180009e80  mov     edi, eax
0x180009e82  mov     rcx, rbx
0x180009e85  mov     rax, [rbx]
0x180009e88  mov     rax, [rax+10h]
0x180009e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e91  test    edi, edi
0x180009e93  js      loc_180009F25
0x180009e99  mov     rax, [r14]
0x180009e9c  lea     r8, aGetmessageRegi; "GetMessage RegId: %S MsgId: %llu"
0x180009ea3  mov     r9, rsi
0x180009ea6  mov     [rsp+0D0h+var_B0], rax
0x180009eab  mov     edx, 165h; unsigned int
0x180009eb0  lea     rcx, aRpcsmsrouterGe_2; "_RpcSmsRouter_GetMessage"
0x180009eb7  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180009ebc  mov     rbx, [rbp+4Fh+hMem]
0x180009ec0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009ec4  inc     rcx
0x180009ec7  cmp     [rbx+rcx*2], r12w
0x180009ecc  jnz     short loc_180009EC4
0x180009ece  lea     rcx, ds:2[rcx*2]; Size
0x180009ed6  call    cs:__imp_malloc
0x180009edc  mov     edx, 7FFFFFFEh
0x180009ee1  mov     [r15], rax
0x180009ee4  mov     r9, rbx
0x180009ee7  lea     r8d, [rdx+1]
0x180009eeb  test    rdx, rdx
0x180009eee  jz      short loc_180009F0D
0x180009ef0  movzx   ecx, word ptr [r9]
0x180009ef4  test    cx, cx
0x180009ef7  jz      short loc_180009F0D
0x180009ef9  mov     [rax], cx
0x180009efc  add     r9, 2
0x180009f00  add     rax, 2
0x180009f04  dec     rdx
0x180009f07  sub     r8, 1
0x180009f0b  jnz     short loc_180009EEB
0x180009f0d  test    r8, r8
0x180009f10  lea     rdx, [rax-2]
0x180009f14  mov     rcx, rbx; hMem
0x180009f17  cmovnz  rdx, rax
0x180009f1b  mov     [rdx], r12w
0x180009f1f  call    cs:__imp_LocalFree
0x180009f25  lea     rcx, [rbp+4Fh+var_78]; void *
0x180009f29  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009f2e  lea     rcx, [rbp+4Fh+var_58]; void *
0x180009f32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009f37  mov     eax, edi
0x180009f39  mov     rcx, [rbp+4Fh+var_38]
0x180009f3d  xor     rcx, rsp; StackCookie
0x180009f40  call    __security_check_cookie
0x180009f45  add     rsp, 0A0h
0x180009f4c  pop     r15
0x180009f4e  pop     r14
0x180009f50  pop     r12
0x180009f52  pop     rdi
0x180009f53  pop     rsi
0x180009f54  pop     rbx
0x180009f55  pop     rbp
0x180009f56  retn
```
