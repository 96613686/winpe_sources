# CMessageConversationHost::InitializeSystemServer(uint *)

- ea: `0x1801eb9b0`
- end: `0x1801ebb57`
- name: `?InitializeSystemServer@CMessageConversationHost@@AEAAJPEAI@Z`
- size: `423`
- prototype: `__int64 __fastcall(CMessageConversationHost *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801eb8f0`

## callees

- `0x180042de0`
- `0x1801d6e60`
- `0x1801d6ec4`
- `0x1801eb9b0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801eb9dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801eb9dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eba2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eba2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801eb9f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801ebb3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801eb9f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801ebb3a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801eba24`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801eba24`

## string_xrefs

- `0x1801eba9c`: `System\CompositionEngine`

## pseudocode

```c
__int64 __fastcall CMessageConversationHost::InitializeSystemServer(CMessageConversationHost *this, unsigned int *a2)
{
  HLOCAL v4; // rbx
  signed int LastError; // eax
  signed int v6; // ebx
  int v7; // r9d
  int v8; // eax
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(__int64, const wchar_t *, __int64, __int64 *, int, int, int, CMessageConversationHost *, unsigned int *, char *); // rax
  __int64 v11; // rcx
  unsigned int v13; // [rsp+20h] [rbp-50h]
  __int64 v14; // [rsp+60h] [rbp-10h] BYREF
  int v15; // [rsp+68h] [rbp-8h]
  HLOCAL hMem; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  hMem = 0;
  v17 = 0;
  SetLastError(0);
  v4 = hMem;
  if ( hMem )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    LocalFree(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  hMem = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;;;S-1-15-3-1024-1502825166-1963708345-2616377461-2562897074-4192028372-3"
          "968301570-1997628692-1435953622)",
         1u,
         &hMem,
         0) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL, __int64 *))(**((_QWORD **)this + 2) + 64LL))(
           *((_QWORD *)this + 2),
           hMem,
           &v17);
    v6 = v8;
    if ( v8 < 0 )
    {
      v13 = 131;
    }
    else
    {
      v9 = *((_QWORD *)this + 2);
      v10 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, int, int, int, CMessageConversationHost *, unsigned int *, char *))(*(_QWORD *)v9 + 304LL);
      v14 = 0;
      v15 = 1;
      v8 = v10(v9, L"System\\CompositionEngine", v17, &v14, 1, 1, 1, this, a2, (char *)this + 24);
      v6 = v8;
      if ( v8 >= 0 )
        goto LABEL_15;
      v13 = 142;
    }
    v7 = v8;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v13 = 127;
    if ( v6 >= 0 )
      v6 = -2003304445;
    v7 = v6;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, v13, 0);
LABEL_15:
  v11 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801eb9b0  mov     [rsp-18h+arg_0], rbx
0x1801eb9b5  mov     [rsp-18h+arg_8], rsi
0x1801eb9ba  push    rbp
0x1801eb9bb  push    rdi
0x1801eb9bc  push    r15
0x1801eb9be  mov     rbp, rsp
0x1801eb9c1  sub     rsp, 70h
0x1801eb9c5  mov     rdi, rcx
0x1801eb9c8  mov     [rbp+hMem], 0
0x1801eb9d0  xor     ecx, ecx; dwErrCode
0x1801eb9d2  mov     [rbp+arg_18], 0
0x1801eb9da  mov     rsi, rdx
0x1801eb9dd  call    cs:__imp_SetLastError
0x1801eb9e3  mov     rbx, [rbp+hMem]
0x1801eb9e7  test    rbx, rbx
0x1801eb9ea  jz      short loc_1801EBA07
0x1801eb9ec  lea     rcx, [rbp+var_10]; this
0x1801eb9f0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801eb9f5  mov     rcx, rbx; hMem
0x1801eb9f8  call    cs:__imp_LocalFree
0x1801eb9fe  lea     rcx, [rbp+var_10]; this
0x1801eba02  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801eba07  xor     r9d, r9d; SecurityDescriptorSize
0x1801eba0a  mov     [rbp+hMem], 0
0x1801eba12  lea     r8, [rbp+hMem]; SecurityDescriptor
0x1801eba16  lea     rcx, StringSecurityDescriptor; "D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;"...
0x1801eba1d  lea     r15d, [r9+1]
0x1801eba21  mov     edx, r15d; StringSDRevision
0x1801eba24  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801eba2a  test    eax, eax
0x1801eba2c  jnz     short loc_1801EBA66
0x1801eba2e  call    cs:__imp_GetLastError
0x1801eba34  mov     ebx, eax
0x1801eba36  test    eax, eax
0x1801eba38  jle     short loc_1801EBA43
0x1801eba3a  movzx   ebx, ax
0x1801eba3d  or      ebx, 80070000h
0x1801eba43  test    ebx, ebx
0x1801eba45  mov     [rsp+70h+var_48], 0
0x1801eba4e  mov     eax, 88980003h
0x1801eba53  mov     [rsp+70h+var_50], 7Fh
0x1801eba5b  cmovns  ebx, eax
0x1801eba5e  mov     r9d, ebx
0x1801eba61  jmp     loc_1801EBB07
0x1801eba66  mov     rcx, [rdi+10h]
0x1801eba6a  lea     r8, [rbp+arg_18]
0x1801eba6e  mov     rdx, [rbp+hMem]
0x1801eba72  mov     rax, [rcx]
0x1801eba75  mov     rax, [rax+40h]
0x1801eba79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eba7e  mov     ebx, eax
0x1801eba80  test    eax, eax
0x1801eba82  js      short loc_1801EBAF3
0x1801eba84  mov     eax, [rbp+var_4]
0x1801eba87  lea     rdx, [rdi+18h]
0x1801eba8b  mov     rcx, [rdi+10h]
0x1801eba8f  lea     r9, [rbp+var_10]
0x1801eba93  mov     r8, [rbp+arg_18]
0x1801eba97  mov     [rsp+70h+var_28], rdx
0x1801eba9c  lea     rdx, aSystemComposit_0; "System\\CompositionEngine"
0x1801ebaa3  mov     [rsp+70h+var_30], rsi
0x1801ebaa8  mov     [rbp+var_4], eax
0x1801ebaab  mov     rax, [rcx]
0x1801ebaae  mov     [rsp+70h+var_38], rdi
0x1801ebab3  mov     [rsp+70h+var_40], r15d
0x1801ebab8  mov     dword ptr [rsp+70h+var_48], r15d
0x1801ebabd  mov     rax, [rax+130h]
0x1801ebac4  mov     [rbp+var_10], 0
0x1801ebacc  mov     [rbp+var_8], r15d
0x1801ebad0  mov     [rsp+70h+var_50], r15d
0x1801ebad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ebada  mov     ebx, eax
0x1801ebadc  test    eax, eax
0x1801ebade  jns     short loc_1801EBB14
0x1801ebae0  mov     [rsp+70h+var_48], 0
0x1801ebae9  mov     [rsp+70h+var_50], 8Eh
0x1801ebaf1  jmp     short loc_1801EBB04
0x1801ebaf3  mov     [rsp+70h+var_48], 0; void *
0x1801ebafc  mov     [rsp+70h+var_50], 83h; unsigned int
0x1801ebb04  mov     r9d, eax; int
0x1801ebb07  xor     edx, edx; int *
0x1801ebb09  xor     r8d, r8d; unsigned int
0x1801ebb0c  lea     ecx, [rdx+14h]; unsigned int
0x1801ebb0f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801ebb14  mov     rcx, [rbp+arg_18]
0x1801ebb18  test    rcx, rcx
0x1801ebb1b  jz      short loc_1801EBB31
0x1801ebb1d  mov     [rbp+arg_18], 0
0x1801ebb25  mov     rax, [rcx]
0x1801ebb28  mov     rax, [rax+10h]
0x1801ebb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ebb31  mov     rcx, [rbp+hMem]; hMem
0x1801ebb35  test    rcx, rcx
0x1801ebb38  jz      short loc_1801EBB40
0x1801ebb3a  call    cs:__imp_LocalFree
0x1801ebb40  lea     r11, [rsp+70h+var_s0]
0x1801ebb45  mov     eax, ebx
0x1801ebb47  mov     rbx, [r11+20h]
0x1801ebb4b  mov     rsi, [r11+28h]
0x1801ebb4f  mov     rsp, r11
0x1801ebb52  pop     r15
0x1801ebb54  pop     rdi
0x1801ebb55  pop     rbp
0x1801ebb56  retn
```
