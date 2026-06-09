# ReplaceGatewayList(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,_SSTP_TENANT_GATEWAY_ENTRY *)

- ea: `0x180011700`
- end: `0x1800117f7`
- name: `?ReplaceGatewayList@@YAKV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800138c0`
- `0x180014490`

## callees

- `0x180008360`
- `0x180011700`
- `0x180012560`
- `0x1800127c0`
- `0x18001b880`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800117ca`
- `msvcrt!wcscpy_s` at `0x1800117ca`

## string_xrefs

- `0x180011765`: `ReplaceGatewayList: Failed to allocate memory for GATEWAY_CONFIG structure.`

## pseudocode

```c
__int64 __fastcall ReplaceGatewayList(_QWORD *a1, __int64 a2)
{
  unsigned __int64 v4; // rax
  unsigned int v5; // esi
  unsigned __int64 v6; // rcx
  unsigned int v7; // ebp
  __int64 v8; // rax

  v4 = *(_QWORD *)(a2 + 24);
  if ( v4
    || (v4 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 3)) == 0
    || (v4 = (unsigned __int64)MIDL_user_allocate(102 * ((__int64)(a1[1] - *a1) >> 3)), (*(_QWORD *)(a2 + 24) = v4) != 0) )
  {
    v5 = 0;
    v6 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 3);
    *(_DWORD *)(a2 + 16) = v6;
    if ( v4 )
    {
      v7 = 0;
      if ( (_DWORD)v6 )
      {
        do
        {
          v8 = std::vector<std::wstring>::at(a1, v7);
          if ( *(_QWORD *)(v8 + 24) >= 8u )
            v8 = *(_QWORD *)v8;
          wcscpy_s((wchar_t *)(*(_QWORD *)(a2 + 24) + 510LL * v7++), 0xFFu, (const wchar_t *)v8);
        }
        while ( v7 < *(_DWORD *)(a2 + 16) );
      }
    }
    *(_DWORD *)(a2 + 32) = 0;
  }
  else
  {
    v5 = 14;
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceError,
        L"ReplaceGatewayList: Failed to allocate memory for GATEWAY_CONFIG structure.");
  }
  std::vector<std::wstring>::_Tidy((__int64)a1);
  return v5;
}

```

## disassembly

```asm
0x180011700  mov     [rsp+arg_10], rbx
0x180011705  mov     [rsp+arg_18], rbp
0x18001170a  mov     [rsp+arg_0], rcx
0x18001170f  push    rsi
0x180011710  push    rdi
0x180011711  push    r14
0x180011713  sub     rsp, 20h
0x180011717  mov     rdi, rdx
0x18001171a  mov     rbx, rcx
0x18001171d  mov     rax, [rdx+18h]
0x180011721  mov     rbp, 0CCCCCCCCCCCCCCCDh
0x18001172b  test    rax, rax
0x18001172e  jnz     short loc_180011781
0x180011730  mov     rax, [rcx+8]
0x180011734  sub     rax, [rcx]
0x180011737  sar     rax, 3
0x18001173b  imul    rax, rbp
0x18001173f  test    rax, rax
0x180011742  jz      short loc_180011781
0x180011744  imul    rcx, rax, 1FEh; size
0x18001174b  call    MIDL_user_allocate
0x180011750  mov     [rdi+18h], rax
0x180011754  test    rax, rax
0x180011757  jnz     short loc_180011781
0x180011759  lea     esi, [rax+0Eh]
0x18001175c  test    cs:byte_18002D803, 8
0x180011763  jz      short loc_1800117DA
0x180011765  lea     r8, aReplacegateway; "ReplaceGatewayList: Failed to allocate "...
0x18001176c  lea     rdx, RasSSTPSvcTraceError
0x180011773  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001177a  call    McTemplateU0z_EventWriteTransfer
0x18001177f  jmp     short loc_1800117DA
0x180011781  xor     esi, esi
0x180011783  mov     rcx, [rbx+8]
0x180011787  sub     rcx, [rbx]
0x18001178a  sar     rcx, 3
0x18001178e  imul    rcx, rbp
0x180011792  mov     [rdi+10h], ecx
0x180011795  test    rax, rax
0x180011798  jz      short loc_1800117D7
0x18001179a  xor     ebp, ebp
0x18001179c  test    ecx, ecx
0x18001179e  jz      short loc_1800117D7
0x1800117a0  mov     r14d, ebp
0x1800117a3  mov     edx, ebp
0x1800117a5  mov     rcx, rbx
0x1800117a8  call    ?at@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::vector<std::wstring>::at(unsigned __int64)
0x1800117ad  cmp     qword ptr [rax+18h], 8
0x1800117b2  jb      short loc_1800117B7
0x1800117b4  mov     rax, [rax]
0x1800117b7  imul    rcx, r14, 1FEh
0x1800117be  add     rcx, [rdi+18h]; Destination
0x1800117c2  mov     r8, rax; Source
0x1800117c5  mov     edx, 0FFh; SizeInWords
0x1800117ca  call    cs:__imp_wcscpy_s
0x1800117d0  inc     ebp
0x1800117d2  cmp     ebp, [rdi+10h]
0x1800117d5  jb      short loc_1800117A0
0x1800117d7  mov     [rdi+20h], esi
0x1800117da  mov     rcx, rbx
0x1800117dd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800117e2  mov     eax, esi
0x1800117e4  mov     rbx, [rsp+38h+arg_10]
0x1800117e9  mov     rbp, [rsp+38h+arg_18]
0x1800117ee  add     rsp, 20h
0x1800117f2  pop     r14
0x1800117f4  pop     rdi
0x1800117f5  pop     rsi
0x1800117f6  retn
```
