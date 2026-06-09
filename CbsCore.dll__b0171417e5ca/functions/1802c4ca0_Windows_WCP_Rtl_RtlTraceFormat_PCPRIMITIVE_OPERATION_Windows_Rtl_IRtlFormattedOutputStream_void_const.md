# Windows::WCP::Rtl::RtlTraceFormat_PCPRIMITIVE_OPERATION(Windows::Rtl::IRtlFormattedOutputStream *,void const *)

- ea: `0x1802c4ca0`
- end: `0x1802c5566`
- name: `?RtlTraceFormat_PCPRIMITIVE_OPERATION@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z`
- size: `2246`
- prototype: `void __fastcall(Windows::WCP::Rtl *__hidden this, struct Windows::Rtl::IRtlFormattedOutputStream *, const void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18011b460`
- `0x18011b580`
- `0x18011ca98`
- `0x1802c4ca0`
- `0x1802d5010`

## string_xrefs

- `0x1802c4d11`: `Create Key: Key = `
- `0x1802c4e74`: `, LastAccessTime = `
- `0x1802c4ea6`: `, LastWriteTime = `
- `0x1802c4fa8`: `Create File: File = `
- `0x1802c4f06`: `Create Directory: Directory = `
- `0x1802c544e`: `Delete Key Value: Key = `
- `0x1802c5412`: `Set Key Security: Key = `
- `0x1802c5181`: `Delete Key: Key = `
- `0x1802c500a`: `Delete File: File = `
- `0x1802c4fb7`: `Hard Link File: Source = `
- `0x1802c5030`: `Move File: Source = `
- `0x1802c50a0`: `, IsDirectory`
- `0x1802c4d4d`: `, SecurityDescriptor = `
- `0x1802c4e20`: `, SecurityDescriptor = `
- `0x1802c4f7b`: `, SecurityDescriptor = `
- `0x1802c515e`: `, SecurityDescriptor = `
- `0x1802c5304`: `, SecurityDescriptor = `
- `0x1802c543f`: `, SecurityDescriptor = `
- `0x1802c50b9`: `Copy File: Source = `
- `0x1802c5254`: `WofDecompress File: File = `
- `0x1802c5263`: `Decompress File: Source = `

## pseudocode

```c
void __fastcall Windows::WCP::Rtl::RtlTraceFormat_PCPRIMITIVE_OPERATION(
        Windows::WCP::Rtl *this,
        struct Windows::Rtl::IRtlFormattedOutputStream *a2,
        const void *a3)
{
  int v3; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  const void *v14; // r8
  const void *v15; // r8
  const void *v16; // r8
  const char *v17; // rdx
  __int64 v18; // rdx
  const char *v19; // rdx
  const char *v20; // rdx
  const char *v21; // rdx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  const void *v29; // r8
  const void *v30; // r8
  struct Windows::Rtl::IRtlFormattedOutputStream *v31; // rdx
  const void *v32; // r8
  const void *v33; // r8

  v3 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 > 0xAu )
  {
    v22 = v3 - 11;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 )
      {
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
          this,
          "Delete Key Value: Key = ",
          a3);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(
          this,
          *((_QWORD *)a2 + 1) + 8LL);
        v19 = ", Value = ";
        goto LABEL_35;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
          this,
          "Set Key Security: Key = ",
          a3);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(
          this,
          *((_QWORD *)a2 + 1) + 8LL);
        v21 = ", SecurityDescriptor = ";
        goto LABEL_40;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v20 = "Begin Transaction: Transaction = ";
        goto LABEL_37;
      }
      v26 = v25 - 1;
      if ( !v26 )
      {
        v20 = "Flush File Buffers: File = ";
        goto LABEL_37;
      }
      v27 = v26 - 2;
      if ( !v27 )
      {
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
          this,
          "Decompress File: Source = ",
          a3);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(
          this,
          *((_QWORD *)a2 + 1) + 8LL);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Destination = ");
        (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(
          this,
          *((_QWORD *)a2 + 1) + 24LL);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Attributes = ");
        (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 400LL))(
          this,
          *(unsigned int *)(*((_QWORD *)a2 + 1) + 4LL));
        if ( *(_QWORD *)(*((_QWORD *)a2 + 1) + 40LL) )
        {
          (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
            this,
            ", SecurityDescriptor = ");
          (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 464LL))(
            this,
            *(_QWORD *)(*((_QWORD *)a2 + 1) + 40LL));
        }
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Flags = ");
        (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 400LL))(
          this,
          **((unsigned int **)a2 + 1));
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", FileHash = ");
        Windows::WCP::Rtl::RtlTraceFormat_PCLBLOB_LimitLength(
          this,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)(*((_QWORD *)a2 + 1) + 48LL),
          v32);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
          this,
          ", HashAlgorithm = ");
        (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 400LL))(
          this,
          *(unsigned int *)(*((_QWORD *)a2 + 1) + 72LL));
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
          this,
          ", HashTransform = ");
        (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 400LL))(
          this,
          *(unsigned int *)(*((_QWORD *)a2 + 1) + 76LL));
        goto LABEL_63;
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        v20 = "WofDecompress File: File = ";
        goto LABEL_37;
      }
      if ( v28 != 1 )
        return;
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
        this,
        "Set Key Info: Key = ",
        a3);
      (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 8LL);
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Class = ");
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegValueType(
        this,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)(*((_QWORD *)a2 + 1) + 24LL),
        v29);
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Data = ");
      v31 = (struct Windows::Rtl::IRtlFormattedOutputStream *)(*((_QWORD *)a2 + 1) + 32LL);
    }
    else
    {
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
        this,
        "Set Key Value: Key = ",
        a3);
      (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 8LL);
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Value = ");
      (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 24LL);
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Type = ");
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegValueType(
        this,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)(*((_QWORD *)a2 + 1) + 40LL),
        v33);
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Data = ");
      v31 = (struct Windows::Rtl::IRtlFormattedOutputStream *)(*((_QWORD *)a2 + 1) + 48LL);
    }
    Windows::WCP::Rtl::RtlTraceFormat_PCLBLOB_LimitLength(this, v31, v30);
    goto LABEL_63;
  }
  if ( v3 == 10 )
  {
    v20 = "Delete Key: Key = ";
    goto LABEL_37;
  }
  v6 = v3 - 1;
  if ( !v6 )
  {
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
      this,
      "Copy File: Source = ",
      a3);
    (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 8LL);
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Destination = ");
    (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 24LL);
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Attributes = ");
    (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 400LL))(
      this,
      *(unsigned int *)(*((_QWORD *)a2 + 1) + 4LL));
    if ( !*(_QWORD *)(*((_QWORD *)a2 + 1) + 40LL) )
      goto LABEL_63;
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
      this,
      ", SecurityDescriptor = ");
    v18 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 40LL);
    goto LABEL_32;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
      this,
      "Move File: Source = ",
      a3);
    (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 8LL);
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Destination = ");
    (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 24LL);
    if ( (**((_DWORD **)a2 + 1) & 0x100) == 0 )
      goto LABEL_63;
    v21 = ", IsDirectory";
LABEL_40:
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, v21);
    goto LABEL_63;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v20 = "Delete File: File = ";
LABEL_37:
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(this, v20, a3);
    v13 = *((_QWORD *)a2 + 1) + 8LL;
    goto LABEL_15;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
      this,
      "Hard Link File: Source = ",
      a3);
    (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 8LL);
    v19 = ", Destination = ";
LABEL_35:
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, v19);
    v13 = *((_QWORD *)a2 + 1) + 24LL;
LABEL_15:
    (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, v13);
    goto LABEL_63;
  }
  v10 = v9 - 2;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( !v12 )
      {
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
          this,
          "Set File Information: File = ",
          a3);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(
          this,
          *((_QWORD *)a2 + 1) + 16LL);
        if ( (**((_BYTE **)a2 + 1) & 1) != 0 )
        {
          (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Attributes = ");
          (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 400LL))(
            this,
            *(unsigned int *)(*((_QWORD *)a2 + 1) + 4LL));
        }
        if ( (**((_BYTE **)a2 + 1) & 2) != 0 )
          (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
            this,
            ", SecurityDescriptor = ");
        if ( (**((_BYTE **)a2 + 1) & 4) != 0 )
        {
          (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
            this,
            ", CreationTime = ");
          Windows::WCP::Rtl::RtlTraceFormat_PCLONGLONG(
            this,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)(*((_QWORD *)a2 + 1) + 32LL),
            v14);
        }
        if ( (**((_BYTE **)a2 + 1) & 8) != 0 )
        {
          (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
            this,
            ", LastAccessTime = ");
          Windows::WCP::Rtl::RtlTraceFormat_PCLONGLONG(
            this,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)(*((_QWORD *)a2 + 1) + 40LL),
            v15);
        }
        if ( (**((_BYTE **)a2 + 1) & 0x10) != 0 )
        {
          (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
            this,
            ", LastWriteTime = ");
          Windows::WCP::Rtl::RtlTraceFormat_PCLONGLONG(
            this,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)(*((_QWORD *)a2 + 1) + 48LL),
            v16);
        }
        if ( (**((_BYTE **)a2 + 1) & 0x20) != 0 )
        {
          (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", EndOfFile = ");
          (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 72LL))(
            this,
            *(_QWORD *)(*((_QWORD *)a2 + 1) + 56LL));
        }
        goto LABEL_63;
      }
      if ( v12 != 1 )
        return;
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(
        this,
        "Create Key: Key = ",
        a3);
      (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 8LL);
      if ( *(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL) )
        (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
          this,
          ", SecurityDescriptor = ");
      if ( !*(_WORD *)(*((_QWORD *)a2 + 1) + 32LL) )
        goto LABEL_63;
      (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Class = ");
      v13 = *((_QWORD *)a2 + 1) + 32LL;
      goto LABEL_15;
    }
    v17 = "Create Directory: Directory = ";
  }
  else
  {
    v17 = "Create File: File = ";
  }
  (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *, const void *))(*(_QWORD *)this + 224LL))(this, v17, a3);
  (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 152LL))(this, *((_QWORD *)a2 + 1) + 8LL);
  (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(this, ", Attributes = ");
  (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(*(_QWORD *)this + 400LL))(
    this,
    *(unsigned int *)(*((_QWORD *)a2 + 1) + 4LL));
  if ( *(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL) )
  {
    (*(void (__fastcall **)(Windows::WCP::Rtl *, const char *))(*(_QWORD *)this + 224LL))(
      this,
      ", SecurityDescriptor = ");
    v18 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL);
LABEL_32:
    (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64))(*(_QWORD *)this + 464LL))(this, v18);
  }
LABEL_63:
  (*(void (__fastcall **)(Windows::WCP::Rtl *, const CHAR *))(*(_QWORD *)this + 224LL))(this, "\n");
}

```

## disassembly

```asm
0x1802c4ca0  mov     [rsp+arg_0], rbx
0x1802c4ca5  mov     [rsp+arg_8], rsi
0x1802c4caa  push    rdi
0x1802c4cab  sub     rsp, 20h
0x1802c4caf  mov     eax, [rdx]
0x1802c4cb1  mov     rdi, rdx
0x1802c4cb4  mov     rbx, rcx
0x1802c4cb7  cmp     eax, 0Ah
0x1802c4cba  ja      loc_1802C518D
0x1802c4cc0  jz      loc_1802C5181
0x1802c4cc6  sub     eax, 1
0x1802c4cc9  jz      loc_1802C50B6
0x1802c4ccf  sub     eax, 1
0x1802c4cd2  jz      loc_1802C502D
0x1802c4cd8  sub     eax, 1
0x1802c4cdb  jz      loc_1802C500A
0x1802c4ce1  sub     eax, 1
0x1802c4ce4  jz      loc_1802C4FB4
0x1802c4cea  sub     eax, 2
0x1802c4ced  jz      loc_1802C4FA8
0x1802c4cf3  sub     eax, 1
0x1802c4cf6  jz      loc_1802C4F06
0x1802c4cfc  sub     eax, 1
0x1802c4cff  jz      loc_1802C4DA9
0x1802c4d05  cmp     eax, 1
0x1802c4d08  jnz     loc_1802C5555
0x1802c4d0e  mov     rax, [rcx]
0x1802c4d11  lea     rdx, aCreateKeyKey; "Create Key: Key = "
0x1802c4d18  mov     rax, [rax+0E0h]
0x1802c4d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4d24  mov     rax, [rbx]
0x1802c4d27  mov     rcx, rbx
0x1802c4d2a  mov     rdx, [rdi+8]
0x1802c4d2e  add     rdx, 8
0x1802c4d32  mov     rax, [rax+98h]
0x1802c4d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4d3e  mov     rax, [rdi+8]
0x1802c4d42  xor     esi, esi
0x1802c4d44  cmp     [rax+18h], rsi
0x1802c4d48  jz      short loc_1802C4D63
0x1802c4d4a  mov     rax, [rbx]
0x1802c4d4d  lea     rdx, aSecuritydescri; ", SecurityDescriptor = "
0x1802c4d54  mov     rcx, rbx
0x1802c4d57  mov     rax, [rax+0E0h]
0x1802c4d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4d63  mov     rax, [rdi+8]
0x1802c4d67  cmp     [rax+20h], si
0x1802c4d6b  jz      loc_1802C553C
0x1802c4d71  mov     rax, [rbx]
0x1802c4d74  lea     rdx, aClass_0; ", Class = "
0x1802c4d7b  mov     rcx, rbx
0x1802c4d7e  mov     rax, [rax+0E0h]
0x1802c4d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4d8a  mov     rdx, [rdi+8]
0x1802c4d8e  add     rdx, 20h ; ' '
0x1802c4d92  mov     rax, [rbx]
0x1802c4d95  mov     rax, [rax+98h]
0x1802c4d9c  mov     rcx, rbx
0x1802c4d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4da4  jmp     loc_1802C553C
0x1802c4da9  mov     rax, [rcx]
0x1802c4dac  lea     rdx, aSetFileInforma; "Set File Information: File = "
0x1802c4db3  mov     rax, [rax+0E0h]
0x1802c4dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4dbf  mov     rax, [rbx]
0x1802c4dc2  mov     rcx, rbx
0x1802c4dc5  mov     rdx, [rdi+8]
0x1802c4dc9  add     rdx, 10h
0x1802c4dcd  mov     rax, [rax+98h]
0x1802c4dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4dd9  mov     rax, [rdi+8]
0x1802c4ddd  test    byte ptr [rax], 1
0x1802c4de0  jz      short loc_1802C4E14
0x1802c4de2  mov     rax, [rbx]
0x1802c4de5  lea     rdx, aAttributes; ", Attributes = "
0x1802c4dec  mov     rcx, rbx
0x1802c4def  mov     rax, [rax+0E0h]
0x1802c4df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4dfb  mov     rax, [rbx]
0x1802c4dfe  mov     rcx, rbx
0x1802c4e01  mov     rdx, [rdi+8]
0x1802c4e05  mov     rax, [rax+190h]
0x1802c4e0c  mov     edx, [rdx+4]
0x1802c4e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4e14  mov     rax, [rdi+8]
0x1802c4e18  test    byte ptr [rax], 2
0x1802c4e1b  jz      short loc_1802C4E36
0x1802c4e1d  mov     rax, [rbx]
0x1802c4e20  lea     rdx, aSecuritydescri; ", SecurityDescriptor = "
0x1802c4e27  mov     rcx, rbx
0x1802c4e2a  mov     rax, [rax+0E0h]
0x1802c4e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4e36  mov     rax, [rdi+8]
0x1802c4e3a  test    byte ptr [rax], 4
0x1802c4e3d  jz      short loc_1802C4E68
0x1802c4e3f  mov     rax, [rbx]
0x1802c4e42  lea     rdx, aCreationtime_1; ", CreationTime = "
0x1802c4e49  mov     rcx, rbx
0x1802c4e4c  mov     rax, [rax+0E0h]
0x1802c4e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4e58  mov     rdx, [rdi+8]
0x1802c4e5c  mov     rcx, rbx; this
0x1802c4e5f  add     rdx, 20h ; ' '; struct Windows::Rtl::IRtlFormattedOutputStream *
0x1802c4e63  call    ?RtlTraceFormat_PCLONGLONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCLONGLONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1802c4e68  mov     rax, [rdi+8]
0x1802c4e6c  test    byte ptr [rax], 8
0x1802c4e6f  jz      short loc_1802C4E9A
0x1802c4e71  mov     rax, [rbx]
0x1802c4e74  lea     rdx, aLastaccesstime_1; ", LastAccessTime = "
0x1802c4e7b  mov     rcx, rbx
0x1802c4e7e  mov     rax, [rax+0E0h]
0x1802c4e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4e8a  mov     rdx, [rdi+8]
0x1802c4e8e  mov     rcx, rbx; this
0x1802c4e91  add     rdx, 28h ; '('; struct Windows::Rtl::IRtlFormattedOutputStream *
0x1802c4e95  call    ?RtlTraceFormat_PCLONGLONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCLONGLONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1802c4e9a  mov     rax, [rdi+8]
0x1802c4e9e  test    byte ptr [rax], 10h
0x1802c4ea1  jz      short loc_1802C4ECC
0x1802c4ea3  mov     rax, [rbx]
0x1802c4ea6  lea     rdx, aLastwritetime_0; ", LastWriteTime = "
0x1802c4ead  mov     rcx, rbx
0x1802c4eb0  mov     rax, [rax+0E0h]
0x1802c4eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4ebc  mov     rdx, [rdi+8]
0x1802c4ec0  mov     rcx, rbx; this
0x1802c4ec3  add     rdx, 30h ; '0'; struct Windows::Rtl::IRtlFormattedOutputStream *
0x1802c4ec7  call    ?RtlTraceFormat_PCLONGLONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCLONGLONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1802c4ecc  mov     rax, [rdi+8]
0x1802c4ed0  test    byte ptr [rax], 20h
0x1802c4ed3  jz      loc_1802C553C
0x1802c4ed9  mov     rax, [rbx]
0x1802c4edc  lea     rdx, aEndoffile; ", EndOfFile = "
0x1802c4ee3  mov     rcx, rbx
0x1802c4ee6  mov     rax, [rax+0E0h]
0x1802c4eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4ef2  mov     rax, [rbx]
0x1802c4ef5  mov     rdx, [rdi+8]
0x1802c4ef9  mov     rax, [rax+48h]
0x1802c4efd  mov     rdx, [rdx+38h]
0x1802c4f01  jmp     loc_1802C4D9C
0x1802c4f06  lea     rdx, aCreateDirector; "Create Directory: Directory = "
0x1802c4f0d  mov     rax, [rcx]
0x1802c4f10  mov     rax, [rax+0E0h]
0x1802c4f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4f1c  mov     rax, [rbx]
0x1802c4f1f  mov     rcx, rbx
0x1802c4f22  mov     rdx, [rdi+8]
0x1802c4f26  add     rdx, 8
0x1802c4f2a  mov     rax, [rax+98h]
0x1802c4f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4f36  mov     rax, [rbx]
0x1802c4f39  lea     rdx, aAttributes; ", Attributes = "
0x1802c4f40  mov     rcx, rbx
0x1802c4f43  mov     rax, [rax+0E0h]
0x1802c4f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4f4f  mov     rax, [rbx]
0x1802c4f52  mov     rcx, rbx
0x1802c4f55  mov     rdx, [rdi+8]
0x1802c4f59  mov     rax, [rax+190h]
0x1802c4f60  mov     edx, [rdx+4]
0x1802c4f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4f68  mov     rax, [rdi+8]
0x1802c4f6c  xor     esi, esi
0x1802c4f6e  cmp     [rax+18h], rsi
0x1802c4f72  jz      loc_1802C553C
0x1802c4f78  mov     rax, [rbx]
0x1802c4f7b  lea     rdx, aSecuritydescri; ", SecurityDescriptor = "
0x1802c4f82  mov     rcx, rbx
0x1802c4f85  mov     rax, [rax+0E0h]
0x1802c4f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4f91  mov     rdx, [rdi+8]
0x1802c4f95  mov     rdx, [rdx+18h]
0x1802c4f99  mov     rax, [rbx]
0x1802c4f9c  mov     rax, [rax+1D0h]
0x1802c4fa3  jmp     loc_1802C4D9C
0x1802c4fa8  lea     rdx, aCreateFileFile; "Create File: File = "
0x1802c4faf  jmp     loc_1802C4F0D
0x1802c4fb4  mov     rax, [rcx]
0x1802c4fb7  lea     rdx, aHardLinkFileSo; "Hard Link File: Source = "
0x1802c4fbe  mov     rax, [rax+0E0h]
0x1802c4fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4fca  mov     rax, [rbx]
0x1802c4fcd  mov     rcx, rbx
0x1802c4fd0  mov     rdx, [rdi+8]
0x1802c4fd4  add     rdx, 8
0x1802c4fd8  mov     rax, [rax+98h]
0x1802c4fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4fe4  lea     rdx, aDestination_0; ", Destination = "
0x1802c4feb  mov     rax, [rbx]
0x1802c4fee  mov     rcx, rbx
0x1802c4ff1  mov     rax, [rax+0E0h]
0x1802c4ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4ffd  mov     rdx, [rdi+8]
0x1802c5001  add     rdx, 18h
0x1802c5005  jmp     loc_1802C4D92
0x1802c500a  lea     rdx, aDeleteFileFile; "Delete File: File = "
0x1802c5011  mov     rax, [rcx]
0x1802c5014  mov     rax, [rax+0E0h]
0x1802c501b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c5020  mov     rdx, [rdi+8]
0x1802c5024  add     rdx, 8
0x1802c5028  jmp     loc_1802C4D92
0x1802c502d  mov     rax, [rcx]
0x1802c5030  lea     rdx, aMoveFileSource; "Move File: Source = "
0x1802c5037  mov     rax, [rax+0E0h]
0x1802c503e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c5043  mov     rax, [rbx]
0x1802c5046  mov     rcx, rbx
0x1802c5049  mov     rdx, [rdi+8]
0x1802c504d  add     rdx, 8
0x1802c5051  mov     rax, [rax+98h]
0x1802c5058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c505d  mov     rax, [rbx]
0x1802c5060  lea     rdx, aDestination_0; ", Destination = "
0x1802c5067  mov     rcx, rbx
0x1802c506a  mov     rax, [rax+0E0h]
0x1802c5071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c5076  mov     rax, [rbx]
0x1802c5079  mov     rcx, rbx
0x1802c507c  mov     rdx, [rdi+8]
0x1802c5080  add     rdx, 18h
0x1802c5084  mov     rax, [rax+98h]
0x1802c508b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c5090  mov     rax, [rdi+8]
0x1802c5094  test    dword ptr [rax], 100h
0x1802c509a  jz      loc_1802C553C
0x1802c50a0  lea     rdx, aIsdirectory; ", IsDirectory"
0x1802c50a7  mov     rax, [rbx]
0x1802c50aa  mov     rax, [rax+0E0h]
0x1802c50b1  jmp     loc_1802C4D9C
0x1802c50b6  mov     rax, [rcx]
0x1802c50b9  lea     rdx, aCopyFileSource; "Copy File: Source = "
0x1802c50c0  mov     rax, [rax+0E0h]
0x1802c50c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c50cc  mov     rax, [rbx]
0x1802c50cf  mov     rcx, rbx
0x1802c50d2  mov     rdx, [rdi+8]
0x1802c50d6  add     rdx, 8
0x1802c50da  mov     rax, [rax+98h]
0x1802c50e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c50e6  mov     rax, [rbx]
0x1802c50e9  lea     rdx, aDestination_0; ", Destination = "
0x1802c50f0  mov     rcx, rbx
0x1802c50f3  mov     rax, [rax+0E0h]
0x1802c50fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c50ff  mov     rax, [rbx]
0x1802c5102  mov     rcx, rbx
0x1802c5105  mov     rdx, [rdi+8]
0x1802c5109  add     rdx, 18h
0x1802c510d  mov     rax, [rax+98h]
0x1802c5114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c5119  mov     rax, [rbx]
0x1802c511c  lea     rdx, aAttributes; ", Attributes = "
0x1802c5123  mov     rcx, rbx
0x1802c5126  mov     rax, [rax+0E0h]
0x1802c512d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c5132  mov     rax, [rbx]
0x1802c5135  mov     rcx, rbx
0x1802c5138  mov     rdx, [rdi+8]
0x1802c513c  mov     rax, [rax+190h]
0x1802c5143  mov     edx, [rdx+4]
0x1802c5146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c514b  mov     rax, [rdi+8]
0x1802c514f  xor     esi, esi
0x1802c5151  cmp     [rax+28h], rsi
0x1802c5155  jz      loc_1802C553C
0x1802c515b  mov     rax, [rbx]
0x1802c515e  lea     rdx, aSecuritydescri; ", SecurityDescriptor = "
0x1802c5165  mov     rcx, rbx
0x1802c5168  mov     rax, [rax+0E0h]
0x1802c516f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c5174  mov     rdx, [rdi+8]
0x1802c5178  mov     rdx, [rdx+28h]
0x1802c517c  jmp     loc_1802C4F99
0x1802c5181  lea     rdx, aDeleteKeyKey; "Delete Key: Key = "
0x1802c5188  jmp     loc_1802C5011
0x1802c518d  sub     eax, 0Bh
0x1802c5190  jz      loc_1802C5487
0x1802c5196  sub     eax, 1
0x1802c5199  jz      loc_1802C544B
0x1802c519f  sub     eax, 1
0x1802c51a2  jz      loc_1802C540F
0x1802c51a8  sub     eax, 1
0x1802c51ab  jz      loc_1802C5403
0x1802c51b1  sub     eax, 1
0x1802c51b4  jz      loc_1802C53F7
0x1802c51ba  sub     eax, 2
0x1802c51bd  jz      loc_1802C5260
0x1802c51c3  sub     eax, 1
0x1802c51c6  jz      loc_1802C5254
0x1802c51cc  cmp     eax, 1
0x1802c51cf  jnz     loc_1802C5555
0x1802c51d5  mov     rax, [rcx]
0x1802c51d8  lea     rdx, aSetKeyInfoKey; "Set Key Info: Key = "
0x1802c51df  mov     rax, [rax+0E0h]
0x1802c51e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c51eb  mov     rax, [rbx]
0x1802c51ee  mov     rcx, rbx
0x1802c51f1  mov     rdx, [rdi+8]
  ... truncated ...
```
