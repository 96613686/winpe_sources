# _IsMutexAvailable

- ea: `0x1800201b0`
- end: `0x180020316`
- name: `_IsMutexAvailable`
- size: `358`
- prototype: `HRESULT __fastcall(int mutexIndex, bool *isAvailable)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fab0`

## callees

- `0x1800060f8`
- `0x18000a28c`
- `0x18000d3c0`
- `0x18000f544`
- `0x180010400`
- `0x1800201b0`
- `0x180020354`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002027a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002027a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002021d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002021d`

## string_xrefs

- `0x180020265`: `onecore\ds\security\webauth\authbroker\lib\wab2wambridge.cpp`
- `0x18002029e`: `onecore\ds\security\webauth\authbroker\lib\wab2wambridge.cpp`
- `0x1800202d7`: `onecore\ds\security\webauth\authbroker\lib\wab2wambridge.cpp`

## pseudocode

```c
HRESULT __fastcall IsMutexAvailable(int mutexIndex, bool *isAvailable)
{
  __int64 v2; // rbx
  LSTATUS ValueW; // eax
  unsigned int v5; // r9d
  HRESULT LastError; // ebx
  HRESULT v7; // eax
  unsigned int size; // [rsp+40h] [rbp-178h] BYREF
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > localMutex; // [rsp+48h] [rbp-170h] BYREF
  wchar_t mutexName[160]; // [rsp+50h] [rbp-168h] BYREF
  void *retaddr; // [rsp+1B8h] [rbp+0h]

  v2 = mutexIndex;
  size = 312;
  *isAvailable = 0;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\WebAuthBridge\\Internet",
             s_WAB2WAMBridgeInternetNamedMutex[mutexIndex],
             0x10002u,
             0,
             mutexName,
             &size);
  if ( (unsigned int)(ValueW - 2) <= 1 )
    goto LABEL_13;
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             0xB0u,
             "onecore\\ds\\security\\webauth\\authbroker\\lib\\wab2wambridge.cpp",
             ValueW);
  if ( mutexName[0] )
  {
    localMutex.m_ptr = 0;
    if ( !_try_create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            &localMutex,
            mutexName,
            0,
            v5) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    0xB3u,
                    "onecore\\ds\\security\\webauth\\authbroker\\lib\\wab2wambridge.cpp");
LABEL_9:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&localMutex);
      return LastError;
    }
    if ( GetLastError() != 183 )
    {
      v7 = _DeleteInternetMutexFromRegistry(s_WAB2WAMBridgeInternetNamedMutex[v2]);
      LastError = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0xB7u,
          "onecore\\ds\\security\\webauth\\authbroker\\lib\\wab2wambridge.cpp",
          v7);
        goto LABEL_9;
      }
      *isAvailable = 1;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&localMutex);
  }
  else
  {
LABEL_13:
    *isAvailable = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800201b0  mov     [rsp+arg_10], rbx
0x1800201b5  push    rsi
0x1800201b6  push    rdi
0x1800201b7  push    r14
0x1800201b9  sub     rsp, 1A0h
0x1800201c0  mov     rax, cs:__security_cookie
0x1800201c7  xor     rax, rsp
0x1800201ca  mov     [rsp+1B8h+var_28], rax
0x1800201d2  movsxd  rbx, mutexIndex
0x1800201d5  lea     rax, [rsp+1B8h+size]
0x1800201da  mov     [rsp+1B8h+pcbData], rax; pcbData
0x1800201df  lea     r14, s_WAB2WAMBridgeInternetNamedMutex
0x1800201e6  xor     esi, esi
0x1800201e8  mov     [rsp+1B8h+size], 138h
0x1800201f0  mov     [isAvailable], sil
0x1800201f3  lea     rax, [rsp+1B8h+mutexName]
0x1800201f8  mov     r8, [r14+rbx*8]; lpValue
0x1800201fc  mov     rdi, isAvailable
0x1800201ff  mov     [rsp+1B8h+pvData], rax; bool *
0x180020204  lea     isAvailable, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002020b  mov     r9d, 10002h; dwFlags
0x180020211  mov     [rsp+1B8h+pdwType], rsi; dwFlags
0x180020216  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18002021d  call    cs:__imp_RegGetValueW
0x180020223  lea     mutexIndex, [rax-2]
0x180020226  cmp     mutexIndex, 1
0x180020229  jbe     loc_1800202ED
0x18002022f  test    eax, eax
0x180020231  jnz     loc_1800202CF
0x180020237  cmp     [rsp+1B8h+mutexName], si
0x18002023c  jz      loc_1800202ED
0x180020242  xor     r8d, r8d; dwFlags
0x180020245  mov     [rsp+1B8h+localMutex.m_ptr], rsi
0x18002024a  lea     isAvailable, [rsp+1B8h+mutexName]; name
0x18002024f  lea     rcx, [rsp+1B8h+localMutex]; this
0x180020254  call    ?try_create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180020259  test    al, al
0x18002025b  jnz     short loc_18002027A
0x18002025d  mov     rcx, [rsp+1B8h]; callerReturnAddress
0x180020265  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\webauth\\authbro"...
0x18002026c  mov     edx, 0B3h; lineNumber
0x180020271  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020276  mov     ebx, eax
0x180020278  jmp     short loc_1800202B2
0x18002027a  call    cs:__imp_GetLastError
0x180020280  cmp     eax, 0B7h
0x180020285  jz      short loc_1800202C3
0x180020287  mov     rcx, [r14+rbx*8]; regValue
0x18002028b  call    ?_DeleteInternetMutexFromRegistry@@YAJPEBG@Z; _DeleteInternetMutexFromRegistry(ushort const *)
0x180020290  mov     ebx, eax
0x180020292  test    eax, eax
0x180020294  jns     short loc_1800202C0
0x180020296  mov     rcx, [rsp+1B8h]; callerReturnAddress
0x18002029e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\webauth\\authbro"...
0x1800202a5  mov     r9d, eax; hr
0x1800202a8  mov     edx, 0B7h; lineNumber
0x1800202ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800202b2  lea     rcx, [rsp+1B8h+localMutex]; this
0x1800202b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800202bc  mov     eax, ebx
0x1800202be  jmp     short loc_1800202F2
0x1800202c0  mov     byte ptr [rdi], 1
0x1800202c3  lea     rcx, [rsp+1B8h+localMutex]; this
0x1800202c8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800202cd  jmp     short loc_1800202F0
0x1800202cf  mov     rcx, [rsp+1B8h]; callerReturnAddress
0x1800202d7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\webauth\\authbro"...
0x1800202de  mov     r9d, eax; err
0x1800202e1  mov     edx, 0B0h; lineNumber
0x1800202e6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800202eb  jmp     short loc_1800202F2
0x1800202ed  mov     byte ptr [rdi], 1
0x1800202f0  xor     eax, eax
0x1800202f2  mov     rcx, [rsp+1B8h+var_28]
0x1800202fa  xor     rcx, rsp; StackCookie
0x1800202fd  call    __security_check_cookie
0x180020302  mov     rbx, [rsp+1B8h+arg_10]
0x18002030a  add     rsp, 1A0h
0x180020311  pop     r14
0x180020313  pop     rdi
0x180020314  pop     rsi
0x180020315  retn
```
