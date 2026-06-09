# CLoggingMgrImpl::LogSavePersistedCacheSucceeded(_FILETIME)

- ea: `0x180129c90`
- end: `0x180129e55`
- name: `?LogSavePersistedCacheSucceeded@CLoggingMgrImpl@@UEAAJU_FILETIME@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(CLoggingMgrImpl *__hidden this, struct _FILETIME)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x180126710`
- `0x180129c90`
- `0x18012b4d0`
- `0x1801448c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180129dd3`
- `ntdll!EtwEventWrite` at `0x180129dd3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180129d06`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180129d06`

## pseudocode

```c
__int64 __fastcall CLoggingMgrImpl::LogSavePersistedCacheSucceeded(CLoggingMgrImpl *this, FILETIME a2)
{
  unsigned int v3; // ebx
  struct _SYSTEMTIME **v4; // r14
  struct _SYSTEMTIME **v5; // rcx
  unsigned int v6; // eax
  int v7; // edi
  FILETIME FileTime; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v10[24]; // [rsp+28h] [rbp-50h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-38h] BYREF

  FileTime = a2;
  SystemTime = 0;
  InCritSec::InCritSec((InCritSec *)v10, (CLoggingMgrImpl *)((char *)this + 40), 1);
  if ( !CLoggingMgrImpl::IsObjectStarted(this, 0) )
  {
    v3 = -2147020842;
LABEL_11:
    InCritSec::~InCritSec((InCritSec *)v10);
    v5 = 0;
    goto LABEL_25;
  }
  if ( !CLoggingMgrImpl::PreEventLog(this, 0x1Au, 0) )
  {
    v3 = 0;
    goto LABEL_11;
  }
  FileTimeToSystemTime(&FileTime, &SystemTime);
  v4 = (struct _SYSTEMTIME **)operator new[](0x10u, (const struct std::nothrow_t *)std::nothrow);
  operator delete(0);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 104, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
    }
    v3 = -2147024882;
    goto LABEL_11;
  }
  v4[1] = (struct _SYSTEMTIME *)16;
  *v4 = &SystemTime;
  v3 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 105, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
  }
  v6 = EtwEventWrite(*((_QWORD *)this + 1), SavePersistedCacheSucceededEvent, 1, v4);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 106, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids, v6);
    }
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    else
      v3 = v7;
  }
  InCritSec::~InCritSec((InCritSec *)v10);
  v5 = v4;
LABEL_25:
  operator delete(v5);
  return v3;
}

```

## disassembly

```asm
0x180129c90  mov     [rsp+arg_10], rbx
0x180129c95  push    rbp
0x180129c96  push    rdi
0x180129c97  push    r14
0x180129c99  sub     rsp, 60h
0x180129c9d  mov     rax, cs:__security_cookie
0x180129ca4  xor     rax, rsp
0x180129ca7  mov     [rsp+78h+var_28], rax
0x180129cac  mov     qword ptr [rsp+78h+FileTime.dwLowDateTime], rdx
0x180129cb1  mov     rdi, rcx
0x180129cb4  lea     rdx, [rcx+28h]; struct CritSec *
0x180129cb8  xorps   xmm0, xmm0
0x180129cbb  lea     rcx, [rsp+78h+var_50]; this
0x180129cc0  mov     r8b, 1; bool
0x180129cc3  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x180129cc8  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180129ccd  xor     edx, edx; bool
0x180129ccf  mov     rcx, rdi; this
0x180129cd2  call    ?IsObjectStarted@CLoggingMgrImpl@@AEAA_N_N@Z; CLoggingMgrImpl::IsObjectStarted(bool)
0x180129cd7  test    al, al
0x180129cd9  jnz     short loc_180129CE5
0x180129cdb  mov     ebx, 80070FD6h
0x180129ce0  jmp     loc_180129D67
0x180129ce5  xor     r8d, r8d; bool
0x180129ce8  mov     rcx, rdi; this
0x180129ceb  lea     edx, [r8+1Ah]; unsigned int
0x180129cef  call    ?PreEventLog@CLoggingMgrImpl@@AEAA_NK_N@Z; CLoggingMgrImpl::PreEventLog(ulong,bool)
0x180129cf4  test    al, al
0x180129cf6  jnz     short loc_180129CFC
0x180129cf8  xor     ebx, ebx
0x180129cfa  jmp     short loc_180129D67
0x180129cfc  lea     rdx, [rsp+78h+SystemTime]; lpSystemTime
0x180129d01  lea     rcx, [rsp+78h+FileTime]; lpFileTime
0x180129d06  call    cs:__imp_FileTimeToSystemTime
0x180129d0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180129d13  mov     ecx, 10h; unsigned __int64
0x180129d18  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180129d1d  xor     ecx, ecx; Block
0x180129d1f  mov     r14, rax
0x180129d22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180129d27  test    r14, r14
0x180129d2a  jnz     short loc_180129D78
0x180129d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180129d33  lea     rbp, WPP_GLOBAL_Control
0x180129d3a  cmp     rcx, rbp
0x180129d3d  jz      short loc_180129D62
0x180129d3f  test    dword ptr [rcx+6Ch], 2000h
0x180129d46  jz      short loc_180129D62
0x180129d48  cmp     byte ptr [rcx+69h], 1
0x180129d4c  jb      short loc_180129D62
0x180129d4e  mov     rcx, [rcx+60h]
0x180129d52  lea     edx, [r14+68h]
0x180129d56  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x180129d5d  call    WPP_SF_
0x180129d62  mov     ebx, 8007000Eh
0x180129d67  lea     rcx, [rsp+78h+var_50]; this
0x180129d6c  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180129d71  xor     ecx, ecx
0x180129d73  jmp     loc_180129E30
0x180129d78  lea     rax, [rsp+78h+SystemTime]
0x180129d7d  mov     qword ptr [r14+8], 10h
0x180129d85  mov     [r14], rax
0x180129d88  xor     ebx, ebx
0x180129d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180129d91  lea     rbp, WPP_GLOBAL_Control
0x180129d98  cmp     rcx, rbp
0x180129d9b  jz      short loc_180129DBF
0x180129d9d  test    dword ptr [rcx+6Ch], 2000h
0x180129da4  jz      short loc_180129DBF
0x180129da6  cmp     byte ptr [rcx+69h], 4
0x180129daa  jb      short loc_180129DBF
0x180129dac  mov     rcx, [rcx+60h]
0x180129db0  lea     edx, [rbx+69h]
0x180129db3  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x180129dba  call    WPP_SF_
0x180129dbf  mov     rcx, [rdi+8]
0x180129dc3  lea     rdx, SavePersistedCacheSucceededEvent
0x180129dca  mov     r9, r14
0x180129dcd  mov     r8d, 1
0x180129dd3  call    cs:__imp_EtwEventWrite
0x180129dd9  mov     edi, eax
0x180129ddb  test    eax, eax
0x180129ddd  jz      short loc_180129E23
0x180129ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x180129de6  cmp     rcx, rbp
0x180129de9  jz      short loc_180129E12
0x180129deb  test    dword ptr [rcx+6Ch], 2000h
0x180129df2  jz      short loc_180129E12
0x180129df4  cmp     byte ptr [rcx+69h], 1
0x180129df8  jb      short loc_180129E12
0x180129dfa  mov     rcx, [rcx+60h]
0x180129dfe  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x180129e05  mov     edx, 6Ah ; 'j'
0x180129e0a  mov     r9d, eax
0x180129e0d  call    WPP_SF_d
0x180129e12  test    edi, edi
0x180129e14  jg      short loc_180129E1A
0x180129e16  mov     ebx, edi
0x180129e18  jmp     short loc_180129E23
0x180129e1a  movzx   ebx, di
0x180129e1d  or      ebx, 80070000h
0x180129e23  lea     rcx, [rsp+78h+var_50]; this
0x180129e28  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180129e2d  mov     rcx, r14; Block
0x180129e30  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180129e35  mov     eax, ebx
0x180129e37  mov     rcx, [rsp+78h+var_28]
0x180129e3c  xor     rcx, rsp; StackCookie
0x180129e3f  call    __security_check_cookie
0x180129e44  mov     rbx, [rsp+78h+arg_10]
0x180129e4c  add     rsp, 60h
0x180129e50  pop     r14
0x180129e52  pop     rdi
0x180129e53  pop     rbp
0x180129e54  retn
```
