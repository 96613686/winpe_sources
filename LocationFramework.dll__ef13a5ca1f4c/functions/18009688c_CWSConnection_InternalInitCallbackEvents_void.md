# CWSConnection::InternalInitCallbackEvents(void)

- ea: `0x18009688c`
- end: `0x180096a26`
- name: `?InternalInitCallbackEvents@CWSConnection@@AEAAJXZ`
- size: `410`
- prototype: `__int64 __fastcall(CWSConnection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18012521c`

## callees

- `0x180048a04`
- `0x18009688c`
- `0x1800a9e0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800968ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180096934`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009695c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180096986`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800969c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800969ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800968ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180096934`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009695c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180096986`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800969c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800969ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800969a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800969a2`

## pseudocode

```c
__int64 __fastcall CWSConnection::InternalInitCallbackEvents(CWSConnection *this)
{
  HANDLE EventW; // rax
  signed int v3; // eax
  unsigned int v4; // edi
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  HANDLE v7; // rax
  _QWORD *v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  signed int LastError; // eax
  __int64 v13; // rbx
  HANDLE v14; // rax
  __int64 v15; // rbx
  HANDLE v16; // rax

  if ( !*((_QWORD *)this + 12) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 12) = EventW;
    if ( !EventW )
      goto LABEL_3;
  }
  v4 = 0;
  if ( !*((_QWORD *)this + 10) )
  {
    v5 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
    v6 = v5;
    if ( !v5 )
    {
      *((_QWORD *)this + 10) = 0;
      return (unsigned int)-2147024882;
    }
    *v5 = 0;
    v5[1] = 0;
    v5[2] = 0;
    v5[3] = 0;
    v5[4] = 0;
    v5[5] = 0;
    v5[6] = 0;
    v5[7] = 0;
    v5[8] = 0;
    *((_QWORD *)this + 10) = v5;
    v7 = CreateEventW(0, 0, 0, 0);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v6,
      v7);
    v8 = (_QWORD *)*((_QWORD *)this + 10);
    if ( !*v8 )
      goto LABEL_3;
    v9 = CreateEventW(0, 0, 0, 0);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v8 + 1,
      v9);
    v10 = *((_QWORD *)this + 10);
    if ( !*(_QWORD *)(v10 + 8) )
      goto LABEL_3;
    v11 = CreateEventW(0, 0, 0, 0);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v10 + 16,
      v11);
    if ( !*(_QWORD *)(*((_QWORD *)this + 10) + 16LL) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    v13 = *((_QWORD *)this + 10);
    v14 = CreateEventW(0, 0, 0, 0);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v13 + 24,
      v14);
    v15 = *((_QWORD *)this + 10);
    if ( !*(_QWORD *)(v15 + 24)
      || (v16 = CreateEventW(0, 0, 0, 0),
          _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
            v15 + 32,
            v16),
          !*(_QWORD *)(*((_QWORD *)this + 10) + 32LL)) )
    {
LABEL_3:
      v3 = GetLastError();
      v4 = v3;
      if ( v3 > 0 )
        return (unsigned __int16)v3 | 0x80070000;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18009688c  push    rbx
0x18009688e  push    rbp
0x18009688f  push    rdi
0x180096890  push    r14
0x180096892  sub     rsp, 28h
0x180096896  xor     r14d, r14d
0x180096899  mov     rbp, rcx
0x18009689c  cmp     [rcx+60h], r14
0x1800968a0  jnz     short loc_1800968D9
0x1800968a2  xor     r9d, r9d; lpName
0x1800968a5  xor     r8d, r8d; bInitialState
0x1800968a8  xor     edx, edx; bManualReset
0x1800968aa  xor     ecx, ecx; lpEventAttributes
0x1800968ac  call    cs:__imp_CreateEventW
0x1800968b2  mov     [rbp+60h], rax
0x1800968b6  test    rax, rax
0x1800968b9  jnz     short loc_1800968D9
0x1800968bb  call    cs:__imp_GetLastError
0x1800968c1  mov     edi, eax
0x1800968c3  test    eax, eax
0x1800968c5  jle     loc_180096A1A
0x1800968cb  movzx   edi, ax
0x1800968ce  or      edi, 80070000h
0x1800968d4  jmp     loc_180096A1A
0x1800968d9  mov     edi, r14d
0x1800968dc  cmp     [rbp+50h], r14
0x1800968e0  jnz     loc_180096A1A
0x1800968e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800968ed  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800968f2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800968f7  mov     rbx, rax
0x1800968fa  test    rax, rax
0x1800968fd  jz      loc_180096A11
0x180096903  mov     [rax], r14
0x180096906  xor     r9d, r9d; lpName
0x180096909  mov     [rax+8], r14
0x18009690d  xor     r8d, r8d; bInitialState
0x180096910  mov     [rax+10h], r14
0x180096914  xor     edx, edx; bManualReset
0x180096916  mov     [rax+18h], r14
0x18009691a  xor     ecx, ecx; lpEventAttributes
0x18009691c  mov     [rax+20h], r14
0x180096920  mov     [rax+28h], r14
0x180096924  mov     [rax+30h], r14
0x180096928  mov     [rax+38h], r14
0x18009692c  mov     [rax+40h], r14
0x180096930  mov     [rbp+50h], rax
0x180096934  call    cs:__imp_CreateEventW
0x18009693a  mov     rdx, rax
0x18009693d  mov     rcx, rbx
0x180096940  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180096945  mov     rbx, [rbp+50h]
0x180096949  cmp     [rbx], r14
0x18009694c  jz      loc_1800968BB
0x180096952  xor     r9d, r9d; lpName
0x180096955  xor     r8d, r8d; bInitialState
0x180096958  xor     edx, edx; bManualReset
0x18009695a  xor     ecx, ecx; lpEventAttributes
0x18009695c  call    cs:__imp_CreateEventW
0x180096962  mov     rdx, rax
0x180096965  lea     rcx, [rbx+8]
0x180096969  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18009696e  mov     rbx, [rbp+50h]
0x180096972  cmp     [rbx+8], r14
0x180096976  jz      loc_1800968BB
0x18009697c  xor     r9d, r9d; lpName
0x18009697f  xor     r8d, r8d; bInitialState
0x180096982  xor     edx, edx; bManualReset
0x180096984  xor     ecx, ecx; lpEventAttributes
0x180096986  call    cs:__imp_CreateEventW
0x18009698c  mov     rdx, rax
0x18009698f  lea     rcx, [rbx+10h]
0x180096993  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180096998  mov     rax, [rbp+50h]
0x18009699c  cmp     [rax+10h], r14
0x1800969a0  jnz     short loc_1800969B7
0x1800969a2  call    cs:__imp_GetLastError
0x1800969a8  mov     edi, eax
0x1800969aa  test    eax, eax
0x1800969ac  jle     short loc_1800969B7
0x1800969ae  movzx   edi, ax
0x1800969b1  or      edi, 80070000h
0x1800969b7  mov     rbx, [rbp+50h]
0x1800969bb  xor     r9d, r9d; lpName
0x1800969be  xor     r8d, r8d; bInitialState
0x1800969c1  xor     edx, edx; bManualReset
0x1800969c3  xor     ecx, ecx; lpEventAttributes
0x1800969c5  call    cs:__imp_CreateEventW
0x1800969cb  mov     rdx, rax
0x1800969ce  lea     rcx, [rbx+18h]
0x1800969d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800969d7  mov     rbx, [rbp+50h]
0x1800969db  cmp     [rbx+18h], r14
0x1800969df  jz      loc_1800968BB
0x1800969e5  xor     r9d, r9d; lpName
0x1800969e8  xor     r8d, r8d; bInitialState
0x1800969eb  xor     edx, edx; bManualReset
0x1800969ed  xor     ecx, ecx; lpEventAttributes
0x1800969ef  call    cs:__imp_CreateEventW
0x1800969f5  mov     rdx, rax
0x1800969f8  lea     rcx, [rbx+20h]
0x1800969fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180096a01  mov     rax, [rbp+50h]
0x180096a05  cmp     [rax+20h], r14
0x180096a09  jz      loc_1800968BB
0x180096a0f  jmp     short loc_180096A1A
0x180096a11  mov     [rbp+50h], r14
0x180096a15  mov     edi, 8007000Eh
0x180096a1a  mov     eax, edi
0x180096a1c  add     rsp, 28h
0x180096a20  pop     r14
0x180096a22  pop     rdi
0x180096a23  pop     rbp
0x180096a24  pop     rbx
0x180096a25  retn
```
