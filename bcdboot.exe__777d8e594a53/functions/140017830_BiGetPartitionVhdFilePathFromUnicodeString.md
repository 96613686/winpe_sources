# BiGetPartitionVhdFilePathFromUnicodeString

- ea: `0x140017830`
- end: `0x140017ae5`
- name: `BiGetPartitionVhdFilePathFromUnicodeString`
- size: `693`
- prototype: `ULONG *__fastcall(struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140006cd8`
- `0x140017800`

## callees

- `0x140017830`
- `0x1400182d8`
- `0x1400265e2`

## import_xrefs

- `msvcrt!wcsrchr` at `0x140017972`
- `msvcrt!wcsrchr` at `0x140017972`
- `ntdll!ZwDeviceIoControlFile` at `0x140017916`
- `ntdll!ZwDeviceIoControlFile` at `0x140017916`
- `ntdll!ZwClose` at `0x140017ac8`
- `ntdll!ZwClose` at `0x140017ac8`
- `ntdll!RtlAllocateHeap` at `0x1400178c9`
- `ntdll!RtlAllocateHeap` at `0x1400179f1`
- `ntdll!RtlAllocateHeap` at `0x1400178c9`
- `ntdll!RtlAllocateHeap` at `0x1400179f1`
- `ntdll!RtlFreeHeap` at `0x140017940`
- `ntdll!RtlFreeHeap` at `0x140017a39`
- `ntdll!RtlFreeHeap` at `0x140017a7d`
- `ntdll!RtlFreeHeap` at `0x140017a99`
- `ntdll!RtlFreeHeap` at `0x140017ab6`
- `ntdll!RtlFreeHeap` at `0x140017940`
- `ntdll!RtlFreeHeap` at `0x140017a39`
- `ntdll!RtlFreeHeap` at `0x140017a7d`
- `ntdll!RtlFreeHeap` at `0x140017a99`
- `ntdll!RtlFreeHeap` at `0x140017ab6`
- `ntdll!ZwOpenFile` at `0x14001789c`
- `ntdll!ZwOpenFile` at `0x14001789c`

## pseudocode

```c
ULONG *__fastcall BiGetPartitionVhdFilePathFromUnicodeString(struct _UNICODE_STRING *a1)
{
  char v1; // r12
  ULONG *v2; // rdi
  ULONG OutputBufferLength; // ebx
  int i; // esi
  ULONG *OutputBuffer; // rax
  NTSTATUS v6; // eax
  _WORD *v7; // r14
  wchar_t *v8; // r15
  wchar_t *v9; // r13
  wchar_t *j; // rbx
  wchar_t *v11; // rsi
  int v12; // eax
  __int64 v13; // rax
  size_t v14; // rbx
  __int64 v15; // rax
  wchar_t *Heap; // rax
  _WORD *v17; // rbx
  signed int v18; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  int InputBuffer; // [rsp+E0h] [rbp+67h] BYREF
  size_t Size; // [rsp+E8h] [rbp+6Fh]
  void *FileHandle; // [rsp+F0h] [rbp+77h] BYREF
  void *Src; // [rsp+F8h] [rbp+7Fh]

  v1 = 0;
  ObjectAttributes.ObjectName = a1;
  InputBuffer = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  v2 = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u) >= 0 )
  {
    OutputBufferLength = 520;
    for ( i = 1; ; i = 2 )
    {
      OutputBuffer = (ULONG *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBufferLength);
      v2 = OutputBuffer;
      if ( !OutputBuffer )
        break;
      InputBuffer = 1;
      v6 = ZwDeviceIoControlFile(
             FileHandle,
             0,
             0,
             0,
             &IoStatusBlock,
             0x2D5928u,
             &InputBuffer,
             4u,
             OutputBuffer,
             OutputBufferLength);
      if ( v6 != -1073741789 )
      {
        if ( v6 < 0 )
        {
LABEL_28:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          v2 = 0;
          break;
        }
        v7 = 0;
        Src = 0;
        v8 = 0;
        v9 = (wchar_t *)v2;
        for ( j = 0; ; j = v11 )
        {
          v11 = wcsrchr(v9, 0x5Cu);
          if ( j )
            *j = 92;
          if ( !v11 )
            break;
          *v11 = 0;
          v12 = BiTranslateSymbolicLink(v9);
          v7 = Src;
          if ( v12 >= 0 )
          {
            *v11 = 92;
            v13 = -1;
            do
              ++v13;
            while ( v7[v13] );
            v14 = (unsigned int)(2 * v13);
            v15 = -1;
            do
              ++v15;
            while ( v11[v15] );
            LODWORD(Size) = 2 * v15 + 2;
            Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v14 + Size));
            v8 = Heap;
            if ( !Heap )
            {
              v18 = -1073741801;
              goto LABEL_24;
            }
            v1 = 1;
            memcpy_0(Heap, v7, v14);
            v17 = (wchar_t *)((char *)v8 + v14);
            memcpy_0(v17, v11, (unsigned int)Size);
            if ( v9 != (wchar_t *)v2 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
            v9 = v8;
            *v17 = 0;
            v11 = v17;
          }
        }
        v18 = v1 == 0 ? 0xC0000001 : 0;
LABEL_24:
        if ( v7 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        if ( v18 >= 0 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          v2 = (ULONG *)v8;
        }
        break;
      }
      if ( i != 1 )
        goto LABEL_28;
      OutputBufferLength = *v2;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x140017830  push    rbp
0x140017832  push    rbx
0x140017833  push    rsi
0x140017834  push    rdi
0x140017835  push    r12
0x140017837  push    r13
0x140017839  push    r14
0x14001783b  push    r15
0x14001783d  lea     rbp, [rsp-1Fh]
0x140017842  sub     rsp, 98h
0x140017849  xor     r12d, r12d
0x14001784c  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x140017850  xorps   xmm0, xmm0
0x140017853  mov     [rsp+0D0h+OpenOptions], 20h ; ' '; OpenOptions
0x14001785b  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001785f  mov     [rbp+57h+arg_0], r12d
0x140017863  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140017867  mov     [rbp+57h+FileHandle], r12
0x14001786b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001786f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140017873  mov     edx, 0C0100000h; DesiredAccess
0x140017878  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140017880  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140017884  mov     edi, r12d
0x140017887  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14001788f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140017894  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x14001789c  call    cs:__imp_ZwOpenFile
0x1400178a2  test    eax, eax
0x1400178a4  js      loc_140017ABF
0x1400178aa  lea     r14d, [r12+1]
0x1400178af  mov     ebx, 208h
0x1400178b4  mov     esi, r14d
0x1400178b7  mov     rcx, gs:60h
0x1400178c0  xor     edx, edx; Flags
0x1400178c2  mov     r8d, ebx; Size
0x1400178c5  mov     rcx, [rcx+30h]; HeapHandle
0x1400178c9  call    cs:__imp_RtlAllocateHeap
0x1400178cf  mov     rdi, rax
0x1400178d2  test    rax, rax
0x1400178d5  jz      loc_140017ABF
0x1400178db  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400178df  xor     r9d, r9d; ApcContext
0x1400178e2  mov     [rsp+0D0h+OutputBufferLength], ebx; OutputBufferLength
0x1400178e6  xor     r8d, r8d; ApcRoutine
0x1400178e9  mov     [rsp+0D0h+OutputBuffer], rax; OutputBuffer
0x1400178ee  xor     edx, edx; Event
0x1400178f0  mov     [rsp+0D0h+InputBufferLength], 4; InputBufferLength
0x1400178f8  lea     rax, [rbp+57h+arg_0]
0x1400178fc  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x140017901  lea     rax, [rbp+57h+IoStatusBlock]
0x140017905  mov     [rsp+0D0h+OpenOptions], 2D5928h; IoControlCode
0x14001790d  mov     qword ptr [rsp+0D0h+ShareAccess], rax; IoStatusBlock
0x140017912  mov     [rbp+57h+arg_0], r14d
0x140017916  call    cs:__imp_ZwDeviceIoControlFile
0x14001791c  cmp     eax, 0C0000023h
0x140017921  jnz     short loc_140017950
0x140017923  cmp     esi, r14d
0x140017926  jnz     loc_140017AA4
0x14001792c  mov     rcx, gs:60h
0x140017935  mov     r8, rdi; P
0x140017938  mov     ebx, [rdi]
0x14001793a  xor     edx, edx; Flags
0x14001793c  mov     rcx, [rcx+30h]; HeapHandle
0x140017940  call    cs:__imp_RtlFreeHeap
0x140017946  mov     esi, 2
0x14001794b  jmp     loc_1400178B7
0x140017950  test    eax, eax
0x140017952  js      loc_140017AA4
0x140017958  mov     r14, r12
0x14001795b  mov     [rbp+57h+Src], r12
0x14001795f  mov     r15, r12
0x140017962  mov     r13, rdi
0x140017965  mov     rbx, r12
0x140017968  mov     eax, 5Ch ; '\'
0x14001796d  mov     rcx, r13; Str
0x140017970  mov     edx, eax; Ch
0x140017972  call    cs:__imp_wcsrchr
0x140017978  mov     rsi, rax
0x14001797b  xor     eax, eax
0x14001797d  test    rbx, rbx
0x140017980  jz      short loc_140017987
0x140017982  mov     word ptr [rbx], 5Ch ; '\'
0x140017987  test    rsi, rsi
0x14001798a  jz      loc_140017A59
0x140017990  lea     rdx, [rbp+57h+Src]
0x140017994  mov     [rsi], ax
0x140017997  mov     rcx, r13; SourceString
0x14001799a  call    BiTranslateSymbolicLink
0x14001799f  mov     r14, [rbp+57h+Src]
0x1400179a3  test    eax, eax
0x1400179a5  js      loc_140017A4A
0x1400179ab  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400179af  mov     word ptr [rsi], 5Ch ; '\'
0x1400179b4  mov     rax, rcx
0x1400179b7  xor     r12d, r12d
0x1400179ba  inc     rax
0x1400179bd  cmp     [r14+rax*2], r12w
0x1400179c2  jnz     short loc_1400179BA
0x1400179c4  lea     ebx, [rax+rax]
0x1400179c7  mov     rax, rcx
0x1400179ca  inc     rax
0x1400179cd  cmp     [rsi+rax*2], r12w
0x1400179d2  jnz     short loc_1400179CA
0x1400179d4  mov     rcx, gs:60h
0x1400179dd  lea     eax, ds:2[rax*2]
0x1400179e4  lea     r8d, [rbx+rax]; Size
0x1400179e8  mov     dword ptr [rbp+57h+Size], eax
0x1400179eb  xor     edx, edx; Flags
0x1400179ed  mov     rcx, [rcx+30h]; HeapHandle
0x1400179f1  call    cs:__imp_RtlAllocateHeap
0x1400179f7  mov     r15, rax
0x1400179fa  test    rax, rax
0x1400179fd  jz      short loc_140017A52
0x1400179ff  mov     r8, rbx; Size
0x140017a02  mov     rdx, r14; Src
0x140017a05  mov     rcx, rax; void *
0x140017a08  mov     r12b, 1
0x140017a0b  call    memcpy_0
0x140017a10  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x140017a14  add     rbx, r15
0x140017a17  mov     rcx, rbx; void *
0x140017a1a  mov     rdx, rsi; Src
0x140017a1d  call    memcpy_0
0x140017a22  cmp     r13, rdi
0x140017a25  jz      short loc_140017A3F
0x140017a27  mov     rcx, gs:60h
0x140017a30  mov     r8, r13; P
0x140017a33  xor     edx, edx; Flags
0x140017a35  mov     rcx, [rcx+30h]; HeapHandle
0x140017a39  call    cs:__imp_RtlFreeHeap
0x140017a3f  xor     eax, eax
0x140017a41  mov     r13, r15
0x140017a44  mov     [rbx], ax
0x140017a47  mov     rsi, rbx
0x140017a4a  mov     rbx, rsi
0x140017a4d  jmp     loc_140017968
0x140017a52  mov     ebx, 0C0000017h
0x140017a57  jmp     short loc_140017A66
0x140017a59  neg     r12b
0x140017a5c  sbb     ebx, ebx
0x140017a5e  not     ebx
0x140017a60  and     ebx, 0C0000001h
0x140017a66  test    r14, r14
0x140017a69  jz      short loc_140017A83
0x140017a6b  mov     rcx, gs:60h
0x140017a74  mov     r8, r14; P
0x140017a77  xor     edx, edx; Flags
0x140017a79  mov     rcx, [rcx+30h]; HeapHandle
0x140017a7d  call    cs:__imp_RtlFreeHeap
0x140017a83  test    ebx, ebx
0x140017a85  js      short loc_140017ABF
0x140017a87  mov     rcx, gs:60h
0x140017a90  mov     r8, rdi; P
0x140017a93  xor     edx, edx; Flags
0x140017a95  mov     rcx, [rcx+30h]; HeapHandle
0x140017a99  call    cs:__imp_RtlFreeHeap
0x140017a9f  mov     rdi, r15
0x140017aa2  jmp     short loc_140017ABF
0x140017aa4  mov     rcx, gs:60h
0x140017aad  mov     r8, rdi; P
0x140017ab0  xor     edx, edx; Flags
0x140017ab2  mov     rcx, [rcx+30h]; HeapHandle
0x140017ab6  call    cs:__imp_RtlFreeHeap
0x140017abc  mov     rdi, r12
0x140017abf  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140017ac3  test    rcx, rcx
0x140017ac6  jz      short loc_140017ACE
0x140017ac8  call    cs:__imp_ZwClose
0x140017ace  mov     rax, rdi
0x140017ad1  add     rsp, 98h
0x140017ad8  pop     r15
0x140017ada  pop     r14
0x140017adc  pop     r13
0x140017ade  pop     r12
0x140017ae0  pop     rdi
0x140017ae1  pop     rsi
0x140017ae2  pop     rbx
0x140017ae3  pop     rbp
0x140017ae4  retn
```
