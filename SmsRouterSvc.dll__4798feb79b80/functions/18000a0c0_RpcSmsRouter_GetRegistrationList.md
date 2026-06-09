# _RpcSmsRouter_GetRegistrationList

- ea: `0x18000a0c0`
- end: `0x18000a340`
- name: `_RpcSmsRouter_GetRegistrationList`
- size: `640`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x180006a5c`
- `0x18000a0c0`
- `0x18000fa18`
- `0x1800152ac`
- `0x18002643c`
- `0x180026f00`
- `0x1800270b0`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a20d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a268`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a20d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a268`

## string_xrefs

- `0x18000a15e`: `Failed security check.`
- `0x18000a185`: `Failed to get service manager instance.`

## pseudocode

```c
__int64 __fastcall RpcSmsRouter_GetRegistrationList(__int64 a1, void *a2, _QWORD *a3, _DWORD *a4)
{
  int RegistrationList; // edi
  unsigned int v8; // edx
  int v9; // r8d
  signed int UserSid; // eax
  int Instance; // eax
  __int128 *v12; // r8
  struct CSmsServiceManager *v13; // rbx
  __int128 *v14; // rdx
  void *v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // esi
  __int64 v18; // r8
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  __int64 v21; // rdi
  size_t v22; // rdi
  unsigned __int64 v23; // rdi
  _WORD *v24; // rdx
  __int64 v25; // rax
  _WORD *v26; // rcx
  int v28; // [rsp+20h] [rbp-49h]
  __int128 v29; // [rsp+28h] [rbp-41h] BYREF
  __int64 v30; // [rsp+38h] [rbp-31h]
  struct CSmsServiceManager *v31; // [rsp+40h] [rbp-29h] BYREF
  __int128 v32; // [rsp+48h] [rbp-21h] BYREF
  __m128i v33; // [rsp+58h] [rbp-11h]
  __int128 v34; // [rsp+68h] [rbp-1h] BYREF
  __m128i si128; // [rsp+78h] [rbp+Fh]

  v34 = 0;
  LOWORD(v34) = 0;
  v32 = 0;
  LOWORD(v32) = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v33 = si128;
  if ( !(unsigned int)HasCapability(L"cellularMessaging") )
  {
    RegistrationList = -2147024891;
    v8 = 29;
    v9 = -2147024891;
LABEL_6:
    LogSmsRouterError("_RpcSmsRouter_GetRegistrationList", v8, v9, "Failed security check.", v28);
    goto LABEL_37;
  }
  UserSid = CSmsRpcUtils::GetUserSid((__int64)&v32);
  RegistrationList = UserSid;
  if ( UserSid < 0 )
  {
    v8 = 35;
LABEL_5:
    v9 = UserSid;
    goto LABEL_6;
  }
  Instance = CSmsServiceManager::GetInstance(&v31);
  RegistrationList = Instance;
  if ( Instance >= 0 )
  {
    v28 = 0;
    UserSid = CSmsRpcUtils::CalculateAppName(a2);
    RegistrationList = UserSid;
    if ( UserSid < 0 )
    {
      v8 = 47;
      goto LABEL_5;
    }
    v12 = &v32;
    v13 = v31;
    v14 = &v34;
    if ( v33.m128i_i64[1] > 7uLL )
      v12 = (__int128 *)v32;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = (__int128 *)v34;
    RegistrationList = CSmsInterceptor::GetRegistrationList((char *)v31 + 96, v14, v12, &v29, 0);
    (*(void (__fastcall **)(struct CSmsServiceManager *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( RegistrationList >= 0 )
    {
      v15 = malloc(8 * ((__int64)(*((_QWORD *)&v29 + 1) - v29) >> 5));
      v16 = *((_QWORD *)&v29 + 1);
      v17 = 0;
      v18 = v29;
      *a3 = v15;
      if ( (v16 - v18) >> 5 )
      {
        do
        {
          v19 = (_QWORD *)(v18 + 32LL * v17);
          if ( v19[3] <= 7u )
            v20 = (_QWORD *)(v18 + 32LL * v17);
          else
            v20 = (_QWORD *)*v19;
          v21 = -1;
          do
            ++v21;
          while ( *((_WORD *)v20 + v21) );
          v22 = 2 * v21 + 2;
          *(_QWORD *)(*a3 + 8LL * v17) = malloc(v22);
          if ( v19[3] > 7u )
            v19 = (_QWORD *)*v19;
          v23 = v22 >> 1;
          if ( v23 )
          {
            v24 = *(_WORD **)(*a3 + 8LL * v17);
            if ( v23 <= 0x7FFFFFFF )
            {
              v25 = 2147483646;
              do
              {
                if ( !v25 )
                  break;
                if ( !*(_WORD *)v19 )
                  break;
                *v24 = *(_WORD *)v19;
                v19 = (_QWORD *)((char *)v19 + 2);
                ++v24;
                --v25;
                --v23;
              }
              while ( v23 );
              v26 = v24 - 1;
              if ( v23 )
                v26 = v24;
              *v26 = 0;
            }
            else
            {
              *v24 = 0;
            }
          }
          v16 = *((_QWORD *)&v29 + 1);
          ++v17;
          v18 = v29;
        }
        while ( v17 < (unsigned __int64)((__int64)(*((_QWORD *)&v29 + 1) - v29) >> 5) );
      }
      RegistrationList = 0;
      *a4 = (v16 - v18) >> 5;
    }
  }
  else
  {
    LogSmsRouterError("_RpcSmsRouter_GetRegistrationList", 0x29u, Instance, "Failed to get service manager instance.");
  }
LABEL_37:
  std::wstring::~wstring((char **)&v32);
  std::wstring::~wstring((char **)&v34);
  std::vector<std::wstring>::~vector<std::wstring>(&v29);
  return (unsigned int)RegistrationList;
}

```

## disassembly

```asm
0x18000a0c0  mov     [rsp-8+arg_0], rbx
0x18000a0c5  push    rbp
0x18000a0c6  push    rsi
0x18000a0c7  push    rdi
0x18000a0c8  push    r12
0x18000a0ca  push    r13
0x18000a0cc  push    r14
0x18000a0ce  push    r15
0x18000a0d0  lea     rbp, [rsp-27h]
0x18000a0d5  sub     rsp, 90h
0x18000a0dc  mov     rax, cs:__security_cookie
0x18000a0e3  xor     rax, rsp
0x18000a0e6  mov     [rbp+57h+var_38], rax
0x18000a0ea  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000a0f2  lea     rcx, SourceString; "cellularMessaging"
0x18000a0f9  xorps   xmm0, xmm0
0x18000a0fc  xor     r13d, r13d
0x18000a0ff  movups  [rbp+57h+var_58], xmm0
0x18000a103  mov     word ptr [rbp+57h+var_58], r13w
0x18000a108  mov     r12, r9
0x18000a10b  movups  [rbp+57h+var_78], xmm0
0x18000a10f  mov     word ptr [rbp+57h+var_78], r13w
0x18000a114  mov     r15, r8
0x18000a117  mov     rbx, rdx
0x18000a11a  mov     [rbp+57h+var_80], r13
0x18000a11e  movdqu  [rbp+57h+var_98], xmm0
0x18000a123  mov     [rbp+57h+var_88], r13
0x18000a127  movdqu  [rbp+57h+var_48], xmm1
0x18000a12c  movdqu  [rbp+57h+var_68], xmm1
0x18000a131  call    ?HasCapability@@YAHPEBG@Z; HasCapability(ushort const *)
0x18000a136  test    eax, eax
0x18000a138  jnz     short loc_18000A147
0x18000a13a  mov     edi, 80070005h
0x18000a13f  lea     edx, [rax+1Dh]
0x18000a142  mov     r8d, edi
0x18000a145  jmp     short loc_18000A15E
0x18000a147  lea     rcx, [rbp+57h+var_78]
0x18000a14b  call    ?GetUserSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSmsRpcUtils::GetUserSid(std::wstring &)
0x18000a150  mov     edi, eax
0x18000a152  test    eax, eax
0x18000a154  jns     short loc_18000A176
0x18000a156  mov     edx, 23h ; '#'; unsigned int
0x18000a15b  mov     r8d, eax; int
0x18000a15e  lea     r9, aFailedSecurity; "Failed security check."
0x18000a165  lea     rcx, aRpcsmsrouterGe_0; "_RpcSmsRouter_GetRegistrationList"
0x18000a16c  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000a171  jmp     loc_18000A2FC
0x18000a176  lea     rcx, [rbp+57h+var_80]; struct CSmsServiceManager **
0x18000a17a  call    ?GetInstance@CSmsServiceManager@@SAJPEAPEAV1@@Z; CSmsServiceManager::GetInstance(CSmsServiceManager * *)
0x18000a17f  mov     edi, eax
0x18000a181  test    eax, eax
0x18000a183  jns     short loc_18000A196
0x18000a185  lea     r9, aFailedToGetSer; "Failed to get service manager instance."
0x18000a18c  mov     r8d, eax
0x18000a18f  mov     edx, 29h ; ')'
0x18000a194  jmp     short loc_18000A165
0x18000a196  lea     r8, [rbp+57h+var_A0]
0x18000a19a  mov     [rbp+57h+var_A0], r13d
0x18000a19e  lea     rdx, [rbp+57h+var_58]
0x18000a1a2  mov     rcx, rbx; Src
0x18000a1a5  call    ?CalculateAppName@CSmsRpcUtils@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAH@Z; CSmsRpcUtils::CalculateAppName(ushort const *,std::wstring &,int &)
0x18000a1aa  mov     edi, eax
0x18000a1ac  test    eax, eax
0x18000a1ae  jns     short loc_18000A1B7
0x18000a1b0  mov     edx, 2Fh ; '/'
0x18000a1b5  jmp     short loc_18000A15B
0x18000a1b7  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18000a1bc  lea     r8, [rbp+57h+var_78]
0x18000a1c0  mov     rbx, [rbp+57h+var_80]
0x18000a1c4  lea     rdx, [rbp+57h+var_58]
0x18000a1c8  cmova   r8, qword ptr [rbp+57h+var_78]
0x18000a1cd  lea     r9, [rbp+57h+var_98]
0x18000a1d1  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18000a1d6  cmova   rdx, qword ptr [rbp+57h+var_58]
0x18000a1db  lea     rcx, [rbx+60h]
0x18000a1df  call    ?GetRegistrationList@CSmsInterceptor@@QEAAJPEBG0AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CSmsInterceptor::GetRegistrationList(ushort const *,ushort const *,std::vector<std::wstring> &)
0x18000a1e4  mov     edi, eax
0x18000a1e6  mov     rcx, rbx
0x18000a1e9  mov     rax, [rbx]
0x18000a1ec  mov     rax, [rax+10h]
0x18000a1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f5  test    edi, edi
0x18000a1f7  js      loc_18000A2FC
0x18000a1fd  mov     rcx, qword ptr [rbp+57h+var_98+8]
0x18000a201  sub     rcx, qword ptr [rbp+57h+var_98]
0x18000a205  sar     rcx, 5
0x18000a209  shl     rcx, 3; Size
0x18000a20d  call    cs:__imp_malloc
0x18000a213  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x18000a217  mov     esi, r13d
0x18000a21a  mov     r8, qword ptr [rbp+57h+var_98]
0x18000a21e  mov     [r15], rax
0x18000a221  mov     rax, rdx
0x18000a224  sub     rax, r8
0x18000a227  sar     rax, 5
0x18000a22b  test    rax, rax
0x18000a22e  jz      loc_18000A2EE
0x18000a234  mov     ebx, esi
0x18000a236  shl     rbx, 5
0x18000a23a  add     rbx, r8
0x18000a23d  mov     r14d, esi
0x18000a240  cmp     qword ptr [rbx+18h], 7
0x18000a245  jbe     short loc_18000A24C
0x18000a247  mov     rax, [rbx]
0x18000a24a  jmp     short loc_18000A24F
0x18000a24c  mov     rax, rbx
0x18000a24f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a253  inc     rdi
0x18000a256  cmp     [rax+rdi*2], r13w
0x18000a25b  jnz     short loc_18000A253
0x18000a25d  lea     rdi, ds:2[rdi*2]
0x18000a265  mov     rcx, rdi; Size
0x18000a268  call    cs:__imp_malloc
0x18000a26e  mov     rcx, [r15]
0x18000a271  mov     [rcx+r14*8], rax
0x18000a275  cmp     qword ptr [rbx+18h], 7
0x18000a27a  jbe     short loc_18000A27F
0x18000a27c  mov     rbx, [rbx]
0x18000a27f  shr     rdi, 1
0x18000a282  jz      short loc_18000A2CF
0x18000a284  mov     rax, [r15]
0x18000a287  mov     rdx, [rax+r14*8]
0x18000a28b  cmp     rdi, 7FFFFFFFh
0x18000a292  jbe     short loc_18000A29A
0x18000a294  mov     [rdx], r13w
0x18000a298  jmp     short loc_18000A2CF
0x18000a29a  mov     eax, 7FFFFFFEh
0x18000a29f  test    rax, rax
0x18000a2a2  jz      short loc_18000A2C0
0x18000a2a4  movzx   ecx, word ptr [rbx]
0x18000a2a7  test    cx, cx
0x18000a2aa  jz      short loc_18000A2C0
0x18000a2ac  mov     [rdx], cx
0x18000a2af  add     rbx, 2
0x18000a2b3  add     rdx, 2
0x18000a2b7  dec     rax
0x18000a2ba  sub     rdi, 1
0x18000a2be  jnz     short loc_18000A29F
0x18000a2c0  test    rdi, rdi
0x18000a2c3  lea     rcx, [rdx-2]
0x18000a2c7  cmovnz  rcx, rdx
0x18000a2cb  mov     [rcx], r13w
0x18000a2cf  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x18000a2d3  inc     esi
0x18000a2d5  mov     r8, qword ptr [rbp+57h+var_98]
0x18000a2d9  mov     rcx, rdx
0x18000a2dc  sub     rcx, r8
0x18000a2df  mov     eax, esi
0x18000a2e1  sar     rcx, 5
0x18000a2e5  cmp     rax, rcx
0x18000a2e8  jb      loc_18000A234
0x18000a2ee  sub     rdx, r8
0x18000a2f1  mov     edi, r13d
0x18000a2f4  sar     rdx, 5
0x18000a2f8  mov     [r12], edx
0x18000a2fc  lea     rcx, [rbp+57h+var_78]; void *
0x18000a300  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a305  lea     rcx, [rbp+57h+var_58]; void *
0x18000a309  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a30e  lea     rcx, [rbp+57h+var_98]
0x18000a312  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18000a317  mov     eax, edi
0x18000a319  mov     rcx, [rbp+57h+var_38]
0x18000a31d  xor     rcx, rsp; StackCookie
0x18000a320  call    __security_check_cookie
0x18000a325  mov     rbx, [rsp+0C0h+arg_0]
0x18000a32d  add     rsp, 90h
0x18000a334  pop     r15
0x18000a336  pop     r14
0x18000a338  pop     r13
0x18000a33a  pop     r12
0x18000a33c  pop     rdi
0x18000a33d  pop     rsi
0x18000a33e  pop     rbp
0x18000a33f  retn
```
