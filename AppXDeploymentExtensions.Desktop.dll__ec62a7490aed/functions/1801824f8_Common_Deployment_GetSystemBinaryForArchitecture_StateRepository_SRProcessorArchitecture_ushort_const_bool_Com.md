# Common::Deployment::GetSystemBinaryForArchitecture(StateRepository::SRProcessorArchitecture,ushort const *,bool,Common::StringBuffer &)

- ea: `0x1801824f8`
- end: `0x1801826f0`
- name: `?GetSystemBinaryForArchitecture@Deployment@Common@@YAJW4SRProcessorArchitecture@StateRepository@@PEBG_NAEAVStringBuffer@2@@Z`
- size: `504`
- prototype: `int __high(enum StateRepository::SRProcessorArchitecture, const unsigned __int16 *, bool, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800dda0c`

## callees

- `0x18000669c`
- `0x18000a138`
- `0x18001adb4`
- `0x18001d920`
- `0x1800ebbd8`
- `0x1801824f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801825bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801825bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180182601`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18018268c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180182601`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18018268c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18018255b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1801825e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18018255b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1801825e6`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1801825a0`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18018269e`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1801825a0`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18018269e`

## string_xrefs

- `0x18018252e`: `onecore\admin\appmodel\common\packageid.cpp`
- `0x180182620`: `onecore\admin\appmodel\common\packageid.cpp`
- `0x180182668`: `onecore\admin\appmodel\common\packageid.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::GetSystemBinaryForArchitecture(
        unsigned int a1,
        const unsigned __int16 *a2,
        char a3,
        Common::StringBuffer *a4)
{
  __int64 v8; // rdx
  int appended; // ebx
  __int64 v11; // rcx
  unsigned __int16 ImageFileMachineFromArchitecture; // ax
  unsigned __int16 v13; // di
  UINT SystemWow64Directory2W; // ebx
  const char *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned int v18; // edx
  int v19; // eax
  unsigned int v20; // esi
  WCHAR *v21; // rcx
  UINT SystemDirectoryW; // eax
  struct _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-98h] BYREF
  struct _SYSTEM_INFO v24; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( !a2 )
  {
    v8 = 19;
LABEL_3:
    appended = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
      (const char *)(unsigned int)appended,
      SystemInfo.dwOemId);
    return (unsigned int)appended;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  if ( SystemInfo.wProcessorArchitecture == 12 && a3 && a1 == 11 )
    a1 = 0;
  v11 = 0;
  if ( a1 != 14 )
    v11 = a1;
  ImageFileMachineFromArchitecture = Common::Deployment::GetImageFileMachineFromArchitecture(v11);
  v13 = ImageFileMachineFromArchitecture;
  if ( ImageFileMachineFromArchitecture != 1 )
  {
    SystemWow64Directory2W = GetSystemWow64Directory2W(0, 0, ImageFileMachineFromArchitecture);
    if ( SystemWow64Directory2W )
      goto LABEL_20;
    if ( v13 != 0x8664 )
      goto LABEL_18;
    if ( GetLastError() != 160 )
      goto LABEL_18;
    memset(&v24, 0, sizeof(v24));
    GetSystemInfo(&v24);
    if ( v24.wProcessorArchitecture != 12 )
      goto LABEL_18;
    v13 = 1;
  }
  SystemWow64Directory2W = GetSystemDirectoryW(0, 0);
  if ( !SystemWow64Directory2W )
  {
LABEL_18:
    v16 = 64;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v16,
             (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
             v15);
  }
LABEL_20:
  v17 = -1;
  do
    ++v17;
  while ( a2[v17] );
  v18 = v17 + SystemWow64Directory2W + 1;
  if ( v18 < SystemWow64Directory2W )
  {
    v8 = 69;
    goto LABEL_3;
  }
  v19 = Common::StringBuffer::SetLength(a4, v18);
  v20 = v19;
  if ( v19 >= 0 )
  {
    v21 = (WCHAR *)*((_QWORD *)a4 + 1);
    if ( v13 == 1 )
      SystemDirectoryW = GetSystemDirectoryW(v21, SystemWow64Directory2W);
    else
      SystemDirectoryW = GetSystemWow64Directory2W(v21, SystemWow64Directory2W, v13);
    if ( !SystemDirectoryW )
    {
      v16 = 82;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v16,
               (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
               v15);
    }
    Common::StringBuffer::SetLength(a4, SystemDirectoryW);
    appended = Common::PathHelpers::AppendPathSegment(a4, a2);
    if ( appended < 0 )
    {
      v8 = 86;
      goto LABEL_4;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
      (const char *)(unsigned int)v19,
      SystemInfo.dwOemId);
    return v20;
  }
}

```

## disassembly

```asm
0x1801824f8  push    rbx
0x1801824fa  push    rbp
0x1801824fb  push    rsi
0x1801824fc  push    rdi
0x1801824fd  push    r12
0x1801824ff  push    r14
0x180182501  push    r15
0x180182503  sub     rsp, 80h
0x18018250a  xor     r15d, r15d
0x18018250d  mov     rbp, r9
0x180182510  mov     dil, r8b
0x180182513  mov     r14, rdx
0x180182516  mov     ebx, ecx
0x180182518  test    rdx, rdx
0x18018251b  jnz     short loc_180182544
0x18018251d  lea     edx, [r14+13h]; void *
0x180182521  mov     ebx, 80070057h
0x180182526  mov     rcx, [rsp+0B8h]; this
0x18018252e  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\packa"...
0x180182535  mov     r9d, ebx; char *
0x180182538  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018253d  mov     eax, ebx
0x18018253f  jmp     loc_1801826DD
0x180182544  xorps   xmm0, xmm0
0x180182547  lea     rcx, [rsp+0B8h+SystemInfo]; lpSystemInfo
0x18018254c  movups  xmmword ptr [rsp+0B8h+SystemInfo], xmm0; int
0x180182551  movups  xmmword ptr [rsp+0B8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180182556  movups  xmmword ptr [rsp+0B8h+SystemInfo.dwNumberOfProcessors], xmm0
0x18018255b  call    cs:__imp_GetSystemInfo
0x180182562  nop     dword ptr [rax+rax+00h]
0x180182567  cmp     word ptr [rsp+0B8h+SystemInfo], 0Ch
0x18018256d  jnz     short loc_18018257B
0x18018256f  test    dil, dil
0x180182572  jz      short loc_18018257B
0x180182574  cmp     ebx, 0Bh
0x180182577  cmovz   ebx, r15d
0x18018257b  mov     ecx, r15d
0x18018257e  cmp     ebx, 0Eh
0x180182581  cmovnz  ecx, ebx
0x180182584  call    ?GetImageFileMachineFromArchitecture@Deployment@Common@@YAGW4SRProcessorArchitecture@StateRepository@@_N@Z; Common::Deployment::GetImageFileMachineFromArchitecture(StateRepository::SRProcessorArchitecture,bool)
0x180182589  xor     edx, edx
0x18018258b  xor     ecx, ecx
0x18018258d  mov     r12d, 1
0x180182593  movzx   edi, ax
0x180182596  cmp     ax, r12w
0x18018259a  jz      short loc_180182601
0x18018259c  movzx   r8d, ax
0x1801825a0  call    cs:__imp_GetSystemWow64Directory2W
0x1801825a7  nop     dword ptr [rax+rax+00h]
0x1801825ac  mov     ebx, eax
0x1801825ae  test    eax, eax
0x1801825b0  jnz     short loc_180182631
0x1801825b2  mov     eax, 8664h
0x1801825b7  cmp     di, ax
0x1801825ba  jnz     short loc_180182613
0x1801825bc  call    cs:__imp_GetLastError
0x1801825c3  nop     dword ptr [rax+rax+00h]
0x1801825c8  cmp     eax, 0A0h
0x1801825cd  jnz     short loc_180182613
0x1801825cf  xorps   xmm0, xmm0
0x1801825d2  lea     rcx, [rsp+0B8h+var_68]; lpSystemInfo
0x1801825d7  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x1801825dc  movups  xmmword ptr [rsp+0B8h+var_68.lpMaximumApplicationAddress], xmm0
0x1801825e1  movups  xmmword ptr [rsp+0B8h+var_68.dwNumberOfProcessors], xmm0
0x1801825e6  call    cs:__imp_GetSystemInfo
0x1801825ed  nop     dword ptr [rax+rax+00h]
0x1801825f2  cmp     word ptr [rsp+0B8h+var_68], 0Ch
0x1801825f8  jnz     short loc_180182613
0x1801825fa  xor     edx, edx; uSize
0x1801825fc  mov     edi, r12d
0x1801825ff  xor     ecx, ecx; lpBuffer
0x180182601  call    cs:__imp_GetSystemDirectoryW
0x180182608  nop     dword ptr [rax+rax+00h]
0x18018260d  mov     ebx, eax
0x18018260f  test    eax, eax
0x180182611  jnz     short loc_180182631
0x180182613  mov     edx, 40h ; '@'; void *
0x180182618  mov     rcx, [rsp+0B8h]; this
0x180182620  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\packa"...
0x180182627  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18018262c  jmp     loc_1801826DD
0x180182631  or      rax, 0FFFFFFFFFFFFFFFFh
0x180182635  inc     rax
0x180182638  cmp     [r14+rax*2], r15w
0x18018263d  jnz     short loc_180182635
0x18018263f  lea     edx, [rbx+1]
0x180182642  add     edx, eax; unsigned int
0x180182644  cmp     edx, ebx
0x180182646  jnb     short loc_180182652
0x180182648  mov     edx, 45h ; 'E'
0x18018264d  jmp     loc_180182521
0x180182652  mov     rcx, rbp; this
0x180182655  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x18018265a  mov     esi, eax
0x18018265c  test    eax, eax
0x18018265e  jns     short loc_180182680
0x180182660  mov     rcx, [rsp+0B8h]; this
0x180182668  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\packa"...
0x18018266f  mov     r9d, eax; char *
0x180182672  mov     edx, 48h ; 'H'; void *
0x180182677  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018267c  mov     eax, esi
0x18018267e  jmp     short loc_1801826DD
0x180182680  mov     rcx, [rbp+8]; lpBuffer
0x180182684  mov     edx, ebx; uSize
0x180182686  cmp     di, r12w
0x18018268a  jnz     short loc_18018269A
0x18018268c  call    cs:__imp_GetSystemDirectoryW
0x180182693  nop     dword ptr [rax+rax+00h]
0x180182698  jmp     short loc_1801826AA
0x18018269a  movzx   r8d, di
0x18018269e  call    cs:__imp_GetSystemWow64Directory2W
0x1801826a5  nop     dword ptr [rax+rax+00h]
0x1801826aa  test    eax, eax
0x1801826ac  jnz     short loc_1801826B6
0x1801826ae  lea     edx, [rax+52h]
0x1801826b1  jmp     loc_180182618
0x1801826b6  mov     edx, eax; unsigned int
0x1801826b8  mov     rcx, rbp; this
0x1801826bb  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x1801826c0  mov     rdx, r14; unsigned __int16 *
0x1801826c3  mov     rcx, rbp; struct Common::StringBuffer *
0x1801826c6  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x1801826cb  mov     ebx, eax
0x1801826cd  test    eax, eax
0x1801826cf  jns     short loc_1801826DB
0x1801826d1  mov     edx, 56h ; 'V'
0x1801826d6  jmp     loc_180182526
0x1801826db  xor     eax, eax
0x1801826dd  add     rsp, 80h
0x1801826e4  pop     r15
0x1801826e6  pop     r14
0x1801826e8  pop     r12
0x1801826ea  pop     rdi
0x1801826eb  pop     rsi
0x1801826ec  pop     rbp
0x1801826ed  pop     rbx
0x1801826ee  retn
```
