# _RpcSmsRouter_GetSmscAddress

- ea: `0x18000a400`
- end: `0x18000a554`
- name: `_RpcSmsRouter_GetSmscAddress`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000a400`
- `0x1800152ac`
- `0x1800157e4`
- `0x1800270b0`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a4d4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a4d4`

## string_xrefs

- `0x18000a45e`: `Failed security check.`
- `0x18000a47e`: `Failed to get service manager instance.`

## pseudocode

```c
__int64 __fastcall RpcSmsRouter_GetSmscAddress(__int64 a1, const OLECHAR *a2, _QWORD *a3)
{
  int SmscAddress; // edi
  int Instance; // eax
  const OLECHAR *v7; // rdx
  struct CSmsServiceManager *v8; // rbx
  size_t v9; // rbx
  _WORD *v10; // rax
  bool v11; // cc
  __int128 *v12; // rcx
  size_t v13; // rbx
  __int64 v14; // rdx
  _WORD *v15; // rcx
  struct CSmsServiceManager *v17; // [rsp+20h] [rbp-30h] BYREF
  __int128 v18; // [rsp+28h] [rbp-28h] BYREF
  __m128i si128; // [rsp+38h] [rbp-18h]

  v18 = 0;
  LOWORD(v18) = 0;
  v17 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (unsigned int)HasCapability(L"cellularMessaging") )
  {
    Instance = CSmsServiceManager::GetInstance(&v17);
    SmscAddress = Instance;
    if ( Instance >= 0 )
    {
      v7 = a2;
      v8 = v17;
      SmscAddress = CSmsServiceManager::GetSmscAddress((__int64)v17, v7, (__int64)&v18);
      (*(void (__fastcall **)(struct CSmsServiceManager *))(*(_QWORD *)v8 + 16LL))(v8);
      if ( SmscAddress >= 0 )
      {
        v9 = (unsigned int)(2 * si128.m128i_i32[0] + 2);
        v10 = malloc(v9);
        v11 = si128.m128i_i64[1] <= 7uLL;
        v12 = &v18;
        *a3 = v10;
        if ( !v11 )
          v12 = (__int128 *)v18;
        v13 = v9 >> 1;
        if ( v13 )
        {
          v14 = 2147483646;
          do
          {
            if ( !v14 )
              break;
            if ( !*(_WORD *)v12 )
              break;
            *v10 = *(_WORD *)v12;
            v12 = (__int128 *)((char *)v12 + 2);
            ++v10;
            --v14;
            --v13;
          }
          while ( v13 );
          v15 = v10 - 1;
          if ( v13 )
            v15 = v10;
          *v15 = 0;
        }
      }
    }
    else
    {
      LogSmsRouterError(
        "_RpcSmsRouter_GetSmscAddress",
        0x22Fu,
        Instance,
        "Failed to get service manager instance.",
        v17);
    }
  }
  else
  {
    SmscAddress = -2147024891;
    LogSmsRouterError("_RpcSmsRouter_GetSmscAddress", 0x229u, -2147024891, "Failed security check.", v17);
  }
  std::wstring::~wstring((char **)&v18);
  return (unsigned int)SmscAddress;
}

```

## disassembly

```asm
0x18000a400  mov     [rsp-18h+arg_0], rbx
0x18000a405  mov     [rsp-18h+arg_18], rsi
0x18000a40a  push    rbp
0x18000a40b  push    rdi
0x18000a40c  push    r14
0x18000a40e  mov     rbp, rsp
0x18000a411  sub     rsp, 50h
0x18000a415  mov     rax, cs:__security_cookie
0x18000a41c  xor     rax, rsp
0x18000a41f  mov     [rbp+var_8], rax
0x18000a423  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000a42b  lea     rcx, SourceString; "cellularMessaging"
0x18000a432  xorps   xmm0, xmm0
0x18000a435  xor     r14d, r14d
0x18000a438  movups  [rbp+var_28], xmm0
0x18000a43c  mov     word ptr [rbp+var_28], r14w
0x18000a441  mov     rsi, r8
0x18000a444  mov     rbx, rdx
0x18000a447  mov     [rbp+var_30], r14
0x18000a44b  movdqu  [rbp+var_18], xmm1
0x18000a450  call    ?HasCapability@@YAHPEBG@Z; HasCapability(ushort const *)
0x18000a455  test    eax, eax
0x18000a457  jnz     short loc_18000A46F
0x18000a459  mov     edi, 80070005h
0x18000a45e  lea     r9, aFailedSecurity; "Failed security check."
0x18000a465  mov     r8d, edi
0x18000a468  mov     edx, 229h
0x18000a46d  jmp     short loc_18000A48D
0x18000a46f  lea     rcx, [rbp+var_30]; struct CSmsServiceManager **
0x18000a473  call    ?GetInstance@CSmsServiceManager@@SAJPEAPEAV1@@Z; CSmsServiceManager::GetInstance(CSmsServiceManager * *)
0x18000a478  mov     edi, eax
0x18000a47a  test    eax, eax
0x18000a47c  jns     short loc_18000A49E
0x18000a47e  lea     r9, aFailedToGetSer; "Failed to get service manager instance."
0x18000a485  mov     r8d, eax; int
0x18000a488  mov     edx, 22Fh; unsigned int
0x18000a48d  lea     rcx, aRpcsmsrouterGe; "_RpcSmsRouter_GetSmscAddress"
0x18000a494  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000a499  jmp     loc_18000A528
0x18000a49e  mov     rdx, rbx
0x18000a4a1  lea     r8, [rbp+var_28]
0x18000a4a5  mov     rbx, [rbp+var_30]
0x18000a4a9  mov     rcx, rbx
0x18000a4ac  call    ?GetSmscAddress@CSmsServiceManager@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSmsServiceManager::GetSmscAddress(ushort const *,std::wstring &)
0x18000a4b1  mov     edi, eax
0x18000a4b3  mov     rcx, rbx
0x18000a4b6  mov     rax, [rbx]
0x18000a4b9  mov     rax, [rax+10h]
0x18000a4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c2  test    edi, edi
0x18000a4c4  js      short loc_18000A528
0x18000a4c6  mov     eax, dword ptr [rbp+var_18]
0x18000a4c9  lea     eax, ds:2[rax*2]
0x18000a4d0  mov     ecx, eax; Size
0x18000a4d2  mov     ebx, eax
0x18000a4d4  call    cs:__imp_malloc
0x18000a4da  cmp     qword ptr [rbp+var_18+8], 7
0x18000a4df  lea     rcx, [rbp+var_28]
0x18000a4e3  mov     [rsi], rax
0x18000a4e6  cmova   rcx, qword ptr [rbp+var_28]
0x18000a4eb  shr     rbx, 1
0x18000a4ee  jz      short loc_18000A528
0x18000a4f0  mov     edx, 7FFFFFFEh
0x18000a4f5  test    rdx, rdx
0x18000a4f8  jz      short loc_18000A519
0x18000a4fa  movzx   r8d, word ptr [rcx]
0x18000a4fe  test    r8w, r8w
0x18000a502  jz      short loc_18000A519
0x18000a504  mov     [rax], r8w
0x18000a508  add     rcx, 2
0x18000a50c  add     rax, 2
0x18000a510  dec     rdx
0x18000a513  sub     rbx, 1
0x18000a517  jnz     short loc_18000A4F5
0x18000a519  test    rbx, rbx
0x18000a51c  lea     rcx, [rax-2]
0x18000a520  cmovnz  rcx, rax
0x18000a524  mov     [rcx], r14w
0x18000a528  lea     rcx, [rbp+var_28]; void *
0x18000a52c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a531  mov     eax, edi
0x18000a533  mov     rcx, [rbp+var_8]
0x18000a537  xor     rcx, rsp; StackCookie
0x18000a53a  call    __security_check_cookie
0x18000a53f  lea     r11, [rsp+50h+var_s0]
0x18000a544  mov     rbx, [r11+20h]
0x18000a548  mov     rsi, [r11+38h]
0x18000a54c  mov     rsp, r11
0x18000a54f  pop     r14
0x18000a551  pop     rdi
0x18000a552  pop     rbp
0x18000a553  retn
```
