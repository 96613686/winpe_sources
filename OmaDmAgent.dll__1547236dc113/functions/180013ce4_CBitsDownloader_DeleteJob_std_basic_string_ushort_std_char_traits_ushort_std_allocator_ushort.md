# CBitsDownloader::DeleteJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180013ce4`
- end: `0x180013e06`
- name: `?DeleteJob@CBitsDownloader@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000c734`

## callees

- `0x1800062ac`
- `0x18000702c`
- `0x180007240`
- `0x18000a2c0`
- `0x180013ce4`
- `0x18001b6bc`
- `0x18001c358`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBitsDownloader::DeleteJob(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rdx
  int v6; // ebx
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rdx
  _BYTE v10[32]; // [rsp+28h] [rbp-31h] BYREF
  __int64 v11; // [rsp+48h] [rbp-11h]
  void **v12; // [rsp+50h] [rbp-9h] BYREF
  char v13; // [rsp+58h] [rbp-1h]
  _WORD v14[8]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  struct _GUID v17; // [rsp+88h] [rbp+2Fh] BYREF

  v11 = a2;
  v17 = 0;
  v12 = &CDownloadService::`vftable';
  v16 = 7;
  v15 = 0;
  v14[0] = 0;
  v13 = 0;
  if ( *(_BYTE *)(a1 + 24)
    && (v3 = *(_DWORD *)(a1 + 64),
        v4 = std::wstring::wstring(v10, a1 + 32),
        v6 = CDownloadService::SetImpersonation(&v12, v4, v3),
        v6 < 0) )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_14cd5ff906c03b036d9c08ef2443ee7b_Traceguids,
        (unsigned int)v6);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 24) < 8u )
      v7 = (const unsigned __int16 *)a2;
    else
      v7 = *(const unsigned __int16 **)a2;
    v6 = ConvertStringToGuid(v7, &v17);
    if ( v6 >= 0 )
      v6 = CDownloadService::CancelJob((CDownloadService *)&v12, &v17);
  }
  v12 = &CDownloadService::`vftable';
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v14, v5, 0);
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(a2, v8, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013ce4  mov     [rsp-8+arg_10], rbx
0x180013ce9  push    rbp
0x180013cea  push    rdi
0x180013ceb  push    r14
0x180013ced  lea     rbp, [rsp-47h]
0x180013cf2  sub     rsp, 0A0h
0x180013cf9  mov     rax, cs:__security_cookie
0x180013d00  xor     rax, rsp
0x180013d03  mov     [rbp+57h+var_18], rax
0x180013d07  mov     rdi, rdx
0x180013d0a  mov     [rbp+57h+var_68], rdx
0x180013d0e  xorps   xmm0, xmm0
0x180013d11  movups  xmmword ptr [rbp+57h+var_28.Data1], xmm0
0x180013d15  lea     r14, ??_7CDownloadService@@6B@; const CDownloadService::`vftable'
0x180013d1c  mov     [rbp+57h+var_60], r14
0x180013d20  mov     [rbp+57h+var_38], 7
0x180013d28  mov     [rbp+57h+var_40], 0
0x180013d30  xor     eax, eax
0x180013d32  mov     [rbp+57h+var_50], ax
0x180013d36  mov     [rbp+57h+var_58], al
0x180013d39  cmp     [rcx+18h], al
0x180013d3c  jz      short loc_180013D96
0x180013d3e  mov     ebx, [rcx+40h]
0x180013d41  lea     rdx, [rcx+20h]
0x180013d45  lea     rcx, [rbp+57h+var_88]
0x180013d49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180013d4e  mov     r8d, ebx
0x180013d51  mov     rdx, rax
0x180013d54  lea     rcx, [rbp+57h+var_60]
0x180013d58  call    ?SetImpersonation@CDownloadService@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; CDownloadService::SetImpersonation(std::wstring,ulong)
0x180013d5d  mov     ebx, eax
0x180013d5f  test    eax, eax
0x180013d61  jns     short loc_180013D96
0x180013d63  lea     rax, WPP_GLOBAL_Control
0x180013d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d71  cmp     rcx, rax
0x180013d74  jz      short loc_180013DC3
0x180013d76  test    byte ptr [rcx+1Ch], 4
0x180013d7a  jz      short loc_180013DC3
0x180013d7c  mov     edx, 12h
0x180013d81  mov     r9d, ebx
0x180013d84  lea     r8, WPP_14cd5ff906c03b036d9c08ef2443ee7b_Traceguids
0x180013d8b  mov     rcx, [rcx+10h]
0x180013d8f  call    WPP_SF_d
0x180013d94  jmp     short loc_180013DC3
0x180013d96  cmp     qword ptr [rdi+18h], 8
0x180013d9b  jb      short loc_180013DA2
0x180013d9d  mov     rcx, [rdi]
0x180013da0  jmp     short loc_180013DA5
0x180013da2  mov     rcx, rdi; unsigned __int16 *
0x180013da5  lea     rdx, [rbp+57h+var_28]; struct _GUID *
0x180013da9  call    ?ConvertStringToGuid@@YAJPEBGPEAU_GUID@@@Z; ConvertStringToGuid(ushort const *,_GUID *)
0x180013dae  mov     ebx, eax
0x180013db0  test    eax, eax
0x180013db2  js      short loc_180013DC3
0x180013db4  lea     rdx, [rbp+57h+var_28]; struct _GUID *
0x180013db8  lea     rcx, [rbp+57h+var_60]; this
0x180013dbc  call    ?CancelJob@CDownloadService@@QEAAJAEBU_GUID@@@Z; CDownloadService::CancelJob(_GUID const &)
0x180013dc1  mov     ebx, eax
0x180013dc3  mov     [rbp+57h+var_60], r14
0x180013dc7  xor     r8d, r8d
0x180013dca  mov     dl, 1
0x180013dcc  lea     rcx, [rbp+57h+var_50]
0x180013dd0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013dd5  nop
0x180013dd6  xor     r8d, r8d
0x180013dd9  mov     dl, 1
0x180013ddb  mov     rcx, rdi
0x180013dde  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013de3  mov     eax, ebx
0x180013de5  mov     rcx, [rbp+57h+var_18]
0x180013de9  xor     rcx, rsp; StackCookie
0x180013dec  call    __security_check_cookie
0x180013df1  mov     rbx, [rsp+0B0h+arg_10]
0x180013df9  add     rsp, 0A0h
0x180013e00  pop     r14
0x180013e02  pop     rdi
0x180013e03  pop     rbp
0x180013e04  retn
```
