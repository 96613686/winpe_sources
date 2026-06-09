# AipValidateLaunchedProcess(ushort const *,void *,void *)

- ea: `0x18000ed20`
- end: `0x18000eec4`
- name: `?AipValidateLaunchedProcess@@YAKPEBGPEAX1@Z`
- size: `420`
- prototype: `__int64 __fastcall(PCWSTR SourceString, HANDLE ProcessHandle, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d8fc`

## callees

- `0x18000ed20`
- `0x18003f8e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eeac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eeac`
- `ntdll!NtClose` at `0x18000ee85`
- `ntdll!NtClose` at `0x18000ee85`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18000ee1a`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18000ee52`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18000ee1a`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18000ee52`
- `ntdll!RtlInitUnicodeString` at `0x18000ede0`
- `ntdll!RtlInitUnicodeString` at `0x18000ede0`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x18000edf2`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x18000edf2`
- `ntdll!NtQueryInformationProcess` at `0x18000ed7e`
- `ntdll!NtQueryInformationProcess` at `0x18000edc3`
- `ntdll!NtQueryInformationProcess` at `0x18000ed7e`
- `ntdll!NtQueryInformationProcess` at `0x18000edc3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ee73`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ee73`

## pseudocode

```c
__int64 __fastcall AipValidateLaunchedProcess(PCWSTR SourceString, HANDLE ProcessHandle, char *a3)
{
  ULONG v5; // ebx
  NTSTATUS InformationProcess; // eax
  void *NewKeyHandle; // [rsp+30h] [rbp-48h] BYREF
  HANDLE hObject[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-30h] BYREF
  char *v11; // [rsp+90h] [rbp+18h] BYREF
  int Buffer; // [rsp+98h] [rbp+20h] BYREF

  v11 = a3;
  NewKeyHandle = 0;
  Buffer = 0;
  v5 = 0;
  DestinationString = 0;
  *(__m128i *)hObject = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_18;
  InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessImageFileMapping, &v11, 8u, 0);
  if ( InformationProcess == -1073741823 )
  {
    AiOpenWOWStubs(hObject);
    while ( v5 < 2 )
    {
      if ( hObject[v5] != (HANDLE)-1LL )
      {
        InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessImageFileMapping, &hObject[v5], 8u, 0);
        if ( InformationProcess != -1073741823 )
          goto LABEL_15;
      }
      ++v5;
    }
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( LdrOpenImageFileOptionsKey(&DestinationString, 0, &NewKeyHandle) < 0 )
      goto LABEL_14;
    if ( LdrQueryImageFileKeyOption(NewKeyHandle, L"Debugger", 1u, 0, 0, 0) == -2147483643 )
    {
      v5 = 0;
      goto LABEL_16;
    }
    if ( LdrQueryImageFileKeyOption(NewKeyHandle, L"AppExecutionAliasRedirect", 4u, &Buffer, 4u, 0) >= 0 && Buffer == 1 )
      v5 = 0;
    else
LABEL_14:
      v5 = 5;
  }
  else
  {
LABEL_15:
    v5 = RtlNtStatusToDosErrorNoTeb(InformationProcess);
  }
LABEL_16:
  if ( NewKeyHandle )
  {
    NtClose(NewKeyHandle);
    NewKeyHandle = 0;
  }
LABEL_18:
  if ( hObject[0] != (HANDLE)-1LL )
    CloseHandle(hObject[0]);
  if ( hObject[1] != (HANDLE)-1LL )
    CloseHandle(hObject[1]);
  return v5;
}

```

## disassembly

```asm
0x18000ed20  mov     r11, rsp
0x18000ed23  mov     [r11+8], rbx
0x18000ed27  mov     [r11+18h], r8
0x18000ed2b  push    rbp
0x18000ed2c  push    rsi
0x18000ed2d  push    rdi
0x18000ed2e  sub     rsp, 60h
0x18000ed32  movdqa  xmm1, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000ed3a  lea     rax, [r8-1]
0x18000ed3e  xor     ebp, ebp
0x18000ed40  xorps   xmm0, xmm0
0x18000ed43  mov     [r11-48h], rbp
0x18000ed47  mov     rdi, rdx
0x18000ed4a  mov     [r11+20h], ebp
0x18000ed4e  mov     rsi, rcx
0x18000ed51  mov     ebx, ebp
0x18000ed53  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x18000ed58  movdqu  xmmword ptr [rsp+78h+hObject], xmm1
0x18000ed5e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ed62  ja      loc_18000EE90
0x18000ed68  mov     r9d, 8; ProcessInformationLength
0x18000ed6e  mov     [r11-58h], rbp
0x18000ed72  lea     r8, [r11+18h]; ProcessInformation
0x18000ed76  mov     edx, 2Ch ; ','; ProcessInformationClass
0x18000ed7b  mov     rcx, rdi; ProcessHandle
0x18000ed7e  call    cs:__imp_NtQueryInformationProcess
0x18000ed84  cmp     eax, 0C0000001h
0x18000ed89  jnz     loc_18000EE71
0x18000ed8f  lea     rcx, [rsp+78h+hObject]; void **
0x18000ed94  call    ?AiOpenWOWStubs@@YAXQEAPEAX@Z; AiOpenWOWStubs(void * * const)
0x18000ed99  cmp     ebx, 2
0x18000ed9c  jnb     short loc_18000EDD8
0x18000ed9e  mov     eax, ebx
0x18000eda0  lea     r8, [rsp+78h+hObject]
0x18000eda5  cmp     qword ptr [r8+rax*8], 0FFFFFFFFFFFFFFFFh
0x18000edaa  lea     r8, [r8+rax*8]; ProcessInformation
0x18000edae  jz      short loc_18000EDD4
0x18000edb0  mov     edx, 2Ch ; ','; ProcessInformationClass
0x18000edb5  mov     [rsp+78h+ReturnLength], rbp; ReturnLength
0x18000edba  mov     r9d, 8; ProcessInformationLength
0x18000edc0  mov     rcx, rdi; ProcessHandle
0x18000edc3  call    cs:__imp_NtQueryInformationProcess
0x18000edc9  cmp     eax, 0C0000001h
0x18000edce  jnz     loc_18000EE71
0x18000edd4  inc     ebx
0x18000edd6  jmp     short loc_18000ED99
0x18000edd8  mov     rdx, rsi; SourceString
0x18000eddb  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18000ede0  call    cs:__imp_RtlInitUnicodeString
0x18000ede6  lea     r8, [rsp+78h+NewKeyHandle]; NewKeyHandle
0x18000edeb  xor     edx, edx; Wow64
0x18000eded  lea     rcx, [rsp+78h+DestinationString]; SubKey
0x18000edf2  call    cs:__imp_LdrOpenImageFileOptionsKey
0x18000edf8  test    eax, eax
0x18000edfa  js      short loc_18000EE6A
0x18000edfc  mov     rcx, [rsp+78h+NewKeyHandle]; KeyHandle
0x18000ee01  lea     rdx, ValueName; "Debugger"
0x18000ee08  mov     [rsp+78h+ReturnedLength], rbp; ReturnedLength
0x18000ee0d  xor     r9d, r9d; Buffer
0x18000ee10  mov     r8d, 1; Type
0x18000ee16  mov     dword ptr [rsp+78h+ReturnLength], ebp; BufferSize
0x18000ee1a  call    cs:__imp_LdrQueryImageFileKeyOption
0x18000ee20  cmp     eax, 80000005h
0x18000ee25  jnz     short loc_18000EE2B
0x18000ee27  mov     ebx, ebp
0x18000ee29  jmp     short loc_18000EE7B
0x18000ee2b  mov     rcx, [rsp+78h+NewKeyHandle]; KeyHandle
0x18000ee30  lea     r9, [rsp+78h+Buffer]; Buffer
0x18000ee38  mov     [rsp+78h+ReturnedLength], rbp; ReturnedLength
0x18000ee3d  lea     rdx, aAppexecutional; "AppExecutionAliasRedirect"
0x18000ee44  mov     r8d, 4; Type
0x18000ee4a  mov     dword ptr [rsp+78h+ReturnLength], 4; BufferSize
0x18000ee52  call    cs:__imp_LdrQueryImageFileKeyOption
0x18000ee58  test    eax, eax
0x18000ee5a  js      short loc_18000EE6A
0x18000ee5c  cmp     [rsp+78h+Buffer], 1
0x18000ee64  jnz     short loc_18000EE6A
0x18000ee66  mov     ebx, ebp
0x18000ee68  jmp     short loc_18000EE7B
0x18000ee6a  mov     ebx, 5
0x18000ee6f  jmp     short loc_18000EE7B
0x18000ee71  mov     ecx, eax; Status
0x18000ee73  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000ee79  mov     ebx, eax
0x18000ee7b  mov     rcx, [rsp+78h+NewKeyHandle]; Handle
0x18000ee80  test    rcx, rcx
0x18000ee83  jz      short loc_18000EE90
0x18000ee85  call    cs:__imp_NtClose
0x18000ee8b  mov     [rsp+78h+NewKeyHandle], rbp
0x18000ee90  mov     rcx, [rsp+78h+hObject]; hObject
0x18000ee95  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ee99  jz      short loc_18000EEA1
0x18000ee9b  call    cs:__imp_CloseHandle
0x18000eea1  mov     rcx, [rsp+78h+hObject+8]; hObject
0x18000eea6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000eeaa  jz      short loc_18000EEB2
0x18000eeac  call    cs:__imp_CloseHandle
0x18000eeb2  mov     eax, ebx
0x18000eeb4  mov     rbx, [rsp+78h+arg_0]
0x18000eebc  add     rsp, 60h
0x18000eec0  pop     rdi
0x18000eec1  pop     rsi
0x18000eec2  pop     rbp
0x18000eec3  retn
```
