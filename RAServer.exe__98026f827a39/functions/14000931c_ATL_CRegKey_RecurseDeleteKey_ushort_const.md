# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x14000931c`
- end: `0x140009429`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000931c`
- `0x140009754`

## callees

- `0x140005134`
- `0x140005dc0`
- `0x1400083d0`
- `0x14000931c`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x1400093c8`
- `ADVAPI32!RegEnumKeyExW` at `0x1400093c8`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open(hKey, *this, a2, 0x2001Fu);
  if ( !v4 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey[0], 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_7;
    }
    ATL::CRegKey::Close(hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close(hKey);
  return v4;
}

```

## disassembly

```asm
0x14000931c  mov     [rsp-8+arg_10], rbx
0x140009321  push    rbp
0x140009322  push    rsi
0x140009323  push    rdi
0x140009324  lea     rbp, [rsp-180h]
0x14000932c  sub     rsp, 280h
0x140009333  mov     rax, cs:__security_cookie
0x14000933a  xor     rax, rsp
0x14000933d  mov     [rbp+190h+var_20], rax
0x140009344  mov     rsi, rdx
0x140009347  mov     [rsp+290h+hKey], 0
0x140009350  mov     r8, rdx; lpSubKey
0x140009353  mov     [rsp+290h+var_240], 0
0x14000935c  mov     rdx, [rcx]; hKey
0x14000935f  mov     rdi, rcx
0x140009362  lea     rcx, [rsp+290h+hKey]; this
0x140009367  mov     [rsp+290h+var_238], 0
0x140009370  mov     r9d, 2001Fh; unsigned int
0x140009376  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000937b  mov     ebx, eax
0x14000937d  test    eax, eax
0x14000937f  jnz     short loc_1400093FB
0x140009381  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x14000938a  mov     rcx, [rsp+290h+hKey]; hKey
0x14000938f  lea     rax, [rsp+290h+ftLastWriteTime]
0x140009394  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140009399  lea     r9, [rsp+290h+cchName]; lpcchName
0x14000939e  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1400093a7  lea     r8, [rsp+290h+Name]; lpName
0x1400093ac  mov     [rsp+290h+lpClass], 0; lpClass
0x1400093b5  xor     edx, edx; dwIndex
0x1400093b7  mov     [rsp+290h+lpReserved], 0; lpReserved
0x1400093c0  mov     [rsp+290h+cchName], 100h
0x1400093c8  call    cs:__imp_RegEnumKeyExW
0x1400093ce  lea     rcx, [rsp+290h+hKey]; this
0x1400093d3  test    eax, eax
0x1400093d5  jnz     short loc_1400093E9
0x1400093d7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1400093dc  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1400093e1  mov     ebx, eax
0x1400093e3  test    eax, eax
0x1400093e5  jnz     short loc_1400093FB
0x1400093e7  jmp     short loc_14000938A
0x1400093e9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400093ee  mov     rdx, rsi; unsigned __int16 *
0x1400093f1  mov     rcx, rdi; this
0x1400093f4  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1400093f9  mov     ebx, eax
0x1400093fb  lea     rcx, [rsp+290h+hKey]; this
0x140009400  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140009405  mov     eax, ebx
0x140009407  mov     rcx, [rbp+190h+var_20]
0x14000940e  xor     rcx, rsp; StackCookie
0x140009411  call    __security_check_cookie
0x140009416  mov     rbx, [rsp+290h+arg_10]
0x14000941e  add     rsp, 280h
0x140009425  pop     rdi
0x140009426  pop     rsi
0x140009427  pop     rbp
0x140009428  retn
```
