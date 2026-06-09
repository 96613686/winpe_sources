# Common::Deployment::MountedFolder::Create(ushort const *,ushort const *)

- ea: `0x1800991e8`
- end: `0x1800994e9`
- name: `?Create@MountedFolder@Deployment@Common@@SAJPEBG0@Z`
- size: `769`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008cf20`
- `0x180116f8c`
- `0x1801890f0`

## callees

- `0x18000669c`
- `0x180009dc0`
- `0x180012fc8`
- `0x180015590`
- `0x180025270`
- `0x18003bea4`
- `0x1800991e8`
- `0x1800994f0`
- `0x1800aed10`
- `0x1800af1bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009923a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009932a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009923a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009932a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009930e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009930e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180099222`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180099222`
- `KERNEL32!DeviceIoControl` at `0x180099478`
- `KERNEL32!DeviceIoControl` at `0x180099478`

## string_xrefs

- `0x180099268`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x1800992ac`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x18009938e`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x18009948f`: `onecore\admin\appmodel\common\mountedfolder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Common::Deployment::MountedFolder::Create(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  signed int LastError; // eax
  signed int SystemNativePath; // ebx
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // rdx
  const struct std::nothrow_t *v9; // rdx
  Common *FileW; // rdi
  signed int v11; // eax
  void *v12; // rdx
  unsigned __int16 *v13; // rbx
  int v14; // esi
  wil::details::in1diag3 *v15; // rcx
  __int64 v16; // rdx
  void *v17; // rdx
  const struct std::nothrow_t *v18; // rdx
  __int64 v19; // rax
  unsigned __int16 *v20; // r14
  __int64 v21; // r10
  __int16 v22; // r11
  void *v23; // rdx
  const char *v24; // r9
  const struct std::nothrow_t *v25; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v29[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  __int128 InBuffer; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v32[528]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  if ( !CreateDirectoryW(lpFileName, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SystemNativePath = 0;
    if ( LastError != -2147024713 )
      SystemNativePath = LastError;
    if ( SystemNativePath < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mountedfolder.cpp",
        (const char *)(unsigned int)SystemNativePath,
        dwCreationDisposition);
      return (unsigned int)SystemNativePath;
    }
  }
  *(_OWORD *)v29 = 0;
  v30 = 0;
  SystemNativePath = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v29, a2);
  v7 = retaddr;
  if ( SystemNativePath < 0 )
  {
    v8 = 38;
LABEL_11:
    wil::details::in1diag3::_Log_Hr(
      v7,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mountedfolder.cpp",
      (const char *)(unsigned int)SystemNativePath,
      dwCreationDisposition);
LABEL_12:
    if ( v29[1] )
      operator delete(v29[1], v9);
    return (unsigned int)SystemNativePath;
  }
  SystemNativePath = Common::PathHelpers::MakeSystemNativePath((struct Common::StringBuffer *)v29);
  v7 = retaddr;
  if ( SystemNativePath < 0 )
  {
    v8 = 39;
    goto LABEL_11;
  }
  FileW = (Common *)CreateFileW(lpFileName, 0x40040000u, 0, 0, 3u, 0x2200000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v11 = GetLastError();
    SystemNativePath = v11;
    if ( v11 > 0 )
      SystemNativePath = (unsigned __int16)v11 | 0x80070000;
    Common::CloseHandleHelper(FileW, v12);
    goto LABEL_12;
  }
  InBuffer = 0;
  *(_QWORD *)v32 = 0;
  LODWORD(InBuffer) = -1610612733;
  v13 = v29[1];
  v14 = StringCchPrintfW(v32, 0x108u, v29[1]);
  v15 = retaddr;
  if ( v14 < 0 )
  {
    v16 = 56;
LABEL_22:
    wil::details::in1diag3::_Log_Hr(
      v15,
      (void *)v16,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mountedfolder.cpp",
      (const char *)(unsigned int)v14,
      dwCreationDispositiona);
LABEL_23:
    Common::CloseHandleHelper(FileW, v17);
    if ( v13 )
      operator delete(v13, v18);
    return (unsigned int)v14;
  }
  v19 = -1;
  do
    ++v19;
  while ( v32[v19] );
  v20 = &v32[(unsigned __int16)v19 + 1];
  v14 = StringCchCopyW(v20, 0x105u, a2);
  v15 = retaddr;
  if ( v14 < 0 )
  {
    v16 = 60;
    goto LABEL_22;
  }
  do
    ++v21;
  while ( v20[v21] );
  WORD4(InBuffer) = 0;
  WORD5(InBuffer) = 2 * v22;
  WORD6(InBuffer) = 2 * v22 + 2;
  HIWORD(InBuffer) = 2 * v21;
  WORD2(InBuffer) = 2 * (v21 + 6 + v22);
  BytesReturned = 0;
  if ( !DeviceIoControl(FileW, 0x900A4u, &InBuffer, WORD2(InBuffer) + 8, 0, 0, &BytesReturned, 0) )
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x55,
            (unsigned int)"onecore\\admin\\appmodel\\common\\mountedfolder.cpp",
            v24);
    goto LABEL_23;
  }
  Common::CloseHandleHelper(FileW, v23);
  if ( v13 )
    operator delete(v13, v25);
  return 0;
}

```

## disassembly

```asm
0x1800991e8  mov     [rsp-8+arg_10], rbx
0x1800991ed  mov     [rsp-8+arg_18], rsi
0x1800991f2  push    rbp
0x1800991f3  push    rdi
0x1800991f4  push    r12
0x1800991f6  push    r14
0x1800991f8  push    r15
0x1800991fa  lea     rbp, [rsp-3A0h]
0x180099202  sub     rsp, 4A0h
0x180099209  mov     rax, cs:__security_cookie
0x180099210  xor     rax, rsp
0x180099213  mov     [rbp+3C0h+var_30], rax
0x18009921a  mov     r15, rdx
0x18009921d  mov     rdi, rcx
0x180099220  xor     edx, edx; lpSecurityAttributes
0x180099222  call    cs:__imp_CreateDirectoryW
0x180099229  nop     dword ptr [rax+rax+00h]
0x18009922e  mov     esi, 80070000h
0x180099233  xor     r12d, r12d
0x180099236  test    eax, eax
0x180099238  jnz     short loc_180099280
0x18009923a  call    cs:__imp_GetLastError
0x180099241  nop     dword ptr [rax+rax+00h]
0x180099246  test    eax, eax
0x180099248  jle     short loc_18009924F
0x18009924a  movzx   eax, ax
0x18009924d  or      eax, esi
0x18009924f  mov     ebx, r12d
0x180099252  cmp     eax, 800700B7h
0x180099257  cmovnz  ebx, eax
0x18009925a  mov     rcx, [rbp+3C8h]; this
0x180099261  test    ebx, ebx
0x180099263  jns     short loc_180099280
0x180099265  mov     r9d, ebx; char *
0x180099268  lea     r8, aOnecoreAdminAp_123; "onecore\\admin\\appmodel\\common\\mount"...
0x18009926f  mov     edx, 21h ; '!'; void *
0x180099274  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180099279  mov     eax, ebx
0x18009927b  jmp     loc_1800994BD
0x180099280  xorps   xmm0, xmm0
0x180099283  movups  xmmword ptr [rsp+4C0h+var_478], xmm0
0x180099288  mov     [rsp+4C0h+var_468], r12d
0x18009928d  mov     rdx, r15; unsigned __int16 *
0x180099290  lea     rcx, [rsp+4C0h+var_478]; this
0x180099295  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18009929a  mov     ebx, eax
0x18009929c  mov     rcx, [rbp+3C8h]; this
0x1800992a3  test    eax, eax
0x1800992a5  jns     short loc_1800992CD
0x1800992a7  mov     edx, 26h ; '&'; void *
0x1800992ac  lea     r8, aOnecoreAdminAp_123; "onecore\\admin\\appmodel\\common\\mount"...
0x1800992b3  mov     r9d, ebx; char *
0x1800992b6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800992bb  nop
0x1800992bc  mov     rcx, [rsp+4C0h+var_478+8]; void *
0x1800992c1  test    rcx, rcx
0x1800992c4  jz      short loc_180099279
0x1800992c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800992cb  jmp     short loc_180099279
0x1800992cd  lea     rcx, [rsp+4C0h+var_478]; struct Common::StringBuffer *
0x1800992d2  call    ?MakeSystemNativePath@PathHelpers@Common@@SAJPEAVStringBuffer@2@@Z; Common::PathHelpers::MakeSystemNativePath(Common::StringBuffer *)
0x1800992d7  mov     ebx, eax
0x1800992d9  mov     rcx, [rbp+3C8h]
0x1800992e0  test    eax, eax
0x1800992e2  jns     short loc_1800992EB
0x1800992e4  mov     edx, 27h ; '''
0x1800992e9  jmp     short loc_1800992AC
0x1800992eb  mov     [rsp+4C0h+hTemplateFile], r12; hTemplateFile
0x1800992f0  mov     [rsp+4C0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800992f8  mov     [rsp+4C0h+dwCreationDisposition], 3; int
0x180099300  xor     r9d, r9d; lpSecurityAttributes
0x180099303  xor     r8d, r8d; dwShareMode
0x180099306  mov     edx, 40040000h; dwDesiredAccess
0x18009930b  mov     rcx, rdi; lpFileName
0x18009930e  call    cs:__imp_CreateFileW
0x180099315  nop     dword ptr [rax+rax+00h]
0x18009931a  mov     rdi, rax
0x18009931d  lea     rcx, [rax+1]
0x180099321  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180099328  jnz     short loc_18009934E
0x18009932a  call    cs:__imp_GetLastError
0x180099331  nop     dword ptr [rax+rax+00h]
0x180099336  mov     ebx, eax
0x180099338  test    eax, eax
0x18009933a  jle     short loc_180099341
0x18009933c  movzx   ebx, ax
0x18009933f  or      ebx, esi
0x180099341  mov     rcx, rdi; this
0x180099344  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x180099349  jmp     loc_1800992BC
0x18009934e  xorps   xmm0, xmm0
0x180099351  xor     eax, eax
0x180099353  movups  [rsp+4C0h+InBuffer], xmm0
0x180099358  mov     qword ptr [rsp+4C0h+var_450], rax
0x18009935d  mov     dword ptr [rsp+4C0h+InBuffer], 0A0000003h
0x180099365  mov     rbx, [rsp+4C0h+var_478+8]
0x18009936a  mov     r8, rbx; unsigned __int16 *
0x18009936d  mov     edx, 108h; unsigned __int64
0x180099372  lea     rcx, [rsp+4C0h+var_450]; unsigned __int16 *
0x180099377  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009937c  mov     esi, eax
0x18009937e  mov     rcx, [rbp+3C8h]; this
0x180099385  test    eax, eax
0x180099387  jns     short loc_1800993BA
0x180099389  mov     edx, 38h ; '8'; void *
0x18009938e  lea     r8, aOnecoreAdminAp_123; "onecore\\admin\\appmodel\\common\\mount"...
0x180099395  mov     r9d, esi; char *
0x180099398  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009939d  mov     rcx, rdi; this
0x1800993a0  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x1800993a5  nop
0x1800993a6  test    rbx, rbx
0x1800993a9  jz      short loc_1800993B3
0x1800993ab  mov     rcx, rbx; void *
0x1800993ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800993b3  mov     eax, esi
0x1800993b5  jmp     loc_1800994BD
0x1800993ba  lea     rcx, [rsp+4C0h+var_450]
0x1800993bf  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800993c3  mov     rax, r10
0x1800993c6  inc     rax
0x1800993c9  cmp     [rcx+rax*2], r12w
0x1800993ce  jnz     short loc_1800993C6
0x1800993d0  movzx   r11d, ax
0x1800993d4  lea     r14, [rsp+4C0h+var_450+2]
0x1800993d9  lea     r14, [r14+r11*2]
0x1800993dd  mov     r8, r15; unsigned __int16 *
0x1800993e0  mov     edx, 105h; unsigned __int64
0x1800993e5  mov     rcx, r14; unsigned __int16 *
0x1800993e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800993ed  mov     esi, eax
0x1800993ef  mov     rcx, [rbp+3C8h]
0x1800993f6  test    eax, eax
0x1800993f8  jns     short loc_180099401
0x1800993fa  mov     edx, 3Ch ; '<'
0x1800993ff  jmp     short loc_18009938E
0x180099401  inc     r10
0x180099404  cmp     [r14+r10*2], r12w
0x180099409  jnz     short loc_180099401
0x18009940b  mov     word ptr [rsp+4C0h+InBuffer+8], r12w
0x180099411  movzx   eax, r11w
0x180099415  add     ax, ax
0x180099418  mov     word ptr [rsp+4C0h+InBuffer+0Ah], ax
0x18009941d  add     ax, 2
0x180099421  mov     word ptr [rsp+4C0h+InBuffer+0Ch], ax
0x180099426  movzx   eax, r10w
0x18009942a  add     ax, ax
0x18009942d  mov     word ptr [rsp+4C0h+InBuffer+0Eh], ax
0x180099432  add     r10w, 6
0x180099437  add     r11w, r10w
0x18009943b  add     r11w, r11w
0x18009943f  movzx   r9d, r11w
0x180099443  mov     word ptr [rsp+4C0h+InBuffer+4], r9w
0x180099449  mov     [rsp+4C0h+BytesReturned], r12d
0x18009944e  add     r9d, 8; nInBufferSize
0x180099452  mov     [rsp+4C0h+lpOverlapped], r12; lpOverlapped
0x180099457  lea     rax, [rsp+4C0h+BytesReturned]
0x18009945c  mov     [rsp+4C0h+hTemplateFile], rax; lpBytesReturned
0x180099461  mov     [rsp+4C0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x180099466  mov     qword ptr [rsp+4C0h+dwCreationDisposition], r12; lpOutBuffer
0x18009946b  lea     r8, [rsp+4C0h+InBuffer]; lpInBuffer
0x180099470  mov     edx, 900A4h; dwIoControlCode
0x180099475  mov     rcx, rdi; hDevice
0x180099478  call    cs:__imp_DeviceIoControl
0x18009947f  nop     dword ptr [rax+rax+00h]
0x180099484  test    eax, eax
0x180099486  jnz     short loc_1800994A5
0x180099488  mov     rcx, [rbp+3C8h]; this
0x18009948f  lea     r8, aOnecoreAdminAp_123; "onecore\\admin\\appmodel\\common\\mount"...
0x180099496  lea     edx, [rax+55h]; void *
0x180099499  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009949e  mov     esi, eax
0x1800994a0  jmp     loc_18009939D
0x1800994a5  mov     rcx, rdi; this
0x1800994a8  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x1800994ad  nop
0x1800994ae  test    rbx, rbx
0x1800994b1  jz      short loc_1800994BB
0x1800994b3  mov     rcx, rbx; void *
0x1800994b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800994bb  xor     eax, eax
0x1800994bd  mov     rcx, [rbp+3C0h+var_30]
0x1800994c4  xor     rcx, rsp; StackCookie
0x1800994c7  call    __security_check_cookie
0x1800994cc  lea     r11, [rsp+4C0h+var_20]
0x1800994d4  mov     rbx, [r11+40h]
0x1800994d8  mov     rsi, [r11+48h]
0x1800994dc  mov     rsp, r11
0x1800994df  pop     r15
0x1800994e1  pop     r14
0x1800994e3  pop     r12
0x1800994e5  pop     rdi
0x1800994e6  pop     rbp
0x1800994e7  retn
```
