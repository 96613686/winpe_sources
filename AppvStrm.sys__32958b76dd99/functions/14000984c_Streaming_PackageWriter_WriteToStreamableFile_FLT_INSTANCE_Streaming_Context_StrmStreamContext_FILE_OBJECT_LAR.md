# Streaming::PackageWriter::WriteToStreamableFile(_FLT_INSTANCE *,Streaming::Context::StrmStreamContext *,_FILE_OBJECT &,_LARGE_INTEGER,void *,ulong,ulong,bool,ulong &)

- ea: `0x14000984c`
- end: `0x140009b52`
- name: `?WriteToStreamableFile@PackageWriter@Streaming@@SAJPEAU_FLT_INSTANCE@@PEAUStrmStreamContext@Context@2@AEAU_FILE_OBJECT@@T_LARGE_INTEGER@@PEAXKK_NAEAK@Z`
- size: `774`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, struct Streaming::Context::StrmStreamContext *, struct _FILE_OBJECT *, union _LARGE_INTEGER, void *Src, size_t Size, unsigned int, ULONG, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14000935c`
- `0x14000f244`

## callees

- `0x1400010b0`
- `0x14000984c`
- `0x14000fab8`
- `0x14000fb9c`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400099ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400099ae`
- `ntoskrnl!ExAllocatePool2` at `0x140009915`
- `ntoskrnl!ExAllocatePool2` at `0x140009915`
- `FLTMGR!FltWriteFile` at `0x140009995`
- `FLTMGR!FltWriteFile` at `0x140009995`

## string_xrefs

- `0x140009b16`: `PackageWriter::WriteToStreamableFile() - PackageWriter::WriteToStreamableFile() - Invalid parameter was passed in the write request for file %s. Size %lld from offset %lld with data size %ld. Failure status 0x%08X.`
- `0x1400099fe`: `PackageWriter::WriteToStreamableFile() - NTFS Error while trying to write to the file %s. Size %lld from offset %lld with data size %ld. Failure status 0x%08X.`
- `0x140009ab1`: `PackageWriter::WriteToStreamableFile() - NTFS Error while trying to write to the file %s. Size %lld from offset %lld with data size %ld. Failure status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::PackageWriter::WriteToStreamableFile(
        struct _FLT_INSTANCE *a1,
        struct Streaming::Context::StrmStreamContext *a2,
        struct _FILE_OBJECT *a3,
        union _LARGE_INTEGER a4,
        void *Src,
        size_t Size,
        unsigned int a7,
        ULONG a8,
        unsigned int *a9)
{
  size_t v12; // r14
  LONGLONG v13; // r9
  LONGLONG v14; // rsi
  unsigned int v15; // edi
  void *v17; // rbx
  void *Pool2; // rax
  void *Buffer; // rdi
  NTSTATUS v20; // r15d
  union _LARGE_INTEGER v21; // rdi
  __int64 v22; // rsi
  __int64 v23; // rbx
  GUID **CurrentActivityID; // rax
  __int64 v25; // rdi
  GUID **v26; // rax
  PULONG BytesWritten; // [rsp+30h] [rbp-78h]
  PFLT_COMPLETED_ASYNC_IO_CALLBACK CallbackRoutine; // [rsp+38h] [rbp-70h]
  GUID *v29[2]; // [rsp+50h] [rbp-58h] BYREF
  GUID *v30[9]; // [rsp+60h] [rbp-48h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+C8h] [rbp+20h] BYREF

  ByteOffset = a4;
  a8 = 0;
  *a9 = 0;
  v12 = (unsigned int)Size;
  v13 = (unsigned int)Size + a4.QuadPart;
  v14 = *((_QWORD *)a2 + 10);
  if ( v14 >= v13
    && (unsigned __int16)((a4.QuadPart >> 63) + LOWORD(a4.LowPart)) == (unsigned __int64)(unsigned __int16)(a4.QuadPart >> 63)
    && (!(_WORD)Size || v13 == v14) )
  {
    v15 = a7;
    if ( Streaming::Context::StreamingBitMap::IsSafeToRead(*((PRTL_BITMAP *)a2 + 11), a4, Size) )
      return 0;
    v17 = 0;
    if ( (unsigned int)v12 % v15 )
    {
      Pool2 = (void *)ExAllocatePool2(256, -v15 & ((_DWORD)v12 + v15 - 1), 1719101043);
      v17 = Pool2;
      if ( !Pool2 )
        return 3221225626LL;
      Buffer = Pool2;
      memmove(Pool2, Src, v12);
    }
    else
    {
      Buffer = Src;
    }
    v20 = FltWriteFile(a1, a3, &ByteOffset, v12, Buffer, 5u, &a8, 0, 0);
    if ( v17 )
      ExFreePoolWithTag(v17, 0);
    if ( v20 >= 0 )
    {
      return Streaming::Context::StreamingBitMap::Update(*((PRTL_BITMAP *)a2 + 11), ByteOffset, v12, a9) == 0
           ? 0xC00000E5
           : 0;
    }
    else
    {
      v21 = ByteOffset;
      v22 = *((_QWORD *)a2 + 10);
      v23 = *Streaming::Utils::GetNullTerminated(v30, &a3->FileName.Length);
      CurrentActivityID = Streaming::Utils::GetCurrentActivityID(v29);
      LODWORD(CallbackRoutine) = v20;
      LODWORD(BytesWritten) = v12;
      LogWrite(
        1,
        *CurrentActivityID,
        L"PackageWriter::WriteToStreamableFile() - NTFS Error while trying to write to the file %s. Size %lld from offset "
         "%lld with data size %ld. Failure status 0x%08X.",
        v23,
        v22,
        v21.QuadPart,
        BytesWritten,
        CallbackRoutine);
      kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>((__int64)v29);
      kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>((__int64)v30);
      return (unsigned int)v20;
    }
  }
  else
  {
    v25 = *Streaming::Utils::GetNullTerminated(v29, &a3->FileName.Length);
    v26 = Streaming::Utils::GetCurrentActivityID(v30);
    LogWrite(
      1,
      *v26,
      L"PackageWriter::WriteToStreamableFile() - PackageWriter::WriteToStreamableFile() - Invalid parameter was passed in "
       "the write request for file %s. Size %lld from offset %lld with data size %ld. Failure status 0x%08X.",
      v25,
      v14,
      a4.QuadPart,
      v12,
      -1073741811);
    kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>((__int64)v30);
    kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>((__int64)v29);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000984c  mov     rax, rsp
0x14000984f  mov     [rax+20h], r9
0x140009853  mov     [rax+18h], r8
0x140009857  mov     [rax+10h], rdx
0x14000985b  mov     [rax+8], rcx
0x14000985f  push    rbx
0x140009860  push    rsi
0x140009861  push    rdi
0x140009862  push    r12
0x140009864  push    r13
0x140009866  push    r14
0x140009868  push    r15
0x14000986a  sub     rsp, 70h
0x14000986e  mov     rbx, r9
0x140009871  mov     r12, r8
0x140009874  mov     r13, rdx
0x140009877  mov     dword ptr [rax+40h], 0
0x14000987e  mov     rax, [rsp+0A8h+arg_40]
0x140009886  mov     dword ptr [rax], 0
0x14000988c  mov     r14d, dword ptr [rsp+0A8h+Size]
0x140009894  add     r9, r14
0x140009897  mov     rsi, [rdx+50h]
0x14000989b  cmp     rsi, r9
0x14000989e  jl      loc_140009ADE
0x1400098a4  mov     rax, rbx
0x1400098a7  cqo
0x1400098a9  mov     ecx, 0FFFFh
0x1400098ae  and     rdx, rcx
0x1400098b1  add     rax, rdx
0x1400098b4  and     rax, rcx
0x1400098b7  cmp     rax, rdx
0x1400098ba  jnz     loc_140009ADE
0x1400098c0  test    r14w, r14w
0x1400098c4  jz      short loc_1400098CF
0x1400098c6  cmp     r9, rsi
0x1400098c9  jnz     loc_140009ADE
0x1400098cf  mov     edi, [rsp+0A8h+arg_30]
0x1400098d6  mov     r8d, r14d; unsigned int
0x1400098d9  mov     rdx, rbx; union _LARGE_INTEGER
0x1400098dc  mov     rcx, [r13+58h]; BitMapHeader
0x1400098e0  call    ?IsSafeToRead@StreamingBitMap@Context@Streaming@@QEAAET_LARGE_INTEGER@@K@Z; Streaming::Context::StreamingBitMap::IsSafeToRead(_LARGE_INTEGER,ulong)
0x1400098e5  test    al, al
0x1400098e7  jz      short loc_1400098F0
0x1400098e9  xor     eax, eax
0x1400098eb  jmp     loc_140009B41
0x1400098f0  xor     ebx, ebx
0x1400098f2  xor     edx, edx
0x1400098f4  mov     eax, r14d
0x1400098f7  div     edi
0x1400098f9  test    edx, edx
0x1400098fb  jz      short loc_14000994B
0x1400098fd  lea     edx, [rdi-1]
0x140009900  add     edx, r14d
0x140009903  neg     edi
0x140009905  mov     eax, edi
0x140009907  and     rdx, rax
0x14000990a  mov     ecx, 100h
0x14000990f  mov     r8d, 66776673h
0x140009915  call    cs:__imp_ExAllocatePool2
0x14000991c  nop     dword ptr [rax+rax+00h]
0x140009921  mov     rbx, rax
0x140009924  test    rax, rax
0x140009927  jnz     short loc_140009933
0x140009929  mov     eax, 0C000009Ah
0x14000992e  jmp     loc_140009B41
0x140009933  mov     rdi, rax
0x140009936  mov     r8, r14; Size
0x140009939  mov     rdx, [rsp+0A8h+Src]; Src
0x140009941  mov     rcx, rax; void *
0x140009944  call    memmove
0x140009949  jmp     short loc_140009953
0x14000994b  mov     rdi, [rsp+0A8h+Src]
0x140009953  mov     [rsp+0A8h+CallbackContext], 0; CallbackContext
0x14000995c  mov     [rsp+0A8h+CallbackRoutine], 0; CallbackRoutine
0x140009965  lea     rax, [rsp+0A8h+arg_38]
0x14000996d  mov     [rsp+0A8h+BytesWritten], rax; BytesWritten
0x140009972  mov     [rsp+0A8h+Flags], 5; Flags
0x14000997a  mov     [rsp+0A8h+Buffer], rdi; unsigned __int8
0x14000997f  mov     r9d, r14d; Length
0x140009982  lea     r8, [rsp+0A8h+ByteOffset]; ByteOffset
0x14000998a  mov     rdx, r12; FileObject
0x14000998d  mov     rcx, [rsp+0A8h+InitiatingInstance]; InitiatingInstance
0x140009995  call    cs:__imp_FltWriteFile
0x14000999c  nop     dword ptr [rax+rax+00h]
0x1400099a1  mov     r15d, eax
0x1400099a4  test    rbx, rbx
0x1400099a7  jz      short loc_1400099BA
0x1400099a9  xor     edx, edx; Tag
0x1400099ab  mov     rcx, rbx; P
0x1400099ae  call    cs:__imp_ExFreePoolWithTag
0x1400099b5  nop     dword ptr [rax+rax+00h]
0x1400099ba  test    r15d, r15d
0x1400099bd  jns     short loc_140009A2E
0x1400099bf  mov     rdi, qword ptr [rsp+0A8h+ByteOffset]
0x1400099c7  mov     rsi, [r13+50h]
0x1400099cb  lea     rdx, [r12+58h]
0x1400099d0  lea     rcx, [rsp+0A8h+var_48]
0x1400099d5  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x1400099da  mov     rbx, [rax]
0x1400099dd  lea     rcx, [rsp+0A8h+var_58]
0x1400099e2  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400099e7  mov     dword ptr [rsp+0A8h+CallbackRoutine], r15d
0x1400099ec  mov     dword ptr [rsp+0A8h+BytesWritten], r14d
0x1400099f1  mov     qword ptr [rsp+0A8h+Flags], rdi
0x1400099f6  mov     [rsp+0A8h+Buffer], rsi
0x1400099fb  mov     r9, rbx
0x1400099fe  lea     r8, aPackagewriterW; "PackageWriter::WriteToStreamableFile() "...
0x140009a05  mov     rdx, [rax]
0x140009a08  mov     ecx, 1
0x140009a0d  call    LogWrite
0x140009a12  lea     rcx, [rsp+0A8h+var_58]
0x140009a17  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x140009a1c  lea     rcx, [rsp+0A8h+var_48]
0x140009a21  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x140009a26  mov     eax, r15d
0x140009a29  jmp     loc_140009B41
0x140009a2e  mov     r9, [rsp+0A8h+arg_40]; unsigned int *
0x140009a36  mov     r8d, r14d; unsigned int
0x140009a39  mov     rdx, qword ptr [rsp+0A8h+ByteOffset]; union _LARGE_INTEGER
0x140009a41  mov     rcx, [r13+58h]; BitMapHeader
0x140009a45  call    ?Update@StreamingBitMap@Context@Streaming@@QEAAET_LARGE_INTEGER@@KAEAKE@Z; Streaming::Context::StreamingBitMap::Update(_LARGE_INTEGER,ulong,ulong &,uchar)
0x140009a4a  neg     al
0x140009a4c  sbb     eax, eax
0x140009a4e  not     eax
0x140009a50  and     eax, 0C00000E5h
0x140009a55  jmp     loc_140009B41
0x140009a5a  mov     r14d, eax
0x140009a5d  mov     rsi, qword ptr [rsp+0A8h+ByteOffset]
0x140009a65  mov     rcx, [rsp+0A8h+arg_8]
0x140009a6d  mov     rdi, [rcx+50h]
0x140009a71  mov     rdx, [rsp+0A8h+arg_10]
0x140009a79  add     rdx, 58h ; 'X'
0x140009a7d  lea     rcx, [rsp+0A8h+var_58]
0x140009a82  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140009a87  mov     rbx, [rax]
0x140009a8a  lea     rcx, [rsp+0A8h+var_48]
0x140009a8f  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140009a94  mov     dword ptr [rsp+0A8h+CallbackRoutine], r14d
0x140009a99  mov     ecx, dword ptr [rsp+0A8h+Size]
0x140009aa0  mov     dword ptr [rsp+0A8h+BytesWritten], ecx
0x140009aa4  mov     qword ptr [rsp+0A8h+Flags], rsi
0x140009aa9  mov     [rsp+0A8h+Buffer], rdi
0x140009aae  mov     r9, rbx
0x140009ab1  lea     r8, aPackagewriterW; "PackageWriter::WriteToStreamableFile() "...
0x140009ab8  mov     rdx, [rax]
0x140009abb  mov     ecx, 1
0x140009ac0  call    LogWrite
0x140009ac5  lea     rcx, [rsp+0A8h+var_48]
0x140009aca  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x140009acf  lea     rcx, [rsp+0A8h+var_58]
0x140009ad4  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x140009ad9  mov     eax, r14d
0x140009adc  jmp     short loc_140009B41
0x140009ade  lea     rdx, [r8+58h]
0x140009ae2  lea     rcx, [rsp+0A8h+var_58]
0x140009ae7  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140009aec  mov     rdi, [rax]
0x140009aef  lea     rcx, [rsp+0A8h+var_48]
0x140009af4  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140009af9  mov     r15d, 0C000000Dh
0x140009aff  mov     dword ptr [rsp+0A8h+CallbackRoutine], r15d
0x140009b04  mov     dword ptr [rsp+0A8h+BytesWritten], r14d
0x140009b09  mov     qword ptr [rsp+0A8h+Flags], rbx
0x140009b0e  mov     [rsp+0A8h+Buffer], rsi
0x140009b13  mov     r9, rdi
0x140009b16  lea     r8, aPackagewriterW_0; "PackageWriter::WriteToStreamableFile() "...
0x140009b1d  mov     rdx, [rax]
0x140009b20  mov     ecx, 1
0x140009b25  call    LogWrite
0x140009b2a  lea     rcx, [rsp+0A8h+var_48]
0x140009b2f  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x140009b34  lea     rcx, [rsp+0A8h+var_58]
0x140009b39  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x140009b3e  mov     eax, r15d
0x140009b41  add     rsp, 70h
0x140009b45  pop     r15
0x140009b47  pop     r14
0x140009b49  pop     r13
0x140009b4b  pop     r12
0x140009b4d  pop     rdi
0x140009b4e  pop     rsi
0x140009b4f  pop     rbx
0x140009b50  retn
```
