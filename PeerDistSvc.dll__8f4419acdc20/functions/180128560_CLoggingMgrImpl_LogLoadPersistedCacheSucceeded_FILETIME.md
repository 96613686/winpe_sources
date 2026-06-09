# CLoggingMgrImpl::LogLoadPersistedCacheSucceeded(_FILETIME)

- ea: `0x180128560`
- end: `0x180128725`
- name: `?LogLoadPersistedCacheSucceeded@CLoggingMgrImpl@@UEAAJU_FILETIME@@@Z`
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
- `0x180128560`
- `0x18012b4d0`
- `0x1801448c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1801286a3`
- `ntdll!EtwEventWrite` at `0x1801286a3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801285d6`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801285d6`

## pseudocode

```c
__int64 __fastcall CLoggingMgrImpl::LogLoadPersistedCacheSucceeded(CLoggingMgrImpl *this, FILETIME a2)
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
  if ( !CLoggingMgrImpl::PreEventLog(this, 0x19u, 0) )
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 101, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 102, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
  }
  v6 = EtwEventWrite(*((_QWORD *)this + 1), LoadPersistedCacheSucceededEvent, 1, v4);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 103, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids, v6);
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
0x180128560  mov     [rsp+arg_10], rbx
0x180128565  push    rbp
0x180128566  push    rdi
0x180128567  push    r14
0x180128569  sub     rsp, 60h
0x18012856d  mov     rax, cs:__security_cookie
0x180128574  xor     rax, rsp
0x180128577  mov     [rsp+78h+var_28], rax
0x18012857c  mov     qword ptr [rsp+78h+FileTime.dwLowDateTime], rdx
0x180128581  mov     rdi, rcx
0x180128584  lea     rdx, [rcx+28h]; struct CritSec *
0x180128588  xorps   xmm0, xmm0
0x18012858b  lea     rcx, [rsp+78h+var_50]; this
0x180128590  mov     r8b, 1; bool
0x180128593  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x180128598  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18012859d  xor     edx, edx; bool
0x18012859f  mov     rcx, rdi; this
0x1801285a2  call    ?IsObjectStarted@CLoggingMgrImpl@@AEAA_N_N@Z; CLoggingMgrImpl::IsObjectStarted(bool)
0x1801285a7  test    al, al
0x1801285a9  jnz     short loc_1801285B5
0x1801285ab  mov     ebx, 80070FD6h
0x1801285b0  jmp     loc_180128637
0x1801285b5  xor     r8d, r8d; bool
0x1801285b8  mov     rcx, rdi; this
0x1801285bb  lea     edx, [r8+19h]; unsigned int
0x1801285bf  call    ?PreEventLog@CLoggingMgrImpl@@AEAA_NK_N@Z; CLoggingMgrImpl::PreEventLog(ulong,bool)
0x1801285c4  test    al, al
0x1801285c6  jnz     short loc_1801285CC
0x1801285c8  xor     ebx, ebx
0x1801285ca  jmp     short loc_180128637
0x1801285cc  lea     rdx, [rsp+78h+SystemTime]; lpSystemTime
0x1801285d1  lea     rcx, [rsp+78h+FileTime]; lpFileTime
0x1801285d6  call    cs:__imp_FileTimeToSystemTime
0x1801285dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801285e3  mov     ecx, 10h; unsigned __int64
0x1801285e8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801285ed  xor     ecx, ecx; Block
0x1801285ef  mov     r14, rax
0x1801285f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801285f7  test    r14, r14
0x1801285fa  jnz     short loc_180128648
0x1801285fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180128603  lea     rbp, WPP_GLOBAL_Control
0x18012860a  cmp     rcx, rbp
0x18012860d  jz      short loc_180128632
0x18012860f  test    dword ptr [rcx+6Ch], 2000h
0x180128616  jz      short loc_180128632
0x180128618  cmp     byte ptr [rcx+69h], 1
0x18012861c  jb      short loc_180128632
0x18012861e  mov     rcx, [rcx+60h]
0x180128622  lea     edx, [r14+65h]
0x180128626  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012862d  call    WPP_SF_
0x180128632  mov     ebx, 8007000Eh
0x180128637  lea     rcx, [rsp+78h+var_50]; this
0x18012863c  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180128641  xor     ecx, ecx
0x180128643  jmp     loc_180128700
0x180128648  lea     rax, [rsp+78h+SystemTime]
0x18012864d  mov     qword ptr [r14+8], 10h
0x180128655  mov     [r14], rax
0x180128658  xor     ebx, ebx
0x18012865a  mov     rcx, cs:WPP_GLOBAL_Control
0x180128661  lea     rbp, WPP_GLOBAL_Control
0x180128668  cmp     rcx, rbp
0x18012866b  jz      short loc_18012868F
0x18012866d  test    dword ptr [rcx+6Ch], 2000h
0x180128674  jz      short loc_18012868F
0x180128676  cmp     byte ptr [rcx+69h], 4
0x18012867a  jb      short loc_18012868F
0x18012867c  mov     rcx, [rcx+60h]
0x180128680  lea     edx, [rbx+66h]
0x180128683  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012868a  call    WPP_SF_
0x18012868f  mov     rcx, [rdi+8]
0x180128693  lea     rdx, LoadPersistedCacheSucceededEvent
0x18012869a  mov     r9, r14
0x18012869d  mov     r8d, 1
0x1801286a3  call    cs:__imp_EtwEventWrite
0x1801286a9  mov     edi, eax
0x1801286ab  test    eax, eax
0x1801286ad  jz      short loc_1801286F3
0x1801286af  mov     rcx, cs:WPP_GLOBAL_Control
0x1801286b6  cmp     rcx, rbp
0x1801286b9  jz      short loc_1801286E2
0x1801286bb  test    dword ptr [rcx+6Ch], 2000h
0x1801286c2  jz      short loc_1801286E2
0x1801286c4  cmp     byte ptr [rcx+69h], 1
0x1801286c8  jb      short loc_1801286E2
0x1801286ca  mov     rcx, [rcx+60h]
0x1801286ce  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x1801286d5  mov     edx, 67h ; 'g'
0x1801286da  mov     r9d, eax
0x1801286dd  call    WPP_SF_d
0x1801286e2  test    edi, edi
0x1801286e4  jg      short loc_1801286EA
0x1801286e6  mov     ebx, edi
0x1801286e8  jmp     short loc_1801286F3
0x1801286ea  movzx   ebx, di
0x1801286ed  or      ebx, 80070000h
0x1801286f3  lea     rcx, [rsp+78h+var_50]; this
0x1801286f8  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1801286fd  mov     rcx, r14; Block
0x180128700  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180128705  mov     eax, ebx
0x180128707  mov     rcx, [rsp+78h+var_28]
0x18012870c  xor     rcx, rsp; StackCookie
0x18012870f  call    __security_check_cookie
0x180128714  mov     rbx, [rsp+78h+arg_10]
0x18012871c  add     rsp, 60h
0x180128720  pop     r14
0x180128722  pop     rdi
0x180128723  pop     rbp
0x180128724  retn
```
