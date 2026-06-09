# _lambda_f8e6df8a116c6a42d7f973bedb0e6e37_::operator()

- ea: `0x180036d48`
- end: `0x180037090`
- name: `_lambda_f8e6df8a116c6a42d7f973bedb0e6e37_::operator()`
- size: `840`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034eb8`

## callees

- `0x180001dd0`
- `0x180002f4d`
- `0x1800039c0`
- `0x18000e0c0`
- `0x180019d20`
- `0x180023d80`
- `0x18003498c`
- `0x180035188`
- `0x1800358d0`
- `0x180036d48`
- `0x18003715c`
- `0x18003a1f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036f4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall lambda_f8e6df8a116c6a42d7f973bedb0e6e37_::operator()(__int64 a1)
{
  int v2; // ecx
  int *v3; // rdx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  const struct BthAvrcpMediaController::BthAvMediaTrackAttribute *v8; // r14
  const struct BthAvrcpMediaController::BthAvMediaTrackAttribute *v9; // r15
  unsigned __int64 v10; // rdx
  unsigned __int8 v11; // si
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // r8
  PVOID *v17; // r10
  void *v18; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // [rsp+20h] [rbp-49h]
  _DWORD v24[2]; // [rsp+30h] [rbp-39h] BYREF
  const WCHAR *v25; // [rsp+38h] [rbp-31h]
  _BYTE v26[40]; // [rsp+40h] [rbp-29h] BYREF
  int v27; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v28[32]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( !**(_QWORD **)a1 || !**(_QWORD **)(a1 + 8) )
  {
    v21 = wil::verify_hresult<long>(2147500035LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\tg\\npsmmediacontroller\\lib\\npsmmediacontroller.cpp",
      (const char *)v21,
      v23);
  }
  v2 = **(_DWORD **)(a1 + 16);
  if ( v2 && !**(_QWORD **)(a1 + 24) )
  {
    v22 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\tg\\npsmmediacontroller\\lib\\npsmmediacontroller.cpp",
      (const char *)v22,
      v23);
  }
  v3 = *(int **)(a1 + 32);
  v4 = *v3;
  if ( *v3 )
  {
    if ( v2 )
      v4 = v2;
    *v3 = v4;
    v7 = *(_QWORD *)(a1 + 48);
    v8 = *(const struct BthAvrcpMediaController::BthAvMediaTrackAttribute **)(v7 + 192);
    v9 = *(const struct BthAvrcpMediaController::BthAvMediaTrackAttribute **)(v7 + 200);
    if ( v8 != v9 )
    {
      while ( 1 )
      {
        BthAvrcpMediaController::BthAvMediaTrackAttribute::BthAvMediaTrackAttribute(
          (BthAvrcpMediaController::BthAvMediaTrackAttribute *)&v27,
          v8);
        v10 = **(unsigned int **)(a1 + 32);
        if ( (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL) - **(_QWORD **)(a1 + 40)) >> 4 > v10 )
          break;
        if ( **(_DWORD **)(a1 + 16) )
        {
          v11 = 0;
          if ( (_DWORD)v10 )
          {
            do
            {
              if ( v27 == *(_DWORD *)(**(_QWORD **)(a1 + 24) + 4LL * v11) )
              {
                v12 = *(_QWORD *)(a1 + 48);
                v13 = BthAvrcpMediaController::BthAvMediaTrackAttribute::BthAvMediaTrackAttribute(
                        (BthAvrcpMediaController::BthAvMediaTrackAttribute *)v26,
                        (const struct BthAvrcpMediaController::BthAvMediaTrackAttribute *)&v27);
                BthAvrcpMediaController::NpsmMediaController::AddAttributeToList(v12, *(_QWORD *)(a1 + 40), v13);
              }
              ++v11;
            }
            while ( (unsigned int)v11 < **(_DWORD **)(a1 + 32) );
          }
        }
        else
        {
          v14 = *(_QWORD *)(a1 + 48);
          v15 = BthAvrcpMediaController::BthAvMediaTrackAttribute::BthAvMediaTrackAttribute(
                  (BthAvrcpMediaController::BthAvMediaTrackAttribute *)v26,
                  (const struct BthAvrcpMediaController::BthAvMediaTrackAttribute *)&v27);
          BthAvrcpMediaController::NpsmMediaController::AddAttributeToList(v14, *(_QWORD *)(a1 + 40), v15);
        }
        std::wstring::_Tidy_deallocate(v28);
        v8 = (const struct BthAvrcpMediaController::BthAvMediaTrackAttribute *)((char *)v8 + 40);
        if ( v8 == v9 )
          goto LABEL_27;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids);
      }
      std::wstring::_Tidy_deallocate(v28);
    }
  }
  else
  {
    v24[0] = 1;
    v24[1] = 0x10000;
    v25 = &String1;
    v5 = *(_QWORD *)(a1 + 40);
    v6 = *(_QWORD *)(v5 + 8);
    if ( v6 == *(_QWORD *)(v5 + 16) )
    {
      std::vector<BthAvMediaItemAttribute>::_Emplace_reallocate<BthAvMediaItemAttribute const &>(v5, v6, v24);
    }
    else
    {
      *(_DWORD *)v6 = 1;
      *(_DWORD *)(v6 + 4) = 0x10000;
      *(_QWORD *)(v6 + 8) = &String1;
      *(_QWORD *)(v5 + 8) += 16LL;
    }
  }
LABEL_27:
  ***(_DWORD ***)(a1 + 8) = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL) - **(_QWORD **)(a1 + 40)) >> 4;
  ***(_QWORD ***)a1 = CoTaskMemAlloc(16LL * ***(unsigned int ***)(a1 + 8));
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v23 = ***(_DWORD ***)(a1 + 8);
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v16, **(unsigned int **)(a1 + 16));
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  v18 = ***(void ****)a1;
  if ( !v18 )
  {
    if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 && *((_BYTE *)v17 + 25) >= 2u )
    {
      v23 = 0;
      WPP_SF_dq(v17[2], 21, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, ***(unsigned int ***)(a1 + 8));
    }
    v20 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\tg\\npsmmediacontroller\\lib\\npsmmediacontroller.cpp",
      (const char *)v20,
      v23);
  }
  return memcpy_0(
           v18,
           **(const void ***)(a1 + 40),
           (*(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL) - **(_QWORD **)(a1 + 40)) & 0xFFFFFFFFFFFFFFF0uLL);
}

```

## disassembly

```asm
0x180036d48  mov     [rsp-8+arg_8], rbx
0x180036d4d  mov     [rsp-8+arg_10], rsi
0x180036d52  push    rbp
0x180036d53  push    rdi
0x180036d54  push    r13
0x180036d56  push    r14
0x180036d58  push    r15
0x180036d5a  lea     rbp, [rsp-37h]
0x180036d5f  sub     rsp, 0A0h
0x180036d66  mov     rax, cs:__security_cookie
0x180036d6d  xor     rax, rsp
0x180036d70  mov     [rbp+57h+var_30], rax
0x180036d74  mov     rdi, rcx
0x180036d77  mov     rax, [rcx]
0x180036d7a  cmp     qword ptr [rax], 0
0x180036d7e  jz      loc_18003704A
0x180036d84  mov     rax, [rcx+8]
0x180036d88  cmp     qword ptr [rax], 0
0x180036d8c  jz      loc_18003704A
0x180036d92  mov     rax, [rcx+10h]
0x180036d96  mov     ecx, [rax]
0x180036d98  test    ecx, ecx
0x180036d9a  jz      short loc_180036DAA
0x180036d9c  mov     rax, [rdi+18h]
0x180036da0  cmp     qword ptr [rax], 0
0x180036da4  jz      loc_18003706D
0x180036daa  mov     rdx, [rdi+20h]
0x180036dae  mov     eax, [rdx]
0x180036db0  mov     r13d, 1
0x180036db6  lea     rbx, WPP_GLOBAL_Control
0x180036dbd  test    eax, eax
0x180036dbf  jnz     short loc_180036E0B
0x180036dc1  mov     [rbp+57h+var_90], r13d
0x180036dc5  mov     [rbp+57h+var_8C], 10000h
0x180036dcc  lea     r8, String1
0x180036dd3  mov     [rbp+57h+var_88], r8
0x180036dd7  mov     rcx, [rdi+28h]
0x180036ddb  mov     rdx, [rcx+8]
0x180036ddf  cmp     rdx, [rcx+10h]
0x180036de3  jz      short loc_180036DFD
0x180036de5  mov     [rdx], r13d
0x180036de8  mov     dword ptr [rdx+4], 10000h
0x180036def  mov     [rdx+8], r8
0x180036df3  add     qword ptr [rcx+8], 10h
0x180036df8  jmp     loc_180036F2A
0x180036dfd  lea     r8, [rbp+57h+var_90]
0x180036e01  call    ??$_Emplace_reallocate@AEBUBthAvMediaItemAttribute@@@?$vector@UBthAvMediaItemAttribute@@V?$allocator@UBthAvMediaItemAttribute@@@std@@@std@@AEAAPEAUBthAvMediaItemAttribute@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaItemAttribute>::_Emplace_reallocate<BthAvMediaItemAttribute const &>(BthAvMediaItemAttribute * const,BthAvMediaItemAttribute const &)
0x180036e06  jmp     loc_180036F2A
0x180036e0b  test    ecx, ecx
0x180036e0d  cmovnz  eax, ecx
0x180036e10  mov     [rdx], eax
0x180036e12  mov     rax, [rdi+30h]
0x180036e16  mov     r14, [rax+0C0h]
0x180036e1d  mov     r15, [rax+0C8h]
0x180036e24  cmp     r14, r15
0x180036e27  jz      loc_180036F2A
0x180036e2d  mov     rdx, r14; struct BthAvrcpMediaController::BthAvMediaTrackAttribute *
0x180036e30  lea     rcx, [rbp+57h+var_58]; this
0x180036e34  call    ??0BthAvMediaTrackAttribute@BthAvrcpMediaController@@QEAA@AEBU01@@Z; BthAvrcpMediaController::BthAvMediaTrackAttribute::BthAvMediaTrackAttribute(BthAvrcpMediaController::BthAvMediaTrackAttribute const &)
0x180036e39  nop
0x180036e3a  mov     rcx, [rdi+28h]
0x180036e3e  mov     rax, [rdi+20h]
0x180036e42  mov     edx, [rax]
0x180036e44  mov     rax, [rcx+8]
0x180036e48  sub     rax, [rcx]
0x180036e4b  sar     rax, 4
0x180036e4f  cmp     rax, rdx
0x180036e52  ja      loc_180036EEC
0x180036e58  mov     rax, [rdi+10h]
0x180036e5c  cmp     dword ptr [rax], 0
0x180036e5f  jz      short loc_180036EAC
0x180036e61  xor     sil, sil
0x180036e64  test    edx, edx
0x180036e66  jz      short loc_180036ECD
0x180036e68  movzx   edx, sil
0x180036e6c  mov     rax, [rdi+18h]
0x180036e70  mov     rcx, [rax]
0x180036e73  mov     eax, [rcx+rdx*4]
0x180036e76  cmp     [rbp+57h+var_58], eax
0x180036e79  jnz     short loc_180036E9B
0x180036e7b  mov     rbx, [rdi+30h]
0x180036e7f  lea     rdx, [rbp+57h+var_58]; struct BthAvrcpMediaController::BthAvMediaTrackAttribute *
0x180036e83  lea     rcx, [rbp+57h+var_80]; this
0x180036e87  call    ??0BthAvMediaTrackAttribute@BthAvrcpMediaController@@QEAA@AEBU01@@Z; BthAvrcpMediaController::BthAvMediaTrackAttribute::BthAvMediaTrackAttribute(BthAvrcpMediaController::BthAvMediaTrackAttribute const &)
0x180036e8c  mov     r8, rax
0x180036e8f  mov     rdx, [rdi+28h]
0x180036e93  mov     rcx, rbx
0x180036e96  call    ?AddAttributeToList@NpsmMediaController@BthAvrcpMediaController@@AEAAXAEAV?$vector@UBthAvMediaItemAttribute@@V?$allocator@UBthAvMediaItemAttribute@@@std@@@std@@UBthAvMediaTrackAttribute@2@@Z; BthAvrcpMediaController::NpsmMediaController::AddAttributeToList(std::vector<BthAvMediaItemAttribute> &,BthAvrcpMediaController::BthAvMediaTrackAttribute)
0x180036e9b  add     sil, r13b
0x180036e9e  mov     rcx, [rdi+20h]
0x180036ea2  movzx   eax, sil
0x180036ea6  cmp     eax, [rcx]
0x180036ea8  jb      short loc_180036E68
0x180036eaa  jmp     short loc_180036ECD
0x180036eac  mov     rbx, [rdi+30h]
0x180036eb0  lea     rdx, [rbp+57h+var_58]; struct BthAvrcpMediaController::BthAvMediaTrackAttribute *
0x180036eb4  lea     rcx, [rbp+57h+var_80]; this
0x180036eb8  call    ??0BthAvMediaTrackAttribute@BthAvrcpMediaController@@QEAA@AEBU01@@Z; BthAvrcpMediaController::BthAvMediaTrackAttribute::BthAvMediaTrackAttribute(BthAvrcpMediaController::BthAvMediaTrackAttribute const &)
0x180036ebd  mov     r8, rax
0x180036ec0  mov     rdx, [rdi+28h]
0x180036ec4  mov     rcx, rbx
0x180036ec7  call    ?AddAttributeToList@NpsmMediaController@BthAvrcpMediaController@@AEAAXAEAV?$vector@UBthAvMediaItemAttribute@@V?$allocator@UBthAvMediaItemAttribute@@@std@@@std@@UBthAvMediaTrackAttribute@2@@Z; BthAvrcpMediaController::NpsmMediaController::AddAttributeToList(std::vector<BthAvMediaItemAttribute> &,BthAvrcpMediaController::BthAvMediaTrackAttribute)
0x180036ecc  nop
0x180036ecd  lea     rcx, [rbp+57h+var_50]
0x180036ed1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036ed6  add     r14, 28h ; '('
0x180036eda  cmp     r14, r15
0x180036edd  jnz     loc_180036E2D
0x180036ee3  lea     rbx, WPP_GLOBAL_Control
0x180036eea  jmp     short loc_180036F2A
0x180036eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ef3  lea     rbx, WPP_GLOBAL_Control
0x180036efa  cmp     rcx, rbx
0x180036efd  jz      short loc_180036F21
0x180036eff  test    [rcx+1Ch], r13b
0x180036f03  jz      short loc_180036F21
0x180036f05  cmp     byte ptr [rcx+19h], 3
0x180036f09  jb      short loc_180036F21
0x180036f0b  mov     edx, 13h
0x180036f10  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180036f17  mov     rcx, [rcx+10h]
0x180036f1b  call    WPP_SF_
0x180036f20  nop
0x180036f21  lea     rcx, [rbp+57h+var_50]
0x180036f25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036f2a  mov     rax, [rdi+28h]
0x180036f2e  mov     rdx, [rax+8]
0x180036f32  sub     rdx, [rax]
0x180036f35  sar     rdx, 4
0x180036f39  mov     rax, [rdi+8]
0x180036f3d  mov     rcx, [rax]
0x180036f40  mov     [rcx], edx
0x180036f42  mov     rax, [rdi+8]
0x180036f46  mov     rcx, [rax]
0x180036f49  mov     ecx, [rcx]
0x180036f4b  shl     rcx, 4; cb
0x180036f4f  call    cs:__imp_CoTaskMemAlloc
0x180036f55  mov     rcx, [rdi]
0x180036f58  mov     rdx, [rcx]
0x180036f5b  mov     [rdx], rax
0x180036f5e  mov     r10, cs:WPP_GLOBAL_Control
0x180036f65  cmp     r10, rbx
0x180036f68  jz      short loc_180036FA0
0x180036f6a  test    [r10+1Ch], r13b
0x180036f6e  jz      short loc_180036FA0
0x180036f70  cmp     byte ptr [r10+19h], 5
0x180036f75  jb      short loc_180036FA0
0x180036f77  mov     rax, [rdi+8]
0x180036f7b  mov     rax, [rax]
0x180036f7e  mov     r9, [rdi+10h]
0x180036f82  mov     edx, 14h
0x180036f87  mov     eax, [rax]
0x180036f89  mov     [rsp+0C0h+var_A0], eax
0x180036f8d  mov     r9d, [r9]
0x180036f90  mov     rcx, [r10+10h]
0x180036f94  call    WPP_SF_dd
0x180036f99  mov     r10, cs:WPP_GLOBAL_Control
0x180036fa0  mov     rax, [rdi]
0x180036fa3  mov     rcx, [rax]
0x180036fa6  mov     rcx, [rcx]; void *
0x180036fa9  test    rcx, rcx
0x180036fac  jz      short loc_180036FED
0x180036fae  mov     rax, [rdi+28h]
0x180036fb2  mov     r8, [rax+8]
0x180036fb6  sub     r8, [rax]
0x180036fb9  and     r8, 0FFFFFFFFFFFFFFF0h; Size
0x180036fbd  mov     rdx, [rax]; Src
0x180036fc0  call    memcpy_0
0x180036fc5  mov     rcx, [rbp+57h+var_30]
0x180036fc9  xor     rcx, rsp; StackCookie
0x180036fcc  call    __security_check_cookie
0x180036fd1  lea     r11, [rsp+0C0h+var_20]
0x180036fd9  mov     rbx, [r11+38h]
0x180036fdd  mov     rsi, [r11+40h]
0x180036fe1  mov     rsp, r11
0x180036fe4  pop     r15
0x180036fe6  pop     r14
0x180036fe8  pop     r13
0x180036fea  pop     rdi
0x180036feb  pop     rbp
0x180036fec  retn
0x180036fed  cmp     r10, rbx
0x180036ff0  jz      short loc_180037027
0x180036ff2  test    [r10+1Ch], r13b
0x180036ff6  jz      short loc_180037027
0x180036ff8  cmp     byte ptr [r10+19h], 2
0x180036ffd  jb      short loc_180037027
0x180036fff  mov     rax, [rdi+8]
0x180037003  mov     r9, [rax]
0x180037006  mov     edx, 15h
0x18003700b  mov     qword ptr [rsp+0C0h+var_A0], 0; int
0x180037014  mov     r9d, [r9]
0x180037017  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x18003701e  mov     rcx, [r10+10h]
0x180037022  call    WPP_SF_dq
0x180037027  mov     ecx, 8007000Eh
0x18003702c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180037031  mov     r9d, eax; char *
0x180037034  mov     rcx, [rbp+5Fh]; this
0x180037038  lea     r8, aOnecoreDrivers_39; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18003703f  mov     edx, 0A5h; void *
0x180037044  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003704a  mov     ecx, 80004003h
0x18003704f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180037054  mov     r9d, eax; char *
0x180037057  mov     rcx, [rbp+5Fh]; this
0x18003705b  lea     r8, aOnecoreDrivers_39; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180037062  mov     edx, 72h ; 'r'; void *
0x180037067  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003706d  mov     ecx, 80070057h
0x180037072  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180037077  mov     r9d, eax; char *
0x18003707a  mov     rcx, [rbp+5Fh]; this
0x18003707e  lea     r8, aOnecoreDrivers_39; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180037085  mov     edx, 77h ; 'w'; void *
0x18003708a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
