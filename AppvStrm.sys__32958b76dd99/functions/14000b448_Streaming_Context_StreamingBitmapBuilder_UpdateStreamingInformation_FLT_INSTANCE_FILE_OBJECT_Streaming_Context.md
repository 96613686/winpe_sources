# Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(_FLT_INSTANCE *,_FILE_OBJECT &,Streaming::Context::StreamingBitMap &)

- ea: `0x14000b448`
- end: `0x14000b619`
- name: `?UpdateStreamingInformation@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAVStreamingBitMap@23@@Z`
- size: `465`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, struct Streaming::Context::StreamingBitMap *)`
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1400044a0`
- `0x1400086a8`
- `0x14000b0bc`
- `0x14000f244`

## callees

- `0x14000279c`
- `0x14000b32c`
- `0x14000b448`
- `0x14000b620`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b4d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b4d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000b4ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000b4ca`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000b493`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000b493`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b480`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b480`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b542`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b542`
- `FLTMGR!FltTagFile` at `0x14000b505`
- `FLTMGR!FltTagFile` at `0x14000b505`

## string_xrefs

- `0x14000b578`: `StreamingBitmapBuilder::UpdateStreamingInformation() - Could not set the streaming information for file %s. Failure status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        struct Streaming::Context::StreamingBitMap *a3)
{
  bool v3; // di
  bool v4; // zf
  struct _ERESOURCE *v8; // rcx
  PVOID v9; // rsi
  NTSTATUS v10; // edi
  struct _FILE_OBJECT *v11; // r8
  unsigned int v12; // r9d
  __int64 v13; // rbx
  _QWORD *CurrentActivityID; // rax
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  PVOID DataBuffer; // [rsp+20h] [rbp-68h]
  __int64 DataBufferLength; // [rsp+30h] [rbp-58h] BYREF
  PVOID P; // [rsp+38h] [rbp-50h]
  _BYTE v21[8]; // [rsp+40h] [rbp-48h] BYREF
  volatile signed __int32 *v22; // [rsp+48h] [rbp-40h]

  v3 = 0;
  DataBufferLength = 0;
  v4 = *((_QWORD *)a3 + 6) == 0;
  P = 0;
  if ( !v4 )
  {
    KeEnterCriticalRegion();
    v3 = ExAcquireResourceSharedLite(*((PERESOURCE *)a3 + 6), 1u) == 1;
  }
  appv::shared::kernel::buffer<appv::shared::kernel::BMBuffer_alloc>::assign(
    &DataBufferLength,
    *((_QWORD *)a3 + 3),
    *((unsigned int *)a3 + 4));
  if ( v3 )
  {
    v8 = (struct _ERESOURCE *)*((_QWORD *)a3 + 6);
    if ( v8 )
    {
      ExReleaseResourceLite(v8);
      KeLeaveCriticalRegion();
    }
  }
  v9 = P;
  v10 = FltTagFile(Instance, FileObject, 0xC0000014, 0, P, DataBufferLength);
  if ( v10 >= 0 )
  {
    LOBYTE(v12) = 1;
    Streaming::FileOperations::ChangeFileAttribute(Instance, FileObject, v11, v12, (unsigned __int8)DataBuffer);
  }
  if ( *((_BYTE *)a3 + 56) )
    v10 = Streaming::Context::StreamingBitmapBuilder::UnMarkFileForStreaming(Instance, FileObject);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v10 < 0 )
  {
    v13 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v21, &FileObject->FileName);
    CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(&DataBufferLength);
    LODWORD(DataBuffer) = v10;
    LogWrite(
      1,
      *CurrentActivityID,
      L"StreamingBitmapBuilder::UpdateStreamingInformation() - Could not set the streaming information for file %s. Failur"
       "e status 0x%08X.",
      v13,
      DataBuffer);
    v15 = (volatile signed __int32 *)P;
    if ( P )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    v16 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000b448  push    rbx
0x14000b44a  push    rbp
0x14000b44b  push    rsi
0x14000b44c  push    rdi
0x14000b44d  push    r12
0x14000b44f  push    r14
0x14000b451  sub     rsp, 58h
0x14000b455  xor     dil, dil
0x14000b458  mov     [rsp+88h+var_58], 0
0x14000b461  cmp     qword ptr [r8+30h], 0
0x14000b466  mov     rbx, r8
0x14000b469  mov     rbp, rdx
0x14000b46c  mov     [rsp+88h+P], 0
0x14000b475  mov     r14, rcx
0x14000b478  mov     r12d, 1
0x14000b47e  jz      short loc_14000B4AA
0x14000b480  call    cs:__imp_KeEnterCriticalRegion
0x14000b487  nop     dword ptr [rax+rax+00h]
0x14000b48c  mov     rcx, [rbx+30h]; Resource
0x14000b490  mov     dl, r12b; Wait
0x14000b493  call    cs:__imp_ExAcquireResourceSharedLite
0x14000b49a  nop     dword ptr [rax+rax+00h]
0x14000b49f  cmp     al, r12b
0x14000b4a2  movzx   edi, dil
0x14000b4a6  cmovz   edi, r12d
0x14000b4aa  mov     r8d, [rbx+10h]
0x14000b4ae  lea     rcx, [rsp+88h+var_58]
0x14000b4b3  mov     rdx, [rbx+18h]
0x14000b4b7  call    ?assign@?$buffer@UBMBuffer_alloc@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEBEK@Z; appv::shared::kernel::buffer<appv::shared::kernel::BMBuffer_alloc>::assign(uchar const *,ulong)
0x14000b4bc  test    dil, dil
0x14000b4bf  jz      short loc_14000B4E2
0x14000b4c1  mov     rcx, [rbx+30h]; Resource
0x14000b4c5  test    rcx, rcx
0x14000b4c8  jz      short loc_14000B4E2
0x14000b4ca  call    cs:__imp_ExReleaseResourceLite
0x14000b4d1  nop     dword ptr [rax+rax+00h]
0x14000b4d6  call    cs:__imp_KeLeaveCriticalRegion
0x14000b4dd  nop     dword ptr [rax+rax+00h]
0x14000b4e2  movzx   eax, word ptr [rsp+88h+var_58]
0x14000b4e7  xor     r9d, r9d; Guid
0x14000b4ea  mov     rsi, [rsp+88h+P]
0x14000b4ef  mov     r8d, 0C0000014h; FileTag
0x14000b4f5  mov     [rsp+88h+DataBufferLength], ax; DataBufferLength
0x14000b4fa  mov     rdx, rbp; FileObject
0x14000b4fd  mov     rcx, r14; InitiatingInstance
0x14000b500  mov     [rsp+88h+DataBuffer], rsi; unsigned __int8
0x14000b505  call    cs:__imp_FltTagFile
0x14000b50c  nop     dword ptr [rax+rax+00h]
0x14000b511  mov     edi, eax
0x14000b513  test    eax, eax
0x14000b515  js      short loc_14000B525
0x14000b517  mov     r9b, r12b; unsigned int
0x14000b51a  mov     rdx, rbp; FileObject
0x14000b51d  mov     rcx, r14; Instance
0x14000b520  call    ?ChangeFileAttribute@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@KE@Z; Streaming::FileOperations::ChangeFileAttribute(_FLT_INSTANCE *,_FILE_OBJECT &,ulong,uchar)
0x14000b525  cmp     byte ptr [rbx+38h], 0
0x14000b529  jz      short loc_14000B538
0x14000b52b  mov     rdx, rbp; FileObject
0x14000b52e  mov     rcx, r14; Instance
0x14000b531  call    ?UnMarkFileForStreaming@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@@Z; Streaming::Context::StreamingBitmapBuilder::UnMarkFileForStreaming(_FLT_INSTANCE *,_FILE_OBJECT &)
0x14000b536  mov     edi, eax
0x14000b538  test    rsi, rsi
0x14000b53b  jz      short loc_14000B54E
0x14000b53d  xor     edx, edx; Tag
0x14000b53f  mov     rcx, rsi; P
0x14000b542  call    cs:__imp_ExFreePoolWithTag
0x14000b549  nop     dword ptr [rax+rax+00h]
0x14000b54e  test    edi, edi
0x14000b550  jns     loc_14000B609
0x14000b556  lea     rdx, [rbp+58h]
0x14000b55a  lea     rcx, [rsp+88h+var_48]
0x14000b55f  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000b564  lea     rcx, [rsp+88h+var_58]
0x14000b569  mov     rbx, [rax]
0x14000b56c  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000b571  mov     r9, rbx
0x14000b574  mov     dword ptr [rsp+88h+DataBuffer], edi
0x14000b578  lea     r8, aStreamingbitma_3; "StreamingBitmapBuilder::UpdateStreaming"...
0x14000b57f  mov     ecx, r12d
0x14000b582  mov     rdx, [rax]
0x14000b585  call    LogWrite
0x14000b58a  mov     rbx, [rsp+88h+P]
0x14000b58f  or      esi, 0FFFFFFFFh
0x14000b592  test    rbx, rbx
0x14000b595  jz      short loc_14000B5CB
0x14000b597  mov     eax, esi
0x14000b599  lock xadd [rbx+8], eax
0x14000b59e  add     eax, esi
0x14000b5a0  jnz     short loc_14000B5CB
0x14000b5a2  mov     rax, [rbx]
0x14000b5a5  mov     rcx, rbx
0x14000b5a8  mov     rax, [rax+8]
0x14000b5ac  call    _guard_dispatch_icall
0x14000b5b1  mov     eax, esi
0x14000b5b3  lock xadd [rbx+0Ch], eax
0x14000b5b8  add     eax, esi
0x14000b5ba  jnz     short loc_14000B5CB
0x14000b5bc  mov     rax, [rbx]
0x14000b5bf  mov     rcx, rbx
0x14000b5c2  mov     rax, [rax+10h]
0x14000b5c6  call    _guard_dispatch_icall
0x14000b5cb  mov     rbx, [rsp+88h+var_40]
0x14000b5d0  test    rbx, rbx
0x14000b5d3  jz      short loc_14000B609
0x14000b5d5  mov     eax, esi
0x14000b5d7  lock xadd [rbx+8], eax
0x14000b5dc  add     eax, esi
0x14000b5de  jnz     short loc_14000B609
0x14000b5e0  mov     rax, [rbx]
0x14000b5e3  mov     rcx, rbx
0x14000b5e6  mov     rax, [rax+8]
0x14000b5ea  call    _guard_dispatch_icall
0x14000b5ef  mov     eax, esi
0x14000b5f1  lock xadd [rbx+0Ch], eax
0x14000b5f6  add     eax, esi
0x14000b5f8  jnz     short loc_14000B609
0x14000b5fa  mov     rax, [rbx]
0x14000b5fd  mov     rcx, rbx
0x14000b600  mov     rax, [rax+10h]
0x14000b604  call    _guard_dispatch_icall
0x14000b609  mov     eax, edi
0x14000b60b  add     rsp, 58h
0x14000b60f  pop     r14
0x14000b611  pop     r12
0x14000b613  pop     rdi
0x14000b614  pop     rsi
0x14000b615  pop     rbp
0x14000b616  pop     rbx
0x14000b617  retn
```
