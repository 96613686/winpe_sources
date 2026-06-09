# PhoneSvcImpl_PhoneRpcDial

- ea: `0x180088e90`
- end: `0x180089339`
- name: `PhoneSvcImpl_PhoneRpcDial`
- size: `1193`
- prototype: `__int64 __fastcall(__int64, _BYTE *, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180005660`
- `0x180006e94`
- `0x180007750`
- `0x1800091a8`
- `0x18004c2ac`
- `0x180086b10`
- `0x180088e90`
- `0x18008caa8`
- `0x18008cab4`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089156`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089156`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180088f33`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180088f33`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008919a`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008919a`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180088f07`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180088f07`

## pseudocode

```c
__int64 __fastcall PhoneSvcImpl_PhoneRpcDial(__int64 a1, _BYTE *a2, __int64 a3)
{
  DialParameters *v5; // rbx
  _WORD *v6; // rcx
  void **v7; // rax
  int RpcClientThreadToken; // eax
  __int64 v9; // r8
  int ApplicationUserModelIdFromToken; // eax
  __int64 v11; // r8
  DialParameters *v12; // rax
  BackTraceCollection *v13; // rcx
  struct ATL::CAtlModule *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r9
  _DWORD *v27; // r14
  int v28; // eax
  BackTraceCollection *v29; // rcx
  unsigned int v30; // edi
  __int64 v31; // r8
  void (*v32)(void); // rax
  int v34; // eax
  BackTraceCollection *v35; // rcx
  __int64 v36; // r8
  int v37; // eax
  BackTraceCollection *v38; // rcx
  unsigned int v39; // esi
  __int64 v40; // r8
  _BYTE v41[80]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v42; // [rsp+90h] [rbp-70h]
  struct ISecurityToken *v43; // [rsp+A0h] [rbp-60h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE token[2]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = 0;
  memset_0(applicationUserModelId, 0, 0x108u);
  v6 = (_WORD *)*((_QWORD *)a2 + 10);
  if ( v6 && *v6 )
    goto LABEL_34;
  token[0] = 0;
  v7 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(token);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v7);
  if ( RpcClientThreadToken < 0 )
    Log_HREvent_31((unsigned int)RpcClientThreadToken, 0, v9, 331);
  applicationUserModelIdLength = 132;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token[0],
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken )
  {
    if ( ApplicationUserModelIdFromToken > 0 )
      ApplicationUserModelIdFromToken = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
    v26 = 342;
    v25 = (unsigned int)ApplicationUserModelIdFromToken;
  }
  else
  {
    v12 = (DialParameters *)operator new(0xD8u);
    v5 = v12;
    if ( v12 )
    {
      memset_0(v12, 0, 0xD8u);
      v14 = ATL::_pAtlModule;
      *((_QWORD *)v5 + 4) = (char *)v5 + 48;
      *((_QWORD *)v5 + 5) = (char *)v5 + 48;
      *((_QWORD *)v5 + 8) = (char *)v5 + 80;
      *((_QWORD *)v5 + 9) = (char *)v5 + 80;
      *((_QWORD *)v5 + 14) = (char *)v5 + 128;
      *((_QWORD *)v5 + 15) = (char *)v5 + 128;
      *((GUID *)v5 + 9) = GUID_00000000_0000_0000_0000_000000000000;
      *((_QWORD *)v5 + 22) = (char *)v5 + 192;
      *((_QWORD *)v5 + 23) = (char *)v5 + 192;
      *((_QWORD *)v5 + 12) = g_ZeroOlItemId;
      *((_DWORD *)v5 + 26) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<DialParameters>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v14 + 8LL))(v14);
      (*(void (__fastcall **)(DialParameters *))(*(_QWORD *)v5 + 8LL))(v5);
      (*(void (__fastcall **)(DialParameters *))(*(_QWORD *)v5 + 8LL))(v5);
      (*(void (__fastcall **)(DialParameters *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    else
    {
      BackTraceCollection::Capture(v13, -2147024882);
      Log_HREvent_32(2147942414LL);
      Log_HREvent_31(2147942414LL, 0, v15, 337);
      v5 = 0;
    }
    *((_DWORD *)v5 + 40) = *((_DWORD *)a2 + 16);
    *((_DWORD *)v5 + 6) = *(_DWORD *)a2;
    *((_DWORD *)v5 + 27) = *((_DWORD *)a2 + 8);
    *((_DWORD *)v5 + 41) = *((_DWORD *)a2 + 17);
    *((_DWORD *)v5 + 7) = *((_DWORD *)a2 + 1);
    *((_OWORD *)v5 + 9) = *((_OWORD *)a2 + 3);
    *((_DWORD *)v5 + 42) = *((_DWORD *)a2 + 18);
    v16 = *((_QWORD *)a2 + 3);
    if ( v16 )
    {
      *((_QWORD *)v5 + 12) = *(_QWORD *)v16;
      *((_DWORD *)v5 + 26) = *(_DWORD *)(v16 + 8);
    }
    v17 = *((_QWORD *)a2 + 5);
    v18 = -1;
    if ( !v17 )
      goto LABEL_63;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(v17 + 2 * v19) );
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)v5 + 112) )
    {
LABEL_63:
      v20 = *((_QWORD *)a2 + 2);
      if ( !v20 )
        goto LABEL_64;
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(v20 + 2 * v21) );
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)v5 + 64) )
      {
LABEL_64:
        v22 = *((_QWORD *)a2 + 1);
        if ( !v22 )
          goto LABEL_65;
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(v22 + 2 * v23) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)v5 + 32) )
        {
LABEL_65:
          v24 = *((_QWORD *)a2 + 10);
          if ( !v24 )
            goto LABEL_27;
          do
            ++v18;
          while ( *(_WORD *)(v24 + 2 * v18) );
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)v5 + 176) )
          {
LABEL_27:
            *((_DWORD *)v5 + 52) = 1;
            goto LABEL_32;
          }
        }
      }
    }
    v25 = 2147500037LL;
    v26 = 338;
  }
  Log_HREvent_31(v25, 0, v11, v26);
LABEL_32:
  if ( token[0] )
    CloseHandle(token[0]);
LABEL_34:
  memset_0(v41, 0, 0x58u);
  v27 = (_DWORD *)((char *)v5 + 208);
  if ( v5 && *v27 )
  {
    DialParameters::PopulateDialParams(v5, (struct PH_DIAL_PARAMETERS *)v41);
    v42 = applicationUserModelId;
  }
  v43 = 0;
  v28 = CreatePerUserSecurityTokenForRpcClient(&v43);
  v30 = v28;
  if ( v28 < 0 )
  {
    BackTraceCollection::Capture(v29, v28);
    Log_HREvent_31(v30, 1, v31, 354);
    if ( !v43 )
    {
LABEL_41:
      if ( v5 )
        (*(void (__fastcall **)(DialParameters *))(*(_QWORD *)v5 + 16LL))(v5);
      return v30;
    }
    v32 = *(void (**)(void))(*(_QWORD *)v43 + 16LL);
LABEL_40:
    v32();
    goto LABEL_41;
  }
  v34 = WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(&g_phoneRpcServer);
  v30 = v34;
  if ( v34 < 0 )
  {
    BackTraceCollection::Capture(v35, v34);
    Log_HREvent_31(v30, 1, v36, 357);
    if ( !v43 )
      goto LABEL_41;
    v32 = *(void (**)(void))(*(_QWORD *)v43 + 16LL);
    goto LABEL_40;
  }
  if ( v5 && *v27 )
    a2 = v41;
  v37 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, struct ISecurityToken *))(MEMORY[0] + 72LL))(
          0,
          a2,
          a3,
          v43);
  v39 = v37;
  if ( v37 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
    if ( v43 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v5 )
      (*(void (__fastcall **)(DialParameters *))(*(_QWORD *)v5 + 16LL))(v5);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v38, v37);
    Log_HREvent_31(v39, 1, v40, 360);
    (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
    if ( v43 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v5 )
      (*(void (__fastcall **)(DialParameters *))(*(_QWORD *)v5 + 16LL))(v5);
    return v39;
  }
}

```

## disassembly

```asm
0x180088e90  mov     [rsp-8+arg_0], rbx
0x180088e95  mov     [rsp-8+arg_18], rsi
0x180088e9a  push    rbp
0x180088e9b  push    rdi
0x180088e9c  push    r12
0x180088e9e  push    r14
0x180088ea0  push    r15
0x180088ea2  lea     rbp, [rsp-0E0h]
0x180088eaa  sub     rsp, 1E0h
0x180088eb1  mov     rax, cs:__security_cookie
0x180088eb8  xor     rax, rsp
0x180088ebb  mov     [rbp+100h+var_30], rax
0x180088ec2  mov     r15, r8
0x180088ec5  lea     rcx, [rbp+100h+applicationUserModelId]; void *
0x180088ec9  mov     rsi, rdx
0x180088ecc  xor     r12d, r12d
0x180088ecf  xor     edx, edx; Val
0x180088ed1  mov     r8d, 108h; Size
0x180088ed7  mov     ebx, r12d
0x180088eda  call    memset_0
0x180088edf  mov     rcx, [rsi+50h]
0x180088ee3  test    rcx, rcx
0x180088ee6  jz      short loc_180088EF2
0x180088ee8  cmp     r12w, [rcx]
0x180088eec  jnz     loc_18008915C
0x180088ef2  lea     rcx, [rbp+100h+token]
0x180088ef6  mov     [rbp+100h+token], r12
0x180088efa  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x180088eff  mov     rdx, rax
0x180088f02  mov     ecx, 8
0x180088f07  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x180088f0d  test    eax, eax
0x180088f0f  jns     short loc_180088F20
0x180088f11  xor     edx, edx
0x180088f13  mov     r9d, 14Bh
0x180088f19  mov     ecx, eax
0x180088f1b  call    Log_HREvent_31
0x180088f20  mov     rcx, [rbp+100h+token]; token
0x180088f24  lea     r8, [rbp+100h+applicationUserModelId]; applicationUserModelId
0x180088f28  lea     rdx, [rbp+100h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180088f2c  mov     [rbp+100h+applicationUserModelIdLength], 84h
0x180088f33  call    cs:__imp_GetApplicationUserModelIdFromToken
0x180088f39  test    eax, eax
0x180088f3b  jnz     loc_180089134
0x180088f41  mov     edi, 0D8h
0x180088f46  mov     ecx, edi; Size
0x180088f48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180088f4d  mov     rbx, rax
0x180088f50  test    rax, rax
0x180088f53  jz      loc_180089013
0x180088f59  mov     r8d, edi; Size
0x180088f5c  xor     edx, edx; Val
0x180088f5e  mov     rcx, rax; void *
0x180088f61  call    memset_0
0x180088f66  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180088f6d  lea     rax, [rbx+30h]
0x180088f71  mov     [rbx+20h], rax
0x180088f75  mov     [rbx+28h], rax
0x180088f79  lea     rax, [rbx+50h]
0x180088f7d  mov     [rbx+40h], rax
0x180088f81  mov     [rbx+48h], rax
0x180088f85  lea     rax, [rbx+80h]
0x180088f8c  mov     [rbx+70h], rax
0x180088f90  mov     [rbx+78h], rax
0x180088f94  lea     rax, [rbx+0C0h]
0x180088f9b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180088fa2  movdqu  xmmword ptr [rbx+90h], xmm0
0x180088faa  mov     [rbx+0B0h], rax
0x180088fb1  mov     [rbx+0B8h], rax
0x180088fb8  movsd   xmm0, cs:?g_ZeroOlItemId@@3UOLITEMID@@B; OLITEMID const g_ZeroOlItemId
0x180088fc0  movsd   qword ptr [rbx+60h], xmm0
0x180088fc5  mov     eax, cs:dword_18009B148
0x180088fcb  mov     [rbx+68h], eax
0x180088fce  lea     rax, ??_7?$CComObject@VDialParameters@@@ATL@@6B@; const ATL::CComObject<DialParameters>::`vftable'
0x180088fd5  mov     [rbx], rax
0x180088fd8  mov     rax, [rcx]
0x180088fdb  mov     rax, [rax+8]
0x180088fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fe4  mov     rax, [rbx]
0x180088fe7  mov     rcx, rbx
0x180088fea  mov     rax, [rax+8]
0x180088fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ff3  mov     rax, [rbx]
0x180088ff6  mov     rcx, rbx
0x180088ff9  mov     rax, [rax+8]
0x180088ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089002  mov     rax, [rbx]
0x180089005  mov     rcx, rbx
0x180089008  mov     rax, [rax+10h]
0x18008900c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089011  jmp     short loc_180089038
0x180089013  mov     ebx, 8007000Eh
0x180089018  mov     edx, ebx; int
0x18008901a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008901f  mov     ecx, ebx
0x180089021  call    Log_HREvent_32
0x180089026  xor     edx, edx
0x180089028  mov     r9d, 151h
0x18008902e  mov     ecx, ebx
0x180089030  call    Log_HREvent_31
0x180089035  mov     rbx, r12
0x180089038  mov     eax, [rsi+40h]
0x18008903b  mov     [rbx+0A0h], eax
0x180089041  mov     eax, [rsi]
0x180089043  mov     [rbx+18h], eax
0x180089046  mov     eax, [rsi+20h]
0x180089049  mov     [rbx+6Ch], eax
0x18008904c  mov     eax, [rsi+44h]
0x18008904f  mov     [rbx+0A4h], eax
0x180089055  mov     eax, [rsi+4]
0x180089058  mov     [rbx+1Ch], eax
0x18008905b  movups  xmm0, xmmword ptr [rsi+30h]
0x18008905f  movdqu  xmmword ptr [rbx+90h], xmm0
0x180089067  mov     eax, [rsi+48h]
0x18008906a  mov     [rbx+0A8h], eax
0x180089070  mov     rax, [rsi+18h]
0x180089074  test    rax, rax
0x180089077  jz      short loc_180089088
0x180089079  movsd   xmm0, qword ptr [rax]
0x18008907d  movsd   qword ptr [rbx+60h], xmm0
0x180089082  mov     eax, [rax+8]
0x180089085  mov     [rbx+68h], eax
0x180089088  mov     rdx, [rsi+28h]
0x18008908c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180089090  test    rdx, rdx
0x180089093  jz      short loc_1800890AF
0x180089095  mov     r8, rdi
0x180089098  inc     r8
0x18008909b  cmp     [rdx+r8*2], r12w
0x1800890a0  jnz     short loc_180089098
0x1800890a2  lea     rcx, [rbx+70h]
0x1800890a6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800890ab  test    al, al
0x1800890ad  jz      short loc_18008911B
0x1800890af  mov     rdx, [rsi+10h]
0x1800890b3  test    rdx, rdx
0x1800890b6  jz      short loc_1800890D2
0x1800890b8  mov     r8, rdi
0x1800890bb  inc     r8
0x1800890be  cmp     [rdx+r8*2], r12w
0x1800890c3  jnz     short loc_1800890BB
0x1800890c5  lea     rcx, [rbx+40h]
0x1800890c9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800890ce  test    al, al
0x1800890d0  jz      short loc_18008911B
0x1800890d2  mov     rdx, [rsi+8]
0x1800890d6  test    rdx, rdx
0x1800890d9  jz      short loc_1800890F5
0x1800890db  mov     r8, rdi
0x1800890de  inc     r8
0x1800890e1  cmp     [rdx+r8*2], r12w
0x1800890e6  jnz     short loc_1800890DE
0x1800890e8  lea     rcx, [rbx+20h]
0x1800890ec  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800890f1  test    al, al
0x1800890f3  jz      short loc_18008911B
0x1800890f5  mov     rdx, [rsi+50h]
0x1800890f9  test    rdx, rdx
0x1800890fc  jz      short loc_180089128
0x1800890fe  inc     rdi
0x180089101  cmp     [rdx+rdi*2], r12w
0x180089106  jnz     short loc_1800890FE
0x180089108  lea     rcx, [rbx+0B0h]
0x18008910f  mov     r8, rdi
0x180089112  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180089117  test    al, al
0x180089119  jnz     short loc_180089128
0x18008911b  mov     ecx, 80004005h
0x180089120  mov     r9d, 152h
0x180089126  jmp     short loc_180089146
0x180089128  mov     dword ptr [rbx+0D0h], 1
0x180089132  jmp     short loc_18008914D
0x180089134  jle     short loc_18008913E
0x180089136  movzx   eax, ax
0x180089139  or      eax, 80070000h
0x18008913e  mov     r9d, 156h
0x180089144  mov     ecx, eax
0x180089146  xor     edx, edx
0x180089148  call    Log_HREvent_31
0x18008914d  mov     rcx, [rbp+100h+token]; hObject
0x180089151  test    rcx, rcx
0x180089154  jz      short loc_18008915C
0x180089156  call    cs:__imp_CloseHandle
0x18008915c  xor     edx, edx; Val
0x18008915e  lea     rcx, [rsp+200h+var_1C0]; void *
0x180089163  lea     r8d, [rdx+58h]; Size
0x180089167  call    memset_0
0x18008916c  lea     r14, [rbx+0D0h]
0x180089173  test    rbx, rbx
0x180089176  jz      short loc_180089192
0x180089178  cmp     [r14], r12d
0x18008917b  jz      short loc_180089192
0x18008917d  lea     rdx, [rsp+200h+var_1C0]; struct PH_DIAL_PARAMETERS *
0x180089182  mov     rcx, rbx; this
0x180089185  call    ?PopulateDialParams@DialParameters@@QEBAXPEAUPH_DIAL_PARAMETERS@@@Z; DialParameters::PopulateDialParams(PH_DIAL_PARAMETERS *)
0x18008918a  lea     rax, [rbp+100h+applicationUserModelId]
0x18008918e  mov     [rbp+100h+var_170], rax
0x180089192  lea     rcx, [rbp+100h+var_160]
0x180089196  mov     [rbp+100h+var_160], r12
0x18008919a  call    cs:__imp_?CreatePerUserSecurityTokenForRpcClient@@YAJPEAPEAUISecurityToken@@@Z; CreatePerUserSecurityTokenForRpcClient(ISecurityToken * *)
0x1800891a0  mov     edi, eax
0x1800891a2  test    eax, eax
0x1800891a4  jns     short loc_1800891EF
0x1800891a6  mov     edx, eax; int
0x1800891a8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800891ad  mov     edx, 1
0x1800891b2  mov     r9d, 162h
0x1800891b8  mov     ecx, edi
0x1800891ba  call    Log_HREvent_31
0x1800891bf  mov     rcx, [rbp+100h+var_160]
0x1800891c3  test    rcx, rcx
0x1800891c6  jz      short loc_1800891D4
0x1800891c8  mov     rdx, [rcx]
0x1800891cb  mov     rax, [rdx+10h]
0x1800891cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800891d4  test    rbx, rbx
0x1800891d7  jz      short loc_1800891E8
0x1800891d9  mov     rax, [rbx]
0x1800891dc  mov     rcx, rbx
0x1800891df  mov     rax, [rax+10h]
0x1800891e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800891e8  mov     eax, edi
0x1800891ea  jmp     loc_18008930E
0x1800891ef  lea     rdx, [rsp+200h+var_1D0]
0x1800891f4  mov     [rsp+200h+var_1D0], r12
0x1800891f9  lea     rcx, ?g_phoneRpcServer@@3VSecurePhoneRpcServer@@A; lpCriticalSection
0x180089200  call    ?Get@?$WrappedComPtrBase@UIPhoneController@@VDoesNotSupportShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneController@@@Z; WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(IPhoneController * *)
0x180089205  mov     edi, eax
0x180089207  test    eax, eax
0x180089209  jns     short loc_18008924C
0x18008920b  mov     edx, eax; int
0x18008920d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180089212  mov     edx, 1
0x180089217  mov     r9d, 165h
0x18008921d  mov     ecx, edi
0x18008921f  call    Log_HREvent_31
0x180089224  mov     rcx, [rsp+200h+var_1D0]
0x180089229  test    rcx, rcx
0x18008922c  jz      short loc_18008923A
0x18008922e  mov     rdx, [rcx]
0x180089231  mov     rax, [rdx+10h]
0x180089235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008923a  mov     rcx, [rbp+100h+var_160]
0x18008923e  test    rcx, rcx
0x180089241  jz      short loc_1800891D4
0x180089243  mov     rax, [rcx]
0x180089246  mov     rax, [rax+10h]
0x18008924a  jmp     short loc_1800891CF
0x18008924c  mov     rdi, [rsp+200h+var_1D0]
0x180089251  mov     rax, [rdi]
0x180089254  test    rbx, rbx
0x180089257  jz      short loc_180089263
0x180089259  cmp     [r14], r12d
0x18008925c  jz      short loc_180089263
0x18008925e  lea     rsi, [rsp+200h+var_1C0]
0x180089263  mov     r9, [rbp+100h+var_160]
0x180089267  mov     r8, r15
0x18008926a  mov     rax, [rax+48h]
0x18008926e  mov     rdx, rsi
0x180089271  mov     rcx, rdi
0x180089274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089279  mov     esi, eax
0x18008927b  test    eax, eax
0x18008927d  jns     short loc_1800892D4
0x18008927f  mov     edx, eax; int
0x180089281  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180089286  mov     edx, 1
0x18008928b  mov     r9d, 168h
0x180089291  mov     ecx, esi
0x180089293  call    Log_HREvent_31
0x180089298  mov     rcx, [rdi]
0x18008929b  mov     rax, [rcx+10h]
0x18008929f  mov     rcx, rdi
0x1800892a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892a7  mov     rcx, [rbp+100h+var_160]
0x1800892ab  test    rcx, rcx
0x1800892ae  jz      short loc_1800892BC
0x1800892b0  mov     rax, [rcx]
0x1800892b3  mov     rax, [rax+10h]
0x1800892b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892bc  test    rbx, rbx
0x1800892bf  jz      short loc_1800892D0
0x1800892c1  mov     rax, [rbx]
0x1800892c4  mov     rcx, rbx
0x1800892c7  mov     rax, [rax+10h]
0x1800892cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892d0  mov     eax, esi
0x1800892d2  jmp     short loc_18008930E
0x1800892d4  mov     rax, [rdi]
0x1800892d7  mov     rcx, rdi
0x1800892da  mov     rax, [rax+10h]
0x1800892de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892e3  mov     rcx, [rbp+100h+var_160]
0x1800892e7  test    rcx, rcx
0x1800892ea  jz      short loc_1800892F8
0x1800892ec  mov     rax, [rcx]
0x1800892ef  mov     rax, [rax+10h]
0x1800892f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892f8  test    rbx, rbx
0x1800892fb  jz      short loc_18008930C
  ... truncated ...
```
