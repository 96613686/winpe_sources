# ConnectedStorage::Service::ScheduledTaskOperation(ConnectedStorage::SimpleHStringWrapper const &)

- ea: `0x180016364`
- end: `0x180016497`
- name: `?ScheduledTaskOperation@Service@ConnectedStorage@@QEAAXAEBVSimpleHStringWrapper@2@@Z`
- size: `307`
- prototype: `void __fastcall(ConnectedStorage::Service *this, const struct ConnectedStorage::SimpleHStringWrapper *, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001cc30`

## callees

- `0x18000aae4`
- `0x18000cb9c`
- `0x180011c0c`
- `0x180012f7c`
- `0x180016364`
- `0x180016bbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001644b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001647b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001644b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001647b`

## string_xrefs

- `0x180016485`: `Service::ScheduledTaskOperation called with an invalid operation type.`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall ConnectedStorage::Service::ScheduledTaskOperation(
        ConnectedStorage::Service *this,
        const struct ConnectedStorage::SimpleHStringWrapper *a2,
        char *a3)
{
  __int64 v5; // rax
  char v6; // bl
  __int64 v7; // rax
  char v8; // bl
  __int64 v9; // rax
  char v10; // bl
  bool v11; // dl
  __int64 v12; // rax
  char v13; // bl
  __int64 v14; // rax
  char v15; // bl
  const unsigned __int16 *v16; // r8
  LPCRITICAL_SECTION v17[3]; // [rsp+20h] [rbp-18h] BYREF
  HSTRING string; // [rsp+60h] [rbp+28h] BYREF

  ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)v17, this, a3);
  v5 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"standby");
  v6 = ConnectedStorage::SimpleHStringWrapper::operator==(a2, v5);
  WindowsDeleteString(string);
  if ( !v6 )
  {
    v7 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"maintenance");
    v8 = ConnectedStorage::SimpleHStringWrapper::operator==(a2, v7);
    WindowsDeleteString(string);
    if ( !v8 )
    {
      v9 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"testenter");
      v10 = ConnectedStorage::SimpleHStringWrapper::operator==(a2, v9);
      WindowsDeleteString(string);
      if ( v10 )
      {
        v11 = 1;
LABEL_5:
        ConnectedStorage::Power::SimulateStateChange((ConnectedStorage::Service *)((char *)this + 160), v11);
        goto LABEL_6;
      }
      v12 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"testexit");
      v13 = ConnectedStorage::SimpleHStringWrapper::operator==(a2, v12);
      WindowsDeleteString(string);
      if ( v13 )
      {
        v11 = 0;
        goto LABEL_5;
      }
      v14 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"logon");
      v15 = ConnectedStorage::SimpleHStringWrapper::operator==(a2, v14);
      WindowsDeleteString(string);
      if ( !v15 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)0x80070057LL,
          (int)L"Service::ScheduledTaskOperation called with an invalid operation type.",
          v16);
    }
  }
LABEL_6:
  LeaveCriticalSection(v17[0]);
}

```

## disassembly

```asm
0x180016364  push    rbp
0x180016366  push    rbx
0x180016367  push    rsi
0x180016368  push    rdi
0x180016369  mov     rbp, rsp
0x18001636c  sub     rsp, 38h
0x180016370  mov     rdi, rdx
0x180016373  mov     rsi, rcx
0x180016376  mov     rdx, rcx; struct ConnectedStorage::Mutex *
0x180016379  lea     rcx, [rbp+var_18]; this
0x18001637d  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180016382  nop
0x180016383  lea     rdx, aStandby; "standby"
0x18001638a  lea     rcx, [rbp+string]; string
0x18001638e  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180016393  nop
0x180016394  mov     rdx, rax
0x180016397  mov     rcx, rdi
0x18001639a  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x18001639f  mov     bl, al
0x1800163a1  mov     rcx, [rbp+string]; string
0x1800163a5  call    cs:__imp_WindowsDeleteString
0x1800163ab  test    bl, bl
0x1800163ad  jnz     short loc_180016416
0x1800163af  lea     rdx, aMaintenance; "maintenance"
0x1800163b6  lea     rcx, [rbp+string]; string
0x1800163ba  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x1800163bf  nop
0x1800163c0  mov     rdx, rax
0x1800163c3  mov     rcx, rdi
0x1800163c6  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x1800163cb  mov     bl, al
0x1800163cd  mov     rcx, [rbp+string]; string
0x1800163d1  call    cs:__imp_WindowsDeleteString
0x1800163d7  test    bl, bl
0x1800163d9  jnz     short loc_180016416
0x1800163db  lea     rdx, aTestenter; "testenter"
0x1800163e2  lea     rcx, [rbp+string]; string
0x1800163e6  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x1800163eb  nop
0x1800163ec  mov     rdx, rax
0x1800163ef  mov     rcx, rdi
0x1800163f2  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x1800163f7  mov     bl, al
0x1800163f9  mov     rcx, [rbp+string]; string
0x1800163fd  call    cs:__imp_WindowsDeleteString
0x180016403  test    bl, bl
0x180016405  jz      short loc_180016429
0x180016407  mov     dl, 1; bool
0x180016409  lea     rcx, [rsi+0A0h]; this
0x180016410  call    ?SimulateStateChange@Power@ConnectedStorage@@QEAAX_N@Z; ConnectedStorage::Power::SimulateStateChange(bool)
0x180016415  nop
0x180016416  mov     rcx, [rbp+var_18]
0x18001641a  add     rsp, 38h
0x18001641e  pop     rdi
0x18001641f  pop     rsi
0x180016420  pop     rbx
0x180016421  pop     rbp
0x180016422  jmp     cs:__imp_LeaveCriticalSection
0x180016429  lea     rdx, aTestexit; "testexit"
0x180016430  lea     rcx, [rbp+string]; string
0x180016434  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180016439  nop
0x18001643a  mov     rdx, rax
0x18001643d  mov     rcx, rdi
0x180016440  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x180016445  mov     bl, al
0x180016447  mov     rcx, [rbp+string]; string
0x18001644b  call    cs:__imp_WindowsDeleteString
0x180016451  test    bl, bl
0x180016453  jz      short loc_180016459
0x180016455  xor     edx, edx
0x180016457  jmp     short loc_180016409
0x180016459  lea     rdx, aLogon; "logon"
0x180016460  lea     rcx, [rbp+string]; string
0x180016464  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180016469  nop
0x18001646a  mov     rdx, rax
0x18001646d  mov     rcx, rdi
0x180016470  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x180016475  mov     bl, al
0x180016477  mov     rcx, [rbp+string]; string
0x18001647b  call    cs:__imp_WindowsDeleteString
0x180016481  test    bl, bl
0x180016483  jnz     short loc_180016416
0x180016485  lea     rdx, aServiceSchedul; "Service::ScheduledTaskOperation called "...
0x18001648c  mov     ecx, 80070057h; this
0x180016491  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
