# CMsmqVssWriter::RestoreServiceMapping(wchar_t const *)

- ea: `0x180093860`
- end: `0x180093a94`
- name: `?RestoreServiceMapping@CMsmqVssWriter@@AEAAJPEB_W@Z`
- size: `564`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18009331c`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x18008f714`
- `0x180092180`
- `0x180093860`
- `0x18009a590`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800938cf`
- `msvcrt!free` at `0x1800939b2`
- `msvcrt!free` at `0x1800939bc`
- `msvcrt!free` at `0x1800939c6`
- `msvcrt!free` at `0x1800939d8`
- `msvcrt!free` at `0x180093a12`
- `msvcrt!free` at `0x180093a1c`
- `msvcrt!free` at `0x180093a57`
- `msvcrt!free` at `0x180093a61`
- `msvcrt!free` at `0x180093a6d`
- `msvcrt!free` at `0x180093a77`
- `msvcrt!free` at `0x1800938cf`
- `msvcrt!free` at `0x1800939b2`
- `msvcrt!free` at `0x1800939bc`
- `msvcrt!free` at `0x1800939c6`
- `msvcrt!free` at `0x1800939d8`
- `msvcrt!free` at `0x180093a12`
- `msvcrt!free` at `0x180093a1c`
- `msvcrt!free` at `0x180093a57`
- `msvcrt!free` at `0x180093a61`
- `msvcrt!free` at `0x180093a6d`
- `msvcrt!free` at `0x180093a77`

## string_xrefs

- `0x1800938f4`: `QueuesAliasPath`
- `0x18009393e`: `MsmqRootPath`
- `0x1800938bd`: `writer/mqwriter`
- `0x1800939a0`: `writer/mqwriter`
- `0x180093a00`: `writer/mqwriter`
- `0x180093a45`: `writer/mqwriter`
- `0x1800939e2`: `*.xml`
- `0x180093a2a`: `*.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::RestoreServiceMapping(CMsmqVssWriter *this, const wchar_t *a2)
{
  wchar_t *v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  wchar_t *v8; // rdi
  void *v9; // rsi
  int v10; // eax
  unsigned int v11; // r15d
  int v12; // eax
  CMsmqVssWriter *v13; // rcx
  unsigned int v14; // esi
  int v15; // eax
  int v16; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h]
  const wchar_t *v18; // [rsp+48h] [rbp-18h]
  int v19; // [rsp+50h] [rbp-10h]
  __int64 v20; // [rsp+58h] [rbp-8h]
  wchar_t *v21; // [rsp+A0h] [rbp+40h] BYREF
  void *Block; // [rsp+A8h] [rbp+48h] BYREF

  v4 = (wchar_t *)MmAllocate(0x20Au);
  v5 = StringCchPrintfW(v4, 0x105u, L"%s\\%s", a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    LogMsgHR(v5, (wchar_t *)L"writer/mqwriter", 0x168u);
    free(v4);
    return v6;
  }
  v21 = 0;
  v16 = 0;
  v17 = *((_QWORD *)this + 4);
  v18 = L"QueuesAliasPath";
  v19 = 0;
  v20 = -2147483646;
  CmQueryValue((const struct RegEntry *)&v16, &v21);
  v8 = v21;
  if ( !v21 )
  {
    Block = 0;
    v16 = 1;
    v17 = *((_QWORD *)this + 4);
    v18 = L"MsmqRootPath";
    v19 = 0;
    v20 = -2147483646;
    CmQueryValue((const struct RegEntry *)&v16, (wchar_t **)&Block);
    v8 = (wchar_t *)MmAllocate(0x20Au);
    v21 = v8;
    v9 = Block;
    v10 = StringCchPrintfW(v8, 0x105u, L"%s\\%s", Block);
    v11 = v10;
    if ( v10 < 0 )
    {
      LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", 0x17Cu);
      free(v9);
      free(v8);
      free(v4);
      return v11;
    }
    free(v9);
  }
  v12 = CMsmqVssWriter::PrepareDirectoryForBackupRestore(this, v8, L"*.xml", 0, (void *)L"mapping");
  v14 = v12;
  if ( v12 < 0 )
  {
    LogMsgHR(v12, (wchar_t *)L"writer/mqwriter", 0x190u);
    free(v8);
    free(v4);
    return v14;
  }
  v15 = CMsmqVssWriter::CopyFiles(v13, v4, L"*.xml", v8);
  v14 = v15;
  if ( v15 < 0 )
  {
    LogMsgHR(v15, (wchar_t *)L"writer/mqwriter", 0x1A4u);
    free(v8);
    free(v4);
    return v14;
  }
  free(v8);
  free(v4);
  return 0;
}

```

## disassembly

```asm
0x180093860  mov     [rsp-28h+arg_0], rbx
0x180093865  push    rbp
0x180093866  push    rsi
0x180093867  push    rdi
0x180093868  push    r14
0x18009386a  push    r15
0x18009386c  mov     rbp, rsp
0x18009386f  sub     rsp, 60h
0x180093873  mov     rdi, rdx
0x180093876  mov     r14, rcx
0x180093879  mov     r15d, 20Ah
0x18009387f  mov     ecx, r15d; unsigned __int64
0x180093882  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180093887  mov     rbx, rax
0x18009388a  mov     [rbp+var_30], rax
0x18009388e  lea     rax, aMapping; "mapping"
0x180093895  mov     [rsp+60h+var_40], rax
0x18009389a  mov     r9, rdi
0x18009389d  lea     r8, aSS_3; "%s\\%s"
0x1800938a4  mov     edx, 105h; unsigned __int64
0x1800938a9  mov     rcx, rbx; wchar_t *
0x1800938ac  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800938b1  mov     edi, eax
0x1800938b3  test    eax, eax
0x1800938b5  jns     short loc_1800938DD
0x1800938b7  mov     r8d, 168h; unsigned __int16
0x1800938bd  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800938c4  mov     ecx, eax; int
0x1800938c6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800938cb  nop
0x1800938cc  mov     rcx, rbx; Block
0x1800938cf  call    cs:__imp_free
0x1800938d5  nop
0x1800938d6  mov     eax, edi
0x1800938d8  jmp     loc_180093A80
0x1800938dd  mov     [rbp+arg_10], 0
0x1800938e5  mov     [rbp+var_28], 0
0x1800938ec  mov     rax, [r14+20h]
0x1800938f0  mov     [rbp+var_20], rax
0x1800938f4  lea     rax, aQueuesaliaspat; "QueuesAliasPath"
0x1800938fb  mov     [rbp+var_18], rax
0x1800938ff  mov     [rbp+var_10], 0
0x180093906  mov     rsi, 0FFFFFFFF80000002h
0x18009390d  mov     [rbp+var_8], rsi
0x180093911  lea     rdx, [rbp+arg_10]; wchar_t **
0x180093915  lea     rcx, [rbp+var_28]; struct RegEntry *
0x180093919  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x18009391e  mov     rdi, [rbp+arg_10]
0x180093922  test    rdi, rdi
0x180093925  jnz     loc_1800939DF
0x18009392b  mov     [rbp+Block], rdi
0x18009392f  mov     [rbp+var_28], 1
0x180093936  mov     rax, [r14+20h]
0x18009393a  mov     [rbp+var_20], rax
0x18009393e  lea     rax, aMsmqrootpath; "MsmqRootPath"
0x180093945  mov     [rbp+var_18], rax
0x180093949  mov     [rbp+var_10], edi
0x18009394c  mov     [rbp+var_8], rsi
0x180093950  lea     rdx, [rbp+Block]; wchar_t **
0x180093954  lea     rcx, [rbp+var_28]; struct RegEntry *
0x180093958  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x18009395d  mov     rcx, r15; unsigned __int64
0x180093960  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180093965  mov     rdi, rax
0x180093968  mov     [rbp+arg_10], rax
0x18009396c  lea     rax, aMapping; "mapping"
0x180093973  mov     [rsp+60h+var_40], rax; int
0x180093978  mov     rsi, [rbp+Block]
0x18009397c  mov     r9, rsi
0x18009397f  lea     r8, aSS_3; "%s\\%s"
0x180093986  mov     edx, 105h; unsigned __int64
0x18009398b  mov     rcx, rdi; wchar_t *
0x18009398e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180093993  mov     r15d, eax
0x180093996  test    eax, eax
0x180093998  jns     short loc_1800939D5
0x18009399a  mov     r8d, 17Ch; unsigned __int16
0x1800939a0  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800939a7  mov     ecx, eax; int
0x1800939a9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800939ae  nop
0x1800939af  mov     rcx, rsi; Block
0x1800939b2  call    cs:__imp_free
0x1800939b8  nop
0x1800939b9  mov     rcx, rdi; Block
0x1800939bc  call    cs:__imp_free
0x1800939c2  nop
0x1800939c3  mov     rcx, rbx; Block
0x1800939c6  call    cs:__imp_free
0x1800939cc  nop
0x1800939cd  mov     eax, r15d
0x1800939d0  jmp     loc_180093A80
0x1800939d5  mov     rcx, rsi; Block
0x1800939d8  call    cs:__imp_free
0x1800939de  nop
0x1800939df  xor     r9d, r9d; int
0x1800939e2  lea     r8, aXml_0; "*.xml"
0x1800939e9  mov     rdx, rdi; wchar_t *
0x1800939ec  mov     rcx, r14; this
0x1800939ef  call    ?PrepareDirectoryForBackupRestore@CMsmqVssWriter@@AEAAJPEB_W0HPEAX@Z; CMsmqVssWriter::PrepareDirectoryForBackupRestore(wchar_t const *,wchar_t const *,int,void *)
0x1800939f4  mov     esi, eax
0x1800939f6  test    eax, eax
0x1800939f8  jns     short loc_180093A27
0x1800939fa  mov     r8d, 190h; unsigned __int16
0x180093a00  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093a07  mov     ecx, eax; int
0x180093a09  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093a0e  nop
0x180093a0f  mov     rcx, rdi; Block
0x180093a12  call    cs:__imp_free
0x180093a18  nop
0x180093a19  mov     rcx, rbx; Block
0x180093a1c  call    cs:__imp_free
0x180093a22  nop
0x180093a23  mov     eax, esi
0x180093a25  jmp     short loc_180093A80
0x180093a27  mov     r9, rdi; wchar_t *
0x180093a2a  lea     r8, aXml_0; "*.xml"
0x180093a31  mov     rdx, rbx; wchar_t *
0x180093a34  call    ?CopyFiles@CMsmqVssWriter@@AEAAJPEB_W00HPEAX@Z; CMsmqVssWriter::CopyFiles(wchar_t const *,wchar_t const *,wchar_t const *,int,void *)
0x180093a39  mov     esi, eax
0x180093a3b  test    eax, eax
0x180093a3d  jns     short loc_180093A6A
0x180093a3f  mov     r8d, 1A4h; unsigned __int16
0x180093a45  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093a4c  mov     ecx, eax; int
0x180093a4e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093a53  nop
0x180093a54  mov     rcx, rdi; Block
0x180093a57  call    cs:__imp_free
0x180093a5d  nop
0x180093a5e  mov     rcx, rbx; Block
0x180093a61  call    cs:__imp_free
0x180093a67  nop
0x180093a68  jmp     short loc_180093A23
0x180093a6a  mov     rcx, rdi; Block
0x180093a6d  call    cs:__imp_free
0x180093a73  nop
0x180093a74  mov     rcx, rbx; Block
0x180093a77  call    cs:__imp_free
0x180093a7d  nop
0x180093a7e  xor     eax, eax
0x180093a80  mov     rbx, [rsp+60h+arg_0]
0x180093a88  add     rsp, 60h
0x180093a8c  pop     r15
0x180093a8e  pop     r14
0x180093a90  pop     rdi
0x180093a91  pop     rsi
0x180093a92  pop     rbp
0x180093a93  retn
```
