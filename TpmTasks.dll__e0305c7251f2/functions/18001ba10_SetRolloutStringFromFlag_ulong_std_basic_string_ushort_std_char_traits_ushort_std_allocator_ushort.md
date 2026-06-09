# SetRolloutStringFromFlag(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ba10`
- end: `0x18001bb5d`
- name: `?SetRolloutStringFromFlag@@YAXKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001e5d0`

## callees

- `0x18000bc54`
- `0x18001ba10`

## string_xrefs

- `0x18001ba3a`: `DBUpdateExternalRollout`
- `0x18001ba33`: ` | DBUpdateExternalRollout`
- `0x18001ba6a`: `KEKUpdateAllowList`
- `0x18001ba63`: ` | KEKUpdateAllowList`
- `0x18001ba9a`: `DBUpdate3PUEFICARollout`
- `0x18001ba93`: ` | DBUpdate3PUEFICARollout`
- `0x18001bace`: `DBUpdate3POROMRollout`
- `0x18001bac7`: ` | DBUpdate3POROMRollout`

## pseudocode

```c
__int64 __fastcall SetRolloutStringFromFlag(__int16 a1, __int64 a2)
{
  _QWORD *v2; // rbx
  __int64 v3; // rdi
  const wchar_t *v6; // rdx
  __int64 v7; // r8
  __int64 result; // rax
  const wchar_t *v9; // rdx
  __int64 v10; // r8
  const wchar_t *v11; // rdx
  __int64 v12; // r8
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  const wchar_t *v15; // rdx
  __int64 v16; // r8
  const wchar_t *v17; // rdx

  v2 = (_QWORD *)(a2 + 16);
  v3 = -1;
  if ( (a1 & 0x40) != 0 )
  {
    v6 = L"DBUpdateExternalRollout";
    v7 = -1;
    if ( *v2 )
      v6 = L" | DBUpdateExternalRollout";
    do
      ++v7;
    while ( v6[v7] );
    result = std::wstring::_Append<unsigned short>(a2, v6, v7);
  }
  if ( (a1 & 4) != 0 )
  {
    v9 = L"KEKUpdateAllowList";
    v10 = -1;
    if ( *v2 )
      v9 = L" | KEKUpdateAllowList";
    do
      ++v10;
    while ( v9[v10] );
    result = std::wstring::_Append<unsigned short>(a2, v9, v10);
  }
  if ( (a1 & 0x1000) != 0 )
  {
    v11 = L"DBUpdate3PUEFICARollout";
    v12 = -1;
    if ( *v2 )
      v11 = L" | DBUpdate3PUEFICARollout";
    do
      ++v12;
    while ( v11[v12] );
    result = std::wstring::_Append<unsigned short>(a2, v11, v12);
    v2 = (_QWORD *)(a2 + 16);
  }
  if ( (a1 & 0x800) != 0 )
  {
    v13 = L"DBUpdate3POROMRollout";
    v14 = -1;
    if ( *v2 )
      v13 = L" | DBUpdate3POROMRollout";
    do
      ++v14;
    while ( v13[v14] );
    result = std::wstring::_Append<unsigned short>(a2, v13, v14);
  }
  if ( (a1 & 0x100) != 0 )
  {
    v15 = L"PCA2023BootMgrRollout";
    v16 = -1;
    if ( *v2 )
      v15 = L" | PCA2023BootMgrRollout";
    do
      ++v16;
    while ( v15[v16] );
    result = std::wstring::_Append<unsigned short>(a2, v15, v16);
    v2 = (_QWORD *)(a2 + 16);
  }
  if ( (a1 & 0x2000) != 0 )
  {
    v17 = L"TestKeyRolling";
    if ( *v2 )
      v17 = L" | TestKeyRolling";
    do
      ++v3;
    while ( v17[v3] );
    return std::wstring::_Append<unsigned short>(a2, v17, v3);
  }
  return result;
}

```

## disassembly

```asm
0x18001ba10  push    rbx
0x18001ba12  push    rbp
0x18001ba13  push    rsi
0x18001ba14  push    rdi
0x18001ba15  push    r14
0x18001ba17  sub     rsp, 20h
0x18001ba1b  xor     r14d, r14d
0x18001ba1e  lea     rbx, [rdx+10h]
0x18001ba22  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ba26  mov     rbp, rdx
0x18001ba29  mov     esi, ecx
0x18001ba2b  test    cl, 40h
0x18001ba2e  jz      short loc_18001BA5A
0x18001ba30  cmp     [rbx], r14
0x18001ba33  lea     rax, aDbupdateextern; " | DBUpdateExternalRollout"
0x18001ba3a  lea     rdx, aDbupdateextern_0; "DBUpdateExternalRollout"
0x18001ba41  mov     r8, rdi
0x18001ba44  cmovnz  rdx, rax
0x18001ba48  inc     r8
0x18001ba4b  cmp     [rdx+r8*2], r14w
0x18001ba50  jnz     short loc_18001BA48
0x18001ba52  mov     rcx, rbp
0x18001ba55  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001ba5a  test    sil, 4
0x18001ba5e  jz      short loc_18001BA8A
0x18001ba60  cmp     [rbx], r14
0x18001ba63  lea     rax, aKekupdateallow; " | KEKUpdateAllowList"
0x18001ba6a  lea     rdx, aKekupdateallow_0; "KEKUpdateAllowList"
0x18001ba71  mov     r8, rdi
0x18001ba74  cmovnz  rdx, rax
0x18001ba78  inc     r8
0x18001ba7b  cmp     [rdx+r8*2], r14w
0x18001ba80  jnz     short loc_18001BA78
0x18001ba82  mov     rcx, rbp
0x18001ba85  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001ba8a  bt      esi, 0Ch
0x18001ba8e  jnb     short loc_18001BABE
0x18001ba90  cmp     [rbx], r14
0x18001ba93  lea     rax, aDbupdate3puefi_0; " | DBUpdate3PUEFICARollout"
0x18001ba9a  lea     rdx, aDbupdate3puefi; "DBUpdate3PUEFICARollout"
0x18001baa1  mov     r8, rdi
0x18001baa4  cmovnz  rdx, rax
0x18001baa8  inc     r8
0x18001baab  cmp     [rdx+r8*2], r14w
0x18001bab0  jnz     short loc_18001BAA8
0x18001bab2  mov     rcx, rbp
0x18001bab5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001baba  lea     rbx, [rbp+10h]
0x18001babe  bt      esi, 0Bh
0x18001bac2  jnb     short loc_18001BAEE
0x18001bac4  cmp     [rbx], r14
0x18001bac7  lea     rax, aDbupdate3porom; " | DBUpdate3POROMRollout"
0x18001bace  lea     rdx, aDbupdate3porom_0; "DBUpdate3POROMRollout"
0x18001bad5  mov     r8, rdi
0x18001bad8  cmovnz  rdx, rax
0x18001badc  inc     r8
0x18001badf  cmp     [rdx+r8*2], r14w
0x18001bae4  jnz     short loc_18001BADC
0x18001bae6  mov     rcx, rbp
0x18001bae9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001baee  bt      esi, 8
0x18001baf2  jnb     short loc_18001BB22
0x18001baf4  cmp     [rbx], r14
0x18001baf7  lea     rax, aPca2023bootmgr; " | PCA2023BootMgrRollout"
0x18001bafe  lea     rdx, aPca2023bootmgr_0; "PCA2023BootMgrRollout"
0x18001bb05  mov     r8, rdi
0x18001bb08  cmovnz  rdx, rax
0x18001bb0c  inc     r8
0x18001bb0f  cmp     [rdx+r8*2], r14w
0x18001bb14  jnz     short loc_18001BB0C
0x18001bb16  mov     rcx, rbp
0x18001bb19  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001bb1e  lea     rbx, [rbp+10h]
0x18001bb22  bt      esi, 0Dh
0x18001bb26  jnb     short loc_18001BB52
0x18001bb28  cmp     [rbx], r14
0x18001bb2b  lea     rax, aTestkeyrolling_2; " | TestKeyRolling"
0x18001bb32  lea     rdx, aTestkeyrolling_0; "TestKeyRolling"
0x18001bb39  cmovnz  rdx, rax
0x18001bb3d  inc     rdi
0x18001bb40  cmp     [rdx+rdi*2], r14w
0x18001bb45  jnz     short loc_18001BB3D
0x18001bb47  mov     r8, rdi
0x18001bb4a  mov     rcx, rbp
0x18001bb4d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001bb52  add     rsp, 20h
0x18001bb56  pop     r14
0x18001bb58  pop     rdi
0x18001bb59  pop     rsi
0x18001bb5a  pop     rbp
0x18001bb5b  pop     rbx
0x18001bb5c  retn
```
