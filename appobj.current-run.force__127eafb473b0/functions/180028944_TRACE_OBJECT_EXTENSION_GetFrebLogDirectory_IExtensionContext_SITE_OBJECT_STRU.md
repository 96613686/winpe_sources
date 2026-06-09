# TRACE_OBJECT_EXTENSION::GetFrebLogDirectory(IExtensionContext *,SITE_OBJECT *,STRU *)

- ea: `0x180028944`
- end: `0x180028b77`
- name: `?GetFrebLogDirectory@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVSITE_OBJECT@@PEAVSTRU@@@Z`
- size: `563`
- prototype: `int(TRACE_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct SITE_OBJECT *, struct STRU *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180027190`

## callees

- `0x180001fb0`
- `0x180004a70`
- `0x18000d654`
- `0x180028944`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a9d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028a93`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028a93`

## string_xrefs

- `0x180028a50`: `traceFailedRequestsLogging.directory`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT_EXTENSION::GetFrebLogDirectory(
        TRACE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct SITE_OBJECT *a3,
        unsigned __int16 **a4)
{
  signed int v7; // ebx
  __int64 (__fastcall *v8)(struct IExtensionContext *, __int64, const wchar_t *, __int16 *, int *, _QWORD); // rax
  DWORD v9; // eax
  signed int LastError; // eax
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *p_Dst; // [rsp+78h] [rbp-88h]
  int v17; // [rsp+80h] [rbp-80h]
  __int16 v18; // [rsp+84h] [rbp-7Ch]
  int v19; // [rsp+88h] [rbp-78h]
  _BYTE v20[32]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpSrc; // [rsp+B0h] [rbp-50h]
  int v22; // [rsp+B8h] [rbp-48h]
  __int16 v23; // [rsp+BCh] [rbp-44h]
  int v24; // [rsp+C0h] [rbp-40h]
  WCHAR Dst; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v26[510]; // [rsp+D2h] [rbp-2Eh] BYREF
  __int16 v27; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v28[526]; // [rsp+2D2h] [rbp+1D2h] BYREF

  v12 = 0;
  v13 = 0;
  memset_0(v28, 0, 0x206u);
  v22 = 520;
  lpSrc = (LPCWSTR)&v27;
  v23 = 256;
  v27 = 0;
  v14 = 0;
  v24 = 0;
  memset_0(v26, 0, sizeof(v26));
  v17 = 512;
  p_Dst = &Dst;
  v18 = 256;
  v19 = 0;
  Dst = 0;
  if ( a2 && a3 && a4 )
  {
    v7 = (*(__int64 (__fastcall **)(struct SITE_OBJECT *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v13);
    if ( v7 >= 0 )
    {
      v8 = *(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, __int16 *, int *, _QWORD))(*(_QWORD *)a2 + 88LL);
      v12 = 260;
      v7 = v8(a2, v13, L"traceFailedRequestsLogging.directory", &v27, &v12, 0);
      if ( v7 >= 0 )
      {
        STRU::SyncWithBuffer((STRU *)v20);
        v9 = ExpandEnvironmentStringsW(lpSrc, &Dst, 0x100u);
        if ( v9 )
        {
          if ( v9 <= 0x100 )
          {
            STRU::SyncWithBuffer((STRU *)v15);
            v7 = (*(__int64 (__fastcall **)(struct SITE_OBJECT *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a3 + 80LL))(
                   a3,
                   L"SITE.ID",
                   &v14);
            if ( v7 >= 0 )
            {
              v7 = StringCchPrintfW(
                     a4[4],
                     (unsigned __int64)*((unsigned int *)a4 + 10) >> 1,
                     L"%ws\\W3SVC%ws",
                     p_Dst,
                     v14);
              if ( v7 >= 0 )
              {
                STRU::SyncWithBuffer((STRU *)a4);
                v7 = 0;
              }
            }
          }
          else
          {
            v7 = -2147024774;
          }
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v15);
  BUFFER::~BUFFER((BUFFER *)v20);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028944  push    rbp
0x180028946  push    rbx
0x180028947  push    rsi
0x180028948  push    rdi
0x180028949  push    r14
0x18002894b  lea     rbp, [rsp-3F0h]
0x180028953  sub     rsp, 4F0h
0x18002895a  mov     rax, cs:__security_cookie
0x180028961  xor     rax, rsp
0x180028964  mov     [rbp+410h+var_30], rax
0x18002896b  mov     rdi, r8
0x18002896e  mov     [rsp+510h+var_4D0], 0
0x180028976  mov     r14, rdx
0x180028979  mov     [rsp+510h+var_4C8], 0
0x180028982  xor     edx, edx; Val
0x180028984  lea     rcx, [rbp+410h+var_23E]; void *
0x18002898b  mov     r8d, 206h; Size
0x180028991  mov     rsi, r9
0x180028994  call    memset_0
0x180028999  lea     rax, [rbp+410h+var_240]
0x1800289a0  mov     [rbp+410h+var_458], 208h
0x1800289a7  mov     [rbp+410h+lpSrc], rax
0x1800289ab  lea     rcx, [rbp+410h+var_43E]; void *
0x1800289af  xor     eax, eax
0x1800289b1  mov     [rbp+410h+var_454], 100h
0x1800289b7  xor     edx, edx; Val
0x1800289b9  mov     [rbp+410h+var_240], ax
0x1800289c0  mov     r8d, 1FEh; Size
0x1800289c6  mov     [rsp+510h+var_4C0], rax
0x1800289cb  mov     [rbp+410h+var_450], 0
0x1800289d2  call    memset_0
0x1800289d7  lea     rax, [rbp+410h+Dst]
0x1800289db  mov     [rbp+410h+var_490], 200h
0x1800289e2  mov     [rsp+510h+var_498], rax
0x1800289e7  xor     eax, eax
0x1800289e9  mov     [rbp+410h+var_48C], 100h
0x1800289ef  mov     [rbp+410h+var_488], 0
0x1800289f6  mov     [rbp+410h+Dst], ax
0x1800289fa  test    r14, r14
0x1800289fd  jz      loc_180028B21
0x180028a03  test    rdi, rdi
0x180028a06  jz      loc_180028B21
0x180028a0c  test    rsi, rsi
0x180028a0f  jz      loc_180028B21
0x180028a15  mov     rax, [rdi]
0x180028a18  lea     rdx, [rsp+510h+var_4C8]
0x180028a1d  mov     rcx, rdi
0x180028a20  mov     rax, [rax+30h]
0x180028a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a29  mov     ebx, eax
0x180028a2b  test    eax, eax
0x180028a2d  js      loc_180028B26
0x180028a33  mov     rax, [r14]
0x180028a36  lea     rcx, [rsp+510h+var_4D0]
0x180028a3b  mov     rdx, [rsp+510h+var_4C8]
0x180028a40  lea     r9, [rbp+410h+var_240]
0x180028a47  mov     [rsp+510h+var_4E8], 0
0x180028a50  lea     r8, aTracefailedreq; "traceFailedRequestsLogging.directory"
0x180028a57  mov     [rsp+510h+var_4F0], rcx
0x180028a5c  mov     rcx, r14
0x180028a5f  mov     rax, [rax+58h]
0x180028a63  mov     [rsp+510h+var_4D0], 104h
0x180028a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a70  mov     ebx, eax
0x180028a72  test    eax, eax
0x180028a74  js      loc_180028B26
0x180028a7a  lea     rcx, [rbp+410h+var_480]; this
0x180028a7e  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180028a83  mov     rcx, [rbp+410h+lpSrc]; lpSrc
0x180028a87  lea     rdx, [rbp+410h+Dst]; lpDst
0x180028a8b  mov     ebx, 100h
0x180028a90  mov     r8d, ebx; nSize
0x180028a93  call    cs:__imp_ExpandEnvironmentStringsW
0x180028a99  test    eax, eax
0x180028a9b  jnz     short loc_180028AB4
0x180028a9d  call    cs:__imp_GetLastError
0x180028aa3  mov     ebx, eax
0x180028aa5  test    eax, eax
0x180028aa7  jle     short loc_180028B26
0x180028aa9  movzx   ebx, ax
0x180028aac  or      ebx, 80070000h
0x180028ab2  jmp     short loc_180028B26
0x180028ab4  cmp     eax, ebx
0x180028ab6  jbe     short loc_180028ABF
0x180028ab8  mov     ebx, 8007007Ah
0x180028abd  jmp     short loc_180028B26
0x180028abf  lea     rcx, [rsp+510h+var_4B8]; this
0x180028ac4  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180028ac9  mov     rax, [rdi]
0x180028acc  lea     r8, [rsp+510h+var_4C0]
0x180028ad1  lea     rdx, aSiteId; "SITE.ID"
0x180028ad8  mov     rcx, rdi
0x180028adb  mov     rax, [rax+50h]
0x180028adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ae4  mov     ebx, eax
0x180028ae6  test    eax, eax
0x180028ae8  js      short loc_180028B26
0x180028aea  mov     edx, [rsi+28h]
0x180028aed  lea     r8, aWsW3svcWs; "%ws\\W3SVC%ws"
0x180028af4  mov     rax, [rsp+510h+var_4C0]
0x180028af9  mov     r9, [rsp+510h+var_498]
0x180028afe  mov     rcx, [rsi+20h]; unsigned __int16 *
0x180028b02  shr     rdx, 1; unsigned __int64
0x180028b05  mov     [rsp+510h+var_4F0], rax
0x180028b0a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028b0f  mov     ebx, eax
0x180028b11  test    eax, eax
0x180028b13  js      short loc_180028B26
0x180028b15  mov     rcx, rsi; this
0x180028b18  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180028b1d  xor     ebx, ebx
0x180028b1f  jmp     short loc_180028B26
0x180028b21  mov     ebx, 80070057h
0x180028b26  mov     rcx, [rsp+510h+var_4C8]
0x180028b2b  test    rcx, rcx
0x180028b2e  jz      short loc_180028B45
0x180028b30  mov     rax, [rcx]
0x180028b33  mov     rax, [rax+10h]
0x180028b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b3c  mov     [rsp+510h+var_4C8], 0
0x180028b45  lea     rcx, [rsp+510h+var_4B8]; this
0x180028b4a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180028b4f  lea     rcx, [rbp+410h+var_480]; this
0x180028b53  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180028b58  mov     eax, ebx
0x180028b5a  mov     rcx, [rbp+410h+var_30]
0x180028b61  xor     rcx, rsp; StackCookie
0x180028b64  call    __security_check_cookie
0x180028b69  add     rsp, 4F0h
0x180028b70  pop     r14
0x180028b72  pop     rdi
0x180028b73  pop     rsi
0x180028b74  pop     rbx
0x180028b75  pop     rbp
0x180028b76  retn
```
