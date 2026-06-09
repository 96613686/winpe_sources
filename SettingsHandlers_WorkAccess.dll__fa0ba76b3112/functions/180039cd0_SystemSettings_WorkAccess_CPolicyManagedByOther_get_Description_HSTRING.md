# SystemSettings::WorkAccess::CPolicyManagedByOther::get_Description(HSTRING__ * *)

- ea: `0x180039cd0`
- end: `0x180039d96`
- name: `?get_Description@CPolicyManagedByOther@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `198`
- prototype: `int(SystemSettings::WorkAccess::CPolicyManagedByOther *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180016e84`
- `0x1800176bc`
- `0x180039cd0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d77`

## string_xrefs

- `0x180039d3f`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CPolicyManagedByOther::get_Description(
        SystemSettings::WorkAccess::CPolicyManagedByOther *this,
        HSTRING *a2)
{
  __int64 v2; // r9
  unsigned __int64 v4; // rcx
  int v5; // ebx
  const unsigned __int16 *v6; // r9
  unsigned int v7; // r8d
  const unsigned __int16 *v8; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v12; // [rsp+30h] [rbp+8h] BYREF
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 26);
  string = 0;
  if ( v2 )
  {
    v12 = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v2 + 2 * v4) );
    v5 = ULongLongToUInt(v4, &v12);
    if ( v5 < 0 )
      goto LABEL_8;
    v7 = v12;
    v8 = v6;
  }
  else
  {
    v7 = 0;
    v8 = &sourceString;
  }
  v5 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v8, v7);
  if ( v5 < 0 )
  {
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AA,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)(unsigned int)v5,
      v10);
    WindowsDeleteString(string);
    return (unsigned int)v5;
  }
  *a2 = string;
  string = 0;
  WindowsDeleteString(0);
  return 0;
}

```

## disassembly

```asm
0x180039cd0  mov     rax, rsp
0x180039cd3  mov     [rax+10h], rbx
0x180039cd7  mov     [rax+20h], rsi
0x180039cdb  push    rdi; int
0x180039cdc  sub     rsp, 20h
0x180039ce0  mov     r9, [rcx+0D0h]
0x180039ce7  xor     esi, esi
0x180039ce9  mov     [rax+18h], rsi
0x180039ced  mov     rdi, rdx
0x180039cf0  test    r9, r9
0x180039cf3  jz      short loc_180039D20
0x180039cf5  mov     [rax+8], esi
0x180039cf8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180039cfc  inc     rcx; unsigned __int64
0x180039cff  cmp     [r9+rcx*2], si
0x180039d04  jnz     short loc_180039CFC
0x180039d06  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x180039d0b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180039d10  mov     ebx, eax
0x180039d12  test    eax, eax
0x180039d14  js      short loc_180039D3A
0x180039d16  mov     r8d, [rsp+28h+arg_0]
0x180039d1b  mov     rdx, r9
0x180039d1e  jmp     short loc_180039D2A
0x180039d20  xor     r8d, r8d; unsigned int
0x180039d23  lea     rdx, sourceString; unsigned __int16 *
0x180039d2a  lea     rcx, [rsp+28h+string]; this
0x180039d2f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180039d34  mov     ebx, eax
0x180039d36  test    eax, eax
0x180039d38  jns     short loc_180039D68
0x180039d3a  mov     rcx, [rsp+28h]; this
0x180039d3f  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180039d46  mov     r9d, ebx; char *
0x180039d49  mov     edx, 6AAh; void *
0x180039d4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d53  mov     rcx, [rsp+28h+string]; string
0x180039d58  call    cs:__imp_WindowsDeleteString
0x180039d5f  nop     dword ptr [rax+rax+00h]
0x180039d64  mov     eax, ebx
0x180039d66  jmp     short loc_180039D85
0x180039d68  mov     rax, [rsp+28h+string]
0x180039d6d  xor     ecx, ecx; string
0x180039d6f  mov     [rdi], rax
0x180039d72  mov     [rsp+28h+string], rsi
0x180039d77  call    cs:__imp_WindowsDeleteString
0x180039d7e  nop     dword ptr [rax+rax+00h]
0x180039d83  xor     eax, eax
0x180039d85  mov     rbx, [rsp+28h+arg_8]
0x180039d8a  mov     rsi, [rsp+28h+arg_18]
0x180039d8f  add     rsp, 20h
0x180039d93  pop     rdi
0x180039d94  retn
```
