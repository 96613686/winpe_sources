# AipValidateLaunchedProcess(ushort const *,void *,void *)

- ea: `0x18000edf0`
- end: `0x18000efd1`
- name: `?AipValidateLaunchedProcess@@YAKPEBGPEAX1@Z`
- size: `481`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, HANDLE ProcessHandle, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014da0`

## callees

- `0x18000edf0`
- `0x18003d0b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000efb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000efb2`
- `ntdll!NtClose` at `0x18000ef77`
- `ntdll!NtClose` at `0x18000ef77`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18000eefa`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18000ef38`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18000eefa`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18000ef38`
- `ntdll!RtlInitUnicodeString` at `0x18000eeb6`
- `ntdll!RtlInitUnicodeString` at `0x18000eeb6`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x18000eece`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x18000eece`
- `ntdll!NtQueryInformationProcess` at `0x18000ee4a`
- `ntdll!NtQueryInformationProcess` at `0x18000ee93`
- `ntdll!NtQueryInformationProcess` at `0x18000ee4a`
- `ntdll!NtQueryInformationProcess` at `0x18000ee93`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ef5f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ef5f`

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
0x18000edf0  mov     r11, rsp
0x18000edf3  mov     [r11+8], rbx
0x18000edf7  mov     [r11+18h], r8
0x18000edfb  push    rbp
0x18000edfc  push    rsi
0x18000edfd  push    rdi
0x18000edfe  sub     rsp, 60h
0x18000ee02  movdqa  xmm1, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000ee0a  lea     rax, [r8-1]
0x18000ee0e  xor     ebp, ebp
0x18000ee10  xorps   xmm0, xmm0
0x18000ee13  mov     [r11-48h], rbp
0x18000ee17  mov     rdi, rdx
0x18000ee1a  mov     [r11+20h], ebp
0x18000ee1e  mov     rsi, rcx
0x18000ee21  mov     ebx, ebp
0x18000ee23  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x18000ee28  movdqu  xmmword ptr [rsp+78h+hObject], xmm1
0x18000ee2e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ee32  ja      loc_18000EF90
0x18000ee38  lea     r9d, [rbp+8]; ProcessInformationLength
0x18000ee3c  mov     [r11-58h], rbp
0x18000ee40  lea     r8, [r11+18h]; ProcessInformation
0x18000ee44  mov     rcx, rdi; ProcessHandle
0x18000ee47  lea     edx, [rbp+2Ch]; ProcessInformationClass
0x18000ee4a  call    cs:__imp_NtQueryInformationProcess
0x18000ee51  nop     dword ptr [rax+rax+00h]
0x18000ee56  cmp     eax, 0C0000001h
0x18000ee5b  jnz     loc_18000EF5D
0x18000ee61  lea     rcx, [rsp+78h+hObject]; void **
0x18000ee66  call    ?AiOpenWOWStubs@@YAXQEAPEAX@Z; AiOpenWOWStubs(void * * const)
0x18000ee6b  cmp     ebx, 2
0x18000ee6e  jnb     short loc_18000EEAE
0x18000ee70  mov     eax, ebx
0x18000ee72  lea     r8, [rsp+78h+hObject]
0x18000ee77  cmp     qword ptr [r8+rax*8], 0FFFFFFFFFFFFFFFFh
0x18000ee7c  lea     r8, [r8+rax*8]; ProcessInformation
0x18000ee80  jz      short loc_18000EEAA
0x18000ee82  mov     edx, 2Ch ; ','; ProcessInformationClass
0x18000ee87  mov     [rsp+78h+ReturnLength], rbp; ReturnLength
0x18000ee8c  mov     rcx, rdi; ProcessHandle
0x18000ee8f  lea     r9d, [rdx-24h]; ProcessInformationLength
0x18000ee93  call    cs:__imp_NtQueryInformationProcess
0x18000ee9a  nop     dword ptr [rax+rax+00h]
0x18000ee9f  cmp     eax, 0C0000001h
0x18000eea4  jnz     loc_18000EF5D
0x18000eeaa  inc     ebx
0x18000eeac  jmp     short loc_18000EE6B
0x18000eeae  mov     rdx, rsi; SourceString
0x18000eeb1  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18000eeb6  call    cs:__imp_RtlInitUnicodeString
0x18000eebd  nop     dword ptr [rax+rax+00h]
0x18000eec2  lea     r8, [rsp+78h+NewKeyHandle]; NewKeyHandle
0x18000eec7  xor     edx, edx; Wow64
0x18000eec9  lea     rcx, [rsp+78h+DestinationString]; SubKey
0x18000eece  call    cs:__imp_LdrOpenImageFileOptionsKey
0x18000eed5  nop     dword ptr [rax+rax+00h]
0x18000eeda  test    eax, eax
0x18000eedc  js      short loc_18000EF56
0x18000eede  mov     rcx, [rsp+78h+NewKeyHandle]; KeyHandle
0x18000eee3  lea     rdx, ValueName; "Debugger"
0x18000eeea  xor     r9d, r9d; Buffer
0x18000eeed  mov     [rsp+78h+ReturnedLength], rbp; ReturnedLength
0x18000eef2  mov     dword ptr [rsp+78h+ReturnLength], ebp; BufferSize
0x18000eef6  lea     r8d, [r9+1]; Type
0x18000eefa  call    cs:__imp_LdrQueryImageFileKeyOption
0x18000ef01  nop     dword ptr [rax+rax+00h]
0x18000ef06  cmp     eax, 80000005h
0x18000ef0b  jnz     short loc_18000EF11
0x18000ef0d  mov     ebx, ebp
0x18000ef0f  jmp     short loc_18000EF6D
0x18000ef11  mov     rcx, [rsp+78h+NewKeyHandle]; KeyHandle
0x18000ef16  lea     r9, [rsp+78h+Buffer]; Buffer
0x18000ef1e  mov     [rsp+78h+ReturnedLength], rbp; ReturnedLength
0x18000ef23  lea     rdx, aAppexecutional; "AppExecutionAliasRedirect"
0x18000ef2a  mov     r8d, 4; Type
0x18000ef30  mov     dword ptr [rsp+78h+ReturnLength], 4; BufferSize
0x18000ef38  call    cs:__imp_LdrQueryImageFileKeyOption
0x18000ef3f  nop     dword ptr [rax+rax+00h]
0x18000ef44  test    eax, eax
0x18000ef46  js      short loc_18000EF56
0x18000ef48  cmp     [rsp+78h+Buffer], 1
0x18000ef50  jnz     short loc_18000EF56
0x18000ef52  mov     ebx, ebp
0x18000ef54  jmp     short loc_18000EF6D
0x18000ef56  mov     ebx, 5
0x18000ef5b  jmp     short loc_18000EF6D
0x18000ef5d  mov     ecx, eax; Status
0x18000ef5f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000ef66  nop     dword ptr [rax+rax+00h]
0x18000ef6b  mov     ebx, eax
0x18000ef6d  mov     rcx, [rsp+78h+NewKeyHandle]; Handle
0x18000ef72  test    rcx, rcx
0x18000ef75  jz      short loc_18000EF90
0x18000ef77  call    cs:__imp_NtClose
0x18000ef7e  nop     dword ptr [rax+rax+00h]
0x18000ef83  mov     [rsp+78h+NewKeyHandle], rbp
0x18000ef88  nop     dword ptr [rax+rax+00000000h]
0x18000ef90  mov     rcx, [rsp+78h+hObject]; hObject
0x18000ef95  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ef99  jz      short loc_18000EFA7
0x18000ef9b  call    cs:__imp_CloseHandle
0x18000efa2  nop     dword ptr [rax+rax+00h]
0x18000efa7  mov     rcx, [rsp+78h+hObject+8]; hObject
0x18000efac  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000efb0  jz      short loc_18000EFBE
0x18000efb2  call    cs:__imp_CloseHandle
0x18000efb9  nop     dword ptr [rax+rax+00h]
0x18000efbe  mov     eax, ebx
0x18000efc0  mov     rbx, [rsp+78h+arg_0]
0x18000efc8  add     rsp, 60h
0x18000efcc  pop     rdi
0x18000efcd  pop     rsi
0x18000efce  pop     rbp
0x18000efcf  retn
```
