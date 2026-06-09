# BthServStart(void)

- ea: `0x18000dc40`
- end: `0x18000dea9`
- name: `?BthServStart@@YAXXZ`
- size: `617`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c3fc`

## callees

- `0x18000c798`
- `0x18000dc40`
- `0x1800110fc`
- `0x180011194`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dcbc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dcbc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dcdc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dd30`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dcdc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dd30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dcfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dcfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dce4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dce4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd38`

## string_xrefs

- `0x18000dcaf`: `Microsoft.Bluetooth.Service.dll`

## pseudocode

```c
void BthServStart(void)
{
  char v0; // di
  bool v1; // dl
  HMODULE Library; // rax
  HMODULE v3; // rbp
  HMODULE v4; // rsi
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  HMODULE v7; // rsi
  DWORD v8; // ebx
  _BYTE *v9; // rcx
  bool v10; // dl
  int v11; // edx
  int v12; // r8d
  bool v13; // dl
  int v14; // [rsp+20h] [rbp-68h]
  int v15; // [rsp+28h] [rbp-60h]

  v0 = 1;
  v1 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  Library = LoadLibraryExW(L"Microsoft.Bluetooth.Service.dll", 0, 0x800u);
  v3 = hLibModule;
  v4 = Library;
  if ( hLibModule )
  {
    LastError = GetLastError();
    FreeLibrary(v3);
    SetLastError(LastError);
  }
  hLibModule = v4;
  if ( v4 )
  {
    ProcAddress = GetProcAddress(v4, (LPCSTR)0x64);
    qword_180044BB8 = (__int64)ProcAddress;
    if ( ProcAddress )
    {
      ((void (__fastcall *)(_QWORD))ProcAddress)(0);
    }
    else
    {
      v7 = hLibModule;
      if ( hLibModule )
      {
        v8 = GetLastError();
        FreeLibrary(v7);
        SetLastError(v8);
      }
      hLibModule = 0;
    }
  }
  BthServLoadBackgroundBrokerModule();
  v9 = WPP_GLOBAL_Control;
  v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v9 = WPP_GLOBAL_Control;
  }
  if ( qword_180044A70 )
  {
    if ( !(unsigned int)qword_180044A70(&GUID_BLUETOOTH_EVENT_BROKER_ID, &dword_180044A80, 7) )
    {
LABEL_32:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_33;
    }
    v9 = WPP_GLOBAL_Control;
    LOBYTE(v11) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v14,
        v15,
        65,
        (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      goto LABEL_32;
    }
  }
LABEL_33:
  v13 = v9 != (_BYTE *)&WPP_GLOBAL_Control && v9[25] >= 5u;
  if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v9 + 2),
      v13,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v9 + 5));
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 5u )
    v0 = 0;
  if ( v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v9 + 2),
      v0,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v9 + 5));
}

```

## disassembly

```asm
0x18000dc40  push    rbx
0x18000dc42  push    rbp
0x18000dc43  push    rsi
0x18000dc44  push    rdi
0x18000dc45  push    r12
0x18000dc47  push    r13
0x18000dc49  push    r14
0x18000dc4b  sub     rsp, 50h
0x18000dc4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc56  lea     r14, WPP_GLOBAL_Control
0x18000dc5d  mov     dil, 1
0x18000dc60  cmp     rcx, r14
0x18000dc63  jz      short loc_18000DC70
0x18000dc65  cmp     byte ptr [rcx+19h], 5
0x18000dc69  jb      short loc_18000DC70
0x18000dc6b  mov     dl, dil
0x18000dc6e  jmp     short loc_18000DC72
0x18000dc70  xor     dl, dl
0x18000dc72  lea     r12, WPP_RECORDER_INITIALIZED
0x18000dc79  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000dc80  lea     r13, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000dc87  setnz   r8b
0x18000dc8b  test    dl, dl
0x18000dc8d  jnz     short loc_18000DC94
0x18000dc8f  test    r8b, r8b
0x18000dc92  jz      short loc_18000DCAD
0x18000dc94  mov     r9, [rcx+28h]
0x18000dc98  mov     rcx, [rcx+10h]
0x18000dc9c  mov     [rsp+88h+var_50], r13
0x18000dca1  mov     [rsp+88h+var_58], 31h ; '1'
0x18000dca8  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000dcad  xor     edx, edx; hFile
0x18000dcaf  lea     rcx, aMicrosoftBluet; "Microsoft.Bluetooth.Service.dll"
0x18000dcb6  mov     r8d, 800h; dwFlags
0x18000dcbc  call    cs:__imp_LoadLibraryExW
0x18000dcc2  mov     rbp, cs:hLibModule
0x18000dcc9  mov     rsi, rax
0x18000dccc  test    rbp, rbp
0x18000dccf  jz      short loc_18000DCEA
0x18000dcd1  call    cs:__imp_GetLastError
0x18000dcd7  mov     rcx, rbp; hLibModule
0x18000dcda  mov     ebx, eax
0x18000dcdc  call    cs:__imp_FreeLibrary
0x18000dce2  mov     ecx, ebx; dwErrCode
0x18000dce4  call    cs:__imp_SetLastError
0x18000dcea  mov     cs:hLibModule, rsi
0x18000dcf1  test    rsi, rsi
0x18000dcf4  jz      short loc_18000DD49
0x18000dcf6  mov     edx, 64h ; 'd'; lpProcName
0x18000dcfb  mov     rcx, rsi; hModule
0x18000dcfe  call    cs:__imp_GetProcAddress
0x18000dd04  mov     cs:qword_180044BB8, rax
0x18000dd0b  test    rax, rax
0x18000dd0e  jz      short loc_18000DD19
0x18000dd10  xor     ecx, ecx
0x18000dd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd17  jmp     short loc_18000DD49
0x18000dd19  mov     rsi, cs:hLibModule
0x18000dd20  test    rsi, rsi
0x18000dd23  jz      short loc_18000DD3E
0x18000dd25  call    cs:__imp_GetLastError
0x18000dd2b  mov     rcx, rsi; hLibModule
0x18000dd2e  mov     ebx, eax
0x18000dd30  call    cs:__imp_FreeLibrary
0x18000dd36  mov     ecx, ebx; dwErrCode
0x18000dd38  call    cs:__imp_SetLastError
0x18000dd3e  mov     cs:hLibModule, 0
0x18000dd49  call    ?BthServLoadBackgroundBrokerModule@@YAXXZ; BthServLoadBackgroundBrokerModule(void)
0x18000dd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd55  cmp     rcx, r14
0x18000dd58  jz      short loc_18000DD65
0x18000dd5a  cmp     byte ptr [rcx+19h], 5
0x18000dd5e  jb      short loc_18000DD65
0x18000dd60  mov     dl, dil
0x18000dd63  jmp     short loc_18000DD67
0x18000dd65  xor     dl, dl
0x18000dd67  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000dd6e  setnz   r8b
0x18000dd72  test    dl, dl
0x18000dd74  jnz     short loc_18000DD7B
0x18000dd76  test    r8b, r8b
0x18000dd79  jz      short loc_18000DD9B
0x18000dd7b  mov     r9, [rcx+28h]
0x18000dd7f  mov     rcx, [rcx+10h]
0x18000dd83  mov     [rsp+88h+var_50], r13
0x18000dd88  mov     [rsp+88h+var_58], 40h ; '@'
0x18000dd8f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000dd94  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd9b  mov     rax, cs:qword_180044A70
0x18000dda2  test    rax, rax
0x18000dda5  jz      short loc_18000DE15
0x18000dda7  mov     r8d, 7
0x18000ddad  lea     rdx, dword_180044A80
0x18000ddb4  lea     rcx, GUID_BLUETOOTH_EVENT_BROKER_ID
0x18000ddbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddc0  test    eax, eax
0x18000ddc2  jz      short loc_18000DE0E
0x18000ddc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddcb  cmp     rcx, r14
0x18000ddce  jz      short loc_18000DDDB
0x18000ddd0  cmp     byte ptr [rcx+19h], 3
0x18000ddd4  jb      short loc_18000DDDB
0x18000ddd6  mov     dl, dil
0x18000ddd9  jmp     short loc_18000DDDD
0x18000dddb  xor     dl, dl
0x18000dddd  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000dde4  setnz   r8b
0x18000dde8  test    dl, dl
0x18000ddea  jnz     short loc_18000DDF1
0x18000ddec  test    r8b, r8b
0x18000ddef  jz      short loc_18000DE15
0x18000ddf1  mov     r9, [rcx+28h]
0x18000ddf5  mov     rcx, [rcx+10h]
0x18000ddf9  mov     [rsp+88h+var_40], eax
0x18000ddfd  mov     [rsp+88h+var_50], r13
0x18000de02  mov     [rsp+88h+var_58], 41h ; 'A'
0x18000de09  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000de0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de15  cmp     rcx, r14
0x18000de18  jz      short loc_18000DE25
0x18000de1a  cmp     byte ptr [rcx+19h], 5
0x18000de1e  jb      short loc_18000DE25
0x18000de20  mov     dl, dil
0x18000de23  jmp     short loc_18000DE27
0x18000de25  xor     dl, dl
0x18000de27  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000de2e  setnz   r8b
0x18000de32  test    dl, dl
0x18000de34  jnz     short loc_18000DE3B
0x18000de36  test    r8b, r8b
0x18000de39  jz      short loc_18000DE5B
0x18000de3b  mov     r9, [rcx+28h]
0x18000de3f  mov     rcx, [rcx+10h]
0x18000de43  mov     [rsp+88h+var_50], r13
0x18000de48  mov     [rsp+88h+var_58], 42h ; 'B'
0x18000de4f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000de54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de5b  cmp     rcx, r14
0x18000de5e  jz      short loc_18000DE66
0x18000de60  cmp     byte ptr [rcx+19h], 5
0x18000de64  jnb     short loc_18000DE69
0x18000de66  xor     dil, dil
0x18000de69  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000de70  setnz   r8b
0x18000de74  test    dil, dil
0x18000de77  jnz     short loc_18000DE7E
0x18000de79  test    r8b, r8b
0x18000de7c  jz      short loc_18000DE9A
0x18000de7e  mov     r9, [rcx+28h]
0x18000de82  mov     dl, dil
0x18000de85  mov     rcx, [rcx+10h]
0x18000de89  mov     [rsp+88h+var_50], r13
0x18000de8e  mov     [rsp+88h+var_58], 32h ; '2'
0x18000de95  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000de9a  add     rsp, 50h
0x18000de9e  pop     r14
0x18000dea0  pop     r13
0x18000dea2  pop     r12
0x18000dea4  pop     rdi
0x18000dea5  pop     rsi
0x18000dea6  pop     rbp
0x18000dea7  pop     rbx
0x18000dea8  retn
```
