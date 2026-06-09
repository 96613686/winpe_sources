# WIMHashFile::ResumeHashWrites(void)

- ea: `0x180002474`
- end: `0x18000275f`
- name: `?ResumeHashWrites@WIMHashFile@@AEAAJXZ`
- size: `747`
- prototype: `__int64 __fastcall(WIMHashFile *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800040a8`

## callees

- `0x1800019d4`
- `0x180001c20`
- `0x180001cdc`
- `0x180002474`
- `0x180002768`
- `0x1800027c4`
- `0x1800028d8`
- `0x1800029bc`
- `0x1800029fc`
- `0x180002a88`
- `0x1800045cc`
- `0x180004af4`
- `0x1800051c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180002686`
- `msvcrt!swprintf_s` at `0x180002686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002718`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002655`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002655`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800026ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800026ad`

## string_xrefs

- `0x18000260f`: `SYSTEM\CurrentControlSet\Services\WOF\Providers\WIM\IntegrityFiles`

## pseudocode

```c
__int64 __fastcall WIMHashFile::ResumeHashWrites(WIMHashFile *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v5; // rsi
  __int64 v6; // r14
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // ebx
  unsigned __int8 *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rsi
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  unsigned int started; // eax
  BYTE Data[4]; // [rsp+50h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-11h] BYREF
  __m128i si128; // [rsp+60h] [rbp-9h] BYREF
  wchar_t Buffer[8]; // [rsp+70h] [rbp+7h] BYREF

  v5 = *((_QWORD *)this + 3);
  v6 = *((_QWORD *)this + 7);
  v7 = (const unsigned __int16 *)*((_QWORD *)this + 18);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(_DWORD *)Data = 0;
  v8 = File::Initialize((File *)&si128, v7, 0x80000000, a4, 0x28000000u, 0);
  if ( v8 )
    goto LABEL_38;
  do
  {
    v5 -= v6;
    if ( !v5 )
    {
      v8 = WIMHashFile::FinalizeHeader(this);
      if ( v8 )
        goto LABEL_38;
      v11 = *((_QWORD *)this + 19);
      *(_DWORD *)Data = 0;
      hKey = 0;
      v12 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Services\\WOF\\Providers\\WIM\\IntegrityFiles",
              0,
              0,
              0,
              2u,
              0,
              &hKey,
              0);
      v8 = v12;
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      if ( !v8 )
      {
        if ( swprintf_s(Buffer, 8u, L"%I64u", v11) < 0 )
        {
          v8 = -2147467259;
        }
        else
        {
          v13 = RegSetValueExW(hKey, Buffer, 0, 4u, Data, 4u);
          v8 = v13;
          if ( v13 > 0 )
            v8 = (unsigned __int16)v13 | 0x80070000;
          if ( !v8 )
          {
            v14 = RegCloseKey(hKey);
            v8 = v14;
            if ( v14 > 0 )
              v8 = (unsigned __int16)v14 | 0x80070000;
            if ( !v8 )
            {
              started = WofStartIntegrity(*((_QWORD *)this + 19));
              v8 = 0;
              if ( started != -2147024553 )
                v8 = started;
              goto LABEL_38;
            }
          }
        }
      }
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_38;
    }
    v8 = File::MoveFilePointer((File *)&si128, *(union _LARGE_INTEGER *)((char *)this + 56));
    if ( v8 )
      goto LABEL_38;
    v8 = File::MoveFilePointer(
           this,
           (union _LARGE_INTEGER)(*((unsigned int *)this + 16) + 16LL * (*((_QWORD *)this + 7) >> 12)));
    if ( v8 )
      goto LABEL_38;
    v6 = (unsigned int)v5;
    if ( v5 >= 0x400000 )
      v6 = 0x400000;
    v8 = File::Read((File *)&si128, qword_18000D000, 0x400000u, (unsigned int *)Data);
    if ( v8 )
      goto LABEL_38;
    if ( *(_DWORD *)Data != (_DWORD)v6 )
    {
      v8 = -2147023900;
      goto LABEL_38;
    }
    v8 = WIMHashFile::HashWimBlock(this, v9, v6);
    if ( !v8 )
    {
      *((_QWORD *)this + 7) += v6;
      hKey = 0;
      v8 = WIMHashFile::Hash(this, (unsigned __int8 *)this + 16, v10, (unsigned __int8 *)this + 100);
      if ( !v8 )
      {
        v8 = File::Flush(this);
        if ( !v8 )
        {
          v8 = File::MoveFilePointer(this, (union _LARGE_INTEGER)hKey);
          if ( !v8 )
            v8 = File::Write(this, (char *)this + 16, 0x74u);
        }
      }
      if ( !v8 )
        continue;
    }
    goto LABEL_38;
  }
  while ( _InterlockedCompareExchange((volatile signed __int32 *)&ExitFlag, 0, 0) != 1 );
  v8 = File::Flush(this);
  if ( !v8 )
    LogFileOffset(&WofTaskPauseHashFileEventId, *((const unsigned __int16 **)this + 1), *((_QWORD *)this + 7));
LABEL_38:
  File::~File((File *)&si128);
  return v8;
}

```

## disassembly

```asm
0x180002474  push    rbp
0x180002476  push    rbx
0x180002477  push    rsi
0x180002478  push    rdi
0x180002479  push    r14
0x18000247b  push    r15
0x18000247d  lea     rbp, [rsp-2Fh]
0x180002482  sub     rsp, 98h
0x180002489  mov     rax, cs:__security_cookie
0x180002490  xor     rax, rsp
0x180002493  mov     [rbp+57h+var_40], rax
0x180002497  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x18000249f  mov     rdi, rcx
0x1800024a2  mov     rsi, [rcx+18h]
0x1800024a6  mov     r8d, 80000000h; unsigned int
0x1800024ac  mov     r14, [rcx+38h]
0x1800024b0  mov     rdx, [rcx+90h]; unsigned __int16 *
0x1800024b7  lea     rcx, [rbp+57h+var_60]; this
0x1800024bb  mov     qword ptr [rsp+0C0h+samDesired], 0; int *
0x1800024c4  movdqu  [rbp+57h+var_60], xmm0
0x1800024c9  mov     dword ptr [rbp+57h+Data], 0
0x1800024d0  mov     [rsp+0C0h+dwOptions], 28000000h; unsigned int
0x1800024d8  call    ?Initialize@File@@QEAAJPEBGKKKPEAH@Z; File::Initialize(ushort const *,ulong,ulong,ulong,int *)
0x1800024dd  mov     ebx, eax
0x1800024df  test    eax, eax
0x1800024e1  jnz     loc_180002738
0x1800024e7  jmp     loc_1800025ED
0x1800024ec  mov     rdx, [rdi+38h]; union _LARGE_INTEGER
0x1800024f0  lea     rcx, [rbp+57h+var_60]; this
0x1800024f4  call    ?MoveFilePointer@File@@QEAAJT_LARGE_INTEGER@@@Z; File::MoveFilePointer(_LARGE_INTEGER)
0x1800024f9  mov     ebx, eax
0x1800024fb  test    eax, eax
0x1800024fd  jnz     loc_180002738
0x180002503  mov     rdx, [rdi+38h]
0x180002507  mov     rcx, rdi; this
0x18000250a  mov     eax, [rdi+40h]
0x18000250d  shr     rdx, 0Ch
0x180002511  shl     rdx, 4
0x180002515  add     rdx, rax; union _LARGE_INTEGER
0x180002518  call    ?MoveFilePointer@File@@QEAAJT_LARGE_INTEGER@@@Z; File::MoveFilePointer(_LARGE_INTEGER)
0x18000251d  mov     ebx, eax
0x18000251f  test    eax, eax
0x180002521  jnz     loc_180002738
0x180002527  mov     r14d, esi
0x18000252a  cmp     rsi, 400000h
0x180002531  jb      short loc_180002539
0x180002533  mov     r14d, 400000h
0x180002539  lea     r9, [rbp+57h+Data]; unsigned int *
0x18000253d  mov     r8d, 400000h; unsigned int
0x180002543  lea     rdx, qword_18000D000; void *
0x18000254a  lea     rcx, [rbp+57h+var_60]; this
0x18000254e  call    ?Read@File@@QEAAJPEAXKPEAK@Z; File::Read(void *,ulong,ulong *)
0x180002553  mov     ebx, eax
0x180002555  test    eax, eax
0x180002557  jnz     loc_180002738
0x18000255d  cmp     dword ptr [rbp+57h+Data], r14d
0x180002561  jnz     loc_180002703
0x180002567  mov     r8d, r14d; unsigned int
0x18000256a  mov     rcx, rdi; this
0x18000256d  call    ?HashWimBlock@WIMHashFile@@AEAAJPEAEK@Z; WIMHashFile::HashWimBlock(uchar *,ulong)
0x180002572  mov     ebx, eax
0x180002574  test    eax, eax
0x180002576  jnz     loc_180002738
0x18000257c  add     [rdi+38h], r14
0x180002580  lea     r9, [rdi+64h]; unsigned __int8 *
0x180002584  lea     rdx, [rdi+10h]; unsigned __int8 *
0x180002588  mov     [rbp+57h+hKey], 0
0x180002590  mov     rcx, rdi; this
0x180002593  call    ?Hash@WIMHashFile@@QEAAJPEAEK0@Z; WIMHashFile::Hash(uchar *,ulong,uchar *)
0x180002598  mov     ebx, eax
0x18000259a  test    eax, eax
0x18000259c  jnz     short loc_1800025D0
0x18000259e  mov     rcx, rdi; this
0x1800025a1  call    ?Flush@File@@QEAAJXZ; File::Flush(void)
0x1800025a6  mov     ebx, eax
0x1800025a8  test    eax, eax
0x1800025aa  jnz     short loc_1800025D0
0x1800025ac  mov     rdx, [rbp+57h+hKey]; union _LARGE_INTEGER
0x1800025b0  mov     rcx, rdi; this
0x1800025b3  call    ?MoveFilePointer@File@@QEAAJT_LARGE_INTEGER@@@Z; File::MoveFilePointer(_LARGE_INTEGER)
0x1800025b8  mov     ebx, eax
0x1800025ba  test    eax, eax
0x1800025bc  jnz     short loc_1800025D0
0x1800025be  lea     r8d, [rax+74h]; unsigned int
0x1800025c2  mov     rcx, rdi; this
0x1800025c5  lea     rdx, [rdi+10h]; void *
0x1800025c9  call    ?Write@File@@QEAAJPEAXK@Z; File::Write(void *,ulong)
0x1800025ce  mov     ebx, eax
0x1800025d0  test    ebx, ebx
0x1800025d2  jnz     loc_180002738
0x1800025d8  xor     ecx, ecx
0x1800025da  xor     eax, eax
0x1800025dc  lock cmpxchg cs:?ExitFlag@@3KA, ecx; ulong ExitFlag
0x1800025e4  cmp     eax, 1
0x1800025e7  jz      loc_1800026DF
0x1800025ed  sub     rsi, r14
0x1800025f0  jnz     loc_1800024EC
0x1800025f6  mov     rcx, rdi; this
0x1800025f9  call    ?FinalizeHeader@WIMHashFile@@AEAAJXZ; WIMHashFile::FinalizeHeader(void)
0x1800025fe  mov     ebx, eax
0x180002600  test    eax, eax
0x180002602  jnz     loc_180002738
0x180002608  mov     rsi, [rdi+98h]
0x18000260f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\WO"...
0x180002616  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x18000261f  xor     r9d, r9d; lpClass
0x180002622  mov     dword ptr [rbp+57h+Data], eax
0x180002625  xor     r8d, r8d; Reserved
0x180002628  lea     rax, [rbp+57h+hKey]
0x18000262c  mov     [rbp+57h+hKey], 0
0x180002634  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180002639  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002640  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180002649  mov     [rsp+0C0h+samDesired], 2; samDesired
0x180002651  mov     [rsp+0C0h+dwOptions], ebx; dwOptions
0x180002655  call    cs:__imp_RegCreateKeyExW
0x18000265b  mov     ebx, eax
0x18000265d  mov     r14d, 80070000h
0x180002663  test    eax, eax
0x180002665  jle     short loc_18000266D
0x180002667  movzx   ebx, ax
0x18000266a  or      ebx, r14d
0x18000266d  test    ebx, ebx
0x18000266f  jnz     loc_18000270F
0x180002675  mov     r9, rsi
0x180002678  lea     r8, aI64u; "%I64u"
0x18000267f  lea     edx, [rbx+8]; BufferCount
0x180002682  lea     rcx, [rbp+57h+Buffer]; Buffer
0x180002686  call    cs:__imp_swprintf_s
0x18000268c  test    eax, eax
0x18000268e  js      short loc_18000270A
0x180002690  mov     rcx, [rbp+57h+hKey]; hKey
0x180002694  lea     r9d, [rbx+4]; dwType
0x180002698  lea     rax, [rbp+57h+Data]
0x18000269c  mov     [rsp+0C0h+samDesired], r9d; cbData
0x1800026a1  xor     r8d, r8d; Reserved
0x1800026a4  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x1800026a9  lea     rdx, [rbp+57h+Buffer]; lpValueName
0x1800026ad  call    cs:__imp_RegSetValueExW
0x1800026b3  mov     ebx, eax
0x1800026b5  test    eax, eax
0x1800026b7  jle     short loc_1800026BF
0x1800026b9  movzx   ebx, ax
0x1800026bc  or      ebx, r14d
0x1800026bf  test    ebx, ebx
0x1800026c1  jnz     short loc_18000270F
0x1800026c3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800026c7  call    cs:__imp_RegCloseKey
0x1800026cd  mov     ebx, eax
0x1800026cf  test    eax, eax
0x1800026d1  jle     short loc_1800026D9
0x1800026d3  movzx   ebx, ax
0x1800026d6  or      ebx, r14d
0x1800026d9  test    ebx, ebx
0x1800026db  jz      short loc_180002722
0x1800026dd  jmp     short loc_18000270F
0x1800026df  mov     rcx, rdi; this
0x1800026e2  call    ?Flush@File@@QEAAJXZ; File::Flush(void)
0x1800026e7  mov     ebx, eax
0x1800026e9  test    eax, eax
0x1800026eb  jnz     short loc_180002738
0x1800026ed  mov     r8, [rdi+38h]; unsigned __int64
0x1800026f1  lea     rcx, WofTaskPauseHashFileEventId; EventDescriptor
0x1800026f8  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800026fc  call    ?LogFileOffset@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG_K@Z; LogFileOffset(_EVENT_DESCRIPTOR const *,ushort const *,unsigned __int64)
0x180002701  jmp     short loc_180002738
0x180002703  mov     ebx, 800703E4h
0x180002708  jmp     short loc_180002738
0x18000270a  mov     ebx, 80004005h
0x18000270f  mov     rcx, [rbp+57h+hKey]; hKey
0x180002713  test    rcx, rcx
0x180002716  jz      short loc_18000271E
0x180002718  call    cs:__imp_RegCloseKey
0x18000271e  test    ebx, ebx
0x180002720  jnz     short loc_180002738
0x180002722  mov     rcx, [rdi+98h]
0x180002729  call    WofStartIntegrity
0x18000272e  xor     ebx, ebx
0x180002730  cmp     eax, 80070157h
0x180002735  cmovnz  ebx, eax
0x180002738  lea     rcx, [rbp+57h+var_60]; this
0x18000273c  call    ??1File@@QEAA@XZ; File::~File(void)
0x180002741  mov     eax, ebx
0x180002743  mov     rcx, [rbp+57h+var_40]
0x180002747  xor     rcx, rsp; StackCookie
0x18000274a  call    __security_check_cookie
0x18000274f  add     rsp, 98h
0x180002756  pop     r15
0x180002758  pop     r14
0x18000275a  pop     rdi
0x18000275b  pop     rsi
0x18000275c  pop     rbx
0x18000275d  pop     rbp
0x18000275e  retn
```
