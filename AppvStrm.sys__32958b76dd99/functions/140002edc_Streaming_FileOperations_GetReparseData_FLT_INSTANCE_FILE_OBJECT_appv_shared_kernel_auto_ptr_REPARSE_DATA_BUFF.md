# Streaming::FileOperations::GetReparseData(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<_REPARSE_DATA_BUFFER,appv::shared::kernel::AllocDelete<_REPARSE_DATA_BUFFER>> &)

- ea: `0x140002edc`
- end: `0x1400030b1`
- name: `?GetReparseData@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@U_REPARSE_DATA_BUFFER@@U?$AllocDelete@U_REPARSE_DATA_BUFFER@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x14000b0bc`

## callees

- `0x140002edc`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002f7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002fc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003078`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003095`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002f7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002fc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003078`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003095`
- `ntoskrnl!ExAllocatePool2` at `0x140002f04`
- `ntoskrnl!ExAllocatePool2` at `0x140002fac`
- `ntoskrnl!ExAllocatePool2` at `0x140002f04`
- `ntoskrnl!ExAllocatePool2` at `0x140002fac`
- `FLTMGR!FltFsControlFile` at `0x140002f57`
- `FLTMGR!FltFsControlFile` at `0x140003061`
- `FLTMGR!FltFsControlFile` at `0x140002f57`
- `FLTMGR!FltFsControlFile` at `0x140003061`

## string_xrefs

- `0x140002f22`: `Streaming::FileOperations::GetReparseData() - Low memory error.`
- `0x140002fdb`: `Streaming::FileOperations::GetReparseData()- Low memory error.`

## pseudocode

```c
__int64 __fastcall Streaming::FileOperations::GetReparseData(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        void **a3)
{
  unsigned __int16 *OutputBuffer; // rax
  unsigned __int16 *v7; // rsi
  _QWORD *CurrentActivityID; // rax
  const wchar_t *v9; // r8
  NTSTATUS v10; // eax
  unsigned int v11; // edi
  void *v12; // rcx
  ULONG OutputBufferLength; // r15d
  void *Pool2; // rdi
  volatile signed __int32 *v16; // rdi
  NTSTATUS v17; // esi
  void *v18; // rcx
  _BYTE v19[8]; // [rsp+40h] [rbp-48h] BYREF
  volatile signed __int32 *v20; // [rsp+48h] [rbp-40h]

  OutputBuffer = (unsigned __int16 *)ExAllocatePool2(256, 28, 1685218931);
  v7 = OutputBuffer;
  if ( !OutputBuffer )
  {
    CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v19);
    v9 = L"Streaming::FileOperations::GetReparseData() - Low memory error.";
    goto LABEL_11;
  }
  v10 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, OutputBuffer, 0x1Cu, 0);
  v11 = v10;
  if ( v10 != -2147483643 )
  {
    if ( v10 < 0 )
    {
      v12 = v7;
    }
    else
    {
      v12 = *a3;
      *a3 = v7;
      if ( !v12 )
        return v11;
    }
    ExFreePoolWithTag(v12, 0);
    return v11;
  }
  OutputBufferLength = v7[2] + 28;
  Pool2 = (void *)ExAllocatePool2(256, OutputBufferLength, 1685218931);
  ExFreePoolWithTag(v7, 0);
  if ( !Pool2 )
  {
    CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v19);
    v9 = L"Streaming::FileOperations::GetReparseData()- Low memory error.";
LABEL_11:
    LogWrite(1, *CurrentActivityID, v9);
    v16 = v20;
    if ( v20 && _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return 3221225626LL;
  }
  v17 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, Pool2, OutputBufferLength, 0);
  if ( v17 >= 0 )
  {
    v18 = *a3;
    *a3 = Pool2;
    if ( v18 )
      ExFreePoolWithTag(v18, 0);
    return 0;
  }
  else
  {
    ExFreePoolWithTag(Pool2, 0);
    return (unsigned int)v17;
  }
}

```

## disassembly

```asm
0x140002edc  push    rbx
0x140002ede  push    rbp
0x140002edf  push    rsi
0x140002ee0  push    rdi
0x140002ee1  push    r14
0x140002ee3  push    r15
0x140002ee5  sub     rsp, 58h
0x140002ee9  mov     rbx, r8
0x140002eec  mov     rbp, rdx
0x140002eef  mov     r14, rcx
0x140002ef2  mov     edi, 1Ch
0x140002ef7  mov     edx, edi
0x140002ef9  mov     r8d, 64726673h
0x140002eff  mov     ecx, 100h
0x140002f04  call    cs:__imp_ExAllocatePool2
0x140002f0b  nop     dword ptr [rax+rax+00h]
0x140002f10  mov     rsi, rax
0x140002f13  test    rax, rax
0x140002f16  jnz     short loc_140002F2E
0x140002f18  lea     rcx, [rsp+88h+var_48]
0x140002f1d  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140002f22  lea     r8, aStreamingFileo; "Streaming::FileOperations::GetReparseDa"...
0x140002f29  jmp     loc_140002FE2
0x140002f2e  mov     [rsp+88h+LengthReturned], 0; LengthReturned
0x140002f37  xor     r9d, r9d; InputBuffer
0x140002f3a  mov     [rsp+88h+OutputBufferLength], edi; OutputBufferLength
0x140002f3e  mov     r8d, 900A8h; FsControlCode
0x140002f44  mov     [rsp+88h+OutputBuffer], rsi; OutputBuffer
0x140002f49  mov     rdx, rbp; FileObject
0x140002f4c  mov     rcx, r14; Instance
0x140002f4f  mov     [rsp+88h+InputBufferLength], 0; InputBufferLength
0x140002f57  call    cs:__imp_FltFsControlFile
0x140002f5e  nop     dword ptr [rax+rax+00h]
0x140002f63  mov     edi, eax
0x140002f65  cmp     eax, 80000005h
0x140002f6a  jz      short loc_140002F95
0x140002f6c  test    eax, eax
0x140002f6e  js      short loc_140002F90
0x140002f70  mov     rcx, [rbx]; P
0x140002f73  mov     [rbx], rsi
0x140002f76  test    rcx, rcx
0x140002f79  jz      short loc_140002F89
0x140002f7b  xor     edx, edx; Tag
0x140002f7d  call    cs:__imp_ExFreePoolWithTag
0x140002f84  nop     dword ptr [rax+rax+00h]
0x140002f89  mov     eax, edi
0x140002f8b  jmp     loc_1400030A3
0x140002f90  mov     rcx, rsi
0x140002f93  jmp     short loc_140002F7B
0x140002f95  movzx   r15d, word ptr [rsi+4]
0x140002f9a  mov     ecx, 100h
0x140002f9f  add     r15d, 1Ch
0x140002fa3  mov     r8d, 64726673h
0x140002fa9  mov     edx, r15d
0x140002fac  call    cs:__imp_ExAllocatePool2
0x140002fb3  nop     dword ptr [rax+rax+00h]
0x140002fb8  xor     edx, edx; Tag
0x140002fba  mov     rcx, rsi; P
0x140002fbd  mov     rdi, rax
0x140002fc0  call    cs:__imp_ExFreePoolWithTag
0x140002fc7  nop     dword ptr [rax+rax+00h]
0x140002fcc  test    rdi, rdi
0x140002fcf  jnz     short loc_140003037
0x140002fd1  lea     rcx, [rsp+88h+var_48]
0x140002fd6  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140002fdb  lea     r8, aStreamingFileo_0; "Streaming::FileOperations::GetReparseDa"...
0x140002fe2  mov     rdx, [rax]
0x140002fe5  mov     ecx, 1
0x140002fea  call    LogWrite
0x140002fef  mov     rdi, [rsp+88h+var_40]
0x140002ff4  test    rdi, rdi
0x140002ff7  jz      short loc_140003030
0x140002ff9  or      ebx, 0FFFFFFFFh
0x140002ffc  mov     eax, ebx
0x140002ffe  lock xadd [rdi+8], eax
0x140003003  add     eax, ebx
0x140003005  jnz     short loc_140003030
0x140003007  mov     rax, [rdi]
0x14000300a  mov     rcx, rdi
0x14000300d  mov     rax, [rax+8]
0x140003011  call    _guard_dispatch_icall
0x140003016  mov     eax, ebx
0x140003018  lock xadd [rdi+0Ch], eax
0x14000301d  add     eax, ebx
0x14000301f  jnz     short loc_140003030
0x140003021  mov     rax, [rdi]
0x140003024  mov     rcx, rdi
0x140003027  mov     rax, [rax+10h]
0x14000302b  call    _guard_dispatch_icall
0x140003030  mov     eax, 0C000009Ah
0x140003035  jmp     short loc_1400030A3
0x140003037  mov     [rsp+88h+LengthReturned], 0; LengthReturned
0x140003040  xor     r9d, r9d; InputBuffer
0x140003043  mov     [rsp+88h+OutputBufferLength], r15d; OutputBufferLength
0x140003048  mov     r8d, 900A8h; FsControlCode
0x14000304e  mov     [rsp+88h+OutputBuffer], rdi; OutputBuffer
0x140003053  mov     rdx, rbp; FileObject
0x140003056  mov     rcx, r14; Instance
0x140003059  mov     [rsp+88h+InputBufferLength], 0; InputBufferLength
0x140003061  call    cs:__imp_FltFsControlFile
0x140003068  nop     dword ptr [rax+rax+00h]
0x14000306d  mov     esi, eax
0x14000306f  test    eax, eax
0x140003071  jns     short loc_140003088
0x140003073  xor     edx, edx; Tag
0x140003075  mov     rcx, rdi; P
0x140003078  call    cs:__imp_ExFreePoolWithTag
0x14000307f  nop     dword ptr [rax+rax+00h]
0x140003084  mov     eax, esi
0x140003086  jmp     short loc_1400030A3
0x140003088  mov     rcx, [rbx]; P
0x14000308b  mov     [rbx], rdi
0x14000308e  test    rcx, rcx
0x140003091  jz      short loc_1400030A1
0x140003093  xor     edx, edx; Tag
0x140003095  call    cs:__imp_ExFreePoolWithTag
0x14000309c  nop     dword ptr [rax+rax+00h]
0x1400030a1  xor     eax, eax
0x1400030a3  add     rsp, 58h
0x1400030a7  pop     r15
0x1400030a9  pop     r14
0x1400030ab  pop     rdi
0x1400030ac  pop     rsi
0x1400030ad  pop     rbp
0x1400030ae  pop     rbx
0x1400030af  retn
```
