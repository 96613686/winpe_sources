# ValidatePcrMatchesLog(void)

- ea: `0x18001dd80`
- end: `0x18001e1cd`
- name: `?ValidatePcrMatchesLog@@YAXXZ`
- size: `1101`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800166dc`

## callees

- `0x1800078b0`
- `0x1800085b0`
- `0x180009768`
- `0x18000b23c`
- `0x18000d568`
- `0x18000d8b0`
- `0x18000e48c`
- `0x180014d38`
- `0x18001800c`
- `0x18001c49c`
- `0x18001dd80`
- `0x18002382c`
- `0x18002386c`
- `0x180043d8c`
- `0x180043e8c`
- `0x180043fc8`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18001ddac`
- `msvcp_win!_Xtime_get_ticks` at `0x18001e12d`
- `msvcp_win!_Xtime_get_ticks` at `0x18001ddac`
- `msvcp_win!_Xtime_get_ticks` at `0x18001e12d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001de4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001df15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001dff4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e127`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001de4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001df15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001dff4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e127`
- `TpmCoreProvisioning!TpmGetPcrValuesFromHardware` at `0x18001dddc`
- `TpmCoreProvisioning!TpmGetPcrValuesFromHardware` at `0x18001ddfe`
- `TpmCoreProvisioning!TpmGetPcrValuesFromHardware` at `0x18001dddc`
- `TpmCoreProvisioning!TpmGetPcrValuesFromHardware` at `0x18001ddfe`
- `TpmCoreProvisioning!TpmGetInformationFromTcgLog` at `0x18001de9f`
- `TpmCoreProvisioning!TpmGetInformationFromTcgLog` at `0x18001dee9`
- `TpmCoreProvisioning!TpmGetInformationFromTcgLog` at `0x18001de9f`
- `TpmCoreProvisioning!TpmGetInformationFromTcgLog` at `0x18001dee9`

## string_xrefs

- `0x18001de28`: `PhysicalPcrRead`
- `0x18001de42`: `PhysicalPcrReadError`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void ValidatePcrMatchesLog(void)
{
  HKEY WbclInstanceKey; // rbx
  int v1; // edi
  __int64 v2; // r14
  int v3; // esi
  int v4; // r15d
  int v5; // r12d
  int v6; // r13d
  __int64 v7; // rcx
  unsigned __int8 *v8; // rdi
  BYTE *v9; // r12
  __int64 v10; // rsi
  __int64 v11; // rdi
  int v12; // edi
  char *v13; // r13
  unsigned int v14; // esi
  __int64 v15; // r15
  unsigned int v16; // r14d
  unsigned int i; // esi
  BYTE *v18; // rax
  const WCHAR *v19; // rdx
  unsigned __int16 v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v21[4]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v23; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE lpData[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+5Ch] [rbp-A4h]
  unsigned int v28; // [rsp+60h] [rbp-A0h]
  __int64 ticks; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  void *Buf2; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v35; // [rsp+A8h] [rbp-58h] BYREF
  int v36; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v37; // [rsp+C0h] [rbp-40h] BYREF
  int v38; // [rsp+C8h] [rbp-38h]
  unsigned __int8 *v39[3]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v40[32]; // [rsp+F0h] [rbp-10h] BYREF

  TpmTaskDebugProvider::TpmTaskCheckPcrInformationStarted();
  ticks = _Xtime_get_ticks();
  WbclInstanceKey = GetWbclInstanceKey();
  hKey = WbclInstanceKey;
  v22 = 0;
  v20[0] = 0;
  TpmGetPcrValuesFromHardware(v20, &v22, 0);
  std::vector<unsigned char>::vector<unsigned char>(&Buf2, v22);
  *(_DWORD *)Data = TpmGetPcrValuesFromHardware(v20, &v22, (unsigned __int8 *)Buf2);
  if ( *(int *)Data < 0 )
    RegSetValueExW(WbclInstanceKey, L"PhysicalPcrReadError", 0, 4u, Data, 4u);
  else
    RegSetValueExW(WbclInstanceKey, L"PhysicalPcrRead", 0, 3u, (const BYTE *)Buf2, v34 - (_DWORD)Buf2);
  ReadWbclType(&v37, 0);
  ReadWbclType(&v35, 1);
  v23 = 0;
  TpmGetInformationFromTcgLog(v20[0], v38 - (_DWORD)v37, v37, v36 - (_DWORD)v35, v35, &v23, 0);
  *(_DWORD *)lpData = 0;
  std::vector<unsigned char>::vector<unsigned char>(v39, v23);
  *(_DWORD *)lpData = TpmGetInformationFromTcgLog(v20[0], v38 - (_DWORD)v37, v37, v36 - (_DWORD)v35, v35, &v23, v39[0]);
  if ( *(int *)lpData >= 0 )
  {
    *(_DWORD *)v21 = *(_DWORD *)(v39[0] + 1);
    v27 = *(_DWORD *)(v39[0] + 5);
    v1 = v39[0][10];
    v2 = *(_QWORD *)(v39[0] + 11);
    v3 = v39[0][19];
    v4 = v39[0][20];
    v5 = v39[0][21];
    v6 = v39[0][22];
    v28 = *(_DWORD *)(v39[0] + 23);
    v26 = *(_DWORD *)(v39[0] + 27);
    HWSecurityRegistryManager::SetDWordNoThrow(0x22u, v39[0][9]);
    HWSecurityRegistryManager::SetDWordNoThrow(0x20u, v1);
    HWSecurityRegistryManager::SetDWordNoThrow(0x23u, v3);
    HWSecurityRegistryManager::SetQWordNoThrow(v7, v2);
    HWSecurityRegistryManager::SetDWordNoThrow(0x1Bu, v4);
    HWSecurityRegistryManager::SetDWordNoThrow(0x1Fu, v5);
    HWSecurityRegistryManager::SetDWordNoThrow(0x1Cu, v6);
    v8 = &v39[0][*(unsigned int *)v21];
    std::vector<unsigned char>::vector<unsigned char>(&v31, v8, &v8[v27]);
    RegSetValueExW(WbclInstanceKey, L"ReplayPcr", 0, 3u, v31, v32 - (_DWORD)v31);
    v9 = v31;
    v10 = v8 - v31 + v32;
    if ( v28 )
    {
      v11 = v28;
      std::wstring::wstring(v40, v10, v28);
      v10 += 2 * v11;
      HWSecurityRegistryManager::SetStringNoThrow(30, v40);
      std::wstring::_Tidy_deallocate(v40);
      v9 = v31;
    }
    if ( v26 )
    {
      std::wstring::wstring(v40, v10, v26);
      HWSecurityRegistryManager::SetStringNoThrow(29, v40);
      std::wstring::_Tidy_deallocate(v40);
      v9 = v31;
    }
    if ( *(int *)Data >= 0 )
    {
      v12 = 0;
      *(_DWORD *)v21 = 0;
      v13 = (char *)Buf2;
      v14 = v34 - (_DWORD)Buf2;
      if ( !memcmp_0(v9, Buf2, v34 - (_QWORD)Buf2) )
        goto LABEL_18;
      v15 = 0;
      v16 = v14 / 0x18;
      for ( i = 0; i < 0x18; ++i )
      {
        if ( memcmp_0(&v9[v15], &v13[v15], v16) )
        {
          v12 |= 1 << i;
          *(_DWORD *)v21 = v12;
        }
        v15 = v16 + (unsigned int)v15;
      }
      WbclInstanceKey = hKey;
      if ( !v12 )
      {
LABEL_18:
        v26 = 1;
        v18 = (BYTE *)&v26;
        v19 = L"PcrsMatched";
      }
      else
      {
        v18 = v21;
        v19 = L"MismatchedPcrsMask";
      }
      RegSetValueExW(WbclInstanceKey, v19, 0, 4u, v18, 4u);
    }
    ticks = (_Xtime_get_ticks() - ticks) / 10000;
    TpmTaskDebugProvider::TpmTaskCheckPcrInformationEnded<__int64,long &,long &>(&ticks, (int *)Data, (int *)lpData);
    std::vector<unsigned char>::_Tidy(&v31);
  }
  else
  {
    RegSetValueExW(WbclInstanceKey, L"ReplayPcrError", 0, 4u, lpData, 4u);
  }
  std::vector<unsigned char>::_Tidy(v39);
  std::vector<unsigned char>::_Tidy(&v35);
  std::vector<unsigned char>::_Tidy(&v37);
  std::vector<unsigned char>::_Tidy(&Buf2);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18001dd80  push    rbp
0x18001dd82  push    rbx
0x18001dd83  push    rsi
0x18001dd84  push    rdi
0x18001dd85  push    r12
0x18001dd87  push    r13
0x18001dd89  push    r14
0x18001dd8b  push    r15
0x18001dd8d  lea     rbp, [rsp-28h]
0x18001dd92  sub     rsp, 128h
0x18001dd99  mov     rax, cs:__security_cookie
0x18001dda0  xor     rax, rsp
0x18001dda3  mov     [rbp+60h+var_50], rax
0x18001dda7  call    ?TpmTaskCheckPcrInformationStarted@TpmTaskDebugProvider@@SAXXZ; TpmTaskDebugProvider::TpmTaskCheckPcrInformationStarted(void)
0x18001ddac  call    cs:__imp__Xtime_get_ticks
0x18001ddb2  mov     [rsp+160h+var_F8], rax
0x18001ddb7  call    ?GetWbclInstanceKey@@YAPEAUHKEY__@@XZ; GetWbclInstanceKey(void)
0x18001ddbc  mov     rbx, rax
0x18001ddbf  mov     [rsp+160h+hKey], rax
0x18001ddc4  xor     edi, edi
0x18001ddc6  mov     [rsp+160h+var_118], edi
0x18001ddca  mov     [rsp+160h+var_120], di
0x18001ddcf  xor     r8d, r8d
0x18001ddd2  lea     rdx, [rsp+160h+var_118]
0x18001ddd7  lea     rcx, [rsp+160h+var_120]
0x18001dddc  call    cs:__imp_?TpmGetPcrValuesFromHardware@@YAJPEAGPEAIPEAE@Z; TpmGetPcrValuesFromHardware(ushort *,uint *,uchar *)
0x18001dde2  mov     edx, [rsp+160h+var_118]
0x18001dde6  lea     rcx, [rbp+60h+Buf2]
0x18001ddea  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18001ddef  nop
0x18001ddf0  mov     r8, [rbp+60h+Buf2]
0x18001ddf4  lea     rdx, [rsp+160h+var_118]
0x18001ddf9  lea     rcx, [rsp+160h+var_120]
0x18001ddfe  call    cs:__imp_?TpmGetPcrValuesFromHardware@@YAJPEAGPEAIPEAE@Z; TpmGetPcrValuesFromHardware(ushort *,uint *,uchar *)
0x18001de04  mov     dword ptr [rsp+160h+Data], eax
0x18001de08  lea     esi, [rdi+4]
0x18001de0b  xor     r8d, r8d; Reserved
0x18001de0e  test    eax, eax
0x18001de10  js      short loc_18001DE31
0x18001de12  mov     eax, dword ptr [rbp+60h+var_C8]
0x18001de15  mov     rcx, [rbp+60h+Buf2]
0x18001de19  sub     eax, ecx
0x18001de1b  mov     [rsp+160h+cbData], eax
0x18001de1f  mov     [rsp+160h+lpData], rcx
0x18001de24  lea     r9d, [rdi+3]
0x18001de28  lea     rdx, aPhysicalpcrrea; "PhysicalPcrRead"
0x18001de2f  jmp     short loc_18001DE49
0x18001de31  mov     [rsp+160h+cbData], esi; cbData
0x18001de35  lea     rax, [rsp+160h+Data]
0x18001de3a  mov     [rsp+160h+lpData], rax; lpData
0x18001de3f  mov     r9d, esi; dwType
0x18001de42  lea     rdx, aPhysicalpcrrea_0; "PhysicalPcrReadError"
0x18001de49  mov     rcx, rbx; hKey
0x18001de4c  call    cs:__imp_RegSetValueExW
0x18001de52  xor     edx, edx
0x18001de54  lea     rcx, [rbp+60h+var_A0]
0x18001de58  call    ?ReadWbclType@@YA?AV?$vector@EV?$allocator@E@std@@@std@@I@Z; ReadWbclType(uint)
0x18001de5d  nop
0x18001de5e  mov     edx, 1
0x18001de63  lea     rcx, [rbp+60h+var_B8]
0x18001de67  call    ?ReadWbclType@@YA?AV?$vector@EV?$allocator@E@std@@@std@@I@Z; ReadWbclType(uint)
0x18001de6c  nop
0x18001de6d  mov     [rsp+160h+var_114], edi
0x18001de71  mov     r9d, [rbp+60h+var_B0]
0x18001de75  mov     rax, [rbp+60h+var_B8]
0x18001de79  sub     r9d, eax
0x18001de7c  mov     edx, [rbp+60h+var_98]
0x18001de7f  mov     r8, [rbp+60h+var_A0]
0x18001de83  sub     edx, r8d
0x18001de86  mov     [rsp+160h+var_130], rdi
0x18001de8b  lea     rcx, [rsp+160h+var_114]
0x18001de90  mov     qword ptr [rsp+160h+cbData], rcx
0x18001de95  mov     [rsp+160h+lpData], rax
0x18001de9a  movzx   ecx, [rsp+160h+var_120]
0x18001de9f  call    cs:__imp_?TpmGetInformationFromTcgLog@@YAJGIQEAEI0PEAIPEAE@Z; TpmGetInformationFromTcgLog(ushort,uint,uchar * const,uint,uchar * const,uint *,uchar *)
0x18001dea5  mov     dword ptr [rsp+160h+var_110], edi
0x18001dea9  mov     edx, [rsp+160h+var_114]
0x18001dead  lea     rcx, [rbp+60h+var_88]
0x18001deb1  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18001deb6  nop
0x18001deb7  mov     rcx, [rbp+60h+var_B8]
0x18001debb  mov     r8, [rbp+60h+var_A0]
0x18001debf  mov     r9d, [rbp+60h+var_B0]
0x18001dec3  sub     r9d, ecx
0x18001dec6  mov     edx, [rbp+60h+var_98]
0x18001dec9  sub     edx, r8d
0x18001decc  mov     rax, [rbp+60h+var_88]
0x18001ded0  mov     [rsp+160h+var_130], rax
0x18001ded5  lea     rax, [rsp+160h+var_114]
0x18001deda  mov     qword ptr [rsp+160h+cbData], rax
0x18001dedf  mov     [rsp+160h+lpData], rcx
0x18001dee4  movzx   ecx, [rsp+160h+var_120]
0x18001dee9  call    cs:__imp_?TpmGetInformationFromTcgLog@@YAJGIQEAEI0PEAIPEAE@Z; TpmGetInformationFromTcgLog(ushort,uint,uchar * const,uint,uchar * const,uint *,uchar *)
0x18001deef  mov     dword ptr [rsp+160h+var_110], eax
0x18001def3  test    eax, eax
0x18001def5  jns     short loc_18001DF20
0x18001def7  mov     [rsp+160h+cbData], esi; cbData
0x18001defb  lea     rax, [rsp+160h+var_110]
0x18001df00  mov     [rsp+160h+lpData], rax; lpData
0x18001df05  mov     r9d, esi; dwType
0x18001df08  xor     r8d, r8d; Reserved
0x18001df0b  lea     rdx, aReplaypcrerror; "ReplayPcrError"
0x18001df12  mov     rcx, rbx; hKey
0x18001df15  call    cs:__imp_RegSetValueExW
0x18001df1b  jmp     loc_18001E17B
0x18001df20  mov     rax, [rbp+60h+var_88]
0x18001df24  mov     ecx, [rax+1]
0x18001df27  mov     dword ptr [rsp+160h+var_11C], ecx
0x18001df2b  mov     ecx, [rax+5]
0x18001df2e  mov     [rsp+160h+var_104], ecx
0x18001df32  movzx   edi, byte ptr [rax+0Ah]
0x18001df36  mov     r14, [rax+0Bh]
0x18001df3a  movzx   esi, byte ptr [rax+13h]
0x18001df3e  movzx   r15d, byte ptr [rax+14h]
0x18001df43  movzx   r12d, byte ptr [rax+15h]
0x18001df48  movzx   r13d, byte ptr [rax+16h]
0x18001df4d  mov     ecx, [rax+17h]
0x18001df50  mov     [rsp+160h+var_100], ecx
0x18001df54  mov     ecx, [rax+1Bh]
0x18001df57  mov     [rsp+160h+var_108], ecx
0x18001df5b  movzx   edx, byte ptr [rax+9]
0x18001df5f  mov     ecx, 22h ; '"'
0x18001df64  call    ?SetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@K@Z; HWSecurityRegistryManager::SetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong)
0x18001df69  mov     edx, edi
0x18001df6b  mov     ecx, 20h ; ' '
0x18001df70  call    ?SetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@K@Z; HWSecurityRegistryManager::SetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong)
0x18001df75  mov     edx, esi
0x18001df77  mov     ecx, 23h ; '#'
0x18001df7c  call    ?SetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@K@Z; HWSecurityRegistryManager::SetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong)
0x18001df81  mov     rdx, r14
0x18001df84  call    ?SetQWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@_K@Z; HWSecurityRegistryManager::SetQWordNoThrow(HWSecurityRegistryManager::RegValues,unsigned __int64)
0x18001df89  mov     edx, r15d
0x18001df8c  mov     ecx, 1Bh
0x18001df91  call    ?SetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@K@Z; HWSecurityRegistryManager::SetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong)
0x18001df96  mov     edx, r12d
0x18001df99  mov     ecx, 1Fh
0x18001df9e  call    ?SetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@K@Z; HWSecurityRegistryManager::SetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong)
0x18001dfa3  mov     edx, r13d
0x18001dfa6  mov     ecx, 1Ch
0x18001dfab  call    ?SetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@K@Z; HWSecurityRegistryManager::SetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong)
0x18001dfb0  mov     edi, dword ptr [rsp+160h+var_11C]
0x18001dfb4  add     rdi, [rbp+60h+var_88]
0x18001dfb8  mov     r8d, [rsp+160h+var_104]
0x18001dfbd  add     r8, rdi
0x18001dfc0  mov     rdx, rdi
0x18001dfc3  lea     rcx, [rsp+160h+var_E8]
0x18001dfc8  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18001dfcd  nop
0x18001dfce  mov     eax, dword ptr [rbp+60h+var_E0]
0x18001dfd1  mov     rcx, [rsp+160h+var_E8]
0x18001dfd6  sub     eax, ecx
0x18001dfd8  mov     [rsp+160h+cbData], eax; cbData
0x18001dfdc  mov     [rsp+160h+lpData], rcx; lpData
0x18001dfe1  mov     r9d, 3; dwType
0x18001dfe7  xor     r8d, r8d; Reserved
0x18001dfea  lea     rdx, aReplaypcr; "ReplayPcr"
0x18001dff1  mov     rcx, rbx; hKey
0x18001dff4  call    cs:__imp_RegSetValueExW
0x18001dffa  mov     r12, [rsp+160h+var_E8]
0x18001dfff  sub     rdi, r12
0x18001e002  mov     rsi, [rbp+60h+var_E0]
0x18001e006  add     rsi, rdi
0x18001e009  mov     eax, [rsp+160h+var_100]
0x18001e00d  test    eax, eax
0x18001e00f  jz      short loc_18001E042
0x18001e011  mov     edi, eax
0x18001e013  mov     r8d, eax
0x18001e016  mov     rdx, rsi
0x18001e019  lea     rcx, [rbp+60h+var_70]
0x18001e01d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18001e022  lea     rsi, [rsi+rdi*2]
0x18001e026  lea     rdx, [rbp+60h+var_70]
0x18001e02a  mov     ecx, 1Eh
0x18001e02f  call    ?SetStringNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HWSecurityRegistryManager::SetStringNoThrow(HWSecurityRegistryManager::RegValues,std::wstring const &)
0x18001e034  lea     rcx, [rbp+60h+var_70]
0x18001e038  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e03d  mov     r12, [rsp+160h+var_E8]
0x18001e042  mov     eax, [rsp+160h+var_108]
0x18001e046  test    eax, eax
0x18001e048  jz      short loc_18001E075
0x18001e04a  mov     r8d, eax
0x18001e04d  mov     rdx, rsi
0x18001e050  lea     rcx, [rbp+60h+var_70]
0x18001e054  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18001e059  lea     rdx, [rbp+60h+var_70]
0x18001e05d  mov     ecx, 1Dh
0x18001e062  call    ?SetStringNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HWSecurityRegistryManager::SetStringNoThrow(HWSecurityRegistryManager::RegValues,std::wstring const &)
0x18001e067  lea     rcx, [rbp+60h+var_70]
0x18001e06b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e070  mov     r12, [rsp+160h+var_E8]
0x18001e075  cmp     dword ptr [rsp+160h+Data], 0
0x18001e07a  jl      loc_18001E12D
0x18001e080  xor     edi, edi
0x18001e082  mov     dword ptr [rsp+160h+var_11C], edi
0x18001e086  mov     r13, [rbp+60h+Buf2]
0x18001e08a  mov     rsi, [rbp+60h+var_C8]
0x18001e08e  sub     rsi, r13
0x18001e091  mov     r8, rsi; Size
0x18001e094  mov     rdx, r13; Buf2
0x18001e097  mov     rcx, r12; Buf1
0x18001e09a  call    memcmp_0
0x18001e09f  test    eax, eax
0x18001e0a1  jz      short loc_18001E0FD
0x18001e0a3  xor     r15d, r15d
0x18001e0a6  mov     eax, 0AAAAAAABh
0x18001e0ab  mul     esi
0x18001e0ad  mov     r14d, edx
0x18001e0b0  shr     r14d, 4
0x18001e0b4  xor     esi, esi
0x18001e0b6  mov     ebx, r14d
0x18001e0b9  lea     rdx, [r15+r13]; Buf2
0x18001e0bd  lea     rcx, [r15+r12]; Buf1
0x18001e0c1  mov     r8, rbx; Size
0x18001e0c4  call    memcmp_0
0x18001e0c9  test    eax, eax
0x18001e0cb  jz      short loc_18001E0DC
0x18001e0cd  mov     ecx, esi
0x18001e0cf  mov     eax, 1
0x18001e0d4  shl     eax, cl
0x18001e0d6  or      edi, eax
0x18001e0d8  mov     dword ptr [rsp+160h+var_11C], edi
0x18001e0dc  add     r15d, r14d
0x18001e0df  inc     esi
0x18001e0e1  cmp     esi, 18h
0x18001e0e4  jb      short loc_18001E0B9
0x18001e0e6  test    edi, edi
0x18001e0e8  mov     rbx, [rsp+160h+hKey]
0x18001e0ed  jz      short loc_18001E0FD
0x18001e0ef  lea     rax, [rsp+160h+var_11C]
0x18001e0f4  lea     rdx, aMismatchedpcrs; "MismatchedPcrsMask"
0x18001e0fb  jmp     short loc_18001E111
0x18001e0fd  mov     [rsp+160h+var_108], 1
0x18001e105  lea     rax, [rsp+160h+var_108]
0x18001e10a  lea     rdx, aPcrsmatched; "PcrsMatched"
0x18001e111  mov     r9d, 4; dwType
0x18001e117  mov     [rsp+160h+cbData], r9d; cbData
0x18001e11c  mov     [rsp+160h+lpData], rax; lpData
0x18001e121  xor     r8d, r8d; Reserved
0x18001e124  mov     rcx, rbx; hKey
0x18001e127  call    cs:__imp_RegSetValueExW
0x18001e12d  call    cs:__imp__Xtime_get_ticks
0x18001e133  mov     rcx, rax
0x18001e136  sub     rcx, [rsp+160h+var_F8]
0x18001e13b  mov     rax, 346DC5D63886594Bh
0x18001e145  imul    rcx
0x18001e148  sar     rdx, 0Bh
0x18001e14c  mov     rax, rdx
0x18001e14f  shr     rax, 3Fh
0x18001e153  add     rdx, rax
0x18001e156  mov     [rsp+160h+var_F8], rdx
0x18001e15b  lea     r8, [rsp+160h+var_110]
0x18001e160  lea     rdx, [rsp+160h+Data]
0x18001e165  lea     rcx, [rsp+160h+var_F8]
0x18001e16a  call    ??$TpmTaskCheckPcrInformationEnded@_JAEAJAEAJ@TpmTaskDebugProvider@@SAX$$QEA_JAEAJ1@Z; TpmTaskDebugProvider::TpmTaskCheckPcrInformationEnded<__int64,long &,long &>(__int64 &&,long &,long &)
0x18001e16f  nop
0x18001e170  lea     rcx, [rsp+160h+var_E8]
0x18001e175  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e17a  nop
0x18001e17b  lea     rcx, [rbp+60h+var_88]
0x18001e17f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e184  nop
0x18001e185  lea     rcx, [rbp+60h+var_B8]
0x18001e189  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e18e  nop
0x18001e18f  lea     rcx, [rbp+60h+var_A0]
0x18001e193  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e198  nop
0x18001e199  lea     rcx, [rbp+60h+Buf2]
0x18001e19d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e1a2  nop
0x18001e1a3  lea     rcx, [rsp+160h+hKey]
0x18001e1a8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e1ad  mov     rcx, [rbp+60h+var_50]
0x18001e1b1  xor     rcx, rsp; StackCookie
0x18001e1b4  call    __security_check_cookie
0x18001e1b9  add     rsp, 128h
0x18001e1c0  pop     r15
0x18001e1c2  pop     r14
0x18001e1c4  pop     r13
0x18001e1c6  pop     r12
0x18001e1c8  pop     rdi
0x18001e1c9  pop     rsi
0x18001e1ca  pop     rbx
0x18001e1cb  pop     rbp
0x18001e1cc  retn
```
