# CommonUtil::CMpWppTraceBase::Initialize(unsigned __int64,wchar_t const *,wchar_t const *,ulong,int,CommonUtil::tagMP_EVENT_TRACE_PROPERTIES *)

- ea: `0x1400f3b24`
- end: `0x1400f3e81`
- name: `?Initialize@CMpWppTraceBase@CommonUtil@@QEAAJ_KPEB_W1KHPEAUtagMP_EVENT_TRACE_PROPERTIES@2@@Z`
- size: `861`
- prototype: `int(CommonUtil::CMpWppTraceBase *__hidden this, unsigned __int64, const wchar_t *, const wchar_t *, unsigned int, int, struct CommonUtil::tagMP_EVENT_TRACE_PROPERTIES *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400f3650`

## callees

- `0x14000b554`
- `0x140014b10`
- `0x140017738`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d210`
- `0x140085d94`
- `0x1400935a0`
- `0x1400f395c`
- `0x1400f3b24`
- `0x1400f3e84`
- `0x1400f3f90`
- `0x1400f48a8`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400f3da2`
- `KERNEL32!CreateFileW` at `0x1400f3da2`
- `KERNEL32!CloseHandle` at `0x1400f3c90`
- `KERNEL32!CloseHandle` at `0x1400f3c90`
- `ADVAPI32!StartTraceW` at `0x1400f3d07`
- `ADVAPI32!StartTraceW` at `0x1400f3d07`
- `ADVAPI32!ControlTraceW` at `0x1400f3cac`
- `ADVAPI32!ControlTraceW` at `0x1400f3cac`

## pseudocode

```c
int __fastcall CommonUtil::CMpWppTraceBase::Initialize(
        CommonUtil::CMpWppTraceBase *this,
        __int64 a2,
        wchar_t *a3,
        wchar_t **a4,
        unsigned int a5,
        unsigned int a6,
        struct CommonUtil::tagMP_EVENT_TRACE_PROPERTIES *a7)
{
  int Directory; // eax
  const struct std::nothrow_t *v12; // rdx
  const wchar_t *v13; // r8
  signed int v14; // ebx
  int result; // eax
  LPCWSTR *v16; // rbx
  void *v17; // rcx
  const wchar_t *v18; // rsi
  PEVENT_TRACE_PROPERTIES *v19; // r14
  void *v20; // rcx
  unsigned int v21; // r15d
  enum tagMP_FEATURE *v22; // rdx
  int ProductFeatureFromRegistry; // eax
  void *v24; // rcx
  signed int v25; // eax
  __int64 v26; // r9
  signed int started; // eax
  WCHAR *v28; // rbx
  HANDLE FileW; // rax
  __int64 v30; // rdx
  int LastFailure; // eax
  int v32; // r14d
  const struct std::nothrow_t *v33; // rdx
  int v34; // edi
  const wchar_t *dwCreationDisposition; // [rsp+20h] [rbp-78h]
  const struct CommonUtil::tagMP_EVENT_TRACE_PROPERTIES *v36; // [rsp+38h] [rbp-60h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-48h] BYREF

  lpFileName = 0;
  Directory = CommonUtil::UtilCreateDirectoryEx(
                (CommonUtil *)a3,
                (const wchar_t *)0xFFFFFFFFFFFFFFFFLL,
                (unsigned __int64)a3);
  v14 = Directory;
  if ( Directory < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        &WPP_69ab96dea61b39c0c05cd0a3fd1238e8_Traceguids,
        (unsigned int)Directory);
    return v14;
  }
  v16 = (LPCWSTR *)((char *)this + 8);
  v17 = (void *)*((_QWORD *)this + 1);
  if ( v17 )
  {
    operator delete(v17, v12);
    *v16 = 0;
  }
  result = CommonUtil::NewSessionName((CommonUtil::CMpWppTraceBase *)((char *)this + 8), a4, v13);
  if ( result >= 0 )
  {
    v18 = *v16;
    v19 = (PEVENT_TRACE_PROPERTIES *)((char *)this + 16);
    v20 = (void *)*((_QWORD *)this + 2);
    if ( v20 )
    {
      operator delete(v20, (const struct std::nothrow_t *)0x78);
      *v19 = 0;
    }
    v21 = a5;
    LODWORD(dwCreationDisposition) = a5;
    result = CommonUtil::NewTraceProperties(
               (CommonUtil::CMpWppTraceBase *)((char *)this + 16),
               (struct _EVENT_TRACE_PROPERTIES **)a3,
               (const wchar_t *)a4,
               v18,
               dwCreationDisposition,
               a6,
               (int)a7,
               v36);
    if ( result >= 0 )
    {
      ProductFeatureFromRegistry = CommonUtil::GetProductFeatureFromRegistry(
                                     (CommonUtil::CMpWppTraceBase *)((char *)this + 52),
                                     v22);
      if ( ProductFeatureFromRegistry < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            12,
            &WPP_69ab96dea61b39c0c05cd0a3fd1238e8_Traceguids,
            (unsigned int)ProductFeatureFromRegistry);
        *((_DWORD *)this + 13) = 0;
      }
      v24 = (void *)*((_QWORD *)this + 4);
      if ( v24 != (void *)-1LL && v24 )
      {
        CloseHandle(v24);
        *((_QWORD *)this + 4) = 0;
      }
      v25 = ControlTraceW(0, *v16, *v19, 1u);
      v26 = (unsigned int)v25;
      if ( v25 > 0 )
        v26 = (unsigned __int16)v25 | 0x80070000;
      if ( (int)(v26 + 0x80000000) >= 0
        && (_DWORD)v26 != -2147020695
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, &WPP_69ab96dea61b39c0c05cd0a3fd1238e8_Traceguids, v26);
      }
      started = StartTraceW((PTRACEHANDLE)this + 3, *v16, *v19);
      v14 = started;
      if ( started > 0 )
        v14 = (unsigned __int16)started | 0x80070000;
      if ( v14 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_SSd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (__int64)a4, v14);
        return v14;
      }
      CommonUtil::NewSprintfW((CommonUtil *)&lpFileName, (wchar_t **)L"%ls\\%ls", a3, a4);
      v28 = (WCHAR *)lpFileName;
      FileW = CreateFileW(lpFileName, 1u, 3u, 0, 3u, 0x80u, 0);
      *((_QWORD *)this + 4) = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastFailure = HrGetLastFailure();
        v32 = LastFailure;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
        {
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            15,
            (unsigned int)&WPP_69ab96dea61b39c0c05cd0a3fd1238e8_Traceguids,
            (_DWORD)v28,
            LastFailure);
        }
        if ( a7 )
          *((_DWORD *)a7 + 4) = v32;
      }
      *((_QWORD *)this + 5) = a2;
      if ( !a2 )
      {
        *((_QWORD *)this + 5) = -1;
        a2 = -1;
      }
      *((_DWORD *)this + 12) = a5;
      if ( !a5 )
      {
        v21 = 2;
        *((_DWORD *)this + 12) = 2;
      }
      LOBYTE(v30) = 1;
      v34 = CommonUtil::EnableModulesWpp(*((_QWORD *)this + 3), v30, v21, a2, *((_DWORD *)this + 13));
      if ( v34 >= 0 )
      {
        if ( v28 )
          operator delete(v28, v33);
        return 0;
      }
      else
      {
        if ( v28 )
          operator delete(v28, v33);
        return v34;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400f3b24  mov     [rsp+arg_8], rbx
0x1400f3b29  push    rbp
0x1400f3b2a  push    rsi
0x1400f3b2b  push    rdi
0x1400f3b2c  push    r12
0x1400f3b2e  push    r13
0x1400f3b30  push    r14
0x1400f3b32  push    r15
0x1400f3b34  sub     rsp, 60h
0x1400f3b38  mov     rax, cs:__security_cookie
0x1400f3b3f  xor     rax, rsp
0x1400f3b42  mov     [rsp+98h+var_40], rax
0x1400f3b47  mov     r15, [rsp+98h+arg_30]
0x1400f3b4f  mov     r12, rdx
0x1400f3b52  mov     rdi, rcx
0x1400f3b55  mov     [rsp+98h+var_50], r15
0x1400f3b5a  or      rdx, 0FFFFFFFFFFFFFFFFh; wchar_t *
0x1400f3b5e  mov     [rsp+98h+var_58], r8
0x1400f3b63  mov     rcx, r8; this
0x1400f3b66  mov     [rsp+98h+lpFileName], 0
0x1400f3b6f  mov     r13, r9
0x1400f3b72  mov     rbp, r8
0x1400f3b75  call    ?UtilCreateDirectoryEx@CommonUtil@@YAJPEB_W_K@Z; CommonUtil::UtilCreateDirectoryEx(wchar_t const *,unsigned __int64)
0x1400f3b7a  mov     ebx, eax
0x1400f3b7c  test    eax, eax
0x1400f3b7e  jns     short loc_1400F3BB8
0x1400f3b80  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3b87  lea     rsi, WPP_GLOBAL_Control
0x1400f3b8e  cmp     rcx, rsi
0x1400f3b91  jz      short loc_1400F3BB1
0x1400f3b93  test    byte ptr [rcx+1Ch], 1
0x1400f3b97  jz      short loc_1400F3BB1
0x1400f3b99  mov     rcx, [rcx+10h]
0x1400f3b9d  lea     r8, WPP_69ab96dea61b39c0c05cd0a3fd1238e8_Traceguids
0x1400f3ba4  mov     edx, 0Bh
0x1400f3ba9  mov     r9d, eax
0x1400f3bac  call    WPP_SF_d
0x1400f3bb1  mov     eax, ebx
0x1400f3bb3  jmp     loc_1400F3E5C
0x1400f3bb8  lea     rbx, [rdi+8]
0x1400f3bbc  mov     rcx, [rbx]; void *
0x1400f3bbf  test    rcx, rcx
0x1400f3bc2  jz      short loc_1400F3BD0
0x1400f3bc4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f3bc9  mov     qword ptr [rbx], 0
0x1400f3bd0  mov     rdx, r13; wchar_t **
0x1400f3bd3  mov     rcx, rbx; this
0x1400f3bd6  call    ?NewSessionName@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::NewSessionName(wchar_t * *,wchar_t const *)
0x1400f3bdb  test    eax, eax
0x1400f3bdd  js      loc_1400F3E5C
0x1400f3be3  mov     rsi, [rbx]
0x1400f3be6  lea     r14, [rdi+10h]
0x1400f3bea  mov     rcx, [r14]; void *
0x1400f3bed  test    rcx, rcx
0x1400f3bf0  jz      short loc_1400F3C03
0x1400f3bf2  mov     edx, 78h ; 'x'; struct std::nothrow_t *
0x1400f3bf7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f3bfc  mov     qword ptr [r14], 0
0x1400f3c03  mov     eax, [rsp+98h+arg_28]
0x1400f3c0a  mov     r9, rsi; wchar_t *
0x1400f3c0d  mov     [rsp+98h+hTemplateFile], r15; int
0x1400f3c12  mov     r8, r13; wchar_t *
0x1400f3c15  mov     r15d, dword ptr [rsp+98h+arg_20]
0x1400f3c1d  mov     rdx, rbp; struct _EVENT_TRACE_PROPERTIES **
0x1400f3c20  mov     [rsp+98h+dwFlagsAndAttributes], eax; unsigned int
0x1400f3c24  mov     rcx, r14; this
0x1400f3c27  mov     [rsp+98h+dwCreationDisposition], r15d; wchar_t *
0x1400f3c2c  call    ?NewTraceProperties@CommonUtil@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@PEB_W11KHPEBUtagMP_EVENT_TRACE_PROPERTIES@1@@Z; CommonUtil::NewTraceProperties(_EVENT_TRACE_PROPERTIES * *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,int,CommonUtil::tagMP_EVENT_TRACE_PROPERTIES const *)
0x1400f3c31  test    eax, eax
0x1400f3c33  js      loc_1400F3E5C
0x1400f3c39  lea     rcx, [rdi+34h]; this
0x1400f3c3d  call    ?GetProductFeatureFromRegistry@CommonUtil@@YAJPEAW4tagMP_FEATURE@@@Z; CommonUtil::GetProductFeatureFromRegistry(tagMP_FEATURE *)
0x1400f3c42  lea     rsi, WPP_GLOBAL_Control
0x1400f3c49  lea     rbp, WPP_69ab96dea61b39c0c05cd0a3fd1238e8_Traceguids
0x1400f3c50  test    eax, eax
0x1400f3c52  jns     short loc_1400F3C81
0x1400f3c54  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3c5b  cmp     rcx, rsi
0x1400f3c5e  jz      short loc_1400F3C7A
0x1400f3c60  test    byte ptr [rcx+1Ch], 2
0x1400f3c64  jz      short loc_1400F3C7A
0x1400f3c66  mov     rcx, [rcx+10h]
0x1400f3c6a  mov     edx, 0Ch
0x1400f3c6f  mov     r9d, eax
0x1400f3c72  mov     r8, rbp
0x1400f3c75  call    WPP_SF_d
0x1400f3c7a  mov     dword ptr [rdi+34h], 0
0x1400f3c81  mov     rcx, [rdi+20h]; hObject
0x1400f3c85  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400f3c89  jz      short loc_1400F3C9E
0x1400f3c8b  test    rcx, rcx
0x1400f3c8e  jz      short loc_1400F3C9E
0x1400f3c90  call    cs:__imp_CloseHandle
0x1400f3c96  mov     qword ptr [rdi+20h], 0
0x1400f3c9e  mov     r8, [r14]; Properties
0x1400f3ca1  mov     r9d, 1; ControlCode
0x1400f3ca7  mov     rdx, [rbx]; InstanceName
0x1400f3caa  xor     ecx, ecx; TraceHandle
0x1400f3cac  call    cs:__imp_ControlTraceW
0x1400f3cb2  mov     r9d, eax
0x1400f3cb5  test    eax, eax
0x1400f3cb7  jle     short loc_1400F3CC4
0x1400f3cb9  movzx   r9d, ax
0x1400f3cbd  or      r9d, 80070000h
0x1400f3cc4  mov     ecx, 80000000h
0x1400f3cc9  lea     eax, [r9+rcx]
0x1400f3ccd  test    ecx, eax
0x1400f3ccf  jnz     short loc_1400F3CFD
0x1400f3cd1  cmp     r9d, 80071069h
0x1400f3cd8  jz      short loc_1400F3CFD
0x1400f3cda  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3ce1  cmp     rcx, rsi
0x1400f3ce4  jz      short loc_1400F3CFD
0x1400f3ce6  test    byte ptr [rcx+1Ch], 1
0x1400f3cea  jz      short loc_1400F3CFD
0x1400f3cec  mov     rcx, [rcx+10h]
0x1400f3cf0  mov     edx, 0Dh
0x1400f3cf5  mov     r8, rbp
0x1400f3cf8  call    WPP_SF_d
0x1400f3cfd  mov     r8, [r14]; Properties
0x1400f3d00  lea     rcx, [rdi+18h]; TraceHandle
0x1400f3d04  mov     rdx, [rbx]; InstanceName
0x1400f3d07  call    cs:__imp_StartTraceW
0x1400f3d0d  mov     ebx, eax
0x1400f3d0f  test    eax, eax
0x1400f3d11  jle     short loc_1400F3D1C
0x1400f3d13  movzx   ebx, ax
0x1400f3d16  or      ebx, 80070000h
0x1400f3d1c  test    ebx, ebx
0x1400f3d1e  jns     short loc_1400F3D5E
0x1400f3d20  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3d27  cmp     rcx, rsi
0x1400f3d2a  jz      loc_1400F3BB1
0x1400f3d30  test    byte ptr [rcx+1Ch], 1
0x1400f3d34  jz      loc_1400F3BB1
0x1400f3d3a  mov     r9, [rsp+98h+var_58]
0x1400f3d3f  mov     edx, 0Eh
0x1400f3d44  mov     rcx, [rcx+10h]; LoggerHandle
0x1400f3d48  mov     r8, rbp
0x1400f3d4b  mov     [rsp+98h+dwFlagsAndAttributes], ebx; char
0x1400f3d4f  mov     qword ptr [rsp+98h+dwCreationDisposition], r13; __int64
0x1400f3d54  call    WPP_SF_SSd
0x1400f3d59  jmp     loc_1400F3BB1
0x1400f3d5e  mov     r8, [rsp+98h+var_58]; wchar_t *
0x1400f3d63  lea     rdx, aLsLs; "%ls\\%ls"
0x1400f3d6a  mov     r9, r13
0x1400f3d6d  lea     rcx, [rsp+98h+lpFileName]; this
0x1400f3d72  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x1400f3d77  mov     rbx, [rsp+98h+lpFileName]
0x1400f3d7c  mov     r8d, 3; dwShareMode
0x1400f3d82  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x1400f3d8b  xor     r9d, r9d; lpSecurityAttributes
0x1400f3d8e  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400f3d96  mov     rcx, rbx; lpFileName
0x1400f3d99  mov     [rsp+98h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400f3d9e  lea     edx, [r8-2]; dwDesiredAccess
0x1400f3da2  call    cs:__imp_CreateFileW
0x1400f3da8  mov     [rdi+20h], rax
0x1400f3dac  inc     rax
0x1400f3daf  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400f3db5  jnz     short loc_1400F3DF7
0x1400f3db7  call    HrGetLastFailure
0x1400f3dbc  mov     r14d, eax
0x1400f3dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3dc6  cmp     rcx, rsi
0x1400f3dc9  jz      short loc_1400F3DE9
0x1400f3dcb  test    byte ptr [rcx+1Ch], 10h
0x1400f3dcf  jz      short loc_1400F3DE9
0x1400f3dd1  mov     rcx, [rcx+10h]
0x1400f3dd5  mov     edx, 0Fh
0x1400f3dda  mov     r9, rbx
0x1400f3ddd  mov     [rsp+98h+dwCreationDisposition], eax
0x1400f3de1  mov     r8, rbp
0x1400f3de4  call    WPP_SF_Sd
0x1400f3de9  mov     rax, [rsp+98h+var_50]
0x1400f3dee  test    rax, rax
0x1400f3df1  jz      short loc_1400F3DF7
0x1400f3df3  mov     [rax+10h], r14d
0x1400f3df7  mov     [rdi+28h], r12
0x1400f3dfb  test    r12, r12
0x1400f3dfe  jnz     short loc_1400F3E0B
0x1400f3e00  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400f3e04  mov     [rdi+28h], rax
0x1400f3e08  mov     r12, rax
0x1400f3e0b  mov     [rdi+30h], r15d
0x1400f3e0f  test    r15d, r15d
0x1400f3e12  jnz     short loc_1400F3E1E
0x1400f3e14  mov     r15d, 2
0x1400f3e1a  mov     [rdi+30h], r15d
0x1400f3e1e  mov     eax, [rdi+34h]
0x1400f3e21  mov     r9, r12
0x1400f3e24  mov     rcx, [rdi+18h]
0x1400f3e28  mov     r8d, r15d
0x1400f3e2b  mov     dl, 1
0x1400f3e2d  mov     [rsp+98h+dwCreationDisposition], eax
0x1400f3e31  call    ?EnableModulesWpp@CommonUtil@@YAJ_K_NK0W4tagMP_FEATURE@@@Z; CommonUtil::EnableModulesWpp(unsigned __int64,bool,ulong,unsigned __int64,tagMP_FEATURE)
0x1400f3e36  mov     edi, eax
0x1400f3e38  test    eax, eax
0x1400f3e3a  jns     short loc_1400F3E4D
0x1400f3e3c  test    rbx, rbx
0x1400f3e3f  jz      short loc_1400F3E49
0x1400f3e41  mov     rcx, rbx; void *
0x1400f3e44  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f3e49  mov     eax, edi
0x1400f3e4b  jmp     short loc_1400F3E5C
0x1400f3e4d  test    rbx, rbx
0x1400f3e50  jz      short loc_1400F3E5A
0x1400f3e52  mov     rcx, rbx; void *
0x1400f3e55  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f3e5a  xor     eax, eax
0x1400f3e5c  mov     rcx, [rsp+98h+var_40]
0x1400f3e61  xor     rcx, rsp; StackCookie
0x1400f3e64  call    __security_check_cookie
0x1400f3e69  mov     rbx, [rsp+98h+arg_8]
0x1400f3e71  add     rsp, 60h
0x1400f3e75  pop     r15
0x1400f3e77  pop     r14
0x1400f3e79  pop     r13
0x1400f3e7b  pop     r12
0x1400f3e7d  pop     rdi
0x1400f3e7e  pop     rsi
0x1400f3e7f  pop     rbp
0x1400f3e80  retn
```
