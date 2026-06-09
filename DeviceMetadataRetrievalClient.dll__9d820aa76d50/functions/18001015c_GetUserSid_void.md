# _GetUserSid(void *)

- ea: `0x18001015c`
- end: `0x180010313`
- name: `?_GetUserSid@@YAPEAXPEAX@Z`
- size: `439`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fd5c`

## callees

- `0x18001015c`
- `0x1800135cc`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800101cf`
- `KERNEL32!HeapAlloc` at `0x180010264`
- `KERNEL32!HeapAlloc` at `0x1800101cf`
- `KERNEL32!HeapAlloc` at `0x180010264`
- `KERNEL32!GetProcessHeap` at `0x1800101c1`
- `KERNEL32!GetProcessHeap` at `0x180010256`
- `KERNEL32!GetProcessHeap` at `0x1800102b6`
- `KERNEL32!GetProcessHeap` at `0x1800102df`
- `KERNEL32!GetProcessHeap` at `0x1800101c1`
- `KERNEL32!GetProcessHeap` at `0x180010256`
- `KERNEL32!GetProcessHeap` at `0x1800102b6`
- `KERNEL32!GetProcessHeap` at `0x1800102df`
- `KERNEL32!SetLastError` at `0x1800102f7`
- `KERNEL32!SetLastError` at `0x1800102f7`
- `KERNEL32!HeapFree` at `0x1800102c4`
- `KERNEL32!HeapFree` at `0x1800102ed`
- `KERNEL32!HeapFree` at `0x1800102c4`
- `KERNEL32!HeapFree` at `0x1800102ed`
- `KERNEL32!GetLastError` at `0x18001019f`
- `KERNEL32!GetLastError` at `0x180010207`
- `KERNEL32!GetLastError` at `0x18001019f`
- `KERNEL32!GetLastError` at `0x180010207`
- `ADVAPI32!CopySid` at `0x18001027f`
- `ADVAPI32!CopySid` at `0x18001027f`
- `ADVAPI32!GetTokenInformation` at `0x18001018d`
- `ADVAPI32!GetTokenInformation` at `0x1800101fd`
- `ADVAPI32!GetTokenInformation` at `0x18001018d`
- `ADVAPI32!GetTokenInformation` at `0x1800101fd`
- `ADVAPI32!IsValidSid` at `0x180010221`
- `ADVAPI32!IsValidSid` at `0x180010233`
- `ADVAPI32!IsValidSid` at `0x180010292`
- `ADVAPI32!IsValidSid` at `0x1800102a4`
- `ADVAPI32!IsValidSid` at `0x180010221`
- `ADVAPI32!IsValidSid` at `0x180010233`
- `ADVAPI32!IsValidSid` at `0x180010292`
- `ADVAPI32!IsValidSid` at `0x1800102a4`
- `ADVAPI32!GetLengthSid` at `0x180010245`
- `ADVAPI32!GetLengthSid` at `0x180010245`

## pseudocode

```c
void *__fastcall _GetUserSid(HANDLE TokenHandle)
{
  void *v1; // rdi
  DWORD LastError; // ebx
  DWORD v4; // ebp
  HANDLE ProcessHeap; // rax
  PSID *v6; // rsi
  DWORD LengthSid; // eax
  SIZE_T v8; // rbp
  HANDLE v9; // rax
  void *v10; // rax
  int v11; // ebp
  HANDLE v12; // rax
  HANDLE v13; // rax
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(dwBytes) = 0;
  v1 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&dwBytes) )
  {
    LastError = 87;
    goto LABEL_32;
  }
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v4 = dwBytes;
    if ( !(_DWORD)dwBytes )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v4 = dwBytes;
    }
    ProcessHeap = GetProcessHeap();
    v6 = (PSID *)HeapAlloc(ProcessHeap, 0, v4);
    if ( !v6 )
    {
      LastError = 8;
      goto LABEL_32;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v6, v4, (PDWORD)&dwBytes) )
    {
      if ( !*v6 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( !IsValidSid(*v6) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( !IsValidSid(*v6) )
      {
        LastError = 13;
        goto LABEL_26;
      }
      LengthSid = GetLengthSid(*v6);
      v8 = LengthSid;
      if ( !LengthSid )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v9 = GetProcessHeap();
      v10 = HeapAlloc(v9, 0, v8);
      v1 = v10;
      if ( !v10 )
      {
        LastError = 8;
        goto LABEL_26;
      }
      if ( CopySid(v8, v10, *v6) )
      {
        v11 = 0;
        if ( !IsValidSid(v1) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( !IsValidSid(v1) )
          v11 = 13;
        LastError = v11;
        goto LABEL_26;
      }
    }
    LastError = GetLastError();
LABEL_26:
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v6);
  }
  if ( LastError )
  {
    if ( v1 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v1);
      v1 = 0;
    }
  }
  else if ( !v1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
LABEL_32:
  SetLastError(LastError);
  return v1;
}

```

## disassembly

```asm
0x18001015c  mov     rax, rsp
0x18001015f  mov     [rax+8], rbx
0x180010163  mov     [rax+18h], rbp
0x180010167  push    rsi
0x180010168  push    rdi
0x180010169  push    r14
0x18001016b  sub     rsp, 30h
0x18001016f  mov     dword ptr [rax+10h], 0
0x180010176  lea     rax, [rax+10h]
0x18001017a  xor     edi, edi
0x18001017c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180010181  xor     r9d, r9d; TokenInformationLength
0x180010184  xor     r8d, r8d; TokenInformation
0x180010187  mov     r14, rcx
0x18001018a  lea     edx, [rdi+1]; TokenInformationClass
0x18001018d  call    cs:__imp_GetTokenInformation
0x180010193  test    eax, eax
0x180010195  jz      short loc_18001019F
0x180010197  lea     ebx, [rdi+57h]
0x18001019a  jmp     loc_1800102F5
0x18001019f  call    cs:__imp_GetLastError
0x1800101a5  mov     ebx, eax
0x1800101a7  cmp     eax, 7Ah ; 'z'
0x1800101aa  jnz     loc_1800102CA
0x1800101b0  mov     ebp, dword ptr [rsp+48h+dwBytes]
0x1800101b4  test    ebp, ebp
0x1800101b6  jnz     short loc_1800101C1
0x1800101b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800101bd  mov     ebp, dword ptr [rsp+48h+dwBytes]
0x1800101c1  call    cs:__imp_GetProcessHeap
0x1800101c7  mov     r8d, ebp; dwBytes
0x1800101ca  xor     edx, edx; dwFlags
0x1800101cc  mov     rcx, rax; hHeap
0x1800101cf  call    cs:__imp_HeapAlloc
0x1800101d5  mov     rsi, rax
0x1800101d8  test    rax, rax
0x1800101db  jnz     short loc_1800101E5
0x1800101dd  lea     ebx, [rax+8]
0x1800101e0  jmp     loc_1800102F5
0x1800101e5  lea     rax, [rsp+48h+dwBytes]
0x1800101ea  mov     r9d, ebp; TokenInformationLength
0x1800101ed  mov     r8, rsi; TokenInformation
0x1800101f0  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800101f5  mov     edx, 1; TokenInformationClass
0x1800101fa  mov     rcx, r14; TokenHandle
0x1800101fd  call    cs:__imp_GetTokenInformation
0x180010203  test    eax, eax
0x180010205  jnz     short loc_180010214
0x180010207  call    cs:__imp_GetLastError
0x18001020d  mov     ebx, eax
0x18001020f  jmp     loc_1800102B6
0x180010214  cmp     [rsi], rdi
0x180010217  jnz     short loc_18001021E
0x180010219  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001021e  mov     rcx, [rsi]; pSid
0x180010221  call    cs:__imp_IsValidSid
0x180010227  test    eax, eax
0x180010229  jnz     short loc_180010230
0x18001022b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010230  mov     rcx, [rsi]; pSid
0x180010233  call    cs:__imp_IsValidSid
0x180010239  test    eax, eax
0x18001023b  jnz     short loc_180010242
0x18001023d  lea     ebx, [rax+0Dh]
0x180010240  jmp     short loc_1800102B6
0x180010242  mov     rcx, [rsi]; pSid
0x180010245  call    cs:__imp_GetLengthSid
0x18001024b  mov     ebp, eax
0x18001024d  test    eax, eax
0x18001024f  jnz     short loc_180010256
0x180010251  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010256  call    cs:__imp_GetProcessHeap
0x18001025c  mov     r8, rbp; dwBytes
0x18001025f  xor     edx, edx; dwFlags
0x180010261  mov     rcx, rax; hHeap
0x180010264  call    cs:__imp_HeapAlloc
0x18001026a  mov     rdi, rax
0x18001026d  test    rax, rax
0x180010270  jnz     short loc_180010277
0x180010272  lea     ebx, [rax+8]
0x180010275  jmp     short loc_1800102B6
0x180010277  mov     r8, [rsi]; pSourceSid
0x18001027a  mov     rdx, rdi; pDestinationSid
0x18001027d  mov     ecx, ebp; nDestinationSidLength
0x18001027f  call    cs:__imp_CopySid
0x180010285  test    eax, eax
0x180010287  jz      loc_180010207
0x18001028d  mov     rcx, rdi; pSid
0x180010290  xor     ebp, ebp
0x180010292  call    cs:__imp_IsValidSid
0x180010298  test    eax, eax
0x18001029a  jnz     short loc_1800102A1
0x18001029c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800102a1  mov     rcx, rdi; pSid
0x1800102a4  call    cs:__imp_IsValidSid
0x1800102aa  mov     ebx, 0Dh
0x1800102af  test    eax, eax
0x1800102b1  cmovz   ebp, ebx
0x1800102b4  mov     ebx, ebp
0x1800102b6  call    cs:__imp_GetProcessHeap
0x1800102bc  mov     r8, rsi; lpMem
0x1800102bf  xor     edx, edx; dwFlags
0x1800102c1  mov     rcx, rax; hHeap
0x1800102c4  call    cs:__imp_HeapFree
0x1800102ca  test    ebx, ebx
0x1800102cc  jnz     short loc_1800102DA
0x1800102ce  test    rdi, rdi
0x1800102d1  jnz     short loc_1800102F5
0x1800102d3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800102d8  jmp     short loc_1800102F5
0x1800102da  test    rdi, rdi
0x1800102dd  jz      short loc_1800102F5
0x1800102df  call    cs:__imp_GetProcessHeap
0x1800102e5  mov     r8, rdi; lpMem
0x1800102e8  xor     edx, edx; dwFlags
0x1800102ea  mov     rcx, rax; hHeap
0x1800102ed  call    cs:__imp_HeapFree
0x1800102f3  xor     edi, edi
0x1800102f5  mov     ecx, ebx; dwErrCode
0x1800102f7  call    cs:__imp_SetLastError
0x1800102fd  mov     rbx, [rsp+48h+arg_0]
0x180010302  mov     rax, rdi
0x180010305  mov     rbp, [rsp+48h+arg_10]
0x18001030a  add     rsp, 30h
0x18001030e  pop     r14
0x180010310  pop     rdi
0x180010311  pop     rsi
0x180010312  retn
```
