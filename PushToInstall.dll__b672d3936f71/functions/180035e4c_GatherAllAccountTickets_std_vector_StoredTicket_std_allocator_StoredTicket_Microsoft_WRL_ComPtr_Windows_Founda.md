# GatherAllAccountTickets(std::vector<StoredTicket,std::allocator<StoredTicket>> &,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<IInspectable *>> &)

- ea: `0x180035e4c`
- end: `0x18003616b`
- name: `?GatherAllAccountTickets@@YAXAEAV?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@AEAV?$ComPtr@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180032cfc`

## callees

- `0x1800026b0`
- `0x18002008c`
- `0x18002c4b8`
- `0x18002d674`
- `0x180030aac`
- `0x180031ac0`
- `0x180035a64`
- `0x180035e4c`
- `0x18003da10`
- `0x18003ef6c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035f71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035fa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035f71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035fa7`

## string_xrefs

- `0x180035f55`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x18003610d`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x180036159`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall GatherAllAccountTickets(__int64 a1, __int64 *a2)
{
  char **v4; // r14
  char **v5; // rdi
  __int64 v6; // rcx
  int AllAccountTickets; // eax
  unsigned __int64 v8; // rdi
  struct WinStoreAuth::TicketHolder **v9; // r14
  __int64 v10; // r15
  __m128i si128; // xmm6
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v13; // r8
  PCWSTR v14; // rax
  unsigned __int64 v15; // r8
  __int128 *v16; // rdx
  __int128 *v17; // rdx
  _OWORD *v18; // rdx
  int v19; // [rsp+28h] [rbp-A9h]
  __int64 v20; // [rsp+38h] [rbp-99h]
  int v21[2]; // [rsp+48h] [rbp-89h] BYREF
  struct WinStoreAuth::TicketHolder **v22; // [rsp+50h] [rbp-81h] BYREF
  __int128 v23; // [rsp+58h] [rbp-79h] BYREF
  __m128i v24; // [rsp+68h] [rbp-69h]
  __int128 v25; // [rsp+78h] [rbp-59h] BYREF
  __m128i v26; // [rsp+88h] [rbp-49h]
  __int128 v27; // [rsp+98h] [rbp-39h] BYREF
  unsigned __int64 v28; // [rsp+A8h] [rbp-29h]
  unsigned __int64 v29; // [rsp+B0h] [rbp-21h]
  __int128 v30; // [rsp+B8h] [rbp-19h] BYREF
  unsigned __int64 v31; // [rsp+C8h] [rbp-9h]
  unsigned __int64 v32; // [rsp+D0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  *(_QWORD *)v21 = 0;
  v22 = 0;
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
                        1,
                        0,
                        (HSTRING)v21,
                        &v22,
                        a2);
  if ( AllAccountTickets < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
      (const char *)(unsigned int)AllAccountTickets,
      v19);
  v8 = 0;
  v9 = v22;
  if ( v22 )
  {
    v10 = *(_QWORD *)v21;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      if ( *(_DWORD *)(v10 + 24 * v8) == 1 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v10 + 24 * v8 + 16), 0);
        v30 = 0;
        v31 = 0;
        v32 = 0;
        v13 = -1;
        do
          ++v13;
        while ( StringRawBuffer[v13] );
        std::wstring::_Construct<1,unsigned short const *>(&v30, StringRawBuffer, v13);
        v14 = WindowsGetStringRawBuffer(*(HSTRING *)(v10 + 24 * v8 + 8), 0);
        v27 = 0;
        v28 = 0;
        v29 = 0;
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
        std::wstring::_Construct<1,unsigned short const *>(&v27, v14, v15);
        v23 = 0;
        v24 = 0;
        v16 = &v27;
        if ( v29 > 7 )
          v16 = (__int128 *)v27;
        std::wstring::_Construct<2,unsigned short const *>((__int64)&v23, v16, v28);
        v25 = 0;
        v26 = 0;
        v17 = &v30;
        if ( v32 > 7 )
          v17 = (__int128 *)v30;
        std::wstring::_Construct<2,unsigned short const *>((__int64)&v25, v17, v31);
        v18 = *(_OWORD **)(a1 + 8);
        if ( v18 == *(_OWORD **)(a1 + 16) )
        {
          std::vector<StoredTicket>::_Emplace_reallocate<StoredTicket>(a1, v18, &v23);
        }
        else
        {
          *v18 = v23;
          v18[1] = v24;
          v24 = si128;
          LOWORD(v23) = 0;
          v18[2] = v25;
          v18[3] = v26;
          v26 = si128;
          LOWORD(v25) = 0;
          *(_QWORD *)(a1 + 8) += 64LL;
        }
        std::wstring::_Tidy_deallocate((char **)&v25);
        std::wstring::_Tidy_deallocate((char **)&v23);
        std::wstring::_Tidy_deallocate((char **)&v27);
        std::wstring::_Tidy_deallocate((char **)&v30);
      }
      else
      {
        LODWORD(v20) = *(_DWORD *)(v10 + 24 * v8);
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
          0x20u,
          "GatherAllAccountTickets",
          -1,
          L"Unexpected ticket provider type %d",
          v20);
      }
      ++v8;
    }
    while ( v8 < (unsigned __int64)v9 );
  }
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
    0x24u,
    "GatherAllAccountTickets",
    -1,
    L"Captured %d MSA tickets.",
    (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 6);
  WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray((LPVOID *)v21, v9);
}

```

## disassembly

```asm
0x180035e4c  mov     rax, rsp
0x180035e4f  mov     [rax+18h], rbx
0x180035e53  push    rbp
0x180035e54  push    rsi
0x180035e55  push    rdi
0x180035e56  push    r12
0x180035e58  push    r13
0x180035e5a  push    r14
0x180035e5c  push    r15
0x180035e5e  lea     rbp, [rax-5Fh]
0x180035e62  sub     rsp, 0F0h
0x180035e69  movaps  xmmword ptr [rax-48h], xmm6
0x180035e6d  mov     rax, cs:__security_cookie
0x180035e74  xor     rax, rsp
0x180035e77  mov     [rbp+57h+var_50], rax
0x180035e7b  mov     rsi, rdx
0x180035e7e  mov     rbx, rcx
0x180035e81  xor     r12d, r12d
0x180035e84  mov     qword ptr [rsp+120h+var_E0], r12
0x180035e89  mov     [rsp+120h+var_D8], r12
0x180035e8e  mov     r14, [rcx+8]
0x180035e92  mov     rdi, [rcx]
0x180035e95  cmp     rdi, r14
0x180035e98  jz      short loc_180035EBB
0x180035e9a  lea     rcx, [rdi+20h]
0x180035e9e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035ea3  mov     rcx, rdi
0x180035ea6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035eab  add     rdi, 40h ; '@'
0x180035eaf  cmp     rdi, r14
0x180035eb2  jnz     short loc_180035E9A
0x180035eb4  mov     rax, [rbx]
0x180035eb7  mov     [rbx+8], rax
0x180035ebb  mov     rcx, [rsi]
0x180035ebe  test    rcx, rcx
0x180035ec1  jz      short loc_180035ED3
0x180035ec3  mov     [rsi], r12
0x180035ec6  mov     rax, [rcx]
0x180035ec9  mov     rax, [rax+10h]
0x180035ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ed2  nop
0x180035ed3  mov     [rsp+120h+var_F0], rsi
0x180035ed8  lea     rax, [rsp+120h+var_D8]
0x180035edd  mov     [rsp+120h+var_F8], rax
0x180035ee2  lea     rax, [rsp+120h+var_E0]
0x180035ee7  mov     qword ptr [rsp+120h+var_100], rax; int
0x180035eec  xor     r9d, r9d
0x180035eef  lea     r8d, [r9+1]
0x180035ef3  call    ?GetAllAccountTickets@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@W4AccountProviderType@2@_NPEAPEAUTicketHolder@2@PEA_KPEAPEAU?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@3@Z; WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,bool,WinStoreAuth::TicketHolder * *,unsigned __int64 *,Windows::Foundation::Collections::IVector<IInspectable *> * *,bool)
0x180035ef8  mov     rcx, [rbp+5Fh]; this
0x180035efc  test    eax, eax
0x180035efe  js      loc_180036156
0x180035f04  mov     rdi, r12
0x180035f07  or      r13, 0FFFFFFFFFFFFFFFFh
0x180035f0b  mov     r14, [rsp+120h+var_D8]
0x180035f10  test    r14, r14
0x180035f13  jz      loc_1800360DF
0x180035f19  mov     r15, qword ptr [rsp+120h+var_E0]
0x180035f1e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180035f26  lea     rsi, [rdi+rdi*2]
0x180035f2a  mov     edx, [r15+rsi*8]
0x180035f2e  cmp     edx, 1
0x180035f31  jz      short loc_180035F6A
0x180035f33  mov     dword ptr [rsp+120h+var_F0], edx
0x180035f37  lea     rax, aUnexpectedTick; "Unexpected ticket provider type %d"
0x180035f3e  mov     [rsp+120h+var_F8], rax; unsigned __int16 *
0x180035f43  mov     [rsp+120h+var_100], r13d; int
0x180035f48  lea     r9, aGatherallaccou; "GatherAllAccountTickets"
0x180035f4f  mov     r8d, 20h ; ' '; unsigned int
0x180035f55  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180035f5c  lea     ecx, [r8-1Eh]; unsigned int
0x180035f60  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180035f65  jmp     loc_1800360D3
0x180035f6a  xor     edx, edx; length
0x180035f6c  mov     rcx, [r15+rsi*8+10h]; string
0x180035f71  call    cs:__imp_WindowsGetStringRawBuffer
0x180035f77  xorps   xmm0, xmm0
0x180035f7a  movups  [rbp+57h+var_70], xmm0
0x180035f7e  mov     [rbp+57h+var_60], r12
0x180035f82  mov     [rbp+57h+var_58], r12
0x180035f86  mov     r8, r13
0x180035f89  inc     r8
0x180035f8c  cmp     [rax+r8*2], r12w
0x180035f91  jnz     short loc_180035F89
0x180035f93  mov     rdx, rax
0x180035f96  lea     rcx, [rbp+57h+var_70]
0x180035f9a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035f9f  nop
0x180035fa0  xor     edx, edx; length
0x180035fa2  mov     rcx, [r15+rsi*8+8]; string
0x180035fa7  call    cs:__imp_WindowsGetStringRawBuffer
0x180035fad  xorps   xmm0, xmm0
0x180035fb0  movups  [rbp+57h+var_90], xmm0
0x180035fb4  mov     [rbp+57h+var_80], r12
0x180035fb8  mov     [rbp+57h+var_78], r12
0x180035fbc  mov     r8, r13
0x180035fbf  inc     r8
0x180035fc2  cmp     [rax+r8*2], r12w
0x180035fc7  jnz     short loc_180035FBF
0x180035fc9  mov     rdx, rax
0x180035fcc  lea     rcx, [rbp+57h+var_90]
0x180035fd0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035fd5  nop
0x180035fd6  xorps   xmm0, xmm0
0x180035fd9  movups  [rbp+57h+var_D0], xmm0
0x180035fdd  xorps   xmm1, xmm1
0x180035fe0  movdqa  [rbp+57h+var_C0], xmm1
0x180035fe5  lea     rdx, [rbp+57h+var_90]
0x180035fe9  cmp     [rbp+57h+var_78], 7
0x180035fee  cmova   rdx, qword ptr [rbp+57h+var_90]
0x180035ff3  mov     r8, [rbp+57h+var_80]
0x180035ff7  lea     rcx, [rbp+57h+var_D0]
0x180035ffb  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180036000  nop
0x180036001  xorps   xmm0, xmm0
0x180036004  movups  [rbp+57h+var_B0], xmm0
0x180036008  xorps   xmm1, xmm1
0x18003600b  movdqa  [rbp+57h+var_A0], xmm1
0x180036010  lea     rdx, [rbp+57h+var_70]
0x180036014  cmp     [rbp+57h+var_58], 7
0x180036019  cmova   rdx, qword ptr [rbp+57h+var_70]
0x18003601e  mov     r8, [rbp+57h+var_60]
0x180036022  lea     rcx, [rbp+57h+var_B0]
0x180036026  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18003602b  nop
0x18003602c  mov     rdx, [rbx+8]
0x180036030  cmp     rdx, [rbx+10h]
0x180036034  jz      short loc_1800360A0
0x180036036  movzx   eax, word ptr [rbp+57h+var_D0]
0x18003603a  mov     [rdx], ax
0x18003603d  movsd   xmm0, qword ptr [rbp+57h+var_D0+2]
0x180036042  movsd   qword ptr [rdx+2], xmm0
0x180036047  mov     eax, dword ptr [rbp+57h+var_D0+0Ah]
0x18003604a  mov     [rdx+0Ah], eax
0x18003604d  movzx   eax, word ptr [rbp+57h+var_D0+0Eh]
0x180036051  mov     [rdx+0Eh], ax
0x180036055  mov     rax, qword ptr [rbp+57h+var_C0]
0x180036059  mov     [rdx+10h], rax
0x18003605d  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x180036061  mov     [rdx+18h], rax
0x180036065  movdqa  [rbp+57h+var_C0], xmm6
0x18003606a  mov     word ptr [rbp+57h+var_D0], r12w
0x18003606f  mov     rax, qword ptr [rbp+57h+var_B0]
0x180036073  mov     [rdx+20h], rax
0x180036077  mov     rax, qword ptr [rbp+57h+var_B0+8]
0x18003607b  mov     [rdx+28h], rax
0x18003607f  mov     rax, qword ptr [rbp+57h+var_A0]
0x180036083  mov     [rdx+30h], rax
0x180036087  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x18003608b  mov     [rdx+38h], rax
0x18003608f  movdqa  [rbp+57h+var_A0], xmm6
0x180036094  mov     word ptr [rbp+57h+var_B0], r12w
0x180036099  add     qword ptr [rbx+8], 40h ; '@'
0x18003609e  jmp     short loc_1800360AD
0x1800360a0  lea     r8, [rbp+57h+var_D0]
0x1800360a4  mov     rcx, rbx
0x1800360a7  call    ??$_Emplace_reallocate@UStoredTicket@@@?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@AEAAPEAUStoredTicket@@QEAU2@$$QEAU2@@Z; std::vector<StoredTicket>::_Emplace_reallocate<StoredTicket>(StoredTicket * const,StoredTicket &&)
0x1800360ac  nop
0x1800360ad  lea     rcx, [rbp+57h+var_B0]
0x1800360b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800360b6  lea     rcx, [rbp+57h+var_D0]
0x1800360ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800360bf  nop
0x1800360c0  lea     rcx, [rbp+57h+var_90]
0x1800360c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800360c9  nop
0x1800360ca  lea     rcx, [rbp+57h+var_70]
0x1800360ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800360d3  inc     rdi
0x1800360d6  cmp     rdi, r14
0x1800360d9  jb      loc_180035F26
0x1800360df  mov     rax, [rbx+8]
0x1800360e3  sub     rax, [rbx]
0x1800360e6  sar     rax, 6
0x1800360ea  mov     [rsp+120h+var_F0], rax
0x1800360ef  lea     rax, aCapturedDMsaTi; "Captured %d MSA tickets."
0x1800360f6  mov     [rsp+120h+var_F8], rax; unsigned __int16 *
0x1800360fb  mov     [rsp+120h+var_100], r13d; int
0x180036100  lea     r9, aGatherallaccou; "GatherAllAccountTickets"
0x180036107  mov     r8d, 24h ; '$'; unsigned int
0x18003610d  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180036114  lea     ecx, [r8-21h]; unsigned int
0x180036118  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18003611d  mov     rdx, r14; struct WinStoreAuth::TicketHolder **
0x180036120  lea     rcx, [rsp+120h+var_E0]; this
0x180036125  call    ?FreeTicketHolderArray@AuthenticationInternal@WinStoreAuth@@YAXPEAPEAUTicketHolder@2@_K@Z; WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(WinStoreAuth::TicketHolder * *,unsigned __int64)
0x18003612a  mov     rcx, [rbp+57h+var_50]
0x18003612e  xor     rcx, rsp; StackCookie
0x180036131  call    __security_check_cookie
0x180036136  lea     r11, [rsp+120h+var_30]
0x18003613e  mov     rbx, [r11+50h]
0x180036142  movaps  xmm6, xmmword ptr [r11-10h]
0x180036147  mov     rsp, r11
0x18003614a  pop     r15
0x18003614c  pop     r14
0x18003614e  pop     r13
0x180036150  pop     r12
0x180036152  pop     rdi
0x180036153  pop     rsi
0x180036154  pop     rbp
0x180036155  retn
0x180036156  mov     r9d, eax; char *
0x180036159  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180036160  mov     edx, 17h; void *
0x180036165  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
