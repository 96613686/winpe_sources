# CreateAndGetLockFile(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)

- ea: `0x1800290a4`
- end: `0x18002933f`
- name: `?CreateAndGetLockFile@@YAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@0@Z`
- size: `667`
- prototype: `__int64 __fastcall(_QWORD **, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029644`
- `0x1800299f4`

## callees

- `0x180002590`
- `0x1800086c4`
- `0x18000f29c`
- `0x180013890`
- `0x1800285f0`
- `0x1800290a4`
- `0x180033010`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800291af`
- `ntdll!NtCreateFile` at `0x1800291af`
- `ntdll!RtlInitUnicodeString` at `0x180029117`
- `ntdll!RtlInitUnicodeString` at `0x180029117`

## pseudocode

```c
__int64 __fastcall CreateAndGetLockFile(_QWORD **a1, _QWORD *a2)
{
  const WCHAR *v4; // rdx
  _QWORD *v5; // rax
  void **v6; // rax
  NTSTATUS v7; // eax
  int v8; // edx
  unsigned int v9; // esi
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rdi
  __int64 v13; // r14
  volatile signed __int32 *v14; // rsi
  volatile signed __int32 *v15; // rdi
  __int128 v17; // [rsp+60h] [rbp-59h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-49h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-39h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-9h] BYREF
  PCWSTR SourceString[2]; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+D0h] [rbp+17h]
  unsigned __int64 v23; // [rsp+D8h] [rbp+1Fh]

  *(_OWORD *)SourceString = 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,unsigned short const *>(SourceString, L"secure_file.lock", 16);
  DestinationString = 0;
  v4 = (const WCHAR *)SourceString;
  if ( v23 > 7 )
    v4 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v4);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ObjectAttributes.Length = 48;
  v5 = *a1;
  if ( *a1 )
    v5 = (_QWORD *)*v5;
  ObjectAttributes.RootDirectory = v5;
  ObjectAttributes.Attributes = 4160;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v17 = 0;
  v6 = (void **)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::operator&(&v17);
  v7 = NtCreateFile(v6, 0x13019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0x1060u, 0, 0);
  if ( v7 >= 0 )
  {
    v11 = v17;
    if ( (_QWORD)v17 && ((*(_QWORD *)v17 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v12 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
      if ( *((_QWORD *)&v17 + 1) )
      {
        v13 = *((_QWORD *)&v17 + 1) + 8LL;
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL));
      }
      else
      {
        v13 = 8;
      }
      *a2 = v11;
      v14 = (volatile signed __int32 *)a2[1];
      a2[1] = v12;
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      v9 = 0;
    }
    else
    {
      v15 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
      if ( *((_QWORD *)&v17 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      v9 = -2147023728;
    }
  }
  else
  {
    v9 = wil::details::NtStatusToHr((wil::details *)(unsigned int)v7, v8);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
    if ( *((_QWORD *)&v17 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
  }
  std::wstring::~wstring(SourceString);
  return v9;
}

```

## disassembly

```asm
0x1800290a4  mov     [rsp-8+arg_10], rbx
0x1800290a9  push    rbp
0x1800290aa  push    rsi
0x1800290ab  push    rdi
0x1800290ac  push    r14
0x1800290ae  push    r15
0x1800290b0  lea     rbp, [rsp-37h]
0x1800290b5  sub     rsp, 0F0h
0x1800290bc  mov     rax, cs:__security_cookie
0x1800290c3  xor     rax, rsp
0x1800290c6  mov     [rbp+57h+var_30], rax
0x1800290ca  mov     r15, rdx
0x1800290cd  mov     rbx, rcx
0x1800290d0  xorps   xmm0, xmm0
0x1800290d3  movups  xmmword ptr [rbp+57h+SourceString], xmm0
0x1800290d7  mov     [rbp+57h+var_40], 0
0x1800290df  mov     [rbp+57h+var_38], 0
0x1800290e7  mov     r8d, 10h
0x1800290ed  lea     rdx, aSecureFileLock; "secure_file.lock"
0x1800290f4  lea     rcx, [rbp+57h+SourceString]
0x1800290f8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800290fd  nop
0x1800290fe  xorps   xmm0, xmm0
0x180029101  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180029105  lea     rdx, [rbp+57h+SourceString]
0x180029109  cmp     [rbp+57h+var_38], 7
0x18002910e  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x180029113  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180029117  call    cs:__imp_RtlInitUnicodeString
0x18002911d  xorps   xmm0, xmm0
0x180029120  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180029124  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180029128  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002912c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180029133  mov     rax, [rbx]
0x180029136  test    rax, rax
0x180029139  jz      short loc_18002913E
0x18002913b  mov     rax, [rax]
0x18002913e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180029142  mov     [rbp+57h+ObjectAttributes.Attributes], 1040h
0x180029149  lea     rax, [rbp+57h+DestinationString]
0x18002914d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180029151  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180029156  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002915a  movdqu  [rbp+57h+var_B0], xmm0
0x18002915f  lea     rcx, [rbp+57h+var_B0]
0x180029163  call    ??I?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>::operator&(void)
0x180029168  mov     rcx, rax; FileHandle
0x18002916b  mov     [rsp+110h+EaLength], 0; EaLength
0x180029173  mov     [rsp+110h+EaBuffer], 0; EaBuffer
0x18002917c  mov     [rsp+110h+CreateOptions], 1060h; CreateOptions
0x180029184  mov     eax, 3
0x180029189  mov     [rsp+110h+CreateDisposition], eax; CreateDisposition
0x18002918d  mov     [rsp+110h+ShareAccess], eax; ShareAccess
0x180029191  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x180029199  mov     [rsp+110h+AllocationSize], 0; AllocationSize
0x1800291a2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800291a6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800291aa  mov     edx, 13019Fh; DesiredAccess
0x1800291af  call    cs:__imp_NtCreateFile
0x1800291b5  test    eax, eax
0x1800291b7  jns     short loc_180029212
0x1800291b9  mov     ecx, eax; this
0x1800291bb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800291c0  mov     esi, eax
0x1800291c2  mov     rdi, qword ptr [rbp+57h+var_B0+8]
0x1800291c6  test    rdi, rdi
0x1800291c9  jz      loc_180029311
0x1800291cf  or      ebx, 0FFFFFFFFh
0x1800291d2  mov     ecx, ebx
0x1800291d4  lock xadd [rdi+8], ecx
0x1800291d9  add     ecx, ebx
0x1800291db  jnz     loc_180029311
0x1800291e1  mov     rdx, [rdi]
0x1800291e4  mov     rcx, rdi
0x1800291e7  mov     rax, [rdx]
0x1800291ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291ef  mov     eax, ebx
0x1800291f1  lock xadd [rdi+0Ch], eax
0x1800291f6  add     eax, ebx
0x1800291f8  jnz     loc_180029311
0x1800291fe  mov     rax, [rdi]
0x180029201  mov     rcx, rdi
0x180029204  mov     rax, [rax+8]
0x180029208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002920d  jmp     loc_180029311
0x180029212  mov     rcx, qword ptr [rbp+57h+var_B0]
0x180029216  test    rcx, rcx
0x180029219  jz      loc_1800292CD
0x18002921f  mov     rax, [rcx]
0x180029222  inc     rax
0x180029225  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002922b  jz      loc_1800292CD
0x180029231  mov     rdi, qword ptr [rbp+57h+var_B0+8]
0x180029235  test    rdi, rdi
0x180029238  jz      short loc_180029244
0x18002923a  lea     r14, [rdi+8]
0x18002923e  lock inc dword ptr [r14]
0x180029242  jmp     short loc_18002924A
0x180029244  mov     r14d, 8
0x18002924a  mov     [r15], rcx
0x18002924d  mov     rsi, [r15+8]
0x180029251  mov     [r15+8], rdi
0x180029255  or      ebx, 0FFFFFFFFh
0x180029258  test    rsi, rsi
0x18002925b  jz      short loc_180029291
0x18002925d  mov     eax, ebx
0x18002925f  lock xadd [rsi+8], eax
0x180029264  add     eax, ebx
0x180029266  jnz     short loc_180029291
0x180029268  mov     rax, [rsi]
0x18002926b  mov     rcx, rsi
0x18002926e  mov     rax, [rax]
0x180029271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029276  mov     eax, ebx
0x180029278  lock xadd [rsi+0Ch], eax
0x18002927d  add     eax, ebx
0x18002927f  jnz     short loc_180029291
0x180029281  mov     rax, [rsi]
0x180029284  mov     rcx, rsi
0x180029287  mov     rax, [rax+8]
0x18002928b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029290  nop
0x180029291  test    rdi, rdi
0x180029294  jz      short loc_1800292C9
0x180029296  mov     eax, ebx
0x180029298  lock xadd [r14], eax
0x18002929d  add     eax, ebx
0x18002929f  jnz     short loc_1800292C9
0x1800292a1  mov     rax, [rdi]
0x1800292a4  mov     rcx, rdi
0x1800292a7  mov     rax, [rax]
0x1800292aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292af  mov     eax, ebx
0x1800292b1  lock xadd [rdi+0Ch], eax
0x1800292b6  add     eax, ebx
0x1800292b8  jnz     short loc_1800292C9
0x1800292ba  mov     rax, [rdi]
0x1800292bd  mov     rcx, rdi
0x1800292c0  mov     rax, [rax+8]
0x1800292c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292c9  xor     esi, esi
0x1800292cb  jmp     short loc_180029311
0x1800292cd  mov     rdi, qword ptr [rbp+57h+var_B0+8]
0x1800292d1  test    rdi, rdi
0x1800292d4  jz      short loc_18002930C
0x1800292d6  or      ebx, 0FFFFFFFFh
0x1800292d9  mov     eax, ebx
0x1800292db  lock xadd [rdi+8], eax
0x1800292e0  add     eax, ebx
0x1800292e2  jnz     short loc_18002930C
0x1800292e4  mov     rax, [rdi]
0x1800292e7  mov     rcx, rdi
0x1800292ea  mov     rax, [rax]
0x1800292ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292f2  mov     eax, ebx
0x1800292f4  lock xadd [rdi+0Ch], eax
0x1800292f9  add     eax, ebx
0x1800292fb  jnz     short loc_18002930C
0x1800292fd  mov     rax, [rdi]
0x180029300  mov     rcx, rdi
0x180029303  mov     rax, [rax+8]
0x180029307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002930c  mov     esi, 80070490h
0x180029311  lea     rcx, [rbp+57h+SourceString]
0x180029315  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002931a  mov     eax, esi
0x18002931c  mov     rcx, [rbp+57h+var_30]
0x180029320  xor     rcx, rsp; StackCookie
0x180029323  call    __security_check_cookie
0x180029328  mov     rbx, [rsp+110h+arg_10]
0x180029330  add     rsp, 0F0h
0x180029337  pop     r15
0x180029339  pop     r14
0x18002933b  pop     rdi
0x18002933c  pop     rsi
0x18002933d  pop     rbp
0x18002933e  retn
```
