# CMsmqVssWriter::RestoreServiceQueues(wchar_t const *,int)

- ea: `0x180093a9c`
- end: `0x180093cd6`
- name: `?RestoreServiceQueues@CMsmqVssWriter@@AEAAJPEB_WH@Z`
- size: `570`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x18009331c`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x18008f714`
- `0x180092180`
- `0x180093a9c`
- `0x18009a590`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x180093b53`
- `msvcrt!free` at `0x180093b62`
- `msvcrt!free` at `0x180093ba6`
- `msvcrt!free` at `0x180093bb5`
- `msvcrt!free` at `0x180093c1f`
- `msvcrt!free` at `0x180093c29`
- `msvcrt!free` at `0x180093c38`
- `msvcrt!free` at `0x180093c7a`
- `msvcrt!free` at `0x180093c84`
- `msvcrt!free` at `0x180093c93`
- `msvcrt!free` at `0x180093c9f`
- `msvcrt!free` at `0x180093ca9`
- `msvcrt!free` at `0x180093cb8`
- `msvcrt!free` at `0x180093b53`
- `msvcrt!free` at `0x180093b62`
- `msvcrt!free` at `0x180093ba6`
- `msvcrt!free` at `0x180093bb5`
- `msvcrt!free` at `0x180093c1f`
- `msvcrt!free` at `0x180093c29`
- `msvcrt!free` at `0x180093c38`
- `msvcrt!free` at `0x180093c7a`
- `msvcrt!free` at `0x180093c84`
- `msvcrt!free` at `0x180093c93`
- `msvcrt!free` at `0x180093c9f`
- `msvcrt!free` at `0x180093ca9`
- `msvcrt!free` at `0x180093cb8`

## string_xrefs

- `0x180093ad0`: `StorePersistentPath`
- `0x180093b41`: `writer/mqwriter`
- `0x180093b94`: `writer/mqwriter`
- `0x180093c0d`: `writer/mqwriter`
- `0x180093c68`: `writer/mqwriter`
- `0x180093bd7`: `config`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::RestoreServiceQueues(CMsmqVssWriter *this, const wchar_t *a2, int a3)
{
  wchar_t *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  wchar_t *v11; // rdi
  const wchar_t *v12; // rax
  int v13; // eax
  CMsmqVssWriter *v14; // rcx
  unsigned int v15; // ebp
  const wchar_t *v16; // r8
  int v17; // eax
  int v18; // [rsp+38h] [rbp-50h] BYREF
  __int64 v19; // [rsp+40h] [rbp-48h]
  const wchar_t *v20; // [rsp+48h] [rbp-40h]
  int v21; // [rsp+50h] [rbp-38h]
  __int64 v22; // [rsp+58h] [rbp-30h]
  void *Block; // [rsp+90h] [rbp+8h] BYREF
  wchar_t *v24; // [rsp+A8h] [rbp+20h]

  Block = 0;
  v18 = 1;
  v19 = *((_QWORD *)this + 4);
  v20 = L"StorePersistentPath";
  v21 = 0;
  v22 = -2147483646;
  CmQueryValue((const struct RegEntry *)&v18, (wchar_t **)&Block);
  v6 = (wchar_t *)MmAllocate(0x20Au);
  v24 = v6;
  v7 = StringCchPrintfW(v6, 0x105u, L"%s\\%s", Block);
  v8 = v7;
  if ( v7 < 0 )
  {
    LogMsgHR(v7, (wchar_t *)L"writer/mqwriter", 0xB4u);
    free(v6);
    free(Block);
    return v8;
  }
  v10 = CMsmqVssWriter::PrepareDirectoryForBackupRestore(this, v6, L"*", 0, (void *)L"LQS");
  v8 = v10;
  if ( v10 < 0 )
  {
    LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", 0xC8u);
    free(v6);
    free(Block);
    return v8;
  }
  v11 = (wchar_t *)MmAllocate(0x20Au);
  v12 = L"config";
  if ( !a3 )
    v12 = L"queue";
  v13 = StringCchPrintfW(v11, 0x105u, L"%s\\%s", a2, v12);
  v15 = v13;
  if ( v13 < 0 )
  {
    LogMsgHR(v13, (wchar_t *)L"writer/mqwriter", 0xDCu);
    free(v11);
    free(v6);
    free(Block);
    return v15;
  }
  v16 = L"0*.*";
  if ( !a3 )
    v16 = L"*";
  v17 = CMsmqVssWriter::CopyFiles(v14, v11, v16, v6);
  v15 = v17;
  if ( v17 < 0 )
  {
    LogMsgHR(v17, (wchar_t *)L"writer/mqwriter", 0xF0u);
    free(v11);
    free(v6);
    free(Block);
    return v15;
  }
  free(v11);
  free(v6);
  free(Block);
  return 0;
}

```

## disassembly

```asm
0x180093a9c  mov     r11, rsp
0x180093a9f  mov     [r11+10h], rbx
0x180093aa3  push    rbp
0x180093aa4  push    rdi
0x180093aa5  push    r12
0x180093aa7  push    r14
0x180093aa9  push    r15
0x180093aab  sub     rsp, 60h
0x180093aaf  mov     r14d, r8d
0x180093ab2  mov     r15, rdx
0x180093ab5  mov     rbp, rcx
0x180093ab8  mov     qword ptr [r11+8], 0
0x180093ac0  mov     [rsp+88h+var_50], 1
0x180093ac8  mov     rax, [rcx+20h]
0x180093acc  mov     [r11-48h], rax
0x180093ad0  lea     rax, aStorepersisten; "StorePersistentPath"
0x180093ad7  mov     [r11-40h], rax
0x180093adb  mov     [rsp+88h+var_38], 0
0x180093ae3  mov     qword ptr [r11-30h], 0FFFFFFFF80000002h
0x180093aeb  lea     rdx, [r11+8]; wchar_t **
0x180093aef  lea     rcx, [r11-50h]; struct RegEntry *
0x180093af3  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x180093af8  mov     ecx, 20Ah; unsigned __int64
0x180093afd  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180093b02  mov     rbx, rax
0x180093b05  mov     [rsp+88h+arg_18], rax
0x180093b0d  lea     rax, aLqs_1; "LQS"
0x180093b14  mov     [rsp+88h+var_68], rax; void *
0x180093b19  mov     r9, [rsp+88h+Block]
0x180093b21  lea     r8, aSS_3; "%s\\%s"
0x180093b28  mov     edx, 105h; unsigned __int64
0x180093b2d  mov     rcx, rbx; wchar_t *
0x180093b30  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180093b35  mov     edi, eax
0x180093b37  test    eax, eax
0x180093b39  jns     short loc_180093B70
0x180093b3b  mov     r8d, 0B4h; unsigned __int16
0x180093b41  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093b48  mov     ecx, eax; int
0x180093b4a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093b4f  nop
0x180093b50  mov     rcx, rbx; Block
0x180093b53  call    cs:__imp_free
0x180093b59  nop
0x180093b5a  mov     rcx, [rsp+88h+Block]; Block
0x180093b62  call    cs:__imp_free
0x180093b68  nop
0x180093b69  mov     eax, edi
0x180093b6b  jmp     loc_180093CC1
0x180093b70  xor     r9d, r9d; int
0x180093b73  lea     r12, asc_180104F98; "*"
0x180093b7a  mov     r8, r12; wchar_t *
0x180093b7d  mov     rdx, rbx; wchar_t *
0x180093b80  mov     rcx, rbp; this
0x180093b83  call    ?PrepareDirectoryForBackupRestore@CMsmqVssWriter@@AEAAJPEB_W0HPEAX@Z; CMsmqVssWriter::PrepareDirectoryForBackupRestore(wchar_t const *,wchar_t const *,int,void *)
0x180093b88  mov     edi, eax
0x180093b8a  test    eax, eax
0x180093b8c  jns     short loc_180093BBE
0x180093b8e  mov     r8d, 0C8h; unsigned __int16
0x180093b94  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093b9b  mov     ecx, eax; int
0x180093b9d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093ba2  nop
0x180093ba3  mov     rcx, rbx; Block
0x180093ba6  call    cs:__imp_free
0x180093bac  nop
0x180093bad  mov     rcx, [rsp+88h+Block]; Block
0x180093bb5  call    cs:__imp_free
0x180093bbb  nop
0x180093bbc  jmp     short loc_180093B69
0x180093bbe  mov     ecx, 20Ah; unsigned __int64
0x180093bc3  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180093bc8  mov     rdi, rax
0x180093bcb  mov     [rsp+88h+var_58], rax
0x180093bd0  lea     rcx, aQueue; "queue"
0x180093bd7  lea     rax, aConfig; "config"
0x180093bde  test    r14d, r14d
0x180093be1  cmovz   rax, rcx
0x180093be5  mov     [rsp+88h+var_68], rax; int
0x180093bea  mov     r9, r15
0x180093bed  lea     r8, aSS_3; "%s\\%s"
0x180093bf4  mov     edx, 105h; unsigned __int64
0x180093bf9  mov     rcx, rdi; wchar_t *
0x180093bfc  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180093c01  mov     ebp, eax
0x180093c03  test    eax, eax
0x180093c05  jns     short loc_180093C43
0x180093c07  mov     r8d, 0DCh; unsigned __int16
0x180093c0d  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093c14  mov     ecx, eax; int
0x180093c16  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093c1b  nop
0x180093c1c  mov     rcx, rdi; Block
0x180093c1f  call    cs:__imp_free
0x180093c25  nop
0x180093c26  mov     rcx, rbx; Block
0x180093c29  call    cs:__imp_free
0x180093c2f  nop
0x180093c30  mov     rcx, [rsp+88h+Block]; Block
0x180093c38  call    cs:__imp_free
0x180093c3e  nop
0x180093c3f  mov     eax, ebp
0x180093c41  jmp     short loc_180093CC1
0x180093c43  lea     r8, a0; "0*.*"
0x180093c4a  test    r14d, r14d
0x180093c4d  cmovz   r8, r12; wchar_t *
0x180093c51  mov     r9, rbx; wchar_t *
0x180093c54  mov     rdx, rdi; wchar_t *
0x180093c57  call    ?CopyFiles@CMsmqVssWriter@@AEAAJPEB_W00HPEAX@Z; CMsmqVssWriter::CopyFiles(wchar_t const *,wchar_t const *,wchar_t const *,int,void *)
0x180093c5c  mov     ebp, eax
0x180093c5e  test    eax, eax
0x180093c60  jns     short loc_180093C9C
0x180093c62  mov     r8d, 0F0h; unsigned __int16
0x180093c68  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093c6f  mov     ecx, eax; int
0x180093c71  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093c76  nop
0x180093c77  mov     rcx, rdi; Block
0x180093c7a  call    cs:__imp_free
0x180093c80  nop
0x180093c81  mov     rcx, rbx; Block
0x180093c84  call    cs:__imp_free
0x180093c8a  nop
0x180093c8b  mov     rcx, [rsp+88h+Block]; Block
0x180093c93  call    cs:__imp_free
0x180093c99  nop
0x180093c9a  jmp     short loc_180093C3F
0x180093c9c  mov     rcx, rdi; Block
0x180093c9f  call    cs:__imp_free
0x180093ca5  nop
0x180093ca6  mov     rcx, rbx; Block
0x180093ca9  call    cs:__imp_free
0x180093caf  nop
0x180093cb0  mov     rcx, [rsp+88h+Block]; Block
0x180093cb8  call    cs:__imp_free
0x180093cbe  nop
0x180093cbf  xor     eax, eax
0x180093cc1  mov     rbx, [rsp+88h+arg_8]
0x180093cc9  add     rsp, 60h
0x180093ccd  pop     r15
0x180093ccf  pop     r14
0x180093cd1  pop     r12
0x180093cd3  pop     rdi
0x180093cd4  pop     rbp
0x180093cd5  retn
```
