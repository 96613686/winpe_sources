# EnableDebugMode(ulong,ATL::CComPtr<IDispatch> &)

- ea: `0x180014210`
- end: `0x1800143d6`
- name: `?EnableDebugMode@@YAHKAEAV?$CComPtr@UIDispatch@@@ATL@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(__int64, BPT **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001800`
- `0x180002678`
- `0x180014210`
- `0x18002f108`
- `0x180030ad4`
- `0x1800325d0`
- `0x180035010`

## string_xrefs

- `0x180014290`: `F12App.dll`

## pseudocode

```c
__int64 __fastcall EnableDebugMode(__int64 a1, BPT **a2)
{
  __int64 v3; // rdx
  void (*v4)(void); // rax
  __int64 v5; // rbx
  struct IDispatch *v6; // rdx
  const unsigned __int16 *v7; // r9
  void **v9; // [rsp+28h] [rbp-D8h]
  struct _GUID v10; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[560]; // [rsp+40h] [rbp-C0h] BYREF

  *(_QWORD *)v10.Data4 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  F12::GetRootF12Directory(v10.Data4);
  if ( *(int *)(*(_QWORD *)v10.Data4 - 16LL) <= 0 )
  {
    v3 = *(_QWORD *)v10.Data4 - 24LL;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v10.Data4 - 24LL + 16), 0xFFFFFFFF) > 1 )
      return 0xFFFFFFFFLL;
    v4 = *(void (**)(void))(**(_QWORD **)v3 + 8LL);
LABEL_9:
    v4();
    return 0xFFFFFFFFLL;
  }
  Win32Helpers::OurPathAppend(v10.Data4, L"F12App.dll");
  *(_QWORD *)&v10.Data1 = 0;
  v5 = *(_QWORD *)v10.Data4;
  if ( BPT::CoCreateUsingDiagnosticsMode(*a2, v6, *(const struct _GUID **)v10.Data4, v7, &v10, v9) )
  {
    if ( *(_QWORD *)&v10.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v10.Data1 + 16LL))(*(_QWORD *)&v10.Data1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 - 24 + 16), 0xFFFFFFFF) > 1 )
      return 0xFFFFFFFFLL;
    v4 = *(void (**)(void))(**(_QWORD **)(v5 - 24) + 8LL);
    goto LABEL_9;
  }
  memset_0(v11, 0, 0x22Cu);
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE *))(**(_QWORD **)&v10.Data1 + 64LL))(
         *(_QWORD *)&v10.Data1,
         102,
         0,
         v11) )
  {
    if ( *(_QWORD *)&v10.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v10.Data1 + 16LL))(*(_QWORD *)&v10.Data1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 - 24) + 8LL))(*(_QWORD *)(v5 - 24));
    return 1;
  }
  else
  {
    if ( *(_QWORD *)&v10.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v10.Data1 + 16LL))(*(_QWORD *)&v10.Data1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 - 24) + 8LL))(*(_QWORD *)(v5 - 24));
    return 0;
  }
}

```

## disassembly

```asm
0x180014210  mov     [rsp-8+arg_0], rbx
0x180014215  mov     [rsp-8+arg_10], rdi
0x18001421a  push    rbp
0x18001421b  lea     rbp, [rsp-180h]
0x180014223  sub     rsp, 280h
0x18001422a  mov     rax, cs:__security_cookie
0x180014231  xor     rax, rsp
0x180014234  mov     [rbp+180h+var_10], rax
0x18001423b  mov     rdi, rdx
0x18001423e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014245  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001424c  mov     rax, [rax+18h]
0x180014250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014255  add     rax, 18h
0x180014259  mov     qword ptr [rsp+280h+var_250.Data4], rax
0x18001425e  lea     rcx, [rsp+280h+var_250.Data4]
0x180014263  call    ?GetRootF12Directory@F12@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; F12::GetRootF12Directory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180014268  mov     rax, qword ptr [rsp+280h+var_250.Data4]
0x18001426d  cmp     dword ptr [rax-10h], 0
0x180014271  jg      short loc_180014290
0x180014273  lea     rdx, [rax-18h]
0x180014277  or      eax, 0FFFFFFFFh
0x18001427a  lock xadd [rdx+10h], eax
0x18001427f  sub     eax, 1
0x180014282  jg      short loc_1800142FF
0x180014284  mov     rcx, [rdx]
0x180014287  mov     rax, [rcx]
0x18001428a  mov     rax, [rax+8]
0x18001428e  jmp     short loc_1800142FA
0x180014290  lea     rdx, aF12appDll; "F12App.dll"
0x180014297  lea     rcx, [rsp+280h+var_250.Data4]
0x18001429c  call    ?OurPathAppend@Win32Helpers@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; Win32Helpers::OurPathAppend(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)
0x1800142a1  mov     qword ptr [rsp+280h+var_250.Data1], 0
0x1800142aa  lea     rax, [rsp+280h+var_250]
0x1800142af  mov     [rsp+280h+var_260], rax; struct _GUID *
0x1800142b4  mov     rbx, qword ptr [rsp+280h+var_250.Data4]
0x1800142b9  mov     r8, rbx; struct _GUID *
0x1800142bc  mov     rcx, [rdi]; this
0x1800142bf  call    ?CoCreateUsingDiagnosticsMode@BPT@@YAJPEAUIDispatch@@AEBU_GUID@@PEBG1PEAPEAX@Z; BPT::CoCreateUsingDiagnosticsMode(IDispatch *,_GUID const &,ushort const *,_GUID const &,void * *)
0x1800142c4  test    eax, eax
0x1800142c6  jz      short loc_180014307
0x1800142c8  mov     rcx, qword ptr [rsp+280h+var_250.Data1]
0x1800142cd  test    rcx, rcx
0x1800142d0  jz      short loc_1800142DF
0x1800142d2  mov     rax, [rcx]
0x1800142d5  mov     rax, [rax+10h]
0x1800142d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142de  nop
0x1800142df  lea     rdx, [rbx-18h]
0x1800142e3  or      ecx, 0FFFFFFFFh
0x1800142e6  lock xadd [rdx+10h], ecx
0x1800142eb  sub     ecx, 1
0x1800142ee  jg      short loc_1800142FF
0x1800142f0  mov     rcx, [rdx]
0x1800142f3  mov     r8, [rcx]
0x1800142f6  mov     rax, [r8+8]
0x1800142fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ff  or      eax, 0FFFFFFFFh
0x180014302  jmp     loc_1800143B2
0x180014307  xor     edx, edx; Val
0x180014309  mov     r8d, 22Ch; Size
0x18001430f  lea     rcx, [rsp+280h+var_240]; void *
0x180014314  call    memset_0
0x180014319  mov     rcx, qword ptr [rsp+280h+var_250.Data1]
0x18001431e  mov     rax, [rcx]
0x180014321  lea     r9, [rsp+280h+var_240]
0x180014326  xor     r8d, r8d
0x180014329  lea     edx, [r8+66h]
0x18001432d  mov     rax, [rax+40h]
0x180014331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014336  nop
0x180014337  test    eax, eax
0x180014339  jnz     short loc_180014376
0x18001433b  mov     rcx, qword ptr [rsp+280h+var_250.Data1]
0x180014340  test    rcx, rcx
0x180014343  jz      short loc_180014352
0x180014345  mov     rax, [rcx]
0x180014348  mov     rax, [rax+10h]
0x18001434c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014351  nop
0x180014352  lea     rdx, [rbx-18h]
0x180014356  or      eax, 0FFFFFFFFh
0x180014359  lock xadd [rdx+10h], eax
0x18001435e  sub     eax, 1
0x180014361  jg      short loc_180014372
0x180014363  mov     rcx, [rdx]
0x180014366  mov     rax, [rcx]
0x180014369  mov     rax, [rax+8]
0x18001436d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014372  xor     eax, eax
0x180014374  jmp     short loc_1800143B2
0x180014376  mov     rcx, qword ptr [rsp+280h+var_250.Data1]
0x18001437b  test    rcx, rcx
0x18001437e  jz      short loc_18001438D
0x180014380  mov     rax, [rcx]
0x180014383  mov     rax, [rax+10h]
0x180014387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001438c  nop
0x18001438d  lea     rdx, [rbx-18h]
0x180014391  or      eax, 0FFFFFFFFh
0x180014394  lock xadd [rdx+10h], eax
0x180014399  sub     eax, 1
0x18001439c  jg      short loc_1800143AD
0x18001439e  mov     rcx, [rdx]
0x1800143a1  mov     rax, [rcx]
0x1800143a4  mov     rax, [rax+8]
0x1800143a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ad  mov     eax, 1
0x1800143b2  mov     rcx, [rbp+180h+var_10]
0x1800143b9  xor     rcx, rsp; StackCookie
0x1800143bc  call    __security_check_cookie
0x1800143c1  lea     r11, [rsp+280h+var_s0]
0x1800143c9  mov     rbx, [r11+10h]
0x1800143cd  mov     rdi, [r11+20h]
0x1800143d1  mov     rsp, r11
0x1800143d4  pop     rbp
0x1800143d5  retn
```
