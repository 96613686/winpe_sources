# Streaming::Context::StreamingBitmapBuilder::ReadStreamingInformation(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StreamingBitMap,appv::shared::kernel::AllocDelete<Streaming::Context::StreamingBitMap>> &)

- ea: `0x14000b0bc`
- end: `0x14000b324`
- name: `?ReadStreamingInformation@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@VStreamingBitMap@Context@Streaming@@U?$AllocDelete@VStreamingBitMap@Context@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, struct Streaming::Context::StreamingBitMap **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, installer_update`

## callers

- `0x14000b748`

## callees

- `0x140002edc`
- `0x14000b0bc`
- `0x14000b448`
- `0x14000f7cc`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b1b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b1b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2fb`

## string_xrefs

- `0x14000b119`: `StreamingBitmapBuilder::ReadStreamingInformation() - Could not read the streaming information from file %s. Failure status 0x%08X.`
- `0x14000b1f7`: `StreamingBitmapBuilder::ReadStreamingInformation() - Could not read the streaming information from file %s. Failure status 0x%08X.`
- `0x14000b2ba`: `StreamingBitmapBuilder::ReadStreamingInformation() - Low memory error.`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamingBitmapBuilder::ReadStreamingInformation(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        struct Streaming::Context::StreamingBitMap **a3)
{
  int ReparseData; // esi
  __int64 v7; // rbx
  _QWORD *CurrentActivityID; // rax
  volatile signed __int32 *v9; // rdi
  volatile signed __int32 *v10; // rdi
  PVOID v12; // rdi
  __int64 v13; // rbx
  _QWORD *v14; // rax
  int v15; // r14d
  volatile signed __int32 *v16; // rsi
  volatile signed __int32 *v17; // rsi
  _QWORD *v18; // rax
  int v19; // [rsp+20h] [rbp-30h]
  int v20; // [rsp+20h] [rbp-30h]
  _BYTE v21[8]; // [rsp+30h] [rbp-20h] BYREF
  volatile signed __int32 *v22; // [rsp+38h] [rbp-18h]
  _BYTE v23[8]; // [rsp+40h] [rbp-10h] BYREF
  volatile signed __int32 *v24; // [rsp+48h] [rbp-8h]
  PVOID P; // [rsp+98h] [rbp+48h] BYREF

  P = 0;
  ReparseData = Streaming::FileOperations::GetReparseData(Instance, FileObject, &P);
  if ( ReparseData < 0 )
  {
    v7 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v23, &FileObject->FileName);
    CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v21);
    v19 = ReparseData;
    LogWrite(
      4,
      *CurrentActivityID,
      L"StreamingBitmapBuilder::ReadStreamingInformation() - Could not read the streaming information from file %s. Failur"
       "e status 0x%08X.",
      v7,
      v19);
    v9 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    v10 = v24;
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)ReparseData;
  }
  v12 = P;
  if ( *(_DWORD *)P != -1073741804 )
  {
    v13 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v21, &FileObject->FileName);
    v14 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v23);
    v15 = -1073741193;
    v20 = -1073741193;
    LogWrite(
      4,
      *v14,
      L"StreamingBitmapBuilder::ReadStreamingInformation() - Could not read the streaming information from file %s. Failur"
       "e status 0x%08X.",
      v13,
      v20);
    v16 = v24;
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    v17 = v22;
    if ( !v22 )
      goto LABEL_27;
    goto LABEL_19;
  }
  v15 = Streaming::Context::StreamingBitMap::CreateInstance((char *)P + 8, *((unsigned __int16 *)P + 2));
  if ( v15 >= 0 )
  {
    if ( *((_BYTE *)*a3 + 56) )
      Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(Instance, FileObject, *a3);
    goto LABEL_27;
  }
  v18 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v23);
  LogWrite(1, *v18, L"StreamingBitmapBuilder::ReadStreamingInformation() - Low memory error.");
  v17 = v24;
  if ( v24 )
  {
LABEL_19:
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
LABEL_27:
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14000b0bc  mov     [rsp-28h+arg_0], rbx
0x14000b0c1  mov     [rsp-28h+arg_8], rsi
0x14000b0c6  push    rbp
0x14000b0c7  push    rdi
0x14000b0c8  push    r12
0x14000b0ca  push    r14
0x14000b0cc  push    r15
0x14000b0ce  mov     rbp, rsp
0x14000b0d1  sub     rsp, 50h
0x14000b0d5  mov     r15, r8
0x14000b0d8  mov     [rbp+P], 0
0x14000b0e0  lea     r8, [rbp+P]
0x14000b0e4  mov     rbx, rdx
0x14000b0e7  mov     r12, rcx
0x14000b0ea  call    ?GetReparseData@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@U_REPARSE_DATA_BUFFER@@U?$AllocDelete@U_REPARSE_DATA_BUFFER@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::FileOperations::GetReparseData(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<_REPARSE_DATA_BUFFER,appv::shared::kernel::AllocDelete<_REPARSE_DATA_BUFFER>> &)
0x14000b0ef  mov     esi, eax
0x14000b0f1  test    eax, eax
0x14000b0f3  jns     loc_14000B1C8
0x14000b0f9  lea     rdx, [rbx+58h]
0x14000b0fd  lea     rcx, [rbp+var_10]
0x14000b101  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000b106  lea     rcx, [rbp+var_20]
0x14000b10a  mov     rbx, [rax]
0x14000b10d  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000b112  mov     r9, rbx
0x14000b115  mov     [rsp+50h+var_30], esi
0x14000b119  lea     r8, aStreamingbitma_0; "StreamingBitmapBuilder::ReadStreamingIn"...
0x14000b120  mov     ecx, 4
0x14000b125  mov     rdx, [rax]
0x14000b128  call    LogWrite
0x14000b12d  mov     rdi, [rbp+var_18]
0x14000b131  or      ebx, 0FFFFFFFFh
0x14000b134  test    rdi, rdi
0x14000b137  jz      short loc_14000B16D
0x14000b139  mov     eax, ebx
0x14000b13b  lock xadd [rdi+8], eax
0x14000b140  add     eax, ebx
0x14000b142  jnz     short loc_14000B16D
0x14000b144  mov     rax, [rdi]
0x14000b147  mov     rcx, rdi
0x14000b14a  mov     rax, [rax+8]
0x14000b14e  call    _guard_dispatch_icall
0x14000b153  mov     eax, ebx
0x14000b155  lock xadd [rdi+0Ch], eax
0x14000b15a  add     eax, ebx
0x14000b15c  jnz     short loc_14000B16D
0x14000b15e  mov     rax, [rdi]
0x14000b161  mov     rcx, rdi
0x14000b164  mov     rax, [rax+10h]
0x14000b168  call    _guard_dispatch_icall
0x14000b16d  mov     rdi, [rbp+var_8]
0x14000b171  test    rdi, rdi
0x14000b174  jz      short loc_14000B1AA
0x14000b176  mov     eax, ebx
0x14000b178  lock xadd [rdi+8], eax
0x14000b17d  add     eax, ebx
0x14000b17f  jnz     short loc_14000B1AA
0x14000b181  mov     rax, [rdi]
0x14000b184  mov     rcx, rdi
0x14000b187  mov     rax, [rax+8]
0x14000b18b  call    _guard_dispatch_icall
0x14000b190  mov     eax, ebx
0x14000b192  lock xadd [rdi+0Ch], eax
0x14000b197  add     eax, ebx
0x14000b199  jnz     short loc_14000B1AA
0x14000b19b  mov     rax, [rdi]
0x14000b19e  mov     rcx, rdi
0x14000b1a1  mov     rax, [rax+10h]
0x14000b1a5  call    _guard_dispatch_icall
0x14000b1aa  mov     rcx, [rbp+P]; P
0x14000b1ae  test    rcx, rcx
0x14000b1b1  jz      short loc_14000B1C1
0x14000b1b3  xor     edx, edx; Tag
0x14000b1b5  call    cs:__imp_ExFreePoolWithTag
0x14000b1bc  nop     dword ptr [rax+rax+00h]
0x14000b1c1  mov     eax, esi
0x14000b1c3  jmp     loc_14000B30A
0x14000b1c8  mov     rdi, [rbp+P]
0x14000b1cc  cmp     dword ptr [rdi], 0C0000014h
0x14000b1d2  jz      loc_14000B29A
0x14000b1d8  lea     rdx, [rbx+58h]
0x14000b1dc  lea     rcx, [rbp+var_20]
0x14000b1e0  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000b1e5  lea     rcx, [rbp+var_10]
0x14000b1e9  mov     rbx, [rax]
0x14000b1ec  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000b1f1  mov     r14d, 0C0000277h
0x14000b1f7  lea     r8, aStreamingbitma_0; "StreamingBitmapBuilder::ReadStreamingIn"...
0x14000b1fe  mov     r9, rbx
0x14000b201  mov     [rsp+50h+var_30], r14d
0x14000b206  mov     ecx, 4
0x14000b20b  mov     rdx, [rax]
0x14000b20e  call    LogWrite
0x14000b213  mov     rsi, [rbp+var_8]
0x14000b217  or      ebx, 0FFFFFFFFh
0x14000b21a  test    rsi, rsi
0x14000b21d  jz      short loc_14000B253
0x14000b21f  mov     eax, ebx
0x14000b221  lock xadd [rsi+8], eax
0x14000b226  add     eax, ebx
0x14000b228  jnz     short loc_14000B253
0x14000b22a  mov     rax, [rsi]
0x14000b22d  mov     rcx, rsi
0x14000b230  mov     rax, [rax+8]
0x14000b234  call    _guard_dispatch_icall
0x14000b239  mov     eax, ebx
0x14000b23b  lock xadd [rsi+0Ch], eax
0x14000b240  add     eax, ebx
0x14000b242  jnz     short loc_14000B253
0x14000b244  mov     rax, [rsi]
0x14000b247  mov     rcx, rsi
0x14000b24a  mov     rax, [rax+10h]
0x14000b24e  call    _guard_dispatch_icall
0x14000b253  mov     rsi, [rbp+var_18]
0x14000b257  test    rsi, rsi
0x14000b25a  jz      loc_14000B2F1
0x14000b260  mov     eax, ebx
0x14000b262  lock xadd [rsi+8], eax
0x14000b267  add     eax, ebx
0x14000b269  jnz     loc_14000B2F1
0x14000b26f  mov     rax, [rsi]
0x14000b272  mov     rcx, rsi
0x14000b275  mov     rax, [rax+8]
0x14000b279  call    _guard_dispatch_icall
0x14000b27e  mov     eax, ebx
0x14000b280  lock xadd [rsi+0Ch], eax
0x14000b285  add     eax, ebx
0x14000b287  jnz     short loc_14000B2F1
0x14000b289  mov     rax, [rsi]
0x14000b28c  mov     rcx, rsi
0x14000b28f  mov     rax, [rax+10h]
0x14000b293  call    _guard_dispatch_icall
0x14000b298  jmp     short loc_14000B2F1
0x14000b29a  movzx   edx, word ptr [rdi+4]; unsigned int
0x14000b29e  lea     rcx, [rdi+8]; void *
0x14000b2a2  mov     r8, r15
0x14000b2a5  call    ?CreateInstance@StreamingBitMap@Context@Streaming@@SAJPEAXKAEAV?$auto_ptr@VStreamingBitMap@Context@Streaming@@U?$AllocDelete@VStreamingBitMap@Context@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Context::StreamingBitMap::CreateInstance(void *,ulong,appv::shared::kernel::auto_ptr<Streaming::Context::StreamingBitMap,appv::shared::kernel::AllocDelete<Streaming::Context::StreamingBitMap>> &)
0x14000b2aa  mov     r14d, eax
0x14000b2ad  test    eax, eax
0x14000b2af  jns     short loc_14000B2DC
0x14000b2b1  lea     rcx, [rbp+var_10]
0x14000b2b5  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000b2ba  lea     r8, aStreamingbitma_1; "StreamingBitmapBuilder::ReadStreamingIn"...
0x14000b2c1  mov     ecx, 1
0x14000b2c6  mov     rdx, [rax]
0x14000b2c9  call    LogWrite
0x14000b2ce  mov     rsi, [rbp+var_8]
0x14000b2d2  test    rsi, rsi
0x14000b2d5  jz      short loc_14000B2F1
0x14000b2d7  or      ebx, 0FFFFFFFFh
0x14000b2da  jmp     short loc_14000B260
0x14000b2dc  mov     r8, [r15]; struct Streaming::Context::StreamingBitMap *
0x14000b2df  cmp     byte ptr [r8+38h], 0
0x14000b2e4  jz      short loc_14000B2F1
0x14000b2e6  mov     rdx, rbx; FileObject
0x14000b2e9  mov     rcx, r12; Instance
0x14000b2ec  call    ?UpdateStreamingInformation@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAVStreamingBitMap@23@@Z; Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(_FLT_INSTANCE *,_FILE_OBJECT &,Streaming::Context::StreamingBitMap &)
0x14000b2f1  test    rdi, rdi
0x14000b2f4  jz      short loc_14000B307
0x14000b2f6  xor     edx, edx; Tag
0x14000b2f8  mov     rcx, rdi; P
0x14000b2fb  call    cs:__imp_ExFreePoolWithTag
0x14000b302  nop     dword ptr [rax+rax+00h]
0x14000b307  mov     eax, r14d
0x14000b30a  lea     r11, [rsp+50h+var_s0]
0x14000b30f  mov     rbx, [r11+30h]
0x14000b313  mov     rsi, [r11+38h]
0x14000b317  mov     rsp, r11
0x14000b31a  pop     r15
0x14000b31c  pop     r14
0x14000b31e  pop     r12
0x14000b320  pop     rdi
0x14000b321  pop     rbp
0x14000b322  retn
```
