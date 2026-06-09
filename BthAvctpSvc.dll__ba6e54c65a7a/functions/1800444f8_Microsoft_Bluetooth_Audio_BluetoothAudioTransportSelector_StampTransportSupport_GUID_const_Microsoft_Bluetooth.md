# Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::StampTransportSupport(_GUID const &,Microsoft::Bluetooth::Audio::ChosenTransport,bool)

- ea: `0x1800444f8`
- end: `0x18004480e`
- name: `?StampTransportSupport@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@AEAAXAEBU_GUID@@W4ChosenTransport@234@_N@Z`
- size: `790`
- prototype: ``
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003fe50`
- `0x180042280`
- `0x180042450`
- `0x180042c24`
- `0x180042e20`

## callees

- `0x180001dd0`
- `0x180012480`
- `0x180012554`
- `0x1800151f4`
- `0x180015238`
- `0x180015b1c`
- `0x180019c68`
- `0x180019d20`
- `0x180019f80`
- `0x18003a434`
- `0x18003aa54`
- `0x18003d654`
- `0x18003d694`
- `0x18003d6cc`
- `0x1800444f8`
- `0x180045bc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180044582`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180044582`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044675`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044675`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180044636`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180044636`

## string_xrefs

- `0x180044530`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::StampTransportSupport(
        __int64 a1,
        const GUID *a2,
        int a3,
        unsigned __int8 a4)
{
  int v4; // r14d
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // bl
  __int64 v15; // rax
  const WCHAR *v16; // rax
  LSTATUS v17; // edx
  int v18; // r8d
  const WCHAR *v19; // rax
  int v20; // edx
  int v21; // r8d
  int lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  DWORD cbDataa; // [rsp+28h] [rbp-D8h]
  char v26; // [rsp+40h] [rbp-C0h]
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v31[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v33[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v34[32]; // [rsp+110h] [rbp+10h] BYREF
  OLECHAR sz[40]; // [rsp+130h] [rbp+30h] BYREF

  v4 = a4;
  v8 = std::wstring::wstring(
         (__int64)v32,
         (__int64)L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats");
  v9 = std::operator+<unsigned short>(v31, v8);
  std::operator+<unsigned short>(v30, v9, a1 + 248);
  std::wstring::_Tidy_deallocate(v31);
  std::wstring::_Tidy_deallocate(v32);
  if ( StringFromGUID2(a2, sz, 39) )
  {
    v10 = std::wstring::wstring((__int64)v34, (__int64)sz);
    v12 = std::operator+<unsigned short>(v33, v11, v10);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
    std::wstring::_Append<unsigned short>(v30, v13);
    std::wstring::_Tidy_deallocate(v33);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v29);
    v14 = 1;
    if ( a3 )
    {
      if ( a3 != 1 )
      {
LABEL_33:
        std::wstring::_Tidy_deallocate(v29);
        return std::wstring::_Tidy_deallocate(v30);
      }
      v15 = 128;
    }
    else
    {
      v15 = 96;
    }
    std::wstring::operator=(v29, v15 + a1);
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    v17 = RegCreateKeyW(HKEY_LOCAL_MACHINE, v16, &phkResult);
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v14 = 0;
      }
      if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v26 = v17;
        LOBYTE(v17) = v14;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_AvrcpTransportChannelq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          v18,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          2,
          cbData,
          69,
          &WPP_b836096fa1863519a0c995e3dad38024_Traceguids,
          v26,
          a1);
      }
    }
    else
    {
      *(_DWORD *)Data = v4;
      v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      if ( RegSetValueExW(phkResult, v19, 0, 4u, Data, 4u) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || (LOBYTE(v20) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
        {
          LOBYTE(v20) = 0;
        }
        if ( (_BYTE)v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            v21,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            2,
            1,
            68,
            &WPP_b836096fa1863519a0c995e3dad38024_Traceguids,
            a1);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || (LOBYTE(v20) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
        {
          LOBYTE(v20) = 0;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 24) )
          v14 = 0;
        if ( (_BYTE)v20 || v14 )
        {
          LOBYTE(v21) = v14;
          WPP_RECORDER_AND_TRACE_SF__guid_ChosenTransportlq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            v21,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            lpData,
            cbDataa);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    goto LABEL_33;
  }
  return std::wstring::_Tidy_deallocate(v30);
}

```

## disassembly

```asm
0x1800444f8  push    rbp
0x1800444fa  push    rbx
0x1800444fb  push    rsi
0x1800444fc  push    rdi
0x1800444fd  push    r12
0x1800444ff  push    r14
0x180044501  push    r15
0x180044503  lea     rbp, [rsp-90h]
0x18004450b  sub     rsp, 190h
0x180044512  mov     rax, cs:__security_cookie
0x180044519  xor     rax, rsp
0x18004451c  mov     [rbp+0C0h+var_40], rax
0x180044523  movzx   r14d, r9b
0x180044527  mov     esi, r8d
0x18004452a  mov     r15, rdx
0x18004452d  mov     rdi, rcx
0x180044530  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x180044537  lea     rcx, [rbp+0C0h+var_F0]
0x18004453b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180044540  nop
0x180044541  mov     rdx, rax
0x180044544  lea     rcx, [rbp+0C0h+var_110]
0x180044548  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18004454d  nop
0x18004454e  lea     r8, [rdi+0F8h]
0x180044555  mov     rdx, rax
0x180044558  lea     rcx, [rbp+0C0h+var_130]
0x18004455c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180044561  nop
0x180044562  lea     rcx, [rbp+0C0h+var_110]
0x180044566  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004456b  nop
0x18004456c  lea     rcx, [rbp+0C0h+var_F0]
0x180044570  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044575  mov     r8d, 27h ; '''; cchMax
0x18004457b  lea     rdx, [rbp+0C0h+sz]; lpsz
0x18004457f  mov     rcx, r15; rguid
0x180044582  call    cs:__imp_StringFromGUID2
0x180044588  xor     r12d, r12d
0x18004458b  test    eax, eax
0x18004458d  jz      loc_1800447E4
0x180044593  lea     rdx, [rbp+0C0h+sz]
0x180044597  lea     rcx, [rbp+0C0h+var_B0]
0x18004459b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800445a0  nop
0x1800445a1  mov     r8, rax
0x1800445a4  lea     rcx, [rbp+0C0h+var_D0]
0x1800445a8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1800445ad  mov     r8, [rax+10h]
0x1800445b1  mov     rcx, rax
0x1800445b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800445b9  mov     rdx, rax
0x1800445bc  lea     rcx, [rbp+0C0h+var_130]
0x1800445c0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800445c5  nop
0x1800445c6  lea     rcx, [rbp+0C0h+var_D0]
0x1800445ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800445cf  nop
0x1800445d0  lea     rcx, [rbp+0C0h+var_B0]
0x1800445d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800445d9  lea     rcx, [rsp+1C0h+var_150]
0x1800445de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800445e3  nop
0x1800445e4  lea     ebx, [r12+1]
0x1800445e9  test    esi, esi
0x1800445eb  jnz     short loc_1800445F2
0x1800445ed  lea     eax, [rbx+5Fh]
0x1800445f0  jmp     short loc_1800445FF
0x1800445f2  cmp     esi, ebx
0x1800445f4  jnz     loc_1800447D9
0x1800445fa  mov     eax, 80h
0x1800445ff  lea     rdx, [rax+rdi]
0x180044603  lea     rcx, [rsp+1C0h+var_150]
0x180044608  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004460d  mov     [rsp+1C0h+phkResult], r12
0x180044612  xor     edx, edx
0x180044614  lea     rcx, [rsp+1C0h+phkResult]
0x180044619  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004461e  lea     rcx, [rbp+0C0h+var_130]
0x180044622  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044627  mov     rdx, rax; lpSubKey
0x18004462a  lea     r8, [rsp+1C0h+phkResult]; phkResult
0x18004462f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044636  call    cs:__imp_RegCreateKeyW
0x18004463c  mov     edx, eax
0x18004463e  test    eax, eax
0x180044640  jnz     loc_180044762
0x180044646  mov     dword ptr [rsp+1C0h+Data], r14d
0x18004464b  lea     rcx, [rsp+1C0h+var_150]
0x180044650  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044655  mov     rdx, rax; lpValueName
0x180044658  mov     r9d, 4; dwType
0x18004465e  mov     [rsp+1C0h+cbData], r9d; cbData
0x180044663  lea     rax, [rsp+1C0h+Data]
0x180044668  mov     [rsp+1C0h+lpData], rax; lpData
0x18004466d  xor     r8d, r8d; Reserved
0x180044670  mov     rcx, [rsp+1C0h+phkResult]; hKey
0x180044675  call    cs:__imp_RegSetValueExW
0x18004467b  test    eax, eax
0x18004467d  jnz     short loc_1800446F0
0x18004467f  lea     rax, WPP_GLOBAL_Control
0x180044686  mov     rcx, cs:WPP_GLOBAL_Control
0x18004468d  cmp     rcx, rax
0x180044690  jz      short loc_18004469F
0x180044692  test    [rcx+1Ch], bl
0x180044695  jz      short loc_18004469F
0x180044697  cmp     byte ptr [rcx+19h], 5
0x18004469b  mov     dl, bl
0x18004469d  jnb     short loc_1800446A2
0x18004469f  mov     dl, r12b
0x1800446a2  lea     rax, WPP_RECORDER_INITIALIZED
0x1800446a9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800446b0  jz      short loc_1800446B9
0x1800446b2  cmp     [rcx+30h], r12w
0x1800446b7  jnz     short loc_1800446BC
0x1800446b9  mov     bl, r12b
0x1800446bc  test    dl, dl
0x1800446be  jnz     short loc_1800446C8
0x1800446c0  test    bl, bl
0x1800446c2  jz      loc_1800447CE
0x1800446c8  mov     [rsp+1C0h+var_168], rdi
0x1800446cd  mov     [rsp+1C0h+var_170], r14d
0x1800446d2  mov     dword ptr [rsp+1C0h+var_178], esi
0x1800446d6  mov     qword ptr [rsp+1C0h+var_180], r15
0x1800446db  mov     r9, [rcx+28h]
0x1800446df  mov     r8b, bl
0x1800446e2  mov     rcx, [rcx+10h]
0x1800446e6  call    WPP_RECORDER_AND_TRACE_SF__guid_ChosenTransportlq
0x1800446eb  jmp     loc_1800447CE
0x1800446f0  lea     rax, WPP_GLOBAL_Control
0x1800446f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446fe  cmp     rcx, rax
0x180044701  jz      short loc_180044710
0x180044703  test    [rcx+1Ch], bl
0x180044706  jz      short loc_180044710
0x180044708  cmp     byte ptr [rcx+19h], 2
0x18004470c  mov     dl, bl
0x18004470e  jnb     short loc_180044713
0x180044710  mov     dl, r12b; int
0x180044713  lea     rax, WPP_RECORDER_INITIALIZED
0x18004471a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180044721  setnz   r8b; int
0x180044725  test    dl, dl
0x180044727  jnz     short loc_180044732
0x180044729  test    r8b, r8b
0x18004472c  jz      loc_1800447CE
0x180044732  mov     qword ptr [rsp+1C0h+var_180], rdi; char
0x180044737  lea     rax, WPP_b836096fa1863519a0c995e3dad38024_Traceguids
0x18004473e  mov     [rsp+1C0h+MessageGuid], rax; MessageGuid
0x180044743  mov     [rsp+1C0h+var_190], 44h ; 'D'; __int16
0x18004474a  mov     [rsp+1C0h+cbData], ebx; int
0x18004474e  mov     byte ptr [rsp+1C0h+lpData], 2; char
0x180044753  mov     r9, [rcx+28h]; int
0x180044757  mov     rcx, [rcx+10h]; int
0x18004475b  call    WPP_RECORDER_AND_TRACE_SF_q
0x180044760  jmp     short loc_1800447CE
0x180044762  lea     rax, WPP_GLOBAL_Control
0x180044769  mov     rcx, cs:WPP_GLOBAL_Control
0x180044770  cmp     rcx, rax
0x180044773  jz      short loc_180044780
0x180044775  test    [rcx+1Ch], bl
0x180044778  jz      short loc_180044780
0x18004477a  cmp     byte ptr [rcx+19h], 2
0x18004477e  jnb     short loc_180044783
0x180044780  mov     bl, r12b
0x180044783  lea     rax, WPP_RECORDER_INITIALIZED
0x18004478a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180044791  setnz   r8b; int
0x180044795  test    bl, bl
0x180044797  jnz     short loc_18004479E
0x180044799  test    r8b, r8b
0x18004479c  jz      short loc_1800447CE
0x18004479e  mov     qword ptr [rsp+1C0h+var_178], rdi; char
0x1800447a3  mov     dword ptr [rsp+1C0h+var_180], edx; char
0x1800447a7  lea     rax, WPP_b836096fa1863519a0c995e3dad38024_Traceguids
0x1800447ae  mov     [rsp+1C0h+MessageGuid], rax; MessageGuid
0x1800447b3  mov     [rsp+1C0h+var_190], 45h ; 'E'; __int16
0x1800447ba  mov     byte ptr [rsp+1C0h+lpData], 2; char
0x1800447bf  mov     r9, [rcx+28h]; int
0x1800447c3  mov     dl, bl; int
0x1800447c5  mov     rcx, [rcx+10h]; int
0x1800447c9  call    WPP_RECORDER_AND_TRACE_SF_AvrcpTransportChannelq
0x1800447ce  lea     rcx, [rsp+1C0h+phkResult]
0x1800447d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800447d8  nop
0x1800447d9  lea     rcx, [rsp+1C0h+var_150]
0x1800447de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800447e3  nop
0x1800447e4  lea     rcx, [rbp+0C0h+var_130]
0x1800447e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800447ed  mov     rcx, [rbp+0C0h+var_40]
0x1800447f4  xor     rcx, rsp; StackCookie
0x1800447f7  call    __security_check_cookie
0x1800447fc  add     rsp, 190h
0x180044803  pop     r15
0x180044805  pop     r14
0x180044807  pop     r12
0x180044809  pop     rdi
0x18004480a  pop     rsi
0x18004480b  pop     rbx
0x18004480c  pop     rbp
0x18004480d  retn
```
