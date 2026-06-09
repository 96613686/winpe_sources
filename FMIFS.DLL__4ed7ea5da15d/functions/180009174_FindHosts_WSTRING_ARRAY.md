# FindHosts(WSTRING *,ARRAY *)

- ea: `0x180009174`
- end: `0x180009406`
- name: `?FindHosts@@YAEPEAVWSTRING@@PEAVARRAY@@@Z`
- size: `658`
- prototype: `unsigned __int8 __fastcall(struct WSTRING *, struct ARRAY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008e18`

## callees

- `0x180009174`
- `0x180009752`
- `0x18000a010`

## import_xrefs

- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18000932c`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18000932c`
- `ntdll!RtlNtStatusToDosError` at `0x180009254`
- `ntdll!RtlNtStatusToDosError` at `0x180009254`
- `ntdll!NtClose` at `0x1800093c9`
- `ntdll!NtClose` at `0x1800093c9`
- `ntdll!NtOpenFile` at `0x180009248`
- `ntdll!NtOpenFile` at `0x180009248`
- `ntdll!NtFsControlFile` at `0x180009302`
- `ntdll!NtFsControlFile` at `0x180009302`
- `ntdll!RtlAllocateHeap` at `0x18000929e`
- `ntdll!RtlAllocateHeap` at `0x18000929e`
- `ntdll!RtlFreeHeap` at `0x180009283`
- `ntdll!RtlFreeHeap` at `0x1800093e6`
- `ntdll!RtlFreeHeap` at `0x180009283`
- `ntdll!RtlFreeHeap` at `0x1800093e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ba`
- `ulib!?Initialize@ARRAY@@QEAAEKK@Z` at `0x1800091d6`
- `ulib!?Initialize@ARRAY@@QEAAEKK@Z` at `0x1800091d6`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180009361`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180009361`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180009342`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180009342`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000939a`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x1800093a8`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000939a`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x1800093a8`
- `ulib!?GetWSTR@WSTRING@@QEBAPEBGXZ` at `0x1800091fb`
- `ulib!?GetWSTR@WSTRING@@QEBAPEBGXZ` at `0x1800091fb`
- `ulib!?QueryString@WSTRING@@QEBAPEAV1@KK@Z` at `0x180009375`
- `ulib!?QueryString@WSTRING@@QEBAPEAV1@KK@Z` at `0x180009375`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800091e7`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800091e7`

## pseudocode

```c
bool __fastcall FindHosts(struct WSTRING *a1, struct ARRAY *a2)
{
  _DWORD *OutputBuffer; // rbx
  bool v3; // di
  DWORD v6; // ecx
  int v7; // eax
  ULONG OutputBufferLength; // esi
  _DWORD *Heap; // rax
  int v10; // eax
  unsigned int i; // esi
  struct WSTRING *String; // rdx
  __int128 v14; // [rsp+50h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v17[80]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 InputBuffer; // [rsp+108h] [rbp+6Fh] BYREF
  void *FileHandle; // [rsp+110h] [rbp+77h] BYREF

  InputBuffer = 0;
  OutputBuffer = 0;
  v3 = 0;
  FileHandle = 0;
  v14 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( a2 )
  {
    if ( ARRAY::Initialize(a2, 0x32u, 0x19u) )
    {
      LOWORD(v14) = 2 * WSTRING::QueryChCount(a1);
      WORD1(v14) = v14;
      *((_QWORD *)&v14 + 1) = WSTRING::GetWSTR(a1);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x11u);
      if ( v7 < 0 )
      {
        v6 = RtlNtStatusToDosError(v7);
        goto LABEL_23;
      }
      OutputBufferLength = 76;
      while ( 1 )
      {
        OutputBufferLength += 328;
        if ( OutputBuffer )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBuffer);
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBufferLength);
        OutputBuffer = Heap;
        if ( !Heap )
          break;
        memset_0(Heap, 0, OutputBufferLength);
        InputBuffer = 0x100000002LL;
        v10 = NtFsControlFile(
                FileHandle,
                0,
                0,
                0,
                &IoStatusBlock,
                0x901F0u,
                &InputBuffer,
                8u,
                OutputBuffer,
                OutputBufferLength);
        if ( v10 != -2147483643 )
        {
          v3 = v10 == -1073741808;
          if ( v10 >= 0 )
          {
            for ( i = 0; i < OutputBuffer[1]; ++i )
            {
              DSTRING::DSTRING((DSTRING *)v17);
              if ( !WSTRING::Initialize(
                      (WSTRING *)v17,
                      (const unsigned __int16 *)((char *)OutputBuffer + (unsigned int)OutputBuffer[17 * i + 11]),
                      OutputBuffer[17 * i + 12] >> 1)
                || (String = WSTRING::QueryString((WSTRING *)v17, 0, 0xFFFFFFFF)) == 0
                || !(*(unsigned __int8 (__fastcall **)(struct ARRAY *, struct WSTRING *))(*(_QWORD *)a2 + 24LL))(
                      a2,
                      String) )
              {
                DSTRING::~DSTRING((DSTRING *)v17);
                goto LABEL_24;
              }
              DSTRING::~DSTRING((DSTRING *)v17);
            }
            v3 = 1;
          }
          else if ( v10 != -1073741808 )
          {
            RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v10);
          }
          goto LABEL_24;
        }
      }
    }
    v6 = 8;
    goto LABEL_23;
  }
  v6 = 87;
LABEL_23:
  SetLastError(v6);
LABEL_24:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( OutputBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBuffer);
  return v3;
}

```

## disassembly

```asm
0x180009174  mov     [rsp-8+arg_0], rbx
0x180009179  push    rbp
0x18000917a  push    rsi
0x18000917b  push    rdi
0x18000917c  push    r14
0x18000917e  push    r15
0x180009180  lea     rbp, [rsp-37h]
0x180009185  sub     rsp, 0D0h
0x18000918c  xorps   xmm1, xmm1
0x18000918f  mov     [rbp+57h+arg_8], 0
0x180009197  xor     ebx, ebx
0x180009199  xorps   xmm0, xmm0
0x18000919c  xor     dil, dil
0x18000919f  mov     [rbp+57h+FileHandle], rbx
0x1800091a3  mov     r14, rdx
0x1800091a6  mov     rsi, rcx
0x1800091a9  movups  [rbp+57h+var_A0], xmm0
0x1800091ad  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800091b1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800091b5  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800091b9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800091bd  test    rdx, rdx
0x1800091c0  jnz     short loc_1800091CA
0x1800091c2  lea     ecx, [rdx+57h]
0x1800091c5  jmp     loc_1800093BA
0x1800091ca  mov     edx, 32h ; '2'
0x1800091cf  mov     rcx, r14
0x1800091d2  lea     r8d, [rdx-19h]
0x1800091d6  call    cs:__imp_?Initialize@ARRAY@@QEAAEKK@Z; ARRAY::Initialize(ulong,ulong)
0x1800091dc  test    al, al
0x1800091de  jz      loc_1800093B5
0x1800091e4  mov     rcx, rsi
0x1800091e7  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x1800091ed  add     ax, ax
0x1800091f0  mov     rcx, rsi
0x1800091f3  mov     word ptr [rbp+57h+var_A0], ax
0x1800091f7  mov     word ptr [rbp+57h+var_A0+2], ax
0x1800091fb  call    cs:__imp_?GetWSTR@WSTRING@@QEBAPEBGXZ; WSTRING::GetWSTR(void)
0x180009201  xorps   xmm0, xmm0
0x180009204  mov     [rsp+0F0h+OpenOptions], 11h; OpenOptions
0x18000920c  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180009210  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180009214  lea     rax, [rbp+57h+var_A0]
0x180009218  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000921f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180009223  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180009227  mov     edx, 100080h; DesiredAccess
0x18000922c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180009230  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180009234  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000923b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009240  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x180009248  call    cs:__imp_NtOpenFile
0x18000924e  test    eax, eax
0x180009250  jns     short loc_180009261
0x180009252  mov     ecx, eax; Status
0x180009254  call    cs:__imp_RtlNtStatusToDosError
0x18000925a  mov     ecx, eax
0x18000925c  jmp     loc_1800093BA
0x180009261  mov     esi, 4Ch ; 'L'
0x180009266  add     esi, 148h
0x18000926c  test    rbx, rbx
0x18000926f  jz      short loc_180009289
0x180009271  mov     rcx, gs:60h
0x18000927a  mov     r8, rbx; P
0x18000927d  xor     edx, edx; Flags
0x18000927f  mov     rcx, [rcx+30h]; HeapHandle
0x180009283  call    cs:__imp_RtlFreeHeap
0x180009289  mov     rcx, gs:60h
0x180009292  xor     edx, edx; Flags
0x180009294  mov     r8d, esi; Size
0x180009297  mov     r15d, esi
0x18000929a  mov     rcx, [rcx+30h]; HeapHandle
0x18000929e  call    cs:__imp_RtlAllocateHeap
0x1800092a4  mov     rbx, rax
0x1800092a7  test    rax, rax
0x1800092aa  jz      loc_1800093B5
0x1800092b0  mov     r8d, r15d; Size
0x1800092b3  xor     edx, edx; Val
0x1800092b5  mov     rcx, rax; void *
0x1800092b8  call    memset_0
0x1800092bd  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800092c1  lea     rax, [rbp+57h+arg_8]
0x1800092c5  mov     [rsp+0F0h+OutputBufferLength], esi; OutputBufferLength
0x1800092c9  xor     r9d, r9d; ApcContext
0x1800092cc  mov     [rsp+0F0h+OutputBuffer], rbx; OutputBuffer
0x1800092d1  xor     r8d, r8d; ApcRoutine
0x1800092d4  mov     [rsp+0F0h+InputBufferLength], 8; InputBufferLength
0x1800092dc  xor     edx, edx; Event
0x1800092de  mov     [rsp+0F0h+InputBuffer], rax; InputBuffer
0x1800092e3  lea     rax, [rbp+57h+IoStatusBlock]
0x1800092e7  mov     [rsp+0F0h+OpenOptions], 901F0h; FsControlCode
0x1800092ef  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x1800092f4  mov     dword ptr [rbp+57h+arg_8], 2
0x1800092fb  mov     dword ptr [rbp+57h+arg_8+4], 1
0x180009302  call    cs:__imp_NtFsControlFile
0x180009308  cmp     eax, 80000005h
0x18000930d  jz      loc_180009266
0x180009313  mov     ecx, 0C0000010h
0x180009318  cmp     eax, ecx
0x18000931a  setz    dil
0x18000931e  test    eax, eax
0x180009320  jns     short loc_180009337
0x180009322  cmp     eax, ecx
0x180009324  jz      loc_1800093C0
0x18000932a  mov     ecx, eax; Status
0x18000932c  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x180009332  jmp     loc_1800093C0
0x180009337  xor     esi, esi
0x180009339  cmp     esi, [rbx+4]
0x18000933c  jnb     short loc_1800093B0
0x18000933e  lea     rcx, [rbp+57h+var_50]
0x180009342  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180009348  mov     eax, esi
0x18000934a  imul    rcx, rax, 44h ; 'D'
0x18000934e  mov     r8d, [rcx+rbx+30h]
0x180009353  mov     edx, [rcx+rbx+2Ch]
0x180009357  lea     rcx, [rbp+57h+var_50]
0x18000935b  shr     r8d, 1
0x18000935e  add     rdx, rbx
0x180009361  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180009367  lea     rcx, [rbp+57h+var_50]
0x18000936b  test    al, al
0x18000936d  jz      short loc_1800093A8
0x18000936f  or      r8d, 0FFFFFFFFh
0x180009373  xor     edx, edx
0x180009375  call    cs:__imp_?QueryString@WSTRING@@QEBAPEAV1@KK@Z; WSTRING::QueryString(ulong,ulong)
0x18000937b  mov     rdx, rax
0x18000937e  test    rax, rax
0x180009381  jz      short loc_1800093A4
0x180009383  mov     rcx, [r14]
0x180009386  mov     rax, [rcx+18h]
0x18000938a  mov     rcx, r14
0x18000938d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009392  test    al, al
0x180009394  jz      short loc_1800093A4
0x180009396  lea     rcx, [rbp+57h+var_50]
0x18000939a  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x1800093a0  inc     esi
0x1800093a2  jmp     short loc_180009339
0x1800093a4  lea     rcx, [rbp+57h+var_50]
0x1800093a8  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x1800093ae  jmp     short loc_1800093C0
0x1800093b0  mov     dil, 1
0x1800093b3  jmp     short loc_1800093C0
0x1800093b5  mov     ecx, 8; dwErrCode
0x1800093ba  call    cs:__imp_SetLastError
0x1800093c0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800093c4  test    rcx, rcx
0x1800093c7  jz      short loc_1800093CF
0x1800093c9  call    cs:__imp_NtClose
0x1800093cf  test    rbx, rbx
0x1800093d2  jz      short loc_1800093EC
0x1800093d4  mov     rcx, gs:60h
0x1800093dd  mov     r8, rbx; P
0x1800093e0  xor     edx, edx; Flags
0x1800093e2  mov     rcx, [rcx+30h]; HeapHandle
0x1800093e6  call    cs:__imp_RtlFreeHeap
0x1800093ec  mov     rbx, [rsp+0F0h+arg_0]
0x1800093f4  mov     al, dil
0x1800093f7  add     rsp, 0D0h
0x1800093fe  pop     r15
0x180009400  pop     r14
0x180009402  pop     rdi
0x180009403  pop     rsi
0x180009404  pop     rbp
0x180009405  retn
```
