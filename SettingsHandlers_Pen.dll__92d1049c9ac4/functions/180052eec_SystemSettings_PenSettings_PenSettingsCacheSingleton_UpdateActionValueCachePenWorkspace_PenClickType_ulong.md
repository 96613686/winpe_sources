# SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(PenClickType,ulong)

- ea: `0x180052eec`
- end: `0x180052f97`
- name: `?UpdateActionValueCachePenWorkspace@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@K@Z`
- size: `171`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180028910`
- `0x180029580`
- `0x18002faf0`
- `0x180030130`

## callees

- `0x180005eec`
- `0x180019b90`
- `0x180052eec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180052f3e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180052f3e`

## string_xrefs

- `0x180052f1b`: `Create`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(
        int a1,
        int a2)
{
  const wchar_t *v2; // rdi
  int v4; // edx
  int v5; // edx
  int v6; // ebx
  int v7; // ebx
  __int64 *v8; // rcx
  RTL_SRWLOCK *v10; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  if ( a2 )
  {
    v4 = a2 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 == 1 )
          v2 = L"Capture";
      }
      else
      {
        v2 = L"Create";
      }
    }
    else
    {
      v2 = L"Remember";
    }
  }
  else
  {
    v2 = L"Home";
  }
  AcquireSRWLockExclusive(&SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock);
  v10 = &SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock;
  v6 = a1 - 1;
  if ( !v6 )
  {
    v8 = &qword_18007C6F8;
    goto LABEL_15;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v8 = &qword_18007C718;
    goto LABEL_15;
  }
  if ( v7 == 1 )
  {
    v8 = &qword_18007C738;
LABEL_15:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v8, v2, -1);
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x180052eec  mov     [rsp+arg_0], rbx
0x180052ef1  mov     [rsp+arg_8], rsi
0x180052ef6  push    rdi
0x180052ef7  sub     rsp, 20h
0x180052efb  xor     edi, edi
0x180052efd  mov     ebx, ecx
0x180052eff  test    edx, edx
0x180052f01  jz      short loc_180052F2D
0x180052f03  sub     edx, 1
0x180052f06  jz      short loc_180052F24
0x180052f08  sub     edx, 1
0x180052f0b  jz      short loc_180052F1B
0x180052f0d  cmp     edx, 1
0x180052f10  jnz     short loc_180052F34
0x180052f12  lea     rdi, aCapture; "Capture"
0x180052f19  jmp     short loc_180052F34
0x180052f1b  lea     rdi, aCreate; "Create"
0x180052f22  jmp     short loc_180052F34
0x180052f24  lea     rdi, aRemember; "Remember"
0x180052f2b  jmp     short loc_180052F34
0x180052f2d  lea     rdi, aHome; "Home"
0x180052f34  lea     rsi, ?m_penSettingsCacheLock@PenSettingsCacheSingleton@PenSettings@SystemSettings@@0Vsrwlock@wil@@A; wil::srwlock SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock
0x180052f3b  mov     rcx, rsi; SRWLock
0x180052f3e  call    cs:__imp_AcquireSRWLockExclusive
0x180052f44  mov     [rsp+28h+arg_10], rsi
0x180052f49  sub     ebx, 1
0x180052f4c  jz      short loc_180052F6A
0x180052f4e  sub     ebx, 1
0x180052f51  jz      short loc_180052F61
0x180052f53  cmp     ebx, 1
0x180052f56  jnz     short loc_180052F7D
0x180052f58  lea     rcx, qword_18007C738
0x180052f5f  jmp     short loc_180052F71
0x180052f61  lea     rcx, qword_18007C718
0x180052f68  jmp     short loc_180052F71
0x180052f6a  lea     rcx, qword_18007C6F8
0x180052f71  or      r8, 0FFFFFFFFFFFFFFFFh
0x180052f75  mov     rdx, rdi
0x180052f78  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180052f7d  lea     rcx, [rsp+28h+arg_10]
0x180052f82  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180052f87  mov     rbx, [rsp+28h+arg_0]
0x180052f8c  mov     rsi, [rsp+28h+arg_8]
0x180052f91  add     rsp, 20h
0x180052f95  pop     rdi
0x180052f96  retn
```
