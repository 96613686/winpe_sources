# wil::make_cloud_store_data_reference<Windows::Data::Nlm::NlmSignature>(ushort const *,ushort const *)

- ea: `0x1800168c4`
- end: `0x1800169b4`
- name: `??$make_cloud_store_data_reference@UNlmSignature@Nlm@Data@Windows@@@wil@@YA?AU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z`
- size: `240`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800144c0`
- `0x180015624`

## callees

- `0x1800168c4`
- `0x1800277c0`
- `0x18002a030`
- `0x18002f1ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001698d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001698d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180016977`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180016977`

## pseudocode

```c
__int64 __fastcall wil::make_cloud_store_data_reference<Windows::Data::Nlm::NlmSignature>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v10; // r8
  GUID pguid; // [rsp+40h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-88h] BYREF

  std::wstring::wstring(a1);
  std::wstring::wstring(v5 + 32);
  if ( v6 )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
  }
  else
  {
    pguid = 0;
    CoCreateGuid(&pguid);
    StringFromGUID2(&pguid, sz, 40);
    v7 = -1;
    v10 = -1;
    do
      ++v10;
    while ( sz[v10] );
  }
  std::wstring::_Assign<unsigned short>(a1);
  if ( a3 )
  {
    do
      ++v7;
    while ( *(_WORD *)(a3 + 2 * v7) );
    std::wstring::_Assign<unsigned short>(a1 + 32);
  }
  return a1;
}

```

## disassembly

```asm
0x1800168c4  push    rbx
0x1800168c6  push    rbp
0x1800168c7  push    rsi
0x1800168c8  push    rdi
0x1800168c9  push    r14
0x1800168cb  sub     rsp, 0B0h
0x1800168d2  mov     rax, cs:__security_cookie
0x1800168d9  xor     rax, rsp
0x1800168dc  mov     [rsp+0D8h+var_38], rax
0x1800168e4  mov     rsi, r8
0x1800168e7  mov     rdi, rcx
0x1800168ea  mov     [rsp+0D8h+var_A8], rcx
0x1800168ef  xor     r14d, r14d
0x1800168f2  mov     [rsp+0D8h+var_B8], r14d
0x1800168f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800168fc  add     rcx, 20h ; ' '
0x180016900  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016905  mov     [rsp+0D8h+var_B8], 1
0x18001690d  test    rdx, rdx
0x180016910  jz      short loc_18001696A
0x180016912  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016916  mov     r8, rbx
0x180016919  inc     r8
0x18001691c  cmp     [rdx+r8*2], r14w
0x180016921  jnz     short loc_180016919
0x180016923  mov     rcx, rdi
0x180016926  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001692b  test    rsi, rsi
0x18001692e  jz      short loc_180016949
0x180016930  inc     rbx
0x180016933  cmp     [rsi+rbx*2], r14w
0x180016938  jnz     short loc_180016930
0x18001693a  mov     r8, rbx
0x18001693d  mov     rdx, rsi
0x180016940  lea     rcx, [rdi+20h]
0x180016944  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180016949  mov     rax, rdi
0x18001694c  mov     rcx, [rsp+0D8h+var_38]
0x180016954  xor     rcx, rsp; StackCookie
0x180016957  call    __security_check_cookie
0x18001695c  add     rsp, 0B0h
0x180016963  pop     r14
0x180016965  pop     rdi
0x180016966  pop     rsi
0x180016967  pop     rbp
0x180016968  pop     rbx
0x180016969  retn
0x18001696a  xorps   xmm0, xmm0
0x18001696d  movups  xmmword ptr [rsp+0D8h+pguid.Data1], xmm0
0x180016972  lea     rcx, [rsp+0D8h+pguid]; pguid
0x180016977  call    cs:__imp_CoCreateGuid
0x18001697d  mov     r8d, 28h ; '('; cchMax
0x180016983  lea     rdx, [rsp+0D8h+sz]; lpsz
0x180016988  lea     rcx, [rsp+0D8h+pguid]; rguid
0x18001698d  call    cs:__imp_StringFromGUID2
0x180016993  lea     rax, [rsp+0D8h+sz]
0x180016998  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001699c  mov     r8, rbx
0x18001699f  inc     r8
0x1800169a2  cmp     [rax+r8*2], r14w
0x1800169a7  jnz     short loc_18001699F
0x1800169a9  lea     rdx, [rsp+0D8h+sz]
0x1800169ae  jmp     loc_180016923
```
