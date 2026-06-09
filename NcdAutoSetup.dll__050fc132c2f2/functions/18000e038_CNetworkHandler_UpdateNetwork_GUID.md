# CNetworkHandler::_UpdateNetwork(_GUID)

- ea: `0x18000e038`
- end: `0x18000e1ae`
- name: `?_UpdateNetwork@CNetworkHandler@@AEAAJU_GUID@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(CNetworkHandler *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000bc10`
- `0x18000be70`

## callees

- `0x1800018c4`
- `0x180001e6c`
- `0x18000a644`
- `0x18000a778`
- `0x18000e038`
- `0x1800130b8`
- `0x1800131bc`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0eb`
- `KERNEL32!QueueUserWorkItem` at `0x18000e0dd`
- `KERNEL32!QueueUserWorkItem` at `0x18000e0dd`

## string_xrefs

- `0x18000e07c`: `CNetworkHandler::_UpdateNetwork`
- `0x18000e105`: `CNetworkHandler::_UpdateNetwork`
- `0x18000e169`: `CNetworkHandler::_UpdateNetwork`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::_UpdateNetwork(CNetworkHandler *this, struct _GUID *a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  signed int LastError; // eax
  __int64 v8; // rcx
  _QWORD *v9; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  v4 = 0;
  if ( !(unsigned int)IncThreadCountIfNotStopping("CNetworkHandler::_UpdateNetwork", 0x5DDu) )
    goto LABEL_19;
  v5 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    DecThreadCount("CNetworkHandler::_UpdateNetwork", 0x5F1u);
    v4 = -2147024882;
    goto LABEL_19;
  }
  *(struct _GUID *)v5 = *a2;
  v5[2] = this;
  if ( this )
    (*(void (__fastcall **)(CNetworkHandler *))(*(_QWORD *)this + 8LL))(this);
  if ( QueueUserWorkItem(WorkItemCheckQualificationAfterSizeCalculation, v6, 0x10u) )
    goto LABEL_19;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    v4 = -2147467259;
  DecThreadCount("CNetworkHandler::_UpdateNetwork", 0x5EAu);
  v8 = v6[2];
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  operator delete(v6);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_20:
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
        WPP_SF_(v9[2], 149, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
      return v4;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
LABEL_19:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  return v4;
}

```

## disassembly

```asm
0x18000e038  push    rbx
0x18000e03a  push    rbp
0x18000e03b  push    rsi
0x18000e03c  push    rdi
0x18000e03d  push    r14
0x18000e03f  sub     rsp, 20h
0x18000e043  mov     rbp, rdx
0x18000e046  mov     rsi, rcx
0x18000e049  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e050  lea     r14, WPP_GLOBAL_Control
0x18000e057  cmp     rcx, r14
0x18000e05a  jz      short loc_18000E077
0x18000e05c  test    byte ptr [rcx+1Ch], 20h
0x18000e060  jz      short loc_18000E077
0x18000e062  mov     rcx, [rcx+10h]
0x18000e066  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000e06d  mov     edx, 93h
0x18000e072  call    WPP_SF_
0x18000e077  mov     edx, 5DDh; unsigned int
0x18000e07c  lea     rcx, aCnetworkhandle_1; "CNetworkHandler::_UpdateNetwork"
0x18000e083  xor     ebx, ebx
0x18000e085  call    ?IncThreadCountIfNotStopping@@YAHPEBDK@Z; IncThreadCountIfNotStopping(char const *,ulong)
0x18000e08a  test    eax, eax
0x18000e08c  jz      loc_18000E17A
0x18000e092  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e099  lea     ecx, [rbx+18h]; unsigned __int64
0x18000e09c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e0a1  mov     rdi, rax
0x18000e0a4  test    rax, rax
0x18000e0a7  jz      loc_18000E164
0x18000e0ad  movups  xmm0, xmmword ptr [rbp+0]
0x18000e0b1  movdqu  xmmword ptr [rax], xmm0
0x18000e0b5  mov     [rax+10h], rsi
0x18000e0b9  test    rsi, rsi
0x18000e0bc  jz      short loc_18000E0CD
0x18000e0be  mov     rcx, [rsi]
0x18000e0c1  mov     rax, [rcx+8]
0x18000e0c5  mov     rcx, rsi
0x18000e0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0cd  mov     r8d, 10h; Flags
0x18000e0d3  lea     rcx, ?WorkItemCheckQualificationAfterSizeCalculation@@YAKPEAX@Z; Function
0x18000e0da  mov     rdx, rdi; Context
0x18000e0dd  call    cs:__imp_QueueUserWorkItem
0x18000e0e3  test    eax, eax
0x18000e0e5  jnz     loc_18000E17A
0x18000e0eb  call    cs:__imp_GetLastError
0x18000e0f1  mov     ebx, eax
0x18000e0f3  test    eax, eax
0x18000e0f5  jle     short loc_18000E100
0x18000e0f7  movzx   ebx, ax
0x18000e0fa  or      ebx, 80070000h
0x18000e100  mov     eax, 80004005h
0x18000e105  lea     rcx, aCnetworkhandle_1; "CNetworkHandler::_UpdateNetwork"
0x18000e10c  test    ebx, ebx
0x18000e10e  mov     edx, 5EAh; unsigned int
0x18000e113  cmovns  ebx, eax
0x18000e116  call    ?DecThreadCount@@YAXPEBDK@Z; DecThreadCount(char const *,ulong)
0x18000e11b  mov     rcx, [rdi+10h]
0x18000e11f  test    rcx, rcx
0x18000e122  jz      short loc_18000E130
0x18000e124  mov     rax, [rcx]
0x18000e127  mov     rax, [rax+10h]
0x18000e12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e130  mov     rcx, rdi; Block
0x18000e133  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e138  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e13f  cmp     rcx, r14
0x18000e142  jz      short loc_18000E1A1
0x18000e144  test    byte ptr [rcx+1Ch], 2
0x18000e148  jz      short loc_18000E181
0x18000e14a  mov     rcx, [rcx+10h]
0x18000e14e  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000e155  mov     edx, 94h
0x18000e15a  mov     r9d, ebx
0x18000e15d  call    WPP_SF_d
0x18000e162  jmp     short loc_18000E17A
0x18000e164  mov     edx, 5F1h; unsigned int
0x18000e169  lea     rcx, aCnetworkhandle_1; "CNetworkHandler::_UpdateNetwork"
0x18000e170  call    ?DecThreadCount@@YAXPEBDK@Z; DecThreadCount(char const *,ulong)
0x18000e175  mov     ebx, 8007000Eh
0x18000e17a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e181  cmp     rcx, r14
0x18000e184  jz      short loc_18000E1A1
0x18000e186  test    byte ptr [rcx+1Ch], 20h
0x18000e18a  jz      short loc_18000E1A1
0x18000e18c  mov     rcx, [rcx+10h]
0x18000e190  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000e197  mov     edx, 95h
0x18000e19c  call    WPP_SF_
0x18000e1a1  mov     eax, ebx
0x18000e1a3  add     rsp, 20h
0x18000e1a7  pop     r14
0x18000e1a9  pop     rdi
0x18000e1aa  pop     rsi
0x18000e1ab  pop     rbp
0x18000e1ac  pop     rbx
0x18000e1ad  retn
```
