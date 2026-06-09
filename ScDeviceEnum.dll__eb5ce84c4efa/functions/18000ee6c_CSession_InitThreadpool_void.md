# CSession::_InitThreadpool(void)

- ea: `0x18000ee6c`
- end: `0x18000f008`
- name: `?_InitThreadpool@CSession@@AEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(CSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d754`

## callees

- `0x1800024b4`
- `0x180006d40`
- `0x1800071d4`
- `0x18000c91c`
- `0x18000d2ec`
- `0x18000d5e4`
- `0x18000ee6c`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000ef49`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000ef49`

## string_xrefs

- `0x18000ee91`: `CSession::_InitThreadpool`

## pseudocode

```c
__int64 __fastcall CSession::_InitThreadpool(CSession *this)
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  signed int v7; // [rsp+30h] [rbp-9h] BYREF
  int v8; // [rsp+34h] [rbp-5h] BYREF
  __int64 v9; // [rsp+38h] [rbp-1h] BYREF
  __int16 v10; // [rsp+40h] [rbp+7h]
  _QWORD *v11; // [rsp+48h] [rbp+Fh] BYREF
  _QWORD v12[3]; // [rsp+50h] [rbp+17h] BYREF
  char v13[32]; // [rsp+68h] [rbp+2Fh] BYREF

  v12[0] = v13;
  v12[1] = &v8;
  strcpy(v13, "CSession::_InitThreadpool");
  v12[2] = &v7;
  v7 = 0;
  v8 = 0;
  lambda_d361444945bb209b5e92375a141172b4_::operator()(v12);
  v8 = 1;
  v11 = v12;
  *((_DWORD *)this + 110) = 3;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_DWORD *)this + 124) = 0;
  *((_DWORD *)this + 125) = 1;
  *((_DWORD *)this + 126) = 72;
  v9 = *wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          &v9,
          (__int64)this);
  v10 = 256;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 64) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    *((_QWORD *)this + 57) = ThreadpoolCleanupGroup;
    *((_QWORD *)this + 58) = 0;
    HIBYTE(v10) = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError;
    WppTraceIndent(v4, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        v7);
    }
  }
  v5 = v7;
  wil::details::ScopeExitFnGuard__lambda_d301b83811554725fa5007d0fd1ba661___::operator()(&v9);
  WppTraceUnwinder__lambda_d361444945bb209b5e92375a141172b4____::_WppTraceUnwinder__lambda_d361444945bb209b5e92375a141172b4____(&v11);
  return v5;
}

```

## disassembly

```asm
0x18000ee6c  mov     [rsp-8+arg_8], rbx
0x18000ee71  mov     [rsp-8+arg_10], rdi
0x18000ee76  push    rbp
0x18000ee77  lea     rbp, [rsp-57h]
0x18000ee7c  sub     rsp, 90h
0x18000ee83  mov     rax, cs:__security_cookie
0x18000ee8a  xor     rax, rsp
0x18000ee8d  mov     [rbp+57h+var_8], rax
0x18000ee91  movups  xmm0, xmmword ptr cs:aCsessionInitth; "CSession::_InitThreadpool"
0x18000ee98  lea     rax, [rbp+57h+var_28]
0x18000ee9c  mov     rbx, rcx
0x18000ee9f  movups  xmm1, xmmword ptr cs:aCsessionInitth+0Ah; "_InitThreadpool"
0x18000eea6  mov     [rbp+57h+var_40], rax
0x18000eeaa  lea     rcx, [rbp+57h+var_40]
0x18000eeae  lea     rax, [rbp+57h+var_5C]
0x18000eeb2  xor     edi, edi
0x18000eeb4  mov     [rbp+57h+var_38], rax
0x18000eeb8  lea     rax, [rbp+57h+var_60]
0x18000eebc  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x18000eec0  mov     [rbp+57h+var_30], rax
0x18000eec4  mov     [rbp+57h+var_60], edi
0x18000eec7  mov     [rbp+57h+var_5C], edi
0x18000eeca  movups  xmmword ptr [rbp+57h+var_28+0Ah], xmm1
0x18000eece  call    _lambda_d361444945bb209b5e92375a141172b4___operator__
0x18000eed3  lea     rax, [rbp+57h+var_40]
0x18000eed7  mov     [rbp+57h+var_5C], 1
0x18000eede  mov     rdx, rbx
0x18000eee1  mov     [rbp+57h+var_48], rax
0x18000eee5  lea     rcx, [rbp+57h+var_58]
0x18000eee9  mov     dword ptr [rbx+1B8h], 3
0x18000eef3  mov     [rbx+1C0h], rdi
0x18000eefa  mov     [rbx+1C8h], rdi
0x18000ef01  mov     [rbx+1D0h], rdi
0x18000ef08  mov     [rbx+1D8h], rdi
0x18000ef0f  mov     [rbx+1E0h], rdi
0x18000ef16  mov     [rbx+1E8h], rdi
0x18000ef1d  mov     [rbx+1F0h], edi
0x18000ef23  mov     dword ptr [rbx+1F4h], 1
0x18000ef2d  mov     dword ptr [rbx+1F8h], 48h ; 'H'
0x18000ef37  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18000ef3c  mov     rcx, [rax]
0x18000ef3f  mov     [rbp+57h+var_58], rcx
0x18000ef43  mov     [rbp+57h+var_50], 100h
0x18000ef49  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000ef4f  mov     [rbx+200h], rax
0x18000ef56  test    rax, rax
0x18000ef59  jnz     short loc_18000EFBE
0x18000ef5b  call    cs:__imp_GetLastError
0x18000ef61  test    eax, eax
0x18000ef63  jle     short loc_18000EF6D
0x18000ef65  movzx   eax, ax
0x18000ef68  or      eax, 80070000h
0x18000ef6d  mov     edx, 2
0x18000ef72  mov     [rbp+57h+var_60], eax
0x18000ef75  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000ef7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef81  lea     rax, WPP_GLOBAL_Control
0x18000ef88  cmp     rcx, rax
0x18000ef8b  jz      short loc_18000EFD0
0x18000ef8d  test    byte ptr [rcx+1Ch], 1
0x18000ef91  jz      short loc_18000EFD0
0x18000ef93  cmp     byte ptr [rcx+19h], 2
0x18000ef97  jb      short loc_18000EFD0
0x18000ef99  mov     eax, [rbp+57h+var_60]
0x18000ef9c  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000efa3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000efaa  mov     edx, 10h
0x18000efaf  mov     rcx, [rcx+10h]
0x18000efb3  mov     [rsp+90h+var_70], eax
0x18000efb7  call    WPP_SF_sd
0x18000efbc  jmp     short loc_18000EFD0
0x18000efbe  mov     [rbx+1C8h], rax
0x18000efc5  mov     [rbx+1D0h], rdi
0x18000efcc  mov     byte ptr [rbp+57h+var_50+1], dil
0x18000efd0  mov     ebx, [rbp+57h+var_60]
0x18000efd3  lea     rcx, [rbp+57h+var_58]
0x18000efd7  call    wil__details__ScopeExitFnGuard__lambda_d301b83811554725fa5007d0fd1ba661_____operator__
0x18000efdc  lea     rcx, [rbp+57h+var_48]
0x18000efe0  call    WppTraceUnwinder__lambda_d361444945bb209b5e92375a141172b4_______WppTraceUnwinder__lambda_d361444945bb209b5e92375a141172b4____
0x18000efe5  mov     eax, ebx
0x18000efe7  mov     rcx, [rbp+57h+var_8]
0x18000efeb  xor     rcx, rsp; StackCookie
0x18000efee  call    __security_check_cookie
0x18000eff3  lea     r11, [rsp+90h+var_s0]
0x18000effb  mov     rbx, [r11+18h]
0x18000efff  mov     rdi, [r11+20h]
0x18000f003  mov     rsp, r11
0x18000f006  pop     rbp
0x18000f007  retn
```
