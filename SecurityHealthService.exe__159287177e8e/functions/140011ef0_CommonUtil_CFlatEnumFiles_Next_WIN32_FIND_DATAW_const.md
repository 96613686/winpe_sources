# CommonUtil::CFlatEnumFiles::Next(_WIN32_FIND_DATAW const * *)

- ea: `0x140011ef0`
- end: `0x14001201c`
- name: `?Next@CFlatEnumFiles@CommonUtil@@UEAAJPEAPEBU_WIN32_FIND_DATAW@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CommonUtil::CFlatEnumFiles *__hidden this, const struct _WIN32_FIND_DATAW **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400015f4`
- `0x14000f3ac`
- `0x140011234`
- `0x140011ef0`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x140011f25`
- `KERNEL32!FindNextFileW` at `0x140011f25`
- `KERNEL32!FindFirstFileW` at `0x140011f9a`
- `KERNEL32!FindFirstFileW` at `0x140011f9a`
- `KERNEL32!FindClose` at `0x140011f84`
- `KERNEL32!FindClose` at `0x140011f84`

## pseudocode

```c
__int64 __fastcall CommonUtil::CFlatEnumFiles::Next(CommonUtil::CFlatEnumFiles *this, struct _WIN32_FIND_DATAW **a2)
{
  struct _WIN32_FIND_DATAW *v4; // rbp
  void *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int LastFailure; // ebx
  char *v11; // r9
  const unsigned __int16 *v12; // r8
  void *v13; // rcx
  HANDLE FirstFileW; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  LPCWSTR lpFileName; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = (struct _WIN32_FIND_DATAW *)((char *)this + 40);
  while ( 1 )
  {
    v5 = (void *)*((_QWORD *)this + 2);
    if ( v5 )
    {
      if ( FindNextFileW(v5, v4) )
      {
        LastFailure = 0;
      }
      else
      {
        LastFailure = HrGetLastFailure(v7, v6, v8, v9);
        if ( LastFailure == -2147024878 )
          LastFailure = -2147024878;
      }
      goto LABEL_18;
    }
    v11 = (char *)*((_QWORD *)this + 4);
    v12 = (const unsigned __int16 *)*((_QWORD *)this + 3);
    lpFileName = 0;
    LastFailure = CommonUtil::NewSprintfW((CommonUtil *)&lpFileName, (unsigned __int16 **)L"%ws\\%ws", v12, v11);
    if ( LastFailure < 0 )
      break;
    v13 = (void *)*((_QWORD *)this + 2);
    if ( v13 )
    {
      if ( v13 != (void *)-1LL )
        FindClose(v13);
      *((_QWORD *)this + 2) = 0;
    }
    FirstFileW = FindFirstFileW(lpFileName, v4);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastFailure = HrGetLastFailure(v16, v15, v17, v18);
    }
    else
    {
      *((_QWORD *)this + 2) = FirstFileW;
      LastFailure = 0;
    }
    if ( lpFileName )
      operator delete((void *)lpFileName);
LABEL_18:
    if ( LastFailure == -2147024878 )
    {
      *a2 = 0;
      return 0;
    }
    if ( LastFailure < 0 )
      return (unsigned int)LastFailure;
    if ( (*((_BYTE *)this + 640) & 2) == 0 || (v4->dwFileAttributes & 0x10) == 0 )
    {
      *a2 = v4;
      return 0;
    }
  }
  if ( lpFileName )
    operator delete((void *)lpFileName);
  return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x140011ef0  mov     [rsp+arg_8], rbx
0x140011ef5  mov     [rsp+arg_10], rbp
0x140011efa  push    rsi
0x140011efb  push    rdi
0x140011efc  push    r12
0x140011efe  sub     rsp, 20h
0x140011f02  mov     rsi, rdx
0x140011f05  mov     qword ptr [rdx], 0
0x140011f0c  mov     rdi, rcx
0x140011f0f  lea     rbp, [rcx+28h]
0x140011f13  mov     r12d, 80070012h
0x140011f19  mov     rcx, [rdi+10h]; hFindFile
0x140011f1d  test    rcx, rcx
0x140011f20  jz      short loc_140011F49
0x140011f22  mov     rdx, rbp; lpFindFileData
0x140011f25  call    cs:__imp_FindNextFileW
0x140011f2b  test    eax, eax
0x140011f2d  jnz     short loc_140011F42
0x140011f2f  call    HrGetLastFailure
0x140011f34  cmp     eax, r12d
0x140011f37  mov     ebx, eax
0x140011f39  cmovz   ebx, r12d
0x140011f3d  jmp     loc_140011FCC
0x140011f42  xor     ebx, ebx
0x140011f44  jmp     loc_140011FCC
0x140011f49  mov     r9, [rdi+20h]
0x140011f4d  lea     rdx, aWsWs; "%ws\\%ws"
0x140011f54  mov     r8, [rdi+18h]; unsigned __int16 *
0x140011f58  lea     rcx, [rsp+38h+lpFileName]; this
0x140011f5d  mov     [rsp+38h+lpFileName], 0
0x140011f66  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x140011f6b  mov     ebx, eax
0x140011f6d  test    eax, eax
0x140011f6f  js      loc_140011FF8
0x140011f75  mov     rcx, [rdi+10h]; hFindFile
0x140011f79  test    rcx, rcx
0x140011f7c  jz      short loc_140011F92
0x140011f7e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140011f82  jz      short loc_140011F8A
0x140011f84  call    cs:__imp_FindClose
0x140011f8a  mov     qword ptr [rdi+10h], 0
0x140011f92  mov     rcx, [rsp+38h+lpFileName]; lpFileName
0x140011f97  mov     rdx, rbp; lpFindFileData
0x140011f9a  call    cs:__imp_FindFirstFileW
0x140011fa0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140011fa4  jnz     short loc_140011FB4
0x140011fa6  call    HrGetLastFailure
0x140011fab  mov     ebx, eax
0x140011fad  add     eax, 7FF8FFFEh
0x140011fb2  jmp     short loc_140011FBA
0x140011fb4  mov     [rdi+10h], rax
0x140011fb8  xor     ebx, ebx
0x140011fba  cmp     [rsp+38h+lpFileName], 0
0x140011fc0  jz      short loc_140011FCC
0x140011fc2  mov     rcx, [rsp+38h+lpFileName]; void *
0x140011fc7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011fcc  cmp     ebx, r12d
0x140011fcf  jz      short loc_140011FED
0x140011fd1  test    ebx, ebx
0x140011fd3  js      short loc_140012007
0x140011fd5  test    byte ptr [rdi+280h], 2
0x140011fdc  jz      short loc_140011FE8
0x140011fde  test    byte ptr [rbp+0], 10h
0x140011fe2  jnz     loc_140011F19
0x140011fe8  mov     [rsi], rbp
0x140011feb  jmp     short loc_140011FF4
0x140011fed  mov     qword ptr [rsi], 0
0x140011ff4  xor     eax, eax
0x140011ff6  jmp     short loc_140012009
0x140011ff8  mov     rcx, [rsp+38h+lpFileName]; void *
0x140011ffd  test    rcx, rcx
0x140012000  jz      short loc_140012007
0x140012002  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012007  mov     eax, ebx
0x140012009  mov     rbx, [rsp+38h+arg_8]
0x14001200e  mov     rbp, [rsp+38h+arg_10]
0x140012013  add     rsp, 20h
0x140012017  pop     r12
0x140012019  pop     rdi
0x14001201a  pop     rsi
0x14001201b  retn
```
