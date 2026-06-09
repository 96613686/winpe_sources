# CTnoCfgMgr::StaticWorkerThreadProc(void *)

- ea: `0x180027070`
- end: `0x180027211`
- name: `?StaticWorkerThreadProc@CTnoCfgMgr@@CAKPEAX@Z`
- size: `417`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004374`
- `0x180008290`
- `0x180020058`
- `0x180025d4c`
- `0x180027070`
- `0x180027bfc`
- `0x180159010`

## import_xrefs

- `ole32!CoUninitialize` at `0x180027200`
- `ole32!CoUninitialize` at `0x180027200`
- `ole32!CoCreateInstance` at `0x18002712a`
- `ole32!CoCreateInstance` at `0x18002712a`
- `ole32!CoInitializeEx` at `0x1800270a8`
- `ole32!CoInitializeEx` at `0x1800270a8`

## string_xrefs

- `0x180027174`: `Failed to get dedup interface in static thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTnoCfgMgr::StaticWorkerThreadProc(char *Parameter)
{
  HRESULT v2; // eax
  int v3; // ebx
  HRESULT v4; // eax
  int v5; // ebx
  LPVOID v6; // rbx
  SystemError *v8; // rbx
  int v9; // eax
  unsigned int v10; // eax
  SystemError *v11; // [rsp+30h] [rbp-28h] BYREF
  Exception *v12; // [rsp+38h] [rbp-20h] BYREF
  char v14; // [rsp+68h] [rbp+10h]
  LPVOID ppv; // [rsp+70h] [rbp+18h] BYREF
  LPVOID v16; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    v14 = 0;
    v16 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)Parameter + 6) + 40LL))(Parameter + 48) )
    {
      v2 = CoInitializeEx(0, 0);
      v3 = v2;
      if ( v2 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              52,
              WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
              (unsigned int)v2);
        }
        ApplicationError::Throw(L"CoInitializeEx failed ", v3);
      }
      v14 = 1;
      ppv = 0;
      v4 = CoCreateInstance(&CLSID_DedupChunkLibrary, 0, 1u, &IID_IDedupChunkLibrary, &ppv);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            53,
            WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
            (unsigned int)v4);
        }
        ApplicationError::Throw(L"Failed to get dedup interface in static thread", v5);
      }
      v6 = ppv;
      CAutoComObject<INetFwRule>::Release(&v16);
      v16 = v6;
    }
    if ( Parameter )
    {
      LODWORD(ppv) = CTnoCfgMgr::WorkerThreadProc((CTnoCfgMgr *)Parameter);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 54, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
      }
      LODWORD(ppv) = 774;
    }
    CAutoComObject<INetFwRule>::Release(&v16);
  }
  catch ( SystemError *v11 )
  {
    *((_DWORD *)Parameter + 16) = 6;
    v8 = v11;
    v9 = (*(__int64 (__fastcall **)(SystemError *))(*(_QWORD *)v11 + 16LL))(v11);
    LODWORD(ppv) = v9;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        55,
        (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
        *((_QWORD *)v8 + 2),
        v9);
    }
  }
  catch ( Exception *v12 )
  {
    *((_DWORD *)Parameter + 16) = 6;
    v10 = (*(__int64 (__fastcall **)(Exception *))(*(_QWORD *)v12 + 16LL))(v12);
    LODWORD(ppv) = v10;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 56, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids, v10);
    }
  }
  catch ( std::bad_alloc )
  {
    *((_DWORD *)Parameter + 16) = 6;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 57, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
    }
    LODWORD(ppv) = 8;
  }
  catch ( ... )
  {
    *((_DWORD *)Parameter + 16) = 6;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 58, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
    }
    LODWORD(ppv) = -2147024122;
  }
  if ( v14 )
    CoUninitialize();
  return (unsigned int)ppv;
}

```

## disassembly

```asm
0x180027070  mov     [rsp+arg_0], rcx
0x180027075  push    rbx
0x180027076  push    rdi
0x180027077  sub     rsp, 48h
0x18002707b  mov     rdi, rcx
0x18002707e  mov     [rsp+58h+arg_8], 0
0x180027083  mov     [rsp+58h+arg_18], 0
0x18002708c  add     rcx, 30h ; '0'
0x180027090  mov     rax, [rcx]
0x180027093  mov     rax, [rax+28h]
0x180027097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002709c  test    al, al
0x18002709e  jz      loc_180027194
0x1800270a4  xor     edx, edx; dwCoInit
0x1800270a6  xor     ecx, ecx; pvReserved
0x1800270a8  call    cs:__imp_CoInitializeEx
0x1800270ae  mov     ebx, eax
0x1800270b0  test    eax, eax
0x1800270b2  jns     short loc_1800270FE
0x1800270b4  lea     rcx, WPP_GLOBAL_Control
0x1800270bb  mov     r10, cs:WPP_GLOBAL_Control
0x1800270c2  cmp     r10, rcx
0x1800270c5  jz      short loc_1800270F0
0x1800270c7  test    dword ptr [r10+6Ch], 200h
0x1800270cf  jz      short loc_1800270F0
0x1800270d1  cmp     byte ptr [r10+69h], 1
0x1800270d6  jb      short loc_1800270F0
0x1800270d8  mov     edx, 34h ; '4'
0x1800270dd  mov     r9d, eax
0x1800270e0  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x1800270e7  mov     rcx, [r10+60h]
0x1800270eb  call    WPP_SF_d
0x1800270f0  mov     edx, ebx; int
0x1800270f2  lea     rcx, aCoinitializeex; "CoInitializeEx failed "
0x1800270f9  call    ?Throw@ApplicationError@@SAXPEBGJ@Z; ApplicationError::Throw(ushort const *,long)
0x1800270fe  mov     [rsp+58h+arg_8], 1
0x180027103  mov     [rsp+58h+arg_10], 0
0x18002710c  lea     rax, [rsp+58h+arg_10]
0x180027111  mov     [rsp+58h+ppv], rax; ppv
0x180027116  lea     r9, IID_IDedupChunkLibrary; riid
0x18002711d  xor     edx, edx; pUnkOuter
0x18002711f  lea     r8d, [rdx+1]; dwClsContext
0x180027123  lea     rcx, CLSID_DedupChunkLibrary; rclsid
0x18002712a  call    cs:__imp_CoCreateInstance
0x180027130  mov     ebx, eax
0x180027132  test    eax, eax
0x180027134  jns     short loc_180027180
0x180027136  lea     rcx, WPP_GLOBAL_Control
0x18002713d  mov     r10, cs:WPP_GLOBAL_Control
0x180027144  cmp     r10, rcx
0x180027147  jz      short loc_180027172
0x180027149  test    dword ptr [r10+6Ch], 200h
0x180027151  jz      short loc_180027172
0x180027153  cmp     byte ptr [r10+69h], 1
0x180027158  jb      short loc_180027172
0x18002715a  mov     edx, 35h ; '5'
0x18002715f  mov     r9d, eax
0x180027162  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180027169  mov     rcx, [r10+60h]
0x18002716d  call    WPP_SF_d
0x180027172  mov     edx, ebx; int
0x180027174  lea     rcx, aFailedToGetDed; "Failed to get dedup interface in static"...
0x18002717b  call    ?Throw@ApplicationError@@SAXPEBGJ@Z; ApplicationError::Throw(ushort const *,long)
0x180027180  mov     rbx, [rsp+58h+arg_10]
0x180027185  lea     rcx, [rsp+58h+arg_18]
0x18002718a  call    ?Release@?$CAutoComObject@UINetFwRule@@@@QEAAXXZ; CAutoComObject<INetFwRule>::Release(void)
0x18002718f  mov     [rsp+58h+arg_18], rbx
0x180027194  test    rdi, rdi
0x180027197  jz      short loc_1800271A7
0x180027199  mov     rcx, rdi; this
0x18002719c  call    ?WorkerThreadProc@CTnoCfgMgr@@AEAAKXZ; CTnoCfgMgr::WorkerThreadProc(void)
0x1800271a1  mov     dword ptr [rsp+58h+arg_10], eax
0x1800271a5  jmp     short loc_1800271E6
0x1800271a7  lea     rcx, WPP_GLOBAL_Control
0x1800271ae  mov     rax, cs:WPP_GLOBAL_Control
0x1800271b5  cmp     rax, rcx
0x1800271b8  jz      short loc_1800271DE
0x1800271ba  test    dword ptr [rax+6Ch], 200h
0x1800271c1  jz      short loc_1800271DE
0x1800271c3  cmp     byte ptr [rax+69h], 1
0x1800271c7  jb      short loc_1800271DE
0x1800271c9  mov     edx, 36h ; '6'
0x1800271ce  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x1800271d5  mov     rcx, [rax+60h]
0x1800271d9  call    WPP_SF_
0x1800271de  mov     dword ptr [rsp+58h+arg_10], 306h
0x1800271e6  lea     rcx, [rsp+58h+arg_18]
0x1800271eb  call    ?Release@?$CAutoComObject@UINetFwRule@@@@QEAAXXZ; CAutoComObject<INetFwRule>::Release(void)
0x1800271f0  nop
0x1800271f1  jmp     short loc_1800271F9
0x1800271f3  jmp     short loc_1800271F9
0x1800271f5  jmp     short loc_1800271F9
0x1800271f7  jmp     short $+2
0x1800271f9  cmp     [rsp+58h+arg_8], 0
0x1800271fe  jz      short loc_180027206
0x180027200  call    cs:__imp_CoUninitialize
0x180027206  mov     eax, dword ptr [rsp+58h+arg_10]
0x18002720a  add     rsp, 48h
0x18002720e  pop     rdi
0x18002720f  pop     rbx
0x180027210  retn
```
