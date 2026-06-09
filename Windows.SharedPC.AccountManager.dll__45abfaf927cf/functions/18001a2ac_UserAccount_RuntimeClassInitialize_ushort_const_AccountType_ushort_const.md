# UserAccount::RuntimeClassInitialize(ushort const *,AccountType,ushort const *)

- ea: `0x18001a2ac`
- end: `0x18001a3e4`
- name: `?RuntimeClassInitialize@UserAccount@@QEAAJPEBGW4AccountType@@0@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014384`

## callees

- `0x180005120`
- `0x180008a38`
- `0x180013c1c`
- `0x180019c34`
- `0x18001a2ac`
- `0x18001a3f0`
- `0x18001a4c0`
- `0x18001a50c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a3aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a3aa`

## string_xrefs

- `0x18001a2ec`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccount.cpp`
- `0x18001a327`: `Created user account for user %ws. Account type: %d.`
- `0x18001a387`: `Loaded the last accessed time for user %ws. LastAccessedTime: 0x%I64x.`

## pseudocode

```c
__int64 __fastcall UserAccount::RuntimeClassInitialize(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  int v8; // ebx
  __int64 v9; // rdx
  const struct _FILETIME *v11; // rdx
  unsigned __int64 v12; // rax
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+10h] BYREF

  SystemTimeAsFileTime = (struct _FILETIME)a2;
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         a1 + 56,
         a2,
         0xFFFFFFFFFFFFFFFFuLL);
  if ( v8 < 0 )
  {
    v9 = 10;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccount.cpp",
      (const char *)(unsigned int)v8,
      v13);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           a1 + 80,
           a4,
           0xFFFFFFFFFFFFFFFFuLL);
    if ( v8 < 0 )
    {
      v9 = 15;
      goto LABEL_3;
    }
  }
  AccountsTelemetry::TraceLoggingInfo("Created user account for user %ws. Account type: %d.", a2, a3);
  *(_DWORD *)(a1 + 104) = a3;
  if ( a3 - 2 <= 1 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 120);
    v8 = Microsoft::WRL::Details::MakeAndInitialize<UserAccountPersistence,IUserAccountPersistence,unsigned short const * &>((void **)(a1 + 120));
    if ( v8 < 0 )
    {
      v9 = 27;
      goto LABEL_3;
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 120) + 32LL))(*(_QWORD *)(a1 + 120), a1 + 48);
    AccountsTelemetry::TraceLoggingInfo(
      "Loaded the last accessed time for user %ws. LastAccessedTime: 0x%I64x.",
      a2,
      *(_QWORD *)(a1 + 48));
    if ( !*(_QWORD *)(a1 + 48) )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v12 = wil::FileTime::ToInt64((wil::FileTime *)&SystemTimeAsFileTime, v11);
      UserAccount::SetLastAccessedTime((UserAccount *)a1, v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001a2ac  mov     [rsp+arg_0], rbx
0x18001a2b1  mov     [rsp+arg_10], rbp
0x18001a2b6  mov     qword ptr [rsp+SystemTimeAsFileTime.dwLowDateTime], rdx
0x18001a2bb  push    rsi
0x18001a2bc  push    rdi
0x18001a2bd  push    r14; int
0x18001a2bf  sub     rsp, 20h
0x18001a2c3  mov     esi, r8d
0x18001a2c6  mov     rdi, rcx
0x18001a2c9  add     rcx, 38h ; '8'
0x18001a2cd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a2d1  mov     rbp, r9
0x18001a2d4  mov     r14, rdx
0x18001a2d7  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001a2dc  mov     ebx, eax
0x18001a2de  test    eax, eax
0x18001a2e0  jns     short loc_18001A302
0x18001a2e2  mov     edx, 0Ah; void *
0x18001a2e7  mov     rcx, [rsp+38h]; this
0x18001a2ec  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001a2f3  mov     r9d, ebx; char *
0x18001a2f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2fb  mov     eax, ebx
0x18001a2fd  jmp     loc_18001A3D1
0x18001a302  test    rbp, rbp
0x18001a305  jz      short loc_18001A324
0x18001a307  lea     rcx, [rdi+50h]
0x18001a30b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a30f  mov     rdx, rbp
0x18001a312  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001a317  mov     ebx, eax
0x18001a319  test    eax, eax
0x18001a31b  jns     short loc_18001A324
0x18001a31d  mov     edx, 0Fh
0x18001a322  jmp     short loc_18001A2E7
0x18001a324  mov     r8d, esi
0x18001a327  lea     rcx, aCreatedUserAcc; "Created user account for user %ws. Acco"...
0x18001a32e  mov     rdx, r14
0x18001a331  call    ?TraceLoggingInfo@AccountsTelemetry@@SAXPEBDZZ; AccountsTelemetry::TraceLoggingInfo(char const *,...)
0x18001a336  lea     eax, [rsi-2]
0x18001a339  mov     [rdi+68h], esi
0x18001a33c  cmp     eax, 1
0x18001a33f  ja      loc_18001A3CF
0x18001a345  lea     rsi, [rdi+78h]
0x18001a349  mov     rcx, rsi
0x18001a34c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a351  lea     rdx, [rsp+38h+SystemTimeAsFileTime]
0x18001a356  mov     rcx, rsi; void **
0x18001a359  call    ??$MakeAndInitialize@VUserAccountPersistence@@UIUserAccountPersistence@@AEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAUIUserAccountPersistence@@AEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<UserAccountPersistence,IUserAccountPersistence,ushort const * &>(IUserAccountPersistence * *,ushort const * &)
0x18001a35e  mov     ebx, eax
0x18001a360  test    eax, eax
0x18001a362  jns     short loc_18001A36E
0x18001a364  mov     edx, 1Bh
0x18001a369  jmp     loc_18001A2E7
0x18001a36e  mov     rcx, [rsi]
0x18001a371  lea     rbx, [rdi+30h]
0x18001a375  mov     rdx, rbx
0x18001a378  mov     rax, [rcx]
0x18001a37b  mov     rax, [rax+20h]
0x18001a37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a384  mov     r8, [rbx]
0x18001a387  lea     rcx, aLoadedTheLastA; "Loaded the last accessed time for user "...
0x18001a38e  mov     rdx, r14
0x18001a391  call    ?TraceLoggingInfo@AccountsTelemetry@@SAXPEBDZZ; AccountsTelemetry::TraceLoggingInfo(char const *,...)
0x18001a396  cmp     qword ptr [rbx], 0
0x18001a39a  jnz     short loc_18001A3CF
0x18001a39c  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a3a1  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001a3aa  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a3b0  mov     rax, qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime]
0x18001a3b5  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; this
0x18001a3ba  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001a3bf  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x18001a3c4  mov     rdx, rax; unsigned __int64
0x18001a3c7  mov     rcx, rdi; this
0x18001a3ca  call    ?SetLastAccessedTime@UserAccount@@UEAAJ_K@Z; UserAccount::SetLastAccessedTime(unsigned __int64)
0x18001a3cf  xor     eax, eax
0x18001a3d1  mov     rbx, [rsp+38h+arg_0]
0x18001a3d6  mov     rbp, [rsp+38h+arg_10]
0x18001a3db  add     rsp, 20h
0x18001a3df  pop     r14
0x18001a3e1  pop     rdi
0x18001a3e2  pop     rsi
0x18001a3e3  retn
```
