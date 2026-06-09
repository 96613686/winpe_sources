# CCbsTiSession::GetSessionId(wchar_t * *)

- ea: `0x14000ffb4`
- end: `0x1400100d9`
- name: `?GetSessionId@CCbsTiSession@@UEAAJPEAPEA_W@Z`
- size: `293`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000ffa0`

## callees

- `0x1400023e0`
- `0x140006778`
- `0x14000e2ac`
- `0x14000ffb4`
- `0x1400106c4`
- `0x140017658`
- `0x14001ddb8`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x140010021`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x140010021`

## string_xrefs

- `0x14001002d`: `Failed to get task allocator for Trusted Installer.`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::GetSessionId(CCbsTiSession *this, wchar_t **a2)
{
  CCbsTiSession *v2; // rbx
  unsigned int v5; // ebx
  int Malloc; // eax
  const char *v7; // r9
  _BYTE v9[24]; // [rsp+20h] [rbp-48h] BYREF
  LPMALLOC ppMalloc; // [rsp+38h] [rbp-30h] BYREF

  v2 = (CCbsTiSession *)((char *)this - 256);
  ppMalloc = 0;
  CritSecLocker::CritSecLocker((CritSecLocker *)v9, (CCbsTiSession *)((char *)this - 208), 1);
  if ( !a2 )
  {
    v5 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: pszIdentity.");
    goto LABEL_12;
  }
  if ( *((_QWORD *)this - 19) )
  {
    Malloc = CoGetMalloc(1u, &ppMalloc);
    v5 = Malloc;
    if ( Malloc >= 0 )
    {
      v5 = SczPublicAllocFromSz(a2, ppMalloc, *((_QWORD *)this - 19));
      goto LABEL_12;
    }
    v7 = "Failed to get task allocator for Trusted Installer.";
  }
  else
  {
    Malloc = CCbsTiSession::MakeSureWorkerSessionAvailable(v2, 1);
    v5 = Malloc;
    if ( Malloc >= 0 )
    {
      Malloc = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(**((_QWORD **)this - 27) + 88LL))(
                 *((_QWORD *)this - 27),
                 a2);
      v5 = Malloc;
      if ( Malloc >= 0 )
        goto LABEL_12;
      v7 = "Failed to GetSessionId using worker session";
    }
    else
    {
      v7 = "Failed to get worker session.";
    }
  }
  CBSWdsLogLight(0x4000000u, (unsigned int)Malloc, (size_t *)1, v7);
LABEL_12:
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  CritSecLocker::~CritSecLocker((CritSecLocker *)v9);
  return v5;
}

```

## disassembly

```asm
0x14000ffb4  mov     [rsp+arg_10], rbx
0x14000ffb9  push    rbp
0x14000ffba  push    rsi
0x14000ffbb  push    rdi
0x14000ffbc  sub     rsp, 50h
0x14000ffc0  mov     rax, cs:__security_cookie
0x14000ffc7  xor     rax, rsp
0x14000ffca  mov     [rsp+68h+var_28], rax
0x14000ffcf  lea     rbx, [rcx-100h]
0x14000ffd6  mov     [rsp+68h+ppMalloc], 0
0x14000ffdf  mov     rsi, rdx
0x14000ffe2  mov     rdi, rcx
0x14000ffe5  mov     ebp, 1
0x14000ffea  lea     rdx, [rbx+30h]; struct AutoCritSec *
0x14000ffee  mov     r8b, bpl; bool
0x14000fff1  lea     rcx, [rsp+68h+var_48]; this
0x14000fff6  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14000fffb  test    rsi, rsi
0x14000fffe  jnz     short loc_140010010
0x140010000  mov     ebx, 80004003h
0x140010005  lea     r9, aInvalidArgumen_2; "Invalid argument: pszIdentity."
0x14001000c  mov     edx, ebx
0x14001000e  jmp     short loc_14001008D
0x140010010  cmp     qword ptr [rdi-98h], 0
0x140010018  jz      short loc_14001004E
0x14001001a  lea     rdx, [rsp+68h+ppMalloc]; ppMalloc
0x14001001f  mov     ecx, ebp; dwMemContext
0x140010021  call    cs:__imp_CoGetMalloc
0x140010027  mov     ebx, eax
0x140010029  test    eax, eax
0x14001002b  jns     short loc_140010036
0x14001002d  lea     r9, aFailedToGetTas; "Failed to get task allocator for Truste"...
0x140010034  jmp     short loc_14001008B
0x140010036  mov     r8, [rdi-98h]
0x14001003d  mov     rcx, rsi
0x140010040  mov     rdx, [rsp+68h+ppMalloc]
0x140010045  call    SczPublicAllocFromSz
0x14001004a  mov     ebx, eax
0x14001004c  jmp     short loc_14001009A
0x14001004e  mov     dl, bpl; bool
0x140010051  mov     rcx, rbx; this
0x140010054  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x140010059  mov     ebx, eax
0x14001005b  test    eax, eax
0x14001005d  jns     short loc_140010068
0x14001005f  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x140010066  jmp     short loc_14001008B
0x140010068  mov     rcx, [rdi-0D8h]
0x14001006f  mov     rdx, rsi
0x140010072  mov     rax, [rcx]
0x140010075  mov     rax, [rax+58h]
0x140010079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001007e  mov     ebx, eax
0x140010080  test    eax, eax
0x140010082  jns     short loc_14001009A
0x140010084  lea     r9, aFailedToGetses; "Failed to GetSessionId using worker ses"...
0x14001008b  mov     edx, eax
0x14001008d  mov     r8d, ebp
0x140010090  mov     ecx, 4000000h
0x140010095  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001009a  mov     rcx, [rsp+68h+ppMalloc]
0x14001009f  test    rcx, rcx
0x1400100a2  jz      short loc_1400100B0
0x1400100a4  mov     rax, [rcx]
0x1400100a7  mov     rax, [rax+10h]
0x1400100ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400100b0  lea     rcx, [rsp+68h+var_48]; this
0x1400100b5  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1400100ba  mov     eax, ebx
0x1400100bc  mov     rcx, [rsp+68h+var_28]
0x1400100c1  xor     rcx, rsp; StackCookie
0x1400100c4  call    __security_check_cookie
0x1400100c9  mov     rbx, [rsp+68h+arg_10]
0x1400100d1  add     rsp, 50h
0x1400100d5  pop     rdi
0x1400100d6  pop     rsi
0x1400100d7  pop     rbp
0x1400100d8  retn
```
