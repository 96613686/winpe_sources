# CPolicyChannel::GetActionWhenFull(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180013274`
- end: `0x180013401`
- name: `?GetActionWhenFull@CPolicyChannel@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18000ce20`

## callees

- `0x180001108`
- `0x180001b90`
- `0x180002d31`
- `0x180011d0c`
- `0x180012afc`
- `0x180013274`

## string_xrefs

- `0x180013365`: `Overwrite`
- `0x18001337a`: `Overwrite`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::GetActionWhenFull(HKEY *a1, __int64 a2)
{
  unsigned int v4; // r14d
  __int64 v5; // r8
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  _WORD *v8; // rbx
  const wchar_t *v9; // r9
  _WORD *v10; // rbx
  _WORD *v11; // rbx
  unsigned int v13; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-54h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+38h] [rbp-50h] BYREF
  unsigned int *v16; // [rsp+58h] [rbp-30h]
  __int64 v17; // [rsp+60h] [rbp-28h]

  v4 = 0;
  v14 = 0;
  v13 = 0;
  CRegUtils::RegReadDWORDValueNoThrow(*a1, L"Retention", &v14);
  CRegUtils::RegReadDWORDValueNoThrow(*a1, L"AutoBackupLogFiles", &v13);
  v6 = *(_QWORD *)(a2 + 24);
  if ( v14 )
  {
    if ( v13 )
    {
      v7 = 7;
      if ( v6 >= 7 )
      {
        if ( v6 <= 7 )
          v8 = (_WORD *)a2;
        else
          v8 = *(_WORD **)a2;
        *(_QWORD *)(a2 + 16) = 7;
        memmove_0(v8, L"Archive", 0xEu);
        v8[7] = 0;
        goto LABEL_15;
      }
      v9 = L"Archive";
    }
    else
    {
      v7 = 8;
      if ( v6 >= 8 )
      {
        v10 = *(_WORD **)a2;
        *(_QWORD *)(a2 + 16) = 8;
        memmove_0(v10, L"Truncate", 0x10u);
        v10[8] = 0;
        goto LABEL_15;
      }
      v9 = L"Truncate";
    }
    try
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a2, v7, v5, v9);
    }
    catch ( std::exception )
    {
      v4 = -2147467259;
    }
  }
  else if ( v6 < 9 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      a2,
      9,
      v5,
      L"Overwrite");
  }
  else
  {
    v11 = *(_WORD **)a2;
    *(_QWORD *)(a2 + 16) = 9;
    memmove_0(v11, L"Overwrite", 0x12u);
    v11[9] = 0;
  }
LABEL_15:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v13 = v4;
    v16 = &v13;
    v17 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, (unsigned __int8 *)byte_180041EF5, 0, 0, 3u, &v15);
  }
  return v4;
}

```

## disassembly

```asm
0x180013274  mov     [rsp+arg_10], rbx
0x180013279  push    rsi
0x18001327a  push    rdi
0x18001327b  push    r14
0x18001327d  sub     rsp, 70h
0x180013281  mov     rax, cs:__security_cookie
0x180013288  xor     rax, rsp
0x18001328b  mov     [rsp+88h+var_20], rax
0x180013290  mov     rdi, rdx
0x180013293  mov     rbx, rcx
0x180013296  xor     esi, esi
0x180013298  mov     r14d, esi
0x18001329b  mov     [rsp+88h+var_54], esi
0x18001329f  mov     [rsp+88h+var_58], esi
0x1800132a3  lea     r8, [rsp+88h+var_54]; unsigned int *
0x1800132a8  lea     rdx, aRetention; "Retention"
0x1800132af  mov     rcx, [rcx]; HKEY
0x1800132b2  call    ?RegReadDWORDValueNoThrow@CRegUtils@@SAJPEAUHKEY__@@PEBGAEAK@Z; CRegUtils::RegReadDWORDValueNoThrow(HKEY__ *,ushort const *,ulong &)
0x1800132b7  lea     r8, [rsp+88h+var_58]; unsigned int *
0x1800132bc  lea     rdx, aAutobackuplogf; "AutoBackupLogFiles"
0x1800132c3  mov     rcx, [rbx]; HKEY
0x1800132c6  call    ?RegReadDWORDValueNoThrow@CRegUtils@@SAJPEAUHKEY__@@PEBGAEAK@Z; CRegUtils::RegReadDWORDValueNoThrow(HKEY__ *,ushort const *,ulong &)
0x1800132cb  mov     rax, [rdi+18h]
0x1800132cf  cmp     [rsp+88h+var_54], esi
0x1800132d3  jz      short loc_180013350
0x1800132d5  cmp     [rsp+88h+var_58], esi
0x1800132d9  jz      short loc_180013315
0x1800132db  lea     edx, [rsi+7]
0x1800132de  cmp     rax, rdx
0x1800132e1  jb      short loc_18001330C
0x1800132e3  jbe     short loc_1800132EA
0x1800132e5  mov     rbx, [rdi]
0x1800132e8  jmp     short loc_1800132ED
0x1800132ea  mov     rbx, rdi
0x1800132ed  mov     [rdi+10h], rdx
0x1800132f1  mov     r8d, 0Eh; Size
0x1800132f7  lea     rdx, aArchive; "Archive"
0x1800132fe  mov     rcx, rbx; void *
0x180013301  call    memmove_0
0x180013306  mov     [rbx+0Eh], si
0x18001330a  jmp     short loc_18001338A
0x18001330c  lea     r9, aArchive; "Archive"
0x180013313  jmp     short loc_180013346
0x180013315  mov     edx, 8
0x18001331a  cmp     rax, rdx
0x18001331d  jb      short loc_18001333F
0x18001331f  mov     rbx, [rdi]
0x180013322  mov     [rdi+10h], rdx
0x180013326  lea     r8d, [rdx+8]; Size
0x18001332a  lea     rdx, aTruncate; "Truncate"
0x180013331  mov     rcx, rbx; void *
0x180013334  call    memmove_0
0x180013339  mov     [rbx+10h], si
0x18001333d  jmp     short loc_18001338A
0x18001333f  lea     r9, aTruncate; "Truncate"
0x180013346  mov     rcx, rdi
0x180013349  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001334e  jmp     short loc_18001338A
0x180013350  mov     edx, 9
0x180013355  cmp     rax, rdx
0x180013358  jb      short loc_18001337A
0x18001335a  mov     rbx, [rdi]
0x18001335d  mov     [rdi+10h], rdx
0x180013361  lea     r8d, [rdx+9]; Size
0x180013365  lea     rdx, aOverwrite; "Overwrite"
0x18001336c  mov     rcx, rbx; void *
0x18001336f  call    memmove_0
0x180013374  mov     [rbx+12h], si
0x180013378  jmp     short loc_18001338A
0x18001337a  lea     r9, aOverwrite; "Overwrite"
0x180013381  mov     rcx, rdi
0x180013384  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180013389  nop
0x18001338a  jmp     short loc_180013391
0x18001338c  mov     r14d, [rsp+88h+var_58]
0x180013391  mov     eax, cs:dword_18004AE90
0x180013397  cmp     eax, 5
0x18001339a  jbe     short loc_1800133DF
0x18001339c  mov     [rsp+88h+var_58], r14d
0x1800133a1  lea     rax, [rsp+88h+var_58]
0x1800133a6  mov     [rsp+88h+var_30], rax
0x1800133ab  mov     [rsp+88h+var_28], 4
0x1800133b4  lea     rax, [rsp+88h+var_50]
0x1800133b9  mov     [rsp+88h+var_60], rax
0x1800133be  mov     [rsp+88h+var_68], 3
0x1800133c6  xor     r9d, r9d
0x1800133c9  xor     r8d, r8d
0x1800133cc  lea     rdx, byte_180041EF5
0x1800133d3  lea     rcx, dword_18004AE90
0x1800133da  call    _tlgWriteTransfer_EventWriteTransfer
0x1800133df  mov     eax, r14d
0x1800133e2  mov     rcx, [rsp+88h+var_20]
0x1800133e7  xor     rcx, rsp; StackCookie
0x1800133ea  call    __security_check_cookie
0x1800133ef  mov     rbx, [rsp+88h+arg_10]
0x1800133f7  add     rsp, 70h
0x1800133fb  pop     r14
0x1800133fd  pop     rdi
0x1800133fe  pop     rsi
0x1800133ff  retn
```
