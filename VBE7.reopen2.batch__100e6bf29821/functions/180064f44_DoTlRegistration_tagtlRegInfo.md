# _DoTlRegistration(tagtlRegInfo *)

- ea: `0x180064f44`
- end: `0x18006523d`
- name: `?_DoTlRegistration@@YAJPEAUtagtlRegInfo@@@Z`
- size: `761`
- prototype: `__int64 __fastcall(struct tagtlRegInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180063ad4`

## callees

- `0x18001606c`
- `0x180059120`
- `0x18005b0d4`
- `0x180064f44`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x180064fbb`
- `KERNEL32!lstrlenA` at `0x180064fc7`
- `KERNEL32!lstrlenA` at `0x180064fd7`
- `KERNEL32!lstrlenA` at `0x180064fe2`
- `KERNEL32!lstrlenA` at `0x180065085`
- `KERNEL32!lstrlenA` at `0x1800650b4`
- `KERNEL32!lstrlenA` at `0x1800650fd`
- `KERNEL32!lstrlenA` at `0x180065172`
- `KERNEL32!lstrlenA` at `0x180064fbb`
- `KERNEL32!lstrlenA` at `0x180064fc7`
- `KERNEL32!lstrlenA` at `0x180064fd7`
- `KERNEL32!lstrlenA` at `0x180064fe2`
- `KERNEL32!lstrlenA` at `0x180065085`
- `KERNEL32!lstrlenA` at `0x1800650b4`
- `KERNEL32!lstrlenA` at `0x1800650fd`
- `KERNEL32!lstrlenA` at `0x180065172`
- `KERNEL32!lstrcpyA` at `0x180064f9d`
- `KERNEL32!lstrcpyA` at `0x180064f9d`
- `KERNEL32!lstrcatA` at `0x180064fb2`
- `KERNEL32!lstrcatA` at `0x180064fb2`
- `USER32!wsprintfA` at `0x18006504b`
- `USER32!wsprintfA` at `0x1800650f2`
- `USER32!wsprintfA` at `0x18006513b`
- `USER32!wsprintfA` at `0x18006504b`
- `USER32!wsprintfA` at `0x1800650f2`
- `USER32!wsprintfA` at `0x18006513b`
- `ADVAPI32!RegSetValueA` at `0x1800650a0`
- `ADVAPI32!RegSetValueA` at `0x1800650d1`
- `ADVAPI32!RegSetValueA` at `0x18006511b`
- `ADVAPI32!RegSetValueA` at `0x18006518f`
- `ADVAPI32!RegSetValueA` at `0x1800650a0`
- `ADVAPI32!RegSetValueA` at `0x1800650d1`
- `ADVAPI32!RegSetValueA` at `0x18006511b`
- `ADVAPI32!RegSetValueA` at `0x18006518f`
- `ADVAPI32!RegCloseKey` at `0x1800651a0`
- `ADVAPI32!RegCloseKey` at `0x1800651b6`
- `ADVAPI32!RegCloseKey` at `0x1800651cc`
- `ADVAPI32!RegCloseKey` at `0x1800651e7`
- `ADVAPI32!RegCloseKey` at `0x1800651f7`
- `ADVAPI32!RegCloseKey` at `0x180065207`
- `ADVAPI32!RegCloseKey` at `0x1800651a0`
- `ADVAPI32!RegCloseKey` at `0x1800651b6`
- `ADVAPI32!RegCloseKey` at `0x1800651cc`
- `ADVAPI32!RegCloseKey` at `0x1800651e7`
- `ADVAPI32!RegCloseKey` at `0x1800651f7`
- `ADVAPI32!RegCloseKey` at `0x180065207`

## pseudocode

```c
LSTATUS __fastcall _DoTlRegistration(struct tagtlRegInfo *a1)
{
  __int64 v2; // rdi
  int v3; // ebx
  int v4; // ebx
  int v5; // eax
  LSTATUS v6; // edi
  HKEY v7; // rax
  HKEY v8; // rbx
  HKEY v9; // rax
  DWORD cbData; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  HKEY v13; // rbx
  HKEY v14; // rax
  DWORD v15; // eax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  LSTATUS result; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v20; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v21; // [rsp+40h] [rbp-C0h] BYREF
  CHAR v22[40]; // [rsp+48h] [rbp-B8h] BYREF
  CHAR String1[256]; // [rsp+70h] [rbp-90h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v21 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v20 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  lstrcpyA(String1, szTypeLib);
  lstrcatA(String1, szSep);
  v2 = lstrlenA(szSep);
  v3 = 256 - lstrlenA(szSep);
  v4 = v3 - lstrlenA(szTypeLib);
  v5 = lstrlenA(szTypeLib);
  StringFromGUID2Ansi((const struct _GUID *)a1 + 3, &String1[v2 + v5], v4);
  v6 = FastRegCreateKey(HKEY_CLASSES_ROOT, String1, &v20);
  v7 = v20;
  if ( v6 )
    v7 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v20 = v7;
  if ( v6 )
    goto LABEL_17;
  wsprintfA(v22, "%x.%x", *((unsigned __int16 *)a1 + 34), *((unsigned __int16 *)a1 + 35));
  v8 = hKey;
  v6 = FastRegCreateKey(v20, v22, &hKey);
  v9 = hKey;
  if ( v6 )
    v9 = v8;
  hKey = v9;
  if ( v6 )
    goto LABEL_17;
  cbData = lstrlenA(*(LPCSTR *)a1);
  v6 = RegSetValueA(hKey, 0, 1u, *(LPCSTR *)a1, cbData);
  if ( v6 )
    goto LABEL_17;
  v11 = lstrlenA(*((LPCSTR *)a1 + 2));
  v6 = RegSetValueA(hKey, aHelpdir_0, 1u, *((LPCSTR *)a1 + 2), v11);
  if ( v6 )
    goto LABEL_17;
  wsprintfA(String1, "%x", *((unsigned __int16 *)a1 + 36));
  v12 = lstrlenA(String1);
  v6 = RegSetValueA(hKey, aFlags_0, 1u, String1, v12);
  if ( v6 )
    goto LABEL_17;
  wsprintfA(String1, "%x", *((_DWORD *)a1 + 16));
  v13 = v21;
  v6 = FastRegCreateKey(hKey, String1, &v21);
  v14 = v21;
  if ( v6 )
    v14 = v13;
  v21 = v14;
  if ( v6
    || (v15 = lstrlenA(*((LPCSTR *)a1 + 1)), (v6 = RegSetValueA(v21, aWin32_1, 1u, *((LPCSTR *)a1 + 1), v15)) != 0)
    || (v16 = RegCloseKey(v21), v21 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL, (v6 = v16) != 0) )
  {
LABEL_17:
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
    goto LABEL_19;
  }
  v17 = RegCloseKey(hKey);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v6 = v17;
  if ( !v17 )
  {
    result = RegCloseKey(v20);
    v20 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v6 = result;
    if ( !result )
      return result;
    goto LABEL_17;
  }
LABEL_19:
  if ( v21 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(v21);
  if ( v20 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(v20);
  return HrFromRegError(v6);
}

```

## disassembly

```asm
0x180064f44  mov     [rsp-8+arg_8], rbx
0x180064f49  mov     [rsp-8+arg_10], rsi
0x180064f4e  mov     [rsp-8+arg_18], rdi
0x180064f53  push    rbp
0x180064f54  push    r14
0x180064f56  push    r15
0x180064f58  lea     rbp, [rsp-80h]
0x180064f5d  mov     eax, 180h
0x180064f62  call    _alloca_probe
0x180064f67  sub     rsp, rax
0x180064f6a  mov     rax, cs:__security_cookie
0x180064f71  xor     rax, rsp
0x180064f74  mov     [rbp+90h+var_20], rax
0x180064f78  or      r15, 0FFFFFFFFFFFFFFFFh
0x180064f7c  mov     rsi, rcx
0x180064f7f  lea     r14, ?szTypeLib@@3PADA; "TypeLib"
0x180064f86  lea     rcx, [rsp+190h+String1]; lpString1
0x180064f8b  mov     rdx, r14; lpString2
0x180064f8e  mov     [rsp+190h+hKey], r15
0x180064f93  mov     [rsp+190h+var_150], r15
0x180064f98  mov     [rsp+190h+var_158], r15
0x180064f9d  call    cs:__imp_lstrcpyA
0x180064fa3  lea     rbx, ?szSep@@3PADA; "\\"
0x180064faa  lea     rcx, [rsp+190h+String1]; lpString1
0x180064faf  mov     rdx, rbx; lpString2
0x180064fb2  call    cs:__imp_lstrcatA
0x180064fb8  mov     rcx, rbx; lpString
0x180064fbb  call    cs:__imp_lstrlenA
0x180064fc1  mov     rcx, rbx; lpString
0x180064fc4  movsxd  rdi, eax
0x180064fc7  call    cs:__imp_lstrlenA
0x180064fcd  mov     ebx, 100h
0x180064fd2  mov     rcx, r14; lpString
0x180064fd5  sub     ebx, eax
0x180064fd7  call    cs:__imp_lstrlenA
0x180064fdd  mov     rcx, r14; lpString
0x180064fe0  sub     ebx, eax
0x180064fe2  call    cs:__imp_lstrlenA
0x180064fe8  lea     rdx, [rsp+190h+String1]
0x180064fed  movsxd  rcx, eax
0x180064ff0  mov     r8d, ebx; int
0x180064ff3  add     rcx, rdi
0x180064ff6  add     rdx, rcx; char *
0x180064ff9  lea     rcx, [rsi+30h]; struct _GUID *
0x180064ffd  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x180065002  mov     rbx, [rsp+190h+var_158]
0x180065007  lea     r8, [rsp+190h+var_158]; HKEY *
0x18006500c  lea     rdx, [rsp+190h+String1]; char *
0x180065011  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180065018  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x18006501d  mov     edi, eax
0x18006501f  mov     rax, [rsp+190h+var_158]
0x180065024  test    edi, edi
0x180065026  cmovnz  rax, rbx
0x18006502a  mov     [rsp+190h+var_158], rax
0x18006502f  jnz     loc_1800651DD
0x180065035  movzx   r9d, word ptr [rsi+46h]
0x18006503a  movzx   r8d, word ptr [rsi+44h]
0x18006503f  lea     rdx, aXX; "%x.%x"
0x180065046  lea     rcx, [rsp+190h+var_148]; LPSTR
0x18006504b  call    cs:__imp_wsprintfA
0x180065051  mov     rcx, [rsp+190h+var_158]; HKEY
0x180065056  mov     rbx, [rsp+190h+hKey]
0x18006505b  lea     r8, [rsp+190h+hKey]; HKEY *
0x180065060  lea     rdx, [rsp+190h+var_148]; char *
0x180065065  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x18006506a  mov     edi, eax
0x18006506c  mov     rax, [rsp+190h+hKey]
0x180065071  test    edi, edi
0x180065073  cmovnz  rax, rbx
0x180065077  mov     [rsp+190h+hKey], rax
0x18006507c  jnz     loc_1800651DD
0x180065082  mov     rcx, [rsi]; lpString
0x180065085  call    cs:__imp_lstrlenA
0x18006508b  mov     r9, [rsi]; lpData
0x18006508e  mov     rcx, [rsp+190h+hKey]; hKey
0x180065093  lea     r14d, [r15+2]
0x180065097  xor     edx, edx; lpSubKey
0x180065099  mov     [rsp+190h+cbData], eax; cbData
0x18006509d  mov     r8d, r14d; dwType
0x1800650a0  call    cs:__imp_RegSetValueA
0x1800650a6  mov     edi, eax
0x1800650a8  test    eax, eax
0x1800650aa  jnz     loc_1800651DD
0x1800650b0  mov     rcx, [rsi+10h]; lpString
0x1800650b4  call    cs:__imp_lstrlenA
0x1800650ba  mov     r9, [rsi+10h]; lpData
0x1800650be  mov     rcx, [rsp+190h+hKey]; hKey
0x1800650c3  lea     rdx, aHelpdir_0; "HelpDir"
0x1800650ca  mov     r8d, r14d; dwType
0x1800650cd  mov     [rsp+190h+cbData], eax; cbData
0x1800650d1  call    cs:__imp_RegSetValueA
0x1800650d7  mov     edi, eax
0x1800650d9  test    eax, eax
0x1800650db  jnz     loc_1800651DD
0x1800650e1  movzx   r8d, word ptr [rsi+48h]
0x1800650e6  lea     rdx, asc_1803A5A08; "%x"
0x1800650ed  lea     rcx, [rsp+190h+String1]; LPSTR
0x1800650f2  call    cs:__imp_wsprintfA
0x1800650f8  lea     rcx, [rsp+190h+String1]; lpString
0x1800650fd  call    cs:__imp_lstrlenA
0x180065103  mov     rcx, [rsp+190h+hKey]; hKey
0x180065108  lea     r9, [rsp+190h+String1]; lpData
0x18006510d  lea     rdx, aFlags_0; "Flags"
0x180065114  mov     r8d, r14d; dwType
0x180065117  mov     [rsp+190h+cbData], eax; cbData
0x18006511b  call    cs:__imp_RegSetValueA
0x180065121  mov     edi, eax
0x180065123  test    eax, eax
0x180065125  jnz     loc_1800651DD
0x18006512b  mov     r8d, [rsi+40h]
0x18006512f  lea     rdx, asc_1803A5A08; "%x"
0x180065136  lea     rcx, [rsp+190h+String1]; LPSTR
0x18006513b  call    cs:__imp_wsprintfA
0x180065141  mov     rcx, [rsp+190h+hKey]; HKEY
0x180065146  mov     rbx, [rsp+190h+var_150]
0x18006514b  lea     r8, [rsp+190h+var_150]; HKEY *
0x180065150  lea     rdx, [rsp+190h+String1]; char *
0x180065155  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x18006515a  mov     edi, eax
0x18006515c  mov     rax, [rsp+190h+var_150]
0x180065161  test    edi, edi
0x180065163  cmovnz  rax, rbx
0x180065167  mov     [rsp+190h+var_150], rax
0x18006516c  jnz     short loc_1800651DD
0x18006516e  mov     rcx, [rsi+8]; lpString
0x180065172  call    cs:__imp_lstrlenA
0x180065178  mov     r9, [rsi+8]; lpData
0x18006517c  mov     rcx, [rsp+190h+var_150]; hKey
0x180065181  lea     rdx, aWin32_1; "win32"
0x180065188  mov     r8d, r14d; dwType
0x18006518b  mov     [rsp+190h+cbData], eax; cbData
0x18006518f  call    cs:__imp_RegSetValueA
0x180065195  mov     edi, eax
0x180065197  test    eax, eax
0x180065199  jnz     short loc_1800651DD
0x18006519b  mov     rcx, [rsp+190h+var_150]; hKey
0x1800651a0  call    cs:__imp_RegCloseKey
0x1800651a6  mov     [rsp+190h+var_150], r15
0x1800651ab  mov     edi, eax
0x1800651ad  test    eax, eax
0x1800651af  jnz     short loc_1800651DD
0x1800651b1  mov     rcx, [rsp+190h+hKey]; hKey
0x1800651b6  call    cs:__imp_RegCloseKey
0x1800651bc  mov     [rsp+190h+hKey], r15
0x1800651c1  mov     edi, eax
0x1800651c3  test    eax, eax
0x1800651c5  jnz     short loc_1800651ED
0x1800651c7  mov     rcx, [rsp+190h+var_158]; hKey
0x1800651cc  call    cs:__imp_RegCloseKey
0x1800651d2  mov     [rsp+190h+var_158], r15
0x1800651d7  mov     edi, eax
0x1800651d9  test    eax, eax
0x1800651db  jz      short loc_180065214
0x1800651dd  mov     rcx, [rsp+190h+hKey]; hKey
0x1800651e2  cmp     rcx, r15
0x1800651e5  jz      short loc_1800651ED
0x1800651e7  call    cs:__imp_RegCloseKey
0x1800651ed  mov     rcx, [rsp+190h+var_150]; hKey
0x1800651f2  cmp     rcx, r15
0x1800651f5  jz      short loc_1800651FD
0x1800651f7  call    cs:__imp_RegCloseKey
0x1800651fd  mov     rcx, [rsp+190h+var_158]; hKey
0x180065202  cmp     rcx, r15
0x180065205  jz      short loc_18006520D
0x180065207  call    cs:__imp_RegCloseKey
0x18006520d  mov     ecx, edi; int
0x18006520f  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x180065214  mov     rcx, [rbp+90h+var_20]
0x180065218  xor     rcx, rsp; StackCookie
0x18006521b  call    __security_check_cookie
0x180065220  lea     r11, [rsp+190h+var_10]
0x180065228  mov     rbx, [r11+28h]
0x18006522c  mov     rsi, [r11+30h]
0x180065230  mov     rdi, [r11+38h]
0x180065234  mov     rsp, r11
0x180065237  pop     r15
0x180065239  pop     r14
0x18006523b  pop     rbp
0x18006523c  retn
```
