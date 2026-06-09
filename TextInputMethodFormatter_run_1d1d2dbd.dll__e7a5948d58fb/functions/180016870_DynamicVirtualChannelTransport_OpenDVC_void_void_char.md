# DynamicVirtualChannelTransport::OpenDVC(void * *,void * *,char *)

- ea: `0x180016870`
- end: `0x180016ba4`
- name: `?OpenDVC@DynamicVirtualChannelTransport@@MEAAJPEAPEAX0PEAD@Z`
- size: `820`
- prototype: `DWORD __fastcall(HANDLE *this, void **, void **, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015f38`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180014b90`
- `0x180016870`
- `0x1800172fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800168df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800168df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016b7d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001697c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001697c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800169db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800169e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800169db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800169e4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016a0e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016a0e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelOpenEx` at `0x18001691e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelOpenEx` at `0x18001691e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180016b30`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180016b30`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelQuery` at `0x180016904`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelQuery` at `0x180016972`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelQuery` at `0x180016904`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelQuery` at `0x180016972`

## string_xrefs

- `0x180016a41`: `DynamicVirtualChannelTransport::OpenDVC`

## pseudocode

```c
DWORD __fastcall DynamicVirtualChannelTransport::OpenDVC(HANDLE *this, void **a2, void **a3, char *a4)
{
  void *v4; // r12
  signed int v9; // edi
  DWORD result; // eax
  HANDLE v11; // rax
  signed int LastError; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // r9d
  signed int v16; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v18; // rax
  signed int v19; // eax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-B9h]
  DWORD pBytesReturned; // [rsp+40h] [rbp-99h] BYREF
  PVOID ppBuffer; // [rsp+48h] [rbp-91h] BYREF
  signed int v23; // [rsp+50h] [rbp-89h] BYREF
  void **v24; // [rsp+58h] [rbp-81h] BYREF
  PVOID v25; // [rsp+60h] [rbp-79h] BYREF
  void *v26; // [rsp+68h] [rbp-71h] BYREF
  __int64 v27; // [rsp+70h] [rbp-69h] BYREF
  char v28[32]; // [rsp+80h] [rbp-59h] BYREF
  __int64 *v29; // [rsp+A0h] [rbp-39h]
  __int64 v30; // [rsp+A8h] [rbp-31h]
  signed int *v31; // [rsp+B0h] [rbp-29h]
  __int64 v32; // [rsp+B8h] [rbp-21h]
  void **v33; // [rsp+C0h] [rbp-19h]
  __int64 v34; // [rsp+C8h] [rbp-11h]
  PVOID *v35; // [rsp+D0h] [rbp-9h]
  __int64 v36; // [rsp+D8h] [rbp-1h]
  void ***v37; // [rsp+E0h] [rbp+7h]
  __int64 v38; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v4 = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"DynamicVirtualChannelTransport::OpenDVC",
        338,
        87);
    goto LABEL_29;
  }
  result = WaitForSingleObject(this[15], 0);
  if ( !result )
    return result;
  v9 = 0;
  if ( !*a2 || !WTSVirtualChannelQuery(*a2, WTSVirtualFileHandle, &ppBuffer, &pBytesReturned) )
  {
    v11 = WTSVirtualChannelOpenEx(0xFFFFFFFF, a4, 5u);
    *a2 = v11;
    if ( v11 )
      goto LABEL_16;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
    {
LABEL_16:
      if ( WTSVirtualChannelQuery(*a2, WTSVirtualFileHandle, &ppBuffer, &pBytesReturned) )
        goto LABEL_19;
      v16 = GetLastError();
      v9 = v16;
      if ( v16 > 0 )
        v9 = (unsigned __int16)v16 | 0x80070000;
      if ( v9 >= 0 )
      {
LABEL_19:
        if ( pBytesReturned != 8 )
        {
          v9 = -2147024809;
          if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
            McTemplateU0sqq_EventWriteTransfer(
              v14,
              v13,
              (unsigned int)"DynamicVirtualChannelTransport::OpenDVC",
              370,
              87);
          goto LABEL_29;
        }
        v4 = *(void **)ppBuffer;
        CurrentProcess = GetCurrentProcess();
        v18 = GetCurrentProcess();
        if ( DuplicateHandle(v18, v4, CurrentProcess, a3, 0, 0, 2u) )
          goto LABEL_29;
        v19 = GetLastError();
        v9 = v19;
        if ( v19 > 0 )
          v9 = (unsigned __int16)v19 | 0x80070000;
        if ( v9 >= 0 || (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
          goto LABEL_29;
        v15 = 381;
      }
      else
      {
        if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
          goto LABEL_29;
        v15 = 368;
      }
    }
    else
    {
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
        goto LABEL_29;
      v15 = 362;
    }
    McTemplateU0sqq_EventWriteTransfer(v14, v13, (unsigned int)"DynamicVirtualChannelTransport::OpenDVC", v15, v9);
  }
LABEL_29:
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000400000LL) != 0
    && (qword_180082098 & 0x400000400000LL) == qword_180082098 )
  {
    v25 = ppBuffer;
    v24 = a3;
    v37 = &v24;
    v26 = v4;
    v35 = &v25;
    v23 = v9;
    v33 = &v26;
    v31 = &v23;
    v29 = &v27;
    v27 = 0x1000000;
    v38 = 8;
    v36 = 8;
    v34 = 8;
    v32 = 4;
    v30 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &unk_18007540E, 0, 0, 7, v28);
  }
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( v9 == -2147024865
    || v9 < 0
    && (wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x197,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\DVCTransport\\DynamicVirtualChannelTransport.cpp",
          (const char *)(unsigned int)v9,
          dwDesiredAccess),
        v9 != -2147024663)
    && v9 != -2147022646 )
  {
    if ( !*((_BYTE *)this + 17) || v9 != -2147024865 )
      SetEvent(_inputServiceShutdownEvent);
  }
  return v9;
}

```

## disassembly

```asm
0x180016870  push    rbp
0x180016872  push    rbx
0x180016873  push    rdi
0x180016874  push    r12
0x180016876  push    r13
0x180016878  push    r14
0x18001687a  push    r15
0x18001687c  lea     rbp, [rsp-27h]
0x180016881  sub     rsp, 100h
0x180016888  mov     rax, cs:__security_cookie
0x18001688f  xor     rax, rsp
0x180016892  mov     [rbp+57h+var_40], rax
0x180016896  xor     r12d, r12d
0x180016899  mov     r14, r9
0x18001689c  mov     [rsp+130h+ppBuffer], r12
0x1800168a1  mov     r13, r8
0x1800168a4  mov     [rsp+130h+pBytesReturned], r12d
0x1800168a9  mov     rbx, rdx
0x1800168ac  mov     r15, rcx
0x1800168af  test    rdx, rdx
0x1800168b2  jnz     short loc_1800168D9
0x1800168b4  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800168bb  mov     edi, 80070057h
0x1800168c0  jz      loc_180016A4D
0x1800168c6  mov     [rsp+130h+dwDesiredAccess], 80070057h
0x1800168ce  mov     r9d, 152h
0x1800168d4  jmp     loc_180016A41
0x1800168d9  mov     rcx, [rcx+78h]; hHandle
0x1800168dd  xor     edx, edx; dwMilliseconds
0x1800168df  call    cs:__imp_WaitForSingleObject
0x1800168e5  test    eax, eax
0x1800168e7  jz      loc_180016B85
0x1800168ed  mov     rcx, [rbx]; hChannelHandle
0x1800168f0  xor     edi, edi
0x1800168f2  test    rcx, rcx
0x1800168f5  jz      short loc_180016912
0x1800168f7  lea     r9, [rsp+130h+pBytesReturned]; pBytesReturned
0x1800168fc  lea     r8, [rsp+130h+ppBuffer]; ppBuffer
0x180016901  lea     edx, [rdi+1]; WTS_VIRTUAL_CLASS
0x180016904  call    cs:__imp_WTSVirtualChannelQuery
0x18001690a  test    eax, eax
0x18001690c  jnz     loc_180016A4D
0x180016912  mov     r8d, 5; flags
0x180016918  mov     rdx, r14; pVirtualName
0x18001691b  or      ecx, 0FFFFFFFFh; SessionId
0x18001691e  call    cs:__imp_WTSVirtualChannelOpenEx
0x180016924  mov     [rbx], rax
0x180016927  mov     r14d, 80070000h
0x18001692d  test    rax, rax
0x180016930  jnz     short loc_180016960
0x180016932  call    cs:__imp_GetLastError
0x180016938  mov     edi, eax
0x18001693a  test    eax, eax
0x18001693c  jle     short loc_180016944
0x18001693e  movzx   edi, ax
0x180016941  or      edi, r14d
0x180016944  test    edi, edi
0x180016946  jns     short loc_180016960
0x180016948  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001694f  jz      loc_180016A4D
0x180016955  mov     r9d, 16Ah
0x18001695b  jmp     loc_180016A3D
0x180016960  mov     rcx, [rbx]; hChannelHandle
0x180016963  lea     r9, [rsp+130h+pBytesReturned]; pBytesReturned
0x180016968  lea     r8, [rsp+130h+ppBuffer]; ppBuffer
0x18001696d  mov     edx, 1; WTS_VIRTUAL_CLASS
0x180016972  call    cs:__imp_WTSVirtualChannelQuery
0x180016978  test    eax, eax
0x18001697a  jnz     short loc_1800169AA
0x18001697c  call    cs:__imp_GetLastError
0x180016982  mov     edi, eax
0x180016984  test    eax, eax
0x180016986  jle     short loc_18001698E
0x180016988  movzx   edi, ax
0x18001698b  or      edi, r14d
0x18001698e  test    edi, edi
0x180016990  jns     short loc_1800169AA
0x180016992  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180016999  jz      loc_180016A4D
0x18001699f  mov     r9d, 170h
0x1800169a5  jmp     loc_180016A3D
0x1800169aa  cmp     [rsp+130h+pBytesReturned], 8
0x1800169af  jz      short loc_1800169D3
0x1800169b1  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800169b8  mov     edi, 80070057h
0x1800169bd  jz      loc_180016A4D
0x1800169c3  mov     [rsp+130h+dwDesiredAccess], 80070057h
0x1800169cb  mov     r9d, 172h
0x1800169d1  jmp     short loc_180016A41
0x1800169d3  mov     rax, [rsp+130h+ppBuffer]
0x1800169d8  mov     r12, [rax]
0x1800169db  call    cs:__imp_GetCurrentProcess
0x1800169e1  mov     rbx, rax
0x1800169e4  call    cs:__imp_GetCurrentProcess
0x1800169ea  mov     [rsp+130h+dwOptions], 2; dwOptions
0x1800169f2  mov     r9, r13; lpTargetHandle
0x1800169f5  mov     rcx, rax; hSourceProcessHandle
0x1800169f8  mov     [rsp+130h+bInheritHandle], 0; bInheritHandle
0x180016a00  mov     r8, rbx; hTargetProcessHandle
0x180016a03  mov     [rsp+130h+dwDesiredAccess], 0; dwDesiredAccess
0x180016a0b  mov     rdx, r12; hSourceHandle
0x180016a0e  call    cs:__imp_DuplicateHandle
0x180016a14  test    eax, eax
0x180016a16  jnz     short loc_180016A4D
0x180016a18  call    cs:__imp_GetLastError
0x180016a1e  mov     edi, eax
0x180016a20  test    eax, eax
0x180016a22  jle     short loc_180016A2A
0x180016a24  movzx   edi, ax
0x180016a27  or      edi, r14d
0x180016a2a  test    edi, edi
0x180016a2c  jns     short loc_180016A4D
0x180016a2e  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180016a35  jz      short loc_180016A4D
0x180016a37  mov     r9d, 17Dh
0x180016a3d  mov     [rsp+130h+dwDesiredAccess], edi
0x180016a41  lea     r8, aDynamicvirtual; "DynamicVirtualChannelTransport::OpenDVC"
0x180016a48  call    McTemplateU0sqq_EventWriteTransfer
0x180016a4d  mov     eax, cs:dword_180082080
0x180016a53  cmp     eax, 5
0x180016a56  jbe     loc_180016B26
0x180016a5c  mov     rcx, cs:qword_180082098
0x180016a63  mov     rdx, 400000400000h
0x180016a6d  mov     rax, cs:qword_180082090
0x180016a74  test    rdx, rax
0x180016a77  jz      loc_180016B26
0x180016a7d  mov     rax, rcx
0x180016a80  and     rax, rdx
0x180016a83  cmp     rax, rcx
0x180016a86  jnz     loc_180016B26
0x180016a8c  mov     rax, [rsp+130h+ppBuffer]
0x180016a91  lea     rdx, unk_18007540E
0x180016a98  mov     [rbp+57h+var_D0], rax
0x180016a9c  lea     rcx, dword_180082080
0x180016aa3  lea     rax, [rsp+130h+var_D8]
0x180016aa8  mov     [rsp+130h+var_D8], r13
0x180016aad  mov     [rbp+57h+var_50], rax
0x180016ab1  xor     r9d, r9d
0x180016ab4  lea     rax, [rbp+57h+var_D0]
0x180016ab8  mov     [rbp+57h+var_C8], r12
0x180016abc  mov     [rbp+57h+var_60], rax
0x180016ac0  xor     r8d, r8d
0x180016ac3  lea     rax, [rbp+57h+var_C8]
0x180016ac7  mov     [rsp+130h+var_E0], edi
0x180016acb  mov     [rbp+57h+var_70], rax
0x180016acf  lea     rax, [rsp+130h+var_E0]
0x180016ad4  mov     [rbp+57h+var_80], rax
0x180016ad8  lea     rax, [rbp+57h+var_C0]
0x180016adc  mov     [rbp+57h+var_90], rax
0x180016ae0  lea     rax, [rbp+57h+var_B0]
0x180016ae4  mov     qword ptr [rsp+130h+bInheritHandle], rax
0x180016ae9  mov     [rsp+130h+dwDesiredAccess], 7; int
0x180016af1  mov     [rbp+57h+var_C0], 1000000h
0x180016af9  mov     [rbp+57h+var_48], 8
0x180016b01  mov     [rbp+57h+var_58], 8
0x180016b09  mov     [rbp+57h+var_68], 8
0x180016b11  mov     [rbp+57h+var_78], 4
0x180016b19  mov     [rbp+57h+var_88], 8
0x180016b21  call    _tlgWriteTransfer_EventWriteTransfer
0x180016b26  mov     rcx, [rsp+130h+ppBuffer]; pMemory
0x180016b2b  test    rcx, rcx
0x180016b2e  jz      short loc_180016B36
0x180016b30  call    cs:__imp_WTSFreeMemory
0x180016b36  mov     ebx, 8007001Fh
0x180016b3b  cmp     edi, ebx
0x180016b3d  jz      short loc_180016B6B
0x180016b3f  test    edi, edi
0x180016b41  jns     short loc_180016B83
0x180016b43  mov     rcx, [rbp+5Fh]; this
0x180016b47  lea     r8, aMincoreTextinp_6; "mincore\\textinput\\dev\\virtualization"...
0x180016b4e  mov     r9d, edi; char *
0x180016b51  mov     edx, 197h; void *
0x180016b56  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016b5b  cmp     edi, 800700E9h
0x180016b61  jz      short loc_180016B83
0x180016b63  cmp     edi, 800708CAh
0x180016b69  jz      short loc_180016B83
0x180016b6b  cmp     byte ptr [r15+11h], 0
0x180016b70  jz      short loc_180016B76
0x180016b72  cmp     edi, ebx
0x180016b74  jz      short loc_180016B83
0x180016b76  mov     rcx, cs:?_inputServiceShutdownEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x180016b7d  call    cs:__imp_SetEvent
0x180016b83  mov     eax, edi
0x180016b85  mov     rcx, [rbp+57h+var_40]
0x180016b89  xor     rcx, rsp; StackCookie
0x180016b8c  call    __security_check_cookie
0x180016b91  add     rsp, 100h
0x180016b98  pop     r15
0x180016b9a  pop     r14
0x180016b9c  pop     r13
0x180016b9e  pop     r12
0x180016ba0  pop     rdi
0x180016ba1  pop     rbx
0x180016ba2  pop     rbp
0x180016ba3  retn
```
