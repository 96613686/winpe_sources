# CreateUserBoundaryDescriptor(void *,ushort const *)

- ea: `0x18000fbdc`
- end: `0x18000fd53`
- name: `?CreateUserBoundaryDescriptor@@YAPEAXPEAXPEBG@Z`
- size: `375`
- prototype: `void *__fastcall(PSID RequiredSid, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000fd5c`

## callees

- `0x180002f2c`
- `0x18000fbdc`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000fc89`
- `KERNEL32!HeapAlloc` at `0x18000fc89`
- `KERNEL32!GetProcessHeap` at `0x18000fc7b`
- `KERNEL32!GetProcessHeap` at `0x18000fd14`
- `KERNEL32!GetProcessHeap` at `0x18000fc7b`
- `KERNEL32!GetProcessHeap` at `0x18000fd14`
- `KERNEL32!SetLastError` at `0x18000fd31`
- `KERNEL32!SetLastError` at `0x18000fd31`
- `KERNEL32!HeapFree` at `0x18000fd22`
- `KERNEL32!HeapFree` at `0x18000fd22`
- `KERNEL32!GetLastError` at `0x18000fcee`
- `KERNEL32!GetLastError` at `0x18000fcee`
- `KERNEL32!DeleteBoundaryDescriptor` at `0x18000fd04`
- `KERNEL32!DeleteBoundaryDescriptor` at `0x18000fd04`
- `KERNEL32!CreateBoundaryDescriptorW` at `0x18000fcc9`
- `KERNEL32!CreateBoundaryDescriptorW` at `0x18000fcc9`
- `KERNEL32!AddSIDToBoundaryDescriptor` at `0x18000fce4`
- `KERNEL32!AddSIDToBoundaryDescriptor` at `0x18000fce4`

## string_xrefs

- `0x18000fbf5`: `DmrcUserBoundaryDescriptor`
- `0x18000fcaa`: `DmrcUserBoundaryDescriptor`

## pseudocode

```c
HANDLE __fastcall CreateUserBoundaryDescriptor(PSID RequiredSid, const unsigned __int16 *a2)
{
  const wchar_t *v2; // rax
  __int64 v3; // r9
  __int64 v6; // rbp
  __int64 v7; // rcx
  const unsigned __int16 *v8; // rax
  __int64 v9; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v11; // rax
  WCHAR *v12; // rdi
  DWORD LastError; // ebx
  HANDLE v14; // rax
  HANDLE BoundaryDescriptor; // [rsp+70h] [rbp+18h] BYREF

  v2 = L"DmrcUserBoundaryDescriptor";
  BoundaryDescriptor = 0;
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v3;
  }
  while ( v3 );
  v6 = (0x7FFFFFFF - v3) & -(__int64)(v3 != 0);
  if ( !v3 || !a2 )
    goto LABEL_20;
  v7 = 0x7FFFFFFF;
  v8 = a2;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
  if ( !v7 )
  {
LABEL_20:
    LastError = 87;
    goto LABEL_21;
  }
  ProcessHeap = GetProcessHeap();
  v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2LL * (unsigned int)(v9 + v6 + 2));
  v12 = v11;
  if ( v11 && (int)StringCchPrintfW(v11, v9 + v6 + 2, L"%ws_%ws", L"DmrcUserBoundaryDescriptor", a2) >= 0 )
  {
    BoundaryDescriptor = CreateBoundaryDescriptorW(v12, 0);
    if ( BoundaryDescriptor && (LastError = 0, AddSIDToBoundaryDescriptor(&BoundaryDescriptor, RequiredSid))
      || (LastError = GetLastError()) == 0 )
    {
LABEL_19:
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v12);
      goto LABEL_21;
    }
  }
  else
  {
    LastError = 8;
  }
  if ( BoundaryDescriptor )
  {
    DeleteBoundaryDescriptor(BoundaryDescriptor);
    BoundaryDescriptor = 0;
  }
  if ( v12 )
    goto LABEL_19;
LABEL_21:
  SetLastError(LastError);
  return BoundaryDescriptor;
}

```

## disassembly

```asm
0x18000fbdc  mov     [rsp+arg_0], rbx
0x18000fbe1  mov     [rsp+arg_8], rbp
0x18000fbe6  push    rsi
0x18000fbe7  push    rdi
0x18000fbe8  push    r12
0x18000fbea  push    r14
0x18000fbec  push    r15
0x18000fbee  sub     rsp, 30h
0x18000fbf2  xor     r12d, r12d
0x18000fbf5  lea     rax, aDmrcuserbounda; "DmrcUserBoundaryDescriptor"
0x18000fbfc  mov     r8d, 7FFFFFFFh
0x18000fc02  mov     [rsp+58h+BoundaryDescriptor], r12
0x18000fc07  mov     r9d, r8d
0x18000fc0a  mov     r14, rdx
0x18000fc0d  mov     r15, rcx
0x18000fc10  cmp     [rax], r12w
0x18000fc14  jz      short loc_18000FC20
0x18000fc16  add     rax, 2
0x18000fc1a  sub     r9, 1
0x18000fc1e  jnz     short loc_18000FC10
0x18000fc20  mov     rcx, r8
0x18000fc23  mov     rax, r9
0x18000fc26  sub     rcx, r9
0x18000fc29  neg     rax
0x18000fc2c  sbb     rbp, rbp
0x18000fc2f  and     rbp, rcx
0x18000fc32  test    r9, r9
0x18000fc35  jz      loc_18000FD2A
0x18000fc3b  test    r14, r14
0x18000fc3e  jz      loc_18000FD2A
0x18000fc44  mov     rcx, r8
0x18000fc47  mov     rax, r14
0x18000fc4a  cmp     [rax], r12w
0x18000fc4e  jz      short loc_18000FC5A
0x18000fc50  add     rax, 2
0x18000fc54  sub     rcx, 1
0x18000fc58  jnz     short loc_18000FC4A
0x18000fc5a  sub     r8, rcx
0x18000fc5d  mov     rax, rcx
0x18000fc60  neg     rax
0x18000fc63  sbb     rsi, rsi
0x18000fc66  and     rsi, r8
0x18000fc69  test    rcx, rcx
0x18000fc6c  jz      loc_18000FD2A
0x18000fc72  lea     ebx, [rsi+rbp]
0x18000fc75  add     ebx, 2
0x18000fc78  add     rbx, rbx
0x18000fc7b  call    cs:__imp_GetProcessHeap
0x18000fc81  mov     r8, rbx; dwBytes
0x18000fc84  xor     edx, edx; dwFlags
0x18000fc86  mov     rcx, rax; hHeap
0x18000fc89  call    cs:__imp_HeapAlloc
0x18000fc8f  mov     rdi, rax
0x18000fc92  test    rax, rax
0x18000fc95  jnz     short loc_18000FC9E
0x18000fc97  mov     ebx, 8
0x18000fc9c  jmp     short loc_18000FCFA
0x18000fc9e  lea     rdx, [rbp+2]
0x18000fca2  mov     [rsp+58h+var_38], r14
0x18000fca7  add     rdx, rsi; unsigned __int64
0x18000fcaa  lea     r9, aDmrcuserbounda; "DmrcUserBoundaryDescriptor"
0x18000fcb1  lea     r8, aWsWs; "%ws_%ws"
0x18000fcb8  mov     rcx, rdi; unsigned __int16 *
0x18000fcbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fcc0  test    eax, eax
0x18000fcc2  js      short loc_18000FC97
0x18000fcc4  xor     edx, edx; Flags
0x18000fcc6  mov     rcx, rdi; Name
0x18000fcc9  call    cs:__imp_CreateBoundaryDescriptorW
0x18000fccf  mov     [rsp+58h+BoundaryDescriptor], rax
0x18000fcd4  test    rax, rax
0x18000fcd7  jz      short loc_18000FCEE
0x18000fcd9  mov     rdx, r15; RequiredSid
0x18000fcdc  lea     rcx, [rsp+58h+BoundaryDescriptor]; BoundaryDescriptor
0x18000fce1  mov     ebx, r12d
0x18000fce4  call    cs:__imp_AddSIDToBoundaryDescriptor
0x18000fcea  test    eax, eax
0x18000fcec  jnz     short loc_18000FD14
0x18000fcee  call    cs:__imp_GetLastError
0x18000fcf4  mov     ebx, eax
0x18000fcf6  test    eax, eax
0x18000fcf8  jz      short loc_18000FD14
0x18000fcfa  mov     rcx, [rsp+58h+BoundaryDescriptor]; BoundaryDescriptor
0x18000fcff  test    rcx, rcx
0x18000fd02  jz      short loc_18000FD0F
0x18000fd04  call    cs:__imp_DeleteBoundaryDescriptor
0x18000fd0a  mov     [rsp+58h+BoundaryDescriptor], r12
0x18000fd0f  test    rdi, rdi
0x18000fd12  jz      short loc_18000FD2F
0x18000fd14  call    cs:__imp_GetProcessHeap
0x18000fd1a  mov     r8, rdi; lpMem
0x18000fd1d  xor     edx, edx; dwFlags
0x18000fd1f  mov     rcx, rax; hHeap
0x18000fd22  call    cs:__imp_HeapFree
0x18000fd28  jmp     short loc_18000FD2F
0x18000fd2a  mov     ebx, 57h ; 'W'
0x18000fd2f  mov     ecx, ebx; dwErrCode
0x18000fd31  call    cs:__imp_SetLastError
0x18000fd37  mov     rax, [rsp+58h+BoundaryDescriptor]
0x18000fd3c  mov     rbx, [rsp+58h+arg_0]
0x18000fd41  mov     rbp, [rsp+58h+arg_8]
0x18000fd46  add     rsp, 30h
0x18000fd4a  pop     r15
0x18000fd4c  pop     r14
0x18000fd4e  pop     r12
0x18000fd50  pop     rdi
0x18000fd51  pop     rsi
0x18000fd52  retn
```
