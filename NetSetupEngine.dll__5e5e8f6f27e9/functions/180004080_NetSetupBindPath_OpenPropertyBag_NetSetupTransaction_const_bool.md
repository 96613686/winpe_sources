# NetSetupBindPath::OpenPropertyBag(NetSetupTransaction const &,bool)

- ea: `0x180004080`
- end: `0x180004423`
- name: `?OpenPropertyBag@NetSetupBindPath@@AEAAXAEBVNetSetupTransaction@@_N@Z`
- size: `931`
- prototype: `void __fastcall(NetSetupBindPath *__hidden this, const struct NetSetupTransaction *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003f4b0`

## callees

- `0x180004080`
- `0x180005660`
- `0x180006eb0`
- `0x180010200`
- `0x180021888`
- `0x180029d20`
- `0x1800646b8`
- `0x180064704`
- `0x1800810d0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180004111`
- `msvcrt!swprintf_s` at `0x180004282`
- `msvcrt!swprintf_s` at `0x180004111`
- `msvcrt!swprintf_s` at `0x180004282`
- `msvcrt!wcscat_s` at `0x18000414a`
- `msvcrt!wcscat_s` at `0x1800042e2`
- `msvcrt!wcscat_s` at `0x180004317`
- `msvcrt!wcscat_s` at `0x18000414a`
- `msvcrt!wcscat_s` at `0x1800042e2`
- `msvcrt!wcscat_s` at `0x180004317`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000419f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800043c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800043f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000419f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800043c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800043f8`

## string_xrefs

- `0x1800040fd`: `Control\NetworkSetup2\BindPaths\%ws`
- `0x180004233`: `Protocols`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NetSetupBindPath::OpenPropertyBag(
        NetSetupBindPath *this,
        const struct NetSetupTransaction *a2,
        char a3)
{
  int v6; // ecx
  _QWORD *v7; // rax
  HKEY *v8; // rdi
  int v9; // ecx
  HKEY SubKey; // rax
  char v11; // di
  HKEY v12; // rsi
  HKEY v13; // r14
  _QWORD *v14; // rax
  _QWORD *v15; // rdi
  __int64 v16; // rdx
  const wchar_t *v17; // rsi
  _QWORD *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int128 v23; // xmm6
  HKEY v24; // rdi
  int v25; // ecx
  __int64 v26; // rax
  HKEY v27; // [rsp+40h] [rbp-2C8h] BYREF
  HKEY v28; // [rsp+48h] [rbp-2C0h]
  HKEY hKey; // [rsp+50h] [rbp-2B8h] BYREF
  void *Block[5]; // [rsp+58h] [rbp-2B0h] BYREF
  _BYTE v31[32]; // [rsp+80h] [rbp-288h] BYREF
  wchar_t Buffer[264]; // [rsp+A0h] [rbp-268h] BYREF

  Block[4] = (void *)-2LL;
  LODWORD(v28) = 0;
  if ( !*((_QWORD *)this + 20) )
  {
    v6 = *((_DWORD *)this + 30);
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        v14 = (_QWORD *)StringFromGuid(v31, *((_QWORD *)this + 10) + 24LL);
        v15 = v14;
        if ( v14[3] >= 8u )
          v15 = (_QWORD *)*v14;
        v16 = *((_QWORD *)this + 10);
        v17 = L"Filters";
        if ( *(_DWORD *)(v16 + 20) != 3 )
          v17 = L"Protocols";
        v18 = (_QWORD *)StringFromGuid(Block, v16 + 4);
        if ( v18[3] >= 8u )
          v18 = (_QWORD *)*v18;
        swprintf_s(Buffer, 0x104u, L"Networking\\NetAdapters\\%ws\\Bindings\\%ws\\%ws", v18, v17, v15);
        LOBYTE(v19) = 1;
        std::wstring::_Tidy(Block, v19, 0);
        LOBYTE(v20) = 1;
        std::wstring::_Tidy(v31, v20, 0);
        if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) >> 2) > 2 )
        {
          wcscat_s(Buffer, 0x104u, L"-");
          v21 = StringFromGuid(v31, *((_QWORD *)this + 10) + 44LL);
          if ( *(_QWORD *)(v21 + 24) >= 8u )
            v21 = *(_QWORD *)v21;
          wcscat_s(Buffer, 0x104u, (const wchar_t *)v21);
          LOBYTE(v22) = 1;
          std::wstring::_Tidy(v31, v22, 0);
        }
      }
    }
    else
    {
      v7 = (_QWORD *)StringFromGuid(Block, (char *)this + 32);
      if ( v7[3] >= 8u )
        v7 = (_QWORD *)*v7;
      swprintf_s(Buffer, 0x104u, L"Control\\NetworkSetup2\\BindPaths\\%ws", v7);
      if ( Block[3] >= (void *)8 )
        operator delete(Block[0]);
    }
    v8 = 0;
    v9 = *((_DWORD *)this + 30);
    if ( v9 )
    {
      if ( v9 == 1 )
        v8 = (HKEY *)((char *)a2 + 48);
    }
    else
    {
      v8 = (HKEY *)((char *)a2 + 24);
      wcscat_s(Buffer, 0x104u, L"\\Properties");
    }
    if ( a3 )
    {
      SubKey = RegistryKey::CreateSubKey(v8, (HKEY)&v27, Buffer, 0xEu, 0, 0);
      v11 = 1;
    }
    else
    {
      SubKey = RegistryKey::TryOpenSubKey(v8, (HKEY)&hKey, Buffer, 0xEu, 0);
      v11 = 2;
    }
    v12 = *(HKEY *)SubKey;
    *(_QWORD *)SubKey = 0;
    v13 = v12;
    v28 = v12;
    if ( (v11 & 2) != 0 )
    {
      v11 &= ~2u;
      if ( hKey )
        RegCloseKey(hKey);
    }
    if ( (v11 & 1) != 0 && v27 )
      RegCloseKey(v27);
    if ( a3 || v12 )
    {
      v23 = *((_OWORD *)this + 2);
      v24 = (HKEY)operator new(0x58u);
      v27 = v24;
      if ( v24 )
      {
        v25 = *((_DWORD *)this + 30);
        if ( *(_QWORD *)a2 )
          v26 = *(_QWORD *)(*(_QWORD *)a2 + 8LL);
        else
          v26 = 0;
        *(_QWORD *)v24 = &NetSetupPropertyBag::`vftable';
        v13 = 0;
        *((_QWORD *)v24 + 1) = v12;
        *((_DWORD *)v24 + 4) = 2;
        *(_OWORD *)(v24 + 5) = v23;
        *((_DWORD *)v24 + 9) = v25;
        *((_QWORD *)v24 + 5) = v26;
        *((_QWORD *)v24 + 6) = 0;
        *((_DWORD *)v24 + 14) = 0;
        *((_QWORD *)v24 + 8) = 0;
        *((_QWORD *)v24 + 9) = 0;
        *((_QWORD *)v24 + 10) = 0;
      }
      else
      {
        v24 = 0;
      }
      if ( v24 != *((HKEY *)this + 20) )
      {
        std::unique_ptr<NetSetupPropertyBag>::_Delete((char *)this + 160);
        *((_QWORD *)this + 20) = v24;
      }
      if ( v13 )
        RegCloseKey(v13);
    }
  }
}

```

## disassembly

```asm
0x180004080  mov     rax, rsp
0x180004083  push    rbp
0x180004084  push    rsi
0x180004085  push    rdi
0x180004086  push    r12
0x180004088  push    r13
0x18000408a  push    r14
0x18000408c  push    r15
0x18000408e  sub     rsp, 2D0h
0x180004095  mov     [rsp+308h+var_290], 0FFFFFFFFFFFFFFFEh
0x18000409e  mov     [rax+18h], rbx
0x1800040a2  movaps  xmmword ptr [rax-48h], xmm6
0x1800040a6  mov     rax, cs:__security_cookie
0x1800040ad  xor     rax, rsp
0x1800040b0  mov     [rsp+308h+var_58], rax
0x1800040b8  movzx   ebp, r8b
0x1800040bc  mov     r12, rdx
0x1800040bf  mov     rbx, rcx
0x1800040c2  xor     r13d, r13d
0x1800040c5  mov     dword ptr [rsp+308h+var_2C0], r13d
0x1800040ca  cmp     [rcx+0A0h], r13
0x1800040d1  jnz     loc_1800041C2
0x1800040d7  mov     ecx, [rcx+78h]
0x1800040da  test    ecx, ecx
0x1800040dc  jnz     loc_180004204
0x1800040e2  lea     rdx, [rbx+20h]
0x1800040e6  lea     rcx, [rsp+308h+Block]
0x1800040eb  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x1800040f0  cmp     qword ptr [rax+18h], 8
0x1800040f5  jb      short loc_1800040FA
0x1800040f7  mov     rax, [rax]
0x1800040fa  mov     r9, rax
0x1800040fd  lea     r8, aControlNetwork; "Control\\NetworkSetup2\\BindPaths\\%ws"
0x180004104  mov     edx, 104h; BufferCount
0x180004109  lea     rcx, [rsp+308h+Buffer]; Buffer
0x180004111  call    cs:__imp_swprintf_s
0x180004117  cmp     [rsp+308h+var_298], 8
0x18000411d  jnb     loc_1800041F5
0x180004123  mov     rdi, r13
0x180004126  mov     ecx, [rbx+78h]
0x180004129  test    ecx, ecx
0x18000412b  jnz     loc_1800043D2
0x180004131  lea     rdi, [r12+18h]
0x180004136  lea     r8, aProperties; "\\Properties"
0x18000413d  mov     edx, 104h; SizeInWords
0x180004142  lea     rcx, [rsp+308h+Buffer]; Destination
0x18000414a  call    cs:__imp_wcscat_s
0x180004150  mov     r9d, 0Eh
0x180004156  lea     r8, [rsp+308h+Buffer]
0x18000415e  mov     rcx, rdi
0x180004161  test    bpl, bpl
0x180004164  jnz     loc_180004403
0x18000416a  mov     [rsp+308h+var_2E8], r13
0x18000416f  lea     rdx, [rsp+308h+hKey]
0x180004174  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x180004179  mov     edi, 2
0x18000417e  mov     rsi, [rax]
0x180004181  mov     [rax], r13
0x180004184  mov     r14, rsi
0x180004187  mov     [rsp+308h+var_2C0], rsi
0x18000418c  test    dil, 2
0x180004190  jz      short loc_1800041A6
0x180004192  and     edi, 0FFFFFFFDh
0x180004195  mov     rcx, [rsp+308h+hKey]; hKey
0x18000419a  test    rcx, rcx
0x18000419d  jz      short loc_1800041A6
0x18000419f  call    cs:__imp_RegCloseKey
0x1800041a5  nop
0x1800041a6  test    dil, 1
0x1800041aa  jnz     loc_1800043EA
0x1800041b0  test    bpl, bpl
0x1800041b3  jnz     loc_180004334
0x1800041b9  test    rsi, rsi
0x1800041bc  jnz     loc_180004334
0x1800041c2  mov     rcx, [rsp+308h+var_58]
0x1800041ca  xor     rcx, rsp; StackCookie
0x1800041cd  call    __security_check_cookie
0x1800041d2  mov     rbx, [rsp+308h+arg_10]
0x1800041da  movaps  xmm6, [rsp+308h+var_48]
0x1800041e2  add     rsp, 2D0h
0x1800041e9  pop     r15
0x1800041eb  pop     r14
0x1800041ed  pop     r13
0x1800041ef  pop     r12
0x1800041f1  pop     rdi
0x1800041f2  pop     rsi
0x1800041f3  pop     rbp
0x1800041f4  retn
0x1800041f5  mov     rcx, [rsp+308h+Block]; Block
0x1800041fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800041ff  jmp     loc_180004123
0x180004204  cmp     ecx, 1
0x180004207  jnz     loc_180004123
0x18000420d  mov     rdx, [rbx+50h]
0x180004211  add     rdx, 18h
0x180004215  lea     rcx, [rsp+308h+var_288]
0x18000421d  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180004222  mov     rdi, rax
0x180004225  cmp     qword ptr [rax+18h], 8
0x18000422a  jb      short loc_18000422F
0x18000422c  mov     rdi, [rax]
0x18000422f  mov     rdx, [rbx+50h]
0x180004233  lea     rax, aProtocols; "Protocols"
0x18000423a  lea     rsi, aFilters; "Filters"
0x180004241  cmp     dword ptr [rdx+14h], 3
0x180004245  cmovnz  rsi, rax
0x180004249  add     rdx, 4
0x18000424d  lea     rcx, [rsp+308h+Block]
0x180004252  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180004257  cmp     qword ptr [rax+18h], 8
0x18000425c  jb      short loc_180004261
0x18000425e  mov     rax, [rax]
0x180004261  mov     [rsp+308h+var_2E0], rdi
0x180004266  mov     [rsp+308h+var_2E8], rsi
0x18000426b  mov     r9, rax
0x18000426e  lea     r8, aNetworkingNeta_0; "Networking\\NetAdapters\\%ws\\Bindings"...
0x180004275  mov     edx, 104h; BufferCount
0x18000427a  lea     rcx, [rsp+308h+Buffer]; Buffer
0x180004282  call    cs:__imp_swprintf_s
0x180004288  xor     r8d, r8d
0x18000428b  mov     dl, 1
0x18000428d  lea     rcx, [rsp+308h+Block]
0x180004292  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004297  nop
0x180004298  xor     r8d, r8d
0x18000429b  mov     dl, 1
0x18000429d  lea     rcx, [rsp+308h+var_288]
0x1800042a5  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800042aa  mov     rax, [rbx+58h]
0x1800042ae  sub     rax, [rbx+50h]
0x1800042b2  sar     rax, 2
0x1800042b6  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800042c0  imul    rax, rcx
0x1800042c4  cmp     rax, 2
0x1800042c8  jbe     loc_180004123
0x1800042ce  lea     r8, asc_18009A088; "-"
0x1800042d5  mov     edx, 104h; SizeInWords
0x1800042da  lea     rcx, [rsp+308h+Buffer]; Destination
0x1800042e2  call    cs:__imp_wcscat_s
0x1800042e8  mov     rdx, [rbx+50h]
0x1800042ec  add     rdx, 2Ch ; ','
0x1800042f0  lea     rcx, [rsp+308h+var_288]
0x1800042f8  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x1800042fd  cmp     qword ptr [rax+18h], 8
0x180004302  jb      short loc_180004307
0x180004304  mov     rax, [rax]
0x180004307  mov     r8, rax; Source
0x18000430a  mov     edx, 104h; SizeInWords
0x18000430f  lea     rcx, [rsp+308h+Buffer]; Destination
0x180004317  call    cs:__imp_wcscat_s
0x18000431d  xor     r8d, r8d
0x180004320  mov     dl, 1
0x180004322  lea     rcx, [rsp+308h+var_288]
0x18000432a  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000432f  jmp     loc_180004123
0x180004334  movups  xmm6, xmmword ptr [rbx+20h]
0x180004338  mov     ecx, 58h ; 'X'; Size
0x18000433d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004342  mov     rdi, rax
0x180004345  mov     [rsp+308h+var_2C8], rax
0x18000434a  test    rax, rax
0x18000434d  jz      loc_1800043E5
0x180004353  mov     ecx, [rbx+78h]
0x180004356  mov     rax, [r12]
0x18000435a  test    rax, rax
0x18000435d  jnz     short loc_1800043CC
0x18000435f  mov     rax, r13
0x180004362  lea     rdx, ??_7NetSetupPropertyBag@@6B@; const NetSetupPropertyBag::`vftable'
0x180004369  mov     [rdi], rdx
0x18000436c  mov     r14, r13
0x18000436f  mov     [rdi+8], rsi
0x180004373  mov     dword ptr [rdi+10h], 2
0x18000437a  movups  xmmword ptr [rdi+14h], xmm6
0x18000437e  mov     [rdi+24h], ecx
0x180004381  mov     [rdi+28h], rax
0x180004385  mov     [rdi+30h], r13
0x180004389  mov     [rdi+38h], r13d
0x18000438d  mov     [rdi+40h], r13
0x180004391  mov     [rdi+48h], r13
0x180004395  mov     [rdi+50h], r13
0x180004399  cmp     rdi, [rbx+0A0h]
0x1800043a0  jz      short loc_1800043B5
0x1800043a2  lea     rcx, [rbx+0A0h]
0x1800043a9  call    ?_Delete@?$unique_ptr@VNetSetupPropertyBag@@U?$default_delete@VNetSetupPropertyBag@@@std@@@std@@AEAAXXZ; std::unique_ptr<NetSetupPropertyBag>::_Delete(void)
0x1800043ae  mov     [rbx+0A0h], rdi
0x1800043b5  test    r14, r14
0x1800043b8  jz      loc_1800041C2
0x1800043be  mov     rcx, r14; hKey
0x1800043c1  call    cs:__imp_RegCloseKey
0x1800043c7  jmp     loc_1800041C2
0x1800043cc  mov     rax, [rax+8]
0x1800043d0  jmp     short loc_180004362
0x1800043d2  cmp     ecx, 1
0x1800043d5  jnz     loc_180004150
0x1800043db  lea     rdi, [r12+30h]
0x1800043e0  jmp     loc_180004150
0x1800043e5  mov     rdi, r13
0x1800043e8  jmp     short loc_180004399
0x1800043ea  mov     rcx, [rsp+308h+var_2C8]; hKey
0x1800043ef  test    rcx, rcx
0x1800043f2  jz      loc_1800041B0
0x1800043f8  call    cs:__imp_RegCloseKey
0x1800043fe  jmp     loc_1800041B0
0x180004403  mov     [rsp+308h+var_2E0], r13
0x180004408  mov     [rsp+308h+var_2E8], r13
0x18000440d  lea     rdx, [rsp+308h+var_2C8]
0x180004412  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180004417  nop
0x180004418  mov     edi, 1
0x18000441d  jmp     loc_18000417E
```
