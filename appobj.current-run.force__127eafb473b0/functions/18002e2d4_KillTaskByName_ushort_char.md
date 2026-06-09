# KillTaskByName(ushort *,char *)

- ea: `0x18002e2d4`
- end: `0x18002e462`
- name: `?KillTaskByName@@YAJPEAGPEAD@Z`
- size: `398`
- prototype: `__int64 __fastcall(unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x18002cfb8`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x18002e194`
- `0x18002e238`
- `0x18002e2d4`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e376`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e429`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18002e367`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18002e367`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18002e3a6`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18002e3a6`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18002e41c`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18002e41c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e3d7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e3d7`

## pseudocode

```c
__int64 __fastcall KillTaskByName(unsigned __int16 *a1, char *a2)
{
  HANDLE Toolhelp32Snapshot; // rax
  void *v5; // rdi
  signed int LastError; // eax
  signed int v7; // ebx
  DWORD th32ProcessID; // esi
  int v9; // eax
  int v11; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v12[32]; // [rsp+28h] [rbp-D8h] BYREF
  LPCWSTR lpString2; // [rsp+48h] [rbp-B8h]
  int v14; // [rsp+50h] [rbp-B0h]
  __int16 v15; // [rsp+54h] [rbp-ACh]
  int v16; // [rsp+58h] [rbp-A8h]
  PROCESSENTRY32W pe; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v18; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v19[510]; // [rsp+2A2h] [rbp+1A2h] BYREF

  v11 = 0;
  memset_0(&pe, 0, sizeof(pe));
  memset_0(v19, 0, sizeof(v19));
  v14 = 512;
  lpString2 = (LPCWSTR)&v18;
  v15 = 256;
  v16 = 0;
  v18 = 0;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  v5 = Toolhelp32Snapshot;
  if ( Toolhelp32Snapshot != (HANDLE)-1LL )
  {
    pe.dwSize = 568;
    v7 = 0;
    if ( !Process32FirstW(Toolhelp32Snapshot, &pe) )
    {
LABEL_14:
      CloseHandle(v5);
      goto LABEL_15;
    }
    STRU::Copy((STRU *)v12, a1);
    STRU::Append((STRU *)v12, L".EXE");
    while ( 1 )
    {
      if ( !lstrcmpiW(pe.szExeFile, lpString2) )
      {
        th32ProcessID = pe.th32ProcessID;
        if ( !a2 )
          goto LABEL_10;
        v9 = IsDllInProcess(pe.th32ProcessID, a2, &v11);
        if ( v9 < 0 )
          goto LABEL_11;
        if ( v11 )
        {
LABEL_10:
          v9 = KillProcess(th32ProcessID);
          if ( v9 < 0 )
          {
LABEL_11:
            if ( v7 >= 0 )
              v7 = v9;
          }
        }
      }
      if ( !Process32NextW(v5, &pe) )
        goto LABEL_14;
    }
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
  BUFFER::~BUFFER((BUFFER *)v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002e2d4  mov     [rsp-8+arg_10], rbx
0x18002e2d9  mov     [rsp-8+arg_18], rsi
0x18002e2de  push    rbp
0x18002e2df  push    rdi
0x18002e2e0  push    r14
0x18002e2e2  lea     rbp, [rsp-3B0h]
0x18002e2ea  sub     rsp, 4B0h
0x18002e2f1  mov     rax, cs:__security_cookie
0x18002e2f8  xor     rax, rsp
0x18002e2fb  mov     [rbp+3C0h+var_20], rax
0x18002e302  mov     r14, rdx
0x18002e305  mov     [rsp+4C0h+var_4A0], 0
0x18002e30d  mov     rsi, rcx
0x18002e310  xor     edx, edx; Val
0x18002e312  lea     rcx, [rsp+4C0h+pe]; void *
0x18002e317  mov     r8d, 238h; Size
0x18002e31d  call    memset_0
0x18002e322  xor     edx, edx; Val
0x18002e324  lea     rcx, [rbp+3C0h+var_21E]; void *
0x18002e32b  mov     r8d, 1FEh; Size
0x18002e331  call    memset_0
0x18002e336  lea     rax, [rbp+3C0h+var_220]
0x18002e33d  mov     [rsp+4C0h+var_470], 200h
0x18002e345  mov     [rsp+4C0h+lpString2], rax
0x18002e34a  xor     edx, edx; th32ProcessID
0x18002e34c  xor     eax, eax
0x18002e34e  mov     [rsp+4C0h+var_46C], 100h
0x18002e355  mov     [rsp+4C0h+var_468], 0
0x18002e35d  mov     [rbp+3C0h+var_220], ax
0x18002e364  lea     ecx, [rax+2]; dwFlags
0x18002e367  call    cs:__imp_CreateToolhelp32Snapshot
0x18002e36d  mov     rdi, rax
0x18002e370  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e374  jnz     short loc_18002E394
0x18002e376  call    cs:__imp_GetLastError
0x18002e37c  mov     ebx, eax
0x18002e37e  test    eax, eax
0x18002e380  jle     loc_18002E42F
0x18002e386  movzx   ebx, ax
0x18002e389  or      ebx, 80070000h
0x18002e38f  jmp     loc_18002E42F
0x18002e394  lea     rdx, [rsp+4C0h+pe]; lppe
0x18002e399  mov     [rsp+4C0h+pe.dwSize], 238h
0x18002e3a1  mov     rcx, rdi; hSnapshot
0x18002e3a4  xor     ebx, ebx
0x18002e3a6  call    cs:__imp_Process32FirstW
0x18002e3ac  test    eax, eax
0x18002e3ae  jz      short loc_18002E426
0x18002e3b0  mov     rdx, rsi; unsigned __int16 *
0x18002e3b3  lea     rcx, [rsp+4C0h+var_498]; this
0x18002e3b8  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002e3bd  lea     rdx, aExe; ".EXE"
0x18002e3c4  lea     rcx, [rsp+4C0h+var_498]; this
0x18002e3c9  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002e3ce  mov     rdx, [rsp+4C0h+lpString2]; lpString2
0x18002e3d3  lea     rcx, [rbp+3C0h+pe.szExeFile]; lpString1
0x18002e3d7  call    cs:__imp_lstrcmpiW
0x18002e3dd  test    eax, eax
0x18002e3df  jnz     short loc_18002E414
0x18002e3e1  mov     esi, [rsp+4C0h+pe.th32ProcessID]
0x18002e3e5  test    r14, r14
0x18002e3e8  jz      short loc_18002E404
0x18002e3ea  lea     r8, [rsp+4C0h+var_4A0]; int *
0x18002e3ef  mov     rdx, r14; char *
0x18002e3f2  mov     ecx, esi; dwProcessId
0x18002e3f4  call    ?IsDllInProcess@@YAJKPEADPEAH@Z; IsDllInProcess(ulong,char *,int *)
0x18002e3f9  test    eax, eax
0x18002e3fb  js      short loc_18002E40F
0x18002e3fd  cmp     [rsp+4C0h+var_4A0], 0
0x18002e402  jz      short loc_18002E414
0x18002e404  mov     ecx, esi; dwProcessId
0x18002e406  call    ?KillProcess@@YAJK@Z; KillProcess(ulong)
0x18002e40b  test    eax, eax
0x18002e40d  jns     short loc_18002E414
0x18002e40f  test    ebx, ebx
0x18002e411  cmovns  ebx, eax
0x18002e414  lea     rdx, [rsp+4C0h+pe]; lppe
0x18002e419  mov     rcx, rdi; hSnapshot
0x18002e41c  call    cs:__imp_Process32NextW
0x18002e422  test    eax, eax
0x18002e424  jnz     short loc_18002E3CE
0x18002e426  mov     rcx, rdi; hObject
0x18002e429  call    cs:__imp_CloseHandle
0x18002e42f  lea     rcx, [rsp+4C0h+var_498]; this
0x18002e434  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002e439  mov     eax, ebx
0x18002e43b  mov     rcx, [rbp+3C0h+var_20]
0x18002e442  xor     rcx, rsp; StackCookie
0x18002e445  call    __security_check_cookie
0x18002e44a  lea     r11, [rsp+4C0h+var_10]
0x18002e452  mov     rbx, [r11+30h]
0x18002e456  mov     rsi, [r11+38h]
0x18002e45a  mov     rsp, r11
0x18002e45d  pop     r14
0x18002e45f  pop     rdi
0x18002e460  pop     rbp
0x18002e461  retn
```
