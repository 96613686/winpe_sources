# PluginState::ReleasePluginHandle(AadContextFunctions *)

- ea: `0x18001f498`
- end: `0x18001f684`
- name: `?ReleasePluginHandle@PluginState@@QEAAJPEAVAadContextFunctions@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(PluginState *__hidden this, struct AadContextFunctions *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000bca0`
- `0x180017248`
- `0x18001e150`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180007ca4`
- `0x18001ec34`
- `0x18001f498`
- `0x18003fa08`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f545`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f552`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f545`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f552`
- `WS2_32!__imp_WSACleanup` at `0x18001f56c`
- `WS2_32!__imp_WSACleanup` at `0x18001f56c`

## string_xrefs

- `0x18001f4b5`: `PluginState::ReleasePluginHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PluginState::ReleasePluginHandle(struct _AadApPluginHandle **this, struct AadContextFunctions *a2)
{
  __int64 v4; // rsi
  struct _UNICODE_STRING *v5; // rdx
  __int64 v6; // rdx
  _BYTE *v7; // rcx
  struct _AadApPluginJoinInfo *v8; // r8
  struct _AadApPluginJoinInfo *v9; // r8
  _BYTE *v10; // rcx
  __int64 v11; // rcx
  struct _AadApPluginHandle *v12; // rax
  unsigned int v13; // ebx
  const char *v15[11]; // [rsp+50h] [rbp-58h] BYREF
  int v16; // [rsp+B8h] [rbp+10h] BYREF

  v16 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v15,
    (int)"pluginstate.cpp",
    (int)"PluginState::ReleasePluginHandle",
    (int)&v16);
  if ( a2 )
  {
    v4 = 24;
    AadContextFunctions::LsaFreeString(a2, (struct _UNICODE_STRING *)((char *)*this + 24));
    if ( *((_DWORD *)*this + 32) )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)*this + 48));
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)*this + 88));
      *((_DWORD *)*this + 32) = 0;
    }
    if ( *((_DWORD *)*this + 33) )
    {
      WSACleanup();
      *((_DWORD *)*this + 33) = 0;
    }
    TokenBindingHelper::ReleaseTokenBindingCache(*this);
    v5 = *(struct _UNICODE_STRING **)*this;
    if ( v5 )
    {
      AadContextFunctions::LsaFreeString(a2, v5 + 1);
      v6 = 56;
      v7 = *(_BYTE **)*this;
      do
      {
        *v7++ = 0;
        --v6;
      }
      while ( v6 );
      (*(void (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, *(_QWORD *)*this);
      *(_QWORD *)*this = 0;
    }
    v8 = (struct _AadApPluginJoinInfo *)*((_QWORD *)*this + 1);
    if ( v8 )
    {
      PluginState::FreeJoinState((PluginState *)this, a2, v8);
      *((_QWORD *)*this + 1) = 0;
    }
    v9 = (struct _AadApPluginJoinInfo *)*((_QWORD *)*this + 2);
    if ( v9 )
    {
      PluginState::FreeJoinState((PluginState *)this, a2, v9);
      *((_QWORD *)*this + 2) = 0;
    }
    v10 = (_BYTE *)*((_QWORD *)*this + 18);
    if ( v10 )
    {
      do
      {
        *v10++ = 0;
        --v4;
      }
      while ( v4 );
      (*(void (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, *((_QWORD *)*this + 18));
    }
    v11 = 160;
    v12 = *this;
    do
    {
      *(_BYTE *)v12 = 0;
      v12 = (struct _AadApPluginHandle *)((char *)v12 + 1);
      --v11;
    }
    while ( v11 );
    (*(void (__fastcall **)(struct AadContextFunctions *, struct _AadApPluginHandle *))(*(_QWORD *)a2 + 32LL))(
      a2,
      *this);
    *this = 0;
  }
  else
  {
    v16 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "pluginstate.cpp", 80, "NTSTATUS", &base);
  }
  v13 = v16;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v15);
  return v13;
}

```

## disassembly

```asm
0x18001f498  mov     rax, rsp
0x18001f49b  push    rbx
0x18001f49c  push    rbp
0x18001f49d  push    rsi
0x18001f49e  push    rdi
0x18001f49f  sub     rsp, 88h
0x18001f4a6  mov     rdi, rdx
0x18001f4a9  mov     rbx, rcx
0x18001f4ac  xor     ebp, ebp
0x18001f4ae  mov     [rax+10h], ebp
0x18001f4b1  lea     r9, [rax+10h]
0x18001f4b5  lea     r8, aPluginstateRel; "PluginState::ReleasePluginHandle"
0x18001f4bc  lea     rsi, aOnecoreuapDsEx_57+21h; "pluginstate.cpp"
0x18001f4c3  mov     rdx, rsi
0x18001f4c6  lea     rcx, [rax-58h]
0x18001f4ca  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18001f4cf  nop
0x18001f4d0  test    rdi, rdi
0x18001f4d3  jnz     short loc_18001F523
0x18001f4d5  mov     ecx, 0C000000Dh
0x18001f4da  mov     [rsp+0A8h+arg_8], ecx
0x18001f4e1  lea     rax, base
0x18001f4e8  mov     [rsp+0A8h+var_68], rax
0x18001f4ed  lea     rax, aNtstatus; "NTSTATUS"
0x18001f4f4  mov     [rsp+0A8h+var_70], rax
0x18001f4f9  mov     [rsp+0A8h+var_78], 50h ; 'P'
0x18001f501  mov     [rsp+0A8h+var_80], rsi
0x18001f506  mov     [rsp+0A8h+var_88], ecx
0x18001f50a  lea     ecx, [rbp+2]
0x18001f50d  mov     r9d, ecx
0x18001f510  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18001f517  xor     edx, edx
0x18001f519  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18001f51e  jmp     loc_18001F665
0x18001f523  mov     rdx, [rbx]
0x18001f526  mov     esi, 18h
0x18001f52b  add     rdx, rsi; struct _UNICODE_STRING *
0x18001f52e  mov     rcx, rdi; this
0x18001f531  call    ?LsaFreeString@AadContextFunctions@@QEAAXPEAU_UNICODE_STRING@@@Z; AadContextFunctions::LsaFreeString(_UNICODE_STRING *)
0x18001f536  mov     rcx, [rbx]
0x18001f539  cmp     [rcx+80h], ebp
0x18001f53f  jz      short loc_18001F561
0x18001f541  add     rcx, 30h ; '0'; lpCriticalSection
0x18001f545  call    cs:__imp_DeleteCriticalSection
0x18001f54b  mov     rcx, [rbx]
0x18001f54e  add     rcx, 58h ; 'X'; lpCriticalSection
0x18001f552  call    cs:__imp_DeleteCriticalSection
0x18001f558  mov     rax, [rbx]
0x18001f55b  mov     [rax+80h], ebp
0x18001f561  mov     rax, [rbx]
0x18001f564  cmp     [rax+84h], ebp
0x18001f56a  jz      short loc_18001F57B
0x18001f56c  call    cs:__imp_WSACleanup
0x18001f572  mov     rax, [rbx]
0x18001f575  mov     [rax+84h], ebp
0x18001f57b  mov     rcx, [rbx]; struct _AadApPluginHandle *
0x18001f57e  call    ?ReleaseTokenBindingCache@TokenBindingHelper@@SAXPEAU_AadApPluginHandle@@@Z; TokenBindingHelper::ReleaseTokenBindingCache(_AadApPluginHandle *)
0x18001f583  mov     rax, [rbx]
0x18001f586  mov     rdx, [rax]
0x18001f589  test    rdx, rdx
0x18001f58c  jz      short loc_18001F5CC
0x18001f58e  add     rdx, 10h; struct _UNICODE_STRING *
0x18001f592  mov     rcx, rdi; this
0x18001f595  call    ?LsaFreeString@AadContextFunctions@@QEAAXPEAU_UNICODE_STRING@@@Z; AadContextFunctions::LsaFreeString(_UNICODE_STRING *)
0x18001f59a  mov     edx, 38h ; '8'
0x18001f59f  mov     rax, [rbx]
0x18001f5a2  mov     rcx, [rax]
0x18001f5a5  mov     [rcx], bpl
0x18001f5a8  inc     rcx
0x18001f5ab  sub     rdx, 1
0x18001f5af  jnz     short loc_18001F5A5
0x18001f5b1  mov     rax, [rdi]
0x18001f5b4  mov     rdx, [rbx]
0x18001f5b7  mov     rdx, [rdx]
0x18001f5ba  mov     rcx, rdi
0x18001f5bd  mov     rax, [rax+20h]
0x18001f5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5c6  mov     rax, [rbx]
0x18001f5c9  mov     [rax], rbp
0x18001f5cc  mov     rax, [rbx]
0x18001f5cf  mov     r8, [rax+8]; struct _AadApPluginJoinInfo *
0x18001f5d3  test    r8, r8
0x18001f5d6  jz      short loc_18001F5EA
0x18001f5d8  mov     rdx, rdi; struct AadContextFunctions *
0x18001f5db  mov     rcx, rbx; this
0x18001f5de  call    ?FreeJoinState@PluginState@@AEAAJPEAVAadContextFunctions@@PEAU_AadApPluginJoinInfo@@@Z; PluginState::FreeJoinState(AadContextFunctions *,_AadApPluginJoinInfo *)
0x18001f5e3  mov     rax, [rbx]
0x18001f5e6  mov     [rax+8], rbp
0x18001f5ea  mov     rax, [rbx]
0x18001f5ed  mov     r8, [rax+10h]; struct _AadApPluginJoinInfo *
0x18001f5f1  test    r8, r8
0x18001f5f4  jz      short loc_18001F608
0x18001f5f6  mov     rdx, rdi; struct AadContextFunctions *
0x18001f5f9  mov     rcx, rbx; this
0x18001f5fc  call    ?FreeJoinState@PluginState@@AEAAJPEAVAadContextFunctions@@PEAU_AadApPluginJoinInfo@@@Z; PluginState::FreeJoinState(AadContextFunctions *,_AadApPluginJoinInfo *)
0x18001f601  mov     rax, [rbx]
0x18001f604  mov     [rax+10h], rbp
0x18001f608  mov     rax, [rbx]
0x18001f60b  mov     rcx, [rax+90h]
0x18001f612  test    rcx, rcx
0x18001f615  jz      short loc_18001F63C
0x18001f617  mov     [rcx], bpl
0x18001f61a  inc     rcx
0x18001f61d  sub     rsi, 1
0x18001f621  jnz     short loc_18001F617
0x18001f623  mov     rax, [rdi]
0x18001f626  mov     rdx, [rbx]
0x18001f629  mov     rdx, [rdx+90h]
0x18001f630  mov     rcx, rdi
0x18001f633  mov     rax, [rax+20h]
0x18001f637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f63c  mov     ecx, 0A0h
0x18001f641  mov     rax, [rbx]
0x18001f644  mov     [rax], bpl
0x18001f647  inc     rax
0x18001f64a  sub     rcx, 1
0x18001f64e  jnz     short loc_18001F644
0x18001f650  mov     rax, [rdi]
0x18001f653  mov     rdx, [rbx]
0x18001f656  mov     rcx, rdi
0x18001f659  mov     rax, [rax+20h]
0x18001f65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f662  mov     [rbx], rbp
0x18001f665  mov     ebx, [rsp+0A8h+arg_8]
0x18001f66c  lea     rcx, [rsp+0A8h+var_58]
0x18001f671  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18001f676  mov     eax, ebx
0x18001f678  add     rsp, 88h
0x18001f67f  pop     rdi
0x18001f680  pop     rsi
0x18001f681  pop     rbp
0x18001f682  pop     rbx
0x18001f683  retn
```
