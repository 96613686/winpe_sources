# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800275ac`
- end: `0x18002771c`
- name: `?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(__int64, __int128 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a510`
- `0x18001a8b4`
- `0x18001c958`
- `0x18001d1c0`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013d68`
- `0x180013de4`
- `0x180013f88`
- `0x180017a20`
- `0x180027328`
- `0x1800275ac`
- `0x180027724`

## string_xrefs

- `0x1800275fa`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
        __int64 a1,
        __int128 *a2)
{
  Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *v4; // rax
  struct SERVICE_STATUS_HANDLE__ *v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  struct Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *Instance; // rax
  _QWORD *v10; // rdx
  __int64 v11; // r8
  int v12; // [rsp+20h] [rbp-68h]
  __int128 Src; // [rsp+28h] [rbp-60h] BYREF
  __m128i si128; // [rsp+38h] [rbp-50h]
  _OWORD v15[2]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( *((_QWORD *)Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance() + 3)
    || (v4 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(),
        v6 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(v4, v5),
        v7 = v6,
        v6 >= 0) )
  {
    Instance = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance();
    v10 = (_QWORD *)((char *)Instance + 8);
    Src = 0;
    si128 = 0;
    if ( *((_QWORD *)Instance + 4) > 7u )
      v10 = (_QWORD *)*v10;
    std::wstring::_Construct<2,unsigned short const *>(&Src, v10, *((_QWORD *)Instance + 3));
    std::wstring::_Append<unsigned short>(&Src);
    memset(v15, 0, sizeof(v15));
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a1 + 2 * v11) );
    std::wstring::_Construct<1,unsigned short const *>(v15, a1);
    std::wstring::_Append<unsigned short>(&Src);
    std::wstring::_Tidy_deallocate(v15);
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
      v12);
    return v7;
  }
}

```

## disassembly

```asm
0x1800275ac  mov     [rsp+arg_10], rbx
0x1800275b1  push    rsi
0x1800275b2  push    rdi
0x1800275b3  push    r14
0x1800275b5  sub     rsp, 70h
0x1800275b9  mov     rax, cs:__security_cookie
0x1800275c0  xor     rax, rsp
0x1800275c3  mov     [rsp+88h+var_20], rax
0x1800275c8  mov     rdi, rdx
0x1800275cb  mov     rsi, rcx
0x1800275ce  call    ?GetInstance@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAPEAV1234@XZ; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(void)
0x1800275d3  xor     r14d, r14d
0x1800275d6  cmp     [rax+18h], r14
0x1800275da  jnz     short loc_180027612
0x1800275dc  call    ?GetInstance@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAPEAV1234@XZ; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(void)
0x1800275e1  mov     rcx, rax; this
0x1800275e4  call    ?Initialize@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@QEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(SERVICE_STATUS_HANDLE__ *)
0x1800275e9  mov     ebx, eax
0x1800275eb  test    eax, eax
0x1800275ed  jns     short loc_180027612
0x1800275ef  mov     rcx, [rsp+88h]; this
0x1800275f7  mov     r9d, eax; char *
0x1800275fa  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027601  mov     edx, 0ABh; void *
0x180027606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002760b  mov     eax, ebx
0x18002760d  jmp     loc_1800276FD
0x180027612  call    ?GetInstance@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAPEAV1234@XZ; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(void)
0x180027617  lea     rdx, [rax+8]
0x18002761b  xorps   xmm0, xmm0
0x18002761e  movups  [rsp+88h+Src], xmm0
0x180027623  xorps   xmm1, xmm1
0x180027626  movdqu  [rsp+88h+var_50], xmm1
0x18002762c  mov     r8, [rdx+10h]
0x180027630  cmp     qword ptr [rdx+18h], 7
0x180027635  jbe     short loc_18002763A
0x180027637  mov     rdx, [rdx]
0x18002763a  lea     rcx, [rsp+88h+Src]
0x18002763f  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180027644  nop
0x180027645  mov     r8d, 1
0x18002764b  lea     rdx, asc_180037100; "\\"
0x180027652  lea     rcx, [rsp+88h+Src]; Src
0x180027657  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002765c  xorps   xmm0, xmm0
0x18002765f  movups  [rsp+88h+var_40], xmm0
0x180027664  xorps   xmm1, xmm1
0x180027667  movdqu  [rsp+88h+var_30], xmm1
0x18002766d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027671  inc     r8
0x180027674  cmp     [rsi+r8*2], r14w
0x180027679  jnz     short loc_180027671
0x18002767b  mov     rdx, rsi
0x18002767e  lea     rcx, [rsp+88h+var_40]
0x180027683  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027688  nop
0x180027689  lea     rdx, [rsp+88h+var_40]
0x18002768e  cmp     qword ptr [rsp+88h+var_30+8], 7
0x180027694  cmova   rdx, qword ptr [rsp+88h+var_40]
0x18002769a  mov     r8, qword ptr [rsp+88h+var_30]
0x18002769f  lea     rcx, [rsp+88h+Src]; Src
0x1800276a4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800276a9  nop
0x1800276aa  lea     rcx, [rsp+88h+var_40]
0x1800276af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800276b4  lea     rax, [rsp+88h+Src]
0x1800276b9  cmp     rdi, rax
0x1800276bc  jz      short loc_1800276EB
0x1800276be  mov     rcx, rdi
0x1800276c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800276c6  movups  xmm0, [rsp+88h+Src]
0x1800276cb  movups  xmmword ptr [rdi], xmm0
0x1800276ce  movups  xmm1, [rsp+88h+var_50]
0x1800276d3  movups  xmmword ptr [rdi+10h], xmm1
0x1800276d7  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800276df  movdqu  [rsp+88h+var_50], xmm0
0x1800276e5  mov     word ptr [rsp+88h+Src], r14w
0x1800276eb  lea     rcx, [rsp+88h+Src]
0x1800276f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800276f5  xor     eax, eax
0x1800276f7  jmp     short loc_1800276FD
0x1800276f9  mov     eax, [rsp+88h+var_68]
0x1800276fd  mov     rcx, [rsp+88h+var_20]
0x180027702  xor     rcx, rsp; StackCookie
0x180027705  call    __security_check_cookie
0x18002770a  mov     rbx, [rsp+88h+arg_10]
0x180027712  add     rsp, 70h
0x180027716  pop     r14
0x180027718  pop     rdi
0x180027719  pop     rsi
0x18002771a  retn
```
