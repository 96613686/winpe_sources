# NotifyMakeCallComplete

- ea: `0x18000cec8`
- end: `0x18000d195`
- name: `NotifyMakeCallComplete`
- size: `717`
- prototype: `char __fastcall(__int64, signed int, _OWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180002908`
- `0x18000df30`

## callees

- `0x180002d40`
- `0x180004d10`
- `0x180005230`
- `0x18000827c`
- `0x180008360`
- `0x18000cec8`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d093`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d093`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cf46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cf46`

## string_xrefs

- `0x18000d12d`: `CoId=%hs:Error completing MAKE_CALL_COMPLETE: %d`
- `0x18000d054`: `CoId=%hs:AsyncMakeCallcomplete fails with %d`

## pseudocode

```c
char __fastcall NotifyMakeCallComplete(__int64 a1, signed int a2, _OWORD *a3)
{
  HANDLE ProcessHeap; // rax
  char *v7; // rax
  void *v8; // rdi
  char v9; // bl
  unsigned int v10; // eax
  HANDLE v11; // rax
  unsigned int v12; // eax
  DWORD v14[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v15[28]; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v17[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v14[0] = 0;
  memset_0(v15, 0, 0x68u);
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( a2 )
  {
    v9 = 1;
    if ( a2 <= 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
  ProcessHeap = GetProcessHeap();
  v7 = (char *)HeapAlloc(ProcessHeap, 8u, 0x90u);
  v8 = v7;
  if ( !v7 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString((wchar_t *)&v16, L"CoId=%hs:Insufficient memory for status indication", a1 + 552);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v16);
    }
    LOWORD(a2) = 8;
    v9 = 0;
LABEL_13:
    a2 = (unsigned __int16)a2 | 0x80070000;
LABEL_14:
    v15[0] = *(_DWORD *)(a1 + 240);
    v15[6] = a2;
    v12 = SyncDeviceControl(*((_QWORD *)SstpSvcGlobals + 35), 1212440, (int)v15, 104, 0, 0, v14);
    if ( v12 )
    {
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v16) = 0;
        FormatRRASErrorString((wchar_t *)&v16, L"CoId=%hs:Error completing MAKE_CALL_COMPLETE: %d", a1 + 552, v12);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
            (const wchar_t *)&v16);
      }
    }
    DereferenceRefCount(a1 + 208);
    return v9;
  }
  *((_DWORD *)v7 + 8) = 17779;
  *((_DWORD *)v7 + 11) = *(_DWORD *)(a1 + 244);
  *((_DWORD *)v7 + 10) = *(_DWORD *)(a1 + 240);
  v9 = 1;
  *((_QWORD *)v7 + 6) = *(_QWORD *)(a1 + 472);
  *((_QWORD *)v7 + 7) = *(_QWORD *)(a1 + 480);
  v7[124] = *(_BYTE *)(a1 + 488);
  *((_DWORD *)v7 + 17) = *(_DWORD *)(a1 + 608);
  *(_OWORD *)(v7 + 72) = *(_OWORD *)(a1 + 489);
  *((_DWORD *)v7 + 22) = *(_DWORD *)(a1 + 505);
  *(_OWORD *)(v7 + 92) = *(_OWORD *)(a1 + 509);
  *(_OWORD *)(v7 + 108) = *(_OWORD *)(a1 + 525);
  *((_OWORD *)v7 + 8) = *a3;
  v10 = AsyncSstpDeviceControl(0x128018u, v7 + 40, 0x68u, v7 + 40, 0x68u, (LPOVERLAPPED)v7);
  if ( v10 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString((wchar_t *)&v16, L"CoId=%hs:AsyncMakeCallcomplete fails with %d", a1 + 552, v10);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v16);
    }
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v8);
    DereferenceRefCount(a1 + 208);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18000cec8  mov     [rsp-8+arg_10], rbx
0x18000cecd  mov     [rsp-8+arg_18], rsi
0x18000ced2  push    rbp
0x18000ced3  push    rdi
0x18000ced4  push    r14
0x18000ced6  lea     rbp, [rsp-7D0h]
0x18000cede  sub     rsp, 8D0h
0x18000cee5  mov     rax, cs:__security_cookie
0x18000ceec  xor     rax, rsp
0x18000ceef  mov     [rbp+7E0h+var_20], rax
0x18000cef6  mov     edi, edx
0x18000cef8  mov     [rsp+8E0h+var_8A0], 0
0x18000cf00  xor     edx, edx; Val
0x18000cf02  mov     r14, r8
0x18000cf05  mov     rsi, rcx
0x18000cf08  lea     rcx, [rsp+8E0h+var_890]; void *
0x18000cf0d  lea     r8d, [rdx+68h]; Size
0x18000cf11  call    memset_0
0x18000cf16  xor     eax, eax
0x18000cf18  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18000cf1c  xor     edx, edx; Val
0x18000cf1e  mov     [rbp+7E0h+var_820], eax
0x18000cf21  mov     r8d, 7FCh; Size
0x18000cf27  call    memset_0
0x18000cf2c  test    edi, edi
0x18000cf2e  jnz     loc_18000D0BA
0x18000cf34  call    cs:__imp_GetProcessHeap
0x18000cf3a  lea     edx, [rdi+8]; dwFlags
0x18000cf3d  mov     r8d, 90h; dwBytes
0x18000cf43  mov     rcx, rax; hHeap
0x18000cf46  call    cs:__imp_HeapAlloc
0x18000cf4c  mov     rdi, rax
0x18000cf4f  test    rax, rax
0x18000cf52  jnz     short loc_18000CFA4
0x18000cf54  test    cs:byte_18002D803, 8
0x18000cf5b  jz      short loc_18000CF98
0x18000cf5d  lea     r8, [rsi+228h]
0x18000cf64  mov     word ptr [rbp+7E0h+var_820], ax
0x18000cf68  lea     rdx, aCoidHsInsuffic; "CoId=%hs:Insufficient memory for status"...
0x18000cf6f  lea     rcx, [rbp+7E0h+var_820]
0x18000cf73  call    FormatRRASErrorString
0x18000cf78  test    cs:byte_18002D803, 8
0x18000cf7f  jz      short loc_18000CF98
0x18000cf81  lea     r8, [rbp+7E0h+var_820]
0x18000cf85  lea     rdx, RasSSTPSvcTraceError
0x18000cf8c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cf93  call    McTemplateU0z_EventWriteTransfer
0x18000cf98  mov     edi, 8
0x18000cf9d  xor     bl, bl
0x18000cf9f  jmp     loc_18000D0BE
0x18000cfa4  mov     dword ptr [rax+20h], 4573h
0x18000cfab  lea     rdx, [rdi+28h]; lpInBuffer
0x18000cfaf  mov     eax, [rsi+0F4h]
0x18000cfb5  mov     r9, rdx; lpOutBuffer
0x18000cfb8  mov     [rdi+2Ch], eax
0x18000cfbb  mov     ecx, 128018h; dwIoControlCode
0x18000cfc0  mov     eax, [rsi+0F0h]
0x18000cfc6  mov     r8d, 68h ; 'h'; nInBufferSize
0x18000cfcc  mov     [rdx], eax
0x18000cfce  mov     bl, 1
0x18000cfd0  mov     rax, [rsi+1D8h]
0x18000cfd7  mov     [rdi+30h], rax
0x18000cfdb  mov     rax, [rsi+1E0h]
0x18000cfe2  mov     [rdi+38h], rax
0x18000cfe6  mov     al, [rsi+1E8h]
0x18000cfec  mov     [rdi+7Ch], al
0x18000cfef  mov     eax, [rsi+260h]
0x18000cff5  mov     [rdi+44h], eax
0x18000cff8  movups  xmm0, xmmword ptr [rsi+1E9h]
0x18000cfff  mov     qword ptr [rsp+8E0h+var_8B8], rdi; LPOVERLAPPED
0x18000d004  mov     [rsp+8E0h+var_8C0], 68h ; 'h'; DWORD
0x18000d00c  movups  xmmword ptr [rdi+48h], xmm0
0x18000d010  mov     eax, [rsi+1F9h]
0x18000d016  mov     [rdi+58h], eax
0x18000d019  movups  xmm0, xmmword ptr [rsi+1FDh]
0x18000d020  movups  xmmword ptr [rdi+5Ch], xmm0
0x18000d024  movups  xmm1, xmmword ptr [rsi+20Dh]
0x18000d02b  movups  xmmword ptr [rdi+6Ch], xmm1
0x18000d02f  movups  xmm0, xmmword ptr [r14]
0x18000d033  movdqu  xmmword ptr [rdi+80h], xmm0
0x18000d03b  call    AsyncSstpDeviceControl
0x18000d040  test    eax, eax
0x18000d042  jz      loc_18000D16C
0x18000d048  test    cs:byte_18002D803, 8
0x18000d04f  jz      short loc_18000D093
0x18000d051  xor     r8d, r8d
0x18000d054  lea     rdx, aCoidHsAsyncmak; "CoId=%hs:AsyncMakeCallcomplete fails wi"...
0x18000d05b  mov     word ptr [rbp+7E0h+var_820], r8w
0x18000d060  lea     rcx, [rbp+7E0h+var_820]
0x18000d064  lea     r8, [rsi+228h]
0x18000d06b  mov     r9d, eax
0x18000d06e  call    FormatRRASErrorString
0x18000d073  test    cs:byte_18002D803, 8
0x18000d07a  jz      short loc_18000D093
0x18000d07c  lea     r8, [rbp+7E0h+var_820]
0x18000d080  lea     rdx, RasSSTPSvcTraceError
0x18000d087  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d08e  call    McTemplateU0z_EventWriteTransfer
0x18000d093  call    cs:__imp_GetProcessHeap
0x18000d099  mov     r8, rdi; lpMem
0x18000d09c  xor     edx, edx; dwFlags
0x18000d09e  mov     rcx, rax; hHeap
0x18000d0a1  call    cs:__imp_HeapFree
0x18000d0a7  lea     rcx, [rsi+0D0h]
0x18000d0ae  call    DereferenceRefCount
0x18000d0b3  xor     bl, bl
0x18000d0b5  jmp     loc_18000D16C
0x18000d0ba  mov     bl, 1
0x18000d0bc  jle     short loc_18000D0C7
0x18000d0be  movzx   edi, di
0x18000d0c1  or      edi, 80070000h
0x18000d0c7  mov     eax, [rsi+0F0h]
0x18000d0cd  lea     r8, [rsp+8E0h+var_890]; int
0x18000d0d2  mov     rcx, cs:SstpSvcGlobals
0x18000d0d9  mov     r9d, 68h ; 'h'; int
0x18000d0df  mov     [rsp+8E0h+var_890], eax
0x18000d0e3  mov     edx, 128018h; int
0x18000d0e8  lea     rax, [rsp+8E0h+var_8A0]
0x18000d0ed  mov     [rsp+8E0h+var_878], edi
0x18000d0f1  mov     [rsp+8E0h+var_8B0], rax; LPDWORD
0x18000d0f6  mov     rcx, [rcx+118h]; int
0x18000d0fd  mov     [rsp+8E0h+var_8B8], 0; DWORD
0x18000d105  mov     qword ptr [rsp+8E0h+var_8C0], 0; LPVOID
0x18000d10e  call    SyncDeviceControl
0x18000d113  test    eax, eax
0x18000d115  jz      short loc_18000D160
0x18000d117  test    cs:byte_18002D803, 8
0x18000d11e  jz      short loc_18000D160
0x18000d120  xor     ecx, ecx
0x18000d122  lea     r8, [rsi+228h]
0x18000d129  mov     word ptr [rbp+7E0h+var_820], cx
0x18000d12d  lea     rdx, aCoidHsErrorCom; "CoId=%hs:Error completing MAKE_CALL_COM"...
0x18000d134  lea     rcx, [rbp+7E0h+var_820]
0x18000d138  mov     r9d, eax
0x18000d13b  call    FormatRRASErrorString
0x18000d140  test    cs:byte_18002D803, 8
0x18000d147  jz      short loc_18000D160
0x18000d149  lea     r8, [rbp+7E0h+var_820]
0x18000d14d  lea     rdx, RasSSTPSvcTraceError
0x18000d154  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d15b  call    McTemplateU0z_EventWriteTransfer
0x18000d160  lea     rcx, [rsi+0D0h]
0x18000d167  call    DereferenceRefCount
0x18000d16c  mov     al, bl
0x18000d16e  mov     rcx, [rbp+7E0h+var_20]
0x18000d175  xor     rcx, rsp; StackCookie
0x18000d178  call    __security_check_cookie
0x18000d17d  lea     r11, [rsp+8E0h+var_10]
0x18000d185  mov     rbx, [r11+30h]
0x18000d189  mov     rsi, [r11+38h]
0x18000d18d  mov     rsp, r11
0x18000d190  pop     r14
0x18000d192  pop     rdi
0x18000d193  pop     rbp
0x18000d194  retn
```
