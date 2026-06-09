# CreateDevice(ushort const *,ushort const *,ulong,int,CreateStorageDeviceFlags,_GUID const *,char const *,ulong,_GUID const *)

- ea: `0x140087488`
- end: `0x14008791c`
- name: `?CreateDevice@@YAPEAXPEBG0KHW4CreateStorageDeviceFlags@@PEBU_GUID@@PEBDK2@Z`
- size: `1172`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140086c0c`
- `0x140116f74`

## callees

- `0x140086dec`
- `0x140087488`
- `0x140087924`
- `0x140132940`
- `0x1401335fc`
- `0x140135935`
- `0x1401b6b40`
- `0x1401b6cfc`
- `0x1401b74b0`
- `0x1401b78d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400878af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400878af`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140087688`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140087688`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400878bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400878bd`
- `ntdll!RtlNtStatusToDosError` at `0x1400875d8`
- `ntdll!RtlNtStatusToDosError` at `0x14008770e`
- `ntdll!RtlNtStatusToDosError` at `0x140087869`
- `ntdll!RtlNtStatusToDosError` at `0x1400875d8`
- `ntdll!RtlNtStatusToDosError` at `0x14008770e`
- `ntdll!RtlNtStatusToDosError` at `0x140087869`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1400875c6`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1400875c6`
- `ntdll!RtlFreeUnicodeString` at `0x140087897`
- `ntdll!RtlFreeUnicodeString` at `0x140087897`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400876fc`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400876fc`
- `ntdll!NtCreateFile` at `0x14008781c`
- `ntdll!NtCreateFile` at `0x14008781c`

## string_xrefs

- `0x1400877a1`: `VstorCreateDevice_CreateFile`
- `0x14008752e`: `VstorCreateDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CreateDevice(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        struct _GUID *a6,
        char *a7,
        unsigned int a8,
        struct _GUID *a9)
{
  char *v13; // r15
  __int64 v14; // rdi
  signed int v15; // ebx
  unsigned int v16; // r12d
  const wchar_t *v17; // r13
  int inited; // eax
  PWSTR Buffer; // r14
  __int16 v20; // cx
  int v21; // eax
  __int64 v22; // rbx
  size_t v23; // rbx
  char *v24; // rsi
  __int64 v25; // rbx
  int v26; // edi
  void *v27; // rbx
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-88h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  int EaBuffer; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v35; // [rsp+C4h] [rbp-3Ch]
  struct _GUID v36; // [rsp+D4h] [rbp-2Ch]
  __int64 v37; // [rsp+E4h] [rbp-1Ch]
  _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v40[42]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v41[42]; // [rsp+260h] [rbp+160h] BYREF

  FileHandle = (void *)-1LL;
  UnicodeString = 0;
  v13 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  EaBuffer = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  memset_0(v40, 0, sizeof(v40));
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v40);
  v40[0] = &VstorlibTraceProvider::VstorCreateDevice::`vftable';
  VstorlibTraceProvider::VstorCreateDevice::StartActivity(
    (VstorlibTraceProvider::VstorCreateDevice *)v40,
    a1,
    (const unsigned __int16 *)a2,
    a3,
    a4,
    a5,
    a6,
    a7,
    a8,
    a9);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a2 + 2 * v14) );
  if ( !v14 )
  {
    v15 = 87;
    goto LABEL_37;
  }
  v16 = 0;
  v17 = 0;
  if ( a4 )
  {
    inited = RtlDosPathNameToNtPathName_U_WithStatus(a2, &UnicodeString, 0, 0);
    if ( inited < 0 )
    {
LABEL_27:
      v15 = RtlNtStatusToDosError(inited);
      goto LABEL_37;
    }
    LODWORD(v14) = UnicodeString.Length >> 1;
    Buffer = UnicodeString.Buffer;
  }
  else if ( (unsigned int)v14 > 2 && *(_WORD *)a2 == 92 && (Buffer = (PWSTR)(a2 + 2), *(_WORD *)(a2 + 2) == 92) )
  {
    v20 = *(_WORD *)(a2 + 4);
    v21 = v14 - 1;
    if ( v20 == 63 )
      v21 = v14;
    LODWORD(v14) = v21;
    if ( v20 == 63 )
      Buffer = (PWSTR)a2;
    v16 = v20 != 63 ? 7 : 0;
    v17 = L"\\\\?\\UNC";
    if ( v20 == 63 )
      v17 = 0;
  }
  else
  {
    Buffer = (PWSTR)a2;
    if ( (unsigned int)v14 > 0x104 )
    {
      v16 = 4;
      v17 = L"\\\\?\\";
    }
  }
  v22 = -1;
  do
    ++v22;
  while ( a1[v22] );
  v13 = (char *)malloc(saturated_mul((unsigned int)v22 + v16 + (_DWORD)v14 + 1, 2u));
  if ( !v13 )
  {
    v15 = 14;
    goto LABEL_37;
  }
  v23 = 2LL * (unsigned int)v22;
  memcpy_0(v13, a1, v23);
  v24 = &v13[v23];
  if ( v16 )
  {
    memcpy_0(v24, v17, 2LL * v16);
    v24 += 2 * v16;
  }
  memcpy_0(v24, Buffer, 2LL * (unsigned int)v14);
  *(_WORD *)&v24[2 * (unsigned int)v14] = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)v13);
  if ( inited < 0 )
    goto LABEL_27;
  BYTE1(v35) = 10;
  WORD1(v35) = 25;
  *(_QWORD *)((char *)&v35 + 4) = *(_QWORD *)"StorVsp-v2";
  *(_DWORD *)((char *)&v35 + 11) = *(_DWORD *)"-v2";
  HIDWORD(v37) = a5;
  if ( a6 )
  {
    v36 = *a6;
    LOBYTE(v37) = 1;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  memset_0(v41, 0, sizeof(v41));
  v25 = v40[34];
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v41);
  v41[0] = &VstorlibTraceProvider::VstorCreateDevice_CreateFile::`vftable';
  VstorlibTraceProvider::VstorCreateDevice_CreateFile::StartActivity(
    (VstorlibTraceProvider::VstorCreateDevice_CreateFile *)v41,
    &DestinationString,
    a6,
    (const struct _GUID *)(v25 + 8));
  v26 = NtCreateFile(&FileHandle, a3, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 2u, 0x40u, &EaBuffer, 0x2Cu);
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v41,
    (v26 | 0x10000000) & (unsigned int)-(v26 != 0));
  VstorlibTraceProvider::VstorCreateDevice_CreateFile::~VstorCreateDevice_CreateFile((VstorlibTraceProvider::VstorCreateDevice_CreateFile *)v41);
  if ( v26 >= 0 )
  {
    v15 = 0;
  }
  else if ( v26 == -1073741808 || v26 == -1073741766 )
  {
    v15 = -1069940716;
  }
  else
  {
    v15 = RtlNtStatusToDosError(v26);
    if ( v15 == 317 )
      v15 = v26;
  }
LABEL_37:
  if ( UnicodeString.Buffer )
  {
    RtlFreeUnicodeString(&UnicodeString);
    UnicodeString.Buffer = 0;
  }
  if ( v13 )
    free(v13);
  SetLastError(v15);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v40, (unsigned int)v15);
  v27 = FileHandle;
  VstorlibTraceProvider::VstorCreateDevice::~VstorCreateDevice((VstorlibTraceProvider::VstorCreateDevice *)v40);
  return v27;
}

```

## disassembly

```asm
0x140087488  mov     [rsp-8+arg_18], rbx
0x14008748d  push    rbp
0x14008748e  push    rsi
0x14008748f  push    rdi
0x140087490  push    r12
0x140087492  push    r13
0x140087494  push    r14
0x140087496  push    r15
0x140087498  lea     rbp, [rsp-2C0h]
0x1400874a0  sub     rsp, 3C0h
0x1400874a7  mov     rax, cs:__security_cookie
0x1400874ae  xor     rax, rsp
0x1400874b1  mov     [rbp+2F0h+var_40], rax
0x1400874b8  mov     r14d, r9d
0x1400874bb  mov     r13d, r8d
0x1400874be  mov     [rsp+3F0h+DesiredAccess], r8d
0x1400874c3  mov     rsi, rdx
0x1400874c6  mov     r12, rcx
0x1400874c9  mov     [rsp+3F0h+Src], rcx
0x1400874ce  mov     rdi, [rbp+2F0h+arg_28]
0x1400874d5  mov     [rsp+3F0h+var_380], rdi
0x1400874da  mov     rbx, [rbp+2F0h+arg_30]
0x1400874e1  mov     [rbp+2F0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400874e9  xorps   xmm0, xmm0
0x1400874ec  movups  xmmword ptr [rsp+3F0h+UnicodeString.Length], xmm0
0x1400874f1  xor     eax, eax
0x1400874f3  mov     r15d, eax
0x1400874f6  movups  xmmword ptr [rbp+2F0h+DestinationString.Length], xmm0
0x1400874fa  xorps   xmm1, xmm1
0x1400874fd  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.Length], xmm1
0x140087501  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.ObjectName], xmm1
0x140087505  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x140087509  movups  xmmword ptr [rbp+2F0h+IoStatusBlock], xmm0
0x14008750d  mov     [rbp+2F0h+var_330], eax
0x140087510  movups  [rbp+2F0h+var_32C], xmm1
0x140087514  movups  [rbp+2F0h+var_31C], xmm1
0x140087518  mov     [rbp+2F0h+var_30C], rax
0x14008751c  xor     edx, edx; Val
0x14008751e  mov     r8d, 150h; Size
0x140087524  lea     rcx, [rbp+2F0h+var_2E0]; void *
0x140087528  call    memset_0
0x14008752d  nop
0x14008752e  lea     rdx, aVstorcreatedev_2; "VstorCreateDevice"
0x140087535  lea     rcx, [rbp+2F0h+var_2E0]; struct wil::details::IFailureCallback *
0x140087539  call    ??0?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14008753e  lea     rax, ??_7VstorCreateDevice@VstorlibTraceProvider@@6B@; const VstorlibTraceProvider::VstorCreateDevice::`vftable'
0x140087545  mov     [rbp+2F0h+var_2E0], rax
0x140087549  mov     rax, [rbp+2F0h+arg_40]
0x140087550  mov     [rsp+3F0h+EaBuffer], rax; struct _GUID *
0x140087555  mov     eax, [rbp+2F0h+arg_38]
0x14008755b  mov     [rsp+3F0h+CreateOptions], eax; unsigned int
0x14008755f  mov     qword ptr [rsp+3F0h+CreateDisposition], rbx; char *
0x140087564  mov     qword ptr [rsp+3F0h+ShareAccess], rdi; struct _GUID *
0x140087569  mov     eax, [rbp+2F0h+arg_20]
0x14008756f  mov     [rsp+3F0h+FileAttributes], eax; unsigned int
0x140087573  mov     dword ptr [rsp+3F0h+AllocationSize], r14d; int
0x140087578  mov     r9d, r13d; unsigned int
0x14008757b  mov     r8, rsi; unsigned __int16 *
0x14008757e  mov     rdx, r12; unsigned __int16 *
0x140087581  lea     rcx, [rbp+2F0h+var_2E0]; this
0x140087585  call    ?StartActivity@VstorCreateDevice@VstorlibTraceProvider@@QEAAXPEBG0KHIPEBU_GUID@@PEBDK1@Z; VstorlibTraceProvider::VstorCreateDevice::StartActivity(ushort const *,ushort const *,ulong,int,uint,_GUID const *,char const *,ulong,_GUID const *)
0x14008758a  nop
0x14008758b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14008758f  mov     rdi, r8
0x140087592  xor     ebx, ebx
0x140087594  inc     rdi
0x140087597  cmp     [rsi+rdi*2], bx
0x14008759b  jnz     short loc_140087594
0x14008759d  test    rdi, rdi
0x1400875a0  jnz     short loc_1400875AD
0x1400875a2  lea     ebx, [rdi+57h]
0x1400875a5  xor     r14d, r14d
0x1400875a8  jmp     loc_14008788C
0x1400875ad  mov     r12d, ebx
0x1400875b0  mov     r13, rbx
0x1400875b3  test    r14d, r14d
0x1400875b6  jz      short loc_1400875F9
0x1400875b8  xor     r9d, r9d
0x1400875bb  xor     r8d, r8d
0x1400875be  lea     rdx, [rsp+3F0h+UnicodeString]
0x1400875c3  mov     rcx, rsi
0x1400875c6  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1400875cd  nop     dword ptr [rax+rax+00h]
0x1400875d2  test    eax, eax
0x1400875d4  jns     short loc_1400875E8
0x1400875d6  mov     ecx, eax; Status
0x1400875d8  call    cs:__imp_RtlNtStatusToDosError
0x1400875df  nop     dword ptr [rax+rax+00h]
0x1400875e4  mov     ebx, eax
0x1400875e6  jmp     short loc_1400875A5
0x1400875e8  movzx   edi, [rsp+3F0h+UnicodeString.Length]
0x1400875ed  shr     edi, 1
0x1400875ef  mov     r14, [rbp+2F0h+UnicodeString.Buffer]
0x1400875f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400875f7  jmp     short loc_14008765E
0x1400875f9  cmp     edi, 2
0x1400875fc  jbe     short loc_140087646
0x1400875fe  cmp     word ptr [rsi], 5Ch ; '\'
0x140087602  jnz     short loc_140087646
0x140087604  lea     r14, [rsi+2]
0x140087608  cmp     word ptr [r14], 5Ch ; '\'
0x14008760d  jnz     short loc_140087646
0x14008760f  movzx   ecx, word ptr [rsi+4]
0x140087613  lea     eax, [rdi-1]
0x140087616  mov     dx, 3Fh ; '?'
0x14008761a  cmp     cx, dx
0x14008761d  cmovz   eax, edi
0x140087620  mov     edi, eax
0x140087622  cmovz   r14, rsi
0x140087626  movzx   eax, cx
0x140087629  sub     ax, dx
0x14008762c  neg     ax
0x14008762f  sbb     r12d, r12d
0x140087632  and     r12d, 7
0x140087636  lea     r13, aUnc; "\\\\?\\UNC"
0x14008763d  cmp     cx, dx
0x140087640  cmovz   r13, rbx
0x140087644  jmp     short loc_14008765E
0x140087646  mov     r14, rsi
0x140087649  cmp     edi, 104h
0x14008764f  jbe     short loc_14008765E
0x140087651  mov     r12d, 4
0x140087657  lea     r13, asc_140308630; "\\\\?\\"
0x14008765e  mov     rbx, r8
0x140087661  mov     rsi, [rsp+3F0h+Src]
0x140087666  xor     eax, eax
0x140087668  inc     rbx
0x14008766b  cmp     [rsi+rbx*2], ax
0x14008766f  jnz     short loc_140087668
0x140087671  lea     edx, [rdi+1]
0x140087674  add     edx, r12d
0x140087677  add     edx, ebx
0x140087679  mov     eax, 2
0x14008767e  mul     rdx
0x140087681  cmovb   rax, r8
0x140087685  mov     rcx, rax; Size
0x140087688  call    cs:__imp_malloc
0x14008768f  nop     dword ptr [rax+rax+00h]
0x140087694  mov     r15, rax
0x140087697  test    rax, rax
0x14008769a  jnz     short loc_1400876A4
0x14008769c  lea     ebx, [rax+0Eh]
0x14008769f  jmp     loc_1400875A5
0x1400876a4  mov     eax, ebx
0x1400876a6  lea     rbx, [rax+rax]
0x1400876aa  mov     r8, rbx; Size
0x1400876ad  mov     rdx, rsi; Src
0x1400876b0  mov     rcx, r15; void *
0x1400876b3  call    memcpy_0
0x1400876b8  lea     rsi, [rbx+r15]
0x1400876bc  test    r12d, r12d
0x1400876bf  jz      short loc_1400876D9
0x1400876c1  mov     eax, r12d
0x1400876c4  lea     rbx, [rax+rax]
0x1400876c8  mov     r8, rbx; Size
0x1400876cb  mov     rdx, r13; Src
0x1400876ce  mov     rcx, rsi; void *
0x1400876d1  call    memcpy_0
0x1400876d6  add     rsi, rbx
0x1400876d9  mov     eax, edi
0x1400876db  lea     rbx, [rax+rax]
0x1400876df  mov     r8, rbx; Size
0x1400876e2  mov     rdx, r14; Src
0x1400876e5  mov     rcx, rsi; void *
0x1400876e8  call    memcpy_0
0x1400876ed  xor     r14d, r14d
0x1400876f0  mov     [rbx+rsi], r14w
0x1400876f5  mov     rdx, r15; SourceString
0x1400876f8  lea     rcx, [rbp+2F0h+DestinationString]; DestinationString
0x1400876fc  call    cs:__imp_RtlInitUnicodeStringEx
0x140087703  nop     dword ptr [rax+rax+00h]
0x140087708  test    eax, eax
0x14008770a  jns     short loc_140087721
0x14008770c  mov     ecx, eax; Status
0x14008770e  call    cs:__imp_RtlNtStatusToDosError
0x140087715  nop     dword ptr [rax+rax+00h]
0x14008771a  mov     ebx, eax
0x14008771c  jmp     loc_14008788C
0x140087721  mov     byte ptr [rbp+2F0h+var_32C+1], 0Ah
0x140087725  mov     eax, 19h
0x14008772a  mov     word ptr [rbp+2F0h+var_32C+2], ax
0x14008772e  movsd   xmm0, qword ptr cs:aStorvspV2; "StorVsp-v2"
0x140087736  movsd   qword ptr [rbp+2F0h+var_32C+4], xmm0
0x14008773b  mov     eax, dword ptr cs:aStorvspV2+7; "-v2"
0x140087741  mov     dword ptr [rbp+2F0h+var_32C+0Bh], eax
0x140087744  mov     eax, [rbp+2F0h+arg_20]
0x14008774a  mov     dword ptr [rbp+2F0h+var_30C+4], eax
0x14008774d  mov     rdi, [rsp+3F0h+var_380]
0x140087752  test    rdi, rdi
0x140087755  jz      short loc_140087763
0x140087757  movups  xmm0, xmmword ptr [rdi]
0x14008775a  movdqu  [rbp+2F0h+var_31C], xmm0
0x14008775f  mov     byte ptr [rbp+2F0h+var_30C], 1
0x140087763  mov     [rbp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x14008776a  mov     [rbp+2F0h+ObjectAttributes.RootDirectory], r14
0x14008776e  mov     esi, 40h ; '@'
0x140087773  mov     [rbp+2F0h+ObjectAttributes.Attributes], esi
0x140087776  lea     rax, [rbp+2F0h+DestinationString]
0x14008777a  mov     [rbp+2F0h+ObjectAttributes.ObjectName], rax
0x14008777e  xorps   xmm0, xmm0
0x140087781  movdqu  xmmword ptr [rbp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140087786  xor     edx, edx; Val
0x140087788  mov     r8d, 150h; Size
0x14008778e  lea     rcx, [rbp+2F0h+var_190]; void *
0x140087795  call    memset_0
0x14008779a  mov     rbx, [rbp+2F0h+var_1D0]
0x1400877a1  lea     rdx, aVstorcreatedev_1; "VstorCreateDevice_CreateFile"
0x1400877a8  lea     rcx, [rbp+2F0h+var_190]; struct wil::details::IFailureCallback *
0x1400877af  call    ??0?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400877b4  lea     rax, ??_7VstorCreateDevice_CreateFile@VstorlibTraceProvider@@6B@; const VstorlibTraceProvider::VstorCreateDevice_CreateFile::`vftable'
0x1400877bb  mov     [rbp+2F0h+var_190], rax
0x1400877c2  lea     r9, [rbx+8]; struct _GUID *
0x1400877c6  mov     r8, rdi; struct _GUID *
0x1400877c9  lea     rdx, [rbp+2F0h+DestinationString]; struct _UNICODE_STRING *
0x1400877cd  lea     rcx, [rbp+2F0h+var_190]; this
0x1400877d4  call    ?StartActivity@VstorCreateDevice_CreateFile@VstorlibTraceProvider@@QEAAXAEAU_UNICODE_STRING@@PEBU_GUID@@1@Z; VstorlibTraceProvider::VstorCreateDevice_CreateFile::StartActivity(_UNICODE_STRING &,_GUID const *,_GUID const *)
0x1400877d9  nop
0x1400877da  mov     [rsp+3F0h+EaLength], 2Ch ; ','; EaLength
0x1400877e2  lea     rax, [rbp+2F0h+var_330]
0x1400877e6  mov     [rsp+3F0h+EaBuffer], rax; EaBuffer
0x1400877eb  mov     [rsp+3F0h+CreateOptions], esi; CreateOptions
0x1400877ef  mov     [rsp+3F0h+CreateDisposition], 2; CreateDisposition
0x1400877f7  mov     [rsp+3F0h+ShareAccess], 7; ShareAccess
0x1400877ff  mov     [rsp+3F0h+FileAttributes], 80h; FileAttributes
0x140087807  mov     [rsp+3F0h+AllocationSize], r14; AllocationSize
0x14008780c  lea     r9, [rbp+2F0h+IoStatusBlock]; IoStatusBlock
0x140087810  lea     r8, [rbp+2F0h+ObjectAttributes]; ObjectAttributes
0x140087814  mov     edx, [rsp+3F0h+DesiredAccess]; DesiredAccess
0x140087818  lea     rcx, [rbp+2F0h+FileHandle]; FileHandle
0x14008781c  call    cs:__imp_NtCreateFile
0x140087823  nop     dword ptr [rax+rax+00h]
0x140087828  mov     edi, eax
0x14008782a  mov     ecx, eax
0x14008782c  mov     r8d, eax
0x14008782f  bts     r8d, 1Ch
0x140087834  neg     ecx
0x140087836  sbb     edx, edx
0x140087838  and     edx, r8d
0x14008783b  lea     rcx, [rbp+2F0h+var_190]
0x140087842  call    ?Stop@?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140087847  lea     rcx, [rbp+2F0h+var_190]; this
0x14008784e  call    ??1VstorCreateDevice_CreateFile@VstorlibTraceProvider@@QEAA@XZ; VstorlibTraceProvider::VstorCreateDevice_CreateFile::~VstorCreateDevice_CreateFile(void)
0x140087853  test    edi, edi
0x140087855  jns     short loc_140087889
0x140087857  cmp     edi, 0C0000010h
0x14008785d  jz      short loc_140087882
0x14008785f  cmp     edi, 0C000003Ah
0x140087865  jz      short loc_140087882
0x140087867  mov     ecx, edi; Status
0x140087869  call    cs:__imp_RtlNtStatusToDosError
0x140087870  nop     dword ptr [rax+rax+00h]
0x140087875  mov     ebx, eax
0x140087877  cmp     eax, 13Dh
0x14008787c  jnz     short loc_14008788C
0x14008787e  mov     ebx, edi
0x140087880  jmp     short loc_14008788C
0x140087882  mov     ebx, 0C03A0014h
0x140087887  jmp     short loc_14008788C
0x140087889  mov     ebx, r14d
0x14008788c  cmp     [rbp+2F0h+UnicodeString.Buffer], r14
0x140087890  jz      short loc_1400878A7
0x140087892  lea     rcx, [rsp+3F0h+UnicodeString]; UnicodeString
0x140087897  call    cs:__imp_RtlFreeUnicodeString
0x14008789e  nop     dword ptr [rax+rax+00h]
0x1400878a3  mov     [rbp+2F0h+UnicodeString.Buffer], r14
0x1400878a7  test    r15, r15
0x1400878aa  jz      short loc_1400878BB
0x1400878ac  mov     rcx, r15; Block
0x1400878af  call    cs:__imp_free
0x1400878b6  nop     dword ptr [rax+rax+00h]
0x1400878bb  mov     ecx, ebx; dwErrCode
0x1400878bd  call    cs:__imp_SetLastError
0x1400878c4  nop     dword ptr [rax+rax+00h]
0x1400878c9  test    ebx, ebx
0x1400878cb  jle     short loc_1400878D6
0x1400878cd  movzx   ebx, bx
0x1400878d0  or      ebx, 80070000h
0x1400878d6  mov     edx, ebx
0x1400878d8  lea     rcx, [rbp+2F0h+var_2E0]
0x1400878dc  call    ?Stop@?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400878e1  mov     rbx, [rbp+2F0h+FileHandle]
0x1400878e5  lea     rcx, [rbp+2F0h+var_2E0]; this
0x1400878e9  call    ??1VstorCreateDevice@VstorlibTraceProvider@@QEAA@XZ; VstorlibTraceProvider::VstorCreateDevice::~VstorCreateDevice(void)
0x1400878ee  mov     rax, rbx
0x1400878f1  mov     rcx, [rbp+2F0h+var_40]
0x1400878f8  xor     rcx, rsp; StackCookie
0x1400878fb  call    __security_check_cookie
0x140087900  mov     rbx, [rsp+3F0h+arg_18]
0x140087908  add     rsp, 3C0h
0x14008790f  pop     r15
0x140087911  pop     r14
0x140087913  pop     r13
0x140087915  pop     r12
0x140087917  pop     rdi
0x140087918  pop     rsi
0x140087919  pop     rbp
0x14008791a  retn
```
