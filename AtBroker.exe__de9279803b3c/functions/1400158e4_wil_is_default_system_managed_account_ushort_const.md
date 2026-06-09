# wil::is_default_system_managed_account(ushort const *)

- ea: `0x1400158e4`
- end: `0x140015a03`
- name: `?is_default_system_managed_account@wil@@YA_NPEBG@Z`
- size: `287`
- prototype: `char __fastcall(wil *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400157f8`

## callees

- `0x1400158e4`
- `0x140015ac2`
- `0x140015b00`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1400159d1`
- `KERNEL32!CompareStringOrdinal` at `0x1400159d1`
- `KERNEL32!RegGetValueW` at `0x14001599f`
- `KERNEL32!RegGetValueW` at `0x14001599f`
- `msvcrt!wcschr` at `0x14001595d`
- `msvcrt!wcschr` at `0x14001595d`
- `Secur32!GetUserNameExW` at `0x140015948`
- `Secur32!GetUserNameExW` at `0x140015948`

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
0x1400158e4  mov     [rsp+arg_0], rbx
0x1400158e9  push    rdi
0x1400158ea  sub     rsp, 4A0h
0x1400158f1  mov     rax, cs:__security_cookie
0x1400158f8  xor     rax, rsp
0x1400158fb  mov     [rsp+4A8h+var_18], rax
0x140015903  mov     edi, 202h
0x140015908  lea     rcx, [rsp+4A8h+String2]; void *
0x14001590d  mov     r8d, edi; Size
0x140015910  xor     edx, edx; Val
0x140015912  xor     ebx, ebx
0x140015914  call    memset_0
0x140015919  xor     edx, edx; Val
0x14001591b  mov     [rsp+4A8h+var_464], edi
0x14001591f  lea     r8d, [rdi+20h]; Size
0x140015923  lea     rcx, [rsp+4A8h+NameBuffer]; void *
0x14001592b  call    memset_0
0x140015930  lea     r8, [rsp+4A8h+nSize]; nSize
0x140015935  mov     [rsp+4A8h+nSize], 111h
0x14001593d  lea     rdx, [rsp+4A8h+NameBuffer]; lpNameBuffer
0x140015945  lea     ecx, [rbx+2]; NameFormat
0x140015948  call    cs:__imp_GetUserNameExW
0x14001594e  test    al, al
0x140015950  jz      short loc_140015967
0x140015952  lea     edx, [rbx+5Ch]; Ch
0x140015955  lea     rcx, [rsp+4A8h+NameBuffer]; Str
0x14001595d  call    cs:__imp_wcschr
0x140015963  lea     rbx, [rax+2]
0x140015967  lea     rax, [rsp+4A8h+var_464]
0x14001596c  mov     r9d, 2; dwFlags
0x140015972  mov     [rsp+4A8h+pcbData], rax; pcbData
0x140015977  lea     r8, Value; "DefaultAccountSAMName"
0x14001597e  lea     rax, [rsp+4A8h+String2]
0x140015983  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001598a  mov     [rsp+4A8h+pvData], rax; pvData
0x14001598f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140015996  mov     [rsp+4A8h+pdwType], 0; pdwType
0x14001599f  call    cs:__imp_RegGetValueW
0x1400159a5  test    eax, eax
0x1400159a7  jle     short loc_1400159B3
0x1400159a9  movzx   eax, ax
0x1400159ac  or      eax, 80070000h
0x1400159b1  test    eax, eax
0x1400159b3  js      short loc_1400159DC
0x1400159b5  test    rbx, rbx
0x1400159b8  jz      short loc_1400159DC
0x1400159ba  or      edx, 0FFFFFFFFh; cchCount1
0x1400159bd  lea     r8, [rsp+4A8h+String2]; lpString2
0x1400159c2  mov     edi, 1
0x1400159c7  mov     r9d, edx; cchCount2
0x1400159ca  mov     rcx, rbx; lpString1
0x1400159cd  mov     dword ptr [rsp+4A8h+pdwType], edi; bIgnoreCase
0x1400159d1  call    cs:__imp_CompareStringOrdinal
0x1400159d7  cmp     eax, 2
0x1400159da  jz      short loc_1400159DF
0x1400159dc  xor     dil, dil
0x1400159df  mov     al, dil
0x1400159e2  mov     rcx, [rsp+4A8h+var_18]
0x1400159ea  xor     rcx, rsp; StackCookie
0x1400159ed  call    __security_check_cookie
0x1400159f2  mov     rbx, [rsp+4A8h+arg_0]
0x1400159fa  add     rsp, 4A0h
0x140015a01  pop     rdi
0x140015a02  retn
```
