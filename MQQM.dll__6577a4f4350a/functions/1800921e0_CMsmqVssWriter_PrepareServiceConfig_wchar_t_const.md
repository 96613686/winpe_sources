# CMsmqVssWriter::PrepareServiceConfig(wchar_t const *)

- ea: `0x1800921e0`
- end: `0x18009240a`
- name: `?PrepareServiceConfig@CMsmqVssWriter@@AEAAJPEB_W@Z`
- size: `554`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task`

## callers

- `0x180091d70`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x18008e824`
- `0x18008eec0`
- `0x18008f714`
- `0x180092180`
- `0x1800921e0`
- `0x18009a590`
- `0x18009bd1c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x1800922d5`
- `msvcrt!free` at `0x1800922e0`
- `msvcrt!free` at `0x18009234e`
- `msvcrt!free` at `0x180092359`
- `msvcrt!free` at `0x18009237b`
- `msvcrt!free` at `0x180092386`
- `msvcrt!free` at `0x180092395`
- `msvcrt!free` at `0x1800923a0`
- `msvcrt!free` at `0x1800922d5`
- `msvcrt!free` at `0x1800922e0`
- `msvcrt!free` at `0x18009234e`
- `msvcrt!free` at `0x180092359`
- `msvcrt!free` at `0x18009237b`
- `msvcrt!free` at `0x180092386`
- `msvcrt!free` at `0x180092395`
- `msvcrt!free` at `0x1800923a0`

## string_xrefs

- `0x18009225b`: `StorePersistentPath`
- `0x180092225`: `writer/mqwriter`
- `0x1800922c3`: `writer/mqwriter`
- `0x18009233b`: `writer/mqwriter`
- `0x180092368`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::PrepareServiceConfig(CMsmqVssWriter *this, const wchar_t *a2)
{
  CMsmqVssWriter *v4; // rcx
  int v5; // ebx
  unsigned __int16 v6; // r8
  void *v8; // rbx
  int v9; // eax
  unsigned int v10; // esi
  unsigned int i; // esi
  int v12; // eax
  CMsmqVssWriter *v13; // rcx
  unsigned int v14; // r12d
  int v15; // eax
  void *v16; // [rsp+20h] [rbp-50h]
  void *Block[2]; // [rsp+30h] [rbp-40h] BYREF
  wchar_t v18[4]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+48h] [rbp-28h]
  const wchar_t *v20; // [rsp+50h] [rbp-20h]
  int v21; // [rsp+58h] [rbp-18h]
  __int64 v22; // [rsp+60h] [rbp-10h]

  v5 = CMsmqVssWriter::PrepareDirectoryForBackupRestore(this, a2, L"*.*", 1, v16);
  if ( v5 < 0 )
  {
    v6 = 1360;
LABEL_3:
    LogMsgHR(v5, (wchar_t *)L"writer/mqwriter", v6);
    return (unsigned int)v5;
  }
  if ( (*((_BYTE *)this + 52) & 2) != 0 )
  {
    Block[0] = 0;
    wcscpy(v18, L"\x01");
    v19 = *((_QWORD *)this + 4);
    v20 = L"StorePersistentPath";
    v21 = 0;
    v22 = -2147483646;
    CmQueryValue((const struct RegEntry *)v18, (wchar_t **)Block);
    v8 = MmAllocate(0x20Au);
    Block[1] = v8;
    v9 = StringCchPrintfW((wchar_t *)v8, 0x105u, L"%s\\%s", Block[0], L"LQS");
    v10 = v9;
    if ( v9 < 0 )
    {
      LogMsgHR(v9, (wchar_t *)L"writer/mqwriter", 0x564u);
      free(v8);
      free(Block[0]);
      return v10;
    }
    for ( i = 1; i <= 6; ++i )
    {
      v12 = StringCchPrintfW(v18, 0x10u, L"%08d.*", i);
      v14 = v12;
      if ( v12 < 0 )
      {
        LogMsgHR(v12, (wchar_t *)L"writer/mqwriter", 0x578u);
        free(v8);
        free(Block[0]);
        return v14;
      }
      v15 = CMsmqVssWriter::CopyFiles(v13, (const wchar_t *)v8, v18, a2);
      v14 = v15;
      if ( v15 < 0 )
      {
        LogMsgHR(v15, (wchar_t *)L"writer/mqwriter", 0x58Cu);
        free(v8);
        free(Block[0]);
        return v14;
      }
    }
    free(v8);
    free(Block[0]);
  }
  if ( (*((_BYTE *)this + 52) & 1) != 0 )
  {
    v5 = CMsmqVssWriter::BackupRegistry(this, a2);
    if ( v5 < 0 )
    {
      v6 = 1440;
      goto LABEL_3;
    }
  }
  if ( (*((_BYTE *)this + 52) & 8) != 0 )
  {
    v5 = CMsmqVssWriter::BackupWebACLs(v4, a2);
    if ( v5 < 0 )
    {
      v6 = 1450;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800921e0  mov     [rsp-28h+arg_10], rbx
0x1800921e5  push    rbp
0x1800921e6  push    rsi
0x1800921e7  push    rdi
0x1800921e8  push    r12
0x1800921ea  push    r15
0x1800921ec  mov     rbp, rsp
0x1800921ef  sub     rsp, 70h
0x1800921f3  mov     rax, cs:__security_cookie
0x1800921fa  xor     rax, rsp
0x1800921fd  mov     [rbp+var_8], rax
0x180092201  mov     r15, rdx
0x180092204  mov     rdi, rcx
0x180092207  mov     r9d, 1; int
0x18009220d  lea     r8, asc_1800FEF68; "*.*"
0x180092214  call    ?PrepareDirectoryForBackupRestore@CMsmqVssWriter@@AEAAJPEB_W0HPEAX@Z; CMsmqVssWriter::PrepareDirectoryForBackupRestore(wchar_t const *,wchar_t const *,int,void *)
0x180092219  mov     ebx, eax
0x18009221b  test    eax, eax
0x18009221d  jns     short loc_18009223A
0x18009221f  mov     r8d, 550h; unsigned __int16
0x180092225  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009222c  mov     ecx, ebx; int
0x18009222e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092233  mov     eax, ebx
0x180092235  jmp     loc_1800923EA
0x18009223a  test    byte ptr [rdi+34h], 2
0x18009223e  jz      loc_1800923A7
0x180092244  mov     [rbp+Block], 0
0x18009224c  mov     dword ptr [rbp+var_30], 1
0x180092253  mov     rax, [rdi+20h]
0x180092257  mov     [rbp+var_28], rax
0x18009225b  lea     rax, aStorepersisten; "StorePersistentPath"
0x180092262  mov     [rbp+var_20], rax
0x180092266  mov     [rbp+var_18], 0
0x18009226d  mov     [rbp+var_10], 0FFFFFFFF80000002h
0x180092275  lea     rdx, [rbp+Block]; wchar_t **
0x180092279  lea     rcx, [rbp+var_30]; struct RegEntry *
0x18009227d  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x180092282  mov     ecx, 20Ah; unsigned __int64
0x180092287  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009228c  mov     rbx, rax
0x18009228f  mov     [rbp+var_38], rax
0x180092293  lea     rax, aLqs_1; "LQS"
0x18009229a  mov     qword ptr [rsp+70h+var_50], rax; int
0x18009229f  mov     r9, [rbp+Block]
0x1800922a3  lea     r8, aSS_3; "%s\\%s"
0x1800922aa  mov     edx, 105h; unsigned __int64
0x1800922af  mov     rcx, rbx; wchar_t *
0x1800922b2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800922b7  mov     esi, eax
0x1800922b9  test    eax, eax
0x1800922bb  jns     short loc_1800922EE
0x1800922bd  mov     r8d, 564h; unsigned __int16
0x1800922c3  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800922ca  mov     ecx, eax; int
0x1800922cc  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800922d1  nop
0x1800922d2  mov     rcx, rbx; Block
0x1800922d5  call    cs:__imp_free
0x1800922db  nop
0x1800922dc  mov     rcx, [rbp+Block]; Block
0x1800922e0  call    cs:__imp_free
0x1800922e6  nop
0x1800922e7  mov     eax, esi
0x1800922e9  jmp     loc_1800923EA
0x1800922ee  mov     esi, 1
0x1800922f3  cmp     esi, 6
0x1800922f6  ja      loc_180092392
0x1800922fc  mov     r9d, esi
0x1800922ff  lea     r8, a08d; "%08d.*"
0x180092306  mov     edx, 10h; unsigned __int64
0x18009230b  lea     rcx, [rbp+var_30]; wchar_t *
0x18009230f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180092314  mov     r12d, eax
0x180092317  test    eax, eax
0x180092319  js      short loc_180092362
0x18009231b  mov     r9, r15; wchar_t *
0x18009231e  lea     r8, [rbp+var_30]; wchar_t *
0x180092322  mov     rdx, rbx; wchar_t *
0x180092325  call    ?CopyFiles@CMsmqVssWriter@@AEAAJPEB_W00HPEAX@Z; CMsmqVssWriter::CopyFiles(wchar_t const *,wchar_t const *,wchar_t const *,int,void *)
0x18009232a  mov     r12d, eax
0x18009232d  test    eax, eax
0x18009232f  js      short loc_180092335
0x180092331  inc     esi
0x180092333  jmp     short loc_1800922F3
0x180092335  mov     r8d, 58Ch; unsigned __int16
0x18009233b  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092342  mov     ecx, r12d; int
0x180092345  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009234a  nop
0x18009234b  mov     rcx, rbx; Block
0x18009234e  call    cs:__imp_free
0x180092354  nop
0x180092355  mov     rcx, [rbp+Block]; Block
0x180092359  call    cs:__imp_free
0x18009235f  nop
0x180092360  jmp     short loc_18009238D
0x180092362  mov     r8d, 578h; unsigned __int16
0x180092368  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009236f  mov     ecx, r12d; int
0x180092372  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092377  nop
0x180092378  mov     rcx, rbx; Block
0x18009237b  call    cs:__imp_free
0x180092381  nop
0x180092382  mov     rcx, [rbp+Block]; Block
0x180092386  call    cs:__imp_free
0x18009238c  nop
0x18009238d  mov     eax, r12d
0x180092390  jmp     short loc_1800923EA
0x180092392  mov     rcx, rbx; Block
0x180092395  call    cs:__imp_free
0x18009239b  nop
0x18009239c  mov     rcx, [rbp+Block]; Block
0x1800923a0  call    cs:__imp_free
0x1800923a6  nop
0x1800923a7  test    byte ptr [rdi+34h], 1
0x1800923ab  jz      short loc_1800923C9
0x1800923ad  mov     rdx, r15; wchar_t *
0x1800923b0  mov     rcx, rdi; this
0x1800923b3  call    ?BackupRegistry@CMsmqVssWriter@@AEAAJPEB_W@Z; CMsmqVssWriter::BackupRegistry(wchar_t const *)
0x1800923b8  mov     ebx, eax
0x1800923ba  test    eax, eax
0x1800923bc  jns     short loc_1800923C9
0x1800923be  mov     r8d, 5A0h
0x1800923c4  jmp     loc_180092225
0x1800923c9  test    byte ptr [rdi+34h], 8
0x1800923cd  jz      short loc_1800923E8
0x1800923cf  mov     rdx, r15; wchar_t *
0x1800923d2  call    ?BackupWebACLs@CMsmqVssWriter@@AEAAJPEB_W@Z; CMsmqVssWriter::BackupWebACLs(wchar_t const *)
0x1800923d7  mov     ebx, eax
0x1800923d9  test    eax, eax
0x1800923db  jns     short loc_1800923E8
0x1800923dd  mov     r8d, 5AAh
0x1800923e3  jmp     loc_180092225
0x1800923e8  xor     eax, eax
0x1800923ea  mov     rcx, [rbp+var_8]
0x1800923ee  xor     rcx, rsp; StackCookie
0x1800923f1  call    __security_check_cookie
0x1800923f6  mov     rbx, [rsp+70h+arg_10]
0x1800923fe  add     rsp, 70h
0x180092402  pop     r15
0x180092404  pop     r12
0x180092406  pop     rdi
0x180092407  pop     rsi
0x180092408  pop     rbp
0x180092409  retn
```
