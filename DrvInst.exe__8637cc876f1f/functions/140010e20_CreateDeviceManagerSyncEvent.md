# CreateDeviceManagerSyncEvent

- ea: `0x140010e20`
- end: `0x140010f7c`
- name: `CreateDeviceManagerSyncEvent`
- size: `348`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140012258`

## callees

- `0x1400070bc`
- `0x140009794`
- `0x140010e20`
- `0x140010f84`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140010ed7`
- `ntdll!RtlInitUnicodeStringEx` at `0x140010ed7`
- `ntdll!RtlUpcaseUnicodeString` at `0x140010eee`
- `ntdll!RtlUpcaseUnicodeString` at `0x140010eee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f56`
- `DEVRTL!DevRtlWriteTextLog` at `0x140010f47`
- `DEVRTL!DevRtlWriteTextLog` at `0x140010f47`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140010e7d`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140010e7d`

## string_xrefs

- `0x140010f39`: `Unable to create Device Manager sync event. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall CreateDeviceManagerSyncEvent(size_t *a1)
{
  __int64 ThreadLogToken; // rdi
  int v3; // eax
  unsigned int v4; // r11d
  DWORD v5; // ebx
  unsigned int v6; // eax
  WCHAR v7; // cx
  __int64 v8; // rdx
  DWORD v9; // eax
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SourceString[200]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  memset_0(pszDest, 0, 0x208u);
  memset_0(SourceString, 0, sizeof(SourceString));
  DestinationString = 0;
  v11 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  v3 = StringCchCopyW(SourceString, 0xC8u, a1);
  if ( v3 < 0 )
    goto LABEL_2;
  v6 = 0;
  do
  {
    v7 = SourceString[v6];
    if ( !v7 )
      break;
    if ( v7 == 92 )
      SourceString[v6] = 35;
    ++v6;
  }
  while ( v6 < v4 );
  if ( RtlInitUnicodeStringEx(&DestinationString, SourceString) < 0
    || RtlUpcaseUnicodeString(&DestinationString, &DestinationString, 0) < 0 )
  {
    v5 = 13;
    goto LABEL_14;
  }
  v3 = StringCchPrintfW(pszDest, 0x104u, L"Global\\DrvInst_Sync_%ws", SourceString);
  if ( v3 < 0 )
  {
LABEL_2:
    v5 = (unsigned __int16)v3;
  }
  else
  {
    v9 = CreateUserSecuredEvent(pszDest, v8, &v11);
    v5 = v9;
    if ( v9 )
      DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Unable to create Device Manager sync event. Error = 0x%08X", v9);
  }
LABEL_14:
  SetLastError(v5);
  return v11;
}

```

## disassembly

```asm
0x140010e20  push    rbp
0x140010e22  push    rbx
0x140010e23  push    rsi
0x140010e24  push    rdi
0x140010e25  lea     rbp, [rsp-308h]
0x140010e2d  sub     rsp, 408h
0x140010e34  mov     rax, cs:__security_cookie
0x140010e3b  xor     rax, rsp
0x140010e3e  mov     [rbp+320h+var_30], rax
0x140010e45  mov     rbx, rcx
0x140010e48  xor     edx, edx; Val
0x140010e4a  lea     rcx, [rbp+320h+pszDest]; void *
0x140010e51  mov     r8d, 208h; Size
0x140010e57  call    memset_0
0x140010e5c  xor     edx, edx; Val
0x140010e5e  lea     rcx, [rsp+420h+SourceString]; void *
0x140010e63  mov     r8d, 190h; Size
0x140010e69  call    memset_0
0x140010e6e  xorps   xmm0, xmm0
0x140010e71  xor     esi, esi
0x140010e73  movups  xmmword ptr [rsp+420h+DestinationString.Length], xmm0
0x140010e78  mov     [rsp+420h+var_3F0], rsi
0x140010e7d  call    cs:__imp_DevRtlGetThreadLogToken
0x140010e83  mov     r11d, 0C8h
0x140010e89  lea     rcx, [rsp+420h+SourceString]; unsigned __int16 *
0x140010e8e  mov     edx, r11d; unsigned __int64
0x140010e91  mov     r8, rbx; unsigned __int16 *
0x140010e94  mov     rdi, rax
0x140010e97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140010e9c  test    eax, eax
0x140010e9e  jns     short loc_140010EA8
0x140010ea0  movzx   ebx, ax
0x140010ea3  jmp     loc_140010F54
0x140010ea8  mov     eax, esi
0x140010eaa  mov     edx, eax
0x140010eac  movzx   ecx, [rsp+rdx*2+420h+SourceString]
0x140010eb1  test    cx, cx
0x140010eb4  jz      short loc_140010ECD
0x140010eb6  cmp     cx, 5Ch ; '\'
0x140010eba  jnz     short loc_140010EC6
0x140010ebc  mov     ecx, 23h ; '#'
0x140010ec1  mov     [rsp+rdx*2+420h+SourceString], cx
0x140010ec6  inc     eax
0x140010ec8  cmp     eax, r11d
0x140010ecb  jb      short loc_140010EAA
0x140010ecd  lea     rdx, [rsp+420h+SourceString]; SourceString
0x140010ed2  lea     rcx, [rsp+420h+DestinationString]; DestinationString
0x140010ed7  call    cs:__imp_RtlInitUnicodeStringEx
0x140010edd  test    eax, eax
0x140010edf  js      short loc_140010F4F
0x140010ee1  xor     r8d, r8d; AllocateDestinationString
0x140010ee4  lea     rdx, [rsp+420h+DestinationString]; SourceString
0x140010ee9  lea     rcx, [rsp+420h+DestinationString]; DestinationString
0x140010eee  call    cs:__imp_RtlUpcaseUnicodeString
0x140010ef4  test    eax, eax
0x140010ef6  js      short loc_140010F4F
0x140010ef8  lea     r9, [rsp+420h+SourceString]
0x140010efd  mov     edx, 104h; cchDest
0x140010f02  lea     r8, aGlobalDrvinstS_0; "Global\\DrvInst_Sync_%ws"
0x140010f09  lea     rcx, [rbp+320h+pszDest]; pszDest
0x140010f10  call    StringCchPrintfW
0x140010f15  test    eax, eax
0x140010f17  js      short loc_140010EA0
0x140010f19  lea     r8, [rsp+420h+var_3F0]
0x140010f1e  lea     rcx, [rbp+320h+pszDest]; lpName
0x140010f25  call    CreateUserSecuredEvent
0x140010f2a  mov     ebx, eax
0x140010f2c  test    eax, eax
0x140010f2e  jz      short loc_140010F54
0x140010f30  mov     edx, 1
0x140010f35  mov     [rsp+420h+var_400], eax
0x140010f39  lea     r9, aUnableToCreate_1; "Unable to create Device Manager sync ev"...
0x140010f40  mov     rcx, rdi
0x140010f43  lea     r8d, [rdx+1]
0x140010f47  call    cs:__imp_DevRtlWriteTextLog
0x140010f4d  jmp     short loc_140010F54
0x140010f4f  mov     ebx, 0Dh
0x140010f54  mov     ecx, ebx; dwErrCode
0x140010f56  call    cs:__imp_SetLastError
0x140010f5c  mov     rax, [rsp+420h+var_3F0]
0x140010f61  mov     rcx, [rbp+320h+var_30]
0x140010f68  xor     rcx, rsp; StackCookie
0x140010f6b  call    __security_check_cookie
0x140010f70  add     rsp, 408h
0x140010f77  pop     rdi
0x140010f78  pop     rsi
0x140010f79  pop     rbx
0x140010f7a  pop     rbp
0x140010f7b  retn
```
