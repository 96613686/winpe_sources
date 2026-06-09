# SpCreateMutex(int,ushort const *,ulong)

- ea: `0x14000ede4`
- end: `0x14000eed9`
- name: `?SpCreateMutex@@YAPEAXHPEBGK@Z`
- size: `245`
- prototype: `void *__fastcall(int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140011650`

## callees

- `0x140002d30`
- `0x140007680`
- `0x14000ede4`
- `0x1400125b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000ee82`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000ee82`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14000ee5d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14000ee5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ee30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eea4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ee30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eea4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000eeaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000eeaf`

## pseudocode

```c
HANDLE __fastcall SpCreateMutex(__int64 a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rdx
  const unsigned __int16 *v3; // r8
  int v4; // eax
  DWORD v5; // ecx
  HANDLE MutexW; // rbx
  int i; // edi
  _BYTE v9[8]; // [rsp+20h] [rbp-258h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-250h]
  _WORD v11[272]; // [rsp+40h] [rbp-238h] BYREF

  CSpSecurityAttribute::CSpSecurityAttribute((CSpSecurityAttribute *)v9);
  v4 = PrefixedObjectName::Initialize((PrefixedObjectName *)v11, v2, v3);
  if ( v4 >= 0 )
  {
    MutexW = 0;
    for ( i = 0; i < 100; ++i )
    {
      MutexW = OpenMutexW(0x100000u, 0, (LPCWSTR)((unsigned __int64)v11 & -(__int64)(v11[0] != 0)));
      if ( MutexW )
      {
        SetLastError(0xB7u);
        break;
      }
      MutexW = CreateMutexW(0, 0, (LPCWSTR)((unsigned __int64)v11 & -(__int64)(v11[0] != 0)));
      if ( MutexW || GetLastError() != 5 )
        break;
    }
  }
  else
  {
    v5 = (unsigned __int16)v4;
    if ( (v4 & 0xFFFF0000) != 0x80070000 )
      v5 = v4;
    SetLastError(v5);
    MutexW = 0;
  }
  LocalFree(hMem);
  return MutexW;
}

```

## disassembly

```asm
0x14000ede4  mov     [rsp+arg_0], rbx
0x14000ede9  push    rdi
0x14000edea  sub     rsp, 270h
0x14000edf1  mov     rax, cs:__security_cookie
0x14000edf8  xor     rax, rsp
0x14000edfb  mov     [rsp+278h+var_18], rax
0x14000ee03  lea     rcx, [rsp+278h+var_258]; this
0x14000ee08  call    ??0CSpSecurityAttribute@@QEAA@KK@Z; CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)
0x14000ee0d  lea     rcx, [rsp+278h+var_238]; this
0x14000ee12  call    ?Initialize@PrefixedObjectName@@AEAAJPEBG0@Z; PrefixedObjectName::Initialize(ushort const *,ushort const *)
0x14000ee17  test    eax, eax
0x14000ee19  jns     short loc_14000EE3A
0x14000ee1b  mov     ecx, eax
0x14000ee1d  and     ecx, 0FFFF0000h
0x14000ee23  cmp     ecx, 80070000h
0x14000ee29  movzx   ecx, ax
0x14000ee2c  jz      short loc_14000EE30
0x14000ee2e  mov     ecx, eax; dwErrCode
0x14000ee30  call    cs:__imp_SetLastError
0x14000ee36  xor     ebx, ebx
0x14000ee38  jmp     short loc_14000EEAA
0x14000ee3a  xor     ebx, ebx
0x14000ee3c  xor     edi, edi
0x14000ee3e  cmp     edi, 64h ; 'd'
0x14000ee41  jge     short loc_14000EEAA
0x14000ee43  movzx   eax, [rsp+278h+var_238]
0x14000ee48  mov     ecx, 100000h; dwDesiredAccess
0x14000ee4d  neg     ax
0x14000ee50  lea     rax, [rsp+278h+var_238]
0x14000ee55  sbb     r8, r8
0x14000ee58  xor     edx, edx; bInheritHandle
0x14000ee5a  and     r8, rax; lpName
0x14000ee5d  call    cs:__imp_OpenMutexW
0x14000ee63  mov     rbx, rax
0x14000ee66  test    rax, rax
0x14000ee69  jnz     short loc_14000EE9F
0x14000ee6b  movzx   eax, [rsp+278h+var_238]
0x14000ee70  neg     ax
0x14000ee73  lea     rax, [rsp+278h+var_238]
0x14000ee78  sbb     r8, r8
0x14000ee7b  xor     edx, edx; bInitialOwner
0x14000ee7d  and     r8, rax; lpName
0x14000ee80  xor     ecx, ecx; lpMutexAttributes
0x14000ee82  call    cs:__imp_CreateMutexW
0x14000ee88  mov     rbx, rax
0x14000ee8b  test    rax, rax
0x14000ee8e  jnz     short loc_14000EEAA
0x14000ee90  call    cs:__imp_GetLastError
0x14000ee96  cmp     eax, 5
0x14000ee99  jnz     short loc_14000EEAA
0x14000ee9b  inc     edi
0x14000ee9d  jmp     short loc_14000EE3E
0x14000ee9f  mov     ecx, 0B7h; dwErrCode
0x14000eea4  call    cs:__imp_SetLastError
0x14000eeaa  mov     rcx, [rsp+278h+hMem]; hMem
0x14000eeaf  call    cs:__imp_LocalFree
0x14000eeb5  mov     rax, rbx
0x14000eeb8  mov     rcx, [rsp+278h+var_18]
0x14000eec0  xor     rcx, rsp; StackCookie
0x14000eec3  call    __security_check_cookie
0x14000eec8  mov     rbx, [rsp+278h+arg_0]
0x14000eed0  add     rsp, 270h
0x14000eed7  pop     rdi
0x14000eed8  retn
```
