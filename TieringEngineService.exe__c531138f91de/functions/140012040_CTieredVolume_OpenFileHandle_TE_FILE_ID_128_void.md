# CTieredVolume::OpenFileHandle(TE_FILE_ID_128 *,void * *)

- ea: `0x140012040`
- end: `0x1400122f5`
- name: `?OpenFileHandle@CTieredVolume@@QEAAJPEAUTE_FILE_ID_128@@PEAPEAX@Z`
- size: `693`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this, struct TE_FILE_ID_128 *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001250c`

## callees

- `0x140002db0`
- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x140012040`
- `0x1400183c0`
- `0x1400185a0`

## import_xrefs

- `msvcrt!malloc` at `0x140012174`
- `msvcrt!malloc` at `0x140012174`
- `ntdll!RtlCopyUnicodeString` at `0x1400121e3`
- `ntdll!RtlCopyUnicodeString` at `0x1400121e3`
- `ntdll!NtOpenFile` at `0x140012255`
- `ntdll!NtOpenFile` at `0x140012255`
- `ntdll!NtClose` at `0x14001212d`
- `ntdll!NtClose` at `0x14001212d`
- `ntdll!RtlNtStatusToDosError` at `0x140012263`
- `ntdll!RtlNtStatusToDosError` at `0x140012263`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001211e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400121f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001211e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400121f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400120bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400120bc`

## string_xrefs

- `0x140012078`: `CTieredVolume::OpenFileHandle`

## pseudocode

```c
__int64 __fastcall CTieredVolume::OpenFileHandle(CTieredVolume *this, struct TE_FILE_ID_128 *a2, void **a3)
{
  unsigned int v6; // ebx
  HANDLE v7; // rcx
  int v9; // r14d
  int v10; // r8d
  int v11; // eax
  char v12; // di
  ULONG v13; // eax
  HANDLE v14; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v16[8]; // [rsp+50h] [rbp-19h] BYREF
  int v17; // [rsp+58h] [rbp-11h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  HANDLE Handle; // [rsp+D0h] [rbp+67h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::OpenFileHandle";
  CHResultImp::CHResultImp((CHResultImp *)v16);
  Handle = 0;
  *a3 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 3);
  if ( !*((_BYTE *)this + 721) )
  {
    v6 = -2138898430;
    v17 = -2138898430;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        240,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        *((unsigned int *)this + 32),
        -2138898430);
    }
LABEL_6:
    if ( this != (CTieredVolume *)-24LL )
      ReleaseSRWLockShared((PSRWLOCK)this + 3);
    goto LABEL_8;
  }
  v9 = (unsigned __int16)(*((_WORD *)this + 72) + 16);
  DestinationString.MaximumLength = *((_WORD *)this + 72) + 16;
  DestinationString.Buffer = (PWSTR)malloc(DestinationString.MaximumLength);
  if ( !DestinationString.Buffer )
  {
    v6 = -2147024882;
    v17 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dZd(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, v10, v9, (__int64)this + 672, 14);
    }
    goto LABEL_6;
  }
  RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)this + 9);
  if ( this != (CTieredVolume *)-24LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 3);
  *(_OWORD *)((char *)DestinationString.Buffer + DestinationString.Length) = *(_OWORD *)a2;
  DestinationString.Length += 16;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 192;
  v11 = NtOpenFile(&Handle, 0x100180u, &ObjectAttributes, &IoStatusBlock, 7u, 0x202020u);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = RtlNtStatusToDosError(v11);
    v6 = ATL::AtlHresultFromWin32(v13);
    v17 = v6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        242,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        (__int64)this + 672,
        v12);
    }
    goto LABEL_8;
  }
  v6 = v17;
  if ( v17 < 0 )
  {
LABEL_8:
    v7 = Handle;
    goto LABEL_9;
  }
  v14 = Handle;
  v7 = 0;
  Handle = 0;
  *a3 = v14;
LABEL_9:
  if ( v7 )
    NtClose(v7);
  CHResultImp::~CHResultImp((CHResultImp *)v16);
  return v6;
}

```

## disassembly

```asm
0x140012040  mov     [rsp-8+arg_8], rbx
0x140012045  mov     [rsp-8+arg_10], rsi
0x14001204a  push    rbp
0x14001204b  push    rdi
0x14001204c  push    r12
0x14001204e  push    r14
0x140012050  push    r15
0x140012052  lea     rbp, [rsp-37h]
0x140012057  sub     rsp, 0A0h
0x14001205e  mov     rax, gs:58h
0x140012067  mov     rsi, rcx
0x14001206a  mov     ecx, 8
0x14001206f  mov     r15, r8
0x140012072  mov     r12, rdx
0x140012075  mov     r9, [rax]
0x140012078  lea     rax, aCtieredvolumeO; "CTieredVolume::OpenFileHandle"
0x14001207f  mov     [rcx+r9], rax
0x140012083  lea     rcx, [rbp+57h+var_70]; this
0x140012087  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001208c  xorps   xmm1, xmm1
0x14001208f  mov     [rbp+57h+Handle], 0
0x140012097  xorps   xmm0, xmm0
0x14001209a  mov     qword ptr [r15], 0
0x1400120a1  lea     rdi, [rsi+18h]
0x1400120a5  mov     rcx, rdi; SRWLock
0x1400120a8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400120ac  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400120b0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400120b4  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400120b8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400120bc  call    cs:__imp_AcquireSRWLockShared
0x1400120c2  cmp     byte ptr [rsi+2D1h], 0
0x1400120c9  jnz     loc_14001215A
0x1400120cf  mov     ebx, 80830002h
0x1400120d4  mov     [rbp+57h+var_68], ebx
0x1400120d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400120de  lea     rax, WPP_GLOBAL_Control
0x1400120e5  cmp     rcx, rax
0x1400120e8  jz      short loc_140012116
0x1400120ea  test    byte ptr [rcx+1Ch], 1
0x1400120ee  jz      short loc_140012116
0x1400120f0  cmp     byte ptr [rcx+19h], 2
0x1400120f4  jb      short loc_140012116
0x1400120f6  mov     r9d, [rsi+80h]
0x1400120fd  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140012104  mov     rcx, [rcx+10h]
0x140012108  mov     edx, 0F0h
0x14001210d  mov     [rsp+0C0h+ShareAccess], ebx
0x140012111  call    WPP_SF_Dd
0x140012116  test    rdi, rdi
0x140012119  jz      short loc_140012124
0x14001211b  mov     rcx, rdi; SRWLock
0x14001211e  call    cs:__imp_ReleaseSRWLockShared
0x140012124  mov     rcx, [rbp+57h+Handle]; Handle
0x140012128  test    rcx, rcx
0x14001212b  jz      short loc_140012133
0x14001212d  call    cs:__imp_NtClose
0x140012133  lea     rcx, [rbp+57h+var_70]; this
0x140012137  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001213c  lea     r11, [rsp+0C0h+var_20]
0x140012144  mov     eax, ebx
0x140012146  mov     rbx, [r11+38h]
0x14001214a  mov     rsi, [r11+40h]
0x14001214e  mov     rsp, r11
0x140012151  pop     r15
0x140012153  pop     r14
0x140012155  pop     r12
0x140012157  pop     rdi
0x140012158  pop     rbp
0x140012159  retn
0x14001215a  lea     rbx, [rsi+90h]
0x140012161  movzx   eax, word ptr [rbx]
0x140012164  add     ax, 10h
0x140012168  movzx   r14d, ax
0x14001216c  mov     ecx, r14d; Size
0x14001216f  mov     [rbp+57h+DestinationString.MaximumLength], r14w
0x140012174  call    cs:__imp_malloc
0x14001217a  mov     [rbp+57h+DestinationString.Buffer], rax
0x14001217e  test    rax, rax
0x140012181  jnz     short loc_1400121DC
0x140012183  mov     ebx, 8007000Eh
0x140012188  mov     [rbp+57h+var_68], ebx
0x14001218b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012192  lea     rax, WPP_GLOBAL_Control
0x140012199  cmp     rcx, rax
0x14001219c  jz      loc_140012116
0x1400121a2  test    byte ptr [rcx+1Ch], 1
0x1400121a6  jz      loc_140012116
0x1400121ac  cmp     byte ptr [rcx+19h], 2
0x1400121b0  jb      loc_140012116
0x1400121b6  mov     rcx, [rcx+10h]
0x1400121ba  lea     rax, [rsi+2A0h]
0x1400121c1  mov     r9d, r14d
0x1400121c4  mov     [rsp+0C0h+OpenOptions], ebx
0x1400121c8  mov     edx, 0F1h
0x1400121cd  mov     qword ptr [rsp+0C0h+ShareAccess], rax
0x1400121d2  call    WPP_SF_dZd
0x1400121d7  jmp     loc_140012116
0x1400121dc  mov     rdx, rbx; SourceString
0x1400121df  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400121e3  call    cs:__imp_RtlCopyUnicodeString
0x1400121e9  test    rdi, rdi
0x1400121ec  jz      short loc_1400121F7
0x1400121ee  mov     rcx, rdi; SRWLock
0x1400121f1  call    cs:__imp_ReleaseSRWLockShared
0x1400121f7  movzx   ecx, [rbp+57h+DestinationString.Length]
0x1400121fb  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400121ff  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140012203  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140012207  movups  xmm0, xmmword ptr [r12]
0x14001220c  mov     [rsp+0C0h+OpenOptions], 202020h; OpenOptions
0x140012214  mov     edx, 100180h; DesiredAccess
0x140012219  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x140012221  movdqu  xmmword ptr [rcx+rax], xmm0
0x140012226  add     [rbp+57h+DestinationString.Length], 10h
0x14001222b  lea     rax, [rbp+57h+DestinationString]
0x14001222f  xorps   xmm0, xmm0
0x140012232  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140012236  lea     rcx, [rbp+57h+Handle]; FileHandle
0x14001223a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012241  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012246  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001224e  mov     [rbp+57h+ObjectAttributes.Attributes], 0C0h
0x140012255  call    cs:__imp_NtOpenFile
0x14001225b  mov     edi, eax
0x14001225d  test    eax, eax
0x14001225f  jns     short loc_1400122D8
0x140012261  mov     ecx, eax; Status
0x140012263  call    cs:__imp_RtlNtStatusToDosError
0x140012269  mov     ecx, eax; unsigned int
0x14001226b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140012270  mov     ebx, eax
0x140012272  mov     [rbp+57h+var_68], eax
0x140012275  mov     rcx, cs:WPP_GLOBAL_Control
0x14001227c  lea     rax, WPP_GLOBAL_Control
0x140012283  cmp     rcx, rax
0x140012286  jz      loc_140012124
0x14001228c  test    byte ptr [rcx+1Ch], 1
0x140012290  jz      loc_140012124
0x140012296  cmp     byte ptr [rcx+19h], 2
0x14001229a  jb      loc_140012124
0x1400122a0  mov     r9, [r12+8]
0x1400122a5  lea     rax, [rsi+2A0h]
0x1400122ac  mov     rcx, [rcx+10h]
0x1400122b0  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x1400122b7  mov     [rsp+0C0h+var_90], edi
0x1400122bb  mov     edx, 0F2h
0x1400122c0  mov     qword ptr [rsp+0C0h+OpenOptions], rax
0x1400122c5  mov     rax, [r12]
0x1400122c9  mov     qword ptr [rsp+0C0h+ShareAccess], rax
0x1400122ce  call    WPP_SF_iiZd
0x1400122d3  jmp     loc_140012124
0x1400122d8  mov     ebx, [rbp+57h+var_68]
0x1400122db  test    ebx, ebx
0x1400122dd  js      loc_140012124
0x1400122e3  mov     rax, [rbp+57h+Handle]
0x1400122e7  xor     ecx, ecx
0x1400122e9  mov     [rbp+57h+Handle], rcx
0x1400122ed  mov     [r15], rax
0x1400122f0  jmp     loc_140012128
```
