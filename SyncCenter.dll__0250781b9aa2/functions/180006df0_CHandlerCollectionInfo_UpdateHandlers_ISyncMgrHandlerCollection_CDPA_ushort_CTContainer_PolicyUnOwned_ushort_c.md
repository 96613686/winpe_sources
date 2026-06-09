# CHandlerCollectionInfo::_UpdateHandlers(ISyncMgrHandlerCollection *,CDPA<ushort,CTContainer_PolicyUnOwned<ushort>> const *)

- ea: `0x180006df0`
- end: `0x180007006`
- name: `?_UpdateHandlers@CHandlerCollectionInfo@@AEAAXPEAUISyncMgrHandlerCollection@@PEBV?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(CHandlerCollectionInfo *this, struct ISyncMgrHandlerCollection *, unsigned int **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016374`

## callees

- `0x180005d30`
- `0x180006df0`
- `0x18000700c`
- `0x1800074a4`
- `0x1800074e8`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ef5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ef5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006f76`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006f76`

## pseudocode

```c
__int64 __fastcall CHandlerCollectionInfo::_UpdateHandlers(
        CHandlerCollectionInfo *this,
        struct ISyncMgrHandlerCollection *a2,
        unsigned int **a3)
{
  unsigned int **v3; // rax
  int v4; // edi
  int i; // r14d
  unsigned int *v8; // rbx
  __int64 result; // rax
  __int64 (__fastcall *v10)(unsigned int *, _QWORD); // rax
  WCHAR *v11; // rax
  __int64 v12; // rcx
  WCHAR *v13; // rdx
  __int64 v14; // r8
  WCHAR *v15; // rcx
  int v16; // r12d
  CHandlerInfo *v17; // rbp
  int *v18; // rax
  int v19; // r15d
  __int64 (__fastcall *v20)(__int64, _QWORD); // rax
  __int64 v21; // rbx
  __int64 v22; // rbx
  GUID v24; // [rsp+40h] [rbp-158h] BYREF
  WCHAR String1[128]; // [rsp+50h] [rbp-148h] BYREF

  v3 = a3;
  v4 = 0;
  for ( i = 0; ; ++i )
  {
    v8 = *v3;
    result = *v3 ? *v8 : 0LL;
    if ( i >= (int)result )
      break;
    v24 = GUID_NULL;
    memset_0(String1, 0, sizeof(String1));
    v10 = (__int64 (__fastcall *)(unsigned int *, _QWORD))qword_1800701D0;
    if ( qword_1800701D0 == -1 )
    {
      GetProcFromComCtl32(&qword_1800701D0, 332);
      v10 = (__int64 (__fastcall *)(unsigned int *, _QWORD))qword_1800701D0;
    }
    if ( v10 )
      v11 = (WCHAR *)v10(v8, i);
    else
      v11 = 0;
    v12 = 2147483646;
    v13 = String1;
    v14 = 64;
    v24 = *(GUID *)((char *)this + 20);
    do
    {
      if ( !v12 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v12;
      --v14;
    }
    while ( v14 );
    v15 = v13 - 1;
    v16 = -2147024894;
    v17 = 0;
    if ( v14 )
      v15 = v13;
    *v15 = 0;
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 6));
    v18 = (int *)*((_QWORD *)this + 5);
    if ( v18 )
      v19 = *v18;
    else
      v19 = 0;
    while ( v4 < v19 )
    {
      v20 = (__int64 (__fastcall *)(__int64, _QWORD))qword_1800701D0;
      v21 = *((_QWORD *)this + 5);
      if ( qword_1800701D0 == -1 )
      {
        GetProcFromComCtl32(&qword_1800701D0, 332);
        v20 = (__int64 (__fastcall *)(__int64, _QWORD))qword_1800701D0;
      }
      if ( v20 )
        v22 = v20(v21, v4);
      else
        v22 = 0;
      if ( CompareStringW(0x7Fu, 1u, String1, -1, (PCNZWCH)(v22 + 116), -1) == 2 )
      {
        v4 = 0;
        v17 = (CHandlerInfo *)v22;
        v16 = 0;
        _InterlockedIncrement((volatile signed __int32 *)(v22 + 2076));
        goto LABEL_30;
      }
      ++v4;
    }
    v4 = 0;
LABEL_30:
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 6));
    if ( v16 < 0 )
    {
      CHandlerCollectionInfo::_LoadHandler(this, a2, (const struct CSyncMgrID *)&v24);
    }
    else
    {
      CHandlerInfo::Init(v17, a2);
      CHandlerInfo::Release(v17);
    }
    v3 = a3;
  }
  return result;
}

```

## disassembly

```asm
0x180006df0  mov     [rsp+arg_18], rbx
0x180006df5  push    rbp
0x180006df6  push    rsi
0x180006df7  push    rdi
0x180006df8  push    r12
0x180006dfa  push    r13
0x180006dfc  push    r14
0x180006dfe  push    r15
0x180006e00  sub     rsp, 160h
0x180006e07  mov     rax, cs:__security_cookie
0x180006e0e  xor     rax, rsp
0x180006e11  mov     [rsp+198h+var_48], rax
0x180006e19  mov     rax, r8
0x180006e1c  xor     edi, edi
0x180006e1e  mov     [rsp+198h+var_168], rax
0x180006e23  mov     r14d, edi
0x180006e26  mov     r13, rdx
0x180006e29  mov     rsi, rcx
0x180006e2c  mov     rbx, [rax]
0x180006e2f  test    rbx, rbx
0x180006e32  jz      short loc_180006E38
0x180006e34  mov     eax, [rbx]
0x180006e36  jmp     short loc_180006E3A
0x180006e38  mov     eax, edi
0x180006e3a  cmp     r14d, eax
0x180006e3d  jge     loc_180006FDB
0x180006e43  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180006e4a  xor     edx, edx; Val
0x180006e4c  lea     rcx, [rsp+198h+String1]; void *
0x180006e51  mov     r8d, 100h; Size
0x180006e57  movdqu  [rsp+198h+var_158], xmm0
0x180006e5d  call    memset_0
0x180006e62  mov     rax, cs:qword_1800701D0
0x180006e69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006e6d  jnz     short loc_180006E87
0x180006e6f  mov     edx, 14Ch
0x180006e74  lea     rcx, qword_1800701D0
0x180006e7b  call    _GetProcFromComCtl32
0x180006e80  mov     rax, cs:qword_1800701D0
0x180006e87  test    rax, rax
0x180006e8a  jz      short loc_180006E99
0x180006e8c  movsxd  rdx, r14d
0x180006e8f  mov     rcx, rbx
0x180006e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e97  jmp     short loc_180006E9C
0x180006e99  mov     rax, rdi
0x180006e9c  movups  xmm0, xmmword ptr [rsi+14h]
0x180006ea0  mov     ecx, 7FFFFFFEh
0x180006ea5  lea     rdx, [rsp+198h+String1]
0x180006eaa  mov     r8d, 40h ; '@'
0x180006eb0  movdqu  [rsp+198h+var_158], xmm0
0x180006eb6  test    rcx, rcx
0x180006eb9  jz      short loc_180006EDA
0x180006ebb  movzx   r9d, word ptr [rax]
0x180006ebf  test    r9w, r9w
0x180006ec3  jz      short loc_180006EDA
0x180006ec5  mov     [rdx], r9w
0x180006ec9  add     rax, 2
0x180006ecd  add     rdx, 2
0x180006ed1  dec     rcx
0x180006ed4  sub     r8, 1
0x180006ed8  jnz     short loc_180006EB6
0x180006eda  test    r8, r8
0x180006edd  lea     rcx, [rdx-2]
0x180006ee1  mov     r12d, 80070002h
0x180006ee7  mov     rbp, rdi
0x180006eea  cmovnz  rcx, rdx
0x180006eee  mov     [rcx], di
0x180006ef1  mov     rcx, [rsi+30h]; lpCriticalSection
0x180006ef5  call    cs:__imp_EnterCriticalSection
0x180006efb  mov     rax, [rsi+28h]
0x180006eff  test    rax, rax
0x180006f02  jz      short loc_180006F09
0x180006f04  mov     r15d, [rax]
0x180006f07  jmp     short loc_180006F0C
0x180006f09  mov     r15d, edi
0x180006f0c  cmp     edi, r15d
0x180006f0f  jge     loc_180006F9B
0x180006f15  mov     rax, cs:qword_1800701D0
0x180006f1c  mov     rbx, [rsi+28h]
0x180006f20  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006f24  jnz     short loc_180006F3E
0x180006f26  mov     edx, 14Ch
0x180006f2b  lea     rcx, qword_1800701D0
0x180006f32  call    _GetProcFromComCtl32
0x180006f37  mov     rax, cs:qword_1800701D0
0x180006f3e  test    rax, rax
0x180006f41  jz      short loc_180006F53
0x180006f43  movsxd  rdx, edi
0x180006f46  mov     rcx, rbx
0x180006f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f4e  mov     rbx, rax
0x180006f51  jmp     short loc_180006F55
0x180006f53  xor     ebx, ebx
0x180006f55  or      r9d, 0FFFFFFFFh; cchCount1
0x180006f59  mov     [rsp+198h+cchCount2], 0FFFFFFFFh; cchCount2
0x180006f61  lea     rax, [rbx+74h]
0x180006f65  lea     r8, [rsp+198h+String1]; lpString1
0x180006f6a  mov     [rsp+198h+lpString2], rax; lpString2
0x180006f6f  lea     edx, [r9+2]; dwCmpFlags
0x180006f73  lea     ecx, [rdx+7Eh]; Locale
0x180006f76  call    cs:__imp_CompareStringW
0x180006f7c  sub     eax, 1
0x180006f7f  jz      short loc_180006F86
0x180006f81  cmp     eax, 1
0x180006f84  jz      short loc_180006F8A
0x180006f86  inc     edi
0x180006f88  jmp     short loc_180006F0C
0x180006f8a  xor     edi, edi
0x180006f8c  mov     rbp, rbx
0x180006f8f  mov     r12d, edi
0x180006f92  lock inc dword ptr [rbx+81Ch]
0x180006f99  jmp     short loc_180006F9D
0x180006f9b  xor     edi, edi
0x180006f9d  mov     rcx, [rsi+30h]; lpCriticalSection
0x180006fa1  call    cs:__imp_LeaveCriticalSection
0x180006fa7  mov     rdx, r13; struct ISyncMgrHandlerCollection *
0x180006faa  test    r12d, r12d
0x180006fad  js      short loc_180006FC1
0x180006faf  mov     rcx, rbp; this
0x180006fb2  call    ?Init@CHandlerInfo@@QEAAJPEAUISyncMgrHandlerCollection@@@Z; CHandlerInfo::Init(ISyncMgrHandlerCollection *)
0x180006fb7  mov     rcx, rbp; this
0x180006fba  call    ?Release@CHandlerInfo@@QEAAKXZ; CHandlerInfo::Release(void)
0x180006fbf  jmp     short loc_180006FCE
0x180006fc1  lea     r8, [rsp+198h+var_158]; struct CSyncMgrID *
0x180006fc6  mov     rcx, rsi; this
0x180006fc9  call    ?_LoadHandler@CHandlerCollectionInfo@@AEAAJPEAUISyncMgrHandlerCollection@@AEBVCSyncMgrID@@@Z; CHandlerCollectionInfo::_LoadHandler(ISyncMgrHandlerCollection *,CSyncMgrID const &)
0x180006fce  mov     rax, [rsp+198h+var_168]
0x180006fd3  inc     r14d
0x180006fd6  jmp     loc_180006E2C
0x180006fdb  mov     rcx, [rsp+198h+var_48]
0x180006fe3  xor     rcx, rsp; StackCookie
0x180006fe6  call    __security_check_cookie
0x180006feb  mov     rbx, [rsp+198h+arg_18]
0x180006ff3  add     rsp, 160h
0x180006ffa  pop     r15
0x180006ffc  pop     r14
0x180006ffe  pop     r13
0x180007000  pop     r12
0x180007002  pop     rdi
0x180007003  pop     rsi
0x180007004  pop     rbp
0x180007005  retn
```
