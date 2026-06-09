# wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(ushort const *,ushort const *)

- ea: `0x1800174c0`
- end: `0x1800175da`
- name: `??$make_cloud_store_data_reference@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@YA?AU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z`
- size: `282`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012594`
- `0x180016ba4`
- `0x1800211b0`
- `0x18002547c`

## callees

- `0x1800174c0`
- `0x1800277f0`
- `0x18002a030`
- `0x18002f1ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800175af`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800175af`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180017599`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180017599`

## pseudocode

```c
__int64 __fastcall wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  GUID v8; // xmm0
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v12; // r8
  GUID pguid; // [rsp+40h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-78h] BYREF

  v8 = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(double *)&v8.Data1 = std::wstring::_Construct_empty(a1);
  *(GUID *)(v5 + 32) = v8;
  *(_QWORD *)(v5 + 48) = v6;
  *(_QWORD *)(v5 + 56) = v6;
  *(double *)&v8.Data1 = std::wstring::_Construct_empty(v5 + 32);
  if ( v7 )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v7 + 2 * v10) );
  }
  else
  {
    pguid = v8;
    CoCreateGuid(&pguid);
    StringFromGUID2(&pguid, sz, 40);
    v9 = -1;
    v12 = -1;
    do
      ++v12;
    while ( sz[v12] );
  }
  std::wstring::_Assign<unsigned short>(a1);
  if ( a3 )
  {
    do
      ++v9;
    while ( *(_WORD *)(a3 + 2 * v9) );
    std::wstring::_Assign<unsigned short>(a1 + 32);
  }
  return a1;
}

```

## disassembly

```asm
0x1800174c0  mov     [rsp+arg_18], rbx
0x1800174c5  push    rbp
0x1800174c6  push    rsi
0x1800174c7  push    rdi
0x1800174c8  sub     rsp, 0B0h
0x1800174cf  mov     rax, cs:__security_cookie
0x1800174d6  xor     rax, rsp
0x1800174d9  mov     [rsp+0C8h+var_28], rax
0x1800174e1  mov     rdi, r8
0x1800174e4  mov     rsi, rcx
0x1800174e7  mov     [rsp+0C8h+var_98], rcx
0x1800174ec  xor     r8d, r8d
0x1800174ef  mov     [rsp+0C8h+var_A8], r8d
0x1800174f4  xorps   xmm0, xmm0
0x1800174f7  movups  xmmword ptr [rcx], xmm0
0x1800174fa  mov     [rcx+10h], r8
0x1800174fe  mov     [rcx+18h], r8
0x180017502  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180017507  movups  xmmword ptr [rcx+20h], xmm0
0x18001750b  mov     [rcx+30h], r8
0x18001750f  mov     [rcx+38h], r8
0x180017513  add     rcx, 20h ; ' '
0x180017517  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001751c  mov     [rsp+0C8h+var_A8], 1
0x180017524  test    rdx, rdx
0x180017527  jz      short loc_18001758F
0x180017529  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180017530  mov     r8, rbx
0x180017533  inc     r8
0x180017536  cmp     word ptr [rdx+r8*2], 0
0x18001753c  jnz     short loc_180017533
0x18001753e  mov     rcx, rsi
0x180017541  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180017546  test    rdi, rdi
0x180017549  jz      short loc_180017569
0x18001754b  nop     dword ptr [rax+rax+00h]
0x180017550  inc     rbx
0x180017553  cmp     word ptr [rdi+rbx*2], 0
0x180017558  jnz     short loc_180017550
0x18001755a  mov     r8, rbx
0x18001755d  mov     rdx, rdi
0x180017560  lea     rcx, [rsi+20h]
0x180017564  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180017569  mov     rax, rsi
0x18001756c  mov     rcx, [rsp+0C8h+var_28]
0x180017574  xor     rcx, rsp; StackCookie
0x180017577  call    __security_check_cookie
0x18001757c  mov     rbx, [rsp+0C8h+arg_18]
0x180017584  add     rsp, 0B0h
0x18001758b  pop     rdi
0x18001758c  pop     rsi
0x18001758d  pop     rbp
0x18001758e  retn
0x18001758f  movups  xmmword ptr [rsp+0C8h+pguid.Data1], xmm0
0x180017594  lea     rcx, [rsp+0C8h+pguid]; pguid
0x180017599  call    cs:__imp_CoCreateGuid
0x18001759f  mov     r8d, 28h ; '('; cchMax
0x1800175a5  lea     rdx, [rsp+0C8h+sz]; lpsz
0x1800175aa  lea     rcx, [rsp+0C8h+pguid]; rguid
0x1800175af  call    cs:__imp_StringFromGUID2
0x1800175b5  lea     rax, [rsp+0C8h+sz]
0x1800175ba  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800175c1  mov     r8, rbx
0x1800175c4  inc     r8
0x1800175c7  cmp     word ptr [rax+r8*2], 0
0x1800175cd  jnz     short loc_1800175C4
0x1800175cf  lea     rdx, [rsp+0C8h+sz]
0x1800175d4  jmp     loc_18001753E
```
