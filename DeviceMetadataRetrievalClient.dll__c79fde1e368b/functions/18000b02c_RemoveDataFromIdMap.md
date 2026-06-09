# RemoveDataFromIdMap

- ea: `0x18000b02c`
- end: `0x18000b23e`
- name: `RemoveDataFromIdMap`
- size: `530`
- prototype: `BOOL __fastcall(__int64, struct NDX_OBJREF *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000b244`

## callees

- `0x180004dc4`
- `0x180004dec`
- `0x180007ea0`
- `0x18000b02c`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b132`
- `msvcrt!_wcsicmp` at `0x18000b132`
- `KERNEL32!GetProcessHeap` at `0x18000b0d2`
- `KERNEL32!GetProcessHeap` at `0x18000b121`
- `KERNEL32!GetProcessHeap` at `0x18000b13c`
- `KERNEL32!GetProcessHeap` at `0x18000b170`
- `KERNEL32!GetProcessHeap` at `0x18000b209`
- `KERNEL32!GetProcessHeap` at `0x18000b0d2`
- `KERNEL32!GetProcessHeap` at `0x18000b121`
- `KERNEL32!GetProcessHeap` at `0x18000b13c`
- `KERNEL32!GetProcessHeap` at `0x18000b170`
- `KERNEL32!GetProcessHeap` at `0x18000b209`
- `KERNEL32!HeapFree` at `0x18000b14a`
- `KERNEL32!HeapFree` at `0x18000b17e`
- `KERNEL32!HeapFree` at `0x18000b217`
- `KERNEL32!HeapFree` at `0x18000b14a`
- `KERNEL32!HeapFree` at `0x18000b17e`
- `KERNEL32!HeapFree` at `0x18000b217`
- `KERNEL32!GetLastError` at `0x18000b198`
- `KERNEL32!GetLastError` at `0x18000b1b1`
- `KERNEL32!GetLastError` at `0x18000b1d2`
- `KERNEL32!GetLastError` at `0x18000b198`
- `KERNEL32!GetLastError` at `0x18000b1b1`
- `KERNEL32!GetLastError` at `0x18000b1d2`
- `DEVRTL!NdxTableRemoveObject` at `0x18000b1a9`
- `DEVRTL!NdxTableRemoveObject` at `0x18000b1a9`
- `DEVRTL!NdxTableFirstObject` at `0x18000b0ed`
- `DEVRTL!NdxTableFirstObject` at `0x18000b0ed`
- `DEVRTL!NdxTableRemoveObjectFromList` at `0x18000b16a`
- `DEVRTL!NdxTableRemoveObjectFromList` at `0x18000b16a`
- `DEVRTL!NdxTableFirstObjectInList` at `0x18000b102`
- `DEVRTL!NdxTableFirstObjectInList` at `0x18000b18e`
- `DEVRTL!NdxTableFirstObjectInList` at `0x18000b102`
- `DEVRTL!NdxTableFirstObjectInList` at `0x18000b18e`
- `DEVRTL!NdxTableNextObject` at `0x18000b154`
- `DEVRTL!NdxTableNextObject` at `0x18000b1c2`
- `DEVRTL!NdxTableNextObject` at `0x18000b154`
- `DEVRTL!NdxTableNextObject` at `0x18000b1c2`

## pseudocode

```c
BOOL __fastcall RemoveDataFromIdMap(__int64 a1, struct NDX_OBJREF *a2)
{
  const wchar_t *ObjectName; // rdi
  HANDLE ProcessHeap; // rax
  wchar_t *v6; // r8
  int i; // eax
  const wchar_t *v8; // rax
  wchar_t *v9; // rbx
  HANDLE v10; // rax
  wchar_t *v11; // r8
  HANDLE v12; // rax
  __int64 LastError; // r9
  _OWORD v15[2]; // [rsp+20h] [rbp-60h] BYREF
  __int64 v16; // [rsp+40h] [rbp-40h]
  _OWORD v17[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v18; // [rsp+68h] [rbp-18h]

  v16 = 0;
  v18 = 0;
  memset(v15, 0, sizeof(v15));
  memset(v17, 0, sizeof(v17));
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *(_DWORD *)a1 != 1229866053 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  ObjectName = MemGetObjectName(a2);
  if ( ObjectName )
  {
    for ( i = NdxTableFirstObject(*(_QWORD *)(a1 + 40), 2, v15); ; i = NdxTableNextObject(v15) )
    {
      if ( !i )
      {
LABEL_31:
        ProcessHeap = GetProcessHeap();
        v6 = (wchar_t *)ObjectName;
        return HeapFree(ProcessHeap, 0, v6);
      }
      if ( !(unsigned int)NdxTableFirstObjectInList(v15, 0, v17) )
      {
        if ( GetLastError() == 259 )
          continue;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, LastError);
        goto LABEL_31;
      }
      while ( 1 )
      {
        v8 = MemGetObjectName((struct NDX_OBJREF *)v17);
        v9 = (wchar_t *)v8;
        if ( v8 )
          break;
        v10 = GetProcessHeap();
        v11 = 0;
LABEL_18:
        HeapFree(v10, 0, v11);
        if ( !(unsigned int)NdxTableNextObject(v17) )
          goto LABEL_21;
      }
      if ( _wcsicmp(ObjectName, v8) )
        break;
      NdxTableRemoveObjectFromList(v15, 0, v17);
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v9);
LABEL_21:
      if ( !(unsigned int)NdxTableFirstObjectInList(v15, 0, v17) && GetLastError() == 259 )
        NdxTableRemoveObject(v15);
    }
    v10 = GetProcessHeap();
    v11 = v9;
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids);
  ProcessHeap = GetProcessHeap();
  v6 = 0;
  return HeapFree(ProcessHeap, 0, v6);
}

```

## disassembly

```asm
0x18000b02c  mov     [rsp-8+arg_10], rbx
0x18000b031  mov     [rsp-8+arg_18], rdi
0x18000b036  push    rbp
0x18000b037  mov     rbp, rsp
0x18000b03a  sub     rsp, 80h
0x18000b041  mov     rax, cs:__security_cookie
0x18000b048  xor     rax, rsp
0x18000b04b  mov     [rbp+var_10], rax
0x18000b04f  xor     eax, eax
0x18000b051  xorps   xmm0, xmm0
0x18000b054  mov     [rbp+var_40], rax
0x18000b058  xorps   xmm1, xmm1
0x18000b05b  mov     [rbp+var_18], rax
0x18000b05f  mov     rdi, rdx
0x18000b062  mov     rbx, rcx
0x18000b065  movups  [rbp+var_60], xmm0
0x18000b069  movups  [rbp+var_50], xmm0
0x18000b06d  movups  [rbp+var_38], xmm1
0x18000b071  movups  [rbp+var_28], xmm1
0x18000b075  test    rcx, rcx
0x18000b078  jnz     short loc_18000B07F
0x18000b07a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b07f  cmp     dword ptr [rbx], 494E4445h
0x18000b085  jz      short loc_18000B08C
0x18000b087  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b08c  test    rdi, rdi
0x18000b08f  jnz     short loc_18000B096
0x18000b091  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b096  mov     rcx, rdi; struct NDX_OBJREF *
0x18000b099  call    ?MemGetObjectName@@YAPEAGPEAUNDX_OBJREF@@@Z; MemGetObjectName(NDX_OBJREF *)
0x18000b09e  mov     rdi, rax
0x18000b0a1  test    rax, rax
0x18000b0a4  jnz     short loc_18000B0E0
0x18000b0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0ad  lea     rax, WPP_GLOBAL_Control
0x18000b0b4  cmp     rcx, rax
0x18000b0b7  jz      short loc_18000B0D2
0x18000b0b9  test    byte ptr [rcx+1Ch], 1
0x18000b0bd  jz      short loc_18000B0D2
0x18000b0bf  mov     rcx, [rcx+10h]
0x18000b0c3  lea     edx, [rdi+20h]
0x18000b0c6  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000b0cd  call    WPP_SF_
0x18000b0d2  call    cs:__imp_GetProcessHeap
0x18000b0d8  xor     r8d, r8d
0x18000b0db  jmp     loc_18000B212
0x18000b0e0  mov     rcx, [rbx+28h]
0x18000b0e4  lea     r8, [rbp+var_60]
0x18000b0e8  mov     edx, 2
0x18000b0ed  call    cs:__imp_NdxTableFirstObject
0x18000b0f3  jmp     loc_18000B1C8
0x18000b0f8  lea     r8, [rbp+var_38]
0x18000b0fc  xor     edx, edx
0x18000b0fe  lea     rcx, [rbp+var_60]
0x18000b102  call    cs:__imp_NdxTableFirstObjectInList
0x18000b108  test    eax, eax
0x18000b10a  jz      loc_18000B1B1
0x18000b110  lea     rcx, [rbp+var_38]; struct NDX_OBJREF *
0x18000b114  call    ?MemGetObjectName@@YAPEAGPEAUNDX_OBJREF@@@Z; MemGetObjectName(NDX_OBJREF *)
0x18000b119  mov     rbx, rax
0x18000b11c  test    rax, rax
0x18000b11f  jnz     short loc_18000B12C
0x18000b121  call    cs:__imp_GetProcessHeap
0x18000b127  xor     r8d, r8d
0x18000b12a  jmp     short loc_18000B145
0x18000b12c  mov     rdx, rbx; String2
0x18000b12f  mov     rcx, rdi; String1
0x18000b132  call    cs:__imp__wcsicmp
0x18000b138  test    eax, eax
0x18000b13a  jz      short loc_18000B160
0x18000b13c  call    cs:__imp_GetProcessHeap
0x18000b142  mov     r8, rbx; lpMem
0x18000b145  xor     edx, edx; dwFlags
0x18000b147  mov     rcx, rax; hHeap
0x18000b14a  call    cs:__imp_HeapFree
0x18000b150  lea     rcx, [rbp+var_38]
0x18000b154  call    cs:__imp_NdxTableNextObject
0x18000b15a  test    eax, eax
0x18000b15c  jnz     short loc_18000B110
0x18000b15e  jmp     short loc_18000B184
0x18000b160  lea     r8, [rbp+var_38]
0x18000b164  xor     edx, edx
0x18000b166  lea     rcx, [rbp+var_60]
0x18000b16a  call    cs:__imp_NdxTableRemoveObjectFromList
0x18000b170  call    cs:__imp_GetProcessHeap
0x18000b176  mov     r8, rbx; lpMem
0x18000b179  xor     edx, edx; dwFlags
0x18000b17b  mov     rcx, rax; hHeap
0x18000b17e  call    cs:__imp_HeapFree
0x18000b184  lea     r8, [rbp+var_38]
0x18000b188  xor     edx, edx
0x18000b18a  lea     rcx, [rbp+var_60]
0x18000b18e  call    cs:__imp_NdxTableFirstObjectInList
0x18000b194  test    eax, eax
0x18000b196  jnz     short loc_18000B1BE
0x18000b198  call    cs:__imp_GetLastError
0x18000b19e  cmp     eax, 103h
0x18000b1a3  jnz     short loc_18000B1BE
0x18000b1a5  lea     rcx, [rbp+var_60]
0x18000b1a9  call    cs:__imp_NdxTableRemoveObject
0x18000b1af  jmp     short loc_18000B1BE
0x18000b1b1  call    cs:__imp_GetLastError
0x18000b1b7  cmp     eax, 103h
0x18000b1bc  jnz     short loc_18000B1D2
0x18000b1be  lea     rcx, [rbp+var_60]
0x18000b1c2  call    cs:__imp_NdxTableNextObject
0x18000b1c8  test    eax, eax
0x18000b1ca  jnz     loc_18000B0F8
0x18000b1d0  jmp     short loc_18000B209
0x18000b1d2  call    cs:__imp_GetLastError
0x18000b1d8  mov     r9d, eax
0x18000b1db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1e2  lea     rax, WPP_GLOBAL_Control
0x18000b1e9  cmp     rcx, rax
0x18000b1ec  jz      short loc_18000B209
0x18000b1ee  test    byte ptr [rcx+1Ch], 1
0x18000b1f2  jz      short loc_18000B209
0x18000b1f4  mov     rcx, [rcx+10h]
0x18000b1f8  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000b1ff  mov     edx, 21h ; '!'
0x18000b204  call    WPP_SF_d
0x18000b209  call    cs:__imp_GetProcessHeap
0x18000b20f  mov     r8, rdi; lpMem
0x18000b212  xor     edx, edx; dwFlags
0x18000b214  mov     rcx, rax; hHeap
0x18000b217  call    cs:__imp_HeapFree
0x18000b21d  mov     rcx, [rbp+var_10]
0x18000b221  xor     rcx, rsp; StackCookie
0x18000b224  call    __security_check_cookie
0x18000b229  lea     r11, [rsp+80h+var_s0]
0x18000b231  mov     rbx, [r11+20h]
0x18000b235  mov     rdi, [r11+28h]
0x18000b239  mov     rsp, r11
0x18000b23c  pop     rbp
0x18000b23d  retn
```
