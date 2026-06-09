# Netbios_OnPrepareTransaction

- ea: `0x18001c010`
- end: `0x18001c1f0`
- name: `Netbios_OnPrepareTransaction`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180005580`
- `0x18000e970`
- `0x18000ed1c`
- `0x180010200`
- `0x180017320`
- `0x18001c010`
- `0x18001df48`
- `0x180028548`
- `0x180028db4`
- `0x18005565c`
- `0x18005a378`
- `0x18005c988`
- `0x180064704`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1d5`

## string_xrefs

- `0x18001c0e6`: `Services\Netbios\Parameters`
- `0x18001c0b6`: `Services\Netbios\Linkage`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Netbios_OnPrepareTransaction(__int64 a1, struct HNETSETUP__ **a2, __int64 a3)
{
  int v4; // ebx
  struct NetSetupOperation *OperationFromHandle; // rax
  int v6; // r8d
  char v7; // bl
  unsigned __int64 v8; // rdx
  unsigned __int8 *v9; // rbx
  unsigned __int64 v10; // rdi
  unsigned int v11; // eax
  __int64 v12; // rcx
  int v13; // r8d
  HKEY v14; // [rsp+48h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-21h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-19h] BYREF
  __int64 v17; // [rsp+68h] [rbp-9h]
  unsigned __int64 v18; // [rsp+70h] [rbp-1h]
  _QWORD v19[4]; // [rsp+78h] [rbp+7h] BYREF
  char v20[8]; // [rsp+98h] [rbp+27h] BYREF
  char v21[32]; // [rsp+A0h] [rbp+2Fh] BYREF
  char v22; // [rsp+C0h] [rbp+4Fh]

  v19[3] = -2;
  v4 = (int)a2;
  OperationFromHandle = NetSetupPluginApi::GetOperationFromHandle(*a2);
  if ( (unsigned __int8)IsNetSetupTheCurrentBindingEngine(*(_QWORD *)OperationFromHandle) )
  {
    std::wstring::wstring(Block, L"ms_netbios");
    NetSetup2::details::TryGetObjectByIdentifierInner<NetSetup2::ServiceDriver>((__int64)v20, v4, v6, Block);
    v7 = v22;
    if ( v22 )
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v21);
    if ( v18 >= 8 )
      operator delete(Block[0]);
    if ( v7 )
    {
      RegistryKey::CreateSubKey((HKEY *)(*(_QWORD *)a3 + 24LL), (HKEY)&v14, L"Services\\Netbios\\Linkage", 3u, 0, 0);
      RegistryKey::CreateSubKey((HKEY *)(*(_QWORD *)a3 + 24LL), (HKEY)&hKey, L"Services\\Netbios\\Parameters", 2u, 0, 0);
      RegistryKey::GetValueMultiString(&v14, v19, L"Bind");
      *(_OWORD *)Block = 0;
      v17 = 0;
      v8 = (__int64)(v19[1] - v19[0]) >> 5;
      if ( v8 > 0xFE )
        v8 = 254;
      std::vector<REG_LANA_ENTRY>::resize(Block, v8);
      v9 = (unsigned __int8 *)Block[0];
      v10 = ((char *)Block[1] - (char *)Block[0]) >> 1;
      if ( v10 )
      {
        v11 = 0;
        v12 = 0;
        do
        {
          v9[2 * v12 + 1] = v11;
          v9[2 * v12] = 1;
          v12 = ++v11;
        }
        while ( v11 < v10 );
      }
      if ( v9 == Block[1] )
        v13 = 0;
      else
        v13 = v10 - 1;
      RegistryKey::SetValue((RegistryKey *)&hKey, L"MaxLana", v13, 0);
      RegistryKey::SetValue(&v14, L"LanaMap", v9, 2 * v10, 3u);
      if ( v9 )
        operator delete(v9);
      std::vector<std::wstring>::_Tidy(v19);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v14 )
        RegCloseKey(v14);
    }
  }
}

```

## disassembly

```asm
0x18001c010  mov     rax, rsp
0x18001c013  push    rbp
0x18001c014  lea     rbp, [rax-5Fh]
0x18001c018  sub     rsp, 0C0h
0x18001c01f  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFEh
0x18001c027  mov     [rax+8], rbx
0x18001c02b  mov     [rax+20h], rdi
0x18001c02f  mov     rdi, r8
0x18001c032  mov     rbx, rdx
0x18001c035  mov     rcx, [rdx]; struct HNETSETUP__ *
0x18001c038  call    ?GetOperationFromHandle@NetSetupPluginApi@@SAPEAVNetSetupOperation@@PEAUHNETSETUP__@@@Z; NetSetupPluginApi::GetOperationFromHandle(HNETSETUP__ *)
0x18001c03d  mov     rcx, [rax]
0x18001c040  call    IsNetSetupTheCurrentBindingEngine
0x18001c045  test    al, al
0x18001c047  jz      loc_18001C1DB
0x18001c04d  lea     rdx, aMsNetbios_0; "ms_netbios"
0x18001c054  lea     rcx, [rbp+57h+Block]
0x18001c058  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18001c05d  nop
0x18001c05e  lea     r9, [rbp+57h+Block]
0x18001c062  mov     rdx, rbx
0x18001c065  lea     rcx, [rbp+57h+var_30]
0x18001c069  call    ??$TryGetObjectByIdentifierInner@VServiceDriver@NetSetup2@@@details@NetSetup2@@YA?AV?$Optional@VServiceDriver@NetSetup2@@@01@AEBVTransactionBase@01@W4_NETSETUP_OBJECT_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetup2::details::TryGetObjectByIdentifierInner<NetSetup2::ServiceDriver>(NetSetup2::details::TransactionBase const &,_NETSETUP_OBJECT_TYPE,std::wstring const &)
0x18001c06e  mov     bl, [rbp+57h+var_8]
0x18001c071  test    bl, bl
0x18001c073  jz      short loc_18001C07F
0x18001c075  lea     rcx, [rbp+57h+var_28]
0x18001c079  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18001c07e  nop
0x18001c07f  cmp     [rbp+57h+var_58], 8
0x18001c084  jb      short loc_18001C08F
0x18001c086  mov     rcx, [rbp+57h+Block]; Block
0x18001c08a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c08f  test    bl, bl
0x18001c091  jz      loc_18001C1DB
0x18001c097  mov     rcx, [rdi]
0x18001c09a  add     rcx, 18h
0x18001c09e  mov     [rsp+0C0h+var_98], 0
0x18001c0a7  mov     qword ptr [rsp+0C0h+var_A0], 0
0x18001c0b0  mov     r9d, 3
0x18001c0b6  lea     r8, aServicesNetbio; "Services\\Netbios\\Linkage"
0x18001c0bd  lea     rdx, [rbp+57h+var_80]
0x18001c0c1  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x18001c0c6  nop
0x18001c0c7  mov     rcx, [rdi]
0x18001c0ca  add     rcx, 18h
0x18001c0ce  mov     [rsp+0C0h+var_98], 0
0x18001c0d7  mov     qword ptr [rsp+0C0h+var_A0], 0
0x18001c0e0  mov     r9d, 2
0x18001c0e6  lea     r8, aServicesNetbio_0; "Services\\Netbios\\Parameters"
0x18001c0ed  lea     rdx, [rbp+57h+hKey]
0x18001c0f1  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x18001c0f6  nop
0x18001c0f7  lea     r8, aBind; "Bind"
0x18001c0fe  lea     rdx, [rbp+57h+var_50]
0x18001c102  lea     rcx, [rbp+57h+var_80]
0x18001c106  call    ?GetValueMultiString@RegistryKey@@QEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEB_W@Z; RegistryKey::GetValueMultiString(wchar_t const *)
0x18001c10b  nop
0x18001c10c  xorps   xmm0, xmm0
0x18001c10f  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x18001c114  mov     [rbp+57h+var_60], 0
0x18001c11c  mov     rdx, [rbp+57h+var_48]
0x18001c120  sub     rdx, [rbp+57h+var_50]
0x18001c124  sar     rdx, 5
0x18001c128  mov     eax, 0FEh
0x18001c12d  cmp     rdx, rax
0x18001c130  cmova   rdx, rax
0x18001c134  lea     rcx, [rbp+57h+Block]
0x18001c138  call    ?resize@?$vector@UREG_LANA_ENTRY@@V?$allocator@UREG_LANA_ENTRY@@@std@@@std@@QEAAX_K@Z; std::vector<REG_LANA_ENTRY>::resize(unsigned __int64)
0x18001c13d  mov     rdi, [rbp+57h+Block+8]
0x18001c141  mov     rbx, [rbp+57h+Block]
0x18001c145  sub     rdi, rbx
0x18001c148  sar     rdi, 1
0x18001c14b  jz      short loc_18001C162
0x18001c14d  xor     eax, eax
0x18001c14f  xor     ecx, ecx
0x18001c151  mov     [rbx+rcx*2+1], al
0x18001c155  mov     byte ptr [rbx+rcx*2], 1
0x18001c159  inc     eax
0x18001c15b  mov     ecx, eax
0x18001c15d  cmp     rcx, rdi
0x18001c160  jb      short loc_18001C151
0x18001c162  cmp     rbx, [rbp+57h+Block+8]
0x18001c166  jnz     short loc_18001C16D
0x18001c168  xor     r8d, r8d
0x18001c16b  jmp     short loc_18001C171
0x18001c16d  lea     r8d, [rdi-1]
0x18001c171  xor     r9d, r9d
0x18001c174  lea     rdx, aMaxlana; "MaxLana"
0x18001c17b  lea     rcx, [rbp+57h+hKey]
0x18001c17f  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18001c184  lea     r9, [rdi+rdi]; unsigned __int64
0x18001c188  mov     [rsp+0C0h+var_A0], 3; unsigned int
0x18001c190  mov     r8, rbx; unsigned __int8 *
0x18001c193  lea     rdx, aLanamap; "LanaMap"
0x18001c19a  lea     rcx, [rbp+57h+var_80]; this
0x18001c19e  call    ?SetValue@RegistryKey@@QEBAXPEB_WPEBE_KK@Z; RegistryKey::SetValue(wchar_t const *,uchar const *,unsigned __int64,ulong)
0x18001c1a3  nop
0x18001c1a4  test    rbx, rbx
0x18001c1a7  jz      short loc_18001C1B2
0x18001c1a9  mov     rcx, rbx; Block
0x18001c1ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c1b1  nop
0x18001c1b2  lea     rcx, [rbp+57h+var_50]
0x18001c1b6  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001c1bb  nop
0x18001c1bc  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c1c0  test    rcx, rcx
0x18001c1c3  jz      short loc_18001C1CC
0x18001c1c5  call    cs:__imp_RegCloseKey
0x18001c1cb  nop
0x18001c1cc  mov     rcx, [rbp+57h+var_80]; hKey
0x18001c1d0  test    rcx, rcx
0x18001c1d3  jz      short loc_18001C1DB
0x18001c1d5  call    cs:__imp_RegCloseKey
0x18001c1db  lea     r11, [rsp+0C0h+var_s0]
0x18001c1e3  mov     rbx, [r11+10h]
0x18001c1e7  mov     rdi, [r11+28h]
0x18001c1eb  mov     rsp, r11
0x18001c1ee  pop     rbp
0x18001c1ef  retn
```
