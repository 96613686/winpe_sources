# wil::is_default_system_managed_account(ushort const *)

- ea: `0x18002976c`
- end: `0x18002988b`
- name: `?is_default_system_managed_account@wil@@YA_NPEBG@Z`
- size: `287`
- prototype: `bool __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800295d4`

## callees

- `0x18002976c`
- `0x18002d1ee`
- `0x18002d220`

## import_xrefs

- `msvcrt!wcschr` at `0x1800297e5`
- `msvcrt!wcschr` at `0x1800297e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029827`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029827`
- `KERNEL32!CompareStringOrdinal` at `0x180029859`
- `KERNEL32!CompareStringOrdinal` at `0x180029859`
- `SspiCli!GetUserNameExW` at `0x1800297d0`
- `SspiCli!GetUserNameExW` at `0x1800297d0`

## pseudocode

```c
char __fastcall wil::is_default_system_managed_account(wil *this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rbx
  LSTATUS ValueW; // eax
  bool v4; // sf
  char v5; // di
  ULONG nSize; // [rsp+40h] [rbp-468h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-464h] BYREF
  WCHAR String2[264]; // [rsp+50h] [rbp-458h] BYREF
  WCHAR NameBuffer[280]; // [rsp+260h] [rbp-248h] BYREF

  v2 = 0;
  memset_0(String2, 0, 0x202u);
  pcbData[0] = 514;
  memset_0(NameBuffer, 0, 0x222u);
  nSize = 273;
  if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    v2 = wcschr(NameBuffer, 0x5Cu) + 1;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             2u,
             0,
             String2,
             pcbData);
  v4 = ValueW < 0;
  if ( ValueW > 0 )
    v4 = 1;
  if ( v4 )
    return 0;
  if ( !v2 )
    return 0;
  v5 = 1;
  if ( CompareStringOrdinal(v2, -1, String2, -1, 1) != 2 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x18002976c  mov     [rsp+arg_0], rbx
0x180029771  push    rdi
0x180029772  sub     rsp, 4A0h
0x180029779  mov     rax, cs:__security_cookie
0x180029780  xor     rax, rsp
0x180029783  mov     [rsp+4A8h+var_18], rax
0x18002978b  mov     edi, 202h
0x180029790  lea     rcx, [rsp+4A8h+String2]; void *
0x180029795  mov     r8d, edi; Size
0x180029798  xor     edx, edx; Val
0x18002979a  xor     ebx, ebx
0x18002979c  call    memset_0
0x1800297a1  xor     edx, edx; Val
0x1800297a3  mov     [rsp+4A8h+var_464], edi
0x1800297a7  lea     r8d, [rdi+20h]; Size
0x1800297ab  lea     rcx, [rsp+4A8h+NameBuffer]; void *
0x1800297b3  call    memset_0
0x1800297b8  lea     r8, [rsp+4A8h+nSize]; nSize
0x1800297bd  mov     [rsp+4A8h+nSize], 111h
0x1800297c5  lea     rdx, [rsp+4A8h+NameBuffer]; lpNameBuffer
0x1800297cd  lea     ecx, [rbx+2]; NameFormat
0x1800297d0  call    cs:__imp_GetUserNameExW
0x1800297d6  test    al, al
0x1800297d8  jz      short loc_1800297EF
0x1800297da  lea     edx, [rbx+5Ch]; Ch
0x1800297dd  lea     rcx, [rsp+4A8h+NameBuffer]; Str
0x1800297e5  call    cs:__imp_wcschr
0x1800297eb  lea     rbx, [rax+2]
0x1800297ef  lea     rax, [rsp+4A8h+var_464]
0x1800297f4  mov     r9d, 2; dwFlags
0x1800297fa  mov     [rsp+4A8h+pcbData], rax; pcbData
0x1800297ff  lea     r8, Value; "DefaultAccountSAMName"
0x180029806  lea     rax, [rsp+4A8h+String2]
0x18002980b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180029812  mov     [rsp+4A8h+pvData], rax; pvData
0x180029817  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002981e  mov     [rsp+4A8h+pdwType], 0; pdwType
0x180029827  call    cs:__imp_RegGetValueW
0x18002982d  test    eax, eax
0x18002982f  jle     short loc_18002983B
0x180029831  movzx   eax, ax
0x180029834  or      eax, 80070000h
0x180029839  test    eax, eax
0x18002983b  js      short loc_180029864
0x18002983d  test    rbx, rbx
0x180029840  jz      short loc_180029864
0x180029842  or      edx, 0FFFFFFFFh; cchCount1
0x180029845  lea     r8, [rsp+4A8h+String2]; lpString2
0x18002984a  mov     edi, 1
0x18002984f  mov     r9d, edx; cchCount2
0x180029852  mov     rcx, rbx; lpString1
0x180029855  mov     dword ptr [rsp+4A8h+pdwType], edi; bIgnoreCase
0x180029859  call    cs:__imp_CompareStringOrdinal
0x18002985f  cmp     eax, 2
0x180029862  jz      short loc_180029867
0x180029864  xor     dil, dil
0x180029867  mov     al, dil
0x18002986a  mov     rcx, [rsp+4A8h+var_18]
0x180029872  xor     rcx, rsp; StackCookie
0x180029875  call    __security_check_cookie
0x18002987a  mov     rbx, [rsp+4A8h+arg_0]
0x180029882  add     rsp, 4A0h
0x180029889  pop     rdi
0x18002988a  retn
```
