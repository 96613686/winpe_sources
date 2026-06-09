# ErrOpenFile(ushort const *,int *,ushort *)

- ea: `0x18003ee5c`
- end: `0x18003ef96`
- name: `?ErrOpenFile@@YAJPEBGPEAHPEAG@Z`
- size: `314`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ece8`

## callees

- `0x180032cbc`
- `0x18003ee5c`
- `0x18003ef9c`
- `0x18004d900`
- `0x18004e530`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003ef6f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003ef6f`
- `ntdll!LdrGetDllPath` at `0x18003eedd`
- `ntdll!LdrGetDllPath` at `0x18003eedd`
- `ntdll!RtlReleasePath` at `0x18003ef16`
- `ntdll!RtlReleasePath` at `0x18003ef16`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18003ef09`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18003ef09`

## pseudocode

```c
__int64 __fastcall ErrOpenFile(LPCWSTR lpFileName, int *a2, unsigned __int16 *a3)
{
  WINBOOL v6; // r8d
  DWORD v7; // ebx
  int v8; // ebx
  __int64 result; // rax
  LPCWSTR lpPath; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[524]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(&v12, 0, 0x20Cu);
  if ( (NtCurrentPeb()->AppCompatFlags.LowPart & 0x800000) != 0 )
    goto LABEL_11;
  lpPath = 0;
  v11 = 0;
  v7 = 0;
  if ( !(unsigned int)LdrGetDllPath(lpFileName, 2560, &lpPath, &v11) )
    v7 = SearchPathW(lpPath, lpFileName, 0, 0x104u, Buffer, 0);
  RtlReleasePath(lpPath);
  if ( v7 - 1 > 0x103 || (v8 = OpenLongFileW(Buffer, (__int64)&v12, v6), v8 == -1) )
  {
LABEL_11:
    v8 = OpenLongFileW(lpFileName, (__int64)&v12, v6);
    if ( v8 == -1 )
      return TiperrOfOFErr(v12);
  }
  _o_wcsncpy_s(a3, 260, v13);
  result = 0;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x18003ee5c  push    rbp
0x18003ee5e  push    rbx
0x18003ee5f  push    rsi
0x18003ee60  push    rdi
0x18003ee61  push    r14
0x18003ee63  lea     rbp, [rsp-370h]
0x18003ee6b  sub     rsp, 470h
0x18003ee72  mov     rax, cs:__security_cookie
0x18003ee79  xor     rax, rsp
0x18003ee7c  mov     [rbp+390h+var_30], rax
0x18003ee83  mov     r14, r8
0x18003ee86  mov     rsi, rdx
0x18003ee89  mov     rdi, rcx
0x18003ee8c  xor     edx, edx; Val
0x18003ee8e  mov     r8d, 20Ch; Size
0x18003ee94  lea     rcx, [rsp+490h+var_450]; void *
0x18003ee99  call    memset_0
0x18003ee9e  mov     rax, gs:60h
0x18003eea7  test    dword ptr [rax+2C8h], 800000h
0x18003eeb1  jnz     loc_18003EF3E
0x18003eeb7  lea     r9, [rsp+490h+var_458]
0x18003eebc  mov     [rsp+490h+lpPath], 0
0x18003eec5  lea     r8, [rsp+490h+lpPath]
0x18003eeca  mov     [rsp+490h+var_458], 0
0x18003eed3  mov     edx, 0A00h
0x18003eed8  mov     rcx, rdi
0x18003eedb  xor     ebx, ebx
0x18003eedd  call    cs:__imp_LdrGetDllPath
0x18003eee3  test    eax, eax
0x18003eee5  jnz     short loc_18003EF11
0x18003eee7  mov     rcx, [rsp+490h+lpPath]; lpPath
0x18003eeec  lea     rax, [rbp+390h+Buffer]
0x18003eef3  mov     [rsp+490h+lpFilePart], rbx; lpFilePart
0x18003eef8  mov     r9d, 104h; nBufferLength
0x18003eefe  xor     r8d, r8d; lpExtension
0x18003ef01  mov     [rsp+490h+lpBuffer], rax; lpBuffer
0x18003ef06  mov     rdx, rdi; lpFileName
0x18003ef09  call    cs:__imp_SearchPathW
0x18003ef0f  mov     ebx, eax
0x18003ef11  mov     rcx, [rsp+490h+lpPath]
0x18003ef16  call    cs:__imp_RtlReleasePath
0x18003ef1c  lea     eax, [rbx-1]
0x18003ef1f  cmp     eax, 103h
0x18003ef24  ja      short loc_18003EF3E
0x18003ef26  lea     rdx, [rsp+490h+var_450]
0x18003ef2b  lea     rcx, [rbp+390h+Buffer]; lpFileName
0x18003ef32  call    OpenLongFileW
0x18003ef37  mov     ebx, eax
0x18003ef39  cmp     eax, 0FFFFFFFFh
0x18003ef3c  jnz     short loc_18003EF5D
0x18003ef3e  lea     rdx, [rsp+490h+var_450]
0x18003ef43  mov     rcx, rdi; lpFileName
0x18003ef46  call    OpenLongFileW
0x18003ef4b  mov     ebx, eax
0x18003ef4d  cmp     eax, 0FFFFFFFFh
0x18003ef50  jnz     short loc_18003EF5D
0x18003ef52  mov     ecx, [rsp+490h+var_450]; unsigned int
0x18003ef56  call    ?TiperrOfOFErr@@YAJI@Z; TiperrOfOFErr(uint)
0x18003ef5b  jmp     short loc_18003EF79
0x18003ef5d  mov     r9d, 103h
0x18003ef63  lea     r8, [rsp+490h+var_44C]
0x18003ef68  mov     rcx, r14
0x18003ef6b  lea     edx, [r9+1]
0x18003ef6f  call    cs:__imp__o_wcsncpy_s
0x18003ef75  xor     eax, eax
0x18003ef77  mov     [rsi], ebx
0x18003ef79  mov     rcx, [rbp+390h+var_30]
0x18003ef80  xor     rcx, rsp; StackCookie
0x18003ef83  call    __security_check_cookie
0x18003ef88  add     rsp, 470h
0x18003ef8f  pop     r14
0x18003ef91  pop     rdi
0x18003ef92  pop     rsi
0x18003ef93  pop     rbx
0x18003ef94  pop     rbp
0x18003ef95  retn
```
