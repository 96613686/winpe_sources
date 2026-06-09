# GetVirtualDiskState(WSTRING *,WSTRING *,ulong)

- ea: `0x180002510`
- end: `0x180002723`
- name: `?GetVirtualDiskState@@YAEPEAVWSTRING@@0K@Z`
- size: `531`
- prototype: `unsigned __int8 __fastcall(struct WSTRING *, struct WSTRING *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800015d0`

## callees

- `0x180002510`
- `0x180009752`
- `0x180009780`

## import_xrefs

- `ntdll!NtClose` at `0x1800026ba`
- `ntdll!NtClose` at `0x1800026ba`
- `ntdll!NtOpenFile` at `0x180002644`
- `ntdll!NtOpenFile` at `0x180002644`
- `ntdll!NtFsControlFile` at `0x1800026ad`
- `ntdll!NtFsControlFile` at `0x1800026ad`
- `ulib!?Initialize@WSTRING@@QEAAEXZ` at `0x18000257e`
- `ulib!?Initialize@WSTRING@@QEAAEXZ` at `0x18000257e`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x18000259d`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x18000259d`
- `ulib!?Strcat@WSTRING@@QEAAEPEBV1@@Z` at `0x1800025b2`
- `ulib!?Strcat@WSTRING@@QEAAEPEBV1@@Z` at `0x1800025c8`
- `ulib!?Strcat@WSTRING@@QEAAEPEBV1@@Z` at `0x1800025b2`
- `ulib!?Strcat@WSTRING@@QEAAEPEBV1@@Z` at `0x1800025c8`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002565`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x18000256f`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002565`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x18000256f`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x1800026c8`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x1800026d2`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000270f`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002719`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x1800026c8`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x1800026d2`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000270f`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002719`
- `ulib!?GetWSTR@WSTRING@@QEBAPEBGXZ` at `0x1800025f3`
- `ulib!?GetWSTR@WSTRING@@QEBAPEBGXZ` at `0x1800025f3`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800025dc`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800025dc`

## pseudocode

```c
bool __fastcall GetVirtualDiskState(struct WSTRING *a1, struct WSTRING *a2, int a3)
{
  bool v5; // bl
  NTSTATUS v6; // edi
  __int64 InputBuffer; // [rsp+50h] [rbp-B0h] BYREF
  void *FileHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v10; // [rsp+60h] [rbp-A0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-90h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v13[48]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v14[48]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD OutputBuffer[68]; // [rsp+110h] [rbp+10h] BYREF

  v10 = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  DSTRING::DSTRING((DSTRING *)v13);
  DSTRING::DSTRING((DSTRING *)v14);
  InputBuffer = 0;
  if ( WSTRING::Initialize((WSTRING *)v13)
    && WSTRING::Initialize((WSTRING *)v14, L"\\", 0xFFFFFFFF)
    && WSTRING::Strcat((WSTRING *)v13, a2)
    && WSTRING::Strcat((WSTRING *)v13, (const struct WSTRING *)v14) )
  {
    v5 = 0;
    LOWORD(v10) = 2 * WSTRING::QueryChCount((WSTRING *)v13);
    WORD1(v10) = v10;
    *((_QWORD *)&v10 + 1) = WSTRING::GetWSTR((WSTRING *)v13);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v10;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x11u) >= 0 )
    {
      memset_0(OutputBuffer, 0, 0x10Cu);
      LODWORD(InputBuffer) = 1;
      HIDWORD(InputBuffer) = a3;
      v6 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x901F0u, &InputBuffer, 8u, OutputBuffer, 0x10Cu);
      NtClose(FileHandle);
      if ( v6 >= 0 && OutputBuffer[0] == 1 )
        v5 = OutputBuffer[1] != 0;
    }
    DSTRING::~DSTRING((DSTRING *)v14);
    DSTRING::~DSTRING((DSTRING *)v13);
    return v5;
  }
  else
  {
    DSTRING::~DSTRING((DSTRING *)v14);
    DSTRING::~DSTRING((DSTRING *)v13);
    return 0;
  }
}

```

## disassembly

```asm
0x180002510  mov     [rsp-8+arg_0], rbx
0x180002515  push    rbp
0x180002516  push    rsi
0x180002517  push    rdi
0x180002518  lea     rbp, [rsp-130h]
0x180002520  sub     rsp, 230h
0x180002527  mov     rax, cs:__security_cookie
0x18000252e  xor     rax, rsp
0x180002531  mov     [rbp+140h+var_20], rax
0x180002538  xorps   xmm1, xmm1
0x18000253b  lea     rcx, [rbp+140h+var_190]
0x18000253f  xorps   xmm0, xmm0
0x180002542  xor     esi, esi
0x180002544  movups  [rsp+240h+var_1E0], xmm0
0x180002549  mov     [rsp+240h+FileHandle], rsi
0x18000254e  mov     edi, r8d
0x180002551  movups  xmmword ptr [rbp+140h+ObjectAttributes.Length], xmm1
0x180002555  mov     rbx, rdx
0x180002558  movups  xmmword ptr [rbp+140h+ObjectAttributes.ObjectName], xmm1
0x18000255c  movups  xmmword ptr [rbp+140h+ObjectAttributes.SecurityDescriptor], xmm1
0x180002560  movups  xmmword ptr [rsp+240h+IoStatusBlock], xmm0
0x180002565  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x18000256b  lea     rcx, [rbp+140h+var_160]
0x18000256f  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180002575  lea     rcx, [rbp+140h+var_190]
0x180002579  mov     [rsp+240h+var_1F0], rsi
0x18000257e  call    cs:__imp_?Initialize@WSTRING@@QEAAEXZ; WSTRING::Initialize(void)
0x180002584  test    al, al
0x180002586  jz      loc_18000270B
0x18000258c  mov     r8d, 0FFFFFFFFh
0x180002592  lea     rdx, asc_18000BB4C; "\\"
0x180002599  lea     rcx, [rbp+140h+var_160]
0x18000259d  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x1800025a3  test    al, al
0x1800025a5  jz      loc_18000270B
0x1800025ab  mov     rdx, rbx
0x1800025ae  lea     rcx, [rbp+140h+var_190]
0x1800025b2  call    cs:__imp_?Strcat@WSTRING@@QEAAEPEBV1@@Z; WSTRING::Strcat(WSTRING const *)
0x1800025b8  test    al, al
0x1800025ba  jz      loc_18000270B
0x1800025c0  lea     rdx, [rbp+140h+var_160]
0x1800025c4  lea     rcx, [rbp+140h+var_190]
0x1800025c8  call    cs:__imp_?Strcat@WSTRING@@QEAAEPEBV1@@Z; WSTRING::Strcat(WSTRING const *)
0x1800025ce  test    al, al
0x1800025d0  jz      loc_18000270B
0x1800025d6  lea     rcx, [rbp+140h+var_190]
0x1800025da  xor     bl, bl
0x1800025dc  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x1800025e2  add     ax, ax
0x1800025e5  lea     rcx, [rbp+140h+var_190]
0x1800025e9  mov     word ptr [rsp+240h+var_1E0], ax
0x1800025ee  mov     word ptr [rsp+240h+var_1E0+2], ax
0x1800025f3  call    cs:__imp_?GetWSTR@WSTRING@@QEBAPEBGXZ; WSTRING::GetWSTR(void)
0x1800025f9  xorps   xmm0, xmm0
0x1800025fc  mov     [rsp+240h+OpenOptions], 11h; OpenOptions
0x180002604  mov     qword ptr [rsp+240h+var_1E0+8], rax
0x180002609  lea     r9, [rsp+240h+IoStatusBlock]; IoStatusBlock
0x18000260e  lea     rax, [rsp+240h+var_1E0]
0x180002613  mov     [rbp+140h+ObjectAttributes.Length], 30h ; '0'
0x18000261a  lea     r8, [rbp+140h+ObjectAttributes]; ObjectAttributes
0x18000261e  mov     [rbp+140h+ObjectAttributes.ObjectName], rax
0x180002622  mov     edx, 100080h; DesiredAccess
0x180002627  mov     [rbp+140h+ObjectAttributes.RootDirectory], rsi
0x18000262b  lea     rcx, [rsp+240h+FileHandle]; FileHandle
0x180002630  mov     [rbp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x180002637  movdqu  xmmword ptr [rbp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000263c  mov     [rsp+240h+ShareAccess], 7; ShareAccess
0x180002644  call    cs:__imp_NtOpenFile
0x18000264a  test    eax, eax
0x18000264c  js      short loc_1800026C4
0x18000264e  xor     edx, edx; Val
0x180002650  lea     rcx, [rbp+140h+var_130]; void *
0x180002654  mov     r8d, 10Ch; Size
0x18000265a  call    memset_0
0x18000265f  mov     rcx, [rsp+240h+FileHandle]; FileHandle
0x180002664  lea     rax, [rbp+140h+var_130]
0x180002668  mov     [rsp+240h+OutputBufferLength], 10Ch; OutputBufferLength
0x180002670  xor     r9d, r9d; ApcContext
0x180002673  mov     [rsp+240h+OutputBuffer], rax; OutputBuffer
0x180002678  xor     r8d, r8d; ApcRoutine
0x18000267b  mov     [rsp+240h+InputBufferLength], 8; InputBufferLength
0x180002683  lea     rax, [rsp+240h+var_1F0]
0x180002688  mov     [rsp+240h+InputBuffer], rax; InputBuffer
0x18000268d  xor     edx, edx; Event
0x18000268f  lea     rax, [rsp+240h+IoStatusBlock]
0x180002694  mov     [rsp+240h+OpenOptions], 901F0h; FsControlCode
0x18000269c  mov     qword ptr [rsp+240h+ShareAccess], rax; IoStatusBlock
0x1800026a1  mov     dword ptr [rsp+240h+var_1F0], 1
0x1800026a9  mov     dword ptr [rsp+240h+var_1F0+4], edi
0x1800026ad  call    cs:__imp_NtFsControlFile
0x1800026b3  mov     rcx, [rsp+240h+FileHandle]; Handle
0x1800026b8  mov     edi, eax
0x1800026ba  call    cs:__imp_NtClose
0x1800026c0  test    edi, edi
0x1800026c2  jns     short loc_1800026FD
0x1800026c4  lea     rcx, [rbp+140h+var_160]
0x1800026c8  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x1800026ce  lea     rcx, [rbp+140h+var_190]
0x1800026d2  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x1800026d8  movzx   eax, bl
0x1800026db  mov     rcx, [rbp+140h+var_20]
0x1800026e2  xor     rcx, rsp; StackCookie
0x1800026e5  call    __security_check_cookie
0x1800026ea  mov     rbx, [rsp+240h+arg_0]
0x1800026f2  add     rsp, 230h
0x1800026f9  pop     rdi
0x1800026fa  pop     rsi
0x1800026fb  pop     rbp
0x1800026fc  retn
0x1800026fd  cmp     [rbp+140h+var_130], 1
0x180002701  jnz     short loc_1800026C4
0x180002703  cmp     [rbp+140h+var_12C], esi
0x180002706  setnbe  bl
0x180002709  jmp     short loc_1800026C4
0x18000270b  lea     rcx, [rbp+140h+var_160]
0x18000270f  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002715  lea     rcx, [rbp+140h+var_190]
0x180002719  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x18000271f  xor     al, al
0x180002721  jmp     short loc_1800026DB
```
