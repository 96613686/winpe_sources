# Streaming::Context::StreamingBitmapBuilder::UnMarkFileForStreaming(_FLT_INSTANCE *,_FILE_OBJECT &)

- ea: `0x14000b32c`
- end: `0x14000b440`
- name: `?UnMarkFileForStreaming@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000b448`

## callees

- `0x14000279c`
- `0x14000b32c`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `FLTMGR!FltUntagFile` at `0x14000b34a`
- `FLTMGR!FltUntagFile` at `0x14000b34a`

## string_xrefs

- `0x14000b38a`: `StreamingBitmapBuilder::UnMarkFileForStreaming() - Could not delete the streaming information for file %s. Failure status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamingBitmapBuilder::UnMarkFileForStreaming(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject)
{
  NTSTATUS v4; // eax
  struct _FILE_OBJECT *v5; // r8
  int v6; // edi
  __int64 v7; // rbx
  GUID **CurrentActivityID; // rax
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  int v12; // [rsp+20h] [rbp-38h]
  GUID *v13; // [rsp+30h] [rbp-28h] BYREF
  volatile signed __int32 *v14; // [rsp+38h] [rbp-20h]
  __int64 v15; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v16; // [rsp+48h] [rbp-10h]

  v4 = FltUntagFile(Instance, FileObject, 0xC0000014, 0);
  v6 = 0;
  if ( v4 != -1073741195 )
    v6 = v4;
  if ( v6 >= 0 )
  {
    Streaming::FileOperations::ChangeFileAttribute(Instance, FileObject, v5, 0);
  }
  else
  {
    v7 = *Streaming::Utils::GetNullTerminated(&v15, &FileObject->FileName.Length);
    CurrentActivityID = Streaming::Utils::GetCurrentActivityID(&v13);
    v12 = v6;
    LogWrite(
      1,
      *CurrentActivityID,
      L"StreamingBitmapBuilder::UnMarkFileForStreaming() - Could not delete the streaming information for file %s. Failure status 0x%08X.",
      v7,
      v12);
    v9 = v14;
    if ( v14 )
    {
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    v10 = v16;
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000b32c  mov     [rsp+arg_0], rbx
0x14000b331  mov     [rsp+arg_8], rsi
0x14000b336  push    rdi
0x14000b337  sub     rsp, 50h
0x14000b33b  xor     r9d, r9d; Guid
0x14000b33e  mov     r8d, 0C0000014h; FileTag
0x14000b344  mov     rbx, rdx
0x14000b347  mov     rsi, rcx
0x14000b34a  call    cs:__imp_FltUntagFile
0x14000b351  nop     dword ptr [rax+rax+00h]
0x14000b356  xor     edi, edi
0x14000b358  cmp     eax, 0C0000275h
0x14000b35d  cmovnz  edi, eax
0x14000b360  test    edi, edi
0x14000b362  jns     loc_14000B41F
0x14000b368  lea     rdx, [rbx+58h]
0x14000b36c  lea     rcx, [rsp+58h+var_18]
0x14000b371  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000b376  lea     rcx, [rsp+58h+var_28]
0x14000b37b  mov     rbx, [rax]
0x14000b37e  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000b383  mov     r9, rbx
0x14000b386  mov     [rsp+58h+var_38], edi
0x14000b38a  lea     r8, aStreamingbitma; "StreamingBitmapBuilder::UnMarkFileForSt"...
0x14000b391  mov     ecx, 1
0x14000b396  mov     rdx, [rax]
0x14000b399  call    LogWrite
0x14000b39e  mov     rbx, [rsp+58h+var_20]
0x14000b3a3  or      esi, 0FFFFFFFFh
0x14000b3a6  test    rbx, rbx
0x14000b3a9  jz      short loc_14000B3DF
0x14000b3ab  mov     eax, esi
0x14000b3ad  lock xadd [rbx+8], eax
0x14000b3b2  add     eax, esi
0x14000b3b4  jnz     short loc_14000B3DF
0x14000b3b6  mov     rax, [rbx]
0x14000b3b9  mov     rcx, rbx
0x14000b3bc  mov     rax, [rax+8]
0x14000b3c0  call    _guard_dispatch_icall
0x14000b3c5  mov     eax, esi
0x14000b3c7  lock xadd [rbx+0Ch], eax
0x14000b3cc  add     eax, esi
0x14000b3ce  jnz     short loc_14000B3DF
0x14000b3d0  mov     rax, [rbx]
0x14000b3d3  mov     rcx, rbx
0x14000b3d6  mov     rax, [rax+10h]
0x14000b3da  call    _guard_dispatch_icall
0x14000b3df  mov     rbx, [rsp+58h+var_10]
0x14000b3e4  test    rbx, rbx
0x14000b3e7  jz      short loc_14000B42D
0x14000b3e9  mov     eax, esi
0x14000b3eb  lock xadd [rbx+8], eax
0x14000b3f0  add     eax, esi
0x14000b3f2  jnz     short loc_14000B42D
0x14000b3f4  mov     rax, [rbx]
0x14000b3f7  mov     rcx, rbx
0x14000b3fa  mov     rax, [rax+8]
0x14000b3fe  call    _guard_dispatch_icall
0x14000b403  mov     edx, esi
0x14000b405  lock xadd [rbx+0Ch], edx
0x14000b40a  add     edx, esi
0x14000b40c  jnz     short loc_14000B42D
0x14000b40e  mov     rdx, [rbx]
0x14000b411  mov     rcx, rbx
0x14000b414  mov     rax, [rdx+10h]
0x14000b418  call    _guard_dispatch_icall
0x14000b41d  jmp     short loc_14000B42D
0x14000b41f  xor     r9d, r9d; unsigned int
0x14000b422  mov     rdx, rbx; FileObject
0x14000b425  mov     rcx, rsi; Instance
0x14000b428  call    ?ChangeFileAttribute@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@KE@Z; Streaming::FileOperations::ChangeFileAttribute(_FLT_INSTANCE *,_FILE_OBJECT &,ulong,uchar)
0x14000b42d  mov     rbx, [rsp+58h+arg_0]
0x14000b432  mov     eax, edi
0x14000b434  mov     rsi, [rsp+58h+arg_8]
0x14000b439  add     rsp, 50h
0x14000b43d  pop     rdi
0x14000b43e  retn
```
