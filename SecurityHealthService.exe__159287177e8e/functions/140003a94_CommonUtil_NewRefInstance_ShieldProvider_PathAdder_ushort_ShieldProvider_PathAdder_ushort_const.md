# CommonUtil::NewRefInstance<ShieldProvider::PathAdder,ushort *>(ShieldProvider::PathAdder * *,ushort * const &)

- ea: `0x140003a94`
- end: `0x140003bcb`
- name: `??$NewRefInstance@VPathAdder@ShieldProvider@@PEAG@CommonUtil@@YAJPEAPEAVPathAdder@ShieldProvider@@AEBQEAG@Z`
- size: `311`
- prototype: `__int64 __fastcall(PCWSTR *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140004588`

## callees

- `0x1400015f4`
- `0x1400039a4`
- `0x140003a94`
- `0x140006bec`
- `0x14000ea5c`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003b51`
- `KERNEL32!GetLastError` at `0x140003b51`
- `api-ms-win-core-libraryloader-l1-2-0!AddDllDirectory` at `0x140003b42`
- `api-ms-win-core-libraryloader-l1-2-0!AddDllDirectory` at `0x140003b42`

## string_xrefs

- `0x140003b1a`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`
- `0x140003b6f`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`

## pseudocode

```c
__int64 __fastcall CommonUtil::NewRefInstance<ShieldProvider::PathAdder,unsigned short *>(
        PCWSTR *a1,
        unsigned __int16 ***a2)
{
  int v4; // ebx
  const unsigned __int16 *v5; // r8
  char *v6; // rcx
  unsigned __int16 **v8; // rdx
  PCWSTR v9; // rdi
  int v10; // eax
  unsigned int v11; // esi
  unsigned __int64 v12; // rdx
  WCHAR *v13; // rcx
  WCHAR *v14; // rbx
  DLL_DIRECTORY_COOKIE v15; // rax
  unsigned __int64 v16; // rdx
  signed int LastError; // eax
  char *v18; // rcx
  int v19; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PCWSTR NewDirectory; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  NewDirectory = 0;
  v4 = CommonUtil::CreateNewRefObject<ShieldProvider::PathAdder>(&NewDirectory);
  if ( v4 < 0 )
  {
    if ( NewDirectory )
    {
      v6 = (char *)NewDirectory + *(int *)(*(_QWORD *)NewDirectory + 4LL);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    }
    return (unsigned int)v4;
  }
  v8 = *a2;
  v9 = NewDirectory;
  if ( !v8 )
  {
LABEL_21:
    *a1 = v9;
    return 0;
  }
  NewDirectory = 0;
  v10 = CommonUtil::UtilExpandEnvironmentStrings((CommonUtil *)&NewDirectory, v8, v5);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldproviderutil.cpp",
      (const char *)(unsigned int)v10,
      v19);
    v13 = (WCHAR *)NewDirectory;
    if ( NewDirectory )
      goto LABEL_15;
    goto LABEL_16;
  }
  v14 = (WCHAR *)NewDirectory;
  v15 = AddDllDirectory(NewDirectory);
  *((_QWORD *)v9 + 2) = v15;
  if ( v15 )
    goto LABEL_19;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( (v11 & 0x80000000) == 0 )
  {
LABEL_19:
    if ( v14 )
      operator delete(v14, v16);
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3D,
    (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldproviderutil.cpp",
    (const char *)v11,
    v19);
  if ( v14 )
  {
    v13 = v14;
LABEL_15:
    operator delete(v13, v12);
  }
LABEL_16:
  if ( v9 )
  {
    v18 = (char *)v9 + *(int *)(*(_QWORD *)v9 + 4LL);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 8LL))(v18);
  }
  return v11;
}

```

## disassembly

```asm
0x140003a94  push    rbx
0x140003a96  push    rsi
0x140003a97  push    rdi
0x140003a98  push    r14
0x140003a9a  sub     rsp, 28h
0x140003a9e  mov     r14, rcx
0x140003aa1  mov     qword ptr [rcx], 0
0x140003aa8  lea     rcx, [rsp+48h+NewDirectory]
0x140003aad  mov     [rsp+48h+NewDirectory], 0
0x140003ab6  mov     rdi, rdx
0x140003ab9  call    ??$CreateNewRefObject@VPathAdder@ShieldProvider@@@CommonUtil@@YAJPEAPEAVPathAdder@ShieldProvider@@@Z; CommonUtil::CreateNewRefObject<ShieldProvider::PathAdder>(ShieldProvider::PathAdder * *)
0x140003abe  mov     ebx, eax
0x140003ac0  test    eax, eax
0x140003ac2  jns     short loc_140003AEB
0x140003ac4  mov     rcx, [rsp+48h+NewDirectory]
0x140003ac9  test    rcx, rcx
0x140003acc  jz      short loc_140003AE4
0x140003ace  mov     rdx, [rcx]
0x140003ad1  movsxd  r8, dword ptr [rdx+4]
0x140003ad5  add     rcx, r8
0x140003ad8  mov     rdx, [rcx]
0x140003adb  mov     rax, [rdx+8]
0x140003adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ae4  mov     eax, ebx
0x140003ae6  jmp     loc_140003BC1
0x140003aeb  mov     rdx, [rdi]; unsigned __int16 **
0x140003aee  mov     rdi, [rsp+48h+NewDirectory]
0x140003af3  test    rdx, rdx
0x140003af6  jz      loc_140003BBC
0x140003afc  lea     rcx, [rsp+48h+NewDirectory]; this
0x140003b01  mov     [rsp+48h+NewDirectory], 0
0x140003b0a  call    ?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::UtilExpandEnvironmentStrings(ushort * *,ushort const *)
0x140003b0f  mov     esi, eax
0x140003b11  test    eax, eax
0x140003b13  jns     short loc_140003B3A
0x140003b15  mov     rcx, [rsp+48h]; this
0x140003b1a  lea     r8, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\s"...
0x140003b21  mov     r9d, eax; char *
0x140003b24  mov     edx, 39h ; '9'; void *
0x140003b29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b2e  mov     rcx, [rsp+48h+NewDirectory]
0x140003b33  test    rcx, rcx
0x140003b36  jz      short loc_140003B90
0x140003b38  jmp     short loc_140003B8B
0x140003b3a  mov     rbx, [rsp+48h+NewDirectory]
0x140003b3f  mov     rcx, rbx; NewDirectory
0x140003b42  call    cs:__imp_AddDllDirectory
0x140003b48  mov     [rdi+10h], rax
0x140003b4c  test    rax, rax
0x140003b4f  jnz     short loc_140003BAF
0x140003b51  call    cs:__imp_GetLastError
0x140003b57  mov     esi, eax
0x140003b59  test    eax, eax
0x140003b5b  jle     short loc_140003B66
0x140003b5d  movzx   esi, ax
0x140003b60  or      esi, 80070000h
0x140003b66  test    esi, esi
0x140003b68  jns     short loc_140003BAF
0x140003b6a  mov     rcx, [rsp+48h]; this
0x140003b6f  lea     r8, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\s"...
0x140003b76  mov     r9d, esi; char *
0x140003b79  mov     edx, 3Dh ; '='; void *
0x140003b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b83  test    rbx, rbx
0x140003b86  jz      short loc_140003B90
0x140003b88  mov     rcx, rbx; void *
0x140003b8b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003b90  test    rdi, rdi
0x140003b93  jz      short loc_140003BAB
0x140003b95  mov     rcx, [rdi]
0x140003b98  movsxd  rcx, dword ptr [rcx+4]
0x140003b9c  add     rcx, rdi
0x140003b9f  mov     rdx, [rcx]
0x140003ba2  mov     rax, [rdx+8]
0x140003ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bab  mov     eax, esi
0x140003bad  jmp     short loc_140003BC1
0x140003baf  test    rbx, rbx
0x140003bb2  jz      short loc_140003BBC
0x140003bb4  mov     rcx, rbx; void *
0x140003bb7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003bbc  mov     [r14], rdi
0x140003bbf  xor     eax, eax
0x140003bc1  add     rsp, 28h
0x140003bc5  pop     r14
0x140003bc7  pop     rdi
0x140003bc8  pop     rsi
0x140003bc9  pop     rbx
0x140003bca  retn
```
