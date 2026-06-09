# KeyManagement::CreateSecurityProcess(_GUID,ushort const *,uchar const *,unsigned __int64,_TRUSTLET_MAILBOX_KEY *,void * *)

- ea: `0x140274b90`
- end: `0x140274e3f`
- name: `?CreateSecurityProcess@KeyManagement@@YAJU_GUID@@PEBGPEBE_KPEAU_TRUSTLET_MAILBOX_KEY@@PEAPEAX@Z`
- size: `687`
- prototype: `__int64 __fastcall(KeyManagement *__hidden this, struct _GUID *, const unsigned __int16 *, const unsigned __int8 *, struct _PS_TRUSTLET_TKSESSION_ID *, struct _TRUSTLET_MAILBOX_KEY *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1402741a0`

## callees

- `0x1400b652c`
- `0x140132940`
- `0x1401335fc`
- `0x140274b90`
- `0x140274e48`
- `0x140275200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140274dca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140274dca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140274cab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140274cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140274cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140274d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140274cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140274d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140274df9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140274df9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140274cf1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140274cf1`
- `ntdll!NtClose` at `0x140274e0f`
- `ntdll!NtClose` at `0x140274e0f`
- `bcrypt!BCryptGenRandom` at `0x140274c45`
- `bcrypt!BCryptGenRandom` at `0x140274c45`

## pseudocode

```c
__int64 __fastcall KeyManagement::CreateSecurityProcess(
        KeyManagement *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        struct _PS_TRUSTLET_TKSESSION_ID *a5)
{
  NTSTATUS v9; // ebx
  int v10; // ebx
  HANDLE EventW; // rdi
  signed int LastError; // eax
  signed int v13; // eax
  DWORD v14; // eax
  HANDLE Handle[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  UCHAR pbBuffer[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v19; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+68h] [rbp-98h]
  WCHAR Name[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v22[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Buffer[264]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v24[296]; // [rsp+520h] [rbp+420h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v22, 0, 0x208u);
  memset_0(v24, 0, 0x248u);
  *(_QWORD *)pbBuffer = 0;
  memset_0(Name, 0, sizeof(Name));
  Handle[0] = 0;
  v19 = 0;
  v20 = 0;
  v9 = BCryptGenRandom(0, pbBuffer, 8u, 2u);
  if ( v9 < 0 )
    return (unsigned int)(v9 | 0x10000000);
  v10 = KeyManagement::_anonymous_namespace_::GenerateSessionId(a3, a4, &v19);
  if ( v10 >= 0 )
  {
    v10 = StringCchPrintfW(Name, 0x40u, L"Global\\%016llX", *(_QWORD *)pbBuffer);
    if ( v10 >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, Name);
      if ( !EventW )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return (unsigned int)v10;
      }
      if ( !GetSystemDirectoryW(Buffer, 0x104u) )
        goto LABEL_9;
      v10 = StringCchPrintfW(v22, 0x104u, L"%s\\%s", Buffer, L"vmsp.exe");
      if ( v10 >= 0 )
      {
        v10 = StringCchPrintfW(v24, 0x124u, L"%s {%s} %016llX", v22, a2, *(_QWORD *)pbBuffer);
        if ( v10 >= 0 )
        {
          v17 = *(_OWORD *)this;
          v10 = KeyManagement::CreateTrustlet(
                  (KeyManagement *)&v17,
                  &v19,
                  a5,
                  (struct _TRUSTLET_MAILBOX_KEY *)v22,
                  v24,
                  (unsigned __int16 *)Handle);
          if ( v10 >= 0 )
          {
            v14 = WaitForSingleObject(EventW, 0x4E20u);
            if ( v14 )
            {
              if ( v14 == 258 )
              {
                v10 = -2147023436;
              }
              else
              {
                if ( v14 == -1 )
                {
LABEL_9:
                  v13 = GetLastError();
                  v10 = v13;
                  if ( v13 > 0 )
                    v10 = (unsigned __int16)v13 | 0x80070000;
                  goto LABEL_19;
                }
                v10 = -2147418113;
              }
            }
          }
        }
      }
LABEL_19:
      CloseHandle(EventW);
      if ( Handle[0] )
        NtClose(Handle[0]);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140274b90  push    rbp
0x140274b92  push    rbx
0x140274b93  push    rsi
0x140274b94  push    rdi
0x140274b95  push    r12
0x140274b97  push    r14
0x140274b99  push    r15
0x140274b9b  lea     rbp, [rsp-680h]
0x140274ba3  sub     rsp, 780h
0x140274baa  mov     rax, cs:__security_cookie
0x140274bb1  xor     rax, rsp
0x140274bb4  mov     [rbp+6B0h+var_40], rax
0x140274bbb  mov     r12, [rbp+6B0h+arg_20]
0x140274bc2  mov     rdi, r8
0x140274bc5  mov     r14, rdx
0x140274bc8  mov     r15, rcx
0x140274bcb  mov     ebx, 208h
0x140274bd0  lea     rcx, [rbp+6B0h+Buffer]; void *
0x140274bd7  mov     r8d, ebx; Size
0x140274bda  xor     edx, edx; Val
0x140274bdc  mov     rsi, r9
0x140274bdf  call    memset_0
0x140274be4  mov     r8d, ebx; Size
0x140274be7  lea     rcx, [rbp+6B0h+var_6B0]; void *
0x140274beb  xor     edx, edx; Val
0x140274bed  call    memset_0
0x140274bf2  xor     edx, edx; Val
0x140274bf4  lea     r8d, [rbx+40h]; Size
0x140274bf8  lea     rcx, [rbp+6B0h+var_290]; void *
0x140274bff  call    memset_0
0x140274c04  xor     edx, edx; Val
0x140274c06  mov     qword ptr [rsp+7B0h+pbBuffer], 0
0x140274c0f  mov     r8d, 80h; Size
0x140274c15  lea     rcx, [rbp+6B0h+Name]; void *
0x140274c19  call    memset_0
0x140274c1e  xorps   xmm0, xmm0
0x140274c21  mov     [rsp+7B0h+Handle], 0; void **
0x140274c2a  mov     r9d, 2; dwFlags
0x140274c30  lea     rdx, [rsp+7B0h+pbBuffer]; pbBuffer
0x140274c35  xor     ecx, ecx; hAlgorithm
0x140274c37  movups  xmmword ptr [rsp+7B0h+var_758.Data1], xmm0
0x140274c3c  lea     r8d, [r9+6]; cbBuffer
0x140274c40  movups  [rsp+7B0h+var_748], xmm0
0x140274c45  call    cs:__imp_BCryptGenRandom
0x140274c4c  nop     dword ptr [rax+rax+00h]
0x140274c51  mov     ebx, eax
0x140274c53  test    eax, eax
0x140274c55  jns     short loc_140274C60
0x140274c57  bts     ebx, 1Ch
0x140274c5b  jmp     loc_140274E1B
0x140274c60  lea     r8, [rsp+7B0h+var_758]
0x140274c65  mov     rdx, rsi
0x140274c68  mov     rcx, rdi
0x140274c6b  call    KeyManagement___anonymous_namespace___GenerateSessionId
0x140274c70  mov     ebx, eax
0x140274c72  test    eax, eax
0x140274c74  js      loc_140274E1B
0x140274c7a  mov     r9, qword ptr [rsp+7B0h+pbBuffer]
0x140274c7f  lea     r8, aGlobal016llx; "Global\\%016llX"
0x140274c86  mov     edx, 40h ; '@'; unsigned __int64
0x140274c8b  lea     rcx, [rbp+6B0h+Name]; unsigned __int16 *
0x140274c8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140274c94  mov     ebx, eax
0x140274c96  test    eax, eax
0x140274c98  js      loc_140274E1B
0x140274c9e  xor     r8d, r8d; bInitialState
0x140274ca1  lea     r9, [rbp+6B0h+Name]; lpName
0x140274ca5  xor     ecx, ecx; lpEventAttributes
0x140274ca7  lea     edx, [r8+1]; bManualReset
0x140274cab  call    cs:__imp_CreateEventW
0x140274cb2  nop     dword ptr [rax+rax+00h]
0x140274cb7  mov     rdi, rax
0x140274cba  test    rax, rax
0x140274cbd  jnz     short loc_140274CE3
0x140274cbf  call    cs:__imp_GetLastError
0x140274cc6  nop     dword ptr [rax+rax+00h]
0x140274ccb  mov     ebx, eax
0x140274ccd  test    eax, eax
0x140274ccf  jle     loc_140274E1B
0x140274cd5  movzx   ebx, ax
0x140274cd8  or      ebx, 80070000h
0x140274cde  jmp     loc_140274E1B
0x140274ce3  mov     ebx, 104h
0x140274ce8  lea     rcx, [rbp+6B0h+Buffer]; lpBuffer
0x140274cef  mov     edx, ebx; uSize
0x140274cf1  call    cs:__imp_GetSystemDirectoryW
0x140274cf8  nop     dword ptr [rax+rax+00h]
0x140274cfd  test    eax, eax
0x140274cff  jnz     short loc_140274D25
0x140274d01  call    cs:__imp_GetLastError
0x140274d08  nop     dword ptr [rax+rax+00h]
0x140274d0d  mov     ebx, eax
0x140274d0f  test    eax, eax
0x140274d11  jle     loc_140274DF6
0x140274d17  movzx   ebx, ax
0x140274d1a  or      ebx, 80070000h
0x140274d20  jmp     loc_140274DF6
0x140274d25  lea     rax, aVmspExe; "vmsp.exe"
0x140274d2c  mov     rdx, rbx; unsigned __int64
0x140274d2f  lea     r9, [rbp+6B0h+Buffer]
0x140274d36  mov     [rsp+7B0h+var_790], rax
0x140274d3b  lea     r8, aSS_0; "%s\\%s"
0x140274d42  lea     rcx, [rbp+6B0h+var_6B0]; unsigned __int16 *
0x140274d46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140274d4b  mov     ebx, eax
0x140274d4d  test    eax, eax
0x140274d4f  js      loc_140274DF6
0x140274d55  mov     rax, qword ptr [rsp+7B0h+pbBuffer]
0x140274d5a  lea     r9, [rbp+6B0h+var_6B0]
0x140274d5e  mov     [rsp+7B0h+var_788], rax
0x140274d63  lea     r8, aSS016llx; "%s {%s} %016llX"
0x140274d6a  mov     edx, 124h; unsigned __int64
0x140274d6f  mov     [rsp+7B0h+var_790], r14
0x140274d74  lea     rcx, [rbp+6B0h+var_290]; unsigned __int16 *
0x140274d7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140274d80  mov     ebx, eax
0x140274d82  test    eax, eax
0x140274d84  js      short loc_140274DF6
0x140274d86  movaps  xmm0, xmmword ptr [r15]
0x140274d8a  lea     rax, [rsp+7B0h+Handle]
0x140274d8f  mov     [rsp+7B0h+var_788], rax; unsigned __int16 *
0x140274d94  lea     r9, [rbp+6B0h+var_6B0]; struct _TRUSTLET_MAILBOX_KEY *
0x140274d98  lea     rax, [rbp+6B0h+var_290]
0x140274d9f  movdqa  [rsp+7B0h+var_770], xmm0
0x140274da5  mov     r8, r12; struct _PS_TRUSTLET_TKSESSION_ID *
0x140274da8  mov     [rsp+7B0h+var_790], rax; unsigned __int16 *
0x140274dad  lea     rdx, [rsp+7B0h+var_758]; struct _GUID *
0x140274db2  lea     rcx, [rsp+7B0h+var_770]; this
0x140274db7  call    ?CreateTrustlet@KeyManagement@@YAJU_GUID@@PEAU_PS_TRUSTLET_TKSESSION_ID@@PEAU_TRUSTLET_MAILBOX_KEY@@PEBG3PEAPEAX@Z; KeyManagement::CreateTrustlet(_GUID,_PS_TRUSTLET_TKSESSION_ID *,_TRUSTLET_MAILBOX_KEY *,ushort const *,ushort const *,void * *)
0x140274dbc  mov     ebx, eax
0x140274dbe  test    eax, eax
0x140274dc0  js      short loc_140274DF6
0x140274dc2  mov     edx, 4E20h; dwMilliseconds
0x140274dc7  mov     rcx, rdi; hHandle
0x140274dca  call    cs:__imp_WaitForSingleObject
0x140274dd1  nop     dword ptr [rax+rax+00h]
0x140274dd6  test    eax, eax
0x140274dd8  jz      short loc_140274DF6
0x140274dda  cmp     eax, 102h
0x140274ddf  jz      short loc_140274DF1
0x140274de1  cmp     eax, 0FFFFFFFFh
0x140274de4  jz      loc_140274D01
0x140274dea  mov     ebx, 8000FFFFh
0x140274def  jmp     short loc_140274DF6
0x140274df1  mov     ebx, 800705B4h
0x140274df6  mov     rcx, rdi; hObject
0x140274df9  call    cs:__imp_CloseHandle
0x140274e00  nop     dword ptr [rax+rax+00h]
0x140274e05  mov     rcx, [rsp+7B0h+Handle]; Handle
0x140274e0a  test    rcx, rcx
0x140274e0d  jz      short loc_140274E1B
0x140274e0f  call    cs:__imp_NtClose
0x140274e16  nop     dword ptr [rax+rax+00h]
0x140274e1b  mov     eax, ebx
0x140274e1d  mov     rcx, [rbp+6B0h+var_40]
0x140274e24  xor     rcx, rsp; StackCookie
0x140274e27  call    __security_check_cookie
0x140274e2c  add     rsp, 780h
0x140274e33  pop     r15
0x140274e35  pop     r14
0x140274e37  pop     r12
0x140274e39  pop     rdi
0x140274e3a  pop     rsi
0x140274e3b  pop     rbx
0x140274e3c  pop     rbp
0x140274e3d  retn
```
