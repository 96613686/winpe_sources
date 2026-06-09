# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(void)

- ea: `0x18002f2a8`
- end: `0x18002f512`
- name: `?WaitForDafQueryEvent@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ`
- size: `618`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002cb84`
- `0x18002e2c0`
- `0x18002e620`

## callees

- `0x180011194`
- `0x18001140c`
- `0x1800116a8`
- `0x18002aec0`
- `0x18002f2a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f376`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002f350`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002f350`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(
        HANDLE *this)
{
  char v2; // di
  bool v3; // dl
  DWORD v4; // eax
  int v5; // edx
  int v6; // r8d
  signed int LastError; // eax
  signed int v8; // ebx
  _BYTE *v9; // rcx
  int v10; // eax
  bool v11; // cf
  int v13; // [rsp+20h] [rbp-88h]
  int v14; // [rsp+28h] [rbp-80h]
  HANDLE Handles[9]; // [rsp+60h] [rbp-48h] BYREF

  *(_OWORD *)Handles = 0;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  Handles[0] = this[257];
  Handles[1] = this[256];
  while ( 1 )
  {
    v4 = WaitForMultipleObjects(2u, Handles, 0, 0x7530u);
    switch ( v4 )
    {
      case 0u:
        v8 = -2147467260;
        goto LABEL_43;
      case 1u:
        v8 = *((_DWORD *)this + 38);
        v9 = WPP_GLOBAL_Control;
LABEL_40:
        if ( !v8 )
        {
          v10 = 0;
          v11 = v9[25] < 5u;
          goto LABEL_45;
        }
        goto LABEL_44;
      case 0x102u:
        v8 = -2147023436;
        v9 = WPP_GLOBAL_Control;
        LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
        if ( !(_BYTE)v5 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_44;
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          v6,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v13,
          v14,
          87,
          (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
LABEL_43:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_44;
    }
    if ( v4 != -1 )
      break;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v13,
        v14,
        88,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v8 < 0 )
      goto LABEL_40;
  }
  v8 = -2147418113;
  v9 = WPP_GLOBAL_Control;
  LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v13,
      v14,
      89,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    goto LABEL_43;
  }
LABEL_44:
  v10 = 0;
  v11 = v9[25] < 2u;
LABEL_45:
  if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v10) = !v11, !v10) )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = v2;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v9 + 2), v5, v6, *((_QWORD *)v9 + 5));
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002f2a8  push    rbx
0x18002f2aa  push    rsi
0x18002f2ab  push    rdi
0x18002f2ac  push    r13
0x18002f2ae  push    r14
0x18002f2b0  push    r15
0x18002f2b2  sub     rsp, 78h
0x18002f2b6  xorps   xmm0, xmm0
0x18002f2b9  mov     rsi, rcx
0x18002f2bc  movups  xmmword ptr [rsp+0A8h+Handles], xmm0
0x18002f2c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2c8  lea     r14, WPP_GLOBAL_Control
0x18002f2cf  mov     edi, 1
0x18002f2d4  cmp     rcx, r14
0x18002f2d7  jz      short loc_18002F2E4
0x18002f2d9  cmp     byte ptr [rcx+19h], 5
0x18002f2dd  jb      short loc_18002F2E4
0x18002f2df  mov     dl, dil
0x18002f2e2  jmp     short loc_18002F2E6
0x18002f2e4  xor     dl, dl
0x18002f2e6  lea     r15, WPP_RECORDER_INITIALIZED
0x18002f2ed  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002f2f4  lea     r13, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f2fb  setnz   r8b
0x18002f2ff  test    dl, dl
0x18002f301  jnz     short loc_18002F308
0x18002f303  test    r8b, r8b
0x18002f306  jz      short loc_18002F326
0x18002f308  mov     r9, [rcx+28h]
0x18002f30c  mov     rcx, [rcx+10h]
0x18002f310  mov     [rsp+0A8h+var_60], rsi
0x18002f315  mov     [rsp+0A8h+var_70], r13
0x18002f31a  mov     [rsp+0A8h+var_78], 55h ; 'U'
0x18002f321  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f326  mov     rax, [rsi+808h]
0x18002f32d  mov     [rsp+0A8h+Handles], rax
0x18002f332  mov     rax, [rsi+800h]
0x18002f339  mov     [rsp+0A8h+Handles+8], rax
0x18002f33e  xor     r8d, r8d; bWaitAll
0x18002f341  lea     rdx, [rsp+0A8h+Handles]; lpHandles
0x18002f346  mov     r9d, 7530h; dwMilliseconds
0x18002f34c  lea     ecx, [r8+2]; nCount
0x18002f350  call    cs:__imp_WaitForMultipleObjects
0x18002f356  test    eax, eax
0x18002f358  jz      loc_18002F4A7
0x18002f35e  cmp     eax, edi
0x18002f360  jz      loc_18002F48E
0x18002f366  cmp     eax, 102h
0x18002f36b  jz      loc_18002F446
0x18002f371  cmp     eax, 0FFFFFFFFh
0x18002f374  jnz     short loc_18002F3F1
0x18002f376  call    cs:__imp_GetLastError
0x18002f37c  mov     ebx, eax
0x18002f37e  test    eax, eax
0x18002f380  jle     short loc_18002F38B
0x18002f382  movzx   ebx, ax
0x18002f385  or      ebx, 80070000h
0x18002f38b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f392  cmp     rcx, r14
0x18002f395  jz      short loc_18002F3A2
0x18002f397  cmp     byte ptr [rcx+19h], 2
0x18002f39b  jb      short loc_18002F3A2
0x18002f39d  mov     dl, dil
0x18002f3a0  jmp     short loc_18002F3A4
0x18002f3a2  xor     dl, dl
0x18002f3a4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002f3ab  setnz   r8b
0x18002f3af  test    dl, dl
0x18002f3b1  jnz     short loc_18002F3B8
0x18002f3b3  test    r8b, r8b
0x18002f3b6  jz      short loc_18002F3E4
0x18002f3b8  mov     r9, [rcx+28h]
0x18002f3bc  mov     rcx, [rcx+10h]
0x18002f3c0  mov     [rsp+0A8h+var_58], ebx
0x18002f3c4  mov     dword ptr [rsp+0A8h+var_60], 0FFFFFFFFh
0x18002f3cc  mov     [rsp+0A8h+var_70], r13
0x18002f3d1  mov     [rsp+0A8h+var_78], 58h ; 'X'
0x18002f3d8  call    WPP_RECORDER_AND_TRACE_SF_sdd
0x18002f3dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3e4  test    ebx, ebx
0x18002f3e6  jns     loc_18002F33E
0x18002f3ec  jmp     loc_18002F49B
0x18002f3f1  mov     ebx, 8000FFFFh
0x18002f3f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3fd  cmp     rcx, r14
0x18002f400  jz      short loc_18002F40D
0x18002f402  cmp     byte ptr [rcx+19h], 2
0x18002f406  jb      short loc_18002F40D
0x18002f408  mov     dl, dil
0x18002f40b  jmp     short loc_18002F40F
0x18002f40d  xor     dl, dl
0x18002f40f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002f416  setnz   r8b
0x18002f41a  test    dl, dl
0x18002f41c  jnz     short loc_18002F427
0x18002f41e  test    r8b, r8b
0x18002f421  jz      loc_18002F4B3
0x18002f427  mov     dword ptr [rsp+0A8h+var_60], eax
0x18002f42b  mov     [rsp+0A8h+var_70], r13
0x18002f430  mov     [rsp+0A8h+var_78], 59h ; 'Y'
0x18002f437  mov     r9, [rcx+28h]
0x18002f43b  mov     rcx, [rcx+10h]
0x18002f43f  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002f444  jmp     short loc_18002F4AC
0x18002f446  mov     ebx, 800705B4h
0x18002f44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f452  cmp     rcx, r14
0x18002f455  jz      short loc_18002F462
0x18002f457  cmp     byte ptr [rcx+19h], 2
0x18002f45b  jb      short loc_18002F462
0x18002f45d  mov     dl, dil
0x18002f460  jmp     short loc_18002F464
0x18002f462  xor     dl, dl
0x18002f464  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002f46b  setnz   r8b
0x18002f46f  test    dl, dl
0x18002f471  jnz     short loc_18002F478
0x18002f473  test    r8b, r8b
0x18002f476  jz      short loc_18002F4B3
0x18002f478  mov     dword ptr [rsp+0A8h+var_60], 102h
0x18002f480  mov     [rsp+0A8h+var_70], r13
0x18002f485  mov     [rsp+0A8h+var_78], 57h ; 'W'
0x18002f48c  jmp     short loc_18002F437
0x18002f48e  mov     ebx, [rsi+98h]
0x18002f494  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f49b  test    ebx, ebx
0x18002f49d  jnz     short loc_18002F4B3
0x18002f49f  xor     eax, eax
0x18002f4a1  cmp     byte ptr [rcx+19h], 5
0x18002f4a5  jmp     short loc_18002F4B9
0x18002f4a7  mov     ebx, 80004004h
0x18002f4ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4b3  xor     eax, eax
0x18002f4b5  cmp     byte ptr [rcx+19h], 2
0x18002f4b9  setnb   al
0x18002f4bc  cmp     rcx, r14
0x18002f4bf  jz      short loc_18002F4C5
0x18002f4c1  test    eax, eax
0x18002f4c3  jnz     short loc_18002F4C8
0x18002f4c5  xor     dil, dil
0x18002f4c8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002f4cf  setnz   r8b
0x18002f4d3  test    dil, dil
0x18002f4d6  jnz     short loc_18002F4DD
0x18002f4d8  test    r8b, r8b
0x18002f4db  jz      short loc_18002F502
0x18002f4dd  mov     r9, [rcx+28h]
0x18002f4e1  mov     dl, dil
0x18002f4e4  mov     rcx, [rcx+10h]
0x18002f4e8  mov     [rsp+0A8h+var_58], ebx
0x18002f4ec  mov     [rsp+0A8h+var_60], rsi
0x18002f4f1  mov     [rsp+0A8h+var_70], r13
0x18002f4f6  mov     [rsp+0A8h+var_78], 5Ah ; 'Z'
0x18002f4fd  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002f502  mov     eax, ebx
0x18002f504  add     rsp, 78h
0x18002f508  pop     r15
0x18002f50a  pop     r14
0x18002f50c  pop     r13
0x18002f50e  pop     rdi
0x18002f50f  pop     rsi
0x18002f510  pop     rbx
0x18002f511  retn
```
