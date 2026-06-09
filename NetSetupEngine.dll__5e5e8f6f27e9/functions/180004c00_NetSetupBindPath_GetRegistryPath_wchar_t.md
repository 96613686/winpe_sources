# NetSetupBindPath::GetRegistryPath(wchar_t *)

- ea: `0x180004c00`
- end: `0x180004d8a`
- name: `?GetRegistryPath@NetSetupBindPath@@QEAAXPEA_W@Z`
- size: `394`
- prototype: `void(NetSetupBindPath *__hidden this, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180017df8`

## callees

- `0x180004c00`
- `0x180005660`
- `0x180029d20`
- `0x180064704`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180004c4c`
- `msvcrt!swprintf_s` at `0x180004ce4`
- `msvcrt!swprintf_s` at `0x180004c4c`
- `msvcrt!swprintf_s` at `0x180004ce4`
- `msvcrt!wcscat_s` at `0x180004d3c`
- `msvcrt!wcscat_s` at `0x180004d69`
- `msvcrt!wcscat_s` at `0x180004d3c`
- `msvcrt!wcscat_s` at `0x180004d69`

## string_xrefs

- `0x180004c3d`: `Control\NetworkSetup2\BindPaths\%ws`
- `0x180004c9a`: `Protocols`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupBindPath::GetRegistryPath(NetSetupBindPath *this, wchar_t *a2)
{
  int v4; // ecx
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  __int64 v8; // rdx
  const wchar_t *v9; // rbp
  _QWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  void *Block[4]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v16[80]; // [rsp+58h] [rbp-50h] BYREF

  v4 = *((_DWORD *)this + 30);
  if ( v4 )
  {
    if ( v4 == 1 )
    {
      v6 = (_QWORD *)StringFromGuid(v16, *((_QWORD *)this + 10) + 24LL);
      v7 = v6;
      if ( v6[3] >= 8u )
        v7 = (_QWORD *)*v6;
      v8 = *((_QWORD *)this + 10);
      v9 = L"Filters";
      if ( *(_DWORD *)(v8 + 20) != 3 )
        v9 = L"Protocols";
      v10 = (_QWORD *)StringFromGuid(Block, v8 + 4);
      if ( v10[3] >= 8u )
        v10 = (_QWORD *)*v10;
      swprintf_s(a2, 0x104u, L"Networking\\NetAdapters\\%ws\\Bindings\\%ws\\%ws", v10, v9, v7, -2);
      LOBYTE(v11) = 1;
      std::wstring::_Tidy(Block, v11, 0);
      LOBYTE(v12) = 1;
      std::wstring::_Tidy(v16, v12, 0);
      if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) >> 2) > 2 )
      {
        wcscat_s(a2, 0x104u, L"-");
        v13 = StringFromGuid(v16, *((_QWORD *)this + 10) + 44LL);
        if ( *(_QWORD *)(v13 + 24) >= 8u )
          v13 = *(_QWORD *)v13;
        wcscat_s(a2, 0x104u, (const wchar_t *)v13);
        LOBYTE(v14) = 1;
        std::wstring::_Tidy(v16, v14, 0);
      }
    }
  }
  else
  {
    v5 = (_QWORD *)StringFromGuid(Block, (char *)this + 32);
    if ( v5[3] >= 8u )
      v5 = (_QWORD *)*v5;
    swprintf_s(a2, 0x104u, L"Control\\NetworkSetup2\\BindPaths\\%ws", v5);
    if ( Block[3] >= (void *)8 )
      operator delete(Block[0]);
  }
}

```

## disassembly

```asm
0x180004c00  push    rbx
0x180004c02  push    rbp
0x180004c03  push    rsi
0x180004c04  push    rdi
0x180004c05  sub     rsp, 88h
0x180004c0c  mov     [rsp+0A8h+var_78], 0FFFFFFFFFFFFFFFEh
0x180004c15  mov     rdi, rdx
0x180004c18  mov     rbx, rcx
0x180004c1b  mov     ecx, [rcx+78h]
0x180004c1e  test    ecx, ecx
0x180004c20  jnz     short loc_180004C72
0x180004c22  lea     rdx, [rbx+20h]
0x180004c26  lea     rcx, [rsp+0A8h+Block]
0x180004c2b  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180004c30  cmp     qword ptr [rax+18h], 8
0x180004c35  jb      short loc_180004C3A
0x180004c37  mov     rax, [rax]
0x180004c3a  mov     r9, rax
0x180004c3d  lea     r8, aControlNetwork; "Control\\NetworkSetup2\\BindPaths\\%ws"
0x180004c44  mov     edx, 104h; BufferCount
0x180004c49  mov     rcx, rdi; Buffer
0x180004c4c  call    cs:__imp_swprintf_s
0x180004c52  cmp     [rsp+0A8h+var_58], 8
0x180004c58  jnb     short loc_180004C66
0x180004c5a  add     rsp, 88h
0x180004c61  pop     rdi
0x180004c62  pop     rsi
0x180004c63  pop     rbp
0x180004c64  pop     rbx
0x180004c65  retn
0x180004c66  mov     rcx, [rsp+0A8h+Block]; Block
0x180004c6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c70  jmp     short loc_180004C5A
0x180004c72  cmp     ecx, 1
0x180004c75  jnz     short loc_180004C5A
0x180004c77  mov     rdx, [rbx+50h]
0x180004c7b  add     rdx, 18h
0x180004c7f  lea     rcx, [rsp+0A8h+var_50]
0x180004c84  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180004c89  mov     rsi, rax
0x180004c8c  cmp     qword ptr [rax+18h], 8
0x180004c91  jb      short loc_180004C96
0x180004c93  mov     rsi, [rax]
0x180004c96  mov     rdx, [rbx+50h]
0x180004c9a  lea     rax, aProtocols; "Protocols"
0x180004ca1  lea     rbp, aFilters; "Filters"
0x180004ca8  cmp     dword ptr [rdx+14h], 3
0x180004cac  cmovnz  rbp, rax
0x180004cb0  add     rdx, 4
0x180004cb4  lea     rcx, [rsp+0A8h+Block]
0x180004cb9  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180004cbe  cmp     qword ptr [rax+18h], 8
0x180004cc3  jb      short loc_180004CC8
0x180004cc5  mov     rax, [rax]
0x180004cc8  mov     [rsp+0A8h+var_80], rsi
0x180004ccd  mov     [rsp+0A8h+var_88], rbp
0x180004cd2  mov     r9, rax
0x180004cd5  lea     r8, aNetworkingNeta_0; "Networking\\NetAdapters\\%ws\\Bindings"...
0x180004cdc  mov     edx, 104h; BufferCount
0x180004ce1  mov     rcx, rdi; Buffer
0x180004ce4  call    cs:__imp_swprintf_s
0x180004cea  xor     r8d, r8d
0x180004ced  mov     dl, 1
0x180004cef  lea     rcx, [rsp+0A8h+Block]
0x180004cf4  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004cf9  nop
0x180004cfa  xor     r8d, r8d
0x180004cfd  mov     dl, 1
0x180004cff  lea     rcx, [rsp+0A8h+var_50]
0x180004d04  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004d09  mov     rax, [rbx+58h]
0x180004d0d  sub     rax, [rbx+50h]
0x180004d11  sar     rax, 2
0x180004d15  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180004d1f  imul    rax, rcx
0x180004d23  cmp     rax, 2
0x180004d27  jbe     loc_180004C5A
0x180004d2d  lea     r8, asc_18009A088; "-"
0x180004d34  mov     edx, 104h; SizeInWords
0x180004d39  mov     rcx, rdi; Destination
0x180004d3c  call    cs:__imp_wcscat_s
0x180004d42  mov     rdx, [rbx+50h]
0x180004d46  add     rdx, 2Ch ; ','
0x180004d4a  lea     rcx, [rsp+0A8h+var_50]
0x180004d4f  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180004d54  cmp     qword ptr [rax+18h], 8
0x180004d59  jb      short loc_180004D5E
0x180004d5b  mov     rax, [rax]
0x180004d5e  mov     r8, rax; Source
0x180004d61  mov     edx, 104h; SizeInWords
0x180004d66  mov     rcx, rdi; Destination
0x180004d69  call    cs:__imp_wcscat_s
0x180004d6f  xor     r8d, r8d
0x180004d72  mov     dl, 1
0x180004d74  lea     rcx, [rsp+0A8h+var_50]
0x180004d79  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004d7e  add     rsp, 88h
0x180004d85  pop     rdi
0x180004d86  pop     rsi
0x180004d87  pop     rbp
0x180004d88  pop     rbx
0x180004d89  retn
```
