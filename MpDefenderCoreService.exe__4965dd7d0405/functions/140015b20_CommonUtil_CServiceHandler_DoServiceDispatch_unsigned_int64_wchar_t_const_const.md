# CommonUtil::CServiceHandler::DoServiceDispatch(unsigned __int64,wchar_t const * const *)

- ea: `0x140015b20`
- end: `0x140015c8c`
- name: `?DoServiceDispatch@CServiceHandler@CommonUtil@@AEAAX_KPEBQEB_W@Z`
- size: `364`
- prototype: `void __fastcall(CommonUtil::CServiceHandler *__hidden this, unsigned __int64, const wchar_t *const *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140016c00`

## callees

- `0x140013bf4`
- `0x140015528`
- `0x140015b20`
- `0x140017738`
- `0x14003a130`
- `0x14003a5c0`
- `0x140085d94`
- `0x140166250`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x140015bfe`
- `KERNEL32!UnregisterWaitEx` at `0x140015bfe`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x140015b94`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x140015b94`

## pseudocode

```c
void __fastcall CommonUtil::CServiceHandler::DoServiceDispatch(
        CommonUtil::CServiceHandler *this,
        __int64 a2,
        wchar_t ***a3)
{
  const WCHAR *v3; // rdi
  wchar_t **v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  void *v9; // rcx
  SERVICE_STATUS_HANDLE v10; // rax
  char LastFailure; // al
  void **v12; // rsi
  void *v13; // rcx
  unsigned int v14[2]; // [rsp+30h] [rbp-38h] BYREF

  v3 = (const WCHAR *)*((_QWORD *)this + 2);
  if ( a2 )
  {
    v7 = *a3;
    if ( *a3 )
    {
      *(_QWORD *)v14 = 0;
      v3 = (const WCHAR *)v7;
      CommonUtil::HrDuplicateStringW((CommonUtil *)v14, v7, (const wchar_t *)a3);
      if ( *(_QWORD *)v14 )
      {
        v9 = (void *)*((_QWORD *)this + 2);
        *((_QWORD *)this + 2) = *(_QWORD *)v14;
        if ( v9 )
          operator delete(v9, v8);
      }
    }
  }
  v10 = RegisterServiceCtrlHandlerExW(v3, CommonUtil::CServiceHandler::ServiceCtrlCallback, this);
  *((_QWORD *)this + 12) = v10;
  if ( v10 )
  {
    v12 = (void **)*((_QWORD *)this + 3);
    v13 = (void *)*((_QWORD *)this + 5);
    if ( v13 )
    {
      UnregisterWaitEx(v13, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)this + 5) = 0;
    }
    if ( (int)CommonUtil::UtilRegisterWaitForSingleObject(
                (CommonUtil::CServiceHandler *)((char *)this + 40),
                v12,
                CommonUtil::CServiceHandler::ServiceShutdownCallback,
                (void (*)(void *, unsigned __int8))this,
                0xFFFFFFFF,
                8u,
                v14[0]) >= 0 )
      (*(void (__fastcall **)(_QWORD, __int64, wchar_t ***))(**((_QWORD **)this + 6) + 24LL))(
        *((_QWORD *)this + 6),
        a2,
        a3);
    else
      (*(void (__fastcall **)(CommonUtil::CServiceHandler *, __int64, _QWORD))(*(_QWORD *)this + 56LL))(this, 1, 0);
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        43,
        (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
        *((_QWORD *)this + 2),
        LastFailure);
    *((_DWORD *)this + 17) = 1;
  }
}

```

## disassembly

```asm
0x140015b20  push    rbx
0x140015b22  push    rbp
0x140015b23  push    rsi
0x140015b24  push    rdi
0x140015b25  push    r14
0x140015b27  sub     rsp, 40h
0x140015b2b  mov     rax, cs:__security_cookie
0x140015b32  xor     rax, rsp
0x140015b35  mov     [rsp+68h+var_30], rax
0x140015b3a  mov     rdi, [rcx+10h]
0x140015b3e  mov     r14, r8
0x140015b41  mov     rbp, rdx
0x140015b44  mov     rbx, rcx
0x140015b47  cmp     rdx, 1
0x140015b4b  jb      short loc_140015B87
0x140015b4d  mov     rdx, [r8]; wchar_t **
0x140015b50  test    rdx, rdx
0x140015b53  jz      short loc_140015B87
0x140015b55  lea     rcx, [rsp+68h+var_38]; this
0x140015b5a  mov     qword ptr [rsp+68h+var_38], 0; unsigned int
0x140015b63  mov     rdi, rdx
0x140015b66  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x140015b6b  mov     rax, qword ptr [rsp+68h+var_38]
0x140015b70  test    rax, rax
0x140015b73  jz      short loc_140015B87
0x140015b75  mov     rcx, [rbx+10h]; void *
0x140015b79  mov     [rbx+10h], rax
0x140015b7d  test    rcx, rcx
0x140015b80  jz      short loc_140015B87
0x140015b82  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015b87  mov     r8, rbx; lpContext
0x140015b8a  lea     rdx, ?ServiceCtrlCallback@CServiceHandler@CommonUtil@@CAKKKPEAX0@Z; lpHandlerProc
0x140015b91  mov     rcx, rdi; lpServiceName
0x140015b94  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140015b9a  mov     [rbx+60h], rax
0x140015b9e  test    rax, rax
0x140015ba1  jnz     short loc_140015BEA
0x140015ba3  call    HrGetLastFailure
0x140015ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x140015baf  lea     rdx, WPP_GLOBAL_Control
0x140015bb6  cmp     rcx, rdx
0x140015bb9  jz      short loc_140015BDE
0x140015bbb  test    byte ptr [rcx+1Ch], 1
0x140015bbf  jz      short loc_140015BDE
0x140015bc1  mov     r9, [rbx+10h]
0x140015bc5  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140015bcc  mov     rcx, [rcx+10h]
0x140015bd0  mov     edx, 2Bh ; '+'
0x140015bd5  mov     [rsp+68h+var_48], eax
0x140015bd9  call    WPP_SF_Sd
0x140015bde  mov     dword ptr [rbx+44h], 1
0x140015be5  jmp     loc_140015C74
0x140015bea  mov     rsi, [rbx+18h]
0x140015bee  lea     rdi, [rbx+28h]
0x140015bf2  mov     rcx, [rdi]; WaitHandle
0x140015bf5  test    rcx, rcx
0x140015bf8  jz      short loc_140015C0B
0x140015bfa  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x140015bfe  call    cs:__imp_UnregisterWaitEx
0x140015c04  mov     qword ptr [rdi], 0
0x140015c0b  mov     [rsp+68h+var_40], 8; ULONG
0x140015c13  lea     r8, ?ServiceShutdownCallback@CServiceHandler@CommonUtil@@CAXPEAXE@Z; void *
0x140015c1a  mov     r9, rbx; void (*)(void *, unsigned __int8)
0x140015c1d  mov     [rsp+68h+var_48], 0FFFFFFFFh; ULONG
0x140015c25  mov     rdx, rsi; void **
0x140015c28  mov     rcx, rdi; this
0x140015c2b  call    ?UtilRegisterWaitForSingleObject@CommonUtil@@YAJPEAPEAXPEAXP6AX1E@Z1KK@Z; CommonUtil::UtilRegisterWaitForSingleObject(void * *,void *,void (*)(void *,uchar),void *,ulong,ulong)
0x140015c30  mov     edx, eax
0x140015c32  mov     r8d, eax
0x140015c35  shr     edx, 1Fh
0x140015c38  test    dl, dl
0x140015c3a  jz      short loc_140015C5D
0x140015c3c  mov     rdx, [rbx]
0x140015c3f  xor     r9d, r9d
0x140015c42  mov     [rsp+68h+var_48], r8d
0x140015c47  mov     rcx, rbx
0x140015c4a  xor     r8d, r8d
0x140015c4d  mov     rax, [rdx+38h]
0x140015c51  lea     edx, [r9+1]
0x140015c55  call    cs:__guard_dispatch_icall_fptr
0x140015c5b  jmp     short loc_140015C74
0x140015c5d  mov     rcx, [rbx+30h]
0x140015c61  mov     r8, r14
0x140015c64  mov     rdx, rbp
0x140015c67  mov     rax, [rcx]
0x140015c6a  mov     rax, [rax+18h]
0x140015c6e  call    cs:__guard_dispatch_icall_fptr
0x140015c74  mov     rcx, [rsp+68h+var_30]
0x140015c79  xor     rcx, rsp; StackCookie
0x140015c7c  call    __security_check_cookie
0x140015c81  add     rsp, 40h
0x140015c85  pop     r14
0x140015c87  pop     rdi
0x140015c88  pop     rsi
0x140015c89  pop     rbp
0x140015c8a  pop     rbx
0x140015c8b  retn
```
