# CleanOldDevicesFromDeviceCache

- ea: `0x1400513e4`
- end: `0x1400517fc`
- name: `CleanOldDevicesFromDeviceCache`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14004f428`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x140004cec`
- `0x140004e48`
- `0x1400512ac`
- `0x1400513e4`
- `0x1400698ec`
- `0x14006998c`
- `0x140074084`
- `0x140074b70`
- `0x140074f18`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005176d`
- `ADVAPI32!RegCloseKey` at `0x1400517c7`
- `ADVAPI32!RegCloseKey` at `0x14005176d`
- `ADVAPI32!RegCloseKey` at `0x1400517c7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14005150c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14005150c`
- `ADVAPI32!RegEnumKeyExW` at `0x14005162d`
- `ADVAPI32!RegEnumKeyExW` at `0x14005162d`
- `KERNEL32!GetLastError` at `0x140051477`
- `KERNEL32!GetLastError` at `0x140051477`
- `msvcrt!swscanf` at `0x1400516f2`
- `msvcrt!swscanf` at `0x1400516f2`

## string_xrefs

- `0x140051454`: `Software\Microsoft\Fax\Devices Cache`
- `0x14005154b`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CleanOldDevicesFromDeviceCache(__int64 a1)
{
  HKEY v2; // r15
  DWORD LastError; // eax
  DWORD v4; // ebx
  WCHAR *v6; // r14
  unsigned int v7; // esi
  unsigned __int64 v8; // rcx
  DWORD i; // ecx
  HKEY v10; // rax
  HKEY v11; // r13
  unsigned __int64 *RegistryBinary; // r12
  _DWORD *j; // rdi
  __int64 v14; // rax
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-94h] BYREF
  unsigned __int64 *v16; // [rsp+68h] [rbp-90h] BYREF
  HKEY v17; // [rsp+70h] [rbp-88h]
  WCHAR *v18; // [rsp+78h] [rbp-80h]
  void *Block[3]; // [rsp+80h] [rbp-78h] BYREF
  unsigned __int64 v20; // [rsp+98h] [rbp-60h]
  HKEY v21; // [rsp+A0h] [rbp-58h]
  exception *v22; // [rsp+A8h] [rbp-50h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+100h] [rbp+8h] BYREF
  DWORD cchName; // [rsp+108h] [rbp+10h] BYREF
  unsigned int v25; // [rsp+110h] [rbp+18h] BYREF
  DWORD v26; // [rsp+118h] [rbp+20h]

  v25 = 0;
  cchName = 0;
  memset(Block, 0, sizeof(Block));
  cbMaxValueLen = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Devices Cache", 0, 0x20019u);
  v17 = v2;
  if ( v2 )
  {
    v6 = 0;
    cbMaxSubKeyLen = 0;
    v7 = RegQueryInfoKeyW(v2, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, &cbMaxValueLen, 0, 0);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          166,
          (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
          v7,
          (__int64)L"Software\\Microsoft\\Fax\\Devices Cache");
      }
    }
    else
    {
      v8 = 2LL * ++cbMaxSubKeyLen;
      if ( v8 > 0xFFFFFFFF )
      {
        v7 = 534;
      }
      else
      {
        v6 = (WCHAR *)pMemAlloc((unsigned int)v8);
        v18 = v6;
        if ( v6 )
        {
          v20 = a1 - 26784000000000LL;
          for ( i = 0; ; i = v26 + 1 )
          {
            v26 = i;
            cchName = cbMaxSubKeyLen;
            if ( RegEnumKeyExW(v2, i, v6, &cchName, 0, 0, 0, 0) )
              break;
            v10 = OpenRegistryKey(v2, v6, 0, 0x20019u);
            v11 = v10;
            v21 = v10;
            if ( v10 )
            {
              RegistryBinary = (unsigned __int64 *)GetRegistryBinary(v10, L"LastDetected", (DWORD *)&v16);
              v16 = RegistryBinary;
              if ( !RegistryBinary || *RegistryBinary < v20 )
              {
                if ( swscanf(v6, L"%lx", &v25) == 1 )
                {
                  try
                  {
                    std::vector<unsigned long>::push_back(Block, &v25);
                  }
                  catch ( exception *v22 )
                  {
                    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v14 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v22 + 8LL))(v22);
                      WPP_SF_s(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        169,
                        &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
                        v14);
                    }
                    SetLastError(8u);
                    pMemFree(v16);
                    RegCloseKey(v21);
                    v2 = v17;
                    v6 = v18;
                    goto LABEL_43;
                  }
                }
                else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
                }
              }
              pMemFree(RegistryBinary);
              RegCloseKey(v11);
            }
            else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v6);
            }
          }
          for ( j = Block[1]; Block[0] != j; Block[1] = j )
          {
            v25 = *--j;
            DeleteCacheEntry(v25);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
          }
          v7 = 8;
        }
      }
    }
LABEL_43:
    pMemFree(v6);
    RegCloseKey(v2);
    if ( Block[0] )
      operator delete(Block[0]);
    return v7;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        165,
        (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        LastError,
        (__int64)L"Software\\Microsoft\\Fax\\Devices Cache");
    }
    return v4;
  }
}

```

## disassembly

```asm
0x1400513e4  mov     rax, rsp
0x1400513e7  push    rbx
0x1400513e8  push    rsi
0x1400513e9  push    rdi
0x1400513ea  push    r12
0x1400513ec  push    r13
0x1400513ee  push    r14
0x1400513f0  push    r15
0x1400513f2  sub     rsp, 0C0h
0x1400513f9  mov     r12, rcx
0x1400513fc  xor     ebx, ebx
0x1400513fe  mov     [rax+18h], ebx
0x140051401  mov     [rax+10h], ebx
0x140051404  xorps   xmm0, xmm0
0x140051407  movdqu  xmmword ptr [rax-78h], xmm0
0x14005140c  mov     [rax-68h], rbx
0x140051410  mov     [rsp+0F8h+cbMaxValueLen], ebx
0x140051414  lea     r13, WPP_GLOBAL_Control
0x14005141b  mov     rcx, cs:WPP_GLOBAL_Control
0x140051422  mov     dil, 4
0x140051425  cmp     rcx, r13
0x140051428  jz      short loc_14005144B
0x14005142a  test    [rcx+1Ch], dil
0x14005142e  jz      short loc_14005144B
0x140051430  cmp     byte ptr [rcx+19h], 5
0x140051434  jb      short loc_14005144B
0x140051436  mov     edx, 0A4h
0x14005143b  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x140051442  mov     rcx, [rcx+10h]
0x140051446  call    WPP_SF_
0x14005144b  mov     r9d, 20019h
0x140051451  xor     r8d, r8d
0x140051454  lea     rsi, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14005145b  mov     rdx, rsi
0x14005145e  mov     rcx, 0FFFFFFFF80000002h
0x140051465  call    OpenRegistryKey
0x14005146a  mov     r15, rax
0x14005146d  mov     [rsp+0F8h+var_88], rax
0x140051472  test    rax, rax
0x140051475  jnz     short loc_1400514C2
0x140051477  call    cs:__imp_GetLastError
0x14005147e  nop     dword ptr [rax+rax+00h]
0x140051483  mov     ebx, eax
0x140051485  mov     rcx, cs:WPP_GLOBAL_Control
0x14005148c  cmp     rcx, r13
0x14005148f  jz      short loc_1400514BB
0x140051491  test    [rcx+1Ch], dil
0x140051495  jz      short loc_1400514BB
0x140051497  cmp     byte ptr [rcx+19h], 3
0x14005149b  jb      short loc_1400514BB
0x14005149d  mov     edx, 0A5h
0x1400514a2  mov     [rsp+0F8h+lpcSubKeys], rsi
0x1400514a7  mov     r9d, eax
0x1400514aa  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x1400514b1  mov     rcx, [rcx+10h]
0x1400514b5  call    WPP_SF_DS
0x1400514ba  nop
0x1400514bb  mov     eax, ebx
0x1400514bd  jmp     loc_1400517E8
0x1400514c2  mov     r14, rbx
0x1400514c5  mov     [rsp+0F8h+cbMaxSubKeyLen], ebx
0x1400514cc  mov     [rsp+0F8h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1400514d1  mov     [rsp+0F8h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1400514d6  lea     rax, [rsp+0F8h+cbMaxValueLen]
0x1400514db  mov     [rsp+0F8h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1400514e0  mov     [rsp+0F8h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x1400514e5  mov     [rsp+0F8h+lpcValues], rbx; lpcValues
0x1400514ea  mov     [rsp+0F8h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x1400514ef  lea     rax, [rsp+0F8h+cbMaxSubKeyLen]
0x1400514f7  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1400514fc  mov     [rsp+0F8h+lpcSubKeys], rbx; lpcSubKeys
0x140051501  xor     r9d, r9d; lpReserved
0x140051504  xor     r8d, r8d; lpcchClass
0x140051507  xor     edx, edx; lpClass
0x140051509  mov     rcx, r15; hKey
0x14005150c  call    cs:__imp_RegQueryInfoKeyW
0x140051513  nop     dword ptr [rax+rax+00h]
0x140051518  mov     esi, eax
0x14005151a  mov     [rsp+0F8h+var_98], eax
0x14005151e  test    eax, eax
0x140051520  jz      short loc_14005156F
0x140051522  mov     rcx, cs:WPP_GLOBAL_Control
0x140051529  cmp     rcx, r13
0x14005152c  jz      loc_1400517BC
0x140051532  test    [rcx+1Ch], dil
0x140051536  jz      loc_1400517BC
0x14005153c  cmp     byte ptr [rcx+19h], 2
0x140051540  jb      loc_1400517BC
0x140051546  mov     edx, 0A6h
0x14005154b  lea     rax, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x140051552  mov     [rsp+0F8h+lpcSubKeys], rax
0x140051557  mov     r9d, esi
0x14005155a  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x140051561  mov     rcx, [rcx+10h]
0x140051565  call    WPP_SF_DS
0x14005156a  jmp     loc_1400517BC
0x14005156f  mov     eax, [rsp+0F8h+cbMaxSubKeyLen]
0x140051576  inc     eax
0x140051578  mov     [rsp+0F8h+cbMaxSubKeyLen], eax
0x14005157f  mov     ecx, eax
0x140051581  add     rcx, rcx
0x140051584  mov     eax, 0FFFFFFFFh
0x140051589  cmp     rcx, rax
0x14005158c  ja      loc_1400517B7
0x140051592  mov     ecx, ecx; dwBytes
0x140051594  call    pMemAlloc
0x140051599  mov     r14, rax
0x14005159c  mov     [rsp+0F8h+var_80], rax
0x1400515a1  test    rax, rax
0x1400515a4  jnz     short loc_1400515DD
0x1400515a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400515ad  cmp     rcx, r13
0x1400515b0  jz      short loc_1400515D3
0x1400515b2  test    [rcx+1Ch], dil
0x1400515b6  jz      short loc_1400515D3
0x1400515b8  cmp     byte ptr [rcx+19h], 2
0x1400515bc  jb      short loc_1400515D3
0x1400515be  mov     edx, 0A7h
0x1400515c3  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x1400515ca  mov     rcx, [rcx+10h]
0x1400515ce  call    WPP_SF_
0x1400515d3  mov     esi, 8
0x1400515d8  jmp     loc_1400517BC
0x1400515dd  mov     rax, 0FFFFE7A3DD31C000h
0x1400515e7  add     rax, r12
0x1400515ea  mov     [rsp+0F8h+var_60], rax
0x1400515f2  mov     ecx, ebx
0x1400515f4  mov     eax, [rsp+0F8h+cbMaxSubKeyLen]
0x1400515fb  mov     [rsp+0F8h+arg_18], ecx
0x140051602  mov     [rsp+0F8h+cchName], eax
0x140051609  mov     [rsp+0F8h+lpcValues], rbx; lpftLastWriteTime
0x14005160e  mov     [rsp+0F8h+lpcbMaxClassLen], rbx; lpcchClass
0x140051613  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rbx; lpClass
0x140051618  mov     [rsp+0F8h+lpcSubKeys], rbx; lpReserved
0x14005161d  lea     r9, [rsp+0F8h+cchName]; lpcchName
0x140051625  mov     r8, r14; lpName
0x140051628  mov     edx, ecx; dwIndex
0x14005162a  mov     rcx, r15; hKey
0x14005162d  call    cs:__imp_RegEnumKeyExW
0x140051634  nop     dword ptr [rax+rax+00h]
0x140051639  test    eax, eax
0x14005163b  jnz     loc_140051787
0x140051641  mov     r9d, 20019h
0x140051647  xor     r8d, r8d
0x14005164a  mov     rdx, r14
0x14005164d  mov     rcx, r15
0x140051650  call    OpenRegistryKey
0x140051655  mov     r13, rax
0x140051658  mov     [rsp+0F8h+var_58], rax
0x140051660  test    rax, rax
0x140051663  jnz     short loc_1400516AD
0x140051665  mov     rcx, cs:WPP_GLOBAL_Control
0x14005166c  lea     rax, WPP_GLOBAL_Control
0x140051673  cmp     rcx, rax
0x140051676  jz      loc_140051779
0x14005167c  test    [rcx+1Ch], dil
0x140051680  jz      loc_140051779
0x140051686  cmp     byte ptr [rcx+19h], 3
0x14005168a  jb      loc_140051779
0x140051690  mov     edx, 0A8h
0x140051695  mov     r9, r14
0x140051698  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14005169f  mov     rcx, [rcx+10h]
0x1400516a3  call    WPP_SF_S
0x1400516a8  jmp     loc_140051779
0x1400516ad  lea     r8, [rsp+0F8h+var_90]
0x1400516b2  lea     rdx, aLastdetected; "LastDetected"
0x1400516b9  mov     rcx, r13; hKey
0x1400516bc  call    GetRegistryBinary
0x1400516c1  mov     r12, rax
0x1400516c4  mov     [rsp+0F8h+var_90], rax
0x1400516c9  test    rax, rax
0x1400516cc  jz      short loc_1400516E0
0x1400516ce  mov     rax, [rsp+0F8h+var_60]
0x1400516d6  cmp     [r12], rax
0x1400516da  jnb     loc_140051762
0x1400516e0  lea     r8, [rsp+0F8h+arg_10]
0x1400516e8  lea     rdx, aLx; "%lx"
0x1400516ef  mov     rcx, r14; Buffer
0x1400516f2  call    cs:__imp_swscanf
0x1400516f9  nop     dword ptr [rax+rax+00h]
0x1400516fe  cmp     eax, 1
0x140051701  jnz     short loc_14005172E
0x140051703  lea     rdx, [rsp+0F8h+arg_10]
0x14005170b  lea     rcx, [rsp+0F8h+Block]
0x140051713  call    ?push_back@?$vector@KV?$allocator@K@std@@@std@@QEAAXAEBK@Z; std::vector<ulong>::push_back(ulong const &)
0x140051718  nop
0x140051719  jmp     short loc_140051762
0x14005171b  mov     r15, [rsp+0F8h+var_88]
0x140051720  mov     esi, [rsp+0F8h+var_98]
0x140051724  mov     r14, [rsp+0F8h+var_80]
0x140051729  jmp     loc_1400517BC
0x14005172e  mov     rcx, cs:WPP_GLOBAL_Control
0x140051735  lea     rax, WPP_GLOBAL_Control
0x14005173c  cmp     rcx, rax
0x14005173f  jz      short loc_140051762
0x140051741  test    [rcx+1Ch], dil
0x140051745  jz      short loc_140051762
0x140051747  cmp     byte ptr [rcx+19h], 3
0x14005174b  jb      short loc_140051762
0x14005174d  mov     edx, 0AAh
0x140051752  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x140051759  mov     rcx, [rcx+10h]
0x14005175d  call    WPP_SF_
0x140051762  mov     rcx, r12; lpMem
0x140051765  call    pMemFree
0x14005176a  mov     rcx, r13; hKey
0x14005176d  call    cs:__imp_RegCloseKey
0x140051774  nop     dword ptr [rax+rax+00h]
0x140051779  mov     ecx, [rsp+0F8h+arg_18]
0x140051780  inc     ecx
0x140051782  jmp     loc_1400515F4
0x140051787  mov     rdi, [rsp+0F8h+var_70]
0x14005178f  cmp     [rsp+0F8h+Block], rdi
0x140051797  jz      short loc_1400517B5
0x140051799  add     rdi, 0FFFFFFFFFFFFFFFCh
0x14005179d  mov     ecx, [rdi]
0x14005179f  mov     [rsp+0F8h+arg_10], ecx
0x1400517a6  call    DeleteCacheEntry
0x1400517ab  mov     [rsp+0F8h+var_70], rdi
0x1400517b3  jmp     short loc_14005178F
0x1400517b5  jmp     short loc_1400517BC
0x1400517b7  mov     esi, 216h
0x1400517bc  mov     rcx, r14; lpMem
0x1400517bf  call    pMemFree
0x1400517c4  mov     rcx, r15; hKey
0x1400517c7  call    cs:__imp_RegCloseKey
0x1400517ce  nop     dword ptr [rax+rax+00h]
0x1400517d3  nop
0x1400517d4  mov     rcx, [rsp+0F8h+Block]; Block
0x1400517dc  test    rcx, rcx
0x1400517df  jz      short loc_1400517E6
0x1400517e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400517e6  mov     eax, esi
0x1400517e8  add     rsp, 0C0h
0x1400517ef  pop     r15
0x1400517f1  pop     r14
0x1400517f3  pop     r13
0x1400517f5  pop     r12
0x1400517f7  pop     rdi
0x1400517f8  pop     rsi
0x1400517f9  pop     rbx
0x1400517fa  retn
```
