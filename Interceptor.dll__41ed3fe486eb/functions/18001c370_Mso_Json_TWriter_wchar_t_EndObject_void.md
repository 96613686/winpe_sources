# Mso::Json::TWriter<wchar_t>::EndObject(void)

- ea: `0x18001c370`
- end: `0x18001c486`
- name: `?EndObject@?$TWriter@_W@Json@Mso@@UEAAXXZ`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001b8c0`

## callees

- `0x180012318`
- `0x18001b740`
- `0x18001c370`
- `0x18001d008`
- `0x18001d1d0`
- `0x18001d4c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001c3b9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001c3b9`

## pseudocode

```c
void __fastcall Mso::Json::TWriter<wchar_t>::EndObject(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  _QWORD *v4; // rdi
  unsigned __int64 v5; // rcx
  _QWORD *v6; // rax
  unsigned __int64 v7; // rcx

  if ( !*(_BYTE *)(a1 + 92) || *(_DWORD *)(a1 + 88) != 6 )
  {
    if ( !(unsigned __int8)Mso::Json::TWriter<wchar_t>::IsNameOrEndObjectAllowed() )
      CrashWithRecovery(0x1E561057u, 0);
    v2 = *(_QWORD *)(a1 + 80);
    if ( !v2 )
      _invoke_watson(0, 0, 0, 0, 0);
    v3 = v2 - 1;
    *(_QWORD *)(a1 + 80) = v3;
    if ( !v3 )
      *(_QWORD *)(a1 + 72) = 0;
    v4 = (_QWORD *)(a1 + 8);
    if ( *(_DWORD *)(a1 + 96) == 2 )
    {
      v5 = *(_QWORD *)(a1 + 24);
      if ( v5 >= *(_QWORD *)(a1 + 32) )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z((void *)(a1 + 8));
      }
      else
      {
        *(_QWORD *)(a1 + 24) = v5 + 1;
        v6 = (_QWORD *)(a1 + 8);
        if ( *(_QWORD *)(a1 + 32) > 7u )
          v6 = (_QWORD *)*v4;
        *(_DWORD *)((char *)v6 + 2 * v5) = 10;
      }
      Mso::Json::TWriter<wchar_t>::WriteIndent(a1);
    }
    v7 = *(_QWORD *)(a1 + 24);
    if ( v7 >= *(_QWORD *)(a1 + 32) )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z((void *)(a1 + 8));
    }
    else
    {
      *(_QWORD *)(a1 + 24) = v7 + 1;
      if ( *(_QWORD *)(a1 + 32) > 7u )
        v4 = (_QWORD *)*v4;
      *(_DWORD *)((char *)v4 + 2 * v7) = 125;
    }
    Mso::Json::TWriter<wchar_t>::OnStateChange((_QWORD *)a1, 4);
  }
}

```

## disassembly

```asm
0x18001c370  mov     [rsp+arg_8], rbx
0x18001c375  mov     [rsp+arg_10], rsi
0x18001c37a  push    rdi
0x18001c37b  sub     rsp, 30h
0x18001c37f  mov     rbx, rcx
0x18001c382  xor     esi, esi
0x18001c384  cmp     [rcx+5Ch], sil
0x18001c388  jz      short loc_18001C394
0x18001c38a  cmp     dword ptr [rcx+58h], 6
0x18001c38e  jz      loc_18001C469
0x18001c394  call    ?IsNameOrEndObjectAllowed@?$TWriter@_W@Json@Mso@@QEBA_NXZ; Mso::Json::TWriter<wchar_t>::IsNameOrEndObjectAllowed(void)
0x18001c399  test    al, al
0x18001c39b  jz      loc_18001C479
0x18001c3a1  mov     rax, [rbx+50h]
0x18001c3a5  test    rax, rax
0x18001c3a8  jnz     short loc_18001C3C0
0x18001c3aa  mov     [rsp+38h+Reserved], rsi; Reserved
0x18001c3af  xor     r9d, r9d; LineNo
0x18001c3b2  xor     r8d, r8d; FileName
0x18001c3b5  xor     edx, edx; FunctionName
0x18001c3b7  xor     ecx, ecx; Expression
0x18001c3b9  call    cs:__imp__invoke_watson
0x18001c3c0  sub     rax, 1
0x18001c3c4  mov     [rbx+50h], rax
0x18001c3c8  jnz     short loc_18001C3CE
0x18001c3ca  mov     [rbx+48h], rsi
0x18001c3ce  lea     rdi, [rbx+8]
0x18001c3d2  cmp     dword ptr [rbx+60h], 2
0x18001c3d6  jnz     short loc_18001C41F
0x18001c3d8  mov     rcx, [rdi+10h]
0x18001c3dc  cmp     rcx, [rdi+18h]
0x18001c3e0  jnb     short loc_18001C400
0x18001c3e2  lea     rax, [rcx+1]
0x18001c3e6  mov     [rdi+10h], rax
0x18001c3ea  mov     rax, rdi
0x18001c3ed  cmp     qword ptr [rdi+18h], 7
0x18001c3f2  jbe     short loc_18001C3F7
0x18001c3f4  mov     rax, [rdi]
0x18001c3f7  mov     dword ptr [rax+rcx*2], 0Ah
0x18001c3fe  jmp     short loc_18001C417
0x18001c400  mov     r9d, 0Ah
0x18001c406  mov     r8b, [rsp+38h+arg_0]
0x18001c40b  lea     edx, [r9-9]
0x18001c40f  mov     rcx, rdi; Src
0x18001c412  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001c417  mov     rcx, rbx
0x18001c41a  call    ?WriteIndent@?$TWriter@_W@Json@Mso@@AEAAXXZ; Mso::Json::TWriter<wchar_t>::WriteIndent(void)
0x18001c41f  mov     rcx, [rdi+10h]
0x18001c423  cmp     rcx, [rdi+18h]
0x18001c427  jnb     short loc_18001C444
0x18001c429  lea     rax, [rcx+1]
0x18001c42d  mov     [rdi+10h], rax
0x18001c431  cmp     qword ptr [rdi+18h], 7
0x18001c436  jbe     short loc_18001C43B
0x18001c438  mov     rdi, [rdi]
0x18001c43b  mov     dword ptr [rdi+rcx*2], 7Dh ; '}'
0x18001c442  jmp     short loc_18001C45B
0x18001c444  mov     r9d, 7Dh ; '}'
0x18001c44a  mov     r8b, [rsp+38h+arg_0]
0x18001c44f  lea     edx, [r9-7Ch]
0x18001c453  mov     rcx, rdi; Src
0x18001c456  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001c45b  mov     edx, 4
0x18001c460  mov     rcx, rbx
0x18001c463  call    ?OnStateChange@?$TWriter@_W@Json@Mso@@AEAAXW4Enum@ParseState@23@@Z; Mso::Json::TWriter<wchar_t>::OnStateChange(Mso::Json::ParseState::Enum)
0x18001c468  nop
0x18001c469  mov     rbx, [rsp+38h+arg_8]
0x18001c46e  mov     rsi, [rsp+38h+arg_10]
0x18001c473  add     rsp, 30h
0x18001c477  pop     rdi
0x18001c478  retn
0x18001c479  xor     edx, edx; struct CrashContext *
0x18001c47b  mov     ecx, 1E561057h; unsigned int
0x18001c480  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
