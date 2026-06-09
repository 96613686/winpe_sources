# BthServBluetoothControlPanelTasksSetState(int)

- ea: `0x18000b10c`
- end: `0x18000b342`
- name: `?BthServBluetoothControlPanelTasksSetState@@YAXH@Z`
- size: `566`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000b348`
- `0x18000cf7c`

## callees

- `0x18000b10c`
- `0x1800110fc`
- `0x180011194`
- `0x18001140c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b2d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b2d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b228`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b228`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b1b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b1b0`

## string_xrefs

- `0x18000b1a2`: `SYSTEM\CurrentControlSet\Services\BthServ\Parameters\BluetoothControlPanelTasks`

## pseudocode

```c
void __fastcall BthServBluetoothControlPanelTasksSetState(int a1)
{
  char v1; // bl
  bool v2; // dl
  int v3; // edx
  int v4; // r8d
  _BYTE *v5; // rcx
  int v6; // edx
  int v7; // r8d
  int phkResult; // [rsp+20h] [rbp-48h]
  int phkResulta; // [rsp+20h] [rbp-48h]
  DWORD cbData; // [rsp+28h] [rbp-40h]
  DWORD cbDataa; // [rsp+28h] [rbp-40h]
  BOOL Data; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  Data = a1 != 0;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\BthServ\\Parameters\\BluetoothControlPanelTasks",
         0,
         0x20006u,
         &hKey) )
  {
    v5 = WPP_GLOBAL_Control;
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v3,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        phkResult,
        cbData,
        77,
        (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
LABEL_31:
      v5 = WPP_GLOBAL_Control;
    }
  }
  else if ( RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)&Data, 4u) )
  {
    v5 = WPP_GLOBAL_Control;
    LOBYTE(v6) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        phkResulta,
        cbDataa,
        78,
        (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      goto LABEL_31;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    LOBYTE(v6) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        phkResulta,
        cbDataa,
        79,
        (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      goto LABEL_31;
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v5 = WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || v5[25] < 5u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v5 + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v5 + 5));
}

```

## disassembly

```asm
0x18000b10c  mov     [rsp+arg_10], rbx
0x18000b111  mov     [rsp+arg_18], rsi
0x18000b116  push    rdi
0x18000b117  push    r14
0x18000b119  push    r15
0x18000b11b  sub     rsp, 50h
0x18000b11f  xor     eax, eax
0x18000b121  mov     [rsp+68h+hKey], 0
0x18000b12a  test    ecx, ecx
0x18000b12c  setnz   al
0x18000b12f  mov     [rsp+68h+Data], eax
0x18000b133  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b13a  lea     rsi, WPP_GLOBAL_Control
0x18000b141  mov     bl, 1
0x18000b143  cmp     rcx, rsi
0x18000b146  jz      short loc_18000B152
0x18000b148  cmp     byte ptr [rcx+19h], 5
0x18000b14c  jb      short loc_18000B152
0x18000b14e  mov     dl, bl
0x18000b150  jmp     short loc_18000B154
0x18000b152  xor     dl, dl
0x18000b154  lea     r14, WPP_RECORDER_INITIALIZED
0x18000b15b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000b162  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000b169  setnz   r8b
0x18000b16d  test    dl, dl
0x18000b16f  jnz     short loc_18000B176
0x18000b171  test    r8b, r8b
0x18000b174  jz      short loc_18000B18F
0x18000b176  mov     r9, [rcx+28h]
0x18000b17a  mov     rcx, [rcx+10h]
0x18000b17e  mov     [rsp+68h+var_30], r15
0x18000b183  mov     [rsp+68h+var_38], 4Ch ; 'L'
0x18000b18a  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000b18f  lea     rax, [rsp+68h+hKey]
0x18000b194  mov     r9d, 20006h; samDesired
0x18000b19a  xor     r8d, r8d; ulOptions
0x18000b19d  mov     [rsp+68h+phkResult], rax; phkResult
0x18000b1a2  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Bt"...
0x18000b1a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b1b0  call    cs:__imp_RegOpenKeyExW
0x18000b1b6  mov     edi, eax
0x18000b1b8  test    eax, eax
0x18000b1ba  jz      short loc_18000B201
0x18000b1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1c3  cmp     rcx, rsi
0x18000b1c6  jz      short loc_18000B1D2
0x18000b1c8  cmp     byte ptr [rcx+19h], 2
0x18000b1cc  jb      short loc_18000B1D2
0x18000b1ce  mov     dl, bl
0x18000b1d0  jmp     short loc_18000B1D4
0x18000b1d2  xor     dl, dl
0x18000b1d4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000b1db  setnz   r8b
0x18000b1df  test    dl, dl
0x18000b1e1  jnz     short loc_18000B1EC
0x18000b1e3  test    r8b, r8b
0x18000b1e6  jz      loc_18000B2C6
0x18000b1ec  mov     dword ptr [rsp+68h+var_20], eax
0x18000b1f0  mov     [rsp+68h+var_30], r15
0x18000b1f5  mov     [rsp+68h+var_38], 4Dh ; 'M'
0x18000b1fc  jmp     loc_18000B2B2
0x18000b201  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b206  lea     rax, [rsp+68h+Data]
0x18000b20b  mov     [rsp+68h+cbData], 4; cbData
0x18000b213  lea     rdx, ValueName; "State"
0x18000b21a  mov     r9d, 4; dwType
0x18000b220  mov     [rsp+68h+phkResult], rax; lpData
0x18000b225  xor     r8d, r8d; Reserved
0x18000b228  call    cs:__imp_RegSetValueExW
0x18000b22e  mov     edi, eax
0x18000b230  test    eax, eax
0x18000b232  jz      short loc_18000B272
0x18000b234  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b23b  cmp     rcx, rsi
0x18000b23e  jz      short loc_18000B24A
0x18000b240  cmp     byte ptr [rcx+19h], 2
0x18000b244  jb      short loc_18000B24A
0x18000b246  mov     dl, bl
0x18000b248  jmp     short loc_18000B24C
0x18000b24a  xor     dl, dl
0x18000b24c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000b253  setnz   r8b
0x18000b257  test    dl, dl
0x18000b259  jnz     short loc_18000B260
0x18000b25b  test    r8b, r8b
0x18000b25e  jz      short loc_18000B2C6
0x18000b260  mov     dword ptr [rsp+68h+var_20], eax
0x18000b264  mov     [rsp+68h+var_30], r15
0x18000b269  mov     [rsp+68h+var_38], 4Eh ; 'N'
0x18000b270  jmp     short loc_18000B2B2
0x18000b272  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b279  cmp     rcx, rsi
0x18000b27c  jz      short loc_18000B288
0x18000b27e  cmp     byte ptr [rcx+19h], 4
0x18000b282  jb      short loc_18000B288
0x18000b284  mov     dl, bl
0x18000b286  jmp     short loc_18000B28A
0x18000b288  xor     dl, dl
0x18000b28a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000b291  setnz   r8b
0x18000b295  test    dl, dl
0x18000b297  jnz     short loc_18000B29E
0x18000b299  test    r8b, r8b
0x18000b29c  jz      short loc_18000B2C6
0x18000b29e  mov     eax, [rsp+68h+Data]
0x18000b2a2  mov     dword ptr [rsp+68h+var_20], eax
0x18000b2a6  mov     [rsp+68h+var_30], r15
0x18000b2ab  mov     [rsp+68h+var_38], 4Fh ; 'O'
0x18000b2b2  mov     r9, [rcx+28h]
0x18000b2b6  mov     rcx, [rcx+10h]
0x18000b2ba  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000b2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2c6  mov     rax, [rsp+68h+hKey]
0x18000b2cb  test    rax, rax
0x18000b2ce  jz      short loc_18000B2E9
0x18000b2d0  mov     rcx, rax; hKey
0x18000b2d3  call    cs:__imp_RegCloseKey
0x18000b2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2e0  mov     [rsp+68h+hKey], 0
0x18000b2e9  cmp     rcx, rsi
0x18000b2ec  jz      short loc_18000B2F4
0x18000b2ee  cmp     byte ptr [rcx+19h], 5
0x18000b2f2  jnb     short loc_18000B2F6
0x18000b2f4  xor     bl, bl
0x18000b2f6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000b2fd  setnz   r8b
0x18000b301  test    bl, bl
0x18000b303  jnz     short loc_18000B30A
0x18000b305  test    r8b, r8b
0x18000b308  jz      short loc_18000B32C
0x18000b30a  mov     r9, [rcx+28h]
0x18000b30e  mov     dl, bl
0x18000b310  mov     rcx, [rcx+10h]
0x18000b314  mov     eax, edi
0x18000b316  mov     [rsp+68h+var_20], rax
0x18000b31b  mov     [rsp+68h+var_30], r15
0x18000b320  mov     [rsp+68h+var_38], 50h ; 'P'
0x18000b327  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000b32c  lea     r11, [rsp+68h+var_18]
0x18000b331  mov     rbx, [r11+30h]
0x18000b335  mov     rsi, [r11+38h]
0x18000b339  mov     rsp, r11
0x18000b33c  pop     r15
0x18000b33e  pop     r14
0x18000b340  pop     rdi
0x18000b341  retn
```
