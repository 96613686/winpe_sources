# GatherXToken(std::vector<StoredTicket,std::allocator<StoredTicket>> &,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<IInspectable *>> &)

- ea: `0x180036174`
- end: `0x18003641a`
- name: `?GatherXToken@@YAXAEAV?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@AEAV?$ComPtr@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180036bfc`

## callees

- `0x1800026b0`
- `0x18002008c`
- `0x18002c4b8`
- `0x18002d674`
- `0x180030aac`
- `0x180031ac0`
- `0x180035a64`
- `0x180036174`
- `0x18003da10`
- `0x18003ef6c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003622b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003622b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036264`

## string_xrefs

- `0x1800363c5`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x180036408`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x1800363b8`: `GatherXToken`
- `0x1800363a8`: `Captured %d Xtokens.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall GatherXToken(__int64 a1, __int64 *a2)
{
  char **v4; // r14
  char **v5; // rdi
  __int64 v6; // rcx
  int AllAccountTickets; // eax
  __int64 v8; // rdi
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v10; // r8
  PCWSTR v11; // rax
  unsigned __int64 v12; // r8
  __int128 *v13; // rdx
  __int128 *v14; // rdx
  _OWORD *v15; // rdx
  __m128i si128; // xmm0
  int v17; // [rsp+20h] [rbp-89h]
  int v18[2]; // [rsp+40h] [rbp-69h] BYREF
  struct WinStoreAuth::TicketHolder **v19; // [rsp+48h] [rbp-61h] BYREF
  __int128 v20; // [rsp+50h] [rbp-59h] BYREF
  __m128i v21; // [rsp+60h] [rbp-49h]
  __int128 v22; // [rsp+70h] [rbp-39h] BYREF
  __m128i v23; // [rsp+80h] [rbp-29h]
  __int128 v24; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v25; // [rsp+A0h] [rbp-9h]
  unsigned __int64 v26; // [rsp+A8h] [rbp-1h]
  __int128 v27; // [rsp+B0h] [rbp+7h] BYREF
  unsigned __int64 v28; // [rsp+C0h] [rbp+17h]
  unsigned __int64 v29; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *(_QWORD *)v18 = 0;
  v19 = 0;
  v4 = *(char ***)(a1 + 8);
  v5 = *(char ***)a1;
  if ( *(char ***)a1 != v4 )
  {
    do
    {
      std::wstring::_Tidy_deallocate(v5 + 4);
      std::wstring::_Tidy_deallocate(v5);
      v5 += 8;
    }
    while ( v5 != v4 );
    *(_QWORD *)(a1 + 8) = *(_QWORD *)a1;
  }
  v6 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  AllAccountTickets = WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(
                        v6,
                        (__int64)a2,
                        8,
                        1,
                        (HSTRING)v18,
                        &v19,
                        a2);
  if ( AllAccountTickets < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x31,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
      (const char *)(unsigned int)AllAccountTickets,
      v17);
  v8 = *(_QWORD *)v18;
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v18 + 16LL), 0);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v10 = -1;
  do
    ++v10;
  while ( StringRawBuffer[v10] );
  std::wstring::_Construct<1,unsigned short const *>(&v27, StringRawBuffer, v10);
  v11 = WindowsGetStringRawBuffer(*(HSTRING *)(v8 + 8), 0);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  std::wstring::_Construct<1,unsigned short const *>(&v24, v11, v12);
  v20 = 0;
  v21 = 0;
  v13 = &v24;
  if ( v26 > 7 )
    v13 = (__int128 *)v24;
  std::wstring::_Construct<2,unsigned short const *>((__int64)&v20, v13, v25);
  v22 = 0;
  v23 = 0;
  v14 = &v27;
  if ( v29 > 7 )
    v14 = (__int128 *)v27;
  std::wstring::_Construct<2,unsigned short const *>((__int64)&v22, v14, v28);
  v15 = *(_OWORD **)(a1 + 8);
  if ( v15 == *(_OWORD **)(a1 + 16) )
  {
    std::vector<StoredTicket>::_Emplace_reallocate<StoredTicket>(a1, v15, &v20);
  }
  else
  {
    *v15 = v20;
    v15[1] = v21;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v21 = si128;
    LOWORD(v20) = 0;
    v15[2] = v22;
    v15[3] = v23;
    v23 = si128;
    LOWORD(v22) = 0;
    *(_QWORD *)(a1 + 8) += 64LL;
  }
  std::wstring::_Tidy_deallocate((char **)&v22);
  std::wstring::_Tidy_deallocate((char **)&v20);
  std::wstring::_Tidy_deallocate((char **)&v24);
  std::wstring::_Tidy_deallocate((char **)&v27);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
    0x36u,
    "GatherXToken",
    -1,
    L"Captured %d Xtokens.",
    (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 6);
  WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray((LPVOID *)v18, v19);
}

```

## disassembly

```asm
0x180036174  mov     [rsp-8+arg_10], rbx
0x180036179  push    rbp
0x18003617a  push    rsi
0x18003617b  push    rdi
0x18003617c  push    r14
0x18003617e  push    r15
0x180036180  lea     rbp, [rsp-37h]
0x180036185  sub     rsp, 0E0h
0x18003618c  mov     rax, cs:__security_cookie
0x180036193  xor     rax, rsp
0x180036196  mov     [rbp+57h+var_30], rax
0x18003619a  mov     rsi, rdx
0x18003619d  mov     rbx, rcx
0x1800361a0  xor     r15d, r15d
0x1800361a3  mov     qword ptr [rbp+57h+var_C0], r15
0x1800361a7  mov     [rbp+57h+var_B8], r15
0x1800361ab  mov     r14, [rcx+8]
0x1800361af  mov     rdi, [rcx]
0x1800361b2  cmp     rdi, r14
0x1800361b5  jz      short loc_1800361D8
0x1800361b7  lea     rcx, [rdi+20h]
0x1800361bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800361c0  mov     rcx, rdi
0x1800361c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800361c8  add     rdi, 40h ; '@'
0x1800361cc  cmp     rdi, r14
0x1800361cf  jnz     short loc_1800361B7
0x1800361d1  mov     rax, [rbx]
0x1800361d4  mov     [rbx+8], rax
0x1800361d8  mov     rcx, [rsi]
0x1800361db  test    rcx, rcx
0x1800361de  jz      short loc_1800361F0
0x1800361e0  mov     [rsi], r15
0x1800361e3  mov     rax, [rcx]
0x1800361e6  mov     rax, [rax+10h]
0x1800361ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361ef  nop
0x1800361f0  mov     [rsp+100h+var_D0], rsi
0x1800361f5  lea     rax, [rbp+57h+var_B8]
0x1800361f9  mov     [rsp+100h+var_D8], rax
0x1800361fe  lea     rax, [rbp+57h+var_C0]
0x180036202  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180036207  mov     r9b, 1
0x18003620a  mov     r8d, 8
0x180036210  call    ?GetAllAccountTickets@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@W4AccountProviderType@2@_NPEAPEAUTicketHolder@2@PEA_KPEAPEAU?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@3@Z; WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,bool,WinStoreAuth::TicketHolder * *,unsigned __int64 *,Windows::Foundation::Collections::IVector<IInspectable *> * *,bool)
0x180036215  mov     rcx, [rbp+5Fh]; this
0x180036219  test    eax, eax
0x18003621b  js      loc_180036405
0x180036221  xor     edx, edx; length
0x180036223  mov     rdi, qword ptr [rbp+57h+var_C0]
0x180036227  mov     rcx, [rdi+10h]; string
0x18003622b  call    cs:__imp_WindowsGetStringRawBuffer
0x180036231  xorps   xmm0, xmm0
0x180036234  movups  [rbp+57h+var_50], xmm0
0x180036238  mov     [rbp+57h+var_40], r15
0x18003623c  mov     [rbp+57h+var_38], r15
0x180036240  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180036244  mov     r8, rsi
0x180036247  inc     r8
0x18003624a  cmp     [rax+r8*2], r15w
0x18003624f  jnz     short loc_180036247
0x180036251  mov     rdx, rax
0x180036254  lea     rcx, [rbp+57h+var_50]
0x180036258  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003625d  nop
0x18003625e  xor     edx, edx; length
0x180036260  mov     rcx, [rdi+8]; string
0x180036264  call    cs:__imp_WindowsGetStringRawBuffer
0x18003626a  xorps   xmm0, xmm0
0x18003626d  movups  [rbp+57h+var_70], xmm0
0x180036271  mov     [rbp+57h+var_60], r15
0x180036275  mov     [rbp+57h+var_58], r15
0x180036279  mov     r8, rsi
0x18003627c  inc     r8
0x18003627f  cmp     [rax+r8*2], r15w
0x180036284  jnz     short loc_18003627C
0x180036286  mov     rdx, rax
0x180036289  lea     rcx, [rbp+57h+var_70]
0x18003628d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036292  nop
0x180036293  xorps   xmm0, xmm0
0x180036296  movups  [rbp+57h+var_B0], xmm0
0x18003629a  xorps   xmm1, xmm1
0x18003629d  movdqa  [rbp+57h+var_A0], xmm1
0x1800362a2  lea     rdx, [rbp+57h+var_70]
0x1800362a6  cmp     [rbp+57h+var_58], 7
0x1800362ab  cmova   rdx, qword ptr [rbp+57h+var_70]
0x1800362b0  mov     r8, [rbp+57h+var_60]
0x1800362b4  lea     rcx, [rbp+57h+var_B0]
0x1800362b8  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800362bd  nop
0x1800362be  xorps   xmm0, xmm0
0x1800362c1  movups  [rbp+57h+var_90], xmm0
0x1800362c5  xorps   xmm1, xmm1
0x1800362c8  movdqa  [rbp+57h+var_80], xmm1
0x1800362cd  lea     rdx, [rbp+57h+var_50]
0x1800362d1  cmp     [rbp+57h+var_38], 7
0x1800362d6  cmova   rdx, qword ptr [rbp+57h+var_50]
0x1800362db  mov     r8, [rbp+57h+var_40]
0x1800362df  lea     rcx, [rbp+57h+var_90]
0x1800362e3  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800362e8  nop
0x1800362e9  mov     rdx, [rbx+8]
0x1800362ed  cmp     rdx, [rbx+10h]
0x1800362f1  jz      short loc_180036365
0x1800362f3  movzx   eax, word ptr [rbp+57h+var_B0]
0x1800362f7  mov     [rdx], ax
0x1800362fa  movsd   xmm0, qword ptr [rbp+57h+var_B0+2]
0x1800362ff  movsd   qword ptr [rdx+2], xmm0
0x180036304  mov     eax, dword ptr [rbp+57h+var_B0+0Ah]
0x180036307  mov     [rdx+0Ah], eax
0x18003630a  movzx   eax, word ptr [rbp+57h+var_B0+0Eh]
0x18003630e  mov     [rdx+0Eh], ax
0x180036312  mov     rax, qword ptr [rbp+57h+var_A0]
0x180036316  mov     [rdx+10h], rax
0x18003631a  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x18003631e  mov     [rdx+18h], rax
0x180036322  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18003632a  movdqa  [rbp+57h+var_A0], xmm0
0x18003632f  mov     word ptr [rbp+57h+var_B0], r15w
0x180036334  mov     rax, qword ptr [rbp+57h+var_90]
0x180036338  mov     [rdx+20h], rax
0x18003633c  mov     rax, qword ptr [rbp+57h+var_90+8]
0x180036340  mov     [rdx+28h], rax
0x180036344  mov     rax, qword ptr [rbp+57h+var_80]
0x180036348  mov     [rdx+30h], rax
0x18003634c  mov     rax, qword ptr [rbp+57h+var_80+8]
0x180036350  mov     [rdx+38h], rax
0x180036354  movdqa  [rbp+57h+var_80], xmm0
0x180036359  mov     word ptr [rbp+57h+var_90], r15w
0x18003635e  add     qword ptr [rbx+8], 40h ; '@'
0x180036363  jmp     short loc_180036372
0x180036365  lea     r8, [rbp+57h+var_B0]
0x180036369  mov     rcx, rbx
0x18003636c  call    ??$_Emplace_reallocate@UStoredTicket@@@?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@AEAAPEAUStoredTicket@@QEAU2@$$QEAU2@@Z; std::vector<StoredTicket>::_Emplace_reallocate<StoredTicket>(StoredTicket * const,StoredTicket &&)
0x180036371  nop
0x180036372  lea     rcx, [rbp+57h+var_90]
0x180036376  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003637b  lea     rcx, [rbp+57h+var_B0]
0x18003637f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036384  nop
0x180036385  lea     rcx, [rbp+57h+var_70]
0x180036389  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003638e  nop
0x18003638f  lea     rcx, [rbp+57h+var_50]
0x180036393  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036398  mov     rax, [rbx+8]
0x18003639c  sub     rax, [rbx]
0x18003639f  sar     rax, 6
0x1800363a3  mov     [rsp+100h+var_D0], rax
0x1800363a8  lea     rax, aCapturedDXtoke; "Captured %d Xtokens."
0x1800363af  mov     [rsp+100h+var_D8], rax; unsigned __int16 *
0x1800363b4  mov     [rsp+100h+var_E0], esi; int
0x1800363b8  lea     r9, aGatherxtoken; "GatherXToken"
0x1800363bf  mov     r8d, 36h ; '6'; unsigned int
0x1800363c5  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800363cc  lea     ecx, [r8-33h]; unsigned int
0x1800363d0  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800363d5  mov     rdx, [rbp+57h+var_B8]; struct WinStoreAuth::TicketHolder **
0x1800363d9  lea     rcx, [rbp+57h+var_C0]; this
0x1800363dd  call    ?FreeTicketHolderArray@AuthenticationInternal@WinStoreAuth@@YAXPEAPEAUTicketHolder@2@_K@Z; WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(WinStoreAuth::TicketHolder * *,unsigned __int64)
0x1800363e2  mov     rcx, [rbp+57h+var_30]
0x1800363e6  xor     rcx, rsp; StackCookie
0x1800363e9  call    __security_check_cookie
0x1800363ee  mov     rbx, [rsp+100h+arg_10]
0x1800363f6  add     rsp, 0E0h
0x1800363fd  pop     r15
0x1800363ff  pop     r14
0x180036401  pop     rdi
0x180036402  pop     rsi
0x180036403  pop     rbp
0x180036404  retn
0x180036405  mov     r9d, eax; char *
0x180036408  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18003640f  mov     edx, 31h ; '1'; void *
0x180036414  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
