# CCbsTiSession::GetProperty(_CbsSessionProperty,wchar_t * *)

- ea: `0x14000fe34`
- end: `0x14000ff8d`
- name: `?GetProperty@CCbsTiSession@@UEAAJW4_CbsSessionProperty@@PEAPEA_W@Z`
- size: `345`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000fe20`

## callees

- `0x1400023e0`
- `0x140006778`
- `0x14000e2ac`
- `0x14000fe34`
- `0x1400106c4`
- `0x140017658`
- `0x14001ddb8`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x14000febe`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x14000febe`

## string_xrefs

- `0x14000feca`: `Failed to get task allocator for Trusted Installer.`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::GetProperty(__int64 a1, unsigned int a2, __int64 a3)
{
  CCbsTiSession *v3; // rbx
  unsigned int v7; // ebx
  __int64 v8; // rax
  int Malloc; // eax
  const char *v10; // r9
  __int64 v11; // rax
  _BYTE v13[24]; // [rsp+20h] [rbp-58h] BYREF
  LPMALLOC ppMalloc; // [rsp+38h] [rbp-40h] BYREF

  v3 = (CCbsTiSession *)(a1 - 256);
  ppMalloc = 0;
  CritSecLocker::CritSecLocker((CritSecLocker *)v13, (struct AutoCritSec *)(a1 - 256 + 48), 1);
  if ( !a3 )
  {
    v7 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: pValue.");
    goto LABEL_18;
  }
  if ( *(_QWORD *)(a1 - 216) )
  {
    if ( a2 == 1 )
    {
      v11 = *(_QWORD *)(a1 - 168);
      if ( v11 )
      {
        if ( *(_DWORD *)(v11 + 48) == -2145116147 )
          goto LABEL_7;
      }
    }
  }
  else
  {
    if ( a2 == 1 )
    {
      v8 = *(_QWORD *)(a1 - 168);
      if ( v8 )
      {
        if ( *(_DWORD *)(v8 + 68) )
        {
LABEL_7:
          Malloc = CoGetMalloc(1u, &ppMalloc);
          v7 = Malloc;
          if ( Malloc >= 0 )
          {
            v7 = SczPublicAllocFromSz(a3, ppMalloc, L"0");
            goto LABEL_18;
          }
          v10 = "Failed to get task allocator for Trusted Installer.";
          goto LABEL_17;
        }
      }
    }
    Malloc = CCbsTiSession::MakeSureWorkerSessionAvailable(v3, 1);
    v7 = Malloc;
    if ( Malloc < 0 )
    {
      v10 = "Failed to get worker session.";
      goto LABEL_17;
    }
  }
  Malloc = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 - 216) + 96LL))(
             *(_QWORD *)(a1 - 216),
             a2,
             a3);
  v7 = Malloc;
  if ( Malloc >= 0 )
    goto LABEL_18;
  v10 = "Failed to GetProperty using worker session";
LABEL_17:
  CBSWdsLogLight(0x4000000u, (unsigned int)Malloc, (size_t *)1, v10);
LABEL_18:
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  CritSecLocker::~CritSecLocker((CritSecLocker *)v13);
  return v7;
}

```

## disassembly

```asm
0x14000fe34  push    rbx
0x14000fe36  push    rbp
0x14000fe37  push    rsi
0x14000fe38  push    rdi
0x14000fe39  push    r14
0x14000fe3b  sub     rsp, 50h
0x14000fe3f  mov     rax, cs:__security_cookie
0x14000fe46  xor     rax, rsp
0x14000fe49  mov     [rsp+78h+var_38], rax
0x14000fe4e  lea     rbx, [rcx-100h]
0x14000fe55  mov     [rsp+78h+ppMalloc], 0
0x14000fe5e  mov     rbp, r8
0x14000fe61  mov     esi, edx
0x14000fe63  mov     rdi, rcx
0x14000fe66  lea     rdx, [rbx+30h]; struct AutoCritSec *
0x14000fe6a  mov     r14d, 1
0x14000fe70  lea     rcx, [rsp+78h+var_58]; this
0x14000fe75  mov     r8b, r14b; bool
0x14000fe78  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14000fe7d  test    rbp, rbp
0x14000fe80  jnz     short loc_14000FE95
0x14000fe82  mov     ebx, 80004003h
0x14000fe87  lea     r9, aInvalidArgumen_25; "Invalid argument: pValue."
0x14000fe8e  mov     edx, ebx
0x14000fe90  jmp     loc_14000FF46
0x14000fe95  cmp     qword ptr [rdi-0D8h], 0
0x14000fe9d  jnz     short loc_14000FF05
0x14000fe9f  cmp     esi, r14d
0x14000fea2  jnz     short loc_14000FEEB
0x14000fea4  mov     rax, [rdi-0A8h]
0x14000feab  test    rax, rax
0x14000feae  jz      short loc_14000FEEB
0x14000feb0  cmp     dword ptr [rax+44h], 0
0x14000feb4  jz      short loc_14000FEEB
0x14000feb6  lea     rdx, [rsp+78h+ppMalloc]; ppMalloc
0x14000febb  mov     ecx, r14d; dwMemContext
0x14000febe  call    cs:__imp_CoGetMalloc
0x14000fec4  mov     ebx, eax
0x14000fec6  test    eax, eax
0x14000fec8  jns     short loc_14000FED3
0x14000feca  lea     r9, aFailedToGetTas; "Failed to get task allocator for Truste"...
0x14000fed1  jmp     short loc_14000FF44
0x14000fed3  mov     rdx, [rsp+78h+ppMalloc]
0x14000fed8  lea     r8, a0_0; "0"
0x14000fedf  mov     rcx, rbp
0x14000fee2  call    SczPublicAllocFromSz
0x14000fee7  mov     ebx, eax
0x14000fee9  jmp     short loc_14000FF53
0x14000feeb  mov     dl, r14b; bool
0x14000feee  mov     rcx, rbx; this
0x14000fef1  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x14000fef6  mov     ebx, eax
0x14000fef8  test    eax, eax
0x14000fefa  jns     short loc_14000FF1F
0x14000fefc  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x14000ff03  jmp     short loc_14000FF44
0x14000ff05  cmp     esi, r14d
0x14000ff08  jnz     short loc_14000FF1F
0x14000ff0a  mov     rax, [rdi-0A8h]
0x14000ff11  test    rax, rax
0x14000ff14  jz      short loc_14000FF1F
0x14000ff16  cmp     dword ptr [rax+30h], 8024200Dh
0x14000ff1d  jz      short loc_14000FEB6
0x14000ff1f  mov     rcx, [rdi-0D8h]
0x14000ff26  mov     r8, rbp
0x14000ff29  mov     edx, esi
0x14000ff2b  mov     rax, [rcx]
0x14000ff2e  mov     rax, [rax+60h]
0x14000ff32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff37  mov     ebx, eax
0x14000ff39  test    eax, eax
0x14000ff3b  jns     short loc_14000FF53
0x14000ff3d  lea     r9, aFailedToGetpro; "Failed to GetProperty using worker sess"...
0x14000ff44  mov     edx, eax
0x14000ff46  mov     r8d, r14d
0x14000ff49  mov     ecx, 4000000h
0x14000ff4e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ff53  mov     rcx, [rsp+78h+ppMalloc]
0x14000ff58  test    rcx, rcx
0x14000ff5b  jz      short loc_14000FF69
0x14000ff5d  mov     rax, [rcx]
0x14000ff60  mov     rax, [rax+10h]
0x14000ff64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff69  lea     rcx, [rsp+78h+var_58]; this
0x14000ff6e  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14000ff73  mov     eax, ebx
0x14000ff75  mov     rcx, [rsp+78h+var_38]
0x14000ff7a  xor     rcx, rsp; StackCookie
0x14000ff7d  call    __security_check_cookie
0x14000ff82  add     rsp, 50h
0x14000ff86  pop     r14
0x14000ff88  pop     rdi
0x14000ff89  pop     rsi
0x14000ff8a  pop     rbp
0x14000ff8b  pop     rbx
0x14000ff8c  retn
```
