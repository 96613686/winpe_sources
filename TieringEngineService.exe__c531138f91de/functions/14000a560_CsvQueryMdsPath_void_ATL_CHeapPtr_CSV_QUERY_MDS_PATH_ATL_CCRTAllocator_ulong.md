# CsvQueryMdsPath(void *,ATL::CHeapPtr<_CSV_QUERY_MDS_PATH,ATL::CCRTAllocator> &,ulong &)

- ea: `0x14000a560`
- end: `0x14000a6f9`
- name: `?CsvQueryMdsPath@@YAJPEAXAEAV?$CHeapPtr@U_CSV_QUERY_MDS_PATH@@VCCRTAllocator@ATL@@@ATL@@AEAK@Z`
- size: `409`
- prototype: `__int64 __fastcall(HANDLE Handle, PVOID *, ULONG *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140005db4`
- `0x1400127dc`

## callees

- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x14000a560`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!realloc` at `0x14000a665`
- `msvcrt!realloc` at `0x14000a665`
- `msvcrt!malloc` at `0x14000a5cf`
- `msvcrt!malloc` at `0x14000a5cf`
- `ntdll!NtFsControlFile` at `0x14000a621`
- `ntdll!NtFsControlFile` at `0x14000a621`
- `ntdll!NtWaitForSingleObject` at `0x14000a638`
- `ntdll!NtWaitForSingleObject` at `0x14000a638`

## string_xrefs

- `0x14000a59b`: `CsvQueryMdsPath`

## pseudocode

```c
__int64 __fastcall CsvQueryMdsPath(HANDLE Handle, PVOID *a2, ULONG *a3)
{
  ULONG OutputBufferLength; // ebx
  void *v7; // rax
  NTSTATUS Status; // ebx
  void *v9; // rax
  int v10; // ebx
  _BYTE v12[8]; // [rsp+50h] [rbp-9h] BYREF
  int v13; // [rsp+58h] [rbp-1h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+7h] BYREF
  __int128 InputBuffer; // [rsp+70h] [rbp+17h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CsvQueryMdsPath";
  CHResultImp::CHResultImp((CHResultImp *)v12);
  OutputBufferLength = *a3;
  InputBuffer = 0;
  LODWORD(InputBuffer) = 8;
  IoStatusBlock = 0;
  if ( OutputBufferLength )
    goto LABEL_5;
  v7 = malloc(0x1100u);
  *a2 = v7;
  if ( !v7 )
  {
LABEL_19:
    v10 = -2147024882;
    v13 = -2147024882;
    goto LABEL_20;
  }
  OutputBufferLength = 272;
  while ( 1 )
  {
    *a3 = OutputBufferLength;
LABEL_5:
    Status = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x902D4u, &InputBuffer, 0x10u, *a2, OutputBufferLength);
    if ( Status == 259 )
    {
      NtWaitForSingleObject(Handle, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status != -1073741789 )
      break;
    OutputBufferLength = 2 * *a3;
LABEL_11:
    v9 = realloc(*a2, OutputBufferLength);
    if ( !v9 )
      goto LABEL_19;
    *a2 = v9;
  }
  if ( Status == -2147483643 )
  {
    OutputBufferLength = *((_DWORD *)*a2 + 2) + 12;
    goto LABEL_11;
  }
  v10 = Status | 0x10000000;
  v13 = v10;
  if ( v10 >= 0 )
  {
    v10 = 0;
    *a3 = IoStatusBlock.Information;
    v13 = 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      &WPP_58242705c75132cdab80b446e38b4c82_Traceguids,
      (unsigned int)v10);
  }
LABEL_20:
  CHResultImp::~CHResultImp((CHResultImp *)v12);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a560  push    rbp
0x14000a562  push    rbx
0x14000a563  push    rsi
0x14000a564  push    rdi
0x14000a565  push    r14
0x14000a567  lea     rbp, [rsp-37h]
0x14000a56c  sub     rsp, 90h
0x14000a573  mov     rax, cs:__security_cookie
0x14000a57a  xor     rax, rsp
0x14000a57d  mov     [rbp+57h+var_30], rax
0x14000a581  mov     rax, gs:58h
0x14000a58a  mov     r14, rcx
0x14000a58d  mov     ecx, 8
0x14000a592  mov     rsi, r8
0x14000a595  mov     rdi, rdx
0x14000a598  mov     r9, [rax]
0x14000a59b  lea     rax, aCsvquerymdspat; "CsvQueryMdsPath"
0x14000a5a2  mov     [rcx+r9], rax
0x14000a5a6  lea     rcx, [rbp+57h+var_60]; this
0x14000a5aa  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000a5af  mov     ebx, [rsi]
0x14000a5b1  xorps   xmm1, xmm1
0x14000a5b4  xorps   xmm0, xmm0
0x14000a5b7  movups  [rbp+57h+var_40], xmm1
0x14000a5bb  mov     dword ptr [rbp+57h+var_40], 8
0x14000a5c2  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x14000a5c6  test    ebx, ebx
0x14000a5c8  jnz     short loc_14000A5E8
0x14000a5ca  mov     ecx, 1100h; Size
0x14000a5cf  call    cs:__imp_malloc
0x14000a5d5  mov     [rdi], rax
0x14000a5d8  test    rax, rax
0x14000a5db  jz      loc_14000A6CC
0x14000a5e1  mov     ebx, 110h
0x14000a5e6  mov     [rsi], ebx
0x14000a5e8  mov     rax, [rdi]
0x14000a5eb  xor     r9d, r9d; ApcContext
0x14000a5ee  mov     [rsp+0B0h+OutputBufferLength], ebx; OutputBufferLength
0x14000a5f2  xor     r8d, r8d; ApcRoutine
0x14000a5f5  mov     [rsp+0B0h+OutputBuffer], rax; OutputBuffer
0x14000a5fa  xor     edx, edx; Event
0x14000a5fc  mov     [rsp+0B0h+InputBufferLength], 10h; InputBufferLength
0x14000a604  lea     rax, [rbp+57h+var_40]
0x14000a608  mov     [rsp+0B0h+InputBuffer], rax; InputBuffer
0x14000a60d  mov     rcx, r14; FileHandle
0x14000a610  lea     rax, [rbp+57h+var_50]
0x14000a614  mov     [rsp+0B0h+FsControlCode], 902D4h; FsControlCode
0x14000a61c  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x14000a621  call    cs:__imp_NtFsControlFile
0x14000a627  mov     ebx, eax
0x14000a629  cmp     eax, 103h
0x14000a62e  jnz     short loc_14000A641
0x14000a630  xor     r8d, r8d; Timeout
0x14000a633  xor     edx, edx; Alertable
0x14000a635  mov     rcx, r14; Handle
0x14000a638  call    cs:__imp_NtWaitForSingleObject
0x14000a63e  mov     ebx, dword ptr [rbp+57h+var_50]
0x14000a641  cmp     ebx, 0C0000023h
0x14000a647  jz      short loc_14000A65C
0x14000a649  cmp     ebx, 80000005h
0x14000a64f  jnz     short loc_14000A678
0x14000a651  mov     rax, [rdi]
0x14000a654  mov     ebx, [rax+8]
0x14000a657  add     ebx, 0Ch
0x14000a65a  jmp     short loc_14000A660
0x14000a65c  mov     ebx, [rsi]
0x14000a65e  add     ebx, ebx
0x14000a660  mov     rcx, [rdi]; Block
0x14000a663  mov     edx, ebx; Size
0x14000a665  call    cs:__imp_realloc
0x14000a66b  test    rax, rax
0x14000a66e  jz      short loc_14000A6CC
0x14000a670  mov     [rdi], rax
0x14000a673  jmp     loc_14000A5E6
0x14000a678  or      ebx, 10000000h
0x14000a67e  mov     [rbp+57h+var_58], ebx
0x14000a681  jge     short loc_14000A6BC
0x14000a683  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a68a  lea     rax, WPP_GLOBAL_Control
0x14000a691  cmp     rcx, rax
0x14000a694  jz      short loc_14000A6D4
0x14000a696  test    byte ptr [rcx+1Ch], 1
0x14000a69a  jz      short loc_14000A6D4
0x14000a69c  cmp     byte ptr [rcx+19h], 2
0x14000a6a0  jb      short loc_14000A6D4
0x14000a6a2  mov     rcx, [rcx+10h]
0x14000a6a6  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000a6ad  mov     edx, 19h
0x14000a6b2  mov     r9d, ebx
0x14000a6b5  call    WPP_SF_d
0x14000a6ba  jmp     short loc_14000A6D4
0x14000a6bc  mov     eax, dword ptr [rbp+57h+var_50.Information]
0x14000a6bf  xor     ebx, ebx
0x14000a6c1  mov     [rsi], eax
0x14000a6c3  mov     [rbp+57h+var_58], 0
0x14000a6ca  jmp     short loc_14000A6D4
0x14000a6cc  mov     ebx, 8007000Eh
0x14000a6d1  mov     [rbp+57h+var_58], ebx
0x14000a6d4  lea     rcx, [rbp+57h+var_60]; this
0x14000a6d8  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14000a6dd  mov     eax, ebx
0x14000a6df  mov     rcx, [rbp+57h+var_30]
0x14000a6e3  xor     rcx, rsp; StackCookie
0x14000a6e6  call    __security_check_cookie
0x14000a6eb  add     rsp, 90h
0x14000a6f2  pop     r14
0x14000a6f4  pop     rdi
0x14000a6f5  pop     rsi
0x14000a6f6  pop     rbx
0x14000a6f7  pop     rbp
0x14000a6f8  retn
```
