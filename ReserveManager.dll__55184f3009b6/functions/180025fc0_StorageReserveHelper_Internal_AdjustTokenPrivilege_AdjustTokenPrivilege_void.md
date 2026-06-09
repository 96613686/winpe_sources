# StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege(void)

- ea: `0x180025fc0`
- end: `0x180026033`
- name: `??1AdjustTokenPrivilege@Internal@StorageReserveHelper@@QEAA@XZ`
- size: `115`
- prototype: `void __fastcall(StorageReserveHelper::Internal::AdjustTokenPrivilege *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027414`

## callees

- `0x180003870`
- `0x180025fc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002601a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002601a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180026007`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180026007`

## pseudocode

```c
void __fastcall StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege(
        StorageReserveHelper::Internal::AdjustTokenPrivilege *this)
{
  HANDLE *v1; // rbx
  LUID v2; // rax
  HANDLE v3; // rcx
  struct _TOKEN_PRIVILEGES v4; // [rsp+30h] [rbp-28h] BYREF

  v1 = (HANDLE *)((char *)this + 16);
  if ( *(_DWORD *)this )
  {
    v2 = *(LUID *)((char *)this + 4);
    v3 = *v1;
    v4.PrivilegeCount = 1;
    v4.Privileges[0].Luid = v2;
    v4.Privileges[0].Attributes = 0;
    AdjustTokenPrivileges(v3, 0, &v4, 0, 0, 0);
  }
  if ( (char *)*v1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*v1);
}

```

## disassembly

```asm
0x180025fc0  mov     r11, rsp
0x180025fc3  push    rbx
0x180025fc4  sub     rsp, 50h
0x180025fc8  mov     rax, cs:__security_cookie
0x180025fcf  xor     rax, rsp
0x180025fd2  mov     [rsp+58h+var_18], rax
0x180025fd7  xor     edx, edx; DisableAllPrivileges
0x180025fd9  lea     rbx, [rcx+10h]
0x180025fdd  cmp     [rcx], edx
0x180025fdf  jz      short loc_18002600D
0x180025fe1  mov     rax, [rcx+4]
0x180025fe5  lea     r8, [r11-28h]; NewState
0x180025fe9  mov     rcx, [rbx]; TokenHandle
0x180025fec  xor     r9d, r9d; BufferLength
0x180025fef  mov     [rsp+58h+var_28], 1
0x180025ff7  mov     [r11-24h], rax
0x180025ffb  mov     [r11-30h], rdx
0x180025fff  mov     [rsp+58h+var_1C], edx
0x180026003  mov     [r11-38h], rdx
0x180026007  call    cs:__imp_AdjustTokenPrivileges
0x18002600d  mov     rcx, [rbx]; hObject
0x180026010  lea     rax, [rcx-1]
0x180026014  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026018  ja      short loc_180026020
0x18002601a  call    cs:__imp_CloseHandle
0x180026020  mov     rcx, [rsp+58h+var_18]
0x180026025  xor     rcx, rsp; StackCookie
0x180026028  call    __security_check_cookie
0x18002602d  add     rsp, 50h
0x180026031  pop     rbx
0x180026032  retn
```
