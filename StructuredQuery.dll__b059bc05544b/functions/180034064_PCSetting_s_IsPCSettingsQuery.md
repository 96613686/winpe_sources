# PCSetting::s_IsPCSettingsQuery

- ea: `0x180034064`
- end: `0x180034270`
- name: `PCSetting::s_IsPCSettingsQuery`
- size: `524`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032b30`
- `0x180034064`
- `0x180034390`
- `0x18004bb94`

## callees

- `0x18002683c`
- `0x180034064`
- `0x18005daf0`
- `0x18005f7fd`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034259`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034259`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800340fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800340fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall PCSetting::s_IsPCSettingsQuery(__int64 *a1)
{
  char IsPCSettingsQuery; // si
  __int64 v3; // rdi
  unsigned int v5; // r14d
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // [rsp+30h] [rbp-19h] BYREF
  __int64 v11; // [rsp+38h] [rbp-11h] BYREF
  int v12; // [rsp+40h] [rbp-9h] BYREF
  __int64 v13; // [rsp+48h] [rbp-1h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v15; // [rsp+60h] [rbp+17h]
  __int128 Buf1; // [rsp+68h] [rbp+1Fh] BYREF
  int v17; // [rsp+78h] [rbp+2Fh]

  IsPCSettingsQuery = 0;
  v12 = 0;
  if ( (*(int (__fastcall **)(__int64 *, int *))(*a1 + 64))(a1, &v12) >= 0 )
  {
    v3 = *a1;
    if ( v12 == 3 )
    {
      *(_OWORD *)pvar = 0;
      v15 = 0;
      v10 = 0;
      Buf1 = 0;
      v17 = 0;
      if ( (*(int (__fastcall **)(__int64 *, __int128 *, unsigned int *, PROPVARIANT *))(v3 + 128))(
             a1,
             &Buf1,
             &v10,
             pvar) >= 0 )
      {
        if ( v17 == 100 && !memcmp_0(&Buf1, &PKEY_FileExtension, 0x10u) && LOWORD(pvar[0]) == 31 && v10 == 1 )
          IsPCSettingsQuery = CompareStringOrdinal(L".settingcontent-ms", -1, (LPCWCH)pvar[1], -1, 1) == 2;
        PropVariantClear(pvar);
      }
    }
    else
    {
      v11 = 0;
      Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&v11);
      if ( (*(int (__fastcall **)(__int64 *, GUID *, __int64 *))(v3 + 72))(
             a1,
             &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
             &v11) >= 0 )
      {
        v10 = 0;
        if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 24LL))(v11, &v10) >= 0 )
        {
          v5 = 0;
          do
          {
            if ( v5 >= v10 )
              break;
            v13 = 0;
            v6 = v11;
            v7 = *(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v11 + 32LL);
            Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&v13);
            if ( v7(v6, v5, &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7, &v13) >= 0 )
              IsPCSettingsQuery = PCSetting::s_IsPCSettingsQuery(v13);
            v8 = v13;
            if ( v13 )
            {
              v13 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
            ++v5;
          }
          while ( !IsPCSettingsQuery );
        }
      }
      v9 = v11;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
  }
  return IsPCSettingsQuery;
}

```

## disassembly

```asm
0x180034064  mov     [rsp-8+arg_8], rbx
0x180034069  mov     [rsp-8+arg_10], rsi
0x18003406e  push    rbp
0x18003406f  push    rdi
0x180034070  push    r14
0x180034072  lea     rbp, [rsp-47h]
0x180034077  sub     rsp, 90h
0x18003407e  mov     rax, cs:__security_cookie
0x180034085  xor     rax, rsp
0x180034088  mov     [rbp+57h+var_20], rax
0x18003408c  mov     rbx, rcx
0x18003408f  xor     sil, sil
0x180034092  mov     [rbp+57h+var_60], 0
0x180034099  mov     rax, [rcx]
0x18003409c  lea     rdx, [rbp+57h+var_60]
0x1800340a0  mov     rax, [rax+40h]
0x1800340a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340a9  test    eax, eax
0x1800340ab  js      short loc_180034100
0x1800340ad  mov     rdi, [rbx]
0x1800340b0  cmp     [rbp+57h+var_60], 3
0x1800340b4  jnz     short loc_180034127
0x1800340b6  xorps   xmm0, xmm0
0x1800340b9  xor     eax, eax
0x1800340bb  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800340bf  mov     [rbp+57h+var_40], rax
0x1800340c3  mov     [rbp+57h+var_70], eax
0x1800340c6  movups  [rbp+57h+Buf1], xmm0
0x1800340ca  mov     [rbp+57h+var_28], eax
0x1800340cd  lea     r9, [rbp+57h+pvar]
0x1800340d1  lea     r8, [rbp+57h+var_70]
0x1800340d5  lea     rdx, [rbp+57h+Buf1]
0x1800340d9  mov     rcx, rbx
0x1800340dc  mov     rax, [rdi+80h]
0x1800340e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340e8  test    eax, eax
0x1800340ea  js      short loc_180034100
0x1800340ec  cmp     [rbp+57h+var_28], 64h ; 'd'
0x1800340f0  jz      loc_18003420D
0x1800340f6  lea     rcx, [rbp+57h+pvar]; pvar
0x1800340fa  call    cs:__imp_PropVariantClear
0x180034100  mov     al, sil
0x180034103  mov     rcx, [rbp+57h+var_20]
0x180034107  xor     rcx, rsp; StackCookie
0x18003410a  call    __security_check_cookie
0x18003410f  lea     r11, [rsp+0A0h+var_10]
0x180034117  mov     rbx, [r11+28h]
0x18003411b  mov     rsi, [r11+30h]
0x18003411f  mov     rsp, r11
0x180034122  pop     r14
0x180034124  pop     rdi
0x180034125  pop     rbp
0x180034126  retn
0x180034127  mov     [rbp+57h+var_68], 0
0x18003412f  lea     rcx, [rbp+57h+var_68]
0x180034133  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x180034138  lea     r8, [rbp+57h+var_68]
0x18003413c  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180034143  mov     rcx, rbx
0x180034146  mov     rax, [rdi+48h]
0x18003414a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003414f  test    eax, eax
0x180034151  js      loc_1800341EA
0x180034157  mov     [rbp+57h+var_70], 0
0x18003415e  mov     rcx, [rbp+57h+var_68]
0x180034162  mov     rax, [rcx]
0x180034165  lea     rdx, [rbp+57h+var_70]
0x180034169  mov     rax, [rax+18h]
0x18003416d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034172  test    eax, eax
0x180034174  js      short loc_1800341EA
0x180034176  xor     r14d, r14d
0x180034179  cmp     r14d, [rbp+57h+var_70]
0x18003417d  jnb     short loc_1800341EA
0x18003417f  mov     [rbp+57h+var_58], 0
0x180034187  mov     rdi, [rbp+57h+var_68]
0x18003418b  mov     rax, [rdi]
0x18003418e  mov     rbx, [rax+20h]
0x180034192  lea     rcx, [rbp+57h+var_58]
0x180034196  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x18003419b  lea     r9, [rbp+57h+var_58]
0x18003419f  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x1800341a6  mov     edx, r14d
0x1800341a9  mov     rcx, rdi
0x1800341ac  mov     rax, rbx
0x1800341af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341b4  test    eax, eax
0x1800341b6  js      short loc_1800341C4
0x1800341b8  mov     rcx, [rbp+57h+var_58]
0x1800341bc  call    PCSetting__s_IsPCSettingsQuery
0x1800341c1  mov     sil, al
0x1800341c4  mov     rcx, [rbp+57h+var_58]
0x1800341c8  test    rcx, rcx
0x1800341cb  jz      short loc_1800341E2
0x1800341cd  mov     [rbp+57h+var_58], 0
0x1800341d5  mov     rdx, [rcx]
0x1800341d8  mov     rax, [rdx+10h]
0x1800341dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341e1  nop
0x1800341e2  inc     r14d
0x1800341e5  test    sil, sil
0x1800341e8  jz      short loc_180034179
0x1800341ea  mov     rcx, [rbp+57h+var_68]
0x1800341ee  test    rcx, rcx
0x1800341f1  jz      short loc_180034208
0x1800341f3  mov     [rbp+57h+var_68], 0
0x1800341fb  mov     rax, [rcx]
0x1800341fe  mov     rax, [rax+10h]
0x180034202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034207  nop
0x180034208  jmp     loc_180034100
0x18003420d  mov     r8d, 10h; Size
0x180034213  lea     rdx, PKEY_FileExtension; Buf2
0x18003421a  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18003421e  call    memcmp_0
0x180034223  test    eax, eax
0x180034225  jnz     loc_1800340F6
0x18003422b  cmp     word ptr [rbp+57h+pvar], 1Fh
0x180034230  jnz     loc_1800340F6
0x180034236  cmp     [rbp+57h+var_70], 1
0x18003423a  jnz     loc_1800340F6
0x180034240  mov     [rsp+0A0h+bIgnoreCase], 1; bIgnoreCase
0x180034248  or      edx, 0FFFFFFFFh; cchCount1
0x18003424b  mov     r9d, edx; cchCount2
0x18003424e  mov     r8, [rbp+57h+pvar+8]; lpString2
0x180034252  lea     rcx, aSettingcontent; ".settingcontent-ms"
0x180034259  call    cs:__imp_CompareStringOrdinal
0x18003425f  cmp     eax, 2
0x180034262  jnz     loc_1800340F6
0x180034268  mov     sil, 1
0x18003426b  jmp     loc_1800340F6
```
