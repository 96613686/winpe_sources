# CPointInTimeRestoreHelper::~CPointInTimeRestoreHelper(void)

- ea: `0x18000bdcc`
- end: `0x18000beeb`
- name: `??1CPointInTimeRestoreHelper@@QEAA@XZ`
- size: `287`
- prototype: `void __fastcall(CPointInTimeRestoreHelper *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000deec`
- `0x18000df1c`
- `0x18000e110`

## callees

- `0x18000bdcc`
- `0x18000bef4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be6c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000be4d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bec9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000be4d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bec9`
- `WDSCORE!CurrentIP` at `0x18000bdf8`
- `WDSCORE!CurrentIP` at `0x18000be74`
- `WDSCORE!CurrentIP` at `0x18000bdf8`
- `WDSCORE!CurrentIP` at `0x18000be74`

## string_xrefs

- `0x18000bde2`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
void __fastcall CPointInTimeRestoreHelper::~CPointInTimeRestoreHelper(CPointInTimeRestoreHelper *this)
{
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax

  if ( *((_QWORD *)this + 1) )
  {
    LastError = GetLastError();
    v3 = CurrentIP();
    v4 = ConstructPartialMsgW(
           0x4000000u,
           "CPointInTimeRestoreHelper::~CPointInTimeRestoreHelper: Releasing PITR settings interface");
    WdsSetupLogMessageW(
      v4,
      0,
      L"D",
      0,
      16,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::~CPointInTimeRestoreHelper",
      v3,
      LastError,
      0,
      0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 192LL))(*((_QWORD *)this + 1));
  }
  if ( *(_QWORD *)this )
  {
    v5 = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(
           0x4000000u,
           "CPointInTimeRestoreHelper::~CPointInTimeRestoreHelper: Releasing PITR base interface");
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      22,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::~CPointInTimeRestoreHelper",
      v6,
      v5,
      0,
      0);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 72LL))(*(_QWORD *)this);
  }
}

```

## disassembly

```asm
0x18000bdcc  push    rbx
0x18000bdce  push    rsi
0x18000bdcf  push    rdi
0x18000bdd0  push    r12
0x18000bdd2  push    r15
0x18000bdd4  sub     rsp, 60h
0x18000bdd8  mov     rsi, rcx
0x18000bddb  lea     r15, aCpointintimere; "CPointInTimeRestoreHelper::~CPointInTim"...
0x18000bde2  lea     r12, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000bde9  cmp     qword ptr [rcx+8], 0
0x18000bdee  jz      short loc_18000BE66
0x18000bdf0  call    cs:__imp_GetLastError
0x18000bdf6  mov     edi, eax
0x18000bdf8  call    cs:__imp_CurrentIP
0x18000bdfe  mov     rbx, rax
0x18000be01  lea     rdx, aCpointintimere_28; "CPointInTimeRestoreHelper::~CPointInTim"...
0x18000be08  mov     ecx, 4000000h; unsigned int
0x18000be0d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000be12  mov     [rsp+88h+var_38], 0
0x18000be1a  mov     [rsp+88h+var_40], 0
0x18000be23  mov     [rsp+88h+var_48], edi
0x18000be27  mov     [rsp+88h+var_50], rbx
0x18000be2c  mov     [rsp+88h+var_58], r15
0x18000be31  mov     [rsp+88h+var_60], r12
0x18000be36  mov     [rsp+88h+var_68], 10h
0x18000be3e  xor     r9d, r9d
0x18000be41  lea     r8, aD; "D"
0x18000be48  xor     edx, edx
0x18000be4a  mov     rcx, rax
0x18000be4d  call    cs:__imp_WdsSetupLogMessageW
0x18000be53  mov     rcx, [rsi+8]
0x18000be57  mov     rax, [rcx]
0x18000be5a  mov     rax, [rax+0C0h]
0x18000be61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be66  cmp     qword ptr [rsi], 0
0x18000be6a  jz      short loc_18000BEDF
0x18000be6c  call    cs:__imp_GetLastError
0x18000be72  mov     edi, eax
0x18000be74  call    cs:__imp_CurrentIP
0x18000be7a  mov     rbx, rax
0x18000be7d  lea     rdx, aCpointintimere_56; "CPointInTimeRestoreHelper::~CPointInTim"...
0x18000be84  mov     ecx, 4000000h; unsigned int
0x18000be89  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000be8e  mov     [rsp+88h+var_38], 0
0x18000be96  mov     [rsp+88h+var_40], 0
0x18000be9f  mov     [rsp+88h+var_48], edi
0x18000bea3  mov     [rsp+88h+var_50], rbx
0x18000bea8  mov     [rsp+88h+var_58], r15
0x18000bead  mov     [rsp+88h+var_60], r12
0x18000beb2  mov     [rsp+88h+var_68], 16h
0x18000beba  xor     r9d, r9d
0x18000bebd  lea     r8, aD; "D"
0x18000bec4  xor     edx, edx
0x18000bec6  mov     rcx, rax
0x18000bec9  call    cs:__imp_WdsSetupLogMessageW
0x18000becf  mov     rcx, [rsi]
0x18000bed2  mov     rax, [rcx]
0x18000bed5  mov     rax, [rax+48h]
0x18000bed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bede  nop
0x18000bedf  add     rsp, 60h
0x18000bee3  pop     r15
0x18000bee5  pop     r12
0x18000bee7  pop     rdi
0x18000bee8  pop     rsi
0x18000bee9  pop     rbx
0x18000beea  retn
```
