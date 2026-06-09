# DeviceFinder::FindInstances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12___

- ea: `0x180017df0`
- end: `0x180017eb9`
- name: `DeviceFinder::FindInstances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12___`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017c70`

## callees

- `0x180017c18`
- `0x180017df0`
- `0x1800252bc`
- `0x18005a8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017e3b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e58`

## pseudocode

```c
__int64 __fastcall DeviceFinder::FindInstances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12___(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v7; // eax
  HANDLE EventW; // rax
  __int64 v9; // rcx
  signed int LastError; // eax
  signed int v11; // ebx
  void **v13; // [rsp+48h] [rbp-20h] BYREF
  __int64 v14; // [rsp+50h] [rbp-18h]
  __int64 v15; // [rsp+58h] [rbp-10h]

  v14 = 0;
  v7 = 2;
  do
  {
    v13 = &Microsoft::WRL::Wrappers::Event::`vftable';
    --v7;
  }
  while ( v7 );
  v15 = a6;
  EventW = CreateEventW(0, 0, 0, 0);
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(&v13, EventW);
  if ( v14 )
    goto LABEL_7;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 >= 0 )
  {
LABEL_7:
    v11 = DeviceFinder::RunQuery(v9, a2);
    if ( v11 >= 0 )
      v11 = 0;
  }
  v13 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(&v13);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180017df0  mov     [rsp+arg_0], rbx
0x180017df5  push    rdi
0x180017df6  sub     rsp, 60h
0x180017dfa  mov     rdi, rdx
0x180017dfd  mov     [rsp+68h+var_28], 0
0x180017e05  mov     [rsp+68h+var_18], 0
0x180017e0e  mov     eax, 2
0x180017e13  lea     rcx, ??_7Event@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::Event::`vftable'
0x180017e1a  mov     [rsp+68h+var_20], rcx
0x180017e1f  sub     eax, 1
0x180017e22  jnz     short loc_180017E13
0x180017e24  mov     rax, [rsp+68h+arg_28]
0x180017e2c  xor     r9d, r9d; lpName
0x180017e2f  xor     r8d, r8d; bInitialState
0x180017e32  mov     [rsp+68h+var_10], rax
0x180017e37  xor     edx, edx; bManualReset
0x180017e39  xor     ecx, ecx; lpEventAttributes
0x180017e3b  call    cs:__imp_CreateEventW
0x180017e41  mov     rdx, rax
0x180017e44  lea     rcx, [rsp+68h+var_20]
0x180017e49  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x180017e4e  mov     rax, [rsp+68h+var_18]
0x180017e53  test    rax, rax
0x180017e56  jnz     short loc_180017E76
0x180017e58  call    cs:__imp_GetLastError
0x180017e5e  mov     ebx, eax
0x180017e60  test    eax, eax
0x180017e62  jle     short loc_180017E6D
0x180017e64  movzx   ebx, ax
0x180017e67  or      ebx, 80070000h
0x180017e6d  test    ebx, ebx
0x180017e6f  js      short loc_180017E96
0x180017e71  mov     rax, [rsp+68h+var_18]
0x180017e76  mov     [rsp+68h+var_30], rax
0x180017e7b  mov     rdx, rdi
0x180017e7e  lea     rax, [rsp+68h+var_28]
0x180017e83  mov     [rsp+68h+var_38], rax
0x180017e88  call    ?RunQuery@DeviceFinder@@SAJW4_DEV_OBJECT_TYPE@@PEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@KP6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z44@Z; DeviceFinder::RunQuery(_DEV_OBJECT_TYPE,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ulong,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,void *)
0x180017e8d  test    eax, eax
0x180017e8f  mov     ebx, eax
0x180017e91  cmovns  ebx, [rsp+68h+var_28]
0x180017e96  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180017e9d  lea     rcx, [rsp+68h+var_20]
0x180017ea2  mov     [rsp+68h+var_20], rax
0x180017ea7  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x180017eac  mov     eax, ebx
0x180017eae  mov     rbx, [rsp+68h+arg_0]
0x180017eb3  add     rsp, 60h
0x180017eb7  pop     rdi
0x180017eb8  retn
```
