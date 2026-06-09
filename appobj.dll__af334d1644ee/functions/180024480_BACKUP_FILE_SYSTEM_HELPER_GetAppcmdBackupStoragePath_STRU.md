# BACKUP_FILE_SYSTEM_HELPER::GetAppcmdBackupStoragePath(STRU *)

- ea: `0x180024480`
- end: `0x180024520`
- name: `?GetAppcmdBackupStoragePath@BACKUP_FILE_SYSTEM_HELPER@@CAJPEAVSTRU@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(struct STRU *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180023208`
- `0x180023474`

## callees

- `0x180001fb0`
- `0x180002e60`
- `0x1800243c8`
- `0x180024480`
- `0x180034d00`

## string_xrefs

- `0x1800244d4`: `%windir%\system32\inetsrv\backup`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::GetAppcmdBackupStoragePath(struct STRU *this)
{
  int v2; // ebx
  _QWORD v4[5]; // [rsp+20h] [rbp-48h] BYREF
  int v5; // [rsp+48h] [rbp-20h]
  __int16 v6; // [rsp+4Ch] [rbp-1Ch]
  int v7; // [rsp+50h] [rbp-18h]

  v4[0] = 0;
  v4[4] = v4;
  v5 = 32;
  v6 = 256;
  v7 = 0;
  if ( !this || *((_DWORD *)this + 12) )
  {
    v2 = -2147024809;
  }
  else
  {
    v2 = BACKUP_FILE_SYSTEM_HELPER::ExpandEnvironmentStringsSTRU(
           L"%windir%\\system32\\inetsrv\\backup",
           (struct STRU *)v4);
    if ( v2 >= 0 )
      v2 = STRU::Copy(this, (const struct STRU *)v4);
  }
  BUFFER::~BUFFER((BUFFER *)v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180024480  mov     r11, rsp
0x180024483  mov     [r11+10h], rbx
0x180024487  push    rdi
0x180024488  sub     rsp, 60h
0x18002448c  mov     rax, cs:__security_cookie
0x180024493  xor     rax, rsp
0x180024496  mov     [rsp+68h+var_10], rax
0x18002449b  mov     qword ptr [r11-48h], 0
0x1800244a3  lea     rax, [r11-48h]
0x1800244a7  mov     [r11-28h], rax
0x1800244ab  mov     rdi, rcx
0x1800244ae  mov     [rsp+68h+var_20], 20h ; ' '
0x1800244b6  mov     [rsp+68h+var_1C], 100h
0x1800244bd  mov     [rsp+68h+var_18], 0
0x1800244c5  test    rcx, rcx
0x1800244c8  jz      short loc_1800244F7
0x1800244ca  cmp     dword ptr [rcx+30h], 0
0x1800244ce  jnz     short loc_1800244F7
0x1800244d0  lea     rdx, [r11-48h]; this
0x1800244d4  lea     rcx, Src; "%windir%\\system32\\inetsrv\\backup"
0x1800244db  call    ?ExpandEnvironmentStringsSTRU@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAVSTRU@@@Z; BACKUP_FILE_SYSTEM_HELPER::ExpandEnvironmentStringsSTRU(ushort const *,STRU *)
0x1800244e0  mov     ebx, eax
0x1800244e2  test    eax, eax
0x1800244e4  js      short loc_1800244FC
0x1800244e6  lea     rdx, [rsp+68h+var_48]; struct STRU *
0x1800244eb  mov     rcx, rdi; this
0x1800244ee  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800244f3  mov     ebx, eax
0x1800244f5  jmp     short loc_1800244FC
0x1800244f7  mov     ebx, 80070057h
0x1800244fc  lea     rcx, [rsp+68h+var_48]; this
0x180024501  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024506  mov     eax, ebx
0x180024508  mov     rcx, [rsp+68h+var_10]
0x18002450d  xor     rcx, rsp; StackCookie
0x180024510  call    __security_check_cookie
0x180024515  mov     rbx, [rsp+68h+arg_8]
0x18002451a  add     rsp, 60h
0x18002451e  pop     rdi
0x18002451f  retn
```
