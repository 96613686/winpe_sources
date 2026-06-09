# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Start(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)

- ea: `0x18002a73c`
- end: `0x18002a923`
- name: `?Start@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000deb0`

## callees

- `0x1800110fc`
- `0x18001140c`
- `0x18002a73c`
- `0x18002a92c`
- `0x18002aec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a7bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a7bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a8ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a8ac`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Start(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this)
{
  char v2; // di
  bool v3; // dl
  int started; // ebx
  int v5; // edx
  int v6; // r8d
  int v7; // ecx
  int v8; // ecx
  _QWORD *v9; // rcx
  bool v10; // dl
  int v11; // eax
  bool v12; // cf

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  started = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v7 = *((_DWORD *)this + 2);
  if ( !v7 )
  {
    started = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::StartInternal(this);
    if ( started >= 0 )
      *((_DWORD *)this + 2) = 1;
    goto LABEL_27;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    started = -2147483634;
    v9 = WPP_GLOBAL_Control;
    v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_24;
    goto LABEL_28;
  }
  if ( v8 != 1 )
  {
LABEL_27:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  started = -2147483634;
  v9 = WPP_GLOBAL_Control;
  v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
LABEL_24:
    WPP_RECORDER_AND_TRACE_SF_s(v9[2], v10, v6, v9[5]);
    v9 = WPP_GLOBAL_Control;
  }
LABEL_28:
  if ( this != (Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)-48LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v9 = WPP_GLOBAL_Control;
  }
  v11 = 0;
  if ( started )
    v12 = *((_BYTE *)v9 + 25) < 2u;
  else
    v12 = *((_BYTE *)v9 + 25) < 5u;
  if ( v9 == &WPP_GLOBAL_Control || (LOBYTE(v11) = !v12, !v11) )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = v2;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(v9[2], v5, v6, v9[5]);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18002a73c  push    rbx
0x18002a73e  push    rbp
0x18002a73f  push    rsi
0x18002a740  push    rdi
0x18002a741  push    r13
0x18002a743  push    r14
0x18002a745  push    r15
0x18002a747  sub     rsp, 60h
0x18002a74b  mov     r14, rdx
0x18002a74e  mov     rsi, rcx
0x18002a751  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a758  lea     r15, WPP_GLOBAL_Control
0x18002a75f  mov     edi, 1
0x18002a764  cmp     rcx, r15
0x18002a767  jz      short loc_18002A774
0x18002a769  cmp     byte ptr [rcx+19h], 5
0x18002a76d  jb      short loc_18002A774
0x18002a76f  mov     dl, dil
0x18002a772  jmp     short loc_18002A776
0x18002a774  xor     dl, dl
0x18002a776  lea     r13, WPP_RECORDER_INITIALIZED
0x18002a77d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002a784  lea     r9, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a78b  setnz   r8b
0x18002a78f  test    dl, dl
0x18002a791  jnz     short loc_18002A798
0x18002a793  test    r8b, r8b
0x18002a796  jz      short loc_18002A7B6
0x18002a798  mov     [rsp+98h+var_50], rsi
0x18002a79d  mov     [rsp+98h+var_60], r9
0x18002a7a2  mov     r9, [rcx+28h]
0x18002a7a6  mov     rcx, [rcx+10h]
0x18002a7aa  mov     [rsp+98h+var_68], 0Ah
0x18002a7b1  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002a7b6  lea     rbp, [rsi+30h]
0x18002a7ba  xor     ebx, ebx
0x18002a7bc  mov     rcx, rbp; lpCriticalSection
0x18002a7bf  call    cs:__imp_EnterCriticalSection
0x18002a7c5  mov     ecx, [rsi+8]
0x18002a7c8  test    ecx, ecx
0x18002a7ca  jz      loc_18002A882
0x18002a7d0  sub     ecx, edi
0x18002a7d2  jz      short loc_18002A827
0x18002a7d4  cmp     ecx, edi
0x18002a7d6  jnz     loc_18002A896
0x18002a7dc  mov     ebx, 8000000Eh
0x18002a7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7e8  cmp     rcx, r15
0x18002a7eb  jz      short loc_18002A7F8
0x18002a7ed  cmp     byte ptr [rcx+19h], 2
0x18002a7f1  jb      short loc_18002A7F8
0x18002a7f3  mov     dl, dil
0x18002a7f6  jmp     short loc_18002A7FA
0x18002a7f8  xor     dl, dl
0x18002a7fa  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002a801  setnz   r8b
0x18002a805  test    dl, dl
0x18002a807  jnz     short loc_18002A812
0x18002a809  test    r8b, r8b
0x18002a80c  jz      loc_18002A89D
0x18002a812  lea     r14, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a819  mov     [rsp+98h+var_60], r14
0x18002a81e  mov     [rsp+98h+var_68], 0Ch
0x18002a825  jmp     short loc_18002A86C
0x18002a827  mov     ebx, 8000000Eh
0x18002a82c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a833  cmp     rcx, r15
0x18002a836  jz      short loc_18002A843
0x18002a838  cmp     byte ptr [rcx+19h], 2
0x18002a83c  jb      short loc_18002A843
0x18002a83e  mov     dl, dil
0x18002a841  jmp     short loc_18002A845
0x18002a843  xor     dl, dl
0x18002a845  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002a84c  setnz   r8b
0x18002a850  test    dl, dl
0x18002a852  jnz     short loc_18002A859
0x18002a854  test    r8b, r8b
0x18002a857  jz      short loc_18002A89D
0x18002a859  lea     r14, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a860  mov     [rsp+98h+var_60], r14
0x18002a865  mov     [rsp+98h+var_68], 0Bh
0x18002a86c  mov     r9, [rcx+28h]
0x18002a870  mov     rcx, [rcx+10h]
0x18002a874  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002a879  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a880  jmp     short loc_18002A8A4
0x18002a882  mov     rdx, r14
0x18002a885  mov     rcx, rsi; this
0x18002a888  call    ?StartInternal@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::StartInternal(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x18002a88d  mov     ebx, eax
0x18002a88f  test    eax, eax
0x18002a891  js      short loc_18002A896
0x18002a893  mov     [rsi+8], edi
0x18002a896  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a89d  lea     r14, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a8a4  test    rbp, rbp
0x18002a8a7  jz      short loc_18002A8B9
0x18002a8a9  mov     rcx, rbp; lpCriticalSection
0x18002a8ac  call    cs:__imp_LeaveCriticalSection
0x18002a8b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8b9  xor     eax, eax
0x18002a8bb  test    ebx, ebx
0x18002a8bd  jnz     short loc_18002A8C5
0x18002a8bf  cmp     byte ptr [rcx+19h], 5
0x18002a8c3  jmp     short loc_18002A8C9
0x18002a8c5  cmp     byte ptr [rcx+19h], 2
0x18002a8c9  setnb   al
0x18002a8cc  cmp     rcx, r15
0x18002a8cf  jz      short loc_18002A8D5
0x18002a8d1  test    eax, eax
0x18002a8d3  jnz     short loc_18002A8D8
0x18002a8d5  xor     dil, dil
0x18002a8d8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002a8df  setnz   r8b
0x18002a8e3  test    dil, dil
0x18002a8e6  jnz     short loc_18002A8ED
0x18002a8e8  test    r8b, r8b
0x18002a8eb  jz      short loc_18002A912
0x18002a8ed  mov     r9, [rcx+28h]
0x18002a8f1  mov     dl, dil
0x18002a8f4  mov     rcx, [rcx+10h]
0x18002a8f8  mov     [rsp+98h+var_48], ebx
0x18002a8fc  mov     [rsp+98h+var_50], rsi
0x18002a901  mov     [rsp+98h+var_60], r14
0x18002a906  mov     [rsp+98h+var_68], 0Dh
0x18002a90d  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002a912  mov     eax, ebx
0x18002a914  add     rsp, 60h
0x18002a918  pop     r15
0x18002a91a  pop     r14
0x18002a91c  pop     r13
0x18002a91e  pop     rdi
0x18002a91f  pop     rsi
0x18002a920  pop     rbp
0x18002a921  pop     rbx
0x18002a922  retn
```
