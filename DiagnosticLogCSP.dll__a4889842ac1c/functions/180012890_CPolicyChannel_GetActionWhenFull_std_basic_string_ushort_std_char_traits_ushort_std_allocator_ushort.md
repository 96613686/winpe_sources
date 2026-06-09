# CPolicyChannel::GetActionWhenFull(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012890`
- end: `0x180012a1c`
- name: `?GetActionWhenFull@CPolicyChannel@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18000c870`

## callees

- `0x180001104`
- `0x180001b60`
- `0x180002d01`
- `0x1800113f8`
- `0x180012140`
- `0x180012890`

## string_xrefs

- `0x180012981`: `Overwrite`
- `0x180012996`: `Overwrite`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::GetActionWhenFull(HKEY *a1, __int64 a2)
{
  unsigned int v4; // r14d
  unsigned __int64 v5; // rax
  _WORD *v6; // rbx
  _WORD *v7; // rbx
  _WORD *v8; // rbx
  unsigned int v10; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-54h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+38h] [rbp-50h] BYREF
  unsigned int *v13; // [rsp+58h] [rbp-30h]
  __int64 v14; // [rsp+60h] [rbp-28h]

  v4 = 0;
  v11 = 0;
  v10 = 0;
  CRegUtils::RegReadDWORDValueNoThrow(*a1, L"Retention", &v11);
  CRegUtils::RegReadDWORDValueNoThrow(*a1, L"AutoBackupLogFiles", &v10);
  v5 = *(_QWORD *)(a2 + 24);
  if ( v11 )
  {
    if ( v10 )
    {
      if ( v5 >= 7 )
      {
        if ( v5 <= 7 )
          v6 = (_WORD *)a2;
        else
          v6 = *(_WORD **)a2;
        *(_QWORD *)(a2 + 16) = 7;
        memmove_0(v6, L"Archive", 0xEu);
        v6[7] = 0;
        goto LABEL_13;
      }
    }
    else if ( v5 >= 8 )
    {
      v7 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 8;
      memmove_0(v7, L"Truncate", 0x10u);
      v7[8] = 0;
      goto LABEL_13;
    }
    try
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a2);
    }
    catch ( std::exception )
    {
      v4 = -2147467259;
    }
  }
  else if ( v5 < 9 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a2);
  }
  else
  {
    v8 = *(_WORD **)a2;
    *(_QWORD *)(a2 + 16) = 9;
    memmove_0(v8, L"Overwrite", 0x12u);
    v8[9] = 0;
  }
LABEL_13:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v10 = v4;
    v13 = &v10;
    v14 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180048E90, (unsigned __int8 *)byte_18003FEF5, 0, 0, 3u, &v12);
  }
  return v4;
}

```

## disassembly

```asm
0x180012890  mov     [rsp+arg_10], rbx
0x180012895  push    rsi
0x180012896  push    rdi
0x180012897  push    r14
0x180012899  sub     rsp, 70h
0x18001289d  mov     rax, cs:__security_cookie
0x1800128a4  xor     rax, rsp
0x1800128a7  mov     [rsp+88h+var_20], rax
0x1800128ac  mov     rdi, rdx
0x1800128af  mov     rbx, rcx
0x1800128b2  xor     esi, esi
0x1800128b4  mov     r14d, esi
0x1800128b7  mov     [rsp+88h+var_54], esi
0x1800128bb  mov     [rsp+88h+var_58], esi
0x1800128bf  lea     r8, [rsp+88h+var_54]; unsigned int *
0x1800128c4  lea     rdx, aRetention; "Retention"
0x1800128cb  mov     rcx, [rcx]; HKEY
0x1800128ce  call    ?RegReadDWORDValueNoThrow@CRegUtils@@SAJPEAUHKEY__@@PEBGAEAK@Z; CRegUtils::RegReadDWORDValueNoThrow(HKEY__ *,ushort const *,ulong &)
0x1800128d3  lea     r8, [rsp+88h+var_58]; unsigned int *
0x1800128d8  lea     rdx, aAutobackuplogf; "AutoBackupLogFiles"
0x1800128df  mov     rcx, [rbx]; HKEY
0x1800128e2  call    ?RegReadDWORDValueNoThrow@CRegUtils@@SAJPEAUHKEY__@@PEBGAEAK@Z; CRegUtils::RegReadDWORDValueNoThrow(HKEY__ *,ushort const *,ulong &)
0x1800128e7  mov     rax, [rdi+18h]
0x1800128eb  cmp     [rsp+88h+var_54], esi
0x1800128ef  jz      short loc_18001296C
0x1800128f1  cmp     [rsp+88h+var_58], esi
0x1800128f5  jz      short loc_180012931
0x1800128f7  lea     edx, [rsi+7]
0x1800128fa  cmp     rax, rdx
0x1800128fd  jb      short loc_180012928
0x1800128ff  jbe     short loc_180012906
0x180012901  mov     rbx, [rdi]
0x180012904  jmp     short loc_180012909
0x180012906  mov     rbx, rdi
0x180012909  mov     [rdi+10h], rdx
0x18001290d  mov     r8d, 0Eh; Size
0x180012913  lea     rdx, aArchive; "Archive"
0x18001291a  mov     rcx, rbx; void *
0x18001291d  call    memmove_0
0x180012922  mov     [rbx+0Eh], si
0x180012926  jmp     short loc_1800129A6
0x180012928  lea     r9, aArchive; "Archive"
0x18001292f  jmp     short loc_180012962
0x180012931  mov     edx, 8
0x180012936  cmp     rax, rdx
0x180012939  jb      short loc_18001295B
0x18001293b  mov     rbx, [rdi]
0x18001293e  mov     [rdi+10h], rdx
0x180012942  lea     r8d, [rdx+8]; Size
0x180012946  lea     rdx, aTruncate; "Truncate"
0x18001294d  mov     rcx, rbx; void *
0x180012950  call    memmove_0
0x180012955  mov     [rbx+10h], si
0x180012959  jmp     short loc_1800129A6
0x18001295b  lea     r9, aTruncate; "Truncate"
0x180012962  mov     rcx, rdi
0x180012965  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001296a  jmp     short loc_1800129A6
0x18001296c  mov     edx, 9
0x180012971  cmp     rax, rdx
0x180012974  jb      short loc_180012996
0x180012976  mov     rbx, [rdi]
0x180012979  mov     [rdi+10h], rdx
0x18001297d  lea     r8d, [rdx+9]; Size
0x180012981  lea     rdx, aOverwrite; "Overwrite"
0x180012988  mov     rcx, rbx; void *
0x18001298b  call    memmove_0
0x180012990  mov     [rbx+12h], si
0x180012994  jmp     short loc_1800129A6
0x180012996  lea     r9, aOverwrite; "Overwrite"
0x18001299d  mov     rcx, rdi
0x1800129a0  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800129a5  nop
0x1800129a6  jmp     short loc_1800129AD
0x1800129a8  mov     r14d, [rsp+88h+var_58]
0x1800129ad  mov     eax, cs:dword_180048E90
0x1800129b3  cmp     eax, 5
0x1800129b6  jbe     short loc_1800129FB
0x1800129b8  mov     [rsp+88h+var_58], r14d
0x1800129bd  lea     rax, [rsp+88h+var_58]
0x1800129c2  mov     [rsp+88h+var_30], rax
0x1800129c7  mov     [rsp+88h+var_28], 4
0x1800129d0  lea     rax, [rsp+88h+var_50]
0x1800129d5  mov     [rsp+88h+var_60], rax
0x1800129da  mov     [rsp+88h+var_68], 3
0x1800129e2  xor     r9d, r9d
0x1800129e5  xor     r8d, r8d
0x1800129e8  lea     rdx, byte_18003FEF5
0x1800129ef  lea     rcx, dword_180048E90
0x1800129f6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800129fb  mov     eax, r14d
0x1800129fe  mov     rcx, [rsp+88h+var_20]
0x180012a03  xor     rcx, rsp; StackCookie
0x180012a06  call    __security_check_cookie
0x180012a0b  mov     rbx, [rsp+88h+arg_10]
0x180012a13  add     rsp, 70h
0x180012a17  pop     r14
0x180012a19  pop     rdi
0x180012a1a  pop     rsi
0x180012a1b  retn
```
