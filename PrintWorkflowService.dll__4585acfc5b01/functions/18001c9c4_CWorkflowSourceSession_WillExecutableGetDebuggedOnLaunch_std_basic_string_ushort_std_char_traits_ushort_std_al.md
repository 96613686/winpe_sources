# CWorkflowSourceSession::WillExecutableGetDebuggedOnLaunch(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar &)

- ea: `0x18001c9c4`
- end: `0x18001cb20`
- name: `?WillExecutableGetDebuggedOnLaunch@CWorkflowSourceSession@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAE@Z`
- size: `348`
- prototype: `__int64 __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b100`

## callees

- `0x1800018d8`
- `0x18000a014`
- `0x180010b0c`
- `0x180012784`
- `0x180013eb0`
- `0x180019ea4`
- `0x18001c9c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca86`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18001ca1f`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18001ca1f`

## string_xrefs

- `0x18001ca2d`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsourcesession.cpp`
- `0x18001caaa`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsourcesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWorkflowSourceSession::WillExecutableGetDebuggedOnLaunch(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  const WCHAR *v8; // rax
  LSTATUS ValueW; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  unsigned int pdwType; // [rsp+20h] [rbp-28h]
  int pdwTypea; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v17; // [rsp+70h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+38h] BYREF
  __int64 v20; // [rsp+88h] [rbp+40h] BYREF

  v17 = a1;
  *a3 = 0;
  if ( !std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) || !*(_QWORD *)(v5 + 16) )
    return 1;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v6 = RegOpenKeyW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options",
         &phkResult);
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x19B,
           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsourcesession.cpp",
           (const char *)v6,
           pdwType);
  }
  else
  {
    pcbData = 0;
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    ValueW = RegGetValueW(phkResult, v8, L"Debugger", 0xFFFFu, 0, 0, &pcbData);
    v7 = ValueW;
    if ( (ValueW & 0xFFFFFFFD) != 0 )
    {
      if ( ValueW > 0 )
        v7 = (unsigned __int16)ValueW | 0x80070000;
      if ( (v7 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A8,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsourcesession.cpp",
          (const char *)v7,
          pdwTypea);
    }
    else
    {
      if ( pcbData )
        *a3 = 1;
      if ( (unsigned int)dword_180083038 > 5 )
      {
        LOBYTE(v17) = *a3;
        v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
          v10,
          (unsigned int)&byte_18007081F,
          v11,
          v12,
          (__int64)&v20,
          (__int64)&v17);
      }
      v7 = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v7;
}

```

## disassembly

```asm
0x18001c9c4  mov     [rsp-20h+arg_0], rcx
0x18001c9c9  push    rbp
0x18001c9ca  push    rbx
0x18001c9cb  push    rsi
0x18001c9cc  push    rdi
0x18001c9cd  mov     rbp, rsp
0x18001c9d0  sub     rsp, 48h
0x18001c9d4  mov     rcx, rdx
0x18001c9d7  mov     byte ptr [r8], 0
0x18001c9db  mov     rsi, r8
0x18001c9de  mov     rdi, rdx
0x18001c9e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c9e6  test    rax, rax
0x18001c9e9  jz      loc_18001CB12
0x18001c9ef  cmp     qword ptr [rdx+10h], 0
0x18001c9f4  jz      loc_18001CB12
0x18001c9fa  xor     edx, edx
0x18001c9fc  mov     [rbp+phkResult], 0
0x18001ca04  lea     rcx, [rbp+phkResult]
0x18001ca08  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001ca0d  lea     r8, [rbp+phkResult]; phkResult
0x18001ca11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ca18  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001ca1f  call    cs:__imp_RegOpenKeyW
0x18001ca25  test    eax, eax
0x18001ca27  jz      short loc_18001CA48
0x18001ca29  mov     rcx, [rbp+20h]; this
0x18001ca2d  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\workflow"...
0x18001ca34  mov     r9d, eax; char *
0x18001ca37  mov     edx, 19Bh; void *
0x18001ca3c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ca41  mov     ebx, eax
0x18001ca43  jmp     loc_18001CB05
0x18001ca48  mov     rcx, rdi
0x18001ca4b  mov     [rbp+arg_8], 0
0x18001ca52  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ca57  lea     rcx, [rbp+arg_8]
0x18001ca5b  mov     r9d, 0FFFFh; dwFlags
0x18001ca61  mov     [rsp+48h+pcbData], rcx; pcbData
0x18001ca66  lea     r8, Value; "Debugger"
0x18001ca6d  mov     rcx, [rbp+phkResult]; hkey
0x18001ca71  mov     rdx, rax; lpSubKey
0x18001ca74  mov     [rsp+48h+pvData], 0; pvData
0x18001ca7d  mov     [rsp+48h+pdwType], 0; int
0x18001ca86  call    cs:__imp_RegGetValueW
0x18001ca8c  mov     ebx, eax
0x18001ca8e  test    eax, 0FFFFFFFDh
0x18001ca93  jz      short loc_18001CAC0
0x18001ca95  test    eax, eax
0x18001ca97  jle     short loc_18001CAA2
0x18001ca99  movzx   ebx, ax
0x18001ca9c  or      ebx, 80070000h
0x18001caa2  test    ebx, ebx
0x18001caa4  jns     short loc_18001CB05
0x18001caa6  mov     rcx, [rbp+20h]; this
0x18001caaa  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\workflow"...
0x18001cab1  mov     r9d, ebx; char *
0x18001cab4  mov     edx, 1A8h; void *
0x18001cab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cabe  jmp     short loc_18001CB05
0x18001cac0  cmp     [rbp+arg_8], 0
0x18001cac4  jbe     short loc_18001CAC9
0x18001cac6  mov     byte ptr [rsi], 1
0x18001cac9  mov     eax, cs:dword_180083038
0x18001cacf  cmp     eax, 5
0x18001cad2  jbe     short loc_18001CB03
0x18001cad4  mov     al, [rsi]
0x18001cad6  mov     rcx, rdi
0x18001cad9  mov     byte ptr [rbp+arg_0], al
0x18001cadc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cae1  mov     [rbp+arg_18], rax
0x18001cae5  lea     rdx, byte_18007081F
0x18001caec  lea     rax, [rbp+arg_0]
0x18001caf0  mov     [rsp+48h+pvData], rax
0x18001caf5  lea     rax, [rbp+arg_18]
0x18001caf9  mov     [rsp+48h+pdwType], rax
0x18001cafe  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x18001cb03  xor     ebx, ebx
0x18001cb05  lea     rcx, [rbp+phkResult]
0x18001cb09  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001cb0e  mov     eax, ebx
0x18001cb10  jmp     short loc_18001CB17
0x18001cb12  mov     eax, 1
0x18001cb17  add     rsp, 48h
0x18001cb1b  pop     rdi
0x18001cb1c  pop     rsi
0x18001cb1d  pop     rbx
0x18001cb1e  pop     rbp
0x18001cb1f  retn
```
