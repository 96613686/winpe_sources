# PCPStorageProvider::IsAppContainer(uchar *)

- ea: `0x1800222b4`
- end: `0x1800223ba`
- name: `?IsAppContainer@PCPStorageProvider@@QEAAJPEAE@Z`
- size: `262`
- prototype: `__int64 __fastcall(PCPStorageProvider *this, bool *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021d14`
- `0x180026b90`
- `0x18005aebc`
- `0x18007f068`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x1800222b4`
- `0x1800223c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002238c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002238c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022368`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022346`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022346`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PCPStorageProvider::IsAppContainer(PCPStorageProvider *this, bool *a2)
{
  unsigned int v3; // edx
  PCPStorageProvider *v4; // rcx
  HANDLE v5; // rbx
  unsigned int v6; // ebx
  signed int LastError; // eax
  _BYTE v9[56]; // [rsp+30h] [rbp-38h] BYREF
  int CallerToken; // [rsp+70h] [rbp+8h] BYREF
  int v11; // [rsp+74h] [rbp+Ch]
  int TokenInformation; // [rsp+78h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+88h] [rbp+20h] BYREF

  v11 = HIDWORD(this);
  CallerToken = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v9, L"PCPStorageProvider::IsAppContainer", &CallerToken);
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( a2 )
  {
    *a2 = 0;
    CallerToken = PCPStorageProvider::GetCallerToken(v4, v3, &TokenHandle);
    v5 = TokenHandle;
    if ( CallerToken >= 0 )
    {
      if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
      {
        *a2 = TokenInformation != 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        CallerToken = LastError;
      }
    }
    if ( v5 )
      CloseHandle(v5);
  }
  else
  {
    CallerToken = -2146893785;
  }
  v6 = CallerToken;
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v9);
  return v6;
}

```

## disassembly

```asm
0x1800222b4  mov     rax, rsp
0x1800222b7  mov     [rax+8], rcx
0x1800222bb  push    rbx
0x1800222bc  push    rdi
0x1800222bd  sub     rsp, 58h
0x1800222c1  mov     rdi, rdx
0x1800222c4  mov     dword ptr [rax+8], 0
0x1800222cb  lea     r8, [rax+8]; int *
0x1800222cf  lea     rdx, aPcpstorageprov_31; "PCPStorageProvider::IsAppContainer"
0x1800222d6  lea     rcx, [rax-38h]; this
0x1800222da  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x1800222df  mov     [rsp+68h+TokenHandle], 0
0x1800222eb  mov     [rsp+68h+TokenInformation], 0
0x1800222f3  mov     [rsp+68h+arg_10], 0
0x1800222fe  test    rdi, rdi
0x180022301  jz      loc_1800223AA
0x180022307  mov     byte ptr [rdi], 0
0x18002230a  lea     r8, [rsp+68h+TokenHandle]; void **
0x180022312  call    ?GetCallerToken@PCPStorageProvider@@QEAAJKPEAPEAX@Z; PCPStorageProvider::GetCallerToken(ulong,void * *)
0x180022317  mov     [rsp+68h+arg_0], eax
0x18002231b  mov     rbx, [rsp+68h+TokenHandle]
0x180022323  test    eax, eax
0x180022325  js      short loc_180022360
0x180022327  lea     rax, [rsp+68h+arg_10]
0x18002232f  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180022334  mov     r9d, 4; TokenInformationLength
0x18002233a  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x18002233f  lea     edx, [r9+19h]; TokenInformationClass
0x180022343  mov     rcx, rbx; TokenHandle
0x180022346  call    cs:__imp_GetTokenInformation
0x18002234d  nop     dword ptr [rax+rax+00h]
0x180022352  test    eax, eax
0x180022354  jz      short loc_18002238C
0x180022356  cmp     [rsp+68h+TokenInformation], 0
0x18002235b  setnz   al
0x18002235e  mov     [rdi], al
0x180022360  test    rbx, rbx
0x180022363  jz      short loc_180022374
0x180022365  mov     rcx, rbx; hObject
0x180022368  call    cs:__imp_CloseHandle
0x18002236f  nop     dword ptr [rax+rax+00h]
0x180022374  mov     ebx, [rsp+68h+arg_0]
0x180022378  lea     rcx, [rsp+68h+var_38]; this
0x18002237d  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180022382  mov     eax, ebx
0x180022384  add     rsp, 58h
0x180022388  pop     rdi
0x180022389  pop     rbx
0x18002238a  retn
0x18002238c  call    cs:__imp_GetLastError
0x180022393  nop     dword ptr [rax+rax+00h]
0x180022398  test    eax, eax
0x18002239a  jle     short loc_1800223A4
0x18002239c  movzx   eax, ax
0x18002239f  or      eax, 80070000h
0x1800223a4  mov     [rsp+68h+arg_0], eax
0x1800223a8  jmp     short loc_180022360
0x1800223aa  mov     [rsp+68h+arg_0], 80090027h
0x1800223b2  jmp     short loc_180022374
0x1800223b4  mov     eax, [rsp+68h+arg_0]
0x1800223b8  jmp     short loc_180022384
```
