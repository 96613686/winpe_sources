# winreMigrateDrivers(DismSessionClass &,DismSessionClass &,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,int)

- ea: `0x1800428d0`
- end: `0x180042b63`
- name: `?winreMigrateDrivers@@YAHAEAVDismSessionClass@@0AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@H@Z`
- size: `659`
- prototype: `__int64 __fastcall(struct DismSessionClass *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180042b6c`

## callees

- `0x1800059fc`
- `0x18001c448`
- `0x18001f47c`
- `0x180041248`
- `0x1800412d0`
- `0x1800413e4`
- `0x180041ccc`
- `0x180041d84`
- `0x180041dd4`
- `0x1800427fc`
- `0x1800428d0`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180042962`
- `msvcrt!_wcsicmp` at `0x180042a30`
- `msvcrt!_wcsicmp` at `0x180042962`
- `msvcrt!_wcsicmp` at `0x180042a30`
- `DismApi!DismAddDriver` at `0x180042a59`
- `DismApi!DismAddDriver` at `0x180042a59`
- `DismApi!DismCommitImage` at `0x180042b1b`
- `DismApi!DismCommitImage` at `0x180042b1b`

## string_xrefs

- `0x180042b28`: `winreMigrateDrivers   DismCommitImage error %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winreMigrateDrivers(struct DismSessionClass *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  unsigned int v6; // esi
  __int64 v7; // rbx
  int v8; // r15d
  int v9; // edx
  int v10; // ecx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // r8
  __int64 v20; // [rsp+20h] [rbp-79h]
  __int64 v21; // [rsp+28h] [rbp-71h]
  __int64 v22; // [rsp+30h] [rbp-69h]
  _QWORD v23[3]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v24[8]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v25[8]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v26[16]; // [rsp+68h] [rbp-31h] BYREF
  char v27; // [rsp+78h] [rbp-21h] BYREF
  int v28; // [rsp+80h] [rbp-19h] BYREF
  __int64 v29; // [rsp+88h] [rbp-11h]
  unsigned int v30; // [rsp+90h] [rbp-9h]
  _QWORD v31[2]; // [rsp+98h] [rbp-1h] BYREF

  v23[2] = -2;
  DismDriverList::DismDriverList((DismDriverList *)&v28, a1);
  if ( v28 < 0 )
  {
    v5 = 0;
    UnattendLogW(2, L"winreMigrateDrivers Session error 0x%x");
    goto LABEL_28;
  }
  v6 = 0;
  v5 = 1;
  if ( v30 )
  {
    while ( 1 )
    {
      v7 = 100LL * v6;
      winreGetInfName(v31, *(_QWORD *)(v7 + v29 + 8));
      v27 = 0;
      v8 = _wcsicmp(*(const wchar_t **)(v7 + v29 + 36), L"{F2E7DD72-6468-4E36-B6F1-6488F42C1B52}");
      v20 = std::char_traits<unsigned short>::length(L"apfiltr.inf");
      if ( (unsigned int)std::wstring::compare(v31) || *(_DWORD *)(v7 + v29 + 84) != 8 )
        break;
      v9 = *(_DWORD *)(v7 + v29 + 88);
      v10 = *(_DWORD *)(v7 + v29 + 96);
      if ( v9 == 103 )
      {
        if ( *(_DWORD *)(v7 + v29 + 92) != 909 || v10 != 108 && v10 != 111 )
          break;
      }
      else if ( v9 != 100
             || *(_DWORD *)(v7 + v29 + 92) != 909
             || v10 != 403 && (unsigned int)(v10 - 310) > 1 && v10 != 405 )
      {
        break;
      }
      LODWORD(v22) = *(_DWORD *)(v7 + v29 + 96);
      LODWORD(v21) = 909;
      LODWORD(v20) = *(_DWORD *)(v7 + v29 + 88);
      UnattendLogW(
        0,
        L"winreMigrateDriversBlocking driver: %ls Version: %d.%d.%d.%d",
        *(_QWORD *)(v7 + v29 + 8),
        8,
        v20,
        v21,
        v22);
LABEL_25:
      std::wstring::~wstring((__int64)v31, v16);
      if ( ++v6 >= v30 )
        goto LABEL_26;
    }
    v11 = (_QWORD *)std::list<std::wstring>::end(a3, v24);
    v13 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned __int64,_VDS_DISK_EXTENT,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_VDS_DISK_EXTENT>>,0>>::begin(
                      v12,
                      v25,
                      *v11);
    v23[0] = &v27;
    v23[1] = v31;
    std::for_each_std::_List_iterator_std::_List_val_std::_List_simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_fc8d3a99deae2929470c51cbcf45ea51___(
      v26,
      *v13,
      v14,
      v23,
      v20);
    v15 = v29;
    if ( *(_DWORD *)(v7 + v29 + 52) == 1 && !*(_DWORD *)(v7 + v29 + 16) && v8
      || v27
      || !_wcsicmp(*(const wchar_t **)(v7 + v29 + 36), L"{4D36E972-E325-11CE-BFC1-08002BE10318}")
      && (v15 = v29, !*(_DWORD *)(v7 + v29 + 16)) )
    {
      v17 = DismAddDriver(*(unsigned int *)(a2 + 4), *(_QWORD *)(v7 + v15 + 8), 1);
      v18 = *(_QWORD *)(v7 + v29 + 8);
      if ( v17 >= 0 )
        UnattendLogW(0, L"winreMigrateDrivers   DismAddDriver %ls", v18);
      else
        UnattendLogW(2, L"winreMigrateDrivers   DismAddDriver error %ls %x", v18, (unsigned int)v17);
    }
    goto LABEL_25;
  }
LABEL_26:
  if ( (int)DismCommitImage(*(unsigned int *)(a2 + 4), 0, 0, 0, 0) < 0 )
    UnattendLogW(2, L"winreMigrateDrivers   DismCommitImage error %x");
LABEL_28:
  DismDriverList::~DismDriverList((DismDriverList *)&v28);
  return v5;
}

```

## disassembly

```asm
0x1800428d0  push    rbp
0x1800428d2  push    rbx
0x1800428d3  push    rsi
0x1800428d4  push    rdi
0x1800428d5  push    r12
0x1800428d7  push    r14
0x1800428d9  push    r15
0x1800428db  lea     rbp, [rsp-27h]
0x1800428e0  sub     rsp, 0C0h
0x1800428e7  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1800428ef  mov     rax, cs:__security_cookie
0x1800428f6  xor     rax, rsp
0x1800428f9  mov     [rbp+57h+var_38], rax
0x1800428fd  mov     r12, r8
0x180042900  mov     r14, rdx
0x180042903  mov     rdx, rcx; struct DismSessionClass *
0x180042906  lea     rcx, [rbp+57h+var_70]; this
0x18004290a  call    ??0DismDriverList@@QEAA@AEAVDismSessionClass@@@Z; DismDriverList::DismDriverList(DismSessionClass &)
0x18004290f  nop
0x180042910  mov     r8d, [rbp+57h+var_70]
0x180042914  test    r8d, r8d
0x180042917  jns     short loc_180042927
0x180042919  xor     edi, edi
0x18004291b  lea     rdx, aWinremigratedr_2; "winreMigrateDrivers Session error 0x%x"
0x180042922  jmp     loc_180042B2F
0x180042927  xor     esi, esi
0x180042929  lea     edi, [rsi+1]
0x18004292c  cmp     [rbp+57h+var_60], esi
0x18004292f  jbe     loc_180042B06
0x180042935  mov     eax, esi
0x180042937  imul    rbx, rax, 64h ; 'd'
0x18004293b  mov     rdx, [rbp+57h+var_68]
0x18004293f  mov     rdx, [rbx+rdx+8]
0x180042944  lea     rcx, [rbp+57h+var_58]
0x180042948  call    ?winreGetInfName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; winreGetInfName(ushort const *)
0x18004294d  nop
0x18004294e  mov     [rbp+57h+var_78], 0
0x180042952  lea     rdx, aF2e7dd7264684e; "{F2E7DD72-6468-4E36-B6F1-6488F42C1B52}"
0x180042959  mov     rcx, [rbp+57h+var_68]
0x18004295d  mov     rcx, [rbx+rcx+24h]; String1
0x180042962  call    cs:__imp__wcsicmp
0x180042968  mov     r15d, eax
0x18004296b  lea     rcx, aApfiltrInf; "apfiltr.inf"
0x180042972  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180042977  mov     [rsp+0F0h+var_D0], rax
0x18004297c  lea     r9, aApfiltrInf; "apfiltr.inf"
0x180042983  mov     r8, [rbp+57h+var_48]
0x180042987  lea     rcx, [rbp+57h+var_58]
0x18004298b  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z; std::wstring::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180042990  test    eax, eax
0x180042992  jnz     short loc_1800429D0
0x180042994  mov     r8, [rbp+57h+var_68]
0x180042998  cmp     dword ptr [rbx+r8+54h], 8
0x18004299e  jnz     short loc_1800429D0
0x1800429a0  mov     edx, [rbx+r8+58h]
0x1800429a5  mov     ecx, [rbx+r8+60h]
0x1800429aa  cmp     edx, 67h ; 'g'
0x1800429ad  jnz     loc_180042A82
0x1800429b3  cmp     dword ptr [rbx+r8+5Ch], 38Dh
0x1800429bc  jnz     short loc_1800429D0
0x1800429be  cmp     ecx, 6Ch ; 'l'
0x1800429c1  jz      loc_180042AB8
0x1800429c7  cmp     ecx, 6Fh ; 'o'
0x1800429ca  jz      loc_180042AB8
0x1800429d0  lea     rdx, [rbp+57h+var_98]
0x1800429d4  mov     rcx, r12
0x1800429d7  call    ?end@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@XZ; std::list<std::wstring>::end(void)
0x1800429dc  mov     r8, [rax]
0x1800429df  lea     rdx, [rbp+57h+var_90]
0x1800429e3  call    ?begin@?$_Tree@V?$_Tmap_traits@_KU_VDS_DISK_EXTENT@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KU_VDS_DISK_EXTENT@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KU_VDS_DISK_EXTENT@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,_VDS_DISK_EXTENT,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_VDS_DISK_EXTENT>>,0>>::begin(void)
0x1800429e8  lea     rcx, [rbp+57h+var_78]
0x1800429ec  mov     [rbp+57h+var_B0], rcx
0x1800429f0  lea     rcx, [rbp+57h+var_58]
0x1800429f4  mov     [rbp+57h+var_A8], rcx
0x1800429f8  lea     r9, [rbp+57h+var_B0]
0x1800429fc  mov     rdx, [rax]
0x1800429ff  lea     rcx, [rbp+57h+var_88]
0x180042a03  call    std__for_each_std___List_iterator_std___List_val_std___List_simple_types_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________lambda_fc8d3a99deae2929470c51cbcf45ea51___
0x180042a08  mov     rax, [rbp+57h+var_68]
0x180042a0c  cmp     [rbx+rax+34h], edi
0x180042a10  jnz     short loc_180042A1E
0x180042a12  cmp     dword ptr [rbx+rax+10h], 0
0x180042a17  jnz     short loc_180042A1E
0x180042a19  test    r15d, r15d
0x180042a1c  jnz     short loc_180042A4D
0x180042a1e  cmp     [rbp+57h+var_78], 0
0x180042a22  jnz     short loc_180042A4D
0x180042a24  lea     rdx, a4d36e972E32511; "{4D36E972-E325-11CE-BFC1-08002BE10318}"
0x180042a2b  mov     rcx, [rbx+rax+24h]; String1
0x180042a30  call    cs:__imp__wcsicmp
0x180042a36  test    eax, eax
0x180042a38  jnz     loc_180042AF2
0x180042a3e  mov     rax, [rbp+57h+var_68]
0x180042a42  cmp     dword ptr [rbx+rax+10h], 0
0x180042a47  jnz     loc_180042AF2
0x180042a4d  mov     r8d, edi
0x180042a50  mov     rdx, [rbx+rax+8]
0x180042a55  mov     ecx, [r14+4]
0x180042a59  call    cs:__imp_DismAddDriver
0x180042a5f  mov     r8, [rbp+57h+var_68]
0x180042a63  mov     r8, [rbx+r8+8]
0x180042a68  test    eax, eax
0x180042a6a  jns     short loc_180042AE3
0x180042a6c  mov     r9d, eax
0x180042a6f  lea     rdx, aWinremigratedr_1; "winreMigrateDrivers   DismAddDriver err"...
0x180042a76  mov     ecx, 2
0x180042a7b  call    UnattendLogW
0x180042a80  jmp     short loc_180042AF2
0x180042a82  cmp     edx, 64h ; 'd'
0x180042a85  jnz     loc_1800429D0
0x180042a8b  cmp     dword ptr [rbx+r8+5Ch], 38Dh
0x180042a94  jnz     loc_1800429D0
0x180042a9a  cmp     ecx, 193h
0x180042aa0  jz      short loc_180042AB8
0x180042aa2  lea     eax, [rcx-136h]
0x180042aa8  cmp     eax, edi
0x180042aaa  jbe     short loc_180042AB8
0x180042aac  cmp     ecx, 195h
0x180042ab2  jnz     loc_1800429D0
0x180042ab8  mov     [rsp+0F0h+var_C0], ecx
0x180042abc  mov     dword ptr [rsp+0F0h+var_C8], 38Dh
0x180042ac4  mov     dword ptr [rsp+0F0h+var_D0], edx
0x180042ac8  mov     r9d, 8
0x180042ace  mov     r8, [rbx+r8+8]
0x180042ad3  lea     rdx, aWinremigratedr_3; "winreMigrateDriversBlocking driver: %ls"...
0x180042ada  xor     ecx, ecx
0x180042adc  call    UnattendLogW
0x180042ae1  jmp     short loc_180042AF2
0x180042ae3  lea     rdx, aWinremigratedr; "winreMigrateDrivers   DismAddDriver %ls"
0x180042aea  xor     ecx, ecx
0x180042aec  call    UnattendLogW
0x180042af1  nop
0x180042af2  lea     rcx, [rbp+57h+var_58]
0x180042af6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042afb  add     esi, edi
0x180042afd  cmp     esi, [rbp+57h+var_60]
0x180042b00  jb      loc_180042935
0x180042b06  mov     [rsp+0F0h+var_D0], 0
0x180042b0f  xor     r9d, r9d
0x180042b12  xor     r8d, r8d
0x180042b15  xor     edx, edx
0x180042b17  mov     ecx, [r14+4]
0x180042b1b  call    cs:__imp_DismCommitImage
0x180042b21  test    eax, eax
0x180042b23  jns     short loc_180042B3A
0x180042b25  mov     r8d, eax
0x180042b28  lea     rdx, aWinremigratedr_0; "winreMigrateDrivers   DismCommitImage e"...
0x180042b2f  mov     ecx, 2
0x180042b34  call    UnattendLogW
0x180042b39  nop
0x180042b3a  lea     rcx, [rbp+57h+var_70]; this
0x180042b3e  call    ??1DismDriverList@@QEAA@XZ; DismDriverList::~DismDriverList(void)
0x180042b43  mov     eax, edi
0x180042b45  mov     rcx, [rbp+57h+var_38]
0x180042b49  xor     rcx, rsp; StackCookie
0x180042b4c  call    __security_check_cookie
0x180042b51  add     rsp, 0C0h
0x180042b58  pop     r15
0x180042b5a  pop     r14
0x180042b5c  pop     r12
0x180042b5e  pop     rdi
0x180042b5f  pop     rsi
0x180042b60  pop     rbx
0x180042b61  pop     rbp
0x180042b62  retn
```
