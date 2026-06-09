# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002661c`
- end: `0x18002678c`
- name: `?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(__int64, __int128 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019ef0`
- `0x18001a280`
- `0x18001c234`
- `0x18001ca58`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800139c4`
- `0x180013a40`
- `0x180013be0`
- `0x1800174f0`
- `0x1800263c8`
- `0x18002661c`
- `0x180026794`

## string_xrefs

- `0x18002666a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
        __int64 a1,
        __int128 *a2)
{
  Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *Instance; // rax
  struct SERVICE_STATUS_HANDLE__ *v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // r8
  int v10; // [rsp+20h] [rbp-68h]
  __int128 Src; // [rsp+28h] [rbp-60h] BYREF
  __m128i si128; // [rsp+38h] [rbp-50h]
  _OWORD v13[2]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( *((_QWORD *)Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance() + 3)
    || (Instance = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(),
        v6 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(Instance, v5),
        v7 = v6,
        v6 >= 0) )
  {
    Src = 0;
    si128 = 0;
    Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance();
    std::wstring::_Construct<2,unsigned short const *>(&Src);
    std::wstring::_Append<unsigned short>(&Src);
    memset(v13, 0, sizeof(v13));
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a1 + 2 * v9) );
    std::wstring::_Construct<1,unsigned short const *>(v13, a1, v9);
    std::wstring::_Append<unsigned short>(&Src);
    std::wstring::_Tidy_deallocate(v13);
    if ( a2 != &Src )
    {
      std::wstring::_Tidy_deallocate(a2);
      *a2 = Src;
      a2[1] = (__int128)si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Src) = 0;
    }
    std::wstring::_Tidy_deallocate(&Src);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
      (const char *)(unsigned int)v6,
      v10);
    return v7;
  }
}

```

## disassembly

```asm
0x18002661c  mov     [rsp+arg_10], rbx
0x180026621  push    rsi
0x180026622  push    rdi
0x180026623  push    r14
0x180026625  sub     rsp, 70h
0x180026629  mov     rax, cs:__security_cookie
0x180026630  xor     rax, rsp
0x180026633  mov     [rsp+88h+var_20], rax
0x180026638  mov     rdi, rdx
0x18002663b  mov     rsi, rcx
0x18002663e  call    ?GetInstance@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAPEAV1234@XZ; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(void)
0x180026643  xor     r14d, r14d
0x180026646  cmp     [rax+18h], r14
0x18002664a  jnz     short loc_180026682
0x18002664c  call    ?GetInstance@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAPEAV1234@XZ; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(void)
0x180026651  mov     rcx, rax; this
0x180026654  call    ?Initialize@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@QEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(SERVICE_STATUS_HANDLE__ *)
0x180026659  mov     ebx, eax
0x18002665b  test    eax, eax
0x18002665d  jns     short loc_180026682
0x18002665f  mov     rcx, [rsp+88h]; this
0x180026667  mov     r9d, eax; char *
0x18002666a  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026671  mov     edx, 0ABh; void *
0x180026676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002667b  mov     eax, ebx
0x18002667d  jmp     loc_18002676D
0x180026682  call    ?GetInstance@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAPEAV1234@XZ; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(void)
0x180026687  lea     rdx, [rax+8]
0x18002668b  xorps   xmm0, xmm0
0x18002668e  movups  [rsp+88h+Src], xmm0
0x180026693  xorps   xmm1, xmm1
0x180026696  movdqu  [rsp+88h+var_50], xmm1
0x18002669c  mov     r8, [rdx+10h]
0x1800266a0  cmp     qword ptr [rdx+18h], 7
0x1800266a5  jbe     short loc_1800266AA
0x1800266a7  mov     rdx, [rdx]
0x1800266aa  lea     rcx, [rsp+88h+Src]
0x1800266af  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800266b4  nop
0x1800266b5  mov     r8d, 1
0x1800266bb  lea     rdx, asc_1800360E0; "\\"
0x1800266c2  lea     rcx, [rsp+88h+Src]; Src
0x1800266c7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800266cc  xorps   xmm0, xmm0
0x1800266cf  movups  [rsp+88h+var_40], xmm0
0x1800266d4  xorps   xmm1, xmm1
0x1800266d7  movdqu  [rsp+88h+var_30], xmm1
0x1800266dd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800266e1  inc     r8
0x1800266e4  cmp     [rsi+r8*2], r14w
0x1800266e9  jnz     short loc_1800266E1
0x1800266eb  mov     rdx, rsi
0x1800266ee  lea     rcx, [rsp+88h+var_40]
0x1800266f3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800266f8  nop
0x1800266f9  lea     rdx, [rsp+88h+var_40]
0x1800266fe  cmp     qword ptr [rsp+88h+var_30+8], 7
0x180026704  cmova   rdx, qword ptr [rsp+88h+var_40]
0x18002670a  mov     r8, qword ptr [rsp+88h+var_30]
0x18002670f  lea     rcx, [rsp+88h+Src]; Src
0x180026714  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180026719  nop
0x18002671a  lea     rcx, [rsp+88h+var_40]
0x18002671f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026724  lea     rax, [rsp+88h+Src]
0x180026729  cmp     rdi, rax
0x18002672c  jz      short loc_18002675B
0x18002672e  mov     rcx, rdi
0x180026731  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026736  movups  xmm0, [rsp+88h+Src]
0x18002673b  movups  xmmword ptr [rdi], xmm0
0x18002673e  movups  xmm1, [rsp+88h+var_50]
0x180026743  movups  xmmword ptr [rdi+10h], xmm1
0x180026747  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18002674f  movdqu  [rsp+88h+var_50], xmm0
0x180026755  mov     word ptr [rsp+88h+Src], r14w
0x18002675b  lea     rcx, [rsp+88h+Src]
0x180026760  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026765  xor     eax, eax
0x180026767  jmp     short loc_18002676D
0x180026769  mov     eax, [rsp+88h+var_68]
0x18002676d  mov     rcx, [rsp+88h+var_20]
0x180026772  xor     rcx, rsp; StackCookie
0x180026775  call    __security_check_cookie
0x18002677a  mov     rbx, [rsp+88h+arg_10]
0x180026782  add     rsp, 70h
0x180026786  pop     r14
0x180026788  pop     rdi
0x180026789  pop     rsi
0x18002678a  retn
```
